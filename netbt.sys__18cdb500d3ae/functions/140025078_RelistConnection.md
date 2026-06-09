# RelistConnection

- ea: `0x140025078`
- end: `0x14002513d`
- name: `RelistConnection`
- size: `197`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010f0`
- `0x14000efd4`
- `0x1400103e8`
- `0x1400182a0`
- `0x14001d460`
- `0x140020900`
- `0x140027c20`
- `0x140029d28`
- `0x14002a8c0`

## callees

- `0x140025078`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002509b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400250b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002509b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400250b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002510e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025120`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002510e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025120`

## pseudocode

```c
void __fastcall RelistConnection(__int64 *a1)
{
  __int64 v1; // rax
  KSPIN_LOCK *v3; // rdi
  KIRQL v4; // bp
  KIRQL v5; // r8
  KSPIN_LOCK v6; // rcx
  __int64 **v7; // rdx
  __int64 v8; // rax
  __int64 **v9; // rcx

  v1 = a1[5];
  if ( v1 )
  {
    v3 = (KSPIN_LOCK *)(v1 + 264);
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 264));
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 31);
    if ( *((_DWORD *)a1 + 12) )
    {
      *((_DWORD *)a1 + 12) = 1;
      v6 = *a1;
      if ( *(__int64 **)(*a1 + 8) != a1
        || (v7 = (__int64 **)a1[1], *v7 != a1)
        || (*v7 = (__int64 *)v6,
            *(_QWORD *)(v6 + 8) = v7,
            v8 = a1[5] + 72,
            v9 = *(__int64 ***)(a1[5] + 80),
            *v9 != (__int64 *)v8) )
      {
        __fastfail(3u);
      }
      *a1 = v8;
      a1[1] = (__int64)v9;
      *v9 = a1;
      *(_QWORD *)(v8 + 8) = a1;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 31, v5);
    KeReleaseSpinLock(v3, v4);
  }
}

```

## disassembly

```asm
0x140025078  push    rbx
0x14002507a  push    rbp
0x14002507b  push    rsi
0x14002507c  push    rdi
0x14002507d  sub     rsp, 28h
0x140025081  mov     rax, [rcx+28h]
0x140025085  mov     rbx, rcx
0x140025088  test    rax, rax
0x14002508b  jz      loc_14002512C
0x140025091  lea     rdi, [rax+108h]
0x140025098  mov     rcx, rdi; SpinLock
0x14002509b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400250a2  nop     dword ptr [rax+rax+00h]
0x1400250a7  lea     rsi, [rbx+0F8h]
0x1400250ae  mov     bpl, al
0x1400250b1  mov     rcx, rsi; SpinLock
0x1400250b4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400250bb  nop     dword ptr [rax+rax+00h]
0x1400250c0  cmp     dword ptr [rbx+30h], 0
0x1400250c4  mov     r8b, al
0x1400250c7  jz      short loc_140025108
0x1400250c9  mov     dword ptr [rbx+30h], 1
0x1400250d0  mov     rcx, [rbx]
0x1400250d3  cmp     [rcx+8], rbx
0x1400250d7  jnz     short loc_140025136
0x1400250d9  mov     rdx, [rbx+8]
0x1400250dd  cmp     [rdx], rbx
0x1400250e0  jnz     short loc_140025136
0x1400250e2  mov     [rdx], rcx
0x1400250e5  mov     [rcx+8], rdx
0x1400250e9  mov     rax, [rbx+28h]
0x1400250ed  add     rax, 48h ; 'H'
0x1400250f1  mov     rcx, [rax+8]
0x1400250f5  cmp     [rcx], rax
0x1400250f8  jnz     short loc_140025136
0x1400250fa  mov     [rbx], rax
0x1400250fd  mov     [rbx+8], rcx
0x140025101  mov     [rcx], rbx
0x140025104  mov     [rax+8], rbx
0x140025108  mov     dl, r8b; NewIrql
0x14002510b  mov     rcx, rsi; SpinLock
0x14002510e  call    cs:__imp_KeReleaseSpinLock
0x140025115  nop     dword ptr [rax+rax+00h]
0x14002511a  mov     dl, bpl; NewIrql
0x14002511d  mov     rcx, rdi; SpinLock
0x140025120  call    cs:__imp_KeReleaseSpinLock
0x140025127  nop     dword ptr [rax+rax+00h]
0x14002512c  add     rsp, 28h
0x140025130  pop     rdi
0x140025131  pop     rsi
0x140025132  pop     rbp
0x140025133  pop     rbx
0x140025134  retn
0x140025136  mov     ecx, 3
0x14002513b  int     29h; Win8: RtlFailFast(ecx)
```
