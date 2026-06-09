# CMSMQTriggerSet::UpdateTrigger(wchar_t *,wchar_t *,wchar_t *,__MIDL___MIDL_itf_mqtrig_0000_0000_0002,long,long,__MIDL___MIDL_itf_mqtrig_0000_0000_0003)

- ea: `0x180012f40`
- end: `0x180013451`
- name: `?UpdateTrigger@CMSMQTriggerSet@@UEAAJPEA_W00W4__MIDL___MIDL_itf_mqtrig_0000_0000_0002@@JJW4__MIDL___MIDL_itf_mqtrig_0000_0000_0003@@@Z`
- size: `1297`
- prototype: `int __high(wchar_t *, wchar_t *, wchar_t *, enum __MIDL___MIDL_itf_mqtrig_0000_0000_0002, int, int, enum __MIDL___MIDL_itf_mqtrig_0000_0000_0003)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180004d88`
- `0x18000544c`
- `0x180005740`
- `0x180009ab0`
- `0x18000c62c`
- `0x18000c654`
- `0x18000d480`
- `0x180010324`
- `0x180011778`
- `0x1800118c8`
- `0x180012bf8`
- `0x180012d10`
- `0x180012f40`
- `0x1800161a8`
- `0x1800164c8`
- `0x1800174d4`
- `0x18001a324`
- `0x18001a718`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMSMQTriggerSet::UpdateTrigger(
        __int64 a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  CMSMQTriggerSet *v12; // rcx
  __int64 result; // rax
  _bstr_t *v14; // rax
  CMSMQTriggerSet *v15; // rcx
  _bstr_t *v16; // rax
  CMSMQTriggerSet *v17; // rcx
  _bstr_t *v18; // rax
  CMSMQTriggerSet *v19; // rcx
  DWORD TriggerInMap; // eax
  CMSMQTriggerSet *v21; // rcx
  DWORD v22; // ebx
  DWORD v23; // eax
  CMSMQTriggerSet *v24; // rcx
  DWORD LocalMachineName; // eax
  CMSMQTriggerSet *v26; // rcx
  _bstr_t *v27; // rax
  const wchar_t **v28; // rdi
  wchar_t *v29; // rax
  CMSMQTriggerSet *v30; // rcx
  int v31; // r15d
  struct CRuntimeTriggerInfo *v32; // rbx
  int v33; // r13d
  wchar_t ***v34; // r12
  const wchar_t *v35; // rdx
  wchar_t ***v36; // rdi
  CMSMQTriggerSet *v37; // rcx
  wchar_t *v38; // r9
  wchar_t *v39; // r8
  wchar_t **v40; // rax
  wchar_t *v41; // rdx
  CMSMQTriggerSet *v42; // rcx
  CMSMQTriggerSet *v43; // rcx
  wchar_t **v44; // [rsp+20h] [rbp-68h] BYREF
  struct CRuntimeTriggerInfo *v45; // [rsp+28h] [rbp-60h] BYREF
  __int64 v46; // [rsp+30h] [rbp-58h] BYREF
  __int64 v47; // [rsp+38h] [rbp-50h] BYREF
  wchar_t *v48[4]; // [rsp+40h] [rbp-48h] BYREF

  if ( !*(_BYTE *)(a1 + 72) )
  {
    v12 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids);
    CMSMQTriggerSet::SetComClassError(v12, 0xC00E0E11);
    return 3222146577LL;
  }
  try
  {
    v14 = _bstr_t::_bstr_t((_bstr_t *)&v47, a2);
    if ( CRuntimeTriggerInfo::IsValidTriggerID(v14) )
    {
      v16 = _bstr_t::_bstr_t((_bstr_t *)&v47, a3);
      if ( CRuntimeTriggerInfo::IsValidTriggerID(v16) )
      {
        if ( a5 || (v18 = _bstr_t::_bstr_t((_bstr_t *)&v47, a4), CRuntimeTriggerInfo::IsValidTriggerID(v18)) )
        {
          v47 = 0;
          v45 = 0;
          TriggerInMap = CMSMQTriggerSet::FindTriggerInMap(a1 - 8, a2, (__int64 *)&v45, &v47);
          v22 = TriggerInMap;
          if ( !TriggerInMap )
          {
            v44 = 0;
            if ( a5 )
            {
              v23 = GenSystemQueueFormatName(a5, (_bstr_t *)&v44);
              if ( v23 )
              {
                v24 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    50,
                    WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids,
                    v23);
                CMSMQTriggerSet::SetComClassError(v24, 0xC00E0E00);
                _bstr_t::_Free((_bstr_t *)&v44);
                SafeRelease<CRuntimeTriggerInfo>((__int64)v45);
                return 3222146560LL;
              }
            }
            else
            {
              v46 = 0;
              LocalMachineName = GetLocalMachineName((struct _bstr_t *)&v46);
              if ( LocalMachineName )
              {
                v26 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    51,
                    WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids,
                    LocalMachineName);
                CMSMQTriggerSet::SetComClassError(v26, 0xC00E0E00);
                _bstr_t::_Free((_bstr_t *)&v46);
                _bstr_t::_Free((_bstr_t *)&v44);
                SafeRelease<CRuntimeTriggerInfo>((__int64)v45);
                return 3222146560LL;
              }
              v48[1] = (wchar_t *)&v47;
              v47 = v46;
              if ( v46 )
                _InterlockedIncrement((volatile signed __int32 *)(v46 + 16));
              v27 = _bstr_t::_bstr_t((_bstr_t *)v48, a4);
              UpdateMachineNameInQueuePath(v27, (_bstr_t *)&v47, (_bstr_t *)&v44);
              _bstr_t::_Free((_bstr_t *)&v46);
            }
            v28 = (const wchar_t **)v44;
            if ( a8
              && (!v44 ? (v29 = 0) : (v29 = *v44),
                  v48[0] = v29,
                  CMSMQTriggerSet::GetNoOfTriggersForQueue((CMSMQTriggerSet *)(a1 - 8), v48) > 1) )
            {
              v30 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids);
              CMSMQTriggerSet::SetComClassError(v30, 0xC00E0E14);
              _bstr_t::_Free((_bstr_t *)&v44);
              SafeRelease<CRuntimeTriggerInfo>((__int64)v45);
              return 3222146580LL;
            }
            else
            {
              v31 = 1;
              if ( a8 != 2 )
                v31 = a7;
              v32 = v45;
              v33 = *((_DWORD *)v45 + 5);
              v34 = (wchar_t ***)((char *)v45 + 2088);
              _bstr_t::operator=((struct CRuntimeTriggerInfo *)((char *)v45 + 2088), a3);
              *((_DWORD *)v32 + 526) = a5;
              if ( v28 )
                v35 = *v28;
              else
                v35 = 0;
              v36 = (wchar_t ***)((char *)v32 + 2096);
              _bstr_t::operator=((struct CRuntimeTriggerInfo *)((char *)v32 + 2096), v35);
              *((_BYTE *)v32 + 2072) = a6 != 0;
              *((_BYTE *)v32 + 2073) = v31 != 0;
              *((_DWORD *)v32 + 5) = a8;
              if ( CRuntimeTriggerInfo::Update(v32, *(HKEY *)(a1 + 80)) )
              {
                if ( v33 != a8 )
                  CMSMQTriggerSet::UpdateQueueAclForTrigger(v37, v32, 0);
                if ( *v36 )
                  v38 = **v36;
                else
                  v38 = 0;
                if ( *v34 )
                  v39 = **v34;
                else
                  v39 = 0;
                v40 = (wchar_t **)*((_QWORD *)v32 + 260);
                if ( v40 )
                  v41 = *v40;
                else
                  v41 = 0;
                CMSMQTriggerNotification::NotifyTriggerUpdated((CMSMQTriggerNotification *)(a1 + 64), v41, v39, v38);
                _bstr_t::_Free((_bstr_t *)&v44);
                SafeRelease<CRuntimeTriggerInfo>((__int64)v32);
                return 0;
              }
              else
              {
                v42 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
                CMSMQTriggerSet::SetComClassError(v42, 0xC00E0E0D);
                _bstr_t::_Free((_bstr_t *)&v44);
                SafeRelease<CRuntimeTriggerInfo>((__int64)v32);
                return 3222146573LL;
              }
            }
          }
          CMSMQTriggerSet::SetComClassError(v21, TriggerInMap);
          SafeRelease<CRuntimeTriggerInfo>((__int64)v45);
          result = v22;
        }
        else
        {
          v19 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
          CMSMQTriggerSet::SetComClassError(v19, 0xC00E0E1E);
          result = 3222146590LL;
        }
      }
      else
      {
        v17 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
        CMSMQTriggerSet::SetComClassError(v17, 0xC00E0E1D);
        result = 3222146589LL;
      }
    }
    else
    {
      v15 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
      CMSMQTriggerSet::SetComClassError(v15, 0xC00E0E1C);
      result = 3222146588LL;
    }
  }
  catch ( std::bad_alloc )
  {
    v43 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids);
    CMSMQTriggerSet::SetComClassError(v43, 0xC00E0E06);
    return 3222146566LL;
  }
  return result;
}

