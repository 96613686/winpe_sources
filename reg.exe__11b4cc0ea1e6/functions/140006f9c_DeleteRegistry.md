# DeleteRegistry

- ea: `0x140006f9c`
- end: `0x14000716a`
- name: `DeleteRegistry`
- size: `462`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1400030b8`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140001fec`
- `0x140002234`
- `0x140002a28`
- `0x140002ac8`
- `0x140002b70`
- `0x140002f30`
- `0x140006f9c`
- `0x140007170`
- `0x14000752c`
- `0x140007834`
- `0x14000cd48`
- `0x14000dc24`

## pseudocode

```c
__int64 __fastcall DeleteRegistry(unsigned int a1, __int64 a2)
{
  FILE *v4; // rax
  unsigned int v5; // ebx
  __int64 v7; // rcx
  int v8; // ebx
  FILE *v9; // rax
  const WCHAR *ResString2FromModule; // rsi
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  FILE *v14; // rax
  FILE *v15; // rax
  _DWORD v16[4]; // [rsp+20h] [rbp-79h] BYREF
  _BYTE v17[4]; // [rsp+30h] [rbp-69h] BYREF
  int v18; // [rsp+34h] [rbp-65h]
  HKEY v19; // [rsp+38h] [rbp-61h]
  int v20; // [rsp+4Ch] [rbp-4Dh]
  const WCHAR *v21; // [rsp+80h] [rbp-19h]
  __int64 v22; // [rsp+90h] [rbp-9h]

  v16[0] = 0;
  v18 = 0;
  memset_0(v17, 0, 0x94u);
  if ( a1 && a2 )
  {
    InitGlobalData(2, v17);
    if ( !(unsigned int)ParseDeleteCmdLine(a1, a2, v17, v16) )
    {
      v4 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v4);
      v5 = 1;
LABEL_7:
      FreeGlobalData(v17);
      return v5;
    }
    if ( v16[0] == 1 )
    {
      Usage(2);
      v5 = 0;
      goto LABEL_7;
    }
    if ( !(unsigned int)RegConnectMachine(v17) )
    {
      v8 = 0;
      SaveErrorMessage(0xFFFFFFFFLL);
      v9 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v9);
LABEL_19:
      FreeGlobalData(v17);
      return v8 != 0;
    }
    if ( v22 || v20 == 1 )
    {
      v13 = DeleteValues(v17);
    }
    else
    {
      ResString2FromModule = (const WCHAR *)GetResString2FromModule(v7, 201, 0);
      GetResString2FromModule(v11, 206, 1);
      do
        v12 = Prompt(ResString2FromModule);
      while ( v12 > 2 );
      if ( v12 != 1 )
      {
        SaveErrorMessage(1223);
        v14 = o___acrt_iob_func_0(1u);
        ShowLastErrorEx(v14);
        v8 = 0;
        goto LABEL_19;
      }
      v13 = RecursiveDeleteKey(v19, v21, 0, (__int64)v17);
    }
    v8 = v13;
    goto LABEL_19;
  }
  SaveErrorMessage(87);
  v15 = o___acrt_iob_func_0(2u);
  ShowLastErrorEx(v15);
  return 1;
}

```

## disassembly

