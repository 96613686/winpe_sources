# CDfwEngWriter::HelperGenerateFwRule(_tag_FW_RULE *,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *,FW_PLUMBER_FILTER *,void * *,_DFW_IP_PORT_RANGE *,unsigned __int64 *,ulong)

- ea: `0x18000b080`
- end: `0x18000b7ec`
- name: `?HelperGenerateFwRule@CDfwEngWriter@@AEAAJPEAU_tag_FW_RULE@@PEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@PEAUFW_PLUMBER_FILTER@@PEAPEAXPEAU_DFW_IP_PORT_RANGE@@PEA_KK@Z`
- size: `1900`
- prototype: `int(CDfwEngWriter *__hidden this, struct _tag_FW_RULE *, struct _LIST_ENTRY *, struct _tag_FW_OBJECT_METADATA *, struct FW_PLUMBER_FILTER *, void **, struct _DFW_IP_PORT_RANGE *, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800281d0`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x18000b080`
- `0x18000b800`
- `0x18000d0b0`
- `0x180017110`
- `0x18002973c`
- `0x18003e030`
- `0x18003ee6c`
- `0x18005a514`
- `0x18006f520`

## import_xrefs

- `fwbase!FwMetaDataAddEnforcementState` at `0x18000b276`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000b2ef`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000b42a`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000b793`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000b276`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000b2ef`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000b42a`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000b793`
- `fwbase!FwFree` at `0x18000b2a1`
- `fwbase!FwFree` at `0x18000b66d`
- `fwbase!FwFree` at `0x18000b2a1`
- `fwbase!FwFree` at `0x18000b66d`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x18000b520`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x18000b53e`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x18000b520`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x18000b53e`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b280`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b28d`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b2f9`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b39c`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b49e`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b624`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b631`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b79d`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b280`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b28d`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b2f9`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b39c`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b49e`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b624`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b631`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000b79d`

## pseudocode

