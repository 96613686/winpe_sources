# _lambda_25492e723f3fb512063019ab9c6aa90a_::operator()(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18001fe40`
- end: `0x18001ff39`
- name: `??R_lambda_25492e723f3fb512063019ab9c6aa90a_@@QEBAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001f4a0`

## callees

- `0x180001b94`
- `0x18001fdb4`
- `0x18001fe40`
- `0x180039010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001fe8a`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001fe8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fe75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fec8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fe75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fec8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fe59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fea5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fe59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fea5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fee2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fee2`

## pseudocode

```c
void __fastcall _lambda_25492e723f3fb512063019ab9c6aa90a_::operator()(__int64 a1, __int64 a2, __int64 a3)
{
  RTL_SRWLOCK *v4; // rdi
  char v5; // si
  __int64 v6; // rcx
  __int64 v7; // rdx
  const char *v8; // r9
  bool v9; // zf
  struct _TP_TIMER *v10; // rcx
  __int64 v11; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = (RTL_SRWLOCK *)(a3 + 88);
  AcquireSRWLockExclusive((PSRWLOCK)(a3 + 88));
  v5 = 1;
  ++*(_DWORD *)(a3 + 96);
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  try
  {
    v6 = *(_QWORD *)(a3 + 72);
    if ( !v6 )
      std::_Xbad_function_call();
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    AcquireSRWLockExclusive(v4);
    v9 = (*(_DWORD *)(a3 + 96))-- == 1;
    if ( !v9 || !*(_BYTE *)(a3 + 100) )
      v5 = 0;
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    if ( v5 )
    {
      v10 = *(struct _TP_TIMER **)(a3 + 80);
      if ( v10 )
        CloseThreadpoolTimer(v10);
      v11 = *(_QWORD *)(a3 + 72);
      if ( v11 )
      {
        LOBYTE(v7) = v11 != a3 + 16;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 32LL))(v11, v7);
        *(_QWORD *)(a3 + 72) = 0;
      }
      wil::details::threadpool_object_context::~threadpool_object_context((wil::details::threadpool_object_context *)a3);
      operator delete((void *)a3, (const struct std::nothrow_t *)0x68);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ThreadpoolCoordinator.h",
      v8);
  }
}

```

## disassembly

```asm
0x18001fe40  mov     [rsp+arg_0], rbx
0x18001fe45  mov     [rsp+arg_8], rsi
0x18001fe4a  push    rdi
0x18001fe4b  sub     rsp, 20h
0x18001fe4f  mov     rbx, r8
0x18001fe52  lea     rdi, [r8+58h]
0x18001fe56  mov     rcx, rdi; SRWLock
0x18001fe59  call    cs:__imp_AcquireSRWLockExclusive
0x18001fe60  nop     dword ptr [rax+rax+00h]
0x18001fe65  mov     esi, 1
0x18001fe6a  add     [rbx+60h], esi
0x18001fe6d  test    rdi, rdi
0x18001fe70  jz      short loc_18001FE81
0x18001fe72  mov     rcx, rdi; SRWLock
0x18001fe75  call    cs:__imp_ReleaseSRWLockExclusive
0x18001fe7c  nop     dword ptr [rax+rax+00h]
0x18001fe81  mov     rcx, [rbx+48h]
0x18001fe85  test    rcx, rcx
0x18001fe88  jnz     short loc_18001FE96
0x18001fe8a  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001fe91  nop     dword ptr [rax+rax+00h]
0x18001fe96  mov     rax, [rcx]
0x18001fe99  mov     rax, [rax+10h]
0x18001fe9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fea2  mov     rcx, rdi; SRWLock
0x18001fea5  call    cs:__imp_AcquireSRWLockExclusive
0x18001feac  nop     dword ptr [rax+rax+00h]
0x18001feb1  add     dword ptr [rbx+60h], 0FFFFFFFFh
0x18001feb5  jnz     short loc_18001FEBD
0x18001feb7  cmp     byte ptr [rbx+64h], 0
0x18001febb  jnz     short loc_18001FEC0
0x18001febd  xor     sil, sil
0x18001fec0  test    rdi, rdi
0x18001fec3  jz      short loc_18001FED4
0x18001fec5  mov     rcx, rdi; SRWLock
0x18001fec8  call    cs:__imp_ReleaseSRWLockExclusive
0x18001fecf  nop     dword ptr [rax+rax+00h]
0x18001fed4  test    sil, sil
0x18001fed7  jz      short loc_18001FF28
0x18001fed9  mov     rcx, [rbx+50h]; pti
0x18001fedd  test    rcx, rcx
0x18001fee0  jz      short loc_18001FEEE
0x18001fee2  call    cs:__imp_CloseThreadpoolTimer
0x18001fee9  nop     dword ptr [rax+rax+00h]
0x18001feee  lea     rdi, [rbx+10h]
0x18001fef2  mov     rcx, [rdi+38h]
0x18001fef6  test    rcx, rcx
0x18001fef9  jz      short loc_18001FF12
0x18001fefb  mov     rax, [rcx]
0x18001fefe  cmp     rcx, rdi
0x18001ff01  setnz   dl
0x18001ff04  mov     rax, [rax+20h]
0x18001ff08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff0d  and     qword ptr [rdi+38h], 0
0x18001ff12  mov     rcx, rbx; this
0x18001ff15  call    ??1threadpool_object_context@details@wil@@QEAA@XZ; wil::details::threadpool_object_context::~threadpool_object_context(void)
0x18001ff1a  mov     edx, 68h ; 'h'; struct std::nothrow_t *
0x18001ff1f  mov     rcx, rbx; void *
0x18001ff22  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ff27  nop
0x18001ff28  mov     rbx, [rsp+28h+arg_0]
0x18001ff2d  mov     rsi, [rsp+28h+arg_8]
0x18001ff32  add     rsp, 20h
0x18001ff36  pop     rdi
0x18001ff37  retn
```
