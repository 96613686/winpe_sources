# ReplaceStringUnsafe

- ea: `0x180017070`
- end: `0x180017297`
- name: `ReplaceStringUnsafe`
- size: `551`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800407d0`

## callees

- `0x180017070`
- `0x1800207c0`
- `0x180020850`
- `0x180023b05`
- `0x180042f7c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180017147`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180017147`

## pseudocode

```c
unsigned int __fastcall ReplaceStringUnsafe(_WORD *Src, __int64 a2, const wchar_t *a3, _WORD *a4)
{
  __int64 v4; // r14
  __int64 v6; // r13
  const wchar_t *v7; // rsi
  __int64 v8; // rbp
  unsigned __int64 v9; // rax
  unsigned int v10; // edi
  __int64 v11; // rbx
  unsigned __int64 v12; // rbx
  wchar_t *v13; // r15
  const wchar_t *i; // rcx
  wchar_t *v15; // rbx
  char *v16; // rcx
  __int64 v17; // rsi
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // ebx
  unsigned int v21; // edi
  unsigned int result; // eax
  char *v23; // [rsp+20h] [rbp-868h]
  char *v24; // [rsp+20h] [rbp-868h]
  wchar_t Str[1024]; // [rsp+40h] [rbp-848h] BYREF

  v4 = -1;
  v6 = -1;
  v7 = a3;
  do
    ++v6;
  while ( a3[v6] );
  v8 = -1;
  do
    ++v8;
  while ( a4[v8] );
  v9 = -1;
  do
    ++v9;
  while ( Src[v9] );
  v10 = 1023;
  v11 = 1023;
  if ( v9 < 0x3FF )
    v11 = (unsigned int)v9;
  if ( TracePrinter )
  {
    if ( DebugExtPrint )
      TracePrinterExt((wchar_t *)L"Replacing %s with %s", a3, a4);
    else
      TracePrinter(L"Replacing %s with %s", a3, a4);
  }
  v12 = v11;
  memcpy_0(Str, Src, v12 * 2);
  if ( v12 >= 1024 )
    _report_rangecheckfailure();
  v23 = (char *)Src;
  Str[v12] = 0;
  v13 = Str;
  while ( 2 )
  {
    for ( i = v13; ; i = &v15[(int)v6] )
    {
      v15 = wcsstr(i, v7);
      if ( !v15 )
      {
        do
          ++v4;
        while ( v13[v4] );
        if ( (int)v4 + 1 <= v10 )
          v10 = v4 + 1;
        memcpy_0(v23, v13, 2LL * v10);
        result = (unsigned int)TracePrinter;
        if ( TracePrinter )
        {
          if ( DebugExtPrint )
            return TracePrinterExt((wchar_t *)L"  giving %s\n", Src);
          else
            return TracePrinter(L"  giving %s\n", Src);
        }
        return result;
      }
      if ( v15 == Str || *v15 != 37 || *(v15 - 1) != 37 )
        break;
    }
    v16 = v23;
    v17 = v15 - v13;
    v24 = &v23[2 * v17];
    if ( (int)v17 + (int)v8 <= v10 )
    {
      memcpy_0(v16, v13, 2LL * (unsigned int)v17);
      memcpy_0(v24, a4, 2LL * ((int)v8 + 1));
      v23 = &v24[2 * (int)v8];
      v18 = v17 + v8;
      v7 = a3;
      v10 -= v18;
      v13 = &v15[(int)v6];
      continue;
    }
    break;
  }
  v19 = v10;
  if ( (unsigned int)v17 <= v10 )
    v19 = v15 - v13;
  v20 = v19;
  memcpy_0(v16, v13, 2LL * v19);
  v21 = v10 - v20;
  if ( (unsigned int)v8 > v21 )
    LODWORD(v8) = v21;
  return (unsigned int)memcpy_0(v24, a4, 2LL * (unsigned int)v8);
}

```

## disassembly

