# ProfileTelemetry::UnmountRegHive::StartActivity(ushort const *)

- ea: `0x180006a10`
- end: `0x180006db6`
- name: `?StartActivity@UnmountRegHive@ProfileTelemetry@@QEAAXPEBG@Z`
- size: `934`
- prototype: `void __fastcall(ProfileTelemetry::UnmountRegHive *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006498`
- `0x1800066cc`

## callees

- `0x180006a10`
- `0x180014c90`
- `0x180017220`
- `0x18003bc70`
- `0x18003c020`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006a60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006a60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006a7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006a9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006aea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006a7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006a9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006aea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c4a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006b0f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006b0f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006c1b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006c1b`
- `ntdll!EtwEventActivityIdControl` at `0x180006ac5`
- `ntdll!EtwEventActivityIdControl` at `0x180006ac5`
- `ntdll!EtwEventWriteTransfer` at `0x180006d62`
- `ntdll!EtwEventWriteTransfer` at `0x180006d62`
- `ntdll!EtwEventSetInformation` at `0x180006be6`
- `ntdll!EtwEventSetInformation` at `0x180006be6`
- `ntdll!EtwEventRegister` at `0x180006bc5`
- `ntdll!EtwEventRegister` at `0x180006bc5`

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
    qword_180082990 = 0;
    SRWLock = (PSRWLOCK)&qword_180082988;
    byte_180082998 = 0;
    dword_18008299C = 0;
    qword_180082988 = (__int64)&ProfileLogging::`vftable';
    qword_1800829A0 = (__int64)&`ProfileLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_cff094b7b3eb7b3291eb3a07719b48ba_::_lambda_invoker_cdecl_);
    v7 = (_QWORD *)qword_1800829A0;
    qword_180082990 = qword_1800829A0;
    byte_180082998 = 1;
    v19 = *(_OWORD *)(*(_QWORD *)(qword_1800829A0 + 8) - 16LL);
    if ( *(_QWORD *)(qword_1800829A0 + 32) )
      __fastfail(5u);
    v8 = qword_1800829A0 + 32;
    *(_QWORD *)(qword_1800829A0 + 40) = 0;
    v7[6] = 0;
    if ( !(unsigned int)EtwEventRegister(&v19, tlgEnableCallback, v7, v8) )
      EtwEventSetInformation(v7[4], 2, v7[1], *(unsigned __int16 *)v7[1]);
    dword_18008299C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180082988 + 8))(&qword_180082988);
    InitOnceComplete(&`ProfileLogging::Instance'::`2'::wrapper, 0, &qword_180082988);
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
      a2 = &qword_1800649D8;
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
    v23 = byte_180073F85;
    v22 = 2;
    v24 = 66;
    v25 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(Ptr[4], &v19, v11 + 8, v12, 5, &v20);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((ProfileTelemetry::UnmountRegHive *)((char *)this + 288));
}

