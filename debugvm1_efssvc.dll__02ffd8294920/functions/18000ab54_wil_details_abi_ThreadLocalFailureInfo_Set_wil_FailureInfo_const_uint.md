# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000ab54`
- end: `0x18000ad70`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800096c0`

## callees

- `0x18000a4fc`
- `0x18000ab54`
- `0x18000c392`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000aca0`
- `msvcrt!memcpy_s` at `0x18000acf1`
- `msvcrt!memcpy_s` at `0x18000ad3c`
- `msvcrt!memcpy_s` at `0x18000aca0`
- `msvcrt!memcpy_s` at `0x18000acf1`
- `msvcrt!memcpy_s` at `0x18000ad3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac3c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v3; // rbp
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  rsize_t *v16; // rsi
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char *v22; // rsi
  _BYTE *v23; // r8
  __int64 v24; // rax
  __int64 v25; // r14
  _BYTE *v26; // r8
  __int64 v27; // rax
  __int64 v28; // r14
  _WORD *v29; // r8
  unsigned __int64 v30; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = -1;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  v7 = 1;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v6 + v9) );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v10 = *((_QWORD *)a2 + 16);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v10 + v11) );
    v7 = v11 + 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v8 + v7 + v13;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v8 + v7 + v13);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = &v20[*v16];
    if ( v20 != v22 && (v23 = (_BYTE *)*((_QWORD *)a2 + 7)) != 0 && *v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v25 = v24 + 1;
      if ( v21 < v24 + 1 )
      {
        *((_QWORD *)this + 2) = 0;
LABEL_30:
        v26 = (_BYTE *)*((_QWORD *)a2 + 16);
        if ( v26 && *v26 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v26[v27] );
          v28 = v27 + 1;
          if ( v22 - v20 < (unsigned __int64)(v27 + 1) )
          {
            *((_QWORD *)this + 4) = 0;
LABEL_39:
            v29 = (_WORD *)*((_QWORD *)a2 + 3);
            if ( v29 && *v29 )
            {
              do
                ++v3;
              while ( v29[v3] );
              v30 = 2 * v3 + 2;
              if ( v22 - v20 >= v30 )
              {
                memcpy_s(v20, v22 - v20, v29, 2 * v3 + 2);
                *((_QWORD *)this + 7) = v20;
                v20 += v30;
LABEL_45:
                memset_0(v20, 0, v22 - v20);
                return;
              }
            }
LABEL_44:
            *((_QWORD *)this + 7) = 0;
            goto LABEL_45;
          }
          memcpy_s(v20, v22 - v20, v26, v27 + 1);
          *((_QWORD *)this + 4) = v20;
          v20 += v28;
LABEL_38:
          if ( v20 == v22 )
            goto LABEL_44;
          goto LABEL_39;
        }
LABEL_37:
        *((_QWORD *)this + 4) = 0;
        goto LABEL_38;
      }
      memcpy_s(*((void *const *)this + 8), v21, v23, v24 + 1);
      *((_QWORD *)this + 2) = v20;
      v20 += v25;
    }
    else
    {
      *((_QWORD *)this + 2) = 0;
    }
    if ( v20 == v22 )
      goto LABEL_37;
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x18000ab54  push    rbx
0x18000ab56  push    rbp
0x18000ab57  push    rsi
0x18000ab58  push    rdi
0x18000ab59  push    r12
0x18000ab5b  push    r13
0x18000ab5d  push    r14
0x18000ab5f  push    r15
0x18000ab61  sub     rsp, 28h
0x18000ab65  mov     [rcx+4], r8d
0x18000ab69  xor     r13d, r13d
0x18000ab6c  mov     eax, [rdx+8]
0x18000ab6f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000ab73  mov     [rcx+8], eax
0x18000ab76  mov     rdi, rcx
0x18000ab79  mov     [rcx+10h], r13
0x18000ab7d  mov     r12, rdx
0x18000ab80  movzx   eax, word ptr [rdx+40h]
0x18000ab84  mov     [rcx+18h], ax
0x18000ab88  mov     al, [rdx]
0x18000ab8a  mov     [rcx+1Ah], al
0x18000ab8d  mov     [rcx+20h], r13
0x18000ab91  mov     rax, [rdx+88h]
0x18000ab98  mov     [rcx+28h], rax
0x18000ab9c  mov     rax, [rdx+90h]
0x18000aba3  mov     [rcx+30h], rax
0x18000aba7  mov     [rcx+38h], r13
0x18000abab  mov     rcx, [rdx+38h]
0x18000abaf  lea     edx, [rbp+2]
0x18000abb2  test    rcx, rcx
0x18000abb5  jnz     short loc_18000ABBC
0x18000abb7  mov     r8d, edx
0x18000abba  jmp     short loc_18000ABCC
0x18000abbc  mov     rax, rbp
0x18000abbf  inc     rax
0x18000abc2  cmp     [rcx+rax], r13b
0x18000abc6  jnz     short loc_18000ABBF
0x18000abc8  lea     r8, [rax+1]; unsigned __int64
0x18000abcc  mov     rcx, [r12+80h]
0x18000abd4  test    rcx, rcx
0x18000abd7  jz      short loc_18000ABE9
0x18000abd9  mov     rax, rbp
0x18000abdc  inc     rax
0x18000abdf  cmp     [rcx+rax], r13b
0x18000abe3  jnz     short loc_18000ABDC
0x18000abe5  lea     rdx, [rax+1]
0x18000abe9  mov     rcx, [r12+18h]
0x18000abee  test    rcx, rcx
0x18000abf1  jnz     short loc_18000ABF8
0x18000abf3  lea     eax, [rcx+2]
0x18000abf6  jmp     short loc_18000AC0D
0x18000abf8  mov     rax, rbp
0x18000abfb  inc     rax
0x18000abfe  cmp     [rcx+rax*2], r13w
0x18000ac03  jnz     short loc_18000ABFB
0x18000ac05  lea     rax, ds:2[rax*2]
0x18000ac0d  lea     r14, [rdx+rax]
0x18000ac11  add     r14, r8
0x18000ac14  lea     rsi, [rdi+48h]
0x18000ac18  cmp     [rdi+40h], r13
0x18000ac1c  jz      short loc_18000AC23
0x18000ac1e  cmp     [rsi], r14
0x18000ac21  jnb     short loc_18000AC57
0x18000ac23  mov     rdx, r14; dwBytes
0x18000ac26  mov     ecx, 8; dwFlags
0x18000ac2b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ac30  mov     r15, rax
0x18000ac33  test    rax, rax
0x18000ac36  jz      short loc_18000AC57
0x18000ac38  mov     rbx, [rdi+40h]
0x18000ac3c  call    cs:__imp_GetProcessHeap
0x18000ac42  mov     r8, rbx; lpMem
0x18000ac45  xor     edx, edx; dwFlags
0x18000ac47  mov     rcx, rax; hHeap
0x18000ac4a  call    cs:__imp_HeapFree
0x18000ac50  mov     [rdi+40h], r15
0x18000ac54  mov     [rsi], r14
0x18000ac57  mov     rbx, [rdi+40h]
0x18000ac5b  test    rbx, rbx
0x18000ac5e  jz      loc_18000AD5F
0x18000ac64  mov     rdx, [rsi]; DestinationSize
0x18000ac67  lea     rsi, [rdx+rbx]
0x18000ac6b  cmp     rbx, rsi
0x18000ac6e  jz      short loc_18000ACAF
0x18000ac70  mov     r8, [r12+38h]; Source
0x18000ac75  test    r8, r8
0x18000ac78  jz      short loc_18000ACAF
0x18000ac7a  cmp     [r8], r13b
0x18000ac7d  jz      short loc_18000ACAF
0x18000ac7f  mov     rax, rbp
0x18000ac82  inc     rax
0x18000ac85  cmp     [r8+rax], r13b
0x18000ac89  jnz     short loc_18000AC82
0x18000ac8b  lea     r14, [rax+1]
0x18000ac8f  cmp     rdx, r14
0x18000ac92  jnb     short loc_18000AC9A
0x18000ac94  mov     [rdi+10h], r13
0x18000ac98  jmp     short loc_18000ACB8
0x18000ac9a  mov     r9, r14; SourceSize
0x18000ac9d  mov     rcx, rbx; Destination
0x18000aca0  call    cs:__imp_memcpy_s
0x18000aca6  mov     [rdi+10h], rbx
0x18000acaa  add     rbx, r14
0x18000acad  jmp     short loc_18000ACB3
0x18000acaf  mov     [rdi+10h], r13
0x18000acb3  cmp     rbx, rsi
0x18000acb6  jz      short loc_18000AD00
0x18000acb8  mov     r8, [r12+80h]; Source
0x18000acc0  test    r8, r8
0x18000acc3  jz      short loc_18000AD00
0x18000acc5  cmp     [r8], r13b
0x18000acc8  jz      short loc_18000AD00
0x18000acca  mov     rax, rbp
0x18000accd  inc     rax
0x18000acd0  cmp     [r8+rax], r13b
0x18000acd4  jnz     short loc_18000ACCD
0x18000acd6  mov     rdx, rsi
0x18000acd9  lea     r14, [rax+1]
0x18000acdd  sub     rdx, rbx; DestinationSize
0x18000ace0  cmp     rdx, r14
0x18000ace3  jnb     short loc_18000ACEB
0x18000ace5  mov     [rdi+20h], r13
0x18000ace9  jmp     short loc_18000AD09
0x18000aceb  mov     r9, r14; SourceSize
0x18000acee  mov     rcx, rbx; Destination
0x18000acf1  call    cs:__imp_memcpy_s
0x18000acf7  mov     [rdi+20h], rbx
0x18000acfb  add     rbx, r14
0x18000acfe  jmp     short loc_18000AD04
0x18000ad00  mov     [rdi+20h], r13
0x18000ad04  cmp     rbx, rsi
0x18000ad07  jz      short loc_18000AD4B
0x18000ad09  mov     r8, [r12+18h]; Source
0x18000ad0e  test    r8, r8
0x18000ad11  jz      short loc_18000AD4B
0x18000ad13  cmp     [r8], r13w
0x18000ad17  jz      short loc_18000AD4B
0x18000ad19  inc     rbp
0x18000ad1c  cmp     [r8+rbp*2], r13w
0x18000ad21  jnz     short loc_18000AD19
0x18000ad23  mov     rdx, rsi
0x18000ad26  lea     r14, ds:2[rbp*2]
0x18000ad2e  sub     rdx, rbx; DestinationSize
0x18000ad31  cmp     rdx, r14
0x18000ad34  jb      short loc_18000AD4B
0x18000ad36  mov     r9, r14; SourceSize
0x18000ad39  mov     rcx, rbx; Destination
0x18000ad3c  call    cs:__imp_memcpy_s
0x18000ad42  mov     [rdi+38h], rbx
0x18000ad46  add     rbx, r14
0x18000ad49  jmp     short loc_18000AD4F
0x18000ad4b  mov     [rdi+38h], r13
0x18000ad4f  sub     rsi, rbx
0x18000ad52  xor     edx, edx; Val
0x18000ad54  mov     r8, rsi; Size
0x18000ad57  mov     rcx, rbx; void *
0x18000ad5a  call    memset_0
0x18000ad5f  add     rsp, 28h
0x18000ad63  pop     r15
0x18000ad65  pop     r14
0x18000ad67  pop     r13
0x18000ad69  pop     r12
0x18000ad6b  pop     rdi
0x18000ad6c  pop     rsi
0x18000ad6d  pop     rbp
0x18000ad6e  pop     rbx
0x18000ad6f  retn
```
