# GetCertInfo_0

- ea: `0x180046a34`
- end: `0x180046d61`
- name: `GetCertInfo_0`
- size: `813`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180045c38`
- `0x18004696c`

## callees

- `0x180009924`
- `0x18000f35c`
- `0x18000f430`
- `0x18000faec`
- `0x180010b88`
- `0x18002c61c`
- `0x180046a34`
- `0x180047b00`
- `0x180047b84`
- `0x1800486a0`
- `0x1800487e8`
- `0x1800d6ea0`
- `0x1800e4010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180046b93`
- `KERNEL32!LeaveCriticalSection` at `0x180046c11`
- `KERNEL32!LeaveCriticalSection` at `0x180046c5f`
- `KERNEL32!LeaveCriticalSection` at `0x180046b93`
- `KERNEL32!LeaveCriticalSection` at `0x180046c11`
- `KERNEL32!LeaveCriticalSection` at `0x180046c5f`
- `mqsec!MQSigCreateCertificate` at `0x180046a84`
- `mqsec!MQSigCreateCertificate` at `0x180046a84`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetCertInfo_0(__int64 a1, unsigned int a2, const WCHAR *a3, DWORD a4, int a5, _QWORD *a6)
{
  int v10; // eax
  int v11; // ebx
  unsigned __int16 v12; // r8
  int v13; // eax
  int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // ebx
  int v19; // eax
  int v20; // ebx
  CReference *v21; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v22[2]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v23; // [rsp+48h] [rbp-30h] BYREF
  int v24; // [rsp+58h] [rbp-20h]
  int v25; // [rsp+5Ch] [rbp-1Ch] BYREF

  SafeRelease<CSockTransport>(*a6);
  *a6 = 0;
  v21 = 0;
  v10 = MQSigCreateCertificate(&v21, 0, a1, a2);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        26,
        WPP_c687450366573ca356992ecf9dac13b8_Traceguids,
        (unsigned int)v10);
    v12 = 100;
LABEL_11:
    LogMsgHR(v11, (wchar_t *)L"qmsecutl", v12);
    if ( v21 )
      CReference::Release(v21);
    return 3222143020LL;
  }
  v25 = 20;
  v23 = 0;
  v24 = 0;
  v13 = (*(__int64 (__fastcall **)(CReference *, __int64, __int128 *, int *))(*(_QWORD *)v21 + 168LL))(
          v21,
          32772,
          &v23,
          &v25);
  v11 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        27,
        WPP_c687450366573ca356992ecf9dac13b8_Traceguids,
        (unsigned int)v13);
    v12 = 101;
    goto LABEL_11;
  }
  while ( 1 )
  {
    CCriticalSection::Lock((CCriticalSection *)&stru_18013A9D8);
    v15 = CCache<CCertificateHash,R<CERTINFO>,CNullExpirationHandler<R<CERTINFO>>>::Lookup(&qword_18013A9D0, &v23, a6);
    LeaveCriticalSection(&stru_18013A9D8);
    if ( v15 )
      goto LABEL_19;
    v22[0] = 0;
    v16 = LookupCertInAD(&v21, a3, a4, (__int64)v22);
    v17 = v16;
    if ( v16 < 0 )
      break;
    v22[1] = &stru_18013A9D8;
    CCriticalSection::Lock((CCriticalSection *)&stru_18013A9D8);
    v18 = CCache<CCertificateHash,R<CERTINFO>,CNullExpirationHandler<R<CERTINFO>>>::Lookup(&qword_18013A9D0, &v23, a6);
    if ( !v18 )
    {
      CCache<CCertificateHash,R<CERTINFO>,CNullExpirationHandler<R<CERTINFO>>>::SetAt(&qword_18013A9D0, &v23, v22);
      R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(a6, v22);
    }
    LeaveCriticalSection(&stru_18013A9D8);
    SafeRelease<CSockTransport>(v22[0]);
    if ( !v18 )
    {
LABEL_25:
      if ( !*(_QWORD *)(*a6 + 32LL) )
      {
        v19 = (*(__int64 (__fastcall **)(CReference *, CReference *, __int64))(*(_QWORD *)v21 + 152LL))(v21, v21, 7);
        v20 = v19;
        if ( v19 < 0 )
          LogMsgHR(v19, (wchar_t *)L"qmsecutl", 0x46Bu);
        *(_BYTE *)(*a6 + 40LL) = v20 != -1072821203;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            28,
            WPP_c687450366573ca356992ecf9dac13b8_Traceguids,
            *(unsigned __int8 *)(*a6 + 40LL));
      }
      if ( v21 )
        CReference::Release(v21);
      return 0;
    }
LABEL_19:
    if ( !a5 || *(_QWORD *)(*a6 + 32LL) )
      goto LABEL_25;
    CCriticalSection::Lock((CCriticalSection *)&stru_18013A9D8);
    CMap<CCertificateHash,CCertificateHash const &,CCacheEntry<R<CERTINFO>,R<CERTINFO> const &>,CCacheEntry<R<CERTINFO>,R<CERTINFO> const &> const &>::RemoveKey(
      &qword_18013AA50,
      &v23);
    SafeRelease<CSockTransport>(*a6);
    *a6 = 0;
    LeaveCriticalSection(&stru_18013A9D8);
  }
  LogMsgHR(v16, (wchar_t *)L"qmsecutl", 0x78u);
  SafeRelease<CSockTransport>(v22[0]);
  if ( v21 )
    CReference::Release(v21);
  return v17;
}

```

