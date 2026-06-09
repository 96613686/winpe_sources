# ScmCmCreateVc

- ea: `0x140003ce0`
- end: `0x140003fab`
- name: `ScmCmCreateVc`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140010fd4`

## callees

- `0x140002bd8`
- `0x140002c08`
- `0x140003a64`
- `0x140003ce0`
- `0x140006240`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140003d3c`
- `ntoskrnl!ExAllocatePool2` at `0x140003d3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ea2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ea2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003e19`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003ede`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003e19`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003ede`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003e8e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003ec4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003f31`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003e8e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003ec4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003f31`
- `ntoskrnl!KeInitializeSpinLock` at `0x140003d97`
- `ntoskrnl!KeInitializeSpinLock` at `0x140003d97`
- `NETIO!HfAllocateHandle32` at `0x140003e3d`
- `NETIO!HfAllocateHandle32` at `0x140003e3d`

## pseudocode

```c
__int64 __fastcall ScmCmCreateVc(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 Pool2; // rbx
  int Handle32; // edi
  KIRQL v7; // bp
  KIRQL v8; // al
  _QWORD *v9; // rdx
  char *v10; // rcx
  PVOID *v11; // r8

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  Pool2 = ExAllocatePool2(64, 21144, 2020885331);
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 0;
    *(_QWORD *)(Pool2 + 8) = CleanupSstpContext;
    KeInitializeSpinLock((PKSPIN_LOCK)(Pool2 + 32));
    *(_QWORD *)(Pool2 + 40) = a2;
    *(_QWORD *)(Pool2 + 56) = 0;
    *(_QWORD *)(Pool2 + 72) = 0;
    *(_QWORD *)(Pool2 + 80) = 0;
    *(_DWORD *)(Pool2 + 116) = 0;
    *(_DWORD *)(Pool2 + 21088) = 0;
    *(_WORD *)(Pool2 + 506) = 0;
    *(_BYTE *)(Pool2 + 508) = 0;
    *(_DWORD *)(Pool2 + 21096) = -1073741536;
    *(_QWORD *)(Pool2 + 21120) = 0;
    *(_BYTE *)(Pool2 + 21132) = 0;
    *(_QWORD *)(Pool2 + 21136) = 0;
    memset((void *)(Pool2 + 544), 0, 0x5014u);
    *(_QWORD *)(Pool2 + 536) = 4;
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 62);
    Handle32 = HfAllocateHandle32(*((_QWORD *)SstpGlobals + 63), Pool2, Pool2 + 112);
    if ( Handle32 >= 0 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v7);
      v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 59);
      v9 = (_QWORD *)(Pool2 + 16);
      *(_QWORD *)(Pool2 + 24) = Pool2 + 16;
      *(_QWORD *)(Pool2 + 16) = Pool2 + 16;
      v10 = (char *)SstpGlobals + 480;
      v11 = (PVOID *)*((_QWORD *)SstpGlobals + 61);
      if ( *v11 != (char *)SstpGlobals + 480 )
        __fastfail(3u);
      *v9 = v10;
      *(_QWORD *)(Pool2 + 24) = v11;
      *v11 = v9;
      *((_QWORD *)v10 + 1) = v9;
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 59, v8);
      _InterlockedIncrement((volatile signed __int32 *)Pool2);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids, Pool2);
      }
      *a3 = Pool2;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
      }
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v7);
      ExFreePoolWithTag((PVOID)Pool2, 0x78744353u);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
    }
    Handle32 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  return (unsigned int)Handle32;
}

