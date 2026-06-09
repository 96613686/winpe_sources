# PROTOCOL::NotifyError(long)

- ea: `0x180003560`
- end: `0x180003583`
- name: `?NotifyError@PROTOCOL@@UEAAXJ@Z`
- size: `35`
- prototype: `void __fastcall(PROTOCOL *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006480`

## pseudocode

```c
void __fastcall PROTOCOL::NotifyError(APPLICATION **this, int a2)
{
  APPLICATION::RealShutdown(this[19], a2, 0, 0, 1);
}

```

## disassembly

```asm
0x180003560  sub     rsp, 38h
0x180003564  mov     rcx, [rcx+98h]; this
0x18000356b  xor     r9d, r9d; int
0x18000356e  xor     r8d, r8d; unsigned int
0x180003571  mov     [rsp+38h+var_18], 1; int
0x180003579  call    ?RealShutdown@APPLICATION@@QEAAXJIHH@Z; APPLICATION::RealShutdown(long,uint,int,int)
0x18000357e  add     rsp, 38h
0x180003582  retn
```
