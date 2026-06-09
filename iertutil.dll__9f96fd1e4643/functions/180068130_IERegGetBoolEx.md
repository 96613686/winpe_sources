# IERegGetBoolEx

- ea: `0x180068130`
- end: `0x180068368`
- name: `IERegGetBoolEx`
- size: `568`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800677bc`
- `0x180068130`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006825a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180068286`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800682b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800682de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180068306`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006832e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006825a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180068286`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800682b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800682de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180068306`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006832e`

## pseudocode

```c
__int64 __fastcall IERegGetBoolEx(unsigned int a1, _DWORD *a2, wchar_t *a3, wchar_t *a4)
{
  int v6; // eax
  unsigned int Value; // ebx
  unsigned int v8; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v9; // [rsp+44h] [rbp-15h] BYREF
  unsigned int v10; // [rsp+48h] [rbp-11h] BYREF
  unsigned int v11; // [rsp+4Ch] [rbp-Dh] BYREF
  WCHAR String2[16]; // [rsp+50h] [rbp-9h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v6 = dword_1800E4B90[10 * a1];
  if ( v6 != 4 )
  {
    if ( v6 == 1 )
    {
      v8 = 1;
      v10 = 6;
      v9 = 32;
      Value = IERegGetValueEx(a1, &v8, String2, &v9, &v10, a3, a4);
      if ( (Value & 0x80000000) != 0 )
        return Value;
      if ( v8 == 1 )
      {
        if ( CompareStringW(0x7Fu, 1u, L"YES", -1, String2, -1) == 2
          || CompareStringW(0x7Fu, 1u, L"TRUE", -1, String2, -1) == 2
          || CompareStringW(0x7Fu, 1u, L"1", -1, String2, -1) == 2 )
        {
          *a2 = 1;
          return Value;
        }
        if ( CompareStringW(0x7Fu, 1u, L"NO", -1, String2, -1) == 2
          || CompareStringW(0x7Fu, 1u, L"FALSE", -1, String2, -1) == 2
          || CompareStringW(0x7Fu, 1u, L"0", -1, String2, -1) == 2 )
        {
          *a2 = 0;
          return Value;
        }
      }
    }
    return (unsigned int)-2147219711;
  }
  v10 = 4;
  v11 = 0;
  v8 = 0;
  v9 = 0;
  Value = IERegGetValueEx(a1, &v11, &v8, &v10, &v9, a3, a4);
  if ( (Value & 0x80000000) == 0 )
  {
    if ( v11 == 4 )
    {
      *a2 = v8 != 0;
      return Value;
    }
    return (unsigned int)-2147219711;
  }
  return Value;
}

```

## disassembly

