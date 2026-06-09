# _CertRegisterLogoffNotify

- ea: `0x180001fc8`
- end: `0x180002217`
- name: `_CertRegisterLogoffNotify`
- size: `591`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, __int64, DWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180001f1c`

## callees

- `0x180001ef0`
- `0x180001fc8`
- `0x1800033a0`
- `0x18000b198`
- `0x18000b2f4`
- `0x18000c3ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800020c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800020c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002125`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002108`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000213f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000215d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000213f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000215d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002070`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002070`
- `RPCRT4!RpcImpersonateClient` at `0x180002040`
- `RPCRT4!RpcImpersonateClient` at `0x180002040`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800020a8`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800021ed`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800020a8`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800021ed`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180002097`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180002097`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000205d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000205d`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800020f7`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800020f7`

## pseudocode

```c
__int64 __fastcall CertRegisterLogoffNotify(RPC_BINDING_HANDLE BindingHandle, __int64 a2, DWORD a3)
{
  int v3; // r12d
  __int64 v4; // rdi
  int v5; // r14d
  __int64 v9; // rax
  HANDLE *v10; // rbx
  _QWORD *v11; // rax
  __int64 v12; // rax
  RPC_STATUS v13; // eax
  HANDLE v14; // rax
  HANDLE CurrentProcess; // rax
  __int64 LogoffProcessEntry; // rax
  __int64 v17; // r8
  __int64 v18; // rax
  unsigned int v19; // ebp
  DWORD LastError; // esi
  DWORD v22; // ecx
  _QWORD *v23; // rax
  HANDLE *v24; // r9
  __int64 *v25; // rax
  _QWORD *v26; // rcx

  v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( !*(_DWORD *)(a2 + 8) || !*(_QWORD *)a2 )
  {
    v10 = 0;
    v22 = -2147024809;
LABEL_21:
    SetLastError(v22);
    goto LABEL_11;
  }
  v9 = PkiZeroAlloc(0x40u);
  v10 = (HANDLE *)v9;
  if ( v9 )
  {
    v11 = (_QWORD *)(v9 + 16);
    v11[1] = v11;
    *v11 = v11;
    *((_DWORD *)v10 + 8) = a3;
    v12 = PkiZeroAlloc(0x28u);
    v4 = v12;
    if ( v12 )
    {
      *(_QWORD *)(v12 + 16) = *(_QWORD *)a2;
      *(_DWORD *)(v12 + 24) = *(_DWORD *)(a2 + 8);
      v13 = RpcImpersonateClient(BindingHandle);
      if ( v13 )
      {
LABEL_26:
        v22 = v13;
        goto LABEL_21;
      }
      v5 = 1;
      v14 = OpenProcess(0x100040u, 0, a3);
      v10[5] = v14;
      if ( !v14 )
        goto LABEL_11;
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(v10[5], *(HANDLE *)(v4 + 16), CurrentProcess, (LPHANDLE)(v4 + 32), 2u, 0, 0) )
      {
        v13 = RpcRevertToSelfEx(BindingHandle);
        v5 = 0;
        if ( !v13 )
        {
          AcquireSRWLockExclusive(&SRWLock);
          v3 = 1;
          LogoffProcessEntry = CertFindLogoffProcessEntry(a3);
          if ( !LogoffProcessEntry )
          {
            v18 = RegisterWaitForSingleObjectEx(v10[5], CertProcessExitCallback, v10, 0xFFFFFFFFLL, 8);
            v10[6] = (HANDLE)v18;
            if ( !v18 )
              goto LABEL_11;
            *((_DWORD *)v10 + 14) = 1;
            v23 = qword_180020360;
            if ( *((HLOCAL **)qword_180020360 + 1) != &qword_180020360 )
LABEL_30:
              __fastfail(3u);
            *v10 = qword_180020360;
            v24 = v10;
            v10[1] = &qword_180020360;
            v23[1] = v10;
            qword_180020360 = v10;
            v10 = 0;
LABEL_24:
            v25 = (__int64 *)(v24 + 2);
            v26 = v24[2];
            if ( (HANDLE *)v26[1] == v24 + 2 )
            {
              *(_QWORD *)v4 = v26;
              LastError = 0;
              *(_QWORD *)(v4 + 8) = v25;
              v19 = 1;
              v26[1] = v4;
              *v25 = v4;
              v4 = 0;
LABEL_14:
              ReleaseSRWLockExclusive(&SRWLock);
              goto LABEL_15;
            }
            goto LABEL_30;
          }
          if ( !CertFindLogoffEventEntry(LogoffProcessEntry, *(_QWORD *)(v4 + 16), v17, LogoffProcessEntry) )
            goto LABEL_24;
          v22 = -2146885627;
          goto LABEL_21;
        }
        goto LABEL_26;
      }
      *(_QWORD *)(v4 + 32) = 0;
    }
  }
