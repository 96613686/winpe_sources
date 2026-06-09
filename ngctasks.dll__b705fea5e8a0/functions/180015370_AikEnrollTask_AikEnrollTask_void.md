# AikEnrollTask::~AikEnrollTask(void)

- ea: `0x180015370`
- end: `0x1800153ba`
- name: `??1AikEnrollTask@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(AikEnrollTask *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800154ec`
- `0x1800161f4`
- `0x180016570`
- `0x180020774`
- `0x1800208f2`

## callees

- `0x180008ab0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800153ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800153ad`

## pseudocode

```c
void __fastcall AikEnrollTask::~AikEnrollTask(AikEnrollTask *this)
{
  ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)this + 3);
  ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)this + 2);
  ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)this + 1);
  SysFreeString(*(BSTR *)this);
}

```

## disassembly

```asm
0x180015370  mov     [rsp+arg_0], rcx
0x180015375  push    rbx
0x180015376  sub     rsp, 20h
0x18001537a  mov     rbx, rcx
0x18001537d  add     rcx, 18h
0x180015381  mov     [rsp+28h+arg_8], rcx
0x180015386  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18001538b  nop
0x18001538c  lea     rcx, [rbx+10h]
0x180015390  mov     [rsp+28h+arg_10], rcx
0x180015395  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18001539a  nop
0x18001539b  lea     rcx, [rbx+8]
0x18001539f  mov     [rsp+28h+arg_18], rcx
0x1800153a4  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x1800153a9  nop
0x1800153aa  mov     rcx, [rbx]; bstrString
0x1800153ad  call    cs:__imp_SysFreeString
0x1800153b3  nop
0x1800153b4  add     rsp, 20h
0x1800153b8  pop     rbx
0x1800153b9  retn
```
