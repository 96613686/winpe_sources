# EapGetEaphostAuthStatusData

- ea: `0x1800129b0`
- end: `0x180012cab`
- name: `EapGetEaphostAuthStatusData`
- size: `763`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180012478`
- `0x18002578c`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x1800129b0`
- `0x18001d108`
- `0x1800214f0`
- `0x180025740`

## import_xrefs

- `eappprxy!EapHostPeerGetAuthStatus` at `0x180012acc`
- `eappprxy!EapHostPeerGetAuthStatus` at `0x180012acc`
- `eappprxy!EapHostPeerFreeEapError` at `0x180012c0b`
- `eappprxy!EapHostPeerFreeEapError` at `0x180012c0b`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180012b7d`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180012b7d`
- `MobileNetworking!FreeMemory` at `0x180012c67`
- `MobileNetworking!FreeMemory` at `0x180012c67`

## pseudocode

```c
__int64 __fastcall EapGetEaphostAuthStatusData(EAP_SESSIONID *a1, int a2, _QWORD *a3, DWORD *a4)
{
  unsigned int v8; // edi
  bool v9; // zf
  DWORD AuthStatus; // ebx
  _QWORD *v11; // rcx
  EapHostPeerAuthParams v12; // ebx
  EAP_ERROR *v13; // rsi
  EAP_ERROR *pEapError; // [rsp+30h] [rbp-10h] BYREF
  DWORD pcbAuthData; // [rsp+80h] [rbp+40h] BYREF
  __int64 v17; // [rsp+90h] [rbp+50h] BYREF
  BYTE *ppAuthData; // [rsp+98h] [rbp+58h] BYREF

  v8 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  pEapError = 0;
  ppAuthData = 0;
  v17 = 0;
  pcbAuthData = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 218, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  *a3 = 0;
  v9 = a1[3] == 0;
  *a4 = 0;
  if ( v9 )
  {
    AuthStatus = 5023;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 219, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v8);
LABEL_27:
      v11 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v12 = EapHostPeerIdentityExtendedInfo;
    if ( a2 != 1 )
      v12 = EapHostPeerIdentity;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 220, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v8);
    AuthStatus = EapHostPeerGetAuthStatus(a1[2], v12, &pcbAuthData, &ppAuthData, &pEapError);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 221, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v8);
      v11 = WPP_GLOBAL_Control;
    }
    if ( AuthStatus )
    {
      if ( (Microsoft_Windows_OneXEnableBits & 4) != 0 )
      {
        McTemplateU0qqq_EtwEventWriteTransfer((_DWORD)v11, (unsigned int)GetPeerAuthStatusFailed, AuthStatus, 2183, v8);
        v11 = WPP_GLOBAL_Control;
      }
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 1) != 0 )
      {
        WPP_SF_dD(v11[7], 222, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v8, AuthStatus);
        goto LABEL_27;
      }
    }
    else
    {
      AuthStatus = AllocateAndCopyPointerData(&v17, ppAuthData, pcbAuthData);
      if ( !AuthStatus )
      {
        *a3 = v17;
        *a4 = pcbAuthData;
        goto LABEL_27;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          223,
          WPP_7a334571dc123d156aa3af8aa642e608_Traceguids,
          v8,
          AuthStatus);
        goto LABEL_27;
      }
    }
  }
  v13 = pEapError;
  if ( pEapError )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 0x10) != 0 )
      WPP_SF_d(v11[7], 11, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v8);
    EapHostPeerFreeEapError(v13);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v8);
      v11 = WPP_GLOBAL_Control;
    }
  }
  if ( AuthStatus )
  {
    FreeMemory(&v17, "EapGetEaphostAuthStatusData", 2202);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
    WPP_SF_D(v11[7], 224, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, AuthStatus);
  return AuthStatus;
}

```

## disassembly

