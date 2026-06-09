# CreateNewResourcesForWin10(_HCLUSTER *)

- ea: `0x180022f94`
- end: `0x1800231ee`
- name: `?CreateNewResourcesForWin10@@YAKPEAU_HCLUSTER@@@Z`
- size: `602`
- prototype: `unsigned int __fastcall(struct _HCLUSTER *)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, registry_config`

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
- `0x180022f94`
- `0x180023724`
- `0x180028f30`
- `0x18003c6d0`
- `0x18006c5e0`
- `0x18006d230`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023130`

## string_xrefs

- `0x180023008`: `CreateNewResourcesForWin10`
- `0x1800230c6`: `CreateNewResourcesForWin10`
- `0x18002317b`: `CreateNewResourcesForWin10`
- `0x1800231a6`: `CreateNewResourcesForWin10`
- `0x1800230b4`: `Failed to open core group - %d`
- `0x180023101`: `clusapi!CreateNewResourcesForWin10`
- `0x180023169`: `Resource %s already present, could not create another instance.`
- `0x180023194`: `Failed to create storage qos resource - %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateNewResourcesForWin10(struct _HCLUSTER *a1)
{
  struct _HCLUSTER *v1; // rbx
  DWORD LocalizedObjectNames; // eax
  DWORD v4; // edi
  __int64 v5; // rax
  const wchar_t *v6; // rax
  struct _HGROUP *CoreClusterGroup; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  struct _HRESOURCE *ClusterResource; // rax
  DWORD LastError; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  struct _HRESOURCE *v14; // [rsp+30h] [rbp-48h] BYREF
  cxl::Exception *v15; // [rsp+38h] [rbp-40h] BYREF
  std::system_error *v16; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v17[48]; // [rsp+48h] [rbp-30h] BYREF
  int v19; // [rsp+88h] [rbp+10h] BYREF
  unsigned int WinError; // [rsp+90h] [rbp+18h] BYREF
  struct _HGROUP *v21; // [rsp+98h] [rbp+20h] BYREF

  v1 = a1;
  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           a1,
                           a1) )
    return 6;
  LODWORD(v21) = 0;
  std::map<unsigned long,std::wstring>::map<unsigned long,std::wstring>(v17);
  try
  {
    LOBYTE(v19) = 1;
    LocalizedObjectNames = LoadLocalizedObjectNames(9, v17);
  }
  catch ( cxl::Exception *v15 )
  {
    WinError = cxl::ErrorCode::GetWinError((cxl::Exception *)((char *)v15 + 88));
    goto LABEL_7;
  }
  catch ( std::system_error *v16 )
  {
    WinError = *((_DWORD *)v16 + 6);
    goto LABEL_7;
  }
  catch ( std::bad_alloc )
  {
    WinError = 14;
    goto LABEL_7;
  }
  catch ( std::exception )
  {
    WinError = 1359;
    goto LABEL_7;
  }
  catch ( ... )
  {
    WinError = 1359;
LABEL_7:
    if ( !(_BYTE)v19 )
    {
      v1 = a1;
      v4 = (unsigned int)v21;
LABEL_10:
      v19 = 14200;
      v5 = std::map<unsigned long,std::wstring>::operator[](v17, &v19);
      v6 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v5);
      CoreClusterGroup = FindCoreClusterGroup(v1, v6);
      v21 = CoreClusterGroup;
      if ( (((unsigned __int64)CoreClusterGroup + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        WinError = 14214;
        v8 = std::map<unsigned long,std::wstring>::operator[](v17, &WinError);
        v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v8);
        ClusterResource = (struct _HRESOURCE *)CreateClusterResourceEx(
                                                 CoreClusterGroup,
                                                 v9,
                                                 L"Storage QoS Policy Manager",
                                                 0,
                                                 L"clusapi!CreateNewResourcesForWin10");
        v14 = ClusterResource;
        if ( ClusterResource )
        {
          OnlineClusterResource(ClusterResource);
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError == 5940 )
          {
            v19 = 14214;
            v12 = std::map<unsigned long,std::wstring>::operator[](v17, &v19);
            v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v12);
            TraceMsg(
              4,
              0,
              L"CreateNewResourcesForWin10",
              7759,
              L"Resource %s already present, could not create another instance.",
              v13,
              v14);
            v4 = 0;
          }
          else
          {
            TraceMsg(
              2,
              0,
              L"CreateNewResourcesForWin10",
              7764,
              L"Failed to create storage qos resource - %d",
              LastError,
              v14);
          }
        }
        cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(&v14);
      }
      else
      {
        v4 = GetLastError();
        TraceMsg(2, 0, L"CreateNewResourcesForWin10", 7744, L"Failed to open core group - %d", v4);
      }
      cxl::AutoHandle<_HGROUP *,int,&int CloseClusterGroup(_HGROUP *),0>::Close(&v21);
      goto LABEL_19;
    }
    v4 = WinError;
