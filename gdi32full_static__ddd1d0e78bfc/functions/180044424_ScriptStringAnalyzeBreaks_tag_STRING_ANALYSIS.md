# ScriptStringAnalyzeBreaks(tag_STRING_ANALYSIS *)

- ea: `0x180044424`
- end: `0x1800446bb`
- name: `?ScriptStringAnalyzeBreaks@@YAJPEAUtag_STRING_ANALYSIS@@@Z`
- size: `663`
- prototype: `__int64 __fastcall(struct tag_STRING_ANALYSIS *)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18000e550`

## callees

- `0x18000d200`
- `0x180013ee0`
- `0x180022950`
- `0x180025f20`
- `0x180044424`
- `0x18004ab70`
- `0x18007bb10`
- `0x18007bb70`
- `0x18007bc70`
- `0x18007bce0`
- `0x18007bdc0`
- `0x18007bf60`
- `0x18007f800`
- `0x18009c350`
- `0x18009ccd0`
- `0x18009df20`
- `0x18009e190`
- `0x18009e4b0`
- `0x1800a8010`

## import_xrefs

- `TextShaping!ShapingGetCombiningOptions` at `0x18004465c`
- `TextShaping!ShapingGetCombiningOptions` at `0x18004465c`
- `TextShaping!ShapingGetBreakingProperties` at `0x1800445aa`
- `TextShaping!ShapingGetBreakingProperties` at `0x1800445aa`

## pseudocode

```c
__int64 __fastcall ScriptStringAnalyzeBreaks(struct tag_STRING_ANALYSIS *a1)
{
  int i; // ebx
  int v3; // eax
  int v4; // edi
  __int64 v5; // rcx
  int v6; // r14d
  __int64 v7; // rdx
  const wchar_t *v8; // r13
  __int64 v9; // rbx
  struct tag_SCRIPT_LOGATTR *v10; // r12
  int v11; // eax
  unsigned __int16 v12; // r8
  unsigned __int16 v13; // cx
  __int64 v14; // rcx
  int v15; // edx
  int BreakingProperties; // eax
  int v17; // ebx
  int v19; // [rsp+30h] [rbp-48h] BYREF
  void **v20; // [rsp+38h] [rbp-40h] BYREF
  int v21; // [rsp+40h] [rbp-38h]
  _DWORD v22[3]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v23; // [rsp+54h] [rbp-24h]
  unsigned int v24; // [rsp+5Ch] [rbp-1Ch]

  for ( i = 0; ; i = v4 )
  {
    v3 = *((_DWORD *)a1 + 100);
    v19 = i;
    if ( i >= v3 )
      return 0;
    v4 = i + 1;
    if ( i + 1 < v3 )
    {
      do
      {
        if ( (ShapingGetCombiningOptions(
                *((unsigned __int16 *)&ShlScriptSupport + 4 * (*(_WORD *)(*((_QWORD *)a1 + 13) + 8LL * i + 4) & 0x3FF)),
                *((unsigned __int16 *)&ShlScriptSupport + 4 * (*(_WORD *)(*((_QWORD *)a1 + 13) + 8LL * v4 + 4) & 0x3FF)))
            & 1) == 0 )
          break;
        ++v4;
      }
      while ( v4 < *((_DWORD *)a1 + 100) );
      i = v19;
    }
    v5 = *((_QWORD *)a1 + 13);
    v6 = *(_DWORD *)(v5 + 8LL * v4) - *(_DWORD *)(v5 + 8LL * i);
    if ( v6 < 0 )
      break;
    v7 = *(int *)(v5 + 8LL * i);
    v8 = (const wchar_t *)(*((_QWORD *)a1 + 6) + 2 * v7);
    if ( !v8
      || (v9 = v5 + 4 + 8LL * i) == 0
      || (v10 = (struct tag_SCRIPT_LOGATTR *)(v7 + *((_QWORD *)a1 + 18))) == 0
      || v6 >= 0x10000
      || (*(_WORD *)v9 & 0x3FFu) >= 0xE1 )
    {
      return (unsigned int)-2147024809;
    }
    v11 = UspAcquireTempAlloc(0xE1u);
    v12 = *(_WORD *)v9;
    v13 = *(_WORD *)v9;
    v19 = v11;
    v14 = v13 & 0x3FF;
    v15 = *((unsigned __int16 *)&ShlScriptSupport + 4 * v14);
    if ( (_WORD)v15 == 0xFFFF || (v12 & 0x3FF) == 0x1F || (v12 & 0x3FF) == 0x38 )
    {
      v17 = funcs_180044620[3 * v14](v8, v6, (const struct tag_SCRIPT_ANALYSIS *)v9, v10);
    }
    else
    {
      v22[2] = 1953261156;
      v20 = &CUspShapingClient::`vftable';
      v21 = 0;
      v23 = 0;
      v22[1] = 0;
      v24 = ((*(_WORD *)(v9 + 2) & 0x400 | 0x2000u) >> 7) | ((v12 & 0x400 | (v12 >> 1) & 0x1800u) >> 10);
      v22[0] = v15;
      BreakingProperties = ShapingGetBreakingProperties(&v20, v22, v8, (unsigned int)v6, v10);
      if ( BreakingProperties )
      {
        v20 = &CUspShapingClient::`vftable';
        if ( BreakingProperties == -2 )
          v17 = -2147024882;
        else
          v17 = -2147467259;
      }
      else
      {
        v17 = 0;
        v20 = &CUspShapingClient::`vftable';
      }
    }
    CTempMemory::~CTempMemory((CTempMemory *)&v19);
    if ( v17 < 0 )
      return (unsigned int)v17;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180044424  push    rbp
