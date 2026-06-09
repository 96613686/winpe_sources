# KsecCreateProcessNotifyRoutine

- ea: `0x1800272b0`
- end: `0x1800272d3`
- name: `KsecCreateProcessNotifyRoutine`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001478`
- `0x180005cf0`
- `0x1800272b0`

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
0x1800272b0  test    r8, r8
0x1800272b3  jz      short loc_1800272B7
0x1800272b5  retn
0x1800272b7  push    rbx
0x1800272b8  sub     rsp, 20h
0x1800272bc  mov     rbx, rcx
0x1800272bf  call    KsecDisconnectRpcConnection
0x1800272c4  mov     rcx, rbx
0x1800272c7  call    KsecRemoveVmAllocations
0x1800272cc  add     rsp, 20h
0x1800272d0  pop     rbx
0x1800272d1  retn
```
