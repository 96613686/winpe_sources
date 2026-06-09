# ChangeKeyPregenTaskTriggersStatus(bool)

- ea: `0x18001d764`
- end: `0x18001d9de`
- name: `?ChangeKeyPregenTaskTriggersStatus@@YAJ_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019964`
- `0x18001b950`

## callees

- `0x18000b0fc`
- `0x18001d6c8`
- `0x18001d708`
- `0x18001d730`
- `0x18001d764`
- `0x18001d9e4`
- `0x18001dd14`
- `0x180028010`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x18001d77e`
- `ntdll!RtlIsMultiSessionSku` at `0x18001d77e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001d7b6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001d7b6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d7f6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d7f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d88a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d9b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d88a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d9b9`

## string_xrefs

- `0x18001d7ef`: `KeyPreGenTask`
- `0x18001d7c9`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`
- `0x18001d81d`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`
- `0x18001d861`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`
- `0x18001d978`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ChangeKeyPregenTaskTriggersStatus(unsigned __int8 a1)
{
  const unsigned __int16 * near **v2; // r14
  enum _TASK_TRIGGER_TYPE2 near **v3; // r15
  unsigned int v4; // esi
  HRESULT v5; // eax
  unsigned int v6; // ebx
  unsigned __int16 *v8; // rax
  OLECHAR *v9; // rbx
  unsigned int v10; // edi
  OLECHAR *v11; // rcx
  int v12; // eax
  __int64 v13; // rdi
  int v14; // eax
  int v15; // [rsp+20h] [rbp-89h]
  struct ITaskFolder *v16; // [rsp+50h] [rbp-59h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-51h] BYREF
  __int64 v18; // [rsp+60h] [rbp-49h] BYREF
  __int64 v19; // [rsp+68h] [rbp-41h] BYREF
  __int128 v20; // [rsp+70h] [rbp-39h]
  __int64 v21; // [rsp+80h] [rbp-29h]
  __int128 v22; // [rsp+90h] [rbp-19h]
  __int64 v23; // [rsp+A0h] [rbp-9h]
  int v24[4]; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v25; // [rsp+C0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  char v27; // [rsp+118h] [rbp+6Fh] BYREF
  __int16 v28; // [rsp+119h] [rbp+70h]
  struct ITaskDefinition *v29; // [rsp+128h] [rbp+7Fh] BYREF

  if ( (unsigned __int8)RtlIsMultiSessionSku() )
  {
    v2 = &c_keyPregenMultiSessionTriggerIds;
    v3 = &c_keyPregenMultiSessionTriggerTypes;
    v4 = 3;
  }
  else
  {
    v2 = &c_keyPregenSingleSessionTriggerIds;
    v3 = &c_keyPregenSingleSessionTriggerTypes;
    v4 = 1;
  }
  v5 = CoInitializeEx(0, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
      (const char *)(unsigned int)v5,
      v15);
    return v6;
  }
  v28 = 256;
  bstrString = 0;
  v8 = SysAllocString(L"KeyPreGenTask");
  ATL::CComBSTR::Attach((ATL::CComBSTR *)&bstrString, v8);
  v9 = bstrString;
  if ( bstrString )
  {
    v29 = 0;
    v16 = 0;
    v12 = OpenKeyPregenTask((const struct ATL::CComBSTR *)&bstrString, &v29, &v16);
    v10 = v12;
    if ( v12 >= 0 )
    {
      v13 = 0;
      do
      {
        v18 = 0;
        if ( (int)GetKeyPregenTaskTrigger(v2[v13], *((unsigned int *)v3 + v13), &v29, &v18) >= 0 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 152LL))(v18, (unsigned __int16)((a1 ^ 1) - 1));
        wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v18);
        v13 = (unsigned int)(v13 + 1);
      }
      while ( (unsigned int)v13 < v4 );
      v20 = 0;
      LOWORD(v20) = 1;
      v19 = 0;
      v21 = 0;
      v22 = 0;
      v23 = 0;
      *(_OWORD *)v24 = 0;
      v25 = 0;
      v9 = bstrString;
      v14 = ((__int64 (__fastcall *)(struct ITaskFolder *, BSTR, struct ITaskDefinition *, __int64))v16->lpVtbl->RegisterTaskDefinition)(
              v16,
              bstrString,
              v29,
              20);
      v10 = v14;
      if ( v14 >= 0 )
      {
        wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v19);
        wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v16);
        wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v29);
        SysFreeString(v9);
        v10 = 0;
        goto LABEL_19;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
        (const char *)(unsigned int)v14,
        (int)v24);
      wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v19);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
        (const char *)(unsigned int)v12,
        v15);
    }
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v16);
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v29);
    v11 = v9;
  }
  else
  {
    v10 = -2146893810;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
      (const char *)0x8009000ELL,
      v15);
    v11 = 0;
  }
  SysFreeString(v11);
LABEL_19:
  wil::details::ScopeExitFnGuard__lambda_7d255d14f0f6400737337ecef14864db___::operator()(&v27);
  return v10;
}

