# UpdateCircularHash

- ea: `0x18004b9f4`
- end: `0x18004bb7c`
- name: `UpdateCircularHash`
- size: `392`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18004b490`
- `0x18004b73c`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x18004b9f4`
- `0x180052520`
- `0x180053780`
- `0x1800537b0`
- `0x180054e10`
- `0x1800569e0`

## pseudocode

```c
__int64 __fastcall UpdateCircularHash(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rdi
  __int64 v5; // rbx
  unsigned int v6; // esi
  unsigned int v7; // r15d
  unsigned int v8; // r8d
  __int64 v9; // r9
  char v10; // dl
  unsigned int v11; // r8d
  __int64 result; // rax
  _BYTE v13[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh]
  __int128 v15; // [rsp+80h] [rbp-80h]
  _BYTE v16[4]; // [rsp+90h] [rbp-70h] BYREF
  int v17; // [rsp+94h] [rbp-6Ch]
  _BYTE v18[24]; // [rsp+110h] [rbp+10h] BYREF

  v3 = a3;
  v17 = 0;
  memset_0(v16, 0, 0x7Cu);
  v14 = 0;
  memset_0(v13, 0, 0x6Cu);
  if ( dword_1800AD940 != 5155 )
    return 0;
  v5 = (unsigned int)Size;
  v6 = HIDWORD(qword_1800AD94C);
  if ( dword_1800AD954 == 1 )
  {
    v15 = xmmword_180098DD8;
    v7 = 16;
    SymCryptHashAppendInternal(SymCryptMd4Algorithm_default, v13, a2, (unsigned int)v3);
    if ( (Size & 0x100000000LL) != 0 )
      SymCryptHashAppendInternal(SymCryptMd4Algorithm_default, v13, qword_1800AD960, (unsigned int)v5);
    SymCryptMd4Result(v13, v18);
  }
  else
  {
    v7 = 20;
    SymCryptSha1Init(v16);
    SymCryptSha1Append(v16, a2, v3);
    if ( (Size & 0x100000000LL) != 0 )
      SymCryptSha1Append(v16, qword_1800AD960, v5);
    SymCryptSha1Result(v16, v18);
  }
  v8 = v6;
  v9 = 0;
  do
  {
    v10 = v18[v9];
    v9 = (unsigned int)(v9 + 1);
    v11 = v8 < (unsigned int)v5 ? v8 : 0;
    *((_BYTE *)qword_1800AD960 + v11) ^= v10;
    v8 = v11 + 1;
  }
  while ( (unsigned int)v9 < v7 );
  result = 1;
  HIDWORD(qword_1800AD94C) = (v6 + (unsigned int)qword_1800AD94C) % (unsigned int)v5;
  return result;
}

```

## disassembly

