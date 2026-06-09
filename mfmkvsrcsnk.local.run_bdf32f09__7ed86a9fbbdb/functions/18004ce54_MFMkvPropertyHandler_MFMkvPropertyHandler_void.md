# MFMkvPropertyHandler::~MFMkvPropertyHandler(void)

- ea: `0x18004ce54`
- end: `0x18004cf28`
- name: `??1MFMkvPropertyHandler@@UEAA@XZ`
- size: `212`
- prototype: `void __fastcall(MFMkvPropertyHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004cfb0`

## callees

- `0x180004b10`
- `0x180005ab8`
- `0x18004ce54`
- `0x1800569a8`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004cee4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004cef1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004cee4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004cef1`

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
0x18004ce54  mov     [rsp+arg_0], rbx
0x18004ce59  push    rdi
0x18004ce5a  sub     rsp, 20h
0x18004ce5e  mov     rbx, rcx
0x18004ce61  lea     rax, ??_7MFMkvPropertyHandler@@6B@; const MFMkvPropertyHandler::`vftable'
0x18004ce68  mov     [rcx], rax
0x18004ce6b  lea     rax, ??_7MFMkvPropertyHandler@@6BIPropertyStore@@?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIInitializeWithStream@@UIPropertyStore@@UIPropertyStoreCapabilities@@@WRL@Microsoft@@@; const MFMkvPropertyHandler::`vftable'{for `IPropertyStore's `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IInitializeWithStream,IPropertyStore,IPropertyStoreCapabilities>'}
0x18004ce72  mov     [rcx+8], rax
0x18004ce76  lea     rax, ??_7MFMkvPropertyHandler@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIPropertyStoreCapabilities@@@Details@WRL@Microsoft@@@; const MFMkvPropertyHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPropertyStoreCapabilities>'}
0x18004ce7d  mov     [rcx+10h], rax
0x18004ce81  lea     rax, ??_7MFMkvPropertyHandler@@6BIInitializeWithStream@@@; const MFMkvPropertyHandler::`vftable'{for `IInitializeWithStream'}
0x18004ce88  mov     [rcx+20h], rax
0x18004ce8c  lea     rax, ??_7MFMkvPropertyHandler@@6BIPropertyStore@@CWMPropHandlerBase@@@; const MFMkvPropertyHandler::`vftable'{for `IPropertyStore's `CWMPropHandlerBase'}
0x18004ce93  mov     [rcx+28h], rax
0x18004ce97  lea     rax, ??_7MFMkvPropertyHandler@@6BIPropertyStoreCapabilities@@@; const MFMkvPropertyHandler::`vftable'{for `IPropertyStoreCapabilities'}
0x18004ce9e  mov     [rcx+30h], rax
0x18004cea2  lea     rax, ??_7MFMkvPropertyHandler@@6BIModifyPropertyStoreCapabilities@@@; const MFMkvPropertyHandler::`vftable'{for `IModifyPropertyStoreCapabilities'}
0x18004cea9  mov     [rcx+38h], rax
0x18004cead  mov     rcx, [rcx+7E0h]
0x18004ceb4  test    rcx, rcx
0x18004ceb7  jz      short loc_18004CED1
0x18004ceb9  mov     qword ptr [rbx+7E0h], 0
0x18004cec4  mov     rax, [rcx]
0x18004cec7  mov     rax, [rax+10h]
0x18004cecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ced0  nop
0x18004ced1  lea     rcx, [rbx+7D8h]
0x18004ced8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cedd  lea     rcx, [rbx+7A8h]; lpCriticalSection
0x18004cee4  call    cs:__imp_DeleteCriticalSection
0x18004ceea  lea     rcx, [rbx+780h]; lpCriticalSection
0x18004cef1  call    cs:__imp_DeleteCriticalSection
0x18004cef7  nop
0x18004cef8  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18004cefd  mov     rdx, [rax]
0x18004cf00  mov     rcx, rax
0x18004cf03  mov     rax, [rdx+10h]
0x18004cf07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf0c  nop
0x18004cf0d  lea     rcx, [rbx+20h]; this
0x18004cf11  call    ??1CWMPropHandlerBase@@MEAA@XZ; CWMPropHandlerBase::~CWMPropHandlerBase(void)
0x18004cf16  mov     dword ptr [rbx+1Ch], 0C0000001h
0x18004cf1d  mov     rbx, [rsp+28h+arg_0]
0x18004cf22  add     rsp, 20h
0x18004cf26  pop     rdi
0x18004cf27  retn
```
