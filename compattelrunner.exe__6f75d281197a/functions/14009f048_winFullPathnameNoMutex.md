# winFullPathnameNoMutex

- ea: `0x14009f048`
- end: `0x14009f20e`
- name: `winFullPathnameNoMutex`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14009efc0`

## callees

- `0x140062d60`
- `0x14008ac90`
- `0x14008ccd0`
- `0x14009f048`
- `0x14009fa4c`
- `0x1400a1220`
- `0x1400a1544`
- `0x1400a8010`

## string_xrefs

- `0x14009f12e`: `winFullPathname1`
- `0x14009f1b3`: `winFullPathname2`

## pseudocode

```c
__int64 __fastcall winFullPathnameNoMutex(__int64 a1, unsigned __int64 a2, int a3, __int64 a4)
{
  unsigned __int8 *v7; // rbx
  __int64 v8; // rcx
  __int64 v10; // rax
  __int64 v11; // rdi
  int v12; // eax
  DWORD v13; // eax
  unsigned int v14; // ebp
  __int64 v15; // rsi
  DWORD v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rcx

  v7 = (unsigned __int8 *)a2;
  if ( *(_BYTE *)a2 == 47 )
  {
    if ( (a2 = *(unsigned __int8 *)(a2 + 1), (byte_1400B2300[a2] & 2) != 0) && v7[2] == 58
      || (_BYTE)a2 == 92 && v7[2] == 92 && v7[3] == 63 && v7[4] == 92 )
    {
      ++v7;
    }
  }
  if ( sqlite3_data_directory && *v7 != 47 && *v7 != 92 && ((byte_1400B2300[*v7] & 2) == 0 || v7[1] != 58) )
  {
    v8 = *(unsigned int *)(a1 + 8);
    if ( a3 < (int)v8 )
      v8 = (unsigned int)a3;
    sqlite3_snprintf(v8, a4, "%s%c%s");
    return 0;
  }
  v10 = winUtf8ToUnicode(v7, a2, 92);
  v11 = v10;
  if ( !v10 )
    return 3082;
  v12 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))off_1400C5C50)(v10, 0, 0, 0);
  if ( v12 )
  {
    v14 = v12 + 3;
    v15 = sqlite3MallocZero(2LL * (unsigned int)(v12 + 3));
    if ( v15 )
    {
      if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD))off_1400C5C50)(v11, v14, v15, 0) )
      {
        sqlite3_free(v11);
        sqlite3_free(v15);
        v16 = off_1400C5C68();
        return winLogErrorAtLine(782, v16, (unsigned int)"winFullPathname2", (_DWORD)v7, 51522);
      }
      sqlite3_free(v11);
      v17 = winUnicodeToUtf8(v15);
      sqlite3_free(v15);
      if ( v17 )
      {
        v18 = *(unsigned int *)(a1 + 8);
        if ( a3 < (int)v18 )
          v18 = (unsigned int)a3;
        sqlite3_snprintf(v18, a4, "%s", v17);
        sqlite3_free(v17);
        return 0;
      }
    }
    else
    {
      sqlite3_free(v11);
    }
    return 3082;
  }
  sqlite3_free(v11);
  v13 = off_1400C5C68();
  return winLogErrorAtLine(782, v13, (unsigned int)"winFullPathname1", (_DWORD)v7, 51509);
}

