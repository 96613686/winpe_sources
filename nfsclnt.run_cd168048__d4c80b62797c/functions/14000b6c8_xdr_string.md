# xdr_string

- ea: `0x14000b6c8`
- end: `0x14000b7dd`
- name: `xdr_string`
- size: `277`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x14000a9f0`
- `0x14000c990`
- `0x14000f9c0`
- `0x14000fa80`

## callees

- `0x140001b2c`
- `0x14000b618`
- `0x14000b6c8`
- `0x140019010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x14000b78b`
- `KERNEL32!GlobalAlloc` at `0x14000b78b`
- `KERNEL32!GlobalFree` at `0x14000b763`
- `KERNEL32!GlobalFree` at `0x14000b763`
- `msvcrt!fprintf` at `0x14000b7ae`
- `msvcrt!fprintf` at `0x14000b7ae`

## pseudocode

```c
__int64 __fastcall xdr_string(__int64 a1, void **a2, unsigned int a3)
{
  _BYTE *v3; // rbx
  __int64 v5; // r8
  int v8; // eax
  HGLOBAL v10; // rax
  FILE *v11; // rax
  unsigned int v12; // [rsp+50h] [rbp+8h] BYREF

  v3 = *a2;
  v5 = 0;
  v12 = 0;
  if ( *(_DWORD *)a1 )
  {
    if ( *(_DWORD *)a1 != 2 )
      goto LABEL_9;
    if ( !v3 )
      return 1;
  }
  else if ( !v3 )
  {
    return 0;
  }
  v5 = -1;
  do
    ++v5;
  while ( v3[v5] );
  v12 = v5;
LABEL_9:
  if ( *(_DWORD *)a1 == 1 )
  {
    v8 = (**(__int64 (__fastcall ***)(__int64, unsigned int *))(a1 + 8))(a1, &v12);
    goto LABEL_13;
  }
  if ( !*(_DWORD *)a1 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)(a1 + 8) + 8LL))(a1, &v12);
LABEL_13:
    if ( v8 )
    {
      v5 = v12;
      goto LABEL_16;
    }
    return 0;
  }
  if ( *(_DWORD *)a1 != 2 )
    return 0;
LABEL_16:
  if ( (unsigned int)v5 > a3 )
    return 0;
  if ( *(_DWORD *)a1 )
  {
    if ( *(_DWORD *)a1 != 1 )
    {
      if ( *(_DWORD *)a1 == 2 )
      {
        GlobalFree(v3);
        *a2 = 0;
        return 1;
      }
      return 0;
    }
    if ( (_DWORD)v5 == -1 )
      return 1;
    if ( !v3 )
    {
      v10 = GlobalAlloc(0x40u, (unsigned int)(v5 + 1));
      *a2 = v10;
      v3 = v10;
      if ( !v10 )
      {
        v11 = _acrt_iob_func(2u);
        fprintf(v11, "xdr_string: out of memory\n");
        return 0;
      }
      LODWORD(v5) = v12;
    }
    v3[(unsigned int)v5] = 0;
    v5 = v12;
  }
  return xdr_opaque(a1, v3, v5);
}

