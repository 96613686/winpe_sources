# SessionSendResponse

- ea: `0x1400162d0`
- end: `0x140016442`
- name: `SessionSendResponse`
- size: `370`
- prototype: `__int64 __fastcall(__int64, __int64, _BYTE *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012c60`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x1400135cc`
- `0x140013abc`
- `0x1400162d0`
- `0x14001e74c`
- `0x140020380`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001632c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001632c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400163df`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400163df`

## string_xrefs

- `0x1400163c6`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall SessionSendResponse(__int64 a1, __int64 a2, _BYTE *a3, unsigned int a4)
{
  size_t v4; // rbp
  KIRQL v8; // al
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rcx
  char v12; // si
  __int64 v13; // rax
  __int64 v14; // r14
  unsigned int v15; // ebx
  __int64 v16; // rax
  void *v17; // rcx
  int v18; // edx
  unsigned int v20; // [rsp+B8h] [rbp+20h] BYREF

  v4 = a4;
  v20 = a4;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      78,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v11 = a2 + 168;
  *(_BYTE *)(a1 + 64) = v8;
  if ( !a2 )
    v11 = a1 + 208;
  v12 = 1;
  LOBYTE(v9) = -17;
  LOBYTE(v10) = *a3 >> 2;
  v13 = RfcommFrameAllocLockedEx(a1, a2, v9, v10, 0, 1, (__int64)&v20, v11, 0);
  v14 = v13;
  if ( v13 )
  {
    v16 = v13 + 155;
    v15 = 0;
    v17 = (void *)(v16 + 1);
    if ( (unsigned int)v4 < 0x80 )
      v17 = (void *)v16;
    memmove(v17, a3, v4);
    RefObj_AddRefEx(v14 + 24, 1346917442, 3621, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  }
  else
  {
    v12 = 0;
    v15 = -1073741670;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  if ( v12 )
    RfcommFrameWrite(a1, v14);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      3,
      79,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v15);
  return v15;
}

```

## disassembly

```asm
0x1400162d0  mov     rax, rsp
0x1400162d3  push    rbx
0x1400162d4  push    rbp
0x1400162d5  push    rsi
0x1400162d6  push    rdi
0x1400162d7  push    r12
0x1400162d9  push    r13
0x1400162db  push    r14
0x1400162dd  push    r15
0x1400162df  sub     rsp, 58h
0x1400162e3  mov     ebp, r9d
0x1400162e6  mov     r15, r8
0x1400162e9  mov     [rax+20h], ebp
0x1400162ec  mov     rbx, rdx
0x1400162ef  mov     rdi, rcx
0x1400162f2  lea     r13, WPP_RECORDER_INITIALIZED
0x1400162f9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140016300  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140016307  jz      short loc_140016328
0x140016309  mov     rcx, cs:WPP_GLOBAL_Control
0x140016310  mov     r9d, 4Eh ; 'N'
0x140016316  mov     [rsp+98h+var_78], rax
0x14001631b  mov     rcx, [rcx+40h]
0x14001631f  lea     r8d, [r9-4Bh]
0x140016323  call    WPP_RECORDER_SF_
0x140016328  lea     rcx, [rdi+38h]; SpinLock
0x14001632c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016333  nop     dword ptr [rax+rax+00h]
0x140016338  mov     [rsp+98h+var_58], 0
0x14001633d  lea     rcx, [rbx+0A8h]
0x140016344  mov     [rdi+40h], al
0x140016347  test    rbx, rbx
0x14001634a  mov     r9b, [r15]
0x14001634d  lea     rax, [rdi+0D0h]
0x140016354  cmovz   rcx, rax
0x140016358  mov     esi, 1
0x14001635d  mov     [rsp+98h+var_60], rcx
0x140016362  lea     rax, [rsp+98h+arg_18]
0x14001636a  mov     [rsp+98h+var_68], rax
0x14001636f  mov     r8b, 0EFh
0x140016372  mov     [rsp+98h+var_70], esi
0x140016376  mov     rdx, rbx
0x140016379  shr     r9b, 2
0x14001637d  mov     rcx, rdi
0x140016380  mov     byte ptr [rsp+98h+var_78], 0
0x140016385  call    RfcommFrameAllocLockedEx
0x14001638a  mov     r14, rax
0x14001638d  test    rax, rax
0x140016390  jnz     short loc_14001639C
0x140016392  xor     sil, sil
0x140016395  mov     ebx, 0C000009Ah
0x14001639a  jmp     short loc_1400163D8
0x14001639c  add     rax, 9Bh
0x1400163a2  xor     ebx, ebx
0x1400163a4  cmp     ebp, 80h
0x1400163aa  mov     r8, rbp; Size
0x1400163ad  mov     rdx, r15; Src
0x1400163b0  lea     rcx, [rax+1]
0x1400163b4  cmovb   rcx, rax; void *
0x1400163b8  call    memmove
0x1400163bd  lea     rcx, [r14+18h]
0x1400163c1  mov     edx, 50485442h
0x1400163c6  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400163cd  mov     r8d, 0E25h
0x1400163d3  call    RefObj_AddRefEx
0x1400163d8  mov     dl, [rdi+40h]; NewIrql
0x1400163db  lea     rcx, [rdi+38h]; SpinLock
0x1400163df  call    cs:__imp_KeReleaseSpinLock
0x1400163e6  nop     dword ptr [rax+rax+00h]
0x1400163eb  test    sil, sil
0x1400163ee  jz      short loc_1400163FB
0x1400163f0  mov     rdx, r14
0x1400163f3  mov     rcx, rdi
0x1400163f6  call    RfcommFrameWrite
0x1400163fb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140016402  jz      short loc_14001642E
0x140016404  mov     rcx, cs:WPP_GLOBAL_Control
0x14001640b  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140016412  mov     r9d, 4Fh ; 'O'
0x140016418  mov     [rsp+98h+var_70], ebx
0x14001641c  mov     [rsp+98h+var_78], rax
0x140016421  mov     rcx, [rcx+40h]
0x140016425  lea     r8d, [r9-4Ch]
0x140016429  call    WPP_RECORDER_SF_d
0x14001642e  mov     eax, ebx
0x140016430  add     rsp, 58h
0x140016434  pop     r15
0x140016436  pop     r14
0x140016438  pop     r13
0x14001643a  pop     r12
0x14001643c  pop     rdi
0x14001643d  pop     rsi
0x14001643e  pop     rbp
0x14001643f  pop     rbx
0x140016440  retn
```
