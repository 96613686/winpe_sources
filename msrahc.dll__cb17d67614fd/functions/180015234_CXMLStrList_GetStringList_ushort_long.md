# CXMLStrList::GetStringList(ushort * * *,long *)

- ea: `0x180015234`
- end: `0x180015509`
- name: `?GetStringList@CXMLStrList@@QEAAJPEAPEAPEAGPEAJ@Z`
- size: `725`
- prototype: `__int64 __fastcall(CXMLStrList *this, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010184`

## callees

- `0x180014660`
- `0x180014da0`
- `0x180014e70`
- `0x180015234`
- `0x18001c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001527e`
- `OLEAUT32!__imp_VariantInit` at `0x180015351`
- `OLEAUT32!__imp_VariantInit` at `0x18001527e`
- `OLEAUT32!__imp_VariantInit` at `0x180015351`
- `OLEAUT32!__imp_VariantClear` at `0x1800153e0`
- `OLEAUT32!__imp_VariantClear` at `0x1800154a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800153e0`
- `OLEAUT32!__imp_VariantClear` at `0x1800154a9`
- `KERNEL32!GetProcessHeap` at `0x180015304`
- `KERNEL32!GetProcessHeap` at `0x180015304`
- `KERNEL32!HeapAlloc` at `0x180015319`
- `KERNEL32!HeapAlloc` at `0x180015319`

## string_xrefs

- `0x1800152b9`: `base\diagnosis\ra\racommon\src\xmlutils.cpp`
- `0x180015484`: `base\diagnosis\ra\racommon\src\xmlutils.cpp`
- `0x1800152b2`: `CXMLStrList::GetStringList`
- `0x180015478`: `CXMLStrList::GetStringList`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXMLStrList::GetStringList(CXMLStrList *this, unsigned __int16 ***a2, unsigned int *a3)
{
  unsigned __int16 **v6; // rsi
  signed int v7; // eax
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  unsigned int v10; // edi
  unsigned int v11; // r9d
  SIZE_T v12; // rbx
  HANDLE ProcessHeap; // rax
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  CEventLogger *v15; // rcx
  signed int i; // ebx
  unsigned int v17; // r9d
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v20; // [rsp+A0h] [rbp+48h] BYREF
  CEventLogger *v21; // [rsp+A8h] [rbp+50h] BYREF
  CEventLogger *v22; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v23; // [rsp+B8h] [rbp+60h] BYREF

  *a3 = 0;
  *a2 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  v6 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *))(**((_QWORD **)this + 1) + 288LL))(
         *((_QWORD *)this + 1),
         L"String",
         &v23);
  v10 = v7;
  if ( v7 < 0 )
  {
    v11 = 333;
LABEL_3:
    CEventLogger::LogError(
      v9,
      v8,
      L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
      v11,
      L"CXMLStrList::GetStringList",
      v7);
    goto LABEL_34;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 64LL))(v23, &v20);
  v10 = v7;
  if ( v7 < 0 )
  {
    v11 = 335;
    goto LABEL_3;
  }
  if ( v20 )
  {
    v12 = 8LL * (int)v20;
    ProcessHeap = GetProcessHeap();
    v6 = (unsigned __int16 **)HeapAlloc(ProcessHeap, 8u, v12);
    if ( v6 )
    {
      for ( i = 0; i < (int)v20; ++i )
      {
        VariantInit(&pvarg);
        v7 = (*(__int64 (__fastcall **)(__int64, CEventLogger **))(*(_QWORD *)v23 + 72LL))(v23, &v22);
        v10 = v7;
        if ( v7 < 0 )
        {
          v11 = 345;
          goto LABEL_3;
        }
        v9 = v22;
        if ( !v22 )
        {
          v17 = 347;
          goto LABEL_33;
        }
        v7 = (*(__int64 (__fastcall **)(CEventLogger *, CEventLogger **))(*(_QWORD *)v22 + 104LL))(v22, &v21);
        v10 = v7;
        if ( v7 < 0 )
        {
          v11 = 349;
          goto LABEL_3;
        }
        v9 = v21;
        if ( !v21 )
        {
          v17 = 351;
          goto LABEL_33;
        }
        v7 = (*(__int64 (__fastcall **)(CEventLogger *, VARIANTARG *))(*(_QWORD *)v21 + 64LL))(v21, &pvarg);
        v10 = v7;
        if ( v7 < 0 )
        {
          v11 = 353;
          goto LABEL_3;
        }
        if ( pvarg.vt != 8 )
        {
          v17 = 355;
          goto LABEL_33;
        }
        v7 = DuplicateString(pvarg.bstrVal, &v6[i]);
        v10 = v7;
        if ( v7 < 0 )
        {
          v11 = 357;
          goto LABEL_3;
        }
        VariantClear(&pvarg);
        if ( v21 )
        {
          (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v21 + 16LL))(v21);
          v21 = 0;
        }
        if ( v22 )
        {
          (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v22 + 16LL))(v22);
          v22 = 0;
        }
      }
      *a3 = v20;
      *a2 = v6;
      v6 = 0;
      v20 = 0;
    }
    else
    {
      v10 = -2147024882;
      CEventLogger::LogError(
        v15,
        v14,
        L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
        0x153u,
        L"CXMLStrList::GetStringList",
        0x8007000E);
    }
  }
  else
  {
    v17 = 337;
LABEL_33:
    CEventLogger::LogError(
      v9,
      v8,
      L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
      v17,
      L"CXMLStrList::GetStringList",
      0);
    v10 = -2147467259;
  }
