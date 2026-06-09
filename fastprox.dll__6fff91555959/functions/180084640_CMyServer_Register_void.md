# CMyServer::Register(void)

- ea: `0x180084640`
- end: `0x180084a29`
- name: `?Register@CMyServer@@UEAAJXZ`
- size: `1001`
- prototype: `__int64 __fastcall(CMyServer *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180037120`
- `0x180084640`
- `0x18008fe40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084969`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800849c8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084969`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800849c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008497b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800849d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008497b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800849d6`
- `wbemcomn!GetMemLogObject` at `0x18008467e`
- `wbemcomn!GetMemLogObject` at `0x180084700`
- `wbemcomn!GetMemLogObject` at `0x18008476d`
- `wbemcomn!GetMemLogObject` at `0x1800847e6`
- `wbemcomn!GetMemLogObject` at `0x18008485f`
- `wbemcomn!GetMemLogObject` at `0x1800848d8`
- `wbemcomn!GetMemLogObject` at `0x18008467e`
- `wbemcomn!GetMemLogObject` at `0x180084700`
- `wbemcomn!GetMemLogObject` at `0x18008476d`
- `wbemcomn!GetMemLogObject` at `0x1800847e6`
- `wbemcomn!GetMemLogObject` at `0x18008485f`
- `wbemcomn!GetMemLogObject` at `0x1800848d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084689`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008470b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084778`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800847f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008486a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800848e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084689`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008470b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180084778`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800847f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008486a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800848e3`

## string_xrefs

- `0x1800848ae`: `IWbemServices`
- `0x180084934`: `software\classes\CLSID\{4590F812-1D3A-11D0-891F-00AA004B2E24}\Implemented Categories\{00000003-0000-0000-C000-000000000046}`
- `0x180084993`: `software\classes\CLSID\{674B6698-EE92-11D0-AD71-00C04FD8FDFF}\Implemented Categories\{00000003-0000-0000-C000-000000000046}`

## pseudocode

