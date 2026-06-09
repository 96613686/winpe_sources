# CCHlpCreateClusterNameInAD(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,ClusterNameADClusterState * *)

- ea: `0x18007a380`
- end: `0x18007a818`
- name: `?CCHlpCreateClusterNameInAD@@YAKPEB_W000HPEAPEAVClusterNameADClusterState@@@Z`
- size: `1176`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, wchar_t *, int, struct ClusterNameADClusterState **)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180002f50`
- `0x180003c14`
- `0x18001cc08`
- `0x18001fd7c`
- `0x180025650`
- `0x180028f30`
- `0x180029578`
- `0x18003a1f0`
- `0x18003aa0c`
- `0x18006f910`
- `0x180071b48`
- `0x180074b2c`
- `0x180078c10`
- `0x18007a380`
- `0x1800a4510`
- `0x1800a4548`
- `0x1800a4d98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a55d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a55d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007a553`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007a553`

## string_xrefs

- `0x18007a61f`: `Getting OS and OS version from node computer object failed. Error %d.`
- `0x18007a445`: `CCHlpCreateClusterNameInAD`
- `0x18007a503`: `CCHlpCreateClusterNameInAD`
- `0x18007a57b`: `CCHlpCreateClusterNameInAD`
- `0x18007a631`: `CCHlpCreateClusterNameInAD`
- `0x18007a6f7`: `CCHlpCreateClusterNameInAD`
- `0x18007a795`: `CCHlpCreateClusterNameInAD`
- `0x18007a4f1`: `Failed to create cluster name %ws in AD, error %d`
- `0x18007a783`: `Node computer object is not found.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCHlpCreateClusterNameInAD(
        const wchar_t *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        wchar_t *a4,
        int a5,
        struct ClusterNameADClusterState **a6)
{
  int v9; // esi
  struct _HCLUSTER *v10; // rdi
  DWORD LastError; // ebx
  unsigned __int16 ClusterFunctionalLevel; // bx
  unsigned __int16 ClusterUpgradeVersion; // ax
  unsigned int v15; // eax
  __int64 v16; // rcx
  int OSVersion; // eax
  const wchar_t *v18; // rbx
  const wchar_t *v19; // rax
  unsigned int v20; // eax
  wchar_t *v21; // [rsp+28h] [rbp-D8h]
  wchar_t *v22; // [rsp+28h] [rbp-D8h]
  wchar_t *v23; // [rsp+30h] [rbp-D0h]
  struct CreateClusterADState *v24; // [rsp+50h] [rbp-B0h] BYREF
  struct CreateClusterADState *v25; // [rsp+58h] [rbp-A8h] BYREF
  DWORD nSize; // [rsp+60h] [rbp-A0h] BYREF
  struct ClusterNameADClusterState *v27; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v28; // [rsp+70h] [rbp-90h]
  _QWORD v29[2]; // [rsp+78h] [rbp-88h] BYREF
  int v30; // [rsp+88h] [rbp-78h]
  __int64 v31; // [rsp+8Ch] [rbp-74h]
  int v32; // [rsp+94h] [rbp-6Ch]
  __int64 v33; // [rsp+98h] [rbp-68h]
  struct CreateClusterADState **v34; // [rsp+A0h] [rbp-60h]
  char v35; // [rsp+A8h] [rbp-58h]
  _BYTE v36[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v37[32]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Buffer[256]; // [rsp+F0h] [rbp-10h] BYREF

  v28 = a4;
  v29[0] = get_startup_argv_mode;
  v9 = 0;
  v29[1] = 0;
  v30 = 1;
  v31 = 1;
  v32 = 1;
  v33 = 0;
  v24 = 0;
  v10 = OpenClusterImpl(a1, 0x10000000u, 0, 1, 0, 0);
  cxl::AutoHandle<_HCLUSTER *,int,&int CloseCluster(_HCLUSTER *),0>::Close(&v24);
  v24 = v10;
  if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    TraceMsg(
      2,
      0,
      L"CCHlpCreateClusterNameInAD",
      1144,
      L"Can't get cluster handle to node %ws, error %d",
      a1,
      LastError);
    cxl::AutoHandle<_HCLUSTER *,int,&int CloseCluster(_HCLUSTER *),0>::Close(&v24);
    return LastError;
  }
  ClusterFunctionalLevel = GetClusterFunctionalLevel(v10);
  ClusterUpgradeVersion = GetClusterUpgradeVersion(v10);
  if ( ClusterFunctionalLevel > 0xBu || ClusterFunctionalLevel == 11 && ClusterUpgradeVersion >= 2u )
    v9 = 1;
  cxl::AutoHandle<_HCLUSTER *,int,&int CloseCluster(_HCLUSTER *),0>::Close(&v24);
  v25 = 0;
  v15 = CreateClusterNameInAD((struct PhaseManager *)v29, a1, a2, 0, 0, 0, a3, a5, &v25, v9);
  LastError = v15;
  if ( v15 )
  {
    LODWORD(v23) = v15;
    TraceMsg(2, 0, L"CCHlpCreateClusterNameInAD", 1174, L"Failed to create cluster name %ws in AD, error %d", a2, v23);
    return LastError;
  }
  v34 = &v25;
  v35 = 0;
  v24 = v25;
  memset_0(Buffer, 0, sizeof(Buffer));
  nSize = 256;
  if ( !GetComputerNameExW(ComputerNameDnsDomain, Buffer, &nSize) )
  {
    LastError = GetLastError();
    LODWORD(v21) = LastError;
    TraceMsg(2, 0, L"CCHlpCreateClusterNameInAD", 1199, L"Failed to get DNS domain name. Error %d.", v21);
    std::unique_ptr<CreateClusterADState>::~unique_ptr<CreateClusterADState>(&v24);
    if ( !v25 )
      return LastError;
    if ( !*((_BYTE *)v25 + 24) )
    {
      if ( *((_BYTE *)v25 + 25) )
        ClusterADObject::DisableAccount(*((ClusterADObject **)v25 + 1));
      return LastError;
    }
    goto LABEL_30;
  }
  std::wstring::wstring(v37);
  std::wstring::wstring(v36);
  v16 = *((_QWORD *)v25 + 2);
  if ( v16 )
  {
    OSVersion = ClusterADObject::GetOSVersion(v16, v37, v36);
    if ( OSVersion < 0 )
    {
      if ( (OSVersion & 0x1FFF0000) != 0x70000 || (LastError = (unsigned __int16)OSVersion, !(_WORD)OSVersion) )
        LastError = OSVersion;
      LODWORD(v21) = LastError;
      TraceMsg(
        2,
        0,
        L"CCHlpCreateClusterNameInAD",
        1212,
        L"Getting OS and OS version from node computer object failed. Error %d.",
        v21);
      std::wstring::_Tidy_deallocate(v36);
      std::wstring::_Tidy_deallocate(v37);
      std::unique_ptr<CreateClusterADState>::~unique_ptr<CreateClusterADState>(&v24);
      if ( !v25 )
        return LastError;
      if ( !*((_BYTE *)v25 + 24) )
      {
        if ( *((_BYTE *)v25 + 25) )
          ClusterADObject::DisableAccount(*((ClusterADObject **)v25 + 1));
        return LastError;
      }
LABEL_30:
      ClusterADObject::DeleteAccount(*((ClusterADObject **)v25 + 1));
      return LastError;
    }
    v27 = 0;
    v18 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v36);
    v19 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v37);
    v20 = ModifyClusterObjectInAD((struct PhaseManager *)v29, v25, v28, Buffer, v19, v18, &v27, v9);
    LastError = v20;
    if ( v20 )
    {
      LODWORD(v22) = v20;
      TraceMsg(2, 0, L"CCHlpCreateClusterNameInAD", 1236, L"Modifying cluster name in AD failed. Error %d.", v22);
      std::wstring::_Tidy_deallocate(v36);
      std::wstring::_Tidy_deallocate(v37);
      std::unique_ptr<CreateClusterADState>::~unique_ptr<CreateClusterADState>(&v24);
      if ( !v25 )
        return LastError;
      if ( !*((_BYTE *)v25 + 24) )
      {
        if ( *((_BYTE *)v25 + 25) )
          ClusterADObject::DisableAccount(*((ClusterADObject **)v25 + 1));
        return LastError;
      }
      goto LABEL_30;
    }
    *a6 = v27;
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v37);
    std::unique_ptr<CreateClusterADState>::~unique_ptr<CreateClusterADState>(&v24);
    return 0;
  }
  else
  {
    TraceMsg(2, 0, L"CCHlpCreateClusterNameInAD", 1218, L"Node computer object is not found.");
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v37);
    std::unique_ptr<CreateClusterADState>::~unique_ptr<CreateClusterADState>(&v24);
    if ( v25 )
    {
      if ( *((_BYTE *)v25 + 24) )
      {
        ClusterADObject::DeleteAccount(*((ClusterADObject **)v25 + 1));
      }
      else if ( *((_BYTE *)v25 + 25) )
      {
        ClusterADObject::DisableAccount(*((ClusterADObject **)v25 + 1));
      }
    }
    return 4312;
  }
}

```

