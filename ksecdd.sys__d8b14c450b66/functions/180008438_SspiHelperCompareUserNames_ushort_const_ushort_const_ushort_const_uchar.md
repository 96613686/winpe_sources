# SspiHelperCompareUserNames(ushort const *,ushort const *,ushort const *,uchar *)

- ea: `0x180008438`
- end: `0x1800085af`
- name: `?SspiHelperCompareUserNames@@YAJPEBG00PEAE@Z`
- size: `375`
- prototype: `__int64 __fastcall(PCWSTR, unsigned __int64 SourceString, unsigned __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008a40`

## callees

- `0x180004050`
- `0x180008438`
- `0x180008990`
- `0x180010980`

## import_xrefs

- `ntoskrnl!wcschr` at `0x18000848b`
- `ntoskrnl!wcschr` at `0x18000850f`
- `ntoskrnl!wcschr` at `0x18000848b`
- `ntoskrnl!wcschr` at `0x18000850f`
- `ntoskrnl!ExAllocatePool2` at `0x1800084d8`
- `ntoskrnl!ExAllocatePool2` at `0x1800084d8`

## pseudocode

```c
__int64 __fastcall SspiHelperCompareUserNames(
        PCWSTR a1,
        const WCHAR *SourceString,
        const WCHAR *a3,
        unsigned __int8 *a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rsi
  PCWSTR v7; // rbx
  unsigned int v8; // ebx
  wchar_t *v9; // rbp
  const WCHAR *v10; // r12
  __int64 v11; // r14
  wchar_t *Pool2; // rax
  wchar_t *v13; // rax

  *a4 = 0;
  v5 = (unsigned __int64)a3;
  v6 = (unsigned __int64)SourceString;
  v7 = a1;
  if ( !a1 )
  {
    if ( !SourceString && !a3 )
      *a4 = 1;
    return 0;
  }
  if ( !SourceString && !a3 )
    return 0;
  v9 = 0;
  v10 = 0;
  if ( wcschr(a1, 0x5Cu) )
  {
    v11 = -1;
    do
      ++v11;
    while ( v7[v11] );
    if ( (unsigned int)v11 > 0x7FFD )
      return (unsigned int)-1073741811;
    Pool2 = (wchar_t *)ExAllocatePool2(256, (unsigned int)(2 * v11 + 2) + 2LL, 1230267731);
    v9 = Pool2;
    if ( !Pool2 )
      return (unsigned int)-1073741801;
    memmove(Pool2, v7, 2LL * (unsigned int)v11);
    v13 = wcschr(v9, 0x5Cu);
    if ( v13 )
    {
      *v13 = 0;
      v7 = (PCWSTR)((unsigned __int64)(v13 + 1) & -(__int64)(v13[1] != 0));
      if ( *v9 )
        v10 = v9;
    }
  }
  if ( v6 )
    v6 &= -(__int64)(*(_WORD *)v6 != 0);
  if ( v5 )
    v5 &= -(__int64)(*(_WORD *)v5 != 0);
  if ( SspiHelperEqualStrings((PCWSTR)v6, v7, 1u) && SspiHelperEqualStrings((PCWSTR)v5, v10, 1u) )
    *a4 = 1;
  v8 = 0;
  if ( v9 )
    SspiLocalFree(v9);
  return v8;
}

```

## disassembly

