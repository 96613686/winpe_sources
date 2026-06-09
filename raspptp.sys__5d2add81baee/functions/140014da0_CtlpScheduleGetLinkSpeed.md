# CtlpScheduleGetLinkSpeed

- ea: `0x140014da0`
- end: `0x140014f2e`
- name: `CtlpScheduleGetLinkSpeed`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140014c30`

## callees

- `0x140003e08`
- `0x140003e38`
- `0x140004204`
- `0x1400072fc`
- `0x140007710`
- `0x140014da0`
- `0x140015338`
- `0x1400154b8`

## pseudocode

```c
__int64 __fastcall CtlpScheduleGetLinkSpeed(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int v2; // edi
  int v3; // eax
  __int64 result; // rax
  unsigned int v5; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 24);
  v5 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids);
  }
  if ( (int)NsiCliGetLinkSpeedFromInterfaceIpAddress(*(unsigned int *)(v1 + 540), &v5) >= 0 )
  {
    v2 = v5;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids, v5);
    }
    *(_DWORD *)(v1 + 656) = v2;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids);
  }
  v3 = *(_DWORD *)(v1 + 48);
  if ( v3 == 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids, v1);
    }
    SendControlStartRequest(v1);
  }
  else if ( v3 == 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids, v1);
    }
    SendControlStartReply(v1);
  }
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 16), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    result = (*(__int64 (__fastcall **)(__int64))(v1 + 24))(v1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140014da0  push    rbx
0x140014da2  push    rdi
0x140014da3  push    r14
0x140014da5  push    r15
0x140014da7  sub     rsp, 28h
0x140014dab  mov     rbx, [rcx+18h]
0x140014daf  mov     [rsp+48h+arg_0], 0
0x140014db7  mov     rcx, cs:WPP_GLOBAL_Control
0x140014dbe  lea     r14, WPP_GLOBAL_Control
0x140014dc5  lea     r15, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x140014dcc  cmp     rcx, r14
0x140014dcf  jz      short loc_140014DEF
0x140014dd1  mov     eax, [rcx+2Ch]
0x140014dd4  test    al, 8
0x140014dd6  jz      short loc_140014DEF
0x140014dd8  cmp     byte ptr [rcx+29h], 4
0x140014ddc  jb      short loc_140014DEF
0x140014dde  mov     rcx, [rcx+18h]
0x140014de2  mov     edx, 1Ch
0x140014de7  mov     r8, r15
0x140014dea  call    WPP_SF_
0x140014def  mov     ecx, [rbx+21Ch]
0x140014df5  lea     rdx, [rsp+48h+arg_0]
0x140014dfa  call    NsiCliGetLinkSpeedFromInterfaceIpAddress
0x140014dff  test    eax, eax
0x140014e01  jns     short loc_140014E2F
0x140014e03  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e0a  cmp     rcx, r14
0x140014e0d  jz      short loc_140014E66
0x140014e0f  mov     eax, [rcx+2Ch]
0x140014e12  test    al, 8
0x140014e14  jz      short loc_140014E66
0x140014e16  cmp     byte ptr [rcx+29h], 4
0x140014e1a  jb      short loc_140014E66
0x140014e1c  mov     rcx, [rcx+18h]
0x140014e20  mov     edx, 1Dh
0x140014e25  mov     r8, r15
0x140014e28  call    WPP_SF_
0x140014e2d  jmp     short loc_140014E66
0x140014e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e36  mov     edi, [rsp+48h+arg_0]
0x140014e3a  cmp     rcx, r14
0x140014e3d  jz      short loc_140014E60
0x140014e3f  mov     eax, [rcx+2Ch]
0x140014e42  test    al, 8
0x140014e44  jz      short loc_140014E60
0x140014e46  cmp     byte ptr [rcx+29h], 4
0x140014e4a  jb      short loc_140014E60
0x140014e4c  mov     rcx, [rcx+18h]
0x140014e50  mov     edx, 1Eh
0x140014e55  mov     r9d, edi
0x140014e58  mov     r8, r15
0x140014e5b  call    WPP_SF_d
0x140014e60  mov     [rbx+290h], edi
0x140014e66  mov     eax, [rbx+30h]
0x140014e69  cmp     eax, 2
0x140014e6c  jnz     short loc_140014EA5
0x140014e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e75  cmp     rcx, r14
0x140014e78  jz      short loc_140014E9B
0x140014e7a  mov     eax, [rcx+2Ch]
0x140014e7d  test    al, 8
0x140014e7f  jz      short loc_140014E9B
0x140014e81  cmp     byte ptr [rcx+29h], 4
0x140014e85  jb      short loc_140014E9B
0x140014e87  mov     rcx, [rcx+18h]
0x140014e8b  mov     edx, 1Fh
0x140014e90  mov     r9, rbx
0x140014e93  mov     r8, r15
0x140014e96  call    WPP_SF_q
0x140014e9b  mov     rcx, rbx
0x140014e9e  call    SendControlStartRequest
0x140014ea3  jmp     short loc_140014EDF
0x140014ea5  cmp     eax, 3
0x140014ea8  jnz     short loc_140014EDF
0x140014eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x140014eb1  cmp     rcx, r14
0x140014eb4  jz      short loc_140014ED7
0x140014eb6  mov     eax, [rcx+2Ch]
0x140014eb9  test    al, 8
0x140014ebb  jz      short loc_140014ED7
0x140014ebd  cmp     byte ptr [rcx+29h], 4
0x140014ec1  jb      short loc_140014ED7
0x140014ec3  mov     rcx, [rcx+18h]
0x140014ec7  mov     edx, 20h ; ' '
0x140014ecc  mov     r9, rbx
0x140014ecf  mov     r8, r15
0x140014ed2  call    WPP_SF_q
0x140014ed7  mov     rcx, rbx
0x140014eda  call    SendControlStartReply
0x140014edf  or      eax, 0FFFFFFFFh
0x140014ee2  lock xadd [rbx+10h], eax
0x140014ee7  cmp     eax, 1
0x140014eea  jnz     short loc_140014EF8
0x140014eec  mov     rax, [rbx+18h]
0x140014ef0  mov     rcx, rbx
0x140014ef3  call    _guard_dispatch_icall
0x140014ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x140014eff  cmp     rcx, r14
0x140014f02  jz      short loc_140014F22
0x140014f04  mov     eax, [rcx+2Ch]
0x140014f07  test    al, 8
0x140014f09  jz      short loc_140014F22
0x140014f0b  cmp     byte ptr [rcx+29h], 4
0x140014f0f  jb      short loc_140014F22
0x140014f11  mov     rcx, [rcx+18h]
0x140014f15  mov     edx, 21h ; '!'
0x140014f1a  mov     r8, r15
0x140014f1d  call    WPP_SF_
0x140014f22  add     rsp, 28h
0x140014f26  pop     r15
0x140014f28  pop     r14
0x140014f2a  pop     rdi
0x140014f2b  pop     rbx
0x140014f2c  retn
```
