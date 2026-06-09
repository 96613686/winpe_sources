# SetAikLogonTrigger(void)

- ea: `0x1800161f4`
- end: `0x18001642e`
- name: `?SetAikLogonTrigger@@YAJXZ`
- size: `570`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001417c`

## callees

- `0x180008ab0`
- `0x18000cc34`
- `0x180011814`
- `0x180015338`
- `0x180015370`
- `0x180015720`
- `0x180015abc`
- `0x1800161f4`
- `0x180016490`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016203`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016203`
- `OLEAUT32!__imp_SysAllocString` at `0x180016315`
- `OLEAUT32!__imp_SysAllocString` at `0x180016315`
- `OLEAUT32!__imp_SysFreeString` at `0x180016350`
- `OLEAUT32!__imp_SysFreeString` at `0x18001639e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800163de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800163f4`
- `OLEAUT32!__imp_SysFreeString` at `0x180016350`
- `OLEAUT32!__imp_SysFreeString` at `0x18001639e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800163de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800163f4`

## string_xrefs

- `0x180016216`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x18001629f`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x1800162e5`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x18001633c`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180016389`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x1800163c9`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 SetAikLogonTrigger(void)
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  int Trigger; // eax
  int v3; // eax
  unsigned __int16 *v4; // rax
  OLECHAR *v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  int updated; // eax
  int v10; // [rsp+20h] [rbp-50h] BYREF
  __int64 v11; // [rsp+28h] [rbp-48h] BYREF
  struct ITrigger *v12; // [rsp+30h] [rbp-40h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-38h] BYREF
  BSTR v14[4]; // [rsp+40h] [rbp-30h] BYREF
  int v15; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v0 = CoInitializeEx(0, 0);
  v1 = v0;
  if ( v0 >= 0 )
  {
    wil::ScopeExitIgnore__lambda_c8ea37a3166e7b4a2f87be30e1bb2a2b___(&v10);
    memset(v14, 0, sizeof(v14));
    v15 = 0;
    v12 = 0;
    Trigger = AikEnrollTask::GetTrigger(v14, 9u, 1, &v12);
    v1 = Trigger;
    if ( Trigger >= 0 )
    {
      v11 = 0;
      v3 = ((__int64 (__fastcall *)(struct ITrigger *, GUID *, __int64 *))v12->lpVtbl->QueryInterface)(
             v12,
             &IID_ILogonTrigger,
             &v11);
      v1 = v3;
      if ( v3 >= 0 )
      {
        bstrString = 0;
        v4 = SysAllocString(L"PT60S");
        ATL::CComBSTR::Attach(&bstrString, v4);
        v5 = bstrString;
        if ( bstrString )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v11 + 168LL))(v11, bstrString);
          v7 = v6;
          if ( v6 >= 0 )
          {
            updated = AikEnrollTask::UpdateTask((AikEnrollTask *)v14);
            v7 = updated;
            if ( updated >= 0 )
            {
              SysFreeString(v5);
              ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v11);
              v1 = 0;
              goto LABEL_15;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DD,
              (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
              (const char *)(unsigned int)updated,
              v10);
            SysFreeString(v5);
            ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v11);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DA,
              (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
              (const char *)(unsigned int)v6,
              v10);
            SysFreeString(v5);
            ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v11);
          }
          v1 = v7;
        }
        else
        {
          v1 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D7,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
            (const char *)0x8007000ELL,
            v10);
          SysFreeString(0);
          ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v11);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D2,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
          (const char *)(unsigned int)v3,
          v10);
        ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v11);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)(unsigned int)Trigger,
        v10);
    }
LABEL_15:
    ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v12);
    AikEnrollTask::~AikEnrollTask((AikEnrollTask *)v14);
    wil::details::ScopeExitFnGuard__lambda_c8ea37a3166e7b4a2f87be30e1bb2a2b___::operator()(&v10);
    return v1;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1C0,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
    (const char *)(unsigned int)v0,
    v10);
  return v1;
}

