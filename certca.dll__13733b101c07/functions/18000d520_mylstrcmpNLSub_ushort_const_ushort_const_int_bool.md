# mylstrcmpNLSub(ushort const *,ushort const *,int,bool)

- ea: `0x18000d520`
- end: `0x18000d5c5`
- name: `?mylstrcmpNLSub@@YAHPEBG0H_N@Z`
- size: `165`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, const unsigned __int16 *, int, unsigned __int8)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800019a0`
- `0x180005010`
- `0x18000596c`
- `0x18000e610`
- `0x18000fb00`
- `0x180012ae8`
- `0x180012f0c`
- `0x1800168a0`
- `0x180016dc0`
- `0x1800175e0`
- `0x180018494`
- `0x180019ac0`
- `0x180019ad0`
- `0x18001f090`
- `0x1800201bc`
- `0x180020378`
- `0x1800217b4`
- `0x18002e4b0`
- `0x18002e620`
- `0x18002e710`
- `0x180030224`
- `0x1800308c0`
- `0x180030c18`
- `0x1800315b4`
- `0x180031af8`
- `0x18003211c`
- `0x180033144`
- `0x180033314`
- `0x1800354fc`
- `0x1800362f8`

## callees

- `0x18000d520`
- `0x18000f718`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d558`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d558`

## pseudocode

```c
__int64 __fastcall mylstrcmpNLSub(PCNZWCH lpString1, const unsigned __int16 *a2, int a3, unsigned __int8 a4)
{
  int cchCount2; // r11d
  DWORD v6; // ebp
  int v7; // ebx
  unsigned __int64 v10; // r11
  unsigned __int64 v11[5]; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int64 v12; // [rsp+60h] [rbp+8h] BYREF

  cchCount2 = a3;
  v6 = a4;
  v7 = a3;
  if ( a3 > 0 )
  {
    v12 = 0;
    v11[0] = 0;
    if ( !(unsigned int)StringCchLengthW(lpString1, a3, &v12) && (int)v10 >= (int)v12 )
      v7 = v12;
    if ( !(unsigned int)StringCchLengthW(a2, v10, v11) && cchCount2 >= SLODWORD(v11[0]) )
      cchCount2 = v11[0];
  }
  return (unsigned int)(CompareStringW(0x7Fu, v6, lpString1, v7, a2, cchCount2) - 2);
}

```

## disassembly

```asm
0x18000d520  mov     [rsp+arg_10], rbx
0x18000d525  push    rbp
0x18000d526  push    rsi
0x18000d527  push    rdi
0x18000d528  sub     rsp, 40h
0x18000d52c  movsxd  r11, r8d
0x18000d52f  mov     rdi, rdx
0x18000d532  movzx   ebp, r9b
0x18000d536  mov     ebx, r11d
0x18000d539  mov     rsi, rcx
0x18000d53c  test    r8d, r8d
0x18000d53f  jg      short loc_18000D56E
0x18000d541  mov     [rsp+58h+cchCount2], r11d; cchCount2
0x18000d546  mov     edx, ebp; dwCmpFlags
0x18000d548  mov     r9d, ebx; cchCount1
0x18000d54b  mov     [rsp+58h+lpString2], rdi; lpString2
0x18000d550  mov     r8, rsi; lpString1
0x18000d553  mov     ecx, 7Fh; Locale
0x18000d558  call    cs:__imp_CompareStringW
0x18000d55e  mov     rbx, [rsp+58h+arg_10]
0x18000d563  sub     eax, 2
0x18000d566  add     rsp, 40h
0x18000d56a  pop     rdi
0x18000d56b  pop     rsi
0x18000d56c  pop     rbp
0x18000d56d  retn
0x18000d56e  xor     eax, eax
0x18000d570  mov     [rsp+58h+arg_8], r14
0x18000d575  lea     r8, [rsp+58h+arg_0]; unsigned __int64 *
0x18000d57a  mov     [rsp+58h+arg_0], rax
0x18000d57f  mov     rdx, r11; unsigned __int64
0x18000d582  mov     [rsp+58h+var_28], rax
0x18000d587  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000d58c  test    eax, eax
0x18000d58e  jnz     short loc_18000D59B
0x18000d590  mov     rax, [rsp+58h+arg_0]
0x18000d595  cmp     r11d, eax
0x18000d598  cmovge  ebx, eax
0x18000d59b  lea     r8, [rsp+58h+var_28]; unsigned __int64 *
0x18000d5a0  mov     rdx, r11; unsigned __int64
0x18000d5a3  mov     rcx, rdi; unsigned __int16 *
0x18000d5a6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000d5ab  mov     r14, [rsp+58h+arg_8]
0x18000d5b0  test    eax, eax
0x18000d5b2  jnz     short loc_18000D541
0x18000d5b4  mov     rax, [rsp+58h+var_28]
0x18000d5b9  cmp     r11d, eax
0x18000d5bc  cmovge  r11d, eax
0x18000d5c0  jmp     loc_18000D541
```
