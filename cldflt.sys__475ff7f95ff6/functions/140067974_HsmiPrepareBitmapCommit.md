# HsmiPrepareBitmapCommit

- ea: `0x140067974`
- end: `0x140067b03`
- name: `HsmiPrepareBitmapCommit`
- size: `399`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140067e24`

## callees

- `0x140003c50`
- `0x140009300`
- `0x140058ddc`
- `0x140065da4`
- `0x140067974`
- `0x1400698e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140067af2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067af2`
- `ntoskrnl!ExAllocatePool2` at `0x1400679e8`
- `ntoskrnl!ExAllocatePool2` at `0x1400679e8`

## pseudocode

```c
__int64 __fastcall HsmiPrepareBitmapCommit(__int64 a1, __int64 a2, _QWORD *a3, _DWORD *a4)
{
  __int64 v4; // r15
  __int64 Bitmap; // rbx
  _DWORD *v9; // r9
  __int64 StreamSize; // r12
  void *Pool2; // rdi
  __int64 v13; // [rsp+70h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 16);
  Bitmap = HsmiGetBitmap(a1, a2, 0);
  StreamSize = HsmpGetStreamSize(a1);
  LODWORD(v13) = 5120;
  if ( Bitmap )
  {
    Pool2 = (void *)ExAllocatePool2(256, 5120, 1884451656);
    if ( Pool2 )
    {
      if ( (*(_DWORD *)(Bitmap + 16) & 7) != 0 )
        LODWORD(Bitmap) = -1073741595;
      else
        LODWORD(Bitmap) = HsmIBitmapNORMALPrepareCommit(Bitmap, StreamSize, 0, (__int64)Pool2, &v13);
      HsmDbgBreakOnStatus(Bitmap);
      if ( (int)Bitmap < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqd(
            WPP_GLOBAL_Control->AttachedDevice,
            25,
            WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
            a1,
            *(_QWORD *)(v4 + 32),
            Bitmap);
        }
        ExFreePoolWithTag(Pool2, 0x70527348u);
      }
      else
      {
        *a4 = v13;
        *a3 = Pool2;
      }
    }
    else
    {
      LODWORD(Bitmap) = -1073741670;
      HsmDbgBreakOnStatus(-1073741670);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
          a1,
          *(_QWORD *)(v4 + 32),
          -1073741670);
      }
    }
  }
  else
  {
    *a3 = 0;
    *v9 = 0;
  }
  return (unsigned int)Bitmap;
}

