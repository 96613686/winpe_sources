# I8xPutControllerCommand

- ea: `0x140005de0`
- end: `0x140005e88`
- name: `I8xPutControllerCommand`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005560`

## callees

- `0x140004530`
- `0x1400059c0`
- `0x140005de0`

## pseudocode

```c
__int64 __fastcall I8xPutControllerCommand(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  unsigned __int8 v4; // bl
  __int64 result; // rax
  int v6; // edx
  __int64 v7; // r8

  v4 = a1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      19,
      71,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  LOBYTE(a4) = 96;
  LOBYTE(a3) = 3;
  LOBYTE(a1) = 1;
  result = I8xPutBytePolled(a1, 0, a3, a4);
  if ( (int)result >= 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        19,
        72,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
    LOBYTE(v7) = 3;
    return I8xPutBytePolled(0, 0, v7, v4);
  }
  return result;
}

```

## disassembly

```asm
0x140005de0  mov     [rsp+arg_0], rbx
0x140005de5  mov     [rsp+arg_8], rsi
0x140005dea  push    rdi
0x140005deb  sub     rsp, 30h
0x140005def  movzx   ebx, cl
0x140005df2  lea     rdi, WPP_RECORDER_INITIALIZED
0x140005df9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140005e00  lea     rsi, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140005e07  jz      short loc_140005E2A
0x140005e09  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e10  mov     r9d, 47h ; 'G'
0x140005e16  mov     r8d, 13h
0x140005e1c  mov     [rsp+38h+var_18], rsi
0x140005e21  mov     rcx, [rcx+40h]
0x140005e25  call    WPP_RECORDER_SF_
0x140005e2a  mov     r9b, 60h ; '`'
0x140005e2d  mov     r8b, 3
0x140005e30  xor     edx, edx
0x140005e32  mov     cl, 1
0x140005e34  call    I8xPutBytePolled
0x140005e39  test    eax, eax
0x140005e3b  js      short loc_140005E77
0x140005e3d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140005e44  jz      short loc_140005E67
0x140005e46  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e4d  mov     r9d, 48h ; 'H'
0x140005e53  mov     r8d, 13h
0x140005e59  mov     [rsp+38h+var_18], rsi
0x140005e5e  mov     rcx, [rcx+40h]
0x140005e62  call    WPP_RECORDER_SF_
0x140005e67  movzx   r9d, bl
0x140005e6b  mov     r8b, 3
0x140005e6e  xor     edx, edx
0x140005e70  xor     ecx, ecx
0x140005e72  call    I8xPutBytePolled
0x140005e77  mov     rbx, [rsp+38h+arg_0]
0x140005e7c  mov     rsi, [rsp+38h+arg_8]
0x140005e81  add     rsp, 30h
0x140005e85  pop     rdi
0x140005e86  retn
```