```asm
0x180068130  push    rbp
0x180068132  push    rbx
0x180068133  push    rsi
0x180068134  push    rdi
0x180068135  push    r12
0x180068137  push    r15
0x180068139  lea     rbp, [rsp-2Fh]
0x18006813e  sub     rsp, 88h
0x180068145  mov     rax, cs:__security_cookie
0x18006814c  xor     rax, rsp
0x18006814f  mov     [rbp+57h+var_40], rax
0x180068153  mov     r10d, ecx
0x180068156  mov     rdi, rdx
0x180068159  test    rdx, rdx
0x18006815c  jnz     short loc_180068168
0x18006815e  mov     eax, 80004003h
0x180068163  jmp     loc_18006834C
0x180068168  lea     rcx, [r10+r10*4]
0x18006816c  lea     rax, dword_1800E4B90
0x180068173  mov     eax, [rax+rcx*8]
0x180068176  cmp     eax, 4
0x180068179  jnz     short loc_1800681DD
0x18006817b  mov     [rsp+0B0h+var_80], r9; wchar_t *
0x180068180  lea     rdx, [rbp+57h+var_64]; unsigned int *
0x180068184  mov     qword ptr [rsp+0B0h+cchCount2], r8; Str
0x180068189  lea     r9, [rbp+57h+var_68]; unsigned int *
0x18006818d  mov     [rbp+57h+var_68], eax
0x180068190  lea     r8, [rbp+57h+var_70]; void *
0x180068194  lea     rax, [rbp+57h+var_6C]
0x180068198  mov     [rbp+57h+var_64], 0
0x18006819f  mov     ecx, r10d; unsigned int
0x1800681a2  mov     [rsp+0B0h+lpString2], rax; unsigned int *
0x1800681a7  mov     [rbp+57h+var_70], 0
0x1800681ae  mov     [rbp+57h+var_6C], 0
0x1800681b5  call    ?IERegGetValueEx@@YAJIPEAKPEAX00PEBG2@Z; IERegGetValueEx(uint,ulong *,void *,ulong *,ulong *,ushort const *,ushort const *)
0x1800681ba  mov     ebx, eax
0x1800681bc  test    eax, eax
0x1800681be  js      loc_18006834A
0x1800681c4  cmp     [rbp+57h+var_64], 4
0x1800681c8  jnz     loc_180068345
0x1800681ce  xor     ecx, ecx
0x1800681d0  cmp     [rbp+57h+var_70], ecx
0x1800681d3  setnz   cl
0x1800681d6  mov     [rdi], ecx
0x1800681d8  jmp     loc_18006834A
0x1800681dd  mov     esi, 1
0x1800681e2  cmp     eax, esi
0x1800681e4  jnz     loc_180068345
0x1800681ea  mov     [rsp+0B0h+var_80], r9; wchar_t *
0x1800681ef  lea     rax, [rbp+57h+var_68]
0x1800681f3  mov     qword ptr [rsp+0B0h+cchCount2], r8; Str
0x1800681f8  lea     r9, [rbp+57h+var_6C]; unsigned int *
0x1800681fc  lea     r8, [rbp+57h+String2]; void *
0x180068200  mov     [rbp+57h+var_70], esi
0x180068203  lea     rdx, [rbp+57h+var_70]; unsigned int *
0x180068207  mov     [rbp+57h+var_68], 6
0x18006820e  mov     ecx, r10d; unsigned int
0x180068211  mov     [rbp+57h+var_6C], 20h ; ' '
0x180068218  mov     [rsp+0B0h+lpString2], rax; unsigned int *
0x18006821d  call    ?IERegGetValueEx@@YAJIPEAKPEAX00PEBG2@Z; IERegGetValueEx(uint,ulong *,void *,ulong *,ulong *,ushort const *,ushort const *)
0x180068222  mov     ebx, eax
0x180068224  test    eax, eax
0x180068226  js      loc_18006834A
0x18006822c  cmp     [rbp+57h+var_70], esi
0x18006822f  jnz     loc_180068345
0x180068235  or      r15d, 0FFFFFFFFh
0x180068239  lea     rax, [rbp+57h+String2]
0x18006823d  lea     r12d, [rsi+7Eh]
0x180068241  mov     [rsp+0B0h+cchCount2], r15d; cchCount2
0x180068246  mov     r9d, r15d; cchCount1
0x180068249  mov     [rsp+0B0h+lpString2], rax; lpString2
0x18006824e  mov     ecx, r12d; Locale
0x180068251  lea     r8, aYes_0; "YES"
0x180068258  mov     edx, esi; dwCmpFlags
0x18006825a  call    cs:__imp_CompareStringW
0x180068260  cmp     eax, 2
0x180068263  jz      loc_180068341
0x180068269  lea     rax, [rbp+57h+String2]
0x18006826d  mov     [rsp+0B0h+cchCount2], r15d; cchCount2
0x180068272  mov     r9d, r15d; cchCount1
0x180068275  mov     [rsp+0B0h+lpString2], rax; lpString2
0x18006827a  lea     r8, aTrue_0; "TRUE"
0x180068281  mov     edx, esi; dwCmpFlags
0x180068283  mov     ecx, r12d; Locale
0x180068286  call    cs:__imp_CompareStringW
0x18006828c  cmp     eax, 2
0x18006828f  jz      loc_180068341
0x180068295  lea     rax, [rbp+57h+String2]
0x180068299  mov     [rsp+0B0h+cchCount2], r15d; cchCount2
0x18006829e  mov     r9d, r15d; cchCount1
0x1800682a1  mov     [rsp+0B0h+lpString2], rax; lpString2
0x1800682a6  lea     r8, a1; "1"
0x1800682ad  mov     edx, esi; dwCmpFlags
0x1800682af  mov     ecx, r12d; Locale
0x1800682b2  call    cs:__imp_CompareStringW
0x1800682b8  cmp     eax, 2
0x1800682bb  jz      loc_180068341
0x1800682c1  lea     rax, [rbp+57h+String2]
0x1800682c5  mov     [rsp+0B0h+cchCount2], r15d; cchCount2
0x1800682ca  mov     r9d, r15d; cchCount1
0x1800682cd  mov     [rsp+0B0h+lpString2], rax; lpString2
0x1800682d2  lea     r8, aNo_1; "NO"
0x1800682d9  mov     edx, esi; dwCmpFlags
0x1800682db  mov     ecx, r12d; Locale
0x1800682de  call    cs:__imp_CompareStringW
0x1800682e4  cmp     eax, 2
0x1800682e7  jz      short loc_180068339
0x1800682e9  lea     rax, [rbp+57h+String2]
0x1800682ed  mov     [rsp+0B0h+cchCount2], r15d; cchCount2
0x1800682f2  mov     r9d, r15d; cchCount1
0x1800682f5  mov     [rsp+0B0h+lpString2], rax; lpString2
0x1800682fa  lea     r8, aFalse_0; "FALSE"
0x180068301  mov     edx, esi; dwCmpFlags
0x180068303  mov     ecx, r12d; Locale
0x180068306  call    cs:__imp_CompareStringW
0x18006830c  cmp     eax, 2
0x18006830f  jz      short loc_180068339
0x180068311  lea     rax, [rbp+57h+String2]
0x180068315  mov     [rsp+0B0h+cchCount2], r15d; cchCount2
0x18006831a  mov     r9d, r15d; cchCount1
0x18006831d  mov     [rsp+0B0h+lpString2], rax; lpString2
0x180068322  lea     r8, a0_0; "0"
0x180068329  mov     edx, esi; dwCmpFlags
0x18006832b  mov     ecx, r12d; Locale
0x18006832e  call    cs:__imp_CompareStringW
0x180068334  cmp     eax, 2
0x180068337  jnz     short loc_180068345
0x180068339  mov     dword ptr [rdi], 0
0x18006833f  jmp     short loc_18006834A
0x180068341  mov     [rdi], esi
0x180068343  jmp     short loc_18006834A
0x180068345  mov     ebx, 80040701h
0x18006834a  mov     eax, ebx
0x18006834c  mov     rcx, [rbp+57h+var_40]
0x180068350  xor     rcx, rsp; StackCookie
0x180068353  call    __security_check_cookie
0x180068358  add     rsp, 88h
0x18006835f  pop     r15
0x180068361  pop     r12
0x180068363  pop     rdi
0x180068364  pop     rsi
0x180068365  pop     rbx
0x180068366  pop     rbp
0x180068367  retn
```