```

## disassembly

```asm
0x140067974  mov     [rsp+arg_8], rbx
0x140067979  mov     [rsp+arg_10], rbp
0x14006797e  push    rsi
0x14006797f  push    rdi
0x140067980  push    r12
0x140067982  push    r14
0x140067984  push    r15
0x140067986  sub     rsp, 40h
0x14006798a  mov     r15, [rcx+10h]
0x14006798e  mov     r14, r8
0x140067991  xor     r8d, r8d
0x140067994  mov     rsi, r9
0x140067997  mov     rbp, rcx
0x14006799a  call    HsmiGetBitmap
0x14006799f  mov     rcx, rbp
0x1400679a2  mov     rbx, rax
0x1400679a5  call    HsmpGetStreamSize
0x1400679aa  mov     edx, 1400h
0x1400679af  mov     r12, rax
0x1400679b2  mov     dword ptr [rsp+68h+arg_0], edx
0x1400679b6  test    rbx, rbx
0x1400679b9  jnz     short loc_1400679DD
0x1400679bb  mov     [r14], rbx
0x1400679be  mov     [r9], ebx
0x1400679c1  lea     r11, [rsp+68h+var_28]
0x1400679c6  mov     eax, ebx
0x1400679c8  mov     rbx, [r11+38h]
0x1400679cc  mov     rbp, [r11+40h]
0x1400679d0  mov     rsp, r11
0x1400679d3  pop     r15
0x1400679d5  pop     r14
0x1400679d7  pop     r12
0x1400679d9  pop     rdi
0x1400679da  pop     rsi
0x1400679db  retn
0x1400679dd  mov     ecx, 100h
0x1400679e2  mov     r8d, 70527348h
0x1400679e8  call    cs:__imp_ExAllocatePool2
0x1400679ef  nop     dword ptr [rax+rax+00h]
0x1400679f4  mov     rdi, rax
0x1400679f7  test    rax, rax
0x1400679fa  jz      short loc_140067A3C
0x1400679fc  test    dword ptr [rbx+10h], 7
0x140067a03  jnz     loc_140067A9E
0x140067a09  lea     rax, [rsp+68h+arg_0]
0x140067a0e  mov     r9, rdi
0x140067a11  xor     r8d, r8d
0x140067a14  mov     [rsp+68h+var_48], rax; __int64
0x140067a19  mov     rdx, r12
0x140067a1c  mov     rcx, rbx; int
0x140067a1f  call    HsmIBitmapNORMALPrepareCommit
0x140067a24  mov     ebx, eax
0x140067a26  mov     ecx, ebx
0x140067a28  call    HsmDbgBreakOnStatus
0x140067a2d  test    ebx, ebx
0x140067a2f  js      short loc_140067AA5
0x140067a31  mov     ecx, dword ptr [rsp+68h+arg_0]
0x140067a35  mov     [rsi], ecx
0x140067a37  mov     [r14], rdi
0x140067a3a  jmp     short loc_1400679C1
0x140067a3c  mov     ebx, 0C000009Ah
0x140067a41  mov     ecx, ebx
0x140067a43  call    HsmDbgBreakOnStatus
0x140067a48  mov     rcx, cs:WPP_GLOBAL_Control
0x140067a4f  lea     rax, WPP_GLOBAL_Control
0x140067a56  cmp     rcx, rax
0x140067a59  jz      loc_1400679C1
0x140067a5f  mov     eax, [rcx+2Ch]
0x140067a62  test    al, 1
0x140067a64  jz      loc_1400679C1
0x140067a6a  cmp     byte ptr [rcx+29h], 2
0x140067a6e  jb      loc_1400679C1
0x140067a74  mov     rax, [r15+20h]
0x140067a78  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x140067a7f  mov     rcx, [rcx+18h]
0x140067a83  mov     edx, 18h
0x140067a88  mov     [rsp+68h+var_40], ebx
0x140067a8c  mov     r9, rbp
0x140067a8f  mov     [rsp+68h+var_48], rax
0x140067a94  call    WPP_SF_qqd
0x140067a99  jmp     loc_1400679C1
0x140067a9e  mov     ebx, 0C00000E5h
0x140067aa3  jmp     short loc_140067A26
0x140067aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x140067aac  lea     rax, WPP_GLOBAL_Control
0x140067ab3  cmp     rcx, rax
0x140067ab6  jz      short loc_140067AEA
0x140067ab8  mov     eax, [rcx+2Ch]
0x140067abb  test    al, 1
0x140067abd  jz      short loc_140067AEA
0x140067abf  cmp     byte ptr [rcx+29h], 2
0x140067ac3  jb      short loc_140067AEA
0x140067ac5  mov     rax, [r15+20h]
0x140067ac9  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x140067ad0  mov     rcx, [rcx+18h]
0x140067ad4  mov     edx, 19h
0x140067ad9  mov     [rsp+68h+var_40], ebx
0x140067add  mov     r9, rbp
0x140067ae0  mov     [rsp+68h+var_48], rax
0x140067ae5  call    WPP_SF_qqd
0x140067aea  mov     edx, 70527348h; Tag
0x140067aef  mov     rcx, rdi; P
0x140067af2  call    cs:__imp_ExFreePoolWithTag
0x140067af9  nop     dword ptr [rax+rax+00h]
0x140067afe  jmp     loc_1400679C1
```
