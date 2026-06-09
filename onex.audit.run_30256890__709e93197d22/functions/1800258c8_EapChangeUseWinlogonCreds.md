# EapChangeUseWinlogonCreds

- ea: `0x1800258c8`
- end: `0x180025bbb`
- name: `EapChangeUseWinlogonCreds`
- size: `755`
- prototype: ``
- caller_count: `7`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x180007fb0`
- `0x180009be0`
- `0x18001d208`
- `0x180027598`
- `0x180029414`
- `0x180029668`
- `0x180029ea8`

## callees

- `0x180005440`
- `0x180007850`
- `0x180007e50`
- `0x180007f60`
- `0x180010ae0`
- `0x180018520`
- `0x180020250`
- `0x1800214f0`
- `0x180025740`
- `0x1800258c8`
- `0x1800277bc`
- `0x18002e118`

## import_xrefs

- `eappcfg!EapHostPeerFreeMemory` at `0x180025b5f`
- `eappcfg!EapHostPeerFreeMemory` at `0x180025b5f`

## pseudocode

```c
__int64 __fastcall EapChangeUseWinlogonCreds(__int64 *a1, int a2, _DWORD *a3)
{
  unsigned int v6; // edi
  _UNKNOWN **v7; // rcx
  BYTE *v8; // r14
  DWORD v9; // ebx
  unsigned int inited; // eax
  unsigned int v11; // ebx
  _UNKNOWN **v12; // rcx
  __int64 v13; // rdx
  unsigned __int16 v14; // dx
  _UNKNOWN **v15; // rcx
  int v16; // eax
  __int64 v18; // [rsp+40h] [rbp-40h] BYREF
  BYTE *pData; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v20[16]; // [rsp+50h] [rbp-30h] BYREF
  EAP_METHOD_TYPE pEapMethodType; // [rsp+60h] [rbp-20h] BYREF

  v6 = *(_DWORD *)(*a1 + 20);
  pData = 0;
  v18 = 0;
  pEapMethodType = *(EAP_METHOD_TYPE *)EapGetEapType(v20, a1);
  v7 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x149u, (__int64)WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
    v7 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  v8 = (BYTE *)a1[11];
  v9 = *((_DWORD *)a1 + 20);
  if ( !v8 && !v9 )
  {
    inited = EapInitWorkingSetConnectionData(a1);
    v11 = inited;
    if ( inited )
    {
      v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v13 = 330;
LABEL_10:
        WPP_SF_dD(v12[7], v13, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6, inited);
LABEL_44:
        v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
        goto LABEL_45;
      }
      goto LABEL_45;
    }
    v9 = *((_DWORD *)a1 + 20);
    v8 = (BYTE *)a1[11];
    v7 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    if ( v7 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v7 + 68) & 0x10) != 0 )
      {
        v14 = 331;
LABEL_19:
        WPP_SF_d((__int64)v7[7], v14, (__int64)WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6);
        v7 = (_UNKNOWN **)WPP_GLOBAL_Control;
        goto LABEL_20;
      }
      goto LABEL_20;
    }
  }
  else if ( v7 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v7 + 68) & 0x10) != 0 )
    {
      v14 = 332;
      goto LABEL_19;
    }
LABEL_20:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 0x10) != 0 )
      WPP_SF_dd((__int64)v7[7], 0x14Du, (__int64)WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6);
  }
  inited = EapXmlChangeUseWinlogonCredsSetting(&pEapMethodType, a2, v9, v8, (DWORD *)&v18, &pData, (int *)&v18 + 1);
  v11 = inited;
  if ( !inited )
  {
    v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x14Fu,
        (__int64)WPP_7a334571dc123d156aa3af8aa642e608_Traceguids,
        v6);
      v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    v16 = HIDWORD(v18);
    if ( HIDWORD(v18) )
    {
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 68) & 0x10) != 0 )
        WPP_SF_d((__int64)v15[7], 0x150u, (__int64)WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6);
      inited = EapSetWorkingSetConnectionData(a1, (unsigned int)v18, pData);
      v11 = inited;
      if ( inited )
      {
        v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v13 = 337;
          goto LABEL_10;
        }
        goto LABEL_45;
      }
      inited = EapUpdateMasterConnectionData(a1, v18, pData);
      v11 = inited;
      if ( inited )
      {
        v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v13 = 338;
          goto LABEL_10;
        }
        goto LABEL_45;
      }
      v16 = HIDWORD(v18);
    }
    *a3 = v16;
    goto LABEL_44;
  }
  v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v13 = 334;
    goto LABEL_10;
  }
