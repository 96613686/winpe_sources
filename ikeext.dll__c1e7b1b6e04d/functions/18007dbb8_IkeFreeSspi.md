# IkeFreeSspi

- ea: `0x18007dbb8`
- end: `0x18007dddb`
- name: `IkeFreeSspi`
- size: `547`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800687ac`
- `0x180068e48`
- `0x18007e5ec`
- `0x18007f2e8`
- `0x1800e7294`
- `0x1800fa24c`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x180025d88`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18007db08`
- `0x18007dbb8`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x18007dd63`
- `CRYPT32!CertFreeCertificateContext` at `0x18007dd90`
- `CRYPT32!CertFreeCertificateContext` at `0x18007dd63`
- `CRYPT32!CertFreeCertificateContext` at `0x18007dd90`
- `SspiCli!DeleteSecurityContext` at `0x18007dcb1`
- `SspiCli!DeleteSecurityContext` at `0x18007dcb1`

## pseudocode

```c
__int64 __fastcall IkeFreeSspi(__int64 a1)
{
  __int64 v2; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v4; // rcx
  int TlsMmLuid; // eax
  __int64 v6; // rcx
  const WCHAR *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  const CERT_CONTEXT *v13; // rcx
  const CERT_CONTEXT *v14; // rcx
  __int64 v16; // [rsp+30h] [rbp-39h] BYREF
  __int64 v17; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-29h] BYREF
  __int64 *v19; // [rsp+60h] [rbp-9h]
  __int64 v20; // [rsp+68h] [rbp-1h]
  _BYTE v21[16]; // [rsp+70h] [rbp+7h] BYREF
  const char *v22; // [rsp+80h] [rbp+17h]
  __int64 v23; // [rsp+88h] [rbp+1Fh]

  v16 = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v2 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(a1);
    TlsMmLuid = IkeGetTlsMmLuid(v4);
    WPP_SF_iSq(v2, 56, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr, a1);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v17 = IkeGetTlsMmLuid(a1);
    v19 = &v17;
    v20 = 8;
    v7 = (const WCHAR *)IkeGetTlsPeerAddr(v6);
    tlgCreate1Sz_wchar_t((__int64)v21, v7);
    v23 = 14;
    v22 = "WFP free sspi";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_180173278,
      (unsigned __int8 *)&dword_180155394,
      v8,
      v9,
      5,
      (__int64)v18);
  }
  if ( *(_QWORD *)(a1 + 24) != -1 && *(_QWORD *)(a1 + 32) != -1 )
  {
    DeleteSecurityContext((PCtxtHandle)(a1 + 24));
    *(_QWORD *)(a1 + 32) = -1;
    *(_QWORD *)(a1 + 24) = -1;
  }
  if ( *(_QWORD *)(a1 + 8) || *(_QWORD *)(a1 + 16) )
    IkeFreeACHCredentialHandle(a1);
  WfpMemFree((LPCVOID *)(a1 + 56));
  WfpMemFree((LPCVOID *)(a1 + 64));
  v10 = a1 + 96;
  v11 = *(_QWORD *)(a1 + 96);
  if ( v11 )
  {
    WfpMemFree((LPCVOID *)(v11 + 8));
    WfpMemFree((LPCVOID *)(*(_QWORD *)v10 + 24LL));
    WfpMemFree((LPCVOID *)(*(_QWORD *)v10 + 40LL));
    WfpMemFree((LPCVOID *)(*(_QWORD *)v10 + 56LL));
    WfpMemFree((LPCVOID *)(a1 + 96));
  }
  v12 = *(_QWORD *)(a1 + 104);
  if ( v12 )
  {
    if ( *(_QWORD *)(v12 + 8) )
    {
      WfpMemFree((LPCVOID *)(v12 + 8));
      *(_OWORD *)*(_QWORD *)(a1 + 104) = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL) = 0;
    }
    v13 = *(const CERT_CONTEXT **)(*(_QWORD *)(a1 + 104) + 16LL);
    if ( v13 )
      CertFreeCertificateContext(v13);
    WfpMemFree((LPCVOID *)(*(_QWORD *)(a1 + 104) + 32LL));
    WfpMemFree((LPCVOID *)(*(_QWORD *)(a1 + 104) + 72LL));
    v14 = *(const CERT_CONTEXT **)(*(_QWORD *)(a1 + 104) + 56LL);
    if ( v14 )
      CertFreeCertificateContext(v14);
    WfpMemFree((LPCVOID *)(*(_QWORD *)(a1 + 104) + 48LL));
    WfpMemFree((LPCVOID *)(a1 + 104));
  }
  WfpMemFree((LPCVOID *)&v16);
  return TraceLogHelper("IkeFreeSspi", 0);
}

```

