# RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)

- ea: `0x18000aa1c`
- end: `0x18000ad38`
- name: `?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z`
- size: `796`
- prototype: `int(RtlNameValueArray *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ad40`
- `0x18000adf8`

## callees

- `0x180007010`
- `0x18000aa1c`
- `0x18000bff2`
- `0x18000bffe`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000aa9b`
- `msvcrt!wcscpy_s` at `0x18000aab2`
- `msvcrt!wcscpy_s` at `0x18000aa9b`
- `msvcrt!wcscpy_s` at `0x18000aab2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aa73`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ab54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ac52`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aa73`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ab54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ac52`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000ab74`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000ac72`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000ab74`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000ac72`

## pseudocode

```c
__int64 __fastcall RtlNameValueArray::Insert(
        RtlNameValueArray *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int64 a5)
{
  __int64 v5; // rax
  __int64 v7; // rcx
  rsize_t v10; // rsi
  rsize_t v11; // r12
  SIZE_T v12; // rdi
  wchar_t *v13; // rax
  wchar_t *v14; // r13
  unsigned __int64 v15; // r15
  _QWORD *v16; // r12
  unsigned __int64 v17; // rsi
  unsigned __int64 v18; // rcx
  __int64 v20; // rdi
  unsigned __int64 v21; // rdx
  __int64 v22; // r9
  unsigned __int64 v23; // rdi
  void *v24; // r8
  SIZE_T v25; // r15
  HANDLE v26; // rcx
  void *v27; // rax
  LPVOID v28; // r14
  unsigned __int64 v29; // rcx
  _QWORD *v30; // r9
  unsigned int v31; // r10d
  wchar_t **v32; // rdx
  unsigned __int64 v33; // rsi
  __int64 v34; // rdi
  unsigned __int64 v35; // rdx
  __int64 v36; // r9
  unsigned __int64 v37; // rdi
  void *v38; // r8
  SIZE_T v39; // r14
  HANDLE v40; // rcx
  void *v41; // rax
  LPVOID v42; // rsi
  unsigned __int64 v43; // rcx
  SIZE_T v44; // r10
  wchar_t **v45; // rdi
  unsigned __int64 v46; // rcx
  void *v47; // r9
  unsigned __int64 v48; // [rsp+20h] [rbp-10h] BYREF
  size_t Size; // [rsp+70h] [rbp+40h] BYREF
  SIZE_T dwBytes; // [rsp+78h] [rbp+48h] BYREF

  dwBytes = (SIZE_T)a2;
  v5 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  v10 = v7 + 1;
  do
    ++v5;
  while ( a4[v5] );
  v11 = v5 + 1;
  v12 = 2 * (v5 + 1 + v10);
  v13 = (wchar_t *)HeapAlloc(*(HANDLE *)this, 0, v12);
  v14 = v13;
  if ( v13 )
  {
    memset_0(v13, 0, v12);
    wcscpy_s(v14, v10, a3);
    wcscpy_s(&v14[v10], v11, a4);
    v15 = a5;
    v16 = (_QWORD *)((char *)this + 16);
    v17 = *((_QWORD *)this + 2);
    v18 = *((_QWORD *)this + 3);
    Size = 0;
    if ( a5 >= v17 )
    {
      if ( v17 < v18 )
      {
LABEL_19:
        v29 = *((_QWORD *)this + 1);
        dwBytes = 0;
        if ( (int)ULongLongMult(v29, v17, &dwBytes) >= 0 )
        {
          v32 = (wchar_t **)(*((_QWORD *)this + 5) + dwBytes);
          if ( (unsigned __int64)v32 >= *((_QWORD *)this + 5) )
          {
            *v32 = v14;
            *v16 = *v30 + 1LL;
            return v31;
          }
        }
        return 534;
      }
      if ( v17 + 1 <= v18 )
        return 160;
      v20 = *((_QWORD *)this + 4) - 1LL;
      if ( *((_QWORD *)this + 4) + v17 >= v17 + 1 )
      {
        v21 = *((_QWORD *)this + 1);
        dwBytes = 0;
        if ( (int)ULongLongMult(v18, v21, &Size) >= 0 )
        {
          v23 = v22 & ~v20;
          if ( (int)ULongLongMult(v23, *((_QWORD *)this + 1), &dwBytes) >= 0 )
          {
            v24 = (void *)*((_QWORD *)this + 5);
            v25 = dwBytes;
            v26 = *(HANDLE *)this;
            if ( v24 )
            {
              v28 = HeapReAlloc(v26, 0, v24, dwBytes);
            }
            else
            {
              v27 = HeapAlloc(v26, 0, dwBytes);
              v28 = v27;
              if ( v27 )
                memset_0(v27, 0, v25);
            }
            if ( v28 )
            {
              *((_QWORD *)this + 5) = v28;
              *((_QWORD *)this + 3) = v23;
              goto LABEL_19;
            }
            return 14;
          }
        }
      }
      return 534;
    }
    if ( v17 >= v18 )
    {
      v33 = v17 + 1;
      if ( v33 <= v18 )
        return 160;
      v34 = *((_QWORD *)this + 4) - 1LL;
      if ( v34 + v33 < v33 )
        return 534;
      v35 = *((_QWORD *)this + 1);
      dwBytes = 0;
      if ( (int)ULongLongMult(v18, v35, &v48) < 0 )
        return 534;
      v37 = v36 & ~v34;
      if ( (int)ULongLongMult(v37, *((_QWORD *)this + 1), &dwBytes) < 0 )
        return 534;
      v38 = (void *)*((_QWORD *)this + 5);
      v39 = dwBytes;
      v40 = *(HANDLE *)this;
      if ( v38 )
      {
        v42 = HeapReAlloc(v40, 0, v38, dwBytes);
      }
      else
      {
        v41 = HeapAlloc(v40, 0, dwBytes);
        v42 = v41;
        if ( v41 )
          memset_0(v41, 0, v39);
      }
      if ( !v42 )
        return 14;
      *((_QWORD *)this + 5) = v42;
      *((_QWORD *)this + 3) = v37;
    }
    v43 = *((_QWORD *)this + 1);
    dwBytes = 0;
    if ( (int)ULongLongMult(v43, v15, &dwBytes) >= 0 )
    {
      v45 = (wchar_t **)(*((_QWORD *)this + 5) + dwBytes);
      if ( (unsigned __int64)v45 >= *((_QWORD *)this + 5) )
      {
        v46 = *((_QWORD *)this + 1);
        dwBytes = v44;
        if ( (int)ULongLongMult(v46, v15 + 1, &dwBytes) >= 0
          && *((_QWORD *)this + 5) + dwBytes >= *((_QWORD *)this + 5)
          && (int)ULongLongMult(*((_QWORD *)this + 2) - v15, *((_QWORD *)this + 1), &Size) >= 0 )
        {
          memmove_0(v47, v45, Size);
          *v45 = v14;
          ++*v16;
          return 0;
        }
      }
    }
    return 534;
  }
  return 3221225495LL;
}

```