```c
__int64 __fastcall CMyServer::Register(CMyServer *this)
{
  CComServer *v1; // rcx
  int v2; // ebx
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v4; // r10
  __int64 v5; // rdx
  __int64 v6; // rcx
  CComServer *v8; // rcx
  CMemoryLog *v9; // rax
  CComServer *v10; // rcx
  CMemoryLog *v11; // rax
  CComServer *v12; // rcx
  CMemoryLog *v13; // rax
  CComServer *v14; // rcx
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CWbemRefreshingSvc *v17; // rax
  const struct _GUID *samDesired; // [rsp+28h] [rbp-38h]
  const struct _GUID *samDesireda; // [rsp+28h] [rbp-38h]
  const struct _GUID *samDesiredb; // [rsp+28h] [rbp-38h]
  const struct _GUID *samDesiredc; // [rsp+28h] [rbp-38h]
  const struct _GUID *samDesiredd; // [rsp+28h] [rbp-38h]
  const struct _GUID *samDesirede; // [rsp+28h] [rbp-38h]
  struct _GUID v24; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+18h] BYREF

  v24 = stru_1800A69F0;
  v2 = CComServer::RegisterInterfaceMarshaler(this, &IID_IWbemObjectSink, &v24, L"IWbemObjectSink", 5, samDesired);
  if ( v2 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v2;
    }
    v5 = 44;
    goto LABEL_6;
  }
  v24 = stru_1800A6918;
  v2 = CComServer::RegisterInterfaceMarshaler(v1, &IID_IWbemObjectSinkEx, &v24, L"IWbemObjectSinkEx", 10, samDesireda);
  if ( v2 < 0 )
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, v2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v2;
    }
    v5 = 45;
    goto LABEL_6;
  }
  v24 = stru_1800A6A78;
  v2 = CComServer::RegisterInterfaceMarshaler(
         v8,
         &IID_IEnumWbemClassObject,
         &v24,
         L"IEnumWbemClassObject",
         5,
         samDesiredb);
  if ( v2 < 0 )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, v2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v2;
    }
    v5 = 46;
    goto LABEL_6;
  }
  v24 = stru_1800A6A68;
  v2 = CComServer::RegisterInterfaceMarshaler(
         v10,
         &IID_IWbemUnboundObjectSink,
         &v24,
         L"IWbemUnboundObjectSink",
         4,
         samDesiredc);
  if ( v2 < 0 )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, v2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v2;
    }
    v5 = 47;
    goto LABEL_6;
  }
  v24 = stru_1800A6AF8;
  v2 = CComServer::RegisterInterfaceMarshaler(v12, &IID_IWbemMultiTarget, &v24, L"IWbemMultiTarget", 4, samDesiredd);
  if ( v2 < 0 )
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, v2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v2;
    }
    v5 = 48;
LABEL_6:
    v6 = *((_QWORD *)v4 + 2);
LABEL_7:
    WPP_SF_d(v6, v5, WPP_789720b20a7b3f9b60cad96e580907a5_Traceguids, (unsigned int)v2);
    return (unsigned int)v2;
  }
  v24 = stru_1800A6C18;
  v2 = CComServer::RegisterInterfaceMarshaler(v14, &IID_IWbemServices, &v24, L"IWbemServices", 40, samDesirede);
  if ( v2 < 0 )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, v2);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v2;
    }
    v5 = 49;
    goto LABEL_34;
  }
  hKey = 0;
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"software\\classes\\CLSID\\{4590F812-1D3A-11D0-891F-00AA004B2E24}\\Implemented Categories\\{00000003-0000-0000-"
           "C000-000000000046}",
          0,
          0,
          0,
          0x2000000u,
          0,
          &hKey,
          0) )
  {
    RegCloseKey(hKey);
    hKey = 0;
    if ( !RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"software\\classes\\CLSID\\{674B6698-EE92-11D0-AD71-00C04FD8FDFF}\\Implemented Categories\\{00000003-0000-000"
             "0-C000-000000000046}",
            0,
            0,
            0,
            0x2000000u,
            0,
            &hKey,
            0) )
    {
      RegCloseKey(hKey);
      hKey = 0;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v2;
      }
      v5 = 50;
LABEL_34:
      v6 = *((_QWORD *)v17 + 2);
      goto LABEL_7;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180084640  mov     [rsp-8+arg_0], rbx
0x180084645  push    rbp
0x180084646  mov     rbp, rsp
0x180084649  sub     rsp, 60h
0x18008464d  movups  xmm0, xmmword ptr cs:stru_1800A69F0.Data1
0x180084654  lea     r9, aIwbemobjectsin; "IWbemObjectSink"
0x18008465b  mov     [rsp+60h+dwOptions], 5; int
0x180084663  lea     r8, [rbp+var_10]; struct _GUID
0x180084667  lea     rdx, IID_IWbemObjectSink; struct _GUID *
0x18008466e  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x180084673  call    ?RegisterInterfaceMarshaler@CComServer@@IEAAJAEBU_GUID@@U2@PEAGH0@Z; CComServer::RegisterInterfaceMarshaler(_GUID const &,_GUID,ushort *,int,_GUID const &)
0x180084678  mov     ebx, eax
0x18008467a  test    eax, eax
0x18008467c  jns     short loc_1800846CF
0x18008467e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180084684  mov     rcx, rax
0x180084687  mov     edx, ebx
0x180084689  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008468f  mov     r10, cs:WPP_GLOBAL_Control
0x180084696  lea     rcx, WPP_GLOBAL_Control
0x18008469d  cmp     r10, rcx
0x1800846a0  jz      short loc_1800846C8
0x1800846a2  test    byte ptr [r10+1Ch], 1
0x1800846a7  jz      short loc_1800846C8
0x1800846a9  cmp     byte ptr [r10+19h], 2
0x1800846ae  jb      short loc_1800846C8
0x1800846b0  mov     edx, 2Ch ; ','
0x1800846b5  mov     rcx, [r10+10h]
0x1800846b9  lea     r8, WPP_789720b20a7b3f9b60cad96e580907a5_Traceguids
0x1800846c0  mov     r9d, ebx
0x1800846c3  call    WPP_SF_d
0x1800846c8  mov     eax, ebx
0x1800846ca  jmp     loc_180084A1E
0x1800846cf  movups  xmm0, xmmword ptr cs:stru_1800A6918.Data1
0x1800846d6  lea     r9, aIwbemobjectsin_0; "IWbemObjectSinkEx"
0x1800846dd  mov     [rsp+60h+dwOptions], 0Ah; int
0x1800846e5  lea     r8, [rbp+var_10]; struct _GUID
0x1800846e9  lea     rdx, IID_IWbemObjectSinkEx; struct _GUID *
0x1800846f0  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x1800846f5  call    ?RegisterInterfaceMarshaler@CComServer@@IEAAJAEBU_GUID@@U2@PEAGH0@Z; CComServer::RegisterInterfaceMarshaler(_GUID const &,_GUID,ushort *,int,_GUID const &)
0x1800846fa  mov     ebx, eax
0x1800846fc  test    eax, eax
0x1800846fe  jns     short loc_18008473C
0x180084700  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180084706  mov     rcx, rax
0x180084709  mov     edx, ebx
0x18008470b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180084711  mov     r10, cs:WPP_GLOBAL_Control
0x180084718  lea     rcx, WPP_GLOBAL_Control
0x18008471f  cmp     r10, rcx
0x180084722  jz      short loc_1800846C8
0x180084724  test    byte ptr [r10+1Ch], 1
0x180084729  jz      short loc_1800846C8
0x18008472b  cmp     byte ptr [r10+19h], 2
0x180084730  jb      short loc_1800846C8
0x180084732  mov     edx, 2Dh ; '-'
0x180084737  jmp     loc_1800846B5
0x18008473c  movups  xmm0, xmmword ptr cs:stru_1800A6A78.Data1
0x180084743  lea     r9, aIenumwbemclass; "IEnumWbemClassObject"
0x18008474a  mov     [rsp+60h+dwOptions], 5; int
0x180084752  lea     r8, [rbp+var_10]; struct _GUID
0x180084756  lea     rdx, IID_IEnumWbemClassObject; struct _GUID *
0x18008475d  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x180084762  call    ?RegisterInterfaceMarshaler@CComServer@@IEAAJAEBU_GUID@@U2@PEAGH0@Z; CComServer::RegisterInterfaceMarshaler(_GUID const &,_GUID,ushort *,int,_GUID const &)
0x180084767  mov     ebx, eax
0x180084769  test    eax, eax
0x18008476b  jns     short loc_1800847B5
0x18008476d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180084773  mov     rcx, rax
0x180084776  mov     edx, ebx
0x180084778  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008477e  mov     r10, cs:WPP_GLOBAL_Control
0x180084785  lea     rcx, WPP_GLOBAL_Control
0x18008478c  cmp     r10, rcx
0x18008478f  jz      loc_1800846C8
0x180084795  test    byte ptr [r10+1Ch], 1
0x18008479a  jz      loc_1800846C8
0x1800847a0  cmp     byte ptr [r10+19h], 2
0x1800847a5  jb      loc_1800846C8
0x1800847ab  mov     edx, 2Eh ; '.'
0x1800847b0  jmp     loc_1800846B5
0x1800847b5  movups  xmm0, xmmword ptr cs:stru_1800A6A68.Data1
0x1800847bc  lea     r9, aIwbemunboundob; "IWbemUnboundObjectSink"
0x1800847c3  mov     [rsp+60h+dwOptions], 4; int
0x1800847cb  lea     r8, [rbp+var_10]; struct _GUID
0x1800847cf  lea     rdx, IID_IWbemUnboundObjectSink; struct _GUID *
0x1800847d6  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x1800847db  call    ?RegisterInterfaceMarshaler@CComServer@@IEAAJAEBU_GUID@@U2@PEAGH0@Z; CComServer::RegisterInterfaceMarshaler(_GUID const &,_GUID,ushort *,int,_GUID const &)
0x1800847e0  mov     ebx, eax
0x1800847e2  test    eax, eax
0x1800847e4  jns     short loc_18008482E
0x1800847e6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800847ec  mov     rcx, rax
0x1800847ef  mov     edx, ebx
0x1800847f1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800847f7  mov     r10, cs:WPP_GLOBAL_Control
0x1800847fe  lea     rcx, WPP_GLOBAL_Control
0x180084805  cmp     r10, rcx
0x180084808  jz      loc_1800846C8
0x18008480e  test    byte ptr [r10+1Ch], 1
0x180084813  jz      loc_1800846C8
0x180084819  cmp     byte ptr [r10+19h], 2
0x18008481e  jb      loc_1800846C8
0x180084824  mov     edx, 2Fh ; '/'
0x180084829  jmp     loc_1800846B5
0x18008482e  movups  xmm0, xmmword ptr cs:stru_1800A6AF8.Data1
0x180084835  lea     r9, aIwbemmultitarg; "IWbemMultiTarget"
0x18008483c  mov     [rsp+60h+dwOptions], 4; int
0x180084844  lea     r8, [rbp+var_10]; struct _GUID
0x180084848  lea     rdx, IID_IWbemMultiTarget; struct _GUID *
0x18008484f  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x180084854  call    ?RegisterInterfaceMarshaler@CComServer@@IEAAJAEBU_GUID@@U2@PEAGH0@Z; CComServer::RegisterInterfaceMarshaler(_GUID const &,_GUID,ushort *,int,_GUID const &)
0x180084859  mov     ebx, eax
0x18008485b  test    eax, eax
0x18008485d  jns     short loc_1800848A7
0x18008485f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180084865  mov     rcx, rax
0x180084868  mov     edx, ebx
0x18008486a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180084870  mov     r10, cs:WPP_GLOBAL_Control
0x180084877  lea     rcx, WPP_GLOBAL_Control
0x18008487e  cmp     r10, rcx
0x180084881  jz      loc_1800846C8
0x180084887  test    byte ptr [r10+1Ch], 1
0x18008488c  jz      loc_1800846C8
0x180084892  cmp     byte ptr [r10+19h], 2
0x180084897  jb      loc_1800846C8
0x18008489d  mov     edx, 30h ; '0'
0x1800848a2  jmp     loc_1800846B5
0x1800848a7  movups  xmm0, xmmword ptr cs:stru_1800A6C18.Data1
0x1800848ae  lea     r9, aIwbemservices; "IWbemServices"
0x1800848b5  mov     [rsp+60h+dwOptions], 28h ; '('; int
0x1800848bd  lea     r8, [rbp+var_10]; struct _GUID
0x1800848c1  lea     rdx, IID_IWbemServices; struct _GUID *
0x1800848c8  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x1800848cd  call    ?RegisterInterfaceMarshaler@CComServer@@IEAAJAEBU_GUID@@U2@PEAGH0@Z; CComServer::RegisterInterfaceMarshaler(_GUID const &,_GUID,ushort *,int,_GUID const &)
0x1800848d2  mov     ebx, eax
0x1800848d4  test    eax, eax
0x1800848d6  jns     short loc_180084922
0x1800848d8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800848de  mov     rcx, rax
0x1800848e1  mov     edx, ebx
0x1800848e3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800848e9  mov     rax, cs:WPP_GLOBAL_Control
0x1800848f0  lea     rcx, WPP_GLOBAL_Control
0x1800848f7  cmp     rax, rcx
0x1800848fa  jz      loc_1800846C8
0x180084900  test    byte ptr [rax+1Ch], 1
0x180084904  jz      loc_1800846C8
0x18008490a  cmp     byte ptr [rax+19h], 2
0x18008490e  jb      loc_1800846C8
0x180084914  mov     edx, 31h ; '1'
0x180084919  mov     rcx, [rax+10h]
0x18008491d  jmp     loc_1800846B9
0x180084922  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18008492b  lea     rax, [rbp+hKey]
0x18008492f  mov     [rsp+60h+phkResult], rax; phkResult
0x180084934  lea     rdx, aSoftwareClasse_2; "software\\classes\\CLSID\\{4590F812-1D3"...
0x18008493b  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180084944  xor     r9d, r9d; lpClass
0x180084947  mov     dword ptr [rsp+60h+samDesired], 2000000h; samDesired
0x18008494f  xor     r8d, r8d; Reserved
0x180084952  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180084959  mov     [rsp+60h+dwOptions], 0; dwOptions
0x180084961  mov     [rbp+hKey], 0
0x180084969  call    cs:__imp_RegCreateKeyExW
0x18008496f  test    eax, eax
0x180084971  jnz     loc_180084A19
0x180084977  mov     rcx, [rbp+hKey]; hKey
0x18008497b  call    cs:__imp_RegCloseKey
0x180084981  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18008498a  lea     rax, [rbp+hKey]
0x18008498e  mov     [rsp+60h+phkResult], rax; phkResult
0x180084993  lea     rdx, aSoftwareClasse_3; "software\\classes\\CLSID\\{674B6698-EE9"...
0x18008499a  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800849a3  xor     r9d, r9d; lpClass
0x1800849a6  mov     dword ptr [rsp+60h+samDesired], 2000000h; samDesired
0x1800849ae  xor     r8d, r8d; Reserved
0x1800849b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800849b8  mov     [rsp+60h+dwOptions], 0; dwOptions
0x1800849c0  mov     [rbp+hKey], 0
0x1800849c8  call    cs:__imp_RegCreateKeyExW
0x1800849ce  test    eax, eax
0x1800849d0  jnz     short loc_180084A19
0x1800849d2  mov     rcx, [rbp+hKey]; hKey
0x1800849d6  call    cs:__imp_RegCloseKey
0x1800849dc  mov     [rbp+hKey], 0
0x1800849e4  mov     rax, cs:WPP_GLOBAL_Control
0x1800849eb  lea     rcx, WPP_GLOBAL_Control
0x1800849f2  cmp     rax, rcx
0x1800849f5  jz      loc_1800846C8
0x1800849fb  test    byte ptr [rax+1Ch], 1
0x1800849ff  jz      loc_1800846C8
0x180084a05  cmp     byte ptr [rax+19h], 2
0x180084a09  jb      loc_1800846C8
0x180084a0f  mov     edx, 32h ; '2'
0x180084a14  jmp     loc_180084919
0x180084a19  mov     eax, 80004005h
0x180084a1e  mov     rbx, [rsp+60h+arg_0]
0x180084a23  add     rsp, 60h
0x180084a27  pop     rbp
0x180084a28  retn
```
