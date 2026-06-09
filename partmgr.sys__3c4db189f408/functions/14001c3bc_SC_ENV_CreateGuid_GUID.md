# SC_ENV::CreateGuid(_GUID *)

- ea: `0x14001c3bc`
- end: `0x14001c3d2`
- name: `?CreateGuid@SC_ENV@@SAJPEAU_GUID@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140009880`
- `0x14000e904`
- `0x14000f7f8`
- `0x14000fc84`
- `0x140010380`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14001c3c0`
- `ntoskrnl!ExUuidCreate` at `0x14001c3c0`

## pseudocode

```c
NTSTATUS __fastcall SC_ENV::CreateGuid(struct _GUID *a1)
{
  return ExUuidCreate(a1);
}

```

## disassembly

```asm
0x14001c3bc  sub     rsp, 28h
0x14001c3c0  call    cs:__imp_ExUuidCreate
0x14001c3c7  nop     dword ptr [rax+rax+00h]
0x14001c3cc  add     rsp, 28h
0x14001c3d0  retn
```
