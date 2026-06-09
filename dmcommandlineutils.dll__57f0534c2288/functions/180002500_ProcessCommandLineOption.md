# ProcessCommandLineOption

- ea: `0x180002500`
- end: `0x18000261b`
- name: `ProcessCommandLineOption`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002180`

## callees

- `0x180001a98`
- `0x180001c04`
- `0x180002500`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002555`
- `msvcrt!_wcsicmp` at `0x180002555`

## pseudocode

```c
__int64 __fastcall ProcessCommandLineOption(
        __int64 a1,
        int a2,
        const wchar_t *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  unsigned int v6; // ebx
  int v7; // edi
  __int64 v8; // rbp
  const wchar_t *v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rdx
  int Number; // eax
  __int64 v17; // rdx
  const wchar_t *v19; // [rsp+60h] [rbp+18h]

  v19 = a3;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  if ( a2 > 0 )
  {
    while ( 1 )
    {
      if ( v7 )
        return v6;
      v12 = *(const wchar_t **)(a1 + 24 * v8);
      if ( !v12 )
        return (unsigned int)-2147024809;
      if ( !_wcsicmp(a3, v12) )
      {
        v13 = *(_DWORD *)(a1 + 24 * v8 + 8);
        if ( v13 )
        {
          if ( v13 == 1 )
          {
            v15 = *(_QWORD *)(a1 + 24 * v8 + 16);
            if ( v15 + 8 > (unsigned __int64)a5 )
              return (unsigned int)-2147467259;
            Number = GetNumber(a6, a4 + v15);
          }
          else
          {
            if ( v13 != 2 )
              goto LABEL_16;
            v17 = *(_QWORD *)(a1 + 24 * v8 + 16);
            if ( v17 + 16 > (unsigned __int64)a5 )
              return (unsigned int)-2147467259;
            Number = GetString(a6, a4 + v17);
          }
          v6 = Number;
          if ( Number < 0 )
            return v6;
          v7 = 1;
        }
        else
        {
          v14 = *(_QWORD *)(a1 + 24 * v8 + 16);
          if ( v14 + 4 > (unsigned __int64)a5 )
            return (unsigned int)-2147467259;
          v7 = 1;
          *(_DWORD *)(v14 + a4) = 1;
        }
      }
LABEL_16:
      v8 = (unsigned int)(v8 + 1);
      if ( (int)v8 >= a2 )
      {
        if ( v7 )
          return v6;
        return (unsigned int)-2147467259;
      }
      a3 = v19;
    }
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x180002500  mov     [rsp+arg_0], rbx
0x180002505  mov     [rsp+arg_8], rbp
0x18000250a  mov     [rsp+arg_10], r8
0x18000250f  push    rsi
0x180002510  push    rdi
0x180002511  push    r12
0x180002513  push    r13
0x180002515  push    r14
0x180002517  sub     rsp, 20h
0x18000251b  xor     ebx, ebx
0x18000251d  xor     edi, edi
0x18000251f  xor     ebp, ebp
0x180002521  mov     r12, r9
0x180002524  mov     r13d, edx
0x180002527  mov     r14, rcx
0x18000252a  test    edx, edx
0x18000252c  jle     loc_1800025F5
0x180002532  test    edi, edi
0x180002534  jnz     loc_1800025FA
0x18000253a  lea     rsi, ds:0[rbp*2]
0x180002542  add     rsi, rbp
0x180002545  mov     rdx, [r14+rsi*8]; String2
0x180002549  test    rdx, rdx
0x18000254c  jz      loc_180002614
0x180002552  mov     rcx, r8; String1
0x180002555  call    cs:__imp__wcsicmp
0x18000255c  nop     dword ptr [rax+rax+00h]
0x180002561  test    eax, eax
0x180002563  jnz     short loc_1800025E0
0x180002565  mov     eax, [r14+rsi*8+8]
0x18000256a  test    eax, eax
0x18000256c  jnz     short loc_18000258B
0x18000256e  mov     rdx, [r14+rsi*8+10h]
0x180002573  mov     eax, [rsp+48h+arg_20]
0x180002577  lea     rcx, [rdx+4]
0x18000257b  cmp     rcx, rax
0x18000257e  ja      short loc_1800025F5
0x180002580  mov     edi, 1
0x180002585  mov     [rdx+r12], edi
0x180002589  jmp     short loc_1800025E0
0x18000258b  cmp     eax, 1
0x18000258e  jnz     short loc_1800025B1
0x180002590  mov     rdx, [r14+rsi*8+10h]
0x180002595  mov     eax, [rsp+48h+arg_20]
0x180002599  lea     rcx, [rdx+8]
0x18000259d  cmp     rcx, rax
0x1800025a0  ja      short loc_1800025F5
0x1800025a2  mov     rcx, [rsp+48h+arg_28]
0x1800025a7  add     rdx, r12
0x1800025aa  call    GetNumber
0x1800025af  jmp     short loc_1800025D5
0x1800025b1  cmp     eax, 2
0x1800025b4  jnz     short loc_1800025E0
0x1800025b6  mov     rdx, [r14+rsi*8+10h]
0x1800025bb  mov     eax, [rsp+48h+arg_20]
0x1800025bf  lea     rcx, [rdx+10h]
0x1800025c3  cmp     rcx, rax
0x1800025c6  ja      short loc_1800025F5
0x1800025c8  mov     rcx, [rsp+48h+arg_28]
0x1800025cd  add     rdx, r12
0x1800025d0  call    GetString
0x1800025d5  mov     ebx, eax
0x1800025d7  test    eax, eax
0x1800025d9  js      short loc_1800025FA
0x1800025db  mov     edi, 1
0x1800025e0  inc     ebp
0x1800025e2  cmp     ebp, r13d
0x1800025e5  jge     short loc_1800025F1
0x1800025e7  mov     r8, [rsp+48h+arg_10]
0x1800025ec  jmp     loc_180002532
0x1800025f1  test    edi, edi
0x1800025f3  jnz     short loc_1800025FA
0x1800025f5  mov     ebx, 80004005h
0x1800025fa  mov     rbp, [rsp+48h+arg_8]
0x1800025ff  mov     eax, ebx
0x180002601  mov     rbx, [rsp+48h+arg_0]
0x180002606  add     rsp, 20h
0x18000260a  pop     r14
0x18000260c  pop     r13
0x18000260e  pop     r12
0x180002610  pop     rdi
0x180002611  pop     rsi
0x180002612  retn
0x180002614  mov     ebx, 80070057h
0x180002619  jmp     short loc_1800025FA
```
