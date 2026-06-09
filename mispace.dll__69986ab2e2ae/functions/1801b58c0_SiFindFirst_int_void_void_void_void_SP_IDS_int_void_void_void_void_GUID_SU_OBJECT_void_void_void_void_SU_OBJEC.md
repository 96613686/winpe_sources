# SiFindFirst(int (*)(void *,void *,void *,void *,_SP_IDS * *),int (*)(void *,void *,void *,void *,_GUID *,_SU_OBJECT * *),void *,void *,void *,void *,_SU_OBJECT * *)

- ea: `0x1801b58c0`
- end: `0x1801b5acd`
- name: `?SiFindFirst@@YAPEAXP6AHPEAX000PEAPEAU_SP_IDS@@@ZP6AH0000PEAU_GUID@@PEAPEAU_SU_OBJECT@@@Z00004@Z`
- size: `525`
- prototype: `void *__fastcall(int (*)(void *, void *, void *, void *, struct _SP_IDS **), int (*)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **), void *, void *, HLOCAL hMem, void *, struct _SU_OBJECT **)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1801b8674`
- `0x1801bbcd8`
- `0x1801c1128`
- `0x1801c2c60`

## callees

- `0x1801b5538`
- `0x1801b5670`
- `0x1801b58c0`
- `0x1801b5c98`
- `0x1801b5d24`
- `0x1801b5d80`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5978`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b5935`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b5991`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b5935`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b5991`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b594d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b594d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801b5968`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801b5968`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801b58e9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801b58e9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801b5a0a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801b5a0a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801b5a2d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801b5a2d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801b5a48`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801b5a48`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801b5a7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801b5a7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b5a93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b5a93`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801b591c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801b591c`

## pseudocode

```c
__int64 __fastcall SiFindFirst(
        int (*a1)(void *, void *, void *, void *, struct _SP_IDS **),
        int (*a2)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **),
        void *a3,
        void *a4,
        _BYTE *hMem,
        void *a6,
        struct _SU_OBJECT **a7)
{
  struct _SU_OBJECT **v11; // r12
  __int64 v12; // r15
  _QWORD *v13; // rax
  void *v14; // rbx
  HANDLE CurrentThread; // rax
  int Control; // eax
  HLOCAL v17; // r14
  struct _TP_WORK *v18; // rdi
  unsigned int i; // esi
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+30h] [rbp-71h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-49h] BYREF
  unsigned int *v23; // [rsp+60h] [rbp-41h] BYREF
  int v24; // [rsp+68h] [rbp-39h]
  int (*v25)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **); // [rsp+70h] [rbp-31h]
  void *v26; // [rsp+78h] [rbp-29h]
  void *v27; // [rsp+80h] [rbp-21h]
  __int64 v28; // [rsp+88h] [rbp-19h]
  __int64 v29; // [rsp+90h] [rbp-11h]
  void *v30; // [rsp+98h] [rbp-9h]

  InitializeCriticalSection(&CriticalSection);
  v11 = a7;
  TokenHandle = 0;
  v12 = -1;
  v23 = 0;
  v24 = 0;
  v30 = 0;
  hMem = 0;
  *a7 = 0;
  v13 = LocalAlloc(0x40u, 0x10u);
  v14 = v13;
  if ( !v13 )
  {
    SetLastError(0x5AAu);
    goto LABEL_22;
  }
  v13[1] = v13;
  *v13 = v13;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
    {
LABEL_21:
      SuFindClose(v14);
      goto LABEL_22;
    }
    SetLastError(0);
  }
  if ( !((unsigned int (__fastcall *)(void *, void *, _QWORD, _QWORD, unsigned int **))a1)(a3, a4, 0, 0, &v23) )
    goto LABEL_21;
  v25 = a2;
  v26 = a3;
  v27 = a4;
  v28 = 0;
  v29 = 0;
  v30 = v14;
  Control = SuGetControl((struct _SP_CONTROL_INFO **)&hMem);
  v17 = hMem;
  if ( !Control )
    goto LABEL_18;
  if ( hMem[46] )
  {
    v18 = 0;
    SI_GET_CONTEXT::Callback(&CriticalSection);
  }
  else
  {
    v18 = CreateThreadpoolWork(SiFindFirstCallback, &CriticalSection, &ThreadpoolEnv);
    if ( !v18 )
      goto LABEL_18;
    for ( i = 0; i < *v23; ++i )
      SubmitThreadpoolWork(v18);
    WaitForThreadpoolWorkCallbacks(v18, 0);
  }
  if ( (unsigned int)SuFindNext(v14, v11) )
  {
    v12 = (__int64)v14;
    v14 = 0;
  }
  if ( v18 )
    CloseThreadpoolWork(v18);
