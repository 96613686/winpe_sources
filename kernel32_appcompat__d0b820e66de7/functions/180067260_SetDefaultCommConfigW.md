# SetDefaultCommConfigW

- ea: `0x180067260`
- end: `0x18006736e`
- name: `SetDefaultCommConfigW`
- size: `270`
- prototype: `BOOL __stdcall(LPCWSTR lpszName, LPCOMMCONFIG lpCC, DWORD dwSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800671c0`

## callees

- `0x18004a024`
- `0x180067260`
- `0x180084010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18006734f`
- `ntdll!RtlSetLastWin32Error` at `0x18008378f`
- `ntdll!RtlSetLastWin32Error` at `0x18006734f`
- `ntdll!RtlSetLastWin32Error` at `0x18008378f`
- `ntdll!RtlFreeHeap` at `0x180067329`
- `ntdll!RtlFreeHeap` at `0x180083765`
- `ntdll!RtlFreeHeap` at `0x180067329`
- `ntdll!RtlFreeHeap` at `0x180083765`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800672c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800672c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006733d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008377b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006733d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008377b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800672a4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800672a4`

## string_xrefs

- `0x1800672bd`: `drvSetDefaultCommConfigW`

## pseudocode

```c
BOOL __stdcall SetDefaultCommConfigW(LPCWSTR lpszName, LPCOMMCONFIG lpCC, DWORD dwSize)
{
  BOOL v6; // esi
  HMODULE v7; // rdi
  ULONG LastErrorValue; // ebx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  __int128 v12; // [rsp+30h] [rbp-48h] BYREF

  v12 = 0;
  v6 = 1;
  v7 = 0;
  LastErrorValue = 0;
  GetFriendlyUi((__int64)lpszName, (__int64)&v12);
  if ( *((_QWORD *)&v12 + 1) )
  {
    LibraryW = LoadLibraryW(*((LPCWSTR *)&v12 + 1));
    v7 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "drvSetDefaultCommConfigW");
      if ( ProcAddress )
      {
        LastErrorValue = ((__int64 (__fastcall *)(LPCWSTR, LPCOMMCONFIG, _QWORD))ProcAddress)(lpszName, lpCC, dwSize);
        goto LABEL_7;
      }
    }
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
  }
  v6 = 0;
LABEL_7:
  if ( *((_QWORD *)&v12 + 1) )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)&v12 + 1));
  if ( v7 )
    FreeLibrary(v7);
  if ( LastErrorValue )
  {
    RtlSetLastWin32Error(LastErrorValue);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180067260  mov     rax, rsp
0x180067263  push    rbx
0x180067264  push    rsi
0x180067265  push    rdi
0x180067266  push    r12
0x180067268  push    r14
0x18006726a  push    r15
0x18006726c  sub     rsp, 48h
0x180067270  mov     r15d, r8d
0x180067273  mov     r12, rdx
0x180067276  mov     r14, rcx
0x180067279  xorps   xmm0, xmm0
0x18006727c  movups  xmmword ptr [rax-48h], xmm0
0x180067280  mov     esi, 1
0x180067285  xor     edi, edi
0x180067287  mov     [rax-50h], rdi
0x18006728b  xor     ebx, ebx
0x18006728d  mov     [rax-58h], ebx
0x180067290  lea     rdx, [rax-48h]
0x180067294  call    GetFriendlyUi
0x180067299  nop
0x18006729a  mov     rcx, [rsp+78h+lpLibFileName]; lpLibFileName
0x18006729f  test    rcx, rcx
0x1800672a2  jz      short loc_18006730B
0x1800672a4  call    cs:__imp_LoadLibraryW
0x1800672ab  nop     dword ptr [rax+rax+00h]
0x1800672b0  mov     rdi, rax
0x1800672b3  mov     [rsp+78h+var_50], rax
0x1800672b8  test    rax, rax
0x1800672bb  jz      short loc_1800672FD
0x1800672bd  lea     rdx, aDrvsetdefaultc; "drvSetDefaultCommConfigW"
0x1800672c4  mov     rcx, rax; hModule
0x1800672c7  call    cs:__imp_GetProcAddress
0x1800672ce  nop     dword ptr [rax+rax+00h]
0x1800672d3  test    rax, rax
0x1800672d6  jnz     short loc_1800672E6
0x1800672d8  mov     ebx, gs:68h
0x1800672e0  mov     [rsp+78h+var_58], ebx
0x1800672e4  jmp     short loc_18006730B
0x1800672e6  mov     r8d, r15d
0x1800672e9  mov     rdx, r12
0x1800672ec  mov     rcx, r14
0x1800672ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800672f4  mov     rbx, rax
0x1800672f7  mov     [rsp+78h+var_58], eax
0x1800672fb  jmp     short loc_18006730D
0x1800672fd  mov     eax, gs:68h
0x180067305  mov     ebx, eax
0x180067307  mov     [rsp+78h+var_58], eax
0x18006730b  xor     esi, esi
0x18006730d  cmp     [rsp+78h+lpLibFileName], 0
0x180067313  jz      short loc_180067335
0x180067315  mov     rcx, gs:60h
0x18006731e  mov     r8, [rsp+78h+lpLibFileName]; P
0x180067323  xor     edx, edx; Flags
0x180067325  mov     rcx, [rcx+30h]; HeapHandle
0x180067329  call    cs:__imp_RtlFreeHeap
0x180067330  nop     dword ptr [rax+rax+00h]
0x180067335  test    rdi, rdi
0x180067338  jz      short loc_180067349
0x18006733a  mov     rcx, rdi; hLibModule
0x18006733d  call    cs:__imp_FreeLibrary
0x180067344  nop     dword ptr [rax+rax+00h]
0x180067349  test    ebx, ebx
0x18006734b  jz      short loc_18006735D
0x18006734d  mov     ecx, ebx; LastError
0x18006734f  call    cs:__imp_RtlSetLastWin32Error
0x180067356  nop     dword ptr [rax+rax+00h]
0x18006735b  xor     esi, esi
0x18006735d  mov     eax, esi
0x18006735f  add     rsp, 48h
0x180067363  pop     r15
0x180067365  pop     r14
0x180067367  pop     r12
0x180067369  pop     rdi
0x18006736a  pop     rsi
0x18006736b  pop     rbx
0x18006736c  retn
0x180083742  push    rbp
0x180083744  sub     rsp, 20h
0x180083748  mov     rbp, rdx
0x18008374b  cmp     qword ptr [rbp+38h], 0
0x180083750  jz      short loc_180083772
0x180083752  mov     rcx, gs:60h
0x18008375b  mov     r8, [rbp+38h]; P
0x18008375f  xor     edx, edx; Flags
0x180083761  mov     rcx, [rcx+30h]; HeapHandle
0x180083765  call    cs:__imp_RtlFreeHeap
0x18008376c  nop     dword ptr [rax+rax+00h]
0x180083771  nop
0x180083772  mov     rcx, [rbp+28h]; hLibModule
0x180083776  test    rcx, rcx
0x180083779  jz      short loc_180083788
0x18008377b  call    cs:__imp_FreeLibrary
0x180083782  nop     dword ptr [rax+rax+00h]
0x180083787  nop
0x180083788  mov     ecx, [rbp+20h]; LastError
0x18008378b  test    ecx, ecx
0x18008378d  jz      short loc_18008379C
0x18008378f  call    cs:__imp_RtlSetLastWin32Error
0x180083796  nop     dword ptr [rax+rax+00h]
0x18008379b  nop
0x18008379c  add     rsp, 20h
0x1800837a0  pop     rbp
0x1800837a1  retn
```
