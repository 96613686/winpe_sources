# OpenClusterCapacityNodeById(_HCLUSTER *,ulong)

- ea: `0x18008e110`
- end: `0x18008e505`
- name: `?OpenClusterCapacityNodeById@@YAPEAU_HNODE@@PEAU_HCLUSTER@@K@Z`
- size: `1013`
- prototype: `struct _HNODE *__fastcall(struct _HCLUSTER *, unsigned int)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x180058b90`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x180014638`
- `0x18001cc08`
- `0x18001cc2c`
- `0x18001cf54`
- `0x18001fe48`
- `0x18001fe7c`
- `0x180028f30`
- `0x180029410`
- `0x180029578`
- `0x1800299b0`
- `0x18003180c`
- `0x1800389b0`
- `0x18003d5b8`
- `0x180057f5c`
- `0x18006f910`
- `0x18008e110`
- `0x180094ce8`
- `0x180095144`
- `0x180096894`
- `0x180096b88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e3ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e3ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008e426`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008e482`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008e4c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008e4d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008e426`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008e482`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008e4c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008e4d9`

## string_xrefs

- `0x18008e3bb`: `OpenClusterNode failed with status:%d`
- `0x18008e48d`: `Can't find Compute Fabric Resource.`
- `0x18008e319`: `Execute Compute Fabric Resource control failed`
- `0x18008e152`: `OpenCapacityNodeById Enter::NodeId:%d`
- `0x18008e164`: `OpenClusterCapacityNodeById`
- `0x18008e305`: `OpenClusterCapacityNodeById`
- `0x18008e3cd`: `OpenClusterCapacityNodeById`
- `0x18008e2bc`: `clusapi!OpenClusterCapacityNodeById`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
struct _HNODE *__fastcall OpenClusterCapacityNodeById(struct _HCLUSTER *a1, DWORD a2)
{
  __int64 v4; // rcx
  DWORD v6; // ecx
  struct _HRESOURCE *v7; // rbx
  DWORD v8; // eax
  wchar_t *v9; // rax
  struct _HNODE *v10; // rbx
  struct _HNODE *result; // rax
  __int64 v12; // [rsp+28h] [rbp-350h]
  DWORD WinError; // [rsp+40h] [rbp-338h] BYREF
  DWORD dwErrCode; // [rsp+48h] [rbp-330h] BYREF
  _QWORD v15[2]; // [rsp+50h] [rbp-328h] BYREF
  _QWORD v16[2]; // [rsp+60h] [rbp-318h] BYREF
  char v17; // [rsp+70h] [rbp-308h]
  _QWORD v18[3]; // [rsp+78h] [rbp-300h] BYREF
  _BYTE v19[40]; // [rsp+90h] [rbp-2E8h] BYREF
  cxl::Exception *v20; // [rsp+B8h] [rbp-2C0h] BYREF
  std::system_error *v21; // [rsp+C0h] [rbp-2B8h] BYREF
  _QWORD v22[4]; // [rsp+C8h] [rbp-2B0h] BYREF
  _BYTE v23[32]; // [rsp+E8h] [rbp-290h] BYREF
  _BYTE v24[40]; // [rsp+108h] [rbp-270h] BYREF
  _BYTE pExceptionObject[272]; // [rsp+130h] [rbp-248h] BYREF
  _BYTE v26[272]; // [rsp+240h] [rbp-138h] BYREF

