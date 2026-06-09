# RRasAdminConnectionNotification

- ea: `0x18000d180`
- end: `0x18000d2e3`
- name: `RRasAdminConnectionNotification`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000d180`
- `0x180019a24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d22e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d22e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d25a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d25a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d2a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d2a4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000d216`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000d216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d264`
- `MPRDDM!DDMRegisterConnectionNotification` at `0x18000d285`
- `MPRDDM!DDMRegisterConnectionNotification` at `0x18000d2c2`
- `MPRDDM!DDMRegisterConnectionNotification` at `0x18000d285`
- `MPRDDM!DDMRegisterConnectionNotification` at `0x18000d2c2`
- `RPCRT4!RpcRevertToSelf` at `0x18000d26c`
- `RPCRT4!RpcRevertToSelf` at `0x18000d2ae`
- `RPCRT4!RpcRevertToSelf` at `0x18000d26c`
- `RPCRT4!RpcRevertToSelf` at `0x18000d2ae`
- `RPCRT4!RpcImpersonateClient` at `0x18000d1fb`
- `RPCRT4!RpcImpersonateClient` at `0x18000d1fb`

## pseudocode

```c
RPC_STATUS __fastcall RRasAdminConnectionNotification(__int64 a1, int a2, DWORD a3, void *a4)
{
  RPC_STATUS result; // eax
  int v8; // esi
  HANDLE v9; // rdi
  DWORD v10; // ebx
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  unsigned int v13; // [rsp+40h] [rbp-38h] BYREF
  HANDLE TargetHandle; // [rsp+48h] [rbp-30h] BYREF

  v13 = 0;
  if ( (unsigned int)DimSecObjAccessCheckOrAllowedServices(3u, (WINBOOL *)&v13) || v13 )
    return 5;
  if ( (gbldwDIMComponentsLoaded & 4) == 0 || (_DWORD)qword_180070F24 == 1 || (unsigned int)(qword_180070F24 - 2) < 2 )
    return 903;
  if ( !a2 )
    return DDMRegisterConnectionNotification(0, a4, 0);
  TargetHandle = 0;
  result = RpcImpersonateClient(0);
  if ( result )
    return result;
  v8 = 1;
  v9 = OpenProcess(0xFFFFFu, 0, a3);
  if ( v9 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( DuplicateHandle(v9, a4, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      v8 = 0;
      v10 = RpcRevertToSelf();
      if ( v10 )
      {
LABEL_15:
        CloseHandle(v9);
        goto LABEL_16;
      }
      LastError = DDMRegisterConnectionNotification(1, a4, TargetHandle);
    }
    else
    {
      LastError = GetLastError();
    }
    v10 = LastError;
    goto LABEL_15;
  }
  v10 = GetLastError();
LABEL_16:
  if ( v10 && TargetHandle )
    CloseHandle(TargetHandle);
  if ( !v8 )
    return v10;
  result = RpcRevertToSelf();
  if ( !result )
    return v10;
  return result;
}

```

## disassembly

