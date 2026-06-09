# McTemplateU0qq_EtwEventWriteTransfer

- ea: `0x180001d8c`
- end: `0x180001df7`
- name: `McTemplateU0qq_EtwEventWriteTransfer`
- size: `107`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `33`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ed4`
- `0x180002328`
- `0x1800027e0`
- `0x1800034c8`
- `0x180003a20`
- `0x180003cc0`
- `0x180006ed8`
- `0x180009a70`
- `0x18000c7dc`
- `0x180010340`
- `0x180010fd4`
- `0x1800132c0`
- `0x180013410`
- `0x180013700`
- `0x180013a00`
- `0x180013b6c`
- `0x1800170cc`
- `0x18001b314`
- `0x18001be30`
- `0x18001c0e4`
- `0x18001f630`
- `0x18001f77c`
- `0x18001fc58`
- `0x1800200d8`
- `0x180020940`
- `0x18002211c`
- `0x1800225c8`
- `0x180022b80`
- `0x180023344`
- `0x180023c2c`
- `0x180023dc0`
- `0x18002458c`
- `0x180025094`

## callees

- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0qq_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  _QWORD v5[6]; // [rsp+30h] [rbp-48h] BYREF
  int v6; // [rsp+90h] [rbp+18h] BYREF
  int v7; // [rsp+98h] [rbp+20h] BYREF

  v7 = a4;
  v6 = a3;
  v5[3] = 4;
  v5[2] = &v6;
  v5[5] = 4;
  v5[4] = &v7;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, a2, a3, 3, (__int64)v5);
}

```

## disassembly

```asm
0x180001d8c  mov     r11, rsp
0x180001d8f  mov     [r11+20h], r9d
0x180001d93  mov     [r11+18h], r8d
0x180001d97  sub     rsp, 78h
0x180001d9b  mov     rax, cs:__security_cookie
0x180001da2  xor     rax, rsp
0x180001da5  mov     [rsp+78h+var_18], rax
0x180001daa  lea     rax, [r11+18h]
0x180001dae  mov     qword ptr [r11-30h], 4
0x180001db6  mov     [r11-38h], rax
0x180001dba  lea     rcx, Dhcpv6_Context
0x180001dc1  lea     rax, [r11+20h]
0x180001dc5  mov     qword ptr [r11-20h], 4
0x180001dcd  mov     [r11-28h], rax
0x180001dd1  mov     r9d, 3
0x180001dd7  lea     rax, [r11-48h]
0x180001ddb  mov     [r11-58h], rax
0x180001ddf  call    McGenEventWrite_EtwEventWriteTransfer
0x180001de4  mov     rcx, [rsp+78h+var_18]
0x180001de9  xor     rcx, rsp; StackCookie
0x180001dec  call    __security_check_cookie
0x180001df1  add     rsp, 78h
0x180001df5  retn
```