```asm
0x140006f9c  mov     [rsp-8+arg_10], rbx
0x140006fa1  push    rbp
0x140006fa2  push    rsi
0x140006fa3  push    r14
0x140006fa5  lea     rbp, [rsp-47h]
0x140006faa  sub     rsp, 0E0h
0x140006fb1  mov     rax, cs:__security_cookie
0x140006fb8  xor     rax, rsp
0x140006fbb  mov     [rbp+57h+var_20], rax
0x140006fbf  mov     rbx, rdx
0x140006fc2  mov     [rbp+57h+var_D0], 0
0x140006fc9  mov     esi, ecx
0x140006fcb  xor     eax, eax
0x140006fcd  xor     edx, edx; Val
0x140006fcf  mov     [rbp+57h+var_BC], eax
0x140006fd2  lea     rcx, [rbp+57h+var_C0]; void *
0x140006fd6  mov     r8d, 94h; Size
0x140006fdc  call    memset_0
0x140006fe1  test    esi, esi
0x140006fe3  jz      loc_140007124
0x140006fe9  test    rbx, rbx
0x140006fec  jz      loc_140007124
0x140006ff2  lea     rdx, [rbp+57h+var_C0]
0x140006ff6  mov     ecx, 2
0x140006ffb  call    InitGlobalData
0x140007000  lea     r9, [rbp+57h+var_D0]
0x140007004  mov     rdx, rbx
0x140007007  lea     r8, [rbp+57h+var_C0]
0x14000700b  mov     ecx, esi
0x14000700d  call    ParseDeleteCmdLine
0x140007012  test    eax, eax
0x140007014  jnz     short loc_140007032
0x140007016  lea     ecx, [rax+2]; Ix
0x140007019  call    _o___acrt_iob_func_0
0x14000701e  mov     rcx, rax
0x140007021  mov     edx, 20000h
0x140007026  call    ShowLastErrorEx
0x14000702b  mov     ebx, 1
0x140007030  jmp     short loc_140007046
0x140007032  mov     ebx, 1
0x140007037  cmp     [rbp+57h+var_D0], ebx
0x14000703a  jnz     short loc_140007056
0x14000703c  lea     ecx, [rbx+1]
0x14000703f  call    Usage
0x140007044  xor     ebx, ebx
0x140007046  lea     rcx, [rbp+57h+var_C0]
0x14000704a  call    FreeGlobalData
0x14000704f  mov     eax, ebx
0x140007051  jmp     loc_14000714A
0x140007056  lea     rcx, [rbp+57h+var_C0]
0x14000705a  call    RegConnectMachine
0x14000705f  test    eax, eax
0x140007061  jnz     short loc_140007087
0x140007063  or      ecx, 0FFFFFFFFh
0x140007066  xor     ebx, ebx
0x140007068  call    SaveErrorMessage
0x14000706d  lea     ecx, [rbx+2]; Ix
0x140007070  call    _o___acrt_iob_func_0
0x140007075  mov     rcx, rax
0x140007078  mov     edx, 20001h
0x14000707d  call    ShowLastErrorEx
0x140007082  jmp     loc_140007112
0x140007087  cmp     [rbp+57h+var_60], 0
0x14000708c  jnz     short loc_140007107
0x14000708e  cmp     [rbp+57h+var_A4], ebx
0x140007091  jz      short loc_140007107
0x140007093  xor     r8d, r8d
0x140007096  mov     edx, 0C9h
0x14000709b  call    GetResString2FromModule
0x1400070a0  mov     r8d, ebx
0x1400070a3  mov     edx, 0CEh
0x1400070a8  mov     rsi, rax
0x1400070ab  call    GetResString2FromModule
0x1400070b0  mov     r14, rax
0x1400070b3  mov     r9d, [rbp+57h+var_A8]
0x1400070b7  mov     r8, r14
0x1400070ba  mov     rdx, [rbp+57h+var_68]
0x1400070be  mov     rcx, rsi
0x1400070c1  call    Prompt
0x1400070c6  cmp     eax, 2
0x1400070c9  jg      short loc_1400070B3
0x1400070cb  cmp     eax, ebx
0x1400070cd  jnz     short loc_1400070E5
0x1400070cf  mov     rdx, [rbp+57h+var_70]
0x1400070d3  lea     r9, [rbp+57h+var_C0]
0x1400070d7  mov     rcx, [rbp+57h+var_B8]
0x1400070db  xor     r8d, r8d
0x1400070de  call    RecursiveDeleteKey
0x1400070e3  jmp     short loc_140007110
0x1400070e5  mov     ecx, 4C7h
0x1400070ea  call    SaveErrorMessage
0x1400070ef  mov     ecx, ebx; Ix
0x1400070f1  call    _o___acrt_iob_func_0
0x1400070f6  mov     rcx, rax
0x1400070f9  mov     edx, 20000h
0x1400070fe  call    ShowLastErrorEx
0x140007103  xor     ebx, ebx
0x140007105  jmp     short loc_140007112
0x140007107  lea     rcx, [rbp+57h+var_C0]
0x14000710b  call    DeleteValues
0x140007110  mov     ebx, eax
0x140007112  lea     rcx, [rbp+57h+var_C0]
0x140007116  call    FreeGlobalData
0x14000711b  xor     eax, eax
0x14000711d  test    ebx, ebx
0x14000711f  setnz   al
0x140007122  jmp     short loc_14000714A
0x140007124  mov     ecx, 57h ; 'W'
0x140007129  call    SaveErrorMessage
0x14000712e  mov     ecx, 2; Ix
0x140007133  call    _o___acrt_iob_func_0
0x140007138  mov     rcx, rax
0x14000713b  mov     edx, 20000h
0x140007140  call    ShowLastErrorEx
0x140007145  mov     eax, 1
0x14000714a  mov     rcx, [rbp+57h+var_20]
0x14000714e  xor     rcx, rsp; StackCookie
0x140007151  call    __security_check_cookie
0x140007156  mov     rbx, [rsp+0F0h+arg_10]
0x14000715e  add     rsp, 0E0h
0x140007165  pop     r14
0x140007167  pop     rsi
0x140007168  pop     rbp
0x140007169  retn
```
