# std::unique_ptr<EapHost::Packet,std::default_delete<EapHost::Packet>>::~unique_ptr<EapHost::Packet,std::default_delete<EapHost::Packet>>(void)

- ea: `0x180004ec0`
- end: `0x180004edb`
- name: `??1?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@QEAA@XZ`
- size: `27`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006c30`
- `0x180013860`
- `0x180028168`
- `0x1800294c8`
- `0x1800299a0`
- `0x18003391c`
- `0x180034731`
- `0x18003538b`
- `0x180036e20`
- `0x180036e70`

## callees

- `0x180002ab4`
- `0x180004ec0`

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
0x180004ec0  sub     rsp, 28h
0x180004ec4  mov     rcx, [rcx]; void *
0x180004ec7  test    rcx, rcx
0x180004eca  jz      short loc_180004ED6
0x180004ecc  mov     edx, 5; unsigned __int64
0x180004ed1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004ed6  add     rsp, 28h
0x180004eda  retn
```