```asm
0x18004b9f4  mov     [rsp-8+arg_0], rbx
0x18004b9f9  push    rbp
0x18004b9fa  push    rsi
0x18004b9fb  push    rdi
0x18004b9fc  push    r14
0x18004b9fe  push    r15
0x18004ba00  lea     rbp, [rsp-30h]
0x18004ba05  sub     rsp, 130h
0x18004ba0c  mov     rax, cs:__security_cookie
0x18004ba13  xor     rax, rsp
0x18004ba16  mov     [rbp+50h+var_28], rax
0x18004ba1a  xor     eax, eax
0x18004ba1c  mov     edi, r8d
0x18004ba1f  mov     r14, rdx
0x18004ba22  mov     [rbp+50h+var_BC], eax
0x18004ba25  xor     edx, edx; Val
0x18004ba27  lea     rcx, [rbp+50h+var_C0]; void *
0x18004ba2b  lea     r8d, [rax+7Ch]; Size
0x18004ba2f  call    memset_0
0x18004ba34  xor     eax, eax
0x18004ba36  lea     rcx, [rsp+150h+var_130]; void *
0x18004ba3b  xor     edx, edx; Val
0x18004ba3d  mov     [rsp+150h+var_12C], eax
0x18004ba41  lea     r8d, [rax+6Ch]; Size
0x18004ba45  call    memset_0
0x18004ba4a  cmp     cs:dword_1800AD940, 1423h
0x18004ba54  jnz     loc_18004BB56
0x18004ba5a  cmp     cs:dword_1800AD954, 1
0x18004ba61  mov     ebx, dword ptr cs:Size
0x18004ba67  mov     esi, dword ptr cs:qword_1800AD94C+4
0x18004ba6d  jnz     short loc_18004BACF
0x18004ba6f  movups  xmm0, cs:xmmword_180098DD8
0x18004ba76  mov     r9d, edi
0x18004ba79  lea     rdx, [rsp+150h+var_130]
0x18004ba7e  mov     r8, r14
0x18004ba81  lea     rcx, SymCryptMd4Algorithm_default
0x18004ba88  movdqu  [rbp+50h+var_D0], xmm0
0x18004ba8d  mov     r15d, 10h
0x18004ba93  call    SymCryptHashAppendInternal
0x18004ba98  test    byte ptr cs:Size+4, 1
0x18004ba9f  lea     rdi, qword_1800AD960
0x18004baa6  jz      short loc_18004BABF
0x18004baa8  mov     r9d, ebx
0x18004baab  lea     rdx, [rsp+150h+var_130]
0x18004bab0  mov     r8, rdi
0x18004bab3  lea     rcx, SymCryptMd4Algorithm_default
0x18004baba  call    SymCryptHashAppendInternal
0x18004babf  lea     rdx, [rbp+50h+var_40]
0x18004bac3  lea     rcx, [rsp+150h+var_130]
0x18004bac8  call    SymCryptMd4Result
0x18004bacd  jmp     short loc_18004BB19
0x18004bacf  lea     rcx, [rbp+50h+var_C0]
0x18004bad3  mov     r15d, 14h
0x18004bad9  call    SymCryptSha1Init
0x18004bade  mov     r8, rdi
0x18004bae1  lea     rcx, [rbp+50h+var_C0]
0x18004bae5  mov     rdx, r14
0x18004bae8  call    SymCryptSha1Append
0x18004baed  test    byte ptr cs:Size+4, 1
0x18004baf4  lea     rdi, qword_1800AD960
0x18004bafb  jz      short loc_18004BB0C
0x18004bafd  mov     r8, rbx
0x18004bb00  lea     rcx, [rbp+50h+var_C0]
0x18004bb04  mov     rdx, rdi
0x18004bb07  call    SymCryptSha1Append
0x18004bb0c  lea     rdx, [rbp+50h+var_40]
0x18004bb10  lea     rcx, [rbp+50h+var_C0]
0x18004bb14  call    SymCryptSha1Result
0x18004bb19  mov     r8d, esi
0x18004bb1c  xor     r9d, r9d
0x18004bb1f  mov     dl, [rbp+r9+50h+var_40]
0x18004bb24  cmp     r8d, ebx
0x18004bb27  sbb     eax, eax
0x18004bb29  inc     r9d
0x18004bb2c  and     eax, r8d
0x18004bb2f  mov     r8d, eax
0x18004bb32  xor     [rax+rdi], dl
0x18004bb35  inc     r8d
0x18004bb38  cmp     r9d, r15d
0x18004bb3b  jb      short loc_18004BB1F
0x18004bb3d  mov     eax, dword ptr cs:qword_1800AD94C
0x18004bb43  xor     edx, edx
0x18004bb45  add     eax, esi
0x18004bb47  div     ebx
0x18004bb49  mov     eax, 1
0x18004bb4e  mov     dword ptr cs:qword_1800AD94C+4, edx
0x18004bb54  jmp     short loc_18004BB58
0x18004bb56  xor     eax, eax
0x18004bb58  mov     rcx, [rbp+50h+var_28]
0x18004bb5c  xor     rcx, rsp; StackCookie
0x18004bb5f  call    __security_check_cookie
0x18004bb64  mov     rbx, [rsp+150h+arg_0]
0x18004bb6c  add     rsp, 130h
0x18004bb73  pop     r15
0x18004bb75  pop     r14
0x18004bb77  pop     rdi
0x18004bb78  pop     rsi
0x18004bb79  pop     rbp
0x18004bb7a  retn
```
