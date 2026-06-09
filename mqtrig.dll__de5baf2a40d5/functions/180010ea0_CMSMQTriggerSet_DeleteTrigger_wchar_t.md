# CMSMQTriggerSet::DeleteTrigger(wchar_t *)

- ea: `0x180010ea0`
- end: `0x180011086`
- name: `?DeleteTrigger@CMSMQTriggerSet@@UEAAJPEA_W@Z`
- size: `486`
- prototype: `__int64 __fastcall(HKEY *this, wchar_t *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180004d88`
- `0x18000544c`
- `0x18000c62c`
- `0x18000d3d0`
- `0x180010324`
- `0x180010ea0`
- `0x1800115d0`
- `0x180011778`
- `0x180012bf8`
- `0x180012d10`
- `0x1800137ec`
- `0x180019b4c`
- `0x18001a324`

## pseudocode

```c
__int64 __fastcall CMSMQTriggerSet::DeleteTrigger(HKEY *this, wchar_t *a2)
{
  CMSMQTriggerSet *v4; // rcx
  __int64 result; // rax
  _bstr_t *v6; // rax
  CMSMQTriggerSet *v7; // rcx
  int TriggerInMap; // eax
  CMSMQTriggerSet *v9; // rcx
  unsigned int v10; // ebx
  CRuntimeTriggerInfo *v11; // rbx
  CMSMQTriggerSet *v12; // rcx
  wchar_t **v13; // rax
  wchar_t *v14; // rdx
  wchar_t **v15; // rax
  wchar_t *v16; // rcx
  CMSMQTriggerSet *v17; // rcx
  CMSMQTriggerSet *v18; // rcx
  CRuntimeTriggerInfo *v19; // [rsp+40h] [rbp+8h] BYREF
  wchar_t *v20; // [rsp+50h] [rbp+18h] BYREF

  if ( *((_BYTE *)this + 72) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v6 = _bstr_t::_bstr_t((_bstr_t *)&v19, a2);
      if ( CRuntimeTriggerInfo::IsValidTriggerID(v6) )
      {
        v20 = 0;
        v19 = 0;
        TriggerInMap = CMSMQTriggerSet::FindTriggerInMap((__int64)(this - 1), a2, (__int64 *)&v19, (__int64 *)&v20);
        v10 = TriggerInMap;
        if ( TriggerInMap )
        {
          ((void (__stdcall *)(CMSMQTriggerSet *, int))CMSMQTriggerSet::SetComClassError)(v9, TriggerInMap);
          SafeRelease<CRuntimeTriggerInfo>((__int64)v19);
          result = v10;
        }
        else
        {
          v11 = v19;
          if ( CRuntimeTriggerInfo::Delete(v19, this[10]) )
          {
            v13 = (wchar_t **)*((_QWORD *)v11 + 260);
            if ( v13 )
              v14 = *v13;
            else
              v14 = 0;
            CMSMQTriggerNotification::NotifyTriggerDeleted((CMSMQTriggerNotification *)(this + 8), v14);
            std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CRuntimeTriggerInfo>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CRuntimeTriggerInfo>>>,0>>::erase(
              this + 148,
              &v20,
              v20);
            v15 = (wchar_t **)*((_QWORD *)v11 + 262);
            if ( v15 )
              v16 = *v15;
            else
              v16 = 0;
            v20 = v16;
            if ( !CMSMQTriggerSet::ExistTriggersForQueue((CMSMQTriggerSet *)(this - 1), &v20) )
              CMSMQTriggerSet::UpdateQueueAclForTrigger(v17, v11, 1);
            SafeRelease<CRuntimeTriggerInfo>((__int64)v11);
            result = 0;
          }
          else
          {
            v12 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
            ((void (__stdcall *)(CMSMQTriggerSet *, int))CMSMQTriggerSet::SetComClassError)(v12, -1072820715);
            SafeRelease<CRuntimeTriggerInfo>((__int64)v11);
            result = 3222146581LL;
          }
        }
      }
      else
      {
        v7 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
        ((void (__stdcall *)(CMSMQTriggerSet *, int))CMSMQTriggerSet::SetComClassError)(v7, -1072820708);
        result = 3222146588LL;
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v18 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids);
        ((void (__stdcall *)(CMSMQTriggerSet *, int))CMSMQTriggerSet::SetComClassError)(v18, -1072820730);
        result = 3222146566LL;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180011072);
      }
    }
  }
  else
  {
    v4 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids);
    ((void (__stdcall *)(CMSMQTriggerSet *, int))CMSMQTriggerSet::SetComClassError)(v4, -1072820719);
    return 3222146577LL;
  }
  return result;
}

```

