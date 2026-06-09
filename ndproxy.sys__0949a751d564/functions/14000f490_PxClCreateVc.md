# PxClCreateVc

- ea: `0x14000f490`
- end: `0x14000f621`
- name: `PxClCreateVc`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140001b54`
- `0x140001bc8`
- `0x140001c0c`
- `0x140006ed4`
- `0x14000f490`
- `0x140010f64`
- `0x1400162c8`
- `0x140016628`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f4e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f4e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f570`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f590`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f570`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f590`

## pseudocode

```c
__int64 __fastcall PxClCreateVc(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v6; // ebx
  char *Vc; // rax
  char *v8; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids, a1);
  *(_BYTE *)(a1 + 192) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 184));
  if ( *(_DWORD *)(a1 + 16) != 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids,
        a1,
        *(_DWORD *)(a1 + 16));
    v6 = -1073741823;
LABEL_14:
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 184), *(_BYTE *)(a1 + 192));
    return v6;
  }
  Vc = PxAllocateVc(a1);
  v8 = Vc;
  if ( !Vc )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids);
    v6 = -1073741670;
    goto LABEL_14;
  }
  *((_QWORD *)Vc + 5) = a2;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 184), *(_BYTE *)(a1 + 192));
  if ( InsertVcInTable((__int64)v8) )
  {
    InsertVcInClAfList(v8);
    *a3 = *((_QWORD *)v8 + 35);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids);
    PxFreeVc(v8);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14000f490  push    rbx
0x14000f492  push    rbp
0x14000f493  push    rsi
0x14000f494  push    rdi
0x14000f495  push    r12
0x14000f497  push    r14
0x14000f499  push    r15
0x14000f49b  sub     rsp, 30h
0x14000f49f  mov     r14, r8
0x14000f4a2  mov     rbp, rdx
0x14000f4a5  mov     rdi, rcx
0x14000f4a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f4af  lea     r15, WPP_GLOBAL_Control
0x14000f4b6  lea     r12, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000f4bd  cmp     rcx, r15
0x14000f4c0  jz      short loc_14000F4DC
0x14000f4c2  cmp     byte ptr [rcx+29h], 5
0x14000f4c6  jb      short loc_14000F4DC
0x14000f4c8  mov     rcx, [rcx+18h]
0x14000f4cc  mov     edx, 0Ah
0x14000f4d1  mov     r9, rdi
0x14000f4d4  mov     r8, r12
0x14000f4d7  call    WPP_SF_q
0x14000f4dc  lea     rsi, [rdi+0B8h]
0x14000f4e3  mov     rcx, rsi; SpinLock
0x14000f4e6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f4ed  nop     dword ptr [rax+rax+00h]
0x14000f4f2  mov     [rdi+0C0h], al
0x14000f4f8  mov     eax, [rdi+10h]
0x14000f4fb  cmp     eax, 3
0x14000f4fe  jz      short loc_14000F531
0x14000f500  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f507  cmp     rcx, r15
0x14000f50a  jz      short loc_14000F52A
0x14000f50c  cmp     byte ptr [rcx+29h], 3
0x14000f510  jb      short loc_14000F52A
0x14000f512  mov     rcx, [rcx+18h]
0x14000f516  mov     edx, 0Bh
0x14000f51b  mov     r9, rdi
0x14000f51e  mov     [rsp+68h+var_48], eax
0x14000f522  mov     r8, r12
0x14000f525  call    WPP_SF_qD
0x14000f52a  mov     ebx, 0C0000001h
0x14000f52f  jmp     short loc_14000F567
0x14000f531  mov     rcx, rdi
0x14000f534  call    PxAllocateVc
0x14000f539  mov     rbx, rax
0x14000f53c  test    rax, rax
0x14000f53f  jnz     short loc_14000F583
0x14000f541  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f548  cmp     rcx, r15
0x14000f54b  jz      short loc_14000F562
0x14000f54d  cmp     byte ptr [rcx+29h], 3
0x14000f551  jb      short loc_14000F562
0x14000f553  mov     rcx, [rcx+18h]
0x14000f557  lea     edx, [rax+0Ch]
0x14000f55a  mov     r8, r12
0x14000f55d  call    WPP_SF_
0x14000f562  mov     ebx, 0C000009Ah
0x14000f567  mov     dl, [rdi+0C0h]; NewIrql
0x14000f56d  mov     rcx, rsi; SpinLock
0x14000f570  call    cs:__imp_KeReleaseSpinLock
0x14000f577  nop     dword ptr [rax+rax+00h]
0x14000f57c  mov     eax, ebx
0x14000f57e  jmp     loc_14000F611
0x14000f583  mov     [rax+28h], rbp
0x14000f587  mov     rcx, rsi; SpinLock
0x14000f58a  mov     dl, [rdi+0C0h]; NewIrql
0x14000f590  call    cs:__imp_KeReleaseSpinLock
0x14000f597  nop     dword ptr [rax+rax+00h]
0x14000f59c  mov     rcx, rbx
0x14000f59f  call    InsertVcInTable
0x14000f5a4  test    al, al
0x14000f5a6  jnz     short loc_14000F5DA
0x14000f5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f5af  cmp     rcx, r15
0x14000f5b2  jz      short loc_14000F5CB
0x14000f5b4  cmp     byte ptr [rcx+29h], 3
0x14000f5b8  jb      short loc_14000F5CB
0x14000f5ba  mov     rcx, [rcx+18h]
0x14000f5be  mov     edx, 0Dh
0x14000f5c3  mov     r8, r12
0x14000f5c6  call    WPP_SF_
0x14000f5cb  mov     rcx, rbx; Entry
0x14000f5ce  call    PxFreeVc
0x14000f5d3  mov     eax, 0C000009Ah
0x14000f5d8  jmp     short loc_14000F611
0x14000f5da  mov     rcx, rbx
0x14000f5dd  call    InsertVcInClAfList
0x14000f5e2  mov     rax, [rbx+118h]
0x14000f5e9  mov     [r14], rax
0x14000f5ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f5f3  cmp     rcx, r15
0x14000f5f6  jz      short loc_14000F60F
0x14000f5f8  cmp     byte ptr [rcx+29h], 5
0x14000f5fc  jb      short loc_14000F60F
0x14000f5fe  mov     rcx, [rcx+18h]
0x14000f602  mov     edx, 0Eh
0x14000f607  mov     r8, r12
0x14000f60a  call    WPP_SF_
0x14000f60f  xor     eax, eax
0x14000f611  add     rsp, 30h
0x14000f615  pop     r15
0x14000f617  pop     r14
0x14000f619  pop     r12
0x14000f61b  pop     rdi
0x14000f61c  pop     rsi
0x14000f61d  pop     rbp
0x14000f61e  pop     rbx
0x14000f61f  retn
```
