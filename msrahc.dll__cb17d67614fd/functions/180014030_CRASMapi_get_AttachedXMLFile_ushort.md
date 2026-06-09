# CRASMapi::get_AttachedXMLFile(ushort * *)

- ea: `0x180014030`
- end: `0x180014063`
- name: `?get_AttachedXMLFile@CRASMapi@@UEAAJPEAPEAG@Z`
- size: `51`
- prototype: `__int64 __fastcall(LPCSTR *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180012cf4`
- `0x180014030`

## pseudocode

```c
__int64 __fastcall CRASMapi::get_AttachedXMLFile(LPCSTR *this, unsigned __int16 **a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = ATL::CComBSTR::Copy(this + 138);
  return 0;
}

```

## disassembly

```asm
0x180014030  push    rbx
0x180014032  sub     rsp, 30h
0x180014036  mov     rbx, rdx
0x180014039  test    rdx, rdx
0x18001403c  jnz     short loc_180014045
0x18001403e  mov     eax, 80004003h
0x180014043  jmp     short loc_18001405D
0x180014045  add     rcx, 450h; this
0x18001404c  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x180014051  mov     [rbx], rax
0x180014054  xor     eax, eax
0x180014056  jmp     short loc_18001405D
0x180014058  mov     eax, 8007000Eh
0x18001405d  add     rsp, 30h
0x180014061  pop     rbx
0x180014062  retn
```