## disassembly

```asm
0x18007dbb8  push    rbp
0x18007dbba  push    rbx
0x18007dbbb  push    rsi
0x18007dbbc  push    rdi
0x18007dbbd  lea     rbp, [rsp-3Fh]
0x18007dbc2  sub     rsp, 0A8h
0x18007dbc9  mov     rax, cs:__security_cookie
0x18007dbd0  xor     rax, rsp
0x18007dbd3  mov     [rbp+57h+var_30], rax
0x18007dbd7  mov     rsi, rcx
0x18007dbda  mov     [rbp+57h+var_90], rcx
0x18007dbde  mov     rdi, cs:WPP_GLOBAL_Control
0x18007dbe5  lea     rax, WPP_GLOBAL_Control
0x18007dbec  cmp     rdi, rax
0x18007dbef  jz      short loc_18007DC2F
0x18007dbf1  cmp     byte ptr [rdi+19h], 4
0x18007dbf5  jb      short loc_18007DC2F
0x18007dbf7  test    byte ptr [rdi+1Ch], 10h
0x18007dbfb  jz      short loc_18007DC2F
0x18007dbfd  mov     rdi, [rdi+10h]
0x18007dc01  call    IkeGetTlsPeerAddr
0x18007dc06  mov     rbx, rax
0x18007dc09  call    IkeGetTlsMmLuid
0x18007dc0e  mov     r9, rax
0x18007dc11  mov     [rsp+0C0h+var_98], rsi
0x18007dc16  mov     edx, 38h ; '8'
0x18007dc1b  mov     [rsp+0C0h+var_A0], rbx
0x18007dc20  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18007dc27  mov     rcx, rdi
0x18007dc2a  call    WPP_SF_iSq
0x18007dc2f  mov     eax, cs:dword_180173278
0x18007dc35  xor     edi, edi
0x18007dc37  cmp     eax, 4
0x18007dc3a  jbe     short loc_18007DC9D
0x18007dc3c  call    IkeGetTlsMmLuid
0x18007dc41  mov     [rbp+57h+var_88], rax
0x18007dc45  lea     rax, [rbp+57h+var_88]
0x18007dc49  mov     [rbp+57h+var_60], rax
0x18007dc4d  mov     [rbp+57h+var_58], 8
0x18007dc55  call    IkeGetTlsPeerAddr
0x18007dc5a  mov     rdx, rax
0x18007dc5d  lea     rcx, [rbp+57h+var_50]
0x18007dc61  call    _tlgCreate1Sz_wchar_t
0x18007dc66  lea     rcx, aWfpFreeSspi; "WFP free sspi"
0x18007dc6d  mov     [rbp+57h+var_38], 0Eh
0x18007dc75  lea     rax, [rbp+57h+var_80]
0x18007dc79  mov     [rbp+57h+var_40], rcx
0x18007dc7d  mov     [rsp+0C0h+var_98], rax
0x18007dc82  lea     rcx, dword_180173278
0x18007dc89  lea     rdx, dword_180155394
0x18007dc90  mov     dword ptr [rsp+0C0h+var_A0], 5
0x18007dc98  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007dc9d  lea     rbx, [rsi+18h]
0x18007dca1  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18007dca5  jz      short loc_18007DCC6
0x18007dca7  cmp     qword ptr [rsi+20h], 0FFFFFFFFFFFFFFFFh
0x18007dcac  jz      short loc_18007DCC6
0x18007dcae  mov     rcx, rbx; phContext
0x18007dcb1  call    cs:__imp_DeleteSecurityContext
0x18007dcb7  mov     qword ptr [rsi+20h], 0FFFFFFFFFFFFFFFFh
0x18007dcbf  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18007dcc6  cmp     [rsi+8], rdi
0x18007dcca  jnz     short loc_18007DCD2
0x18007dccc  cmp     [rsi+10h], rdi
0x18007dcd0  jz      short loc_18007DCDA
0x18007dcd2  mov     rcx, rsi
0x18007dcd5  call    IkeFreeACHCredentialHandle
0x18007dcda  lea     rcx, [rsi+38h]
0x18007dcde  call    WfpMemFree
0x18007dce3  lea     rcx, [rsi+40h]
0x18007dce7  call    WfpMemFree
0x18007dcec  lea     rbx, [rsi+60h]
0x18007dcf0  mov     rcx, [rbx]
0x18007dcf3  test    rcx, rcx
0x18007dcf6  jz      short loc_18007DD2D
0x18007dcf8  add     rcx, 8
0x18007dcfc  call    WfpMemFree
0x18007dd01  mov     rcx, [rbx]
0x18007dd04  add     rcx, 18h
0x18007dd08  call    WfpMemFree
0x18007dd0d  mov     rcx, [rbx]
0x18007dd10  add     rcx, 28h ; '('
0x18007dd14  call    WfpMemFree
0x18007dd19  mov     rcx, [rbx]
0x18007dd1c  add     rcx, 38h ; '8'
0x18007dd20  call    WfpMemFree
0x18007dd25  mov     rcx, rbx
0x18007dd28  call    WfpMemFree
0x18007dd2d  mov     rax, [rsi+68h]
0x18007dd31  test    rax, rax
0x18007dd34  jz      short loc_18007DDAC
0x18007dd36  lea     rcx, [rax+8]
0x18007dd3a  cmp     [rcx], rdi
0x18007dd3d  jz      short loc_18007DD56
0x18007dd3f  call    WfpMemFree
0x18007dd44  mov     rax, [rsi+68h]
0x18007dd48  xorps   xmm0, xmm0
0x18007dd4b  movups  xmmword ptr [rax], xmm0
0x18007dd4e  mov     rax, [rsi+68h]
0x18007dd52  mov     [rax+8], rdi
0x18007dd56  mov     rax, [rsi+68h]
0x18007dd5a  mov     rcx, [rax+10h]; pCertContext
0x18007dd5e  test    rcx, rcx
0x18007dd61  jz      short loc_18007DD69
0x18007dd63  call    cs:__imp_CertFreeCertificateContext
0x18007dd69  mov     rcx, [rsi+68h]
0x18007dd6d  add     rcx, 20h ; ' '
0x18007dd71  call    WfpMemFree
0x18007dd76  mov     rcx, [rsi+68h]
0x18007dd7a  add     rcx, 48h ; 'H'
0x18007dd7e  call    WfpMemFree
0x18007dd83  mov     rax, [rsi+68h]
0x18007dd87  mov     rcx, [rax+38h]; pCertContext
0x18007dd8b  test    rcx, rcx
0x18007dd8e  jz      short loc_18007DD96
0x18007dd90  call    cs:__imp_CertFreeCertificateContext
0x18007dd96  mov     rcx, [rsi+68h]
0x18007dd9a  add     rcx, 30h ; '0'
0x18007dd9e  call    WfpMemFree
0x18007dda3  lea     rcx, [rsi+68h]
0x18007dda7  call    WfpMemFree
0x18007ddac  lea     rcx, [rbp+57h+var_90]
0x18007ddb0  call    WfpMemFree
0x18007ddb5  xor     edx, edx
0x18007ddb7  lea     rcx, aIkefreesspi; "IkeFreeSspi"
0x18007ddbe  call    TraceLogHelper
0x18007ddc3  mov     rcx, [rbp+57h+var_30]
0x18007ddc7  xor     rcx, rsp; StackCookie
0x18007ddca  call    __security_check_cookie
0x18007ddcf  add     rsp, 0A8h
0x18007ddd6  pop     rdi
0x18007ddd7  pop     rsi
0x18007ddd8  pop     rbx
0x18007ddd9  pop     rbp
0x18007ddda  retn
```
