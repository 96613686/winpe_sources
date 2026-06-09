# AllocRequest

- ea: `0x18000274c`
- end: `0x1800028c7`
- name: `AllocRequest`
- size: `379`
- prototype: `char *__fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039f8`
- `0x180003af0`

## callees

- `0x18000274c`
- `0x180007df8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180002817`
- `KERNEL32!LocalFree` at `0x180002817`
- `KERNEL32!LocalAlloc` at `0x18000283b`
- `KERNEL32!LocalAlloc` at `0x18000283b`
- `KERNEL32!LeaveCriticalSection` at `0x1800027c9`
- `KERNEL32!LeaveCriticalSection` at `0x1800028ab`
- `KERNEL32!LeaveCriticalSection` at `0x1800027c9`
- `KERNEL32!LeaveCriticalSection` at `0x1800028ab`
- `KERNEL32!EnterCriticalSection` at `0x180002767`
- `KERNEL32!EnterCriticalSection` at `0x180002767`

## pseudocode

```c
char *__fastcall AllocRequest(unsigned int a1)
{
  unsigned int *v2; // rsi
  unsigned int *v3; // rcx
  unsigned int *v4; // r8
  int v5; // eax
  unsigned int *v6; // r9
  int v7; // edx
  unsigned int *v8; // rbx
  unsigned int v10; // edi
  unsigned int *v11; // rax

  v2 = 0;
  EnterCriticalSection(&stru_18000E350);
  v3 = (unsigned int *)qword_18000E348;
  if ( !qword_18000E348 )
    goto LABEL_23;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = (unsigned int *)qword_18000E348;
  do
  {
    if ( v8[1] )
    {
      if ( !v5 )
        v4 = v8;
      if ( a1 <= *v8 )
      {
        v7 = 1;
        goto LABEL_8;
      }
    }
    else
    {
      if ( a1 <= *v8 )
        break;
      v5 = 1;
    }
    if ( !v7 )
    {
      v6 = v2;
      v2 = v8;
    }
LABEL_8:
    v8 = (unsigned int *)*((_QWORD *)v8 + 2);
  }
  while ( v8 );
  if ( v8 )
  {
    v8[1] = 1;
    goto LABEL_11;
  }
  if ( v5 )
  {
    if ( v4 )
    {
      v3 = (unsigned int *)*((_QWORD *)v4 + 2);
      *((_QWORD *)v4 + 2) = *((_QWORD *)v3 + 2);
    }
    else
    {
      qword_18000E348 = (HLOCAL)*((_QWORD *)qword_18000E348 + 2);
    }
    if ( v2 == v3 )
      v2 = v6;
    LocalFree(v3);
  }
LABEL_23:
  if ( a1 + 7 < a1 || (v10 = (a1 + 7) & 0xFFFFFFF8, v10 + 24 < v10) )
  {
    TspLog(1, "AllocRequest: Arithmatic overflow error %x", -2147024362);
LABEL_31:
    LeaveCriticalSection(&stru_18000E350);
    return 0;
  }
  else
  {
    v11 = (unsigned int *)LocalAlloc(0x40u, v10 + 24);
    v8 = v11;
    if ( !v11 )
    {
      TspLog(1, "AllocRequest: failed to alloc a req block");
      goto LABEL_31;
    }
    *v11 = v10;
    v11[1] = 1;
    if ( v2 )
    {
      *((_QWORD *)v11 + 2) = *((_QWORD *)v2 + 2);
      *((_QWORD *)v2 + 2) = v11;
    }
    else
    {
      *((_QWORD *)v11 + 2) = qword_18000E348;
      qword_18000E348 = v11;
    }
LABEL_11:
    LeaveCriticalSection(&stru_18000E350);
    return (char *)(v8 + 6);
  }
}

```

## disassembly