```c
__int64 __fastcall CDfwEngWriter::HelperGenerateFwRule(
        CDfwEngWriter *this,
        struct _tag_FW_RULE *a2,
        struct _LIST_ENTRY *a3,
        struct _tag_FW_OBJECT_METADATA *a4,
        struct FW_PLUMBER_FILTER *a5,
        void **a6,
        struct _DFW_IP_PORT_RANGE *a7,
        unsigned __int64 *a8,
        unsigned int a9)
{
  int v11; // ebp
  __int64 result; // rax
  int v13; // edx
  int v14; // r8d
  unsigned int v15; // edi
  int v16; // eax
  __int64 v17; // rcx
  int FwRule2; // eax
  __int64 v19; // rdx
  _WORD *v20; // rax
  _WORD *v21; // rcx
  CDfwEngWriter *v22; // rdi
  char *v23; // r8
  CDfwEngWriter *v24; // rdx
  _DWORD *v25; // r10
  CDfwEngWriter *v26; // r9
  int v27; // eax
  int v28; // eax
  unsigned __int64 *v29; // rax
  unsigned int v30; // ecx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r9
  int v34; // [rsp+50h] [rbp-B8h]
  int v35; // [rsp+54h] [rbp-B4h]
  int v36; // [rsp+58h] [rbp-B0h]
  unsigned int v37; // [rsp+5Ch] [rbp-ACh] BYREF
  _WORD *v38; // [rsp+60h] [rbp-A8h]
  CDfwEngWriter *v39; // [rsp+68h] [rbp-A0h]
  _QWORD *v40; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 *v41; // [rsp+78h] [rbp-90h] BYREF
  struct _DFW_IP_PORT_RANGE *v42; // [rsp+80h] [rbp-88h]
  void **v43; // [rsp+88h] [rbp-80h]
  struct FW_PLUMBER_FILTER *v44; // [rsp+90h] [rbp-78h]
  struct _LIST_ENTRY *v45; // [rsp+98h] [rbp-70h]
  char *v46; // [rsp+A0h] [rbp-68h]
  int v47; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-58h] BYREF

  v44 = a5;
  v43 = a6;
  v42 = a7;
  v45 = a3;
  v39 = this;
  v47 = 0;
  v48 = 0;
  v40 = 0;
  v41 = 0;
  v37 = 0;
  if ( !a9 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  v11 = 1;
  result = ResolveAddresses((struct _tag_FW_RULE *)((char *)a2 + 104), 0, 1, 0);
  v15 = result;
  if ( (int)result < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        92,
        WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
        (unsigned int)result);
      return v15;
    }
    return result;
  }
  v35 = 0;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    WPP_SF_Sdddd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      v13,
      v14,
      *((_QWORD *)a2 + 3),
      *((_DWORD *)a2 + 50),
      *((_DWORD *)a2 + 46),
      *((_DWORD *)a2 + 58),
      *((_DWORD *)a2 + 54));
  v16 = ResolveAddresses((struct _tag_FW_RULE *)((char *)a2 + 176), (__int64)&v48, 1, (__int64)a2 + 480);
  v34 = v16;
  v15 = v16;
  if ( v16 < 0 )
  {
    v11 = 0;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_28;
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      95,
      WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
      (unsigned int)v16);
    FwPolioEmptyWFAddresses((char *)a2 + 104);
    return v15;
  }
  v17 = *((unsigned int *)a2 + 98);
  if ( !(_DWORD)v17 )
  {
    FwRule2 = CDfwEngWriter::HelperGenerateFwRule2(v39, a2, v45, a4, v44, v43, v42, a8, a9, (unsigned int *)&v48);
    v15 = FwRule2;
    if ( FwRule2 < 0 )
    {
      v31 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v32 = 103;
        v33 = (unsigned int)FwRule2;
LABEL_60:
        WPP_SF_d(*(_QWORD *)(v31 + 16), v32, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids, v33);
        goto LABEL_12;
      }
      goto LABEL_28;
    }
LABEL_10:
    v19 = 1;
LABEL_11:
    FwMetaDataAddEnforcementState(a4, v19);
    goto LABEL_12;
  }
  FwGetTuplePerPackageCollection(v17, *((_QWORD *)a2 + 47), &v40);
  v20 = v40;
  if ( !v40 || (v21 = (_WORD *)*v40, v38 = v21, v21 == (_WORD *)v40) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 97, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
    v19 = 23;
    goto LABEL_11;
  }
  v22 = v39;
  v23 = (char *)a2 + 64;
  v24 = (struct _tag_FW_RULE *)((char *)a2 + 88);
  v36 = 0;
  v25 = (_DWORD *)((char *)a2 + 64);
  v26 = (struct _tag_FW_RULE *)((char *)a2 + 88);
  while ( 1 )
  {
    if ( v21 == v20 )
    {
      if ( v36 )
      {
        v15 = v34;
        goto LABEL_10;
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 102, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
      FwMetaDataAddEnforcementState(a4, 23);
      FwPolioEmptyWFAddresses((char *)a2 + 104);
      v15 = v34;
      goto LABEL_13;
    }
    v47 = 0;
    *((_WORD *)a2 + 24) = v21[10];
    v35 = 0;
    if ( v21[11] || (v25 = v23, v21[12]) )
    {
      *v25 = 1;
      v26 = v24;
      *((_QWORD *)a2 + 9) = v21 + 11;
    }
    if ( v21[13] || (v26 = v24, v21[14]) )
    {
      *(_DWORD *)v26 = 1;
      *((_QWORD *)a2 + 12) = v21 + 13;
    }
    v27 = FwPolioCopyWFAddressesContents(v21 + 16, (char *)a2 + 104);
    if ( v27 < 0 )
    {
      v31 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        v15 = v27;
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v32 = 98;
          goto LABEL_59;
        }
LABEL_12:
        FwPolioEmptyWFAddresses((char *)a2 + 104);
LABEL_13:
        FwPolioEmptyWFAddresses((char *)a2 + 176);
        goto LABEL_14;
      }
LABEL_67:
      v15 = v27;
      goto LABEL_12;
    }
    v27 = FwPolioCopyWFAddressesContents(v38 + 52, (char *)a2 + 176);
    v34 = v27;
    if ( v27 < 0 )
    {
      v31 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        v15 = v27;
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_12;
        v32 = 99;
LABEL_59:
        v33 = v15;
        goto LABEL_60;
      }
      goto LABEL_67;
    }
    if ( *((_DWORD *)v38 + 44) )
    {
      v28 = ResolveInterfaces((int)v38 + 176, 0, (unsigned int)&v41, (unsigned int)&v37, (__int64)&v47);
      v34 = v28;
      if ( v28 < 0 )
      {
        v31 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          v15 = v28;
          if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_28;
          v32 = 100;
          goto LABEL_59;
        }
        goto LABEL_78;
      }
      v29 = v41;
      v30 = v37;
      v35 = 1;
    }
    else
    {
      v30 = *((_DWORD *)v38 + 48);
      if ( v30 )
      {
        v29 = (unsigned __int64 *)*((_QWORD *)v38 + 25);
      }
      else
      {
        v30 = a9;
        v29 = a8;
      }
    }
    if ( v47 )
      goto LABEL_53;
    v28 = CDfwEngWriter::HelperGenerateFwRule2(v22, a2, v45, a4, v44, v43, v42, v29, v30, (unsigned int *)&v48);
    v34 = v28;
    if ( v28 < 0 )
      break;
    ++v36;
LABEL_53:
    FwPolioEmptyWFAddresses((char *)a2 + 104);
    FwPolioEmptyWFAddresses((char *)a2 + 176);
    v23 = (char *)a2 + 64;
    v24 = (struct _tag_FW_RULE *)((char *)a2 + 88);
    v46 = (char *)a2 + 64;
    v39 = (struct _tag_FW_RULE *)((char *)a2 + 88);
    v25 = (_DWORD *)((char *)a2 + 64);
    *((_OWORD *)a2 + 4) = 0;
    v26 = (struct _tag_FW_RULE *)((char *)a2 + 88);
    *(_OWORD *)((char *)a2 + 88) = 0;
    if ( v35 )
    {
      FwFree(*((_QWORD *)a2 + 32));
      v26 = v39;
      v24 = (struct _tag_FW_RULE *)((char *)a2 + 88);
      v25 = v46;
      v23 = (char *)a2 + 64;
      *((_DWORD *)a2 + 62) = 0;
      *((_QWORD *)a2 + 32) = 0;
    }
    v20 = v40;
    v21 = *(_WORD **)v38;
    v38 = *(_WORD **)v38;
  }
  v31 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
  {
LABEL_78:
    v15 = v28;
    goto LABEL_28;
  }
  v15 = v28;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v32 = 101;
    goto LABEL_59;
  }
LABEL_28:
  FwPolioEmptyWFAddresses((char *)a2 + 104);
  if ( v11 == 1 )
    goto LABEL_13;
LABEL_14:
  if ( v35 )
  {
    FwFree(*((_QWORD *)a2 + 32));
    *((_DWORD *)a2 + 62) = 0;
    *((_QWORD *)a2 + 32) = 0;
  }
  return v15;
}

```

