# ProfileTelemetry::UnmountRegHive::StartActivity(ushort const *)

- ea: `0x180009690`
- end: `0x1800099ef`
- name: `?StartActivity@UnmountRegHive@ProfileTelemetry@@QEAAXPEBG@Z`
- size: `863`
- prototype: `void __fastcall(ProfileTelemetry::UnmountRegHive *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008ef4`
- `0x180009320`

## callees

- `0x180009690`
- `0x1800121d0`
- `0x180013a80`
- `0x18003a730`
- `0x18003aae0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800096e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800096e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800096f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000970e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009752`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800096f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000970e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009752`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009894`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009894`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009771`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009771`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000986b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000986b`
- `ntdll!EtwEventActivityIdControl` at `0x180009733`
- `ntdll!EtwEventActivityIdControl` at `0x180009733`
- `ntdll!EtwEventWriteTransfer` at `0x1800099a2`
- `ntdll!EtwEventWriteTransfer` at `0x1800099a2`
- `ntdll!EtwEventSetInformation` at `0x18000983c`
- `ntdll!EtwEventSetInformation` at `0x18000983c`
- `ntdll!EtwEventRegister` at `0x180009821`
- `ntdll!EtwEventRegister` at `0x180009821`

## pseudocode

```c
void __fastcall ProfileTelemetry::UnmountRegHive::StartActivity(
        ProfileTelemetry::UnmountRegHive *this,
        const unsigned __int16 *a2)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v5; // rbx
  __int64 v6; // r14
  _QWORD *v7; // rbx
  __int64 v8; // r9
  _QWORD *Ptr; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rax
  int v15; // eax
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-59h] BYREF
  PSRWLOCK v17; // [rsp+40h] [rbp-51h] BYREF
  __int64 v18; // [rsp+48h] [rbp-49h] BYREF
  __int128 v19; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int16 *v20; // [rsp+68h] [rbp-29h] BYREF
  int v21; // [rsp+70h] [rbp-21h]
  int v22; // [rsp+74h] [rbp-1Dh]
  char *v23; // [rsp+78h] [rbp-19h]
  int v24; // [rsp+80h] [rbp-11h]
  int v25; // [rsp+84h] [rbp-Dh]
  __int64 *v26; // [rsp+88h] [rbp-9h]
  __int64 v27; // [rsp+90h] [rbp-1h]
  PSRWLOCK *v28; // [rsp+98h] [rbp+7h]
  __int64 v29; // [rsp+A0h] [rbp+Fh]
  const unsigned __int16 *v30; // [rsp+A8h] [rbp+17h]
  int v31; // [rsp+B0h] [rbp+1Fh]
  int v32; // [rsp+B4h] [rbp+23h]

  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v2 )
  {
    v5 = v2 + 33;
    AcquireSRWLockExclusive(v5);
    SRWLock = 0;
  }
  else
  {
    v17 = 0;
    v5 = 0;
  }
  v6 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)ProfileLogging::Provider() <= 4u )
    *(_OWORD *)(v6 + 8) = 0;
  else
    EtwEventActivityIdControl(3, v6 + 8);
  *(_DWORD *)v6 = 1;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  SRWLock = 0;
  LODWORD(v17) = 0;
  if ( InitOnceBeginInitialize(&`ProfileLogging::Instance'::`2'::wrapper, 0, (PBOOL)&v17, (LPVOID *)&SRWLock)
    && (_DWORD)v17 )
  {
    qword_18007F890 = 0;
    SRWLock = (PSRWLOCK)&qword_18007F888;
    byte_18007F898 = 0;
    dword_18007F89C = 0;
    qword_18007F888 = (__int64)&ProfileLogging::`vftable';
    qword_18007F8A0 = (__int64)&`ProfileLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_cff094b7b3eb7b3291eb3a07719b48ba_::_lambda_invoker_cdecl_);
    v7 = (_QWORD *)qword_18007F8A0;
    qword_18007F890 = qword_18007F8A0;
    byte_18007F898 = 1;
    v19 = *(_OWORD *)(*(_QWORD *)(qword_18007F8A0 + 8) - 16LL);
    if ( *(_QWORD *)(qword_18007F8A0 + 32) )
      __fastfail(5u);
    v8 = qword_18007F8A0 + 32;
    *(_QWORD *)(qword_18007F8A0 + 40) = 0;
    v7[6] = 0;
    if ( !(unsigned int)EtwEventRegister(&v19, tlgEnableCallback, v7, v8) )
      EtwEventSetInformation(v7[4], 2, v7[1], *(unsigned __int16 *)v7[1]);
    dword_18007F89C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18007F888 + 8))(&qword_18007F888);
    InitOnceComplete(&`ProfileLogging::Instance'::`2'::wrapper, 0, &qword_18007F888);
  }
  Ptr = SRWLock[1].Ptr;
  if ( *(_DWORD *)Ptr > 4u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = *((_QWORD *)this + 34);
    LODWORD(v17) = CurrentThreadId;
    v18 = 0x1000000;
    if ( !*(_BYTE *)(v11 + 4)
      || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
      && !*(_DWORD *)(v11 + 28)
      && !*(_DWORD *)(v11 + 32)
      && !*(_DWORD *)(v11 + 36) )
    {
      v12 = 0;
    }
    if ( a2 )
    {
      v13 = -1;
      while ( a2[++v13] != 0 )
        ;
      v15 = 2 * v13 + 2;
    }
    else
    {
      a2 = &qword_180061CC0;
      v15 = 2;
    }
    v31 = v15;
    v30 = a2;
    v28 = &v17;
    v32 = 0;
    v26 = &v18;
    v20 = (unsigned __int16 *)Ptr[1];
    v29 = 4;
    v27 = 8;
    v19 = 0x1040B000000uLL;
    v21 = *v20;
    v23 = byte_180070ECD;
    v22 = 2;
    v24 = 66;
    v25 = 1;
    EtwEventWriteTransfer(
      Ptr[4],
      &v19,
      v11 + 8,
      v12,
      5,
      &v20,
      (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata,
      v17,
      v18);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((ProfileTelemetry::UnmountRegHive *)((char *)this + 288));
}

```

## disassembly

```asm
0x180009690  mov     r11, rsp
0x180009693  push    rbp
0x180009694  lea     rbp, [r11-5Fh]
0x180009698  sub     rsp, 0E0h
0x18000969f  mov     rax, cs:__security_cookie
0x1800096a6  xor     rax, rsp
0x1800096a9  mov     [rbp+57h+var_30], rax
0x1800096ad  mov     [r11+10h], rbx
0x1800096b1  mov     rbx, [rcx+118h]
0x1800096b8  mov     [r11+18h], rsi
0x1800096bc  mov     rsi, rcx
0x1800096bf  mov     [r11-10h], rdi
0x1800096c3  mov     rdi, rdx
0x1800096c6  mov     [r11-20h], r14
0x1800096ca  mov     [r11-28h], r15
0x1800096ce  xor     r15d, r15d
0x1800096d1  test    rbx, rbx
0x1800096d4  jz      short loc_1800096FE
0x1800096d6  add     rbx, 108h
0x1800096dd  mov     rcx, rbx; SRWLock
0x1800096e0  call    cs:__imp_AcquireSRWLockExclusive
0x1800096e6  lea     rax, [rbp+57h+SRWLock]
0x1800096ea  mov     [rax], r15
0x1800096ed  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800096f1  test    rcx, rcx
0x1800096f4  jz      short loc_180009717
0x1800096f6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800096fc  jmp     short loc_180009717
0x1800096fe  lea     rax, [rbp+57h+var_A8]
0x180009702  mov     [rax], r15
0x180009705  mov     rcx, [rbp+57h+var_A8]; SRWLock
0x180009709  test    rcx, rcx
0x18000970c  jz      short loc_180009714
0x18000970e  call    cs:__imp_ReleaseSRWLockExclusive
0x180009714  mov     rbx, r15
0x180009717  mov     r14, [rsi+110h]
0x18000971e  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x180009723  mov     ecx, [rax]
0x180009725  cmp     ecx, 4
0x180009728  jbe     short loc_18000973B
0x18000972a  lea     rdx, [r14+8]
0x18000972e  mov     ecx, 3
0x180009733  call    cs:__imp_EtwEventActivityIdControl
0x180009739  jmp     short loc_180009743
0x18000973b  xorps   xmm0, xmm0
0x18000973e  movups  xmmword ptr [r14+8], xmm0
0x180009743  mov     dword ptr [r14], 1
0x18000974a  test    rbx, rbx
0x18000974d  jz      short loc_180009758
0x18000974f  mov     rcx, rbx; SRWLock
0x180009752  call    cs:__imp_ReleaseSRWLockExclusive
0x180009758  lea     r9, [rbp+57h+SRWLock]; lpContext
0x18000975c  mov     [rbp+57h+SRWLock], r15
0x180009760  lea     r8, [rbp+57h+var_A8]; fPending
0x180009764  mov     dword ptr [rbp+57h+var_A8], r15d
0x180009768  xor     edx, edx; dwFlags
0x18000976a  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x180009771  call    cs:__imp_InitOnceBeginInitialize
0x180009777  test    eax, eax
0x180009779  jz      loc_180009879
0x18000977f  cmp     dword ptr [rbp+57h+var_A8], r15d
0x180009783  jz      loc_180009879
0x180009789  mov     [rsp+0E0h+var_10], r12
0x180009791  lea     rax, ??_7ProfileLogging@@6B@; const ProfileLogging::`vftable'
0x180009798  lea     r12, qword_18007F888
0x18000979f  mov     cs:qword_18007F890, r15
0x1800097a6  mov     [rbp+57h+SRWLock], r12
0x1800097aa  mov     cs:byte_18007F898, r15b
0x1800097b1  mov     cs:dword_18007F89C, r15d
0x1800097b8  mov     cs:qword_18007F888, rax
0x1800097bf  lea     rax, ?__hInner@?1???0StaticHandle@ProfileLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ProfileLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800097c6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_cff094b7b3eb7b3291eb3a07719b48ba_@@CA@XZ; void (__cdecl *)()
0x1800097cd  mov     cs:qword_18007F8A0, rax
0x1800097d4  call    atexit
0x1800097d9  mov     rbx, cs:qword_18007F8A0
0x1800097e0  mov     cs:qword_18007F890, rbx
0x1800097e7  mov     cs:byte_18007F898, 1
0x1800097ee  mov     rax, [rbx+8]
0x1800097f2  movups  xmm0, xmmword ptr [rax-10h]
0x1800097f6  movups  [rbp+57h+var_98], xmm0
0x1800097fa  cmp     [rbx+20h], r15
0x1800097fe  jz      short loc_180009807
0x180009800  mov     ecx, 5
0x180009805  int     29h; Win8: RtlFailFast(ecx)
0x180009807  lea     r9, [rbx+20h]
0x18000980b  mov     [rbx+28h], r15
0x18000980f  mov     r8, rbx
0x180009812  mov     [rbx+30h], r15
0x180009816  lea     rdx, _tlgEnableCallback
0x18000981d  lea     rcx, [rbp+57h+var_98]
0x180009821  call    cs:__imp_EtwEventRegister
0x180009827  test    eax, eax
0x180009829  jnz     short loc_180009842
0x18000982b  mov     r8, [rbx+8]
0x18000982f  mov     edx, 2
0x180009834  mov     rcx, [rbx+20h]
0x180009838  movzx   r9d, word ptr [r8]
0x18000983c  call    cs:__imp_EtwEventSetInformation
0x180009842  mov     rax, cs:qword_18007F888
0x180009849  mov     rcx, r12
0x18000984c  mov     cs:dword_18007F89C, 1
0x180009856  mov     rax, [rax+8]
0x18000985a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000985f  mov     r8, r12; lpContext
0x180009862  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x180009869  xor     edx, edx; dwFlags
0x18000986b  call    cs:__imp_InitOnceComplete
0x180009871  mov     r12, [rsp+0E0h+var_10]
0x180009879  mov     rax, [rbp+57h+SRWLock]
0x18000987d  mov     r14, [rsp+0E0h+var_18]
0x180009885  mov     rbx, [rax+8]
0x180009889  mov     eax, [rbx]
0x18000988b  cmp     eax, 4
0x18000988e  jbe     loc_1800099A8
0x180009894  call    cs:__imp_GetCurrentThreadId
0x18000989a  mov     r8, [rsi+110h]
0x1800098a1  mov     dword ptr [rbp+57h+var_A8], eax
0x1800098a4  mov     [rbp+57h+var_A0], 1000000h
0x1800098ac  cmp     [r8+4], r15b
0x1800098b0  jz      short loc_1800098CE
0x1800098b2  cmp     [r8+18h], r15d
0x1800098b6  lea     r9, [r8+18h]
0x1800098ba  jnz     short loc_1800098D1
0x1800098bc  cmp     [r9+4], r15d
0x1800098c0  jnz     short loc_1800098D1
0x1800098c2  cmp     [r9+8], r15d
0x1800098c6  jnz     short loc_1800098D1
0x1800098c8  cmp     [r9+0Ch], r15d
0x1800098cc  jnz     short loc_1800098D1
0x1800098ce  mov     r9, r15
0x1800098d1  test    rdi, rdi
0x1800098d4  jz      short loc_1800098F5
0x1800098d6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800098dd  nop     dword ptr [rax]
0x1800098e0  cmp     [rdi+rax*2+2], r15w
0x1800098e6  lea     rax, [rax+1]
0x1800098ea  jnz     short loc_1800098E0
0x1800098ec  lea     eax, ds:2[rax*2]
0x1800098f3  jmp     short loc_180009901
0x1800098f5  lea     rdi, qword_180061CC0
0x1800098fc  mov     eax, 2
0x180009901  mov     [rbp+57h+var_38], eax
0x180009904  lea     rcx, _TraceLoggingMetadata
0x18000990b  mov     [rbp+57h+var_40], rdi
0x18000990f  lea     rax, [rbp+57h+var_A8]
0x180009913  mov     [rbp+57h+var_50], rax
0x180009917  lea     rdx, [rbp+57h+var_98]
0x18000991b  lea     rax, [rbp+57h+var_A0]
0x18000991f  mov     [rbp+57h+var_34], r15d
0x180009923  mov     [rbp+57h+var_60], rax
0x180009927  add     r8, 8
0x18000992b  movzx   eax, cs:word_180070EC3
0x180009932  mov     dword ptr [rbp+57h+var_98+4], eax
0x180009935  mov     rax, [rbx+8]
0x180009939  mov     [rbp+57h+var_80], rax
0x18000993d  mov     [rbp+57h+var_48], 4
0x180009945  mov     [rbp+57h+var_58], 8
0x18000994d  mov     dword ptr [rbp+57h+var_98], 0B000000h
0x180009954  mov     qword ptr [rbp+57h+var_98+8], r15
0x180009958  movzx   eax, word ptr [rax]
0x18000995b  mov     [rbp+57h+var_78], eax
0x18000995e  lea     rax, byte_180070ECD
0x180009965  mov     [rbp+57h+var_70], rax
0x180009969  lea     rax, _TraceLoggingMetadataEnd
0x180009970  sub     eax, ecx
0x180009972  mov     [rbp+57h+var_74], 2
0x180009979  mov     [rbp+57h+var_68], 42h ; 'B'
0x180009980  mov     [rbp+57h+var_64], 1
0x180009987  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000998a  mov     eax, dword ptr [rbp+57h+SRWLock]
0x18000998d  mov     rcx, [rbx+20h]
0x180009991  lea     rax, [rbp+57h+var_80]
0x180009995  mov     [rsp+28h], rax
0x18000999a  mov     dword ptr [rsp+0E0h+var_C0], 5
0x1800099a2  call    cs:__imp_EtwEventWriteTransfer
0x1800099a8  mov     r15, [rsp+0E0h+var_20]
0x1800099b0  lea     rcx, [rsi+120h]; this
0x1800099b7  cmp     dword ptr [rcx+18h], 0
0x1800099bb  mov     rdi, [rsp+0D8h]
0x1800099c3  mov     rsi, [rsp+0E0h+arg_10]
0x1800099cb  mov     rbx, [rsp+0E0h+arg_8]
0x1800099d3  jnz     short loc_1800099DA
0x1800099d5  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800099da  mov     rcx, [rbp+57h+var_30]
0x1800099de  xor     rcx, rsp; StackCookie
0x1800099e1  call    __security_check_cookie
0x1800099e6  add     rsp, 0E0h
0x1800099ed  pop     rbp
0x1800099ee  retn
```
