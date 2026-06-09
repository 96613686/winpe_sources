# SCEPTaskSchedulerImpl::RegisterTask(ushort const *,ushort const *,bool)

- ea: `0x180038560`
- end: `0x1800387f6`
- name: `?RegisterTask@SCEPTaskSchedulerImpl@@UEAAJPEBG0_N@Z`
- size: `662`
- prototype: `int(SCEPTaskSchedulerImpl *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000604c`
- `0x18001ce6c`
- `0x18003593c`
- `0x180038560`
- `0x18003b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003863e`
- `OLEAUT32!__imp_SysAllocString` at `0x180038686`
- `OLEAUT32!__imp_SysAllocString` at `0x18003863e`
- `OLEAUT32!__imp_SysAllocString` at `0x180038686`
- `OLEAUT32!__imp_VariantInit` at `0x180038605`
- `OLEAUT32!__imp_VariantInit` at `0x18003861c`
- `OLEAUT32!__imp_VariantInit` at `0x18003876d`
- `OLEAUT32!__imp_VariantInit` at `0x180038605`
- `OLEAUT32!__imp_VariantInit` at `0x18003861c`
- `OLEAUT32!__imp_VariantInit` at `0x18003876d`
- `OLEAUT32!__imp_VariantClear` at `0x18003871d`
- `OLEAUT32!__imp_VariantClear` at `0x18003872f`
- `OLEAUT32!__imp_VariantClear` at `0x180038742`
- `OLEAUT32!__imp_VariantClear` at `0x1800387a2`
- `OLEAUT32!__imp_VariantClear` at `0x18003871d`
- `OLEAUT32!__imp_VariantClear` at `0x18003872f`
- `OLEAUT32!__imp_VariantClear` at `0x180038742`
- `OLEAUT32!__imp_VariantClear` at `0x1800387a2`

## pseudocode

