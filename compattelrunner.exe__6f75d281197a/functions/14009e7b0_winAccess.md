# winAccess

- ea: `0x14009e7b0`
- end: `0x14009e914`
- name: `winAccess`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14009ff30`

## callees

- `0x140001ba0`
- `0x14008ac90`
- `0x14009e7b0`
- `0x14009fa4c`
- `0x14009fb28`
- `0x1400a07a8`
- `0x1400a1544`
- `0x1400a8010`

## string_xrefs

- `0x14009e882`: `winAccess`

## pseudocode

```c
__int64 __fastcall winAccess(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  int v5; // ebx
  int v6; // esi
  __int64 v7; // r14
  int v9; // edi
  int v10; // r13d
  int v11; // esi
  int v12; // ebx
  unsigned int v13; // [rsp+30h] [rbp-40h] BYREF
  int v14; // [rsp+34h] [rbp-3Ch] BYREF
  __int128 v15; // [rsp+38h] [rbp-38h] BYREF
  __int128 v16; // [rsp+48h] [rbp-28h]
  int v17; // [rsp+58h] [rbp-18h]

  v14 = 0;
  v5 = a3;
  v6 = a2;
  if ( a2 )
  {
    v7 = winUtf8ToUnicode(a2, a2, a3);
    if ( !v7 )
      return 3082;
    v13 = 0;
    v15 = 0;
    v17 = 0;
    v16 = 0;
    do
    {
      v9 = ((__int64 (__fastcall *)(__int64, _QWORD, __int128 *))off_1400C5C08)(v7, 0, &v15);
      if ( v9 )
      {
        if ( v5 || HIDWORD(v16) || (v11 = -1, v17) )
          v11 = v15;
        goto LABEL_15;
      }
    }
    while ( (unsigned int)winRetryIoerr(&v13, &v14) );
    winLogIoerr(v13, 51288);
    v10 = v14;
    if ( (unsigned int)(v14 - 2) > 1 )
    {
      sqlite3_free(v7);
      return winLogErrorAtLine(3338, v10, (unsigned int)"winAccess", v6, 51292);
    }
    v11 = -1;
LABEL_15:
    sqlite3_free(v7);
    if ( !v5 )
      goto LABEL_18;
    v12 = v5 - 1;
    if ( !v12 )
    {
      v9 = v11 != -1 && (v11 & 1) == 0;
      goto LABEL_19;
    }
    if ( v12 == 1 )
LABEL_18:
      v9 = v11 != -1;
LABEL_19:
    *a4 = v9;
    return 0;
  }
  *a4 = 0;
  return 0;
}

