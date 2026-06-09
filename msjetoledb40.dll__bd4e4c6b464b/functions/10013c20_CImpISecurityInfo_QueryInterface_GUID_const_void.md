# CImpISecurityInfo::QueryInterface(_GUID const &,void * *)

- ea: `0x10013c20`
- end: `0x10013c49`
- name: `?QueryInterface@CImpISecurityInfo@@UAGJABU_GUID@@PAPAX@Z`
- size: `41`
- prototype: `int __stdcall(CImpISecurityInfo *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1001c6d0`

## pseudocode

```c
int __stdcall CImpISecurityInfo::QueryInterface(CImpISecurityInfo *this, const struct _GUID *a2, void **a3)
{
  return (***(int (__thiscall ****)(_DWORD, _DWORD, const struct _GUID *, void **))(*((_DWORD *)this + 2) + 8))(
           ***(_DWORD ***)(*((_DWORD *)this + 2) + 8),
           *(_DWORD *)(*((_DWORD *)this + 2) + 8),
           a2,
           a3);
}

```

## disassembly

```asm
0x10013c20  mov     edi, edi
0x10013c22  push    ebp
0x10013c23  mov     ebp, esp
0x10013c25  mov     eax, [ebp+this]
0x10013c28  push    esi
0x10013c29  push    [ebp+arg_8]
0x10013c2c  mov     eax, [eax+8]
0x10013c2f  push    [ebp+arg_4]
0x10013c32  mov     ecx, [eax+8]
0x10013c35  push    ecx
0x10013c36  mov     eax, [ecx]
0x10013c38  mov     esi, [eax]
0x10013c3a  mov     ecx, esi
0x10013c3c  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10013c42  call    esi
0x10013c44  pop     esi
0x10013c45  pop     ebp
0x10013c46  retn    0Ch
```
