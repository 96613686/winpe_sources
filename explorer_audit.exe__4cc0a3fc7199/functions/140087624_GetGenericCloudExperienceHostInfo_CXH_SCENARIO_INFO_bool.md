# GetGenericCloudExperienceHostInfo(_CXH_SCENARIO_INFO * *,bool *)

- ea: `0x140087624`
- end: `0x140087914`
- name: `?GetGenericCloudExperienceHostInfo@@YAJPEAPEAU_CXH_SCENARIO_INFO@@PEA_N@Z`
- size: `752`
- prototype: `__int64 __fastcall(struct _CXH_SCENARIO_INFO **, bool *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14009d5c0`
- `0x1401ab210`

## callees

- `0x14001eba8`
- `0x1400811ac`
- `0x14008192c`
- `0x14008194c`
- `0x140087624`
- `0x1400954e0`
- `0x14009ef5c`
- `0x140107518`
- `0x1401ce504`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x140087755`
- `ntdll!RtlPublishWnfStateData` at `0x140087755`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400876e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140087877`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400878e3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400876e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140087877`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400878e3`
- `dsreg!DsrGetCxhScenarioInfo` at `0x1400876ad`
- `dsreg!DsrGetCxhScenarioInfo` at `0x1400877eb`
- `dsreg!DsrGetCxhScenarioInfo` at `0x14008784e`
- `dsreg!DsrGetCxhScenarioInfo` at `0x1400878b7`
- `dsreg!DsrGetCxhScenarioInfo` at `0x1400876ad`
- `dsreg!DsrGetCxhScenarioInfo` at `0x1400877eb`
- `dsreg!DsrGetCxhScenarioInfo` at `0x14008784e`
- `dsreg!DsrGetCxhScenarioInfo` at `0x1400878b7`
- `dsreg!DsrCanCurrentUserResetNgcKey` at `0x14008770c`
- `dsreg!DsrCanCurrentUserResetNgcKey` at `0x14008770c`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x1400877d1`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x140087832`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x14008789b`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x1400877d1`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x140087832`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x14008789b`
- `ext-ms-win-security-cfl-l1-1-0!CflGetScenarioData` at `0x14008767c`
- `ext-ms-win-security-cfl-l1-1-0!CflGetScenarioData` at `0x14008767c`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x140087695`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x140087695`

## pseudocode

