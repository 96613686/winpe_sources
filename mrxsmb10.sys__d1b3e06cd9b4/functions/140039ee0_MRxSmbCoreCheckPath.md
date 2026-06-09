# MRxSmbCoreCheckPath

- ea: `0x140039ee0`
- end: `0x14003a022`
- name: `MRxSmbCoreCheckPath`
- size: `322`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14000dc44`
- `0x14000ebd8`
- `0x140039ee0`
- `0x140045d50`
- `0x140046380`
- `0x14004a590`
- `0x14004f390`

## pseudocode

```c
__int64 __fastcall MRxSmbCoreCheckPath(unsigned __int8 *pContext, __int64 a2)
{
  unsigned int started; // ebx
  __int64 v5; // r9
  __int64 v7; // [rsp+20h] [rbp-88h]
  struct _LIST_ENTRY v8[2]; // [rsp+60h] [rbp-48h] BYREF
  __int64 v9; // [rsp+80h] [rbp-28h]
  unsigned int v10; // [rsp+B0h] [rbp+8h] BYREF

  v10 = 0;
  memset(v8, 0, sizeof(v8));
  v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids, pContext);
  if ( !(unsigned __int8)MRxSmbIsBasicFileInfoCacheFound(a2, v8, &v10, *((__int16 **)pContext + 108))
    || (started = v10) != 0 )
  {
    started = MRxSmbStartSMBCommand((__int64)(pContext + 888), 1, 16, 3, v7, 0x10000u);
    if ( !started )
    {
      MRxSmbStuffSMB((__int64)(pContext + 888), (__int64)"0B4!", *((_QWORD *)pContext + 108), v5);
      started = SmbPseOrdinaryExchange(pContext, a2, 25);
    }
  }
  else if ( (v9 & 0x10) == 0 )
  {
    started = -1073741565;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids,
      pContext,
      started);
  return started;
}

```

## disassembly

```asm
0x140039ee0  mov     r11, rsp
0x140039ee3  mov     [r11+10h], rbx
0x140039ee7  mov     [r11+18h], rbp
0x140039eeb  push    rsi
0x140039eec  push    rdi
0x140039eed  push    r15
0x140039eef  sub     rsp, 90h
0x140039ef6  xorps   xmm0, xmm0
0x140039ef9  mov     dword ptr [r11+8], 0
0x140039f01  xor     eax, eax
0x140039f03  mov     rsi, rdx
0x140039f06  movups  [rsp+0A8h+var_48], xmm0
0x140039f0b  mov     rdi, rcx
0x140039f0e  movups  [rsp+0A8h+var_38], xmm0
0x140039f13  mov     [r11-28h], rax
0x140039f17  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140039f1e  lea     r15, WPP_GLOBAL_Control
0x140039f25  cmp     rcx, r15
0x140039f28  jz      short loc_140039F49
0x140039f2a  test    dword ptr [rcx+2Ch], 400h
0x140039f31  jz      short loc_140039F49
0x140039f33  mov     rcx, [rcx+18h]
0x140039f37  lea     edx, [rax+0Fh]
0x140039f3a  mov     r9, rdi
0x140039f3d  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x140039f44  call    WPP_SF_q
0x140039f49  mov     r9, [rdi+360h]
0x140039f50  lea     r8, [rsp+0A8h+arg_0]
0x140039f58  lea     rdx, [rsp+0A8h+var_48]
0x140039f5d  mov     rcx, rsi
0x140039f60  call    MRxSmbIsBasicFileInfoCacheFound
0x140039f65  test    al, al
0x140039f67  jz      short loc_140039F85
0x140039f69  mov     ebx, [rsp+0A8h+arg_0]
0x140039f70  test    ebx, ebx
0x140039f72  jnz     short loc_140039F85
0x140039f74  test    byte ptr [rsp+0A8h+var_28], 10h
0x140039f7c  jnz     short loc_140039FD6
0x140039f7e  mov     ebx, 0C0000103h
0x140039f83  jmp     short loc_140039FD6
0x140039f85  mov     r9d, 3
0x140039f8b  mov     [rsp+0A8h+var_80], 10000h
0x140039f93  lea     rbp, [rdi+378h]
0x140039f9a  mov     r8b, 10h
0x140039f9d  mov     rcx, rbp
0x140039fa0  lea     edx, [r9-2]
0x140039fa4  call    MRxSmbStartSMBCommand
0x140039fa9  mov     ebx, eax
0x140039fab  test    eax, eax
0x140039fad  jnz     short loc_140039FD6
0x140039faf  mov     r8, [rdi+360h]
0x140039fb6  lea     rdx, a0b4; "0B4!"
0x140039fbd  mov     rcx, rbp
0x140039fc0  call    MRxSmbStuffSMB
0x140039fc5  lea     r8d, [rbx+19h]
0x140039fc9  mov     rdx, rsi
0x140039fcc  mov     rcx, rdi; pContext
0x140039fcf  call    SmbPseOrdinaryExchange
0x140039fd4  mov     ebx, eax
0x140039fd6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140039fdd  cmp     rcx, r15
0x140039fe0  jz      short loc_14003A007
0x140039fe2  test    dword ptr [rcx+2Ch], 400h
0x140039fe9  jz      short loc_14003A007
0x140039feb  mov     rcx, [rcx+18h]
0x140039fef  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x140039ff6  mov     edx, 10h
0x140039ffb  mov     dword ptr [rsp+0A8h+var_88], ebx
0x140039fff  mov     r9, rdi
0x14003a002  call    WPP_SF_qD
0x14003a007  lea     r11, [rsp+0A8h+var_18]
0x14003a00f  mov     eax, ebx
0x14003a011  mov     rbx, [r11+28h]
0x14003a015  mov     rbp, [r11+30h]
0x14003a019  mov     rsp, r11
0x14003a01c  pop     r15
0x14003a01e  pop     rdi
0x14003a01f  pop     rsi
0x14003a020  retn
```
