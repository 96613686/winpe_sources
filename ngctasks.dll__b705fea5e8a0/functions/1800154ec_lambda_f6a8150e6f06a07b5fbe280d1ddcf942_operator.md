# _lambda_f6a8150e6f06a07b5fbe280d1ddcf942_::operator()

- ea: `0x1800154ec`
- end: `0x18001571a`
- name: `_lambda_f6a8150e6f06a07b5fbe280d1ddcf942_::operator()`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180015310`

## callees

- `0x180008ab0`
- `0x18000cc34`
- `0x180015338`
- `0x180015370`
- `0x1800154ec`
- `0x180015720`
- `0x180015748`
- `0x180015abc`
- `0x180016490`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800154fe`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800154fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18001563b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001568a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001563b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001568a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156e0`

## string_xrefs

- `0x180015511`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x18001559a`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x1800155e0`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015625`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015675`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x1800156b5`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall lambda_f6a8150e6f06a07b5fbe280d1ddcf942_::operator()(const struct _FILETIME ***a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  int Trigger; // eax
  int v5; // eax
  int v6; // eax
  OLECHAR *v7; // rbx
  int v8; // eax
  int v9; // edi
  int updated; // eax
  int v12; // [rsp+20h] [rbp-50h] BYREF
  __int64 v13; // [rsp+28h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-40h] BYREF
  struct ITrigger *v15; // [rsp+38h] [rbp-38h] BYREF
  BSTR v16[4]; // [rsp+40h] [rbp-30h] BYREF
  int v17; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    wil::ScopeExitIgnore__lambda_c8ea37a3166e7b4a2f87be30e1bb2a2b___(&v12);
    memset(v16, 0, sizeof(v16));
    v17 = 0;
    v15 = 0;
    Trigger = AikEnrollTask::GetTrigger(v16, 1u, 1, &v15);
    v3 = Trigger;
    if ( Trigger >= 0 )
    {
      v13 = 0;
      v5 = ((__int64 (__fastcall *)(struct ITrigger *, GUID *, __int64 *))v15->lpVtbl->QueryInterface)(
             v15,
             &IID_ITimeTrigger,
             &v13);
      v3 = v5;
      if ( v5 >= 0 )
      {
        bstrString = 0;
        v6 = FileTimeToTaskTimeString(**a1, &bstrString);
        v3 = v6;
        if ( v6 >= 0 )
        {
          v7 = bstrString;
          v8 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v13 + 120LL))(v13, bstrString);
          v9 = v8;
          if ( v8 >= 0 )
          {
            updated = AikEnrollTask::UpdateTask((AikEnrollTask *)v16);
            v9 = updated;
            if ( updated >= 0 )
            {
              SysFreeString(v7);
              ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v13);
              v3 = 0;
              goto LABEL_15;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x241,
              (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
              (const char *)(unsigned int)updated,
              v12);
            SysFreeString(v7);
            ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v13);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x23E,
              (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
              (const char *)(unsigned int)v8,
              v12);
            SysFreeString(v7);
            ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v13);
          }
          v3 = v9;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x23B,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
            (const char *)(unsigned int)v6,
            v12);
          SysFreeString(bstrString);
          ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v13);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x235,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
          (const char *)(unsigned int)v5,
          v12);
        ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v13);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x230,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)(unsigned int)Trigger,
        v12);
    }
LABEL_15:
    ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v15);
    AikEnrollTask::~AikEnrollTask((AikEnrollTask *)v16);
    wil::details::ScopeExitFnGuard__lambda_c8ea37a3166e7b4a2f87be30e1bb2a2b___::operator()(&v12);
    return v3;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x223,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
    (const char *)(unsigned int)v2,
    v12);
  return v3;
}

