# wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset(void)

- ea: `0x1000f5b7`
- end: `0x1000f5d6`
- name: `?reset@?$com_ptr_t@UIKsProxyCameraAccessHandler@@Uerr_returncode_policy@wil@@@wil@@QAEXXZ`
- size: `31`
- prototype: `int __thiscall(int *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x10008c1d`
- `0x1000cf60`
- `0x100375df`

## callees

- `0x1000f5b7`
- `0x1002d510`

## pseudocode

```c
int __thiscall wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset(int *this)
{
  int v1; // edx
  int result; // eax

  v1 = *this;
  *this = 0;
  if ( v1 )
    return (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v1 + 8))(*(_DWORD *)(*(_DWORD *)v1 + 8), v1);
  return result;
}

```

## disassembly

```asm
0x1000f5b7  mov     edx, [ecx]
0x1000f5b9  mov     dword ptr [ecx], 0
0x1000f5bf  test    edx, edx
0x1000f5c1  jz      short locret_1000F5D5
0x1000f5c3  mov     eax, [edx]
0x1000f5c5  push    esi
0x1000f5c6  push    edx
0x1000f5c7  mov     esi, [eax+8]
0x1000f5ca  mov     ecx, esi; this
0x1000f5cc  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f5d2  call    esi
0x1000f5d4  pop     esi
0x1000f5d5  retn
```