LABEL_11:
  v19 = 0;
  LastError = GetLastError();
  if ( v5 )
    RpcRevertToSelfEx(BindingHandle);
  if ( v3 )
    goto LABEL_14;
LABEL_15:
  if ( v4 )
    CertFreeLogoffEventEntry((HLOCAL)v4);
  if ( v10 )
    CertFreeLogoffProcessEntry(v10);
  SetLastError(LastError);
  return v19;
}

```

## disassembly

```asm
0x180001fc8  push    rbx
0x180001fca  push    rbp
0x180001fcb  push    rsi
0x180001fcc  push    rdi
0x180001fcd  push    r12
0x180001fcf  push    r14
0x180001fd1  push    r15
0x180001fd3  sub     rsp, 40h
0x180001fd7  xor     r12d, r12d
0x180001fda  xor     edi, edi
0x180001fdc  xor     r14d, r14d
0x180001fdf  mov     ebp, r8d
0x180001fe2  mov     rsi, rdx
0x180001fe5  mov     r15, rcx
0x180001fe8  cmp     [rdx+8], edi
0x180001feb  jz      loc_180002156
0x180001ff1  cmp     [rdx], rdi
0x180001ff4  jz      loc_180002156
0x180001ffa  lea     ecx, [rdi+40h]; uBytes
0x180001ffd  call    PkiZeroAlloc
0x180002002  mov     rbx, rax
0x180002005  test    rax, rax
0x180002008  jz      loc_180002106
0x18000200e  add     rax, 10h
0x180002012  lea     ecx, [rdi+28h]; uBytes
0x180002015  mov     [rax+8], rax
0x180002019  mov     [rax], rax
0x18000201c  mov     [rbx+20h], ebp
0x18000201f  call    PkiZeroAlloc
0x180002024  mov     rdi, rax
0x180002027  test    rax, rax
0x18000202a  jz      loc_180002106
0x180002030  mov     rax, [rsi]
0x180002033  mov     rcx, r15; BindingHandle
0x180002036  mov     [rdi+10h], rax
0x18000203a  mov     eax, [rsi+8]
0x18000203d  mov     [rdi+18h], eax
0x180002040  call    cs:__imp_RpcImpersonateClient
0x180002046  test    eax, eax
0x180002048  jnz     loc_1800021BB
0x18000204e  mov     r8d, ebp; dwProcessId
0x180002051  lea     r14d, [r12+1]
0x180002056  xor     edx, edx; bInheritHandle
0x180002058  mov     ecx, 100040h; dwDesiredAccess
0x18000205d  call    cs:__imp_OpenProcess
0x180002063  mov     [rbx+28h], rax
0x180002067  test    rax, rax
0x18000206a  jz      loc_180002106
0x180002070  call    cs:__imp_GetCurrentProcess
0x180002076  mov     rdx, [rdi+10h]; hSourceHandle
0x18000207a  lea     r9, [rdi+20h]; lpTargetHandle
0x18000207e  mov     rcx, [rbx+28h]; hSourceProcessHandle
0x180002082  mov     r8, rax; hTargetProcessHandle
0x180002085  mov     [rsp+78h+dwOptions], r12d; dwOptions
0x18000208a  mov     [rsp+78h+bInheritHandle], r12d; bInheritHandle
0x18000208f  mov     [rsp+78h+dwDesiredAccess], 2; dwDesiredAccess
0x180002097  call    cs:__imp_DuplicateHandle
0x18000209d  test    eax, eax
0x18000209f  jz      loc_1800021BF
0x1800020a5  mov     rcx, r15; BindingHandle
0x1800020a8  call    cs:__imp_RpcRevertToSelfEx
0x1800020ae  xor     r14d, r14d
0x1800020b1  test    eax, eax
0x1800020b3  jnz     loc_1800021BB
0x1800020b9  lea     rcx, SRWLock; SRWLock
0x1800020c0  call    cs:__imp_AcquireSRWLockExclusive
0x1800020c6  mov     ecx, ebp
0x1800020c8  lea     r12d, [r14+1]
0x1800020cc  call    _CertFindLogoffProcessEntry
0x1800020d1  mov     r9, rax
0x1800020d4  test    rax, rax
0x1800020d7  jnz     loc_1800021C8
0x1800020dd  mov     rcx, [rbx+28h]
0x1800020e1  lea     rdx, _CertProcessExitCallback
0x1800020e8  or      r9d, 0FFFFFFFFh
0x1800020ec  mov     [rsp+78h+dwDesiredAccess], 8
0x1800020f4  mov     r8, rbx
0x1800020f7  call    cs:__imp_RegisterWaitForSingleObjectEx
0x1800020fd  mov     [rbx+30h], rax
0x180002101  test    rax, rax
0x180002104  jnz     short loc_180002165
0x180002106  xor     ebp, ebp
0x180002108  call    cs:__imp_GetLastError
0x18000210e  mov     esi, eax
0x180002110  test    r14d, r14d
0x180002113  jnz     loc_1800021EA
0x180002119  test    r12d, r12d
0x18000211c  jz      short loc_18000212B
0x18000211e  lea     rcx, SRWLock; SRWLock
0x180002125  call    cs:__imp_ReleaseSRWLockExclusive
0x18000212b  test    rdi, rdi
0x18000212e  jnz     loc_1800021F8
0x180002134  test    rbx, rbx
0x180002137  jnz     loc_180002205
0x18000213d  mov     ecx, esi; dwErrCode
0x18000213f  call    cs:__imp_SetLastError
0x180002145  mov     eax, ebp
0x180002147  add     rsp, 40h
0x18000214b  pop     r15
0x18000214d  pop     r14
0x18000214f  pop     r12
0x180002151  pop     rdi
0x180002152  pop     rsi
0x180002153  pop     rbp
0x180002154  pop     rbx
0x180002155  retn
0x180002156  xor     ebx, ebx
0x180002158  mov     ecx, 80070057h; dwErrCode
0x18000215d  call    cs:__imp_SetLastError
0x180002163  jmp     short loc_180002106
0x180002165  mov     [rbx+38h], r12d
0x180002169  lea     rcx, qword_180020360
0x180002170  mov     rax, cs:qword_180020360
0x180002177  cmp     [rax+8], rcx
0x18000217b  jnz     short loc_1800021E3
0x18000217d  mov     [rbx], rax
0x180002180  mov     r9, rbx
0x180002183  mov     [rbx+8], rcx
0x180002187  mov     [rax+8], rbx
0x18000218b  mov     cs:qword_180020360, rbx
0x180002192  xor     ebx, ebx
0x180002194  lea     rax, [r9+10h]
0x180002198  mov     rcx, [rax]
0x18000219b  cmp     [rcx+8], rax
0x18000219f  jnz     short loc_1800021E3
0x1800021a1  mov     [rdi], rcx
0x1800021a4  xor     esi, esi
0x1800021a6  mov     [rdi+8], rax
0x1800021aa  mov     ebp, r12d
0x1800021ad  mov     [rcx+8], rdi
0x1800021b1  mov     [rax], rdi
0x1800021b4  xor     edi, edi
0x1800021b6  jmp     loc_18000211E
0x1800021bb  mov     ecx, eax
0x1800021bd  jmp     short loc_18000215D
0x1800021bf  mov     [rdi+20h], r12
0x1800021c3  jmp     loc_180002106
0x1800021c8  mov     rdx, [rdi+10h]
0x1800021cc  mov     rcx, rax
0x1800021cf  call    _CertFindLogoffEventEntry
0x1800021d4  test    rax, rax
0x1800021d7  jz      short loc_180002194
0x1800021d9  mov     ecx, 80092005h
0x1800021de  jmp     loc_18000215D
0x1800021e3  mov     ecx, 3
0x1800021e8  int     29h; Win8: RtlFailFast(ecx)
0x1800021ea  mov     rcx, r15; BindingHandle
0x1800021ed  call    cs:__imp_RpcRevertToSelfEx
0x1800021f3  jmp     loc_180002119
0x1800021f8  mov     rcx, rdi; hMem
0x1800021fb  call    _CertFreeLogoffEventEntry
0x180002200  jmp     loc_180002134
0x180002205  mov     edx, 1
0x18000220a  mov     rcx, rbx; hMem
0x18000220d  call    _CertFreeLogoffProcessEntry
0x180002212  jmp     loc_18000213D
```
