# FwBatchUpdateRequestWriteRule(_tag_FW_BATCH_UPDATE_RECORD *)

- ea: `0x180065e90`
- end: `0x180066494`
- name: `?FwBatchUpdateRequestWriteRule@@YAJPEAU_tag_FW_BATCH_UPDATE_RECORD@@@Z`
- size: `1540`
- prototype: `__int64 __fastcall(struct _tag_FW_BATCH_UPDATE_RECORD *)`
- caller_count: `1`
- callee_count: `29`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800272c0`

## callees

- `0x180001bf0`
- `0x180002b90`
- `0x1800089bc`
- `0x18000a710`
- `0x180024de0`
- `0x180024e50`
- `0x180025980`
- `0x180025ce0`
- `0x180026210`
- `0x180032430`
- `0x180032580`
- `0x180032aa0`
- `0x180032d00`
- `0x180032f50`
- `0x18003cc74`
- `0x1800557b0`
- `0x18005e394`
- `0x180065e90`
- `0x18006c0c0`
- `0x1800729c0`
- `0x180073488`
- `0x18008bccc`
- `0x18008ed84`
- `0x1800ab1a0`
- `0x1800ab1e0`
- `0x1800ab390`
- `0x1800ab3d0`
- `0x1800ab500`
- `0x1800ec010`

## import_xrefs

- `fwbase!FwMarshalledMetaDataCopy` at `0x18006615d`
- `fwbase!FwMarshalledMetaDataCopy` at `0x180066171`
- `fwbase!FwMarshalledMetaDataCopy` at `0x180066186`
- `fwbase!FwMarshalledMetaDataCopy` at `0x18006615d`
- `fwbase!FwMarshalledMetaDataCopy` at `0x180066171`
- `fwbase!FwMarshalledMetaDataCopy` at `0x180066186`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180066112`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180066112`
- `fwbase!FwMarshalledMetaDataInitialize` at `0x180065edc`
- `fwbase!FwMarshalledMetaDataInitialize` at `0x180065edc`

## pseudocode

```c
__int64 __fastcall FwBatchUpdateRequestWriteRule(struct _tag_FW_BATCH_UPDATE_RECORD *a1)
{
  int v2; // r12d
  __int64 v3; // r13
  unsigned int v4; // r8d
  int v5; // r9d
  __int64 *v6; // r15
  int *v7; // rbx
  GUID *v8; // rcx
  int v9; // ecx
  __int64 *v10; // r13
  __int64 *v11; // rax
  int v12; // edx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r14
  __int64 v18; // rdi
  __int64 v19; // rbx
  int v20; // ecx
  int v21; // eax
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // r14
  _QWORD *v25; // rcx
  _QWORD *v26; // rax
  _QWORD *v27; // rcx
  __int64 v28; // r14
  _QWORD *v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  _QWORD *v32; // rdx
  _QWORD *v33; // rax
  __int64 *v34; // rcx
  bool v35; // zf
  __int64 v36; // rdx
  int v37; // ecx
  __int64 v38; // rax
  __int64 v39; // rdx
  _QWORD *v40; // rcx
  unsigned int v41; // eax
  __int64 v42; // rcx
  unsigned int v43; // edx
  int v45; // [rsp+40h] [rbp-C0h] BYREF
  int v46; // [rsp+44h] [rbp-BCh] BYREF
  int v47; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v50[216]; // [rsp+68h] [rbp-98h] BYREF

  v2 = 0;
  v49 = 0;
  v3 = 0;
  memset_0(v50, 0, sizeof(v50));
  FwMarshalledMetaDataInitialize(&v49);
  v6 = (__int64 *)*((_QWORD *)a1 + 5);
  if ( *((_DWORD *)a1 + 14) != 1 )
    goto LABEL_36;
  v7 = (int *)((char *)a1 + 16);
  if ( ((*((_DWORD *)a1 + 4) - 1) & 0xFFFFFFFB) != 0 )
  {
    FwBatchUpdateDeleteFilters((struct _LIST_ENTRY *)(v6 + 33), 0, 0);
    v4 = *((_DWORD *)a1 + 15);
    if ( v4 )
    {
      FwBatchUpdateDeleteFilters((struct _LIST_ENTRY *)(v6 + 35), (struct _tag_FW_MARSHALLED_METADATA *)(v6 + 5), v4);
    }
    else
    {
      v8 = (GUID *)(*v6 + 460);
      if ( *(_QWORD *)&GUID_NULL.Data1 != *(_QWORD *)&v8->Data1 || *(_QWORD *)GUID_NULL.Data4 != *(_QWORD *)(*v6 + 468) )
        FwPlumberDeleteFilterOriginProviderContext(v8);
    }
  }
  v9 = *v7;
  if ( (unsigned int)(*v7 - 4) <= 1 )
  {
LABEL_36:
    v17 = *((_QWORD *)a1 + 3);
    v18 = 0;
    if ( *((_DWORD *)a1 + 14) == 1 )
    {
      v19 = *((_QWORD *)a1 + 5);
      FwSwapListHeads((struct _LIST_ENTRY *)((char *)a1 + 296), (struct _LIST_ENTRY *)(v19 + 264));
      FwSwapListHeads((struct _LIST_ENTRY *)((char *)a1 + 312), (struct _LIST_ENTRY *)(v19 + 280));
      FwMarshalledMetaDataCopy((char *)a1 + 72, &v49);
      FwMarshalledMetaDataCopy(v19 + 40, (char *)a1 + 72);
      FwMarshalledMetaDataCopy(&v49, v19 + 40);
      v18 = v19;
    }
    v7 = (int *)((char *)a1 + 16);
    v20 = *((_DWORD *)a1 + 4);
    if ( v20 == 1 )
    {
      v21 = *((_DWORD *)a1 + 15);
      if ( *((_DWORD *)a1 + 14) == 1 )
      {
        switch ( v21 )
        {
          case 0:
            v22 = *(_QWORD **)(v17 + 8);
            if ( *v22 == v17 )
            {
              v23 = (_QWORD *)*((_QWORD *)a1 + 5);
              v23[3] = v22;
              v23 += 2;
              *v23 = v17;
              *v22 = v23;
              *(_QWORD *)(v17 + 8) = v23;
              FwIncreaseRuleCount(*((unsigned int *)a1 + 8), *(unsigned int *)(*v6 + 40));
              break;
            }
LABEL_86:
            __fastfail(3u);
          case 1:
            if ( *((_DWORD *)a1 + 17) )
              v24 = v17 + 72;
            else
              v24 = v17 + 24;
            v25 = *(_QWORD **)(v24 + 8);
            if ( *v25 != v24 )
              goto LABEL_86;
            v26 = (_QWORD *)(*((_QWORD *)a1 + 5) + 16LL);
            *v26 = v24;
            v26[1] = v25;
            *v25 = v26;
            *(_QWORD *)(v24 + 8) = v26;
            *(_DWORD *)(*((_QWORD *)a1 + 5) + 32LL) = *((_DWORD *)a1 + 17);
            break;
          case 2:
            v27 = *(_QWORD **)(v17 + 56);
            v28 = v17 + 48;
            if ( *v27 != v28 )
              goto LABEL_86;
            v29 = (_QWORD *)(*((_QWORD *)a1 + 5) + 16LL);
            v29[1] = v27;
            *v29 = v28;
            *v27 = v29;
            *(_QWORD *)(v28 + 8) = v29;
            break;
        }
      }
      else
      {
        if ( v21 )
        {
          if ( v21 != 1 )
            goto LABEL_74;
          v30 = *((int *)a1 + 16) + 7LL;
        }
        else
        {
          v30 = *((int *)a1 + 16) + 4LL;
        }
        v31 = v17 + 24 * v30;
        v32 = *(_QWORD **)(v31 + 8);
        if ( *v32 != v31 )
          goto LABEL_86;
        v33 = (_QWORD *)(*((_QWORD *)a1 + 5) + 16LL);
        *v33 = v31;
        v33[1] = v32;
        *v32 = v33;
        *(_QWORD *)(v31 + 8) = v33;
      }
    }
    else if ( (unsigned int)(v20 - 4) <= 1 )
    {
      v38 = *((_QWORD *)a1 + 5) + 16LL;
      v39 = *(_QWORD *)v38;
      if ( *(_QWORD *)(*(_QWORD *)v38 + 8LL) != v38 )
        goto LABEL_86;
      v40 = *(_QWORD **)(*((_QWORD *)a1 + 5) + 24LL);
      if ( *v40 != v38 )
        goto LABEL_86;
      *v40 = v39;
      *(_QWORD *)(v39 + 8) = v40;
      if ( *((_DWORD *)a1 + 14) == 1 )
      {
        if ( !*((_DWORD *)a1 + 15) )
          FwDecreaseRuleCount(*((unsigned int *)a1 + 8), *(unsigned int *)(*v6 + 40));
        if ( *(_DWORD *)(v18 + 336) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v40);
      }
    }
    else if ( ((v20 - 2) & 0xFFFFFFFB) == 0 )
    {
      if ( *((_DWORD *)a1 + 14) && !*((_DWORD *)a1 + 15) && v20 == 2 )
        FwUpdateProfileRuleCount(
          *((unsigned int *)a1 + 8),
          *(unsigned int *)(**((_QWORD **)a1 + 5) + 40LL),
          *(unsigned int *)(*((_QWORD *)a1 + 6) + 40LL));
      v34 = (__int64 *)*((_QWORD *)a1 + 5);
      v3 = *v34;
      *v34 = *((_QWORD *)a1 + 6);
      v35 = *((_DWORD *)a1 + 14) == 1;
      *((_QWORD *)a1 + 6) = v3;
      if ( v35 && *((_DWORD *)a1 + 15) == 1 )
      {
        v36 = *((_QWORD *)a1 + 5);
        v37 = *(_DWORD *)(v36 + 32);
        *(_DWORD *)(v36 + 32) = *((_DWORD *)a1 + 17);
        *((_DWORD *)a1 + 17) = v37;
      }
    }
LABEL_74:
    if ( v2 >= 0 )
      return (unsigned int)v2;
    goto LABEL_75;
  }
  if ( v9 == 6 )
    goto LABEL_34;
  if ( v9 == 2 )
    v10 = (__int64 *)((char *)a1 + 48);
  else
    v10 = v6;
  v11 = (__int64 *)((char *)a1 + 48);
  v12 = *((_DWORD *)v6 + 76);
  v3 = *v10;
  if ( (v12 & 4) != 0 && v9 == 3 )
  {
    v3 = *v11;
    if ( !*v11 )
      v3 = *v6;
  }
  v13 = *((_DWORD *)a1 + 15);
  if ( v13 )
  {
    if ( v13 == 1 )
    {
      v14 = (*(&funcs_180066060 + 3 * *((int *)a1 + 8)))(
              v3,
              (int)a1 + 312,
              *((_DWORD *)a1 + 8),
              *((_DWORD *)a1 + 17),
              (__int64)a1 + 72);
      v2 = v14;
      if ( v14 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_75;
        v16 = 15;
        goto LABEL_23;
      }
    }
    else if ( v13 == 2 )
    {
      v14 = ((__int64 (__fastcall *)(__int64, char *, _QWORD, _QWORD, char *))funcs_1800660C8[3 * *((int *)a1 + 8)])(
              v3,
              (char *)a1 + 312,
              *((int *)a1 + 8),
              *((unsigned int *)a1 + 17),
              (char *)a1 + 72);
      v2 = v14;
      if ( v14 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_75;
        v16 = 16;
        goto LABEL_23;
      }
    }
    goto LABEL_34;
  }
  if ( v12 == 2
    || (FwPlumberAddFilterOriginProviderContext(v3),
        v14 = ((__int64 (__fastcall *)(__int64, char *, char *))*(&gWriterStoreFns + 3 * *((int *)a1 + 8)))(
                v3,
                (char *)a1 + 296,
                (char *)a1 + 72),
        v2 = v14,
        v14 >= 0) )
  {
LABEL_34:
    if ( *((_DWORD *)v6 + 76) == 2 )
      FwMetaDataAddEnforcementState((char *)a1 + 72, 25);
    goto LABEL_36;
  }
  v15 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
    goto LABEL_75;
  v16 = 14;
LABEL_23:
  WPP_SF_d(*(_QWORD *)(v15 + 16), v16, WPP_e32f5b0274d23b6ec5b45e864c5eefab_Traceguids, (unsigned int)v14);
LABEL_75:
  if ( *((_DWORD *)a1 + 14) )
  {
    v41 = *((_DWORD *)a1 + 15);
    if ( v41 < 2 || (v42 = 0, v41 == 2) )
      v42 = *(_QWORD *)(v3 + 24);
    if ( (unsigned int)dword_18012C3B0 > 5 )
    {
      v46 = *((_DWORD *)a1 + 4);
      v47 = *((_DWORD *)a1 + 15);
      v45 = v2;
      v48 = v42;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v42,
        (unsigned int)byte_180116503,
        v4,
        v5,
        (__int64)&v48,
        (__int64)&v47,
        (__int64)&v46,
        (__int64)&v45);
    }
  }
  else if ( (unsigned int)dword_18012C3B0 > 5 )
  {
    v46 = *v7;
    v45 = *((_DWORD *)a1 + 15);
    v47 = v2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18012C3B0,
      (unsigned int)byte_1801164A3,
      v4,
      v5,
      (__int64)&v45,
      (__int64)&v46,
      (__int64)&v47);
  }
  FwBatchUpdateFreeFilters((struct _LIST_ENTRY *)((char *)a1 + 296), 0);
  v43 = *((_DWORD *)a1 + 15);
  if ( v43 )
    FwBatchUpdateFreeFilters((struct _LIST_ENTRY *)((char *)a1 + 312), v43);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180065e90  push    rbp
