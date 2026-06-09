# MQpRegisterCertificate

- ea: `0x1800114c0`
- end: `0x180011b52`
- name: `MQpRegisterCertificate`
- size: `1682`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180012000`

## callees

- `0x1800087f8`
- `0x18000a33c`
- `0x180010a58`
- `0x180010b10`
- `0x180010f00`
- `0x180011050`
- `0x180011200`
- `0x18001138c`
- `0x1800113d8`
- `0x1800114c0`
- `0x180011b8c`
- `0x1800120b0`
- `0x180012700`
- `0x180012e88`
- `0x180013c74`
- `0x180014458`

## import_xrefs

- `mqsec!MQSigCreateCertificate` at `0x180011a1d`
- `mqsec!MQSigCreateCertificate` at `0x180011a1d`
- `mqsec!MQSec_GetUserType` at `0x180011602`
- `mqsec!MQSec_GetUserType` at `0x180011602`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MQpRegisterCertificate(char a1, __int64 a2, unsigned int a3)
{
  int v6; // ebx
  unsigned __int16 v7; // r8
  int v9; // r15d
  int UserType; // eax
  unsigned int v11; // r14d
  int v12; // eax
  unsigned int v13; // r14d
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // eax
  unsigned __int16 v17; // r8
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  int v22; // r15d
  __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // [rsp+30h] [rbp-28h] BYREF
  int v29; // [rsp+34h] [rbp-24h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-20h] BYREF
  __int64 v31; // [rsp+40h] [rbp-18h] BYREF
  _QWORD v32[2]; // [rsp+48h] [rbp-10h] BYREF
  unsigned int v33; // [rsp+B8h] [rbp+60h] BYREF

  v6 = RtpOneTimeThreadInit();
  if ( v6 < 0 )
  {
    v7 = 1108;
LABEL_3:
    LogMsgHR(v6, (wchar_t *)L"rt/rtintcrt", v7);
    return (unsigned int)v6;
  }
  if ( IsWorkGroupMode() )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 11, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids);
    v7 = 1111;
    v6 = -1072824214;
    goto LABEL_3;
  }
  v9 = a1 & 2;
  if ( a2 )
  {
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 12, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids);
      v7 = 1112;
LABEL_15:
      v6 = -1072824314;
      goto LABEL_3;
    }
    if ( !a3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 13, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids);
      v7 = 1113;
      goto LABEL_15;
    }
  }
  v29 = 0;
  v33 = 0;
  v28 = 0;
  UserType = MQSec_GetUserType(0, &v29, (int *)&v33, &v28);
  v11 = UserType;
  if ( UserType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        14,
        WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids,
        (unsigned int)UserType);
    LogMsgHR(v11, (wchar_t *)L"rt/rtintcrt", 0x461u);
    return v11;
  }
  if ( v29 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 15, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids);
    v7 = 1122;
    v6 = -1072824303;
    goto LABEL_3;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 32), 16, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids, v33, v28);
  v32[0] = 0;
  if ( v9 )
  {
    v30 = 0;
    v12 = RTOpenInternalCertStore(v32, &v30, 1, v33, 0);
    v11 = v12;
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          17,
          WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids,
          (unsigned int)v12);
      LogMsgHR(v11, (wchar_t *)L"rt/rtintcrt", 0x463u);
      goto LABEL_106;
    }
    v13 = v30;
    if ( v30 && !(unsigned int)GetDWORDKeyValue(L"ShouldRegisterCertInDs") )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 18, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids);
      v11 = 1074659338;
      goto LABEL_106;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 19, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids, v13);
    v14 = v32[0];
    v32[0] = 0;
    SafeRelease<CMQSigCertificate>(v14);
  }
  v31 = 0;
  if ( a2 )
  {
    v22 = 0;
    v25 = MQSigCreateCertificate(&v31, 0, a2, a3);
    v11 = v25;
    if ( v25 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          24,
          WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids,
          (unsigned int)v25);
      v17 = 1134;
      goto LABEL_104;
    }
  }
  else
  {
    if ( (int)RTGetInternalCert((unsigned int)&v31, (unsigned int)v32, 1, v33, 0) >= 0 )
    {
      if ( v33 || (v15 = 0, v28) )
        v15 = 1;
      v16 = RTRegisterUserCert(v31, v15);
      v11 = v16;
      if ( (int)(v16 + 0x80000000) >= 0 && v16 != -1072824274 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 20, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids, v16);
        v17 = 1127;
        goto LABEL_104;
      }
      v18 = RTRemoveUserCert(v31);
      v11 = v18;
      if ( ((v18 + 0x80000000) & 0x80000000) == 0 && v18 != -1072823025 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 21, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids, v18);
        v17 = 1128;
        goto LABEL_104;
      }
      v19 = RTDeleteInternalCert(v31);
      v11 = v19;
      if ( ((v19 + 0x80000000) & 0x80000000) == 0 && v19 != -1072824273 )
      {
        SetDWORDKeyValue(L"ShouldRegisterCertInDs");
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 22, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids, v11);
        v17 = 1131;
        goto LABEL_104;
      }
      v20 = v31;
      v31 = 0;
      SafeRelease<CMQSigCertificate>(v20);
    }
    v21 = RTCreateInternalCertificate(&v31);
    v11 = v21;
    if ( v21 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          23,
          WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids,
          (unsigned int)v21);
      v17 = 1132;
      goto LABEL_104;
    }
    v22 = 1;
    SetDWORDKeyValue(L"ShouldRegisterCertInDs");
  }
  if ( v33 || (v23 = 0, v28) )
    v23 = 1;
  v24 = RTRegisterUserCert(v31, v23);
  v11 = v24;
  if ( v24 >= 0 && !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 25, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids);
    goto LABEL_105;
  }
  if ( v22 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        26,
        WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids,
        (unsigned int)v24);
    v26 = v31;
    v31 = 0;
    SafeRelease<CMQSigCertificate>(v26);
    v27 = v32[0];
    v32[0] = 0;
    SafeRelease<CMQSigCertificate>(v27);
    if ( (int)RTGetInternalCert((unsigned int)&v31, (unsigned int)v32, 1, v33, 0) < 0
      || (int)RTDeleteInternalCert(v31) < 0 )
    {
      SetDWORDKeyValue(L"ShouldRegisterCertInDs");
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 27, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids);
    }
  }
  if ( (v11 & 0x80000000) == 0 )
    goto LABEL_105;
  v17 = 400;
LABEL_104:
  LogMsgHR(v11, (wchar_t *)L"rt/rtintcrt", v17);
LABEL_105:
  SafeRelease<CMQSigCertificate>(v31);
LABEL_106:
  SafeRelease<CMQSigCertificate>(v32[0]);
  return v11;
}

```