LABEL_18:
  if ( v17 )
    LocalFree(v17);
  if ( v14 )
    goto LABEL_21;
LABEL_22:
  SI_GET_CONTEXT::~SI_GET_CONTEXT((SI_GET_CONTEXT *)&CriticalSection);
  return v12;
}

```

## disassembly

```asm
0x1801b58c0  push    rbp
0x1801b58c2  push    rbx
0x1801b58c3  push    rsi
0x1801b58c4  push    rdi
0x1801b58c5  push    r12
0x1801b58c7  push    r13
0x1801b58c9  push    r14
0x1801b58cb  push    r15
0x1801b58cd  lea     rbp, [rsp-7]
0x1801b58d2  sub     rsp, 0A8h
0x1801b58d9  mov     r13, rcx
0x1801b58dc  mov     rdi, r9
0x1801b58df  lea     rcx, [rbp+3Fh+CriticalSection]; lpCriticalSection
0x1801b58e3  mov     rsi, r8
0x1801b58e6  mov     r14, rdx
0x1801b58e9  call    cs:__imp_InitializeCriticalSection
0x1801b58f0  nop     dword ptr [rax+rax+00h]
0x1801b58f5  mov     r12, [rbp+3Fh+arg_30]
0x1801b58f9  xor     eax, eax
0x1801b58fb  mov     [rbp+3Fh+TokenHandle], rax
0x1801b58ff  or      r15, 0FFFFFFFFFFFFFFFFh
0x1801b5903  mov     [rbp+3Fh+var_80], rax
0x1801b5907  mov     [rbp+3Fh+var_78], eax
0x1801b590a  lea     edx, [rax+10h]; uBytes
0x1801b590d  mov     [rbp+3Fh+var_48], rax
0x1801b5911  lea     ecx, [rax+40h]; uFlags
0x1801b5914  mov     [rbp+3Fh+hMem], rax
0x1801b5918  mov     [r12], rax
0x1801b591c  call    cs:__imp_LocalAlloc
0x1801b5923  nop     dword ptr [rax+rax+00h]
0x1801b5928  mov     rbx, rax
0x1801b592b  test    rax, rax
0x1801b592e  jnz     short loc_1801B5946
0x1801b5930  mov     ecx, 5AAh; dwErrCode
0x1801b5935  call    cs:__imp_SetLastError
0x1801b593c  nop     dword ptr [rax+rax+00h]
0x1801b5941  jmp     loc_1801B5AAC
0x1801b5946  mov     [rax+8], rbx
0x1801b594a  mov     [rax], rbx
0x1801b594d  call    cs:__imp_GetCurrentThread
0x1801b5954  nop     dword ptr [rax+rax+00h]
0x1801b5959  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x1801b595d  xor     r8d, r8d; OpenAsSelf
0x1801b5960  mov     rcx, rax; ThreadHandle
0x1801b5963  mov     edx, 2000Ch; DesiredAccess
0x1801b5968  call    cs:__imp_OpenThreadToken
0x1801b596f  nop     dword ptr [rax+rax+00h]
0x1801b5974  test    eax, eax
0x1801b5976  jnz     short loc_1801B599D
0x1801b5978  call    cs:__imp_GetLastError
0x1801b597f  nop     dword ptr [rax+rax+00h]
0x1801b5984  cmp     eax, 3F0h
0x1801b5989  jnz     loc_1801B5AA4
0x1801b598f  xor     ecx, ecx; dwErrCode
0x1801b5991  call    cs:__imp_SetLastError
0x1801b5998  nop     dword ptr [rax+rax+00h]
0x1801b599d  lea     rax, [rbp+3Fh+var_80]
0x1801b59a1  xor     r9d, r9d
0x1801b59a4  mov     [rsp+0E0h+var_C0], rax
0x1801b59a9  xor     r8d, r8d
0x1801b59ac  mov     rax, r13
0x1801b59af  mov     rdx, rdi
0x1801b59b2  mov     rcx, rsi
0x1801b59b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b59ba  xor     r13d, r13d
0x1801b59bd  test    eax, eax
0x1801b59bf  jz      loc_1801B5AA4
0x1801b59c5  lea     rcx, [rbp+3Fh+hMem]; struct _SP_CONTROL_INFO **
0x1801b59c9  mov     [rbp+3Fh+var_70], r14
0x1801b59cd  mov     [rbp+3Fh+var_68], rsi
0x1801b59d1  mov     [rbp+3Fh+var_60], rdi
0x1801b59d5  mov     [rbp+3Fh+var_58], r13
0x1801b59d9  mov     [rbp+3Fh+var_50], r13
0x1801b59dd  mov     [rbp+3Fh+var_48], rbx
0x1801b59e1  call    ?SuGetControl@@YAHPEAPEAU_SP_CONTROL_INFO@@@Z; SuGetControl(_SP_CONTROL_INFO * *)
0x1801b59e6  mov     r14, [rbp+3Fh+hMem]
0x1801b59ea  test    eax, eax
0x1801b59ec  jz      loc_1801B5A8B
0x1801b59f2  cmp     [r14+2Eh], r13b
0x1801b59f6  jnz     short loc_1801B5A56
0x1801b59f8  lea     r8, ?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1801b59ff  lea     rdx, [rbp+3Fh+CriticalSection]; pv
0x1801b5a03  lea     rcx, ?SiFindFirstCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801b5a0a  call    cs:__imp_CreateThreadpoolWork
0x1801b5a11  nop     dword ptr [rax+rax+00h]
0x1801b5a16  mov     rdi, rax
0x1801b5a19  test    rax, rax
0x1801b5a1c  jz      short loc_1801B5A8B
0x1801b5a1e  mov     rcx, [rbp+3Fh+var_80]
0x1801b5a22  mov     esi, r13d
0x1801b5a25  cmp     [rcx], r13d
0x1801b5a28  jbe     short loc_1801B5A43
0x1801b5a2a  mov     rcx, rdi; pwk
0x1801b5a2d  call    cs:__imp_SubmitThreadpoolWork
0x1801b5a34  nop     dword ptr [rax+rax+00h]
0x1801b5a39  mov     rcx, [rbp+3Fh+var_80]
0x1801b5a3d  inc     esi
0x1801b5a3f  cmp     esi, [rcx]
0x1801b5a41  jb      short loc_1801B5A2A
0x1801b5a43  xor     edx, edx; fCancelPendingCallbacks
0x1801b5a45  mov     rcx, rdi; pwk
0x1801b5a48  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1801b5a4f  nop     dword ptr [rax+rax+00h]
0x1801b5a54  jmp     short loc_1801B5A62
0x1801b5a56  lea     rcx, [rbp+3Fh+CriticalSection]; lpCriticalSection
0x1801b5a5a  mov     rdi, r13
0x1801b5a5d  call    ?Callback@SI_GET_CONTEXT@@QEAAXXZ; SI_GET_CONTEXT::Callback(void)
0x1801b5a62  mov     rdx, r12; struct _SU_OBJECT **
0x1801b5a65  mov     rcx, rbx; void *
0x1801b5a68  call    ?SuFindNext@@YAHPEAXPEAPEAU_SU_OBJECT@@@Z; SuFindNext(void *,_SU_OBJECT * *)
0x1801b5a6d  test    eax, eax
0x1801b5a6f  jz      short loc_1801B5A77
0x1801b5a71  mov     r15, rbx
0x1801b5a74  mov     rbx, r13
0x1801b5a77  test    rdi, rdi
0x1801b5a7a  jz      short loc_1801B5A8B
0x1801b5a7c  mov     rcx, rdi; pwk
0x1801b5a7f  call    cs:__imp_CloseThreadpoolWork
0x1801b5a86  nop     dword ptr [rax+rax+00h]
0x1801b5a8b  test    r14, r14
0x1801b5a8e  jz      short loc_1801B5A9F
0x1801b5a90  mov     rcx, r14; hMem
0x1801b5a93  call    cs:__imp_LocalFree
0x1801b5a9a  nop     dword ptr [rax+rax+00h]
0x1801b5a9f  test    rbx, rbx
0x1801b5aa2  jz      short loc_1801B5AAC
0x1801b5aa4  mov     rcx, rbx; hMem
0x1801b5aa7  call    ?SuFindClose@@YAHPEAX@Z; SuFindClose(void *)
0x1801b5aac  lea     rcx, [rbp+3Fh+CriticalSection]; this
0x1801b5ab0  call    ??1SI_GET_CONTEXT@@QEAA@XZ; SI_GET_CONTEXT::~SI_GET_CONTEXT(void)
0x1801b5ab5  mov     rax, r15
0x1801b5ab8  add     rsp, 0A8h
0x1801b5abf  pop     r15
0x1801b5ac1  pop     r14
0x1801b5ac3  pop     r13
0x1801b5ac5  pop     r12
0x1801b5ac7  pop     rdi
0x1801b5ac8  pop     rsi
0x1801b5ac9  pop     rbx
0x1801b5aca  pop     rbp
0x1801b5acb  retn
```
