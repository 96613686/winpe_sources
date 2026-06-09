# OpenClusterNodeById

- ea: `0x180058b90`
- end: `0x1800590dc`
- name: `OpenClusterNodeById`
- size: `1356`
- prototype: `__int64 __fastcall(struct _HCLUSTER *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180083050`

## callees

- `0x180014638`
- `0x18001a9cc`
- `0x18001cf80`
- `0x18001fe48`
- `0x18001feac`
- `0x1800294f0`
- `0x18002acc0`
- `0x18002c220`
- `0x180057f5c`
- `0x1800589e0`
- `0x180058b90`
- `0x18006f910`
- `0x18008e110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180058fba`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180058fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058dc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058dc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058c77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058d8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058e32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058f2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058fa2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005903f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059097`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800590b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800590c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058c77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058d8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058e32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058f2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058fa2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005903f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059097`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800590b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800590c5`

## string_xrefs

- `0x180058bd9`: `OpenNodeById Enter::NodeId:%d`
- `0x180058beb`: `OpenClusterNodeById`
- `0x180058c59`: `OpenClusterNodeById`
- `0x180058d39`: `OpenClusterNodeById`
- `0x180058de6`: `OpenClusterNodeById`
- `0x180058edf`: `OpenClusterNodeById`
- `0x180058f54`: `OpenClusterNodeById`
- `0x180058fe9`: `OpenClusterNodeById`
- `0x180058c47`: `ClusterOpenEnum Failed GLE=%d`
- `0x180058dd4`: `OpenClusterNode failed with status:%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct _HNODE *__fastcall OpenClusterNodeById(struct _HCLUSTER *a1, unsigned int a2)
{
  struct _HNODE *result; // rax
  __int64 v5; // rcx
  DWORD v6; // ecx
  WCHAR *v7; // rax
  struct _HCLUSENUM *v8; // rbx
  DWORD v9; // esi
  DWORD v10; // eax
  struct _HNODE *v11; // rsi
  DWORD ClusterNodeId; // eax
  DWORD v13; // eax
  int v14; // eax
  __int64 v15; // [rsp+28h] [rbp-B0h]
  __int64 v16; // [rsp+30h] [rbp-A8h]
  DWORD dwType[2]; // [rsp+40h] [rbp-98h] BYREF
  DWORD v18; // [rsp+48h] [rbp-90h]
  DWORD *p_dwErrCode; // [rsp+50h] [rbp-88h]
  char v20; // [rsp+58h] [rbp-80h]
  LPWSTR lpszNodeId; // [rsp+60h] [rbp-78h] BYREF
  __int64 v22; // [rsp+68h] [rbp-70h]
  LPWSTR lpszName[4]; // [rsp+78h] [rbp-60h] BYREF
  cxl::Exception *v24; // [rsp+98h] [rbp-40h] BYREF
  std::system_error *v25; // [rsp+A0h] [rbp-38h] BYREF
  DWORD cchName; // [rsp+E8h] [rbp+10h] BYREF
  DWORD dwErrCode; // [rsp+F0h] [rbp+18h] BYREF
  DWORD v28; // [rsp+F8h] [rbp+20h] BYREF

  if ( a2 >= 0x96 )
    return OpenClusterCapacityNodeById(a1, a2);
  dwErrCode = 0;
  p_dwErrCode = &dwErrCode;
  v20 = 0;
  TraceMsg(4, 0, L"OpenClusterNodeById", 1115, L"OpenNodeById Enter::NodeId:%d", a2);
  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           v5,
                           a1) )
  {
    v6 = 87;
    dwErrCode = 87;
    goto LABEL_40;
  }
  v7 = (WCHAR *)ClusterOpenEnum(a1, 1u);
  try
  {
    v8 = (struct _HCLUSENUM *)v7;
    lpszName[3] = v7;
    if ( !v7 )
    {
      dwErrCode = GetLastError();
      LODWORD(v15) = dwErrCode;
      TraceMsg(2, 0, L"OpenClusterNodeById", 1129, L"ClusterOpenEnum Failed GLE=%d", v15);
      v20 = 1;
      SetLastError(dwErrCode);
      return 0;
    }
    std::vector<wchar_t>::vector<wchar_t>(lpszName, 260, &cchName);
    v9 = 0;
    v18 = 0;
    std::vector<wchar_t>::vector<wchar_t>(&lpszNodeId, 4, &cchName);
    while ( 1 )
    {
      if ( dwErrCode )
      {
        std::vector<wchar_t>::_Tidy(&lpszNodeId);
        std::vector<wchar_t>::_Tidy(lpszName);
        if ( v8 != (struct _HCLUSENUM *)-1LL )
          ClusterCloseEnumCommon(v8, 1);
        goto LABEL_37;
      }
      cchName = lpszName[1] - lpszName[0];
      v10 = ClusterEnum(v8, v9, dwType, lpszName[0], &cchName);
      dwErrCode = v10;
      if ( v10 )
      {
        if ( v10 == 259 )
        {
          dwErrCode = 0;
          std::vector<wchar_t>::_Tidy(&lpszNodeId);
          std::vector<wchar_t>::_Tidy(lpszName);
          if ( v8 != (struct _HCLUSENUM *)-1LL )
            ClusterCloseEnumCommon(v8, 1);
LABEL_37:
          v20 = 1;
          SetLastError(dwErrCode);
          return 0;
        }
        LODWORD(v16) = GetLastError();
        LODWORD(v15) = dwErrCode;
        TraceMsg(2, 0, L"OpenClusterNodeById", 1184, L"ClusterEnum Failed Ret=%d GLE=%d", v15, v16);
      }
      else
      {
        v11 = OpenClusterNodeImpl(a1, lpszName[0], 0x10000000, 0, 1);
        *(_QWORD *)dwType = v11;
        if ( !v11 )
        {
          dwErrCode = GetLastError();
          LODWORD(v15) = dwErrCode;
          TraceMsg(2, 0, L"OpenClusterNodeById", 1148, L"OpenClusterNode failed with status:%d", v15);
          cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(dwType);
          std::vector<wchar_t>::_Tidy(&lpszNodeId);
          std::vector<wchar_t>::_Tidy(lpszName);
          if ( v8 != (struct _HCLUSENUM *)-1LL )
            ClusterCloseEnumCommon(v8, 1);
          goto LABEL_37;
        }
        v28 = (v22 - (__int64)lpszNodeId) >> 1;
        ClusterNodeId = GetClusterNodeId(v11, lpszNodeId, &v28);
        dwErrCode = ClusterNodeId;
        if ( ClusterNodeId == 234 )
        {
          std::vector<wchar_t>::_Resize<std::_Value_init_tag>(&lpszNodeId, v28 + 1, &cchName);
          v28 = (v22 - (__int64)lpszNodeId) >> 1;
          v13 = GetClusterNodeId(v11, lpszNodeId, &v28);
          dwErrCode = v13;
          if ( v13 )
          {
            LODWORD(v15) = v13;
            TraceMsg(2, 0, L"OpenClusterNodeById", 1161, L"GetClusterNodeId 2nd call failed with status:%d", v15);
            cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(dwType);
            std::vector<wchar_t>::_Tidy(&lpszNodeId);
            std::vector<wchar_t>::_Tidy(lpszName);
            if ( v8 != (struct _HCLUSENUM *)-1LL )
              ClusterCloseEnumCommon(v8, 1);
            goto LABEL_37;
          }
        }
        else if ( ClusterNodeId )
        {
          LODWORD(v15) = ClusterNodeId;
          TraceMsg(2, 0, L"OpenClusterNodeById", 1167, L"GetClusterNodeId failed with status:%d", v15);
          cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(dwType);
          std::vector<wchar_t>::_Tidy(&lpszNodeId);
          std::vector<wchar_t>::_Tidy(lpszName);
          if ( v8 != (struct _HCLUSENUM *)-1LL )
            ClusterCloseEnumCommon(v8, 1);
          goto LABEL_37;
        }
        v14 = wcstol(lpszNodeId, 0, 10);
        if ( v14 == a2 )
        {
          LODWORD(v16) = v14;
          TraceMsg(4, 0, L"OpenClusterNodeById", 1175, L"Nodename:%ws NodeId:%u", lpszName[0], v16);
          *(_QWORD *)dwType = 0;
          cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(dwType);
          std::vector<wchar_t>::_Tidy(&lpszNodeId);
          std::vector<wchar_t>::_Tidy(lpszName);
          if ( v8 != (struct _HCLUSENUM *)-1LL )
            ClusterCloseEnumCommon(v8, 1);
          v20 = 1;
          SetLastError(dwErrCode);
          return v11;
        }
        cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(dwType);
        v9 = v18;
      }
      v18 = ++v9;
    }
  }
  catch ( cxl::Exception *v24 )
  {
    cchName = cxl::ErrorCode::GetWinError((cxl::Exception *)((char *)v24 + 88));
    goto LABEL_38;
  }
  catch ( std::system_error *v25 )
  {
    cchName = *((_DWORD *)v25 + 6);
    goto LABEL_38;
  }
  catch ( std::bad_alloc )
  {
    cchName = 14;
    goto LABEL_38;
  }
  catch ( std::exception )
  {
    cchName = 1359;
    goto LABEL_38;
  }
  catch ( ... )
  {
    cchName = 1359;
LABEL_38:
    SetLastError(cchName);
    if ( v20 )
      return 0;
    v6 = *p_dwErrCode;
LABEL_40:
    SetLastError(v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180058b90  push    rbx
0x180058b92  push    rsi
0x180058b93  push    rdi
0x180058b94  push    r12
0x180058b96  push    r13
0x180058b98  sub     rsp, 0B0h
0x180058b9f  mov     r12d, edx
0x180058ba2  mov     r13, rcx
0x180058ba5  cmp     edx, 96h
0x180058bab  jb      short loc_180058BB7
0x180058bad  call    ?OpenClusterCapacityNodeById@@YAPEAU_HNODE@@PEAU_HCLUSTER@@K@Z; OpenClusterCapacityNodeById(_HCLUSTER *,ulong)
0x180058bb2  jmp     loc_1800590CD
0x180058bb7  mov     [rsp+0D8h+dwErrCode], 0
0x180058bc2  lea     rdi, [rsp+0D8h+dwErrCode]
0x180058bca  mov     [rsp+0D8h+var_88], rdi
0x180058bcf  mov     [rsp+0D8h+var_80], 0
0x180058bd4  mov     dword ptr [rsp+0D8h+var_B0], r12d
0x180058bd9  lea     rax, aOpennodebyidEn; "OpenNodeById Enter::NodeId:%d"
0x180058be0  mov     [rsp+0D8h+lpcchName], rax
0x180058be5  mov     r9d, 45Bh
0x180058beb  lea     r8, aOpenclusternod_3; "OpenClusterNodeById"
0x180058bf2  xor     edx, edx
0x180058bf4  lea     ecx, [rdx+4]
0x180058bf7  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180058bfc  mov     rdx, r13
0x180058bff  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x180058c04  test    al, al
0x180058c06  jnz     short loc_180058C19
0x180058c08  mov     ecx, 57h ; 'W'
0x180058c0d  mov     [rsp+0D8h+dwErrCode], ecx
0x180058c14  jmp     loc_1800590C5
0x180058c19  mov     edx, 1; dwType
0x180058c1e  mov     rcx, r13; hCluster
0x180058c21  call    ClusterOpenEnum
0x180058c26  mov     rbx, rax
0x180058c29  mov     [rsp+0D8h+var_48], rax
0x180058c31  test    rax, rax
0x180058c34  jnz     short loc_180058C84
0x180058c36  call    cs:__imp_GetLastError
0x180058c3c  mov     [rsp+0D8h+dwErrCode], eax
0x180058c43  mov     dword ptr [rsp+0D8h+var_B0], eax
0x180058c47  lea     rax, aClusteropenenu_2; "ClusterOpenEnum Failed GLE=%d"
0x180058c4e  mov     [rsp+0D8h+lpcchName], rax
0x180058c53  mov     r9d, 469h
0x180058c59  lea     r8, aOpenclusternod_3; "OpenClusterNodeById"
0x180058c60  xor     edx, edx
0x180058c62  lea     ecx, [rbx+2]
0x180058c65  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180058c6a  nop
0x180058c6b  mov     [rsp+0D8h+var_80], 1
0x180058c70  mov     ecx, [rsp+0D8h+dwErrCode]; dwErrCode
0x180058c77  call    cs:__imp_SetLastError
0x180058c7d  xor     eax, eax
0x180058c7f  jmp     loc_1800590CD
0x180058c84  lea     r8, [rsp+0D8h+cchName]
0x180058c8c  mov     edx, 104h
0x180058c91  lea     rcx, [rsp+0D8h+lpszName]
0x180058c96  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x180058c9b  nop
0x180058c9c  xor     esi, esi
0x180058c9e  mov     [rsp+0D8h+var_90], esi
0x180058ca2  lea     r8, [rsp+0D8h+cchName]
0x180058caa  lea     edx, [rsi+4]
0x180058cad  lea     rcx, [rsp+0D8h+lpszNodeId]
0x180058cb2  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x180058cb7  nop
0x180058cb8  cmp     [rsp+0D8h+dwErrCode], 0
0x180058cc0  jnz     loc_180059066
0x180058cc6  mov     r9, [rsp+0D8h+lpszName]; lpszName
0x180058ccb  mov     rax, [rsp+0D8h+var_58]
0x180058cd3  sub     rax, r9
0x180058cd6  sar     rax, 1
0x180058cd9  mov     [rsp+0D8h+cchName], eax
0x180058ce0  lea     rax, [rsp+0D8h+cchName]
0x180058ce8  mov     [rsp+0D8h+lpcchName], rax; lpcchName
0x180058ced  lea     r8, [rsp+0D8h+dwType]; lpdwType
0x180058cf2  mov     edx, esi; dwIndex
0x180058cf4  mov     rcx, rbx; hEnum
0x180058cf7  call    ClusterEnum
0x180058cfc  mov     [rsp+0D8h+dwErrCode], eax
0x180058d03  test    eax, eax
0x180058d05  jz      loc_180058D98
0x180058d0b  cmp     eax, 103h
0x180058d10  jz      short loc_180058D4F
0x180058d12  call    cs:__imp_GetLastError
0x180058d18  mov     [rsp+0D8h+var_A8], eax
0x180058d1c  mov     eax, [rsp+0D8h+dwErrCode]
0x180058d23  mov     dword ptr [rsp+0D8h+var_B0], eax
0x180058d27  lea     rax, aClusterenumFai; "ClusterEnum Failed Ret=%d GLE=%d"
0x180058d2e  mov     [rsp+0D8h+lpcchName], rax
0x180058d33  mov     r9d, 4A0h
0x180058d39  lea     r8, aOpenclusternod_3; "OpenClusterNodeById"
0x180058d40  xor     edx, edx
0x180058d42  lea     ecx, [rdx+2]
0x180058d45  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180058d4a  jmp     loc_18005905B
0x180058d4f  mov     [rsp+0D8h+dwErrCode], 0
0x180058d5a  lea     rcx, [rsp+0D8h+lpszNodeId]
0x180058d5f  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180058d64  nop
0x180058d65  lea     rcx, [rsp+0D8h+lpszName]
0x180058d6a  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180058d6f  nop
0x180058d70  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180058d74  jz      short loc_180058D84
0x180058d76  mov     edx, 1; int
0x180058d7b  mov     rcx, rbx; struct _HCLUSENUM *
0x180058d7e  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x180058d83  nop
0x180058d84  mov     [rsp+0D8h+var_80], 1
0x180058d89  mov     ecx, [rdi]; dwErrCode
0x180058d8b  call    cs:__imp_SetLastError
0x180058d91  xor     eax, eax
0x180058d93  jmp     loc_1800590CD
0x180058d98  mov     dword ptr [rsp+0D8h+lpcchName], 1; int
0x180058da0  xor     r9d, r9d; unsigned int *
0x180058da3  mov     r8d, 10000000h; unsigned int
0x180058da9  mov     rdx, [rsp+0D8h+lpszName]; wchar_t *
0x180058dae  mov     rcx, r13; struct _HCLUSTER *
0x180058db1  call    ?OpenClusterNodeImpl@@YAPEAU_HNODE@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z; OpenClusterNodeImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)
0x180058db6  mov     rsi, rax
0x180058db9  mov     qword ptr [rsp+0D8h+dwType], rax
0x180058dbe  test    rax, rax
0x180058dc1  jnz     short loc_180058E3F
0x180058dc3  call    cs:__imp_GetLastError
0x180058dc9  mov     [rsp+0D8h+dwErrCode], eax
0x180058dd0  mov     dword ptr [rsp+0D8h+var_B0], eax
0x180058dd4  lea     rax, aOpenclusternod_2; "OpenClusterNode failed with status:%d"
0x180058ddb  mov     [rsp+0D8h+lpcchName], rax
0x180058de0  mov     r9d, 47Ch
0x180058de6  lea     r8, aOpenclusternod_3; "OpenClusterNodeById"
0x180058ded  xor     edx, edx
0x180058def  lea     ecx, [rsi+2]
0x180058df2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180058df7  nop
0x180058df8  lea     rcx, [rsp+0D8h+dwType]
0x180058dfd  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x180058e02  nop
0x180058e03  lea     rcx, [rsp+0D8h+lpszNodeId]
0x180058e08  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180058e0d  nop
0x180058e0e  lea     rcx, [rsp+0D8h+lpszName]
0x180058e13  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180058e18  nop
0x180058e19  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180058e1d  jz      short loc_180058E2B
0x180058e1f  lea     edx, [rsi+1]; int
0x180058e22  mov     rcx, rbx; struct _HCLUSENUM *
0x180058e25  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x180058e2a  nop
0x180058e2b  mov     [rsp+0D8h+var_80], 1
0x180058e30  mov     ecx, [rdi]; dwErrCode
0x180058e32  call    cs:__imp_SetLastError
0x180058e38  xor     eax, eax
0x180058e3a  jmp     loc_1800590CD
0x180058e3f  mov     rdx, [rsp+0D8h+lpszNodeId]; lpszNodeId
0x180058e44  mov     rax, [rsp+0D8h+var_70]
0x180058e49  sub     rax, rdx
0x180058e4c  sar     rax, 1
0x180058e4f  mov     [rsp+0D8h+arg_18], eax
0x180058e56  lea     r8, [rsp+0D8h+arg_18]; lpcchName
0x180058e5e  mov     rcx, rsi; hNode
0x180058e61  call    GetClusterNodeId
0x180058e66  mov     [rsp+0D8h+dwErrCode], eax
0x180058e6d  cmp     eax, 0EAh
0x180058e72  jnz     loc_180058F3A
0x180058e78  mov     edx, [rsp+0D8h+arg_18]
0x180058e7f  inc     edx
0x180058e81  lea     r8, [rsp+0D8h+cchName]
0x180058e89  lea     rcx, [rsp+0D8h+lpszNodeId]
0x180058e8e  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180058e93  mov     rdx, [rsp+0D8h+lpszNodeId]; lpszNodeId
0x180058e98  mov     rax, [rsp+0D8h+var_70]
0x180058e9d  sub     rax, rdx
0x180058ea0  sar     rax, 1
0x180058ea3  mov     [rsp+0D8h+arg_18], eax
0x180058eaa  lea     r8, [rsp+0D8h+arg_18]; lpcchName
0x180058eb2  mov     rcx, rsi; hNode
0x180058eb5  call    GetClusterNodeId
0x180058eba  mov     [rsp+0D8h+dwErrCode], eax
0x180058ec1  test    eax, eax
0x180058ec3  jz      loc_180058FAF
0x180058ec9  mov     dword ptr [rsp+0D8h+var_B0], eax
0x180058ecd  lea     rax, aGetclusternode_3; "GetClusterNodeId 2nd call failed with s"...
0x180058ed4  mov     [rsp+0D8h+lpcchName], rax
0x180058ed9  mov     r9d, 489h
0x180058edf  lea     r8, aOpenclusternod_3; "OpenClusterNodeById"
0x180058ee6  xor     edx, edx
0x180058ee8  lea     ecx, [rdx+2]
0x180058eeb  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180058ef0  nop
0x180058ef1  lea     rcx, [rsp+0D8h+dwType]
0x180058ef6  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x180058efb  nop
0x180058efc  lea     rcx, [rsp+0D8h+lpszNodeId]
0x180058f01  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180058f06  nop
0x180058f07  lea     rcx, [rsp+0D8h+lpszName]
0x180058f0c  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180058f11  nop
0x180058f12  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180058f16  jz      short loc_180058F26
0x180058f18  mov     edx, 1; int
0x180058f1d  mov     rcx, rbx; struct _HCLUSENUM *
0x180058f20  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x180058f25  nop
0x180058f26  mov     [rsp+0D8h+var_80], 1
0x180058f2b  mov     ecx, [rdi]; dwErrCode
0x180058f2d  call    cs:__imp_SetLastError
0x180058f33  xor     eax, eax
0x180058f35  jmp     loc_1800590CD
0x180058f3a  test    eax, eax
0x180058f3c  jz      short loc_180058FAF
0x180058f3e  mov     dword ptr [rsp+0D8h+var_B0], eax
0x180058f42  lea     rax, aGetclusternode_6; "GetClusterNodeId failed with status:%d"
0x180058f49  mov     [rsp+0D8h+lpcchName], rax
0x180058f4e  mov     r9d, 48Fh
0x180058f54  lea     r8, aOpenclusternod_3; "OpenClusterNodeById"
0x180058f5b  xor     edx, edx
0x180058f5d  lea     ecx, [rdx+2]
0x180058f60  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180058f65  nop
0x180058f66  lea     rcx, [rsp+0D8h+dwType]
0x180058f6b  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x180058f70  nop
0x180058f71  lea     rcx, [rsp+0D8h+lpszNodeId]
0x180058f76  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180058f7b  nop
0x180058f7c  lea     rcx, [rsp+0D8h+lpszName]
0x180058f81  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180058f86  nop
0x180058f87  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180058f8b  jz      short loc_180058F9B
0x180058f8d  mov     edx, 1; int
0x180058f92  mov     rcx, rbx; struct _HCLUSENUM *
0x180058f95  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x180058f9a  nop
0x180058f9b  mov     [rsp+0D8h+var_80], 1
0x180058fa0  mov     ecx, [rdi]; dwErrCode
0x180058fa2  call    cs:__imp_SetLastError
0x180058fa8  xor     eax, eax
0x180058faa  jmp     loc_1800590CD
0x180058faf  xor     edx, edx; EndPtr
0x180058fb1  lea     r8d, [rdx+0Ah]; Radix
0x180058fb5  mov     rcx, [rsp+0D8h+lpszNodeId]; String
0x180058fba  call    cs:__imp_wcstol
0x180058fc0  cmp     eax, r12d
0x180058fc3  jnz     loc_18005904D
0x180058fc9  mov     [rsp+0D8h+var_A8], eax
0x180058fcd  mov     rax, [rsp+0D8h+lpszName]
0x180058fd2  mov     [rsp+0D8h+var_B0], rax
0x180058fd7  lea     rax, aNodenameWsNode; "Nodename:%ws NodeId:%u"
0x180058fde  mov     [rsp+0D8h+lpcchName], rax
0x180058fe3  mov     r9d, 497h
0x180058fe9  lea     r8, aOpenclusternod_3; "OpenClusterNodeById"
0x180058ff0  xor     edx, edx
0x180058ff2  lea     ecx, [rdx+4]
0x180058ff5  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180058ffa  mov     qword ptr [rsp+0D8h+dwType], 0
0x180059003  lea     rcx, [rsp+0D8h+dwType]
0x180059008  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x18005900d  nop
0x18005900e  lea     rcx, [rsp+0D8h+lpszNodeId]
0x180059013  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180059018  nop
0x180059019  lea     rcx, [rsp+0D8h+lpszName]
0x18005901e  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180059023  nop
0x180059024  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180059028  jz      short loc_180059038
0x18005902a  mov     edx, 1; int
0x18005902f  mov     rcx, rbx; struct _HCLUSENUM *
0x180059032  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x180059037  nop
0x180059038  mov     [rsp+0D8h+var_80], 1
0x18005903d  mov     ecx, [rdi]; dwErrCode
0x18005903f  call    cs:__imp_SetLastError
0x180059045  mov     rax, rsi
0x180059048  jmp     loc_1800590CD
0x18005904d  lea     rcx, [rsp+0D8h+dwType]
0x180059052  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x180059057  mov     esi, [rsp+0D8h+var_90]
0x18005905b  inc     esi
0x18005905d  mov     [rsp+0D8h+var_90], esi
0x180059061  jmp     loc_180058CB8
0x180059066  lea     rcx, [rsp+0D8h+lpszNodeId]
0x18005906b  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180059070  nop
0x180059071  lea     rcx, [rsp+0D8h+lpszName]
0x180059076  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18005907b  nop
0x18005907c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180059080  jz      short loc_180059090
0x180059082  mov     edx, 1; int
0x180059087  mov     rcx, rbx; struct _HCLUSENUM *
0x18005908a  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x18005908f  nop
0x180059090  mov     [rsp+0D8h+var_80], 1
0x180059095  mov     ecx, [rdi]; dwErrCode
0x180059097  call    cs:__imp_SetLastError
  ... truncated ...
```
