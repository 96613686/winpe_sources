# ClassDetermineTokenOperationCommandSupport

- ea: `0x1400561c0`
- end: `0x14005628c`
- name: `ClassDetermineTokenOperationCommandSupport`
- size: `204`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400579b4`

## callees

- `0x14001fc38`
- `0x14002001c`
- `0x140024550`
- `0x140030fdc`
- `0x1400561c0`

## pseudocode

```c
__int64 __fastcall ClassDetermineTokenOperationCommandSupport(__int64 a1)
{
  __int64 v2; // rdx
  int BlockDeviceTokenLimitsInfo; // ebx
  unsigned int v5; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 209, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1);
  }
  BlockDeviceTokenLimitsInfo = ClasspGetBlockDeviceTokenLimitsInfo(a1);
  if ( BlockDeviceTokenLimitsInfo >= 0 )
  {
    v5 = MaxTokenOperationListIdentifier;
    if ( (int)ClasspGetMaximumTokenListIdentifier(a1, v2, &v5) >= 0 && v5 >= 0x100 )
      MaxTokenOperationListIdentifier = v5;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      210,
      WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
      a1,
      BlockDeviceTokenLimitsInfo);
  }
  return (unsigned int)BlockDeviceTokenLimitsInfo;
}

```

## disassembly

```asm
0x1400561c0  mov     [rsp+arg_0], rbx
0x1400561c5  mov     [rsp+arg_10], rsi
0x1400561ca  push    rdi
0x1400561cb  sub     rsp, 30h
0x1400561cf  mov     rdi, rcx
0x1400561d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400561d9  lea     rsi, WPP_GLOBAL_Control
0x1400561e0  cmp     rcx, rsi
0x1400561e3  jz      short loc_14005620A
0x1400561e5  mov     eax, [rcx+2Ch]
0x1400561e8  test    al, 2
0x1400561ea  jz      short loc_14005620A
0x1400561ec  cmp     byte ptr [rcx+29h], 5
0x1400561f0  jb      short loc_14005620A
0x1400561f2  mov     rcx, [rcx+18h]
0x1400561f6  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400561fd  mov     edx, 0D1h
0x140056202  mov     r9, rdi
0x140056205  call    WPP_SF_q
0x14005620a  mov     rcx, rdi
0x14005620d  call    ClasspGetBlockDeviceTokenLimitsInfo
0x140056212  mov     ebx, eax
0x140056214  test    eax, eax
0x140056216  js      short loc_140056244
0x140056218  mov     ecx, cs:MaxTokenOperationListIdentifier
0x14005621e  lea     r8, [rsp+38h+arg_8]
0x140056223  mov     [rsp+38h+arg_8], ecx
0x140056227  mov     rcx, rdi
0x14005622a  call    ClasspGetMaximumTokenListIdentifier
0x14005622f  test    eax, eax
0x140056231  js      short loc_140056244
0x140056233  mov     eax, [rsp+38h+arg_8]
0x140056237  cmp     eax, 100h
0x14005623c  jb      short loc_140056244
0x14005623e  mov     cs:MaxTokenOperationListIdentifier, eax
0x140056244  mov     rcx, cs:WPP_GLOBAL_Control
0x14005624b  cmp     rcx, rsi
0x14005624e  jz      short loc_140056279
0x140056250  mov     eax, [rcx+2Ch]
0x140056253  test    al, 2
0x140056255  jz      short loc_140056279
0x140056257  cmp     byte ptr [rcx+29h], 5
0x14005625b  jb      short loc_140056279
0x14005625d  mov     rcx, [rcx+18h]
0x140056261  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140056268  mov     edx, 0D2h
0x14005626d  mov     [rsp+38h+var_18], ebx
0x140056271  mov     r9, rdi
0x140056274  call    WPP_SF_qD
0x140056279  mov     rsi, [rsp+38h+arg_10]
0x14005627e  mov     eax, ebx
0x140056280  mov     rbx, [rsp+38h+arg_0]
0x140056285  add     rsp, 30h
0x140056289  pop     rdi
0x14005628a  retn
```
