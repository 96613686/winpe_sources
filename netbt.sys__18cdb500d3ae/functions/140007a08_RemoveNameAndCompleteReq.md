# RemoveNameAndCompleteReq

- ea: `0x140007a08`
- end: `0x140007b35`
- name: `RemoveNameAndCompleteReq`
- size: `301`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140007b3c`
- `0x14001a7c8`
- `0x14004d740`

## callees

- `0x140007a08`
- `0x140007be8`
- `0x140007c4c`
- `0x140007df8`
- `0x14000b810`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007a3e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007a9e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007a3e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007a9e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007a5e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007acf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007a5e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007acf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007a2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007a2b`

## pseudocode

```c
void __fastcall RemoveNameAndCompleteReq(_QWORD *a1, unsigned int a2)
{
  __int64 v2; // rdi
  void (__fastcall *v4)(_QWORD *, _QWORD); // rbp
  _QWORD *v5; // r14
  KIRQL v6; // bl
  void *v7; // rcx
  KIRQL v8; // bl

  if ( a1 )
  {
    v2 = a1[2];
    v4 = (void (__fastcall *)(_QWORD *, _QWORD))a1[4];
    v5 = (_QWORD *)a1[3];
    ExFreePoolWithTag(a1, 0);
    v6 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    NbtCancelCancelRoutine(v5[3]);
    KeReleaseSpinLock(&SpinLock, v6);
    if ( v2 )
    {
      if ( a2 )
      {
        v7 = *(void **)(v2 + 48);
        if ( v7 )
        {
          SetNameState(v7);
          *(_QWORD *)(v2 + 48) = 0;
        }
      }
      if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
        WPP_SF_qddds(
          *(_DWORD *)(v2 + 20),
          84,
          (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
          v2,
          *(_DWORD *)(v2 + 20),
          *(_DWORD *)(v2 + 20) - 1,
          54,
          (__int64)"minio\\netbt\\sys\\parse.c");
      v8 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 20), 0xFFFFFFFF) == 1 )
        FreeTracker(v2, 4);
      KeReleaseSpinLock(&SpinLock, v8);
    }
    if ( v4 )
      CompleteClientReq(v4, v5, a2);
  }
}

```

## disassembly

```asm
0x140007a08  test    rcx, rcx
0x140007a0b  jz      locret_140007AF8
0x140007a11  push    rbx
0x140007a12  push    rbp
0x140007a13  push    rsi
0x140007a14  push    rdi
0x140007a15  push    r14
0x140007a17  sub     rsp, 40h
0x140007a1b  mov     rdi, [rcx+10h]
0x140007a1f  mov     esi, edx
0x140007a21  mov     rbp, [rcx+20h]
0x140007a25  xor     edx, edx; Tag
0x140007a27  mov     r14, [rcx+18h]
0x140007a2b  call    cs:__imp_ExFreePoolWithTag
0x140007a32  nop     dword ptr [rax+rax+00h]
0x140007a37  lea     rcx, SpinLock; SpinLock
0x140007a3e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007a45  nop     dword ptr [rax+rax+00h]
0x140007a4a  mov     rcx, [r14+18h]
0x140007a4e  mov     bl, al
0x140007a50  call    NbtCancelCancelRoutine
0x140007a55  mov     dl, bl; NewIrql
0x140007a57  lea     rcx, SpinLock; SpinLock
0x140007a5e  call    cs:__imp_KeReleaseSpinLock
0x140007a65  nop     dword ptr [rax+rax+00h]
0x140007a6a  test    rdi, rdi
0x140007a6d  jz      short loc_140007ADB
0x140007a6f  test    esi, esi
0x140007a71  jz      short loc_140007A8E
0x140007a73  mov     rcx, [rdi+30h]; P
0x140007a77  test    rcx, rcx
0x140007a7a  jz      short loc_140007A8E
0x140007a7c  xor     r8d, r8d
0x140007a7f  xor     edx, edx
0x140007a81  call    SetNameState
0x140007a86  mov     qword ptr [rdi+30h], 0
0x140007a8e  test    byte ptr cs:xmmword_140038420+9, 40h
0x140007a95  jnz     short loc_140007AFA
0x140007a97  lea     rcx, SpinLock; SpinLock
0x140007a9e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007aa5  nop     dword ptr [rax+rax+00h]
0x140007aaa  mov     bl, al
0x140007aac  or      edx, 0FFFFFFFFh
0x140007aaf  lock xadd [rdi+14h], edx
0x140007ab4  cmp     edx, 1
0x140007ab7  jnz     short loc_140007AC6
0x140007ab9  mov     edx, 4
0x140007abe  mov     rcx, rdi
0x140007ac1  call    FreeTracker
0x140007ac6  mov     dl, bl; NewIrql
0x140007ac8  lea     rcx, SpinLock; SpinLock
0x140007acf  call    cs:__imp_KeReleaseSpinLock
0x140007ad6  nop     dword ptr [rax+rax+00h]
0x140007adb  test    rbp, rbp
0x140007ade  jz      short loc_140007AEE
0x140007ae0  mov     r8d, esi
0x140007ae3  mov     rdx, r14
0x140007ae6  mov     rcx, rbp
0x140007ae9  call    CompleteClientReq
0x140007aee  add     rsp, 40h
0x140007af2  pop     r14
0x140007af4  pop     rdi
0x140007af5  pop     rsi
0x140007af6  pop     rbp
0x140007af7  pop     rbx
0x140007af8  retn
0x140007afa  mov     ecx, [rdi+14h]
0x140007afd  lea     r8, aMinioNetbtSysP; "minio\\netbt\\sys\\parse.c"
0x140007b04  mov     [rsp+68h+var_30], r8
0x140007b09  mov     edx, 54h ; 'T'
0x140007b0e  mov     [rsp+68h+var_38], 0F36h
0x140007b16  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x140007b1d  mov     r9, rdi
0x140007b20  lea     eax, [rcx-1]
0x140007b23  mov     [rsp+68h+var_40], eax
0x140007b27  mov     [rsp+68h+var_48], ecx
0x140007b2b  call    WPP_SF_qddds
0x140007b30  jmp     loc_140007A97
```