0x180044426  push    rbx
0x180044427  push    rsi
0x180044428  push    rdi
0x180044429  push    r12
0x18004442b  push    r13
0x18004442d  push    r14
0x18004442f  push    r15
0x180044431  mov     rbp, rsp
0x180044434  sub     rsp, 78h
0x180044438  mov     rax, cs:__security_cookie
0x18004443f  xor     rax, rsp
0x180044442  mov     [rbp+var_18], rax
0x180044446  mov     rsi, rcx
0x180044449  xor     ebx, ebx
0x18004444b  mov     eax, [rsi+190h]
0x180044451  lea     r10, __ImageBase
0x180044458  mov     [rbp+var_48], ebx
0x18004445b  mov     r12d, 1
0x180044461  mov     r9d, 3FFh
0x180044467  cmp     ebx, eax
0x180044469  jge     loc_1800445DF
0x18004446f  lea     edi, [rbx+1]
0x180044472  cmp     edi, eax
0x180044474  jl      loc_180044629
0x18004447a  mov     rcx, [rsi+68h]
0x18004447e  movsxd  rax, edi
0x180044481  movsxd  r8, ebx
0x180044484  mov     r14d, [rcx+rax*8]
0x180044488  sub     r14d, [rcx+r8*8]
0x18004448c  js      loc_18004468D
0x180044492  movsxd  rdx, dword ptr [rcx+r8*8]
0x180044496  mov     rax, [rsi+30h]
0x18004449a  lea     r13, [rax+rdx*2]
0x18004449e  test    r13, r13
0x1800444a1  jz      loc_1800445FF
0x1800444a7  lea     rbx, [rcx+4]
0x1800444ab  lea     rbx, [rbx+r8*8]
0x1800444af  test    rbx, rbx
0x1800444b2  jz      loc_1800445FF
0x1800444b8  mov     r12, [rsi+90h]
0x1800444bf  add     r12, rdx
0x1800444c2  jz      loc_1800445FF
0x1800444c8  cmp     r14d, 10000h
0x1800444cf  jge     loc_1800445FF
0x1800444d5  movzx   eax, word ptr [rbx]
0x1800444d8  mov     ecx, 0E1h; unsigned int
0x1800444dd  and     ax, r9w
0x1800444e1  cmp     ax, cx
0x1800444e4  jnb     loc_1800445FF
0x1800444ea  call    ?UspAcquireTempAlloc@@YAHK@Z; UspAcquireTempAlloc(ulong)
0x1800444ef  movzx   r8d, word ptr [rbx]
0x1800444f3  lea     r10, __ImageBase
0x1800444fa  mov     ecx, r8d
0x1800444fd  mov     [rbp+var_48], eax
0x180044500  mov     r9d, 3FFh
0x180044506  mov     r11d, 0FFFFh
0x18004450c  and     rcx, r9
0x18004450f  movzx   edx, ds:rva ?ShlScriptSupport@@3QBUSHAPING_LIBRARY_XREF@@B[r10+rcx*8]; SHAPING_LIBRARY_XREF const near * const ShlScriptSupport ...
0x180044518  cmp     dx, r11w
0x18004451c  jz      loc_180044608
0x180044522  movzx   eax, r8w
0x180044526  and     ax, r9w
0x18004452a  cmp     ax, 1Fh
0x18004452e  jz      loc_180044608
0x180044534  cmp     ax, 38h ; '8'
0x180044538  jz      loc_180044608
0x18004453e  lea     rax, ??_7CUspShapingClient@@6B@; const CUspShapingClient::`vftable'
0x180044545  mov     [rbp+var_28], 746C6664h
0x18004454c  mov     [rbp+var_40], rax
0x180044550  xor     eax, eax
0x180044552  mov     [rbp+var_38], eax
0x180044555  mov     [rbp+var_24], rax
0x180044559  mov     [rbp+var_2C], eax
0x18004455c  movzx   eax, r8w
0x180044560  lea     r8d, [r9+1]
0x180044564  mov     ecx, eax
0x180044566  mov     [rsp+78h+var_58], r12
0x18004456b  and     eax, r8d
0x18004456e  shr     ecx, 1
0x180044570  and     ecx, 1800h
0x180044576  mov     r9d, r14d
0x180044579  or      ecx, eax
0x18004457b  movzx   eax, word ptr [rbx+2]
0x18004457f  and     eax, r8d
0x180044582  shr     ecx, 0Ah
0x180044585  bts     eax, 0Dh
0x180044589  mov     r8, r13
0x18004458c  shr     eax, 7
0x18004458f  or      ecx, eax
0x180044591  mov     eax, 1
0x180044596  cmp     edx, r11d
0x180044599  mov     [rbp+var_1C], ecx
0x18004459c  lea     rcx, [rbp+var_40]
0x1800445a0  cmovz   edx, eax
0x1800445a3  mov     [rbp+var_30], edx
0x1800445a6  lea     rdx, [rbp+var_30]
0x1800445aa  call    cs:__imp_ShapingGetBreakingProperties
0x1800445b1  nop     dword ptr [rax+rax+00h]
0x1800445b6  test    eax, eax
0x1800445b8  jnz     loc_180044697
0x1800445be  lea     rax, ??_7CUspShapingClient@@6B@; const CUspShapingClient::`vftable'
0x1800445c5  xor     ebx, ebx
0x1800445c7  mov     [rbp+var_40], rax
0x1800445cb  lea     rcx, [rbp+var_48]; this
0x1800445cf  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x1800445d4  test    ebx, ebx
0x1800445d6  js      short loc_180044604
0x1800445d8  mov     ebx, edi
0x1800445da  jmp     loc_18004444B
0x1800445df  xor     eax, eax
0x1800445e1  mov     rcx, [rbp+var_18]
0x1800445e5  xor     rcx, rsp; StackCookie
0x1800445e8  call    __security_check_cookie
0x1800445ed  add     rsp, 78h
0x1800445f1  pop     r15
0x1800445f3  pop     r14
0x1800445f5  pop     r13
0x1800445f7  pop     r12
0x1800445f9  pop     rdi
0x1800445fa  pop     rsi
0x1800445fb  pop     rbx
0x1800445fc  pop     rbp
0x1800445fd  retn
0x1800445ff  mov     ebx, 80070057h
0x180044604  mov     eax, ebx
0x180044606  jmp     short loc_1800445E1
0x180044608  lea     rax, [rcx+rcx*2]
0x18004460c  mov     r9, r12; struct tag_SCRIPT_LOGATTR *
0x18004460f  mov     rax, ds:(funcs_180044620 - 180000000h)[r10+rax*8]
0x180044617  mov     r8, rbx; struct tag_SCRIPT_ANALYSIS *
0x18004461a  mov     edx, r14d; int
0x18004461d  mov     rcx, r13; wchar_t *
0x180044620  call    _guard_dispatch_icall$thunk$10345483385596137414; ThaiBreak(wchar_t const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180044625  mov     ebx, eax
0x180044627  jmp     short loc_1800445CB
0x180044629  movsxd  r14, ebx
0x18004462c  mov     ebx, 3FFh
0x180044631  mov     r8, [rsi+68h]
0x180044635  movsxd  rax, edi
0x180044638  movzx   ecx, word ptr [r8+rax*8+4]
0x18004463e  movzx   eax, word ptr [r8+r14*8+4]
0x180044644  and     rcx, rbx
0x180044647  and     rax, rbx
0x18004464a  movzx   edx, ds:rva ?ShlScriptSupport@@3QBUSHAPING_LIBRARY_XREF@@B[r10+rcx*8]; SHAPING_LIBRARY_XREF const near * const ShlScriptSupport ...
0x180044653  movzx   ecx, ds:rva ?ShlScriptSupport@@3QBUSHAPING_LIBRARY_XREF@@B[r10+rax*8]; SHAPING_LIBRARY_XREF const near * const ShlScriptSupport ...
0x18004465c  call    cs:__imp_ShapingGetCombiningOptions
0x180044663  nop     dword ptr [rax+rax+00h]
0x180044668  test    r12b, al
0x18004466b  jz      short loc_18004467F
0x18004466d  add     edi, r12d
0x180044670  lea     r10, __ImageBase
0x180044677  cmp     edi, [rsi+190h]
0x18004467d  jl      short loc_180044631
0x18004467f  mov     ebx, [rbp+var_48]
0x180044682  mov     r9d, 3FFh
0x180044688  jmp     loc_18004447A
0x18004468d  mov     eax, 80070057h
0x180044692  jmp     loc_1800445E1
0x180044697  cmp     eax, 0FFFFFFFEh
0x18004469a  lea     rax, ??_7CUspShapingClient@@6B@; const CUspShapingClient::`vftable'
0x1800446a1  mov     [rbp+var_40], rax
0x1800446a5  jnz     short loc_1800446B1
0x1800446a7  mov     ebx, 8007000Eh
0x1800446ac  jmp     loc_1800445CB
0x1800446b1  mov     ebx, 80004005h
0x1800446b6  jmp     loc_1800445CB
```