## disassembly

```asm
0x18000b080  mov     r11, rsp
0x18000b083  push    rbx
0x18000b084  push    rbp
0x18000b085  push    rsi
0x18000b086  push    rdi
0x18000b087  push    r12
0x18000b089  push    r13
0x18000b08b  push    r14
0x18000b08d  push    r15
0x18000b08f  sub     rsp, 0C8h
0x18000b096  mov     rax, cs:__security_cookie
0x18000b09d  xor     rax, rsp
0x18000b0a0  mov     [rsp+108h+var_50], rax
0x18000b0a8  mov     rax, [rsp+108h+arg_20]
0x18000b0b0  xor     ebx, ebx
0x18000b0b2  mov     r15d, [rsp+108h+arg_40]
0x18000b0ba  mov     r12, r9
0x18000b0bd  mov     r13, [rsp+108h+arg_38]
0x18000b0c5  mov     rsi, rdx
0x18000b0c8  mov     [rsp+108h+var_78], rax
0x18000b0d0  mov     rax, [rsp+108h+arg_28]
0x18000b0d8  mov     [rsp+108h+var_80], rax
0x18000b0e0  mov     rax, [rsp+108h+arg_30]
0x18000b0e8  mov     [rsp+108h+var_88], rax
0x18000b0f0  mov     [rsp+108h+var_70], r8
0x18000b0f8  mov     [rsp+108h+var_A0], rcx
0x18000b0fd  mov     [r11-60h], ebx
0x18000b101  mov     [r11-58h], rbx
0x18000b105  mov     [rsp+108h+var_98], rbx
0x18000b10a  mov     [rsp+108h+var_90], rbx
0x18000b10f  mov     [rsp+108h+var_AC], ebx
0x18000b113  test    r15d, r15d
0x18000b116  jz      loc_18000B3B0
0x18000b11c  mov     edx, [rsi+28h]
0x18000b11f  lea     r8, [rsp+108h+var_60]
0x18000b127  mov     [rsp+108h+var_D8], rbx; __int64
0x18000b12c  lea     rcx, [rsi+68h]; struct _tag_FW_ADDRESSES *
0x18000b130  mov     ebp, 1
0x18000b135  xor     r9d, r9d
0x18000b138  mov     dword ptr [rsp+108h+var_E0], ebp; char
0x18000b13c  mov     [rsp+108h+var_E8], rbx; __int64
0x18000b141  call    ResolveAddresses
0x18000b146  mov     edi, eax
0x18000b148  test    eax, eax
0x18000b14a  jns     short loc_18000B187
0x18000b14c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b153  lea     rbx, WPP_GLOBAL_Control
0x18000b15a  cmp     rcx, rbx
0x18000b15d  jnz     loc_18000B3BA
0x18000b163  mov     rcx, [rsp+108h+var_50]
0x18000b16b  xor     rcx, rsp; StackCookie
0x18000b16e  call    __security_check_cookie
0x18000b173  add     rsp, 0C8h
0x18000b17a  pop     r15
0x18000b17c  pop     r14
0x18000b17e  pop     r13
0x18000b180  pop     r12
0x18000b182  pop     rdi
0x18000b183  pop     rsi
0x18000b184  pop     rbp
0x18000b185  pop     rbx
0x18000b186  retn
0x18000b187  cmp     [rsp+108h+var_60], ebx
0x18000b18e  jnz     loc_18000B3E1
0x18000b194  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b19b  mov     [rsp+108h+var_B4], ebx
0x18000b19f  lea     rbx, WPP_GLOBAL_Control
0x18000b1a6  test    byte ptr [rcx+1Ch], 4
0x18000b1aa  jnz     loc_18000B435
0x18000b1b0  mov     edx, [rsi+28h]
0x18000b1b3  lea     rax, [rsi+1E0h]
0x18000b1ba  mov     [rsp+108h+var_D8], rax; __int64
0x18000b1bf  lea     rcx, [rsi+0B0h]; struct _tag_FW_ADDRESSES *
0x18000b1c6  lea     rax, [rsp+108h+var_58]
0x18000b1ce  mov     dword ptr [rsp+108h+var_E0], ebp; char
0x18000b1d2  xor     r9d, r9d
0x18000b1d5  mov     [rsp+108h+var_E8], rax; __int64
0x18000b1da  lea     r8, [rsp+108h+var_60]
0x18000b1e2  call    ResolveAddresses
0x18000b1e7  mov     [rsp+108h+var_B8], eax
0x18000b1eb  mov     edi, eax
0x18000b1ed  test    eax, eax
0x18000b1ef  js      loc_18000B386
0x18000b1f5  cmp     [rsp+108h+var_60], 0
0x18000b1fd  jnz     loc_18000B2BE
0x18000b203  mov     ecx, [rsi+188h]
0x18000b209  test    ecx, ecx
0x18000b20b  jnz     loc_18000B306
0x18000b211  mov     r8, [rsp+108h+var_70]; struct _LIST_ENTRY *
0x18000b219  lea     rax, [rsp+108h+var_58]
0x18000b221  mov     rcx, [rsp+108h+var_A0]; this
0x18000b226  mov     r9, r12; struct _tag_FW_OBJECT_METADATA *
0x18000b229  mov     [rsp+108h+var_C0], rax; unsigned int *
0x18000b22e  mov     rdx, rsi; struct _tag_FW_RULE *
0x18000b231  mov     rax, [rsp+108h+var_88]
0x18000b239  mov     [rsp+108h+var_C8], r15d; unsigned int
0x18000b23e  mov     [rsp+108h+var_D0], r13; unsigned __int64 *
0x18000b243  mov     [rsp+108h+var_D8], rax; struct _DFW_IP_PORT_RANGE *
0x18000b248  mov     rax, [rsp+108h+var_80]
0x18000b250  mov     [rsp+108h+var_E0], rax; void **
0x18000b255  mov     rax, [rsp+108h+var_78]
0x18000b25d  mov     [rsp+108h+var_E8], rax; struct FW_PLUMBER_FILTER *
0x18000b262  call    ?HelperGenerateFwRule2@CDfwEngWriter@@AEAAJPEAU_tag_FW_RULE@@PEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@PEAUFW_PLUMBER_FILTER@@PEAPEAXPEAU_DFW_IP_PORT_RANGE@@PEA_KKPEAK@Z; CDfwEngWriter::HelperGenerateFwRule2(_tag_FW_RULE *,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *,FW_PLUMBER_FILTER *,void * *,_DFW_IP_PORT_RANGE *,unsigned __int64 *,ulong,ulong *)
0x18000b267  mov     edi, eax
0x18000b269  test    eax, eax
0x18000b26b  js      loc_18000B7C6
0x18000b271  mov     edx, ebp
0x18000b273  mov     rcx, r12
0x18000b276  call    cs:__imp_FwMetaDataAddEnforcementState
0x18000b27c  lea     rcx, [rsi+68h]
0x18000b280  call    cs:__imp_FwPolioEmptyWFAddresses
0x18000b286  lea     rcx, [rsi+0B0h]
0x18000b28d  call    cs:__imp_FwPolioEmptyWFAddresses
0x18000b293  cmp     [rsp+108h+var_B4], 0
0x18000b298  jz      short loc_18000B2FF
0x18000b29a  mov     rcx, [rsi+100h]
0x18000b2a1  call    cs:__imp_FwFree
0x18000b2a7  mov     dword ptr [rsi+0F8h], 0
0x18000b2b1  mov     qword ptr [rsi+100h], 0
0x18000b2bc  jmp     short loc_18000B2FF
0x18000b2be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2c5  cmp     rcx, rbx
0x18000b2c8  jz      short loc_18000B2D4
0x18000b2ca  test    byte ptr [rcx+1Ch], 4
0x18000b2ce  jnz     loc_18000B4A9
0x18000b2d4  mov     r8, [rsi+18h]
0x18000b2d8  mov     r9d, 3
0x18000b2de  mov     rdx, [rsi+10h]
0x18000b2e2  call    FwAuditLogEmptyResolution
0x18000b2e7  mov     edx, 7
0x18000b2ec  mov     rcx, r12
0x18000b2ef  call    cs:__imp_FwMetaDataAddEnforcementState
0x18000b2f5  lea     rcx, [rsi+68h]
0x18000b2f9  call    cs:__imp_FwPolioEmptyWFAddresses
0x18000b2ff  mov     eax, edi
0x18000b301  jmp     loc_18000B163
0x18000b306  mov     rdx, [rsi+178h]
0x18000b30d  lea     r8, [rsp+108h+var_98]
0x18000b312  call    FwGetTuplePerPackageCollection
0x18000b317  mov     rax, [rsp+108h+var_98]
0x18000b31c  test    rax, rax
0x18000b31f  jz      short loc_18000B32E
0x18000b321  mov     rcx, [rax]
0x18000b324  mov     [rsp+108h+var_A8], rcx
0x18000b329  cmp     rcx, rax
0x18000b32c  jnz     short loc_18000B34E
0x18000b32e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b335  cmp     rcx, rbx
0x18000b338  jz      short loc_18000B344
0x18000b33a  test    byte ptr [rcx+1Ch], 4
0x18000b33e  jnz     loc_18000B7AC
0x18000b344  mov     edx, 17h
0x18000b349  jmp     loc_18000B273
0x18000b34e  mov     rdi, [rsp+108h+var_A0]
0x18000b353  lea     r8, [rsi+40h]
0x18000b357  lea     rdx, [rsi+58h]
0x18000b35b  mov     [rsp+108h+var_B0], 0
0x18000b363  mov     r10, r8
0x18000b366  mov     r9, rdx
0x18000b369  cmp     rcx, rax
0x18000b36c  jnz     loc_18000B4C3
0x18000b372  cmp     [rsp+108h+var_B0], 0
0x18000b377  jz      loc_18000B764
0x18000b37d  mov     edi, [rsp+108h+var_B8]
0x18000b381  jmp     loc_18000B271
0x18000b386  xor     ebp, ebp
0x18000b388  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b38f  cmp     rcx, rbx
0x18000b392  jnz     loc_18000B478
0x18000b398  lea     rcx, [rsi+68h]
0x18000b39c  call    cs:__imp_FwPolioEmptyWFAddresses
0x18000b3a2  cmp     ebp, 1
0x18000b3a5  jnz     loc_18000B293
0x18000b3ab  jmp     loc_18000B286
0x18000b3b0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b3b5  jmp     loc_18000B11C
0x18000b3ba  test    [rcx+1Ch], bpl
0x18000b3be  jz      loc_18000B163
0x18000b3c4  mov     rcx, [rcx+10h]
0x18000b3c8  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x18000b3cf  mov     edx, 5Ch ; '\'
0x18000b3d4  mov     r9d, edi
0x18000b3d7  call    WPP_SF_d
0x18000b3dc  jmp     loc_18000B2FF
0x18000b3e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3e8  lea     rbx, WPP_GLOBAL_Control
0x18000b3ef  cmp     rcx, rbx
0x18000b3f2  jz      short loc_18000B40F
0x18000b3f4  test    byte ptr [rcx+1Ch], 4
0x18000b3f8  jz      short loc_18000B40F
0x18000b3fa  mov     rcx, [rcx+10h]
0x18000b3fe  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x18000b405  mov     edx, 5Dh ; ']'
0x18000b40a  call    WPP_SF_
0x18000b40f  mov     r8, [rsi+18h]
0x18000b413  mov     r9d, 2
0x18000b419  mov     rdx, [rsi+10h]
0x18000b41d  call    FwAuditLogEmptyResolution
0x18000b422  mov     edx, 6
0x18000b427  mov     rcx, r12
0x18000b42a  call    cs:__imp_FwMetaDataAddEnforcementState
0x18000b430  jmp     loc_18000B2FF
0x18000b435  cmp     rcx, rbx
0x18000b438  jz      loc_18000B1B0
0x18000b43e  mov     eax, [rsi+0D8h]
0x18000b444  mov     r9, [rsi+18h]
0x18000b448  mov     rcx, [rcx+10h]
0x18000b44c  mov     dword ptr [rsp+108h+var_D0], eax
0x18000b450  mov     eax, [rsi+0E8h]
0x18000b456  mov     dword ptr [rsp+108h+var_D8], eax
0x18000b45a  mov     eax, [rsi+0B8h]
0x18000b460  mov     dword ptr [rsp+108h+var_E0], eax
0x18000b464  mov     eax, [rsi+0C8h]
0x18000b46a  mov     dword ptr [rsp+108h+var_E8], eax
0x18000b46e  call    WPP_SF_Sdddd
0x18000b473  jmp     loc_18000B1B0
0x18000b478  test    byte ptr [rcx+1Ch], 1
0x18000b47c  jz      loc_18000B398
0x18000b482  mov     rcx, [rcx+10h]
0x18000b486  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x18000b48d  mov     edx, 5Fh ; '_'
0x18000b492  mov     r9d, edi
0x18000b495  call    WPP_SF_d
0x18000b49a  lea     rcx, [rsi+68h]
0x18000b49e  call    cs:__imp_FwPolioEmptyWFAddresses
0x18000b4a4  jmp     loc_18000B2FF
0x18000b4a9  mov     rcx, [rcx+10h]
0x18000b4ad  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x18000b4b4  mov     edx, 60h ; '`'
0x18000b4b9  call    WPP_SF_
0x18000b4be  jmp     loc_18000B2D4
0x18000b4c3  mov     [rsp+108h+var_60], 0
0x18000b4ce  movzx   eax, word ptr [rcx+14h]
0x18000b4d2  mov     [rsi+30h], ax
0x18000b4d6  lea     rax, [rcx+16h]
0x18000b4da  cmp     word ptr [rax], 0
0x18000b4de  mov     [rsp+108h+var_B4], 0
0x18000b4e6  jnz     short loc_18000B4F2
0x18000b4e8  cmp     word ptr [rcx+18h], 0
0x18000b4ed  mov     r10, r8
0x18000b4f0  jz      short loc_18000B4FC
0x18000b4f2  mov     [r10], ebp
0x18000b4f5  mov     r9, rdx
0x18000b4f8  mov     [rsi+48h], rax
0x18000b4fc  cmp     word ptr [rcx+1Ah], 0
0x18000b501  lea     rax, [rcx+1Ah]
0x18000b505  jnz     short loc_18000B511
0x18000b507  cmp     word ptr [rcx+1Ch], 0
0x18000b50c  mov     r9, rdx
0x18000b50f  jz      short loc_18000B518
0x18000b511  mov     [r9], ebp
0x18000b514  mov     [rsi+60h], rax
0x18000b518  add     rcx, 20h ; ' '
0x18000b51c  lea     rdx, [rsi+68h]
0x18000b520  call    cs:__imp_FwPolioCopyWFAddressesContents
0x18000b526  test    eax, eax
0x18000b528  js      loc_18000B747
0x18000b52e  mov     rcx, [rsp+108h+var_A8]
0x18000b533  lea     rdx, [rsi+0B0h]
0x18000b53a  add     rcx, 68h ; 'h'
0x18000b53e  call    cs:__imp_FwPolioCopyWFAddressesContents
0x18000b544  mov     [rsp+108h+var_B8], eax
0x18000b548  test    eax, eax
0x18000b54a  js      loc_18000B721
0x18000b550  mov     rax, [rsp+108h+var_A8]
0x18000b555  lea     rcx, [rax+0B0h]
0x18000b55c  cmp     dword ptr [rcx], 0
0x18000b55f  jbe     short loc_18000B59A
0x18000b561  lea     rax, [rsp+108h+var_60]
0x18000b569  xor     edx, edx
0x18000b56b  lea     r9, [rsp+108h+var_AC]
0x18000b570  mov     [rsp+108h+var_E8], rax
0x18000b575  lea     r8, [rsp+108h+var_90]
0x18000b57a  call    ResolveInterfaces
0x18000b57f  mov     [rsp+108h+var_B8], eax
0x18000b583  test    eax, eax
0x18000b585  js      loc_18000B6B4
0x18000b58b  mov     rax, [rsp+108h+var_90]
0x18000b590  mov     ecx, [rsp+108h+var_AC]
0x18000b594  mov     [rsp+108h+var_B4], ebp
0x18000b598  jmp     short loc_18000B5B3
0x18000b59a  mov     ecx, [rax+0C0h]
0x18000b5a0  test    ecx, ecx
0x18000b5a2  jz      short loc_18000B5AD
0x18000b5a4  mov     rax, [rax+0C8h]
0x18000b5ab  jmp     short loc_18000B5B3
0x18000b5ad  mov     ecx, r15d
0x18000b5b0  mov     rax, r13
0x18000b5b3  cmp     [rsp+108h+var_60], 0
0x18000b5bb  jnz     short loc_18000B620
0x18000b5bd  mov     r8, [rsp+108h+var_70]; struct _LIST_ENTRY *
0x18000b5c5  lea     rdx, [rsp+108h+var_58]
0x18000b5cd  mov     [rsp+108h+var_C0], rdx; unsigned int *
0x18000b5d2  mov     r9, r12; struct _tag_FW_OBJECT_METADATA *
0x18000b5d5  mov     [rsp+108h+var_C8], ecx; unsigned int
0x18000b5d9  mov     rdx, rsi; struct _tag_FW_RULE *
0x18000b5dc  mov     [rsp+108h+var_D0], rax; unsigned __int64 *
0x18000b5e1  mov     rcx, rdi; this
0x18000b5e4  mov     rax, [rsp+108h+var_88]
0x18000b5ec  mov     [rsp+108h+var_D8], rax; struct _DFW_IP_PORT_RANGE *
  ... truncated ...
```