  dwErrCode = 0;
  v16[1] = &dwErrCode;
  v17 = 0;
  TraceMsg(4, 11, L"OpenClusterCapacityNodeById", 1109, L"OpenCapacityNodeById Enter::NodeId:%d", a2);
  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           v4,
                           a1) )
  {
    v6 = 87;
    dwErrCode = 87;
    goto LABEL_12;
  }
  try
  {
    v7 = OpenClusterResourceByResType(a1, L"Fabric Controller Manager");
    v16[0] = v7;
    if ( (unsigned __int64)v7 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)v26, 5007, L"Can't find Compute Fabric Resource.");
      throw (ClusRtl::ExceptionMsg *)v26;
    }
    cxl::PropertyList::PropertyList((cxl::PropertyList *)v19);
    std::wstring::wstring(v23, L"GetNodeName");
    std::wstring::wstring(v22, L"Operation");
    WinError = 65539;
    v15[0] = v23;
    v15[1] = &WinError;
    cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(v19, v22, v15);
    std::wstring::_Tidy_deallocate(v22);
    std::wstring::_Tidy_deallocate(v23);
    std::wstring::wstring(v23, L"CapacityNodeID");
    WinError = a2;
    LODWORD(v15[0]) = 65538;
    v22[0] = &WinError;
    v22[1] = v15;
    cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v19, v23, v22);
    std::wstring::_Tidy_deallocate(v23);
    std::vector<unsigned char>::vector<unsigned char>(v18, 520);
    v8 = ExecuteClusterResourceControlEx(
           (_DWORD)v7,
           20983370,
           (unsigned int)v19,
           (unsigned int)v18,
           (__int64)L"clusapi!OpenClusterCapacityNodeById");
    dwErrCode = v8;
    if ( v8 )
    {
      TraceMsg(
        2,
        11,
        L"OpenClusterCapacityNodeById",
        1138,
        L"FCM resource control ('%ws') failed, status = %d",
        L"GetNodeName",
        v8);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        dwErrCode,
        L"Execute Compute Fabric Resource control failed");
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
    std::wstring::wstring(v24);
    std::wstring::assign(v24, v18[0], (v18[1] - v18[0]) >> 1);
    v9 = (wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v24);
    v10 = OpenClusterNodeImpl(a1, v9, 0x10000000, 0, 1);
    v15[0] = v10;
    if ( v10 )
    {
      v15[0] = 0;
      cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(v15);
      std::wstring::_Tidy_deallocate(v24);
      std::vector<unsigned char>::_Tidy(v18);
      cxl::PropertyList::~PropertyList((cxl::PropertyList *)v19);
      cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(v16);
      v17 = 1;
      SetLastError(dwErrCode);
      result = v10;
    }
    else
    {
      dwErrCode = GetLastError();
      LODWORD(v12) = dwErrCode;
      TraceMsg(2, 11, L"OpenClusterCapacityNodeById", 1148, L"OpenClusterNode failed with status:%d", v12);
      cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(v15);
      std::wstring::_Tidy_deallocate(v24);
      std::vector<unsigned char>::_Tidy(v18);
      cxl::PropertyList::~PropertyList((cxl::PropertyList *)v19);
      cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(v16);
      v17 = 1;
      SetLastError(dwErrCode);
      result = 0;
    }
  }
  catch ( cxl::Exception *v20 )
  {
    WinError = cxl::ErrorCode::GetWinError((cxl::Exception *)((char *)v20 + 88));
    goto LABEL_10;
  }
  catch ( std::system_error *v21 )
  {
    WinError = *((_DWORD *)v21 + 6);
    goto LABEL_10;
  }
  catch ( std::bad_alloc )
  {
    WinError = 14;
    goto LABEL_10;
  }
  catch ( std::exception )
  {
    WinError = 1359;
    goto LABEL_10;
  }
  catch ( ... )
  {
    WinError = 1359;
LABEL_10:
    SetLastError(WinError);
    if ( v17 )
      return 0;
    v6 = dwErrCode;
LABEL_12:
    SetLastError(v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18008e110  mov     [rsp+arg_10], rbx
0x18008e115  push    rsi
0x18008e116  push    rdi
0x18008e117  push    r14
0x18008e119  sub     rsp, 360h
0x18008e120  mov     rax, cs:__security_cookie
0x18008e127  xor     rax, rsp
0x18008e12a  mov     [rsp+378h+var_28], rax
0x18008e132  mov     edi, edx
0x18008e134  mov     rsi, rcx
0x18008e137  mov     [rsp+378h+dwErrCode], 0
0x18008e13f  lea     rax, [rsp+378h+dwErrCode]
0x18008e144  mov     [rsp+378h+var_310], rax
0x18008e149  mov     [rsp+378h+var_308], 0
0x18008e14e  mov     dword ptr [rsp+378h+var_350], edx
0x18008e152  lea     rax, aOpencapacityno; "OpenCapacityNodeById Enter::NodeId:%d"
0x18008e159  mov     qword ptr [rsp+378h+var_358], rax
0x18008e15e  mov     r9d, 455h
0x18008e164  lea     r8, aOpenclustercap; "OpenClusterCapacityNodeById"
0x18008e16b  mov     edx, 0Bh
0x18008e170  lea     ecx, [rdx-7]
0x18008e173  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008e178  mov     rdx, rsi
0x18008e17b  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18008e180  test    al, al
0x18008e182  jnz     short loc_18008E192
0x18008e184  mov     ecx, 57h ; 'W'
0x18008e189  mov     [rsp+378h+dwErrCode], ecx
0x18008e18d  jmp     loc_18008E4D9
0x18008e192  lea     rdx, aFabricControll; "Fabric Controller Manager"
0x18008e199  mov     rcx, rsi; struct _HCLUSTER *
0x18008e19c  call    ?OpenClusterResourceByResType@@YAPEAU_HRESOURCE@@PEAU_HCLUSTER@@PEB_W@Z; OpenClusterResourceByResType(_HCLUSTER *,wchar_t const *)
0x18008e1a1  mov     rbx, rax
0x18008e1a4  mov     [rsp+378h+var_318], rax
0x18008e1a9  dec     rax
0x18008e1ac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008e1b0  ja      loc_18008E48D
0x18008e1b6  lea     rcx, [rsp+378h+var_2E8]; this
0x18008e1be  call    ??0PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::PropertyList(void)
0x18008e1c3  nop
0x18008e1c4  lea     r14, aGetnodename; "GetNodeName"
0x18008e1cb  mov     rdx, r14
0x18008e1ce  lea     rcx, [rsp+378h+var_290]
0x18008e1d6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008e1db  nop
0x18008e1dc  lea     rdx, aOperation; "Operation"
0x18008e1e3  lea     rcx, [rsp+378h+var_2B0]
0x18008e1eb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008e1f0  nop
0x18008e1f1  mov     [rsp+378h+var_338], 10003h
0x18008e1f9  lea     rax, [rsp+378h+var_290]
0x18008e201  mov     [rsp+378h+var_328], rax
0x18008e206  lea     rax, [rsp+378h+var_338]
0x18008e20b  mov     [rsp+378h+var_320], rax
0x18008e210  lea     r8, [rsp+378h+var_328]
0x18008e215  lea     rdx, [rsp+378h+var_2B0]
0x18008e21d  lea     rcx, [rsp+378h+var_2E8]
0x18008e225  call    ??$AddPropertyT@V_lambda_5d897758465b3281188928bc355bf98e_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_5d897758465b3281188928bc355bf98e_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(std::wstring const &,_lambda_5d897758465b3281188928bc355bf98e_ const &)
0x18008e22a  nop
0x18008e22b  lea     rcx, [rsp+378h+var_2B0]
0x18008e233  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008e238  nop
0x18008e239  lea     rcx, [rsp+378h+var_290]
0x18008e241  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008e246  lea     rdx, aCapacitynodeid; "CapacityNodeID"
0x18008e24d  lea     rcx, [rsp+378h+var_290]
0x18008e255  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008e25a  nop
0x18008e25b  mov     [rsp+378h+var_338], edi
0x18008e25f  mov     dword ptr [rsp+378h+var_328], 10002h
0x18008e267  lea     rax, [rsp+378h+var_338]
0x18008e26c  mov     [rsp+378h+var_2B0], rax
0x18008e274  lea     rax, [rsp+378h+var_328]
0x18008e279  mov     [rsp+378h+var_2A8], rax
0x18008e281  lea     r8, [rsp+378h+var_2B0]
0x18008e289  lea     rdx, [rsp+378h+var_290]
0x18008e291  lea     rcx, [rsp+378h+var_2E8]
0x18008e299  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x18008e29e  nop
0x18008e29f  lea     rcx, [rsp+378h+var_290]
0x18008e2a7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008e2ac  mov     edx, 208h
0x18008e2b1  lea     rcx, [rsp+378h+var_300]
0x18008e2b6  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18008e2bb  nop
0x18008e2bc  lea     rax, aClusapiOpenclu; "clusapi!OpenClusterCapacityNodeById"
0x18008e2c3  mov     qword ptr [rsp+378h+var_358], rax
0x18008e2c8  lea     r9, [rsp+378h+var_300]
0x18008e2cd  lea     r8, [rsp+378h+var_2E8]
0x18008e2d5  mov     edx, 1402E4Ah
0x18008e2da  mov     rcx, rbx
0x18008e2dd  call    ?ExecuteClusterResourceControlEx@@YAKPEAU_HRESOURCE@@KAEAVPropertyList@cxl@@AEAV?$vector@EV?$allocator@E@std@@@std@@PEB_W@Z; ExecuteClusterResourceControlEx(_HRESOURCE *,ulong,cxl::PropertyList &,std::vector<uchar> &,wchar_t const *)
0x18008e2e2  mov     [rsp+378h+dwErrCode], eax
0x18008e2e6  test    eax, eax
0x18008e2e8  jz      short loc_18008E345
0x18008e2ea  mov     [rsp+378h+var_348], eax
0x18008e2ee  mov     [rsp+378h+var_350], r14
0x18008e2f3  lea     rax, aFcmResourceCon_0; "FCM resource control ('%ws') failed, st"...
0x18008e2fa  mov     qword ptr [rsp+378h+var_358], rax
0x18008e2ff  mov     r9d, 472h
0x18008e305  lea     r8, aOpenclustercap; "OpenClusterCapacityNodeById"
0x18008e30c  mov     edx, 0Bh
0x18008e311  lea     ecx, [rdx-9]
0x18008e314  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008e319  lea     r8, aExecuteCompute; "Execute Compute Fabric Resource control"...
0x18008e320  mov     edx, [rsp+378h+dwErrCode]; int
0x18008e324  lea     rcx, [rsp+378h+pExceptionObject]; this
0x18008e32c  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x18008e331  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18008e338  lea     rcx, [rsp+378h+pExceptionObject]; pExceptionObject
0x18008e340  call    _CxxThrowException_0
0x18008e345  lea     rcx, [rsp+378h+var_270]
0x18008e34d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008e352  nop
0x18008e353  mov     rdx, [rsp+378h+var_300]
0x18008e358  mov     r8, [rsp+378h+var_2F8]
0x18008e360  sub     r8, rdx
0x18008e363  shr     r8, 1
0x18008e366  lea     rcx, [rsp+378h+var_270]
0x18008e36e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x18008e373  lea     rcx, [rsp+378h+var_270]
0x18008e37b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18008e380  mov     rdx, rax; wchar_t *
0x18008e383  mov     [rsp+378h+var_358], 1; int
0x18008e38b  xor     r9d, r9d; unsigned int *
0x18008e38e  mov     r8d, 10000000h; unsigned int
0x18008e394  mov     rcx, rsi; struct _HCLUSTER *
0x18008e397  call    ?OpenClusterNodeImpl@@YAPEAU_HNODE@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z; OpenClusterNodeImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)
0x18008e39c  mov     rbx, rax
0x18008e39f  mov     [rsp+378h+var_328], rax
0x18008e3a4  test    rax, rax
0x18008e3a7  jnz     loc_18008E433
0x18008e3ad  call    cs:__imp_GetLastError
0x18008e3b3  mov     [rsp+378h+dwErrCode], eax
0x18008e3b7  mov     dword ptr [rsp+378h+var_350], eax
0x18008e3bb  lea     rax, aOpenclusternod_2; "OpenClusterNode failed with status:%d"
0x18008e3c2  mov     qword ptr [rsp+378h+var_358], rax
0x18008e3c7  mov     r9d, 47Ch
0x18008e3cd  lea     r8, aOpenclustercap; "OpenClusterCapacityNodeById"
0x18008e3d4  lea     edx, [rbx+0Bh]
0x18008e3d7  lea     ecx, [rbx+2]
0x18008e3da  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008e3df  nop
0x18008e3e0  lea     rcx, [rsp+378h+var_328]
0x18008e3e5  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x18008e3ea  nop
0x18008e3eb  lea     rcx, [rsp+378h+var_270]
0x18008e3f3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008e3f8  nop
0x18008e3f9  lea     rcx, [rsp+378h+var_300]
0x18008e3fe  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008e403  nop
0x18008e404  lea     rcx, [rsp+378h+var_2E8]; this
0x18008e40c  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x18008e411  nop
0x18008e412  lea     rcx, [rsp+378h+var_318]
0x18008e417  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x18008e41c  nop
0x18008e41d  mov     [rsp+378h+var_308], 1
0x18008e422  mov     ecx, [rsp+378h+dwErrCode]; dwErrCode
0x18008e426  call    cs:__imp_SetLastError
0x18008e42c  xor     eax, eax
0x18008e42e  jmp     loc_18008E4E1
0x18008e433  mov     [rsp+378h+var_328], 0
0x18008e43c  lea     rcx, [rsp+378h+var_328]
0x18008e441  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x18008e446  nop
0x18008e447  lea     rcx, [rsp+378h+var_270]
0x18008e44f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008e454  nop
0x18008e455  lea     rcx, [rsp+378h+var_300]
0x18008e45a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008e45f  nop
0x18008e460  lea     rcx, [rsp+378h+var_2E8]; this
0x18008e468  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x18008e46d  nop
0x18008e46e  lea     rcx, [rsp+378h+var_318]
0x18008e473  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x18008e478  nop
0x18008e479  mov     [rsp+378h+var_308], 1
0x18008e47e  mov     ecx, [rsp+378h+dwErrCode]; dwErrCode
0x18008e482  call    cs:__imp_SetLastError
0x18008e488  mov     rax, rbx
0x18008e48b  jmp     short loc_18008E4E1
0x18008e48d  lea     r8, aCanTFindComput; "Can't find Compute Fabric Resource."
0x18008e494  mov     edx, 138Fh; int
0x18008e499  lea     rcx, [rsp+378h+var_138]; this
0x18008e4a1  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x18008e4a6  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18008e4ad  lea     rcx, [rsp+378h+var_138]; pExceptionObject
0x18008e4b5  call    _CxxThrowException_0
0x18008e4bb  jmp     short loc_18008E4C3
0x18008e4bd  jmp     short loc_18008E4C3
0x18008e4bf  jmp     short loc_18008E4C3
0x18008e4c1  jmp     short $+2
0x18008e4c3  mov     ecx, [rsp+378h+var_338]; dwErrCode
0x18008e4c7  call    cs:__imp_SetLastError
0x18008e4cd  nop
0x18008e4ce  cmp     [rsp+378h+var_308], 0
0x18008e4d3  jnz     short loc_18008E4DF
0x18008e4d5  mov     ecx, [rsp+378h+dwErrCode]; dwErrCode
0x18008e4d9  call    cs:__imp_SetLastError
0x18008e4df  xor     eax, eax
0x18008e4e1  mov     rcx, [rsp+378h+var_28]
0x18008e4e9  xor     rcx, rsp; StackCookie
0x18008e4ec  call    __security_check_cookie
0x18008e4f1  mov     rbx, [rsp+378h+arg_10]
0x18008e4f9  add     rsp, 360h
0x18008e500  pop     r14
0x18008e502  pop     rdi
0x18008e503  pop     rsi
0x18008e504  retn
```
