# CPackage::GetClassID(_GUID *)

- ea: `0x1800067e0`
- end: `0x1800067f9`
- name: `?GetClassID@CPackage@@UEAAJPEAU_GUID@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800085f0`

## callees

- `0x1800067e0`

## pseudocode

```c
__int64 __fastcall CPackage::GetClassID(CPackage *this, struct _GUID *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147942487LL;
  result = 0;
  *a2 = CLSID_OldPackage;
  return result;
}

```

## disassembly

```asm
0x1800067e0  test    rdx, rdx
0x1800067e3  jnz     short loc_1800067EB
0x1800067e5  mov     eax, 80070057h
0x1800067ea  retn
0x1800067eb  movups  xmm0, xmmword ptr cs:CLSID_OldPackage.Data1
0x1800067f2  xor     eax, eax
0x1800067f4  movdqu  xmmword ptr [rdx], xmm0
0x1800067f8  retn
```
