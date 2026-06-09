# wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180007d40`
- end: `0x1800080bf`
- name: `?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `895`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006498`
- `0x1800066cc`
- `0x180006dbc`
- `0x180007450`
- `0x180008fa0`
- `0x1800178bc`
- `0x18001bdd8`
- `0x18003a24c`
- `0x18003b0c4`

## callees

- `0x180007d40`
- `0x180025eb4`
- `0x18002a120`
- `0x18003657c`
- `0x18003bc70`
- `0x18003c020`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007d7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007d7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007d9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007dbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007e04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007d9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007dbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007e04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f6a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180007e41`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180007e41`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007f4a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007f4a`
- `ntdll!EtwEventWriteTransfer` at `0x180008048`
- `ntdll!EtwEventWriteTransfer` at `0x180008048`
- `ntdll!EtwEventSetInformation` at `0x180007f15`
- `ntdll!EtwEventSetInformation` at `0x180007f15`
- `ntdll!EtwEventRegister` at `0x180007ef4`
- `ntdll!EtwEventRegister` at `0x180007ef4`

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
      SRWLock = (PSRWLOCK)&qword_180082988;
      qword_180082990 = 0;
      byte_180082998 = 0;
      dword_18008299C = 0;
      qword_180082988 = (__int64)&ProfileLogging::`vftable';
      qword_1800829A0 = (__int64)&`ProfileLogging::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(_lambda_cff094b7b3eb7b3291eb3a07719b48ba_::_lambda_invoker_cdecl_);
      v9 = (_QWORD *)qword_1800829A0;
      qword_180082990 = qword_1800829A0;
      byte_180082998 = 1;
      v16 = *(_OWORD *)(*(_QWORD *)(qword_1800829A0 + 8) - 16LL);
      if ( *(_QWORD *)(qword_1800829A0 + 32) )
        __fastfail(5u);
      *(_QWORD *)(qword_1800829A0 + 40) = 0;
      v9[6] = 0;
      if ( !(unsigned int)EtwEventRegister(&v16, tlgEnableCallback, v9, v9 + 4) )
        EtwEventSetInformation(v9[4], 2, v9[1], *(unsigned __int16 *)v9[1]);
      dword_18008299C = 1;
      (*(void (__fastcall **)(__int64 *))(qword_180082988 + 8))(&qword_180082988);
      InitOnceComplete(&`ProfileLogging::Instance'::`2'::wrapper, 0, &qword_180082988);
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
      *(_QWORD *)&v18 = byte_180071B09;
      *((_QWORD *)&v18 + 1) = 0x10000004DLL;
      LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(Ptr[4], &v16, v11, 0, 5, &v17);
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
0x180007d40  push    rbp
0x180007d42  push    rbx
0x180007d43  push    rsi
0x180007d44  push    rdi
0x180007d45  push    r14
0x180007d47  push    r15
0x180007d49  lea     rbp, [rsp-18h]
0x180007d4e  sub     rsp, 118h
0x180007d55  mov     rax, cs:__security_cookie
0x180007d5c  xor     rax, rsp
0x180007d5f  mov     [rbp+40h+var_40], rax
0x180007d63  mov     rdi, rcx
0x180007d66  xor     r15d, r15d
0x180007d69  mov     rbx, [rcx+118h]
0x180007d70  test    rbx, rbx
0x180007d73  jz      short loc_180007DAB
0x180007d75  add     rbx, 108h
0x180007d7c  mov     rcx, rbx; SRWLock
0x180007d7f  call    cs:__imp_AcquireSRWLockExclusive
0x180007d86  nop     dword ptr [rax+rax+00h]
0x180007d8b  lea     rax, [rsp+140h+SRWLock]
0x180007d90  mov     [rax], r15
0x180007d93  mov     rcx, [rsp+140h+SRWLock]; SRWLock
0x180007d98  test    rcx, rcx
0x180007d9b  jz      short loc_180007DCC
0x180007d9d  call    cs:__imp_ReleaseSRWLockExclusive
0x180007da4  nop     dword ptr [rax+rax+00h]
0x180007da9  jmp     short loc_180007DCC
0x180007dab  lea     rax, [rsp+140h+var_100]
0x180007db0  mov     [rax], r15
0x180007db3  mov     rcx, [rsp+140h+var_100]; SRWLock
0x180007db8  test    rcx, rcx
0x180007dbb  jz      short loc_180007DC9
0x180007dbd  call    cs:__imp_ReleaseSRWLockExclusive
0x180007dc4  nop     dword ptr [rax+rax+00h]
0x180007dc9  mov     rbx, r15
0x180007dcc  mov     rax, [rdi+110h]
0x180007dd3  mov     r14d, [rax+0F8h]
0x180007dda  cmp     r14d, 1
0x180007dde  jl      loc_180008085
0x180007de4  mov     esi, [rax+48h]
0x180007de7  test    esi, esi
0x180007de9  js      short loc_180007DF2
0x180007deb  mov     [rax+48h], r15d
0x180007def  mov     esi, r15d
0x180007df2  dec     r14d
0x180007df5  mov     [rax+0F8h], r14d
0x180007dfc  test    rbx, rbx
0x180007dff  jz      short loc_180007E10
0x180007e01  mov     rcx, rbx; SRWLock
0x180007e04  call    cs:__imp_ReleaseSRWLockExclusive
0x180007e0b  nop     dword ptr [rax+rax+00h]
0x180007e10  test    r14d, r14d
0x180007e13  jnz     short loc_180007E24
0x180007e15  mov     edx, esi
0x180007e17  mov     rcx, rdi
0x180007e1a  call    ?ReportStopActivity@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180007e1f  jmp     loc_180008055
0x180007e24  mov     [rsp+140h+SRWLock], r15
0x180007e29  mov     [rsp+140h+fPending], r15d
0x180007e2e  lea     r9, [rsp+140h+SRWLock]; lpContext
0x180007e33  lea     r8, [rsp+140h+fPending]; fPending
0x180007e38  xor     edx, edx; dwFlags
0x180007e3a  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x180007e41  call    cs:__imp_InitOnceBeginInitialize
0x180007e48  nop     dword ptr [rax+rax+00h]
0x180007e4d  test    eax, eax
0x180007e4f  jz      loc_180007F56
0x180007e55  cmp     [rsp+140h+fPending], 0
0x180007e5a  jz      loc_180007F56
0x180007e60  lea     r14, qword_180082988
0x180007e67  mov     [rsp+140h+SRWLock], r14
0x180007e6c  mov     cs:qword_180082990, r15
0x180007e73  mov     cs:byte_180082998, 0
0x180007e7a  mov     cs:dword_18008299C, r15d
0x180007e81  lea     rax, ??_7ProfileLogging@@6B@; const ProfileLogging::`vftable'
0x180007e88  mov     cs:qword_180082988, rax
0x180007e8f  lea     rax, ?__hInner@?1???0StaticHandle@ProfileLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ProfileLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180007e96  mov     cs:qword_1800829A0, rax
0x180007e9d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_cff094b7b3eb7b3291eb3a07719b48ba_@@CA@XZ; void (__cdecl *)()
0x180007ea4  call    atexit
0x180007ea9  mov     rbx, cs:qword_1800829A0
0x180007eb0  mov     cs:qword_180082990, rbx
0x180007eb7  mov     cs:byte_180082998, 1
0x180007ebe  mov     rax, [rbx+8]
0x180007ec2  movups  xmm0, xmmword ptr [rax-10h]
0x180007ec6  movups  [rsp+140h+var_F0], xmm0
0x180007ecb  cmp     qword ptr [rbx+20h], 0
0x180007ed0  jz      short loc_180007ED9
0x180007ed2  mov     ecx, 5
0x180007ed7  int     29h; Win8: RtlFailFast(ecx)
0x180007ed9  mov     [rbx+28h], r15
0x180007edd  mov     [rbx+30h], r15
0x180007ee1  lea     r9, [rbx+20h]
0x180007ee5  mov     r8, rbx
0x180007ee8  lea     rdx, _tlgEnableCallback
0x180007eef  lea     rcx, [rsp+140h+var_F0]
0x180007ef4  call    cs:__imp_EtwEventRegister
0x180007efb  nop     dword ptr [rax+rax+00h]
0x180007f00  test    eax, eax
0x180007f02  jnz     short loc_180007F21
0x180007f04  mov     r8, [rbx+8]
0x180007f08  movzx   r9d, word ptr [r8]
0x180007f0c  mov     edx, 2
0x180007f11  mov     rcx, [rbx+20h]
0x180007f15  call    cs:__imp_EtwEventSetInformation
0x180007f1c  nop     dword ptr [rax+rax+00h]
0x180007f21  mov     cs:dword_18008299C, 1
0x180007f2b  mov     rax, cs:qword_180082988
0x180007f32  mov     rcx, r14
0x180007f35  mov     rax, [rax+8]
0x180007f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f3e  mov     r8, r14; lpContext
0x180007f41  xor     edx, edx; dwFlags
0x180007f43  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x180007f4a  call    cs:__imp_InitOnceComplete
0x180007f51  nop     dword ptr [rax+rax+00h]
0x180007f56  mov     rax, [rsp+140h+SRWLock]
0x180007f5b  mov     rbx, [rax+8]
0x180007f5f  mov     eax, [rbx]
0x180007f61  cmp     eax, 5
0x180007f64  jbe     loc_180008055
0x180007f6a  call    cs:__imp_GetCurrentThreadId
0x180007f71  nop     dword ptr [rax+rax+00h]
0x180007f76  mov     [rsp+140h+fPending], eax
0x180007f7a  mov     dword ptr [rsp+140h+var_100], r15d
0x180007f7f  mov     [rsp+140h+var_F8], 1000000h
0x180007f88  mov     r8, [rdi+110h]
0x180007f8f  add     r8, 8
0x180007f93  lea     rax, [rsp+140h+fPending]
0x180007f98  mov     qword ptr [rbp+40h+var_A0], rax
0x180007f9c  mov     qword ptr [rbp+40h+var_A0+8], 4
0x180007fa4  lea     rax, [rsp+140h+var_100]
0x180007fa9  mov     qword ptr [rbp+40h+var_B0], rax
0x180007fad  mov     qword ptr [rbp+40h+var_B0+8], 4
0x180007fb5  lea     rax, [rsp+140h+var_F8]
0x180007fba  mov     qword ptr [rbp+40h+var_C0], rax
0x180007fbe  mov     qword ptr [rbp+40h+var_C0+8], 8
0x180007fc6  mov     dword ptr [rsp+140h+var_F0], 0B000000h
0x180007fce  movzx   eax, cs:word_180071AFF
0x180007fd5  mov     dword ptr [rsp+140h+var_F0+4], eax
0x180007fd9  mov     qword ptr [rsp+140h+var_F0+8], r15
0x180007fde  mov     rax, [rbx+8]
0x180007fe2  mov     qword ptr [rsp+140h+var_E0], rax
0x180007fe7  movzx   eax, word ptr [rax]
0x180007fea  mov     dword ptr [rsp+140h+var_E0+8], eax
0x180007fee  mov     dword ptr [rsp+140h+var_E0+0Ch], 2
0x180007ff6  lea     rax, byte_180071B09
0x180007ffd  mov     qword ptr [rsp+140h+var_D0], rax
0x180008002  mov     dword ptr [rsp+140h+var_D0+8], 4Dh ; 'M'
0x18000800a  mov     dword ptr [rsp+140h+var_D0+0Ch], 1
0x180008012  lea     rax, _TraceLoggingMetadataEnd
0x180008019  lea     rcx, _TraceLoggingMetadata
0x180008020  sub     eax, ecx
0x180008022  mov     dword ptr [rsp+140h+SRWLock], eax
0x180008026  mov     eax, dword ptr [rsp+140h+SRWLock]
0x18000802a  lea     rax, [rsp+140h+var_E0]
0x18000802f  mov     [rsp+140h+var_118], rax
0x180008034  mov     [rsp+140h+var_120], 5
0x18000803c  xor     r9d, r9d
0x18000803f  lea     rdx, [rsp+140h+var_F0]
0x180008044  mov     rcx, [rbx+20h]
0x180008048  call    cs:__imp_EtwEventWriteTransfer
0x18000804f  nop     dword ptr [rax+rax+00h]
0x180008054  nop
0x180008055  lea     rcx, [rdi+120h]; this
0x18000805c  cmp     dword ptr [rcx+18h], 0
0x180008060  jz      short loc_180008068
0x180008062  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180008067  nop
0x180008068  mov     rcx, [rbp+40h+var_40]
0x18000806c  xor     rcx, rsp; StackCookie
0x18000806f  call    __security_check_cookie
0x180008074  add     rsp, 118h
0x18000807b  pop     r15
0x18000807d  pop     r14
0x18000807f  pop     rdi
0x180008080  pop     rsi
0x180008081  pop     rbx
0x180008082  pop     rbp
0x180008083  retn
0x180008085  xorps   xmm0, xmm0
0x180008088  xor     eax, eax
0x18000808a  movups  [rsp+140h+var_E0], xmm0
0x18000808f  movups  [rsp+140h+var_D0], xmm0
0x180008094  movups  [rbp+40h+var_C0], xmm0
0x180008098  movups  [rbp+40h+var_B0], xmm0
0x18000809c  movups  [rbp+40h+var_A0], xmm0
0x1800080a0  movups  [rbp+40h+var_90], xmm0
0x1800080a4  movups  [rbp+40h+var_80], xmm0
0x1800080a8  movups  [rbp+40h+var_70], xmm0
0x1800080ac  movups  [rbp+40h+var_60], xmm0
0x1800080b0  mov     [rbp+40h+var_50], rax
0x1800080b4  lea     rcx, [rsp+140h+var_E0]; this
0x1800080b9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