## disassembly

```asm
0x180010ea0  mov     [rsp+arg_8], rbx
0x180010ea5  push    rsi
0x180010ea6  push    rdi
0x180010ea7  push    r14
0x180010ea9  sub     rsp, 20h
0x180010ead  mov     rsi, rdx
0x180010eb0  mov     rdi, rcx
0x180010eb3  cmp     byte ptr [rcx+48h], 0
0x180010eb7  jnz     short loc_180010EFA
0x180010eb9  lea     rax, WPP_GLOBAL_Control
0x180010ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ec7  cmp     rcx, rax
0x180010eca  jz      short loc_180010EE7
0x180010ecc  test    byte ptr [rcx+1Ch], 1
0x180010ed0  jz      short loc_180010EE7
0x180010ed2  mov     edx, 2Ah ; '*'
0x180010ed7  lea     r8, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids
0x180010ede  mov     rcx, [rcx+10h]
0x180010ee2  call    WPP_SF_
0x180010ee7  mov     ebx, 0C00E0E11h
0x180010eec  mov     edx, ebx; int
0x180010eee  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x180010ef3  mov     eax, ebx
0x180010ef5  jmp     loc_180011077
0x180010efa  lea     rcx, [rsp+38h+arg_0]; this
0x180010eff  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180010f04  mov     rcx, rax
0x180010f07  call    ?IsValidTriggerID@CRuntimeTriggerInfo@@SA_NV_bstr_t@@@Z; CRuntimeTriggerInfo::IsValidTriggerID(_bstr_t)
0x180010f0c  test    al, al
0x180010f0e  jnz     short loc_180010F54
0x180010f10  lea     rax, WPP_GLOBAL_Control
0x180010f17  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f1e  cmp     rcx, rax
0x180010f21  jz      short loc_180010F41
0x180010f23  test    byte ptr [rcx+1Ch], 1
0x180010f27  jz      short loc_180010F41
0x180010f29  mov     edx, 2Bh ; '+'
0x180010f2e  mov     r9, rsi
0x180010f31  lea     r8, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids
0x180010f38  mov     rcx, [rcx+10h]; LoggerHandle
0x180010f3c  call    WPP_SF_S
0x180010f41  mov     ebx, 0C00E0E1Ch
0x180010f46  mov     edx, ebx; int
0x180010f48  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x180010f4d  mov     eax, ebx
0x180010f4f  jmp     loc_180011077
0x180010f54  mov     [rsp+38h+arg_10], 0
0x180010f5d  mov     [rsp+38h+arg_0], 0
0x180010f66  lea     r9, [rsp+38h+arg_10]
0x180010f6b  lea     r8, [rsp+38h+arg_0]
0x180010f70  mov     rdx, rsi
0x180010f73  lea     rcx, [rdi-8]
0x180010f77  call    ?FindTriggerInMap@CMSMQTriggerSet@@AEAAJPEA_WAEAV?$R@VCRuntimeTriggerInfo@@@@AEAViterator@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@@std@@@2@$0A@@std@@@std@@@Z; CMSMQTriggerSet::FindTriggerInMap(wchar_t *,R<CRuntimeTriggerInfo> &,std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CRuntimeTriggerInfo>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CRuntimeTriggerInfo>>>,0>>::iterator &)
0x180010f7c  mov     ebx, eax
0x180010f7e  test    eax, eax
0x180010f80  jz      short loc_180010F9B
0x180010f82  mov     edx, eax; int
0x180010f84  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x180010f89  nop
0x180010f8a  mov     rcx, [rsp+38h+arg_0]
0x180010f8f  call    ??$SafeRelease@VCRuntimeTriggerInfo@@@@YAXPEAVCRuntimeTriggerInfo@@@Z; SafeRelease<CRuntimeTriggerInfo>(CRuntimeTriggerInfo *)
0x180010f94  mov     eax, ebx
0x180010f96  jmp     loc_180011077
0x180010f9b  mov     rdx, [rdi+50h]; HKEY
0x180010f9f  mov     rbx, [rsp+38h+arg_0]
0x180010fa4  mov     rcx, rbx; this
0x180010fa7  call    ?Delete@CRuntimeTriggerInfo@@QEAA_NPEAUHKEY__@@@Z; CRuntimeTriggerInfo::Delete(HKEY__ *)
0x180010fac  test    al, al
0x180010fae  jnz     short loc_180010FFA
0x180010fb0  lea     rax, WPP_GLOBAL_Control
0x180010fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fbe  cmp     rcx, rax
0x180010fc1  jz      short loc_180010FE1
0x180010fc3  test    byte ptr [rcx+1Ch], 1
0x180010fc7  jz      short loc_180010FE1
0x180010fc9  mov     edx, 2Ch ; ','
0x180010fce  mov     r9, rsi
0x180010fd1  lea     r8, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids
0x180010fd8  mov     rcx, [rcx+10h]; LoggerHandle
0x180010fdc  call    WPP_SF_S
0x180010fe1  mov     edi, 0C00E0E15h
0x180010fe6  mov     edx, edi; int
0x180010fe8  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x180010fed  nop
0x180010fee  mov     rcx, rbx
0x180010ff1  call    ??$SafeRelease@VCRuntimeTriggerInfo@@@@YAXPEAVCRuntimeTriggerInfo@@@Z; SafeRelease<CRuntimeTriggerInfo>(CRuntimeTriggerInfo *)
0x180010ff6  mov     eax, edi
0x180010ff8  jmp     short loc_180011077
0x180010ffa  mov     rax, [rbx+820h]
0x180011001  test    rax, rax
0x180011004  jz      short loc_18001100B
0x180011006  mov     rdx, [rax]
0x180011009  jmp     short loc_18001100D
0x18001100b  xor     edx, edx; wchar_t *
0x18001100d  lea     rcx, [rdi+40h]; this
0x180011011  call    ?NotifyTriggerDeleted@CMSMQTriggerNotification@@IEAAJPEA_W@Z; CMSMQTriggerNotification::NotifyTriggerDeleted(wchar_t *)
0x180011016  lea     rcx, [rdi+4A0h]
0x18001101d  mov     r8, [rsp+38h+arg_10]
0x180011022  lea     rdx, [rsp+38h+arg_10]
0x180011027  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@@std@@@2@$0A@@std@@@std@@QEAA?AViterator@12@V312@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CRuntimeTriggerInfo>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CRuntimeTriggerInfo>>>,0>>::erase(std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CRuntimeTriggerInfo>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CRuntimeTriggerInfo>>>,0>>::iterator)
0x18001102c  mov     rax, [rbx+830h]
0x180011033  test    rax, rax
0x180011036  jz      short loc_18001103D
0x180011038  mov     rcx, [rax]
0x18001103b  jmp     short loc_18001103F
0x18001103d  xor     ecx, ecx
0x18001103f  mov     [rsp+38h+arg_10], rcx
0x180011044  lea     rdx, [rsp+38h+arg_10]; wchar_t **
0x180011049  lea     rcx, [rdi-8]; this
0x18001104d  call    ?ExistTriggersForQueue@CMSMQTriggerSet@@AEBA_NAEBQEA_W@Z; CMSMQTriggerSet::ExistTriggersForQueue(wchar_t * const &)
0x180011052  test    al, al
0x180011054  jnz     short loc_180011065
0x180011056  mov     r8d, 1; int
0x18001105c  mov     rdx, rbx; struct CRuntimeTriggerInfo *
0x18001105f  call    ?UpdateQueueAclForTrigger@CMSMQTriggerSet@@AEAAJPEAVCRuntimeTriggerInfo@@H@Z; CMSMQTriggerSet::UpdateQueueAclForTrigger(CRuntimeTriggerInfo *,int)
0x180011064  nop
0x180011065  mov     rcx, rbx
0x180011068  call    ??$SafeRelease@VCRuntimeTriggerInfo@@@@YAXPEAVCRuntimeTriggerInfo@@@Z; SafeRelease<CRuntimeTriggerInfo>(CRuntimeTriggerInfo *)
0x18001106d  nop
0x18001106e  xor     eax, eax
0x180011070  jmp     short loc_180011077
0x180011072  mov     eax, 0C00E0E06h
0x180011077  mov     rbx, [rsp+38h+arg_8]
0x18001107c  add     rsp, 20h
0x180011080  pop     r14
0x180011082  pop     rdi
0x180011083  pop     rsi
0x180011084  retn
```
