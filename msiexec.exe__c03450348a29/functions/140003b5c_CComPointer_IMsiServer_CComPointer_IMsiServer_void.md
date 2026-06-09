# CComPointer<IMsiServer>::~CComPointer<IMsiServer>(void)

- ea: `0x140003b5c`
- end: `0x140003b79`
- name: `??1?$CComPointer@UIMsiServer@@@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400011e4`

## callees

- `0x140003b5c`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall CComPointer<IMsiServer>::~CComPointer<IMsiServer>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x140003b5c  sub     rsp, 28h
0x140003b60  mov     rcx, [rcx]
0x140003b63  test    rcx, rcx
0x140003b66  jz      short loc_140003B74
0x140003b68  mov     rax, [rcx]
0x140003b6b  mov     rax, [rax+10h]
0x140003b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b74  add     rsp, 28h
0x140003b78  retn
```