0x180065e92  push    rbx
0x180065e93  push    rsi
0x180065e94  push    rdi
0x180065e95  push    r12
0x180065e97  push    r13
0x180065e99  push    r14
0x180065e9b  push    r15
0x180065e9d  lea     rbp, [rsp-58h]
0x180065ea2  sub     rsp, 158h
0x180065ea9  mov     rax, cs:__security_cookie
0x180065eb0  xor     rax, rsp
0x180065eb3  mov     [rbp+90h+var_50], rax
0x180065eb7  mov     rsi, rcx
0x180065eba  xor     r12d, r12d
0x180065ebd  lea     rcx, [rsp+190h+var_128]; void *
0x180065ec2  mov     [rsp+190h+var_130], r12
0x180065ec7  xor     edx, edx; Val
0x180065ec9  mov     r8d, 0D8h; Size
0x180065ecf  xor     r13d, r13d
0x180065ed2  call    memset_0
0x180065ed7  lea     rcx, [rsp+190h+var_130]
0x180065edc  call    cs:__imp_FwMarshalledMetaDataInitialize
0x180065ee3  nop     dword ptr [rax+rax+00h]
0x180065ee8  cmp     dword ptr [rsi+38h], 1
0x180065eec  mov     r15, [rsi+28h]
0x180065ef0  jnz     loc_18006611E
0x180065ef6  lea     rbx, [rsi+10h]
0x180065efa  mov     eax, [rbx]
0x180065efc  dec     eax
0x180065efe  test    eax, 0FFFFFFFBh
0x180065f03  jz      short loc_180065F59
0x180065f05  lea     rcx, [r15+108h]; struct _LIST_ENTRY *
0x180065f0c  xor     r8d, r8d; unsigned int
0x180065f0f  xor     edx, edx; struct _tag_FW_MARSHALLED_METADATA *
0x180065f11  call    ?FwBatchUpdateDeleteFilters@@YAJPEAU_LIST_ENTRY@@PEAU_tag_FW_MARSHALLED_METADATA@@K@Z; FwBatchUpdateDeleteFilters(_LIST_ENTRY *,_tag_FW_MARSHALLED_METADATA *,ulong)
0x180065f16  mov     r8d, [rsi+3Ch]; unsigned int
0x180065f1a  test    r8d, r8d
0x180065f1d  jz      short loc_180065F31
0x180065f1f  lea     rdx, [r15+28h]; struct _tag_FW_MARSHALLED_METADATA *
0x180065f23  lea     rcx, [r15+118h]; struct _LIST_ENTRY *
0x180065f2a  call    ?FwBatchUpdateDeleteFilters@@YAJPEAU_LIST_ENTRY@@PEAU_tag_FW_MARSHALLED_METADATA@@K@Z; FwBatchUpdateDeleteFilters(_LIST_ENTRY *,_tag_FW_MARSHALLED_METADATA *,ulong)
0x180065f2f  jmp     short loc_180065F59
0x180065f31  mov     rcx, [r15]
0x180065f34  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180065f3b  add     rcx, 1CCh; key
0x180065f42  cmp     rax, [rcx]
0x180065f45  jnz     short loc_180065F54
0x180065f47  mov     rax, qword ptr cs:GUID_NULL.Data4
0x180065f4e  cmp     rax, [rcx+8]
0x180065f52  jz      short loc_180065F59
0x180065f54  call    FwPlumberDeleteFilterOriginProviderContext
0x180065f59  mov     ecx, [rbx]
0x180065f5b  lea     eax, [rcx-4]
0x180065f5e  cmp     eax, 1
0x180065f61  jbe     loc_18006611E
0x180065f67  cmp     ecx, 6
0x180065f6a  jz      loc_1800660FF
0x180065f70  cmp     ecx, 2
0x180065f73  jnz     short loc_180065F7E
0x180065f75  lea     r13, [rsi+30h]
0x180065f79  mov     rax, r13
0x180065f7c  jmp     short loc_180065F85
0x180065f7e  mov     r13, r15
0x180065f81  lea     rax, [rsi+30h]
0x180065f85  mov     edx, [r15+130h]
0x180065f8c  mov     r13, [r13+0]
0x180065f90  test    dl, 4
0x180065f93  jz      short loc_180065FA5
0x180065f95  cmp     ecx, 3
0x180065f98  jnz     short loc_180065FA5
0x180065f9a  mov     r13, [rax]
0x180065f9d  test    r13, r13
0x180065fa0  jnz     short loc_180065FA5
0x180065fa2  mov     r13, [r15]
0x180065fa5  mov     eax, [rsi+3Ch]
0x180065fa8  test    eax, eax
0x180065faa  jnz     loc_180066030
0x180065fb0  cmp     edx, 2
0x180065fb3  jz      loc_1800660FF
0x180065fb9  mov     rcx, r13
0x180065fbc  call    FwPlumberAddFilterOriginProviderContext
0x180065fc1  movsxd  rax, dword ptr [rsi+20h]
0x180065fc5  lea     r10, ?gWriterStoreFns@@3PAU_tag_FW_WRITER_FUNCTIONS@@A; _tag_FW_WRITER_FUNCTIONS near * gWriterStoreFns
0x180065fcc  lea     r8, [rsi+48h]; struct _tag_FW_OBJECT_METADATA *
0x180065fd0  mov     rcx, r13; struct _tag_FW_RULE *
0x180065fd3  lea     rdx, [rsi+128h]; struct _LIST_ENTRY *
0x180065fda  lea     rax, [rax+rax*2]
0x180065fde  mov     rax, (?gWriterStoreFns@@3PAU_tag_FW_WRITER_FUNCTIONS@@A - 18012A840h)[r10+rax*8]; _tag_FW_WRITER_FUNCTIONS near * gWriterStoreFns
0x180065fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065fe7  mov     r12d, eax
0x180065fea  test    eax, eax
0x180065fec  jns     loc_1800660FF
0x180065ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x180065ff9  lea     rdx, WPP_GLOBAL_Control
0x180066000  cmp     rcx, rdx
0x180066003  jz      loc_180066380
0x180066009  test    byte ptr [rcx+1Ch], 1
0x18006600d  jz      loc_180066380
0x180066013  mov     edx, 0Eh
0x180066018  mov     rcx, [rcx+10h]
0x18006601c  lea     r8, WPP_e32f5b0274d23b6ec5b45e864c5eefab_Traceguids
0x180066023  mov     r9d, eax
0x180066026  call    WPP_SF_d
0x18006602b  jmp     loc_180066380
0x180066030  cmp     eax, 1
0x180066033  jnz     short loc_180066098
0x180066035  movsxd  r8, dword ptr [rsi+20h]
0x180066039  lea     r10, ?gWriterStoreFns@@3PAU_tag_FW_WRITER_FUNCTIONS@@A; _tag_FW_WRITER_FUNCTIONS near * gWriterStoreFns
0x180066040  lea     rcx, [rsi+48h]
0x180066044  mov     [rsp+190h+var_170], rcx
0x180066049  lea     rdx, [rsi+138h]
0x180066050  mov     rcx, r13
0x180066053  lea     r9, [r8+r8*2]
0x180066057  mov     rax, (funcs_180066060 - 18012A840h)[r10+r9*8]
0x18006605c  mov     r9d, [rsi+44h]
0x180066060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066065  mov     r12d, eax
0x180066068  test    eax, eax
0x18006606a  jns     loc_1800660FF
0x180066070  mov     rcx, cs:WPP_GLOBAL_Control
0x180066077  lea     rdx, WPP_GLOBAL_Control
0x18006607e  cmp     rcx, rdx
0x180066081  jz      loc_180066380
0x180066087  test    byte ptr [rcx+1Ch], 1
0x18006608b  jz      loc_180066380
0x180066091  mov     edx, 0Fh
0x180066096  jmp     short loc_180066018
0x180066098  cmp     eax, 2
0x18006609b  jnz     short loc_1800660FF
0x18006609d  movsxd  r8, dword ptr [rsi+20h]; struct _tag_FW_OBJECT_METADATA *
0x1800660a1  lea     r10, ?gWriterStoreFns@@3PAU_tag_FW_WRITER_FUNCTIONS@@A; _tag_FW_WRITER_FUNCTIONS near * gWriterStoreFns
0x1800660a8  lea     rcx, [rsi+48h]
0x1800660ac  mov     [rsp+190h+var_170], rcx
0x1800660b1  lea     rdx, [rsi+138h]; struct _LIST_ENTRY *
0x1800660b8  mov     rcx, r13; struct _tag_FW_RULE *
0x1800660bb  lea     r9, [r8+r8*2]
0x1800660bf  mov     rax, (funcs_1800660C8 - 18012A840h)[r10+r9*8]
0x1800660c4  mov     r9d, [rsi+44h]
0x1800660c8  call    _guard_dispatch_icall$thunk$10345483385596137414; std::_Ref_count_base::_Get_deleter(type_info const &) ...
0x1800660cd  mov     r12d, eax
0x1800660d0  test    eax, eax
0x1800660d2  jns     short loc_1800660FF
0x1800660d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800660db  lea     rdx, WPP_GLOBAL_Control
0x1800660e2  cmp     rcx, rdx
0x1800660e5  jz      loc_180066380
0x1800660eb  test    byte ptr [rcx+1Ch], 1
0x1800660ef  jz      loc_180066380
0x1800660f5  mov     edx, 10h
0x1800660fa  jmp     loc_180066018
0x1800660ff  cmp     dword ptr [r15+130h], 2
0x180066107  jnz     short loc_18006611E
0x180066109  mov     edx, 19h
0x18006610e  lea     rcx, [rsi+48h]
0x180066112  call    cs:__imp_FwMetaDataAddEnforcementState
0x180066119  nop     dword ptr [rax+rax+00h]
0x18006611e  mov     r14, [rsi+18h]
0x180066122  xor     edi, edi
0x180066124  cmp     dword ptr [rsi+38h], 1
0x180066128  jnz     short loc_180066195
0x18006612a  mov     rbx, [rsi+28h]
0x18006612e  lea     rcx, [rsi+128h]; struct _LIST_ENTRY *
0x180066135  lea     rdx, [rbx+108h]; struct _LIST_ENTRY *
0x18006613c  call    ?FwSwapListHeads@@YAXPEAU_LIST_ENTRY@@0@Z; FwSwapListHeads(_LIST_ENTRY *,_LIST_ENTRY *)
0x180066141  lea     rcx, [rsi+138h]; struct _LIST_ENTRY *
0x180066148  lea     rdx, [rbx+118h]; struct _LIST_ENTRY *
0x18006614f  call    ?FwSwapListHeads@@YAXPEAU_LIST_ENTRY@@0@Z; FwSwapListHeads(_LIST_ENTRY *,_LIST_ENTRY *)
0x180066154  lea     rcx, [rsi+48h]
0x180066158  lea     rdx, [rsp+190h+var_130]
0x18006615d  call    cs:__imp_FwMarshalledMetaDataCopy
0x180066164  nop     dword ptr [rax+rax+00h]
0x180066169  lea     rdx, [rsi+48h]
0x18006616d  lea     rcx, [rbx+28h]
0x180066171  call    cs:__imp_FwMarshalledMetaDataCopy
0x180066178  nop     dword ptr [rax+rax+00h]
0x18006617d  lea     rdx, [rbx+28h]
0x180066181  lea     rcx, [rsp+190h+var_130]
0x180066186  call    cs:__imp_FwMarshalledMetaDataCopy
0x18006618d  nop     dword ptr [rax+rax+00h]
0x180066192  mov     rdi, rbx
0x180066195  lea     rbx, [rsi+10h]
0x180066199  mov     ecx, [rbx]
0x18006619b  cmp     ecx, 1
0x18006619e  jnz     loc_1800662B5
0x1800661a4  mov     eax, [rsi+3Ch]
0x1800661a7  cmp     [rsi+38h], ecx
0x1800661aa  jnz     loc_180066266
0x1800661b0  test    eax, eax
0x1800661b2  jnz     short loc_1800661EA
0x1800661b4  mov     rcx, [r14+8]
0x1800661b8  cmp     [rcx], r14
0x1800661bb  jnz     loc_18006648D
0x1800661c1  mov     rax, [rsi+28h]
0x1800661c5  mov     [rax+18h], rcx
0x1800661c9  add     rax, 10h
0x1800661cd  mov     [rax], r14
0x1800661d0  mov     [rcx], rax
0x1800661d3  mov     [r14+8], rax
0x1800661d7  mov     rdx, [r15]
0x1800661da  mov     ecx, [rsi+20h]
0x1800661dd  mov     edx, [rdx+28h]
0x1800661e0  call    FwIncreaseRuleCount
0x1800661e5  jmp     loc_180066377
0x1800661ea  cmp     eax, 1
0x1800661ed  jnz     short loc_180066231
0x1800661ef  cmp     dword ptr [rsi+44h], 0
0x1800661f3  mov     rax, [rsi+28h]
0x1800661f7  jnz     short loc_1800661FF
0x1800661f9  add     r14, 18h
0x1800661fd  jmp     short loc_180066203
0x1800661ff  add     r14, 48h ; 'H'
0x180066203  mov     rcx, [r14+8]
0x180066207  cmp     [rcx], r14
0x18006620a  jnz     loc_18006648D
0x180066210  add     rax, 10h
0x180066214  mov     [rax], r14
0x180066217  mov     [rax+8], rcx
0x18006621b  mov     [rcx], rax
0x18006621e  mov     [r14+8], rax
0x180066222  mov     rcx, [rsi+28h]
0x180066226  mov     eax, [rsi+44h]
0x180066229  mov     [rcx+20h], eax
0x18006622c  jmp     loc_180066377
0x180066231  cmp     eax, 2
0x180066234  jnz     loc_180066377
0x18006623a  mov     rcx, [r14+38h]
0x18006623e  add     r14, 30h ; '0'
0x180066242  cmp     [rcx], r14
0x180066245  jnz     loc_18006648D
0x18006624b  mov     rax, [rsi+28h]
0x18006624f  add     rax, 10h
0x180066253  mov     [rax+8], rcx
0x180066257  mov     [rax], r14
0x18006625a  mov     [rcx], rax
0x18006625d  mov     [r14+8], rax
0x180066261  jmp     loc_180066377
0x180066266  test    eax, eax
0x180066268  jnz     short loc_180066274
0x18006626a  movsxd  rax, dword ptr [rsi+40h]
0x18006626e  add     rax, 4
0x180066272  jmp     short loc_180066285
0x180066274  cmp     eax, 1
0x180066277  jnz     loc_180066377
0x18006627d  movsxd  rax, dword ptr [rsi+40h]
0x180066281  add     rax, 7
0x180066285  lea     rax, [rax+rax*2]
0x180066289  lea     rcx, [r14+rax*8]
0x18006628d  mov     rdx, [rcx+8]
0x180066291  cmp     [rdx], rcx
0x180066294  jnz     loc_18006648D
0x18006629a  mov     rax, [rsi+28h]
0x18006629e  add     rax, 10h
0x1800662a2  mov     [rax], rcx
0x1800662a5  mov     [rax+8], rdx
0x1800662a9  mov     [rdx], rax
0x1800662ac  mov     [rcx+8], rax
0x1800662b0  jmp     loc_180066377
0x1800662b5  lea     eax, [rcx-4]
0x1800662b8  cmp     eax, 1
0x1800662bb  jbe     short loc_180066326
0x1800662bd  lea     eax, [rcx-2]
0x1800662c0  test    eax, 0FFFFFFFBh
0x1800662c5  jnz     loc_180066377
0x1800662cb  cmp     dword ptr [rsi+38h], 0
0x1800662cf  jz      short loc_1800662F6
0x1800662d1  cmp     dword ptr [rsi+3Ch], 0
0x1800662d5  jnz     short loc_1800662F6
0x1800662d7  cmp     ecx, 2
0x1800662da  jnz     short loc_1800662F6
0x1800662dc  mov     rax, [rsi+28h]
0x1800662e0  mov     r8, [rsi+30h]
0x1800662e4  mov     ecx, [rsi+20h]
0x1800662e7  mov     rdx, [rax]
0x1800662ea  mov     r8d, [r8+28h]
0x1800662ee  mov     edx, [rdx+28h]
0x1800662f1  call    FwUpdateProfileRuleCount
0x1800662f6  mov     rcx, [rsi+28h]
0x1800662fa  mov     rax, [rsi+30h]
0x1800662fe  mov     r13, [rcx]
0x180066301  mov     [rcx], rax
0x180066304  cmp     dword ptr [rsi+38h], 1
0x180066308  mov     [rsi+30h], r13
0x18006630c  jnz     short loc_180066377
0x18006630e  cmp     dword ptr [rsi+3Ch], 1
0x180066312  jnz     short loc_180066377
0x180066314  mov     rdx, [rsi+28h]
0x180066318  mov     eax, [rsi+44h]
0x18006631b  mov     ecx, [rdx+20h]
0x18006631e  mov     [rdx+20h], eax
0x180066321  mov     [rsi+44h], ecx
0x180066324  jmp     short loc_180066377
0x180066326  mov     rax, [rsi+28h]
0x18006632a  add     rax, 10h
0x18006632e  mov     rdx, [rax]
0x180066331  cmp     [rdx+8], rax
0x180066335  jnz     loc_18006648D
0x18006633b  mov     rcx, [rax+8]
0x18006633f  cmp     [rcx], rax
0x180066342  jnz     loc_18006648D
  ... truncated ...
```
