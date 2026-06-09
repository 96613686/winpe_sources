# findItem

- ea: `0x14000a670`
- end: `0x14000a79e`
- name: `findItem`
- size: `302`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140003d28`
- `0x140005148`
- `0x14000705c`
- `0x140007934`
- `0x14000a29c`
- `0x14000a3f8`
- `0x14000b2d8`

## callees

- `0x14000a670`
- `0x14000a7a4`
- `0x14000e412`

## import_xrefs

- `msvcrt!_stricmp` at `0x14000a6b1`
- `msvcrt!_stricmp` at `0x14000a776`
- `msvcrt!_stricmp` at `0x14000a6b1`
- `msvcrt!_stricmp` at `0x14000a776`
- `msvcrt!malloc` at `0x14000a6ea`
- `msvcrt!malloc` at `0x14000a6ea`

## pseudocode

```c
__int64 __fastcall findItem(__int64 a1, const char *a2)
{
  __int64 i; // rbx
  __int64 v4; // r14
  char *v5; // rdi
  char *v7; // rax
  __int64 j; // rcx
  _QWORD *k; // r14
  int v10; // eax
  bool v11; // zf

  i = a1;
  if ( !a1 )
    return 0;
  v4 = *(_QWORD *)(a1 + 40);
  v5 = (char *)(v4 + 40);
  if ( *(_QWORD *)(v4 + 40) )
  {
    for ( i = *(_QWORD *)(*(_QWORD *)v5 + 8LL * (int)hashString(a2)); i; i = *(_QWORD *)(i + 16) )
    {
      if ( !_stricmp(*(const char **)i, a2) )
        return i;
    }
    return 0;
  }
  if ( *(int *)(v4 + 32) >= 50 )
  {
    if ( !a2 )
      goto LABEL_26;
    v7 = (char *)malloc(0x4000u);
    *(_QWORD *)v5 = v7;
    if ( v7 )
    {
      if ( v7 > v5 || v7 + 16376 < v5 )
      {
        memset_0(v7, 0, 0x4000u);
      }
      else
      {
        for ( j = 0; j != 2048; ++j )
          *(_QWORD *)(*(_QWORD *)v5 + 8 * j) = 0;
      }
      for ( k = *(_QWORD **)v4; k; k = (_QWORD *)k[3] )
      {
        v10 = 0;
        if ( *k )
          v10 = ((__int64 (*)(void))hashString)();
        k[2] = *(_QWORD *)(*(_QWORD *)v5 + 8LL * v10);
        *(_QWORD *)(*(_QWORD *)v5 + 8LL * v10) = k;
      }
    }
  }
  while ( 1 )
  {
    if ( a2 && *(_QWORD *)i )
      v11 = _stricmp(*(const char **)i, a2) == 0;
    else
LABEL_26:
      v11 = a2 == *(const char **)i;
    if ( v11 )
      break;
    i = *(_QWORD *)(i + 24);
    if ( !i )
      return 0;
  }
  return i;
}

```

## disassembly

```asm
0x14000a670  push    rbx
0x14000a672  push    rsi
0x14000a673  push    rdi
0x14000a674  push    r14
0x14000a676  sub     rsp, 28h
0x14000a67a  mov     rsi, rdx
0x14000a67d  mov     rbx, rcx
0x14000a680  test    rcx, rcx
0x14000a683  jz      loc_14000A792
0x14000a689  mov     r14, [rcx+28h]
0x14000a68d  lea     rdi, [r14+28h]
0x14000a691  cmp     qword ptr [rdi], 0
0x14000a695  jz      short loc_14000A6D1
0x14000a697  mov     rcx, rdx
0x14000a69a  call    hashString
0x14000a69f  movsxd  rcx, eax
0x14000a6a2  mov     rax, [rdi]
0x14000a6a5  mov     rbx, [rax+rcx*8]
0x14000a6a9  jmp     short loc_14000A6BF
0x14000a6ab  mov     rcx, [rbx]; String1
0x14000a6ae  mov     rdx, rsi; String2
0x14000a6b1  call    cs:__imp__stricmp
0x14000a6b7  test    eax, eax
0x14000a6b9  jz      short loc_14000A6C9
0x14000a6bb  mov     rbx, [rbx+10h]
0x14000a6bf  test    rbx, rbx
0x14000a6c2  jnz     short loc_14000A6AB
0x14000a6c4  jmp     loc_14000A792
0x14000a6c9  mov     rax, rbx
0x14000a6cc  jmp     loc_14000A794
0x14000a6d1  cmp     dword ptr [r14+20h], 32h ; '2'
0x14000a6d6  jl      loc_14000A766
0x14000a6dc  test    rsi, rsi
0x14000a6df  jz      loc_14000A780
0x14000a6e5  mov     ecx, 4000h; Size
0x14000a6ea  call    cs:__imp_malloc
0x14000a6f0  mov     [rdi], rax
0x14000a6f3  test    rax, rax
0x14000a6f6  jz      short loc_14000A766
0x14000a6f8  cmp     rax, rdi
0x14000a6fb  ja      short loc_14000A724
0x14000a6fd  lea     rcx, [rax+3FF8h]
0x14000a704  cmp     rcx, rdi
0x14000a707  jb      short loc_14000A724
0x14000a709  xor     ecx, ecx
0x14000a70b  mov     rax, [rdi]
0x14000a70e  mov     qword ptr [rax+rcx*8], 0
0x14000a716  inc     rcx
0x14000a719  cmp     rcx, 800h
0x14000a720  jnz     short loc_14000A70B
0x14000a722  jmp     short loc_14000A734
0x14000a724  xor     edx, edx; Val
0x14000a726  mov     r8d, 4000h; Size
0x14000a72c  mov     rcx, rax; void *
0x14000a72f  call    memset_0
0x14000a734  mov     r14, [r14]
0x14000a737  jmp     short loc_14000A761
0x14000a739  mov     rcx, [r14]
0x14000a73c  xor     eax, eax
0x14000a73e  test    rcx, rcx
0x14000a741  jz      short loc_14000A748
0x14000a743  call    hashString
0x14000a748  movsxd  rdx, eax
0x14000a74b  mov     rax, [rdi]
0x14000a74e  mov     rcx, [rax+rdx*8]
0x14000a752  mov     [r14+10h], rcx
0x14000a756  mov     rax, [rdi]
0x14000a759  mov     [rax+rdx*8], r14
0x14000a75d  mov     r14, [r14+18h]
0x14000a761  test    r14, r14
0x14000a764  jnz     short loc_14000A739
0x14000a766  test    rsi, rsi
0x14000a769  jz      short loc_14000A780
0x14000a76b  mov     rcx, [rbx]; String1
0x14000a76e  test    rcx, rcx
0x14000a771  jz      short loc_14000A780
0x14000a773  mov     rdx, rsi; String2
0x14000a776  call    cs:__imp__stricmp
0x14000a77c  test    eax, eax
0x14000a77e  jmp     short loc_14000A783
0x14000a780  cmp     rsi, [rbx]
0x14000a783  jz      loc_14000A6C9
0x14000a789  mov     rbx, [rbx+18h]
0x14000a78d  test    rbx, rbx
0x14000a790  jnz     short loc_14000A766
0x14000a792  xor     eax, eax
0x14000a794  add     rsp, 28h
0x14000a798  pop     r14
0x14000a79a  pop     rdi
0x14000a79b  pop     rsi
0x14000a79c  pop     rbx
0x14000a79d  retn
```
