# CValue::FromString(ushort const * const)

- ea: `0x18000ab50`
- end: `0x18000ad91`
- name: `?FromString@CValue@@QEAAHQEBG@Z`
- size: `577`
- prototype: `__int64 __fastcall(CValue *__hidden this, const unsigned __int16 *const)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800090b4`
- `0x18000a99c`
- `0x18000add0`
- `0x18000af5c`

## callees

- `0x180001f90`
- `0x180001fec`
- `0x1800069b8`
- `0x180007d38`
- `0x18000ab50`
- `0x1800123d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18000ac9c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18000ad75`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18000ac9c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18000ad75`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000ad4d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000ad5f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000ad4d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000ad5f`

## pseudocode

```c
__int64 __fastcall CValue::FromString(CValue *this, wchar_t *a2)
{
  __int64 v2; // rdi
  __int64 v4; // rcx
  wchar_t *v5; // rax
  __int64 v6; // r8
  wchar_t *v7; // rcx
  wchar_t *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  wchar_t *i; // rcx
  bool v12; // cf
  int v13; // r8d
  __int16 v14; // ax
  wchar_t *v15; // rcx
  __int64 result; // rax
  void *v17; // rcx
  __int64 v18; // rcx
  unsigned int v19; // eax
  wchar_t *EndPtr[2]; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t String[256]; // [rsp+30h] [rbp-D0h] BYREF

  v2 = -1;
  EndPtr[0] = 0;
  if ( a2 )
  {
    v4 = 2147483646;
    v5 = String;
    v6 = 256;
    do
    {
      if ( !v4 )
        break;
      if ( !*a2 )
        break;
      *v5++ = *a2++;
      --v4;
      --v6;
    }
    while ( v6 );
    v7 = v5 - 1;
    v8 = String;
    if ( v6 )
      v7 = v5;
    *v7 = 0;
    if ( String[0] == 32 )
    {
      do
        ++v8;
      while ( *v8 == 32 );
    }
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    memmove_0(String, v8, (unsigned int)(2 * v9 + 2));
    v10 = -1;
    do
      ++v10;
    while ( String[v10] );
    if ( v10 )
    {
      for ( i = (wchar_t *)&EndPtr[1] + v10 + 3; i >= String && *i == 32; --i )
        ;
      i[1] = 0;
    }
  }
  else
  {
    String[0] = 0;
  }
  v12 = *((_DWORD *)this + 3) != 0;
  *(_QWORD *)((char *)this + 20) = 0;
  v13 = v12 ? 16 : 10;
  if ( !String[0] )
    *((_DWORD *)this + 6) = 1;
  switch ( *((_DWORD *)this + 1) )
  {
    case 1:
LABEL_30:
      v14 = wcstol(String, EndPtr, v13);
      v15 = EndPtr[0];
      *((_WORD *)this + 16) = v14;
      if ( *v15 )
LABEL_31:
        *((_DWORD *)this + 5) = 1;
      return 1;
    case 2:
      v19 = wcstol(String, EndPtr, v13);
      goto LABEL_44;
    case 3:
      *((_WORD *)this + 16) = wcstoul(String, EndPtr, v13);
      goto LABEL_45;
    case 4:
      v19 = wcstoul(String, EndPtr, v13);
LABEL_44:
      *((_DWORD *)this + 8) = v19;
LABEL_45:
      if ( !*EndPtr[0] )
        return 1;
      goto LABEL_31;
  }
  if ( *((_DWORD *)this + 1) != 5 && *((_DWORD *)this + 1) != 6 )
  {
    if ( *((_DWORD *)this + 1) == 7 )
      return 1;
    goto LABEL_30;
  }
  v17 = (void *)*((_QWORD *)this + 4);
  if ( v17 )
  {
    operator delete(v17);
    *((_QWORD *)this + 4) = 0;
  }
  v18 = -1;
  do
    ++v18;
  while ( String[v18] );
  result = (__int64)MemAlloc(saturated_mul(v18 + 1, 2u));
  *((_QWORD *)this + 4) = result;
  if ( result )
  {
    do
      ++v2;
    while ( String[v2] );
    StringCchCopyW((unsigned __int16 *)result, v2 + 1, String);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000ab50  push    rbp
0x18000ab52  push    rbx
0x18000ab53  push    rsi
0x18000ab54  push    rdi
0x18000ab55  lea     rbp, [rsp-148h]
0x18000ab5d  sub     rsp, 248h
0x18000ab64  mov     rax, cs:__security_cookie
0x18000ab6b  xor     rax, rsp
0x18000ab6e  mov     [rbp+160h+var_30], rax
0x18000ab75  xor     esi, esi
0x18000ab77  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000ab7b  mov     [rsp+260h+EndPtr], rsi
0x18000ab80  mov     rbx, rcx
0x18000ab83  test    rdx, rdx
0x18000ab86  jnz     short loc_18000AB92
0x18000ab88  mov     [rsp+260h+String], si
0x18000ab8d  jmp     loc_18000AC3E
0x18000ab92  mov     ecx, 7FFFFFFEh
0x18000ab97  lea     rax, [rsp+260h+String]
0x18000ab9c  mov     r8d, 100h
0x18000aba2  test    rcx, rcx
0x18000aba5  jz      short loc_18000ABC6
0x18000aba7  movzx   r9d, word ptr [rdx]
0x18000abab  test    r9w, r9w
0x18000abaf  jz      short loc_18000ABC6
0x18000abb1  mov     [rax], r9w
0x18000abb5  add     rdx, 2
0x18000abb9  add     rax, 2
0x18000abbd  dec     rcx
0x18000abc0  sub     r8, 1
0x18000abc4  jnz     short loc_18000ABA2
0x18000abc6  test    r8, r8
0x18000abc9  lea     rcx, [rax-2]
0x18000abcd  lea     rdx, [rsp+260h+String]
0x18000abd2  cmovnz  rcx, rax
0x18000abd6  mov     [rcx], si
0x18000abd9  cmp     [rsp+260h+String], 20h ; ' '
0x18000abdf  jnz     short loc_18000ABEB
0x18000abe1  add     rdx, 2; Src
0x18000abe5  cmp     word ptr [rdx], 20h ; ' '
0x18000abe9  jz      short loc_18000ABE1
0x18000abeb  mov     rax, rdi
0x18000abee  inc     rax
0x18000abf1  cmp     [rdx+rax*2], si
0x18000abf5  jnz     short loc_18000ABEE
0x18000abf7  lea     r8d, ds:2[rax*2]; Size
0x18000abff  lea     rcx, [rsp+260h+String]; void *
0x18000ac04  call    memmove_0
0x18000ac09  lea     rcx, [rsp+260h+String]
0x18000ac0e  mov     rax, rdi
0x18000ac11  inc     rax
0x18000ac14  cmp     [rcx+rax*2], si
0x18000ac18  jnz     short loc_18000AC11
0x18000ac1a  test    rax, rax
0x18000ac1d  jz      short loc_18000AC3E
0x18000ac1f  lea     rcx, [rsp+rax*2+260h+var_232]
0x18000ac24  jmp     short loc_18000AC30
0x18000ac26  cmp     word ptr [rcx], 20h ; ' '
0x18000ac2a  jnz     short loc_18000AC3A
0x18000ac2c  sub     rcx, 2
0x18000ac30  lea     rax, [rsp+260h+String]
0x18000ac35  cmp     rcx, rax
0x18000ac38  jnb     short loc_18000AC26
0x18000ac3a  mov     [rcx+2], si
0x18000ac3e  mov     eax, [rbx+0Ch]
0x18000ac41  neg     eax
0x18000ac43  mov     [rbx+14h], rsi
0x18000ac47  sbb     r8d, r8d
0x18000ac4a  and     r8d, 6
0x18000ac4e  add     r8d, 0Ah; Radix
0x18000ac52  cmp     [rsp+260h+String], si
0x18000ac57  jnz     short loc_18000AC60
0x18000ac59  mov     dword ptr [rbx+18h], 1
0x18000ac60  mov     ecx, [rbx+4]
0x18000ac63  sub     ecx, 1
0x18000ac66  jz      short loc_18000AC92
0x18000ac68  sub     ecx, 1
0x18000ac6b  jz      loc_18000AD6B
0x18000ac71  sub     ecx, 1
0x18000ac74  jz      loc_18000AD55
0x18000ac7a  sub     ecx, 1
0x18000ac7d  jz      loc_18000AD43
0x18000ac83  sub     ecx, 1
0x18000ac86  jz      short loc_18000ACD7
0x18000ac88  sub     ecx, 1
0x18000ac8b  jz      short loc_18000ACD7
0x18000ac8d  cmp     ecx, 1
0x18000ac90  jz      short loc_18000ACB7
0x18000ac92  lea     rdx, [rsp+260h+EndPtr]; EndPtr
0x18000ac97  lea     rcx, [rsp+260h+String]; String
0x18000ac9c  call    cs:__imp_wcstol
0x18000aca2  mov     rcx, [rsp+260h+EndPtr]
0x18000aca7  mov     [rbx+20h], ax
0x18000acab  cmp     [rcx], si
0x18000acae  jz      short loc_18000ACB7
0x18000acb0  mov     dword ptr [rbx+14h], 1
0x18000acb7  mov     eax, 1
0x18000acbc  mov     rcx, [rbp+160h+var_30]
0x18000acc3  xor     rcx, rsp; StackCookie
0x18000acc6  call    __security_check_cookie
0x18000accb  add     rsp, 248h
0x18000acd2  pop     rdi
0x18000acd3  pop     rsi
0x18000acd4  pop     rbx
0x18000acd5  pop     rbp
0x18000acd6  retn
0x18000acd7  mov     rcx, [rbx+20h]; void *
0x18000acdb  test    rcx, rcx
0x18000acde  jz      short loc_18000ACEE
0x18000ace0  mov     edx, 2; unsigned __int64
0x18000ace5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000acea  mov     [rbx+20h], rsi
0x18000acee  lea     rax, [rsp+260h+String]
0x18000acf3  mov     rcx, rdi
0x18000acf6  inc     rcx
0x18000acf9  cmp     [rax+rcx*2], si
0x18000acfd  jnz     short loc_18000ACF6
0x18000acff  inc     rcx
0x18000ad02  mov     eax, 2
0x18000ad07  mul     rcx
0x18000ad0a  cmovb   rax, rdi
0x18000ad0e  mov     rcx, rax; unsigned __int64
0x18000ad11  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000ad16  mov     [rbx+20h], rax
0x18000ad1a  test    rax, rax
0x18000ad1d  jz      short loc_18000ACBC
0x18000ad1f  lea     rcx, [rsp+260h+String]
0x18000ad24  inc     rdi
0x18000ad27  cmp     [rcx+rdi*2], si
0x18000ad2b  jnz     short loc_18000AD24
0x18000ad2d  lea     rdx, [rdi+1]; unsigned __int64
0x18000ad31  mov     rcx, rax; unsigned __int16 *
0x18000ad34  lea     r8, [rsp+260h+String]; unsigned __int16 *
0x18000ad39  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ad3e  jmp     loc_18000ACB7
0x18000ad43  lea     rdx, [rsp+260h+EndPtr]; EndPtr
0x18000ad48  lea     rcx, [rsp+260h+String]; String
0x18000ad4d  call    cs:__imp_wcstoul
0x18000ad53  jmp     short loc_18000AD7B
0x18000ad55  lea     rdx, [rsp+260h+EndPtr]; EndPtr
0x18000ad5a  lea     rcx, [rsp+260h+String]; String
0x18000ad5f  call    cs:__imp_wcstoul
0x18000ad65  mov     [rbx+20h], ax
0x18000ad69  jmp     short loc_18000AD7E
0x18000ad6b  lea     rdx, [rsp+260h+EndPtr]; EndPtr
0x18000ad70  lea     rcx, [rsp+260h+String]; String
0x18000ad75  call    cs:__imp_wcstol
0x18000ad7b  mov     [rbx+20h], eax
0x18000ad7e  mov     rax, [rsp+260h+EndPtr]
0x18000ad83  cmp     [rax], si
0x18000ad86  jnz     loc_18000ACB0
0x18000ad8c  jmp     loc_18000ACB7
```