## disassembly

```asm
0x1800114c0  push    rbp
0x1800114c2  push    rbx
0x1800114c3  push    rsi
0x1800114c4  push    rdi
0x1800114c5  push    r12
0x1800114c7  push    r13
0x1800114c9  push    r14
0x1800114cb  push    r15
0x1800114cd  mov     rbp, rsp
0x1800114d0  sub     rsp, 58h
0x1800114d4  mov     r13d, r8d
0x1800114d7  mov     r12, rdx
0x1800114da  mov     r15d, ecx
0x1800114dd  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x1800114e2  mov     ebx, eax
0x1800114e4  xor     edi, edi
0x1800114e6  test    eax, eax
0x1800114e8  jns     short loc_180011505
0x1800114ea  mov     r8d, 454h; unsigned __int16
0x1800114f0  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x1800114f7  mov     ecx, ebx; int
0x1800114f9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800114fe  mov     eax, ebx
0x180011500  jmp     loc_180011B41
0x180011505  call    ?IsWorkGroupMode@@YA_NXZ; IsWorkGroupMode(void)
0x18001150a  test    al, al
0x18001150c  jz      short loc_180011551
0x18001150e  lea     rdi, WPP_GLOBAL_Control
0x180011515  mov     rcx, cs:WPP_GLOBAL_Control
0x18001151c  cmp     rcx, rdi
0x18001151f  jz      short loc_180011544
0x180011521  mov     ebx, 1
0x180011526  test    [rcx+10Ch], bl
0x18001152c  jz      short loc_180011544
0x18001152e  lea     edx, [rbx+0Ah]
0x180011531  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x180011538  mov     rcx, [rcx+100h]
0x18001153f  call    WPP_SF_
0x180011544  mov     r8d, 457h
0x18001154a  mov     ebx, 0C00E006Ah
0x18001154f  jmp     short loc_1800114F0
0x180011551  and     r15d, 2
0x180011555  test    r12, r12
0x180011558  jz      loc_1800115EB
0x18001155e  test    r15d, r15d
0x180011561  jz      short loc_1800115A9
0x180011563  lea     rdi, WPP_GLOBAL_Control
0x18001156a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011571  cmp     rcx, rdi
0x180011574  jz      short loc_180011599
0x180011576  mov     ebx, 1
0x18001157b  test    [rcx+10Ch], bl
0x180011581  jz      short loc_180011599
0x180011583  lea     edx, [rbx+0Bh]
0x180011586  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x18001158d  mov     rcx, [rcx+100h]
0x180011594  call    WPP_SF_
0x180011599  mov     r8d, 458h
0x18001159f  mov     ebx, 0C00E0006h
0x1800115a4  jmp     loc_1800114F0
0x1800115a9  test    r13d, r13d
0x1800115ac  jnz     short loc_1800115EB
0x1800115ae  lea     rdi, WPP_GLOBAL_Control
0x1800115b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115bc  cmp     rcx, rdi
0x1800115bf  jz      short loc_1800115E3
0x1800115c1  lea     ebx, [r13+1]
0x1800115c5  test    [rcx+10Ch], bl
0x1800115cb  jz      short loc_1800115E3
0x1800115cd  lea     edx, [rbx+0Ch]
0x1800115d0  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x1800115d7  mov     rcx, [rcx+100h]
0x1800115de  call    WPP_SF_
0x1800115e3  mov     r8d, 459h
0x1800115e9  jmp     short loc_18001159F
0x1800115eb  mov     [rbp+var_24], edi
0x1800115ee  mov     [rbp+arg_18], edi
0x1800115f1  mov     [rbp+var_28], edi
0x1800115f4  lea     r9, [rbp+var_28]
0x1800115f8  lea     r8, [rbp+arg_18]
0x1800115fc  lea     rdx, [rbp+var_24]
0x180011600  xor     ecx, ecx
0x180011602  call    cs:__imp_?MQSec_GetUserType@@YAJPEAXPEAH11@Z; MQSec_GetUserType(void *,int *,int *,int *)
0x180011608  mov     r14d, eax
0x18001160b  test    eax, eax
0x18001160d  jns     short loc_180011662
0x18001160f  lea     rdi, WPP_GLOBAL_Control
0x180011616  mov     rcx, cs:WPP_GLOBAL_Control
0x18001161d  cmp     rcx, rdi
0x180011620  jz      short loc_180011648
0x180011622  mov     ebx, 1
0x180011627  test    [rcx+10Ch], bl
0x18001162d  jz      short loc_180011648
0x18001162f  lea     edx, [rbx+0Dh]
0x180011632  mov     r9d, eax
0x180011635  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x18001163c  mov     rcx, [rcx+100h]
0x180011643  call    WPP_SF_d
0x180011648  mov     r8d, 461h; unsigned __int16
0x18001164e  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180011655  mov     ecx, r14d; int
0x180011658  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001165d  jmp     loc_180011B3E
0x180011662  cmp     [rbp+var_24], edi
0x180011665  jz      short loc_1800116AD
0x180011667  lea     rdi, WPP_GLOBAL_Control
0x18001166e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011675  cmp     rcx, rdi
0x180011678  jz      short loc_18001169D
0x18001167a  mov     ebx, 1
0x18001167f  test    [rcx+10Ch], bl
0x180011685  jz      short loc_18001169D
0x180011687  lea     edx, [rbx+0Eh]
0x18001168a  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x180011691  mov     rcx, [rcx+100h]
0x180011698  call    WPP_SF_
0x18001169d  mov     r8d, 462h
0x1800116a3  mov     ebx, 0C00E0011h
0x1800116a8  jmp     loc_1800114F0
0x1800116ad  lea     rdi, WPP_GLOBAL_Control
0x1800116b4  lea     rsi, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x1800116bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116c2  cmp     rcx, rdi
0x1800116c5  jz      short loc_1800116EF
0x1800116c7  test    byte ptr [rcx+10Ch], 4
0x1800116ce  jz      short loc_1800116EF
0x1800116d0  mov     edx, 10h
0x1800116d5  mov     eax, [rbp+var_28]
0x1800116d8  mov     dword ptr [rsp+58h+var_38], eax
0x1800116dc  mov     r9d, [rbp+arg_18]
0x1800116e0  mov     r8, rsi
0x1800116e3  mov     rcx, [rcx+100h]
0x1800116ea  call    WPP_SF_dd
0x1800116ef  mov     [rbp+var_10], 0
0x1800116f7  mov     ebx, 1
0x1800116fc  test    r15d, r15d
0x1800116ff  jz      loc_1800117FB
0x180011705  mov     [rbp+var_20], 0
0x18001170c  mov     [rsp+58h+var_38], 0
0x180011715  mov     r9d, [rbp+arg_18]
0x180011719  mov     r8d, ebx
0x18001171c  lea     rdx, [rbp+var_20]
0x180011720  lea     rcx, [rbp+var_10]
0x180011724  call    RTOpenInternalCertStore
0x180011729  mov     r14d, eax
0x18001172c  test    eax, eax
0x18001172e  jns     short loc_180011773
0x180011730  mov     rcx, cs:WPP_GLOBAL_Control
0x180011737  cmp     rcx, rdi
0x18001173a  jz      short loc_180011759
0x18001173c  test    [rcx+10Ch], bl
0x180011742  jz      short loc_180011759
0x180011744  lea     edx, [rbx+10h]
0x180011747  mov     r9d, eax
0x18001174a  mov     r8, rsi
0x18001174d  mov     rcx, [rcx+100h]
0x180011754  call    WPP_SF_d
0x180011759  mov     r8d, 463h; unsigned __int16
0x18001175f  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180011766  mov     ecx, r14d; int
0x180011769  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001176e  jmp     loc_180011B35
0x180011773  mov     r14d, [rbp+var_20]
0x180011777  test    r14d, r14d
0x18001177a  jz      short loc_1800117BE
0x18001177c  lea     rcx, aShouldregister; "ShouldRegisterCertInDs"
0x180011783  call    GetDWORDKeyValue
0x180011788  test    eax, eax
0x18001178a  jnz     short loc_1800117BE
0x18001178c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011793  cmp     rcx, rdi
0x180011796  jz      short loc_1800117B3
0x180011798  test    byte ptr [rcx+10Ch], 4
0x18001179f  jz      short loc_1800117B3
0x1800117a1  lea     edx, [rax+12h]
0x1800117a4  mov     r8, rsi
0x1800117a7  mov     rcx, [rcx+100h]
0x1800117ae  call    WPP_SF_
0x1800117b3  mov     r14d, 400E000Ah
0x1800117b9  jmp     loc_180011B35
0x1800117be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117c5  cmp     rcx, rdi
0x1800117c8  jz      short loc_1800117EA
0x1800117ca  test    byte ptr [rcx+10Ch], 4
0x1800117d1  jz      short loc_1800117EA
0x1800117d3  mov     edx, 13h
0x1800117d8  mov     r9d, r14d
0x1800117db  mov     r8, rsi
0x1800117de  mov     rcx, [rcx+100h]
0x1800117e5  call    WPP_SF_d
0x1800117ea  mov     rcx, [rbp+var_10]
0x1800117ee  mov     [rbp+var_10], 0
0x1800117f6  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x1800117fb  mov     [rbp+var_18], 0
0x180011803  lea     rcx, [rbp+var_18]
0x180011807  test    r12, r12
0x18001180a  jnz     loc_180011A12
0x180011810  xor     r13d, r13d
0x180011813  mov     [rsp+58h+var_38], r13
0x180011818  mov     r9d, [rbp+arg_18]
0x18001181c  mov     r8d, ebx
0x18001181f  lea     rdx, [rbp+var_10]
0x180011823  call    RTGetInternalCert
0x180011828  test    eax, eax
0x18001182a  js      loc_180011958
0x180011830  cmp     [rbp+arg_18], r13d
0x180011834  jnz     short loc_18001183F
0x180011836  cmp     [rbp+var_28], r13d
0x18001183a  mov     edx, r13d
0x18001183d  jz      short loc_180011841
0x18001183f  mov     edx, ebx
0x180011841  mov     rcx, [rbp+var_18]
0x180011845  call    RTRegisterUserCert
0x18001184a  mov     r14d, eax
0x18001184d  mov     r15d, 80000000h
0x180011853  lea     ecx, [rax+r15]
0x180011857  test    r15d, ecx
0x18001185a  jnz     short loc_180011899
0x18001185c  cmp     eax, 0C00E002Eh
0x180011861  jz      short loc_180011899
0x180011863  mov     rcx, cs:WPP_GLOBAL_Control
0x18001186a  cmp     rcx, rdi
0x18001186d  jz      short loc_18001188E
0x18001186f  test    [rcx+10Ch], bl
0x180011875  jz      short loc_18001188E
0x180011877  mov     edx, 14h
0x18001187c  mov     r9d, eax
0x18001187f  mov     r8, rsi
0x180011882  mov     rcx, [rcx+100h]
0x180011889  call    WPP_SF_d
0x18001188e  mov     r8d, 467h
0x180011894  jmp     loc_180011B1B
0x180011899  mov     rcx, [rbp+var_18]
0x18001189d  call    RTRemoveUserCert
0x1800118a2  mov     r14d, eax
0x1800118a5  lea     ecx, [rax+r15]
0x1800118a9  test    r15d, ecx
0x1800118ac  jnz     short loc_1800118EB
0x1800118ae  cmp     eax, 0C00E050Fh
0x1800118b3  jz      short loc_1800118EB
0x1800118b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118bc  cmp     rcx, rdi
0x1800118bf  jz      short loc_1800118E0
0x1800118c1  test    [rcx+10Ch], bl
0x1800118c7  jz      short loc_1800118E0
0x1800118c9  mov     edx, 15h
0x1800118ce  mov     r9d, eax
0x1800118d1  mov     r8, rsi
0x1800118d4  mov     rcx, [rcx+100h]
0x1800118db  call    WPP_SF_d
0x1800118e0  mov     r8d, 468h
0x1800118e6  jmp     loc_180011B1B
0x1800118eb  mov     rcx, [rbp+var_18]
0x1800118ef  call    RTDeleteInternalCert
0x1800118f4  mov     r14d, eax
0x1800118f7  lea     edx, [rax+r15]
0x1800118fb  test    r15d, edx
0x1800118fe  jnz     short loc_18001194B
0x180011900  cmp     eax, 0C00E002Fh
0x180011905  jz      short loc_18001194B
0x180011907  mov     edx, ebx
0x180011909  lea     rcx, aShouldregister; "ShouldRegisterCertInDs"
0x180011910  call    SetDWORDKeyValue
0x180011915  mov     rcx, cs:WPP_GLOBAL_Control
0x18001191c  cmp     rcx, rdi
0x18001191f  jz      short loc_180011940
0x180011921  test    [rcx+10Ch], bl
0x180011927  jz      short loc_180011940
0x180011929  mov     edx, 16h
0x18001192e  mov     r9d, r14d
0x180011931  mov     r8, rsi
0x180011934  mov     rcx, [rcx+100h]
0x18001193b  call    WPP_SF_d
0x180011940  mov     r8d, 46Bh
0x180011946  jmp     loc_180011B1B
0x18001194b  mov     rcx, [rbp+var_18]
0x18001194f  mov     [rbp+var_18], r13
0x180011953  call    ??$SafeRelease@VCMQSigCertificate@@@@YAXPEAVCMQSigCertificate@@@Z; SafeRelease<CMQSigCertificate>(CMQSigCertificate *)
0x180011958  lea     rcx, [rbp+var_18]
0x18001195c  call    RTCreateInternalCertificate
0x180011961  mov     r14d, eax
0x180011964  test    eax, eax
0x180011966  jns     short loc_18001199E
0x180011968  mov     rcx, cs:WPP_GLOBAL_Control
0x18001196f  cmp     rcx, rdi
0x180011972  jz      short loc_180011993
0x180011974  test    [rcx+10Ch], bl
0x18001197a  jz      short loc_180011993
0x18001197c  mov     edx, 17h
0x180011981  mov     r9d, eax
0x180011984  mov     r8, rsi
0x180011987  mov     rcx, [rcx+100h]
0x18001198e  call    WPP_SF_d
0x180011993  mov     r8d, 46Ch
0x180011999  jmp     loc_180011B1B
0x18001199e  mov     r15d, ebx
0x1800119a1  xor     edx, edx
0x1800119a3  lea     rcx, aShouldregister; "ShouldRegisterCertInDs"
0x1800119aa  call    SetDWORDKeyValue
0x1800119af  cmp     [rbp+arg_18], r13d
  ... truncated ...
```
