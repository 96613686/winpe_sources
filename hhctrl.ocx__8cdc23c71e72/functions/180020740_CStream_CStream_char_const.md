# CStream::CStream(char const *)

- ea: `0x180020740`
- end: `0x180020911`
- name: `??0CStream@@QEAA@PEBD@Z`
- size: `465`
- prototype: `CStream *(CStream *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002c074`

## callees

- `0x180020740`
- `0x180042da8`

## import_xrefs

- `msvcrt!malloc` at `0x1800207f1`
- `msvcrt!malloc` at `0x180020800`
- `msvcrt!malloc` at `0x180020829`
- `msvcrt!malloc` at `0x1800207f1`
- `msvcrt!malloc` at `0x180020800`
- `msvcrt!malloc` at `0x180020829`
- `KERNEL32!ReleaseSemaphore` at `0x1800208bb`
- `KERNEL32!ReleaseSemaphore` at `0x1800208ce`
- `KERNEL32!ReleaseSemaphore` at `0x1800208bb`
- `KERNEL32!ReleaseSemaphore` at `0x1800208ce`
- `KERNEL32!_lclose` at `0x18002084f`
- `KERNEL32!_lclose` at `0x18002084f`
- `KERNEL32!CreateSemaphoreA` at `0x1800207c7`
- `KERNEL32!CreateSemaphoreA` at `0x1800207df`
- `KERNEL32!CreateSemaphoreA` at `0x1800207c7`
- `KERNEL32!CreateSemaphoreA` at `0x1800207df`
- `KERNEL32!_lread` at `0x18002083e`
- `KERNEL32!_lread` at `0x18002083e`
- `KERNEL32!CreateThread` at `0x180020890`
- `KERNEL32!CreateThread` at `0x180020890`
- `KERNEL32!_lopen` at `0x180020777`
- `KERNEL32!_lopen` at `0x180020777`

## pseudocode

```c
CStream *__fastcall CStream::CStream(CStream *this, const char *a2)
{
  HFILE v4; // edi
  int v5; // eax
  bool v6; // zf
  UINT v7; // esi
  void *v8; // rax
  signed int v9; // eax
  __int64 v10; // rdi
  HANDLE Thread; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx

  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 19) = 0;
  if ( !qword_18008C320 )
    qword_18008C320 = (__int64)this;
  v4 = _lopen(a2, 0);
  *((_DWORD *)this + 7) = v4;
  v5 = *((_DWORD *)this + 19);
  if ( v4 == -1 )
  {
    v6 = v5 == 0;
    goto LABEL_5;
  }
  if ( v5 )
  {
    v6 = hSemaphore == 0;
    v7 = 0x2000;
    *((_DWORD *)this + 14) = 0x2000;
    if ( v6 )
    {
      hSemaphore = CreateSemaphoreA(0, 1, 1, 0);
      hHandle = CreateSemaphoreA(0, 1, 1, 0);
      lpBuffer = malloc(0x2002u);
      v8 = malloc(0x2002u);
      v7 = *((_DWORD *)this + 14);
      v4 = *((_DWORD *)this + 7);
      Block = v8;
    }
    else
    {
      v8 = Block;
    }
  }
  else
  {
    v7 = 0x10000;
    *((_DWORD *)this + 14) = 0x10000;
    v8 = malloc(0x10002u);
  }
  *((_QWORD *)this + 5) = v8;
  *(_DWORD *)this = 1;
  v9 = _lread(v4, v8, v7);
  v10 = v9;
  if ( v9 == -1 )
  {
    _lclose(*((_DWORD *)this + 7));
    v6 = *((_DWORD *)this + 19) == 0;
LABEL_5:
    *(_DWORD *)this = 0;
    if ( !v6 )
      qword_18008C320 = 0;
    return this;
  }
  if ( *((_DWORD *)this + 19) )
  {
    v6 = dword_18008C21C == 0;
    *((_DWORD *)this + 15) = -2;
    if ( v6 )
    {
      Thread = CreateThread(0, 0, ReadAhead, 0, 0, (LPDWORD)this + 18);
      *((_QWORD *)this + 8) = Thread;
      if ( Thread )
        dword_18008C21C = 1;
      else
        *((_DWORD *)this + 19) = 0;
    }
    else
    {
      ReleaseSemaphore(hSemaphore, 1, 0);
      ReleaseSemaphore(hHandle, 1, 0);
    }
  }
  v12 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 1) = v12;
  v13 = v10 + v12;
  *((_QWORD *)this + 2) = v13;
  *(_BYTE *)(v13 + 1) = 0;
  *((_DWORD *)this + 8) = v10;
  *((_DWORD *)this + 9) = 0;
  *((_QWORD *)this + 6) = lcStrDup(a2);
  *(_DWORD *)this = 1;
  *((_DWORD *)this + 6) = 0;
  return this;
}

```

## disassembly

