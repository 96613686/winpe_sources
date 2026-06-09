# CCabObj::GetClassID(_GUID *)

- ea: `0x18000b870`
- end: `0x18000b87e`
- name: `?GetClassID@CCabObj@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CCabObj *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CCabObj::GetClassID(CCabObj *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_CabViewDataObject;
  return result;
}

```

## disassembly

```asm
0x18000b870  movups  xmm0, xmmword ptr cs:CLSID_CabViewDataObject.Data1
0x18000b877  xor     eax, eax
0x18000b879  movdqu  xmmword ptr [rdx], xmm0
0x18000b87d  retn
```