## disassembly

```asm
0x18007a380  push    rbp
0x18007a382  push    rbx
0x18007a383  push    rsi
0x18007a384  push    rdi
0x18007a385  push    r12
0x18007a387  push    r13
0x18007a389  push    r14
0x18007a38b  push    r15
0x18007a38d  lea     rbp, [rsp-208h]
0x18007a395  sub     rsp, 308h
0x18007a39c  mov     rax, cs:__security_cookie
0x18007a3a3  xor     rax, rsp
0x18007a3a6  mov     [rbp+240h+var_50], rax
0x18007a3ad  mov     [rsp+340h+var_2D0], r9
0x18007a3b2  mov     r13, r8
0x18007a3b5  mov     r15, rdx
0x18007a3b8  mov     r14, rcx
0x18007a3bb  mov     r12, [rbp+240h+arg_28]
0x18007a3c2  lea     rax, _get_startup_argv_mode
0x18007a3c9  mov     [rsp+340h+var_2C8], rax
0x18007a3ce  xor     esi, esi
0x18007a3d0  mov     [rbp+240h+var_2C0], rsi
0x18007a3d4  lea     eax, [rsi+1]
0x18007a3d7  mov     [rbp+240h+var_2B8], eax
0x18007a3da  mov     [rbp+240h+var_2B4], rax
0x18007a3de  mov     [rbp+240h+var_2AC], eax
0x18007a3e1  mov     [rbp+240h+var_2A8], rsi
0x18007a3e5  mov     [rsp+340h+var_2F0], rsi
0x18007a3ea  mov     [rsp+340h+var_318], rsi; struct CLUS_AUTH_INFO *
0x18007a3ef  mov     dword ptr [rsp+340h+var_320], esi; int
0x18007a3f3  mov     r9d, eax; int
0x18007a3f6  xor     r8d, r8d; unsigned int *
0x18007a3f9  mov     edx, 10000000h; unsigned int
0x18007a3fe  call    ?OpenClusterImpl@@YAPEAU_HCLUSTER@@PEB_WKPEAKHHPEAUCLUS_AUTH_INFO@@@Z; OpenClusterImpl(wchar_t const *,ulong,ulong *,int,int,CLUS_AUTH_INFO *)
0x18007a403  mov     rdi, rax
0x18007a406  lea     rcx, [rsp+340h+var_2F0]
0x18007a40b  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x18007a410  mov     [rsp+340h+var_2F0], rdi
0x18007a415  lea     rcx, [rdi+1]
0x18007a419  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18007a420  jnz     short loc_18007A468
0x18007a422  call    cs:__imp_GetLastError
0x18007a428  mov     ebx, eax
0x18007a42a  mov     dword ptr [rsp+340h+var_310], eax
0x18007a42e  mov     [rsp+340h+var_318], r14
0x18007a433  lea     rax, aCanTGetCluster; "Can't get cluster handle to node %ws, e"...
0x18007a43a  mov     [rsp+340h+var_320], rax
0x18007a43f  mov     r9d, 478h
0x18007a445  lea     r8, aCchlpcreateclu_2; "CCHlpCreateClusterNameInAD"
0x18007a44c  xor     edx, edx
0x18007a44e  lea     ecx, [rsi+2]
0x18007a451  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18007a456  nop
0x18007a457  lea     rcx, [rsp+340h+var_2F0]
0x18007a45c  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x18007a461  mov     eax, ebx
0x18007a463  jmp     loc_18007A7F5
0x18007a468  mov     rcx, rdi; hCluster
0x18007a46b  call    ?GetClusterFunctionalLevel@@YAGPEAU_HCLUSTER@@@Z; GetClusterFunctionalLevel(_HCLUSTER *)
0x18007a470  movzx   ebx, ax
0x18007a473  mov     rcx, rdi; struct _HCLUSTER *
0x18007a476  call    ?GetClusterUpgradeVersion@@YAGPEAU_HCLUSTER@@@Z; GetClusterUpgradeVersion(_HCLUSTER *)
0x18007a47b  mov     edi, 2
0x18007a480  cmp     bx, 0Bh
0x18007a484  ja      short loc_18007A48D
0x18007a486  jnz     short loc_18007A492
0x18007a488  cmp     ax, di
0x18007a48b  jb      short loc_18007A492
0x18007a48d  mov     esi, 1
0x18007a492  lea     rcx, [rsp+340h+var_2F0]
0x18007a497  call    ?Close@?$AutoHandle@PEAU_HCLUSTER@@H$1?CloseCluster@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSTER *,int,&CloseCluster(_HCLUSTER *),0>::Close(void)
0x18007a49c  mov     [rsp+340h+var_2E8], 0
0x18007a4a5  mov     [rsp+340h+var_2F8], esi; int
0x18007a4a9  lea     rax, [rsp+340h+var_2E8]
0x18007a4ae  mov     [rsp+340h+var_300], rax; struct CreateClusterADState **
0x18007a4b3  mov     eax, [rbp+240h+arg_20]
0x18007a4b9  mov     [rsp+340h+var_308], eax; int
0x18007a4bd  mov     [rsp+340h+var_310], r13; wchar_t *
0x18007a4c2  xor     r13d, r13d
0x18007a4c5  mov     [rsp+340h+var_318], r13; wchar_t *
0x18007a4ca  mov     [rsp+340h+var_320], r13; wchar_t *
0x18007a4cf  xor     r9d, r9d; wchar_t *
0x18007a4d2  mov     r8, r15; wchar_t *
0x18007a4d5  mov     rdx, r14; wchar_t *
0x18007a4d8  lea     rcx, [rsp+340h+var_2C8]; struct PhaseManager *
0x18007a4dd  call    ?CreateClusterNameInAD@@YAKAEAVPhaseManager@@PEB_W11111HPEAPEAVCreateClusterADState@@H@Z; CreateClusterNameInAD(PhaseManager &,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,CreateClusterADState * *,int)
0x18007a4e2  mov     ebx, eax
0x18007a4e4  test    eax, eax
0x18007a4e6  jz      short loc_18007A518
0x18007a4e8  mov     dword ptr [rsp+340h+var_310], eax
0x18007a4ec  mov     [rsp+340h+var_318], r15
0x18007a4f1  lea     rax, aFailedToCreate_20; "Failed to create cluster name %ws in AD"...
0x18007a4f8  mov     [rsp+340h+var_320], rax
0x18007a4fd  mov     r9d, 496h
0x18007a503  lea     r8, aCchlpcreateclu_2; "CCHlpCreateClusterNameInAD"
0x18007a50a  xor     edx, edx
0x18007a50c  mov     ecx, edi
0x18007a50e  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18007a513  jmp     loc_18007A461
0x18007a518  lea     rax, [rsp+340h+var_2E8]
0x18007a51d  mov     [rbp+240h+var_2A0], rax
0x18007a521  mov     [rbp+240h+var_298], r13b
0x18007a525  mov     rax, [rsp+340h+var_2E8]
0x18007a52a  mov     [rsp+340h+var_2F0], rax
0x18007a52f  xor     edx, edx; Val
0x18007a531  mov     r8d, 200h; Size
0x18007a537  lea     rcx, [rbp+240h+Buffer]; void *
0x18007a53b  call    memset_0
0x18007a540  mov     [rsp+340h+nSize], 100h
0x18007a548  lea     r8, [rsp+340h+nSize]; nSize
0x18007a54d  lea     rdx, [rbp+240h+Buffer]; lpBuffer
0x18007a551  mov     ecx, edi; NameType
0x18007a553  call    cs:__imp_GetComputerNameExW
0x18007a559  test    eax, eax
0x18007a55b  jnz     short loc_18007A5C7
0x18007a55d  call    cs:__imp_GetLastError
0x18007a563  mov     ebx, eax
0x18007a565  mov     dword ptr [rsp+340h+var_318], eax
0x18007a569  lea     rax, aFailedToGetDns; "Failed to get DNS domain name. Error %d"...
0x18007a570  mov     [rsp+340h+var_320], rax
0x18007a575  mov     r9d, 4AFh
0x18007a57b  lea     r8, aCchlpcreateclu_2; "CCHlpCreateClusterNameInAD"
0x18007a582  xor     edx, edx
0x18007a584  mov     ecx, edi
0x18007a586  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18007a58b  nop
0x18007a58c  lea     rcx, [rsp+340h+var_2F0]
0x18007a591  call    ??1?$unique_ptr@VCreateClusterADState@@U?$default_delete@VCreateClusterADState@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateClusterADState>::~unique_ptr<CreateClusterADState>(void)
0x18007a596  nop
0x18007a597  mov     rcx, [rsp+340h+var_2E8]
0x18007a59c  test    rcx, rcx
0x18007a59f  jz      short loc_18007A5C2
0x18007a5a1  cmp     [rcx+18h], r13b
0x18007a5a5  jz      short loc_18007A5B2
0x18007a5a7  mov     rcx, [rcx+8]; this
0x18007a5ab  call    ?DeleteAccount@ClusterADObject@@QEAAJXZ; ClusterADObject::DeleteAccount(void)
0x18007a5b0  jmp     short loc_18007A5C2
0x18007a5b2  cmp     [rcx+19h], r13b
0x18007a5b6  jz      short loc_18007A5C2
0x18007a5b8  mov     rcx, [rcx+8]; this
0x18007a5bc  call    ?DisableAccount@ClusterADObject@@QEAAJXZ; ClusterADObject::DisableAccount(void)
0x18007a5c1  nop
0x18007a5c2  jmp     loc_18007A461
0x18007a5c7  lea     rcx, [rbp+240h+var_270]
0x18007a5cb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007a5d0  nop
0x18007a5d1  lea     rcx, [rbp+240h+var_290]
0x18007a5d5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007a5da  nop
0x18007a5db  mov     rax, [rsp+340h+var_2E8]
0x18007a5e0  mov     rcx, [rax+10h]
0x18007a5e4  test    rcx, rcx
0x18007a5e7  jz      loc_18007A783
0x18007a5ed  lea     r8, [rbp+240h+var_290]
0x18007a5f1  lea     rdx, [rbp+240h+var_270]
0x18007a5f5  call    ?GetOSVersion@ClusterADObject@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; ClusterADObject::GetOSVersion(std::wstring &,std::wstring &)
0x18007a5fa  test    eax, eax
0x18007a5fc  jns     loc_18007A691
0x18007a602  mov     ecx, eax
0x18007a604  and     ecx, 1FFF0000h
0x18007a60a  cmp     ecx, 70000h
0x18007a610  jnz     short loc_18007A619
0x18007a612  movzx   ebx, ax
0x18007a615  test    ebx, ebx
0x18007a617  jnz     short loc_18007A61B
0x18007a619  mov     ebx, eax
0x18007a61b  mov     dword ptr [rsp+340h+var_318], ebx
0x18007a61f  lea     rax, aGettingOsAndOs; "Getting OS and OS version from node com"...
0x18007a626  mov     [rsp+340h+var_320], rax
0x18007a62b  mov     r9d, 4BCh
0x18007a631  lea     r8, aCchlpcreateclu_2; "CCHlpCreateClusterNameInAD"
0x18007a638  xor     edx, edx
0x18007a63a  mov     ecx, edi
0x18007a63c  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18007a641  nop
0x18007a642  lea     rcx, [rbp+240h+var_290]
0x18007a646  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a64b  nop
0x18007a64c  lea     rcx, [rbp+240h+var_270]
0x18007a650  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a655  nop
0x18007a656  lea     rcx, [rsp+340h+var_2F0]
0x18007a65b  call    ??1?$unique_ptr@VCreateClusterADState@@U?$default_delete@VCreateClusterADState@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateClusterADState>::~unique_ptr<CreateClusterADState>(void)
0x18007a660  nop
0x18007a661  mov     rcx, [rsp+340h+var_2E8]
0x18007a666  test    rcx, rcx
0x18007a669  jz      short loc_18007A68C
0x18007a66b  cmp     [rcx+18h], r13b
0x18007a66f  jz      short loc_18007A67C
0x18007a671  mov     rcx, [rcx+8]; this
0x18007a675  call    ?DeleteAccount@ClusterADObject@@QEAAJXZ; ClusterADObject::DeleteAccount(void)
0x18007a67a  jmp     short loc_18007A68C
0x18007a67c  cmp     [rcx+19h], r13b
0x18007a680  jz      short loc_18007A68C
0x18007a682  mov     rcx, [rcx+8]; this
0x18007a686  call    ?DisableAccount@ClusterADObject@@QEAAJXZ; ClusterADObject::DisableAccount(void)
0x18007a68b  nop
0x18007a68c  jmp     loc_18007A461
0x18007a691  mov     [rsp+340h+var_2D8], r13
0x18007a696  lea     rcx, [rbp+240h+var_290]
0x18007a69a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18007a69f  mov     rbx, rax
0x18007a6a2  lea     rcx, [rbp+240h+var_270]
0x18007a6a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18007a6ab  mov     [rsp+340h+var_308], esi; int
0x18007a6af  lea     rcx, [rsp+340h+var_2D8]
0x18007a6b4  mov     [rsp+340h+var_310], rcx; struct ClusterNameADClusterState **
0x18007a6b9  mov     [rsp+340h+var_318], rbx; wchar_t *
0x18007a6be  mov     [rsp+340h+var_320], rax; wchar_t *
0x18007a6c3  lea     r9, [rbp+240h+Buffer]; wchar_t *
0x18007a6c7  mov     r8, [rsp+340h+var_2D0]; wchar_t *
0x18007a6cc  mov     rdx, [rsp+340h+var_2E8]; struct CreateClusterADState *
0x18007a6d1  lea     rcx, [rsp+340h+var_2C8]; this
0x18007a6d6  call    ?ModifyClusterObjectInAD@@YAKAEAVPhaseManager@@PEAVCreateClusterADState@@PEB_W222PEAPEAVClusterNameADClusterState@@H@Z; ModifyClusterObjectInAD(PhaseManager &,CreateClusterADState *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ClusterNameADClusterState * *,int)
0x18007a6db  mov     ebx, eax
0x18007a6dd  test    eax, eax
0x18007a6df  jz      short loc_18007A757
0x18007a6e1  mov     dword ptr [rsp+340h+var_318], eax
0x18007a6e5  lea     rax, aModifyingClust_0; "Modifying cluster name in AD failed. Er"...
0x18007a6ec  mov     [rsp+340h+var_320], rax
0x18007a6f1  mov     r9d, 4D4h
0x18007a6f7  lea     r8, aCchlpcreateclu_2; "CCHlpCreateClusterNameInAD"
0x18007a6fe  xor     edx, edx
0x18007a700  mov     ecx, edi
0x18007a702  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18007a707  nop
0x18007a708  lea     rcx, [rbp+240h+var_290]
0x18007a70c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a711  nop
0x18007a712  lea     rcx, [rbp+240h+var_270]
0x18007a716  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a71b  nop
0x18007a71c  lea     rcx, [rsp+340h+var_2F0]
0x18007a721  call    ??1?$unique_ptr@VCreateClusterADState@@U?$default_delete@VCreateClusterADState@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateClusterADState>::~unique_ptr<CreateClusterADState>(void)
0x18007a726  nop
0x18007a727  mov     rcx, [rsp+340h+var_2E8]
0x18007a72c  test    rcx, rcx
0x18007a72f  jz      short loc_18007A752
0x18007a731  cmp     [rcx+18h], r13b
0x18007a735  jz      short loc_18007A742
0x18007a737  mov     rcx, [rcx+8]; this
0x18007a73b  call    ?DeleteAccount@ClusterADObject@@QEAAJXZ; ClusterADObject::DeleteAccount(void)
0x18007a740  jmp     short loc_18007A752
0x18007a742  cmp     [rcx+19h], r13b
0x18007a746  jz      short loc_18007A752
0x18007a748  mov     rcx, [rcx+8]; this
0x18007a74c  call    ?DisableAccount@ClusterADObject@@QEAAJXZ; ClusterADObject::DisableAccount(void)
0x18007a751  nop
0x18007a752  jmp     loc_18007A461
0x18007a757  mov     rax, [rsp+340h+var_2D8]
0x18007a75c  mov     [r12], rax
0x18007a760  lea     rcx, [rbp+240h+var_290]
0x18007a764  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a769  nop
0x18007a76a  lea     rcx, [rbp+240h+var_270]
0x18007a76e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a773  nop
0x18007a774  lea     rcx, [rsp+340h+var_2F0]
0x18007a779  call    ??1?$unique_ptr@VCreateClusterADState@@U?$default_delete@VCreateClusterADState@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateClusterADState>::~unique_ptr<CreateClusterADState>(void)
0x18007a77e  nop
0x18007a77f  xor     eax, eax
0x18007a781  jmp     short loc_18007A7F5
0x18007a783  lea     rax, aNodeComputerOb; "Node computer object is not found."
0x18007a78a  mov     [rsp+340h+var_320], rax
0x18007a78f  mov     r9d, 4C2h
0x18007a795  lea     r8, aCchlpcreateclu_2; "CCHlpCreateClusterNameInAD"
0x18007a79c  xor     edx, edx
0x18007a79e  mov     ecx, edi
0x18007a7a0  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18007a7a5  nop
0x18007a7a6  lea     rcx, [rbp+240h+var_290]
0x18007a7aa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a7af  nop
0x18007a7b0  lea     rcx, [rbp+240h+var_270]
0x18007a7b4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a7b9  nop
0x18007a7ba  lea     rcx, [rsp+340h+var_2F0]
0x18007a7bf  call    ??1?$unique_ptr@VCreateClusterADState@@U?$default_delete@VCreateClusterADState@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateClusterADState>::~unique_ptr<CreateClusterADState>(void)
0x18007a7c4  nop
0x18007a7c5  mov     rcx, [rsp+340h+var_2E8]
0x18007a7ca  test    rcx, rcx
0x18007a7cd  jz      short loc_18007A7F0
0x18007a7cf  cmp     [rcx+18h], r13b
0x18007a7d3  jz      short loc_18007A7E0
0x18007a7d5  mov     rcx, [rcx+8]; this
0x18007a7d9  call    ?DeleteAccount@ClusterADObject@@QEAAJXZ; ClusterADObject::DeleteAccount(void)
0x18007a7de  jmp     short loc_18007A7F0
0x18007a7e0  cmp     [rcx+19h], r13b
0x18007a7e4  jz      short loc_18007A7F0
0x18007a7e6  mov     rcx, [rcx+8]; this
0x18007a7ea  call    ?DisableAccount@ClusterADObject@@QEAAJXZ; ClusterADObject::DisableAccount(void)
0x18007a7ef  nop
0x18007a7f0  mov     eax, 10D8h
0x18007a7f5  mov     rcx, [rbp+240h+var_50]
0x18007a7fc  xor     rcx, rsp; StackCookie
0x18007a7ff  call    __security_check_cookie
0x18007a804  add     rsp, 308h
0x18007a80b  pop     r15
0x18007a80d  pop     r14
0x18007a80f  pop     r13
  ... truncated ...
```
