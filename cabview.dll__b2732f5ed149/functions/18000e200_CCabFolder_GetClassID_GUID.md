# CCabFolder::GetClassID(_GUID *)

- ea: `0x18000e200`
- end: `0x18000e20e`
- name: `?GetClassID@CCabFolder@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CCabFolder *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CCabFolder::GetClassID(CCabFolder *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_CabFolder;
  return result;
}

```

## disassembly

```asm
0x18000e200  movups  xmm0, xmmword ptr cs:CLSID_CabFolder.Data1
0x18000e207  xor     eax, eax
0x18000e209  movdqu  xmmword ptr [rdx], xmm0
0x18000e20d  retn
```
