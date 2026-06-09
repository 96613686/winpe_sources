# Loader_RxC_Invoke_SelectObject

- ea: `0x180003440`
- end: `0x1800037bf`
- name: `Loader_RxC_Invoke_SelectObject`
- size: `895`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001b44`
- `0x180003440`
- `0x180006ef8`
- `0x180007c80`
- `0x180008ea0`
- `0x180008f20`
- `0x180032a70`
- `0x180033250`
- `0x180033310`
- `0x1800374cc`
- `0x18003b7c8`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000353e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000353e`

## string_xrefs

- `0x18000352e`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall Loader_RxC_Invoke_SelectObject(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        _BYTE *a7)
{
  __int64 v7; // rsi
  __int64 v9; // rbx
  __int64 *v10; // r14
  const wchar_t *v11; // rcx
  unsigned int v12; // edi
  __int64 result; // rax
  _BYTE *v14; // rax
  void (__fastcall **v15)(__int64, __int128 *); // rax
  int v16; // r8d
  HMODULE ModuleHandleA; // rax
  int v18; // r10d
  int v19; // r11d
  int v20; // r9d
  int v21; // edi
  const wchar_t *v22; // rdx
  const wchar_t *v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rax
  __int128 v26; // [rsp+30h] [rbp-10h] BYREF
  __int64 *v27; // [rsp+78h] [rbp+38h] BYREF

  v7 = (__int64)a7;
  v27 = 0;
  v9 = 0;
  v10 = 0;
  if ( !a7[88] )
  {
    v11 = L"UpstreamPipe";
LABEL_3:
    v12 = 4;
    result = MI_ReportErrorDetails_MandatoryParameterMissing((__int64)v11);
    goto LABEL_61;
  }
  v14 = (_BYTE *)((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*((_QWORD *)a7 + 10));
  a7 = v14;
  v9 = (__int64)v14;
  *(_QWORD *)&v26 = 0;
  if ( v14 )
  {
    v15 = *(void (__fastcall ***)(__int64, __int128 *))v14;
    if ( v15 )
      (*v15)(v9, &v26);
  }
  if ( *(_BYTE *)(v7 + 140) )
  {
    if ( !*(_BYTE *)(v7 + 128) )
    {
      v11 = L"Until";
      goto LABEL_3;
    }
  }
  else if ( !*(_BYTE *)(v7 + 128) )
  {
    goto LABEL_12;
  }
  result = DelegateFromPropertyArgument(*(_QWORD *)(v7 + 120), &v27);
  v10 = v27;
  v12 = result;
  if ( (_DWORD)result )
    goto LABEL_61;
LABEL_12:
  v16 = *(unsigned __int8 *)(v7 + 100);
  if ( !(_BYTE)v16 && !*(_BYTE *)(v7 + 108) && !*(_BYTE *)(v7 + 116) && !*(_BYTE *)(v7 + 137) && !*(_BYTE *)(v7 + 128) )
  {
    v26 = 0;
    v12 = 4;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&v26 = Intlstr_GetString_LoadString(ModuleHandleA, 2105);
    BYTE8(v26) = 0;
    result = MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
    goto LABEL_61;
  }
  v18 = *(unsigned __int8 *)(v7 + 116);
  v19 = *(unsigned __int8 *)(v7 + 137);
  v20 = *(unsigned __int8 *)(v7 + 108);
  v21 = *(unsigned __int8 *)(v7 + 128);
  if ( v21 + v16 + v20 + v18 + v19 != 1 )
  {
    v22 = L"Until";
    if ( (_BYTE)v16 )
    {
      v23 = L"First";
    }
    else if ( (_BYTE)v18 )
    {
      v23 = L"Last";
    }
    else if ( (_BYTE)v20 )
    {
      v23 = L"Skip";
    }
    else
    {
      v23 = L"Unique";
      if ( !(_BYTE)v19 )
        v23 = L"Until";
    }
    if ( !(_BYTE)v21 )
    {
      if ( (_BYTE)v19 )
      {
        v22 = L"Unique";
      }
      else if ( (_BYTE)v20 )
      {
        v22 = L"Skip";
      }
      else
      {
        v22 = L"Last";
        if ( !(_BYTE)v18 )
          v22 = L"First";
      }
    }
    v12 = 4;
    result = MI_ReportErrorDetails_MutuallyExclusiveParameters(v23, v22);
    goto LABEL_61;
  }
  if ( (_BYTE)v16 )
  {
    result = RxcTake(v9, *(unsigned int *)(v7 + 96), &a7);
LABEL_47:
    v12 = result;
    if ( (_DWORD)result )
    {
      v9 = (__int64)a7;
      goto LABEL_61;
    }
    if ( v9 && *(_QWORD *)v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = (__int64)a7;
    goto LABEL_52;
  }
  if ( (_BYTE)v20 )
  {
    result = RxcSkip(v9, *(unsigned int *)(v7 + 104), &a7);
    goto LABEL_47;
  }
  if ( (_BYTE)v18 )
  {
    result = RxcTakeLast(v9, *(unsigned int *)(v7 + 112), &a7);
    goto LABEL_47;
  }
  if ( (_BYTE)v21 && *(_QWORD *)(v7 + 120) )
  {
    if ( !*(_BYTE *)(v7 + 140) || (v24 = 3, !*(_BYTE *)(v7 + 139)) )
      v24 = 2;
    result = RxcSelect_impl(v9, v10, v24, &a7);
    goto LABEL_47;
  }
  if ( (_BYTE)v19 && *(_BYTE *)(v7 + 136) )
  {
    result = KeyUnitBase(v9, 0, off_180049D20, &a7);
    goto LABEL_47;
  }
LABEL_52:
  v25 = *(_QWORD *)v7;
  a7 = (_BYTE *)v9;
  result = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE **, __int64, int))(v25 + 80))(v7, 0, &a7, 15, 0x40000000);
  v12 = result;
  if ( !(_DWORD)result )
  {
    if ( a2 && (result = *a2) != 0 )
    {
      result = (*(__int64 (__fastcall **)(__int64 *, __int64))(result + 8))(a2, v7);
      v12 = result;
    }
    else
    {
      v12 = 4;
    }
  }
