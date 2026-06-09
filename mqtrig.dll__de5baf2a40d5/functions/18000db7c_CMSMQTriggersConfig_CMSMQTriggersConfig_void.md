# CMSMQTriggersConfig::~CMSMQTriggersConfig(void)

- ea: `0x18000db7c`
- end: `0x18000db9c`
- name: `??1CMSMQTriggersConfig@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(CMSMQTriggersConfig *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dafc`

## callees

- `0x1800030d8`
- `0x1800055fc`

## pseudocode

```c
void __fastcall CMSMQTriggersConfig::~CMSMQTriggersConfig(CMSMQTriggersConfig *this)
{
  ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>((__int64 *)this + 9);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((CMSMQTriggersConfig *)((char *)this + 24));
}

```

## disassembly

```asm
0x18000db7c  push    rbx
0x18000db7e  sub     rsp, 20h
0x18000db82  mov     rbx, rcx
0x18000db85  add     rcx, 48h ; 'H'
0x18000db89  call    ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
0x18000db8e  lea     rcx, [rbx+18h]; this
0x18000db92  add     rsp, 20h
0x18000db96  pop     rbx
0x18000db97  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
