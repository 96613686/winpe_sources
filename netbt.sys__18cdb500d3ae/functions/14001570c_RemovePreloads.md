# RemovePreloads

- ea: `0x14001570c`
- end: `0x140015810`
- name: `RemovePreloads`
- size: `260`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14004d390`

## callees

- `0x140007ff8`
- `0x140008110`
- `0x14001570c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015738`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015738`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015777`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015777`

## pseudocode

```c
_QWORD **RemovePreloads()
{
  _DWORD *v0; // rbx
  KIRQL v1; // al
  int v2; // r10d
  KIRQL i; // r14
  __int64 **v4; // r9
  __int64 *v5; // r8
  _QWORD **result; // rax
  __int64 v7; // rdi
  _QWORD *v8; // r8
  _QWORD *v9; // r11
  PVOID v10; // rcx
  PVOID *v11; // rax
  _QWORD *v12; // [rsp+20h] [rbp-10h] BYREF
  PVOID P; // [rsp+28h] [rbp-8h]

  v0 = qword_140039468;
  P = &v12;
  v12 = &v12;
  v1 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v2 = 0;
  for ( i = v1; v2 < *v0; ++v2 )
  {
    v4 = (__int64 **)&v0[4 * v2 + 2];
    v5 = *v4;
    if ( *v4 != (__int64 *)v4 )
    {
      do
      {
        v7 = *v5;
        if ( (v5[9] & 0x800) != 0 && *((_DWORD *)v5 + 5) == 2 )
        {
          NbtUnlinkNameFromHashTable(v5);
          v9 = P;
          if ( *(_QWORD ***)P != &v12 )
LABEL_16:
            __fastfail(3u);
          v8[1] = P;
          *v8 = &v12;
          *v9 = v8;
          P = v8;
        }
        v5 = (__int64 *)v7;
      }
      while ( (__int64 **)v7 != v4 );
    }
  }
  KeReleaseSpinLock(&SpinLock, i);
  while ( 1 )
  {
    result = &v12;
    if ( v12 == &v12 )
      return result;
    v10 = P;
    if ( *(_QWORD ***)P != &v12 )
      goto LABEL_16;
    v11 = (PVOID *)*((_QWORD *)P + 1);
    if ( *v11 != P )
      goto LABEL_16;
    P = (PVOID)*((_QWORD *)P + 1);
    *v11 = &v12;
    NbtFreeNameAddr(v10);
  }
}

```

## disassembly

```asm
0x14001570c  push    rbp
0x14001570e  push    rbx
0x14001570f  push    rsi
0x140015710  push    rdi
0x140015711  push    r14
0x140015713  mov     rbp, rsp
0x140015716  sub     rsp, 30h
0x14001571a  mov     rbx, cs:qword_140039468
0x140015721  lea     rax, [rbp+var_10]
0x140015725  mov     [rbp+P], rax
0x140015729  lea     rcx, SpinLock; SpinLock
0x140015730  lea     rax, [rbp+var_10]
0x140015734  mov     [rbp+var_10], rax
0x140015738  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001573f  nop     dword ptr [rax+rax+00h]
0x140015744  xor     r10d, r10d
0x140015747  mov     r14b, al
0x14001574a  cmp     [rbx], r10d
0x14001574d  jle     short loc_14001576D
0x14001574f  lea     rsi, [rbx+8]
0x140015753  movsxd  r9, r10d
0x140015756  shl     r9, 4
0x14001575a  add     r9, rsi
0x14001575d  mov     r8, [r9]
0x140015760  cmp     r8, r9
0x140015763  jnz     short loc_140015799
0x140015765  inc     r10d
0x140015768  cmp     r10d, [rbx]
0x14001576b  jl      short loc_140015753
0x14001576d  mov     dl, r14b; NewIrql
0x140015770  lea     rcx, SpinLock; SpinLock
0x140015777  call    cs:__imp_KeReleaseSpinLock
0x14001577e  nop     dword ptr [rax+rax+00h]
0x140015783  lea     rax, [rbp+var_10]
0x140015787  cmp     [rbp+var_10], rax
0x14001578b  jnz     short loc_1400157DE
0x14001578d  add     rsp, 30h
0x140015791  pop     r14
0x140015793  pop     rdi
0x140015794  pop     rsi
0x140015795  pop     rbx
0x140015796  pop     rbp
0x140015797  retn
0x140015799  test    dword ptr [r8+48h], 800h
0x1400157a1  mov     rdi, [r8]
0x1400157a4  jz      short loc_1400157D4
0x1400157a6  cmp     dword ptr [r8+14h], 2
0x1400157ab  jnz     short loc_1400157D4
0x1400157ad  mov     rcx, r8
0x1400157b0  call    NbtUnlinkNameFromHashTable
0x1400157b5  mov     r11, [rbp+P]
0x1400157b9  lea     rax, [rbp+var_10]
0x1400157bd  cmp     [r11], rax
0x1400157c0  jnz     short loc_140015809
0x1400157c2  mov     [r8+8], r11
0x1400157c6  lea     rax, [rbp+var_10]
0x1400157ca  mov     [r8], rax
0x1400157cd  mov     [r11], r8
0x1400157d0  mov     [rbp+P], r8
0x1400157d4  mov     r8, rdi
0x1400157d7  cmp     rdi, r9
0x1400157da  jz      short loc_140015765
0x1400157dc  jmp     short loc_140015799
0x1400157de  mov     rcx, [rbp+P]; P
0x1400157e2  lea     rax, [rbp+var_10]
0x1400157e6  cmp     [rcx], rax
0x1400157e9  jnz     short loc_140015809
0x1400157eb  mov     rax, [rcx+8]
0x1400157ef  cmp     [rax], rcx
0x1400157f2  jnz     short loc_140015809
0x1400157f4  lea     rdx, [rbp+var_10]
0x1400157f8  mov     [rbp+P], rax
0x1400157fc  mov     [rax], rdx
0x1400157ff  call    NbtFreeNameAddr
0x140015804  jmp     loc_140015783
0x140015809  mov     ecx, 3
0x14001580e  int     29h; Win8: RtlFailFast(ecx)
```