```

## disassembly

```asm
0x14000b6c8  push    rbx
0x14000b6ca  push    rbp
0x14000b6cb  push    rsi
0x14000b6cc  push    rdi
0x14000b6cd  sub     rsp, 28h
0x14000b6d1  mov     rbx, [rdx]
0x14000b6d4  mov     ebp, r8d
0x14000b6d7  xor     r8d, r8d
0x14000b6da  mov     rsi, rdx
0x14000b6dd  mov     rdi, rcx
0x14000b6e0  mov     [rsp+48h+arg_0], r8d
0x14000b6e5  cmp     [rcx], r8d
0x14000b6e8  jz      short loc_14000B6FA
0x14000b6ea  cmp     dword ptr [rcx], 2
0x14000b6ed  jnz     short loc_14000B716
0x14000b6ef  test    rbx, rbx
0x14000b6f2  jz      loc_14000B77A
0x14000b6f8  jmp     short loc_14000B703
0x14000b6fa  test    rbx, rbx
0x14000b6fd  jz      loc_14000B7B4
0x14000b703  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000b707  inc     r8
0x14000b70a  cmp     byte ptr [rbx+r8], 0
0x14000b70f  jnz     short loc_14000B707
0x14000b711  mov     [rsp+48h+arg_0], r8d
0x14000b716  cmp     dword ptr [rcx], 1
0x14000b719  jnz     short loc_14000B724
0x14000b71b  mov     rax, [rcx+8]
0x14000b71f  mov     rax, [rax]
0x14000b722  jmp     short loc_14000B731
0x14000b724  cmp     dword ptr [rcx], 0
0x14000b727  jnz     short loc_14000B746
0x14000b729  mov     rax, [rcx+8]
0x14000b72d  mov     rax, [rax+8]
0x14000b731  lea     rdx, [rsp+48h+arg_0]
0x14000b736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b73b  test    eax, eax
0x14000b73d  jz      short loc_14000B7B4
0x14000b73f  mov     r8d, [rsp+48h+arg_0]
0x14000b744  jmp     short loc_14000B74B
0x14000b746  cmp     dword ptr [rcx], 2
0x14000b749  jnz     short loc_14000B7B4
0x14000b74b  cmp     r8d, ebp
0x14000b74e  ja      short loc_14000B7B4
0x14000b750  mov     ecx, [rdi]
0x14000b752  test    ecx, ecx
0x14000b754  jz      short loc_14000B7D0
0x14000b756  sub     ecx, 1
0x14000b759  jz      short loc_14000B772
0x14000b75b  cmp     ecx, 1
0x14000b75e  jnz     short loc_14000B7B4
0x14000b760  mov     rcx, rbx; hMem
0x14000b763  call    cs:__imp_GlobalFree
0x14000b769  mov     qword ptr [rsi], 0
0x14000b770  jmp     short loc_14000B77A
0x14000b772  lea     eax, [r8+1]
0x14000b776  test    eax, eax
0x14000b778  jnz     short loc_14000B781
0x14000b77a  mov     eax, 1
0x14000b77f  jmp     short loc_14000B7B6
0x14000b781  test    rbx, rbx
0x14000b784  jnz     short loc_14000B7C4
0x14000b786  mov     edx, eax; dwBytes
0x14000b788  lea     ecx, [rbx+40h]; uFlags
0x14000b78b  call    cs:__imp_GlobalAlloc
0x14000b791  mov     [rsi], rax
0x14000b794  mov     rbx, rax
0x14000b797  test    rax, rax
0x14000b79a  jnz     short loc_14000B7BF
0x14000b79c  lea     ecx, [rax+2]; Ix
0x14000b79f  call    __acrt_iob_func
0x14000b7a4  mov     rcx, rax; Stream
0x14000b7a7  lea     rdx, aXdrStringOutOf; "xdr_string: out of memory\n"
0x14000b7ae  call    cs:__imp_fprintf
0x14000b7b4  xor     eax, eax
0x14000b7b6  add     rsp, 28h
0x14000b7ba  pop     rdi
0x14000b7bb  pop     rsi
0x14000b7bc  pop     rbp
0x14000b7bd  pop     rbx
0x14000b7be  retn
0x14000b7bf  mov     r8d, [rsp+48h+arg_0]
0x14000b7c4  mov     eax, r8d
0x14000b7c7  mov     byte ptr [rax+rbx], 0
0x14000b7cb  mov     r8d, [rsp+48h+arg_0]
0x14000b7d0  mov     rdx, rbx
0x14000b7d3  mov     rcx, rdi
0x14000b7d6  call    xdr_opaque
0x14000b7db  jmp     short loc_14000B7B6
```
