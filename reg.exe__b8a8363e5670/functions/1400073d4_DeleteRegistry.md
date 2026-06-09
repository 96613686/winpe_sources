# DeleteRegistry

- ea: `0x1400073d4`
- end: `0x1400075a3`
- name: `DeleteRegistry`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1400031f4`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140002004`
- `0x1400022dc`
- `0x140002b6c`
- `0x140002c20`
- `0x140002ce4`
- `0x140003068`
- `0x1400073d4`
- `0x1400075ac`
- `0x14000799c`
- `0x140007cbc`
- `0x14000d694`
- `0x14000e798`

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
    if ( !(unsigned int)ParseDeleteCmdLine(a1, a2, (__int64)v17, v16) )
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
    if ( !RegConnectMachine((__int64)v17) )
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
      v13 = DeleteValues((__int64)v17);
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
0x1400073d4  mov     [rsp-8+arg_10], rbx
0x1400073d9  push    rbp
0x1400073da  push    rsi
0x1400073db  push    r14
0x1400073dd  lea     rbp, [rsp-47h]
0x1400073e2  sub     rsp, 0E0h
0x1400073e9  mov     rax, cs:__security_cookie
0x1400073f0  xor     rax, rsp
0x1400073f3  mov     [rbp+57h+var_20], rax
0x1400073f7  mov     rbx, rdx
0x1400073fa  mov     [rbp+57h+var_D0], 0
0x140007401  mov     esi, ecx
0x140007403  xor     eax, eax
0x140007405  xor     edx, edx; Val
0x140007407  mov     [rbp+57h+var_BC], eax
0x14000740a  lea     rcx, [rbp+57h+var_C0]; void *
0x14000740e  mov     r8d, 94h; Size
0x140007414  call    memset_0
0x140007419  test    esi, esi
0x14000741b  jz      loc_14000755C
0x140007421  test    rbx, rbx
0x140007424  jz      loc_14000755C
0x14000742a  lea     rdx, [rbp+57h+var_C0]
0x14000742e  mov     ecx, 2
0x140007433  call    InitGlobalData
0x140007438  lea     r9, [rbp+57h+var_D0]
0x14000743c  mov     rdx, rbx
0x14000743f  lea     r8, [rbp+57h+var_C0]
0x140007443  mov     ecx, esi
0x140007445  call    ParseDeleteCmdLine
0x14000744a  test    eax, eax
0x14000744c  jnz     short loc_14000746A
0x14000744e  lea     ecx, [rax+2]; Ix
0x140007451  call    _o___acrt_iob_func_0
0x140007456  mov     rcx, rax
0x140007459  mov     edx, 20000h
0x14000745e  call    ShowLastErrorEx
0x140007463  mov     ebx, 1
0x140007468  jmp     short loc_14000747E
0x14000746a  mov     ebx, 1
0x14000746f  cmp     [rbp+57h+var_D0], ebx
0x140007472  jnz     short loc_14000748E
0x140007474  lea     ecx, [rbx+1]
0x140007477  call    Usage
0x14000747c  xor     ebx, ebx
0x14000747e  lea     rcx, [rbp+57h+var_C0]
0x140007482  call    FreeGlobalData
0x140007487  mov     eax, ebx
0x140007489  jmp     loc_140007582
0x14000748e  lea     rcx, [rbp+57h+var_C0]
0x140007492  call    RegConnectMachine
0x140007497  test    eax, eax
0x140007499  jnz     short loc_1400074BF
0x14000749b  or      ecx, 0FFFFFFFFh
0x14000749e  xor     ebx, ebx
0x1400074a0  call    SaveErrorMessage
0x1400074a5  lea     ecx, [rbx+2]; Ix
0x1400074a8  call    _o___acrt_iob_func_0
0x1400074ad  mov     rcx, rax
0x1400074b0  mov     edx, 20001h
0x1400074b5  call    ShowLastErrorEx
0x1400074ba  jmp     loc_14000754A
0x1400074bf  cmp     [rbp+57h+var_60], 0
0x1400074c4  jnz     short loc_14000753F
0x1400074c6  cmp     [rbp+57h+var_A4], ebx
0x1400074c9  jz      short loc_14000753F
0x1400074cb  xor     r8d, r8d
0x1400074ce  mov     edx, 0C9h
0x1400074d3  call    GetResString2FromModule
0x1400074d8  mov     r8d, ebx
0x1400074db  mov     edx, 0CEh
0x1400074e0  mov     rsi, rax
0x1400074e3  call    GetResString2FromModule
0x1400074e8  mov     r14, rax
0x1400074eb  mov     r9d, [rbp+57h+var_A8]
0x1400074ef  mov     r8, r14
0x1400074f2  mov     rdx, [rbp+57h+var_68]
0x1400074f6  mov     rcx, rsi
0x1400074f9  call    Prompt
0x1400074fe  cmp     eax, 2
0x140007501  jg      short loc_1400074EB
0x140007503  cmp     eax, ebx
0x140007505  jnz     short loc_14000751D
0x140007507  mov     rdx, [rbp+57h+var_70]
0x14000750b  lea     r9, [rbp+57h+var_C0]
0x14000750f  mov     rcx, [rbp+57h+var_B8]
0x140007513  xor     r8d, r8d
0x140007516  call    RecursiveDeleteKey
0x14000751b  jmp     short loc_140007548
0x14000751d  mov     ecx, 4C7h
0x140007522  call    SaveErrorMessage
0x140007527  mov     ecx, ebx; Ix
0x140007529  call    _o___acrt_iob_func_0
0x14000752e  mov     rcx, rax
0x140007531  mov     edx, 20000h
0x140007536  call    ShowLastErrorEx
0x14000753b  xor     ebx, ebx
0x14000753d  jmp     short loc_14000754A
0x14000753f  lea     rcx, [rbp+57h+var_C0]
0x140007543  call    DeleteValues
0x140007548  mov     ebx, eax
0x14000754a  lea     rcx, [rbp+57h+var_C0]
0x14000754e  call    FreeGlobalData
0x140007553  xor     eax, eax
0x140007555  test    ebx, ebx
0x140007557  setnz   al
0x14000755a  jmp     short loc_140007582
0x14000755c  mov     ecx, 57h ; 'W'
0x140007561  call    SaveErrorMessage
0x140007566  mov     ecx, 2; Ix
0x14000756b  call    _o___acrt_iob_func_0
0x140007570  mov     rcx, rax
0x140007573  mov     edx, 20000h
0x140007578  call    ShowLastErrorEx
0x14000757d  mov     eax, 1
0x140007582  mov     rcx, [rbp+57h+var_20]
0x140007586  xor     rcx, rsp; StackCookie
0x140007589  call    __security_check_cookie
0x14000758e  mov     rbx, [rsp+0F0h+arg_10]
0x140007596  add     rsp, 0E0h
0x14000759d  pop     r14
0x14000759f  pop     rsi
0x1400075a0  pop     rbp
0x1400075a1  retn
```
