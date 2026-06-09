# DiskIoctlSmartGetVersion

- ea: `0x140013ff0`
- end: `0x1400141f3`
- name: `DiskIoctlSmartGetVersion`
- size: `515`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400014a0`

## callees

- `0x140004078`
- `0x14000431c`
- `0x140005d00`
- `0x140013ff0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400140f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400140f6`
- `ntoskrnl!ExAllocatePool2` at `0x140014069`
- `ntoskrnl!ExAllocatePool2` at `0x140014069`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001401f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001401f`
- `CLASSPNP!ClassSendDeviceIoControlSynchronous` at `0x1400140dd`
- `CLASSPNP!ClassSendDeviceIoControlSynchronous` at `0x1400140dd`

## pseudocode

```c
__int64 __fastcall DiskIoctlSmartGetVersion(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v3; // rbx
  __int64 v6; // r14
  char *Pool2; // rax
  char *v8; // rbx
  unsigned int Status; // edi
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+40h] [rbp-28h] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  v3 = *(_QWORD *)(a2 + 184);
  v6 = *(_QWORD *)(v2 + 96);
  IoStatus = 0;
  if ( KeGetCurrentIrql() >= 2u )
    return 3221225800LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, a1, a2);
  }
  if ( *(_DWORD *)(v3 + 8) < 0x18u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225507LL;
  }
  else
  {
    Pool2 = (char *)ExAllocatePool2(64, 52, 1631871827);
    v8 = Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)Pool2 = 28;
      *(_QWORD *)(Pool2 + 4) = 0x4B53494449534353LL;
      *((_DWORD *)Pool2 + 3) = *(_DWORD *)(v2 + 584);
      *((_DWORD *)Pool2 + 6) = 24;
      *((_DWORD *)Pool2 + 4) = 1770752;
      Pool2[31] = *(_BYTE *)(v6 + 14);
      ClassSendDeviceIoControlSynchronous(0x4D008u, *(PDEVICE_OBJECT *)(v2 + 16), Pool2, 0x34u, 0x34u, 0, &IoStatus);
      Status = IoStatus.Status;
      if ( IoStatus.Status >= 0 )
      {
        memmove(*(void **)(a2 + 24), v8 + 28, 0x18u);
        *(_QWORD *)(a2 + 56) = 24;
      }
      ExFreePoolWithTag(v8, 0);
      return Status;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
      }
      return 3221225626LL;
    }
  }
}

```

## disassembly

