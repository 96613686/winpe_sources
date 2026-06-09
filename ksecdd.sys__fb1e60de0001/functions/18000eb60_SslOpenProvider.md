# SslOpenProvider

- ea: `0x18000eb60`
- end: `0x18000eb8b`
- name: `SslOpenProvider`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000eb60`
- `0x180010980`

## pseudocode

```c
__int64 SslOpenProvider()
{
  __int64 (*Flink)(void); // rax

  if ( WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
    && (Flink = (__int64 (*)(void))WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink[3].Flink) != 0 )
  {
    return Flink();
  }
  else
  {
    return 3221225474LL;
  }
}

```

## disassembly

```asm
0x18000eb60  sub     rsp, 28h
0x18000eb64  mov     rax, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x18000eb6b  test    rax, rax
0x18000eb6e  jz      short loc_18000EB80
0x18000eb70  mov     rax, [rax+30h]
0x18000eb74  test    rax, rax
0x18000eb77  jz      short loc_18000EB80
0x18000eb79  call    _guard_dispatch_icall
0x18000eb7e  jmp     short loc_18000EB85
0x18000eb80  mov     eax, 0C0000002h
0x18000eb85  add     rsp, 28h
0x18000eb89  retn
```
