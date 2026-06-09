# SslGetExtensions

- ea: `0x18000ea50`
- end: `0x18000ea9b`
- name: `SslGetExtensions`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000ea50`
- `0x180010920`

## pseudocode

```c
__int64 __fastcall SslGetExtensions(__int64 a1, __int64 a2, __int64 a3)
{
  struct _LIST_ENTRY *Flink; // rax

  if ( WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink
    && (Flink = WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink[4].Flink) != 0 )
  {
    return ((__int64 (__fastcall *)(__int64, __int64, __int64))Flink)(a1, a2, a3);
  }
  else
  {
    return 3221225474LL;
  }
}

```

## disassembly

```asm
0x18000ea50  sub     rsp, 48h
0x18000ea54  mov     rax, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink
0x18000ea5b  mov     r10, r8
0x18000ea5e  mov     r11, rcx
0x18000ea61  test    rax, rax
0x18000ea64  jz      short loc_18000EA90
0x18000ea66  mov     rax, [rax+40h]
0x18000ea6a  test    rax, rax
0x18000ea6d  jz      short loc_18000EA90
0x18000ea6f  mov     r8d, [rsp+48h+arg_28]
0x18000ea74  mov     rcx, [rsp+48h+arg_20]
0x18000ea79  mov     [rsp+48h+var_20], r8d
0x18000ea7e  mov     r8, r10
0x18000ea81  mov     [rsp+48h+var_28], rcx
0x18000ea86  mov     rcx, r11
0x18000ea89  call    _guard_dispatch_icall
0x18000ea8e  jmp     short loc_18000EA95
0x18000ea90  mov     eax, 0C0000002h
0x18000ea95  add     rsp, 48h
0x18000ea99  retn
```
