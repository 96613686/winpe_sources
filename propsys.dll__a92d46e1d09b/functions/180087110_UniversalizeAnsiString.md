# _UniversalizeAnsiString

- ea: `0x180087110`
- end: `0x180087246`
- name: `_UniversalizeAnsiString`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18008724c`

## callees

- `0x180020110`
- `0x18006ed20`
- `0x18006f2a4`
- `0x180087110`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18008715b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18008715b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800871ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800871fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800871ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800871fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800871c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800871c4`
- `SHCORE!__imp_SHAnsiToUnicodeCP` at `0x1800871b4`
- `SHCORE!__imp_SHAnsiToUnicodeCP` at `0x1800871b4`
- `SHCORE!__imp_SHUnicodeToAnsiCP` at `0x1800871e0`
- `SHCORE!__imp_SHUnicodeToAnsiCP` at `0x1800871e0`

## pseudocode

```c
__int64 __fastcall UniversalizeAnsiString(LPVOID *a1, unsigned int a2)
{
  const CHAR *v4; // rcx
  __int64 result; // rax
  unsigned int v6; // esi
  unsigned __int64 v7; // rax
  _WORD *v8; // rdi
  unsigned int v9; // ebx
  unsigned int v10; // ebp
  LPVOID v11; // rax
  void *v12; // rsi
  _WORD v13[264]; // [rsp+20h] [rbp-238h] BYREF

  v4 = (const CHAR *)*a1;
  if ( !v4 )
    return 1;
  result = 0;
  if ( *v4 )
  {
    v13[0] = 0;
    v6 = lstrlenA(v4) + 1;
    if ( v6 <= 0x104 )
    {
      v8 = v13;
    }
    else
    {
      v7 = 2LL * v6;
      if ( !is_mul_ok(v6, 2u) )
        v7 = -1;
      v8 = operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
      if ( !v8 )
        return (unsigned int)-2147024882;
    }
    v9 = -2147467259;
    if ( (unsigned int)SHAnsiToUnicodeCP(a2, *a1, v8, v6) )
    {
      v10 = 3 * v6;
      v11 = CoTaskMemAlloc((int)(3 * v6));
      v12 = v11;
      if ( v11 )
      {
        if ( (unsigned int)SHUnicodeToAnsiCP(65001, v8, v11, v10) )
        {
          CoTaskMemFree(*a1);
          v9 = 0;
          *a1 = v12;
        }
        else
        {
          CoTaskMemFree(v12);
        }
      }
      else
      {
        v9 = -2147024882;
      }
    }
    if ( v8 != v13 )
      CZeroInitNew::operator delete(v8);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180087110  mov     [rsp+arg_10], rbx
0x180087115  mov     [rsp+arg_18], rbp
0x18008711a  push    rsi
0x18008711b  push    rdi
0x18008711c  push    r14
0x18008711e  sub     rsp, 240h
0x180087125  mov     rax, cs:__security_cookie
0x18008712c  xor     rax, rsp
0x18008712f  mov     [rsp+258h+var_28], rax
0x180087137  mov     r14, rcx
0x18008713a  mov     ebp, edx
0x18008713c  mov     rcx, [rcx]; lpString
0x18008713f  test    rcx, rcx
0x180087142  jnz     short loc_18008714C
0x180087144  lea     eax, [rcx+1]
0x180087147  jmp     loc_18008721E
0x18008714c  xor     eax, eax
0x18008714e  cmp     [rcx], al
0x180087150  jz      loc_18008721E
0x180087156  mov     [rsp+258h+var_238], ax
0x18008715b  call    cs:__imp_lstrlenA
0x180087161  lea     esi, [rax+1]
0x180087164  cmp     esi, 104h
0x18008716a  jbe     short loc_18008719F
0x18008716c  mov     ecx, esi
0x18008716e  mov     eax, 2
0x180087173  mul     rcx
0x180087176  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008717d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180087184  cmovb   rax, rcx
0x180087188  mov     rcx, rax; unsigned __int64
0x18008718b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180087190  mov     rdi, rax
0x180087193  test    rax, rax
0x180087196  jnz     short loc_1800871A4
0x180087198  mov     ebx, 8007000Eh
0x18008719d  jmp     short loc_18008721C
0x18008719f  lea     rdi, [rsp+258h+var_238]
0x1800871a4  mov     rdx, [r14]
0x1800871a7  mov     r9d, esi
0x1800871aa  mov     r8, rdi
0x1800871ad  mov     ecx, ebp
0x1800871af  mov     ebx, 80004005h
0x1800871b4  call    cs:__imp_SHAnsiToUnicodeCP
0x1800871ba  test    eax, eax
0x1800871bc  jz      short loc_18008720A
0x1800871be  lea     ebp, [rsi+rsi*2]
0x1800871c1  movsxd  rcx, ebp; cb
0x1800871c4  call    cs:__imp_CoTaskMemAlloc
0x1800871ca  mov     rsi, rax
0x1800871cd  test    rax, rax
0x1800871d0  jz      short loc_180087205
0x1800871d2  mov     r9d, ebp
0x1800871d5  mov     r8, rax
0x1800871d8  mov     rdx, rdi
0x1800871db  mov     ecx, 0FDE9h
0x1800871e0  call    cs:__imp_SHUnicodeToAnsiCP
0x1800871e6  test    eax, eax
0x1800871e8  jz      short loc_1800871FA
0x1800871ea  mov     rcx, [r14]; pv
0x1800871ed  call    cs:__imp_CoTaskMemFree
0x1800871f3  xor     ebx, ebx
0x1800871f5  mov     [r14], rsi
0x1800871f8  jmp     short loc_18008720A
0x1800871fa  mov     rcx, rsi; pv
0x1800871fd  call    cs:__imp_CoTaskMemFree
0x180087203  jmp     short loc_18008720A
0x180087205  mov     ebx, 8007000Eh
0x18008720a  lea     rax, [rsp+258h+var_238]
0x18008720f  cmp     rdi, rax
0x180087212  jz      short loc_18008721C
0x180087214  mov     rcx, rdi; lpMem
0x180087217  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x18008721c  mov     eax, ebx
0x18008721e  mov     rcx, [rsp+258h+var_28]
0x180087226  xor     rcx, rsp; StackCookie
0x180087229  call    __security_check_cookie
0x18008722e  lea     r11, [rsp+258h+var_18]
0x180087236  mov     rbx, [r11+30h]
0x18008723a  mov     rbp, [r11+38h]
0x18008723e  mov     rsp, r11
0x180087241  pop     r14
0x180087243  pop     rdi
0x180087244  pop     rsi
0x180087245  retn
```