```

## disassembly

```asm
0x180006a10  mov     r11, rsp
0x180006a13  push    rbp
0x180006a14  lea     rbp, [r11-5Fh]
0x180006a18  sub     rsp, 0E0h
0x180006a1f  mov     rax, cs:__security_cookie
0x180006a26  xor     rax, rsp
0x180006a29  mov     [rbp+57h+var_30], rax
0x180006a2d  mov     [r11+10h], rbx
0x180006a31  mov     rbx, [rcx+118h]
0x180006a38  mov     [r11+18h], rsi
0x180006a3c  mov     rsi, rcx
0x180006a3f  mov     [r11-10h], rdi
0x180006a43  mov     rdi, rdx
0x180006a46  mov     [r11-20h], r14
0x180006a4a  mov     [r11-28h], r15
0x180006a4e  xor     r15d, r15d
0x180006a51  test    rbx, rbx
0x180006a54  jz      short loc_180006A8A
0x180006a56  add     rbx, 108h
0x180006a5d  mov     rcx, rbx; SRWLock
0x180006a60  call    cs:__imp_AcquireSRWLockExclusive
0x180006a67  nop     dword ptr [rax+rax+00h]
0x180006a6c  lea     rax, [rbp+57h+SRWLock]
0x180006a70  mov     [rax], r15
0x180006a73  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180006a77  test    rcx, rcx
0x180006a7a  jz      short loc_180006AA9
0x180006a7c  call    cs:__imp_ReleaseSRWLockExclusive
0x180006a83  nop     dword ptr [rax+rax+00h]
0x180006a88  jmp     short loc_180006AA9
0x180006a8a  lea     rax, [rbp+57h+var_A8]
0x180006a8e  mov     [rax], r15
0x180006a91  mov     rcx, [rbp+57h+var_A8]; SRWLock
0x180006a95  test    rcx, rcx
0x180006a98  jz      short loc_180006AA6
0x180006a9a  call    cs:__imp_ReleaseSRWLockExclusive
0x180006aa1  nop     dword ptr [rax+rax+00h]
0x180006aa6  mov     rbx, r15
0x180006aa9  mov     r14, [rsi+110h]
0x180006ab0  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x180006ab5  mov     ecx, [rax]
0x180006ab7  cmp     ecx, 4
0x180006aba  jbe     short loc_180006AD3
0x180006abc  lea     rdx, [r14+8]
0x180006ac0  mov     ecx, 3
0x180006ac5  call    cs:__imp_EtwEventActivityIdControl
0x180006acc  nop     dword ptr [rax+rax+00h]
0x180006ad1  jmp     short loc_180006ADB
0x180006ad3  xorps   xmm0, xmm0
0x180006ad6  movups  xmmword ptr [r14+8], xmm0
0x180006adb  mov     dword ptr [r14], 1
0x180006ae2  test    rbx, rbx
0x180006ae5  jz      short loc_180006AF6
0x180006ae7  mov     rcx, rbx; SRWLock
0x180006aea  call    cs:__imp_ReleaseSRWLockExclusive
0x180006af1  nop     dword ptr [rax+rax+00h]
0x180006af6  lea     r9, [rbp+57h+SRWLock]; lpContext
0x180006afa  mov     [rbp+57h+SRWLock], r15
0x180006afe  lea     r8, [rbp+57h+var_A8]; fPending
0x180006b02  mov     dword ptr [rbp+57h+var_A8], r15d
0x180006b06  xor     edx, edx; dwFlags
0x180006b08  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x180006b0f  call    cs:__imp_InitOnceBeginInitialize
0x180006b16  nop     dword ptr [rax+rax+00h]
0x180006b1b  test    eax, eax
0x180006b1d  jz      loc_180006C2F
0x180006b23  cmp     dword ptr [rbp+57h+var_A8], r15d
0x180006b27  jz      loc_180006C2F
0x180006b2d  mov     [rsp+0E0h+var_10], r12
0x180006b35  lea     rax, ??_7ProfileLogging@@6B@; const ProfileLogging::`vftable'
0x180006b3c  lea     r12, qword_180082988
0x180006b43  mov     cs:qword_180082990, r15
0x180006b4a  mov     [rbp+57h+SRWLock], r12
0x180006b4e  mov     cs:byte_180082998, r15b
0x180006b55  mov     cs:dword_18008299C, r15d
0x180006b5c  mov     cs:qword_180082988, rax
0x180006b63  lea     rax, ?__hInner@?1???0StaticHandle@ProfileLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ProfileLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180006b6a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_cff094b7b3eb7b3291eb3a07719b48ba_@@CA@XZ; void (__cdecl *)()
0x180006b71  mov     cs:qword_1800829A0, rax
0x180006b78  call    atexit
0x180006b7d  mov     rbx, cs:qword_1800829A0
0x180006b84  mov     cs:qword_180082990, rbx
0x180006b8b  mov     cs:byte_180082998, 1
0x180006b92  mov     rax, [rbx+8]
0x180006b96  movups  xmm0, xmmword ptr [rax-10h]
0x180006b9a  movups  [rbp+57h+var_98], xmm0
0x180006b9e  cmp     [rbx+20h], r15
0x180006ba2  jz      short loc_180006BAB
0x180006ba4  mov     ecx, 5
0x180006ba9  int     29h; Win8: RtlFailFast(ecx)
0x180006bab  lea     r9, [rbx+20h]
0x180006baf  mov     [rbx+28h], r15
0x180006bb3  mov     r8, rbx
0x180006bb6  mov     [rbx+30h], r15
0x180006bba  lea     rdx, _tlgEnableCallback
0x180006bc1  lea     rcx, [rbp+57h+var_98]
0x180006bc5  call    cs:__imp_EtwEventRegister
0x180006bcc  nop     dword ptr [rax+rax+00h]
0x180006bd1  test    eax, eax
0x180006bd3  jnz     short loc_180006BF2
0x180006bd5  mov     r8, [rbx+8]
0x180006bd9  mov     edx, 2
0x180006bde  mov     rcx, [rbx+20h]
0x180006be2  movzx   r9d, word ptr [r8]
0x180006be6  call    cs:__imp_EtwEventSetInformation
0x180006bed  nop     dword ptr [rax+rax+00h]
0x180006bf2  mov     rax, cs:qword_180082988
0x180006bf9  mov     rcx, r12
0x180006bfc  mov     cs:dword_18008299C, 1
0x180006c06  mov     rax, [rax+8]
0x180006c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c0f  mov     r8, r12; lpContext
0x180006c12  lea     rcx, ?wrapper@?1??Instance@ProfileLogging@@KAPEAV2@XZ@4V?$static_lazy@VProfileLogging@@@details@wil@@A; lpInitOnce
0x180006c19  xor     edx, edx; dwFlags
0x180006c1b  call    cs:__imp_InitOnceComplete
0x180006c22  nop     dword ptr [rax+rax+00h]
0x180006c27  mov     r12, [rsp+0E0h+var_10]
0x180006c2f  mov     rax, [rbp+57h+SRWLock]
0x180006c33  mov     r14, [rsp+0E0h+var_18]
0x180006c3b  mov     rbx, [rax+8]
0x180006c3f  mov     eax, [rbx]
0x180006c41  cmp     eax, 4
0x180006c44  jbe     loc_180006D6E
0x180006c4a  call    cs:__imp_GetCurrentThreadId
0x180006c51  nop     dword ptr [rax+rax+00h]
0x180006c56  mov     r8, [rsi+110h]
0x180006c5d  mov     dword ptr [rbp+57h+var_A8], eax
0x180006c60  mov     [rbp+57h+var_A0], 1000000h
0x180006c68  cmp     [r8+4], r15b
0x180006c6c  jz      short loc_180006C8A
0x180006c6e  cmp     [r8+18h], r15d
0x180006c72  lea     r9, [r8+18h]
0x180006c76  jnz     short loc_180006C8D
0x180006c78  cmp     [r9+4], r15d
0x180006c7c  jnz     short loc_180006C8D
0x180006c7e  cmp     [r9+8], r15d
0x180006c82  jnz     short loc_180006C8D
0x180006c84  cmp     [r9+0Ch], r15d
0x180006c88  jnz     short loc_180006C8D
0x180006c8a  mov     r9, r15
0x180006c8d  test    rdi, rdi
0x180006c90  jz      short loc_180006CB5
0x180006c92  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006c99  nop     dword ptr [rax+00000000h]
0x180006ca0  cmp     [rdi+rax*2+2], r15w
0x180006ca6  lea     rax, [rax+1]
0x180006caa  jnz     short loc_180006CA0
0x180006cac  lea     eax, ds:2[rax*2]
0x180006cb3  jmp     short loc_180006CC1
0x180006cb5  lea     rdi, qword_1800649D8
0x180006cbc  mov     eax, 2
0x180006cc1  mov     [rbp+57h+var_38], eax
0x180006cc4  lea     rcx, _TraceLoggingMetadata
0x180006ccb  mov     [rbp+57h+var_40], rdi
0x180006ccf  lea     rax, [rbp+57h+var_A8]
0x180006cd3  mov     [rbp+57h+var_50], rax
0x180006cd7  lea     rdx, [rbp+57h+var_98]
0x180006cdb  lea     rax, [rbp+57h+var_A0]
0x180006cdf  mov     [rbp+57h+var_34], r15d
0x180006ce3  mov     [rbp+57h+var_60], rax
0x180006ce7  add     r8, 8
0x180006ceb  movzx   eax, cs:word_180073F7B
0x180006cf2  mov     dword ptr [rbp+57h+var_98+4], eax
0x180006cf5  mov     rax, [rbx+8]
0x180006cf9  mov     [rbp+57h+var_80], rax
0x180006cfd  mov     [rbp+57h+var_48], 4
0x180006d05  mov     [rbp+57h+var_58], 8
0x180006d0d  mov     dword ptr [rbp+57h+var_98], 0B000000h
0x180006d14  mov     qword ptr [rbp+57h+var_98+8], r15
0x180006d18  movzx   eax, word ptr [rax]
0x180006d1b  mov     [rbp+57h+var_78], eax
0x180006d1e  lea     rax, byte_180073F85
0x180006d25  mov     [rbp+57h+var_70], rax
0x180006d29  lea     rax, _TraceLoggingMetadataEnd
0x180006d30  sub     eax, ecx
0x180006d32  mov     [rbp+57h+var_74], 2
0x180006d39  mov     [rbp+57h+var_68], 42h ; 'B'
0x180006d40  mov     [rbp+57h+var_64], 1
0x180006d47  mov     dword ptr [rbp+57h+SRWLock], eax
0x180006d4a  mov     eax, dword ptr [rbp+57h+SRWLock]
0x180006d4d  mov     rcx, [rbx+20h]
0x180006d51  lea     rax, [rbp+57h+var_80]
0x180006d55  mov     [rsp+28h], rax
0x180006d5a  mov     dword ptr [rsp+0E0h+var_C0], 5
0x180006d62  call    cs:__imp_EtwEventWriteTransfer
0x180006d69  nop     dword ptr [rax+rax+00h]
0x180006d6e  mov     r15, [rsp+0E0h+var_20]
0x180006d76  lea     rcx, [rsi+120h]; this
0x180006d7d  cmp     dword ptr [rcx+18h], 0
0x180006d81  mov     rdi, [rsp+0D8h]
0x180006d89  mov     rsi, [rsp+0E0h+arg_10]
0x180006d91  mov     rbx, [rsp+0E0h+arg_8]
0x180006d99  jnz     short loc_180006DA0
0x180006d9b  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180006da0  mov     rcx, [rbp+57h+var_30]
0x180006da4  xor     rcx, rsp; StackCookie
0x180006da7  call    __security_check_cookie
0x180006dac  add     rsp, 0E0h
0x180006db3  pop     rbp
0x180006db4  retn
```
