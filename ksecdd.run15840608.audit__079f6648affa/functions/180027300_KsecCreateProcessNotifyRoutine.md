# KsecCreateProcessNotifyRoutine

- ea: `0x180027300`
- end: `0x180027323`
- name: `KsecCreateProcessNotifyRoutine`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001478`
- `0x180005cf0`
- `0x180027300`

## pseudocode

```c
void __fastcall KsecCreateProcessNotifyRoutine(struct _EPROCESS *a1, __int64 a2, __int64 a3)
{
  if ( !a3 )
  {
    KsecDisconnectRpcConnection(a1);
    KsecRemoveVmAllocations((__int64)a1);
  }
}

```

## disassembly

```asm
0x180027300  test    r8, r8
0x180027303  jz      short loc_180027307
0x180027305  retn
0x180027307  push    rbx
0x180027308  sub     rsp, 20h
0x18002730c  mov     rbx, rcx
0x18002730f  call    KsecDisconnectRpcConnection
0x180027314  mov     rcx, rbx
0x180027317  call    KsecRemoveVmAllocations
0x18002731c  add     rsp, 20h
0x180027320  pop     rbx
0x180027321  retn
```
