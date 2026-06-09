# std::unique_ptr<EapHost::Packet,std::default_delete<EapHost::Packet>>::~unique_ptr<EapHost::Packet,std::default_delete<EapHost::Packet>>(void)

- ea: `0x180005000`
- end: `0x18000501c`
- name: `??1?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006ec0`
- `0x180014050`
- `0x180028f50`
- `0x18002a2fc`
- `0x18002a7f0`
- `0x180034cd4`
- `0x180035af1`
- `0x180036743`
- `0x1800381f2`
- `0x180038243`

## callees

- `0x180002b14`
- `0x180005000`

## pseudocode

```c
void __fastcall std::unique_ptr<EapHost::Packet>::~unique_ptr<EapHost::Packet>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x180005000  sub     rsp, 28h
0x180005004  mov     rcx, [rcx]; void *
0x180005007  test    rcx, rcx
0x18000500a  jz      short loc_180005016
0x18000500c  mov     edx, 5; unsigned __int64
0x180005011  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005016  add     rsp, 28h
0x18000501a  retn
```
