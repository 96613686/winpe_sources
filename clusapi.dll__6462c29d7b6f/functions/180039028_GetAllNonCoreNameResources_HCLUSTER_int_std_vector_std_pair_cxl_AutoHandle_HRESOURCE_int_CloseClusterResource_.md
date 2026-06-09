# GetAllNonCoreNameResources(_HCLUSTER *,int,std::vector<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>> &)

- ea: `0x180039028`
- end: `0x1800395e6`
- name: `?GetAllNonCoreNameResources@@YAKPEAU_HCLUSTER@@HAEAV?$vector@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@@Z`
- size: `1470`
- prototype: `__int64 __fastcall(HCLUSTER hCluster)`
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180041f00`
- `0x180045a00`
- `0x180075a58`

## callees

- `0x180002f50`
- `0x180003320`
- `0x180003510`
- `0x180014638`
- `0x18001cc2c`
- `0x18001fe7c`
- `0x18001feac`
- `0x180029578`
- `0x18002acc0`
- `0x18002c220`
- `0x18002ff9c`
- `0x180031cf0`
- `0x180039028`
- `0x180052d30`
- `0x18006b834`
- `0x18006cf40`
- `0x18006f910`
- `0x1800ad034`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039524`

## string_xrefs

- `0x1800390d7`: `Failed to open cluster enumeration, error %d.`
- `0x1800390e9`: `GetAllNonCoreNameResources`
- `0x18003941d`: `GetAllNonCoreNameResources`
- `0x180039489`: `GetAllNonCoreNameResources`
- `0x1800394cd`: `GetAllNonCoreNameResources`
- `0x18003954c`: `GetAllNonCoreNameResources`
- `0x180039574`: `GetAllNonCoreNameResources`
- `0x18003953a`: `Failed to open resource '%s', error %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetAllNonCoreNameResources(HCLUSTER hCluster, int a2, __int64 a3)
{
  struct _HCLUSTER *v3; // r12
  struct _HCLUSENUM *v4; // rbx
  DWORD LastError; // ebx
  DWORD v7; // r15d
  DWORD i; // r13d
  _BYTE *j; // rax
  __int64 v10; // rcx
  DWORD v11; // eax
  struct _HRESOURCE *v12; // r14
  wchar_t *v13; // rax
  unsigned int v14; // ebx
  DWORD v15; // esi
  CLUSTER_RESOURCE_STATE ClusterResourceState; // eax
  __int64 v17; // rcx
  __int16 v18; // r8
  __int64 v19; // xmm0_8
  int v20; // r9d
  __int16 v21; // r10
  __int64 v22; // r11
  __int64 v23; // rsi
  __int64 v24; // rcx
  __int64 v25; // rdx
  const wchar_t *v26; // rax
  __int64 v27; // r9
  void *v28; // [rsp+28h] [rbp-B1h]
  __int64 v29; // [rsp+30h] [rbp-A9h]
  void *Block; // [rsp+50h] [rbp-89h] BYREF
  wchar_t *String2; // [rsp+58h] [rbp-81h] BYREF
  unsigned int v32; // [rsp+60h] [rbp-79h] BYREF
  DWORD dwType[2]; // [rsp+68h] [rbp-71h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-69h] BYREF
  int v35; // [rsp+74h] [rbp-65h] BYREF
  unsigned int v36; // [rsp+78h] [rbp-61h] BYREF
  int v37; // [rsp+7Ch] [rbp-5Dh]
  struct _HCLUSENUM *v38; // [rsp+80h] [rbp-59h]
  HCLUSTER v39; // [rsp+88h] [rbp-51h]
  __int64 v40; // [rsp+90h] [rbp-49h]
  void **p_Block; // [rsp+98h] [rbp-41h]
  wchar_t **p_String2; // [rsp+A0h] [rbp-39h]
  char v43; // [rsp+A8h] [rbp-31h]
  struct _HRESOURCE *v44; // [rsp+B0h] [rbp-29h] BYREF
  __int128 v45; // [rsp+B8h] [rbp-21h]
  __int64 v46; // [rsp+C8h] [rbp-11h]
  __int64 v47; // [rsp+D0h] [rbp-9h]
  _BYTE v48[32]; // [rsp+D8h] [rbp-1h] BYREF

  v40 = a3;
  v37 = a2;
  v3 = hCluster;
  v39 = hCluster;
  if ( !hCluster
    || !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           hCluster,
                           hCluster) )
  {
    return 6;
  }
  Block = operator new[](0x208u);
  String2 = (wchar_t *)operator new[](0x208u);
  p_Block = &Block;
  p_String2 = &String2;
  v43 = 0;
  v36 = 0;
  v35 = 0;
  v4 = ClusterOpenEnum(v3, 4u);
  v38 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    TraceMsg(2, 0, L"GetAllNonCoreNameResources", 10276, L"Failed to open cluster enumeration, error %d.", LastError);
    if ( Block )
    {
      operator delete(Block);
      Block = 0;
    }
    if ( String2 )
      operator delete(String2);
    return LastError;
  }
  v7 = 260;
  v32 = 260;
  for ( i = 0; ; ++i )
  {
    for ( j = Block; ; Block = j )
    {
      cchName = v7;
      v10 = 2LL * v7;
      if ( v10 )
      {
        do
        {
          *j++ = 0;
          --v10;
        }
        while ( v10 );
        j = Block;
      }
      v11 = ClusterEnum(v4, i, dwType, (LPWSTR)j, &cchName);
      if ( v11 != 234 )
        break;
      if ( Block )
      {
        operator delete(Block);
        Block = 0;
      }
      v7 *= 2;
      j = operator new[](saturated_mul(v7, 2u));
    }
    if ( v11 )
    {
      LODWORD(v28) = 0;
      TraceMsg(2, 0, L"GetAllNonCoreNameResources", 10308, L"Failed to enumerate Resources, error %d.", v28);
      goto LABEL_54;
    }
    v12 = OpenClusterResourceImpl(v3, (const wchar_t *)Block, 0x10000000u, 0, 1);
    *(_QWORD *)dwType = v12;
    if ( !v12 )
    {
      v15 = GetLastError();
      LODWORD(v29) = v15;
      TraceMsg(2, 0, L"GetAllNonCoreNameResources", 10377, L"Failed to open resource '%s', error %d.", Block, v29);
      goto LABEL_47;
    }
    v13 = String2;
    v14 = v32;
    while ( 1 )
    {
      v32 = 0;
      v15 = ClusterpResourceControl(v12, 0, 0x100002Du, 0, 0, v13, v14, &v32, 0, 0);
      if ( v15 != 234 )
        break;
      if ( String2 )
      {
        operator delete(String2);
        String2 = 0;
      }
      v14 *= 2;
      v13 = (wchar_t *)operator new[](saturated_mul(v14, 2u));
      String2 = v13;
    }
    v32 = v14;
    v4 = v38;
    v3 = v39;
    if ( v15 )
      break;
    v15 = ClusterpResourceControl(v12, 0, 0x1000009u, 0, 0, &v35, 4u, &v36, 0, 0);
    if ( v15 )
    {
      v26 = L"Failed to get Resource flags, error %d.";
      v27 = 10344;
      goto LABEL_46;
    }
    if ( (v35 & 1) == 0 && (!wcscmp_0(L"Network Name", String2) || !wcscmp_0(L"Distributed Network Name", String2)) )
    {
      if ( !v37 )
      {
LABEL_33:
        v17 = std::wstring::wstring(v48, Block);
        v44 = v12;
        *(_QWORD *)dwType = 0;
        v45 = 0;
        v18 = *(_WORD *)v17;
        LOWORD(v45) = *(_WORD *)v17;
        v19 = *(_QWORD *)(v17 + 2);
        *(_QWORD *)((char *)&v45 + 2) = v19;
        v20 = *(_DWORD *)(v17 + 10);
        *(_DWORD *)((char *)&v45 + 10) = v20;
        v21 = *(_WORD *)(v17 + 14);
        HIWORD(v45) = v21;
        v22 = *(_QWORD *)(v17 + 16);
        v46 = v22;
        v23 = *(_QWORD *)(v17 + 24);
        v47 = v23;
        *(_QWORD *)(v17 + 16) = 0;
        *(_QWORD *)(v17 + 24) = 7;
        *(_WORD *)v17 = 0;
        v24 = v40;
        v25 = *(_QWORD *)(v40 + 8);
        if ( v25 == *(_QWORD *)(v40 + 16) )
        {
          std::vector<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>,std::wstring>>::_Emplace_reallocate<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>,std::wstring>>(
            v40,
            v25,
            &v44);
        }
        else
        {
          *(_QWORD *)v25 = v12;
          v44 = 0;
          *(_WORD *)(v25 + 8) = v18;
          *(_QWORD *)(v25 + 10) = v19;
          *(_DWORD *)(v25 + 18) = v20;
          *(_WORD *)(v25 + 22) = v21;
          *(_QWORD *)(v25 + 24) = v22;
          *(_QWORD *)(v25 + 32) = v23;
          v46 = 0;
          v47 = 7;
          LOWORD(v45) = 0;
          *(_QWORD *)(v24 + 8) += 40LL;
        }
        std::pair<cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>,std::wstring>::~pair<cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>,std::wstring>(&v44);
        std::wstring::_Tidy_deallocate(v48);
        goto LABEL_37;
      }
      ClusterResourceState = GetClusterResourceState(v12, 0, 0, 0, 0);
      if ( ClusterResourceState != ClusterResourceStateUnknown )
      {
        if ( ClusterResourceState != ClusterResourceOffline )
        {
          TraceMsg(2, 0, L"GetAllNonCoreNameResources", 10365, L"A Network Name is in the incorrect State");
          cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(dwType);
          ClusterCloseEnumCommon(v4, 1);
          if ( Block )
          {
            operator delete(Block);
            Block = 0;
          }
          if ( String2 )
            operator delete(String2);
          return 5023;
        }
        goto LABEL_33;
      }
      LODWORD(v28) = 0;
      TraceMsg(2, 0, L"GetAllNonCoreNameResources", 10359, L"Failed to get Resource state, error %d.", v28);
      cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(dwType);
LABEL_54:
      ClusterCloseEnumCommon(v4, 1);
      if ( Block )
      {
        operator delete(Block);
        Block = 0;
      }
      if ( String2 )
        operator delete(String2);
      return 0;
    }
LABEL_37:
    cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(dwType);
  }
  v26 = L"Failed to get Resource type string, error %d.";
  v27 = 10336;
LABEL_46:
  LODWORD(v28) = v15;
  TraceMsg(2, 0, L"GetAllNonCoreNameResources", v27, v26, v28);
LABEL_47:
  cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(dwType);
  ClusterCloseEnumCommon(v4, 1);
  if ( Block )
  {
    operator delete(Block);
    Block = 0;
  }
  if ( String2 )
    operator delete(String2);
  return v15;
}

```