```

## disassembly

```asm
0x14009e7b0  mov     [rsp-28h+arg_0], rbx
0x14009e7b5  mov     [rsp-28h+arg_10], rsi
0x14009e7ba  push    rbp
0x14009e7bb  push    rdi
0x14009e7bc  push    r13
0x14009e7be  push    r14
0x14009e7c0  push    r15
0x14009e7c2  mov     rbp, rsp
0x14009e7c5  sub     rsp, 70h
0x14009e7c9  mov     rax, cs:__security_cookie
0x14009e7d0  xor     rax, rsp
0x14009e7d3  mov     [rbp+var_10], rax
0x14009e7d7  mov     [rbp+var_3C], 0
0x14009e7de  mov     r15, r9
0x14009e7e1  mov     ebx, r8d
0x14009e7e4  mov     rsi, rdx
0x14009e7e7  test    rdx, rdx
0x14009e7ea  jnz     short loc_14009E7F4
0x14009e7ec  mov     [r9], edx
0x14009e7ef  jmp     loc_14009E8D7
0x14009e7f4  mov     rcx, rsi
0x14009e7f7  call    winUtf8ToUnicode
0x14009e7fc  mov     r14, rax
0x14009e7ff  test    rax, rax
0x14009e802  jnz     short loc_14009E80E
0x14009e804  mov     eax, 0C0Ah
0x14009e809  jmp     loc_14009E8D9
0x14009e80e  xorps   xmm0, xmm0
0x14009e811  mov     [rbp+var_40], 0
0x14009e818  xor     eax, eax
0x14009e81a  movups  [rbp+var_38], xmm0
0x14009e81e  mov     [rbp+var_18], eax
0x14009e821  movups  [rbp+var_28], xmm0
0x14009e825  mov     rax, cs:off_1400C5C08
0x14009e82c  lea     r8, [rbp+var_38]
0x14009e830  xor     edx, edx
0x14009e832  mov     rcx, r14
0x14009e835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009e83a  or      r13d, 0FFFFFFFFh
0x14009e83e  mov     edi, eax
0x14009e840  test    eax, eax
0x14009e842  jnz     short loc_14009E8A1
0x14009e844  lea     rdx, [rbp+var_3C]
0x14009e848  lea     rcx, [rbp+var_40]
0x14009e84c  call    winRetryIoerr
0x14009e851  test    eax, eax
0x14009e853  jnz     short loc_14009E825
0x14009e855  mov     ecx, [rbp+var_40]
0x14009e858  mov     edx, 0C858h
0x14009e85d  call    winLogIoerr
0x14009e862  mov     r13d, [rbp+var_3C]
0x14009e866  lea     eax, [r13-2]
0x14009e86a  cmp     eax, 1
0x14009e86d  jbe     short loc_14009E898
0x14009e86f  mov     rcx, r14
0x14009e872  call    sqlite3_free
0x14009e877  mov     r9, rsi
0x14009e87a  mov     [rsp+70h+var_50], 0C85Ch
0x14009e882  lea     r8, aWinaccess; "winAccess"
0x14009e889  mov     edx, r13d
0x14009e88c  mov     ecx, 0D0Ah
0x14009e891  call    winLogErrorAtLine
0x14009e896  jmp     short loc_14009E8D9
0x14009e898  or      r13d, 0FFFFFFFFh
0x14009e89c  mov     esi, r13d
0x14009e89f  jmp     short loc_14009E8B5
0x14009e8a1  test    ebx, ebx
0x14009e8a3  jnz     short loc_14009E8B2
0x14009e8a5  cmp     dword ptr [rbp+var_28+0Ch], ebx
0x14009e8a8  jnz     short loc_14009E8B2
0x14009e8aa  mov     esi, r13d
0x14009e8ad  cmp     [rbp+var_18], ebx
0x14009e8b0  jz      short loc_14009E8B5
0x14009e8b2  mov     esi, dword ptr [rbp+var_38]
0x14009e8b5  mov     rcx, r14
0x14009e8b8  call    sqlite3_free
0x14009e8bd  test    ebx, ebx
0x14009e8bf  jz      short loc_14009E8CB
0x14009e8c1  sub     ebx, 1
0x14009e8c4  jz      short loc_14009E8FE
0x14009e8c6  cmp     ebx, 1
0x14009e8c9  jnz     short loc_14009E8D4
0x14009e8cb  xor     edi, edi
0x14009e8cd  cmp     esi, r13d
0x14009e8d0  setnz   dil
0x14009e8d4  mov     [r15], edi
0x14009e8d7  xor     eax, eax
0x14009e8d9  mov     rcx, [rbp+var_10]
0x14009e8dd  xor     rcx, rsp; StackCookie
0x14009e8e0  call    __security_check_cookie
0x14009e8e5  lea     r11, [rsp+70h+var_s0]
0x14009e8ea  mov     rbx, [r11+30h]
0x14009e8ee  mov     rsi, [r11+40h]
0x14009e8f2  mov     rsp, r11
0x14009e8f5  pop     r15
0x14009e8f7  pop     r14
0x14009e8f9  pop     r13
0x14009e8fb  pop     rdi
0x14009e8fc  pop     rbp
0x14009e8fd  retn
0x14009e8fe  cmp     esi, r13d
0x14009e901  jz      short loc_14009E910
0x14009e903  test    sil, 1
0x14009e907  jnz     short loc_14009E910
0x14009e909  mov     edi, 1
0x14009e90e  jmp     short loc_14009E8D4
0x14009e910  xor     edi, edi
0x14009e912  jmp     short loc_14009E8D4
```
