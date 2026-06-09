# IkeInplaceRekeyCompleteIkeV2

- ea: `0x1800e1944`
- end: `0x1800e1c92`
- name: `IkeInplaceRekeyCompleteIkeV2`
- size: `846`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800e0590`
- `0x1800e17b8`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180008388`
- `0x180018240`
- `0x18003cfa0`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x18004d2c8`
- `0x180050850`
- `0x180069e80`
- `0x18006db48`
- `0x18006e4f8`
- `0x180088e5c`
- `0x1800e1028`
- `0x1800e1944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e1c16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e1c16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e1be3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e1be3`

## string_xrefs

- `0x1800e197b`: `IkeInplaceRekeyCompleteIkeV2`
- `0x1800e1c4f`: `IkeInplaceRekeyCompleteIkeV2`
- `0x1800e1c5b`: `IkeInplaceRekeyCompleteIkeV2`
- `0x1800e1a26`: `IkeV2 inplace rekey complete`

## pseudocode

```c
__int64 __fastcall IkeInplaceRekeyCompleteIkeV2(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v7; // rcx
  int TlsMmLuid; // eax
  __int64 v9; // rcx
  const WCHAR *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r15
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  const WCHAR *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  _QWORD *v26; // rdx
  _QWORD *v27; // rax
  __int64 v28; // rcx
  __int64 *v29; // rcx
  __int64 v31; // [rsp+40h] [rbp-69h] BYREF
  __int64 v32; // [rsp+48h] [rbp-61h] BYREF
  __int64 v33; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v34[32]; // [rsp+60h] [rbp-49h] BYREF
  __int64 *v35; // [rsp+80h] [rbp-29h]
  __int64 v36; // [rsp+88h] [rbp-21h]
  _BYTE v37[16]; // [rsp+90h] [rbp-19h] BYREF
  const char *v38; // [rsp+A0h] [rbp-9h]
  __int64 v39; // [rsp+A8h] [rbp-1h]
  __int64 *v40; // [rsp+B0h] [rbp+7h]
  __int64 v41; // [rsp+B8h] [rbp+Fh]
  __int64 *v42; // [rsp+C0h] [rbp+17h]
  __int64 v43; // [rsp+C8h] [rbp+1Fh]

  TraceLogHelper("IkeInplaceRekeyCompleteIkeV2", 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v5 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v4);
    TlsMmLuid = IkeGetTlsMmLuid(v7);
    WPP_SF_iSqq(v5, 11, (unsigned int)WPP_639729265dbb3b0803814a57dbffdef8_Traceguids, TlsMmLuid, TlsPeerAddr, a1, a2);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v33 = IkeGetTlsMmLuid(v4);
    v35 = &v33;
    v36 = 8;
    v10 = (const WCHAR *)IkeGetTlsPeerAddr(v9);
    tlgCreate1Sz_wchar_t((__int64)v37, v10);
    v39 = 29;
    v40 = &v31;
    v38 = "IkeV2 inplace rekey complete";
    v42 = &v32;
    v31 = a1;
    v41 = 8;
    v32 = a2;
    v43 = 8;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_180173278,
      (unsigned __int8 *)byte_18016148F,
      v11,
      v12,
      7,
      (__int64)v34);
  }
  v13 = IkeCopyOldMMToNewMMIkeV2(a1, a2);
  if ( !v13
    && (!(unsigned int)IkeIsCertAuth(*(unsigned int *)(*(_QWORD *)(a2 + 1104) + 504LL))
     && !(unsigned int)IkeIsCertAuth(*(unsigned int *)(v14 + 500))
     || (v13 = IkeAdjustMMRekeyLifetimeFromCertIkeV2(a2)) == 0) )
  {
    v13 = IkeMMEstablished(a2);
    if ( !v13 )
    {
      v15 = *(_QWORD *)(a2 + 1008);
      if ( v15 )
      {
        if ( (*(_BYTE *)(v15 + 376) & 0x20) != 0 )
        {
          IkeFreeAcquireContext(v15);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v16 = *(_QWORD *)(v15 + 360);
            v17 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v18 = IkeGetTlsPeerAddr(v15);
            v20 = IkeGetTlsMmLuid(v19);
            WPP_SF_iSI(v17, 12, (unsigned int)WPP_639729265dbb3b0803814a57dbffdef8_Traceguids, v20, v18, v16);
          }
          if ( (unsigned int)dword_180173278 > 4 )
          {
            v32 = IkeGetTlsMmLuid(v15);
            v35 = &v32;
            v36 = 8;
            v22 = (const WCHAR *)IkeGetTlsPeerAddr(v21);
            tlgCreate1Sz_wchar_t((__int64)v37, v22);
            v23 = *(_QWORD *)(a2 + 1008);
            v38 = "Handing off inplace rekey acquire";
            v39 = 34;
            v24 = *(_QWORD *)(v23 + 360);
            v40 = &v31;
            v31 = v24;
            v41 = 8;
            tlgWriteTransfer_EtwEventWriteTransfer(
              (__int64)&dword_180173278,
              (unsigned __int8 *)byte_180161441,
              v25,
              (__int64)"Handing off inplace rekey acquire",
              6,
              (__int64)v34);
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 48));
          v26 = *(_QWORD **)(a2 + 120);
          if ( *v26 != a2 + 112 )
            __fastfail(3u);
          v27 = *(_QWORD **)(a2 + 1008);
          *v27 = a2 + 112;
          v27[1] = v26;
          *v26 = v27;
          *(_QWORD *)(a2 + 120) = v27;
          LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 48));
        }
        *(_QWORD *)(a2 + 1008) = 0;
      }
      v28 = *(_QWORD *)(a1 + 1104);
      *(_DWORD *)(a1 + 592) |= 0x8000u;
      v29 = (__int64 *)(v28 + 128);
      if ( *v29 )
        IkeDestroyTimerContext(v29);
    }
  }
  TraceLogHelper("IkeInplaceRekeyCompleteIkeV2", 0);
  return IkeReturnError(v13, "IkeInplaceRekeyCompleteIkeV2");
}