## disassembly

```asm
0x180039028  mov     [rsp-8+arg_8], rbx
0x18003902d  push    rbp
0x18003902e  push    rsi
0x18003902f  push    rdi
0x180039030  push    r12
0x180039032  push    r13
0x180039034  push    r14
0x180039036  push    r15
0x180039038  lea     rbp, [rsp-27h]
0x18003903d  sub     rsp, 100h
0x180039044  mov     rax, cs:__security_cookie
0x18003904b  xor     rax, rsp
0x18003904e  mov     [rbp+57h+var_38], rax
0x180039052  mov     [rbp+57h+var_A0], r8
0x180039056  mov     [rbp+57h+var_B4], edx
0x180039059  mov     r12, rcx
0x18003905c  mov     [rbp+57h+var_A8], rcx
0x180039060  xor     esi, esi
0x180039062  test    rcx, rcx
0x180039065  jz      loc_1800395BA
0x18003906b  mov     rdx, rcx
0x18003906e  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x180039073  test    al, al
0x180039075  jz      loc_1800395BA
0x18003907b  mov     ebx, 208h
0x180039080  mov     ecx, ebx; unsigned __int64
0x180039082  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180039087  mov     [rsp+130h+Block], rax
0x18003908c  mov     ecx, ebx; unsigned __int64
0x18003908e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180039093  mov     [rsp+130h+String2], rax
0x180039098  lea     rax, [rsp+130h+Block]
0x18003909d  mov     [rbp+57h+var_98], rax
0x1800390a1  lea     rax, [rsp+130h+String2]
0x1800390a6  mov     [rbp+57h+var_90], rax
0x1800390aa  mov     [rbp+57h+var_88], sil
0x1800390ae  mov     [rbp+57h+var_B8], esi
0x1800390b1  mov     [rbp+57h+var_BC], esi
0x1800390b4  lea     edx, [rsi+4]; dwType
0x1800390b7  mov     rcx, r12; hCluster
0x1800390ba  call    ClusterOpenEnum
0x1800390bf  mov     rbx, rax
0x1800390c2  mov     [rbp+57h+var_B0], rax
0x1800390c6  test    rax, rax
0x1800390c9  jnz     short loc_180039125
0x1800390cb  call    cs:__imp_GetLastError
0x1800390d1  mov     ebx, eax
0x1800390d3  mov     dword ptr [rsp+130h+var_108], eax
0x1800390d7  lea     rax, aFailedToOpenCl_3; "Failed to open cluster enumeration, err"...
0x1800390de  mov     [rsp+130h+lpcchName], rax
0x1800390e3  mov     r9d, 2824h
0x1800390e9  lea     r8, aGetallnoncoren; "GetAllNonCoreNameResources"
0x1800390f0  xor     edx, edx
0x1800390f2  lea     ecx, [rsi+2]
0x1800390f5  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800390fa  nop
0x1800390fb  mov     rcx, [rsp+130h+Block]; Block
0x180039100  test    rcx, rcx
0x180039103  jz      short loc_18003910F
0x180039105  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003910a  mov     [rsp+130h+Block], rsi
0x18003910f  mov     rcx, [rsp+130h+String2]; Block
0x180039114  test    rcx, rcx
0x180039117  jz      short loc_18003911E
0x180039119  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003911e  mov     eax, ebx
0x180039120  jmp     loc_1800395BF
0x180039125  mov     r15d, 104h
0x18003912b  mov     [rbp+57h+var_D0], r15d
0x18003912f  mov     r13d, esi
0x180039132  mov     edi, 2
0x180039137  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003913b  mov     rax, [rsp+130h+Block]
0x180039140  mov     [rbp+57h+cchName], r15d
0x180039144  mov     ecx, r15d
0x180039147  add     rcx, rcx
0x18003914a  jz      short loc_18003915D
0x18003914c  mov     [rax], sil
0x18003914f  inc     rax
0x180039152  sub     rcx, 1
0x180039156  jnz     short loc_18003914C
0x180039158  mov     rax, [rsp+130h+Block]
0x18003915d  lea     rcx, [rbp+57h+cchName]
0x180039161  mov     [rsp+130h+lpcchName], rcx; lpcchName
0x180039166  mov     r9, rax; lpszName
0x180039169  lea     r8, [rbp+57h+dwType]; lpdwType
0x18003916d  mov     edx, r13d; dwIndex
0x180039170  mov     rcx, rbx; hEnum
0x180039173  call    ClusterEnum
0x180039178  cmp     eax, 0EAh
0x18003917d  jnz     short loc_1800391B2
0x18003917f  mov     rcx, [rsp+130h+Block]; Block
0x180039184  test    rcx, rcx
0x180039187  jz      short loc_180039193
0x180039189  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003918e  mov     [rsp+130h+Block], rsi
0x180039193  add     r15d, r15d
0x180039196  mov     ecx, r15d
0x180039199  mov     rax, rdi
0x18003919c  mul     rcx
0x18003919f  cmovb   rax, r14
0x1800391a3  mov     rcx, rax; unsigned __int64
0x1800391a6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800391ab  mov     [rsp+130h+Block], rax
0x1800391b0  jmp     short loc_180039140
0x1800391b2  test    eax, eax
0x1800391b4  jnz     loc_18003955E
0x1800391ba  mov     dword ptr [rsp+130h+lpcchName], 1; int
0x1800391c2  xor     r9d, r9d; unsigned int *
0x1800391c5  mov     r8d, 10000000h; unsigned int
0x1800391cb  mov     rdx, [rsp+130h+Block]; wchar_t *
0x1800391d0  mov     rcx, r12; struct _HCLUSTER *
0x1800391d3  call    ?OpenClusterResourceImpl@@YAPEAU_HRESOURCE@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z; OpenClusterResourceImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)
0x1800391d8  mov     r14, rax
0x1800391db  mov     qword ptr [rbp+57h+dwType], rax
0x1800391df  test    rax, rax
0x1800391e2  jz      loc_180039524
0x1800391e8  mov     rax, [rsp+130h+String2]
0x1800391ed  mov     ebx, [rbp+57h+var_D0]
0x1800391f0  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800391f4  mov     [rbp+57h+var_D0], esi
0x1800391f7  mov     [rsp+130h+var_E8], rsi; wchar_t *
0x1800391fc  mov     [rsp+130h+var_F0], sil; bool
0x180039201  lea     rcx, [rbp+57h+var_D0]
0x180039205  mov     [rsp+130h+var_F8], rcx; unsigned int *
0x18003920a  mov     dword ptr [rsp+130h+var_100], ebx; unsigned int
0x18003920e  mov     [rsp+130h+var_108], rax; void *
0x180039213  mov     dword ptr [rsp+130h+lpcchName], esi; unsigned int
0x180039217  xor     r9d, r9d; void *
0x18003921a  xor     edx, edx; struct _HNODE *
0x18003921c  mov     r8d, 100002Dh; unsigned int
0x180039222  mov     rcx, r14; struct _HRESOURCE *
0x180039225  call    ?ClusterpResourceControl@@YAKPEAU_HRESOURCE@@PEAU_HNODE@@KPEAXK2KPEAK_NPEB_W@Z; ClusterpResourceControl(_HRESOURCE *,_HNODE *,ulong,void *,ulong,void *,ulong,ulong *,bool,wchar_t const *)
0x18003922a  mov     esi, eax
0x18003922c  cmp     eax, 0EAh
0x180039231  jnz     short loc_180039266
0x180039233  mov     rcx, [rsp+130h+String2]; Block
0x180039238  xor     esi, esi
0x18003923a  test    rcx, rcx
0x18003923d  jz      short loc_180039249
0x18003923f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180039244  mov     [rsp+130h+String2], rsi
0x180039249  add     ebx, ebx
0x18003924b  mov     ecx, ebx
0x18003924d  mov     rax, rdi
0x180039250  mul     rcx
0x180039253  cmovb   rax, r12
0x180039257  mov     rcx, rax; unsigned __int64
0x18003925a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003925f  mov     [rsp+130h+String2], rax
0x180039264  jmp     short loc_1800391F4
0x180039266  mov     [rbp+57h+var_D0], ebx
0x180039269  xor     ecx, ecx
0x18003926b  test    esi, esi
0x18003926d  mov     rbx, [rbp+57h+var_B0]
0x180039271  mov     r12, [rbp+57h+var_A8]
0x180039275  jnz     loc_1800394B7
0x18003927b  mov     [rsp+130h+var_E8], rcx; wchar_t *
0x180039280  mov     [rsp+130h+var_F0], cl; bool
0x180039284  lea     rax, [rbp+57h+var_B8]
0x180039288  mov     [rsp+130h+var_F8], rax; unsigned int *
0x18003928d  mov     dword ptr [rsp+130h+var_100], 4; unsigned int
0x180039295  lea     rax, [rbp+57h+var_BC]
0x180039299  mov     [rsp+130h+var_108], rax; void *
0x18003929e  mov     dword ptr [rsp+130h+lpcchName], ecx; unsigned int
0x1800392a2  xor     r9d, r9d; void *
0x1800392a5  xor     edx, edx; struct _HNODE *
0x1800392a7  mov     r8d, 1000009h; unsigned int
0x1800392ad  mov     rcx, r14; struct _HRESOURCE *
0x1800392b0  call    ?ClusterpResourceControl@@YAKPEAU_HRESOURCE@@PEAU_HNODE@@KPEAXK2KPEAK_NPEB_W@Z; ClusterpResourceControl(_HRESOURCE *,_HNODE *,ulong,void *,ulong,void *,ulong,ulong *,bool,wchar_t const *)
0x1800392b5  mov     esi, eax
0x1800392b7  test    eax, eax
0x1800392b9  jnz     loc_1800394A8
0x1800392bf  test    byte ptr [rbp+57h+var_BC], 1
0x1800392c3  jnz     loc_1800393F8
0x1800392c9  mov     rdx, [rsp+130h+String2]; String2
0x1800392ce  lea     rcx, aNetworkName; "Network Name"
0x1800392d5  call    wcscmp_0
0x1800392da  xor     esi, esi
0x1800392dc  test    eax, eax
0x1800392de  jz      short loc_1800392F9
0x1800392e0  mov     rdx, [rsp+130h+String2]; String2
0x1800392e5  lea     rcx, aDistributedNet; "Distributed Network Name"
0x1800392ec  call    wcscmp_0
0x1800392f1  test    eax, eax
0x1800392f3  jnz     loc_1800393FA
0x1800392f9  cmp     [rbp+57h+var_B4], esi
0x1800392fc  jz      short loc_180039325
0x1800392fe  mov     [rsp+130h+lpcchName], rsi; lpcchGroupName
0x180039303  xor     r9d, r9d; lpszGroupName
0x180039306  xor     r8d, r8d; lpcchNodeName
0x180039309  xor     edx, edx; lpszNodeName
0x18003930b  mov     rcx, r14; hResource
0x18003930e  call    GetClusterResourceState
0x180039313  cmp     eax, 0FFFFFFFFh
0x180039316  jz      loc_180039473
0x18003931c  cmp     eax, 3
0x18003931f  jnz     loc_18003940B
0x180039325  mov     rdx, [rsp+130h+Block]
0x18003932a  lea     rcx, [rbp+57h+var_58]
0x18003932e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180039333  mov     rcx, rax
0x180039336  mov     [rbp+57h+var_80], r14
0x18003933a  mov     qword ptr [rbp+57h+dwType], rsi
0x18003933e  xorps   xmm0, xmm0
0x180039341  movups  [rbp+57h+var_78], xmm0
0x180039345  movzx   r8d, word ptr [rax]
0x180039349  mov     word ptr [rbp+57h+var_78], r8w
0x18003934e  movsd   xmm0, qword ptr [rax+2]
0x180039353  movsd   qword ptr [rbp+57h+var_78+2], xmm0
0x180039358  mov     r9d, [rax+0Ah]
0x18003935c  mov     dword ptr [rbp+57h+var_78+0Ah], r9d
0x180039360  movzx   r10d, word ptr [rax+0Eh]
0x180039365  mov     word ptr [rbp+57h+var_78+0Eh], r10w
0x18003936a  mov     r11, [rax+10h]
0x18003936e  mov     [rbp+57h+var_68], r11
0x180039372  mov     rsi, [rax+18h]
0x180039376  mov     [rbp+57h+var_60], rsi
0x18003937a  mov     qword ptr [rax+10h], 0
0x180039382  mov     qword ptr [rax+18h], 7
0x18003938a  xor     eax, eax
0x18003938c  mov     [rcx], ax
0x18003938f  mov     rcx, [rbp+57h+var_A0]
0x180039393  mov     rdx, [rcx+8]
0x180039397  cmp     rdx, [rcx+10h]
0x18003939b  jz      short loc_1800393D8
0x18003939d  mov     [rdx], r14
0x1800393a0  mov     [rbp+57h+var_80], rax
0x1800393a4  mov     [rdx+8], r8w
0x1800393a9  movsd   qword ptr [rdx+0Ah], xmm0
0x1800393ae  mov     [rdx+12h], r9d
0x1800393b2  mov     [rdx+16h], r10w
0x1800393b7  mov     [rdx+18h], r11
0x1800393bb  mov     [rdx+20h], rsi
0x1800393bf  xor     esi, esi
0x1800393c1  mov     [rbp+57h+var_68], rsi
0x1800393c5  mov     [rbp+57h+var_60], 7
0x1800393cd  mov     word ptr [rbp+57h+var_78], si
0x1800393d1  add     qword ptr [rcx+8], 28h ; '('
0x1800393d6  jmp     short loc_1800393E3
0x1800393d8  lea     r8, [rbp+57h+var_80]
0x1800393dc  call    ??$_Emplace_reallocate@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@?$vector@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@AEAAPEAU?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring>>::_Emplace_reallocate<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring>>(std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring> * const,std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring> &&)
0x1800393e1  xor     esi, esi
0x1800393e3  lea     rcx, [rbp+57h+var_80]
0x1800393e7  call    ??1?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring>::~pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring>(void)
0x1800393ec  nop
0x1800393ed  lea     rcx, [rbp+57h+var_58]
0x1800393f1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800393f6  jmp     short loc_1800393FA
0x1800393f8  xor     esi, esi
0x1800393fa  inc     r13d
0x1800393fd  lea     rcx, [rbp+57h+dwType]
0x180039401  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x180039406  jmp     loc_180039137
0x18003940b  lea     rax, aANetworkNameIs; "A Network Name is in the incorrect Stat"...
0x180039412  mov     [rsp+130h+lpcchName], rax
0x180039417  mov     r9d, 287Dh
0x18003941d  lea     r8, aGetallnoncoren; "GetAllNonCoreNameResources"
0x180039424  xor     edx, edx
0x180039426  mov     ecx, edi
0x180039428  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003942d  nop
0x18003942e  lea     rcx, [rbp+57h+dwType]
0x180039432  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x180039437  nop
0x180039438  mov     edx, 1; int
0x18003943d  mov     rcx, rbx; struct _HCLUSENUM *
0x180039440  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x180039445  nop
0x180039446  mov     rcx, [rsp+130h+Block]; Block
0x18003944b  test    rcx, rcx
0x18003944e  jz      short loc_18003945A
0x180039450  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180039455  mov     [rsp+130h+Block], rsi
0x18003945a  mov     rcx, [rsp+130h+String2]; Block
0x18003945f  test    rcx, rcx
0x180039462  jz      short loc_180039469
0x180039464  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180039469  mov     eax, 139Fh
0x18003946e  jmp     loc_1800395BF
0x180039473  mov     dword ptr [rsp+130h+var_108], esi
0x180039477  lea     rax, aFailedToGetRes; "Failed to get Resource state, error %d."
0x18003947e  mov     [rsp+130h+lpcchName], rax
0x180039483  mov     r9d, 2877h
0x180039489  lea     r8, aGetallnoncoren; "GetAllNonCoreNameResources"
0x180039490  xor     edx, edx
0x180039492  mov     ecx, edi
0x180039494  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180039499  nop
0x18003949a  lea     rcx, [rbp+57h+dwType]
0x18003949e  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x1800394a3  jmp     loc_180039585
0x1800394a8  lea     rax, aFailedToGetRes_2; "Failed to get Resource flags, error %d."
0x1800394af  mov     r9d, 2868h
0x1800394b5  jmp     short loc_1800394C4
0x1800394b7  lea     rax, aFailedToGetRes_4; "Failed to get Resource type string, err"...
0x1800394be  mov     r9d, 2860h
0x1800394c4  mov     dword ptr [rsp+130h+var_108], esi
0x1800394c8  mov     [rsp+130h+lpcchName], rax
0x1800394cd  lea     r8, aGetallnoncoren; "GetAllNonCoreNameResources"
  ... truncated ...
```