LABEL_34:
  FreeStringList(v6, v20);
  VariantClear(&pvarg);
  if ( v21 )
  {
    (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  return v10;
}

```

## disassembly

```asm
0x180015234  push    rbp
0x180015236  push    rbx
0x180015237  push    rsi
0x180015238  push    rdi
0x180015239  push    r12
0x18001523b  push    r13
0x18001523d  push    r14
0x18001523f  push    r15
0x180015241  mov     rbp, rsp
0x180015244  sub     rsp, 58h
0x180015248  xor     r12d, r12d
0x18001524b  mov     rbx, rcx
0x18001524e  xorps   xmm0, xmm0
0x180015251  mov     [r8], r12d
0x180015254  xor     eax, eax
0x180015256  mov     [rdx], r12
0x180015259  lea     rcx, [rbp+pvarg]; pvarg
0x18001525d  mov     [rbp+arg_18], r12
0x180015261  mov     r14, r8
0x180015264  mov     [rbp+arg_10], r12
0x180015268  mov     r15, rdx
0x18001526b  mov     [rbp+arg_8], r12
0x18001526f  mov     [rbp+arg_0], r12d
0x180015273  mov     esi, r12d
0x180015276  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001527a  mov     qword ptr [rbp+pvarg+10h], rax
0x18001527e  call    cs:__imp_VariantInit
0x180015284  mov     rcx, [rbx+8]
0x180015288  lea     r8, [rbp+arg_18]
0x18001528c  lea     rdx, aString; "String"
0x180015293  mov     rax, [rcx]
0x180015296  mov     rax, [rax+120h]
0x18001529d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152a2  mov     edi, eax
0x1800152a4  test    eax, eax
0x1800152a6  jns     short loc_1800152CF
0x1800152a8  mov     r9d, 14Dh; unsigned int
0x1800152ae  mov     [rsp+58h+var_30], eax; unsigned int
0x1800152b2  lea     rax, aCxmlstrlistGet; "CXMLStrList::GetStringList"
0x1800152b9  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\racommon\\src\\xml"...
0x1800152c0  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x1800152c5  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800152ca  jmp     loc_18001549A
0x1800152cf  mov     rcx, [rbp+arg_18]
0x1800152d3  lea     rdx, [rbp+arg_0]
0x1800152d7  mov     rax, [rcx]
0x1800152da  mov     rax, [rax+40h]
0x1800152de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152e3  mov     edi, eax
0x1800152e5  test    eax, eax
0x1800152e7  jns     short loc_1800152F1
0x1800152e9  mov     r9d, 14Fh
0x1800152ef  jmp     short loc_1800152AE
0x1800152f1  movsxd  rax, [rbp+arg_0]
0x1800152f5  test    eax, eax
0x1800152f7  jz      loc_180015472
0x1800152fd  mov     rbx, rax
0x180015300  shl     rbx, 3
0x180015304  call    cs:__imp_GetProcessHeap
0x18001530a  mov     r13d, 8
0x180015310  mov     r8, rbx; dwBytes
0x180015313  mov     edx, r13d; dwFlags
0x180015316  mov     rcx, rax; hHeap
0x180015319  call    cs:__imp_HeapAlloc
0x18001531f  mov     rsi, rax
0x180015322  test    rax, rax
0x180015325  jnz     short loc_18001533F
0x180015327  mov     edi, 8007000Eh
0x18001532c  mov     [rsp+58h+var_30], 8007000Eh
0x180015334  mov     r9d, 153h
0x18001533a  jmp     loc_1800152B2
0x18001533f  mov     ebx, r12d
0x180015342  mov     eax, [rbp+arg_0]
0x180015345  cmp     ebx, eax
0x180015347  jge     loc_180015463
0x18001534d  lea     rcx, [rbp+pvarg]; pvarg
0x180015351  call    cs:__imp_VariantInit
0x180015357  mov     rcx, [rbp+arg_18]
0x18001535b  lea     rdx, [rbp+arg_10]
0x18001535f  mov     rax, [rcx]
0x180015362  mov     rax, [rax+48h]
0x180015366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001536b  mov     edi, eax
0x18001536d  test    eax, eax
0x18001536f  js      loc_180015458
0x180015375  mov     rcx, [rbp+arg_10]
0x180015379  test    rcx, rcx
0x18001537c  jz      loc_180015450
0x180015382  mov     rax, [rcx]
0x180015385  lea     rdx, [rbp+arg_8]
0x180015389  mov     rax, [rax+68h]
0x18001538d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015392  mov     edi, eax
0x180015394  test    eax, eax
0x180015396  js      loc_180015445
0x18001539c  mov     rcx, [rbp+arg_8]
0x1800153a0  test    rcx, rcx
0x1800153a3  jz      loc_18001543D
0x1800153a9  mov     rax, [rcx]
0x1800153ac  lea     rdx, [rbp+pvarg]
0x1800153b0  mov     rax, [rax+40h]
0x1800153b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153b9  mov     edi, eax
0x1800153bb  test    eax, eax
0x1800153bd  js      short loc_180015432
0x1800153bf  cmp     r13w, word ptr [rbp+pvarg]
0x1800153c4  jnz     short loc_18001542A
0x1800153c6  mov     rcx, qword ptr [rbp+pvarg+8]; Src
0x1800153ca  movsxd  rax, ebx
0x1800153cd  lea     rdx, [rsi+rax*8]; unsigned __int16 **
0x1800153d1  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x1800153d6  mov     edi, eax
0x1800153d8  test    eax, eax
0x1800153da  js      short loc_18001541F
0x1800153dc  lea     rcx, [rbp+pvarg]; pvarg
0x1800153e0  call    cs:__imp_VariantClear
0x1800153e6  mov     rcx, [rbp+arg_8]
0x1800153ea  test    rcx, rcx
0x1800153ed  jz      short loc_1800153FF
0x1800153ef  mov     rax, [rcx]
0x1800153f2  mov     rax, [rax+10h]
0x1800153f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153fb  mov     [rbp+arg_8], r12
0x1800153ff  mov     rcx, [rbp+arg_10]
0x180015403  test    rcx, rcx
0x180015406  jz      short loc_180015418
0x180015408  mov     rax, [rcx]
0x18001540b  mov     rax, [rax+10h]
0x18001540f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015414  mov     [rbp+arg_10], r12
0x180015418  inc     ebx
0x18001541a  jmp     loc_180015342
0x18001541f  mov     r9d, 165h
0x180015425  jmp     loc_1800152AE
0x18001542a  mov     r9d, 163h
0x180015430  jmp     short loc_180015478
0x180015432  mov     r9d, 161h
0x180015438  jmp     loc_1800152AE
0x18001543d  mov     r9d, 15Fh
0x180015443  jmp     short loc_180015478
0x180015445  mov     r9d, 15Dh
0x18001544b  jmp     loc_1800152AE
0x180015450  mov     r9d, 15Bh
0x180015456  jmp     short loc_180015478
0x180015458  mov     r9d, 159h
0x18001545e  jmp     loc_1800152AE
0x180015463  mov     [r14], eax
0x180015466  mov     [r15], rsi
0x180015469  mov     rsi, r12
0x18001546c  mov     [rbp+arg_0], r12d
0x180015470  jmp     short loc_18001549A
0x180015472  mov     r9d, 151h; unsigned int
0x180015478  lea     rax, aCxmlstrlistGet; "CXMLStrList::GetStringList"
0x18001547f  mov     [rsp+58h+var_30], r12d; unsigned int
0x180015484  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\racommon\\src\\xml"...
0x18001548b  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x180015490  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180015495  mov     edi, 80004005h
0x18001549a  mov     edx, [rbp+arg_0]; unsigned int
0x18001549d  mov     rcx, rsi; lpMem
0x1800154a0  call    ?FreeStringList@@YAJPEAPEAGK@Z; FreeStringList(ushort * *,ulong)
0x1800154a5  lea     rcx, [rbp+pvarg]; pvarg
0x1800154a9  call    cs:__imp_VariantClear
0x1800154af  mov     rcx, [rbp+arg_8]
0x1800154b3  test    rcx, rcx
0x1800154b6  jz      short loc_1800154C8
0x1800154b8  mov     rax, [rcx]
0x1800154bb  mov     rax, [rax+10h]
0x1800154bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154c4  mov     [rbp+arg_8], r12
0x1800154c8  mov     rcx, [rbp+arg_10]
0x1800154cc  test    rcx, rcx
0x1800154cf  jz      short loc_1800154E1
0x1800154d1  mov     rax, [rcx]
0x1800154d4  mov     rax, [rax+10h]
0x1800154d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154dd  mov     [rbp+arg_10], r12
0x1800154e1  mov     rcx, [rbp+arg_18]
0x1800154e5  test    rcx, rcx
0x1800154e8  jz      short loc_1800154F6
0x1800154ea  mov     rax, [rcx]
0x1800154ed  mov     rax, [rax+10h]
0x1800154f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154f6  mov     eax, edi
0x1800154f8  add     rsp, 58h
0x1800154fc  pop     r15
0x1800154fe  pop     r14
0x180015500  pop     r13
0x180015502  pop     r12
0x180015504  pop     rdi
0x180015505  pop     rsi
0x180015506  pop     rbx
0x180015507  pop     rbp
0x180015508  retn
```
