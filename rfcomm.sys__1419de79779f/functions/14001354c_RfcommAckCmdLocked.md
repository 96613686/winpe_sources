# RfcommAckCmdLocked

- ea: `0x14001354c`
- end: `0x1400135c4`
- name: `RfcommAckCmdLocked`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fd78`
- `0x140013d20`
- `0x140013fb4`
- `0x1400161d0`

## callees

- `0x140013400`
- `0x14001354c`
- `0x1400171e0`

## pseudocode

```c
__int64 __fastcall RfcommAckCmdLocked(char a1, __int64 *a2, volatile __int32 *a3)
{
  __int64 result; // rax
  __int64 v4; // rax
  char v5; // r9
  __int64 v6; // rcx
  __int64 v7; // rdx
  int v8; // edx

  result = *a2;
  if ( *a2 )
  {
    if ( !a1 || *(_BYTE *)(result + 140) == a1 )
    {
      *a2 = 0;
      _InterlockedExchange(a3, 0);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v4 = ((__int64 (*)(void))MsgToString)();
        LOBYTE(v6) = v5;
        MsgToString(v6, v7, v4);
        WPP_RECORDER_SF_ss(WPP_GLOBAL_Control->DeviceExtension, v8, 2, 41);
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001354c  sub     rsp, 48h
0x140013550  mov     rax, [rdx]
0x140013553  mov     r9b, cl
0x140013556  test    rax, rax
0x140013559  jz      short loc_1400135BE
0x14001355b  test    cl, cl
0x14001355d  jz      short loc_1400135B2
0x14001355f  mov     cl, [rax+8Ch]
0x140013565  cmp     cl, r9b
0x140013568  jz      short loc_1400135B2
0x14001356a  lea     rax, WPP_RECORDER_INITIALIZED
0x140013571  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013578  jz      short loc_1400135AE
0x14001357a  call    MsgToString
0x14001357f  mov     cl, r9b
0x140013582  mov     r8, rax
0x140013585  call    MsgToString
0x14001358a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013591  mov     r9d, 29h ; ')'
0x140013597  mov     [rsp+48h+var_18], r8
0x14001359c  mov     [rsp+48h+var_20], rax
0x1400135a1  mov     rcx, [rcx+40h]
0x1400135a5  lea     r8d, [r9-27h]
0x1400135a9  call    WPP_RECORDER_SF_ss
0x1400135ae  xor     eax, eax
0x1400135b0  jmp     short loc_1400135BE
0x1400135b2  xor     ecx, ecx
0x1400135b4  mov     qword ptr [rdx], 0
0x1400135bb  xchg    ecx, [r8]
0x1400135be  add     rsp, 48h
0x1400135c2  retn
```
