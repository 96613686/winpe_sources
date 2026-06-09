# DoesSuffixMatchesIppOnline(ushort const *)

- ea: `0x1800253c8`
- end: `0x1800254c7`
- name: `?DoesSuffixMatchesIppOnline@@YAHPEBG@Z`
- size: `255`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026568`
- `0x180032f58`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x1800253c8`

## import_xrefs

- `msvcrt!towlower` at `0x180025486`
- `msvcrt!towlower` at `0x180025486`
- `msvcrt!iswupper` at `0x180025478`
- `msvcrt!iswupper` at `0x180025478`
- `msvcrt!iswascii` at `0x18002546a`
- `msvcrt!iswascii` at `0x18002546a`
- `msvcrt!wcsstr` at `0x1800254a3`
- `msvcrt!wcsstr` at `0x1800254a3`

## string_xrefs

- `0x180025499`: `.aadrm.com`

## pseudocode

```c
_BOOL8 __fastcall DoesSuffixMatchesIppOnline(unsigned __int16 *a1)
{
  unsigned __int16 *v3; // rax
  __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  unsigned __int16 *v6; // rax
  wchar_t *v7; // rdi
  BOOL v8; // ebx
  unsigned int i; // esi

  if ( !a1 )
    return 0;
  v3 = a1;
  v4 = 0x7FFFFFFF;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v4;
  }
  while ( v4 );
  v5 = (0x7FFFFFFF - v4) & -(__int64)(v4 != 0);
  if ( !v4 || v5 == 0x7FFFFFFF )
    v5 = 2147483646;
  v6 = (unsigned __int16 *)operator new[](saturated_mul(v5 + 1, 2u));
  v7 = v6;
  if ( v6 )
  {
    StringCchCopyW(v6, v5 + 1, a1);
    for ( i = 0; i < v5; ++i )
    {
      if ( iswascii(v7[i]) )
      {
        if ( iswupper(v7[i]) )
          v7[i] = towlower(v7[i]);
      }
    }
    v8 = wcsstr(v7, L".aadrm.com") != 0;
    operator delete(v7);
  }
  else
  {
    return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x1800253c8  push    rbx
0x1800253ca  push    rbp
0x1800253cb  push    rsi
0x1800253cc  push    rdi
0x1800253cd  push    r14
0x1800253cf  sub     rsp, 20h
0x1800253d3  xor     r14d, r14d
0x1800253d6  mov     rsi, rcx
0x1800253d9  test    rcx, rcx
0x1800253dc  jnz     short loc_1800253E5
0x1800253de  xor     eax, eax
0x1800253e0  jmp     loc_1800254BC
0x1800253e5  mov     r8d, 7FFFFFFFh
0x1800253eb  mov     rax, rsi
0x1800253ee  mov     edx, r8d
0x1800253f1  cmp     [rax], r14w
0x1800253f5  jz      short loc_180025401
0x1800253f7  add     rax, 2
0x1800253fb  sub     rdx, 1
0x1800253ff  jnz     short loc_1800253F1
0x180025401  mov     rcx, r8
0x180025404  mov     rax, rdx
0x180025407  sub     rcx, rdx
0x18002540a  neg     rax
0x18002540d  sbb     rbx, rbx
0x180025410  and     rbx, rcx
0x180025413  test    rdx, rdx
0x180025416  jz      short loc_18002541D
0x180025418  cmp     rbx, r8
0x18002541b  jnz     short loc_180025422
0x18002541d  mov     ebx, 7FFFFFFEh
0x180025422  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180025429  lea     rbp, [rbx+1]
0x18002542d  mov     eax, 2
0x180025432  mul     rbp
0x180025435  cmovb   rax, rcx
0x180025439  mov     rcx, rax; unsigned __int64
0x18002543c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180025441  mov     rdi, rax
0x180025444  test    rax, rax
0x180025447  jnz     short loc_18002544E
0x180025449  mov     ebx, r14d
0x18002544c  jmp     short loc_1800254BA
0x18002544e  mov     r8, rsi; unsigned __int16 *
0x180025451  mov     rdx, rbp; unsigned __int64
0x180025454  mov     rcx, rdi; unsigned __int16 *
0x180025457  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002545c  mov     esi, r14d
0x18002545f  test    rbx, rbx
0x180025462  jz      short loc_180025499
0x180025464  mov     ebp, esi
0x180025466  movzx   ecx, word ptr [rdi+rbp*2]; C
0x18002546a  call    cs:__imp_iswascii
0x180025470  test    eax, eax
0x180025472  jz      short loc_180025490
0x180025474  movzx   ecx, word ptr [rdi+rbp*2]; C
0x180025478  call    cs:__imp_iswupper
0x18002547e  test    eax, eax
0x180025480  jz      short loc_180025490
0x180025482  movzx   ecx, word ptr [rdi+rbp*2]; C
0x180025486  call    cs:__imp_towlower
0x18002548c  mov     [rdi+rbp*2], ax
0x180025490  inc     esi
0x180025492  mov     eax, esi
0x180025494  cmp     rax, rbx
0x180025497  jb      short loc_180025464
0x180025499  lea     rdx, aAadrmCom; ".aadrm.com"
0x1800254a0  mov     rcx, rdi; Str
0x1800254a3  call    cs:__imp_wcsstr
0x1800254a9  mov     ebx, r14d
0x1800254ac  mov     rcx, rdi; Block
0x1800254af  test    rax, rax
0x1800254b2  setnz   bl
0x1800254b5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800254ba  mov     eax, ebx
0x1800254bc  add     rsp, 20h
0x1800254c0  pop     r14
0x1800254c2  pop     rdi
0x1800254c3  pop     rsi
0x1800254c4  pop     rbp
0x1800254c5  pop     rbx
0x1800254c6  retn
```
