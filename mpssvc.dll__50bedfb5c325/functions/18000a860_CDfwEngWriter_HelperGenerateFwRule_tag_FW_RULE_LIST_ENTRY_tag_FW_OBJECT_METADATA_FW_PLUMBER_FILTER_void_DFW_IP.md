# CDfwEngWriter::HelperGenerateFwRule(_tag_FW_RULE *,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *,FW_PLUMBER_FILTER *,void * *,_DFW_IP_PORT_RANGE *,unsigned __int64 *,ulong)

- ea: `0x18000a860`
- end: `0x18000b01d`
- name: `?HelperGenerateFwRule@CDfwEngWriter@@AEAAJPEAU_tag_FW_RULE@@PEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@PEAUFW_PLUMBER_FILTER@@PEAPEAXPEAU_DFW_IP_PORT_RANGE@@PEA_KK@Z`
- size: `1981`
- prototype: `int(CDfwEngWriter *__hidden this, struct _tag_FW_RULE *, struct _LIST_ENTRY *, struct _tag_FW_OBJECT_METADATA *, struct FW_PLUMBER_FILTER *, void **, struct _DFW_IP_PORT_RANGE *, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b8b0`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x18000a860`
- `0x18000b030`
- `0x18000c980`
- `0x1800192e0`
- `0x18002cf08`
- `0x18003e420`
- `0x18003f928`
- `0x18005f584`
- `0x1800729c0`

## import_xrefs

- `fwbase!FwMetaDataAddEnforcementState` at `0x18000aa57`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000aae8`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000ac35`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000afb8`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000aa57`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000aae8`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000ac35`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18000afb8`
- `fwbase!FwFree` at `0x18000aa94`
- `fwbase!FwFree` at `0x18000ae8c`
- `fwbase!FwFree` at `0x18000aa94`
- `fwbase!FwFree` at `0x18000ae8c`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000aa67`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000aa7a`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000aaf8`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000aba1`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000ae37`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000ae4a`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000afc8`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000aa67`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000aa7a`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000aaf8`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000aba1`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000ae37`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000ae4a`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000afc8`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x18000ad27`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x18000ad4b`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x18000ad27`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x18000ad4b`

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
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
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
        WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
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
      WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
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
        WPP_SF_d(*(_QWORD *)(v31 + 16), v32, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids, v33);
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
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 97, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
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
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 102, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
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
0x18000a860  mov     r11, rsp
0x18000a863  push    rbx
0x18000a864  push    rbp
0x18000a865  push    rsi
0x18000a866  push    rdi
0x18000a867  push    r12
0x18000a869  push    r13
0x18000a86b  push    r14
0x18000a86d  push    r15
0x18000a86f  sub     rsp, 0C8h
0x18000a876  mov     rax, cs:__security_cookie
0x18000a87d  xor     rax, rsp
0x18000a880  mov     [rsp+108h+var_50], rax
0x18000a888  mov     rax, [rsp+108h+arg_20]
0x18000a890  xor     ebx, ebx
0x18000a892  mov     r15d, [rsp+108h+arg_40]
0x18000a89a  mov     r12, r9
0x18000a89d  mov     r13, [rsp+108h+arg_38]
0x18000a8a5  mov     rsi, rdx
0x18000a8a8  mov     [rsp+108h+var_78], rax
0x18000a8b0  mov     rax, [rsp+108h+arg_28]
0x18000a8b8  mov     [rsp+108h+var_80], rax
0x18000a8c0  mov     rax, [rsp+108h+arg_30]
0x18000a8c8  mov     [rsp+108h+var_88], rax
0x18000a8d0  mov     [rsp+108h+var_70], r8
0x18000a8d8  mov     [rsp+108h+var_A0], rcx
0x18000a8dd  mov     [r11-60h], ebx
0x18000a8e1  mov     [r11-58h], rbx
0x18000a8e5  mov     [rsp+108h+var_98], rbx
0x18000a8ea  mov     [rsp+108h+var_90], rbx
0x18000a8ef  mov     [rsp+108h+var_AC], ebx
0x18000a8f3  test    r15d, r15d
0x18000a8f6  jz      loc_18000ABBB
0x18000a8fc  mov     edx, [rsi+28h]
0x18000a8ff  lea     r8, [rsp+108h+var_60]
0x18000a907  mov     [rsp+108h+var_D8], rbx; __int64
0x18000a90c  lea     rcx, [rsi+68h]; struct _tag_FW_ADDRESSES *
0x18000a910  mov     ebp, 1
0x18000a915  xor     r9d, r9d
0x18000a918  mov     dword ptr [rsp+108h+var_E0], ebp; char
0x18000a91c  mov     [rsp+108h+var_E8], rbx; __int64
0x18000a921  call    ResolveAddresses
0x18000a926  mov     edi, eax
0x18000a928  test    eax, eax
0x18000a92a  jns     short loc_18000A968
0x18000a92c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a933  lea     rbx, WPP_GLOBAL_Control
0x18000a93a  cmp     rcx, rbx
0x18000a93d  jnz     loc_18000ABC5
0x18000a943  mov     rcx, [rsp+108h+var_50]
0x18000a94b  xor     rcx, rsp; StackCookie
0x18000a94e  call    __security_check_cookie
0x18000a953  add     rsp, 0C8h
0x18000a95a  pop     r15
0x18000a95c  pop     r14
0x18000a95e  pop     r13
0x18000a960  pop     r12
0x18000a962  pop     rdi
0x18000a963  pop     rsi
0x18000a964  pop     rbp
0x18000a965  pop     rbx
0x18000a966  retn
0x18000a968  cmp     [rsp+108h+var_60], ebx
0x18000a96f  jnz     loc_18000ABEC
0x18000a975  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a97c  mov     [rsp+108h+var_B4], ebx
0x18000a980  lea     rbx, WPP_GLOBAL_Control
0x18000a987  test    byte ptr [rcx+1Ch], 4
0x18000a98b  jnz     loc_18000AC46
0x18000a991  mov     edx, [rsi+28h]
0x18000a994  lea     rax, [rsi+1E0h]
0x18000a99b  mov     [rsp+108h+var_D8], rax; __int64
0x18000a9a0  lea     rcx, [rsi+0B0h]; struct _tag_FW_ADDRESSES *
0x18000a9a7  lea     rax, [rsp+108h+var_58]
0x18000a9af  mov     dword ptr [rsp+108h+var_E0], ebp; char
0x18000a9b3  xor     r9d, r9d
0x18000a9b6  mov     [rsp+108h+var_E8], rax; __int64
0x18000a9bb  lea     r8, [rsp+108h+var_60]
0x18000a9c3  call    ResolveAddresses
0x18000a9c8  mov     [rsp+108h+var_B8], eax
0x18000a9cc  mov     edi, eax
0x18000a9ce  test    eax, eax
0x18000a9d0  js      loc_18000AB8B
0x18000a9d6  cmp     [rsp+108h+var_60], 0
0x18000a9de  jnz     loc_18000AAB7
0x18000a9e4  mov     ecx, [rsi+188h]
0x18000a9ea  test    ecx, ecx
0x18000a9ec  jnz     loc_18000AB0B
0x18000a9f2  mov     r8, [rsp+108h+var_70]; struct _LIST_ENTRY *
0x18000a9fa  lea     rax, [rsp+108h+var_58]
0x18000aa02  mov     rcx, [rsp+108h+var_A0]; this
0x18000aa07  mov     r9, r12; struct _tag_FW_OBJECT_METADATA *
0x18000aa0a  mov     [rsp+108h+var_C0], rax; unsigned int *
0x18000aa0f  mov     rdx, rsi; struct _tag_FW_RULE *
0x18000aa12  mov     rax, [rsp+108h+var_88]
0x18000aa1a  mov     [rsp+108h+var_C8], r15d; unsigned int
0x18000aa1f  mov     [rsp+108h+var_D0], r13; unsigned __int64 *
0x18000aa24  mov     [rsp+108h+var_D8], rax; struct _DFW_IP_PORT_RANGE *
0x18000aa29  mov     rax, [rsp+108h+var_80]
0x18000aa31  mov     [rsp+108h+var_E0], rax; void **
0x18000aa36  mov     rax, [rsp+108h+var_78]
0x18000aa3e  mov     [rsp+108h+var_E8], rax; struct FW_PLUMBER_FILTER *
0x18000aa43  call    ?HelperGenerateFwRule2@CDfwEngWriter@@AEAAJPEAU_tag_FW_RULE@@PEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@PEAUFW_PLUMBER_FILTER@@PEAPEAXPEAU_DFW_IP_PORT_RANGE@@PEA_KKPEAK@Z; CDfwEngWriter::HelperGenerateFwRule2(_tag_FW_RULE *,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *,FW_PLUMBER_FILTER *,void * *,_DFW_IP_PORT_RANGE *,unsigned __int64 *,ulong,ulong *)
0x18000aa48  mov     edi, eax
0x18000aa4a  test    eax, eax
0x18000aa4c  js      loc_18000AFF7
0x18000aa52  mov     edx, ebp
0x18000aa54  mov     rcx, r12
0x18000aa57  call    cs:__imp_FwMetaDataAddEnforcementState
0x18000aa5e  nop     dword ptr [rax+rax+00h]
0x18000aa63  lea     rcx, [rsi+68h]
0x18000aa67  call    cs:__imp_FwPolioEmptyWFAddresses
0x18000aa6e  nop     dword ptr [rax+rax+00h]
0x18000aa73  lea     rcx, [rsi+0B0h]
0x18000aa7a  call    cs:__imp_FwPolioEmptyWFAddresses
0x18000aa81  nop     dword ptr [rax+rax+00h]
0x18000aa86  cmp     [rsp+108h+var_B4], 0
0x18000aa8b  jz      short loc_18000AB04
0x18000aa8d  mov     rcx, [rsi+100h]
0x18000aa94  call    cs:__imp_FwFree
0x18000aa9b  nop     dword ptr [rax+rax+00h]
0x18000aaa0  mov     dword ptr [rsi+0F8h], 0
0x18000aaaa  mov     qword ptr [rsi+100h], 0
0x18000aab5  jmp     short loc_18000AB04
0x18000aab7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aabe  cmp     rcx, rbx
0x18000aac1  jz      short loc_18000AACD
0x18000aac3  test    byte ptr [rcx+1Ch], 4
0x18000aac7  jnz     loc_18000ACB0
0x18000aacd  mov     r8, [rsi+18h]
0x18000aad1  mov     r9d, 3
0x18000aad7  mov     rdx, [rsi+10h]
0x18000aadb  call    FwAuditLogEmptyResolution
0x18000aae0  mov     edx, 7
0x18000aae5  mov     rcx, r12
0x18000aae8  call    cs:__imp_FwMetaDataAddEnforcementState
0x18000aaef  nop     dword ptr [rax+rax+00h]
0x18000aaf4  lea     rcx, [rsi+68h]
0x18000aaf8  call    cs:__imp_FwPolioEmptyWFAddresses
0x18000aaff  nop     dword ptr [rax+rax+00h]
0x18000ab04  mov     eax, edi
0x18000ab06  jmp     loc_18000A943
0x18000ab0b  mov     rdx, [rsi+178h]
0x18000ab12  lea     r8, [rsp+108h+var_98]
0x18000ab17  call    FwGetTuplePerPackageCollection
0x18000ab1c  mov     rax, [rsp+108h+var_98]
0x18000ab21  test    rax, rax
0x18000ab24  jz      short loc_18000AB33
0x18000ab26  mov     rcx, [rax]
0x18000ab29  mov     [rsp+108h+var_A8], rcx
0x18000ab2e  cmp     rcx, rax
0x18000ab31  jnz     short loc_18000AB53
0x18000ab33  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab3a  cmp     rcx, rbx
0x18000ab3d  jz      short loc_18000AB49
0x18000ab3f  test    byte ptr [rcx+1Ch], 4
0x18000ab43  jnz     loc_18000AFDD
0x18000ab49  mov     edx, 17h
0x18000ab4e  jmp     loc_18000AA54
0x18000ab53  mov     rdi, [rsp+108h+var_A0]
0x18000ab58  lea     r8, [rsi+40h]
0x18000ab5c  lea     rdx, [rsi+58h]
0x18000ab60  mov     [rsp+108h+var_B0], 0
0x18000ab68  mov     r10, r8
0x18000ab6b  mov     r9, rdx
0x18000ab6e  cmp     rcx, rax
0x18000ab71  jnz     loc_18000ACCA
0x18000ab77  cmp     [rsp+108h+var_B0], 0
0x18000ab7c  jz      loc_18000AF89
0x18000ab82  mov     edi, [rsp+108h+var_B8]
0x18000ab86  jmp     loc_18000AA52
0x18000ab8b  xor     ebp, ebp
0x18000ab8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab94  cmp     rcx, rbx
0x18000ab97  jnz     loc_18000AC89
0x18000ab9d  lea     rcx, [rsi+68h]
0x18000aba1  call    cs:__imp_FwPolioEmptyWFAddresses
0x18000aba8  nop     dword ptr [rax+rax+00h]
0x18000abad  cmp     ebp, 1
0x18000abb0  jnz     loc_18000AA86
0x18000abb6  jmp     loc_18000AA73
0x18000abbb  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "dwNumIndexes != 0")
0x18000abc0  jmp     loc_18000A8FC
0x18000abc5  test    [rcx+1Ch], bpl
0x18000abc9  jz      loc_18000A943
0x18000abcf  mov     rcx, [rcx+10h]
0x18000abd3  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x18000abda  mov     edx, 5Ch ; '\'
0x18000abdf  mov     r9d, edi
0x18000abe2  call    WPP_SF_d
0x18000abe7  jmp     loc_18000AB04
0x18000abec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abf3  lea     rbx, WPP_GLOBAL_Control
0x18000abfa  cmp     rcx, rbx
0x18000abfd  jz      short loc_18000AC1A
0x18000abff  test    byte ptr [rcx+1Ch], 4
0x18000ac03  jz      short loc_18000AC1A
0x18000ac05  mov     rcx, [rcx+10h]
0x18000ac09  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x18000ac10  mov     edx, 5Dh ; ']'
0x18000ac15  call    WPP_SF_
0x18000ac1a  mov     r8, [rsi+18h]
0x18000ac1e  mov     r9d, 2
0x18000ac24  mov     rdx, [rsi+10h]
0x18000ac28  call    FwAuditLogEmptyResolution
0x18000ac2d  mov     edx, 6
0x18000ac32  mov     rcx, r12
0x18000ac35  call    cs:__imp_FwMetaDataAddEnforcementState
0x18000ac3c  nop     dword ptr [rax+rax+00h]
0x18000ac41  jmp     loc_18000AB04
0x18000ac46  cmp     rcx, rbx
0x18000ac49  jz      loc_18000A991
0x18000ac4f  mov     eax, [rsi+0D8h]
0x18000ac55  mov     r9, [rsi+18h]
0x18000ac59  mov     rcx, [rcx+10h]
0x18000ac5d  mov     dword ptr [rsp+108h+var_D0], eax
0x18000ac61  mov     eax, [rsi+0E8h]
0x18000ac67  mov     dword ptr [rsp+108h+var_D8], eax
0x18000ac6b  mov     eax, [rsi+0B8h]
0x18000ac71  mov     dword ptr [rsp+108h+var_E0], eax
0x18000ac75  mov     eax, [rsi+0C8h]
0x18000ac7b  mov     dword ptr [rsp+108h+var_E8], eax
0x18000ac7f  call    WPP_SF_Sdddd
0x18000ac84  jmp     loc_18000A991
0x18000ac89  test    byte ptr [rcx+1Ch], 1
0x18000ac8d  jz      loc_18000AB9D
0x18000ac93  mov     rcx, [rcx+10h]
0x18000ac97  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x18000ac9e  mov     edx, 5Fh ; '_'
0x18000aca3  mov     r9d, edi
0x18000aca6  call    WPP_SF_d
0x18000acab  jmp     loc_18000AAF4
0x18000acb0  mov     rcx, [rcx+10h]
0x18000acb4  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x18000acbb  mov     edx, 60h ; '`'
0x18000acc0  call    WPP_SF_
0x18000acc5  jmp     loc_18000AACD
0x18000acca  mov     [rsp+108h+var_60], 0
0x18000acd5  movzx   eax, word ptr [rcx+14h]
0x18000acd9  mov     [rsi+30h], ax
0x18000acdd  lea     rax, [rcx+16h]
0x18000ace1  cmp     word ptr [rax], 0
0x18000ace5  mov     [rsp+108h+var_B4], 0
0x18000aced  jnz     short loc_18000ACF9
0x18000acef  cmp     word ptr [rcx+18h], 0
0x18000acf4  mov     r10, r8
0x18000acf7  jz      short loc_18000AD03
0x18000acf9  mov     [r10], ebp
0x18000acfc  mov     r9, rdx
0x18000acff  mov     [rsi+48h], rax
0x18000ad03  cmp     word ptr [rcx+1Ah], 0
0x18000ad08  lea     rax, [rcx+1Ah]
0x18000ad0c  jnz     short loc_18000AD18
0x18000ad0e  cmp     word ptr [rcx+1Ch], 0
0x18000ad13  mov     r9, rdx
0x18000ad16  jz      short loc_18000AD1F
0x18000ad18  mov     [r9], ebp
0x18000ad1b  mov     [rsi+60h], rax
0x18000ad1f  add     rcx, 20h ; ' '
0x18000ad23  lea     rdx, [rsi+68h]
0x18000ad27  call    cs:__imp_FwPolioCopyWFAddressesContents
0x18000ad2e  nop     dword ptr [rax+rax+00h]
0x18000ad33  test    eax, eax
0x18000ad35  js      loc_18000AF6C
0x18000ad3b  mov     rcx, [rsp+108h+var_A8]
0x18000ad40  lea     rdx, [rsi+0B0h]
0x18000ad47  add     rcx, 68h ; 'h'
0x18000ad4b  call    cs:__imp_FwPolioCopyWFAddressesContents
0x18000ad52  nop     dword ptr [rax+rax+00h]
0x18000ad57  mov     [rsp+108h+var_B8], eax
0x18000ad5b  test    eax, eax
0x18000ad5d  js      loc_18000AF46
0x18000ad63  mov     rax, [rsp+108h+var_A8]
0x18000ad68  lea     rcx, [rax+0B0h]
0x18000ad6f  cmp     dword ptr [rcx], 0
0x18000ad72  jbe     short loc_18000ADAD
0x18000ad74  lea     rax, [rsp+108h+var_60]
0x18000ad7c  xor     edx, edx
0x18000ad7e  lea     r9, [rsp+108h+var_AC]
0x18000ad83  mov     [rsp+108h+var_E8], rax
0x18000ad88  lea     r8, [rsp+108h+var_90]
0x18000ad8d  call    ResolveInterfaces
0x18000ad92  mov     [rsp+108h+var_B8], eax
0x18000ad96  test    eax, eax
0x18000ad98  js      loc_18000AED9
0x18000ad9e  mov     rax, [rsp+108h+var_90]
0x18000ada3  mov     ecx, [rsp+108h+var_AC]
0x18000ada7  mov     [rsp+108h+var_B4], ebp
0x18000adab  jmp     short loc_18000ADC6
0x18000adad  mov     ecx, [rax+0C0h]
0x18000adb3  test    ecx, ecx
0x18000adb5  jz      short loc_18000ADC0
0x18000adb7  mov     rax, [rax+0C8h]
0x18000adbe  jmp     short loc_18000ADC6
0x18000adc0  mov     ecx, r15d
0x18000adc3  mov     rax, r13
0x18000adc6  cmp     [rsp+108h+var_60], 0
0x18000adce  jnz     short loc_18000AE33
0x18000add0  mov     r8, [rsp+108h+var_70]; struct _LIST_ENTRY *
0x18000add8  lea     rdx, [rsp+108h+var_58]
  ... truncated ...
```
