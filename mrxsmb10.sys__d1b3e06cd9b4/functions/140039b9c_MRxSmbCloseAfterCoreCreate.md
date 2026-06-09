# MRxSmbCloseAfterCoreCreate

- ea: `0x140039b9c`
- end: `0x140039c7d`
- name: `MRxSmbCloseAfterCoreCreate`
- size: `225`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14003a5f0`

## callees

- `0x14000dc44`
- `0x14000ebd8`
- `0x140039b9c`
- `0x140045d50`
- `0x140046380`
- `0x14004a590`

## pseudocode

```c
__int64 __fastcall MRxSmbCloseAfterCoreCreate(unsigned __int8 *pContext, __int64 a2)
{
  unsigned int started; // ebx
  __int64 v6; // [rsp+20h] [rbp-68h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids, pContext);
  started = MRxSmbStartSMBCommand((__int64)(pContext + 888), 1, 4, 9, v6, 0x10000u);
  if ( !started )
  {
    MRxSmbStuffSMB((__int64)(pContext + 888), (__int64)"0wdB!", *((unsigned int *)pContext + 142), 0);
    started = SmbPseOrdinaryExchange(pContext, a2, 12);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids,
      pContext,
      started);
  return started;
}

```

## disassembly

```asm
0x140039b9c  push    rbx
0x140039b9e  push    rbp
0x140039b9f  push    rsi
0x140039ba0  push    rdi
0x140039ba1  push    r15
0x140039ba3  sub     rsp, 60h
0x140039ba7  mov     rbp, rdx
0x140039baa  mov     rdi, rcx
0x140039bad  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140039bb4  lea     r15, WPP_GLOBAL_Control
0x140039bbb  cmp     rcx, r15
0x140039bbe  jz      short loc_140039BE1
0x140039bc0  test    dword ptr [rcx+2Ch], 400h
0x140039bc7  jz      short loc_140039BE1
0x140039bc9  mov     rcx, [rcx+18h]
0x140039bcd  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x140039bd4  mov     edx, 19h
0x140039bd9  mov     r9, rdi
0x140039bdc  call    WPP_SF_q
0x140039be1  mov     r9d, 9
0x140039be7  mov     [rsp+88h+var_60], 10000h
0x140039bef  lea     rsi, [rdi+378h]
0x140039bf6  mov     r8b, 4
0x140039bf9  mov     rcx, rsi
0x140039bfc  lea     edx, [r9-8]
0x140039c00  call    MRxSmbStartSMBCommand
0x140039c05  mov     ebx, eax
0x140039c07  test    eax, eax
0x140039c09  jnz     short loc_140039C3E
0x140039c0b  mov     r8d, [rdi+238h]
0x140039c12  lea     rdx, a0wdb; "0wdB!"
0x140039c19  xor     r9d, r9d
0x140039c1c  mov     [rsp+88h+var_68], 0
0x140039c25  mov     rcx, rsi
0x140039c28  call    MRxSmbStuffSMB
0x140039c2d  lea     r8d, [rbx+0Ch]
0x140039c31  mov     rdx, rbp
0x140039c34  mov     rcx, rdi; pContext
0x140039c37  call    SmbPseOrdinaryExchange
0x140039c3c  mov     ebx, eax
0x140039c3e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140039c45  cmp     rcx, r15
0x140039c48  jz      short loc_140039C6F
0x140039c4a  test    dword ptr [rcx+2Ch], 400h
0x140039c51  jz      short loc_140039C6F
0x140039c53  mov     rcx, [rcx+18h]
0x140039c57  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x140039c5e  mov     edx, 1Ah
0x140039c63  mov     dword ptr [rsp+88h+var_68], ebx
0x140039c67  mov     r9, rdi
0x140039c6a  call    WPP_SF_qD
0x140039c6f  mov     eax, ebx
0x140039c71  add     rsp, 60h
0x140039c75  pop     r15
0x140039c77  pop     rdi
0x140039c78  pop     rsi
0x140039c79  pop     rbp
0x140039c7a  pop     rbx
0x140039c7b  retn
```