```asm
0x18000274c  push    rbx
0x18000274e  push    rbp
0x18000274f  push    rsi
0x180002750  push    rdi
0x180002751  push    r14
0x180002753  push    r15
0x180002755  sub     rsp, 28h
0x180002759  mov     ebp, ecx
0x18000275b  lea     r15, stru_18000E350
0x180002762  mov     rcx, r15; lpCriticalSection
0x180002765  xor     esi, esi
0x180002767  call    cs:__imp_EnterCriticalSection
0x18000276e  nop     dword ptr [rax+rax+00h]
0x180002773  mov     rcx, cs:qword_18000E348
0x18000277a  lea     r14d, [rsi+1]
0x18000277e  test    rcx, rcx
0x180002781  jz      loc_180002823
0x180002787  xor     r8d, r8d
0x18000278a  xor     eax, eax
0x18000278c  xor     r9d, r9d
0x18000278f  xor     edx, edx
0x180002791  mov     rbx, rcx
0x180002794  test    rcx, rcx
0x180002797  jz      loc_180002823
0x18000279d  cmp     dword ptr [rbx+4], 0
0x1800027a1  jnz     short loc_1800027DE
0x1800027a3  cmp     ebp, [rbx]
0x1800027a5  jbe     short loc_1800027BD
0x1800027a7  mov     eax, r14d
0x1800027aa  test    edx, edx
0x1800027ac  jnz     short loc_1800027B4
0x1800027ae  mov     r9, rsi
0x1800027b1  mov     rsi, rbx
0x1800027b4  mov     rbx, [rbx+10h]
0x1800027b8  test    rbx, rbx
0x1800027bb  jnz     short loc_18000279D
0x1800027bd  test    rbx, rbx
0x1800027c0  jz      short loc_1800027EE
0x1800027c2  mov     [rbx+4], r14d
0x1800027c6  mov     rcx, r15; lpCriticalSection
0x1800027c9  call    cs:__imp_LeaveCriticalSection
0x1800027d0  nop     dword ptr [rax+rax+00h]
0x1800027d5  lea     rax, [rbx+18h]
0x1800027d9  jmp     loc_1800028B9
0x1800027de  test    eax, eax
0x1800027e0  jnz     short loc_1800027E5
0x1800027e2  mov     r8, rbx
0x1800027e5  cmp     ebp, [rbx]
0x1800027e7  ja      short loc_1800027AA
0x1800027e9  mov     edx, r14d
0x1800027ec  jmp     short loc_1800027B4
0x1800027ee  test    eax, eax
0x1800027f0  jz      short loc_180002823
0x1800027f2  test    r8, r8
0x1800027f5  jnz     short loc_180002804
0x1800027f7  mov     rax, [rcx+10h]
0x1800027fb  mov     cs:qword_18000E348, rax
0x180002802  jmp     short loc_180002810
0x180002804  mov     rcx, [r8+10h]; hMem
0x180002808  mov     rax, [rcx+10h]
0x18000280c  mov     [r8+10h], rax
0x180002810  cmp     rsi, rcx
0x180002813  cmovz   rsi, r9
0x180002817  call    cs:__imp_LocalFree
0x18000281e  nop     dword ptr [rax+rax+00h]
0x180002823  lea     edi, [rbp+7]
0x180002826  cmp     edi, ebp
0x180002828  jb      short loc_180002893
0x18000282a  and     edi, 0FFFFFFF8h
0x18000282d  lea     eax, [rdi+18h]
0x180002830  cmp     eax, edi
0x180002832  jb      short loc_180002893
0x180002834  mov     edx, eax; uBytes
0x180002836  mov     ecx, 40h ; '@'; uFlags
0x18000283b  call    cs:__imp_LocalAlloc
0x180002842  nop     dword ptr [rax+rax+00h]
0x180002847  mov     rbx, rax
0x18000284a  test    rax, rax
0x18000284d  jnz     short loc_180002860
0x18000284f  lea     rdx, aAllocrequestFa; "AllocRequest: failed to alloc a req blo"...
0x180002856  mov     ecx, r14d
0x180002859  call    TspLog
0x18000285e  jmp     short loc_1800028A8
0x180002860  mov     [rax], edi
0x180002862  mov     [rax+4], r14d
0x180002866  test    rsi, rsi
0x180002869  jnz     short loc_180002882
0x18000286b  mov     rax, cs:qword_18000E348
0x180002872  mov     [rbx+10h], rax
0x180002876  mov     cs:qword_18000E348, rbx
0x18000287d  jmp     loc_1800027C6
0x180002882  mov     rax, [rsi+10h]
0x180002886  mov     [rbx+10h], rax
0x18000288a  mov     [rsi+10h], rbx
0x18000288e  jmp     loc_1800027C6
0x180002893  mov     r8d, 80070216h
0x180002899  lea     rdx, aAllocrequestAr; "AllocRequest: Arithmatic overflow error"...
0x1800028a0  mov     ecx, r14d
0x1800028a3  call    TspLog
0x1800028a8  mov     rcx, r15; lpCriticalSection
0x1800028ab  call    cs:__imp_LeaveCriticalSection
0x1800028b2  nop     dword ptr [rax+rax+00h]
0x1800028b7  xor     eax, eax
0x1800028b9  add     rsp, 28h
0x1800028bd  pop     r15
0x1800028bf  pop     r14
0x1800028c1  pop     rdi
0x1800028c2  pop     rsi
0x1800028c3  pop     rbp
0x1800028c4  pop     rbx
0x1800028c5  retn
```
