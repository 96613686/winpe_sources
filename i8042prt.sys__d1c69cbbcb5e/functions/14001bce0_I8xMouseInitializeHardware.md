# I8xMouseInitializeHardware

- ea: `0x14001bce0`
- end: `0x14001bdc9`
- name: `I8xMouseInitializeHardware`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400198e0`
- `0x14001c068`

## callees

- `0x140004530`
- `0x1400171e8`
- `0x140019490`
- `0x14001b924`
- `0x14001bce0`
- `0x14001ce6c`

## pseudocode

```c
__int64 __fastcall I8xMouseInitializeHardware(__int64 a1, __int64 a2)
{
  int v4; // ebp
  __int64 v5; // rdx
  int v6; // ebx
  unsigned int v8; // ecx
  int v9; // [rsp+60h] [rbp+18h] BYREF
  int v10; // [rsp+68h] [rbp+20h] BYREF

  v9 = -1073741823;
  v10 = -1073741823;
  v4 = **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  v6 = I8xInitializeHardwareAtBoot(&v9, &v10);
  if ( v6 == -1073741808 )
  {
    I8xManuallyRemoveDevice(a2, v5);
    return (unsigned int)v6;
  }
  if ( v6 < 0 )
    return (unsigned int)v6;
  if ( (int)(v9 + 0x80000000) < 0 || v9 == -1073741667 )
  {
    I8xKeyboardConnectInterrupt(a1);
  }
  else if ( (v4 & 1) != 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v5,
      0x11u,
      0x10u,
      (__int64)WPP_16fba2f764b430b57540c812abbc2952_Traceguids);
  }
  v8 = v10;
  if ( ((v10 + 0x80000000) & 0x80000000) != 0 || v10 == -1073741667 )
    return (unsigned int)I8xMouseConnectInterruptAndEnable(a2, v10 != -1073741667);
  return v8;
}

```

## disassembly

```asm
0x14001bce0  mov     [rsp+arg_0], rbx
0x14001bce5  push    rbp
0x14001bce6  push    rsi
0x14001bce7  push    rdi
0x14001bce8  sub     rsp, 30h
0x14001bcec  mov     eax, 0C0000001h
0x14001bcf1  mov     rdi, rdx
0x14001bcf4  mov     [rsp+48h+arg_10], eax
0x14001bcf8  lea     rdx, [rsp+48h+arg_18]
0x14001bcfd  mov     [rsp+48h+arg_18], eax
0x14001bd01  mov     rsi, rcx
0x14001bd04  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001bd0b  lea     rcx, [rsp+48h+arg_10]
0x14001bd10  mov     ebp, [rax]
0x14001bd12  call    I8xInitializeHardwareAtBoot
0x14001bd17  mov     ebx, eax
0x14001bd19  cmp     eax, 0C0000010h
0x14001bd1e  jnz     short loc_14001BD2A
0x14001bd20  mov     rcx, rdi
0x14001bd23  call    I8xManuallyRemoveDevice
0x14001bd28  jmp     short loc_14001BD2E
0x14001bd2a  test    ebx, ebx
0x14001bd2c  jns     short loc_14001BD35
0x14001bd2e  mov     eax, ebx
0x14001bd30  jmp     loc_14001BDBB
0x14001bd35  mov     ecx, [rsp+48h+arg_10]
0x14001bd39  mov     ebx, 80000000h
0x14001bd3e  lea     eax, [rcx+rbx]
0x14001bd41  test    ebx, eax
0x14001bd43  jnz     short loc_14001BD8B
0x14001bd45  cmp     ecx, 0C000009Dh
0x14001bd4b  jz      short loc_14001BD8B
0x14001bd4d  test    bpl, 1
0x14001bd51  jz      short loc_14001BD93
0x14001bd53  lea     rax, WPP_RECORDER_INITIALIZED
0x14001bd5a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001bd61  jz      short loc_14001BD93
0x14001bd63  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bd6a  lea     rax, WPP_16fba2f764b430b57540c812abbc2952_Traceguids
0x14001bd71  mov     r9d, 10h
0x14001bd77  mov     [rsp+48h+var_28], rax
0x14001bd7c  mov     rcx, [rcx+40h]
0x14001bd80  lea     r8d, [r9+1]
0x14001bd84  call    WPP_RECORDER_SF_
0x14001bd89  jmp     short loc_14001BD93
0x14001bd8b  mov     rcx, rsi
0x14001bd8e  call    I8xKeyboardConnectInterrupt
0x14001bd93  mov     ecx, [rsp+48h+arg_18]
0x14001bd97  lea     eax, [rcx+rbx]
0x14001bd9a  test    ebx, eax
0x14001bd9c  jnz     short loc_14001BDA6
0x14001bd9e  cmp     ecx, 0C000009Dh
0x14001bda4  jnz     short loc_14001BDB9
0x14001bda6  cmp     ecx, 0C000009Dh
0x14001bdac  mov     rcx, rdi
0x14001bdaf  setnz   dl
0x14001bdb2  call    I8xMouseConnectInterruptAndEnable
0x14001bdb7  mov     ecx, eax
0x14001bdb9  mov     eax, ecx
0x14001bdbb  mov     rbx, [rsp+48h+arg_0]
0x14001bdc0  add     rsp, 30h
0x14001bdc4  pop     rdi
0x14001bdc5  pop     rsi
0x14001bdc6  pop     rbp
0x14001bdc7  retn
```
