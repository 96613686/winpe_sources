# NfsDeleteResource

- ea: `0x18002aa74`
- end: `0x18002aaa6`
- name: `NfsDeleteResource`
- size: `50`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ef68`
- `0x18001f2d8`
- `0x18001f674`
- `0x18001f95c`
- `0x18001fae8`
- `0x18001fcdc`

## callees

- `0x180029b78`
- `0x18002aa74`

## import_xrefs

- `CLUSAPI!OfflineClusterResource` at `0x18002aa7d`
- `CLUSAPI!OfflineClusterResource` at `0x18002aa7d`
- `CLUSAPI!DeleteClusterResource` at `0x18002aa9f`

## pseudocode

```c
DWORD __fastcall NfsDeleteResource(struct _HRESOURCE *a1)
{
  if ( OfflineClusterResource(a1) == 997 )
    WaitForTargetState((int)a1, 3);
  return DeleteClusterResource(a1);
}

```

## disassembly

```asm
0x18002aa74  push    rbx
0x18002aa76  sub     rsp, 20h
0x18002aa7a  mov     rbx, rcx
0x18002aa7d  call    cs:__imp_OfflineClusterResource
0x18002aa83  cmp     eax, 3E5h
0x18002aa88  jnz     short loc_18002AA97
0x18002aa8a  mov     edx, 3
0x18002aa8f  mov     rcx, rbx
0x18002aa92  call    WaitForTargetState
0x18002aa97  mov     rcx, rbx
0x18002aa9a  add     rsp, 20h
0x18002aa9e  pop     rbx
0x18002aa9f  jmp     cs:__imp_DeleteClusterResource
```
