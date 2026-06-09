# _SerialChainCheckTimeValidity

- ea: `0x18009bb0c`
- end: `0x18009bbfa`
- name: `_SerialChainCheckTimeValidity`
- size: `238`
- prototype: `__int64 __fastcall(FILETIME *lpFileTime2, FILETIME *lpFileTime1, FILETIME *, FILETIME *, FILETIME *, FILETIME *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800178dc`

## callees

- `0x18009bb0c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18009bb3a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18009bb4a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18009bb84`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18009bb9d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18009bbb6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18009bbda`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18011c9c0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18011c9d2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18011c9e4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18009bb3a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18009bb4a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18009bb84`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18009bb9d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18009bbb6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18009bbda`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18011c9c0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18011c9d2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18011c9e4`

## pseudocode

```c
__int64 __fastcall SerialChainCheckTimeValidity(
        FILETIME *lpFileTime2,
        FILETIME *lpFileTime1,
        FILETIME *a3,
        FILETIME *a4,
        FILETIME *lpFileTime2a,
        FILETIME *lpFileTime1a,
        int a7)
{
  const FILETIME *v7; // rsi
  const FILETIME *v13; // rbx
  LONG v14; // eax
  const FILETIME *v15; // rsi
  bool v16; // cf
  LONG v17; // eax
  unsigned int v18; // ecx
  FILETIME FileTime2; // [rsp+58h] [rbp+20h] BYREF

  v7 = a4;
  if ( !a4 )
    v7 = a3;
  if ( CompareFileTime(v7, lpFileTime2) >= 0 && CompareFileTime(v7, lpFileTime1) <= 0 )
    return 0;
  if ( a4 )
  {
    if ( CompareFileTime(a3, a4) < 0 )
      return 0xFFFFFFFFLL;
    FileTime2 = (FILETIME)(*(_QWORD *)a3 - 1200000000LL);
    if ( CompareFileTime(a4, &FileTime2) < 0 )
      return 0xFFFFFFFFLL;
  }
  v13 = lpFileTime2a;
  if ( !lpFileTime2a->dwLowDateTime && !lpFileTime2a->dwHighDateTime )
  {
    v16 = a7 != 0;
    a7 = -a7;
    return v16 ? 2 : -1;
  }
  v14 = CompareFileTime(a3, lpFileTime2a);
  v15 = lpFileTime1a;
  if ( v14 >= 0 && CompareFileTime(a3, lpFileTime1a) <= 0 )
    return 0xFFFFFFFFLL;
  if ( CompareFileTime(v13, lpFileTime2) <= 0 )
    v13 = lpFileTime2;
  if ( CompareFileTime(v15, lpFileTime1) >= 0 )
    v15 = lpFileTime1;
  v17 = CompareFileTime(v15, v13);
  v18 = -1;
  if ( v17 >= 0 )
    return 1;
  return v18;
}

```

## disassembly