```asm
0x180017070  mov     [rsp+arg_8], rbx
0x180017075  push    rbp
0x180017076  push    rsi
0x180017077  push    rdi
0x180017078  push    r12
0x18001707a  push    r13
0x18001707c  push    r14
0x18001707e  push    r15
0x180017080  sub     rsp, 850h
0x180017087  mov     rax, cs:__security_cookie
0x18001708e  xor     rax, rsp
0x180017091  mov     [rsp+888h+var_48], rax
0x180017099  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001709d  mov     [rsp+888h+Src], r9
0x1800170a2  mov     r12, rcx
0x1800170a5  mov     [rsp+888h+var_858], r8
0x1800170aa  mov     r13, r14
0x1800170ad  xor     ecx, ecx
0x1800170af  mov     rsi, r8
0x1800170b2  inc     r13
0x1800170b5  cmp     [r8+r13*2], cx
0x1800170ba  jnz     short loc_1800170B2
0x1800170bc  mov     rbp, r14
0x1800170bf  inc     rbp
0x1800170c2  cmp     [r9+rbp*2], cx
0x1800170c7  jnz     short loc_1800170BF
0x1800170c9  mov     rax, r14
0x1800170cc  inc     rax
0x1800170cf  cmp     [r12+rax*2], cx
0x1800170d4  jnz     short loc_1800170CC
0x1800170d6  mov     edi, 3FFh
0x1800170db  cmp     rax, rdi
0x1800170de  mov     ebx, edi
0x1800170e0  cmovb   ebx, eax
0x1800170e3  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800170ea  test    rax, rax
0x1800170ed  jz      short loc_180017110
0x1800170ef  cmp     cs:?DebugExtPrint@@3HA, ecx; int DebugExtPrint
0x1800170f5  mov     r8, r9
0x1800170f8  lea     rcx, aReplacingSWith; "Replacing %s with %s"
0x1800170ff  mov     rdx, rsi
0x180017102  jnz     short loc_18001710B
0x180017104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017109  jmp     short loc_180017110
0x18001710b  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x180017110  add     rbx, rbx
0x180017113  lea     rcx, [rsp+888h+Str]; void *
0x180017118  mov     r8, rbx; Size
0x18001711b  mov     rdx, r12; Src
0x18001711e  call    memcpy_0
0x180017123  cmp     rbx, 800h
0x18001712a  jnb     loc_180017291
0x180017130  xor     eax, eax
0x180017132  mov     [rsp+888h+var_868], r12
0x180017137  mov     [rsp+rbx+888h+Str], ax
0x18001713c  lea     r15, [rsp+888h+Str]
0x180017141  mov     rcx, r15; Str
0x180017144  mov     rdx, rsi; SubStr
0x180017147  call    cs:__imp_wcsstr
0x18001714d  mov     rbx, rax
0x180017150  test    rax, rax
0x180017153  jz      loc_18001723D
0x180017159  lea     rax, [rsp+888h+Str]
0x18001715e  cmp     rbx, rax
0x180017161  jz      short loc_180017179
0x180017163  cmp     word ptr [rbx], 25h ; '%'
0x180017167  jnz     short loc_180017179
0x180017169  cmp     word ptr [rbx-2], 25h ; '%'
0x18001716e  jnz     short loc_180017179
0x180017170  movsxd  rcx, r13d
0x180017173  lea     rcx, [rbx+rcx*2]
0x180017177  jmp     short loc_180017144
0x180017179  mov     rcx, [rsp+888h+var_868]; void *
0x18001717e  mov     rsi, rbx
0x180017181  sub     rsi, r15
0x180017184  mov     rdx, r15; Src
0x180017187  sar     rsi, 1
0x18001718a  lea     rax, [rcx+rsi*2]
0x18001718e  mov     [rsp+888h+var_868], rax
0x180017193  lea     eax, [rsi+rbp]
0x180017196  cmp     eax, edi
0x180017198  ja      short loc_1800171E2
0x18001719a  mov     r8d, esi
0x18001719d  add     r8, r8; Size
0x1800171a0  call    memcpy_0
0x1800171a5  mov     r15, [rsp+888h+var_868]
0x1800171aa  lea     eax, [rbp+1]
0x1800171ad  mov     rdx, [rsp+888h+Src]; Src
0x1800171b2  mov     rcx, r15; void *
0x1800171b5  movsxd  r8, eax
0x1800171b8  add     r8, r8; Size
0x1800171bb  call    memcpy_0
0x1800171c0  movsxd  rax, ebp
0x1800171c3  lea     rax, [r15+rax*2]
0x1800171c7  mov     [rsp+888h+var_868], rax
0x1800171cc  lea     eax, [rsi+rbp]
0x1800171cf  mov     rsi, [rsp+888h+var_858]
0x1800171d4  sub     edi, eax
0x1800171d6  movsxd  rax, r13d
0x1800171d9  lea     r15, [rbx+rax*2]
0x1800171dd  jmp     loc_180017141
0x1800171e2  mov     eax, edi
0x1800171e4  cmp     esi, edi
0x1800171e6  cmovbe  eax, esi
0x1800171e9  mov     r8d, eax
0x1800171ec  add     r8, r8; Size
0x1800171ef  mov     ebx, eax
0x1800171f1  call    memcpy_0
0x1800171f6  mov     rdx, [rsp+888h+Src]; Src
0x1800171fb  sub     edi, ebx
0x1800171fd  mov     rcx, [rsp+888h+var_868]; void *
0x180017202  cmp     ebp, edi
0x180017204  cmova   ebp, edi
0x180017207  mov     r8d, ebp
0x18001720a  add     r8, r8; Size
0x18001720d  call    memcpy_0
0x180017212  mov     rcx, [rsp+888h+var_48]
0x18001721a  xor     rcx, rsp; StackCookie
0x18001721d  call    __security_check_cookie
0x180017222  mov     rbx, [rsp+888h+arg_8]
0x18001722a  add     rsp, 850h
0x180017231  pop     r15
0x180017233  pop     r14
0x180017235  pop     r13
0x180017237  pop     r12
0x180017239  pop     rdi
0x18001723a  pop     rsi
0x18001723b  pop     rbp
0x18001723c  retn
0x18001723d  xor     ebx, ebx
0x18001723f  inc     r14
0x180017242  cmp     [r15+r14*2], bx
0x180017247  jnz     short loc_18001723F
0x180017249  mov     rcx, [rsp+888h+var_868]; void *
0x18001724e  lea     eax, [r14+1]
0x180017252  cmp     eax, edi
0x180017254  mov     rdx, r15; Src
0x180017257  cmovbe  edi, eax
0x18001725a  mov     r8d, edi
0x18001725d  add     r8, r8; Size
0x180017260  call    memcpy_0
0x180017265  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x18001726c  test    rax, rax
0x18001726f  jz      short loc_180017212
0x180017271  cmp     cs:?DebugExtPrint@@3HA, ebx; int DebugExtPrint
0x180017277  lea     rcx, aGivingS; "  giving %s\n"
0x18001727e  mov     rdx, r12
0x180017281  jnz     short loc_18001728A
0x180017283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017288  jmp     short loc_180017212
0x18001728a  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x18001728f  jmp     short loc_180017212
0x180017291  call    __report_rangecheckfailure
```
