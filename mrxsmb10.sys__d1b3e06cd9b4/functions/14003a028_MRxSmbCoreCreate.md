# MRxSmbCoreCreate

- ea: `0x14003a028`
- end: `0x14003a117`
- name: `MRxSmbCoreCreate`
- size: `239`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14003a5f0`

## callees

- `0x14000dc44`
- `0x14000ebd8`
- `0x14003a028`
- `0x140045d50`
- `0x140046380`
- `0x14004a590`

## pseudocode

```c
__int64 __fastcall MRxSmbCoreCreate(unsigned __int8 *pContext, __int64 a2, unsigned int a3)
{
  unsigned int started; // ebx
  __int64 v8; // [rsp+20h] [rbp-78h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids, pContext);
  started = MRxSmbStartSMBCommand((__int64)(pContext + 888), 1, 15, 9, v8, 0x10000u);
  if ( !started )
  {
    MRxSmbStuffSMB((__int64)(pContext + 888), (__int64)"0wdB4!", a3, 0);
    started = SmbPseOrdinaryExchange(pContext, a2, 21);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      24,
      WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids,
      pContext,
      started);
  return started;
}

```

## disassembly

```asm
0x14003a028  push    rbx
0x14003a02a  push    rbp
0x14003a02b  push    rsi
0x14003a02c  push    rdi
0x14003a02d  push    r13
0x14003a02f  push    r14
0x14003a031  push    r15
0x14003a033  sub     rsp, 60h
0x14003a037  mov     r15, [rdx+38h]
0x14003a03b  mov     r14d, r8d
0x14003a03e  mov     rbp, rdx
0x14003a041  mov     rdi, rcx
0x14003a044  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a04b  lea     r13, WPP_GLOBAL_Control
0x14003a052  cmp     rcx, r13
0x14003a055  jz      short loc_14003A078
0x14003a057  test    dword ptr [rcx+2Ch], 400h
0x14003a05e  jz      short loc_14003A078
0x14003a060  mov     rcx, [rcx+18h]
0x14003a064  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003a06b  mov     edx, 17h
0x14003a070  mov     r9, rdi
0x14003a073  call    WPP_SF_q
0x14003a078  mov     r9d, 9
0x14003a07e  mov     [rsp+98h+var_70], 10000h
0x14003a086  lea     rsi, [rdi+378h]
0x14003a08d  mov     r8b, 0Fh
0x14003a090  mov     rcx, rsi
0x14003a093  lea     edx, [r9-8]
0x14003a097  call    MRxSmbStartSMBCommand
0x14003a09c  mov     ebx, eax
0x14003a09e  test    eax, eax
0x14003a0a0  jnz     short loc_14003A0D4
0x14003a0a2  lea     rax, [r15+168h]
0x14003a0a9  xor     r9d, r9d
0x14003a0ac  mov     r8d, r14d
0x14003a0af  mov     [rsp+98h+var_78], rax
0x14003a0b4  lea     rdx, a0wdb4; "0wdB4!"
0x14003a0bb  mov     rcx, rsi
0x14003a0be  call    MRxSmbStuffSMB
0x14003a0c3  lea     r8d, [rbx+15h]
0x14003a0c7  mov     rdx, rbp
0x14003a0ca  mov     rcx, rdi; pContext
0x14003a0cd  call    SmbPseOrdinaryExchange
0x14003a0d2  mov     ebx, eax
0x14003a0d4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a0db  cmp     rcx, r13
0x14003a0de  jz      short loc_14003A105
0x14003a0e0  test    dword ptr [rcx+2Ch], 400h
0x14003a0e7  jz      short loc_14003A105
0x14003a0e9  mov     rcx, [rcx+18h]
0x14003a0ed  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003a0f4  mov     edx, 18h
0x14003a0f9  mov     dword ptr [rsp+98h+var_78], ebx
0x14003a0fd  mov     r9, rdi
0x14003a100  call    WPP_SF_qD
0x14003a105  mov     eax, ebx
0x14003a107  add     rsp, 60h
0x14003a10b  pop     r15
0x14003a10d  pop     r14
0x14003a10f  pop     r13
0x14003a111  pop     rdi
0x14003a112  pop     rsi
0x14003a113  pop     rbp
0x14003a114  pop     rbx
0x14003a115  retn
```
