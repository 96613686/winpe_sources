# SymCompareInlineTrace

- ea: `0x1801a51c0`
- end: `0x1801a5729`
- name: `SymCompareInlineTrace`
- size: `1385`
- prototype: `DWORD __stdcall(HANDLE hProcess, DWORD64 Address1, DWORD InlineContext1, DWORD64 RetAddress1, DWORD64 Address2, DWORD64 RetAddress2)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000a820`
- `0x18000aeec`
- `0x18000af48`
- `0x18000dfac`
- `0x180021374`
- `0x18018ce90`
- `0x180191ed0`
- `0x1801a51c0`

## string_xrefs

- `0x1801a5396`: `SymCompareInlineTrace(%d,%I64x,%x,%I64x,%s)\n`
- `0x1801a5526`: `SymCompareInlineTrace(%d)(%I64x,%x,%s,%I64x)(%I64x,%s,%I64x)\n`
- `0x1801a558e`: `SymCompareInlineTrace(%d)(%I64x,%x,%I64x)(%I64x,%I64x)\n`
- `0x1801a55c4`: `SymCompareInlineTrace_Addr1(ERROR_MOD_LOAD_FAIL,%I64x,%s)\n`
- `0x1801a5600`: `SymCompareInlineTrace_RetAddr1(ERROR_MOD_LOAD_FAIL,%I64x,%s)\n`
- `0x1801a5675`: `SymCompareInlineTrace_RetAddr1(ERROR_MOD_LOAD_FAIL,%I64x,%s)\n`
- `0x1801a5639`: `SymCompareInlineTrace_Addr2(ERROR_MOD_LOAD_FAIL,%I64x,%s)\n`
- `0x1801a56bd`: `SymCompareInlineTrace(ERROR_INVALID_PROCESS,%I64x,%x,%I64x,%I64x,%I64x)\n`
- `0x1801a5702`: `SymCompareInlineTrace(Exception(%x),%I64x,%x,%I64x)\n`

## pseudocode

