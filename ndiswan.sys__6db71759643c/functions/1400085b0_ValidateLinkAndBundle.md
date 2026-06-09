# ValidateLinkAndBundle

- ea: `0x1400085b0`
- end: `0x1400087e9`
- name: `ValidateLinkAndBundle`
- size: `569`
- prototype: ``
- caller_count: `17`
- callee_count: `4`
- tags: ``

## callers

- `0x140004be0`
- `0x140007560`
- `0x140007710`
- `0x140007bf0`
- `0x140007fb0`
- `0x140024008`
- `0x140025070`
- `0x1400267f4`
- `0x140026970`
- `0x1400274e0`
- `0x140027da0`
- `0x140027fe0`
- `0x140028f60`
- `0x14002a0f0`
- `0x14002aa40`
- `0x14002b270`
- `0x14002bab0`

## callees

- `0x1400085b0`
- `0x14000a648`
- `0x14000a744`
- `0x140010ff8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400086ad`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000878e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400086ad`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000878e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008706`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008764`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008778`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400087a0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008706`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008764`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008778`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400087a0`
- `NDIS!NdisAcquireRWLockRead` at `0x1400085f8`
- `NDIS!NdisAcquireRWLockRead` at `0x1400085f8`
- `NDIS!NdisReleaseRWLock` at `0x1400087c2`
- `NDIS!NdisReleaseRWLock` at `0x1400087c2`

## pseudocode

```c
__int64 __fastcall ValidateLinkAndBundle(__int64 a1, char a2, _QWORD *a3, _QWORD *a4)
{
  struct _NDIS_RW_LOCK_EX *v7; // rcx
  unsigned int v9; // r14d
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // r8
  __int64 v14; // rbp
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+8h] BYREF

  *a3 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  v7 = ConnTableLock;
  LockState.Flags = 0;
  *a4 = 0;
  v9 = -1073741816;
  NdisAcquireRWLockRead(v7, &LockState, 0);
  if ( (unsigned int)a1 <= *((_DWORD *)ConnectionTable + 1) )
  {
    _mm_lfence();
    v12 = *(_QWORD *)(*((_QWORD *)ConnectionTable + 7) + 8LL * (unsigned int)a1);
    if ( v12 )
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v12 + 736));
      if ( !a2 || (v13 = *(unsigned int *)(v12 + 20), (_DWORD)v13 == 2) )
      {
        v14 = *(_QWORD *)(v12 + 80);
        if ( v14 )
        {
          ++*(_DWORD *)(v12 + 28);
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v12 + 736));
          KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v14 + 1768));
          ++*(_DWORD *)(v14 + 24);
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v14 + 1768));
          v9 = 0;
          *a3 = v12;
          *a4 = v14;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids, v12, a1);
          }
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v12 + 736));
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 22, v13, v12, a1, *(_DWORD *)(v12 + 20));
        }
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v12 + 736));
        v9 = -1073741667;
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v11 = 21;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v11 = 20;
LABEL_6:
      WPP_SF_q(v10->AttachedDevice, v11, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids, a1);
    }
  }
  NdisReleaseRWLock(ConnTableLock, &LockState);
  return v9;
}

```

## disassembly