```c
__int64 __fastcall GetGenericCloudExperienceHostInfo(struct _CXH_SCENARIO_INFO **a1, bool *a2)
{
  unsigned int ScenarioData; // ebx
  int CxhScenarioInfo; // eax
  __int64 v6; // r9
  __int64 v7; // rdx
  char v8; // bl
  int CanCurrentUserResetNgcKey; // eax
  int PinResetPolicyFailureState; // eax
  int v11; // eax
  __int64 v13; // rsi
  int v14; // esi
  __int64 v15; // rdx
  __int64 v16; // rsi
  __int64 v17; // rsi
  int bIgnoreCase; // [rsp+20h] [rbp-28h]
  int bIgnoreCasea; // [rsp+20h] [rbp-28h]
  LPCWCH lpString1; // [rsp+30h] [rbp-18h] BYREF
  _BYTE v21[16]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  int v23; // [rsp+80h] [rbp+38h] BYREF
  unsigned int v24; // [rsp+88h] [rbp+40h] BYREF
  int v25; // [rsp+90h] [rbp+48h] BYREF
  __int64 v26; // [rsp+98h] [rbp+50h] BYREF

  *a1 = 0;
  *a2 = 0;
  if ( !(unsigned __int8)IsCflGetScenarioDataPresent() )
  {
    ScenarioData = -2146893807;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
      (const char *)0x80090011LL,
      bIgnoreCase);
    return ScenarioData;
  }
  lpString1 = 0;
  ScenarioData = CflGetScenarioData(&lpString1, 0, 0);
  if ( (ScenarioData & 0x80000000) == 0 )
  {
    v26 = 0;
    CxhScenarioInfo = DsrGetCxhScenarioInfo(3, &v26);
    ScenarioData = CxhScenarioInfo;
    if ( CxhScenarioInfo < 0 )
    {
      v6 = (unsigned int)CxhScenarioInfo;
      v7 = 206;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
        (const char *)v6,
        bIgnoreCase);
      goto LABEL_16;
    }
    v8 = 1;
    if ( CompareStringOrdinal(lpString1, -1, *(LPCWCH *)(v26 + 8), -1, 1) == 2 )
    {
      v25 = 0;
      v23 = 0;
      v24 = 0;
      *a2 = 1;
      CanCurrentUserResetNgcKey = DsrCanCurrentUserResetNgcKey(0, &v23, &v24);
      if ( CanCurrentUserResetNgcKey < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD9,
          (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
          (const char *)(unsigned int)CanCurrentUserResetNgcKey,
          bIgnoreCasea);
LABEL_11:
        v8 = 0;
        PinResetPolicyFailureState = GetPinResetPolicyFailureState();
        goto LABEL_12;
      }
      if ( !v23 )
        goto LABEL_11;
      v13 = v26;
      if ( v26 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v21);
        DsrFreeCxhScenarioInfo(v13);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v21);
      }
      v26 = 0;
      v14 = DsrGetCxhScenarioInfo(v24, &v26);
      if ( v14 >= 0 )
      {
        PinResetPolicyFailureState = 1;
LABEL_12:
        v25 = PinResetPolicyFailureState;
        bIgnoreCase = 0;
        v11 = RtlPublishWnfStateData(WNF_NGC_PIN_RESET_SCENARIO_STATE_CHANGE, 0, &v25, 4) | 0x10000000;
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xE8,
            (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
            (const char *)(unsigned int)v11,
            0);
        if ( v8 )
          goto LABEL_15;
LABEL_35:
        ScenarioData = -2146893807;
        v7 = 251;
        v6 = 2148073489LL;
        goto LABEL_36;
      }
      v15 = 221;
    }
    else
    {
      v16 = v26;
      if ( v26 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v23);
        DsrFreeCxhScenarioInfo(v16);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v23);
      }
      v26 = 0;
      v14 = DsrGetCxhScenarioInfo(5, &v26);
      if ( v14 >= 0 )
      {
        if ( CompareStringOrdinal(lpString1, -1, *(LPCWCH *)(v26 + 8), -1, 1) != 2 )
        {
          v17 = v26;
          if ( v26 )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v23);
            DsrFreeCxhScenarioInfo(v17);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v23);
          }
          v26 = 0;
          v14 = DsrGetCxhScenarioInfo(8, &v26);
          if ( v14 < 0 )
          {
            v15 = 243;
            goto LABEL_23;
          }
          if ( CompareStringOrdinal(lpString1, -1, *(LPCWCH *)(v26 + 8), -1, 1) != 2 )
            goto LABEL_35;
        }
LABEL_15:
        ScenarioData = 0;
        *a1 = (struct _CXH_SCENARIO_INFO *)v26;
        v26 = 0;
LABEL_16:
        wil::details::unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>(&v26);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
        return ScenarioData;
      }
      v15 = 236;
    }
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
      (const char *)(unsigned int)v14,
      bIgnoreCasea);
    ScenarioData = v14;
    goto LABEL_16;
  }
  if ( lpString1 )
    CflFreeBuffer(lpString1);
  return ScenarioData;
}

```

## disassembly

