# DeviceEncryptionSupportLevel::EvaluateDeviceEncryptionSupport(void)

- ea: `0x180016084`
- end: `0x1800164c1`
- name: `?EvaluateDeviceEncryptionSupport@DeviceEncryptionSupportLevel@@AEAAJXZ`
- size: `1085`
- prototype: `__int64 __fastcall(DeviceEncryptionSupportLevel *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180017b2c`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x1800037a0`
- `0x180005018`
- `0x18000e354`
- `0x180010078`
- `0x180010160`
- `0x180010208`
- `0x1800105f8`
- `0x180016084`
- `0x180017a40`
- `0x180018838`

## import_xrefs

- `FVEAPI!FveCheckTpmCapability` at `0x180016361`
- `FVEAPI!FveCheckTpmCapability` at `0x180016361`
- `FVEAPI!FveGetSecureBootBindingState` at `0x1800163d3`
- `FVEAPI!FveGetSecureBootBindingState` at `0x1800163d3`
- `FVEAPI!FveGetStatus` at `0x180016256`
- `FVEAPI!FveGetStatus` at `0x180016256`

## string_xrefs

- `0x180016319`: `ReportDEHardwareCompliant`

## pseudocode

```c
__int64 __fastcall DeviceEncryptionSupportLevel::EvaluateDeviceEncryptionSupport(DeviceEncryptionSupportLevel *this)
{
  unsigned int v2; // eax
  int v3; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  unsigned int OSVolumeHandle; // eax
  unsigned int Status; // eax
  PVOID *v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rdx
  PVOID *v12; // rcx
  unsigned int v13; // eax
  unsigned int SecureBootBindingState; // eax
  PVOID *v15; // rcx
  bool v17; // [rsp+20h] [rbp-89h] BYREF
  bool v18; // [rsp+21h] [rbp-88h] BYREF
  bool v19; // [rsp+22h] [rbp-87h] BYREF
  unsigned int v20; // [rsp+24h] [rbp-85h] BYREF
  void **v21; // [rsp+28h] [rbp-81h] BYREF
  __int64 v22; // [rsp+30h] [rbp-79h]
  _DWORD v23[2]; // [rsp+38h] [rbp-71h] BYREF
  __int64 v24; // [rsp+40h] [rbp-69h]
  int v25; // [rsp+48h] [rbp-61h]
  _DWORD v26[14]; // [rsp+50h] [rbp-59h] BYREF
  char v27; // [rsp+88h] [rbp-21h]

  v23[0] = 20;
  v23[1] = 2;
  v24 = 0;
  v25 = 0;
  v19 = 0;
  v17 = 0;
  v18 = 0;
  v20 = -1;
  v21 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v22 = 0;
  memset_0(v26, 0, 0x90u);
  *(_BYTE *)this = 0;
  *((_BYTE *)this + 3) = 0;
  v2 = NgscbCheckPreventDeviceEncryption(&v17);
  v3 = v2;
  if ( v2 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v2);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 < 0 )
      goto LABEL_81;
  }
  else
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v17 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    {
      v5 = 15;
LABEL_12:
      WPP_SF_(v4[2], v5, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
      goto LABEL_81;
    }
    goto LABEL_81;
  }
  v6 = NgscbCheckPreventDeviceEncryptionForAad(&v18);
  v3 = v6;
  if ( v6 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v6);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 < 0 )
      goto LABEL_81;
  }
  else
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v18 )
  {
    v26[0] = 144;
    v26[1] = 10;
    OSVolumeHandle = FveEasUtil::I_GetOSVolumeHandle(&v21);
    v3 = OSVolumeHandle;
    if ( OSVolumeHandle )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
          OSVolumeHandle);
      if ( v3 < 0 )
        goto LABEL_81;
    }
    Status = FveGetStatus(v22, v26);
    v3 = Status;
    if ( Status )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, Status);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v3 < 0 )
        goto LABEL_81;
    }
    else
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (v27 & 8) != 0 )
    {
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
        WPP_SF_(v9[2], 20, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
      *(_BYTE *)this = 1;
LABEL_80:
      *((_BYTE *)this + 3) = 1;
      goto LABEL_81;
    }
    v10 = NgscbCheckIsAOACDevice(&v19);
    v3 = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v10);
      if ( v3 < 0 )
        goto LABEL_81;
    }
    LOBYTE(v11) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs>::GetImpl'::`2'::impl,
      v11);
    if ( NgscbGet_TEST_BooleanOverride(L"ReportDEHardwareCompliant", (bool *)this) )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_75;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
        *(unsigned __int8 *)this);
    }
    else
    {
      v13 = FveCheckTpmCapability(v23);
      v3 = v13;
      if ( v13 )
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v13);
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v3 < 0 )
          goto LABEL_81;
      }
      else
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !v25 )
      {
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
        {
          v5 = 36;
          goto LABEL_12;
        }
        goto LABEL_81;
      }
      SecureBootBindingState = FveGetSecureBootBindingState(&v20);
      v3 = SecureBootBindingState;
      if ( SecureBootBindingState )
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
            SecureBootBindingState);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v3 < 0 )
          goto LABEL_81;
      }
      else
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v20 != 1 && v20 - 2 >= 2 )
      {
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
          WPP_SF_d(v15[2], 38, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v20);
        goto LABEL_81;
      }
      *(_BYTE *)this = 1;
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_75:
    if ( (!v19 || !*(_BYTE *)this) && v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      WPP_SF_(v12[2], 39, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
    goto LABEL_80;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
  {
    v5 = 17;
    goto LABEL_12;
  }
LABEL_81:
  v21 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close((__int64)&v21);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180016084  mov     [rsp-8+arg_8], rbx
0x180016089  mov     [rsp-8+arg_10], rdi
0x18001608e  push    rbp
0x18001608f  push    r14
0x180016091  push    r15
0x180016093  lea     rbp, [rsp-47h]
0x180016098  sub     rsp, 0F0h
0x18001609f  mov     rax, cs:__security_cookie
0x1800160a6  xor     rax, rsp
0x1800160a9  mov     [rbp+57h+var_20], rax
0x1800160ad  mov     rdi, rcx
0x1800160b0  mov     [rbp+57h+var_C8], 14h
0x1800160b7  mov     [rbp+57h+var_C4], 2
0x1800160be  xor     eax, eax
0x1800160c0  mov     [rbp+57h+var_C0], rax
0x1800160c4  mov     [rbp+57h+var_B8], eax
0x1800160c7  mov     [rsp+100h+var_DE], al
0x1800160cb  mov     [rsp+100h+var_E0], al
0x1800160cf  mov     [rsp+100h+var_DF], al
0x1800160d3  mov     [rsp+100h+var_DC], 0FFFFFFFFh
0x1800160db  lea     rax, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x1800160e2  mov     [rsp+100h+var_D8], rax
0x1800160e7  mov     [rbp+57h+var_D0], 0
0x1800160ef  xor     edx, edx; Val
0x1800160f1  mov     r8d, 90h; Size
0x1800160f7  lea     rcx, [rbp+57h+var_B0]; void *
0x1800160fb  call    memset_0
0x180016100  mov     byte ptr [rdi], 0
0x180016103  mov     byte ptr [rdi+3], 0
0x180016107  lea     rcx, [rsp+100h+var_E0]; bool *
0x18001610c  call    ?NgscbCheckPreventDeviceEncryption@@YAJPEA_N@Z; NgscbCheckPreventDeviceEncryption(bool *)
0x180016111  mov     ebx, eax
0x180016113  lea     r14, WPP_GLOBAL_Control
0x18001611a  lea     r15, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180016121  test    eax, eax
0x180016123  jz      short loc_18001615C
0x180016125  mov     rcx, cs:WPP_GLOBAL_Control
0x18001612c  cmp     rcx, r14
0x18001612f  jz      short loc_180016152
0x180016131  test    byte ptr [rcx+1Ch], 40h
0x180016135  jz      short loc_180016152
0x180016137  mov     edx, 0Eh
0x18001613c  mov     r9d, eax
0x18001613f  mov     r8, r15
0x180016142  mov     rcx, [rcx+10h]
0x180016146  call    WPP_SF_d
0x18001614b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016152  test    ebx, ebx
0x180016154  js      loc_180016484
0x18001615a  jmp     short loc_180016163
0x18001615c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016163  cmp     [rsp+100h+var_E0], 0
0x180016168  jz      short loc_180016193
0x18001616a  cmp     rcx, r14
0x18001616d  jz      loc_180016484
0x180016173  test    byte ptr [rcx+1Ch], 8
0x180016177  jz      loc_180016484
0x18001617d  mov     edx, 0Fh
0x180016182  mov     r8, r15
0x180016185  mov     rcx, [rcx+10h]
0x180016189  call    WPP_SF_
0x18001618e  jmp     loc_180016484
0x180016193  lea     rcx, [rsp+100h+var_DF]; bool *
0x180016198  call    ?NgscbCheckPreventDeviceEncryptionForAad@@YAJPEA_N@Z; NgscbCheckPreventDeviceEncryptionForAad(bool *)
0x18001619d  mov     ebx, eax
0x18001619f  test    eax, eax
0x1800161a1  jz      short loc_1800161DA
0x1800161a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161aa  cmp     rcx, r14
0x1800161ad  jz      short loc_1800161D0
0x1800161af  test    byte ptr [rcx+1Ch], 40h
0x1800161b3  jz      short loc_1800161D0
0x1800161b5  mov     edx, 10h
0x1800161ba  mov     r9d, eax
0x1800161bd  mov     r8, r15
0x1800161c0  mov     rcx, [rcx+10h]
0x1800161c4  call    WPP_SF_d
0x1800161c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161d0  test    ebx, ebx
0x1800161d2  js      loc_180016484
0x1800161d8  jmp     short loc_1800161E1
0x1800161da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161e1  cmp     [rsp+100h+var_DF], 0
0x1800161e6  jz      short loc_180016202
0x1800161e8  cmp     rcx, r14
0x1800161eb  jz      loc_180016484
0x1800161f1  test    byte ptr [rcx+1Ch], 8
0x1800161f5  jz      loc_180016484
0x1800161fb  mov     edx, 11h
0x180016200  jmp     short loc_180016182
0x180016202  mov     [rbp+57h+var_B0], 90h
0x180016209  mov     [rbp+57h+var_AC], 0Ah
0x180016210  lea     rcx, [rsp+100h+var_D8]
0x180016215  call    ?I_GetOSVolumeHandle@FveEasUtil@@CAJAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetOSVolumeHandle(Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x18001621a  mov     ebx, eax
0x18001621c  test    eax, eax
0x18001621e  jz      short loc_18001624E
0x180016220  mov     rcx, cs:WPP_GLOBAL_Control
0x180016227  cmp     rcx, r14
0x18001622a  jz      short loc_180016246
0x18001622c  test    byte ptr [rcx+1Ch], 40h
0x180016230  jz      short loc_180016246
0x180016232  mov     edx, 12h
0x180016237  mov     r9d, eax
0x18001623a  mov     r8, r15
0x18001623d  mov     rcx, [rcx+10h]
0x180016241  call    WPP_SF_d
0x180016246  test    ebx, ebx
0x180016248  js      loc_180016484
0x18001624e  lea     rdx, [rbp+57h+var_B0]
0x180016252  mov     rcx, [rbp+57h+var_D0]
0x180016256  call    cs:__imp_FveGetStatus
0x18001625c  mov     ebx, eax
0x18001625e  test    eax, eax
0x180016260  jz      short loc_180016299
0x180016262  mov     rcx, cs:WPP_GLOBAL_Control
0x180016269  cmp     rcx, r14
0x18001626c  jz      short loc_18001628F
0x18001626e  test    byte ptr [rcx+1Ch], 40h
0x180016272  jz      short loc_18001628F
0x180016274  mov     edx, 13h
0x180016279  mov     r9d, eax
0x18001627c  mov     r8, r15
0x18001627f  mov     rcx, [rcx+10h]
0x180016283  call    WPP_SF_d
0x180016288  mov     rcx, cs:WPP_GLOBAL_Control
0x18001628f  test    ebx, ebx
0x180016291  js      loc_180016484
0x180016297  jmp     short loc_1800162A0
0x180016299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162a0  test    [rbp+57h+var_78], 8
0x1800162a4  jz      short loc_1800162CA
0x1800162a6  cmp     rcx, r14
0x1800162a9  jz      short loc_1800162C2
0x1800162ab  test    byte ptr [rcx+1Ch], 8
0x1800162af  jz      short loc_1800162C2
0x1800162b1  mov     edx, 14h
0x1800162b6  mov     r8, r15
0x1800162b9  mov     rcx, [rcx+10h]
0x1800162bd  call    WPP_SF_
0x1800162c2  mov     byte ptr [rdi], 1
0x1800162c5  jmp     loc_180016480
0x1800162ca  lea     rcx, [rsp+100h+var_DE]; bool *
0x1800162cf  call    ?NgscbCheckIsAOACDevice@@YAJPEA_N@Z; NgscbCheckIsAOACDevice(bool *)
0x1800162d4  mov     ebx, eax
0x1800162d6  test    eax, eax
0x1800162d8  jz      short loc_180016308
0x1800162da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162e1  cmp     rcx, r14
0x1800162e4  jz      short loc_180016300
0x1800162e6  test    byte ptr [rcx+1Ch], 40h
0x1800162ea  jz      short loc_180016300
0x1800162ec  mov     edx, 15h
0x1800162f1  mov     r9d, eax
0x1800162f4  mov     r8, r15
0x1800162f7  mov     rcx, [rcx+10h]
0x1800162fb  call    WPP_SF_d
0x180016300  test    ebx, ebx
0x180016302  js      loc_180016484
0x180016308  mov     dl, 1
0x18001630a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs> `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs>::GetImpl(void)'::`2'::impl
0x180016311  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180016316  mov     rdx, rdi; bool *
0x180016319  lea     rcx, aReportdehardwa; "ReportDEHardwareCompliant"
0x180016320  call    ?NgscbGet_TEST_BooleanOverride@@YA_NPEBGPEA_N@Z; NgscbGet_TEST_BooleanOverride(ushort const *,bool *)
0x180016325  test    al, al
0x180016327  jz      short loc_18001635D
0x180016329  mov     rcx, cs:WPP_GLOBAL_Control
0x180016330  cmp     rcx, r14
0x180016333  jz      loc_180016458
0x180016339  test    byte ptr [rcx+1Ch], 8
0x18001633d  jz      loc_180016458
0x180016343  movzx   r9d, byte ptr [rdi]
0x180016347  mov     edx, 22h ; '"'
0x18001634c  mov     r8, r15
0x18001634f  mov     rcx, [rcx+10h]
0x180016353  call    WPP_SF_d
0x180016358  jmp     loc_180016451
0x18001635d  lea     rcx, [rbp+57h+var_C8]
0x180016361  call    cs:__imp_FveCheckTpmCapability
0x180016367  mov     ebx, eax
0x180016369  test    eax, eax
0x18001636b  jz      short loc_1800163A4
0x18001636d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016374  cmp     rcx, r14
0x180016377  jz      short loc_18001639A
0x180016379  test    byte ptr [rcx+1Ch], 40h
0x18001637d  jz      short loc_18001639A
0x18001637f  mov     edx, 23h ; '#'
0x180016384  mov     r9d, eax
0x180016387  mov     r8, r15
0x18001638a  mov     rcx, [rcx+10h]
0x18001638e  call    WPP_SF_d
0x180016393  mov     rcx, cs:WPP_GLOBAL_Control
0x18001639a  test    ebx, ebx
0x18001639c  js      loc_180016484
0x1800163a2  jmp     short loc_1800163AB
0x1800163a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163ab  cmp     [rbp+57h+var_B8], 0
0x1800163af  jnz     short loc_1800163CE
0x1800163b1  cmp     rcx, r14
0x1800163b4  jz      loc_180016484
0x1800163ba  test    byte ptr [rcx+1Ch], 2
0x1800163be  jz      loc_180016484
0x1800163c4  mov     edx, 24h ; '$'
0x1800163c9  jmp     loc_180016182
0x1800163ce  lea     rcx, [rsp+100h+var_DC]
0x1800163d3  call    cs:__imp_FveGetSecureBootBindingState
0x1800163d9  mov     ebx, eax
0x1800163db  test    eax, eax
0x1800163dd  jz      short loc_180016412
0x1800163df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163e6  cmp     rcx, r14
0x1800163e9  jz      short loc_18001640C
0x1800163eb  test    byte ptr [rcx+1Ch], 40h
0x1800163ef  jz      short loc_18001640C
0x1800163f1  mov     edx, 25h ; '%'
0x1800163f6  mov     r9d, eax
0x1800163f9  mov     r8, r15
0x1800163fc  mov     rcx, [rcx+10h]
0x180016400  call    WPP_SF_d
0x180016405  mov     rcx, cs:WPP_GLOBAL_Control
0x18001640c  test    ebx, ebx
0x18001640e  js      short loc_180016484
0x180016410  jmp     short loc_180016419
0x180016412  mov     rcx, cs:WPP_GLOBAL_Control
0x180016419  mov     r9d, [rsp+100h+var_DC]
0x18001641e  mov     edx, r9d
0x180016421  sub     edx, 1
0x180016424  jz      short loc_18001644E
0x180016426  sub     edx, 1
0x180016429  jz      short loc_18001644E
0x18001642b  cmp     edx, 1
0x18001642e  jz      short loc_18001644E
0x180016430  cmp     rcx, r14
0x180016433  jz      short loc_180016484
0x180016435  test    byte ptr [rcx+1Ch], 2
0x180016439  jz      short loc_180016484
0x18001643b  mov     edx, 26h ; '&'
0x180016440  mov     r8, r15
0x180016443  mov     rcx, [rcx+10h]
0x180016447  call    WPP_SF_d
0x18001644c  jmp     short loc_180016484
0x18001644e  mov     byte ptr [rdi], 1
0x180016451  mov     rcx, cs:WPP_GLOBAL_Control
0x180016458  cmp     [rsp+100h+var_DE], 0
0x18001645d  jz      short loc_180016464
0x18001645f  cmp     byte ptr [rdi], 0
0x180016462  jnz     short loc_180016480
0x180016464  cmp     rcx, r14
0x180016467  jz      short loc_180016480
0x180016469  test    byte ptr [rcx+1Ch], 1
0x18001646d  jz      short loc_180016480
0x18001646f  mov     edx, 27h ; '''
0x180016474  mov     r8, r15
0x180016477  mov     rcx, [rcx+10h]
0x18001647b  call    WPP_SF_
0x180016480  mov     byte ptr [rdi+3], 1
0x180016484  lea     rax, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x18001648b  mov     [rsp+100h+var_D8], rax
0x180016490  lea     rcx, [rsp+100h+var_D8]
0x180016495  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x18001649a  mov     eax, ebx
0x18001649c  mov     rcx, [rbp+57h+var_20]
0x1800164a0  xor     rcx, rsp; StackCookie
0x1800164a3  call    __security_check_cookie
0x1800164a8  lea     r11, [rsp+100h+var_10]
0x1800164b0  mov     rbx, [r11+28h]
0x1800164b4  mov     rdi, [r11+30h]
0x1800164b8  mov     rsp, r11
0x1800164bb  pop     r15
0x1800164bd  pop     r14
0x1800164bf  pop     rbp
0x1800164c0  retn
```
