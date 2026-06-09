# wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)

- ea: `0x1000f598`
- end: `0x1000f5b1`
- name: `??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ`
- size: `25`
- prototype: `int __thiscall(int *this)`
- caller_count: `22`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10008640`
- `0x10008c1d`
- `0x10036f60`
- `0x100373a0`
- `0x10037431`
- `0x100375df`
- `0x1003771b`
- `0x10037be0`
- `0x10037eb2`
- `0x10038410`
- `0x10039500`
- `0x10039550`
- `0x10039795`
- `0x1003990a`
- `0x10039a00`
- `0x10039b30`
- `0x10039cc7`
- `0x10039dec`
- `0x10039e3c`
- `0x1003a0bd`
- `0x1003a20a`
- `0x1003a270`

## callees

- `0x1000f598`
- `0x1002d510`

## pseudocode

```c
int __thiscall wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(
        int *this)
{
  int v1; // ecx
  int result; // eax

  v1 = *this;
  if ( v1 )
    return (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v1 + 8))(*(_DWORD *)(*(_DWORD *)v1 + 8), v1);
  return result;
}

```

## disassembly

```asm
0x1000f598  mov     ecx, [ecx]
0x1000f59a  test    ecx, ecx
0x1000f59c  jz      short locret_1000F5B0
0x1000f59e  mov     eax, [ecx]
0x1000f5a0  push    esi
0x1000f5a1  push    ecx
0x1000f5a2  mov     esi, [eax+8]
0x1000f5a5  mov     ecx, esi; this
0x1000f5a7  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f5ad  call    esi
0x1000f5af  pop     esi
0x1000f5b0  retn
```
