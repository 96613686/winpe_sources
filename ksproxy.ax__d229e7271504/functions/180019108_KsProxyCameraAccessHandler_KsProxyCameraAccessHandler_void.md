# KsProxyCameraAccessHandler::~KsProxyCameraAccessHandler(void)

- ea: `0x180019108`
- end: `0x180019147`
- name: `??1KsProxyCameraAccessHandler@@EEAA@XZ`
- size: `63`
- prototype: `void __fastcall(KsProxyCameraAccessHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800190d0`

## callees

- `0x180007b14`
- `0x18001b5f0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180019124`
- `KERNEL32!DeleteCriticalSection` at `0x180019124`

## pseudocode

```c
void __fastcall KsProxyCameraAccessHandler::~KsProxyCameraAccessHandler(KsProxyCameraAccessHandler *this)
{
  *(_QWORD *)this = &KsProxyCameraAccessHandler::`vftable';
  KsProxyCameraAccessHandler::Shutdown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)this + 2);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180019108  push    rbx
0x18001910a  sub     rsp, 20h
0x18001910e  lea     rax, ??_7KsProxyCameraAccessHandler@@6B@; const KsProxyCameraAccessHandler::`vftable'
0x180019115  mov     rbx, rcx
0x180019118  mov     [rcx], rax
0x18001911b  call    ?Shutdown@KsProxyCameraAccessHandler@@UEAAJXZ; KsProxyCameraAccessHandler::Shutdown(void)
0x180019120  lea     rcx, [rbx+18h]; lpCriticalSection
0x180019124  call    cs:__imp_DeleteCriticalSection
0x18001912b  nop     dword ptr [rax+rax+00h]
0x180019130  lea     rcx, [rbx+10h]
0x180019134  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180019139  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180019140  add     rsp, 20h
0x180019144  pop     rbx
0x180019145  retn
```
