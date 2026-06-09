# CCompiledInitString::GatherExtendedProperties(ushort * *)

- ea: `0x180025664`
- end: `0x180025893`
- name: `?GatherExtendedProperties@CCompiledInitString@@QEAAJPEAPEAG@Z`
- size: `559`
- prototype: `__int64 __fastcall(CCompiledInitString *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18005d070`

## callees

- `0x18000fbe0`
- `0x180013870`
- `0x180025664`
- `0x180029560`

## import_xrefs

- `msvcrt!iswspace` at `0x1800257b2`
- `msvcrt!iswspace` at `0x1800257b2`
- `MSDART!mpMalloc` at `0x180025786`
- `MSDART!mpMalloc` at `0x180025786`

## string_xrefs

- `0x18002569a`: `<CCompiledInitString::GatherExtendedProperties|OLEDB|ERR> `
- `0x18002583c`: `<CCompiledInitString::GatherExtendedProperties|OLEDB|ERR> `
- `0x1800256be`: `<CCompiledInitString::GatherExtendedProperties|Trace|HR> `
- `0x1800256ef`: `<CCompiledInitString::GatherExtendedProperties|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CCompiledInitString::GatherExtendedProperties(CCompiledInitString *this, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  unsigned int v7; // ecx
  unsigned __int16 *v8; // rbx
  __int64 v9; // rsi
  unsigned __int16 *v10; // rdi
  unsigned __int64 v11; // r13
  unsigned int v12; // eax
  wint_t *v13; // r12
  int v14; // r15d
  __int64 v15; // rax
  unsigned __int16 *v16; // rax
  __int64 v17; // [rsp+30h] [rbp-58h]
  unsigned __int64 v18[9]; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v19; // [rsp+98h] [rbp+10h]
  unsigned int v20; // [rsp+A0h] [rbp+18h]
  unsigned __int16 *v21; // [rsp+A8h] [rbp+20h] BYREF

  if ( !a2 )
  {
    v4 = -2147467261;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147467261, L"<CCompiledInitString::GatherExtendedProperties|OLEDB|ERR> ", 0x332u);
      if ( (bidGblFlags & 2) != 0 )
      {
        v5 = 837641;
        return (unsigned int)bidTraceHR(
                               off_1800C8430[0],
                               v5,
                               L"<CCompiledInitString::GatherExtendedProperties|Trace|HR> ",
                               v4);
      }
    }
    return v4;
  }
  *a2 = 0;
  if ( !*((_QWORD *)this + 3) )
  {
    if ( (bidGblFlags & 2) != 0 )
      return bidTraceHR(off_1800C8430[0], 842761, L"<CCompiledInitString::GatherExtendedProperties|Trace|HR> ", 0);
    else
      return 0;
  }
  v7 = *((_DWORD *)this + 5);
  v8 = 0;
  v9 = *((_QWORD *)this + 1);
  v10 = 0;
  v20 = v7;
  v11 = 0;
  v21 = 0;
  v12 = 0;
  v18[0] = 0;
  while ( 1 )
  {
    v19 = v12;
    if ( v12 >= v7 )
    {
      if ( v8 && *(v10 - 1) == 59 )
        *(v10 - 1) = 0;
      *a2 = v8;
      return 0;
    }
    if ( *(_DWORD *)(v9 + 48) == -1 && *(_DWORD *)(v9 + 52) == -1 )
      break;
LABEL_24:
    ++v12;
    v9 += 56;
  }
  v13 = *(wint_t **)v9;
  v14 = *(_DWORD *)(v9 + 8);
  if ( v8 )
  {
LABEL_20:
    while ( v14 )
    {
      if ( !iswspace(*v13) )
        break;
      ++v13;
      --v14;
    }
    LODWORD(v17) = v14;
    StringCchPrintfExW(v10, v11, &v21, v18, 0, L"%.*ls;", v17, v13);
    v12 = v19;
    v7 = v20;
    v10 = v21;
    v11 = v18[0];
    goto LABEL_24;
  }
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(*((_QWORD *)this + 3) + 2 * v15) );
  v11 = v15 + 2;
  v18[0] = v15 + 2;
  v16 = (unsigned __int16 *)mpMalloc(2 * (v15 + 2), 0);
  v8 = v16;
  if ( v16 )
  {
    v10 = v16;
    v21 = v16;
    *v16 = 0;
    goto LABEL_20;
  }
  v4 = -2147024882;
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(-2147024882, L"<CCompiledInitString::GatherExtendedProperties|OLEDB|ERR> ", 0x358u);
    if ( (bidGblFlags & 2) != 0 )
    {
      v5 = 876553;
      return (unsigned int)bidTraceHR(
                             off_1800C8430[0],
                             v5,
                             L"<CCompiledInitString::GatherExtendedProperties|Trace|HR> ",
                             v4);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180025664  mov     [rsp+arg_0], rbx
0x180025669  push    rbp
0x18002566a  push    rsi
0x18002566b  push    rdi
0x18002566c  push    r12
0x18002566e  push    r13
0x180025670  push    r14
0x180025672  push    r15
0x180025674  sub     rsp, 50h
0x180025678  mov     r14, rdx
0x18002567b  mov     rbp, rcx
0x18002567e  xor     edx, edx
0x180025680  test    r14, r14
0x180025683  jnz     short loc_1800256D6
0x180025685  mov     eax, cs:_bidGblFlags
0x18002568b  mov     ebx, 80004003h
0x180025690  test    al, 2
0x180025692  jz      short loc_1800256CF
0x180025694  mov     r8d, 332h; unsigned int
0x18002569a  lea     rdx, aCcompiledinits_3; "<CCompiledInitString::GatherExtendedPro"...
0x1800256a1  mov     ecx, ebx; int
0x1800256a3  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800256a8  mov     eax, cs:_bidGblFlags
0x1800256ae  test    al, 2
0x1800256b0  jz      short loc_1800256CF
0x1800256b2  mov     edx, 0CC809h
0x1800256b7  mov     rcx, cs:off_1800C8430; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800256be  lea     r8, aCcompiledinits_8; "<CCompiledInitString::GatherExtendedPro"...
0x1800256c5  mov     r9d, ebx
0x1800256c8  call    _bidTraceHR
0x1800256cd  mov     ebx, eax
0x1800256cf  mov     eax, ebx
0x1800256d1  jmp     loc_18002587B
0x1800256d6  mov     [r14], rdx
0x1800256d9  cmp     [rcx+18h], rdx
0x1800256dd  jnz     short loc_18002570F
0x1800256df  test    byte ptr cs:_bidGblFlags, 2
0x1800256e6  jz      short loc_180025708
0x1800256e8  mov     rcx, cs:off_1800C8430; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800256ef  lea     r8, aCcompiledinits_8; "<CCompiledInitString::GatherExtendedPro"...
0x1800256f6  xor     r9d, r9d
0x1800256f9  mov     edx, 0CDC09h
0x1800256fe  call    _bidTraceHR
0x180025703  jmp     loc_18002587B
0x180025708  mov     eax, edx
0x18002570a  jmp     loc_18002587B
0x18002570f  mov     ecx, [rcx+14h]
0x180025712  mov     rbx, rdx
0x180025715  mov     rsi, [rbp+8]
0x180025719  mov     rdi, rdx
0x18002571c  mov     [rsp+88h+arg_10], ecx
0x180025723  mov     r13, rdx
0x180025726  mov     [rsp+88h+arg_18], rdx
0x18002572e  mov     eax, edx
0x180025730  mov     [rsp+88h+var_48], rdx
0x180025735  mov     [rsp+88h+arg_8], eax
0x18002573c  cmp     eax, ecx
0x18002573e  jnb     loc_180025862
0x180025744  cmp     dword ptr [rsi+30h], 0FFFFFFFFh
0x180025748  jnz     loc_180025818
0x18002574e  cmp     dword ptr [rsi+34h], 0FFFFFFFFh
0x180025752  jnz     loc_180025818
0x180025758  mov     r12, [rsi]
0x18002575b  mov     r15d, [rsi+8]
0x18002575f  test    rbx, rbx
0x180025762  jnz     short loc_1800257A8
0x180025764  mov     rcx, [rbp+18h]
0x180025768  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002576c  inc     rax
0x18002576f  cmp     [rcx+rax*2], dx
0x180025773  jnz     short loc_18002576C
0x180025775  lea     r13, [rax+2]
0x180025779  lea     rcx, ds:0[r13*2]
0x180025781  mov     [rsp+88h+var_48], r13
0x180025786  call    cs:__imp_mpMalloc
0x18002578c  xor     edx, edx
0x18002578e  mov     rbx, rax
0x180025791  test    rax, rax
0x180025794  jz      loc_180025823
0x18002579a  mov     rdi, rax
0x18002579d  mov     [rsp+88h+arg_18], rax
0x1800257a5  mov     [rax], dx
0x1800257a8  test    r15d, r15d
0x1800257ab  jz      short loc_1800257C8
0x1800257ad  movzx   ecx, word ptr [r12]; C
0x1800257b2  call    cs:__imp_iswspace
0x1800257b8  xor     edx, edx
0x1800257ba  test    eax, eax
0x1800257bc  jz      short loc_1800257C8
0x1800257be  add     r12, 2
0x1800257c2  add     r15d, 0FFFFFFFFh
0x1800257c6  jnz     short loc_1800257AD
0x1800257c8  mov     [rsp+88h+var_50], r12
0x1800257cd  lea     rax, aLs; "%.*ls;"
0x1800257d4  mov     dword ptr [rsp+88h+var_58], r15d
0x1800257d9  lea     r9, [rsp+88h+var_48]; unsigned __int64 *
0x1800257de  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x1800257e3  lea     r8, [rsp+88h+arg_18]; unsigned __int16 **
0x1800257eb  mov     qword ptr [rsp+88h+var_68], rdx; unsigned int
0x1800257f0  mov     rcx, rdi; pszDest
0x1800257f3  mov     rdx, r13; unsigned __int64
0x1800257f6  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800257fb  mov     eax, [rsp+88h+arg_8]
0x180025802  xor     edx, edx
0x180025804  mov     ecx, [rsp+88h+arg_10]
0x18002580b  mov     rdi, [rsp+88h+arg_18]
0x180025813  mov     r13, [rsp+88h+var_48]
0x180025818  inc     eax
0x18002581a  add     rsi, 38h ; '8'
0x18002581e  jmp     loc_180025735
0x180025823  mov     eax, cs:_bidGblFlags
0x180025829  mov     ebx, 8007000Eh
0x18002582e  test    al, 2
0x180025830  jz      loc_1800256CF
0x180025836  mov     r8d, 358h; unsigned int
0x18002583c  lea     rdx, aCcompiledinits_3; "<CCompiledInitString::GatherExtendedPro"...
0x180025843  mov     ecx, ebx; int
0x180025845  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002584a  mov     eax, cs:_bidGblFlags
0x180025850  test    al, 2
0x180025852  jz      loc_1800256CF
0x180025858  mov     edx, 0D6009h
0x18002585d  jmp     loc_1800256B7
0x180025862  test    rbx, rbx
0x180025865  jz      short loc_180025876
0x180025867  mov     eax, 3Bh ; ';'
0x18002586c  cmp     ax, [rdi-2]
0x180025870  jnz     short loc_180025876
0x180025872  mov     [rdi-2], dx
0x180025876  mov     [r14], rbx
0x180025879  xor     eax, eax
0x18002587b  mov     rbx, [rsp+88h+arg_0]
0x180025883  add     rsp, 50h
0x180025887  pop     r15
0x180025889  pop     r14
0x18002588b  pop     r13
0x18002588d  pop     r12
0x18002588f  pop     rdi
0x180025890  pop     rsi
0x180025891  pop     rbp
0x180025892  retn
```
