# SetDefaultCommConfigW

- ea: `0x180060a10`
- end: `0x180060aff`
- name: `SetDefaultCommConfigW`
- size: `239`
- prototype: `BOOL __stdcall(LPCWSTR lpszName, LPCOMMCONFIG lpCC, DWORD dwSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180060980`

## callees

- `0x18004586c`
- `0x180060a10`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180060ae7`
- `ntdll!RtlSetLastWin32Error` at `0x18007b67c`
- `ntdll!RtlSetLastWin32Error` at `0x180060ae7`
- `ntdll!RtlSetLastWin32Error` at `0x18007b67c`
- `ntdll!RtlFreeHeap` at `0x180060acd`
- `ntdll!RtlFreeHeap` at `0x18007b65e`
- `ntdll!RtlFreeHeap` at `0x180060acd`
- `ntdll!RtlFreeHeap` at `0x18007b65e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060a71`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060a71`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180060adb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007b66e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180060adb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007b66e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180060a54`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180060a54`

## string_xrefs

- `0x180060a67`: `drvSetDefaultCommConfigW`

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
0x180060a10  mov     rax, rsp
0x180060a13  push    rbx
0x180060a14  push    rsi
0x180060a15  push    rdi
0x180060a16  push    r12
0x180060a18  push    r14
0x180060a1a  push    r15
0x180060a1c  sub     rsp, 48h
0x180060a20  mov     r15d, r8d
0x180060a23  mov     r12, rdx
0x180060a26  mov     r14, rcx
0x180060a29  xorps   xmm0, xmm0
0x180060a2c  movups  xmmword ptr [rax-48h], xmm0
0x180060a30  mov     esi, 1
0x180060a35  xor     edi, edi
0x180060a37  mov     [rax-50h], rdi
0x180060a3b  xor     ebx, ebx
0x180060a3d  mov     [rax-58h], ebx
0x180060a40  lea     rdx, [rax-48h]
0x180060a44  call    GetFriendlyUi
0x180060a49  nop
0x180060a4a  mov     rcx, [rsp+78h+lpLibFileName]; lpLibFileName
0x180060a4f  test    rcx, rcx
0x180060a52  jz      short loc_180060AAF
0x180060a54  call    cs:__imp_LoadLibraryW
0x180060a5a  mov     rdi, rax
0x180060a5d  mov     [rsp+78h+var_50], rax
0x180060a62  test    rax, rax
0x180060a65  jz      short loc_180060AA1
0x180060a67  lea     rdx, aDrvsetdefaultc; "drvSetDefaultCommConfigW"
0x180060a6e  mov     rcx, rax; hModule
0x180060a71  call    cs:__imp_GetProcAddress
0x180060a77  test    rax, rax
0x180060a7a  jnz     short loc_180060A8A
0x180060a7c  mov     ebx, gs:68h
0x180060a84  mov     [rsp+78h+var_58], ebx
0x180060a88  jmp     short loc_180060AAF
0x180060a8a  mov     r8d, r15d
0x180060a8d  mov     rdx, r12
0x180060a90  mov     rcx, r14
0x180060a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060a98  mov     rbx, rax
0x180060a9b  mov     [rsp+78h+var_58], eax
0x180060a9f  jmp     short loc_180060AB1
0x180060aa1  mov     eax, gs:68h
0x180060aa9  mov     ebx, eax
0x180060aab  mov     [rsp+78h+var_58], eax
0x180060aaf  xor     esi, esi
0x180060ab1  cmp     [rsp+78h+lpLibFileName], 0
0x180060ab7  jz      short loc_180060AD3
0x180060ab9  mov     rcx, gs:60h
0x180060ac2  mov     r8, [rsp+78h+lpLibFileName]; P
0x180060ac7  xor     edx, edx; Flags
0x180060ac9  mov     rcx, [rcx+30h]; HeapHandle
0x180060acd  call    cs:__imp_RtlFreeHeap
0x180060ad3  test    rdi, rdi
0x180060ad6  jz      short loc_180060AE1
0x180060ad8  mov     rcx, rdi; hLibModule
0x180060adb  call    cs:__imp_FreeLibrary
0x180060ae1  test    ebx, ebx
0x180060ae3  jz      short loc_180060AEF
0x180060ae5  mov     ecx, ebx; LastError
0x180060ae7  call    cs:__imp_RtlSetLastWin32Error
0x180060aed  xor     esi, esi
0x180060aef  mov     eax, esi
0x180060af1  add     rsp, 48h
0x180060af5  pop     r15
0x180060af7  pop     r14
0x180060af9  pop     r12
0x180060afb  pop     rdi
0x180060afc  pop     rsi
0x180060afd  pop     rbx
0x180060afe  retn
0x18007b63b  push    rbp
0x18007b63d  sub     rsp, 20h
0x18007b641  mov     rbp, rdx
0x18007b644  cmp     qword ptr [rbp+38h], 0
0x18007b649  jz      short loc_18007B665
0x18007b64b  mov     rcx, gs:60h
0x18007b654  mov     r8, [rbp+38h]; P
0x18007b658  xor     edx, edx; Flags
0x18007b65a  mov     rcx, [rcx+30h]; HeapHandle
0x18007b65e  call    cs:__imp_RtlFreeHeap
0x18007b664  nop
0x18007b665  mov     rcx, [rbp+28h]; hLibModule
0x18007b669  test    rcx, rcx
0x18007b66c  jz      short loc_18007B675
0x18007b66e  call    cs:__imp_FreeLibrary
0x18007b674  nop
0x18007b675  mov     ecx, [rbp+20h]; LastError
0x18007b678  test    ecx, ecx
0x18007b67a  jz      short loc_18007B683
0x18007b67c  call    cs:__imp_RtlSetLastWin32Error
0x18007b682  nop
0x18007b683  add     rsp, 20h
0x18007b687  pop     rbp
0x18007b688  retn
```