```

## disassembly

```asm
0x14009f048  push    rbx
0x14009f04a  push    rbp
0x14009f04b  push    rsi
0x14009f04c  push    rdi
0x14009f04d  push    r13
0x14009f04f  push    r14
0x14009f051  push    r15
0x14009f053  sub     rsp, 30h
0x14009f057  cmp     byte ptr [rdx], 2Fh ; '/'
0x14009f05a  mov     r14d, r8d
0x14009f05d  mov     r13, rcx
0x14009f060  mov     r8d, 5Ch ; '\'
0x14009f066  lea     rcx, byte_1400B2300
0x14009f06d  mov     r15, r9
0x14009f070  mov     rbx, rdx
0x14009f073  jnz     short loc_14009F09F
0x14009f075  movzx   edx, byte ptr [rdx+1]
0x14009f079  test    byte ptr [rdx+rcx], 2
0x14009f07d  jz      short loc_14009F085
0x14009f07f  cmp     byte ptr [rbx+2], 3Ah ; ':'
0x14009f083  jz      short loc_14009F09C
0x14009f085  cmp     dl, r8b
0x14009f088  jnz     short loc_14009F09F
0x14009f08a  cmp     [rbx+2], r8b
0x14009f08e  jnz     short loc_14009F09F
0x14009f090  cmp     byte ptr [rbx+3], 3Fh ; '?'
0x14009f094  jnz     short loc_14009F09F
0x14009f096  cmp     [rbx+4], r8b
0x14009f09a  jnz     short loc_14009F09F
0x14009f09c  inc     rbx
0x14009f09f  mov     r9, cs:sqlite3_data_directory
0x14009f0a6  test    r9, r9
0x14009f0a9  jz      short loc_14009F0EF
0x14009f0ab  cmp     byte ptr [rbx], 2Fh ; '/'
0x14009f0ae  jz      short loc_14009F0EF
0x14009f0b0  cmp     [rbx], r8b
0x14009f0b3  jz      short loc_14009F0EF
0x14009f0b5  movzx   eax, byte ptr [rbx]
0x14009f0b8  test    byte ptr [rax+rcx], 2
0x14009f0bc  jz      short loc_14009F0C4
0x14009f0be  cmp     byte ptr [rbx+1], 3Ah ; ':'
0x14009f0c2  jz      short loc_14009F0EF
0x14009f0c4  mov     ecx, [r13+8]
0x14009f0c8  mov     rdx, r15
0x14009f0cb  cmp     r14d, ecx
0x14009f0ce  mov     [rsp+68h+var_40], rbx
0x14009f0d3  mov     [rsp+68h+var_48], r8d
0x14009f0d8  lea     r8, aSCS; "%s%c%s"
0x14009f0df  cmovl   ecx, r14d
0x14009f0e3  call    sqlite3_snprintf
0x14009f0e8  xor     eax, eax
0x14009f0ea  jmp     loc_14009F170
0x14009f0ef  mov     rcx, rbx
0x14009f0f2  call    winUtf8ToUnicode
0x14009f0f7  mov     rdi, rax
0x14009f0fa  test    rax, rax
0x14009f0fd  jz      short loc_14009F16B
0x14009f0ff  mov     rcx, rax
0x14009f102  xor     r9d, r9d
0x14009f105  mov     rax, cs:off_1400C5C50
0x14009f10c  xor     r8d, r8d
0x14009f10f  xor     edx, edx
0x14009f111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f116  test    eax, eax
0x14009f118  jnz     short loc_14009F14E
0x14009f11a  mov     rcx, rdi
0x14009f11d  call    sqlite3_free
0x14009f122  mov     rax, cs:off_1400C5C68
0x14009f129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f12e  lea     r8, aWinfullpathnam; "winFullPathname1"
0x14009f135  mov     [rsp+68h+var_48], 0C935h
0x14009f13d  mov     r9, rbx
0x14009f140  mov     edx, eax
0x14009f142  mov     ecx, 30Eh
0x14009f147  call    winLogErrorAtLine
0x14009f14c  jmp     short loc_14009F170
0x14009f14e  lea     ebp, [rax+3]
0x14009f151  mov     ecx, ebp
0x14009f153  add     rcx, rcx; Size
0x14009f156  call    sqlite3MallocZero
0x14009f15b  mov     rsi, rax
0x14009f15e  mov     rcx, rdi
0x14009f161  test    rax, rax
0x14009f164  jnz     short loc_14009F17F
0x14009f166  call    sqlite3_free
0x14009f16b  mov     eax, 0C0Ah
0x14009f170  add     rsp, 30h
0x14009f174  pop     r15
0x14009f176  pop     r14
0x14009f178  pop     r13
0x14009f17a  pop     rdi
0x14009f17b  pop     rsi
0x14009f17c  pop     rbp
0x14009f17d  pop     rbx
0x14009f17e  retn
0x14009f17f  mov     rax, cs:off_1400C5C50
0x14009f186  xor     r9d, r9d
0x14009f189  mov     r8, rsi
0x14009f18c  mov     edx, ebp
0x14009f18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f193  mov     rcx, rdi
0x14009f196  test    eax, eax
0x14009f198  jnz     short loc_14009F1C7
0x14009f19a  call    sqlite3_free
0x14009f19f  mov     rcx, rsi
0x14009f1a2  call    sqlite3_free
0x14009f1a7  mov     rax, cs:off_1400C5C68
0x14009f1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f1b3  lea     r8, aWinfullpathnam_0; "winFullPathname2"
0x14009f1ba  mov     [rsp+68h+var_48], 0C942h
0x14009f1c2  jmp     loc_14009F13D
0x14009f1c7  call    sqlite3_free
0x14009f1cc  mov     rcx, rsi
0x14009f1cf  call    winUnicodeToUtf8
0x14009f1d4  mov     rcx, rsi
0x14009f1d7  mov     rbx, rax
0x14009f1da  call    sqlite3_free
0x14009f1df  test    rbx, rbx
0x14009f1e2  jz      short loc_14009F16B
0x14009f1e4  mov     ecx, [r13+8]
0x14009f1e8  lea     r8, aS_6; "%s"
0x14009f1ef  cmp     r14d, ecx
0x14009f1f2  mov     r9, rbx
0x14009f1f5  mov     rdx, r15
0x14009f1f8  cmovl   ecx, r14d
0x14009f1fc  call    sqlite3_snprintf
0x14009f201  mov     rcx, rbx
0x14009f204  call    sqlite3_free
0x14009f209  jmp     loc_14009F0E8
```
