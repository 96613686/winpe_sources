# MRxSmbCoreOpen

- ea: `0x14003a394`
- end: `0x14003a48d`
- name: `MRxSmbCoreOpen`
- size: `249`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14003a5f0`

## callees

- `0x14000dc44`
- `0x14000ebd8`
- `0x14003a394`
- `0x140045d50`
- `0x140046380`
- `0x14004a590`

## pseudocode

```c
__int64 __fastcall MRxSmbCoreOpen(unsigned __int8 *pContext, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned int started; // ebx
  __int64 v10; // [rsp+20h] [rbp-78h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids, pContext);
  started = MRxSmbStartSMBCommand((__int64)(pContext + 888), 1, 2, 7, v10, 0x10000u);
  if ( !started )
  {
    MRxSmbStuffSMB((__int64)(pContext + 888), (__int64)"0wwB4!", a3, a4);
    started = SmbPseOrdinaryExchange(pContext, a2, 2);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      18,
      WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids,
      pContext,
      started);
  return started;
}

```

## disassembly

```asm
0x14003a394  push    rbx
0x14003a396  push    rbp
0x14003a397  push    rsi
0x14003a398  push    rdi
0x14003a399  push    r13
0x14003a39b  push    r14
0x14003a39d  push    r15
0x14003a39f  sub     rsp, 60h
0x14003a3a3  mov     r13, [rdx+38h]
0x14003a3a7  mov     r14d, r9d
0x14003a3aa  mov     r15d, r8d
0x14003a3ad  mov     rbp, rdx
0x14003a3b0  mov     rdi, rcx
0x14003a3b3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a3ba  lea     rax, WPP_GLOBAL_Control
0x14003a3c1  cmp     rcx, rax
0x14003a3c4  jz      short loc_14003A3E7
0x14003a3c6  test    dword ptr [rcx+2Ch], 400h
0x14003a3cd  jz      short loc_14003A3E7
0x14003a3cf  mov     rcx, [rcx+18h]
0x14003a3d3  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003a3da  mov     edx, 11h
0x14003a3df  mov     r9, rdi
0x14003a3e2  call    WPP_SF_q
0x14003a3e7  mov     r9d, 7
0x14003a3ed  mov     [rsp+98h+var_70], 10000h
0x14003a3f5  lea     rsi, [rdi+378h]
0x14003a3fc  mov     r8b, 2
0x14003a3ff  mov     rcx, rsi
0x14003a402  lea     edx, [r9-6]
0x14003a406  call    MRxSmbStartSMBCommand
0x14003a40b  mov     ebx, eax
0x14003a40d  test    eax, eax
0x14003a40f  jnz     short loc_14003A443
0x14003a411  lea     rax, [r13+168h]
0x14003a418  mov     r9d, r14d
0x14003a41b  mov     r8d, r15d
0x14003a41e  mov     [rsp+98h+var_78], rax
0x14003a423  lea     rdx, a0wwb4; "0wwB4!"
0x14003a42a  mov     rcx, rsi
0x14003a42d  call    MRxSmbStuffSMB
0x14003a432  lea     r8d, [rbx+2]
0x14003a436  mov     rdx, rbp
0x14003a439  mov     rcx, rdi; pContext
0x14003a43c  call    SmbPseOrdinaryExchange
0x14003a441  mov     ebx, eax
0x14003a443  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a44a  lea     rax, WPP_GLOBAL_Control
0x14003a451  cmp     rcx, rax
0x14003a454  jz      short loc_14003A47B
0x14003a456  test    dword ptr [rcx+2Ch], 400h
0x14003a45d  jz      short loc_14003A47B
0x14003a45f  mov     rcx, [rcx+18h]
0x14003a463  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003a46a  mov     edx, 12h
0x14003a46f  mov     dword ptr [rsp+98h+var_78], ebx
0x14003a473  mov     r9, rdi
0x14003a476  call    WPP_SF_qD
0x14003a47b  mov     eax, ebx
0x14003a47d  add     rsp, 60h
0x14003a481  pop     r15
0x14003a483  pop     r14
0x14003a485  pop     r13
0x14003a487  pop     rdi
0x14003a488  pop     rsi
0x14003a489  pop     rbp
0x14003a48a  pop     rbx
0x14003a48b  retn
```