```asm
0x180008438  push    rbx
0x18000843a  push    rbp
0x18000843b  push    rsi
0x18000843c  push    rdi
0x18000843d  push    r12
0x18000843f  push    r13
0x180008441  push    r14
0x180008443  push    r15
0x180008445  sub     rsp, 28h
0x180008449  xor     r13d, r13d
0x18000844c  mov     r15, r9
0x18000844f  mov     [r9], r13b
0x180008452  mov     rdi, r8
0x180008455  mov     rsi, rdx
0x180008458  mov     rbx, rcx
0x18000845b  test    rcx, rcx
0x18000845e  jnz     short loc_180008476
0x180008460  test    rdx, rdx
0x180008463  jnz     short loc_18000846E
0x180008465  test    r8, r8
0x180008468  jnz     short loc_18000846E
0x18000846a  mov     byte ptr [r9], 1
0x18000846e  mov     ebx, r13d
0x180008471  jmp     loc_18000859B
0x180008476  test    rsi, rsi
0x180008479  jnz     short loc_180008480
0x18000847b  test    rdi, rdi
0x18000847e  jz      short loc_18000846E
0x180008480  mov     edx, 5Ch ; '\'; Ch
0x180008485  mov     rbp, r13
0x180008488  mov     r12, r13
0x18000848b  call    cs:__imp_wcschr
0x180008492  nop     dword ptr [rax+rax+00h]
0x180008497  test    rax, rax
0x18000849a  jz      loc_180008541
0x1800084a0  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800084a4  inc     r14
0x1800084a7  cmp     [rbx+r14*2], r13w
0x1800084ac  jnz     short loc_1800084A4
0x1800084ae  cmp     r14d, 7FFDh
0x1800084b5  jbe     short loc_1800084C1
0x1800084b7  mov     ebx, 0C000000Dh
0x1800084bc  jmp     loc_18000859B
0x1800084c1  lea     edx, ds:2[r14*2]
0x1800084c9  mov     ecx, 100h
0x1800084ce  add     rdx, 2
0x1800084d2  mov     r8d, 49546553h
0x1800084d8  call    cs:__imp_ExAllocatePool2
0x1800084df  nop     dword ptr [rax+rax+00h]
0x1800084e4  mov     rbp, rax
0x1800084e7  test    rax, rax
0x1800084ea  jnz     short loc_1800084F6
0x1800084ec  mov     ebx, 0C0000017h
0x1800084f1  jmp     loc_18000859B
0x1800084f6  mov     r8d, r14d
0x1800084f9  mov     rdx, rbx; Src
0x1800084fc  add     r8, r8; Size
0x1800084ff  mov     rcx, rbp; void *
0x180008502  call    memmove
0x180008507  mov     edx, 5Ch ; '\'; Ch
0x18000850c  mov     rcx, rbp; Str
0x18000850f  call    cs:__imp_wcschr
0x180008516  nop     dword ptr [rax+rax+00h]
0x18000851b  mov     rcx, rax
0x18000851e  test    rax, rax
0x180008521  jz      short loc_180008541
0x180008523  add     rcx, 2
0x180008527  mov     [rax], r13w
0x18000852b  movzx   eax, word ptr [rcx]
0x18000852e  neg     ax
0x180008531  sbb     rbx, rbx
0x180008534  and     rbx, rcx
0x180008537  cmp     [rbp+0], r13w
0x18000853c  jz      short loc_180008541
0x18000853e  mov     r12, rbp
0x180008541  test    rsi, rsi
0x180008544  jz      short loc_180008552
0x180008546  movzx   eax, word ptr [rsi]
0x180008549  neg     ax
0x18000854c  sbb     rcx, rcx
0x18000854f  and     rsi, rcx
0x180008552  test    rdi, rdi
0x180008555  jz      short loc_180008563
0x180008557  movzx   eax, word ptr [rdi]
0x18000855a  neg     ax
0x18000855d  sbb     rcx, rcx
0x180008560  and     rdi, rcx
0x180008563  mov     r8b, 1; CaseInSensitive
0x180008566  mov     rdx, rbx; PCWSTR
0x180008569  mov     rcx, rsi; SourceString
0x18000856c  call    ?SspiHelperEqualStrings@@YAEPEBG0E@Z; SspiHelperEqualStrings(ushort const *,ushort const *,uchar)
0x180008571  test    al, al
0x180008573  jz      short loc_18000858B
0x180008575  mov     r8b, 1; CaseInSensitive
0x180008578  mov     rdx, r12; PCWSTR
0x18000857b  mov     rcx, rdi; SourceString
0x18000857e  call    ?SspiHelperEqualStrings@@YAEPEBG0E@Z; SspiHelperEqualStrings(ushort const *,ushort const *,uchar)
0x180008583  test    al, al
0x180008585  jz      short loc_18000858B
0x180008587  mov     byte ptr [r15], 1
0x18000858b  mov     ebx, r13d
0x18000858e  test    rbp, rbp
0x180008591  jz      short loc_18000859B
0x180008593  mov     rcx, rbp; DataBuffer
0x180008596  call    SspiLocalFree
0x18000859b  mov     eax, ebx
0x18000859d  add     rsp, 28h
0x1800085a1  pop     r15
0x1800085a3  pop     r14
0x1800085a5  pop     r13
0x1800085a7  pop     r12
0x1800085a9  pop     rdi
0x1800085aa  pop     rsi
0x1800085ab  pop     rbp
0x1800085ac  pop     rbx
0x1800085ad  retn
```
