# GetInfCustomVar

- ea: `0x14000aa6c`
- end: `0x14000ac00`
- name: `GetInfCustomVar`
- size: `404`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14000488c`
- `0x14000ac08`
- `0x14000b2d8`

## callees

- `0x140008620`
- `0x14000aa6c`
- `0x14000dfd8`
- `0x14000e028`
- `0x14000e412`
- `0x14000e450`

## pseudocode

```c
__int64 __fastcall GetInfCustomVar(__int64 a1, const char *a2, int a3, __int64 a4)
{
  __int64 v8; // r11
  const char *v9; // r9
  _BYTE *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r8
  bool v13; // zf
  _BYTE *v14; // rax
  __int64 v15; // r8
  _BYTE *v16; // rax
  __int64 v17; // r9
  const char *v18; // rax
  _BYTE *v19; // rcx
  __int64 v20; // rdx
  _BYTE *v21; // rax
  __int64 result; // rax
  _BYTE v23[560]; // [rsp+30h] [rbp-278h] BYREF
  _BYTE v24[32]; // [rsp+260h] [rbp-48h] BYREF

  memset_0(v23, 0, sizeof(v23));
  v8 = 2147483646;
  v9 = "Inf";
  v10 = v24;
  v11 = 2147483646;
  v12 = 32;
  do
  {
    if ( !v11 )
      break;
    if ( !*v9 )
      break;
    *v10++ = *v9++;
    --v11;
    --v12;
  }
  while ( v12 );
  v13 = v12 == 0;
  v14 = v10 - 1;
  v15 = 32;
  if ( !v13 )
    v14 = v10;
  *v14 = 0;
  v16 = v24;
  do
  {
    if ( !*v16 )
      break;
    ++v16;
    --v15;
  }
  while ( v15 );
  v17 = (32 - v15) & -(__int64)(v15 != 0);
  if ( !v15 )
    goto LABEL_22;
  v18 = a2;
  v19 = &v24[v17];
  v20 = 32 - v17;
  if ( 32 != v17 )
  {
    do
    {
      if ( !v8 )
        break;
      if ( !*v18 )
        break;
      *v19++ = *v18++;
      --v8;
      --v20;
    }
    while ( v20 );
  }
  v21 = v19 - 1;
  if ( v20 )
    v21 = v19;
  *v21 = 0;
  if ( v20 )
  {
    result = VarFind(*(_QWORD *)(a1 + 16), (__int64)v24, (__int64)v23);
    if ( a3 && result && !*(_DWORD *)(a1 + 32) )
      return result & -(__int64)(VarSet(*(_QWORD *)(a1 + 24), v24, *(_QWORD *)(result + 8), a4) != 0);
  }
  else
  {
LABEL_22:
    ErrSet(a4, (int)"Parameter name exceeds maximum length(%1): %2", "%d%s", 31, a2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000aa6c  mov     [rsp+arg_10], rbx
0x14000aa71  push    rbp
0x14000aa72  push    rsi
0x14000aa73  push    rdi
0x14000aa74  sub     rsp, 290h
0x14000aa7b  mov     rax, cs:__security_cookie
0x14000aa82  xor     rax, rsp
0x14000aa85  mov     [rsp+2A8h+var_28], rax
0x14000aa8d  mov     ebp, r8d
0x14000aa90  mov     rbx, rdx
0x14000aa93  mov     rdi, rcx
0x14000aa96  xor     edx, edx; Val
0x14000aa98  mov     r8d, 230h; Size
0x14000aa9e  lea     rcx, [rsp+2A8h+var_278]; void *
0x14000aaa3  mov     rsi, r9
0x14000aaa6  call    memset_0
0x14000aaab  mov     r11d, 7FFFFFFEh
0x14000aab1  lea     r9, aInf; "Inf"
0x14000aab8  mov     edx, 20h ; ' '
0x14000aabd  lea     rcx, [rsp+2A8h+var_48]
0x14000aac5  mov     eax, r11d
0x14000aac8  mov     r8d, edx
0x14000aacb  test    rax, rax
0x14000aace  jz      short loc_14000AAEA
0x14000aad0  mov     r10b, [r9]
0x14000aad3  test    r10b, r10b
0x14000aad6  jz      short loc_14000AAEA
0x14000aad8  mov     [rcx], r10b
0x14000aadb  inc     r9
0x14000aade  inc     rcx
0x14000aae1  dec     rax
0x14000aae4  sub     r8, 1
0x14000aae8  jnz     short loc_14000AACB
0x14000aaea  test    r8, r8
0x14000aaed  lea     rax, [rcx-1]
0x14000aaf1  mov     r8, rdx
0x14000aaf4  cmovnz  rax, rcx
0x14000aaf8  mov     byte ptr [rax], 0
0x14000aafb  lea     rax, [rsp+2A8h+var_48]
0x14000ab03  cmp     byte ptr [rax], 0
0x14000ab06  jz      short loc_14000AB11
0x14000ab08  inc     rax
0x14000ab0b  sub     r8, 1
0x14000ab0f  jnz     short loc_14000AB03
0x14000ab11  mov     rcx, rdx
0x14000ab14  mov     rax, r8
0x14000ab17  sub     rcx, r8
0x14000ab1a  neg     rax
0x14000ab1d  sbb     r9, r9
0x14000ab20  and     r9, rcx
0x14000ab23  test    r8, r8
0x14000ab26  jz      loc_14000ABBA
0x14000ab2c  lea     rcx, [rsp+2A8h+var_48]
0x14000ab34  mov     rax, rbx
0x14000ab37  lea     rcx, [rcx+r9]
0x14000ab3b  sub     rdx, r9
0x14000ab3e  jz      short loc_14000AB5F
0x14000ab40  test    r11, r11
0x14000ab43  jz      short loc_14000AB5F
0x14000ab45  mov     r8b, [rax]
0x14000ab48  test    r8b, r8b
0x14000ab4b  jz      short loc_14000AB5F
0x14000ab4d  mov     [rcx], r8b
0x14000ab50  inc     rax
0x14000ab53  inc     rcx
0x14000ab56  dec     r11
0x14000ab59  sub     rdx, 1
0x14000ab5d  jnz     short loc_14000AB40
0x14000ab5f  test    rdx, rdx
0x14000ab62  lea     rax, [rcx-1]
0x14000ab66  cmovnz  rax, rcx
0x14000ab6a  mov     byte ptr [rax], 0
0x14000ab6d  jz      short loc_14000ABBA
0x14000ab6f  mov     rcx, [rdi+10h]
0x14000ab73  lea     r8, [rsp+2A8h+var_278]
0x14000ab78  lea     rdx, [rsp+2A8h+var_48]
0x14000ab80  call    VarFind
0x14000ab85  mov     rbx, rax
0x14000ab88  test    ebp, ebp
0x14000ab8a  jz      short loc_14000ABDD
0x14000ab8c  test    rax, rax
0x14000ab8f  jz      short loc_14000ABDD
0x14000ab91  cmp     dword ptr [rdi+20h], 0
0x14000ab95  jnz     short loc_14000ABDD
0x14000ab97  mov     r8, [rax+8]
0x14000ab9b  lea     rdx, [rsp+2A8h+var_48]
0x14000aba3  mov     rcx, [rdi+18h]
0x14000aba7  mov     r9, rsi
0x14000abaa  call    VarSet
0x14000abaf  neg     rax
0x14000abb2  sbb     rax, rax
0x14000abb5  and     rax, rbx
0x14000abb8  jmp     short loc_14000ABDD
0x14000abba  mov     r9d, 1Fh
0x14000abc0  mov     [rsp+2A8h+var_288], rbx
0x14000abc5  lea     r8, aDS; "%d%s"
0x14000abcc  mov     rcx, rsi
0x14000abcf  lea     rdx, aParameterNameE; "Parameter name exceeds maximum length(%"...
0x14000abd6  call    ErrSet
0x14000abdb  xor     eax, eax
0x14000abdd  mov     rcx, [rsp+2A8h+var_28]
0x14000abe5  xor     rcx, rsp; StackCookie
0x14000abe8  call    __security_check_cookie
0x14000abed  mov     rbx, [rsp+2A8h+arg_10]
0x14000abf5  add     rsp, 290h
0x14000abfc  pop     rdi
0x14000abfd  pop     rsi
0x14000abfe  pop     rbp
0x14000abff  retn
```
