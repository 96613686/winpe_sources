# McGenEventRegister_EtwRegister

- ea: `0x1400016c0`
- end: `0x1400016eb`
- name: `McGenEventRegister_EtwRegister`
- size: `43`
- prototype: `NTSTATUS __fastcall(const GUID *, __int64, void *, ULONGLONG *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b080`

## callees

- `0x1400016c0`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x1400016d9`
- `ntoskrnl!EtwRegister` at `0x1400016d9`

## pseudocode

```c
NTSTATUS __fastcall McGenEventRegister_EtwRegister(const GUID *a1, __int64 a2, void *a3, ULONGLONG *a4)
{
  if ( *a4 )
    return 0;
  else
    return EtwRegister(a1, McGenControlCallbackV2, a3, a4);
}

```

## disassembly

```asm
0x1400016c0  sub     rsp, 28h
0x1400016c4  cmp     qword ptr [r9], 0
0x1400016c8  jz      short loc_1400016D2
0x1400016ca  xor     eax, eax
0x1400016cc  add     rsp, 28h
0x1400016d0  retn
0x1400016d2  lea     rdx, McGenControlCallbackV2; EnableCallback
0x1400016d9  call    cs:__imp_EtwRegister
0x1400016e0  nop     dword ptr [rax+rax+00h]
0x1400016e5  add     rsp, 28h
0x1400016e9  retn
```