```

## disassembly

```asm
0x1800161f4  push    rbp
0x1800161f6  push    rbx
0x1800161f7  push    rdi
0x1800161f8  mov     rbp, rsp
0x1800161fb  sub     rsp, 70h
0x1800161ff  xor     edx, edx; dwCoInit
0x180016201  xor     ecx, ecx; pvReserved
0x180016203  call    cs:__imp_CoInitializeEx
0x180016209  mov     ebx, eax
0x18001620b  test    eax, eax
0x18001620d  jns     short loc_18001622C
0x18001620f  mov     rcx, [rbp+18h]; this
0x180016213  mov     r9d, eax; char *
0x180016216  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001621d  mov     edx, 1C0h; void *
0x180016222  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016227  jmp     loc_180016424
0x18001622c  lea     rcx, [rbp+var_50]
0x180016230  call    wil__ScopeExitIgnore__lambda_c8ea37a3166e7b4a2f87be30e1bb2a2b___
0x180016235  nop
0x180016236  mov     [rbp+var_30], 0
0x18001623e  lea     rax, [rbp+var_28]
0x180016242  mov     [rbp+arg_0], rax
0x180016246  mov     [rbp+var_28], 0
0x18001624e  lea     rax, [rbp+var_20]
0x180016252  mov     [rbp+arg_8], rax
0x180016256  mov     [rbp+var_20], 0
0x18001625e  lea     rax, [rbp+var_18]
0x180016262  mov     [rbp+arg_10], rax
0x180016266  mov     [rbp+var_18], 0
0x18001626e  mov     [rbp+var_10], 0
0x180016275  mov     [rbp+var_40], 0
0x18001627d  lea     r9, [rbp+var_40]; struct ITrigger **
0x180016281  mov     r8b, 1; bool
0x180016284  mov     edx, 9; enum _TASK_TRIGGER_TYPE2
0x180016289  lea     rcx, [rbp+var_30]; this
0x18001628d  call    ?GetTrigger@AikEnrollTask@@QEAAJW4_TASK_TRIGGER_TYPE2@@_NPEAPEAUITrigger@@@Z; AikEnrollTask::GetTrigger(_TASK_TRIGGER_TYPE2,bool,ITrigger * *)
0x180016292  mov     ebx, eax
0x180016294  test    eax, eax
0x180016296  jns     short loc_1800162B6
0x180016298  mov     rcx, [rbp+18h]; this
0x18001629c  mov     r9d, eax; char *
0x18001629f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800162a6  mov     edx, 1CDh; void *
0x1800162ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800162b0  nop
0x1800162b1  jmp     loc_180016407
0x1800162b6  mov     [rbp+var_48], 0
0x1800162be  mov     rcx, [rbp+var_40]
0x1800162c2  mov     rax, [rcx]
0x1800162c5  lea     r8, [rbp+var_48]
0x1800162c9  lea     rdx, IID_ILogonTrigger
0x1800162d0  mov     rax, [rax]
0x1800162d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162d8  mov     ebx, eax
0x1800162da  test    eax, eax
0x1800162dc  jns     short loc_180016306
0x1800162de  mov     rcx, [rbp+18h]; this
0x1800162e2  mov     r9d, eax; char *
0x1800162e5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800162ec  mov     edx, 1D2h; void *
0x1800162f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800162f6  nop
0x1800162f7  lea     rcx, [rbp+var_48]
0x1800162fb  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180016300  nop
0x180016301  jmp     loc_180016407
0x180016306  mov     [rbp+bstrString], 0
0x18001630e  lea     rcx, aPt60s; "PT60S"
0x180016315  call    cs:__imp_SysAllocString
0x18001631b  mov     rdx, rax; unsigned __int16 *
0x18001631e  lea     rcx, [rbp+bstrString]; this
0x180016322  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x180016327  mov     rbx, [rbp+bstrString]
0x18001632b  test    rbx, rbx
0x18001632e  jnz     short loc_180016366
0x180016330  mov     rcx, [rbp+18h]; this
0x180016334  mov     ebx, 8007000Eh
0x180016339  mov     r9d, ebx; char *
0x18001633c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016343  mov     edx, 1D7h; void *
0x180016348  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001634d  nop
0x18001634e  xor     ecx, ecx; bstrString
0x180016350  call    cs:__imp_SysFreeString
0x180016356  nop
0x180016357  lea     rcx, [rbp+var_48]
0x18001635b  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180016360  nop
0x180016361  jmp     loc_180016407
0x180016366  mov     rcx, [rbp+var_48]
0x18001636a  mov     rax, [rcx]
0x18001636d  mov     rdx, rbx
0x180016370  mov     rax, [rax+0A8h]
0x180016377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001637c  mov     edi, eax
0x18001637e  test    eax, eax
0x180016380  jns     short loc_1800163B3
0x180016382  mov     rcx, [rbp+18h]; this
0x180016386  mov     r9d, eax; char *
0x180016389  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016390  mov     edx, 1DAh; void *
0x180016395  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001639a  nop
0x18001639b  mov     rcx, rbx; bstrString
0x18001639e  call    cs:__imp_SysFreeString
0x1800163a4  nop
0x1800163a5  lea     rcx, [rbp+var_48]
0x1800163a9  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x1800163ae  nop
0x1800163af  mov     ebx, edi
0x1800163b1  jmp     short loc_180016407
0x1800163b3  lea     rcx, [rbp+var_30]; this
0x1800163b7  call    ?UpdateTask@AikEnrollTask@@QEAAJXZ; AikEnrollTask::UpdateTask(void)
0x1800163bc  mov     edi, eax
0x1800163be  test    eax, eax
0x1800163c0  jns     short loc_1800163F1
0x1800163c2  mov     rcx, [rbp+18h]; this
0x1800163c6  mov     r9d, eax; char *
0x1800163c9  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800163d0  mov     edx, 1DDh; void *
0x1800163d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800163da  nop
0x1800163db  mov     rcx, rbx; bstrString
0x1800163de  call    cs:__imp_SysFreeString
0x1800163e4  nop
0x1800163e5  lea     rcx, [rbp+var_48]
0x1800163e9  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x1800163ee  nop
0x1800163ef  jmp     short loc_1800163AF
0x1800163f1  mov     rcx, rbx; bstrString
0x1800163f4  call    cs:__imp_SysFreeString
0x1800163fa  nop
0x1800163fb  lea     rcx, [rbp+var_48]
0x1800163ff  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180016404  nop
0x180016405  xor     ebx, ebx
0x180016407  lea     rcx, [rbp+var_40]
0x18001640b  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180016410  nop
0x180016411  lea     rcx, [rbp+var_30]; this
0x180016415  call    ??1AikEnrollTask@@QEAA@XZ; AikEnrollTask::~AikEnrollTask(void)
0x18001641a  nop
0x18001641b  lea     rcx, [rbp+var_50]
0x18001641f  call    wil__details__ScopeExitFnGuard__lambda_c8ea37a3166e7b4a2f87be30e1bb2a2b_____operator__
0x180016424  mov     eax, ebx
0x180016426  add     rsp, 70h
0x18001642a  pop     rdi
0x18001642b  pop     rbx
0x18001642c  pop     rbp
0x18001642d  retn
```