```asm
0x180020740  push    rbx
0x180020742  push    rbp
0x180020743  push    rsi
0x180020744  push    rdi
0x180020745  push    r14
0x180020747  push    r15
0x180020749  sub     rsp, 38h
0x18002074d  xor     r14d, r14d
0x180020750  mov     rbp, rdx
0x180020753  mov     [rcx+28h], r14
0x180020757  mov     rbx, rcx
0x18002075a  mov     [rcx+30h], r14
0x18002075e  mov     [rcx+4Ch], r14d
0x180020762  cmp     cs:qword_18008C320, r14
0x180020769  jnz     short loc_180020772
0x18002076b  mov     cs:qword_18008C320, rcx
0x180020772  xor     edx, edx; iReadWrite
0x180020774  mov     rcx, rbp; lpPathName
0x180020777  call    cs:__imp__lopen
0x18002077d  mov     edi, eax
0x18002077f  mov     [rbx+1Ch], eax
0x180020782  mov     eax, [rbx+4Ch]
0x180020785  cmp     edi, 0FFFFFFFFh
0x180020788  jnz     short loc_1800207A1
0x18002078a  test    eax, eax
0x18002078c  mov     [rbx], r14d
0x18002078f  jz      loc_180020901
0x180020795  mov     cs:qword_18008C320, r14
0x18002079c  jmp     loc_180020901
0x1800207a1  mov     r15d, 1
0x1800207a7  test    eax, eax
0x1800207a9  jz      short loc_18002081E
0x1800207ab  cmp     cs:hSemaphore, r14
0x1800207b2  mov     esi, 2000h
0x1800207b7  mov     [rbx+38h], esi
0x1800207ba  jnz     short loc_180020815
0x1800207bc  xor     r9d, r9d; lpName
0x1800207bf  mov     r8d, r15d; lMaximumCount
0x1800207c2  mov     edx, r15d; lInitialCount
0x1800207c5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800207c7  call    cs:__imp_CreateSemaphoreA
0x1800207cd  xor     r9d, r9d; lpName
0x1800207d0  mov     r8d, r15d; lMaximumCount
0x1800207d3  mov     edx, r15d; lInitialCount
0x1800207d6  mov     cs:hSemaphore, rax
0x1800207dd  xor     ecx, ecx; lpSemaphoreAttributes
0x1800207df  call    cs:__imp_CreateSemaphoreA
0x1800207e5  lea     edi, [rsi+2]
0x1800207e8  mov     cs:hHandle, rax
0x1800207ef  mov     ecx, edi; Size
0x1800207f1  call    cs:__imp_malloc
0x1800207f7  mov     ecx, edi; Size
0x1800207f9  mov     cs:lpBuffer, rax
0x180020800  call    cs:__imp_malloc
0x180020806  mov     esi, [rbx+38h]
0x180020809  mov     edi, [rbx+1Ch]
0x18002080c  mov     cs:Block, rax
0x180020813  jmp     short loc_18002082F
0x180020815  mov     rax, cs:Block
0x18002081c  jmp     short loc_18002082F
0x18002081e  mov     esi, 10000h
0x180020823  mov     [rbx+38h], esi
0x180020826  lea     ecx, [rsi+2]; Size
0x180020829  call    cs:__imp_malloc
0x18002082f  mov     r8d, esi; uBytes
0x180020832  mov     [rbx+28h], rax
0x180020836  mov     rdx, rax; lpBuffer
0x180020839  mov     [rbx], r15d
0x18002083c  mov     ecx, edi; hFile
0x18002083e  call    cs:__imp__lread
0x180020844  movsxd  rdi, eax
0x180020847  cmp     edi, 0FFFFFFFFh
0x18002084a  jnz     short loc_18002085E
0x18002084c  mov     ecx, [rbx+1Ch]; hFile
0x18002084f  call    cs:__imp__lclose
0x180020855  cmp     [rbx+4Ch], r14d
0x180020859  jmp     loc_18002078C
0x18002085e  cmp     [rbx+4Ch], r14d
0x180020862  jz      short loc_1800208D4
0x180020864  cmp     cs:dword_18008C21C, r14d
0x18002086b  mov     dword ptr [rbx+3Ch], 0FFFFFFFEh
0x180020872  jnz     short loc_1800208AE
0x180020874  lea     rax, [rbx+48h]
0x180020878  xor     r9d, r9d; lpParameter
0x18002087b  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x180020880  lea     r8, ?ReadAhead@@YAKPEAX@Z; lpStartAddress
0x180020887  xor     edx, edx; dwStackSize
0x180020889  mov     [rsp+68h+dwCreationFlags], r14d; dwCreationFlags
0x18002088e  xor     ecx, ecx; lpThreadAttributes
0x180020890  call    cs:__imp_CreateThread
0x180020896  mov     [rbx+40h], rax
0x18002089a  test    rax, rax
0x18002089d  jnz     short loc_1800208A5
0x18002089f  mov     [rbx+4Ch], r14d
0x1800208a3  jmp     short loc_1800208D4
0x1800208a5  mov     cs:dword_18008C21C, r15d
0x1800208ac  jmp     short loc_1800208D4
0x1800208ae  mov     rcx, cs:hSemaphore; hSemaphore
0x1800208b5  xor     r8d, r8d; lpPreviousCount
0x1800208b8  mov     edx, r15d; lReleaseCount
0x1800208bb  call    cs:__imp_ReleaseSemaphore
0x1800208c1  mov     rcx, cs:hHandle; hSemaphore
0x1800208c8  xor     r8d, r8d; lpPreviousCount
0x1800208cb  mov     edx, r15d; lReleaseCount
0x1800208ce  call    cs:__imp_ReleaseSemaphore
0x1800208d4  mov     rcx, [rbx+28h]
0x1800208d8  mov     [rbx+8], rcx
0x1800208dc  add     rcx, rdi
0x1800208df  mov     [rbx+10h], rcx
0x1800208e3  mov     [rcx+1], r14b
0x1800208e7  mov     rcx, rbp; char *
0x1800208ea  mov     [rbx+20h], edi
0x1800208ed  mov     [rbx+24h], r14d
0x1800208f1  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x1800208f6  mov     [rbx+30h], rax
0x1800208fa  mov     [rbx], r15d
0x1800208fd  mov     [rbx+18h], r14d
0x180020901  mov     rax, rbx
0x180020904  add     rsp, 38h
0x180020908  pop     r15
0x18002090a  pop     r14
0x18002090c  pop     rdi
0x18002090d  pop     rsi
0x18002090e  pop     rbp
0x18002090f  pop     rbx
0x180020910  retn
```
