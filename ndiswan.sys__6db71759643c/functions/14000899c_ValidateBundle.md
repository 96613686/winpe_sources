# ValidateBundle

- ea: `0x14000899c`
- end: `0x140008b3f`
- name: `ValidateBundle`
- size: `419`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140025c80`
- `0x140026c80`
- `0x1400274e0`
- `0x140027a50`
- `0x140028610`
- `0x140028f60`
- `0x14002a0f0`

## callees

- `0x14000899c`
- `0x14000a648`
- `0x140010ff8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140008a8e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140008a8e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008ae7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008b00`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008ae7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008b00`
- `NDIS!NdisAcquireRWLockRead` at `0x1400089d9`
- `NDIS!NdisAcquireRWLockRead` at `0x1400089d9`
- `NDIS!NdisReleaseRWLock` at `0x140008b1d`
- `NDIS!NdisReleaseRWLock` at `0x140008b1d`

## pseudocode

```c
__int64 __fastcall ValidateBundle(__int64 a1, char a2, _QWORD *a3)
{
  unsigned int v6; // edi
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // r8
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+8h] BYREF

  *a3 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v6 = -1073741816;
  NdisAcquireRWLockRead(ConnTableLock, &LockState, 0);
  if ( (unsigned int)a1 <= *((_DWORD *)ConnectionTable + 1) )
  {
    _mm_lfence();
    v9 = *(_QWORD *)(*((_QWORD *)ConnectionTable + 8) + 8LL * (unsigned int)a1);
    if ( v9 )
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v9 + 1768));
      if ( !a2 || (v10 = *(unsigned int *)(v9 + 20), (_DWORD)v10 == 2) )
      {
        ++*(_DWORD *)(v9 + 24);
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v9 + 1768));
        v6 = 0;
        *a3 = v9;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 19, v10, v9, a1, *(_DWORD *)(v9 + 20));
        }
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v9 + 1768));
        v6 = -1073741667;
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v8 = 18;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v8 = 17;
LABEL_6:
      WPP_SF_q(v7->AttachedDevice, v8, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids, a1);
    }
  }
  NdisReleaseRWLock(ConnTableLock, &LockState);
  return v6;
}

```

## disassembly

```asm
0x14000899c  mov     [rsp+arg_8], rbx
0x1400089a1  mov     [rsp+arg_10], rbp
0x1400089a6  push    rsi
0x1400089a7  push    rdi
0x1400089a8  push    r14
0x1400089aa  sub     rsp, 30h
0x1400089ae  xor     eax, eax
0x1400089b0  mov     r14, r8
0x1400089b3  mov     [r8], rax
0x1400089b6  mov     bpl, dl
0x1400089b9  mov     rsi, rcx
0x1400089bc  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x1400089c1  mov     rcx, cs:ConnTableLock; Lock
0x1400089c8  lea     rdx, [rsp+48h+LockState]; LockState
0x1400089cd  xor     r8d, r8d; Flags
0x1400089d0  mov     [rsp+48h+LockState.Flags], al
0x1400089d4  mov     edi, 0C0000008h
0x1400089d9  call    cs:__imp_NdisAcquireRWLockRead
0x1400089e0  nop     dword ptr [rax+rax+00h]
0x1400089e5  mov     rax, cs:ConnectionTable
0x1400089ec  cmp     esi, [rax+4]
0x1400089ef  jbe     short loc_140008A3A
0x1400089f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400089f8  lea     rax, WPP_GLOBAL_Control
0x1400089ff  cmp     rcx, rax
0x140008a02  jz      loc_140008B11
0x140008a08  mov     eax, [rcx+2Ch]
0x140008a0b  test    al, 8
0x140008a0d  jz      loc_140008B11
0x140008a13  cmp     byte ptr [rcx+29h], 4
0x140008a17  jb      loc_140008B11
0x140008a1d  mov     edx, 11h
0x140008a22  mov     rcx, [rcx+18h]
0x140008a26  lea     r8, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids
0x140008a2d  mov     r9, rsi
0x140008a30  call    WPP_SF_q
0x140008a35  jmp     loc_140008B11
0x140008a3a  lfence
0x140008a3d  mov     rax, cs:ConnectionTable
0x140008a44  mov     edx, esi
0x140008a46  mov     rcx, [rax+40h]
0x140008a4a  mov     rbx, [rcx+rdx*8]
0x140008a4e  test    rbx, rbx
0x140008a51  jnz     short loc_140008A84
0x140008a53  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a5a  lea     rax, WPP_GLOBAL_Control
0x140008a61  cmp     rcx, rax
0x140008a64  jz      loc_140008B11
0x140008a6a  mov     eax, [rcx+2Ch]
0x140008a6d  test    al, 8
0x140008a6f  jz      loc_140008B11
0x140008a75  cmp     byte ptr [rcx+29h], 4
0x140008a79  jb      loc_140008B11
0x140008a7f  lea     edx, [rbx+12h]
0x140008a82  jmp     short loc_140008A22
0x140008a84  lea     rdi, [rbx+6E8h]
0x140008a8b  mov     rcx, rdi; SpinLock
0x140008a8e  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140008a95  nop     dword ptr [rax+rax+00h]
0x140008a9a  test    bpl, bpl
0x140008a9d  jz      short loc_140008AFA
0x140008a9f  mov     r8d, [rbx+14h]
0x140008aa3  cmp     r8d, 2
0x140008aa7  jz      short loc_140008AFA
0x140008aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ab0  lea     rax, WPP_GLOBAL_Control
0x140008ab7  cmp     rcx, rax
0x140008aba  jz      short loc_140008AE4
0x140008abc  mov     eax, [rcx+2Ch]
0x140008abf  test    al, 8
0x140008ac1  jz      short loc_140008AE4
0x140008ac3  cmp     byte ptr [rcx+29h], 4
0x140008ac7  jb      short loc_140008AE4
0x140008ac9  mov     rcx, [rcx+18h]
0x140008acd  mov     edx, 13h
0x140008ad2  mov     [rsp+48h+var_20], r8d
0x140008ad7  mov     r9, rbx
0x140008ada  mov     [rsp+48h+var_28], rsi
0x140008adf  call    WPP_SF_qqd
0x140008ae4  mov     rcx, rdi; SpinLock
0x140008ae7  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140008aee  nop     dword ptr [rax+rax+00h]
0x140008af3  mov     edi, 0C000009Dh
0x140008af8  jmp     short loc_140008B11
0x140008afa  inc     dword ptr [rbx+18h]
0x140008afd  mov     rcx, rdi; SpinLock
0x140008b00  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140008b07  nop     dword ptr [rax+rax+00h]
0x140008b0c  xor     edi, edi
0x140008b0e  mov     [r14], rbx
0x140008b11  mov     rcx, cs:ConnTableLock; Lock
0x140008b18  lea     rdx, [rsp+48h+LockState]; LockState
0x140008b1d  call    cs:__imp_NdisReleaseRWLock
0x140008b24  nop     dword ptr [rax+rax+00h]
0x140008b29  mov     rbx, [rsp+48h+arg_8]
0x140008b2e  mov     eax, edi
0x140008b30  mov     rbp, [rsp+48h+arg_10]
0x140008b35  add     rsp, 30h
0x140008b39  pop     r14
0x140008b3b  pop     rdi
0x140008b3c  pop     rsi
0x140008b3d  retn
```