```

## disassembly

```asm
0x1800154ec  push    rbp
0x1800154ee  push    rbx
0x1800154ef  push    rdi
0x1800154f0  mov     rbp, rsp
0x1800154f3  sub     rsp, 70h
0x1800154f7  mov     rdi, rcx
0x1800154fa  xor     edx, edx; dwCoInit
0x1800154fc  xor     ecx, ecx; pvReserved
0x1800154fe  call    cs:__imp_CoInitializeEx
0x180015504  mov     ebx, eax
0x180015506  test    eax, eax
0x180015508  jns     short loc_180015527
0x18001550a  mov     rcx, [rbp+18h]; this
0x18001550e  mov     r9d, eax; char *
0x180015511  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015518  mov     edx, 223h; void *
0x18001551d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015522  jmp     loc_180015710
0x180015527  lea     rcx, [rbp+var_50]
0x18001552b  call    wil__ScopeExitIgnore__lambda_c8ea37a3166e7b4a2f87be30e1bb2a2b___
0x180015530  nop
0x180015531  mov     [rbp+var_30], 0
0x180015539  lea     rax, [rbp+var_28]
0x18001553d  mov     [rbp+arg_8], rax
0x180015541  mov     [rbp+var_28], 0
0x180015549  lea     rax, [rbp+var_20]
0x18001554d  mov     [rbp+arg_10], rax
0x180015551  mov     [rbp+var_20], 0
0x180015559  lea     rax, [rbp+var_18]
0x18001555d  mov     [rbp+arg_18], rax
0x180015561  mov     [rbp+var_18], 0
0x180015569  mov     [rbp+var_10], 0
0x180015570  mov     [rbp+var_38], 0
0x180015578  lea     r9, [rbp+var_38]; struct ITrigger **
0x18001557c  mov     r8b, 1; bool
0x18001557f  mov     edx, 1; enum _TASK_TRIGGER_TYPE2
0x180015584  lea     rcx, [rbp+var_30]; this
0x180015588  call    ?GetTrigger@AikEnrollTask@@QEAAJW4_TASK_TRIGGER_TYPE2@@_NPEAPEAUITrigger@@@Z; AikEnrollTask::GetTrigger(_TASK_TRIGGER_TYPE2,bool,ITrigger * *)
0x18001558d  mov     ebx, eax
0x18001558f  test    eax, eax
0x180015591  jns     short loc_1800155B1
0x180015593  mov     rcx, [rbp+18h]; this
0x180015597  mov     r9d, eax; char *
0x18001559a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800155a1  mov     edx, 230h; void *
0x1800155a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800155ab  nop
0x1800155ac  jmp     loc_1800156F3
0x1800155b1  mov     [rbp+var_48], 0
0x1800155b9  mov     rcx, [rbp+var_38]
0x1800155bd  mov     rax, [rcx]
0x1800155c0  lea     r8, [rbp+var_48]
0x1800155c4  lea     rdx, IID_ITimeTrigger
0x1800155cb  mov     rax, [rax]
0x1800155ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155d3  mov     ebx, eax
0x1800155d5  test    eax, eax
0x1800155d7  jns     short loc_180015601
0x1800155d9  mov     rcx, [rbp+18h]; this
0x1800155dd  mov     r9d, eax; char *
0x1800155e0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800155e7  mov     edx, 235h; void *
0x1800155ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800155f1  nop
0x1800155f2  lea     rcx, [rbp+var_48]
0x1800155f6  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x1800155fb  nop
0x1800155fc  jmp     loc_1800156F3
0x180015601  mov     [rbp+bstrString], 0
0x180015609  mov     rcx, [rdi]
0x18001560c  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x180015610  mov     rcx, [rcx]; struct _FILETIME *
0x180015613  call    ?FileTimeToTaskTimeString@@YAJPEBU_FILETIME@@PEAPEAG@Z; FileTimeToTaskTimeString(_FILETIME const *,ushort * *)
0x180015618  mov     ebx, eax
0x18001561a  test    eax, eax
0x18001561c  jns     short loc_180015651
0x18001561e  mov     rcx, [rbp+18h]; this
0x180015622  mov     r9d, eax; char *
0x180015625  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001562c  mov     edx, 23Bh; void *
0x180015631  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015636  nop
0x180015637  mov     rcx, [rbp+bstrString]; bstrString
0x18001563b  call    cs:__imp_SysFreeString
0x180015641  nop
0x180015642  lea     rcx, [rbp+var_48]
0x180015646  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18001564b  nop
0x18001564c  jmp     loc_1800156F3
0x180015651  mov     rcx, [rbp+var_48]
0x180015655  mov     rax, [rcx]
0x180015658  mov     rbx, [rbp+bstrString]
0x18001565c  mov     rdx, rbx
0x18001565f  mov     rax, [rax+78h]
0x180015663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015668  mov     edi, eax
0x18001566a  test    eax, eax
0x18001566c  jns     short loc_18001569F
0x18001566e  mov     rcx, [rbp+18h]; this
0x180015672  mov     r9d, eax; char *
0x180015675  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001567c  mov     edx, 23Eh; void *
0x180015681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015686  nop
0x180015687  mov     rcx, rbx; bstrString
0x18001568a  call    cs:__imp_SysFreeString
0x180015690  nop
0x180015691  lea     rcx, [rbp+var_48]
0x180015695  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18001569a  nop
0x18001569b  mov     ebx, edi
0x18001569d  jmp     short loc_1800156F3
0x18001569f  lea     rcx, [rbp+var_30]; this
0x1800156a3  call    ?UpdateTask@AikEnrollTask@@QEAAJXZ; AikEnrollTask::UpdateTask(void)
0x1800156a8  mov     edi, eax
0x1800156aa  test    eax, eax
0x1800156ac  jns     short loc_1800156DD
0x1800156ae  mov     rcx, [rbp+18h]; this
0x1800156b2  mov     r9d, eax; char *
0x1800156b5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800156bc  mov     edx, 241h; void *
0x1800156c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800156c6  nop
0x1800156c7  mov     rcx, rbx; bstrString
0x1800156ca  call    cs:__imp_SysFreeString
0x1800156d0  nop
0x1800156d1  lea     rcx, [rbp+var_48]
0x1800156d5  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x1800156da  nop
0x1800156db  jmp     short loc_18001569B
0x1800156dd  mov     rcx, rbx; bstrString
0x1800156e0  call    cs:__imp_SysFreeString
0x1800156e6  nop
0x1800156e7  lea     rcx, [rbp+var_48]
0x1800156eb  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x1800156f0  nop
0x1800156f1  xor     ebx, ebx
0x1800156f3  lea     rcx, [rbp+var_38]
0x1800156f7  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x1800156fc  nop
0x1800156fd  lea     rcx, [rbp+var_30]; this
0x180015701  call    ??1AikEnrollTask@@QEAA@XZ; AikEnrollTask::~AikEnrollTask(void)
0x180015706  nop
0x180015707  lea     rcx, [rbp+var_50]
0x18001570b  call    wil__details__ScopeExitFnGuard__lambda_c8ea37a3166e7b4a2f87be30e1bb2a2b_____operator__
0x180015710  mov     eax, ebx
0x180015712  add     rsp, 70h
0x180015716  pop     rdi
0x180015717  pop     rbx
0x180015718  pop     rbp
0x180015719  retn
```
