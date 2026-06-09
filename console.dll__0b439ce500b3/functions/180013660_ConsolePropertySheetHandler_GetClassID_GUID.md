# ConsolePropertySheetHandler::GetClassID(_GUID *)

- ea: `0x180013660`
- end: `0x18001366e`
- name: `?GetClassID@ConsolePropertySheetHandler@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(ConsolePropertySheetHandler *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting`

## pseudocode

```c
__int64 __fastcall ConsolePropertySheetHandler::GetClassID(ConsolePropertySheetHandler *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = GUID_d2942f8e_478e_41d3_870a_35a16238f4ee;
  return result;
}

```

## disassembly

```asm
0x180013660  movups  xmm0, xmmword ptr cs:_GUID_d2942f8e_478e_41d3_870a_35a16238f4ee.Data1
0x180013667  xor     eax, eax
0x180013669  movdqu  xmmword ptr [rdx], xmm0
0x18001366d  retn
```
