# ScmCmDeactivateVcComplete

- ea: `0x140013dc0`
- end: `0x140013ea9`
- name: `ScmCmDeactivateVcComplete`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400018b0`

## callees

- `0x1400018b0`
- `0x140002bd8`
- `0x140002fc4`
- `0x140013dc0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013e46`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013e46`

## pseudocode

```c
__int64 __fastcall ScmCmDeactivateVcComplete(int a1, __int64 a2)
{
  KIRQL v4; // al
  __int64 v5; // r8
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_D(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids,
        a2 + 484,
        a1);
    }
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  *(_DWORD *)(a2 + 21088) &= ~0x400u;
  LOBYTE(v5) = v4;
  result = InitiateSstpContextCleanup(a2, 4, v5);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer) & 0x81;
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140013dc0  mov     [rsp+arg_0], rbx
0x140013dc5  mov     [rsp+arg_8], rdi
0x140013dca  push    r14
0x140013dcc  sub     rsp, 30h
0x140013dd0  mov     rbx, rdx
0x140013dd3  mov     edi, ecx
0x140013dd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ddc  lea     r14, WPP_GLOBAL_Control
0x140013de3  cmp     rcx, r14
0x140013de6  jz      short loc_140013E42
0x140013de8  mov     eax, [rcx+2Ch]
0x140013deb  and     eax, 81h
0x140013df0  cmp     al, 81h
0x140013df2  jnz     short loc_140013E09
0x140013df4  mov     rcx, [rcx+18h]
0x140013df8  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140013dff  mov     edx, 31h ; '1'
0x140013e04  call    WPP_SF_
0x140013e09  mov     rcx, cs:WPP_GLOBAL_Control
0x140013e10  cmp     rcx, r14
0x140013e13  jz      short loc_140013E42
0x140013e15  mov     eax, [rcx+2Ch]
0x140013e18  test    al, 1
0x140013e1a  jz      short loc_140013E42
0x140013e1c  cmp     byte ptr [rcx+29h], 3
0x140013e20  jb      short loc_140013E42
0x140013e22  mov     rcx, [rcx+18h]
0x140013e26  lea     r9, [rbx+1E4h]
0x140013e2d  mov     edx, 32h ; '2'
0x140013e32  mov     [rsp+38h+var_18], edi
0x140013e36  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140013e3d  call    WPP_SF__guid_D
0x140013e42  lea     rcx, [rbx+20h]; SpinLock
0x140013e46  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013e4d  nop     dword ptr [rax+rax+00h]
0x140013e52  btr     dword ptr [rbx+5260h], 0Ah
0x140013e5a  mov     edx, 4
0x140013e5f  mov     r8b, al
0x140013e62  mov     rcx, rbx
0x140013e65  call    InitiateSstpContextCleanup
0x140013e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013e71  cmp     rcx, r14
0x140013e74  jz      short loc_140013E97
0x140013e76  mov     eax, [rcx+2Ch]
0x140013e79  and     eax, 81h
0x140013e7e  cmp     al, 81h
0x140013e80  jnz     short loc_140013E97
0x140013e82  mov     rcx, [rcx+18h]
0x140013e86  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140013e8d  mov     edx, 33h ; '3'
0x140013e92  call    WPP_SF_
0x140013e97  mov     rbx, [rsp+38h+arg_0]
0x140013e9c  mov     rdi, [rsp+38h+arg_8]
0x140013ea1  add     rsp, 30h
0x140013ea5  pop     r14
0x140013ea7  retn
```