```asm
0x18000d180  push    rbx
0x18000d182  push    rbp
0x18000d183  push    rsi
0x18000d184  push    rdi
0x18000d185  sub     rsp, 58h
0x18000d189  mov     ebx, edx
0x18000d18b  mov     [rsp+78h+var_38], 0
0x18000d193  lea     rdx, [rsp+78h+var_38]; unsigned int *
0x18000d198  mov     ecx, 3; unsigned int
0x18000d19d  mov     rbp, r9
0x18000d1a0  mov     edi, r8d
0x18000d1a3  call    ?DimSecObjAccessCheckOrAllowedServices@@YAKKPEAK@Z; DimSecObjAccessCheckOrAllowedServices(ulong,ulong *)
0x18000d1a8  test    eax, eax
0x18000d1aa  jnz     loc_18000D2D5
0x18000d1b0  cmp     [rsp+78h+var_38], eax
0x18000d1b4  jnz     loc_18000D2D5
0x18000d1ba  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 4; ulong gbldwDIMComponentsLoaded
0x18000d1c1  jz      loc_18000D2CE
0x18000d1c7  mov     eax, dword ptr cs:qword_180070F24
0x18000d1cd  sub     eax, 1
0x18000d1d0  jz      loc_18000D2CE
0x18000d1d6  sub     eax, 1
0x18000d1d9  jz      loc_18000D2CE
0x18000d1df  cmp     eax, 1
0x18000d1e2  jz      loc_18000D2CE
0x18000d1e8  test    ebx, ebx
0x18000d1ea  jz      loc_18000D2BA
0x18000d1f0  xor     ecx, ecx; BindingHandle
0x18000d1f2  mov     [rsp+78h+TargetHandle], 0
0x18000d1fb  call    cs:__imp_RpcImpersonateClient
0x18000d201  test    eax, eax
0x18000d203  jnz     loc_18000D2DA
0x18000d209  mov     r8d, edi; dwProcessId
0x18000d20c  lea     esi, [rax+1]
0x18000d20f  xor     edx, edx; bInheritHandle
0x18000d211  mov     ecx, 0FFFFFh; dwDesiredAccess
0x18000d216  call    cs:__imp_OpenProcess
0x18000d21c  mov     rdi, rax
0x18000d21f  test    rax, rax
0x18000d222  jnz     short loc_18000D22E
0x18000d224  call    cs:__imp_GetLastError
0x18000d22a  mov     ebx, eax
0x18000d22c  jmp     short loc_18000D296
0x18000d22e  call    cs:__imp_GetCurrentProcess
0x18000d234  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18000d23c  lea     r9, [rsp+78h+TargetHandle]; lpTargetHandle
0x18000d241  mov     r8, rax; hTargetProcessHandle
0x18000d244  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x18000d24c  mov     rdx, rbp; hSourceHandle
0x18000d24f  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x18000d257  mov     rcx, rdi; hSourceProcessHandle
0x18000d25a  call    cs:__imp_DuplicateHandle
0x18000d260  test    eax, eax
0x18000d262  jnz     short loc_18000D26C
0x18000d264  call    cs:__imp_GetLastError
0x18000d26a  jmp     short loc_18000D28B
0x18000d26c  call    cs:__imp_RpcRevertToSelf
0x18000d272  xor     esi, esi
0x18000d274  mov     ebx, eax
0x18000d276  test    eax, eax
0x18000d278  jnz     short loc_18000D28D
0x18000d27a  mov     r8, [rsp+78h+TargetHandle]
0x18000d27f  lea     ecx, [rax+1]
0x18000d282  mov     rdx, rbp
0x18000d285  call    cs:__imp_DDMRegisterConnectionNotification
0x18000d28b  mov     ebx, eax
0x18000d28d  mov     rcx, rdi; hObject
0x18000d290  call    cs:__imp_CloseHandle
0x18000d296  test    ebx, ebx
0x18000d298  jz      short loc_18000D2AA
0x18000d29a  mov     rcx, [rsp+78h+TargetHandle]; hObject
0x18000d29f  test    rcx, rcx
0x18000d2a2  jz      short loc_18000D2AA
0x18000d2a4  call    cs:__imp_CloseHandle
0x18000d2aa  test    esi, esi
0x18000d2ac  jz      short loc_18000D2CA
0x18000d2ae  call    cs:__imp_RpcRevertToSelf
0x18000d2b4  test    eax, eax
0x18000d2b6  jz      short loc_18000D2CA
0x18000d2b8  jmp     short loc_18000D2DA
0x18000d2ba  xor     r8d, r8d
0x18000d2bd  mov     rdx, rbp
0x18000d2c0  xor     ecx, ecx
0x18000d2c2  call    cs:__imp_DDMRegisterConnectionNotification
0x18000d2c8  mov     ebx, eax
0x18000d2ca  mov     eax, ebx
0x18000d2cc  jmp     short loc_18000D2DA
0x18000d2ce  mov     eax, 387h
0x18000d2d3  jmp     short loc_18000D2DA
0x18000d2d5  mov     eax, 5
0x18000d2da  add     rsp, 58h
0x18000d2de  pop     rdi
0x18000d2df  pop     rsi
0x18000d2e0  pop     rbp
0x18000d2e1  pop     rbx
0x18000d2e2  retn
```