LABEL_45:
  if ( pData )
  {
    EapHostPeerFreeMemory(pData);
    v12 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
    WPP_SF_D((__int64)v12[7], 0x153u, (__int64)WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x1800258c8  mov     [rsp-38h+arg_18], rbx
0x1800258cd  push    rbp
0x1800258ce  push    rsi
0x1800258cf  push    rdi
0x1800258d0  push    r12
0x1800258d2  push    r13
0x1800258d4  push    r14
0x1800258d6  push    r15
0x1800258d8  mov     rbp, rsp
0x1800258db  sub     rsp, 80h
0x1800258e2  mov     rax, cs:__security_cookie
0x1800258e9  xor     rax, rsp
0x1800258ec  mov     [rbp+var_10], rax
0x1800258f0  mov     rax, [rcx]
0x1800258f3  mov     r15d, edx
0x1800258f6  mov     rdx, rcx
0x1800258f9  mov     rsi, rcx
0x1800258fc  lea     rcx, [rbp+var_30]
0x180025900  mov     r12, r8
0x180025903  mov     edi, [rax+14h]
0x180025906  xor     eax, eax
0x180025908  mov     [rbp+pData], rax
0x18002590c  mov     dword ptr [rbp+var_40], eax
0x18002590f  mov     dword ptr [rbp+var_40+4], eax
0x180025912  call    EapGetEapType
0x180025917  movups  xmm1, xmmword ptr [rax]
0x18002591a  movdqu  xmmword ptr [rbp+pEapMethodType.eapType.type], xmm1
0x18002591f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025926  lea     r13, WPP_GLOBAL_Control
0x18002592d  cmp     rcx, r13
0x180025930  jz      short loc_180025957
0x180025932  test    dword ptr [rcx+44h], 800h
0x180025939  jz      short loc_180025957
0x18002593b  mov     rcx, [rcx+38h]
0x18002593f  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180025946  mov     edx, 149h
0x18002594b  call    WPP_SF_
0x180025950  mov     rcx, cs:WPP_GLOBAL_Control
0x180025957  mov     r14, [rsi+58h]
0x18002595b  mov     ebx, [rsi+50h]
0x18002595e  test    r14, r14
0x180025961  jnz     short loc_1800259BE
0x180025963  test    ebx, ebx
0x180025965  jnz     short loc_1800259BE
0x180025967  mov     rcx, rsi
0x18002596a  call    EapInitWorkingSetConnectionData
0x18002596f  mov     ebx, eax
0x180025971  test    eax, eax
0x180025973  jz      short loc_1800259B0
0x180025975  mov     rcx, cs:WPP_GLOBAL_Control
0x18002597c  cmp     rcx, r13
0x18002597f  jz      loc_180025B53
0x180025985  test    byte ptr [rcx+44h], 1
0x180025989  jz      loc_180025B53
0x18002598f  mov     edx, 14Ah
0x180025994  mov     rcx, [rcx+38h]
0x180025998  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18002599f  mov     r9d, edi
0x1800259a2  mov     dword ptr [rsp+80h+var_60], eax
0x1800259a6  call    WPP_SF_dD
0x1800259ab  jmp     loc_180025B4C
0x1800259b0  mov     ebx, [rsi+50h]
0x1800259b3  mov     r14, [rsi+58h]
0x1800259b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259be  test    r15d, r15d
0x1800259c1  jz      short loc_1800259D5
0x1800259c3  cmp     rcx, r13
0x1800259c6  jz      short loc_180025A26
0x1800259c8  test    byte ptr [rcx+44h], 10h
0x1800259cc  jz      short loc_1800259FF
0x1800259ce  mov     edx, 14Bh
0x1800259d3  jmp     short loc_1800259E5
0x1800259d5  cmp     rcx, r13
0x1800259d8  jz      short loc_180025A26
0x1800259da  test    byte ptr [rcx+44h], 10h
0x1800259de  jz      short loc_1800259FF
0x1800259e0  mov     edx, 14Ch
0x1800259e5  mov     rcx, [rcx+38h]
0x1800259e9  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x1800259f0  mov     r9d, edi
0x1800259f3  call    WPP_SF_d
0x1800259f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259ff  cmp     rcx, r13
0x180025a02  jz      short loc_180025A26
0x180025a04  test    byte ptr [rcx+44h], 10h
0x180025a08  jz      short loc_180025A26
0x180025a0a  mov     rcx, [rcx+38h]
0x180025a0e  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180025a15  mov     edx, 14Dh
0x180025a1a  mov     dword ptr [rsp+80h+var_60], ebx
0x180025a1e  mov     r9d, edi
0x180025a21  call    WPP_SF_dd
0x180025a26  lea     rax, [rbp+var_40+4]
0x180025a2a  mov     r9, r14
0x180025a2d  mov     [rsp+80h+var_50], rax; __int64
0x180025a32  lea     rcx, [rbp+pEapMethodType]; pEapMethodType
0x180025a36  lea     rax, [rbp+pData]
0x180025a3a  mov     r8d, ebx
0x180025a3d  mov     [rsp+80h+var_58], rax; __int64
0x180025a42  mov     edx, r15d
0x180025a45  lea     rax, [rbp+var_40]
0x180025a49  mov     [rsp+80h+var_60], rax; __int64
0x180025a4e  call    EapXmlChangeUseWinlogonCredsSetting
0x180025a53  mov     ebx, eax
0x180025a55  test    eax, eax
0x180025a57  jz      short loc_180025A7D
0x180025a59  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a60  cmp     rcx, r13
0x180025a63  jz      loc_180025B53
0x180025a69  test    byte ptr [rcx+44h], 1
0x180025a6d  jz      loc_180025B53
0x180025a73  mov     edx, 14Eh
0x180025a78  jmp     loc_180025994
0x180025a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a84  cmp     rcx, r13
0x180025a87  jz      short loc_180025AB5
0x180025a89  test    byte ptr [rcx+44h], 10h
0x180025a8d  jz      short loc_180025AB5
0x180025a8f  mov     eax, dword ptr [rbp+var_40]
0x180025a92  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180025a99  mov     rcx, [rcx+38h]
0x180025a9d  mov     edx, 14Fh
0x180025aa2  mov     r9d, edi
0x180025aa5  mov     dword ptr [rsp+80h+var_60], eax
0x180025aa9  call    WPP_SF_dd
0x180025aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ab5  mov     eax, dword ptr [rbp+var_40+4]
0x180025ab8  test    eax, eax
0x180025aba  jz      loc_180025B48
0x180025ac0  cmp     rcx, r13
0x180025ac3  jz      short loc_180025AE3
0x180025ac5  test    byte ptr [rcx+44h], 10h
0x180025ac9  jz      short loc_180025AE3
0x180025acb  mov     rcx, [rcx+38h]
0x180025acf  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180025ad6  mov     edx, 150h
0x180025adb  mov     r9d, edi
0x180025ade  call    WPP_SF_d
0x180025ae3  mov     r8, [rbp+pData]
0x180025ae7  mov     rcx, rsi
0x180025aea  mov     edx, dword ptr [rbp+var_40]
0x180025aed  call    EapSetWorkingSetConnectionData
0x180025af2  mov     ebx, eax
0x180025af4  test    eax, eax
0x180025af6  jz      short loc_180025B14
0x180025af8  mov     rcx, cs:WPP_GLOBAL_Control
0x180025aff  cmp     rcx, r13
0x180025b02  jz      short loc_180025B53
0x180025b04  test    byte ptr [rcx+44h], 1
0x180025b08  jz      short loc_180025B53
0x180025b0a  mov     edx, 151h
0x180025b0f  jmp     loc_180025994
0x180025b14  mov     r8, [rbp+pData]
0x180025b18  mov     rcx, rsi
0x180025b1b  mov     edx, dword ptr [rbp+var_40]
0x180025b1e  call    EapUpdateMasterConnectionData
0x180025b23  mov     ebx, eax
0x180025b25  test    eax, eax
0x180025b27  jz      short loc_180025B45
0x180025b29  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b30  cmp     rcx, r13
0x180025b33  jz      short loc_180025B53
0x180025b35  test    byte ptr [rcx+44h], 1
0x180025b39  jz      short loc_180025B53
0x180025b3b  mov     edx, 152h
0x180025b40  jmp     loc_180025994
0x180025b45  mov     eax, dword ptr [rbp+var_40+4]
0x180025b48  mov     [r12], eax
0x180025b4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b53  mov     rax, [rbp+pData]
0x180025b57  test    rax, rax
0x180025b5a  jz      short loc_180025B6C
0x180025b5c  mov     rcx, rax; pData
0x180025b5f  call    cs:__imp_EapHostPeerFreeMemory
0x180025b65  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b6c  cmp     rcx, r13
0x180025b6f  jz      short loc_180025B92
0x180025b71  test    dword ptr [rcx+44h], 800h
0x180025b78  jz      short loc_180025B92
0x180025b7a  mov     rcx, [rcx+38h]
0x180025b7e  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180025b85  mov     edx, 153h
0x180025b8a  mov     r9d, ebx
0x180025b8d  call    WPP_SF_D
0x180025b92  mov     eax, ebx
0x180025b94  mov     rcx, [rbp+var_10]
0x180025b98  xor     rcx, rsp; StackCookie
0x180025b9b  call    __security_check_cookie
0x180025ba0  mov     rbx, [rsp+80h+arg_18]
0x180025ba8  add     rsp, 80h
0x180025baf  pop     r15
0x180025bb1  pop     r14
0x180025bb3  pop     r13
0x180025bb5  pop     r12
0x180025bb7  pop     rdi
0x180025bb8  pop     rsi
0x180025bb9  pop     rbp
0x180025bba  retn
```
