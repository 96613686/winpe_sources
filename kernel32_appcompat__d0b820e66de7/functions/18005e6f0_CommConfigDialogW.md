# CommConfigDialogW

- ea: `0x18005e6f0`
- end: `0x18005e7fe`
- name: `CommConfigDialogW`
- size: `270`
- prototype: `BOOL __stdcall(LPCWSTR lpszName, HWND hWnd, LPCOMMCONFIG lpCC)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180067080`

## callees

- `0x18004a024`
- `0x18005e6f0`
- `0x180067260`
- `0x180084010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18005e7df`
- `ntdll!RtlSetLastWin32Error` at `0x18005e7df`
- `ntdll!RtlFreeHeap` at `0x18005e7b9`
- `ntdll!RtlFreeHeap` at `0x18005e7b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005e757`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005e757`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005e7cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005e7cd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005e734`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005e734`

## string_xrefs

- `0x18005e74d`: `drvCommConfigDialogW`

## pseudocode

```c
BOOL __stdcall CommConfigDialogW(LPCWSTR lpszName, HWND hWnd, LPCOMMCONFIG lpCC)
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
      ProcAddress = GetProcAddress(LibraryW, "drvCommConfigDialogW");
      if ( ProcAddress )
      {
        LastErrorValue = ((__int64 (__fastcall *)(LPCWSTR, HWND, LPCOMMCONFIG))ProcAddress)(lpszName, hWnd, lpCC);
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
0x18005e6f0  mov     rax, rsp
0x18005e6f3  push    rbx
0x18005e6f4  push    rsi
0x18005e6f5  push    rdi
0x18005e6f6  push    r12
0x18005e6f8  push    r14
0x18005e6fa  push    r15
0x18005e6fc  sub     rsp, 48h
0x18005e700  mov     r15, r8
0x18005e703  mov     r12, rdx
0x18005e706  mov     r14, rcx
0x18005e709  xorps   xmm0, xmm0
0x18005e70c  movups  xmmword ptr [rax-48h], xmm0
0x18005e710  mov     esi, 1
0x18005e715  xor     edi, edi
0x18005e717  mov     [rax-50h], rdi
0x18005e71b  xor     ebx, ebx
0x18005e71d  mov     [rax-58h], ebx
0x18005e720  lea     rdx, [rax-48h]
0x18005e724  call    GetFriendlyUi
0x18005e729  nop
0x18005e72a  mov     rcx, [rsp+78h+lpLibFileName]; lpLibFileName
0x18005e72f  test    rcx, rcx
0x18005e732  jz      short loc_18005E79B
0x18005e734  call    cs:__imp_LoadLibraryW
0x18005e73b  nop     dword ptr [rax+rax+00h]
0x18005e740  mov     rdi, rax
0x18005e743  mov     [rsp+78h+var_50], rax
0x18005e748  test    rax, rax
0x18005e74b  jz      short loc_18005E78D
0x18005e74d  lea     rdx, aDrvcommconfigd; "drvCommConfigDialogW"
0x18005e754  mov     rcx, rax; hModule
0x18005e757  call    cs:__imp_GetProcAddress
0x18005e75e  nop     dword ptr [rax+rax+00h]
0x18005e763  test    rax, rax
0x18005e766  jnz     short loc_18005E776
0x18005e768  mov     ebx, gs:68h
0x18005e770  mov     [rsp+78h+var_58], ebx
0x18005e774  jmp     short loc_18005E79B
0x18005e776  mov     r8, r15
0x18005e779  mov     rdx, r12
0x18005e77c  mov     rcx, r14
0x18005e77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e784  mov     rbx, rax
0x18005e787  mov     [rsp+78h+var_58], eax
0x18005e78b  jmp     short loc_18005E79D
0x18005e78d  mov     eax, gs:68h
0x18005e795  mov     ebx, eax
0x18005e797  mov     [rsp+78h+var_58], eax
0x18005e79b  xor     esi, esi
0x18005e79d  cmp     [rsp+78h+lpLibFileName], 0
0x18005e7a3  jz      short loc_18005E7C5
0x18005e7a5  mov     rcx, gs:60h
0x18005e7ae  mov     r8, [rsp+78h+lpLibFileName]; P
0x18005e7b3  xor     edx, edx; Flags
0x18005e7b5  mov     rcx, [rcx+30h]; HeapHandle
0x18005e7b9  call    cs:__imp_RtlFreeHeap
0x18005e7c0  nop     dword ptr [rax+rax+00h]
0x18005e7c5  test    rdi, rdi
0x18005e7c8  jz      short loc_18005E7D9
0x18005e7ca  mov     rcx, rdi; hLibModule
0x18005e7cd  call    cs:__imp_FreeLibrary
0x18005e7d4  nop     dword ptr [rax+rax+00h]
0x18005e7d9  test    ebx, ebx
0x18005e7db  jz      short loc_18005E7ED
0x18005e7dd  mov     ecx, ebx; LastError
0x18005e7df  call    cs:__imp_RtlSetLastWin32Error
0x18005e7e6  nop     dword ptr [rax+rax+00h]
0x18005e7eb  xor     esi, esi
0x18005e7ed  mov     eax, esi
0x18005e7ef  add     rsp, 48h
0x18005e7f3  pop     r15
0x18005e7f5  pop     r14
0x18005e7f7  pop     r12
0x18005e7f9  pop     rdi
0x18005e7fa  pop     rsi
0x18005e7fb  pop     rbx
0x18005e7fc  retn
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
