# PerflibciOpenLocalQueryHandle

- ea: `0x1800166cc`
- end: `0x180016815`
- name: `PerflibciOpenLocalQueryHandle`
- size: `329`
- prototype: `__int64 __fastcall(unsigned __int16 *, char, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015250`
- `0x180018b90`

## callees

- `0x180005da0`
- `0x180008050`
- `0x18000dca0`
- `0x18000fea0`
- `0x1800166cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800167c8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800167c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167d6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180016786`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180016786`

## pseudocode

```c
__int64 __fastcall PerflibciOpenLocalQueryHandle(unsigned __int16 *a1, char a2, _QWORD *a3)
{
  _QWORD *v5; // rbx
  DWORD LastError; // edi
  __int64 v7; // rdi
  char v8; // bp
  int v9; // eax
  __int64 v10; // rax
  WCHAR *v11; // rcx
  __int64 v12; // rdx
  HANDLE MutexW; // rax
  DWORD nSize; // [rsp+58h] [rbp+10h] BYREF

  LOBYTE(nSize) = a2;
  if ( a3 )
  {
    v7 = -1;
    *a3 = 0;
    v8 = 1;
    if ( a1 && *a1 )
    {
      v10 = -1;
      do
        ++v10;
      while ( a1[v10] );
      v9 = v10 + 1;
      v8 = 0;
    }
    else
    {
      v9 = 261;
    }
    v5 = (_QWORD *)operator new(2 * ((v9 + 7) & 0xFFFFFFF8) + 96);
    if ( !v5 )
      goto LABEL_20;
    *((_DWORD *)v5 + 9) = PerflibciValidateCode();
    v11 = (WCHAR *)(v5 + 12);
    v5[1] = v5 + 12;
    v5[2] = 0;
    if ( v8 )
    {
      nSize = 260;
      GetComputerNameW(v11, &nSize);
    }
    else
    {
      v12 = -1;
      do
        ++v12;
      while ( a1[v12] );
      StringCchCopyW(v11, v12 + 1, a1);
    }
    do
      ++v7;
    while ( *(_WORD *)(v5[1] + 2 * v7) );
    *((_DWORD *)v5 + 23) = ((2 * v7 + 9) & 0xFFFFFFF8) + 16;
    if ( ((2 * (_DWORD)v7 + 9) & 0xFFFFFFF8) >= 0xFFFFFFF0 )
    {
      LastError = 534;
      operator delete(v5);
      v5 = 0;
      goto LABEL_21;
    }
    MutexW = CreateMutexW(0, 0, 0);
    *v5 = MutexW;
    if ( MutexW )
    {
      LastError = 0;
      *a3 = v5;
      return LastError;
    }
    LastError = GetLastError();
    operator delete(v5);
    v5 = 0;
    if ( !LastError )
LABEL_20:
      LastError = 14;
  }
  else
  {
    v5 = 0;
    LastError = 87;
  }
LABEL_21:
  operator delete(v5);
  return LastError;
}

```

## disassembly

```asm
0x1800166cc  mov     [rsp+arg_0], rbx
0x1800166d1  mov     byte ptr [rsp+nSize], dl
0x1800166d5  push    rbp
0x1800166d6  push    rsi
0x1800166d7  push    rdi
0x1800166d8  push    r14
0x1800166da  push    r15
0x1800166dc  sub     rsp, 20h
0x1800166e0  xor     r15d, r15d
0x1800166e3  mov     r14, r8
0x1800166e6  mov     rsi, rcx
0x1800166e9  test    r8, r8
0x1800166ec  jnz     short loc_1800166FA
0x1800166ee  mov     ebx, r15d
0x1800166f1  lea     edi, [r8+57h]
0x1800166f5  jmp     loc_1800167F2
0x1800166fa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800166fe  mov     [r8], r15
0x180016701  mov     bpl, 1
0x180016704  test    rsi, rsi
0x180016707  jz      short loc_18001670F
0x180016709  cmp     [rcx], r15w
0x18001670d  jnz     short loc_180016716
0x18001670f  mov     eax, 105h
0x180016714  jmp     short loc_180016728
0x180016716  mov     rax, rdi
0x180016719  inc     rax
0x18001671c  cmp     [rcx+rax*2], r15w
0x180016721  jnz     short loc_180016719
0x180016723  inc     eax
0x180016725  mov     bpl, r15b
0x180016728  add     eax, 7
0x18001672b  and     eax, 0FFFFFFF8h
0x18001672e  lea     ecx, ds:60h[rax*2]
0x180016735  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18001673a  mov     rbx, rax
0x18001673d  test    rax, rax
0x180016740  jz      loc_1800167ED
0x180016746  call    ?PerflibciValidateCode@@YAKXZ; PerflibciValidateCode(void)
0x18001674b  mov     [rbx+24h], eax
0x18001674e  lea     rcx, [rbx+60h]; unsigned __int16 *
0x180016752  mov     [rbx+8], rcx
0x180016756  mov     [rbx+10h], r15
0x18001675a  test    bpl, bpl
0x18001675d  jnz     short loc_180016779
0x18001675f  mov     rdx, rdi
0x180016762  inc     rdx
0x180016765  cmp     [rsi+rdx*2], r15w
0x18001676a  jnz     short loc_180016762
0x18001676c  inc     rdx; unsigned __int64
0x18001676f  mov     r8, rsi; unsigned __int16 *
0x180016772  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016777  jmp     short loc_18001678C
0x180016779  lea     rdx, [rsp+48h+nSize]; nSize
0x18001677e  mov     [rsp+48h+nSize], 104h
0x180016786  call    cs:__imp_GetComputerNameW
0x18001678c  mov     rax, [rbx+8]
0x180016790  inc     rdi
0x180016793  cmp     [rax+rdi*2], r15w
0x180016798  jnz     short loc_180016790
0x18001679a  lea     eax, ds:9[rdi*2]
0x1800167a1  and     eax, 0FFFFFFF8h
0x1800167a4  add     eax, 10h
0x1800167a7  mov     [rbx+5Ch], eax
0x1800167aa  cmp     eax, 10h
0x1800167ad  jnb     short loc_1800167C1
0x1800167af  mov     rcx, rbx; Block
0x1800167b2  mov     edi, 216h
0x1800167b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800167bc  mov     rbx, r15
0x1800167bf  jmp     short loc_1800167F2
0x1800167c1  xor     r8d, r8d; lpName
0x1800167c4  xor     edx, edx; bInitialOwner
0x1800167c6  xor     ecx, ecx; lpMutexAttributes
0x1800167c8  call    cs:__imp_CreateMutexW
0x1800167ce  mov     [rbx], rax
0x1800167d1  test    rax, rax
0x1800167d4  jnz     short loc_18001680D
0x1800167d6  call    cs:__imp_GetLastError
0x1800167dc  mov     rcx, rbx; Block
0x1800167df  mov     edi, eax
0x1800167e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800167e6  mov     rbx, r15
0x1800167e9  test    edi, edi
0x1800167eb  jnz     short loc_1800167F2
0x1800167ed  mov     edi, 0Eh
0x1800167f2  mov     rcx, rbx; Block
0x1800167f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800167fa  mov     rbx, [rsp+48h+arg_0]
0x1800167ff  mov     eax, edi
0x180016801  add     rsp, 20h
0x180016805  pop     r15
0x180016807  pop     r14
0x180016809  pop     rdi
0x18001680a  pop     rsi
0x18001680b  pop     rbp
0x18001680c  retn
0x18001680d  mov     edi, r15d
0x180016810  mov     [r14], rbx
0x180016813  jmp     short loc_1800167FA
```
