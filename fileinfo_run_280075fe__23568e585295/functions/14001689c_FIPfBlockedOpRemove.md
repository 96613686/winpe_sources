# FIPfBlockedOpRemove

- ea: `0x14001689c`
- end: `0x140016909`
- name: `FIPfBlockedOpRemove`
- size: `109`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140010350`
- `0x140015a48`
- `0x140015d3c`
- `0x14001606c`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x14001689c`

## pseudocode

```c
__int64 __fastcall FIPfBlockedOpRemove(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  __int64 v3; // rcx
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  __int64 v7; // rdx
  _QWORD *v8; // rax

  v3 = *a3;
  if ( *(_QWORD **)(*a3 + 8LL) != a3 )
    goto LABEL_6;
  v5 = (_QWORD *)a3[1];
  if ( (_QWORD *)*v5 != a3
    || (*v5 = v3,
        *(_QWORD *)(v3 + 8) = v5,
        --*a2,
        FILockExclusiveAcquire(&qword_140009578),
        v6 = a3 + 2,
        v7 = *v6,
        *(_QWORD **)(*v6 + 8LL) != v6)
    || (v8 = (_QWORD *)v6[1], (_QWORD *)*v8 != v6) )
  {
LABEL_6:
    __fastfail(3u);
  }
  *v8 = v7;
  *(_QWORD *)(v7 + 8) = v8;
  --dword_140009590;
  return FILockExclusiveRelease(&qword_140009578);
}

```

## disassembly

```asm
0x14001689c  push    rbx
0x14001689e  sub     rsp, 20h
0x1400168a2  mov     rcx, [r8]
0x1400168a5  mov     rbx, r8
0x1400168a8  cmp     [rcx+8], r8
0x1400168ac  jnz     short loc_140016902
0x1400168ae  mov     rax, [r8+8]
0x1400168b2  cmp     [rax], rbx
0x1400168b5  jnz     short loc_140016902
0x1400168b7  mov     [rax], rcx
0x1400168ba  mov     [rcx+8], rax
0x1400168be  lea     rcx, qword_140009578
0x1400168c5  dec     dword ptr [rdx]
0x1400168c7  call    FILockExclusiveAcquire
0x1400168cc  add     rbx, 10h
0x1400168d0  mov     rdx, [rbx]
0x1400168d3  cmp     [rdx+8], rbx
0x1400168d7  jnz     short loc_140016902
0x1400168d9  mov     rax, [rbx+8]
0x1400168dd  cmp     [rax], rbx
0x1400168e0  jnz     short loc_140016902
0x1400168e2  mov     [rax], rdx
0x1400168e5  lea     rcx, qword_140009578
0x1400168ec  mov     [rdx+8], rax
0x1400168f0  dec     cs:dword_140009590
0x1400168f6  call    FILockExclusiveRelease
0x1400168fb  add     rsp, 20h
0x1400168ff  pop     rbx
0x140016900  retn
0x140016902  mov     ecx, 3
0x140016907  int     29h; Win8: RtlFailFast(ecx)
```
