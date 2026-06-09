# ScmCmDeleteVc

- ea: `0x140003fc0`
- end: `0x14000414d`
- name: `ScmCmDeleteVc`
- size: `397`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400018b0`
- `0x140010fd4`

## callees

- `0x140002030`
- `0x140002bd8`
- `0x140003fc0`
- `0x140004a1c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000403d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400040bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000403d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400040bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400040a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400040f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400040a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400040f8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004050`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004050`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004085`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004085`
- `NETIO!HfFreeHandle32` at `0x1400040dc`
- `NETIO!HfFreeHandle32` at `0x1400040dc`

## pseudocode

```c
__int64 __fastcall ScmCmDeleteVc(_QWORD *a1, __int64 a2, __int64 a3)
{
  KIRQL v4; // si
  __int64 v5; // r9
  _QWORD *v6; // r8
  KIRQL v7; // bl

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_q(WPP_GLOBAL_Control->AttachedDevice, a2, a3, (char *)a1 + 484, a1);
    }
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 59);
  KeAcquireSpinLockAtDpcLevel(a1 + 4);
  v5 = a1[2];
  if ( *(_QWORD **)(v5 + 8) != a1 + 2 || (v6 = (_QWORD *)a1[3], (_QWORD *)*v6 != a1 + 2) )
    __fastfail(3u);
  *v6 = v5;
  *(_QWORD *)(v5 + 8) = v6;
  KeReleaseSpinLockFromDpcLevel(a1 + 4);
  KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 59, v4);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 62);
  HfFreeHandle32(*((_QWORD *)SstpGlobals + 63), a1 + 14);
  KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v7);
  DereferenceRefCount(a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140003fc0  push    rbx
0x140003fc2  push    rsi
0x140003fc3  push    rdi
0x140003fc4  push    r14
0x140003fc6  sub     rsp, 38h
0x140003fca  mov     rdi, rcx
0x140003fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140003fd4  lea     r14, WPP_GLOBAL_Control
0x140003fdb  cmp     rcx, r14
0x140003fde  jz      short loc_14000402F
0x140003fe0  mov     eax, [rcx+2Ch]
0x140003fe3  and     eax, 81h
0x140003fe8  cmp     al, 81h
0x140003fea  jnz     short loc_140004001
0x140003fec  mov     rcx, [rcx+18h]
0x140003ff0  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140003ff7  mov     edx, 10h
0x140003ffc  call    WPP_SF_
0x140004001  mov     rcx, cs:WPP_GLOBAL_Control
0x140004008  cmp     rcx, r14
0x14000400b  jz      short loc_14000402F
0x14000400d  mov     eax, [rcx+2Ch]
0x140004010  test    al, 1
0x140004012  jz      short loc_14000402F
0x140004014  cmp     byte ptr [rcx+29h], 3
0x140004018  jb      short loc_14000402F
0x14000401a  mov     rcx, [rcx+18h]
0x14000401e  lea     r9, [rdi+1E4h]
0x140004025  mov     [rsp+58h+var_38], rdi
0x14000402a  call    WPP_SF__guid_q
0x14000402f  mov     rcx, cs:SstpGlobals
0x140004036  add     rcx, 1D8h; SpinLock
0x14000403d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004044  nop     dword ptr [rax+rax+00h]
0x140004049  lea     rcx, [rdi+20h]; SpinLock
0x14000404d  mov     sil, al
0x140004050  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140004057  nop     dword ptr [rax+rax+00h]
0x14000405c  lea     rdx, [rdi+10h]
0x140004060  mov     r9, [rdx]
0x140004063  cmp     [r9+8], rdx
0x140004067  jnz     loc_140004146
0x14000406d  mov     r8, [rdx+8]
0x140004071  cmp     [r8], rdx
0x140004074  jnz     loc_140004146
0x14000407a  mov     [r8], r9
0x14000407d  lea     rcx, [rdi+20h]; SpinLock
0x140004081  mov     [r9+8], r8
0x140004085  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000408c  nop     dword ptr [rax+rax+00h]
0x140004091  mov     rcx, cs:SstpGlobals
0x140004098  mov     dl, sil; NewIrql
0x14000409b  add     rcx, 1D8h; SpinLock
0x1400040a2  call    cs:__imp_KeReleaseSpinLock
0x1400040a9  nop     dword ptr [rax+rax+00h]
0x1400040ae  mov     rcx, cs:SstpGlobals
0x1400040b5  add     rcx, 1F0h; SpinLock
0x1400040bc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400040c3  nop     dword ptr [rax+rax+00h]
0x1400040c8  mov     rcx, cs:SstpGlobals
0x1400040cf  lea     rdx, [rdi+70h]
0x1400040d3  mov     bl, al
0x1400040d5  mov     rcx, [rcx+1F8h]
0x1400040dc  call    cs:__imp_HfFreeHandle32
0x1400040e3  nop     dword ptr [rax+rax+00h]
0x1400040e8  mov     rcx, cs:SstpGlobals
0x1400040ef  mov     dl, bl; NewIrql
0x1400040f1  add     rcx, 1F0h; SpinLock
0x1400040f8  call    cs:__imp_KeReleaseSpinLock
0x1400040ff  nop     dword ptr [rax+rax+00h]
0x140004104  mov     rcx, rdi
0x140004107  call    DereferenceRefCount
0x14000410c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004113  cmp     rcx, r14
0x140004116  jz      short loc_140004139
0x140004118  mov     eax, [rcx+2Ch]
0x14000411b  and     eax, 81h
0x140004120  cmp     al, 81h
0x140004122  jnz     short loc_140004139
0x140004124  mov     rcx, [rcx+18h]
0x140004128  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x14000412f  mov     edx, 12h
0x140004134  call    WPP_SF_
0x140004139  xor     eax, eax
0x14000413b  add     rsp, 38h
0x14000413f  pop     r14
0x140004141  pop     rdi
0x140004142  pop     rsi
0x140004143  pop     rbx
0x140004144  retn
0x140004146  mov     ecx, 3
0x14000414b  int     29h; Win8: RtlFailFast(ecx)
```
