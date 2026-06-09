# EapEndSession

- ea: `0x180008d40`
- end: `0x180009057`
- name: `EapEndSession`
- size: `791`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800084a0`
- `0x180008bd0`
- `0x180009540`
- `0x18000a100`
- `0x18001ba00`
- `0x180024860`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180008d40`
- `0x180010ae0`
- `0x180018520`
- `0x18001d108`
- `0x1800214f0`
- `0x180025740`
- `0x180027d10`
- `0x180027ee4`

## import_xrefs

- `eappprxy!EapHostPeerEndSession` at `0x180008e8a`
- `eappprxy!EapHostPeerEndSession` at `0x180008e8a`
- `eappprxy!EapHostPeerGetDataToUnplumbCredentials` at `0x180008e50`
- `eappprxy!EapHostPeerGetDataToUnplumbCredentials` at `0x180008e50`
- `eappprxy!EapHostPeerFreeEapError` at `0x180008fee`
- `eappprxy!EapHostPeerFreeEapError` at `0x180008fee`
- `MobileNetworking!ReleaseWriteLock` at `0x180008e7c`
- `MobileNetworking!ReleaseWriteLock` at `0x180008e7c`
- `MobileNetworking!AcquireWriteLock` at `0x180008e27`
- `MobileNetworking!AcquireWriteLock` at `0x180008e27`

## pseudocode

