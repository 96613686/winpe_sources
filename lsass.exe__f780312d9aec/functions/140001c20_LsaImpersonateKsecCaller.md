# LsaImpersonateKsecCaller

- ea: `0x140001c20`
- end: `0x140001ccd`
- name: `LsaImpersonateKsecCaller`
- size: `173`
- prototype: `NTSTATUS __fastcall(LPHANDLE lpTargetHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140001c20`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x140001cc6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140001c93`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140001c93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001c65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001c71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001c65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001c71`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140001c3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140001c3d`

## pseudocode

```c
NTSTATUS __fastcall LsaImpersonateKsecCaller(LPHANDLE lpTargetHandle)
{
  void **Value; // rsi
  HANDLE CurrentProcess; // rax
  void *v5; // rsi
  void *v6; // rdi
  HANDLE v7; // rax

  *lpTargetHandle = 0;
  Value = (void **)TlsGetValue(dwTlsIndex);
  if ( Value
    && (CurrentProcess = GetCurrentProcess(),
        v5 = *Value,
        v6 = CurrentProcess,
        v7 = GetCurrentProcess(),
        DuplicateHandle(v7, v5, v6, lpTargetHandle, 0, 0, 2u)) )
  {
    return NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, lpTargetHandle, 8u);
  }
  else
  {
    return -1073741732;
  }
}

```

## disassembly

```asm
0x140001c20  mov     [rsp+arg_8], rbx
0x140001c25  mov     [rsp+arg_10], rbp
0x140001c2a  push    rsi
0x140001c2b  sub     rsp, 40h
0x140001c2f  mov     rbx, rcx
0x140001c32  xor     ebp, ebp
0x140001c34  mov     [rcx], rbp
0x140001c37  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x140001c3d  call    cs:__imp_TlsGetValue
0x140001c43  mov     rsi, rax
0x140001c46  test    rax, rax
0x140001c49  jnz     short loc_140001C60
0x140001c4b  mov     eax, 0C000005Ch
0x140001c50  mov     rbx, [rsp+48h+arg_8]
0x140001c55  mov     rbp, [rsp+48h+arg_10]
0x140001c5a  add     rsp, 40h
0x140001c5e  pop     rsi
0x140001c5f  retn
0x140001c60  mov     [rsp+48h+arg_0], rdi
0x140001c65  call    cs:__imp_GetCurrentProcess
0x140001c6b  mov     rsi, [rsi]
0x140001c6e  mov     rdi, rax
0x140001c71  call    cs:__imp_GetCurrentProcess
0x140001c77  mov     [rsp+48h+dwOptions], 2; dwOptions
0x140001c7f  mov     r9, rbx; lpTargetHandle
0x140001c82  mov     rcx, rax; hSourceProcessHandle
0x140001c85  mov     [rsp+48h+bInheritHandle], ebp; bInheritHandle
0x140001c89  mov     r8, rdi; hTargetProcessHandle
0x140001c8c  mov     [rsp+48h+dwDesiredAccess], ebp; dwDesiredAccess
0x140001c90  mov     rdx, rsi; hSourceHandle
0x140001c93  call    cs:__imp_DuplicateHandle
0x140001c99  mov     rdi, [rsp+48h+arg_0]
0x140001c9e  test    eax, eax
0x140001ca0  jz      short loc_140001C4B
0x140001ca2  mov     r9d, 8
0x140001ca8  mov     r8, rbx
0x140001cab  mov     edx, 5
0x140001cb0  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x140001cb7  mov     rbx, [rsp+48h+arg_8]
0x140001cbc  mov     rbp, [rsp+48h+arg_10]
0x140001cc1  add     rsp, 40h
0x140001cc5  pop     rsi
0x140001cc6  jmp     cs:__imp_NtSetInformationThread
```
