# GetGenericCloudExperienceHostInfo(_CXH_SCENARIO_INFO * *,bool *)

- ea: `0x14008d55c`
- end: `0x14008d8a1`
- name: `?GetGenericCloudExperienceHostInfo@@YAJPEAPEAU_CXH_SCENARIO_INFO@@PEA_N@Z`
- size: `837`
- prototype: `__int64 __fastcall(struct _CXH_SCENARIO_INFO **, bool *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400a08d0`
- `0x1401ab4e0`

## callees

- `0x14001b2c8`
- `0x140086b94`
- `0x140087550`
- `0x140087664`
- `0x14008d55c`
- `0x14009ac68`
- `0x1400a2294`
- `0x140111588`
- `0x1401cd3d8`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x14008d6ab`
- `ntdll!RtlPublishWnfStateData` at `0x14008d6ab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14008d62f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14008d7ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14008d86a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14008d62f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14008d7ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14008d86a`
- `dsreg!DsrGetCxhScenarioInfo` at `0x14008d5f1`
- `dsreg!DsrGetCxhScenarioInfo` at `0x14008d74e`
- `dsreg!DsrGetCxhScenarioInfo` at `0x14008d7bd`
- `dsreg!DsrGetCxhScenarioInfo` at `0x14008d838`
- `dsreg!DsrGetCxhScenarioInfo` at `0x14008d5f1`
- `dsreg!DsrGetCxhScenarioInfo` at `0x14008d74e`
- `dsreg!DsrGetCxhScenarioInfo` at `0x14008d7bd`
- `dsreg!DsrGetCxhScenarioInfo` at `0x14008d838`
- `dsreg!DsrCanCurrentUserResetNgcKey` at `0x14008d65c`
- `dsreg!DsrCanCurrentUserResetNgcKey` at `0x14008d65c`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x14008d72e`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x14008d79b`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x14008d816`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x14008d72e`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x14008d79b`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x14008d816`
- `ext-ms-win-security-cfl-l1-1-0!CflGetScenarioData` at `0x14008d5b4`
- `ext-ms-win-security-cfl-l1-1-0!CflGetScenarioData` at `0x14008d5b4`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x14008d5d3`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x14008d5d3`

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
0x14008d55c  push    rbp
0x14008d55e  push    rbx
0x14008d55f  push    rsi
0x14008d560  push    r12
0x14008d562  push    r14
0x14008d564  push    r15
0x14008d566  mov     rbp, rsp
0x14008d569  sub     rsp, 48h
0x14008d56d  xor     r15d, r15d
0x14008d570  mov     rsi, rdx
0x14008d573  mov     [rcx], r15
0x14008d576  mov     r14, rcx
0x14008d579  mov     [rdx], r15b
0x14008d57c  call    IsCflGetScenarioDataPresent
0x14008d581  test    al, al
0x14008d583  jnz     short loc_14008D5A7
0x14008d585  mov     rcx, [rbp+30h]; this
0x14008d589  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x14008d590  mov     ebx, 80090011h
0x14008d595  mov     edx, 0C2h; void *
0x14008d59a  mov     r9d, ebx; char *
0x14008d59d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008d5a2  jmp     loc_14008D6FE
0x14008d5a7  xor     r8d, r8d
0x14008d5aa  mov     [rbp+lpString1], r15
0x14008d5ae  xor     edx, edx
0x14008d5b0  lea     rcx, [rbp+lpString1]
0x14008d5b4  call    cs:__imp_CflGetScenarioData
0x14008d5bb  nop     dword ptr [rax+rax+00h]
0x14008d5c0  mov     ebx, eax
0x14008d5c2  test    eax, eax
0x14008d5c4  jns     short loc_14008D5E4
0x14008d5c6  mov     rcx, [rbp+lpString1]
0x14008d5ca  test    rcx, rcx
0x14008d5cd  jz      loc_14008D6FE
0x14008d5d3  call    cs:__imp_CflFreeBuffer
0x14008d5da  nop     dword ptr [rax+rax+00h]
0x14008d5df  jmp     loc_14008D6FE
0x14008d5e4  lea     rdx, [rbp+arg_18]
0x14008d5e8  mov     [rbp+arg_18], r15
0x14008d5ec  mov     ecx, 3
0x14008d5f1  call    cs:__imp_DsrGetCxhScenarioInfo
0x14008d5f8  nop     dword ptr [rax+rax+00h]
0x14008d5fd  mov     ebx, eax
0x14008d5ff  test    eax, eax
0x14008d601  jns     short loc_14008D610
0x14008d603  mov     r9d, eax
0x14008d606  mov     edx, 0CEh
0x14008d60b  jmp     loc_14008D88C
0x14008d610  mov     r8, [rbp+arg_18]
0x14008d614  or      r12d, 0FFFFFFFFh
0x14008d618  mov     rcx, [rbp+lpString1]; lpString1
0x14008d61c  mov     ebx, 1
0x14008d621  mov     r9d, r12d; cchCount2
0x14008d624  mov     [rsp+48h+bIgnoreCase], ebx; int
0x14008d628  mov     edx, r12d; cchCount1
0x14008d62b  mov     r8, [r8+8]; lpString2
0x14008d62f  call    cs:__imp_CompareStringOrdinal
0x14008d636  nop     dword ptr [rax+rax+00h]
0x14008d63b  cmp     eax, 2
0x14008d63e  jnz     loc_14008D786
0x14008d644  lea     r8, [rbp+arg_8]
0x14008d648  mov     [rbp+arg_10], r15d
0x14008d64c  lea     rdx, [rbp+arg_0]
0x14008d650  mov     [rbp+arg_0], r15d
0x14008d654  xor     ecx, ecx
0x14008d656  mov     [rbp+arg_8], r15d
0x14008d65a  mov     [rsi], bl
0x14008d65c  call    cs:__imp_DsrCanCurrentUserResetNgcKey
0x14008d663  nop     dword ptr [rax+rax+00h]
0x14008d668  test    eax, eax
0x14008d66a  jns     loc_14008D70F
0x14008d670  mov     rcx, [rbp+30h]; this
0x14008d674  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x14008d67b  mov     r9d, eax; char *
0x14008d67e  mov     edx, 0D9h; void *
0x14008d683  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14008d688  mov     bl, r15b
0x14008d68b  call    ?GetPinResetPolicyFailureState@@YA?AW4_NgcPinResetScenarioState@@XZ; GetPinResetPolicyFailureState(void)
0x14008d690  mov     rcx, cs:WNF_NGC_PIN_RESET_SCENARIO_STATE_CHANGE
0x14008d697  lea     r8, [rbp+arg_10]
0x14008d69b  mov     r9d, 4
0x14008d6a1  mov     [rbp+arg_10], eax
0x14008d6a4  xor     edx, edx
0x14008d6a6  mov     qword ptr [rsp+48h+bIgnoreCase], r15; int
0x14008d6ab  call    cs:__imp_RtlPublishWnfStateData
0x14008d6b2  nop     dword ptr [rax+rax+00h]
0x14008d6b7  or      eax, 10000000h
0x14008d6bc  jge     short loc_14008D6D6
0x14008d6be  mov     rcx, [rbp+30h]; this
0x14008d6c2  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x14008d6c9  mov     r9d, eax; char *
0x14008d6cc  mov     edx, 0E8h; void *
0x14008d6d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14008d6d6  test    bl, bl
0x14008d6d8  jz      loc_14008D87F
0x14008d6de  mov     rax, [rbp+arg_18]
0x14008d6e2  mov     ebx, r15d
0x14008d6e5  mov     [r14], rax
0x14008d6e8  mov     [rbp+arg_18], r15
0x14008d6ec  lea     rcx, [rbp+arg_18]
0x14008d6f0  call    ??1?$unique_storage@U?$resource_policy@PEAU_CXH_SCENARIO_INFO@@P6AXPEAU1@@Z$1?DsrFreeCxhScenarioInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>(void)
0x14008d6f5  lea     rcx, [rbp+lpString1]
0x14008d6f9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CflFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14008d6fe  mov     eax, ebx
0x14008d700  add     rsp, 48h
0x14008d704  pop     r15
0x14008d706  pop     r14
0x14008d708  pop     r12
0x14008d70a  pop     rsi
0x14008d70b  pop     rbx
0x14008d70c  pop     rbp
0x14008d70d  retn
0x14008d70f  cmp     [rbp+arg_0], r15d
0x14008d713  jz      loc_14008D688
0x14008d719  mov     rsi, [rbp+arg_18]
0x14008d71d  test    rsi, rsi
0x14008d720  jz      short loc_14008D743
0x14008d722  lea     rcx, [rbp+var_10]; this
0x14008d726  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14008d72b  mov     rcx, rsi
0x14008d72e  call    cs:__imp_DsrFreeCxhScenarioInfo
0x14008d735  nop     dword ptr [rax+rax+00h]
0x14008d73a  lea     rcx, [rbp+var_10]; this
0x14008d73e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14008d743  mov     ecx, [rbp+arg_8]
0x14008d746  lea     rdx, [rbp+arg_18]
0x14008d74a  mov     [rbp+arg_18], r15
0x14008d74e  call    cs:__imp_DsrGetCxhScenarioInfo
0x14008d755  nop     dword ptr [rax+rax+00h]
0x14008d75a  mov     esi, eax
0x14008d75c  test    eax, eax
0x14008d75e  jns     short loc_14008D77F
0x14008d760  mov     edx, 0DDh; void *
0x14008d765  mov     rcx, [rbp+30h]; this
0x14008d769  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x14008d770  mov     r9d, esi; char *
0x14008d773  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008d778  mov     ebx, esi
0x14008d77a  jmp     loc_14008D6EC
0x14008d77f  mov     eax, ebx
0x14008d781  jmp     loc_14008D690
0x14008d786  mov     rsi, [rbp+arg_18]
0x14008d78a  test    rsi, rsi
0x14008d78d  jz      short loc_14008D7B0
0x14008d78f  lea     rcx, [rbp+arg_0]; this
0x14008d793  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14008d798  mov     rcx, rsi
0x14008d79b  call    cs:__imp_DsrFreeCxhScenarioInfo
0x14008d7a2  nop     dword ptr [rax+rax+00h]
0x14008d7a7  lea     rcx, [rbp+arg_0]; this
0x14008d7ab  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14008d7b0  lea     rdx, [rbp+arg_18]
0x14008d7b4  mov     [rbp+arg_18], r15
0x14008d7b8  mov     ecx, 5
0x14008d7bd  call    cs:__imp_DsrGetCxhScenarioInfo
0x14008d7c4  nop     dword ptr [rax+rax+00h]
0x14008d7c9  mov     esi, eax
0x14008d7cb  test    eax, eax
0x14008d7cd  jns     short loc_14008D7D6
0x14008d7cf  mov     edx, 0ECh
0x14008d7d4  jmp     short loc_14008D765
0x14008d7d6  mov     r8, [rbp+arg_18]
0x14008d7da  mov     r9d, r12d; cchCount2
0x14008d7dd  mov     rcx, [rbp+lpString1]; lpString1
0x14008d7e1  mov     edx, r12d; cchCount1
0x14008d7e4  mov     [rsp+48h+bIgnoreCase], ebx; bIgnoreCase
0x14008d7e8  mov     r8, [r8+8]; lpString2
0x14008d7ec  call    cs:__imp_CompareStringOrdinal
0x14008d7f3  nop     dword ptr [rax+rax+00h]
0x14008d7f8  cmp     eax, 2
0x14008d7fb  jz      loc_14008D6DE
0x14008d801  mov     rsi, [rbp+arg_18]
0x14008d805  test    rsi, rsi
0x14008d808  jz      short loc_14008D82B
0x14008d80a  lea     rcx, [rbp+arg_0]; this
0x14008d80e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14008d813  mov     rcx, rsi
0x14008d816  call    cs:__imp_DsrFreeCxhScenarioInfo
0x14008d81d  nop     dword ptr [rax+rax+00h]
0x14008d822  lea     rcx, [rbp+arg_0]; this
0x14008d826  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14008d82b  lea     rdx, [rbp+arg_18]
0x14008d82f  mov     [rbp+arg_18], r15
0x14008d833  mov     ecx, 8
0x14008d838  call    cs:__imp_DsrGetCxhScenarioInfo
0x14008d83f  nop     dword ptr [rax+rax+00h]
0x14008d844  mov     esi, eax
0x14008d846  test    eax, eax
0x14008d848  jns     short loc_14008D854
0x14008d84a  mov     edx, 0F3h
0x14008d84f  jmp     loc_14008D765
0x14008d854  mov     r8, [rbp+arg_18]
0x14008d858  mov     r9d, r12d; cchCount2
0x14008d85b  mov     rcx, [rbp+lpString1]; lpString1
0x14008d85f  mov     edx, r12d; cchCount1
0x14008d862  mov     [rsp+48h+bIgnoreCase], ebx; int
0x14008d866  mov     r8, [r8+8]; lpString2
0x14008d86a  call    cs:__imp_CompareStringOrdinal
0x14008d871  nop     dword ptr [rax+rax+00h]
0x14008d876  cmp     eax, 2
0x14008d879  jz      loc_14008D6DE
0x14008d87f  mov     ebx, 80090011h
0x14008d884  mov     edx, 0FBh; void *
0x14008d889  mov     r9d, ebx; char *
0x14008d88c  mov     rcx, [rbp+30h]; this
0x14008d890  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x14008d897  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008d89c  jmp     loc_14008D6EC
```