```c
__int64 __fastcall EapEndSession(EAP_SESSIONID *a1)
{
  unsigned int v2; // edi
  _BYTE *v3; // r10
  unsigned __int8 *EapType; // rax
  __int64 v5; // r10
  int v6; // edx
  int v7; // ecx
  DWORD v8; // esi
  int v9; // r8d
  _QWORD *v10; // r10
  EAP_ERROR *v11; // r14
  EAP_ERROR *v12; // rbx
  _BYTE v14[40]; // [rsp+40h] [rbp-28h] BYREF
  EAP_ERROR *ppEapError; // [rsp+70h] [rbp+8h] BYREF

  v2 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  ppEapError = 0;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 130, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
    if ( v3 != (_BYTE *)&WPP_GLOBAL_Control && (v3[68] & 0x10) != 0 )
    {
      EapType = (unsigned __int8 *)EapGetEapType(v14, a1);
      WPP_SF_dd(*(_QWORD *)(v5 + 56), 131, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v2, *EapType);
      v3 = WPP_GLOBAL_Control;
    }
  }
  if ( a1[3] )
  {
    if ( v3 != (_BYTE *)&WPP_GLOBAL_Control && (v3[68] & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)v3 + 7), 132, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v2);
    AcquireWriteLock(g_OneXSsoInfo, g_OneXSsoInfo, "EapEndSession", 1317);
    EapHostPeerGetDataToUnplumbCredentials(
      &pConnectionIdThatLastSavedCreds,
      (__int64 *)&hObject,
      a1[2],
      &ppEapError,
      &fSaveToCredMan);
    hObject = (HANDLE)-1LL;
    ReleaseWriteLock(g_OneXSsoInfo, g_OneXSsoInfo, "EapEndSession", 1326);
    v8 = EapHostPeerEndSession(a1[2], &ppEapError);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 133, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v2);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v8 )
    {
      v11 = ppEapError;
      if ( ppEapError )
      {
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 68) & 0x10) != 0 )
        {
          WPP_SF_dDDdS(
            v10[7],
            v6,
            v9,
            v2,
            ppEapError->dwWinError,
            ppEapError->dwReasonCode,
            ppEapError->type.eapType.type,
            (__int64)ppEapError->pRootCauseString);
          v10 = WPP_GLOBAL_Control;
        }
        if ( (Microsoft_Windows_OneXEnableBits & 4) != 0 )
        {
          McTemplateU0qqquz_EtwEventWriteTransfer(
            v7,
            v6,
            v2,
            v11->dwWinError,
            v11->dwReasonCode,
            v11->type.eapType.type,
            (__int64)v11->pRootCauseString);
          v10 = WPP_GLOBAL_Control;
        }
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 68) & 1) != 0 )
        WPP_SF_dD(v10[7], 134, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v2, v8);
      if ( (Microsoft_Windows_OneXEnableBits & 4) != 0 )
        McTemplateU0qqq_EtwEventWriteTransfer(v7, (unsigned int)EAPHostPeerEndSessionFailed, v8, 1337, v2);
    }
    a1[3] = 0;
    v3 = WPP_GLOBAL_Control;
  }
  v12 = ppEapError;
  if ( !ppEapError )
    goto LABEL_34;
  if ( v3 != (_BYTE *)&WPP_GLOBAL_Control && (v3[68] & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)v3 + 7), 11, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v2);
  EapHostPeerFreeEapError(v12);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v2);
      v3 = WPP_GLOBAL_Control;
    }
LABEL_34:
    if ( v3 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v3 + 17) & 0x800) != 0 )
      WPP_SF_D(*((_QWORD *)v3 + 7), 135, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180008d40  push    rbx
0x180008d42  push    rbp
0x180008d43  push    rdi
0x180008d44  sub     rsp, 50h
0x180008d48  mov     rax, [rcx]
0x180008d4b  mov     rbx, rcx
0x180008d4e  mov     [rsp+68h+arg_18], r15
0x180008d56  xor     r15d, r15d
0x180008d59  mov     edi, [rax+14h]
0x180008d5c  mov     [rsp+68h+ppEapError], r15
0x180008d61  mov     r10, cs:WPP_GLOBAL_Control
0x180008d68  lea     rbp, WPP_GLOBAL_Control
0x180008d6f  cmp     r10, rbp
0x180008d72  jz      short loc_180008DD9
0x180008d74  test    dword ptr [r10+44h], 800h
0x180008d7c  jz      short loc_180008D9A
0x180008d7e  mov     rcx, [r10+38h]
0x180008d82  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180008d89  mov     edx, 82h
0x180008d8e  call    WPP_SF_
0x180008d93  mov     r10, cs:WPP_GLOBAL_Control
0x180008d9a  cmp     r10, rbp
0x180008d9d  jz      short loc_180008DD9
0x180008d9f  test    byte ptr [r10+44h], 10h
0x180008da4  jz      short loc_180008DD9
0x180008da6  mov     rdx, rbx
0x180008da9  lea     rcx, [rsp+68h+var_28]
0x180008dae  call    EapGetEapType
0x180008db3  mov     edx, 83h
0x180008db8  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180008dbf  mov     r9d, edi
0x180008dc2  movzx   ecx, byte ptr [rax]
0x180008dc5  mov     dword ptr [rsp+68h+fSaveToCredMan], ecx
0x180008dc9  mov     rcx, [r10+38h]
0x180008dcd  call    WPP_SF_dd
0x180008dd2  mov     r10, cs:WPP_GLOBAL_Control
0x180008dd9  cmp     [rbx+0Ch], r15d
0x180008ddd  jz      loc_180008FB5
0x180008de3  mov     [rsp+68h+arg_8], rsi
0x180008de8  cmp     r10, rbp
0x180008deb  jz      short loc_180008E0C
0x180008ded  test    byte ptr [r10+44h], 10h
0x180008df2  jz      short loc_180008E0C
0x180008df4  mov     rcx, [r10+38h]
0x180008df8  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180008dff  mov     edx, 84h
0x180008e04  mov     r9d, edi
0x180008e07  call    WPP_SF_d
0x180008e0c  mov     r9d, 525h
0x180008e12  lea     r8, aEapendsession; "EapEndSession"
0x180008e19  lea     rdx, g_OneXSsoInfo
0x180008e20  lea     rcx, g_OneXSsoInfo
0x180008e27  call    cs:__imp_AcquireWriteLock
0x180008e2d  mov     r8d, [rbx+8]; sessionHandle
0x180008e31  lea     rax, fSaveToCredMan
0x180008e38  lea     r9, [rsp+68h+ppEapError]; ppEapError
0x180008e3d  mov     [rsp+68h+fSaveToCredMan], rax; fSaveToCredMan
0x180008e42  lea     rdx, hObject; phCredentialImpersonationToken
0x180008e49  lea     rcx, pConnectionIdThatLastSavedCreds; pConnectionIdThatLastSavedCreds
0x180008e50  call    cs:__imp_EapHostPeerGetDataToUnplumbCredentials
0x180008e56  mov     r9d, 52Eh
0x180008e5c  mov     cs:hObject, 0FFFFFFFFFFFFFFFFh
0x180008e67  lea     r8, aEapendsession; "EapEndSession"
0x180008e6e  lea     rdx, g_OneXSsoInfo
0x180008e75  lea     rcx, g_OneXSsoInfo
0x180008e7c  call    cs:__imp_ReleaseWriteLock
0x180008e82  mov     ecx, [rbx+8]; sessionHandle
0x180008e85  lea     rdx, [rsp+68h+ppEapError]; ppEapError
0x180008e8a  call    cs:__imp_EapHostPeerEndSession
0x180008e90  mov     esi, eax
0x180008e92  mov     r10, cs:WPP_GLOBAL_Control
0x180008e99  cmp     r10, rbp
0x180008e9c  jz      short loc_180008EC4
0x180008e9e  test    byte ptr [r10+44h], 10h
0x180008ea3  jz      short loc_180008EC4
0x180008ea5  mov     rcx, [r10+38h]
0x180008ea9  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180008eb0  mov     edx, 85h
0x180008eb5  mov     r9d, edi
0x180008eb8  call    WPP_SF_d
0x180008ebd  mov     r10, cs:WPP_GLOBAL_Control
0x180008ec4  test    esi, esi
0x180008ec6  jz      loc_180008FA5
0x180008ecc  mov     [rsp+68h+arg_10], r14
0x180008ed4  mov     r14, [rsp+68h+ppEapError]
0x180008ed9  test    r14, r14
0x180008edc  jz      short loc_180008F53
0x180008ede  cmp     r10, rbp
0x180008ee1  jz      short loc_180008F1E
0x180008ee3  test    byte ptr [r10+44h], 10h
0x180008ee8  jz      short loc_180008F1E
0x180008eea  mov     rax, [r14+48h]
0x180008eee  mov     r9d, edi
0x180008ef1  movzx   ecx, byte ptr [r14+4]
0x180008ef6  mov     [rsp+68h+var_30], rax
0x180008efb  mov     eax, [r14+14h]
0x180008eff  mov     dword ptr [rsp+68h+var_38], ecx
0x180008f03  mov     rcx, [r10+38h]
0x180008f07  mov     [rsp+68h+var_40], eax
0x180008f0b  mov     eax, [r14]
0x180008f0e  mov     dword ptr [rsp+68h+fSaveToCredMan], eax
0x180008f12  call    WPP_SF_dDDdS
0x180008f17  mov     r10, cs:WPP_GLOBAL_Control
0x180008f1e  test    cs:Microsoft_Windows_OneXEnableBits, 4
0x180008f25  jz      short loc_180008F53
0x180008f27  mov     rax, [r14+48h]
0x180008f2b  mov     r8d, edi
0x180008f2e  mov     r9d, [r14]
0x180008f31  mov     [rsp+68h+var_38], rax
0x180008f36  movzx   eax, byte ptr [r14+4]
0x180008f3b  mov     byte ptr [rsp+68h+var_40], al
0x180008f3f  mov     eax, [r14+14h]
0x180008f43  mov     dword ptr [rsp+68h+fSaveToCredMan], eax
0x180008f47  call    McTemplateU0qqquz_EtwEventWriteTransfer
0x180008f4c  mov     r10, cs:WPP_GLOBAL_Control
0x180008f53  mov     r14, [rsp+68h+arg_10]
0x180008f5b  cmp     r10, rbp
0x180008f5e  jz      short loc_180008F83
0x180008f60  test    byte ptr [r10+44h], 1
0x180008f65  jz      short loc_180008F83
0x180008f67  mov     rcx, [r10+38h]
0x180008f6b  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180008f72  mov     edx, 86h
0x180008f77  mov     dword ptr [rsp+68h+fSaveToCredMan], esi
0x180008f7b  mov     r9d, edi
0x180008f7e  call    WPP_SF_dD
0x180008f83  test    cs:Microsoft_Windows_OneXEnableBits, 4
0x180008f8a  jz      short loc_180008FA5
0x180008f8c  mov     r9d, 539h
0x180008f92  mov     dword ptr [rsp+68h+fSaveToCredMan], edi
0x180008f96  mov     r8d, esi
0x180008f99  lea     rdx, EAPHostPeerEndSessionFailed
0x180008fa0  call    McTemplateU0qqq_EtwEventWriteTransfer
0x180008fa5  mov     rsi, [rsp+68h+arg_8]
0x180008faa  mov     [rbx+0Ch], r15d
0x180008fae  mov     r10, cs:WPP_GLOBAL_Control
0x180008fb5  mov     rbx, [rsp+68h+ppEapError]
0x180008fba  mov     r15, [rsp+68h+arg_18]
0x180008fc2  test    rbx, rbx
0x180008fc5  jz      short loc_180009026
0x180008fc7  cmp     r10, rbp
0x180008fca  jz      short loc_180008FEB
0x180008fcc  test    byte ptr [r10+44h], 10h
0x180008fd1  jz      short loc_180008FEB
0x180008fd3  mov     rcx, [r10+38h]
0x180008fd7  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180008fde  mov     edx, 0Bh
0x180008fe3  mov     r9d, edi
0x180008fe6  call    WPP_SF_d
0x180008feb  mov     rcx, rbx; pEapError
0x180008fee  call    cs:__imp_EapHostPeerFreeEapError
0x180008ff4  mov     r10, cs:WPP_GLOBAL_Control
0x180008ffb  cmp     r10, rbp
0x180008ffe  jz      short loc_18000904D
0x180009000  test    byte ptr [r10+44h], 10h
0x180009005  jz      short loc_180009026
0x180009007  mov     rcx, [r10+38h]
0x18000900b  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180009012  mov     edx, 0Ch
0x180009017  mov     r9d, edi
0x18000901a  call    WPP_SF_d
0x18000901f  mov     r10, cs:WPP_GLOBAL_Control
0x180009026  cmp     r10, rbp
0x180009029  jz      short loc_18000904D
0x18000902b  test    dword ptr [r10+44h], 800h
0x180009033  jz      short loc_18000904D
0x180009035  mov     rcx, [r10+38h]
0x180009039  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180009040  mov     edx, 87h
0x180009045  xor     r9d, r9d
0x180009048  call    WPP_SF_D
0x18000904d  xor     eax, eax
0x18000904f  add     rsp, 50h
0x180009053  pop     rdi
0x180009054  pop     rbp
0x180009055  pop     rbx
0x180009056  retn
```