LABEL_19:
    std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v17);
    return v4;
  }
  v4 = LocalizedObjectNames;
  LODWORD(v21) = LocalizedObjectNames;
  if ( LocalizedObjectNames )
  {
    TraceMsg(
      2,
      0,
      L"CreateNewResourcesForWin10",
      7735,
      L"Failed to load localized object names - %d",
      LocalizedObjectNames);
    std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v17);
    return v4;
  }
  LOBYTE(v19) = 0;
  goto LABEL_10;
}

```

## disassembly

```asm
0x180022f94  mov     [rsp+arg_0], rcx
0x180022f99  push    rbx
0x180022f9a  push    rdi
0x180022f9b  sub     rsp, 68h
0x180022f9f  mov     rbx, rcx
0x180022fa2  mov     rdx, rcx
0x180022fa5  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x180022faa  test    al, al
0x180022fac  jnz     short loc_180022FB8
0x180022fae  mov     eax, 6
0x180022fb3  jmp     loc_1800231E7
0x180022fb8  mov     dword ptr [rsp+78h+arg_18], 0
0x180022fc3  lea     rcx, [rsp+78h+var_30]
0x180022fc8  call    ??0?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAA@XZ; std::map<ulong,std::wstring>::map<ulong,std::wstring>(void)
0x180022fcd  nop
0x180022fce  mov     byte ptr [rsp+78h+arg_8], 1
0x180022fd6  mov     ecx, 9
0x180022fdb  lea     rdx, [rsp+78h+var_30]
0x180022fe0  call    ?LoadLocalizedObjectNames@@YAKGAEAV?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@@Z; LoadLocalizedObjectNames(ushort,std::map<ulong,std::wstring> &)
0x180022fe5  mov     edi, eax
0x180022fe7  mov     dword ptr [rsp+78h+arg_18], eax
0x180022fee  test    eax, eax
0x180022ff0  jz      short loc_18002302B
0x180022ff2  mov     dword ptr [rsp+78h+var_50], eax
0x180022ff6  lea     rax, aFailedToLoadLo; "Failed to load localized object names -"...
0x180022ffd  mov     [rsp+78h+var_58], rax
0x180023002  mov     r9d, 1E37h
0x180023008  lea     r8, aCreatenewresou; "CreateNewResourcesForWin10"
0x18002300f  xor     edx, edx
0x180023011  lea     ecx, [rdx+2]
0x180023014  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180023019  nop
0x18002301a  lea     rcx, [rsp+78h+var_30]
0x18002301f  call    ??1?$_Tree@V?$_Tmap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>(void)
0x180023024  mov     eax, edi
0x180023026  jmp     loc_1800231E7
0x18002302b  mov     byte ptr [rsp+78h+arg_8], 0
0x180023033  jmp     short loc_180023062
0x180023035  jmp     short loc_18002303D
0x180023037  jmp     short loc_18002303D
0x180023039  jmp     short loc_18002303D
0x18002303b  jmp     short $+2
0x18002303d  cmp     byte ptr [rsp+78h+arg_8], 0
0x180023045  jz      short loc_180023053
0x180023047  mov     edi, [rsp+78h+arg_10]
0x18002304e  jmp     loc_1800231DB
0x180023053  mov     rbx, [rsp+78h+arg_0]
0x18002305b  mov     edi, dword ptr [rsp+78h+arg_18]
0x180023062  mov     [rsp+78h+arg_8], 3778h
0x18002306d  lea     rdx, [rsp+78h+arg_8]
0x180023075  lea     rcx, [rsp+78h+var_30]
0x18002307a  call    ??A?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAK@Z; std::map<ulong,std::wstring>::operator[](ulong &&)
0x18002307f  mov     rcx, rax
0x180023082  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180023087  mov     rdx, rax; wchar_t *
0x18002308a  mov     rcx, rbx; hCluster
0x18002308d  call    ?FindCoreClusterGroup@@YAPEAU_HGROUP@@PEAU_HCLUSTER@@PEB_W@Z; FindCoreClusterGroup(_HCLUSTER *,wchar_t const *)
0x180023092  mov     rbx, rax
0x180023095  mov     [rsp+78h+arg_18], rax
0x18002309d  inc     rax
0x1800230a0  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800230a6  jnz     short loc_1800230DC
0x1800230a8  call    cs:__imp_GetLastError
0x1800230ae  mov     edi, eax
0x1800230b0  mov     dword ptr [rsp+78h+var_50], eax
0x1800230b4  lea     rax, aFailedToOpenCo; "Failed to open core group - %d"
0x1800230bb  mov     [rsp+78h+var_58], rax
0x1800230c0  mov     r9d, 1E40h
0x1800230c6  lea     r8, aCreatenewresou; "CreateNewResourcesForWin10"
0x1800230cd  xor     edx, edx
0x1800230cf  lea     ecx, [rdx+2]
0x1800230d2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800230d7  jmp     loc_1800231CD
0x1800230dc  mov     [rsp+78h+arg_10], 3786h
0x1800230e7  lea     rdx, [rsp+78h+arg_10]
0x1800230ef  lea     rcx, [rsp+78h+var_30]
0x1800230f4  call    ??A?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAK@Z; std::map<ulong,std::wstring>::operator[](ulong &&)
0x1800230f9  mov     rcx, rax
0x1800230fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180023101  lea     rcx, aClusapiCreaten; "clusapi!CreateNewResourcesForWin10"
0x180023108  mov     [rsp+78h+var_58], rcx
0x18002310d  xor     r9d, r9d
0x180023110  lea     r8, aStorageQosPoli; "Storage QoS Policy Manager"
0x180023117  mov     rdx, rax
0x18002311a  mov     rcx, rbx
0x18002311d  call    CreateClusterResourceEx
0x180023122  mov     [rsp+78h+var_48], rax
0x180023127  test    rax, rax
0x18002312a  jnz     loc_1800231B9
0x180023130  call    cs:__imp_GetLastError
0x180023136  mov     edi, eax
0x180023138  cmp     eax, 1734h
0x18002313d  jnz     short loc_180023190
0x18002313f  mov     [rsp+78h+arg_8], 3786h
0x18002314a  lea     rdx, [rsp+78h+arg_8]
0x180023152  lea     rcx, [rsp+78h+var_30]
0x180023157  call    ??A?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAK@Z; std::map<ulong,std::wstring>::operator[](ulong &&)
0x18002315c  mov     rcx, rax
0x18002315f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180023164  mov     [rsp+78h+var_50], rax
0x180023169  lea     rax, aResourceSAlrea; "Resource %s already present, could not "...
0x180023170  mov     [rsp+78h+var_58], rax
0x180023175  mov     r9d, 1E4Fh
0x18002317b  lea     r8, aCreatenewresou; "CreateNewResourcesForWin10"
0x180023182  xor     edx, edx
0x180023184  lea     ecx, [rdx+4]
0x180023187  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18002318c  xor     edi, edi
0x18002318e  jmp     short loc_1800231C2
0x180023190  mov     dword ptr [rsp+78h+var_50], eax
0x180023194  lea     rax, aFailedToCreate_16; "Failed to create storage qos resource -"...
0x18002319b  mov     [rsp+78h+var_58], rax
0x1800231a0  mov     r9d, 1E54h
0x1800231a6  lea     r8, aCreatenewresou; "CreateNewResourcesForWin10"
0x1800231ad  xor     edx, edx
0x1800231af  lea     ecx, [rdx+2]
0x1800231b2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800231b7  jmp     short loc_1800231C2
0x1800231b9  mov     rcx, rax; hResource
0x1800231bc  call    OnlineClusterResource
0x1800231c1  nop
0x1800231c2  lea     rcx, [rsp+78h+var_48]
0x1800231c7  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x1800231cc  nop
0x1800231cd  lea     rcx, [rsp+78h+arg_18]
0x1800231d5  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x1800231da  nop
0x1800231db  lea     rcx, [rsp+78h+var_30]
0x1800231e0  call    ??1?$_Tree@V?$_Tmap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>(void)
0x1800231e5  mov     eax, edi
0x1800231e7  add     rsp, 68h
0x1800231eb  pop     rdi
0x1800231ec  pop     rbx
0x1800231ed  retn
```
