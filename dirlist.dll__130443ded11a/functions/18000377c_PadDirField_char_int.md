# PadDirField(char *,int)

- ea: `0x18000377c`
- end: `0x1800037e0`
- name: `?PadDirField@@YAXPEADH@Z`
- size: `100`
- prototype: `void __fastcall(char *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000243c`

## callees

- `0x18000377c`
- `0x180003a06`
- `0x180003a12`

## pseudocode

```c
void __fastcall PadDirField(char *a1, int a2)
{
  int v2; // esi
  char *v3; // rbx
  __int64 v4; // rdi
  int v5; // esi
  char *v6; // rbp
  int v7; // edx

  v2 = a2;
  v3 = a1;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  if ( (int)v4 > a2 )
    v2 = v4;
  v5 = v2 - v4;
  v6 = &a1[v5];
  memmove_0(v6, a1, (int)v4 + 1);
  if ( v5 > 0 )
  {
    LOBYTE(v7) = 32;
    memset_0(v3, v7, v5);
    v3 = v6;
  }
  *(_WORD *)&v3[(int)v4] = 32;
}

```

## disassembly

```asm
0x18000377c  push    rbx
0x18000377e  push    rbp
0x18000377f  push    rsi
0x180003780  push    rdi
0x180003781  push    r14
0x180003783  sub     rsp, 20h
0x180003787  mov     esi, edx
0x180003789  mov     rbx, rcx
0x18000378c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003790  inc     rdi
0x180003793  cmp     byte ptr [rcx+rdi], 0
0x180003797  jnz     short loc_180003790
0x180003799  cmp     edi, esi
0x18000379b  lea     eax, [rdi+1]
0x18000379e  movsxd  r8, eax; Size
0x1800037a1  mov     rdx, rbx; Src
0x1800037a4  cmovg   esi, edi
0x1800037a7  sub     esi, edi
0x1800037a9  movsxd  r14, esi
0x1800037ac  lea     rbp, [r14+rcx]
0x1800037b0  mov     rcx, rbp; void *
0x1800037b3  call    memmove_0
0x1800037b8  test    esi, esi
0x1800037ba  jle     short loc_1800037CC
0x1800037bc  mov     r8, r14; Size
0x1800037bf  mov     dl, 20h ; ' '; Val
0x1800037c1  mov     rcx, rbx; void *
0x1800037c4  call    memset_0
0x1800037c9  mov     rbx, rbp
0x1800037cc  movsxd  rax, edi
0x1800037cf  mov     word ptr [rax+rbx], 20h ; ' '
0x1800037d5  add     rsp, 20h
0x1800037d9  pop     r14
0x1800037db  pop     rdi
0x1800037dc  pop     rsi
0x1800037dd  pop     rbp
0x1800037de  pop     rbx
0x1800037df  retn
```
