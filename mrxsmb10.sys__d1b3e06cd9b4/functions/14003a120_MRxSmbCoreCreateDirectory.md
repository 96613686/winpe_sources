# MRxSmbCoreCreateDirectory

- ea: `0x14003a120`
- end: `0x14003a1fd`
- name: `MRxSmbCoreCreateDirectory`
- size: `221`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14003a5f0`

## callees

- `0x14000dc44`
- `0x14000ebd8`
- `0x14003a120`
- `0x140045d50`
- `0x140046380`
- `0x14004a590`

## pseudocode

```c
__int64 __fastcall MRxSmbCoreCreateDirectory(unsigned __int8 *pContext, __int64 a2)
{
  __int64 v2; // r14
  unsigned int started; // ebx
  __int64 v6; // r9
  __int64 v8; // [rsp+20h] [rbp-78h]

  v2 = *(_QWORD *)(a2 + 56);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids, pContext);
  started = MRxSmbStartSMBCommand((__int64)(pContext + 888), 1, 0, 3, v8, 0x10000u);
  if ( !started )
  {
    MRxSmbStuffSMB((__int64)(pContext + 888), (__int64)"0B4!", v2 + 360, v6);
    started = SmbPseOrdinaryExchange(pContext, a2, 24);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids,
      pContext,
      started);
  return started;
}

```

## disassembly

```asm
0x14003a120  push    rbx
0x14003a122  push    rbp
0x14003a123  push    rsi
0x14003a124  push    rdi
0x14003a125  push    r12
0x14003a127  push    r14
0x14003a129  sub     rsp, 68h
0x14003a12d  mov     r14, [rdx+38h]
0x14003a131  mov     rsi, rdx
0x14003a134  mov     rdi, rcx
0x14003a137  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a13e  lea     r12, WPP_GLOBAL_Control
0x14003a145  cmp     rcx, r12
0x14003a148  jz      short loc_14003A16B
0x14003a14a  test    dword ptr [rcx+2Ch], 400h
0x14003a151  jz      short loc_14003A16B
0x14003a153  mov     rcx, [rcx+18h]
0x14003a157  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003a15e  mov     edx, 15h
0x14003a163  mov     r9, rdi
0x14003a166  call    WPP_SF_q
0x14003a16b  mov     r9d, 3
0x14003a171  mov     [rsp+98h+var_70], 10000h
0x14003a179  lea     rbp, [rdi+378h]
0x14003a180  xor     r8d, r8d
0x14003a183  mov     rcx, rbp
0x14003a186  lea     edx, [r9-2]
0x14003a18a  call    MRxSmbStartSMBCommand
0x14003a18f  mov     ebx, eax
0x14003a191  test    eax, eax
0x14003a193  jnz     short loc_14003A1BC
0x14003a195  lea     r8, [r14+168h]
0x14003a19c  mov     rcx, rbp
0x14003a19f  lea     rdx, a0b4; "0B4!"
0x14003a1a6  call    MRxSmbStuffSMB
0x14003a1ab  lea     r8d, [rbx+18h]
0x14003a1af  mov     rdx, rsi
0x14003a1b2  mov     rcx, rdi; pContext
0x14003a1b5  call    SmbPseOrdinaryExchange
0x14003a1ba  mov     ebx, eax
0x14003a1bc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a1c3  cmp     rcx, r12
0x14003a1c6  jz      short loc_14003A1ED
0x14003a1c8  test    dword ptr [rcx+2Ch], 400h
0x14003a1cf  jz      short loc_14003A1ED
0x14003a1d1  mov     rcx, [rcx+18h]
0x14003a1d5  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003a1dc  mov     edx, 16h
0x14003a1e1  mov     dword ptr [rsp+98h+var_78], ebx
0x14003a1e5  mov     r9, rdi
0x14003a1e8  call    WPP_SF_qD
0x14003a1ed  mov     eax, ebx
0x14003a1ef  add     rsp, 68h
0x14003a1f3  pop     r14
0x14003a1f5  pop     r12
0x14003a1f7  pop     rdi
0x14003a1f8  pop     rsi
0x14003a1f9  pop     rbp
0x14003a1fa  pop     rbx
0x14003a1fb  retn
```
