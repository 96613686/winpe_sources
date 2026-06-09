# wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::com_ptr_t<IWeakReference,wil::err_returncode_policy>(wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> const &)

- ea: `0x100399ce`
- end: `0x100399fa`
- name: `??0?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QAE@ABV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10039550`
- `0x10039795`
- `0x10039e3c`
- `0x1003a0bd`

## callees

- `0x1002d510`
- `0x100399ce`

## pseudocode

```c
int *__thiscall wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::com_ptr_t<IWeakReference,wil::err_returncode_policy>(
        int *this,
        int *a2)
{
  int v3; // edx

  v3 = *a2;
  *this = *a2;
  if ( v3 )
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v3 + 4))(*(_DWORD *)(*(_DWORD *)v3 + 4), v3);
  return this;
}

```

## disassembly

```asm
0x100399ce  mov     edi, edi
0x100399d0  push    ebp
0x100399d1  mov     ebp, esp
0x100399d3  mov     eax, [ebp+arg_0]
0x100399d6  push    edi
0x100399d7  mov     edi, ecx
0x100399d9  mov     edx, [eax]
0x100399db  mov     [edi], edx
0x100399dd  test    edx, edx
0x100399df  jz      short loc_100399F3
0x100399e1  mov     eax, [edx]
0x100399e3  push    esi
0x100399e4  push    edx
0x100399e5  mov     esi, [eax+4]
0x100399e8  mov     ecx, esi; this
0x100399ea  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100399f0  call    esi
0x100399f2  pop     esi
0x100399f3  mov     eax, edi
0x100399f5  pop     edi
0x100399f6  pop     ebp
0x100399f7  retn    4
```
