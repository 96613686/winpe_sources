# FltpDeleteTxVolContextList

- ea: `0x180070b30`
- end: `0x180070bec`
- name: `FltpDeleteTxVolContextList`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180068e20`

## callees

- `0x180009f20`
- `0x180012d80`
- `0x18004fbf0`
- `0x18005dcc0`
- `0x180060e10`
- `0x180070b30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18007ae9c`
- `ntoskrnl!ObfDereferenceObject` at `0x18007ae9c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180070b3d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180070b3d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180070b8b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180070b8b`
- `ntoskrnl!ZwClose` at `0x18007aeac`
- `ntoskrnl!ZwClose` at `0x18007aeac`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x180070b55`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x180070b55`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180070b7f`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180070b7f`
- `ntoskrnl!TmReadOnlyEnlistment` at `0x18007ae70`
- `ntoskrnl!TmReadOnlyEnlistment` at `0x18007ae70`

## pseudocode

```c
void __fastcall FltpDeleteTxVolContextList(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rbx
  struct _KENLISTMENT *v7; // rcx
  unsigned int OnlyEnlistment; // eax
  __int64 v9; // rcx

  KeEnterGuardedRegion();
  ExAcquireAutoExpandPushLockExclusive(a1 + 2040, 0);
  v2 = TreeUnlinkMulti((_QWORD *)(a1 + 2056), 0xFFFFFFFFFFFFFFFFuLL, -1);
  v3 = a1 + 2040;
  v4 = v2;
  ExReleaseAutoExpandPushLockExclusive(v3, 0);
  KeLeaveGuardedRegion();
  if ( v4 )
  {
    do
    {
      v5 = *(_QWORD *)(v4 + 16);
      v6 = v4 - 88;
      v7 = *(struct _KENLISTMENT **)(v6 + 24);
      if ( v7 == (struct _KENLISTMENT *)-1LL )
      {
        FltpObjectPointerDereference(*(_QWORD *)(v6 + 8));
      }
      else
      {
        OnlyEnlistment = TmReadOnlyEnlistment(v7, 0);
        if ( (int)FltpDbgStatus(OnlyEnlistment, "minkernel\\fs\\filtermgr\\filter\\txvolcontextsup.c", 1344, 0) < 0 )
        {
          if ( (*(_DWORD *)(v6 + 148) & 8) == 0 )
            _InterlockedOr((volatile signed __int32 *)(v6 + 148), 8u);
        }
        else
        {
          ObfDereferenceObject(*(PVOID *)(v6 + 24));
          ZwClose(*(HANDLE *)(v6 + 16));
          v9 = *(_QWORD *)(v6 + 8);
          *(_QWORD *)(v6 + 24) = -1;
          *(_QWORD *)(v6 + 16) = 0;
          FltpObjectPointerDereference(v9);
          FltpReleaseTxVolContext((PVOID)v6);
        }
      }
      FltpFreeTxVolStreamListCtrlEntries(v6);
      FltpReleaseTxVolContext((PVOID)v6);
      v4 = v5;
    }
    while ( v5 );
  }
}

```

## disassembly

```asm
0x180070b30  mov     [rsp+arg_8], rbx
0x180070b35  push    rdi
0x180070b36  sub     rsp, 20h
0x180070b3a  mov     rbx, rcx
0x180070b3d  call    cs:__imp_KeEnterGuardedRegion
0x180070b44  nop     dword ptr [rax+rax+00h]
0x180070b49  lea     rdi, [rbx+7F8h]
0x180070b50  xor     edx, edx
0x180070b52  mov     rcx, rdi
0x180070b55  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x180070b5c  nop     dword ptr [rax+rax+00h]
0x180070b61  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180070b68  lea     rcx, [rbx+808h]
0x180070b6f  mov     r8, rdx
0x180070b72  call    TreeUnlinkMulti
0x180070b77  xor     edx, edx
0x180070b79  mov     rcx, rdi
0x180070b7c  mov     rbx, rax
0x180070b7f  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x180070b86  nop     dword ptr [rax+rax+00h]
0x180070b8b  call    cs:__imp_KeLeaveGuardedRegion
0x180070b92  nop     dword ptr [rax+rax+00h]
0x180070b97  test    rbx, rbx
0x180070b9a  jnz     short loc_180070BDD
0x180070b9c  mov     rbx, [rsp+28h+arg_8]
0x180070ba1  add     rsp, 20h
0x180070ba5  pop     rdi
0x180070ba6  retn
0x180070ba8  mov     eax, [rbx+94h]
0x180070bae  test    al, 8
0x180070bb0  jnz     short loc_180070BBA
0x180070bb2  lock or dword ptr [rbx+94h], 8
0x180070bba  mov     rcx, rbx
0x180070bbd  call    FltpFreeTxVolStreamListCtrlEntries
0x180070bc2  mov     rcx, rbx; Entry
0x180070bc5  call    FltpReleaseTxVolContext
0x180070bca  mov     rbx, rdi
0x180070bcd  test    rdi, rdi
0x180070bd0  jnz     loc_18007AE5C
0x180070bd6  mov     rsi, [rsp+28h+arg_0]
0x180070bdb  jmp     short loc_180070B9C
0x180070bdd  mov     [rsp+28h+arg_0], rsi
0x180070be2  mov     esi, 540h
0x180070be7  jmp     loc_18007AE5C
0x18007ae5c  mov     rdi, [rbx+10h]
0x18007ae60  add     rbx, 0FFFFFFFFFFFFFFA8h
0x18007ae64  mov     rcx, [rbx+18h]; Enlistment
0x18007ae68  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18007ae6c  jz      short loc_18007AEDF
0x18007ae6e  xor     edx, edx; TmVirtualClock
0x18007ae70  call    cs:__imp_TmReadOnlyEnlistment
0x18007ae77  nop     dword ptr [rax+rax+00h]
0x18007ae7c  xor     r9d, r9d
0x18007ae7f  lea     rdx, aMinkernelFsFil_26; "minkernel\\fs\\filtermgr\\filter\\txvol"...
0x18007ae86  mov     ecx, eax
0x18007ae88  mov     r8d, esi
0x18007ae8b  call    FltpDbgStatus
0x18007ae90  test    eax, eax
0x18007ae92  js      loc_180070BA8
0x18007ae98  mov     rcx, [rbx+18h]; Object
0x18007ae9c  call    cs:__imp_ObfDereferenceObject
0x18007aea3  nop     dword ptr [rax+rax+00h]
0x18007aea8  mov     rcx, [rbx+10h]; Handle
0x18007aeac  call    cs:__imp_ZwClose
0x18007aeb3  nop     dword ptr [rax+rax+00h]
0x18007aeb8  mov     rcx, [rbx+8]
0x18007aebc  mov     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18007aec4  mov     qword ptr [rbx+10h], 0
0x18007aecc  call    FltpObjectPointerDereference
0x18007aed1  mov     rcx, rbx; Entry
0x18007aed4  call    FltpReleaseTxVolContext
0x18007aed9  nop
0x18007aeda  jmp     loc_180070BBA
0x18007aedf  mov     rcx, [rbx+8]
0x18007aee3  call    FltpObjectPointerDereference
0x18007aee8  nop
0x18007aee9  jmp     loc_180070BBA
```