```

## disassembly

```asm
0x180012f40  mov     rax, rsp
0x180012f43  mov     [rax+10h], rbx
0x180012f47  mov     [rax+20h], rsi
0x180012f4b  mov     [rax+18h], r8
0x180012f4f  mov     [rax+8], rcx
0x180012f53  push    rdi
0x180012f54  push    r12
0x180012f56  push    r13
0x180012f58  push    r14
0x180012f5a  push    r15
0x180012f5c  sub     rsp, 60h
0x180012f60  mov     rdi, r9
0x180012f63  mov     rsi, r8
0x180012f66  mov     rbx, rdx
0x180012f69  mov     r15, rcx
0x180012f6c  xor     r12d, r12d
0x180012f6f  cmp     [rcx+48h], r12b
0x180012f73  jnz     short loc_180012FB6
0x180012f75  lea     rax, WPP_GLOBAL_Control
0x180012f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f83  cmp     rcx, rax
0x180012f86  jz      short loc_180012FA3
0x180012f88  test    byte ptr [rcx+1Ch], 1
0x180012f8c  jz      short loc_180012FA3
0x180012f8e  lea     edx, [r12+2Eh]
0x180012f93  lea     r8, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids
0x180012f9a  mov     rcx, [rcx+10h]
0x180012f9e  call    WPP_SF_
0x180012fa3  mov     ebx, 0C00E0E11h
0x180012fa8  mov     edx, ebx; int
0x180012faa  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x180012faf  mov     eax, ebx
0x180012fb1  jmp     loc_180013436
0x180012fb6  lea     rcx, [rsp+88h+var_50]; this
0x180012fbb  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180012fc0  mov     rcx, rax
0x180012fc3  call    ?IsValidTriggerID@CRuntimeTriggerInfo@@SA_NV_bstr_t@@@Z; CRuntimeTriggerInfo::IsValidTriggerID(_bstr_t)
0x180012fc8  test    al, al
0x180012fca  jnz     short loc_180013010
0x180012fcc  lea     rax, WPP_GLOBAL_Control
0x180012fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fda  cmp     rcx, rax
0x180012fdd  jz      short loc_180012FFD
0x180012fdf  test    byte ptr [rcx+1Ch], 1
0x180012fe3  jz      short loc_180012FFD
0x180012fe5  mov     edx, 2Fh ; '/'
0x180012fea  mov     r9, rbx
0x180012fed  lea     r8, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids
0x180012ff4  mov     rcx, [rcx+10h]; LoggerHandle
0x180012ff8  call    WPP_SF_S
0x180012ffd  mov     ebx, 0C00E0E1Ch
0x180013002  mov     edx, ebx; int
0x180013004  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x180013009  mov     eax, ebx
0x18001300b  jmp     loc_180013436
0x180013010  mov     rdx, rsi; wchar_t *
0x180013013  lea     rcx, [rsp+88h+var_50]; this
0x180013018  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18001301d  mov     rcx, rax
0x180013020  call    ?IsValidTriggerID@CRuntimeTriggerInfo@@SA_NV_bstr_t@@@Z; CRuntimeTriggerInfo::IsValidTriggerID(_bstr_t)
0x180013025  test    al, al
0x180013027  jnz     short loc_18001306D
0x180013029  lea     rax, WPP_GLOBAL_Control
0x180013030  mov     rcx, cs:WPP_GLOBAL_Control
0x180013037  cmp     rcx, rax
0x18001303a  jz      short loc_18001305A
0x18001303c  test    byte ptr [rcx+1Ch], 1
0x180013040  jz      short loc_18001305A
0x180013042  mov     edx, 30h ; '0'
0x180013047  mov     r9, rsi
0x18001304a  lea     r8, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids
0x180013051  mov     rcx, [rcx+10h]; LoggerHandle
0x180013055  call    WPP_SF_S
0x18001305a  mov     ebx, 0C00E0E1Dh
0x18001305f  mov     edx, ebx; int
0x180013061  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x180013066  mov     eax, ebx
0x180013068  jmp     loc_180013436
0x18001306d  mov     r14d, [rsp+88h+arg_20]
0x180013075  test    r14d, r14d
0x180013078  jnz     short loc_1800130D6
0x18001307a  mov     rdx, rdi; wchar_t *
0x18001307d  lea     rcx, [rsp+88h+var_50]; this
0x180013082  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180013087  mov     rcx, rax
0x18001308a  call    ?IsValidTriggerID@CRuntimeTriggerInfo@@SA_NV_bstr_t@@@Z; CRuntimeTriggerInfo::IsValidTriggerID(_bstr_t)
0x18001308f  test    al, al
0x180013091  jnz     short loc_1800130D6
0x180013093  lea     rax, WPP_GLOBAL_Control
0x18001309a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130a1  cmp     rcx, rax
0x1800130a4  jz      short loc_1800130C3
0x1800130a6  test    byte ptr [rcx+1Ch], 1
0x1800130aa  jz      short loc_1800130C3
0x1800130ac  lea     edx, [r14+31h]
0x1800130b0  mov     r9, rdi
0x1800130b3  lea     r8, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids
0x1800130ba  mov     rcx, [rcx+10h]; LoggerHandle
0x1800130be  call    WPP_SF_S
0x1800130c3  mov     ebx, 0C00E0E1Eh
0x1800130c8  mov     edx, ebx; int
0x1800130ca  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x1800130cf  mov     eax, ebx
0x1800130d1  jmp     loc_180013436
0x1800130d6  mov     [rsp+88h+var_50], r12
0x1800130db  mov     [rsp+88h+var_60], r12
0x1800130e0  lea     r9, [rsp+88h+var_50]
0x1800130e5  lea     r8, [rsp+88h+var_60]
0x1800130ea  mov     rdx, rbx
0x1800130ed  lea     rcx, [r15-8]
0x1800130f1  call    ?FindTriggerInMap@CMSMQTriggerSet@@AEAAJPEA_WAEAV?$R@VCRuntimeTriggerInfo@@@@AEAViterator@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@@std@@@2@$0A@@std@@@std@@@Z; CMSMQTriggerSet::FindTriggerInMap(wchar_t *,R<CRuntimeTriggerInfo> &,std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CRuntimeTriggerInfo>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CRuntimeTriggerInfo>>>,0>>::iterator &)
0x1800130f6  mov     ebx, eax
0x1800130f8  test    eax, eax
0x1800130fa  jz      short loc_180013115
0x1800130fc  mov     edx, eax; int
0x1800130fe  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x180013103  nop
0x180013104  mov     rcx, [rsp+88h+var_60]
0x180013109  call    ??$SafeRelease@VCRuntimeTriggerInfo@@@@YAXPEAVCRuntimeTriggerInfo@@@Z; SafeRelease<CRuntimeTriggerInfo>(CRuntimeTriggerInfo *)
0x18001310e  mov     eax, ebx
0x180013110  jmp     loc_180013436
0x180013115  mov     [rsp+88h+var_68], r12
0x18001311a  test    r14d, r14d
0x18001311d  jz      short loc_18001318E
0x18001311f  lea     rdx, [rsp+88h+var_68]
0x180013124  mov     ecx, r14d
0x180013127  call    ?GenSystemQueueFormatName@@YAJW4__MIDL___MIDL_itf_mqtrig_0000_0000_0002@@PEAV_bstr_t@@@Z; GenSystemQueueFormatName(__MIDL___MIDL_itf_mqtrig_0000_0000_0002,_bstr_t *)
0x18001312c  mov     r9d, eax
0x18001312f  test    eax, eax
0x180013131  jz      loc_18001324E
0x180013137  lea     rax, WPP_GLOBAL_Control
0x18001313e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013145  cmp     rcx, rax
0x180013148  jz      short loc_180013165
0x18001314a  test    byte ptr [rcx+1Ch], 1
0x18001314e  jz      short loc_180013165
0x180013150  mov     edx, 32h ; '2'
0x180013155  lea     r8, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids
0x18001315c  mov     rcx, [rcx+10h]
0x180013160  call    WPP_SF_d
0x180013165  mov     ebx, 0C00E0E00h
0x18001316a  mov     edx, ebx; int
0x18001316c  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x180013171  nop
0x180013172  lea     rcx, [rsp+88h+var_68]; this
0x180013177  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18001317c  nop
0x18001317d  mov     rcx, [rsp+88h+var_60]
0x180013182  call    ??$SafeRelease@VCRuntimeTriggerInfo@@@@YAXPEAVCRuntimeTriggerInfo@@@Z; SafeRelease<CRuntimeTriggerInfo>(CRuntimeTriggerInfo *)
0x180013187  mov     eax, ebx
0x180013189  jmp     loc_180013436
0x18001318e  mov     [rsp+88h+var_58], r12
0x180013193  lea     rcx, [rsp+88h+var_58]; struct _bstr_t *
0x180013198  call    ?GetLocalMachineName@@YAKPEAV_bstr_t@@@Z; GetLocalMachineName(_bstr_t *)
0x18001319d  mov     r9d, eax
0x1800131a0  test    eax, eax
0x1800131a2  jz      short loc_180013206
0x1800131a4  lea     rax, WPP_GLOBAL_Control
0x1800131ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131b2  cmp     rcx, rax
0x1800131b5  jz      short loc_1800131D2
0x1800131b7  test    byte ptr [rcx+1Ch], 1
0x1800131bb  jz      short loc_1800131D2
0x1800131bd  mov     edx, 33h ; '3'
0x1800131c2  lea     r8, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids
0x1800131c9  mov     rcx, [rcx+10h]
0x1800131cd  call    WPP_SF_d
0x1800131d2  mov     ebx, 0C00E0E00h
0x1800131d7  mov     edx, ebx; int
0x1800131d9  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x1800131de  nop
0x1800131df  lea     rcx, [rsp+88h+var_58]; this
0x1800131e4  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800131e9  nop
0x1800131ea  lea     rcx, [rsp+88h+var_68]; this
0x1800131ef  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800131f4  nop
0x1800131f5  mov     rcx, [rsp+88h+var_60]
0x1800131fa  call    ??$SafeRelease@VCRuntimeTriggerInfo@@@@YAXPEAVCRuntimeTriggerInfo@@@Z; SafeRelease<CRuntimeTriggerInfo>(CRuntimeTriggerInfo *)
0x1800131ff  mov     eax, ebx
0x180013201  jmp     loc_180013436
0x180013206  lea     rax, [rsp+88h+var_50]
0x18001320b  mov     [rsp+88h+var_40], rax
0x180013210  mov     rax, [rsp+88h+var_58]
0x180013215  mov     [rsp+88h+var_50], rax
0x18001321a  test    rax, rax
0x18001321d  jz      short loc_180013223
0x18001321f  lock inc dword ptr [rax+10h]
0x180013223  mov     rdx, rdi; wchar_t *
0x180013226  lea     rcx, [rsp+88h+var_48]; this
0x18001322b  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180013230  nop
0x180013231  lea     r8, [rsp+88h+var_68]
0x180013236  lea     rdx, [rsp+88h+var_50]
0x18001323b  mov     rcx, rax
0x18001323e  call    ?UpdateMachineNameInQueuePath@@YA_NV_bstr_t@@0PEAV1@@Z; UpdateMachineNameInQueuePath(_bstr_t,_bstr_t,_bstr_t *)
0x180013243  nop
0x180013244  lea     rcx, [rsp+88h+var_58]; this
0x180013249  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18001324e  mov     esi, [rsp+88h+arg_38]
0x180013255  mov     rdi, [rsp+88h+var_68]
0x18001325a  test    esi, esi
0x18001325c  jz      short loc_1800132DA
0x18001325e  test    rdi, rdi
0x180013261  jz      short loc_180013268
0x180013263  mov     rax, [rdi]
0x180013266  jmp     short loc_18001326B
0x180013268  mov     rax, r12
0x18001326b  mov     [rsp+88h+var_48], rax
0x180013270  lea     rdx, [rsp+88h+var_48]; wchar_t **
0x180013275  lea     rcx, [r15-8]; this
0x180013279  call    ?GetNoOfTriggersForQueue@CMSMQTriggerSet@@AEBAKAEBQEA_W@Z; CMSMQTriggerSet::GetNoOfTriggersForQueue(wchar_t * const &)
0x18001327e  cmp     eax, 1
0x180013281  jbe     short loc_1800132DA
0x180013283  lea     rax, WPP_GLOBAL_Control
0x18001328a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013291  cmp     rcx, rax
0x180013294  jz      short loc_1800132B1
0x180013296  test    byte ptr [rcx+1Ch], 1
0x18001329a  jz      short loc_1800132B1
0x18001329c  mov     edx, 34h ; '4'
0x1800132a1  lea     r8, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids
0x1800132a8  mov     rcx, [rcx+10h]
0x1800132ac  call    WPP_SF_
0x1800132b1  mov     ebx, 0C00E0E14h
0x1800132b6  mov     edx, ebx; int
0x1800132b8  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x1800132bd  nop
0x1800132be  lea     rcx, [rsp+88h+var_68]; this
0x1800132c3  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800132c8  nop
0x1800132c9  mov     rcx, [rsp+88h+var_60]
0x1800132ce  call    ??$SafeRelease@VCRuntimeTriggerInfo@@@@YAXPEAVCRuntimeTriggerInfo@@@Z; SafeRelease<CRuntimeTriggerInfo>(CRuntimeTriggerInfo *)
0x1800132d3  mov     eax, ebx
0x1800132d5  jmp     loc_180013436
0x1800132da  mov     r15d, 1
0x1800132e0  cmp     esi, 2
0x1800132e3  cmovnz  r15d, [rsp+88h+arg_30]
0x1800132ec  mov     rbx, [rsp+88h+var_60]
0x1800132f1  mov     r13d, [rbx+14h]
0x1800132f5  lea     r12, [rbx+828h]
0x1800132fc  mov     rdx, [rsp+88h+arg_10]
0x180013304  mov     rcx, r12
0x180013307  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x18001330c  mov     [rbx+838h], r14d
0x180013313  test    rdi, rdi
0x180013316  jz      short loc_18001331D
0x180013318  mov     rdx, [rdi]
0x18001331b  jmp     short loc_18001331F
0x18001331d  xor     edx, edx
0x18001331f  lea     rdi, [rbx+830h]
0x180013326  mov     rcx, rdi
0x180013329  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x18001332e  cmp     [rsp+88h+arg_28], 0
0x180013336  setnz   al
0x180013339  mov     [rbx+818h], al
0x18001333f  test    r15d, r15d
0x180013342  setnz   al
0x180013345  mov     [rbx+819h], al
0x18001334b  mov     [rbx+14h], esi
0x18001334e  mov     r14, [rsp+88h+arg_0]
0x180013356  mov     rdx, [r14+50h]; HKEY
0x18001335a  mov     rcx, rbx; this
0x18001335d  call    ?Update@CRuntimeTriggerInfo@@QEAA_NPEAUHKEY__@@@Z; CRuntimeTriggerInfo::Update(HKEY__ *)
0x180013362  cmp     al, 1
0x180013364  jnz     short loc_1800133CB
0x180013366  cmp     r13d, esi
0x180013369  jz      short loc_180013376
0x18001336b  xor     r8d, r8d; int
0x18001336e  mov     rdx, rbx; struct CRuntimeTriggerInfo *
0x180013371  call    ?UpdateQueueAclForTrigger@CMSMQTriggerSet@@AEAAJPEAVCRuntimeTriggerInfo@@H@Z; CMSMQTriggerSet::UpdateQueueAclForTrigger(CRuntimeTriggerInfo *,int)
0x180013376  mov     rax, [rdi]
0x180013379  test    rax, rax
0x18001337c  jz      short loc_180013383
0x18001337e  mov     r9, [rax]
0x180013381  jmp     short loc_180013386
0x180013383  xor     r9d, r9d; wchar_t *
0x180013386  mov     rax, [r12]
0x18001338a  test    rax, rax
0x18001338d  jz      short loc_180013394
0x18001338f  mov     r8, [rax]
0x180013392  jmp     short loc_180013397
0x180013394  xor     r8d, r8d; wchar_t *
0x180013397  mov     rax, [rbx+820h]
0x18001339e  test    rax, rax
0x1800133a1  jz      short loc_1800133A8
0x1800133a3  mov     rdx, [rax]
0x1800133a6  jmp     short loc_1800133AA
0x1800133a8  xor     edx, edx; wchar_t *
0x1800133aa  lea     rcx, [r14+40h]; this
0x1800133ae  call    ?NotifyTriggerUpdated@CMSMQTriggerNotification@@IEAAJPEA_W00@Z; CMSMQTriggerNotification::NotifyTriggerUpdated(wchar_t *,wchar_t *,wchar_t *)
0x1800133b3  nop
0x1800133b4  lea     rcx, [rsp+88h+var_68]; this
0x1800133b9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800133be  nop
0x1800133bf  mov     rcx, rbx
0x1800133c2  call    ??$SafeRelease@VCRuntimeTriggerInfo@@@@YAXPEAVCRuntimeTriggerInfo@@@Z; SafeRelease<CRuntimeTriggerInfo>(CRuntimeTriggerInfo *)
0x1800133c7  xor     eax, eax
0x1800133c9  jmp     short loc_180013436
0x1800133cb  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
