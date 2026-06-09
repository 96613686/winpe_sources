# GetDefaultCommConfigW

- ea: `0x180055f50`
- end: `0x18005603f`
- name: `GetDefaultCommConfigW`
- size: `239`
- prototype: `BOOL __stdcall(LPCWSTR lpszName, LPCOMMCONFIG lpCC, LPDWORD lpdwSize)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800608f0`

## callees

- `0x18004586c`
- `0x180055f50`
- `0x180060a10`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180056027`
- `ntdll!RtlSetLastWin32Error` at `0x180056027`
- `ntdll!RtlFreeHeap` at `0x18005600d`
- `ntdll!RtlFreeHeap` at `0x18005600d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180055fb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180055fb1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005601b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005601b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180055f94`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180055f94`

## string_xrefs

- `0x180055fa7`: `drvGetDefaultCommConfigW`

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
0x180055f50  mov     rax, rsp
0x180055f53  push    rbx
0x180055f54  push    rsi
0x180055f55  push    rdi
0x180055f56  push    r12
0x180055f58  push    r14
0x180055f5a  push    r15
0x180055f5c  sub     rsp, 48h
0x180055f60  mov     r15, r8
0x180055f63  mov     r12, rdx
0x180055f66  mov     r14, rcx
0x180055f69  xorps   xmm0, xmm0
0x180055f6c  movups  xmmword ptr [rax-48h], xmm0
0x180055f70  mov     esi, 1
0x180055f75  xor     edi, edi
0x180055f77  mov     [rax-50h], rdi
0x180055f7b  xor     ebx, ebx
0x180055f7d  mov     [rax-58h], ebx
0x180055f80  lea     rdx, [rax-48h]
0x180055f84  call    GetFriendlyUi
0x180055f89  nop
0x180055f8a  mov     rcx, [rsp+78h+lpLibFileName]; lpLibFileName
0x180055f8f  test    rcx, rcx
0x180055f92  jz      short loc_180055FEF
0x180055f94  call    cs:__imp_LoadLibraryW
0x180055f9a  mov     rdi, rax
0x180055f9d  mov     [rsp+78h+var_50], rax
0x180055fa2  test    rax, rax
0x180055fa5  jz      short loc_180055FE1
0x180055fa7  lea     rdx, aDrvgetdefaultc; "drvGetDefaultCommConfigW"
0x180055fae  mov     rcx, rax; hModule
0x180055fb1  call    cs:__imp_GetProcAddress
0x180055fb7  test    rax, rax
0x180055fba  jnz     short loc_180055FCA
0x180055fbc  mov     ebx, gs:68h
0x180055fc4  mov     [rsp+78h+var_58], ebx
0x180055fc8  jmp     short loc_180055FEF
0x180055fca  mov     r8, r15
0x180055fcd  mov     rdx, r12
0x180055fd0  mov     rcx, r14
0x180055fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fd8  mov     rbx, rax
0x180055fdb  mov     [rsp+78h+var_58], eax
0x180055fdf  jmp     short loc_180055FF1
0x180055fe1  mov     eax, gs:68h
0x180055fe9  mov     ebx, eax
0x180055feb  mov     [rsp+78h+var_58], eax
0x180055fef  xor     esi, esi
0x180055ff1  cmp     [rsp+78h+lpLibFileName], 0
0x180055ff7  jz      short loc_180056013
0x180055ff9  mov     rcx, gs:60h
0x180056002  mov     r8, [rsp+78h+lpLibFileName]; P
0x180056007  xor     edx, edx; Flags
0x180056009  mov     rcx, [rcx+30h]; HeapHandle
0x18005600d  call    cs:__imp_RtlFreeHeap
0x180056013  test    rdi, rdi
0x180056016  jz      short loc_180056021
0x180056018  mov     rcx, rdi; hLibModule
0x18005601b  call    cs:__imp_FreeLibrary
0x180056021  test    ebx, ebx
0x180056023  jz      short loc_18005602F
0x180056025  mov     ecx, ebx; LastError
0x180056027  call    cs:__imp_RtlSetLastWin32Error
0x18005602d  xor     esi, esi
0x18005602f  mov     eax, esi
0x180056031  add     rsp, 48h
0x180056035  pop     r15
0x180056037  pop     r14
0x180056039  pop     r12
0x18005603b  pop     rdi
0x18005603c  pop     rsi
0x18005603d  pop     rbx
0x18005603e  retn
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
