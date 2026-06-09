# CPackage::GetUserClassID(_GUID *)

- ea: `0x1800059b0`
- end: `0x1800059be`
- name: `?GetUserClassID@CPackage@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CPackage::GetUserClassID(CPackage *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_OldPackage;
  return result;
}

```

## disassembly

```asm
0x1800059b0  movups  xmm0, xmmword ptr cs:CLSID_OldPackage.Data1
0x1800059b7  xor     eax, eax
0x1800059b9  movdqu  xmmword ptr [rdx], xmm0
0x1800059bd  retn
```