```c
DWORD __stdcall SymCompareInlineTrace(
        HANDLE hProcess,
        DWORD64 Address1,
        DWORD InlineContext1,
        DWORD64 RetAddress1,
        DWORD64 Address2,
        DWORD64 RetAddress2)
{
  DWORD v10; // ebx
  int v11; // r14d
  struct _PROCESS_ENTRY *ProcessEntry; // rax
  struct _PROCESS_ENTRY *v13; // r15
  struct _MODULE_ENTRY *ModuleForPC; // rax
  struct _MODULE_ENTRY *v15; // rdi
  struct _MODULE_ENTRY *v16; // rax
  struct _MODULE_ENTRY *v17; // rax
  struct _MODULE_ENTRY *v18; // rsi
  struct _MODULE_ENTRY *v19; // rax
  DWORD64 v20; // rdx
  __int64 v21; // r9
  __int64 v22; // r9
  bool v24[8]; // [rsp+20h] [rbp-98h]
  bool v25[8]; // [rsp+20h] [rbp-98h]
  __int64 v26; // [rsp+50h] [rbp-68h] BYREF
  unsigned int v27; // [rsp+58h] [rbp-60h] BYREF
  int v28; // [rsp+5Ch] [rbp-5Ch]
  int v29; // [rsp+60h] [rbp-58h]
  int Symbols; // [rsp+64h] [rbp-54h]
  struct _MODULE_ENTRY *v31; // [rsp+68h] [rbp-50h]
  struct _MODULE_ENTRY *v32; // [rsp+70h] [rbp-48h]

  v10 = 0;
  v11 = 1;
  Symbols = 1;
  v28 = 1;
  v29 = 1;
  HIDWORD(v26) = 0;
  v27 = 0;
  ProcessEntry = FindProcessEntry(hProcess);
  v13 = ProcessEntry;
  if ( !ProcessEntry )
  {
    if ( g_InlineDebugMask && (unsigned int)spew() )
      _pwprint(
        0,
        L"SymCompareInlineTrace(ERROR_INVALID_PROCESS,%I64x,%x,%I64x,%I64x,%I64x)\n",
        Address1,
        InlineContext1,
        RetAddress1,
        Address2,
        RetAddress2);
    return v10;
  }
  ModuleForPC = GetModuleForPC(ProcessEntry, Address1, 0, 1, 1, 1);
  v15 = ModuleForPC;
  if ( ModuleForPC )
    Symbols = LoadSymbols(hProcess, ModuleForPC, 0);
  v16 = GetModuleForPC(v13, RetAddress1, 0, 1, 1, 1);
  v31 = v16;
  if ( v16 )
    v28 = LoadSymbols(hProcess, v16, 0);
  v17 = GetModuleForPC(v13, Address2, 0, 1, 1, 1);
  v18 = v17;
  if ( v17 )
    v29 = LoadSymbols(hProcess, v17, 0);
  v19 = GetModuleForPC(v13, RetAddress2, 0, 1, 1, 1);
  v32 = v19;
  if ( v19 )
  {
    v11 = LoadSymbols(hProcess, v19, 0);
    v19 = v32;
  }
  if ( !Symbols )
  {
    if ( v15 && g_InlineDebugMask && (unsigned int)spew() )
      _pwprint(v13, L"SymCompareInlineTrace_Addr1(ERROR_MOD_LOAD_FAIL,%I64x,%s)\n", Address1, (char *)v15 + 46);
    goto LABEL_51;
  }
  if ( !v28 || !v29 || !v11 )
  {
LABEL_51:
    if ( !v28 && v31 && g_InlineDebugMask && (unsigned int)spew() )
      _pwprint(v13, L"SymCompareInlineTrace_RetAddr1(ERROR_MOD_LOAD_FAIL,%I64x,%s)\n", RetAddress1, v21 + 46);
    if ( !v29 && v18 && g_InlineDebugMask && (unsigned int)spew() )
      _pwprint(v13, L"SymCompareInlineTrace_Addr2(ERROR_MOD_LOAD_FAIL,%I64x,%s)\n", Address2, (char *)v18 + 46);
    if ( !v11 && v32 && g_InlineDebugMask && (unsigned int)spew() )
      _pwprint(v13, L"SymCompareInlineTrace_RetAddr1(ERROR_MOD_LOAD_FAIL,%I64x,%s)\n", RetAddress2, v22 + 46);
    return v10;
  }
  if ( v15 == v18 && v15 )
  {
    v10 = diaCompareInlineTrace(v13, v15, Address1, InlineContext1, Address2);
    if ( g_InlineDebugMask && (unsigned int)spew() )
    {
      *(_DWORD *)v25 = InlineContext1;
      _pwprint(
        v13,
        L"SymCompareInlineTrace(%d,%I64x,%x,%I64x,%s)\n",
        v10,
        Address1,
        *(_QWORD *)v25,
        Address2,
        (char *)v15 + 46);
    }
    if ( v10 == 5 )
    {
      if ( v15 != v32 )
      {
        if ( v31 != v18 || !(unsigned int)diaGetSymbolIndexId(v18, RetAddress1, (unsigned int *)&v26 + 1) )
          return v10;
        v20 = Address2;
        goto LABEL_24;
      }
      goto LABEL_30;
    }
  }
  else
  {
    if ( v15 == v19 && v15 )
    {
      v10 = 5;
LABEL_30:
      if ( (unsigned int)diaGetSymbolIndexId(v15, Address1, (unsigned int *)&v26 + 1)
        && (unsigned int)diaGetSymbolIndexId(v15, RetAddress2, &v27)
        && HIDWORD(v26) == v27 )
      {
        return 2;
      }
      return v10;
    }
    if ( v31 == v18 && v18 )
    {
      v10 = 5;
      if ( !(unsigned int)diaGetSymbolIndexId(v18, RetAddress1, (unsigned int *)&v26 + 1) )
        return v10;
      v20 = Address2;
LABEL_24:
      if ( (unsigned int)diaGetSymbolIndexId(v18, v20, &v27) && HIDWORD(v26) == v27 )
        return 3;
      return v10;
    }
    v10 = 5;
    LODWORD(v26) = 5;
    if ( v15 && v18 )
    {
      if ( g_InlineDebugMask && (unsigned int)spew() )
      {
        *(_DWORD *)v24 = InlineContext1;
        _pwprint(
          v13,
          L"SymCompareInlineTrace(%d)(%I64x,%x,%s,%I64x)(%I64x,%s,%I64x)\n",
          5,
          Address1,
          *(_QWORD *)v24,
          (char *)v15 + 46,
          RetAddress1,
          Address2,
          (char *)v18 + 46,
          RetAddress2,
          v26);
      }
    }
    else if ( g_InlineDebugMask && (unsigned int)spew() )
    {
      *(_DWORD *)v24 = InlineContext1;
      _pwprint(
        v13,
        L"SymCompareInlineTrace(%d)(%I64x,%x,%I64x)(%I64x,%I64x)\n",
        5,
        Address1,
        *(_QWORD *)v24,
        RetAddress1,
        Address2,
        RetAddress2);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1801a51c0  mov     rax, rsp
0x1801a51c3  mov     [rax+20h], r9
0x1801a51c7  mov     [rax+18h], r8d
0x1801a51cb  mov     [rax+10h], rdx
0x1801a51cf  push    rbx
0x1801a51d0  push    rsi
0x1801a51d1  push    rdi
0x1801a51d2  push    r12
0x1801a51d4  push    r13
0x1801a51d6  push    r14
0x1801a51d8  push    r15
0x1801a51da  sub     rsp, 80h
0x1801a51e1  mov     rsi, r9
0x1801a51e4  mov     edi, r8d
0x1801a51e7  mov     r12, rdx
0x1801a51ea  mov     r13, rcx
0x1801a51ed  xor     ebx, ebx
0x1801a51ef  mov     [rax-68h], ebx
0x1801a51f2  lea     r14d, [rbx+1]
0x1801a51f6  mov     [rax-54h], r14d
0x1801a51fa  mov     [rax-5Ch], r14d
0x1801a51fe  mov     [rax-58h], r14d
0x1801a5202  mov     [rax-64h], ebx
0x1801a5205  mov     [rax-60h], ebx
0x1801a5208  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x1801a520d  mov     r15, rax
0x1801a5210  test    rax, rax
0x1801a5213  jz      loc_1801A5686
0x1801a5219  mov     [rsp+0B8h+var_90], r14b; bool
0x1801a521e  mov     [rsp+0B8h+var_98], r14b; bool
0x1801a5223  mov     r9b, r14b; bool
0x1801a5226  xor     r8d, r8d; bool
0x1801a5229  mov     rdx, r12; unsigned __int64
0x1801a522c  mov     rcx, rax; struct _PROCESS_ENTRY *
0x1801a522f  call    ?GetModuleForPC@@YAPEAU_MODULE_ENTRY@@PEAU_PROCESS_ENTRY@@_K_N222@Z; GetModuleForPC(_PROCESS_ENTRY *,unsigned __int64,bool,bool,bool,bool)
0x1801a5234  mov     rdi, rax
0x1801a5237  test    rax, rax
0x1801a523a  jz      short loc_1801A524E
0x1801a523c  xor     r8d, r8d; unsigned int
0x1801a523f  mov     rdx, rax; struct _MODULE_ENTRY *
0x1801a5242  mov     rcx, r13; void *
0x1801a5245  call    ?LoadSymbols@@YAHPEAXPEAU_MODULE_ENTRY@@K@Z; LoadSymbols(void *,_MODULE_ENTRY *,ulong)
0x1801a524a  mov     [rsp+0B8h+var_54], eax
0x1801a524e  mov     [rsp+0B8h+var_90], r14b; bool
0x1801a5253  mov     [rsp+0B8h+var_98], r14b; bool
0x1801a5258  mov     r9b, r14b; bool
0x1801a525b  xor     r8d, r8d; bool
0x1801a525e  mov     rdx, rsi; unsigned __int64
0x1801a5261  mov     rcx, r15; struct _PROCESS_ENTRY *
0x1801a5264  call    ?GetModuleForPC@@YAPEAU_MODULE_ENTRY@@PEAU_PROCESS_ENTRY@@_K_N222@Z; GetModuleForPC(_PROCESS_ENTRY *,unsigned __int64,bool,bool,bool,bool)
0x1801a5269  mov     [rsp+0B8h+var_50], rax
0x1801a526e  test    rax, rax
0x1801a5271  jz      short loc_1801A5285
0x1801a5273  xor     r8d, r8d; unsigned int
0x1801a5276  mov     rdx, rax; struct _MODULE_ENTRY *
0x1801a5279  mov     rcx, r13; void *
0x1801a527c  call    ?LoadSymbols@@YAHPEAXPEAU_MODULE_ENTRY@@K@Z; LoadSymbols(void *,_MODULE_ENTRY *,ulong)
0x1801a5281  mov     [rsp+0B8h+var_5C], eax
0x1801a5285  mov     [rsp+0B8h+var_90], r14b; bool
0x1801a528a  mov     [rsp+0B8h+var_98], r14b; bool
0x1801a528f  mov     r9b, r14b; bool
0x1801a5292  xor     r8d, r8d; bool
0x1801a5295  mov     rdx, [rsp+0B8h+Address2]; unsigned __int64
0x1801a529d  mov     rcx, r15; struct _PROCESS_ENTRY *
0x1801a52a0  call    ?GetModuleForPC@@YAPEAU_MODULE_ENTRY@@PEAU_PROCESS_ENTRY@@_K_N222@Z; GetModuleForPC(_PROCESS_ENTRY *,unsigned __int64,bool,bool,bool,bool)
0x1801a52a5  mov     rsi, rax
0x1801a52a8  test    rax, rax
0x1801a52ab  jz      short loc_1801A52BF
0x1801a52ad  xor     r8d, r8d; unsigned int
0x1801a52b0  mov     rdx, rax; struct _MODULE_ENTRY *
0x1801a52b3  mov     rcx, r13; void *
0x1801a52b6  call    ?LoadSymbols@@YAHPEAXPEAU_MODULE_ENTRY@@K@Z; LoadSymbols(void *,_MODULE_ENTRY *,ulong)
0x1801a52bb  mov     [rsp+0B8h+var_58], eax
0x1801a52bf  mov     [rsp+0B8h+var_90], r14b; bool
0x1801a52c4  mov     [rsp+0B8h+var_98], r14b; bool
0x1801a52c9  mov     r9b, r14b; bool
0x1801a52cc  xor     r8d, r8d; bool
0x1801a52cf  mov     rdx, [rsp+0B8h+RetAddress2]; unsigned __int64
0x1801a52d7  mov     rcx, r15; struct _PROCESS_ENTRY *
0x1801a52da  call    ?GetModuleForPC@@YAPEAU_MODULE_ENTRY@@PEAU_PROCESS_ENTRY@@_K_N222@Z; GetModuleForPC(_PROCESS_ENTRY *,unsigned __int64,bool,bool,bool,bool)
0x1801a52df  mov     [rsp+0B8h+var_48], rax
0x1801a52e4  test    rax, rax
0x1801a52e7  jz      short loc_1801A52FF
0x1801a52e9  xor     r8d, r8d; unsigned int
0x1801a52ec  mov     rdx, rax; struct _MODULE_ENTRY *
0x1801a52ef  mov     rcx, r13; void *
0x1801a52f2  call    ?LoadSymbols@@YAHPEAXPEAU_MODULE_ENTRY@@K@Z; LoadSymbols(void *,_MODULE_ENTRY *,ulong)
0x1801a52f7  mov     r14d, eax
0x1801a52fa  mov     rax, [rsp+0B8h+var_48]
0x1801a52ff  mov     ecx, [rsp+0B8h+var_54]
0x1801a5303  mov     r13d, [rsp+0B8h+var_5C]
0x1801a5308  test    ecx, ecx
0x1801a530a  jz      loc_1801A55A6
0x1801a5310  test    r13d, r13d
0x1801a5313  jz      loc_1801A55A2
0x1801a5319  cmp     [rsp+0B8h+var_58], 0
0x1801a531e  jz      loc_1801A55A2
0x1801a5324  test    r14d, r14d
0x1801a5327  jz      loc_1801A55A2
0x1801a532d  cmp     rdi, rsi
0x1801a5330  jnz     loc_1801A5411
0x1801a5336  test    rdi, rdi
0x1801a5339  jz      loc_1801A5411
0x1801a533f  mov     r14, [rsp+0B8h+Address2]
0x1801a5347  mov     qword ptr [rsp+0B8h+var_98], r14; unsigned __int64
0x1801a534c  mov     r13d, [rsp+0B8h+arg_10]
0x1801a5354  mov     r9d, r13d; unsigned int
0x1801a5357  mov     r8, r12; unsigned __int64
0x1801a535a  mov     rdx, rdi; struct _MODULE_ENTRY *
0x1801a535d  mov     rcx, r15; struct _PROCESS_ENTRY *
0x1801a5360  call    ?diaCompareInlineTrace@@YAKPEAU_PROCESS_ENTRY@@PEAU_MODULE_ENTRY@@_KK2@Z; diaCompareInlineTrace(_PROCESS_ENTRY *,_MODULE_ENTRY *,unsigned __int64,ulong,unsigned __int64)
0x1801a5365  mov     ebx, eax
0x1801a5367  mov     [rsp+0B8h+var_68], eax
0x1801a536b  cmp     cs:g_InlineDebugMask, 0
0x1801a5372  jz      short loc_1801A53A5
0x1801a5374  call    ?spew@@YAHXZ; spew(void)
0x1801a5379  test    eax, eax
0x1801a537b  jz      short loc_1801A53A5
0x1801a537d  lea     rcx, [rdi+2Eh]
0x1801a5381  mov     [rsp+0B8h+var_88], rcx
0x1801a5386  mov     qword ptr [rsp+0B8h+var_90], r14
0x1801a538b  mov     dword ptr [rsp+0B8h+var_98], r13d
0x1801a5390  mov     r9, r12
0x1801a5393  mov     r8d, ebx
0x1801a5396  lea     rdx, aSymcompareinli_3; "SymCompareInlineTrace(%d,%I64x,%x,%I64x"...
0x1801a539d  mov     rcx, r15; struct _PROCESS_ENTRY *
0x1801a53a0  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a53a5  cmp     ebx, 5
0x1801a53a8  jnz     loc_1801A56CB
0x1801a53ae  cmp     rdi, [rsp+0B8h+var_48]
0x1801a53b3  jz      short loc_1801A5424
0x1801a53b5  cmp     [rsp+0B8h+var_50], rsi
0x1801a53ba  jnz     loc_1801A56CB
0x1801a53c0  lea     r8, [rsp+0B8h+var_64]; unsigned int *
0x1801a53c5  mov     rdx, [rsp+0B8h+arg_18]; unsigned __int64
0x1801a53cd  mov     rcx, rsi; struct _MODULE_ENTRY *
0x1801a53d0  call    ?diaGetSymbolIndexId@@YAHPEAU_MODULE_ENTRY@@_KPEAK@Z; diaGetSymbolIndexId(_MODULE_ENTRY *,unsigned __int64,ulong *)
0x1801a53d5  test    eax, eax
0x1801a53d7  jz      loc_1801A56CB
0x1801a53dd  mov     rdx, r14; unsigned __int64
0x1801a53e0  lea     r8, [rsp+0B8h+var_60]; unsigned int *
0x1801a53e5  mov     rcx, rsi; struct _MODULE_ENTRY *
0x1801a53e8  call    ?diaGetSymbolIndexId@@YAHPEAU_MODULE_ENTRY@@_KPEAK@Z; diaGetSymbolIndexId(_MODULE_ENTRY *,unsigned __int64,ulong *)
0x1801a53ed  test    eax, eax
0x1801a53ef  jz      loc_1801A56CB
0x1801a53f5  mov     eax, [rsp+0B8h+var_64]
0x1801a53f9  cmp     eax, [rsp+0B8h+var_60]
0x1801a53fd  jnz     loc_1801A56CB
0x1801a5403  mov     ebx, 3
0x1801a5408  mov     [rsp+0B8h+var_68], ebx
0x1801a540c  jmp     loc_1801A56CB
0x1801a5411  cmp     rdi, rax
0x1801a5414  jnz     short loc_1801A546E
0x1801a5416  test    rdi, rdi
0x1801a5419  jz      short loc_1801A546E
0x1801a541b  mov     ebx, 5
0x1801a5420  mov     [rsp+0B8h+var_68], ebx
0x1801a5424  lea     r8, [rsp+0B8h+var_64]; unsigned int *
0x1801a5429  mov     rdx, r12; unsigned __int64
0x1801a542c  mov     rcx, rdi; struct _MODULE_ENTRY *
0x1801a542f  call    ?diaGetSymbolIndexId@@YAHPEAU_MODULE_ENTRY@@_KPEAK@Z; diaGetSymbolIndexId(_MODULE_ENTRY *,unsigned __int64,ulong *)
0x1801a5434  test    eax, eax
0x1801a5436  jz      loc_1801A56CB
0x1801a543c  lea     r8, [rsp+0B8h+var_60]; unsigned int *
0x1801a5441  mov     rdx, [rsp+0B8h+RetAddress2]; unsigned __int64
0x1801a5449  mov     rcx, rdi; struct _MODULE_ENTRY *
0x1801a544c  call    ?diaGetSymbolIndexId@@YAHPEAU_MODULE_ENTRY@@_KPEAK@Z; diaGetSymbolIndexId(_MODULE_ENTRY *,unsigned __int64,ulong *)
0x1801a5451  test    eax, eax
0x1801a5453  jz      loc_1801A56CB
0x1801a5459  mov     eax, [rsp+0B8h+var_64]
0x1801a545d  cmp     eax, [rsp+0B8h+var_60]
0x1801a5461  jnz     loc_1801A56CB
0x1801a5467  mov     ebx, 2
0x1801a546c  jmp     short loc_1801A5408
0x1801a546e  cmp     [rsp+0B8h+var_50], rsi
0x1801a5473  jnz     short loc_1801A54AD
0x1801a5475  test    rsi, rsi
0x1801a5478  jz      short loc_1801A54AD
0x1801a547a  mov     ebx, 5
0x1801a547f  mov     [rsp+0B8h+var_68], ebx
0x1801a5483  lea     r8, [rsp+0B8h+var_64]; unsigned int *
0x1801a5488  mov     rdx, [rsp+0B8h+arg_18]; unsigned __int64
0x1801a5490  mov     rcx, rsi; struct _MODULE_ENTRY *
0x1801a5493  call    ?diaGetSymbolIndexId@@YAHPEAU_MODULE_ENTRY@@_KPEAK@Z; diaGetSymbolIndexId(_MODULE_ENTRY *,unsigned __int64,ulong *)
0x1801a5498  test    eax, eax
0x1801a549a  jz      loc_1801A56CB
0x1801a54a0  mov     rdx, [rsp+0B8h+Address2]
0x1801a54a8  jmp     loc_1801A53E0
0x1801a54ad  mov     ebx, 5
0x1801a54b2  mov     [rsp+0B8h+var_68], ebx
0x1801a54b6  test    rdi, rdi
0x1801a54b9  jz      short loc_1801A553A
0x1801a54bb  test    rsi, rsi
0x1801a54be  jz      short loc_1801A553A
0x1801a54c0  cmp     cs:g_InlineDebugMask, 0
0x1801a54c7  jz      loc_1801A56CB
0x1801a54cd  call    ?spew@@YAHXZ; spew(void)
0x1801a54d2  test    eax, eax
0x1801a54d4  jz      loc_1801A56CB
0x1801a54da  lea     rax, [rsi+2Eh]
0x1801a54de  lea     rcx, [rdi+2Eh]
0x1801a54e2  mov     rdx, [rsp+0B8h+RetAddress2]
0x1801a54ea  mov     [rsp+0B8h+var_70], rdx
0x1801a54ef  mov     [rsp+0B8h+var_78], rax
0x1801a54f4  mov     rax, [rsp+0B8h+Address2]
0x1801a54fc  mov     [rsp+0B8h+var_80], rax
0x1801a5501  mov     rax, [rsp+0B8h+arg_18]
0x1801a5509  mov     [rsp+0B8h+var_88], rax
0x1801a550e  mov     qword ptr [rsp+0B8h+var_90], rcx
0x1801a5513  mov     r13d, [rsp+0B8h+arg_10]
0x1801a551b  mov     dword ptr [rsp+0B8h+var_98], r13d
0x1801a5520  mov     r9, r12
0x1801a5523  mov     r8d, ebx
0x1801a5526  lea     rdx, aSymcompareinli_2; "SymCompareInlineTrace(%d)(%I64x,%x,%s,%"...
0x1801a552d  mov     rcx, r15; struct _PROCESS_ENTRY *
0x1801a5530  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a5535  jmp     loc_1801A56CB
0x1801a553a  cmp     cs:g_InlineDebugMask, 0
0x1801a5541  jz      loc_1801A56CB
0x1801a5547  call    ?spew@@YAHXZ; spew(void)
0x1801a554c  test    eax, eax
0x1801a554e  jz      loc_1801A56CB
0x1801a5554  mov     rax, [rsp+0B8h+RetAddress2]
0x1801a555c  mov     [rsp+0B8h+var_80], rax
0x1801a5561  mov     rax, [rsp+0B8h+Address2]
0x1801a5569  mov     [rsp+0B8h+var_88], rax
0x1801a556e  mov     rax, [rsp+0B8h+arg_18]
0x1801a5576  mov     qword ptr [rsp+0B8h+var_90], rax
0x1801a557b  mov     r13d, [rsp+0B8h+arg_10]
0x1801a5583  mov     dword ptr [rsp+0B8h+var_98], r13d
0x1801a5588  mov     r9, r12
0x1801a558b  mov     r8d, ebx
0x1801a558e  lea     rdx, aSymcompareinli_5; "SymCompareInlineTrace(%d)(%I64x,%x,%I64"...
0x1801a5595  mov     rcx, r15; struct _PROCESS_ENTRY *
0x1801a5598  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a559d  jmp     loc_1801A56CB
0x1801a55a2  test    ecx, ecx
0x1801a55a4  jnz     short loc_1801A55D3
0x1801a55a6  test    rdi, rdi
0x1801a55a9  jz      short loc_1801A55D3
0x1801a55ab  cmp     cs:g_InlineDebugMask, 0
0x1801a55b2  jz      short loc_1801A55D3
0x1801a55b4  call    ?spew@@YAHXZ; spew(void)
0x1801a55b9  test    eax, eax
0x1801a55bb  jz      short loc_1801A55D3
0x1801a55bd  lea     r9, [rdi+2Eh]
0x1801a55c1  mov     r8, r12
0x1801a55c4  lea     rdx, aSymcompareinli_0; "SymCompareInlineTrace_Addr1(ERROR_MOD_L"...
0x1801a55cb  mov     rcx, r15; struct _PROCESS_ENTRY *
0x1801a55ce  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a55d3  test    r13d, r13d
0x1801a55d6  jnz     short loc_1801A560F
0x1801a55d8  mov     r9, [rsp+0B8h+var_50]
0x1801a55dd  test    r9, r9
0x1801a55e0  jz      short loc_1801A560F
0x1801a55e2  cmp     cs:g_InlineDebugMask, r13d
0x1801a55e9  jz      short loc_1801A560F
0x1801a55eb  call    ?spew@@YAHXZ; spew(void)
0x1801a55f0  test    eax, eax
0x1801a55f2  jz      short loc_1801A560F
0x1801a55f4  add     r9, 2Eh ; '.'
0x1801a55f8  mov     r8, [rsp+0B8h+arg_18]
0x1801a5600  lea     rdx, aSymcompareinli_7; "SymCompareInlineTrace_RetAddr1(ERROR_MO"...
0x1801a5607  mov     rcx, r15; struct _PROCESS_ENTRY *
0x1801a560a  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a560f  cmp     [rsp+0B8h+var_58], 0
0x1801a5614  jnz     short loc_1801A5648
0x1801a5616  test    rsi, rsi
0x1801a5619  jz      short loc_1801A5648
0x1801a561b  cmp     cs:g_InlineDebugMask, 0
0x1801a5622  jz      short loc_1801A5648
0x1801a5624  call    ?spew@@YAHXZ; spew(void)
0x1801a5629  test    eax, eax
0x1801a562b  jz      short loc_1801A5648
0x1801a562d  lea     r9, [rsi+2Eh]
0x1801a5631  mov     r8, [rsp+0B8h+Address2]
0x1801a5639  lea     rdx, aSymcompareinli_4; "SymCompareInlineTrace_Addr2(ERROR_MOD_L"...
0x1801a5640  mov     rcx, r15; struct _PROCESS_ENTRY *
0x1801a5643  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a5648  test    r14d, r14d
0x1801a564b  jnz     short loc_1801A56CB
0x1801a564d  mov     r9, [rsp+0B8h+var_48]
0x1801a5652  test    r9, r9
0x1801a5655  jz      short loc_1801A56CB
0x1801a5657  cmp     cs:g_InlineDebugMask, r14d
0x1801a565e  jz      short loc_1801A56CB
0x1801a5660  call    ?spew@@YAHXZ; spew(void)
0x1801a5665  test    eax, eax
0x1801a5667  jz      short loc_1801A56CB
0x1801a5669  add     r9, 2Eh ; '.'
0x1801a566d  mov     r8, [rsp+0B8h+RetAddress2]
0x1801a5675  lea     rdx, aSymcompareinli_7; "SymCompareInlineTrace_RetAddr1(ERROR_MO"...
0x1801a567c  mov     rcx, r15; struct _PROCESS_ENTRY *
0x1801a567f  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a5684  jmp     short loc_1801A56CB
0x1801a5686  cmp     cs:g_InlineDebugMask, 0
0x1801a568d  jz      short loc_1801A56CB
0x1801a568f  call    ?spew@@YAHXZ; spew(void)
0x1801a5694  test    eax, eax
0x1801a5696  jz      short loc_1801A56CB
  ... truncated ...
```