```asm
0x1400085b0  mov     [rsp+arg_8], rbx
0x1400085b5  mov     [rsp+arg_10], rbp
0x1400085ba  push    rsi
0x1400085bb  push    rdi
0x1400085bc  push    r12
0x1400085be  push    r14
0x1400085c0  push    r15
0x1400085c2  sub     rsp, 30h
0x1400085c6  xor     eax, eax
0x1400085c8  mov     r12, r8
0x1400085cb  mov     [r8], rax
0x1400085ce  mov     bpl, dl
0x1400085d1  mov     rsi, rcx
0x1400085d4  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x1400085d9  mov     rcx, cs:ConnTableLock; Lock
0x1400085e0  lea     rdx, [rsp+58h+LockState]; LockState
0x1400085e5  xor     r8d, r8d; Flags
0x1400085e8  mov     [rsp+58h+LockState.Flags], al
0x1400085ec  mov     r15, r9
0x1400085ef  mov     [r9], rax
0x1400085f2  mov     r14d, 0C0000008h
0x1400085f8  call    cs:__imp_NdisAcquireRWLockRead
0x1400085ff  nop     dword ptr [rax+rax+00h]
0x140008604  mov     rax, cs:ConnectionTable
0x14000860b  cmp     esi, [rax+4]
0x14000860e  jbe     short loc_140008659
0x140008610  mov     rcx, cs:WPP_GLOBAL_Control
0x140008617  lea     rax, WPP_GLOBAL_Control
0x14000861e  cmp     rcx, rax
0x140008621  jz      loc_1400087B6
0x140008627  mov     eax, [rcx+2Ch]
0x14000862a  test    al, 8
0x14000862c  jz      loc_1400087B6
0x140008632  cmp     byte ptr [rcx+29h], 4
0x140008636  jb      loc_1400087B6
0x14000863c  mov     edx, 14h
0x140008641  mov     rcx, [rcx+18h]
0x140008645  lea     r8, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids
0x14000864c  mov     r9, rsi
0x14000864f  call    WPP_SF_q
0x140008654  jmp     loc_1400087B6
0x140008659  lfence
0x14000865c  mov     rax, cs:ConnectionTable
0x140008663  mov     edx, esi
0x140008665  mov     rcx, [rax+38h]
0x140008669  mov     rdi, [rcx+rdx*8]
0x14000866d  test    rdi, rdi
0x140008670  jnz     short loc_1400086A3
0x140008672  mov     rcx, cs:WPP_GLOBAL_Control
0x140008679  lea     rax, WPP_GLOBAL_Control
0x140008680  cmp     rcx, rax
0x140008683  jz      loc_1400087B6
0x140008689  mov     eax, [rcx+2Ch]
0x14000868c  test    al, 8
0x14000868e  jz      loc_1400087B6
0x140008694  cmp     byte ptr [rcx+29h], 4
0x140008698  jb      loc_1400087B6
0x14000869e  lea     edx, [rdi+15h]
0x1400086a1  jmp     short loc_140008641
0x1400086a3  lea     rbx, [rdi+2E0h]
0x1400086aa  mov     rcx, rbx; SpinLock
0x1400086ad  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400086b4  nop     dword ptr [rax+rax+00h]
0x1400086b9  test    bpl, bpl
0x1400086bc  jz      short loc_14000871D
0x1400086be  mov     r8d, [rdi+14h]
0x1400086c2  cmp     r8d, 2
0x1400086c6  jz      short loc_14000871D
0x1400086c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086cf  lea     rax, WPP_GLOBAL_Control
0x1400086d6  cmp     rcx, rax
0x1400086d9  jz      short loc_140008703
0x1400086db  mov     eax, [rcx+2Ch]
0x1400086de  test    al, 8
0x1400086e0  jz      short loc_140008703
0x1400086e2  cmp     byte ptr [rcx+29h], 4
0x1400086e6  jb      short loc_140008703
0x1400086e8  mov     rcx, [rcx+18h]
0x1400086ec  mov     edx, 16h
0x1400086f1  mov     [rsp+58h+var_30], r8d
0x1400086f6  mov     r9, rdi
0x1400086f9  mov     [rsp+58h+var_38], rsi
0x1400086fe  call    WPP_SF_qqd
0x140008703  mov     rcx, rbx; SpinLock
0x140008706  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000870d  nop     dword ptr [rax+rax+00h]
0x140008712  mov     r14d, 0C000009Dh
0x140008718  jmp     loc_1400087B6
0x14000871d  mov     rbp, [rdi+50h]
0x140008721  test    rbp, rbp
0x140008724  jnz     short loc_140008772
0x140008726  mov     rcx, cs:WPP_GLOBAL_Control
0x14000872d  lea     rax, WPP_GLOBAL_Control
0x140008734  cmp     rcx, rax
0x140008737  jz      short loc_140008761
0x140008739  mov     eax, [rcx+2Ch]
0x14000873c  test    al, 8
0x14000873e  jz      short loc_140008761
0x140008740  cmp     byte ptr [rcx+29h], 4
0x140008744  jb      short loc_140008761
0x140008746  mov     rcx, [rcx+18h]
0x14000874a  lea     edx, [rbp+17h]
0x14000874d  mov     r9, rdi
0x140008750  mov     [rsp+58h+var_38], rsi
0x140008755  lea     r8, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids
0x14000875c  call    WPP_SF_qq
0x140008761  mov     rcx, rbx; SpinLock
0x140008764  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000876b  nop     dword ptr [rax+rax+00h]
0x140008770  jmp     short loc_1400087B6
0x140008772  inc     dword ptr [rdi+1Ch]
0x140008775  mov     rcx, rbx; SpinLock
0x140008778  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000877f  nop     dword ptr [rax+rax+00h]
0x140008784  lea     rbx, [rbp+6E8h]
0x14000878b  mov     rcx, rbx; SpinLock
0x14000878e  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140008795  nop     dword ptr [rax+rax+00h]
0x14000879a  inc     dword ptr [rbp+18h]
0x14000879d  mov     rcx, rbx; SpinLock
0x1400087a0  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400087a7  nop     dword ptr [rax+rax+00h]
0x1400087ac  xor     r14d, r14d
0x1400087af  mov     [r12], rdi
0x1400087b3  mov     [r15], rbp
0x1400087b6  mov     rcx, cs:ConnTableLock; Lock
0x1400087bd  lea     rdx, [rsp+58h+LockState]; LockState
0x1400087c2  call    cs:__imp_NdisReleaseRWLock
0x1400087c9  nop     dword ptr [rax+rax+00h]
0x1400087ce  mov     rbx, [rsp+58h+arg_8]
0x1400087d3  mov     eax, r14d
0x1400087d6  mov     rbp, [rsp+58h+arg_10]
0x1400087db  add     rsp, 30h
0x1400087df  pop     r15
0x1400087e1  pop     r14
0x1400087e3  pop     r12
0x1400087e5  pop     rdi
0x1400087e6  pop     rsi
0x1400087e7  retn
```
