# wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000a4a0`
- end: `0x18000a7e2`
- name: `?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `834`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800085cc`
- `0x180008ef4`
- `0x180009320`
- `0x180009bf0`
- `0x18000b540`
- `0x1800123cc`
- `0x1800190f4`
- `0x1800384b8`
- `0x180039bcc`

## callees

- `0x18000a4a0`
- `0x1800235cc`
- `0x1800281a8`
- `0x180035fe0`
- `0x18003a730`
- `0x18003aae0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a4df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a4df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a4f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a511`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a552`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a4f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a511`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a552`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a69a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a69a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a589`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a589`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a680`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a680`
- `ntdll!EtwEventWriteTransfer` at `0x18000a772`
- `ntdll!EtwEventWriteTransfer` at `0x18000a772`
- `ntdll!EtwEventSetInformation` at `0x18000a651`
- `ntdll!EtwEventSetInformation` at `0x18000a651`
- `ntdll!EtwEventRegister` at `0x18000a636`
- `ntdll!EtwEventRegister` at `0x18000a636`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        const struct wil::FailureInfo *a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rbx
  __int64 v5; // rax
  int v6; // r14d
  int v7; // esi
  int v8; // r14d
  _QWORD *v9; // rbx
  _QWORD *Ptr; // rbx
  __int64 v11; // r8
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v17; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v18; // [rsp+70h] [rbp-90h]
  __int128 v19; // [rsp+80h] [rbp-80h]
  __int128 v20; // [rsp+90h] [rbp-70h]
  __int128 v21; // [rsp+A0h] [rbp-60h]
  __int128 v22; // [rsp+B0h] [rbp-50h]
  __int128 v23; // [rsp+C0h] [rbp-40h]
  __int128 v24; // [rsp+D0h] [rbp-30h]
  __int128 v25; // [rsp+E0h] [rbp-20h]
  __int64 v26; // [rsp+F0h] [rbp-10h]

  v3 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v3 )
  {
    v4 = v3 + 33;
    AcquireSRWLockExclusive(v4);
    SRWLock = 0;
  }
  else
  {
    v14 = 0;
    v4 = 0;
  }
  v5 = *(_QWORD *)(a1 + 272);
  v6 = *(_DWORD *)(v5 + 248);
  if ( v6 < 1 )
  {
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    wil::details::WilFailFast((wil::details *)&v17, a2);
  }
  v7 = *(_DWORD *)(v5 + 72);
  if ( v7 >= 0 )
  {
    *(_DWORD *)(v5 + 72) = 0;
    v7 = 0;
  }
  v8 = v6 - 1;
  *(_DWORD *)(v5 + 248) = v8;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  if ( v8 )
  {
    SRWLock = 0;
    fPending = 0;
    if ( InitOnceBeginInitialize(&`ProfileLogging::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
      && fPending )
    {
      SRWLock = (PSRWLOCK)&qword_18007F888;
      qword_18007F890 = 0;
      byte_18007F898 = 0;
      dword_18007F89C = 0;
      qword_18007F888 = (__int64)&ProfileLogging::`vftable';
      qword_18007F8A0 = (__int64)&`ProfileLogging::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(_lambda_cff094b7b3eb7b3291eb3a07719b48ba_::_lambda_invoker_cdecl_);
      v9 = (_QWORD *)qword_18007F8A0;
      qword_18007F890 = qword_18007F8A0;
      byte_18007F898 = 1;
      v16 = *(_OWORD *)(*(_QWORD *)(qword_18007F8A0 + 8) - 16LL);
      if ( *(_QWORD *)(qword_18007F8A0 + 32) )
        __fastfail(5u);
      *(_QWORD *)(qword_18007F8A0 + 40) = 0;
      v9[6] = 0;
      if ( !(unsigned int)EtwEventRegister(&v16, tlgEnableCallback, v9, v9 + 4) )
        EtwEventSetInformation(v9[4], 2, v9[1], *(unsigned __int16 *)v9[1]);
      dword_18007F89C = 1;
      (*(void (__fastcall **)(__int64 *))(qword_18007F888 + 8))(&qword_18007F888);
      InitOnceComplete(&`ProfileLogging::Instance'::`2'::wrapper, 0, &qword_18007F888);
    }
    Ptr = SRWLock[1].Ptr;
    if ( *(_DWORD *)Ptr > 5u )
    {
      fPending = GetCurrentThreadId();
      LODWORD(v14) = 0;
      v15 = 0x1000000;
      v11 = *(_QWORD *)(a1 + 272) + 8LL;
      *(_QWORD *)&v21 = &fPending;
      *((_QWORD *)&v21 + 1) = 4;
      *(_QWORD *)&v20 = &v14;
      *((_QWORD *)&v20 + 1) = 4;
      *(_QWORD *)&v19 = &v15;
      *((_QWORD *)&v19 + 1) = 8;
      v16 = 0x50B000000uLL;
      *(_QWORD *)&v17 = Ptr[1];
      *((_QWORD *)&v17 + 1) = *(unsigned __int16 *)v17 | 0x200000000LL;
      *(_QWORD *)&v18 = byte_18006EA51;
      *((_QWORD *)&v18 + 1) = 0x10000004DLL;
      LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(Ptr[4], &v16, v11, 0, 5, &v17, fPending, SRWLock, v14);
    }
  }
  else
  {
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
      a1,
      (unsigned int)v7);
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x18000a4a0  push    rbp
0x18000a4a2  push    rbx
0x18000a4a3  push    rsi
0x18000a4a4  push    rdi
0x18000a4a5  push    r14
0x18000a4a7  push    r15
0x18000a4a9  lea     rbp, [rsp-18h]
0x18000a4ae  sub     rsp, 118h
0x18000a4b5  mov     rax, cs:__security_cookie
0x18000a4bc  xor     rax, rsp
0x18000a4bf  mov     [rbp+40h+var_40], rax
0x18000a4c3  mov     rdi, rcx
0x18000a4c6  xor     r15d, r15d
0x18000a4c9  mov     rbx, [rcx+118h]
0x18000a4d0  test    rbx, rbx
0x18000a4d3  jz      short loc_18000A4FF
0x18000a4d5  add     rbx, 108h
0x18000a4dc  mov     rcx, rbx; SRWLock
0x18000a4df  call    cs:__imp_AcquireSRWLockExclusive
0x18000a4e5  lea     rax, [rsp+140h+SRWLock]
0x18000a4ea  mov     [rax], r15
0x18000a4ed  mov     rcx, [rsp+140h+SRWLock]; SRWLock
0x18000a4f2  test    rcx, rcx
0x18000a4f5  jz      short loc_18000A51A
0x18000a4f7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a4fd  jmp     short loc_18000A51A
0x18000a4ff  lea     rax, [rsp+140h+var_100]
0x18000a504  mov     [rax], r15
0x18000a507  mov     rcx, [rsp+140h+var_100]; SRWLock
0x18000a50c  test    rcx, rcx
0x18000a50f  jz      short loc_18000A517
0x18000a511  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a517  mov     rbx, r15
0x18000a51a  mov     rax, [rdi+110h]
0x18000a521  mov     r14d, [rax+0F8h]
0x18000a528  cmp     r14d, 1
0x18000a52c  jl      loc_18000A7A8
0x18000a532  mov     esi, [rax+48h]
0x18000a535  test    esi, esi
0x18000a537  js      short loc_18000A540
0x18000a539  mov     [rax+48h], r15d
0x18000a53d  mov     esi, r15d
0x18000a540  dec     r14d
0x18000a543  mov     [rax+0F8h], r14d
0x18000a54a  test    rbx, rbx
0x18000a54d  jz      short loc_18000A558
0x18000a54f  mov     rcx, rbx; SRWLock
0x18000a552  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a558  test    r14d, r14d
0x18000a55b  jnz     short loc_18000A56C
0x18000a55d  mov     edx, esi
0x18000a55f  mov     rcx, rdi
0x18000a562  call    ?ReportStopActivity@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18000a567  jmp     loc_18000A779
0x18000a56c  mov     [rsp+140h+SRWLock], r15
0x18000a571  mov     [rsp+140h+fPending], r15d
0x18000a576  lea     r9, [rsp+140h+SRWLock]; lpContext
0x18000a57b  lea     r8, [rsp+140h+fPending]; fPending
0x18000a580  xor     edx, edx; dwFlags
0x18000a582  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x18000a589  call    cs:__imp_InitOnceBeginInitialize
0x18000a58f  test    eax, eax
0x18000a591  jz      loc_18000A686
0x18000a597  cmp     [rsp+140h+fPending], 0
0x18000a59c  jz      loc_18000A686
0x18000a5a2  lea     r14, qword_18007F888
0x18000a5a9  mov     [rsp+140h+SRWLock], r14
0x18000a5ae  mov     cs:qword_18007F890, r15
0x18000a5b5  mov     cs:byte_18007F898, 0
0x18000a5bc  mov     cs:dword_18007F89C, r15d
0x18000a5c3  lea     rax, ??_7ProfileLogging@@6B@; const ProfileLogging::`vftable'
0x18000a5ca  mov     cs:qword_18007F888, rax
0x18000a5d1  lea     rax, ?__hInner@?1???0StaticHandle@ProfileLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ProfileLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000a5d8  mov     cs:qword_18007F8A0, rax
0x18000a5df  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_cff094b7b3eb7b3291eb3a07719b48ba_@@CA@XZ; void (__cdecl *)()
0x18000a5e6  call    atexit
0x18000a5eb  mov     rbx, cs:qword_18007F8A0
0x18000a5f2  mov     cs:qword_18007F890, rbx
0x18000a5f9  mov     cs:byte_18007F898, 1
0x18000a600  mov     rax, [rbx+8]
0x18000a604  movups  xmm0, xmmword ptr [rax-10h]
0x18000a608  movups  [rsp+140h+var_F0], xmm0
0x18000a60d  cmp     qword ptr [rbx+20h], 0
0x18000a612  jz      short loc_18000A61B
0x18000a614  mov     ecx, 5
0x18000a619  int     29h; Win8: RtlFailFast(ecx)
0x18000a61b  mov     [rbx+28h], r15
0x18000a61f  mov     [rbx+30h], r15
0x18000a623  lea     r9, [rbx+20h]
0x18000a627  mov     r8, rbx
0x18000a62a  lea     rdx, _tlgEnableCallback
0x18000a631  lea     rcx, [rsp+140h+var_F0]
0x18000a636  call    cs:__imp_EtwEventRegister
0x18000a63c  test    eax, eax
0x18000a63e  jnz     short loc_18000A657
0x18000a640  mov     r8, [rbx+8]
0x18000a644  movzx   r9d, word ptr [r8]
0x18000a648  mov     edx, 2
0x18000a64d  mov     rcx, [rbx+20h]
0x18000a651  call    cs:__imp_EtwEventSetInformation
0x18000a657  mov     cs:dword_18007F89C, 1
0x18000a661  mov     rax, cs:qword_18007F888
0x18000a668  mov     rcx, r14
0x18000a66b  mov     rax, [rax+8]
0x18000a66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a674  mov     r8, r14; lpContext
0x18000a677  xor     edx, edx; dwFlags
0x18000a679  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x18000a680  call    cs:__imp_InitOnceComplete
0x18000a686  mov     rax, [rsp+140h+SRWLock]
0x18000a68b  mov     rbx, [rax+8]
0x18000a68f  mov     eax, [rbx]
0x18000a691  cmp     eax, 5
0x18000a694  jbe     loc_18000A779
0x18000a69a  call    cs:__imp_GetCurrentThreadId
0x18000a6a0  mov     [rsp+140h+fPending], eax
0x18000a6a4  mov     dword ptr [rsp+140h+var_100], r15d
0x18000a6a9  mov     [rsp+140h+var_F8], 1000000h
0x18000a6b2  mov     r8, [rdi+110h]
0x18000a6b9  add     r8, 8
0x18000a6bd  lea     rax, [rsp+140h+fPending]
0x18000a6c2  mov     qword ptr [rbp+40h+var_A0], rax
0x18000a6c6  mov     qword ptr [rbp+40h+var_A0+8], 4
0x18000a6ce  lea     rax, [rsp+140h+var_100]
0x18000a6d3  mov     qword ptr [rbp+40h+var_B0], rax
0x18000a6d7  mov     qword ptr [rbp+40h+var_B0+8], 4
0x18000a6df  lea     rax, [rsp+140h+var_F8]
0x18000a6e4  mov     qword ptr [rbp+40h+var_C0], rax
0x18000a6e8  mov     qword ptr [rbp+40h+var_C0+8], 8
0x18000a6f0  mov     dword ptr [rsp+140h+var_F0], 0B000000h
0x18000a6f8  movzx   eax, cs:word_18006EA47
0x18000a6ff  mov     dword ptr [rsp+140h+var_F0+4], eax
0x18000a703  mov     qword ptr [rsp+140h+var_F0+8], r15
0x18000a708  mov     rax, [rbx+8]
0x18000a70c  mov     qword ptr [rsp+140h+var_E0], rax
0x18000a711  movzx   eax, word ptr [rax]
0x18000a714  mov     dword ptr [rsp+140h+var_E0+8], eax
0x18000a718  mov     dword ptr [rsp+140h+var_E0+0Ch], 2
0x18000a720  lea     rax, byte_18006EA51
0x18000a727  mov     qword ptr [rsp+140h+var_D0], rax
0x18000a72c  mov     dword ptr [rsp+140h+var_D0+8], 4Dh ; 'M'
0x18000a734  mov     dword ptr [rsp+140h+var_D0+0Ch], 1
0x18000a73c  lea     rax, _TraceLoggingMetadataEnd
0x18000a743  lea     rcx, _TraceLoggingMetadata
0x18000a74a  sub     eax, ecx
0x18000a74c  mov     dword ptr [rsp+140h+SRWLock], eax
0x18000a750  mov     eax, dword ptr [rsp+140h+SRWLock]
0x18000a754  lea     rax, [rsp+140h+var_E0]
0x18000a759  mov     [rsp+140h+var_118], rax
0x18000a75e  mov     [rsp+140h+var_120], 5
0x18000a766  xor     r9d, r9d
0x18000a769  lea     rdx, [rsp+140h+var_F0]
0x18000a76e  mov     rcx, [rbx+20h]
0x18000a772  call    cs:__imp_EtwEventWriteTransfer
0x18000a778  nop
0x18000a779  lea     rcx, [rdi+120h]; this
0x18000a780  cmp     dword ptr [rcx+18h], 0
0x18000a784  jz      short loc_18000A78C
0x18000a786  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18000a78b  nop
0x18000a78c  mov     rcx, [rbp+40h+var_40]
0x18000a790  xor     rcx, rsp; StackCookie
0x18000a793  call    __security_check_cookie
0x18000a798  add     rsp, 118h
0x18000a79f  pop     r15
0x18000a7a1  pop     r14
0x18000a7a3  pop     rdi
0x18000a7a4  pop     rsi
0x18000a7a5  pop     rbx
0x18000a7a6  pop     rbp
0x18000a7a7  retn
0x18000a7a8  xorps   xmm0, xmm0
0x18000a7ab  xor     eax, eax
0x18000a7ad  movups  [rsp+140h+var_E0], xmm0
0x18000a7b2  movups  [rsp+140h+var_D0], xmm0
0x18000a7b7  movups  [rbp+40h+var_C0], xmm0
0x18000a7bb  movups  [rbp+40h+var_B0], xmm0
0x18000a7bf  movups  [rbp+40h+var_A0], xmm0
0x18000a7c3  movups  [rbp+40h+var_90], xmm0
0x18000a7c7  movups  [rbp+40h+var_80], xmm0
0x18000a7cb  movups  [rbp+40h+var_70], xmm0
0x18000a7cf  movups  [rbp+40h+var_60], xmm0
0x18000a7d3  mov     [rbp+40h+var_50], rax
0x18000a7d7  lea     rcx, [rsp+140h+var_E0]; this
0x18000a7dc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