## disassembly

```asm
0x180046a34  push    rbp
0x180046a36  push    rbx
0x180046a37  push    rsi
0x180046a38  push    rdi
0x180046a39  push    r14
0x180046a3b  push    r15
0x180046a3d  mov     rbp, rsp
0x180046a40  sub     rsp, 78h
0x180046a44  mov     rax, cs:__security_cookie
0x180046a4b  xor     rax, rsp
0x180046a4e  mov     [rbp+var_18], rax
0x180046a52  mov     r15d, r9d
0x180046a55  mov     r14, r8
0x180046a58  mov     edi, edx
0x180046a5a  mov     rbx, rcx
0x180046a5d  mov     rsi, [rbp+arg_28]
0x180046a61  mov     rcx, [rsi]
0x180046a64  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180046a69  mov     qword ptr [rsi], 0
0x180046a70  mov     [rbp+var_48], 0
0x180046a78  mov     r9d, edi
0x180046a7b  mov     r8, rbx
0x180046a7e  xor     edx, edx
0x180046a80  lea     rcx, [rbp+var_48]
0x180046a84  call    cs:__imp_MQSigCreateCertificate
0x180046a8a  mov     ebx, eax
0x180046a8c  test    eax, eax
0x180046a8e  jns     short loc_180046ACF
0x180046a90  lea     rdx, WPP_GLOBAL_Control
0x180046a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180046a9e  cmp     rcx, rdx
0x180046aa1  jz      short loc_180046AC7
0x180046aa3  test    byte ptr [rcx+10Ch], 1
0x180046aaa  jz      short loc_180046AC7
0x180046aac  mov     edx, 1Ah
0x180046ab1  mov     r9d, eax
0x180046ab4  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x180046abb  mov     rcx, [rcx+100h]
0x180046ac2  call    WPP_SF_d
0x180046ac7  mov     r8d, 64h ; 'd'
0x180046acd  jmp     short loc_180046B45
0x180046acf  mov     [rbp+var_1C], 14h
0x180046ad6  xorps   xmm0, xmm0
0x180046ad9  xor     eax, eax
0x180046adb  movups  [rbp+var_30], xmm0
0x180046adf  mov     [rbp+var_20], eax
0x180046ae2  mov     rcx, [rbp+var_48]
0x180046ae6  mov     rax, [rcx]
0x180046ae9  lea     r9, [rbp+var_1C]
0x180046aed  lea     r8, [rbp+var_30]
0x180046af1  mov     edx, 8004h
0x180046af6  mov     rax, [rax+0A8h]
0x180046afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b02  mov     ebx, eax
0x180046b04  test    eax, eax
0x180046b06  jns     short loc_180046B6C
0x180046b08  lea     rdx, WPP_GLOBAL_Control
0x180046b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b16  cmp     rcx, rdx
0x180046b19  jz      short loc_180046B3F
0x180046b1b  test    byte ptr [rcx+10Ch], 1
0x180046b22  jz      short loc_180046B3F
0x180046b24  mov     edx, 1Bh
0x180046b29  mov     r9d, eax
0x180046b2c  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x180046b33  mov     rcx, [rcx+100h]
0x180046b3a  call    WPP_SF_d
0x180046b3f  mov     r8d, 65h ; 'e'; unsigned __int16
0x180046b45  lea     rdx, aQmsecutl; "qmsecutl"
0x180046b4c  mov     ecx, ebx; int
0x180046b4e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180046b53  nop
0x180046b54  mov     rcx, [rbp+var_48]; this
0x180046b58  test    rcx, rcx
0x180046b5b  jz      short loc_180046B62
0x180046b5d  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x180046b62  mov     eax, 0C00E002Ch
0x180046b67  jmp     loc_180046D48
0x180046b6c  lea     rdi, stru_18013A9D8
0x180046b73  mov     rcx, rdi; this
0x180046b76  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180046b7b  mov     r8, rsi
0x180046b7e  lea     rdx, [rbp+var_30]
0x180046b82  lea     rcx, qword_18013A9D0
0x180046b89  call    ?Lookup@?$CCache@VCCertificateHash@@V?$R@VCERTINFO@@@@V?$CNullExpirationHandler@V?$R@VCERTINFO@@@@@@@@QEBAHAEBVCCertificateHash@@AEAV?$R@VCERTINFO@@@@@Z; CCache<CCertificateHash,R<CERTINFO>,CNullExpirationHandler<R<CERTINFO>>>::Lookup(CCertificateHash const &,R<CERTINFO> &)
0x180046b8e  mov     ebx, eax
0x180046b90  mov     rcx, rdi; lpCriticalSection
0x180046b93  call    cs:__imp_LeaveCriticalSection
0x180046b99  nop
0x180046b9a  test    ebx, ebx
0x180046b9c  jnz     loc_180046C25
0x180046ba2  mov     [rbp+var_40], 0
0x180046baa  lea     r9, [rbp+var_40]
0x180046bae  mov     r8d, r15d
0x180046bb1  mov     rdx, r14
0x180046bb4  lea     rcx, [rbp+var_48]
0x180046bb8  call    LookupCertInAD
0x180046bbd  mov     ebx, eax
0x180046bbf  test    eax, eax
0x180046bc1  js      loc_180046C6B
0x180046bc7  mov     [rbp+var_38], rdi
0x180046bcb  mov     rcx, rdi; this
0x180046bce  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180046bd3  nop
0x180046bd4  mov     r8, rsi
0x180046bd7  lea     rdx, [rbp+var_30]
0x180046bdb  lea     rcx, qword_18013A9D0
0x180046be2  call    ?Lookup@?$CCache@VCCertificateHash@@V?$R@VCERTINFO@@@@V?$CNullExpirationHandler@V?$R@VCERTINFO@@@@@@@@QEBAHAEBVCCertificateHash@@AEAV?$R@VCERTINFO@@@@@Z; CCache<CCertificateHash,R<CERTINFO>,CNullExpirationHandler<R<CERTINFO>>>::Lookup(CCertificateHash const &,R<CERTINFO> &)
0x180046be7  mov     ebx, eax
0x180046be9  test    eax, eax
0x180046beb  jnz     short loc_180046C0E
0x180046bed  lea     r8, [rbp+var_40]
0x180046bf1  lea     rdx, [rbp+var_30]
0x180046bf5  lea     rcx, qword_18013A9D0
0x180046bfc  call    ?SetAt@?$CCache@VCCertificateHash@@V?$R@VCERTINFO@@@@V?$CNullExpirationHandler@V?$R@VCERTINFO@@@@@@@@QEAAXAEBVCCertificateHash@@AEBV?$R@VCERTINFO@@@@@Z; CCache<CCertificateHash,R<CERTINFO>,CNullExpirationHandler<R<CERTINFO>>>::SetAt(CCertificateHash const &,R<CERTINFO> const &)
0x180046c01  lea     rdx, [rbp+var_40]
0x180046c05  mov     rcx, rsi
0x180046c08  call    ??4?$R@UCTX_OPENREMOTE_HANDLE_TYPE@@@@QEAAAEAV0@AEBV0@@Z; R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(R<CTX_OPENREMOTE_HANDLE_TYPE> const &)
0x180046c0d  nop
0x180046c0e  mov     rcx, rdi; lpCriticalSection
0x180046c11  call    cs:__imp_LeaveCriticalSection
0x180046c17  nop
0x180046c18  mov     rcx, [rbp+var_40]
0x180046c1c  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180046c21  test    ebx, ebx
0x180046c23  jz      short loc_180046C9F
0x180046c25  cmp     [rbp+arg_20], 0
0x180046c29  jz      short loc_180046C9F
0x180046c2b  mov     rax, [rsi]
0x180046c2e  cmp     qword ptr [rax+20h], 0
0x180046c33  jnz     short loc_180046C9F
0x180046c35  mov     rcx, rdi; this
0x180046c38  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180046c3d  lea     rdx, [rbp+var_30]
0x180046c41  lea     rcx, qword_18013AA50
0x180046c48  call    ?RemoveKey@?$CMap@VCCertificateHash@@AEBV1@V?$CCacheEntry@V?$R@VCERTINFO@@@@AEBV1@@@AEBV2@@@QEAAHAEBVCCertificateHash@@@Z; CMap<CCertificateHash,CCertificateHash const &,CCacheEntry<R<CERTINFO>,R<CERTINFO> const &>,CCacheEntry<R<CERTINFO>,R<CERTINFO> const &> const &>::RemoveKey(CCertificateHash const &)
0x180046c4d  mov     rcx, [rsi]
0x180046c50  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180046c55  mov     qword ptr [rsi], 0
0x180046c5c  mov     rcx, rdi; lpCriticalSection
0x180046c5f  call    cs:__imp_LeaveCriticalSection
0x180046c65  nop
0x180046c66  jmp     loc_180046B73
0x180046c6b  mov     r8d, 78h ; 'x'; unsigned __int16
0x180046c71  lea     rdx, aQmsecutl; "qmsecutl"
0x180046c78  mov     ecx, ebx; int
0x180046c7a  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180046c7f  nop
0x180046c80  mov     rcx, [rbp+var_40]
0x180046c84  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180046c89  nop
0x180046c8a  mov     rcx, [rbp+var_48]; this
0x180046c8e  test    rcx, rcx
0x180046c91  jz      short loc_180046C98
0x180046c93  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x180046c98  mov     eax, ebx
0x180046c9a  jmp     loc_180046D48
0x180046c9f  mov     rax, [rsi]
0x180046ca2  cmp     qword ptr [rax+20h], 0
0x180046ca7  jnz     loc_180046D38
0x180046cad  mov     rcx, [rbp+var_48]
0x180046cb1  mov     rax, [rcx]
0x180046cb4  mov     [rsp+78h+var_58], 1
0x180046cbc  xor     r9d, r9d
0x180046cbf  lea     r8d, [r9+7]
0x180046cc3  mov     rdx, rcx
0x180046cc6  mov     rax, [rax+98h]
0x180046ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cd2  mov     ebx, eax
0x180046cd4  test    eax, eax
0x180046cd6  jns     short loc_180046CEC
0x180046cd8  mov     r8d, 46Bh; unsigned __int16
0x180046cde  lea     rdx, aQmsecutl; "qmsecutl"
0x180046ce5  mov     ecx, eax; int
0x180046ce7  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180046cec  cmp     ebx, 0C00E0C2Dh
0x180046cf2  setnz   cl
0x180046cf5  mov     rax, [rsi]
0x180046cf8  mov     [rax+28h], cl
0x180046cfb  lea     rdx, WPP_GLOBAL_Control
0x180046d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180046d09  cmp     rcx, rdx
0x180046d0c  jz      short loc_180046D38
0x180046d0e  test    byte ptr [rcx+10Ch], 2
0x180046d15  jz      short loc_180046D38
0x180046d17  mov     rax, [rsi]
0x180046d1a  movzx   r9d, byte ptr [rax+28h]
0x180046d1f  mov     edx, 1Ch
0x180046d24  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x180046d2b  mov     rcx, [rcx+100h]
0x180046d32  call    WPP_SF_d
0x180046d37  nop
0x180046d38  mov     rcx, [rbp+var_48]; this
0x180046d3c  test    rcx, rcx
0x180046d3f  jz      short loc_180046D46
0x180046d41  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x180046d46  xor     eax, eax
0x180046d48  mov     rcx, [rbp+var_18]
0x180046d4c  xor     rcx, rsp; StackCookie
0x180046d4f  call    __security_check_cookie
0x180046d54  add     rsp, 78h
0x180046d58  pop     r15
0x180046d5a  pop     r14
0x180046d5c  pop     rdi
0x180046d5d  pop     rsi
0x180046d5e  pop     rbx
0x180046d5f  pop     rbp
0x180046d60  retn
```