```

## disassembly

```asm
0x18001d764  push    rbp
0x18001d766  push    rbx
0x18001d767  push    rsi
0x18001d768  push    rdi
0x18001d769  push    r12
0x18001d76b  push    r14
0x18001d76d  push    r15
0x18001d76f  lea     rbp, [rsp-27h]
0x18001d774  sub     rsp, 0D0h
0x18001d77b  mov     r12b, cl
0x18001d77e  call    cs:__imp_RtlIsMultiSessionSku
0x18001d784  mov     edi, 1
0x18001d789  test    al, al
0x18001d78b  jnz     short loc_18001D79F
0x18001d78d  lea     r14, ?c_keyPregenSingleSessionTriggerIds@@3PAPEBGA; ushort const * near * c_keyPregenSingleSessionTriggerIds
0x18001d794  lea     r15, ?c_keyPregenSingleSessionTriggerTypes@@3PAW4_TASK_TRIGGER_TYPE2@@A; _TASK_TRIGGER_TYPE2 near * c_keyPregenSingleSessionTriggerTypes
0x18001d79b  mov     esi, edi
0x18001d79d  jmp     short loc_18001D7B2
0x18001d79f  lea     r14, ?c_keyPregenMultiSessionTriggerIds@@3PAPEBGA; ushort const * near * c_keyPregenMultiSessionTriggerIds
0x18001d7a6  lea     r15, ?c_keyPregenMultiSessionTriggerTypes@@3PAW4_TASK_TRIGGER_TYPE2@@A; _TASK_TRIGGER_TYPE2 near * c_keyPregenMultiSessionTriggerTypes
0x18001d7ad  mov     esi, 3
0x18001d7b2  xor     edx, edx; dwCoInit
0x18001d7b4  xor     ecx, ecx; pvReserved
0x18001d7b6  call    cs:__imp_CoInitializeEx
0x18001d7bc  mov     ebx, eax
0x18001d7be  test    eax, eax
0x18001d7c0  jns     short loc_18001D7E1
0x18001d7c2  mov     rcx, [rbp+5Fh]; this
0x18001d7c6  mov     r9d, eax; char *
0x18001d7c9  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001d7d0  mov     edx, 0DDh; void *
0x18001d7d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d7da  mov     eax, ebx
0x18001d7dc  jmp     loc_18001D9CC
0x18001d7e1  mov     [rbp+57h+arg_9], 100h
0x18001d7e7  mov     [rbp+57h+bstrString], 0
0x18001d7ef  lea     rcx, psz; "KeyPreGenTask"
0x18001d7f6  call    cs:__imp_SysAllocString
0x18001d7fc  mov     rdx, rax; unsigned __int16 *
0x18001d7ff  lea     rcx, [rbp+57h+bstrString]; this
0x18001d803  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x18001d808  mov     rbx, [rbp+57h+bstrString]
0x18001d80c  test    rbx, rbx
0x18001d80f  jnz     short loc_18001D833
0x18001d811  mov     rcx, [rbp+5Fh]; this
0x18001d815  mov     edi, 8009000Eh
0x18001d81a  mov     r9d, edi; char *
0x18001d81d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001d824  mov     edx, 0E8h; void *
0x18001d829  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d82e  nop
0x18001d82f  xor     ecx, ecx
0x18001d831  jmp     short loc_18001D88A
0x18001d833  mov     [rbp+57h+arg_18], 0
0x18001d83b  mov     [rbp+57h+var_B0], 0
0x18001d843  lea     r8, [rbp+57h+var_B0]; struct ITaskFolder **
0x18001d847  lea     rdx, [rbp+57h+arg_18]; struct ITaskDefinition **
0x18001d84b  lea     rcx, [rbp+57h+bstrString]; struct ATL::CComBSTR *
0x18001d84f  call    ?OpenKeyPregenTask@@YAJAEBVCComBSTR@ATL@@PEAPEAUITaskDefinition@@PEAPEAUITaskFolder@@@Z; OpenKeyPregenTask(ATL::CComBSTR const &,ITaskDefinition * *,ITaskFolder * *)
0x18001d854  mov     edi, eax
0x18001d856  test    eax, eax
0x18001d858  jns     short loc_18001D895
0x18001d85a  mov     rcx, [rbp+5Fh]; this
0x18001d85e  mov     r9d, eax; char *
0x18001d861  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001d868  mov     edx, 0EFh; void *
0x18001d86d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d872  nop
0x18001d873  lea     rcx, [rbp+57h+var_B0]
0x18001d877  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001d87c  nop
0x18001d87d  lea     rcx, [rbp+57h+arg_18]
0x18001d881  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001d886  nop
0x18001d887  mov     rcx, rbx; bstrString
0x18001d88a  call    cs:__imp_SysFreeString
0x18001d890  jmp     loc_18001D9C1
0x18001d895  xor     edi, edi
0x18001d897  lea     ebx, [rdi+1]
0x18001d89a  mov     [rbp+57h+var_A0], 0
0x18001d8a2  lea     r9, [rbp+57h+var_A0]
0x18001d8a6  lea     r8, [rbp+57h+arg_18]
0x18001d8aa  mov     edx, [r15+rdi*4]
0x18001d8ae  mov     rcx, [r14+rdi*8]
0x18001d8b2  call    ?GetKeyPregenTaskTrigger@@YAJPEBGW4_TASK_TRIGGER_TYPE2@@AEBV?$CComPtr@UITaskDefinition@@@ATL@@PEAPEAUITrigger@@@Z; GetKeyPregenTaskTrigger(ushort const *,_TASK_TRIGGER_TYPE2,ATL::CComPtr<ITaskDefinition> const &,ITrigger * *)
0x18001d8b7  test    eax, eax
0x18001d8b9  js      short loc_18001D8DA
0x18001d8bb  mov     rcx, [rbp+57h+var_A0]
0x18001d8bf  mov     r8, [rcx]
0x18001d8c2  mov     al, r12b
0x18001d8c5  xor     al, bl
0x18001d8c7  movzx   edx, al
0x18001d8ca  sub     dx, bx
0x18001d8cd  mov     rax, [r8+98h]
0x18001d8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8d9  nop
0x18001d8da  lea     rcx, [rbp+57h+var_A0]
0x18001d8de  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001d8e3  add     edi, ebx
0x18001d8e5  cmp     edi, esi
0x18001d8e7  jb      short loc_18001D89A
0x18001d8e9  xorps   xmm2, xmm2
0x18001d8ec  xor     edx, edx
0x18001d8ee  xorps   xmm0, xmm0
0x18001d8f1  xor     eax, eax
0x18001d8f3  movups  [rbp+57h+var_90], xmm0
0x18001d8f7  mov     word ptr [rbp+57h+var_90], bx
0x18001d8fb  mov     [rbp+57h+var_98], rax
0x18001d8ff  mov     rcx, [rbp+57h+var_B0]
0x18001d903  movups  xmm0, [rbp+57h+var_90]
0x18001d907  movaps  [rbp+57h+var_90], xmm0
0x18001d90b  mov     [rbp+57h+var_80], rax
0x18001d90f  movaps  [rbp+57h+var_70], xmm2
0x18001d913  mov     [rbp+57h+var_60], rdx
0x18001d917  movaps  xmmword ptr [rbp+57h+var_50], xmm2
0x18001d91b  mov     [rbp+57h+var_40], rdx
0x18001d91f  mov     rax, [rcx]
0x18001d922  lea     rdx, [rbp+57h+var_98]
0x18001d926  mov     [rsp+100h+var_C0], rdx
0x18001d92b  lea     rdx, [rbp+57h+var_90]
0x18001d92f  mov     [rsp+100h+var_C8], rdx
0x18001d934  mov     [rsp+100h+var_D0], 5
0x18001d93c  lea     rdx, [rbp+57h+var_70]
0x18001d940  mov     [rsp+100h+var_D8], rdx
0x18001d945  lea     rdx, [rbp+57h+var_50]
0x18001d949  mov     qword ptr [rsp+100h+var_E0], rdx; int
0x18001d94e  mov     r9d, 14h
0x18001d954  mov     r8, [rbp+57h+arg_18]
0x18001d958  mov     rbx, [rbp+57h+bstrString]
0x18001d95c  mov     rdx, rbx
0x18001d95f  mov     rax, [rax+88h]
0x18001d966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d96b  mov     edi, eax
0x18001d96d  test    eax, eax
0x18001d96f  jns     short loc_18001D998
0x18001d971  mov     rcx, [rbp+5Fh]; this
0x18001d975  mov     r9d, eax; char *
0x18001d978  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001d97f  mov     edx, 118h; void *
0x18001d984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d989  nop
0x18001d98a  lea     rcx, [rbp+57h+var_98]
0x18001d98e  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001d993  jmp     loc_18001D873
0x18001d998  lea     rcx, [rbp+57h+var_98]
0x18001d99c  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001d9a1  nop
0x18001d9a2  lea     rcx, [rbp+57h+var_B0]
0x18001d9a6  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001d9ab  nop
0x18001d9ac  lea     rcx, [rbp+57h+arg_18]
0x18001d9b0  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001d9b5  nop
0x18001d9b6  mov     rcx, rbx; bstrString
0x18001d9b9  call    cs:__imp_SysFreeString
0x18001d9bf  xor     edi, edi
0x18001d9c1  lea     rcx, [rbp+57h+arg_8]
0x18001d9c5  call    wil__details__ScopeExitFnGuard__lambda_7d255d14f0f6400737337ecef14864db_____operator__
0x18001d9ca  mov     eax, edi
0x18001d9cc  add     rsp, 0D0h
0x18001d9d3  pop     r15
0x18001d9d5  pop     r14
0x18001d9d7  pop     r12
0x18001d9d9  pop     rdi
0x18001d9da  pop     rsi
0x18001d9db  pop     rbx
0x18001d9dc  pop     rbp
0x18001d9dd  retn
```