```asm
0x1800129b0  push    rbp
0x1800129b2  push    rbx
0x1800129b3  push    rsi
0x1800129b4  push    rdi
0x1800129b5  push    r12
0x1800129b7  push    r14
0x1800129b9  push    r15
0x1800129bb  mov     rbp, rsp
0x1800129be  sub     rsp, 40h
0x1800129c2  mov     rax, [rcx]
0x1800129c5  mov     r15, r9
0x1800129c8  mov     r12, r8
0x1800129cb  mov     esi, edx
0x1800129cd  mov     r14, rcx
0x1800129d0  mov     edi, [rax+14h]
0x1800129d3  mov     [rbp+pEapError], 0
0x1800129db  mov     [rbp+ppAuthData], 0
0x1800129e3  mov     [rbp+arg_10], 0
0x1800129eb  mov     [rbp+pcbAuthData], 0
0x1800129f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129f9  lea     rax, WPP_GLOBAL_Control
0x180012a00  cmp     rcx, rax
0x180012a03  jz      short loc_180012A2A
0x180012a05  test    dword ptr [rcx+44h], 800h
0x180012a0c  jz      short loc_180012A2A
0x180012a0e  mov     rcx, [rcx+38h]
0x180012a12  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180012a19  mov     edx, 0DAh
0x180012a1e  call    WPP_SF_
0x180012a23  lea     rax, WPP_GLOBAL_Control
0x180012a2a  mov     qword ptr [r12], 0
0x180012a32  cmp     dword ptr [r14+0Ch], 0
0x180012a37  mov     dword ptr [r15], 0
0x180012a3e  jnz     short loc_180012A7C
0x180012a40  mov     ebx, 139Fh
0x180012a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a4c  cmp     rcx, rax
0x180012a4f  jz      loc_180012BDC
0x180012a55  test    byte ptr [rcx+44h], 1
0x180012a59  jz      loc_180012BDC
0x180012a5f  mov     rcx, [rcx+38h]
0x180012a63  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180012a6a  mov     edx, 0DBh
0x180012a6f  mov     r9d, edi
0x180012a72  call    WPP_SF_d
0x180012a77  jmp     loc_180012BCE
0x180012a7c  mov     ebx, 3
0x180012a81  cmp     esi, 1
0x180012a84  jz      short loc_180012A8B
0x180012a86  mov     ebx, 2
0x180012a8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a92  cmp     rcx, rax
0x180012a95  jz      short loc_180012AB5
0x180012a97  test    byte ptr [rcx+44h], 10h
0x180012a9b  jz      short loc_180012AB5
0x180012a9d  mov     rcx, [rcx+38h]
0x180012aa1  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180012aa8  mov     edx, 0DCh
0x180012aad  mov     r9d, edi
0x180012ab0  call    WPP_SF_d
0x180012ab5  mov     ecx, [r14+8]; sessionHandle
0x180012ab9  lea     rax, [rbp+pEapError]
0x180012abd  lea     r9, [rbp+ppAuthData]; ppAuthData
0x180012ac1  mov     [rsp+40h+ppEapError], rax; ppEapError
0x180012ac6  lea     r8, [rbp+pcbAuthData]; pcbAuthData
0x180012aca  mov     edx, ebx; authParam
0x180012acc  call    cs:__imp_EapHostPeerGetAuthStatus
0x180012ad2  mov     ebx, eax
0x180012ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012adb  lea     rsi, WPP_GLOBAL_Control
0x180012ae2  cmp     rcx, rsi
0x180012ae5  jz      short loc_180012B0C
0x180012ae7  test    byte ptr [rcx+44h], 10h
0x180012aeb  jz      short loc_180012B0C
0x180012aed  mov     rcx, [rcx+38h]
0x180012af1  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180012af8  mov     edx, 0DDh
0x180012afd  mov     r9d, edi
0x180012b00  call    WPP_SF_d
0x180012b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b0c  test    ebx, ebx
0x180012b0e  jz      short loc_180012B71
0x180012b10  test    cs:Microsoft_Windows_OneXEnableBits, 4
0x180012b17  jz      short loc_180012B39
0x180012b19  mov     r9d, 887h
0x180012b1f  mov     dword ptr [rsp+40h+ppEapError], edi
0x180012b23  mov     r8d, ebx
0x180012b26  lea     rdx, GetPeerAuthStatusFailed
0x180012b2d  call    McTemplateU0qqq_EtwEventWriteTransfer
0x180012b32  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b39  lea     rax, WPP_GLOBAL_Control
0x180012b40  cmp     rcx, rax
0x180012b43  jz      loc_180012BDC
0x180012b49  test    byte ptr [rcx+44h], 1
0x180012b4d  jz      loc_180012BDC
0x180012b53  mov     rcx, [rcx+38h]
0x180012b57  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180012b5e  mov     edx, 0DEh
0x180012b63  mov     dword ptr [rsp+40h+ppEapError], ebx
0x180012b67  mov     r9d, edi
0x180012b6a  call    WPP_SF_dD
0x180012b6f  jmp     short loc_180012BCE
0x180012b71  mov     r8d, [rbp+pcbAuthData]
0x180012b75  lea     rcx, [rbp+arg_10]
0x180012b79  mov     rdx, [rbp+ppAuthData]
0x180012b7d  call    cs:__imp_AllocateAndCopyPointerData
0x180012b83  mov     ebx, eax
0x180012b85  test    eax, eax
0x180012b87  jz      short loc_180012BC0
0x180012b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b90  lea     rax, WPP_GLOBAL_Control
0x180012b97  cmp     rcx, rax
0x180012b9a  jz      short loc_180012BDC
0x180012b9c  test    byte ptr [rcx+44h], 1
0x180012ba0  jz      short loc_180012BDC
0x180012ba2  mov     rcx, [rcx+38h]
0x180012ba6  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180012bad  mov     edx, 0DFh
0x180012bb2  mov     dword ptr [rsp+40h+ppEapError], ebx
0x180012bb6  mov     r9d, edi
0x180012bb9  call    WPP_SF_dd
0x180012bbe  jmp     short loc_180012BCE
0x180012bc0  mov     rax, [rbp+arg_10]
0x180012bc4  mov     [r12], rax
0x180012bc8  mov     eax, [rbp+pcbAuthData]
0x180012bcb  mov     [r15], eax
0x180012bce  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bd5  lea     rax, WPP_GLOBAL_Control
0x180012bdc  mov     rsi, [rbp+pEapError]
0x180012be0  test    rsi, rsi
0x180012be3  jz      short loc_180012C4B
0x180012be5  cmp     rcx, rax
0x180012be8  jz      short loc_180012C08
0x180012bea  test    byte ptr [rcx+44h], 10h
0x180012bee  jz      short loc_180012C08
0x180012bf0  mov     rcx, [rcx+38h]
0x180012bf4  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180012bfb  mov     edx, 0Bh
0x180012c00  mov     r9d, edi
0x180012c03  call    WPP_SF_d
0x180012c08  mov     rcx, rsi; pEapError
0x180012c0b  call    cs:__imp_EapHostPeerFreeEapError
0x180012c11  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c18  lea     rsi, WPP_GLOBAL_Control
0x180012c1f  cmp     rcx, rsi
0x180012c22  jz      short loc_180012C52
0x180012c24  test    byte ptr [rcx+44h], 10h
0x180012c28  jz      short loc_180012C52
0x180012c2a  mov     rcx, [rcx+38h]
0x180012c2e  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180012c35  mov     edx, 0Ch
0x180012c3a  mov     r9d, edi
0x180012c3d  call    WPP_SF_d
0x180012c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c49  jmp     short loc_180012C52
0x180012c4b  lea     rsi, WPP_GLOBAL_Control
0x180012c52  test    ebx, ebx
0x180012c54  jz      short loc_180012C74
0x180012c56  mov     r8d, 89Ah
0x180012c5c  lea     rdx, aEapgeteaphosta; "EapGetEaphostAuthStatusData"
0x180012c63  lea     rcx, [rbp+arg_10]
0x180012c67  call    cs:__imp_FreeMemory
0x180012c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c74  cmp     rcx, rsi
0x180012c77  jz      short loc_180012C9A
0x180012c79  test    dword ptr [rcx+44h], 800h
0x180012c80  jz      short loc_180012C9A
0x180012c82  mov     rcx, [rcx+38h]
0x180012c86  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180012c8d  mov     edx, 0E0h
0x180012c92  mov     r9d, ebx
0x180012c95  call    WPP_SF_D
0x180012c9a  mov     eax, ebx
0x180012c9c  add     rsp, 40h
0x180012ca0  pop     r15
0x180012ca2  pop     r14
0x180012ca4  pop     r12
0x180012ca6  pop     rdi
0x180012ca7  pop     rsi
0x180012ca8  pop     rbx
0x180012ca9  pop     rbp
0x180012caa  retn
```