```

## disassembly

```asm
0x1800e1944  mov     [rsp-8+arg_10], rbx
0x1800e1949  mov     [rsp-8+arg_18], rsi
0x1800e194e  push    rbp
0x1800e194f  push    rdi
0x1800e1950  push    r13
0x1800e1952  push    r14
0x1800e1954  push    r15
0x1800e1956  lea     rbp, [rsp-37h]
0x1800e195b  sub     rsp, 0E0h
0x1800e1962  mov     rax, cs:__security_cookie
0x1800e1969  xor     rax, rsp
0x1800e196c  mov     [rbp+57h+var_30], rax
0x1800e1970  mov     r14, rdx
0x1800e1973  mov     r13, rcx
0x1800e1976  mov     edx, 1
0x1800e197b  lea     rcx, aIkeinplacereke; "IkeInplaceRekeyCompleteIkeV2"
0x1800e1982  call    TraceLogHelper
0x1800e1987  mov     rdi, cs:WPP_GLOBAL_Control
0x1800e198e  lea     rax, WPP_GLOBAL_Control
0x1800e1995  cmp     rdi, rax
0x1800e1998  jz      short loc_1800E19DD
0x1800e199a  cmp     byte ptr [rdi+19h], 4
0x1800e199e  jb      short loc_1800E19DD
0x1800e19a0  test    byte ptr [rdi+1Ch], 10h
0x1800e19a4  jz      short loc_1800E19DD
0x1800e19a6  mov     rdi, [rdi+10h]
0x1800e19aa  call    IkeGetTlsPeerAddr
0x1800e19af  mov     rbx, rax
0x1800e19b2  call    IkeGetTlsMmLuid
0x1800e19b7  mov     [rsp+100h+var_D0], r14
0x1800e19bc  lea     r8, WPP_639729265dbb3b0803814a57dbffdef8_Traceguids
0x1800e19c3  mov     r9, rax
0x1800e19c6  mov     [rsp+100h+var_D8], r13
0x1800e19cb  mov     edx, 0Bh
0x1800e19d0  mov     [rsp+100h+var_E0], rbx
0x1800e19d5  mov     rcx, rdi
0x1800e19d8  call    WPP_SF_iSqq
0x1800e19dd  mov     eax, cs:dword_180173278
0x1800e19e3  cmp     eax, 4
0x1800e19e6  jbe     loc_1800E1A75
0x1800e19ec  call    IkeGetTlsMmLuid
0x1800e19f1  mov     [rbp+57h+var_B0], rax
0x1800e19f5  lea     rax, [rbp+57h+var_B0]
0x1800e19f9  mov     [rbp+57h+var_80], rax
0x1800e19fd  mov     [rbp+57h+var_78], 8
0x1800e1a05  call    IkeGetTlsPeerAddr
0x1800e1a0a  mov     rdx, rax
0x1800e1a0d  lea     rcx, [rbp+57h+var_70]
0x1800e1a11  call    _tlgCreate1Sz_wchar_t
0x1800e1a16  lea     rax, [rbp+57h+var_C0]
0x1800e1a1a  mov     [rbp+57h+var_58], 1Dh
0x1800e1a22  mov     [rbp+57h+var_50], rax
0x1800e1a26  lea     rcx, aIkev2InplaceRe; "IkeV2 inplace rekey complete"
0x1800e1a2d  lea     rax, [rbp+57h+var_B8]
0x1800e1a31  mov     [rbp+57h+var_60], rcx
0x1800e1a35  mov     [rbp+57h+var_40], rax
0x1800e1a39  lea     rdx, byte_18016148F
0x1800e1a40  lea     rax, [rbp+57h+var_A0]
0x1800e1a44  mov     [rbp+57h+var_C0], r13
0x1800e1a48  mov     [rsp+100h+var_D8], rax
0x1800e1a4d  lea     rcx, dword_180173278
0x1800e1a54  mov     dword ptr [rsp+100h+var_E0], 7
0x1800e1a5c  mov     [rbp+57h+var_48], 8
0x1800e1a64  mov     [rbp+57h+var_B8], r14
0x1800e1a68  mov     [rbp+57h+var_38], 8
0x1800e1a70  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800e1a75  mov     rdx, r14
0x1800e1a78  mov     rcx, r13
0x1800e1a7b  call    IkeCopyOldMMToNewMMIkeV2
0x1800e1a80  mov     r15, rax
0x1800e1a83  test    rax, rax
0x1800e1a86  jnz     loc_1800E1C4D
0x1800e1a8c  mov     rdx, [r14+450h]
0x1800e1a93  mov     ecx, [rdx+1F8h]
0x1800e1a99  call    IkeIsCertAuth
0x1800e1a9e  test    eax, eax
0x1800e1aa0  jnz     short loc_1800E1AB1
0x1800e1aa2  mov     ecx, [rdx+1F4h]
0x1800e1aa8  call    IkeIsCertAuth
0x1800e1aad  test    eax, eax
0x1800e1aaf  jz      short loc_1800E1AC5
0x1800e1ab1  mov     rcx, r14
0x1800e1ab4  call    IkeAdjustMMRekeyLifetimeFromCertIkeV2
0x1800e1ab9  mov     r15, rax
0x1800e1abc  test    rax, rax
0x1800e1abf  jnz     loc_1800E1C4D
0x1800e1ac5  mov     rcx, r14
0x1800e1ac8  call    IkeMMEstablished
0x1800e1acd  mov     r15, rax
0x1800e1ad0  test    rax, rax
0x1800e1ad3  jnz     loc_1800E1C4D
0x1800e1ad9  mov     rcx, [r14+3F0h]
0x1800e1ae0  test    rcx, rcx
0x1800e1ae3  jz      loc_1800E1C2E
0x1800e1ae9  test    byte ptr [rcx+178h], 20h
0x1800e1af0  jnz     loc_1800E1C1E
0x1800e1af6  mov     rsi, cs:WPP_GLOBAL_Control
0x1800e1afd  lea     rax, WPP_GLOBAL_Control
0x1800e1b04  cmp     rsi, rax
0x1800e1b07  jz      short loc_1800E1B4D
0x1800e1b09  cmp     byte ptr [rsi+19h], 4
0x1800e1b0d  jb      short loc_1800E1B4D
0x1800e1b0f  test    byte ptr [rsi+1Ch], 10h
0x1800e1b13  jz      short loc_1800E1B4D
0x1800e1b15  mov     rdi, [rcx+168h]
0x1800e1b1c  mov     rsi, [rsi+10h]
0x1800e1b20  call    IkeGetTlsPeerAddr
0x1800e1b25  mov     rbx, rax
0x1800e1b28  call    IkeGetTlsMmLuid
0x1800e1b2d  mov     r9, rax
0x1800e1b30  mov     [rsp+100h+var_D8], rdi
0x1800e1b35  lea     edx, [r15+0Ch]
0x1800e1b39  mov     [rsp+100h+var_E0], rbx
0x1800e1b3e  lea     r8, WPP_639729265dbb3b0803814a57dbffdef8_Traceguids
0x1800e1b45  mov     rcx, rsi
0x1800e1b48  call    WPP_SF_iSI
0x1800e1b4d  mov     eax, cs:dword_180173278
0x1800e1b53  cmp     eax, 4
0x1800e1b56  jbe     loc_1800E1BDF
0x1800e1b5c  call    IkeGetTlsMmLuid
0x1800e1b61  mov     [rbp+57h+var_B8], rax
0x1800e1b65  lea     rax, [rbp+57h+var_B8]
0x1800e1b69  mov     [rbp+57h+var_80], rax
0x1800e1b6d  mov     [rbp+57h+var_78], 8
0x1800e1b75  call    IkeGetTlsPeerAddr
0x1800e1b7a  mov     rdx, rax
0x1800e1b7d  lea     rcx, [rbp+57h+var_70]
0x1800e1b81  call    _tlgCreate1Sz_wchar_t
0x1800e1b86  mov     rax, [r14+3F0h]
0x1800e1b8d  lea     r9, aHandingOffInpl; "Handing off inplace rekey acquire"
0x1800e1b94  mov     [rbp+57h+var_60], r9
0x1800e1b98  lea     rcx, dword_180173278
0x1800e1b9f  mov     [rbp+57h+var_58], 22h ; '"'
0x1800e1ba7  mov     rdx, [rax+168h]
0x1800e1bae  lea     rax, [rbp+57h+var_C0]
0x1800e1bb2  mov     [rbp+57h+var_50], rax
0x1800e1bb6  lea     rax, [rbp+57h+var_A0]
0x1800e1bba  mov     [rbp+57h+var_C0], rdx
0x1800e1bbe  lea     rdx, byte_180161441
0x1800e1bc5  mov     [rsp+100h+var_D8], rax
0x1800e1bca  mov     dword ptr [rsp+100h+var_E0], 6
0x1800e1bd2  mov     [rbp+57h+var_48], 8
0x1800e1bda  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800e1bdf  lea     rcx, [r14+30h]; lpCriticalSection
0x1800e1be3  call    cs:__imp_EnterCriticalSection
0x1800e1be9  lea     rcx, [r14+70h]
0x1800e1bed  mov     rdx, [rcx+8]
0x1800e1bf1  cmp     [rdx], rcx
0x1800e1bf4  jz      short loc_1800E1BFD
0x1800e1bf6  mov     ecx, 3
0x1800e1bfb  int     29h; Win8: RtlFailFast(ecx)
0x1800e1bfd  mov     rax, [r14+3F0h]
0x1800e1c04  mov     [rax], rcx
0x1800e1c07  mov     [rax+8], rdx
0x1800e1c0b  mov     [rdx], rax
0x1800e1c0e  mov     [rcx+8], rax
0x1800e1c12  lea     rcx, [r14+30h]; lpCriticalSection
0x1800e1c16  call    cs:__imp_LeaveCriticalSection
0x1800e1c1c  jmp     short loc_1800E1C23
0x1800e1c1e  call    IkeFreeAcquireContext
0x1800e1c23  mov     qword ptr [r14+3F0h], 0
0x1800e1c2e  mov     rcx, [r13+450h]
0x1800e1c35  bts     dword ptr [r13+250h], 0Fh
0x1800e1c3e  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1800e1c42  cmp     qword ptr [rcx], 0
0x1800e1c46  jz      short loc_1800E1C4D
0x1800e1c48  call    IkeDestroyTimerContext
0x1800e1c4d  xor     edx, edx
0x1800e1c4f  lea     rcx, aIkeinplacereke; "IkeInplaceRekeyCompleteIkeV2"
0x1800e1c56  call    TraceLogHelper
0x1800e1c5b  lea     rdx, aIkeinplacereke; "IkeInplaceRekeyCompleteIkeV2"
0x1800e1c62  mov     rcx, r15
0x1800e1c65  call    IkeReturnError
0x1800e1c6a  mov     rcx, [rbp+57h+var_30]
0x1800e1c6e  xor     rcx, rsp; StackCookie
0x1800e1c71  call    __security_check_cookie
0x1800e1c76  lea     r11, [rsp+100h+var_20]
0x1800e1c7e  mov     rbx, [r11+40h]
0x1800e1c82  mov     rsi, [r11+48h]
0x1800e1c86  mov     rsp, r11
0x1800e1c89  pop     r15
0x1800e1c8b  pop     r14
0x1800e1c8d  pop     r13
0x1800e1c8f  pop     rdi
0x1800e1c90  pop     rbp
0x1800e1c91  retn
```
