# IsLinkValid

- ea: `0x140003060`
- end: `0x140003180`
- name: `IsLinkValid`
- size: `288`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
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

- `0x140003060`
- `0x14000a290`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400030d3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400030d3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400030ee`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003172`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400030ee`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003172`
- `NDIS!NdisAcquireRWLockRead` at `0x140003096`
- `NDIS!NdisAcquireRWLockRead` at `0x140003096`
- `NDIS!NdisReleaseRWLock` at `0x140003111`
- `NDIS!NdisReleaseRWLock` at `0x140003111`

## pseudocode

```c
__int64 __fastcall IsLinkValid(unsigned int a1, char a2, _QWORD *a3)
{
  unsigned __int8 v6; // si
  __int64 v7; // rbx
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+8h] BYREF

  *a3 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v6 = 0;
  NdisAcquireRWLockRead(ConnTableLock, &LockState, 0);
  if ( a1 <= *((_DWORD *)ConnectionTable + 1) )
  {
    _mm_lfence();
    v7 = *(_QWORD *)(*((_QWORD *)ConnectionTable + 7) + 8LL * a1);
    if ( v7 )
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v7 + 736));
      if ( !a2 || *(_DWORD *)(v7 + 20) == 2 )
      {
        ++*(_DWORD *)(v7 + 28);
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v7 + 736));
        *a3 = v7;
        v6 = 1;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids);
        }
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v7 + 736));
      }
    }
  }
  NdisReleaseRWLock(ConnTableLock, &LockState);
  return v6;
}

```

## disassembly

```asm
0x140003060  mov     [rsp+arg_10], rbx
0x140003065  push    rbp
0x140003066  push    rsi
0x140003067  push    r14
0x140003069  sub     rsp, 20h
0x14000306d  xor     eax, eax
0x14000306f  mov     r14, r8
0x140003072  mov     [r8], rax
0x140003075  movzx   ebp, dl
0x140003078  mov     rbx, rcx
0x14000307b  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x140003080  mov     rcx, cs:ConnTableLock; Lock
0x140003087  lea     rdx, [rsp+38h+LockState]; LockState
0x14000308c  xor     r8d, r8d; Flags
0x14000308f  mov     [rsp+38h+LockState.Flags], al
0x140003093  xor     sil, sil
0x140003096  call    cs:__imp_NdisAcquireRWLockRead
0x14000309d  nop     dword ptr [rax+rax+00h]
0x1400030a2  mov     rax, cs:ConnectionTable
0x1400030a9  cmp     ebx, [rax+4]
0x1400030ac  ja      short loc_140003105
0x1400030ae  lfence
0x1400030b1  mov     rax, cs:ConnectionTable
0x1400030b8  mov     ecx, ebx
0x1400030ba  mov     rbx, [rax+38h]
0x1400030be  mov     rbx, [rbx+rcx*8]
0x1400030c2  test    rbx, rbx
0x1400030c5  jz      short loc_140003105
0x1400030c7  lea     rcx, [rbx+2E0h]; SpinLock
0x1400030ce  mov     [rsp+38h+arg_8], rdi
0x1400030d3  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400030da  nop     dword ptr [rax+rax+00h]
0x1400030df  test    bpl, bpl
0x1400030e2  jnz     short loc_140003130
0x1400030e4  inc     dword ptr [rbx+1Ch]
0x1400030e7  lea     rcx, [rbx+2E0h]; SpinLock
0x1400030ee  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400030f5  nop     dword ptr [rax+rax+00h]
0x1400030fa  mov     [r14], rbx
0x1400030fd  mov     sil, 1
0x140003100  mov     rdi, [rsp+38h+arg_8]
0x140003105  mov     rcx, cs:ConnTableLock; Lock
0x14000310c  lea     rdx, [rsp+38h+LockState]; LockState
0x140003111  call    cs:__imp_NdisReleaseRWLock
0x140003118  nop     dword ptr [rax+rax+00h]
0x14000311d  mov     rbx, [rsp+38h+arg_10]
0x140003122  movzx   eax, sil
0x140003126  add     rsp, 20h
0x14000312a  pop     r14
0x14000312c  pop     rsi
0x14000312d  pop     rbp
0x14000312e  retn
0x140003130  cmp     dword ptr [rbx+14h], 2
0x140003134  jz      short loc_1400030E4
0x140003136  mov     rcx, cs:WPP_GLOBAL_Control
0x14000313d  lea     rax, WPP_GLOBAL_Control
0x140003144  cmp     rcx, rax
0x140003147  jz      short loc_14000316B
0x140003149  mov     eax, [rcx+2Ch]
0x14000314c  test    al, 8
0x14000314e  jz      short loc_14000316B
0x140003150  cmp     byte ptr [rcx+29h], 5
0x140003154  jb      short loc_14000316B
0x140003156  mov     rcx, [rcx+18h]
0x14000315a  lea     r8, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids
0x140003161  mov     edx, 0Ch
0x140003166  call    WPP_SF_
0x14000316b  lea     rcx, [rbx+2E0h]; SpinLock
0x140003172  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140003179  nop     dword ptr [rax+rax+00h]
0x14000317e  jmp     short loc_140003100
```