```asm
0x140087624  push    rbp
0x140087626  push    rbx
0x140087627  push    rsi
0x140087628  push    r12
0x14008762a  push    r14
0x14008762c  push    r15
0x14008762e  mov     rbp, rsp
0x140087631  sub     rsp, 48h
0x140087635  xor     r15d, r15d
0x140087638  mov     rsi, rdx
0x14008763b  mov     [rcx], r15
0x14008763e  mov     r14, rcx
0x140087641  mov     [rdx], r15b
0x140087644  call    IsCflGetScenarioDataPresent
0x140087649  test    al, al
0x14008764b  jnz     short loc_14008766F
0x14008764d  mov     rcx, [rbp+30h]; this
0x140087651  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x140087658  mov     ebx, 80090011h
0x14008765d  mov     edx, 0C2h; void *
0x140087662  mov     r9d, ebx; char *
0x140087665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008766a  jmp     loc_1400877A2
0x14008766f  xor     r8d, r8d
0x140087672  mov     [rbp+lpString1], r15
0x140087676  xor     edx, edx
0x140087678  lea     rcx, [rbp+lpString1]
0x14008767c  call    cs:__imp_CflGetScenarioData
0x140087682  mov     ebx, eax
0x140087684  test    eax, eax
0x140087686  jns     short loc_1400876A0
0x140087688  mov     rcx, [rbp+lpString1]
0x14008768c  test    rcx, rcx
0x14008768f  jz      loc_1400877A2
0x140087695  call    cs:__imp_CflFreeBuffer
0x14008769b  jmp     loc_1400877A2
0x1400876a0  lea     rdx, [rbp+arg_18]
0x1400876a4  mov     [rbp+arg_18], r15
0x1400876a8  mov     ecx, 3
0x1400876ad  call    cs:__imp_DsrGetCxhScenarioInfo
0x1400876b3  mov     ebx, eax
0x1400876b5  test    eax, eax
0x1400876b7  jns     short loc_1400876C6
0x1400876b9  mov     r9d, eax
0x1400876bc  mov     edx, 0CEh
0x1400876c1  jmp     loc_1400878FF
0x1400876c6  mov     r8, [rbp+arg_18]
0x1400876ca  or      r12d, 0FFFFFFFFh
0x1400876ce  mov     rcx, [rbp+lpString1]; lpString1
0x1400876d2  mov     ebx, 1
0x1400876d7  mov     r9d, r12d; cchCount2
0x1400876da  mov     [rsp+48h+bIgnoreCase], ebx; int
0x1400876de  mov     edx, r12d; cchCount1
0x1400876e1  mov     r8, [r8+8]; lpString2
0x1400876e5  call    cs:__imp_CompareStringOrdinal
0x1400876eb  cmp     eax, 2
0x1400876ee  jnz     loc_14008781D
0x1400876f4  lea     r8, [rbp+arg_8]
0x1400876f8  mov     [rbp+arg_10], r15d
0x1400876fc  lea     rdx, [rbp+arg_0]
0x140087700  mov     [rbp+arg_0], r15d
0x140087704  xor     ecx, ecx
0x140087706  mov     [rbp+arg_8], r15d
0x14008770a  mov     [rsi], bl
0x14008770c  call    cs:__imp_DsrCanCurrentUserResetNgcKey
0x140087712  test    eax, eax
0x140087714  jns     loc_1400877B2
0x14008771a  mov     rcx, [rbp+30h]; this
0x14008771e  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x140087725  mov     r9d, eax; char *
0x140087728  mov     edx, 0D9h; void *
0x14008772d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140087732  mov     bl, r15b
0x140087735  call    ?GetPinResetPolicyFailureState@@YA?AW4_NgcPinResetScenarioState@@XZ; GetPinResetPolicyFailureState(void)
0x14008773a  mov     rcx, cs:WNF_NGC_PIN_RESET_SCENARIO_STATE_CHANGE
0x140087741  lea     r8, [rbp+arg_10]
0x140087745  mov     r9d, 4
0x14008774b  mov     [rbp+arg_10], eax
0x14008774e  xor     edx, edx
0x140087750  mov     qword ptr [rsp+48h+bIgnoreCase], r15; int
0x140087755  call    cs:__imp_RtlPublishWnfStateData
0x14008775b  or      eax, 10000000h
0x140087760  jge     short loc_14008777A
0x140087762  mov     rcx, [rbp+30h]; this
0x140087766  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x14008776d  mov     r9d, eax; char *
0x140087770  mov     edx, 0E8h; void *
0x140087775  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14008777a  test    bl, bl
0x14008777c  jz      loc_1400878F2
0x140087782  mov     rax, [rbp+arg_18]
0x140087786  mov     ebx, r15d
0x140087789  mov     [r14], rax
0x14008778c  mov     [rbp+arg_18], r15
0x140087790  lea     rcx, [rbp+arg_18]
0x140087794  call    ??1?$unique_storage@U?$resource_policy@PEAU_CXH_SCENARIO_INFO@@P6AXPEAU1@@Z$1?DsrFreeCxhScenarioInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>(void)
0x140087799  lea     rcx, [rbp+lpString1]
0x14008779d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CflFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400877a2  mov     eax, ebx
0x1400877a4  add     rsp, 48h
0x1400877a8  pop     r15
0x1400877aa  pop     r14
0x1400877ac  pop     r12
0x1400877ae  pop     rsi
0x1400877af  pop     rbx
0x1400877b0  pop     rbp
0x1400877b1  retn
0x1400877b2  cmp     [rbp+arg_0], r15d
0x1400877b6  jz      loc_140087732
0x1400877bc  mov     rsi, [rbp+arg_18]
0x1400877c0  test    rsi, rsi
0x1400877c3  jz      short loc_1400877E0
0x1400877c5  lea     rcx, [rbp+var_10]; this
0x1400877c9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400877ce  mov     rcx, rsi
0x1400877d1  call    cs:__imp_DsrFreeCxhScenarioInfo
0x1400877d7  lea     rcx, [rbp+var_10]; this
0x1400877db  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400877e0  mov     ecx, [rbp+arg_8]
0x1400877e3  lea     rdx, [rbp+arg_18]
0x1400877e7  mov     [rbp+arg_18], r15
0x1400877eb  call    cs:__imp_DsrGetCxhScenarioInfo
0x1400877f1  mov     esi, eax
0x1400877f3  test    eax, eax
0x1400877f5  jns     short loc_140087816
0x1400877f7  mov     edx, 0DDh; void *
0x1400877fc  mov     rcx, [rbp+30h]; this
0x140087800  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x140087807  mov     r9d, esi; char *
0x14008780a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008780f  mov     ebx, esi
0x140087811  jmp     loc_140087790
0x140087816  mov     eax, ebx
0x140087818  jmp     loc_14008773A
0x14008781d  mov     rsi, [rbp+arg_18]
0x140087821  test    rsi, rsi
0x140087824  jz      short loc_140087841
0x140087826  lea     rcx, [rbp+arg_0]; this
0x14008782a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14008782f  mov     rcx, rsi
0x140087832  call    cs:__imp_DsrFreeCxhScenarioInfo
0x140087838  lea     rcx, [rbp+arg_0]; this
0x14008783c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140087841  lea     rdx, [rbp+arg_18]
0x140087845  mov     [rbp+arg_18], r15
0x140087849  mov     ecx, 5
0x14008784e  call    cs:__imp_DsrGetCxhScenarioInfo
0x140087854  mov     esi, eax
0x140087856  test    eax, eax
0x140087858  jns     short loc_140087861
0x14008785a  mov     edx, 0ECh
0x14008785f  jmp     short loc_1400877FC
0x140087861  mov     r8, [rbp+arg_18]
0x140087865  mov     r9d, r12d; cchCount2
0x140087868  mov     rcx, [rbp+lpString1]; lpString1
0x14008786c  mov     edx, r12d; cchCount1
0x14008786f  mov     [rsp+48h+bIgnoreCase], ebx; bIgnoreCase
0x140087873  mov     r8, [r8+8]; lpString2
0x140087877  call    cs:__imp_CompareStringOrdinal
0x14008787d  cmp     eax, 2
0x140087880  jz      loc_140087782
0x140087886  mov     rsi, [rbp+arg_18]
0x14008788a  test    rsi, rsi
0x14008788d  jz      short loc_1400878AA
0x14008788f  lea     rcx, [rbp+arg_0]; this
0x140087893  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140087898  mov     rcx, rsi
0x14008789b  call    cs:__imp_DsrFreeCxhScenarioInfo
0x1400878a1  lea     rcx, [rbp+arg_0]; this
0x1400878a5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400878aa  lea     rdx, [rbp+arg_18]
0x1400878ae  mov     [rbp+arg_18], r15
0x1400878b2  mov     ecx, 8
0x1400878b7  call    cs:__imp_DsrGetCxhScenarioInfo
0x1400878bd  mov     esi, eax
0x1400878bf  test    eax, eax
0x1400878c1  jns     short loc_1400878CD
0x1400878c3  mov     edx, 0F3h
0x1400878c8  jmp     loc_1400877FC
0x1400878cd  mov     r8, [rbp+arg_18]
0x1400878d1  mov     r9d, r12d; cchCount2
0x1400878d4  mov     rcx, [rbp+lpString1]; lpString1
0x1400878d8  mov     edx, r12d; cchCount1
0x1400878db  mov     [rsp+48h+bIgnoreCase], ebx; int
0x1400878df  mov     r8, [r8+8]; lpString2
0x1400878e3  call    cs:__imp_CompareStringOrdinal
0x1400878e9  cmp     eax, 2
0x1400878ec  jz      loc_140087782
0x1400878f2  mov     ebx, 80090011h
0x1400878f7  mov     edx, 0FBh; void *
0x1400878fc  mov     r9d, ebx; char *
0x1400878ff  mov     rcx, [rbp+30h]; this
0x140087903  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x14008790a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008790f  jmp     loc_140087790
```