```asm
0x140013ff0  mov     [rsp+arg_8], rbx
0x140013ff5  mov     [rsp+arg_10], rbp
0x140013ffa  push    rsi
0x140013ffb  push    rdi
0x140013ffc  push    r14
0x140013ffe  sub     rsp, 50h
0x140014002  mov     rdi, [rcx+40h]
0x140014006  xorps   xmm0, xmm0
0x140014009  mov     rbx, [rdx+0B8h]
0x140014010  mov     rbp, rdx
0x140014013  mov     rsi, rcx
0x140014016  mov     r14, [rdi+60h]
0x14001401a  movups  xmmword ptr [rsp+68h+var_28], xmm0
0x14001401f  call    cs:__imp_KeGetCurrentIrql
0x140014026  nop     dword ptr [rax+rax+00h]
0x14001402b  cmp     al, 2
0x14001402d  jnb     loc_14001418D
0x140014033  mov     rcx, cs:WPP_GLOBAL_Control
0x14001403a  mov     [rsp+68h+arg_0], r15
0x14001403f  lea     r15, WPP_GLOBAL_Control
0x140014046  cmp     rcx, r15
0x140014049  jnz     loc_140014120
0x14001404f  cmp     dword ptr [rbx+8], 18h
0x140014053  jb      loc_140014177
0x140014059  mov     edx, 34h ; '4'
0x14001405e  mov     ecx, 40h ; '@'
0x140014063  mov     r8d, 61446353h
0x140014069  call    cs:__imp_ExAllocatePool2
0x140014070  nop     dword ptr [rax+rax+00h]
0x140014075  mov     rbx, rax
0x140014078  test    rax, rax
0x14001407b  jz      loc_1400141BB
0x140014081  mov     dword ptr [rax], 1Ch
0x140014087  mov     r9d, 34h ; '4'; InputBufferLength
0x14001408d  mov     rax, 4B53494449534353h
0x140014097  mov     r8, rbx; Buffer
0x14001409a  mov     [rbx+4], rax
0x14001409e  mov     ecx, 4D008h; IoControlCode
0x1400140a3  mov     eax, [rdi+248h]
0x1400140a9  mov     [rbx+0Ch], eax
0x1400140ac  mov     dword ptr [rbx+18h], 18h
0x1400140b3  mov     dword ptr [rbx+10h], 1B0500h
0x1400140ba  movzx   eax, byte ptr [r14+0Eh]
0x1400140bf  mov     [rbx+1Fh], al
0x1400140c2  lea     rax, [rsp+68h+var_28]
0x1400140c7  mov     rdx, [rdi+10h]; TargetDeviceObject
0x1400140cb  mov     [rsp+68h+IoStatus], rax; IoStatus
0x1400140d0  mov     [rsp+68h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x1400140d5  mov     [rsp+68h+OutputBufferLength], 34h ; '4'; OutputBufferLength
0x1400140dd  call    cs:__imp_ClassSendDeviceIoControlSynchronous
0x1400140e4  nop     dword ptr [rax+rax+00h]
0x1400140e9  mov     edi, dword ptr [rsp+68h+var_28]
0x1400140ed  test    edi, edi
0x1400140ef  jns     short loc_140014157
0x1400140f1  xor     edx, edx; Tag
0x1400140f3  mov     rcx, rbx; P
0x1400140f6  call    cs:__imp_ExFreePoolWithTag
0x1400140fd  nop     dword ptr [rax+rax+00h]
0x140014102  mov     eax, edi
0x140014104  mov     r15, [rsp+68h+arg_0]
0x140014109  mov     rbx, [rsp+68h+arg_8]
0x14001410e  mov     rbp, [rsp+68h+arg_10]
0x140014116  add     rsp, 50h
0x14001411a  pop     r14
0x14001411c  pop     rdi
0x14001411d  pop     rsi
0x14001411e  retn
0x140014120  mov     eax, [rcx+2Ch]
0x140014123  test    al, 10h
0x140014125  jz      loc_14001404F
0x14001412b  cmp     byte ptr [rcx+29h], 4
0x14001412f  jb      loc_14001404F
0x140014135  mov     rcx, [rcx+18h]
0x140014139  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140014140  mov     edx, 64h ; 'd'
0x140014145  mov     qword ptr [rsp+68h+OutputBufferLength], rbp
0x14001414a  mov     r9, rsi
0x14001414d  call    WPP_SF_qq
0x140014152  jmp     loc_14001404F
0x140014157  mov     rcx, [rbp+18h]; void *
0x14001415b  lea     rdx, [rbx+1Ch]; Src
0x14001415f  mov     r8d, 18h; Size
0x140014165  call    memmove
0x14001416a  mov     qword ptr [rbp+38h], 18h
0x140014172  jmp     loc_1400140F1
0x140014177  mov     rcx, cs:WPP_GLOBAL_Control
0x14001417e  cmp     rcx, r15
0x140014181  jnz     short loc_140014197
0x140014183  mov     eax, 0C0000023h
0x140014188  jmp     loc_140014104
0x14001418d  mov     eax, 0C0000148h
0x140014192  jmp     loc_140014109
0x140014197  mov     eax, [rcx+2Ch]
0x14001419a  test    al, 10h
0x14001419c  jz      short loc_140014183
0x14001419e  cmp     byte ptr [rcx+29h], 2
0x1400141a2  jb      short loc_140014183
0x1400141a4  mov     rcx, [rcx+18h]
0x1400141a8  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x1400141af  mov     edx, 65h ; 'e'
0x1400141b4  call    WPP_SF_
0x1400141b9  jmp     short loc_140014183
0x1400141bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400141c2  cmp     rcx, r15
0x1400141c5  jz      short loc_1400141E9
0x1400141c7  mov     eax, [rcx+2Ch]
0x1400141ca  test    al, 10h
0x1400141cc  jz      short loc_1400141E9
0x1400141ce  cmp     byte ptr [rcx+29h], 2
0x1400141d2  jb      short loc_1400141E9
0x1400141d4  mov     rcx, [rcx+18h]
0x1400141d8  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x1400141df  mov     edx, 66h ; 'f'
0x1400141e4  call    WPP_SF_
0x1400141e9  mov     eax, 0C000009Ah
0x1400141ee  jmp     loc_140014104
```