```

## disassembly

```asm
0x140003ce0  push    rbx
0x140003ce2  push    rbp
0x140003ce3  push    rsi
0x140003ce4  push    rdi
0x140003ce5  push    r12
0x140003ce7  push    r14
0x140003ce9  push    r15
0x140003ceb  sub     rsp, 20h
0x140003cef  mov     rsi, r8
0x140003cf2  mov     rdi, rdx
0x140003cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x140003cfc  lea     r15, WPP_GLOBAL_Control
0x140003d03  lea     r14, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140003d0a  cmp     rcx, r15
0x140003d0d  jz      short loc_140003D2C
0x140003d0f  mov     eax, [rcx+2Ch]
0x140003d12  and     eax, 81h
0x140003d17  cmp     al, 81h
0x140003d19  jnz     short loc_140003D2C
0x140003d1b  mov     rcx, [rcx+18h]
0x140003d1f  mov     edx, 0Bh
0x140003d24  mov     r8, r14
0x140003d27  call    WPP_SF_
0x140003d2c  mov     edx, 5298h
0x140003d31  mov     ecx, 40h ; '@'
0x140003d36  mov     r8d, 78744353h
0x140003d3c  call    cs:__imp_ExAllocatePool2
0x140003d43  nop     dword ptr [rax+rax+00h]
0x140003d48  xor     r12d, r12d
0x140003d4b  mov     rbx, rax
0x140003d4e  test    rax, rax
0x140003d51  jnz     short loc_140003D85
0x140003d53  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d5a  cmp     rcx, r15
0x140003d5d  jz      short loc_140003D7B
0x140003d5f  mov     eax, [rcx+2Ch]
0x140003d62  test    al, 1
0x140003d64  jz      short loc_140003D7B
0x140003d66  cmp     byte ptr [rcx+29h], 1
0x140003d6a  jb      short loc_140003D7B
0x140003d6c  mov     rcx, [rcx+18h]
0x140003d70  lea     edx, [rbx+0Ch]
0x140003d73  mov     r8, r14
0x140003d76  call    WPP_SF_
0x140003d7b  mov     edi, 0C000009Ah
0x140003d80  jmp     loc_140003F70
0x140003d85  lea     rax, CleanupSstpContext
0x140003d8c  mov     [rbx], r12d
0x140003d8f  lea     rcx, [rbx+20h]; SpinLock
0x140003d93  mov     [rbx+8], rax
0x140003d97  call    cs:__imp_KeInitializeSpinLock
0x140003d9e  nop     dword ptr [rax+rax+00h]
0x140003da3  lea     rcx, [rbx+220h]; void *
0x140003daa  mov     [rbx+28h], rdi
0x140003dae  xor     edx, edx; Val
0x140003db0  mov     [rbx+38h], r12
0x140003db4  mov     r8d, 5014h; Size
0x140003dba  mov     [rbx+48h], r12
0x140003dbe  mov     [rbx+50h], r12
0x140003dc2  mov     [rbx+74h], r12d
0x140003dc6  mov     [rbx+5260h], r12d
0x140003dcd  mov     [rbx+1FAh], r12w
0x140003dd5  mov     [rbx+1FCh], r12b
0x140003ddc  mov     dword ptr [rbx+5268h], 0C0000120h
0x140003de6  mov     [rbx+5280h], r12
0x140003ded  mov     [rbx+528Ch], r12b
0x140003df4  mov     [rbx+5290h], r12
0x140003dfb  call    memset
0x140003e00  mov     qword ptr [rbx+218h], 4
0x140003e0b  mov     rcx, cs:SstpGlobals
0x140003e12  add     rcx, 1F0h; SpinLock
0x140003e19  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003e20  nop     dword ptr [rax+rax+00h]
0x140003e25  mov     rcx, cs:SstpGlobals
0x140003e2c  lea     r8, [rbx+70h]
0x140003e30  mov     rdx, rbx
0x140003e33  mov     bpl, al
0x140003e36  mov     rcx, [rcx+1F8h]
0x140003e3d  call    cs:__imp_HfAllocateHandle32
0x140003e44  nop     dword ptr [rax+rax+00h]
0x140003e49  mov     edi, eax
0x140003e4b  test    eax, eax
0x140003e4d  jns     short loc_140003EB3
0x140003e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e56  cmp     rcx, r15
0x140003e59  jz      short loc_140003E7D
0x140003e5b  mov     edx, [rcx+2Ch]
0x140003e5e  test    dl, 2
0x140003e61  jz      short loc_140003E7D
0x140003e63  cmp     byte ptr [rcx+29h], 1
0x140003e67  jb      short loc_140003E7D
0x140003e69  mov     rcx, [rcx+18h]
0x140003e6d  mov     edx, 0Dh
0x140003e72  mov     r9d, eax
0x140003e75  mov     r8, r14
0x140003e78  call    WPP_SF_d
0x140003e7d  mov     rcx, cs:SstpGlobals
0x140003e84  mov     dl, bpl; NewIrql
0x140003e87  add     rcx, 1F0h; SpinLock
0x140003e8e  call    cs:__imp_KeReleaseSpinLock
0x140003e95  nop     dword ptr [rax+rax+00h]
0x140003e9a  mov     edx, 78744353h; Tag
0x140003e9f  mov     rcx, rbx; P
0x140003ea2  call    cs:__imp_ExFreePoolWithTag
0x140003ea9  nop     dword ptr [rax+rax+00h]
0x140003eae  jmp     loc_140003F70
0x140003eb3  mov     rcx, cs:SstpGlobals
0x140003eba  mov     dl, bpl; NewIrql
0x140003ebd  add     rcx, 1F0h; SpinLock
0x140003ec4  call    cs:__imp_KeReleaseSpinLock
0x140003ecb  nop     dword ptr [rax+rax+00h]
0x140003ed0  mov     rcx, cs:SstpGlobals
0x140003ed7  add     rcx, 1D8h; SpinLock
0x140003ede  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003ee5  nop     dword ptr [rax+rax+00h]
0x140003eea  lea     rdx, [rbx+10h]
0x140003eee  mov     [rdx+8], rdx
0x140003ef2  mov     [rdx], rdx
0x140003ef5  mov     rcx, cs:SstpGlobals
0x140003efc  add     rcx, 1E0h
0x140003f03  mov     r8, [rcx+8]
0x140003f07  cmp     [r8], rcx
0x140003f0a  jz      short loc_140003F13
0x140003f0c  mov     ecx, 3
0x140003f11  int     29h; Win8: RtlFailFast(ecx)
0x140003f13  mov     [rdx], rcx
0x140003f16  mov     [rdx+8], r8
0x140003f1a  mov     [r8], rdx
0x140003f1d  mov     [rcx+8], rdx
0x140003f21  mov     dl, al; NewIrql
0x140003f23  mov     rcx, cs:SstpGlobals
0x140003f2a  add     rcx, 1D8h; SpinLock
0x140003f31  call    cs:__imp_KeReleaseSpinLock
0x140003f38  nop     dword ptr [rax+rax+00h]
0x140003f3d  lock inc dword ptr [rbx]
0x140003f40  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f47  cmp     rcx, r15
0x140003f4a  jz      short loc_140003F6D
0x140003f4c  mov     eax, [rcx+2Ch]
0x140003f4f  test    al, 1
0x140003f51  jz      short loc_140003F6D
0x140003f53  cmp     byte ptr [rcx+29h], 2
0x140003f57  jb      short loc_140003F6D
0x140003f59  mov     rcx, [rcx+18h]
0x140003f5d  mov     edx, 0Eh
0x140003f62  mov     r9, rbx
0x140003f65  mov     r8, r14
0x140003f68  call    WPP_SF_q
0x140003f6d  mov     [rsi], rbx
0x140003f70  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f77  cmp     rcx, r15
0x140003f7a  jz      short loc_140003F99
0x140003f7c  mov     eax, [rcx+2Ch]
0x140003f7f  and     eax, 81h
0x140003f84  cmp     al, 81h
0x140003f86  jnz     short loc_140003F99
0x140003f88  mov     rcx, [rcx+18h]
0x140003f8c  mov     edx, 0Fh
0x140003f91  mov     r8, r14
0x140003f94  call    WPP_SF_
0x140003f99  mov     eax, edi
0x140003f9b  add     rsp, 20h
0x140003f9f  pop     r15
0x140003fa1  pop     r14
0x140003fa3  pop     r12
0x140003fa5  pop     rdi
0x140003fa6  pop     rsi
0x140003fa7  pop     rbp
0x140003fa8  pop     rbx
0x140003fa9  retn
```
