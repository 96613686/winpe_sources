# PxClDeregisterSapComplete

- ea: `0x14000f750`
- end: `0x14000f81c`
- name: `PxClDeregisterSapComplete`
- size: `204`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400011b0`
- `0x140003940`
- `0x1400100b0`
- `0x140011850`
- `0x140014ca0`

## callees

- `0x140001c0c`
- `0x1400078f0`
- `0x140007c50`
- `0x14000f750`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f7a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f7a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f7eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f7eb`

## pseudocode

```c
__int64 __fastcall PxClDeregisterSapComplete(int a1, void *a2)
{
  __int64 v2; // rdi
  _QWORD *v4; // rcx
  void **v5; // rax

  v2 = *((_QWORD *)a2 + 4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids, a2, a1);
  *(_BYTE *)(v2 + 192) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 184));
  v4 = *(_QWORD **)a2;
  if ( *(void **)(*(_QWORD *)a2 + 8LL) != a2 || (v5 = (void **)*((_QWORD *)a2 + 1), *v5 != a2) )
    __fastfail(3u);
  *v5 = v4;
  v4[1] = v5;
  if ( (*(_DWORD *)(v2 + 20))-- == 1 )
    DoDerefClAfWork(v2);
  else
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 184), *(_BYTE *)(v2 + 192));
  _InterlockedExchange((volatile __int32 *)a2 + 4, 0);
  return PxFreeClSap(a2);
}

```

## disassembly

```asm
0x14000f750  mov     [rsp+arg_0], rbx
0x14000f755  mov     [rsp+arg_10], rsi
0x14000f75a  push    rdi
0x14000f75b  sub     rsp, 30h
0x14000f75f  mov     rdi, [rdx+20h]
0x14000f763  mov     rbx, rdx
0x14000f766  mov     eax, ecx
0x14000f768  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f76f  lea     rdx, WPP_GLOBAL_Control
0x14000f776  cmp     rcx, rdx
0x14000f779  jz      short loc_14000F79D
0x14000f77b  cmp     byte ptr [rcx+29h], 5
0x14000f77f  jb      short loc_14000F79D
0x14000f781  mov     rcx, [rcx+18h]
0x14000f785  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000f78c  mov     edx, 18h
0x14000f791  mov     [rsp+38h+var_18], eax
0x14000f795  mov     r9, rbx
0x14000f798  call    WPP_SF_qD
0x14000f79d  lea     rsi, [rdi+0B8h]
0x14000f7a4  mov     rcx, rsi; SpinLock
0x14000f7a7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f7ae  nop     dword ptr [rax+rax+00h]
0x14000f7b3  mov     [rdi+0C0h], al
0x14000f7b9  mov     rcx, [rbx]
0x14000f7bc  cmp     [rcx+8], rbx
0x14000f7c0  jnz     short loc_14000F815
0x14000f7c2  mov     rax, [rbx+8]
0x14000f7c6  cmp     [rax], rbx
0x14000f7c9  jnz     short loc_14000F815
0x14000f7cb  mov     [rax], rcx
0x14000f7ce  mov     [rcx+8], rax
0x14000f7d2  add     dword ptr [rdi+14h], 0FFFFFFFFh
0x14000f7d6  jnz     short loc_14000F7E2
0x14000f7d8  mov     rcx, rdi
0x14000f7db  call    DoDerefClAfWork
0x14000f7e0  jmp     short loc_14000F7F7
0x14000f7e2  mov     dl, [rdi+0C0h]; NewIrql
0x14000f7e8  mov     rcx, rsi; SpinLock
0x14000f7eb  call    cs:__imp_KeReleaseSpinLock
0x14000f7f2  nop     dword ptr [rax+rax+00h]
0x14000f7f7  xor     eax, eax
0x14000f7f9  mov     rcx, rbx; P
0x14000f7fc  xchg    eax, [rbx+10h]
0x14000f7ff  call    PxFreeClSap
0x14000f804  mov     rbx, [rsp+38h+arg_0]
0x14000f809  mov     rsi, [rsp+38h+arg_10]
0x14000f80e  add     rsp, 30h
0x14000f812  pop     rdi
0x14000f813  retn
0x14000f815  mov     ecx, 3
0x14000f81a  int     29h; Win8: RtlFailFast(ecx)
```
