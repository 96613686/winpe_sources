# KsProxyCameraAccessHandler::~KsProxyCameraAccessHandler(void)

- ea: `0x1003771b`
- end: `0x10037747`
- name: `??1KsProxyCameraAccessHandler@@EAE@XZ`
- size: `44`
- prototype: `void __thiscall(KsProxyCameraAccessHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x10037750`

## callees

- `0x1000f598`
- `0x100377d0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x10037730`
- `KERNEL32!DeleteCriticalSection` at `0x10037730`

## pseudocode

```c
void __thiscall KsProxyCameraAccessHandler::~KsProxyCameraAccessHandler(KsProxyCameraAccessHandler *this)
{
  *(_DWORD *)this = &KsProxyCameraAccessHandler::`vftable';
  KsProxyCameraAccessHandler::Shutdown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>((char *)this + 12);
  *((_DWORD *)this + 2) = -1073741823;
}

```

## disassembly

```asm
0x1003771b  mov     edi, edi
0x1003771d  push    esi
0x1003771e  mov     esi, ecx
0x10037720  push    esi; this
0x10037721  mov     dword ptr [esi], offset ??_7KsProxyCameraAccessHandler@@6B@; const KsProxyCameraAccessHandler::`vftable'
0x10037727  call    ?Shutdown@KsProxyCameraAccessHandler@@UAGJXZ; KsProxyCameraAccessHandler::Shutdown(void)
0x1003772c  lea     eax, [esi+10h]
0x1003772f  push    eax; lpCriticalSection
0x10037730  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10037736  lea     ecx, [esi+0Ch]
0x10037739  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x1003773e  mov     dword ptr [esi+8], 0C0000001h
0x10037745  pop     esi
0x10037746  retn
```
