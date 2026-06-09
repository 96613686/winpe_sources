# ValidateLink

- ea: `0x1400087f0`
- end: `0x140008993`
- name: `ValidateLink`
- size: `419`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140002e40`
- `0x140007a00`
- `0x140007dd0`
- `0x1400288a0`
- `0x1400296d0`
- `0x140029850`
- `0x14002bd20`

## callees

- `0x1400087f0`
- `0x14000a648`
- `0x140010ff8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400088e2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400088e2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000893b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008954`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000893b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008954`
- `NDIS!NdisAcquireRWLockRead` at `0x14000882d`
- `NDIS!NdisAcquireRWLockRead` at `0x14000882d`
- `NDIS!NdisReleaseRWLock` at `0x140008971`
- `NDIS!NdisReleaseRWLock` at `0x140008971`

## pseudocode

```c
__int64 __fastcall ValidateLink(__int64 a1, char a2, _QWORD *a3)
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
    v9 = *(_QWORD *)(*((_QWORD *)ConnectionTable + 7) + 8LL * (unsigned int)a1);
    if ( v9 )
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v9 + 736));
      if ( !a2 || (v10 = *(unsigned int *)(v9 + 20), (_DWORD)v10 == 2) )
      {
        ++*(_DWORD *)(v9 + 28);
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v9 + 736));
        v6 = 0;
        *a3 = v9;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 16, v10, v9, a1, *(_DWORD *)(v9 + 20));
        }
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v9 + 736));
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
        v8 = 15;
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
      v8 = 14;
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
0x1400087f0  mov     [rsp+arg_8], rbx
0x1400087f5  mov     [rsp+arg_10], rbp
0x1400087fa  push    rsi
0x1400087fb  push    rdi
0x1400087fc  push    r14
0x1400087fe  sub     rsp, 30h
0x140008802  xor     eax, eax
0x140008804  mov     r14, r8
0x140008807  mov     [r8], rax
0x14000880a  mov     bpl, dl
0x14000880d  mov     rsi, rcx
0x140008810  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x140008815  mov     rcx, cs:ConnTableLock; Lock
0x14000881c  lea     rdx, [rsp+48h+LockState]; LockState
0x140008821  xor     r8d, r8d; Flags
0x140008824  mov     [rsp+48h+LockState.Flags], al
0x140008828  mov     edi, 0C0000008h
0x14000882d  call    cs:__imp_NdisAcquireRWLockRead
0x140008834  nop     dword ptr [rax+rax+00h]
0x140008839  mov     rax, cs:ConnectionTable
0x140008840  cmp     esi, [rax+4]
0x140008843  jbe     short loc_14000888E
0x140008845  mov     rcx, cs:WPP_GLOBAL_Control
0x14000884c  lea     rax, WPP_GLOBAL_Control
0x140008853  cmp     rcx, rax
0x140008856  jz      loc_140008965
0x14000885c  mov     eax, [rcx+2Ch]
0x14000885f  test    al, 8
0x140008861  jz      loc_140008965
0x140008867  cmp     byte ptr [rcx+29h], 4
0x14000886b  jb      loc_140008965
0x140008871  mov     edx, 0Eh
0x140008876  mov     rcx, [rcx+18h]
0x14000887a  lea     r8, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids
0x140008881  mov     r9, rsi
0x140008884  call    WPP_SF_q
0x140008889  jmp     loc_140008965
0x14000888e  lfence
0x140008891  mov     rax, cs:ConnectionTable
0x140008898  mov     edx, esi
0x14000889a  mov     rcx, [rax+38h]
0x14000889e  mov     rbx, [rcx+rdx*8]
0x1400088a2  test    rbx, rbx
0x1400088a5  jnz     short loc_1400088D8
0x1400088a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088ae  lea     rax, WPP_GLOBAL_Control
0x1400088b5  cmp     rcx, rax
0x1400088b8  jz      loc_140008965
0x1400088be  mov     eax, [rcx+2Ch]
0x1400088c1  test    al, 8
0x1400088c3  jz      loc_140008965
0x1400088c9  cmp     byte ptr [rcx+29h], 4
0x1400088cd  jb      loc_140008965
0x1400088d3  lea     edx, [rbx+0Fh]
0x1400088d6  jmp     short loc_140008876
0x1400088d8  lea     rdi, [rbx+2E0h]
0x1400088df  mov     rcx, rdi; SpinLock
0x1400088e2  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400088e9  nop     dword ptr [rax+rax+00h]
0x1400088ee  test    bpl, bpl
0x1400088f1  jz      short loc_14000894E
0x1400088f3  mov     r8d, [rbx+14h]
0x1400088f7  cmp     r8d, 2
0x1400088fb  jz      short loc_14000894E
0x1400088fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140008904  lea     rax, WPP_GLOBAL_Control
0x14000890b  cmp     rcx, rax
0x14000890e  jz      short loc_140008938
0x140008910  mov     eax, [rcx+2Ch]
0x140008913  test    al, 8
0x140008915  jz      short loc_140008938
0x140008917  cmp     byte ptr [rcx+29h], 4
0x14000891b  jb      short loc_140008938
0x14000891d  mov     rcx, [rcx+18h]
0x140008921  mov     edx, 10h
0x140008926  mov     [rsp+48h+var_20], r8d
0x14000892b  mov     r9, rbx
0x14000892e  mov     [rsp+48h+var_28], rsi
0x140008933  call    WPP_SF_qqd
0x140008938  mov     rcx, rdi; SpinLock
0x14000893b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140008942  nop     dword ptr [rax+rax+00h]
0x140008947  mov     edi, 0C000009Dh
0x14000894c  jmp     short loc_140008965
0x14000894e  inc     dword ptr [rbx+1Ch]
0x140008951  mov     rcx, rdi; SpinLock
0x140008954  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000895b  nop     dword ptr [rax+rax+00h]
0x140008960  xor     edi, edi
0x140008962  mov     [r14], rbx
0x140008965  mov     rcx, cs:ConnTableLock; Lock
0x14000896c  lea     rdx, [rsp+48h+LockState]; LockState
0x140008971  call    cs:__imp_NdisReleaseRWLock
0x140008978  nop     dword ptr [rax+rax+00h]
0x14000897d  mov     rbx, [rsp+48h+arg_8]
0x140008982  mov     eax, edi
0x140008984  mov     rbp, [rsp+48h+arg_10]
0x140008989  add     rsp, 30h
0x14000898d  pop     r14
0x14000898f  pop     rdi
0x140008990  pop     rsi
0x140008991  retn
```
