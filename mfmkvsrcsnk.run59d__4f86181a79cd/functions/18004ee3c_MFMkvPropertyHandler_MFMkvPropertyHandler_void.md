# MFMkvPropertyHandler::~MFMkvPropertyHandler(void)

- ea: `0x18004ee3c`
- end: `0x18004ef1d`
- name: `??1MFMkvPropertyHandler@@UEAA@XZ`
- size: `225`
- prototype: `void __fastcall(MFMkvPropertyHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004efb0`

## callees

- `0x180004be4`
- `0x180005c68`
- `0x18004ee3c`
- `0x180058e90`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004eecc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004eedf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004eecc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004eedf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MFMkvPropertyHandler::~MFMkvPropertyHandler(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE OwningThread; // rcx
  __int64 v3; // rax

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&MFMkvPropertyHandler::`vftable';
  *(_QWORD *)&this->LockCount = &MFMkvPropertyHandler::`vftable'{for `IPropertyStore's `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IInitializeWithStream,IPropertyStore,IPropertyStoreCapabilities>'};
  this->OwningThread = &MFMkvPropertyHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPropertyStoreCapabilities>'};
  this->SpinCount = (ULONG_PTR)&MFMkvPropertyHandler::`vftable'{for `IInitializeWithStream'};
  this[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&MFMkvPropertyHandler::`vftable'{for `IPropertyStore's `CWMPropHandlerBase'};
  *(_QWORD *)&this[1].LockCount = &MFMkvPropertyHandler::`vftable'{for `IPropertyStoreCapabilities'};
  this[1].OwningThread = &MFMkvPropertyHandler::`vftable'{for `IModifyPropertyStoreCapabilities'};
  OwningThread = this[50].OwningThread;
  if ( OwningThread )
  {
    this[50].OwningThread = 0;
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)OwningThread + 16LL))(OwningThread);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&this[50].LockCount);
  DeleteCriticalSection(this + 49);
  DeleteCriticalSection(this + 48);
  v3 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  CWMPropHandlerBase::~CWMPropHandlerBase((CWMPropHandlerBase *)&this->SpinCount);
  HIDWORD(this->LockSemaphore) = -1073741823;
}

```

## disassembly

```asm
0x18004ee3c  mov     [rsp+arg_0], rbx
0x18004ee41  push    rdi
0x18004ee42  sub     rsp, 20h
0x18004ee46  mov     rbx, rcx
0x18004ee49  lea     rax, ??_7MFMkvPropertyHandler@@6B@; const MFMkvPropertyHandler::`vftable'
0x18004ee50  mov     [rcx], rax
0x18004ee53  lea     rax, ??_7MFMkvPropertyHandler@@6BIPropertyStore@@?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIInitializeWithStream@@UIPropertyStore@@UIPropertyStoreCapabilities@@@WRL@Microsoft@@@; const MFMkvPropertyHandler::`vftable'{for `IPropertyStore's `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IInitializeWithStream,IPropertyStore,IPropertyStoreCapabilities>'}
0x18004ee5a  mov     [rcx+8], rax
0x18004ee5e  lea     rax, ??_7MFMkvPropertyHandler@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIPropertyStoreCapabilities@@@Details@WRL@Microsoft@@@; const MFMkvPropertyHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPropertyStoreCapabilities>'}
0x18004ee65  mov     [rcx+10h], rax
0x18004ee69  lea     rax, ??_7MFMkvPropertyHandler@@6BIInitializeWithStream@@@; const MFMkvPropertyHandler::`vftable'{for `IInitializeWithStream'}
0x18004ee70  mov     [rcx+20h], rax
0x18004ee74  lea     rax, ??_7MFMkvPropertyHandler@@6BIPropertyStore@@CWMPropHandlerBase@@@; const MFMkvPropertyHandler::`vftable'{for `IPropertyStore's `CWMPropHandlerBase'}
0x18004ee7b  mov     [rcx+28h], rax
0x18004ee7f  lea     rax, ??_7MFMkvPropertyHandler@@6BIPropertyStoreCapabilities@@@; const MFMkvPropertyHandler::`vftable'{for `IPropertyStoreCapabilities'}
0x18004ee86  mov     [rcx+30h], rax
0x18004ee8a  lea     rax, ??_7MFMkvPropertyHandler@@6BIModifyPropertyStoreCapabilities@@@; const MFMkvPropertyHandler::`vftable'{for `IModifyPropertyStoreCapabilities'}
0x18004ee91  mov     [rcx+38h], rax
0x18004ee95  mov     rcx, [rcx+7E0h]
0x18004ee9c  test    rcx, rcx
0x18004ee9f  jz      short loc_18004EEB9
0x18004eea1  mov     qword ptr [rbx+7E0h], 0
0x18004eeac  mov     rax, [rcx]
0x18004eeaf  mov     rax, [rax+10h]
0x18004eeb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eeb8  nop
0x18004eeb9  lea     rcx, [rbx+7D8h]
0x18004eec0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004eec5  lea     rcx, [rbx+7A8h]; lpCriticalSection
0x18004eecc  call    cs:__imp_DeleteCriticalSection
0x18004eed3  nop     dword ptr [rax+rax+00h]
0x18004eed8  lea     rcx, [rbx+780h]; lpCriticalSection
0x18004eedf  call    cs:__imp_DeleteCriticalSection
0x18004eee6  nop     dword ptr [rax+rax+00h]
0x18004eeeb  nop
0x18004eeec  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18004eef1  mov     rdx, [rax]
0x18004eef4  mov     rcx, rax
0x18004eef7  mov     rax, [rdx+10h]
0x18004eefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef00  nop
0x18004ef01  lea     rcx, [rbx+20h]; this
0x18004ef05  call    ??1CWMPropHandlerBase@@MEAA@XZ; CWMPropHandlerBase::~CWMPropHandlerBase(void)
0x18004ef0a  mov     dword ptr [rbx+1Ch], 0C0000001h
0x18004ef11  mov     rbx, [rsp+28h+arg_0]
0x18004ef16  add     rsp, 20h
0x18004ef1a  pop     rdi
0x18004ef1b  retn
```