```asm
0x18009bb0c  mov     [rsp+arg_0], rbx
0x18009bb11  mov     [rsp+arg_8], rbp
0x18009bb16  push    rsi
0x18009bb17  push    rdi
0x18009bb18  push    r14
0x18009bb1a  sub     rsp, 20h
0x18009bb1e  test    r9, r9
0x18009bb21  mov     rsi, r9
0x18009bb24  mov     rbp, rdx
0x18009bb27  mov     r14, rcx
0x18009bb2a  cmovz   rsi, r8
0x18009bb2e  mov     rdx, rcx; lpFileTime2
0x18009bb31  mov     rcx, rsi; lpFileTime1
0x18009bb34  mov     rbx, r9
0x18009bb37  mov     rdi, r8
0x18009bb3a  call    cs:__imp_CompareFileTime
0x18009bb40  test    eax, eax
0x18009bb42  js      short loc_18009BB69
0x18009bb44  mov     rdx, rbp; lpFileTime2
0x18009bb47  mov     rcx, rsi; lpFileTime1
0x18009bb4a  call    cs:__imp_CompareFileTime
0x18009bb50  test    eax, eax
0x18009bb52  jg      short loc_18009BB69
0x18009bb54  xor     eax, eax
0x18009bb56  mov     rbx, [rsp+38h+arg_0]
0x18009bb5b  mov     rbp, [rsp+38h+arg_8]
0x18009bb60  add     rsp, 20h
0x18009bb64  pop     r14
0x18009bb66  pop     rdi
0x18009bb67  pop     rsi
0x18009bb68  retn
0x18009bb69  test    rbx, rbx
0x18009bb6c  jnz     short loc_18009BBB0
0x18009bb6e  mov     rbx, [rsp+38h+lpFileTime2]
0x18009bb73  cmp     dword ptr [rbx], 0
0x18009bb76  jnz     short loc_18009BB7E
0x18009bb78  cmp     dword ptr [rbx+4], 0
0x18009bb7c  jz      short loc_18009BBEA
0x18009bb7e  mov     rdx, rbx; lpFileTime2
0x18009bb81  mov     rcx, rdi; lpFileTime1
0x18009bb84  call    cs:__imp_CompareFileTime
0x18009bb8a  mov     rsi, [rsp+38h+lpFileTime1]
0x18009bb8f  test    eax, eax
0x18009bb91  js      loc_18011C9BA
0x18009bb97  mov     rdx, rsi; lpFileTime2
0x18009bb9a  mov     rcx, rdi; lpFileTime1
0x18009bb9d  call    cs:__imp_CompareFileTime
0x18009bba3  test    eax, eax
0x18009bba5  jle     loc_18011C9B2
0x18009bbab  jmp     loc_18011C9BA
0x18009bbb0  mov     rdx, rbx; lpFileTime2
0x18009bbb3  mov     rcx, rdi; lpFileTime1
0x18009bbb6  call    cs:__imp_CompareFileTime
0x18009bbbc  test    eax, eax
0x18009bbbe  js      loc_18011C9B2
0x18009bbc4  mov     rax, [rdi]
0x18009bbc7  lea     rdx, [rsp+38h+FileTime2]; lpFileTime2
0x18009bbcc  sub     rax, 47868C00h
0x18009bbd2  mov     rcx, rbx; lpFileTime1
0x18009bbd5  mov     qword ptr [rsp+38h+FileTime2.dwLowDateTime], rax
0x18009bbda  call    cs:__imp_CompareFileTime
0x18009bbe0  test    eax, eax
0x18009bbe2  js      loc_18011C9B2
0x18009bbe8  jmp     short loc_18009BB6E
0x18009bbea  neg     [rsp+38h+arg_30]
0x18009bbee  sbb     eax, eax
0x18009bbf0  and     eax, 3
0x18009bbf3  dec     eax
0x18009bbf5  jmp     loc_18009BB56
0x18011c9b2  or      eax, 0FFFFFFFFh
0x18011c9b5  jmp     loc_18009BB56
0x18011c9ba  mov     rdx, r14; lpFileTime2
0x18011c9bd  mov     rcx, rbx; lpFileTime1
0x18011c9c0  call    cs:__imp_CompareFileTime
0x18011c9c6  mov     rdx, rbp; lpFileTime2
0x18011c9c9  mov     rcx, rsi; lpFileTime1
0x18011c9cc  test    eax, eax
0x18011c9ce  cmovle  rbx, r14
0x18011c9d2  call    cs:__imp_CompareFileTime
0x18011c9d8  test    eax, eax
0x18011c9da  mov     rdx, rbx; lpFileTime2
0x18011c9dd  cmovns  rsi, rbp
0x18011c9e1  mov     rcx, rsi; lpFileTime1
0x18011c9e4  call    cs:__imp_CompareFileTime
0x18011c9ea  or      ecx, 0FFFFFFFFh
0x18011c9ed  test    eax, eax
0x18011c9ef  lea     edx, [rcx+2]
0x18011c9f2  cmovns  ecx, edx
0x18011c9f5  mov     eax, ecx
0x18011c9f7  jmp     loc_18009BB56
```
