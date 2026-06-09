# CreateNewResourcesForWin11(_HCLUSTER *)

- ea: `0x1800231f4`
- end: `0x180023549`
- name: `?CreateNewResourcesForWin11@@YAKPEAU_HCLUSTER@@@Z`
- size: `853`
- prototype: `unsigned int __fastcall(struct _HCLUSTER *)`
- caller_count: `2`
- callee_count: `15`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18002ce30`
- `0x18002d2f0`

## callees

- `0x180014638`
- `0x18001ce04`
- `0x18001dbcc`
- `0x18001ef44`
- `0x18001fdac`
- `0x18001fe7c`
- `0x180022dbc`
- `0x1800231f4`
- `0x180023724`
- `0x180024a58`
- `0x180028f30`
- `0x18003c6d0`
- `0x18006c5e0`
- `0x18006d230`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002330c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002330c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023438`

## string_xrefs

- `0x180023245`: `Failed to get cluster common RO property - %d`
- `0x180023236`: `CreateNewResourcesForWin11`
- `0x18002337e`: `Failed to open cluster core group %d`
- `0x1800233fa`: `clusapi!CreateNewResourcesForWin11`
- `0x180023471`: `Resource %ws already present, could not create another instance.`
- `0x1800234aa`: `Failed to create sddc management resource '%ws' - %d`
- `0x1800234dd`: `Try to create dependency to health resource - status: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CreateNewResourcesForWin11(struct _HCLUSTER *a1)
{
  unsigned int S2DEnabledProperty; // eax
  DWORD LastError; // esi
  DWORD LocalizedObjectNames; // eax
  __int64 v6; // rax
  const wchar_t *v7; // rax
  struct _HGROUP *CoreClusterGroup; // rdi
  __int64 v9; // rax
  const wchar_t *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  struct _HRESOURCE *ClusterResource; // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // [rsp+28h] [rbp-70h]
  _QWORD v17[3]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v18[64]; // [rsp+58h] [rbp-40h] BYREF
  unsigned int v19; // [rsp+A8h] [rbp+10h] BYREF
  int v20; // [rsp+B0h] [rbp+18h] BYREF
  struct _HGROUP *v21; // [rsp+B8h] [rbp+20h] BYREF

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           a1,
                           a1) )
    return 6;
  v19 = 0;
  S2DEnabledProperty = GetS2DEnabledProperty(a1, &v19);
  LastError = S2DEnabledProperty;
  if ( S2DEnabledProperty )
    TraceMsg(
      2,
      0,
      L"CreateNewResourcesForWin11",
      7980,
      L"Failed to get cluster common RO property - %d",
      S2DEnabledProperty);
  if ( v19 )
  {
    std::map<unsigned long,std::wstring>::map<unsigned long,std::wstring>(v18);
    LocalizedObjectNames = LoadLocalizedObjectNames(10, v18);
    LastError = LocalizedObjectNames;
    if ( LocalizedObjectNames )
    {
      LODWORD(v16) = LocalizedObjectNames;
      TraceMsg(2, 0, L"CreateNewResourcesForWin11", 7992, L"Failed to load localized object names - %d", v16);
      std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v18);
      return LastError;
    }
    v19 = 14216;
    v6 = std::map<unsigned long,std::wstring>::operator[](v18, &v19);
    v7 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6);
    CoreClusterGroup = FindCoreClusterGroup(a1, v7);
    v17[0] = CoreClusterGroup;
    if ( (unsigned __int64)CoreClusterGroup - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      LODWORD(v16) = LastError;
      TraceMsg(
        2,
        0,
        L"CreateNewResourcesForWin11",
        8001,
        L"Failed to get sddc core group , will use cluster core group instead- %d",
        v16);
      v20 = 14200;
      v9 = std::map<unsigned long,std::wstring>::operator[](v18, &v20);
      v10 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v9);
      v21 = FindCoreClusterGroup(a1, v10);
      if ( (((unsigned __int64)v21 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LODWORD(v16) = LastError;
        TraceMsg(2, 0, L"CreateNewResourcesForWin11", 8005, L"Failed to open cluster core group %d", v16);
        cxl::AutoHandle<_HGROUP *,int,&int CloseClusterGroup(_HGROUP *),0>::Close(&v21);
        cxl::AutoHandle<_HGROUP *,int,&int CloseClusterGroup(_HGROUP *),0>::Close(v17);
        std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v18);
        return LastError;
      }
      cxl::AutoHandle<_HGROUP *,int,&int CloseClusterGroup(_HGROUP *),0>::Close(&v21);
    }
    v20 = 14215;
    v11 = std::map<unsigned long,std::wstring>::operator[](v18, &v20);
    v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v11);
    ClusterResource = (struct _HRESOURCE *)CreateClusterResourceEx(
                                             CoreClusterGroup,
                                             v12,
                                             L"SDDC Management",
                                             1,
                                             L"clusapi!CreateNewResourcesForWin11");
    v21 = ClusterResource;
    if ( (((unsigned __int64)ClusterResource + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      LODWORD(v16) = CreateDependencyToHealth(a1, CoreClusterGroup, ClusterResource);
      TraceMsg(
        4,
        0,
        L"CreateNewResourcesForWin11",
        8037,
        L"Try to create dependency to health resource - status: %d",
        v16);
      OnlineClusterResource(ClusterResource);
    }
    else
    {
      LastError = GetLastError();
      v19 = 14215;
      v14 = std::map<unsigned long,std::wstring>::operator[](v18, &v19);
      v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v14);
      if ( LastError == 5940 )
      {
        TraceMsg(
          4,
          0,
          L"CreateNewResourcesForWin11",
          8021,
          L"Resource %ws already present, could not create another instance.",
          v15);
        LastError = 0;
      }
      else
      {
        TraceMsg(
          2,
          0,
          L"CreateNewResourcesForWin11",
          8026,
          L"Failed to create sddc management resource '%ws' - %d",
          v15,
          LastError);
      }
    }
    cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(&v21);
    cxl::AutoHandle<_HGROUP *,int,&int CloseClusterGroup(_HGROUP *),0>::Close(v17);
    std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v18);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800231f4  push    rbx
0x1800231f6  push    rsi
0x1800231f7  push    rdi
0x1800231f8  push    r12
0x1800231fa  push    r14
0x1800231fc  sub     rsp, 70h
0x180023200  mov     r12, rcx
0x180023203  mov     rdx, rcx
0x180023206  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18002320b  test    al, al
0x18002320d  jnz     short loc_180023219
0x18002320f  mov     eax, 6
0x180023214  jmp     loc_18002353C
0x180023219  mov     [rsp+98h+arg_8], 0
0x180023224  lea     rdx, [rsp+98h+arg_8]; unsigned int *
0x18002322c  mov     rcx, r12; struct _HCLUSTER *
0x18002322f  call    ?GetS2DEnabledProperty@@YAKPEAU_HCLUSTER@@AEAK@Z; GetS2DEnabledProperty(_HCLUSTER *,ulong &)
0x180023234  mov     esi, eax
0x180023236  lea     r14, aCreatenewresou_0; "CreateNewResourcesForWin11"
0x18002323d  test    eax, eax
0x18002323f  jz      short loc_180023264
0x180023241  mov     dword ptr [rsp+98h+var_70], eax
0x180023245  lea     rax, aFailedToGetClu_2; "Failed to get cluster common RO propert"...
0x18002324c  mov     [rsp+98h+var_78], rax
0x180023251  mov     r9d, 1F2Ch
0x180023257  mov     r8, r14
0x18002325a  xor     edx, edx
0x18002325c  lea     ecx, [rdx+2]
0x18002325f  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180023264  cmp     [rsp+98h+arg_8], 0
0x18002326c  jbe     loc_180023529
0x180023272  lea     rcx, [rsp+98h+var_40]
0x180023277  call    ??0?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAA@XZ; std::map<ulong,std::wstring>::map<ulong,std::wstring>(void)
0x18002327c  nop
0x18002327d  mov     ecx, 0Ah
0x180023282  lea     rdx, [rsp+98h+var_40]
0x180023287  call    ?LoadLocalizedObjectNames@@YAKGAEAV?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@@Z; LoadLocalizedObjectNames(ushort,std::map<ulong,std::wstring> &)
0x18002328c  mov     esi, eax
0x18002328e  test    eax, eax
0x180023290  jz      short loc_1800232C7
0x180023292  mov     dword ptr [rsp+98h+var_70], eax
0x180023296  lea     rax, aFailedToLoadLo; "Failed to load localized object names -"...
0x18002329d  mov     [rsp+98h+var_78], rax
0x1800232a2  mov     r9d, 1F38h
0x1800232a8  mov     r8, r14
0x1800232ab  xor     edx, edx
0x1800232ad  lea     ecx, [rdx+2]
0x1800232b0  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800232b5  nop
0x1800232b6  lea     rcx, [rsp+98h+var_40]
0x1800232bb  call    ??1?$_Tree@V?$_Tmap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>(void)
0x1800232c0  mov     eax, esi
0x1800232c2  jmp     loc_18002353C
0x1800232c7  mov     [rsp+98h+arg_8], 3788h
0x1800232d2  lea     rdx, [rsp+98h+arg_8]
0x1800232da  lea     rcx, [rsp+98h+var_40]
0x1800232df  call    ??A?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAK@Z; std::map<ulong,std::wstring>::operator[](ulong &&)
0x1800232e4  mov     rcx, rax
0x1800232e7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800232ec  mov     rdx, rax; wchar_t *
0x1800232ef  mov     rcx, r12; hCluster
0x1800232f2  call    ?FindCoreClusterGroup@@YAPEAU_HGROUP@@PEAU_HCLUSTER@@PEB_W@Z; FindCoreClusterGroup(_HCLUSTER *,wchar_t const *)
0x1800232f7  mov     rdi, rax
0x1800232fa  mov     [rsp+98h+var_58], rax
0x1800232ff  dec     rax
0x180023302  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023306  jbe     loc_1800233D5
0x18002330c  call    cs:__imp_GetLastError
0x180023312  mov     esi, eax
0x180023314  mov     dword ptr [rsp+98h+var_70], eax
0x180023318  lea     rax, aFailedToGetSdd; "Failed to get sddc core group , will us"...
0x18002331f  mov     [rsp+98h+var_78], rax
0x180023324  mov     r9d, 1F41h
0x18002332a  mov     r8, r14
0x18002332d  xor     edx, edx
0x18002332f  lea     ecx, [rdx+2]
0x180023332  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180023337  mov     [rsp+98h+arg_10], 3778h
0x180023342  lea     rdx, [rsp+98h+arg_10]
0x18002334a  lea     rcx, [rsp+98h+var_40]
0x18002334f  call    ??A?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAK@Z; std::map<ulong,std::wstring>::operator[](ulong &&)
0x180023354  mov     rcx, rax
0x180023357  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002335c  mov     rdx, rax; wchar_t *
0x18002335f  mov     rcx, r12; hCluster
0x180023362  call    ?FindCoreClusterGroup@@YAPEAU_HGROUP@@PEAU_HCLUSTER@@PEB_W@Z; FindCoreClusterGroup(_HCLUSTER *,wchar_t const *)
0x180023367  mov     [rsp+98h+arg_18], rax
0x18002336f  inc     rax
0x180023372  test    rax, 0FFFFFFFFFFFFFFFEh
0x180023378  jnz     short loc_1800233C8
0x18002337a  mov     dword ptr [rsp+98h+var_70], esi
0x18002337e  lea     rax, aFailedToOpenCl_2; "Failed to open cluster core group %d"
0x180023385  mov     [rsp+98h+var_78], rax
0x18002338a  mov     r9d, 1F45h
0x180023390  mov     r8, r14
0x180023393  xor     edx, edx
0x180023395  lea     ecx, [rdx+2]
0x180023398  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18002339d  nop
0x18002339e  lea     rcx, [rsp+98h+arg_18]
0x1800233a6  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x1800233ab  nop
0x1800233ac  lea     rcx, [rsp+98h+var_58]
0x1800233b1  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x1800233b6  nop
0x1800233b7  lea     rcx, [rsp+98h+var_40]
0x1800233bc  call    ??1?$_Tree@V?$_Tmap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>(void)
0x1800233c1  mov     eax, esi
0x1800233c3  jmp     loc_18002353C
0x1800233c8  lea     rcx, [rsp+98h+arg_18]
0x1800233d0  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x1800233d5  mov     [rsp+98h+arg_10], 3787h
0x1800233e0  lea     rdx, [rsp+98h+arg_10]
0x1800233e8  lea     rcx, [rsp+98h+var_40]
0x1800233ed  call    ??A?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAK@Z; std::map<ulong,std::wstring>::operator[](ulong &&)
0x1800233f2  mov     rcx, rax
0x1800233f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800233fa  lea     rcx, aClusapiCreaten_0; "clusapi!CreateNewResourcesForWin11"
0x180023401  mov     [rsp+98h+var_78], rcx
0x180023406  mov     r9d, 1
0x18002340c  lea     r8, aSddcManagement; "SDDC Management"
0x180023413  mov     rdx, rax
0x180023416  mov     rcx, rdi
0x180023419  call    CreateClusterResourceEx
0x18002341e  mov     rbx, rax
0x180023421  mov     [rsp+98h+arg_18], rax
0x180023429  inc     rax
0x18002342c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180023432  jnz     loc_1800234CB
0x180023438  call    cs:__imp_GetLastError
0x18002343e  mov     esi, eax
0x180023440  mov     [rsp+98h+arg_8], 3787h
0x18002344b  lea     rdx, [rsp+98h+arg_8]
0x180023453  lea     rcx, [rsp+98h+var_40]
0x180023458  cmp     eax, 1734h
0x18002345d  jnz     short loc_180023494
0x18002345f  call    ??A?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAK@Z; std::map<ulong,std::wstring>::operator[](ulong &&)
0x180023464  mov     rcx, rax
0x180023467  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002346c  mov     [rsp+98h+var_70], rax
0x180023471  lea     rax, aResourceWsAlre; "Resource %ws already present, could not"...
0x180023478  mov     [rsp+98h+var_78], rax
0x18002347d  mov     r9d, 1F55h
0x180023483  mov     r8, r14
0x180023486  xor     edx, edx
0x180023488  lea     ecx, [rdx+4]
0x18002348b  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180023490  xor     esi, esi
0x180023492  jmp     short loc_180023505
0x180023494  call    ??A?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAK@Z; std::map<ulong,std::wstring>::operator[](ulong &&)
0x180023499  mov     rcx, rax
0x18002349c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800234a1  mov     [rsp+98h+var_68], esi
0x1800234a5  mov     [rsp+98h+var_70], rax
0x1800234aa  lea     rax, aFailedToCreate; "Failed to create sddc management resour"...
0x1800234b1  mov     [rsp+98h+var_78], rax
0x1800234b6  mov     r9d, 1F5Ah
0x1800234bc  mov     r8, r14
0x1800234bf  xor     edx, edx
0x1800234c1  lea     ecx, [rdx+2]
0x1800234c4  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800234c9  jmp     short loc_180023505
0x1800234cb  mov     r8, rbx; struct _HRESOURCE *
0x1800234ce  mov     rdx, rdi; struct _HGROUP *
0x1800234d1  mov     rcx, r12; struct _HCLUSTER *
0x1800234d4  call    ?CreateDependencyToHealth@@YAKPEAU_HCLUSTER@@PEAU_HGROUP@@PEAU_HRESOURCE@@@Z; CreateDependencyToHealth(_HCLUSTER *,_HGROUP *,_HRESOURCE *)
0x1800234d9  mov     dword ptr [rsp+98h+var_70], eax
0x1800234dd  lea     rax, aTryToCreateDep; "Try to create dependency to health reso"...
0x1800234e4  mov     [rsp+98h+var_78], rax
0x1800234e9  mov     r9d, 1F65h
0x1800234ef  mov     r8, r14
0x1800234f2  xor     edx, edx
0x1800234f4  lea     ecx, [rdx+4]
0x1800234f7  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800234fc  mov     rcx, rbx; hResource
0x1800234ff  call    OnlineClusterResource
0x180023504  nop
0x180023505  lea     rcx, [rsp+98h+arg_18]
0x18002350d  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x180023512  nop
0x180023513  lea     rcx, [rsp+98h+var_58]
0x180023518  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x18002351d  nop
0x18002351e  lea     rcx, [rsp+98h+var_40]
0x180023523  call    ??1?$_Tree@V?$_Tmap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>(void)
0x180023528  nop
0x180023529  jmp     short loc_18002353A
0x18002352b  jmp     short loc_180023533
0x18002352d  jmp     short loc_180023533
0x18002352f  jmp     short loc_180023533
0x180023531  jmp     short $+2
0x180023533  mov     esi, [rsp+98h+arg_8]
0x18002353a  mov     eax, esi
0x18002353c  add     rsp, 70h
0x180023540  pop     r14
0x180023542  pop     r12
0x180023544  pop     rdi
0x180023545  pop     rsi
0x180023546  pop     rbx
0x180023547  retn
```
