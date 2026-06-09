# reschedRemoveTrigger(_TASK_TRIGGER_TYPE2)

- ea: `0x180016570`
- end: `0x1800166b2`
- name: `?reschedRemoveTrigger@@YAJW4_TASK_TRIGGER_TYPE2@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(enum _TASK_TRIGGER_TYPE2)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001417c`
- `0x180016100`

## callees

- `0x180008ab0`
- `0x18000cc34`
- `0x180015338`
- `0x180015370`
- `0x180015720`
- `0x180015abc`
- `0x180016144`
- `0x180016490`
- `0x180016570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016581`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016581`

## string_xrefs

- `0x180016594`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x18001661a`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x18001664b`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180016675`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall reschedRemoveTrigger(unsigned int a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  int Trigger; // eax
  int v5; // eax
  int updated; // eax
  int v8; // [rsp+20h] [rbp-40h] BYREF
  struct ITrigger *v9; // [rsp+28h] [rbp-38h] BYREF
  BSTR v10[4]; // [rsp+30h] [rbp-30h] BYREF
  int v11; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    wil::ScopeExitIgnore__lambda_c8ea37a3166e7b4a2f87be30e1bb2a2b___(&v8);
    memset(v10, 0, sizeof(v10));
    v11 = 0;
    v9 = 0;
    Trigger = AikEnrollTask::GetTrigger(v10, a1, 0, &v9);
    v3 = Trigger;
    if ( Trigger < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F4,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)(unsigned int)Trigger,
        v8);
LABEL_11:
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v9);
      AikEnrollTask::~AikEnrollTask((AikEnrollTask *)v10);
      wil::details::ScopeExitFnGuard__lambda_c8ea37a3166e7b4a2f87be30e1bb2a2b___::operator()(&v8);
      return v3;
    }
    if ( v9 )
    {
      v5 = AikEnrollTask::RemoveTrigger((AikEnrollTask *)v10);
      v3 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F8,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
          (const char *)(unsigned int)v5,
          v8);
        goto LABEL_11;
      }
      updated = AikEnrollTask::UpdateTask((AikEnrollTask *)v10);
      v3 = updated;
      if ( updated < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1FB,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
          (const char *)(unsigned int)updated,
          v8);
        goto LABEL_11;
      }
    }
    v3 = 0;
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E7,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
    (const char *)(unsigned int)v2,
    v8);
  return v3;
}

```

## disassembly

```asm
0x180016570  push    rbp
0x180016572  push    rbx
0x180016573  push    rdi
0x180016574  mov     rbp, rsp
0x180016577  sub     rsp, 60h
0x18001657b  mov     edi, ecx
0x18001657d  xor     edx, edx; dwCoInit
0x18001657f  xor     ecx, ecx; pvReserved
0x180016581  call    cs:__imp_CoInitializeEx
0x180016587  mov     ebx, eax
0x180016589  test    eax, eax
0x18001658b  jns     short loc_1800165AA
0x18001658d  mov     rcx, [rbp+18h]; this
0x180016591  mov     r9d, eax; char *
0x180016594  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001659b  mov     edx, 1E7h; void *
0x1800165a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800165a5  jmp     loc_1800166A8
0x1800165aa  lea     rcx, [rbp+var_40]
0x1800165ae  call    wil__ScopeExitIgnore__lambda_c8ea37a3166e7b4a2f87be30e1bb2a2b___
0x1800165b3  nop
0x1800165b4  mov     [rbp+var_30], 0
0x1800165bc  lea     rax, [rbp+var_28]
0x1800165c0  mov     [rbp+arg_8], rax
0x1800165c4  mov     [rbp+var_28], 0
0x1800165cc  lea     rax, [rbp+var_20]
0x1800165d0  mov     [rbp+arg_10], rax
0x1800165d4  mov     [rbp+var_20], 0
0x1800165dc  lea     rax, [rbp+var_18]
0x1800165e0  mov     [rbp+arg_18], rax
0x1800165e4  mov     [rbp+var_18], 0
0x1800165ec  mov     [rbp+var_10], 0
0x1800165f3  mov     [rbp+var_38], 0
0x1800165fb  lea     r9, [rbp+var_38]; struct ITrigger **
0x1800165ff  xor     r8d, r8d; bool
0x180016602  mov     edx, edi; enum _TASK_TRIGGER_TYPE2
0x180016604  lea     rcx, [rbp+var_30]; this
0x180016608  call    ?GetTrigger@AikEnrollTask@@QEAAJW4_TASK_TRIGGER_TYPE2@@_NPEAPEAUITrigger@@@Z; AikEnrollTask::GetTrigger(_TASK_TRIGGER_TYPE2,bool,ITrigger * *)
0x18001660d  mov     ebx, eax
0x18001660f  test    eax, eax
0x180016611  jns     short loc_18001662E
0x180016613  mov     rcx, [rbp+18h]; this
0x180016617  mov     r9d, eax; char *
0x18001661a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016621  mov     edx, 1F4h; void *
0x180016626  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001662b  nop
0x18001662c  jmp     short loc_18001668B
0x18001662e  cmp     [rbp+var_38], 0
0x180016633  jz      short loc_180016689
0x180016635  lea     rcx, [rbp+var_30]; this
0x180016639  call    ?RemoveTrigger@AikEnrollTask@@QEAAJXZ; AikEnrollTask::RemoveTrigger(void)
0x18001663e  mov     ebx, eax
0x180016640  test    eax, eax
0x180016642  jns     short loc_18001665F
0x180016644  mov     rcx, [rbp+18h]; this
0x180016648  mov     r9d, eax; char *
0x18001664b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016652  mov     edx, 1F8h; void *
0x180016657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001665c  nop
0x18001665d  jmp     short loc_18001668B
0x18001665f  lea     rcx, [rbp+var_30]; this
0x180016663  call    ?UpdateTask@AikEnrollTask@@QEAAJXZ; AikEnrollTask::UpdateTask(void)
0x180016668  mov     ebx, eax
0x18001666a  test    eax, eax
0x18001666c  jns     short loc_180016689
0x18001666e  mov     rcx, [rbp+18h]; this
0x180016672  mov     r9d, eax; char *
0x180016675  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001667c  mov     edx, 1FBh; void *
0x180016681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016686  nop
0x180016687  jmp     short loc_18001668B
0x180016689  xor     ebx, ebx
0x18001668b  lea     rcx, [rbp+var_38]
0x18001668f  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180016694  nop
0x180016695  lea     rcx, [rbp+var_30]; this
0x180016699  call    ??1AikEnrollTask@@QEAA@XZ; AikEnrollTask::~AikEnrollTask(void)
0x18001669e  nop
0x18001669f  lea     rcx, [rbp+var_40]
0x1800166a3  call    wil__details__ScopeExitFnGuard__lambda_c8ea37a3166e7b4a2f87be30e1bb2a2b_____operator__
0x1800166a8  mov     eax, ebx
0x1800166aa  add     rsp, 60h
0x1800166ae  pop     rdi
0x1800166af  pop     rbx
0x1800166b0  pop     rbp
0x1800166b1  retn
```
