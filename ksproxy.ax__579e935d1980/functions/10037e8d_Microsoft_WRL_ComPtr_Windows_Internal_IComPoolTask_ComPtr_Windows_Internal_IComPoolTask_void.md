# Microsoft::WRL::ComPtr<Windows::Internal::IComPoolTask>::~ComPtr<Windows::Internal::IComPoolTask>(void)

- ea: `0x10037e8d`
- end: `0x10037eac`
- name: `??1?$ComPtr@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QAE@XZ`
- size: `31`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x10038fb5`
- `0x100392dd`
- `0x10039550`
- `0x10039795`
- `0x10039cc7`
- `0x10039cf0`
- `0x10039db7`
- `0x10039e3c`
- `0x1003a0bd`

## callees

- `0x1002d510`
- `0x10037e8d`

## pseudocode

```c
int __thiscall Microsoft::WRL::ComPtr<Windows::Internal::IComPoolTask>::~ComPtr<Windows::Internal::IComPoolTask>(
        int *this)
{
  int v1; // edx
  int result; // eax

  v1 = *this;
  if ( *this )
  {
    *this = 0;
    return (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v1 + 8))(*(_DWORD *)(*(_DWORD *)v1 + 8), v1);
  }
  return result;
}

```

## disassembly

```asm
0x10037e8d  mov     edx, [ecx]
0x10037e8f  test    edx, edx
0x10037e91  jz      short locret_10037EAB
0x10037e93  mov     dword ptr [ecx], 0
0x10037e99  mov     eax, [edx]
0x10037e9b  push    esi
0x10037e9c  push    edx
0x10037e9d  mov     esi, [eax+8]
0x10037ea0  mov     ecx, esi; this
0x10037ea2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10037ea8  call    esi
0x10037eaa  pop     esi
0x10037eab  retn
```