```c
__int64 __fastcall SCEPTaskSchedulerImpl::RegisterTask(
        SCEPTaskSchedulerImpl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  __int64 *v4; // rdi
  __int64 v10; // r13
  __int128 v11; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v13; // xmm10
  IRecordInfo *v14; // xmm11_8
  BSTR v15; // rax
  IRecordInfo *v16; // xmm7_8
  __int64 v17; // rsi
  __int128 v18; // xmm6
  BSTR *v19; // rbx
  BSTR v20; // rax
  BSTR v21; // rdx
  __int64 (__fastcall *v22)(__int64 *, BSTR, __int64, __int64, VARIANTARG *, __int128 *, int, __int128 *, __int64 *); // rax
  int v23; // ebx
  HRESULT v24; // eax
  HRESULT v25; // eax
  HRESULT v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, VARIANTARG *, _QWORD); // rbx
  HRESULT v29; // eax
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  BSTR *v31; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG v32; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG v33; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v34; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v35; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *v36; // [rsp+D0h] [rbp-30h]
  __int128 v37; // [rsp+E0h] [rbp-20h] BYREF
  IRecordInfo *v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+190h] [rbp+90h] BYREF

  v4 = (__int64 *)*((_QWORD *)this + 2);
  if ( !v4 )
    return 2147947423LL;
  v39 = 0;
  v10 = *v4;
  VariantInit(&pvarg);
  v11 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v34);
  v13 = *(_OWORD *)&v34.vt;
  v14 = v34.pRecInfo;
  if ( !a3 )
    a3 = L"S-1-5-18";
  v15 = SysAllocString(a3);
  if ( !v15 )
    goto LABEL_18;
  v16 = v33.pRecInfo;
  v17 = *((_QWORD *)this + 3);
  v33.vt = 8;
  v33.llVal = (LONGLONG)v15;
  v18 = *(_OWORD *)&v33.vt;
  v19 = (BSTR *)operator new(0x18u);
  v19[1] = 0;
  *((_DWORD *)v19 + 4) = 1;
  v20 = SysAllocString(a2);
  *v19 = v20;
  if ( !v20 )
  {
    if ( a2 )
LABEL_18:
      _com_issue_error(-2147024882);
  }
  v31 = v19;
  v21 = v20;
  v22 = *(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int64, VARIANTARG *, __int128 *, int, __int128 *, __int64 *))(v10 + 136);
  v35 = v11;
  v36 = pRecInfo;
  v37 = v13;
  v38 = v14;
  *(_OWORD *)&v32.vt = v18;
  v32.pRecInfo = v16;
  v23 = v22(v4, v21, v17, 6, &v32, &v37, 3, &v35, &v39);
  _bstr_t::~_bstr_t((_bstr_t *)&v31);
  v24 = VariantClear(&v33);
  if ( v24 < 0 )
    _com_issue_error(v24);
  v25 = VariantClear(&v34);
  if ( v25 < 0 )
    _com_issue_error(v25);
  v26 = VariantClear(&pvarg);
  if ( v26 < 0 )
    _com_issue_error(v26);
  if ( v23 >= 0 && a4 == 1 )
  {
    v27 = v39;
    v28 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, _QWORD))(*(_QWORD *)v39 + 96LL);
    VariantInit(&pvarg);
    v32 = pvarg;
    v23 = v28(v27, &v32, 0);
    v29 = VariantClear(&pvarg);
    if ( v29 < 0 )
      _com_issue_error(v29);
  }
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180038560  mov     rax, rsp
0x180038563  mov     [rax+10h], rbx
0x180038567  mov     [rax+18h], rsi
0x18003856b  push    rbp
0x18003856c  push    rdi
0x18003856d  push    r13
0x18003856f  push    r14
0x180038571  push    r15
0x180038573  lea     rbp, [rsp-60h]
0x180038578  sub     rsp, 160h
0x18003857f  mov     rdi, [rcx+10h]
0x180038583  mov     r15b, r9b
0x180038586  movaps  xmmword ptr [rax-38h], xmm6
0x18003858a  mov     rbx, r8
0x18003858d  movaps  xmmword ptr [rax-48h], xmm7
0x180038591  mov     r14, rdx
0x180038594  movaps  xmmword ptr [rax-58h], xmm8
0x180038599  mov     rsi, rcx
0x18003859c  movaps  xmmword ptr [rax-68h], xmm9
0x1800385a1  movaps  xmmword ptr [rax-78h], xmm10
0x1800385a6  movaps  xmmword ptr [rax-88h], xmm11
0x1800385ae  test    rdi, rdi
0x1800385b1  jnz     short loc_1800385F2
0x1800385b3  mov     eax, 8007139Fh
0x1800385b8  lea     r11, [rsp+180h+var_20]
0x1800385c0  mov     rbx, [r11+38h]
0x1800385c4  mov     rsi, [r11+40h]
0x1800385c8  movaps  xmm6, xmmword ptr [r11-10h]
0x1800385cd  movaps  xmm7, xmmword ptr [r11-20h]
0x1800385d2  movaps  xmm8, xmmword ptr [r11-30h]
0x1800385d7  movaps  xmm9, xmmword ptr [r11-40h]
0x1800385dc  movaps  xmm10, xmmword ptr [r11-50h]
0x1800385e1  movaps  xmm11, xmmword ptr [r11-60h]
0x1800385e6  mov     rsp, r11
0x1800385e9  pop     r15
0x1800385eb  pop     r14
0x1800385ed  pop     r13
0x1800385ef  pop     rdi
0x1800385f0  pop     rbp
0x1800385f1  retn
0x1800385f2  mov     [rbp+80h+arg_0], 0
0x1800385fd  lea     rcx, [rsp+180h+pvarg]; pvarg
0x180038602  mov     r13, [rdi]
0x180038605  call    cs:__imp_VariantInit
0x18003860b  movups  xmm8, xmmword ptr [rsp+180h+pvarg]
0x180038611  lea     rcx, [rbp+80h+var_D8]; pvarg
0x180038615  movsd   xmm9, qword ptr [rsp+180h+pvarg+10h]
0x18003861c  call    cs:__imp_VariantInit
0x180038622  movups  xmm10, xmmword ptr [rbp+80h+var_D8]
0x180038627  lea     rax, aS1518; "S-1-5-18"
0x18003862e  test    rbx, rbx
0x180038631  movsd   xmm11, qword ptr [rbp+80h+var_D8+10h]
0x180038637  cmovz   rbx, rax
0x18003863b  mov     rcx, rbx; psz
0x18003863e  call    cs:__imp_SysAllocString
0x180038644  test    rax, rax
0x180038647  jz      loc_1800387D3
0x18003864d  movsd   xmm7, qword ptr [rbp+80h+var_F0+10h]
0x180038652  mov     ecx, 8
0x180038657  mov     rsi, [rsi+18h]
0x18003865b  mov     word ptr [rbp+80h+var_F0], cx
0x18003865f  mov     ecx, 18h; Size
0x180038664  mov     qword ptr [rbp+80h+var_F0+8], rax
0x180038668  movups  xmm6, xmmword ptr [rbp+80h+var_F0]
0x18003866c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038671  mov     rcx, r14; psz
0x180038674  mov     rbx, rax
0x180038677  mov     qword ptr [rax+8], 0
0x18003867f  mov     dword ptr [rax+10h], 1
0x180038686  call    cs:__imp_SysAllocString
0x18003868c  mov     [rbx], rax
0x18003868f  test    rax, rax
0x180038692  jnz     short loc_18003869D
0x180038694  test    r14, r14
0x180038697  jnz     loc_1800387D3
0x18003869d  lea     rcx, [rbp+80h+arg_0]
0x1800386a4  mov     [rsp+180h+var_118], rbx
0x1800386a9  mov     [rsp+180h+var_140], rcx
0x1800386ae  mov     rdx, rax
0x1800386b1  mov     rax, [r13+88h]
0x1800386b8  lea     rcx, [rbp+80h+var_C0]
0x1800386bc  mov     [rsp+180h+var_148], rcx
0x1800386c1  mov     r9d, 6
0x1800386c7  lea     rcx, [rbp+80h+var_A0]
0x1800386cb  mov     [rsp+180h+var_150], 3
0x1800386d3  mov     [rsp+180h+var_158], rcx
0x1800386d8  mov     r8, rsi
0x1800386db  lea     rcx, [rsp+180h+var_110]
0x1800386e0  movaps  [rbp+80h+var_C0], xmm8
0x1800386e5  mov     [rsp+180h+var_160], rcx
0x1800386ea  mov     rcx, rdi
0x1800386ed  movsd   [rbp+80h+var_B0], xmm9
0x1800386f3  movaps  [rbp+80h+var_A0], xmm10
0x1800386f8  movsd   [rbp+80h+var_90], xmm11
0x1800386fe  movaps  [rsp+180h+var_110], xmm6
0x180038703  movsd   [rbp+80h+var_100], xmm7
0x180038708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003870d  lea     rcx, [rsp+180h+var_118]; this
0x180038712  mov     ebx, eax
0x180038714  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180038719  lea     rcx, [rbp+80h+var_F0]; pvarg
0x18003871d  call    cs:__imp_VariantClear
0x180038723  test    eax, eax
0x180038725  js      loc_1800387DE
0x18003872b  lea     rcx, [rbp+80h+var_D8]; pvarg
0x18003872f  call    cs:__imp_VariantClear
0x180038735  test    eax, eax
0x180038737  js      loc_1800387E6
0x18003873d  lea     rcx, [rsp+180h+pvarg]; pvarg
0x180038742  call    cs:__imp_VariantClear
0x180038748  test    eax, eax
0x18003874a  js      loc_1800387EE
0x180038750  test    ebx, ebx
0x180038752  js      short loc_1800387AC
0x180038754  cmp     r15b, 1
0x180038758  jnz     short loc_1800387AC
0x18003875a  mov     rdi, [rbp+80h+arg_0]
0x180038761  lea     rcx, [rsp+180h+pvarg]; pvarg
0x180038766  mov     rax, [rdi]
0x180038769  mov     rbx, [rax+60h]
0x18003876d  call    cs:__imp_VariantInit
0x180038773  movups  xmm0, xmmword ptr [rsp+180h+pvarg]
0x180038778  lea     rdx, [rsp+180h+var_110]
0x18003877d  xor     r8d, r8d
0x180038780  movsd   xmm1, qword ptr [rsp+180h+pvarg+10h]
0x180038786  mov     rcx, rdi
0x180038789  mov     rax, rbx
0x18003878c  movaps  [rsp+180h+var_110], xmm0
0x180038791  movsd   [rbp+80h+var_100], xmm1
0x180038796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003879b  lea     rcx, [rsp+180h+pvarg]; pvarg
0x1800387a0  mov     ebx, eax
0x1800387a2  call    cs:__imp_VariantClear
0x1800387a8  test    eax, eax
0x1800387aa  js      short loc_1800387CB
0x1800387ac  mov     rcx, [rbp+80h+arg_0]
0x1800387b3  test    rcx, rcx
0x1800387b6  jz      short loc_1800387C4
0x1800387b8  mov     rdx, [rcx]
0x1800387bb  mov     rax, [rdx+10h]
0x1800387bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387c4  mov     eax, ebx
0x1800387c6  jmp     loc_1800385B8
0x1800387cb  mov     ecx, eax; int
0x1800387cd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800387d3  mov     ecx, 8007000Eh; int
0x1800387d8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800387de  mov     ecx, eax; int
0x1800387e0  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800387e6  mov     ecx, eax; int
0x1800387e8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800387ee  mov     ecx, eax; int
0x1800387f0  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
