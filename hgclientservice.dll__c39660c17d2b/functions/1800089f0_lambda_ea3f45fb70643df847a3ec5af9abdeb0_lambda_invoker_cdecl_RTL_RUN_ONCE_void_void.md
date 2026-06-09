# _lambda_ea3f45fb70643df847a3ec5af9abdeb0_::_lambda_invoker_cdecl_(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800089f0`
- end: `0x180008a5c`
- name: `?_lambda_invoker_cdecl_@_lambda_ea3f45fb70643df847a3ec5af9abdeb0_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008760`
- `0x1800089f0`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x180008a2e`
- `combase!__imp_CoGetSharedServiceId` at `0x180008a2e`

## string_xrefs

- `0x180008a4a`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_ea3f45fb70643df847a3ec5af9abdeb0_::_lambda_invoker_cdecl_(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  int SharedServiceId; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  byte_1800205E8 = 1;
  Microsoft::WRL::Details::ModuleBase::module_ = (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<HgServiceModule,1,int>::instance_;
  qword_1800205D8 = 0;
  Microsoft::WRL::Details::StaticStorage<HgServiceModule,1,int>::instance_ = &HgServiceModule::`vftable';
  SharedServiceId = CoGetSharedServiceId(&qword_1800205E0, Parameter, Context);
  if ( SharedServiceId < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      (const char *)(unsigned int)SharedServiceId,
      v5);
  return 1;
}

```

## disassembly

```asm
0x1800089f0  sub     rsp, 28h
0x1800089f4  mov     cs:byte_1800205E8, 1
0x1800089fb  lea     rax, ?instance_@?$StaticStorage@VHgServiceModule@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<HgServiceModule,1,int> Microsoft::WRL::Details::StaticStorage<HgServiceModule,1,int>::instance_
0x180008a02  mov     [rsp+28h+arg_18], rax
0x180008a07  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, rax; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008a0e  mov     cs:qword_1800205D8, 0
0x180008a19  lea     rax, ??_7HgServiceModule@@6B@; const HgServiceModule::`vftable'
0x180008a20  mov     cs:?instance_@?$StaticStorage@VHgServiceModule@@$00H@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<HgServiceModule,1,int> Microsoft::WRL::Details::StaticStorage<HgServiceModule,1,int>::instance_
0x180008a27  lea     rcx, qword_1800205E0
0x180008a2e  call    cs:__imp_CoGetSharedServiceId
0x180008a34  mov     rcx, [rsp+28h]; this
0x180008a39  test    eax, eax
0x180008a3b  js      short loc_180008A47
0x180008a3d  mov     eax, 1
0x180008a42  add     rsp, 28h
0x180008a46  retn
0x180008a47  mov     r9d, eax; char *
0x180008a4a  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x180008a51  mov     edx, 15h; void *
0x180008a56  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
