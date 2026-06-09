# ensureCabinet

- ea: `0x1400052b0`
- end: `0x14000540a`
- name: `ensureCabinet`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000488c`

## callees

- `0x140004398`
- `0x1400052b0`
- `0x140006e0c`
- `0x140008190`
- `0x14000e412`
- `0x14000e450`

## import_xrefs

- `Cabinet!__imp_FCICreate` at `0x1400053b9`
- `Cabinet!__imp_FCICreate` at `0x1400053b9`

## string_xrefs

- `0x1400053cf`: `FCICreate`

## pseudocode

```c
__int64 __fastcall ensureCabinet(__int64 a1, int a2, __int64 a3)
{
  __int64 v6; // r9
  INT_PTR (__cdecl *pfnopen)(LPSTR, int, int, int *, void *); // r8
  HFCI v8; // rax
  CCAB pccab; // [rsp+70h] [rbp-358h] BYREF

  memset_0(&pccab, 0, sizeof(pccab));
  if ( !*(_QWORD *)(a1 + 88) )
  {
    if ( !(unsigned int)ccabFromSession(&pccab, a1, 0, a3) || !(unsigned int)setCabinetReserve(&pccab, a1, a3, v6) )
      return 0;
    pfnopen = (INT_PTR (__cdecl *)(LPSTR, int, int, int *, void *))fciOpenUNC;
    if ( !a2 )
      pfnopen = (INT_PTR (__cdecl *)(LPSTR, int, int, int *, void *))fciOpen;
    v8 = FCICreate(
           (PERF)(a1 + 96),
           fciFilePlaced,
           fciAlloc,
           fciFree,
           pfnopen,
           fciRead,
           fciWrite,
           fciClose,
           fciSeek,
           fciDelete,
           fciTempFile,
           &pccab,
           (void *)(a1 + 3128));
    *(_QWORD *)(a1 + 88) = v8;
    if ( !v8 )
    {
      mapFCIError(a3, a1, "FCICreate", (_DWORD *)(a1 + 96));
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1400052b0  mov     [rsp+arg_8], rbx
0x1400052b5  push    rbp
0x1400052b6  push    rsi
0x1400052b7  push    rdi
0x1400052b8  sub     rsp, 3B0h
0x1400052bf  mov     rax, cs:__security_cookie
0x1400052c6  xor     rax, rsp
0x1400052c9  mov     [rsp+3C8h+var_28], rax
0x1400052d1  mov     rdi, r8
0x1400052d4  mov     ebp, edx
0x1400052d6  mov     rbx, rcx
0x1400052d9  xor     edx, edx; Val
0x1400052db  mov     r8d, 324h; Size
0x1400052e1  lea     rcx, [rsp+3C8h+var_358]; void *
0x1400052e6  call    memset_0
0x1400052eb  cmp     qword ptr [rbx+58h], 0
0x1400052f0  jnz     loc_1400053E2
0x1400052f6  mov     r9, rdi
0x1400052f9  lea     rcx, [rsp+3C8h+var_358]
0x1400052fe  xor     r8d, r8d
0x140005301  mov     rdx, rbx
0x140005304  call    ccabFromSession
0x140005309  test    eax, eax
0x14000530b  jz      loc_1400053DE
0x140005311  mov     r8, rdi
0x140005314  lea     rcx, [rsp+3C8h+var_358]
0x140005319  mov     rdx, rbx
0x14000531c  call    setCabinetReserve
0x140005321  test    eax, eax
0x140005323  jz      loc_1400053DE
0x140005329  lea     rax, [rbx+0C38h]
0x140005330  test    ebp, ebp
0x140005332  mov     [rsp+3C8h+pv], rax; pv
0x140005337  lea     rcx, fciOpen
0x14000533e  lea     rax, [rsp+3C8h+var_358]
0x140005343  mov     [rsp+3C8h+pccab], rax; pccab
0x140005348  lea     r8, fciOpenUNC
0x14000534f  cmovz   r8, rcx
0x140005353  lea     rax, fciTempFile
0x14000535a  mov     [rsp+3C8h+pfnfcigtf], rax; pfnfcigtf
0x14000535f  lea     r9, fciFree; pfnf
0x140005366  lea     rax, fciDelete
0x14000536d  mov     [rsp+3C8h+pfndelete], rax; pfndelete
0x140005372  lea     rdx, fciFilePlaced; pfnfcifp
0x140005379  lea     rax, fciSeek
0x140005380  mov     [rsp+3C8h+pfnseek], rax; pfnseek
0x140005385  lea     rcx, [rbx+60h]; perf
0x140005389  lea     rax, fciClose
0x140005390  mov     [rsp+3C8h+pfnclose], rax; pfnclose
0x140005395  lea     rax, fciWrite
0x14000539c  mov     [rsp+3C8h+pfnwrite], rax; pfnwrite
0x1400053a1  lea     rax, fciRead
0x1400053a8  mov     [rsp+3C8h+pfnread], rax; pfnread
0x1400053ad  mov     [rsp+3C8h+pfnopen], r8; pfnopen
0x1400053b2  lea     r8, fciAlloc; pfna
0x1400053b9  call    cs:__imp_FCICreate
0x1400053bf  mov     [rbx+58h], rax
0x1400053c3  test    rax, rax
0x1400053c6  jnz     short loc_1400053E2
0x1400053c8  lea     r9, [rbx+60h]
0x1400053cc  mov     rdx, rbx
0x1400053cf  lea     r8, aFcicreate; "FCICreate"
0x1400053d6  mov     rcx, rdi
0x1400053d9  call    mapFCIError
0x1400053de  xor     eax, eax
0x1400053e0  jmp     short loc_1400053E7
0x1400053e2  mov     eax, 1
0x1400053e7  mov     rcx, [rsp+3C8h+var_28]
0x1400053ef  xor     rcx, rsp; StackCookie
0x1400053f2  call    __security_check_cookie
0x1400053f7  mov     rbx, [rsp+3C8h+arg_8]
0x1400053ff  add     rsp, 3B0h
0x140005406  pop     rdi
0x140005407  pop     rsi
0x140005408  pop     rbp
0x140005409  retn
```
