# NbtDeleteLowerConn

- ea: `0x14001206c`
- end: `0x140012126`
- name: `NbtDeleteLowerConn`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011f50`

## callees

- `0x14001206c`
- `0x140013184`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012099`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012099`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012100`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012100`

## pseudocode

```c
__int64 __fastcall NbtDeleteLowerConn(__int64 a1)
{
  KSPIN_LOCK *v2; // rdi
  __int64 v3; // rdx
  KIRQL v4; // si
  __int64 v5; // r8
  __int64 v6; // rax
  _QWORD *v7; // rcx

  if ( *(_DWORD *)(a1 + 16) == 1131900748 )
  {
    v2 = (KSPIN_LOCK *)(*(_QWORD *)(a1 + 40) + 848LL);
    v4 = KeAcquireSpinLockRaiseToDpc(v2);
    if ( *(int *)(a1 + 20) <= 500 )
    {
      if ( (*(_BYTE *)(a1 + 120) & 2) == 0 )
      {
        v6 = *(_QWORD *)a1;
        if ( *(_QWORD *)(*(_QWORD *)a1 + 8LL) != a1 || (v7 = *(_QWORD **)(a1 + 8), *v7 != a1) )
          __fastfail(3u);
        *v7 = v6;
        *(_QWORD *)(v6 + 8) = v7;
        *(_BYTE *)(a1 + 120) |= 4u;
        *(_QWORD *)(a1 + 8) = 38793;
        *(_QWORD *)a1 = 38793;
      }
      NbtDereferenceLowerConnection(a1, v3, v5, 14, (__int64)"minio\\netbt\\sys\\name.c");
    }
    KeReleaseSpinLock(v2, v4);
  }
  return 0;
}

```

## disassembly

```asm
0x14001206c  mov     [rsp+arg_0], rbx
0x140012071  mov     [rsp+arg_8], rsi
0x140012076  push    rdi
0x140012077  sub     rsp, 30h
0x14001207b  cmp     dword ptr [rcx+10h], 43776F4Ch
0x140012082  mov     rbx, rcx
0x140012085  jnz     loc_14001210C
0x14001208b  mov     rdi, [rcx+28h]
0x14001208f  add     rdi, 350h
0x140012096  mov     rcx, rdi; SpinLock
0x140012099  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400120a0  nop     dword ptr [rax+rax+00h]
0x1400120a5  cmp     dword ptr [rbx+14h], 1F4h
0x1400120ac  mov     sil, al
0x1400120af  jg      short loc_1400120FA
0x1400120b1  test    byte ptr [rbx+78h], 2
0x1400120b5  jnz     short loc_1400120E0
0x1400120b7  mov     rax, [rbx]
0x1400120ba  cmp     [rax+8], rbx
0x1400120be  jnz     short loc_14001211F
0x1400120c0  mov     rcx, [rbx+8]
0x1400120c4  cmp     [rcx], rbx
0x1400120c7  jnz     short loc_14001211F
0x1400120c9  mov     [rcx], rax
0x1400120cc  mov     [rax+8], rcx
0x1400120d0  mov     eax, 9789h
0x1400120d5  or      byte ptr [rbx+78h], 4
0x1400120d9  mov     [rbx+8], rax
0x1400120dd  mov     [rbx], rax
0x1400120e0  lea     rax, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x1400120e7  mov     r9d, 2D0Eh
0x1400120ed  mov     rcx, rbx
0x1400120f0  mov     [rsp+38h+var_18], rax
0x1400120f5  call    NbtDereferenceLowerConnection
0x1400120fa  mov     dl, sil; NewIrql
0x1400120fd  mov     rcx, rdi; SpinLock
0x140012100  call    cs:__imp_KeReleaseSpinLock
0x140012107  nop     dword ptr [rax+rax+00h]
0x14001210c  mov     rbx, [rsp+38h+arg_0]
0x140012111  xor     eax, eax
0x140012113  mov     rsi, [rsp+38h+arg_8]
0x140012118  add     rsp, 30h
0x14001211c  pop     rdi
0x14001211d  retn
0x14001211f  mov     ecx, 3
0x140012124  int     29h; Win8: RtlFailFast(ecx)
```
