# RemoveLinkFromBundle

- ea: `0x140005930`
- end: `0x1400059ce`
- name: `RemoveLinkFromBundle`
- size: `158`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000550c`
- `0x14000a310`
- `0x140024008`
- `0x1400274e0`

## callees

- `0x140005494`
- `0x140005930`
- `0x140007364`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400059b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400059b9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000594c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000594c`

## pseudocode

```c
void __fastcall RemoveLinkFromBundle(__int64 Entry, _QWORD *a2, char a3)
{
  __int64 v5; // rax
  _QWORD *v6; // rcx

  if ( !a3 )
    *(_BYTE *)(Entry + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(Entry + 1768));
  v5 = *a2;
  if ( *(_QWORD **)(*a2 + 8LL) != a2 || (v6 = (_QWORD *)a2[1], (_QWORD *)*v6 != a2) )
    __fastfail(3u);
  *v6 = v5;
  *(_QWORD *)(v5 + 8) = v6;
  a2[10] = 0;
  --*(_DWORD *)(Entry + 64);
  --*(_DWORD *)(Entry + 156);
  UpdateBundleInfo(Entry);
  if ( (*(_DWORD *)(Entry + 24))-- == 1 )
    DoDerefBundleCBWork((PVOID)Entry);
  else
    KeReleaseSpinLock((PKSPIN_LOCK)(Entry + 1768), *(_BYTE *)(Entry + 1776));
}

```

## disassembly

```asm
0x140005930  mov     [rsp+arg_0], rbx
0x140005935  push    rdi
0x140005936  sub     rsp, 20h
0x14000593a  mov     rdi, rdx
0x14000593d  mov     rbx, rcx
0x140005940  test    r8b, r8b
0x140005943  jnz     short loc_14000595E
0x140005945  add     rcx, 6E8h; SpinLock
0x14000594c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005953  nop     dword ptr [rax+rax+00h]
0x140005958  mov     [rbx+6F0h], al
0x14000595e  mov     rax, [rdi]
0x140005961  cmp     [rax+8], rdi
0x140005965  jnz     short loc_1400059C7
0x140005967  mov     rcx, [rdi+8]
0x14000596b  cmp     [rcx], rdi
0x14000596e  jnz     short loc_1400059C7
0x140005970  mov     [rcx], rax
0x140005973  mov     [rax+8], rcx
0x140005977  mov     rcx, rbx
0x14000597a  mov     qword ptr [rdi+50h], 0
0x140005982  or      edi, 0FFFFFFFFh
0x140005985  add     [rbx+40h], edi
0x140005988  add     [rbx+9Ch], edi
0x14000598e  call    UpdateBundleInfo
0x140005993  add     [rbx+18h], edi
0x140005996  jnz     short loc_1400059AC
0x140005998  mov     rcx, rbx; Entry
0x14000599b  call    DoDerefBundleCBWork
0x1400059a0  mov     rbx, [rsp+28h+arg_0]
0x1400059a5  add     rsp, 20h
0x1400059a9  pop     rdi
0x1400059aa  retn
0x1400059ac  mov     dl, [rbx+6F0h]; NewIrql
0x1400059b2  lea     rcx, [rbx+6E8h]; SpinLock
0x1400059b9  call    cs:__imp_KeReleaseSpinLock
0x1400059c0  nop     dword ptr [rax+rax+00h]
0x1400059c5  jmp     short loc_1400059A0
0x1400059c7  mov     ecx, 3
0x1400059cc  int     29h; Win8: RtlFailFast(ecx)
```