LABEL_61:
  if ( v9 )
  {
    result = *(_QWORD *)v9;
    if ( *(_QWORD *)v9 )
      result = (*(__int64 (__fastcall **)(__int64))(result + 16))(v9);
  }
  if ( v10 )
  {
    result = *v10;
    if ( *v10 )
      result = (*(__int64 (__fastcall **)(__int64 *))(result + 16))(v10);
  }
  if ( a2 )
  {
    result = *a2;
    if ( *a2 )
      return (*(__int64 (__fastcall **)(__int64 *, _QWORD))result)(a2, v12);
  }
  return result;
}

```

## disassembly

```asm
0x180003440  mov     [rsp-28h+arg_0], rbx
0x180003445  mov     [rsp-28h+arg_10], rsi
0x18000344a  push    rbp
0x18000344b  push    rdi
0x18000344c  push    r12
0x18000344e  push    r14
0x180003450  push    r15
0x180003452  mov     rbp, rsp
0x180003455  sub     rsp, 40h
0x180003459  mov     rsi, [rbp+arg_30]
0x18000345d  xor     r12d, r12d
0x180003460  mov     r15, rdx
0x180003463  mov     [rbp+arg_8], r12
0x180003467  mov     ebx, r12d
0x18000346a  mov     r14d, r12d
0x18000346d  cmp     [rsi+58h], r12b
0x180003471  jnz     short loc_180003489
0x180003473  lea     rcx, aUpstreampipe_0; "UpstreamPipe"
0x18000347a  mov     edi, 4
0x18000347f  call    MI_ReportErrorDetails_MandatoryParameterMissing
0x180003484  jmp     loc_18000375A
0x180003489  mov     rax, cs:off_180047B90
0x180003490  mov     rcx, [rsi+50h]
0x180003494  mov     rax, [rax+8]
0x180003498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000349d  mov     [rbp+arg_30], rax
0x1800034a1  mov     rbx, rax
0x1800034a4  mov     qword ptr [rbp+var_10], r12
0x1800034a8  test    rax, rax
0x1800034ab  jz      short loc_1800034C4
0x1800034ad  mov     rax, [rax]
0x1800034b0  test    rax, rax
0x1800034b3  jz      short loc_1800034C4
0x1800034b5  mov     rax, [rax]
0x1800034b8  lea     rdx, [rbp+var_10]
0x1800034bc  mov     rcx, rbx
0x1800034bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034c4  cmp     [rsi+8Ch], r12b
0x1800034cb  jz      short loc_1800034DF
0x1800034cd  cmp     [rsi+80h], r12b
0x1800034d4  jnz     short loc_1800034E8
0x1800034d6  lea     rcx, aUntil; "Until"
0x1800034dd  jmp     short loc_18000347A
0x1800034df  cmp     [rsi+80h], r12b
0x1800034e6  jz      short loc_180003503
0x1800034e8  mov     rcx, [rsi+78h]
0x1800034ec  lea     rdx, [rbp+arg_8]
0x1800034f0  call    DelegateFromPropertyArgument
0x1800034f5  mov     r14, [rbp+arg_8]
0x1800034f9  mov     edi, eax
0x1800034fb  test    eax, eax
0x1800034fd  jnz     loc_18000375A
0x180003503  movzx   r8d, byte ptr [rsi+64h]
0x180003508  test    r8b, r8b
0x18000350b  jnz     short loc_180003587
0x18000350d  cmp     [rsi+6Ch], r12b
0x180003511  jnz     short loc_180003587
0x180003513  cmp     [rsi+74h], r12b
0x180003517  jnz     short loc_180003587
0x180003519  cmp     [rsi+89h], r12b
0x180003520  jnz     short loc_180003587
0x180003522  cmp     [rsi+80h], r12b
0x180003529  jnz     short loc_180003587
0x18000352b  xorps   xmm0, xmm0
0x18000352e  lea     rcx, ModuleName; "mpunits.dll"
0x180003535  movups  [rbp+var_10], xmm0
0x180003539  mov     edi, 4
0x18000353e  call    cs:__imp_GetModuleHandleA
0x180003544  mov     rcx, rax
0x180003547  mov     edx, 839h
0x18000354c  call    _Intlstr_GetString_LoadString
0x180003551  mov     qword ptr [rbp+var_10], rax
0x180003555  lea     r9, [rbp+var_10]
0x180003559  mov     byte ptr [rbp+var_10+8], r12b
0x18000355d  lea     r8d, [rdi+1]
0x180003561  movaps  xmm0, [rbp+var_10]
0x180003565  lea     rdx, aMi; "MI"
0x18000356c  mov     [rsp+40h+var_18], r12; __int64
0x180003571  mov     ecx, edi; int
0x180003573  movdqa  [rbp+var_10], xmm0
0x180003578  mov     [rsp+40h+var_20], r12; __int64
0x18000357d  call    MI_ReportErrorDetails_ForCustomError
0x180003582  jmp     loc_18000375A
0x180003587  movzx   r10d, byte ptr [rsi+74h]
0x18000358c  movzx   r11d, byte ptr [rsi+89h]
0x180003594  movzx   r9d, byte ptr [rsi+6Ch]
0x180003599  movzx   edi, byte ptr [rsi+80h]
0x1800035a0  lea     ecx, [r10+r11]
0x1800035a4  add     ecx, r9d
0x1800035a7  add     ecx, r8d
0x1800035aa  add     ecx, edi
0x1800035ac  cmp     ecx, 1
0x1800035af  jz      loc_180003635
0x1800035b5  lea     rdx, aUntil; "Until"
0x1800035bc  lea     rax, aFirst; "First"
0x1800035c3  test    r8b, r8b
0x1800035c6  jz      short loc_1800035CD
0x1800035c8  mov     rcx, rax
0x1800035cb  jmp     short loc_1800035F7
0x1800035cd  test    r10b, r10b
0x1800035d0  jz      short loc_1800035DB
0x1800035d2  lea     rcx, aLast; "Last"
0x1800035d9  jmp     short loc_1800035F7
0x1800035db  test    r9b, r9b
0x1800035de  jz      short loc_1800035E9
0x1800035e0  lea     rcx, aSkip; "Skip"
0x1800035e7  jmp     short loc_1800035F7
0x1800035e9  test    r11b, r11b
0x1800035ec  lea     rcx, aUnique; "Unique"
0x1800035f3  cmovz   rcx, rdx
0x1800035f7  test    dil, dil
0x1800035fa  jnz     short loc_180003626
0x1800035fc  test    r11b, r11b
0x1800035ff  jz      short loc_18000360A
0x180003601  lea     rdx, aUnique; "Unique"
0x180003608  jmp     short loc_180003626
0x18000360a  test    r9b, r9b
0x18000360d  jz      short loc_180003618
0x18000360f  lea     rdx, aSkip; "Skip"
0x180003616  jmp     short loc_180003626
0x180003618  test    r10b, r10b
0x18000361b  lea     rdx, aLast; "Last"
0x180003622  cmovz   rdx, rax
0x180003626  mov     edi, 4
0x18000362b  call    MI_ReportErrorDetails_MutuallyExclusiveParameters
0x180003630  jmp     loc_18000375A
0x180003635  test    r8b, r8b
0x180003638  jz      short loc_18000364B
0x18000363a  mov     edx, [rsi+60h]
0x18000363d  lea     r8, [rbp+arg_30]
0x180003641  mov     rcx, rbx
0x180003644  call    RxcTake
0x180003649  jmp     short loc_1800036B7
0x18000364b  test    r9b, r9b
0x18000364e  jz      short loc_180003661
0x180003650  mov     edx, [rsi+68h]
0x180003653  lea     r8, [rbp+arg_30]
0x180003657  mov     rcx, rbx
0x18000365a  call    RxcSkip
0x18000365f  jmp     short loc_1800036B7
0x180003661  test    r10b, r10b
0x180003664  jz      short loc_180003677
0x180003666  mov     edx, [rsi+70h]
0x180003669  lea     r8, [rbp+arg_30]
0x18000366d  mov     rcx, rbx
0x180003670  call    RxcTakeLast
0x180003675  jmp     short loc_1800036B7
0x180003677  test    dil, dil
0x18000367a  jz      loc_18000372D
0x180003680  cmp     [rsi+78h], r12
0x180003684  jz      loc_18000372D
0x18000368a  cmp     [rsi+8Ch], r12b
0x180003691  jz      short loc_1800036A2
0x180003693  mov     r8d, 3
0x180003699  cmp     [rsi+8Bh], r12b
0x1800036a0  jnz     short loc_1800036A8
0x1800036a2  mov     r8d, 2
0x1800036a8  mov     rdx, r14
0x1800036ab  lea     r9, [rbp+arg_30]
0x1800036af  mov     rcx, rbx
0x1800036b2  call    RxcSelect_impl
0x1800036b7  mov     edi, eax
0x1800036b9  test    eax, eax
0x1800036bb  jnz     short loc_180003727
0x1800036bd  test    rbx, rbx
0x1800036c0  jz      short loc_1800036D6
0x1800036c2  mov     rax, [rbx]
0x1800036c5  test    rax, rax
0x1800036c8  jz      short loc_1800036D6
0x1800036ca  mov     rax, [rax+10h]
0x1800036ce  mov     rcx, rbx
0x1800036d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036d6  mov     rbx, [rbp+arg_30]
0x1800036da  mov     rax, [rsi]
0x1800036dd  lea     r8, [rbp+arg_30]
0x1800036e1  mov     [rbp+arg_30], rbx
0x1800036e5  mov     r9d, 0Fh
0x1800036eb  xor     edx, edx
0x1800036ed  mov     dword ptr [rsp+40h+var_20], 40000000h
0x1800036f5  mov     rcx, rsi
0x1800036f8  mov     rax, [rax+50h]
0x1800036fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003701  mov     edi, eax
0x180003703  test    eax, eax
0x180003705  jnz     short loc_18000375A
0x180003707  test    r15, r15
0x18000370a  jz      short loc_180003755
0x18000370c  mov     rax, [r15]
0x18000370f  test    rax, rax
0x180003712  jz      short loc_180003755
0x180003714  mov     rax, [rax+8]
0x180003718  mov     rdx, rsi
0x18000371b  mov     rcx, r15
0x18000371e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003723  mov     edi, eax
0x180003725  jmp     short loc_18000375A
0x180003727  mov     rbx, [rbp+arg_30]
0x18000372b  jmp     short loc_18000375A
0x18000372d  test    r11b, r11b
0x180003730  jz      short loc_1800036DA
0x180003732  cmp     [rsi+88h], r12b
0x180003739  jz      short loc_1800036DA
0x18000373b  lea     r9, [rbp+arg_30]
0x18000373f  xor     edx, edx
0x180003741  lea     r8, off_180049D20
0x180003748  mov     rcx, rbx
0x18000374b  call    KeyUnitBase
0x180003750  jmp     loc_1800036B7
0x180003755  mov     edi, 4
0x18000375a  test    rbx, rbx
0x18000375d  jz      short loc_180003773
0x18000375f  mov     rax, [rbx]
0x180003762  test    rax, rax
0x180003765  jz      short loc_180003773
0x180003767  mov     rax, [rax+10h]
0x18000376b  mov     rcx, rbx
0x18000376e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003773  test    r14, r14
0x180003776  jz      short loc_18000378C
0x180003778  mov     rax, [r14]
0x18000377b  test    rax, rax
0x18000377e  jz      short loc_18000378C
0x180003780  mov     rax, [rax+10h]
0x180003784  mov     rcx, r14
0x180003787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000378c  test    r15, r15
0x18000378f  jz      short loc_1800037A6
0x180003791  mov     rax, [r15]
0x180003794  test    rax, rax
0x180003797  jz      short loc_1800037A6
0x180003799  mov     rax, [rax]
0x18000379c  mov     edx, edi
0x18000379e  mov     rcx, r15
0x1800037a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037a6  lea     r11, [rsp+40h+var_s0]
0x1800037ab  mov     rbx, [r11+30h]
0x1800037af  mov     rsi, [r11+40h]
0x1800037b3  mov     rsp, r11
0x1800037b6  pop     r15
0x1800037b8  pop     r14
0x1800037ba  pop     r12
0x1800037bc  pop     rdi
0x1800037bd  pop     rbp
0x1800037be  retn
```
