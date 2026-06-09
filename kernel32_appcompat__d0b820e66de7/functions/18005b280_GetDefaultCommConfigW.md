# GetDefaultCommConfigW

- ea: `0x18005b280`
- end: `0x18005b38e`
- name: `GetDefaultCommConfigW`
- size: `270`
- prototype: `BOOL __stdcall(LPCWSTR lpszName, LPCOMMCONFIG lpCC, LPDWORD lpdwSize)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180067120`

## callees

- `0x18004a024`
- `0x18005b280`
- `0x180067260`
- `0x180084010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18005b36f`
- `ntdll!RtlSetLastWin32Error` at `0x18005b36f`
- `ntdll!RtlFreeHeap` at `0x18005b349`
- `ntdll!RtlFreeHeap` at `0x18005b349`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b2e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b2e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005b35d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005b35d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005b2c4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005b2c4`

## string_xrefs

- `0x18005b2dd`: `drvGetDefaultCommConfigW`

## pseudocode

```c
BOOL __stdcall GetDefaultCommConfigW(LPCWSTR lpszName, LPCOMMCONFIG lpCC, LPDWORD lpdwSize)
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
      ProcAddress = GetProcAddress(LibraryW, "drvGetDefaultCommConfigW");
      if ( ProcAddress )
      {
        LastErrorValue = ((__int64 (__fastcall *)(LPCWSTR, LPCOMMCONFIG, LPDWORD))ProcAddress)(lpszName, lpCC, lpdwSize);
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
0x18005b280  mov     rax, rsp
0x18005b283  push    rbx
0x18005b284  push    rsi
0x18005b285  push    rdi
0x18005b286  push    r12
0x18005b288  push    r14
0x18005b28a  push    r15
0x18005b28c  sub     rsp, 48h
0x18005b290  mov     r15, r8
0x18005b293  mov     r12, rdx
0x18005b296  mov     r14, rcx
0x18005b299  xorps   xmm0, xmm0
0x18005b29c  movups  xmmword ptr [rax-48h], xmm0
0x18005b2a0  mov     esi, 1
0x18005b2a5  xor     edi, edi
0x18005b2a7  mov     [rax-50h], rdi
0x18005b2ab  xor     ebx, ebx
0x18005b2ad  mov     [rax-58h], ebx
0x18005b2b0  lea     rdx, [rax-48h]
0x18005b2b4  call    GetFriendlyUi
0x18005b2b9  nop
0x18005b2ba  mov     rcx, [rsp+78h+lpLibFileName]; lpLibFileName
0x18005b2bf  test    rcx, rcx
0x18005b2c2  jz      short loc_18005B32B
0x18005b2c4  call    cs:__imp_LoadLibraryW
0x18005b2cb  nop     dword ptr [rax+rax+00h]
0x18005b2d0  mov     rdi, rax
0x18005b2d3  mov     [rsp+78h+var_50], rax
0x18005b2d8  test    rax, rax
0x18005b2db  jz      short loc_18005B31D
0x18005b2dd  lea     rdx, aDrvgetdefaultc; "drvGetDefaultCommConfigW"
0x18005b2e4  mov     rcx, rax; hModule
0x18005b2e7  call    cs:__imp_GetProcAddress
0x18005b2ee  nop     dword ptr [rax+rax+00h]
0x18005b2f3  test    rax, rax
0x18005b2f6  jnz     short loc_18005B306
0x18005b2f8  mov     ebx, gs:68h
0x18005b300  mov     [rsp+78h+var_58], ebx
0x18005b304  jmp     short loc_18005B32B
0x18005b306  mov     r8, r15
0x18005b309  mov     rdx, r12
0x18005b30c  mov     rcx, r14
0x18005b30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b314  mov     rbx, rax
0x18005b317  mov     [rsp+78h+var_58], eax
0x18005b31b  jmp     short loc_18005B32D
0x18005b31d  mov     eax, gs:68h
0x18005b325  mov     ebx, eax
0x18005b327  mov     [rsp+78h+var_58], eax
0x18005b32b  xor     esi, esi
0x18005b32d  cmp     [rsp+78h+lpLibFileName], 0
0x18005b333  jz      short loc_18005B355
0x18005b335  mov     rcx, gs:60h
0x18005b33e  mov     r8, [rsp+78h+lpLibFileName]; P
0x18005b343  xor     edx, edx; Flags
0x18005b345  mov     rcx, [rcx+30h]; HeapHandle
0x18005b349  call    cs:__imp_RtlFreeHeap
0x18005b350  nop     dword ptr [rax+rax+00h]
0x18005b355  test    rdi, rdi
0x18005b358  jz      short loc_18005B369
0x18005b35a  mov     rcx, rdi; hLibModule
0x18005b35d  call    cs:__imp_FreeLibrary
0x18005b364  nop     dword ptr [rax+rax+00h]
0x18005b369  test    ebx, ebx
0x18005b36b  jz      short loc_18005B37D
0x18005b36d  mov     ecx, ebx; LastError
0x18005b36f  call    cs:__imp_RtlSetLastWin32Error
0x18005b376  nop     dword ptr [rax+rax+00h]
0x18005b37b  xor     esi, esi
0x18005b37d  mov     eax, esi
0x18005b37f  add     rsp, 48h
0x18005b383  pop     r15
0x18005b385  pop     r14
0x18005b387  pop     r12
0x18005b389  pop     rdi
0x18005b38a  pop     rsi
0x18005b38b  pop     rbx
0x18005b38c  retn
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