## disassembly

```asm
0x18000aa1c  mov     [rsp-38h+arg_10], rbx
0x18000aa21  mov     [rsp-38h+dwBytes], rdx
0x18000aa26  push    rbp
0x18000aa27  push    rsi
0x18000aa28  push    rdi
0x18000aa29  push    r12
0x18000aa2b  push    r13
0x18000aa2d  push    r14
0x18000aa2f  push    r15
0x18000aa31  mov     rbp, rsp
0x18000aa34  sub     rsp, 30h
0x18000aa38  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000aa3c  mov     rbx, rcx
0x18000aa3f  mov     rcx, rax
0x18000aa42  xor     edx, edx; dwFlags
0x18000aa44  mov     r14, r9
0x18000aa47  mov     r15, r8
0x18000aa4a  inc     rcx
0x18000aa4d  cmp     [r8+rcx*2], dx
0x18000aa52  jnz     short loc_18000AA4A
0x18000aa54  lea     rsi, [rcx+1]
0x18000aa58  inc     rax
0x18000aa5b  cmp     [r9+rax*2], dx
0x18000aa60  jnz     short loc_18000AA58
0x18000aa62  mov     rcx, [rbx]; hHeap
0x18000aa65  lea     r12, [rax+1]
0x18000aa69  lea     rdi, [r12+rsi]
0x18000aa6d  add     rdi, rdi
0x18000aa70  mov     r8, rdi; dwBytes
0x18000aa73  call    cs:__imp_HeapAlloc
0x18000aa79  mov     r13, rax
0x18000aa7c  test    rax, rax
0x18000aa7f  jz      loc_18000AD1B
0x18000aa85  mov     r8, rdi; Size
0x18000aa88  xor     edx, edx; Val
0x18000aa8a  mov     rcx, rax; void *
0x18000aa8d  call    memset_0
0x18000aa92  mov     r8, r15; Source
0x18000aa95  mov     rdx, rsi; SizeInWords
0x18000aa98  mov     rcx, r13; Destination
0x18000aa9b  call    cs:__imp_wcscpy_s
0x18000aaa1  lea     rcx, ds:0[rsi*2]
0x18000aaa9  mov     r8, r14; Source
0x18000aaac  add     rcx, r13; Destination
0x18000aaaf  mov     rdx, r12; SizeInWords
0x18000aab2  call    cs:__imp_wcscpy_s
0x18000aab8  mov     r15, [rbp+arg_20]
0x18000aabc  lea     r12, [rbx+10h]
0x18000aac0  mov     rsi, [r12]
0x18000aac4  xor     r10d, r10d
0x18000aac7  mov     rcx, [rbx+18h]; unsigned __int64
0x18000aacb  mov     [rbp+Size], r10
0x18000aacf  cmp     r15, rsi
0x18000aad2  jb      loc_18000ABDD
0x18000aad8  cmp     rsi, rcx
0x18000aadb  jb      loc_18000AB97
0x18000aae1  lea     rdx, [rsi+1]
0x18000aae5  cmp     rdx, rcx
0x18000aae8  ja      short loc_18000AAF4
0x18000aaea  mov     eax, 0A0h
0x18000aaef  jmp     loc_18000AD20
0x18000aaf4  mov     rdi, [rbx+20h]
0x18000aaf8  dec     rdi
0x18000aafb  lea     r9, [rdi+rdx]
0x18000aaff  cmp     r9, rdx
0x18000ab02  jb      loc_18000AD14
0x18000ab08  mov     rdx, [rbx+8]; unsigned __int64
0x18000ab0c  lea     r8, [rbp+Size]; unsigned __int64 *
0x18000ab10  mov     [rbp+dwBytes], r10
0x18000ab14  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000ab19  test    eax, eax
0x18000ab1b  js      loc_18000AD14
0x18000ab21  mov     rdx, [rbx+8]; unsigned __int64
0x18000ab25  lea     r8, [rbp+dwBytes]; unsigned __int64 *
0x18000ab29  not     rdi
0x18000ab2c  and     rdi, r9
0x18000ab2f  mov     rcx, rdi; unsigned __int64
0x18000ab32  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000ab37  test    eax, eax
0x18000ab39  js      loc_18000AD14
0x18000ab3f  mov     r8, [rbx+28h]; lpMem
0x18000ab43  xor     edx, edx; dwFlags
0x18000ab45  mov     r15, [rbp+dwBytes]
0x18000ab49  mov     rcx, [rbx]; hHeap
0x18000ab4c  test    r8, r8
0x18000ab4f  jnz     short loc_18000AB71
0x18000ab51  mov     r8, r15; dwBytes
0x18000ab54  call    cs:__imp_HeapAlloc
0x18000ab5a  mov     r14, rax
0x18000ab5d  test    rax, rax
0x18000ab60  jz      short loc_18000AB7D
0x18000ab62  mov     r8, r15; Size
0x18000ab65  xor     edx, edx; Val
0x18000ab67  mov     rcx, rax; void *
0x18000ab6a  call    memset_0
0x18000ab6f  jmp     short loc_18000AB7D
0x18000ab71  mov     r9, r15; dwBytes
0x18000ab74  call    cs:__imp_HeapReAlloc
0x18000ab7a  mov     r14, rax
0x18000ab7d  xor     r10d, r10d
0x18000ab80  test    r14, r14
0x18000ab83  jz      loc_18000AC83
0x18000ab89  mov     [rbx+28h], r14
0x18000ab8d  lea     r9, [rbx+10h]
0x18000ab91  mov     [rbx+18h], rdi
0x18000ab95  jmp     short loc_18000AB9A
0x18000ab97  mov     r9, r12
0x18000ab9a  mov     rcx, [rbx+8]; unsigned __int64
0x18000ab9e  lea     r8, [rbp+dwBytes]; unsigned __int64 *
0x18000aba2  mov     rdx, rsi; unsigned __int64
0x18000aba5  mov     [rbp+dwBytes], r10
0x18000aba9  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000abae  test    eax, eax
0x18000abb0  js      loc_18000AD14
0x18000abb6  mov     rdx, [rbp+dwBytes]
0x18000abba  add     rdx, [rbx+28h]
0x18000abbe  cmp     rdx, [rbx+28h]
0x18000abc2  jb      loc_18000AD14
0x18000abc8  mov     [rdx], r13
0x18000abcb  mov     rax, [r9]
0x18000abce  inc     rax
0x18000abd1  mov     [r12], rax
0x18000abd5  mov     eax, r10d
0x18000abd8  jmp     loc_18000AD20
0x18000abdd  cmp     rsi, rcx
0x18000abe0  jb      loc_18000AC95
0x18000abe6  inc     rsi
0x18000abe9  cmp     rsi, rcx
0x18000abec  jbe     loc_18000AAEA
0x18000abf2  mov     rdi, [rbx+20h]
0x18000abf6  dec     rdi
0x18000abf9  lea     r9, [rdi+rsi]
0x18000abfd  cmp     r9, rsi
0x18000ac00  jb      loc_18000AD14
0x18000ac06  mov     rdx, [rbx+8]; unsigned __int64
0x18000ac0a  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18000ac0e  mov     [rbp+dwBytes], r10
0x18000ac12  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000ac17  test    eax, eax
0x18000ac19  js      loc_18000AD14
0x18000ac1f  mov     rdx, [rbx+8]; unsigned __int64
0x18000ac23  lea     r8, [rbp+dwBytes]; unsigned __int64 *
0x18000ac27  not     rdi
0x18000ac2a  and     rdi, r9
0x18000ac2d  mov     rcx, rdi; unsigned __int64
0x18000ac30  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000ac35  test    eax, eax
0x18000ac37  js      loc_18000AD14
0x18000ac3d  mov     r8, [rbx+28h]; lpMem
0x18000ac41  xor     edx, edx; dwFlags
0x18000ac43  mov     r14, [rbp+dwBytes]
0x18000ac47  mov     rcx, [rbx]; hHeap
0x18000ac4a  test    r8, r8
0x18000ac4d  jnz     short loc_18000AC6F
0x18000ac4f  mov     r8, r14; dwBytes
0x18000ac52  call    cs:__imp_HeapAlloc
0x18000ac58  mov     rsi, rax
0x18000ac5b  test    rax, rax
0x18000ac5e  jz      short loc_18000AC7B
0x18000ac60  mov     r8, r14; Size
0x18000ac63  xor     edx, edx; Val
0x18000ac65  mov     rcx, rax; void *
0x18000ac68  call    memset_0
0x18000ac6d  jmp     short loc_18000AC7B
0x18000ac6f  mov     r9, r14; dwBytes
0x18000ac72  call    cs:__imp_HeapReAlloc
0x18000ac78  mov     rsi, rax
0x18000ac7b  xor     r10d, r10d
0x18000ac7e  test    rsi, rsi
0x18000ac81  jnz     short loc_18000AC8D
0x18000ac83  mov     eax, 0Eh
0x18000ac88  jmp     loc_18000AD20
0x18000ac8d  mov     [rbx+28h], rsi
0x18000ac91  mov     [rbx+18h], rdi
0x18000ac95  mov     rcx, [rbx+8]; unsigned __int64
0x18000ac99  lea     r8, [rbp+dwBytes]; unsigned __int64 *
0x18000ac9d  mov     rdx, r15; unsigned __int64
0x18000aca0  mov     [rbp+dwBytes], r10
0x18000aca4  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000aca9  test    eax, eax
0x18000acab  js      short loc_18000AD14
0x18000acad  mov     rdi, [rbp+dwBytes]
0x18000acb1  add     rdi, [rbx+28h]
0x18000acb5  cmp     rdi, [rbx+28h]
0x18000acb9  jb      short loc_18000AD14
0x18000acbb  mov     rcx, [rbx+8]; unsigned __int64
0x18000acbf  lea     rdx, [r15+1]; unsigned __int64
0x18000acc3  lea     r8, [rbp+dwBytes]; unsigned __int64 *
0x18000acc7  mov     [rbp+dwBytes], r10
0x18000accb  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000acd0  test    eax, eax
0x18000acd2  js      short loc_18000AD14
0x18000acd4  mov     r9, [rbp+dwBytes]
0x18000acd8  add     r9, [rbx+28h]
0x18000acdc  cmp     r9, [rbx+28h]
0x18000ace0  jb      short loc_18000AD14
0x18000ace2  mov     rcx, [rbx+10h]
0x18000ace6  lea     r8, [rbp+Size]; unsigned __int64 *
0x18000acea  mov     rdx, [rbx+8]; unsigned __int64
0x18000acee  sub     rcx, r15; unsigned __int64
0x18000acf1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000acf6  test    eax, eax
0x18000acf8  js      short loc_18000AD14
0x18000acfa  mov     r8, [rbp+Size]; Size
0x18000acfe  mov     rdx, rdi; Src
0x18000ad01  mov     rcx, r9; void *
0x18000ad04  call    memmove_0
0x18000ad09  mov     [rdi], r13
0x18000ad0c  inc     qword ptr [r12]
0x18000ad10  xor     eax, eax
0x18000ad12  jmp     short loc_18000AD20
0x18000ad14  mov     eax, 216h
0x18000ad19  jmp     short loc_18000AD20
0x18000ad1b  mov     eax, 0C0000017h
0x18000ad20  mov     rbx, [rsp+30h+arg_10]
0x18000ad28  add     rsp, 30h
0x18000ad2c  pop     r15
0x18000ad2e  pop     r14
0x18000ad30  pop     r13
0x18000ad32  pop     r12
0x18000ad34  pop     rdi
0x18000ad35  pop     rsi
0x18000ad36  pop     rbp
0x18000ad37  retn
```
