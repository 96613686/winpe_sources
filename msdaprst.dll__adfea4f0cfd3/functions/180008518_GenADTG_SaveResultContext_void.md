# GenADTG::SaveResultContext(void)

- ea: `0x180008518`
- end: `0x180008790`
- name: `?SaveResultContext@GenADTG@@QEAAXXZ`
- size: `632`
- prototype: `void __fastcall(GenADTG *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task`

## callers

- `0x180009394`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x180002770`
- `0x1800028b8`
- `0x180006610`
- `0x180008360`
- `0x180008518`
- `0x180009678`
- `0x18001b008`
- `0x18002dca4`
- `0x18002f0e0`
- `0x18002f1a0`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180008737`
- `ole32!CoTaskMemFree` at `0x180008760`
- `ole32!CoTaskMemFree` at `0x180008737`
- `ole32!CoTaskMemFree` at `0x180008760`
- `OLEAUT32!__imp_VariantClear` at `0x180008715`
- `OLEAUT32!__imp_VariantClear` at `0x180008715`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GenADTG::SaveResultContext(GenADTG *this)
{
  int v2; // eax
  int v3; // ebx
  unsigned __int8 *v4; // rbx
  unsigned __int64 v5; // rax
  __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  void *v8; // rsp
  void *v9; // rsp
  unsigned int *v10; // rdi
  unsigned __int128 v11; // rax
  GenADTG *v12; // rcx
  unsigned int i; // esi
  unsigned __int16 v14; // r14
  __int64 v15; // rdi
  char *v16; // rcx
  unsigned int v17[3]; // [rsp+10h] [rbp-40h] BYREF
  GUID v18; // [rsp+1Ch] [rbp-34h]
  __int64 *v19; // [rsp+30h] [rbp-20h]
  int v20; // [rsp+38h] [rbp-18h]
  GUID v21; // [rsp+3Ch] [rbp-14h]
  unsigned __int8 v22[4]; // [rsp+50h] [rbp+0h] BYREF
  unsigned int v23; // [rsp+54h] [rbp+4h] BYREF
  unsigned __int8 v24[8]; // [rsp+58h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+10h] BYREF
  __int64 v26; // [rsp+68h] [rbp+18h] BYREF
  unsigned __int8 *v27; // [rsp+70h] [rbp+20h]
  __int64 v28; // [rsp+78h] [rbp+28h]

  v22[0] = 16;
  *(_WORD *)v24 = 0;
  v26 = 0;
  v23 = 0;
  pv = 0;
  GenADTG::SaveToBuffer(this, v22, 1u);
  v2 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
         *((_QWORD *)this + 3),
         &IID_IRowsetInfo,
         &v26);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180049588[0] )
        bidTraceW(off_1800491C0[0], 1201152, off_180049588[0], (unsigned int)v2, 1173);
    }
    ThrowHR(v3);
  }
  v28 = 0;
  OnNullThrowOOM(v17);
  *(_QWORD *)v17 = qword_180037868;
  v17[2] = 4;
  v18 = DBPROPSET_ROWSET;
  v19 = qword_180037850;
  v20 = 5;
  v21 = DBPROPSET_ADC;
  if ( (*(int (__fastcall **)(__int64, __int64, unsigned int *, unsigned int *, LPVOID *))(*(_QWORD *)v26 + 24LL))(
         v26,
         2,
         v17,
         &v23,
         &pv) >= 0 )
  {
    v4 = 0;
    v27 = 0;
    if ( v23 > 0x100 )
    {
      v11 = v23 * (unsigned __int128)4uLL;
      if ( !is_mul_ok(v23, 4u) )
        LODWORD(v11) = -1;
      v4 = MMMAlloc(v11, DWORD2(v11));
      v27 = v4;
      v10 = (unsigned int *)v4;
    }
    else
    {
      v5 = 4LL * v23;
      v6 = v5 + 15;
      if ( v5 + 15 < v5 )
        v6 = 0xFFFFFFFFFFFFFF0LL;
      v7 = v6 & 0xFFFFFFFFFFFFFFF0uLL;
      v8 = alloca(v7);
      v9 = alloca(v7);
      v10 = v17;
    }
    OnNullThrowOOM(v10);
    *(_WORD *)v24 = GenADTG::DeterminePropLength(v12, v23, (struct tagDBPROPSET *)pv, v10);
    GenADTG::SaveToBuffer(this, v24, 2u);
    GenADTG::SaveProperties(this, v23, (struct tagDBPROPSET *)pv, v10);
    for ( i = 0; i < v23; ++i )
    {
      v14 = 0;
      v15 = 32LL * i;
      v16 = (char *)pv;
      if ( *(_DWORD *)((char *)pv + v15 + 8) )
      {
        do
        {
          VariantClear((VARIANTARG *)(*(_QWORD *)&v16[v15] + 8 * (9LL * v14++ + 6)));
          v16 = (char *)pv;
        }
        while ( (unsigned int)v14 < *(_DWORD *)((char *)pv + v15 + 8) );
      }
      CoTaskMemFree(*(LPVOID *)&v16[v15]);
    }
    operator delete(v4);
  }
  operator delete(0);
  CoTaskMemFree(pv);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v26);
}

```

## disassembly

```asm
0x180008518  push    rbp
0x18000851a  push    rbx
0x18000851b  push    rsi
0x18000851c  push    rdi
0x18000851d  push    r12
0x18000851f  push    r14
0x180008521  sub     rsp, 78h
0x180008525  lea     rbp, [rsp+30h]
0x18000852a  mov     rax, cs:__security_cookie
0x180008531  xor     rax, rbp
0x180008534  mov     [rbp+70h+var_40], rax
0x180008538  mov     rsi, rcx
0x18000853b  mov     [rbp+70h+var_70], 10h
0x18000853f  xor     eax, eax
0x180008541  mov     word ptr [rbp+70h+var_68], ax
0x180008545  mov     [rbp+70h+var_58], rax
0x180008549  mov     [rbp+70h+var_6C], eax
0x18000854c  mov     [rbp+70h+pv], rax
0x180008550  lea     r12d, [rax+1]
0x180008554  mov     r8d, r12d; unsigned int
0x180008557  lea     rdx, [rbp+70h+var_70]; unsigned __int8 *
0x18000855b  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008560  mov     rcx, [rsi+18h]
0x180008564  mov     rax, [rcx]
0x180008567  lea     r8, [rbp+70h+var_58]
0x18000856b  lea     rdx, IID_IRowsetInfo
0x180008572  mov     rax, [rax]
0x180008575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000857a  mov     ebx, eax
0x18000857c  test    eax, eax
0x18000857e  jns     short loc_1800085C0
0x180008580  test    byte ptr cs:_bidGblFlags, 2
0x180008587  jz      short loc_1800085B8
0x180008589  mov     rcx, cs:off_180049588; "<GenADTG::SaveResultContext|ADO|ERR>  H"...
0x180008590  test    rcx, rcx
0x180008593  jz      short loc_1800085B8
0x180008595  mov     [rsp+0A0h+var_80], 495h
0x18000859d  mov     r9d, eax
0x1800085a0  mov     r8, cs:off_180049588; "<GenADTG::SaveResultContext|ADO|ERR>  H"...
0x1800085a7  mov     edx, 125400h
0x1800085ac  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800085b3  call    _bidTraceW
0x1800085b8  mov     ecx, ebx; int
0x1800085ba  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800085c0  mov     [rbp+70h+var_48], 0
0x1800085c8  mov     eax, [rsp+0A0h+var_A0]
0x1800085cb  sub     rsp, 40h
0x1800085cf  lea     rbx, [rsp+0E0h+var_B0]
0x1800085d4  mov     eax, [rbx]
0x1800085d6  mov     rcx, rbx; void *
0x1800085d9  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800085de  lea     rax, qword_180037868
0x1800085e5  mov     [rbx], rax
0x1800085e8  mov     edi, 4
0x1800085ed  mov     [rbx+8], edi
0x1800085f0  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x1800085f7  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x1800085fc  lea     rax, qword_180037850
0x180008603  mov     [rbx+20h], rax
0x180008607  mov     dword ptr [rbx+28h], 5
0x18000860e  movups  xmm0, xmmword ptr cs:?DBPROPSET_ADC@@3U_GUID@@B.Data1; _GUID const DBPROPSET_ADC ...
0x180008615  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x18000861a  mov     rcx, [rbp+70h+var_58]
0x18000861e  mov     rax, [rcx]
0x180008621  lea     rdx, [rbp+70h+pv]
0x180008625  mov     [rsp+0E0h+var_C0], rdx
0x18000862a  lea     r9, [rbp+70h+var_6C]
0x18000862e  mov     r8, rbx
0x180008631  lea     edx, [rdi-2]
0x180008634  mov     rax, [rax+18h]
0x180008638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000863d  test    eax, eax
0x18000863f  js      loc_180008754
0x180008645  xor     ebx, ebx
0x180008647  mov     [rbp+70h+var_50], rbx
0x18000864b  mov     eax, [rbp+70h+var_6C]
0x18000864e  cmp     eax, 100h
0x180008653  ja      short loc_180008682
0x180008655  shl     rax, 2
0x180008659  lea     rcx, [rax+0Fh]
0x18000865d  cmp     rcx, rax
0x180008660  ja      short loc_18000866C
0x180008662  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000866c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008670  mov     rax, rcx
0x180008673  call    _alloca_probe
0x180008678  sub     rsp, rcx
0x18000867b  lea     rdi, [rsp+0E0h+var_B0]
0x180008680  jmp     short loc_1800086A7
0x180008682  mov     rcx, rax
0x180008685  mov     rax, rdi
0x180008688  mul     rcx
0x18000868b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180008692  cmovb   rax, rcx
0x180008696  mov     ecx, eax; unsigned int
0x180008698  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000869d  mov     rbx, rax
0x1800086a0  mov     [rbp+70h+var_50], rax
0x1800086a4  mov     rdi, rax
0x1800086a7  mov     rcx, rdi; void *
0x1800086aa  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800086af  mov     r9, rdi; unsigned int *
0x1800086b2  mov     r8, [rbp+70h+pv]; struct tagDBPROPSET *
0x1800086b6  mov     edx, [rbp+70h+var_6C]; unsigned int
0x1800086b9  call    ?DeterminePropLength@GenADTG@@AEAAGKPEAUtagDBPROPSET@@PEAK@Z; GenADTG::DeterminePropLength(ulong,tagDBPROPSET *,ulong *)
0x1800086be  mov     word ptr [rbp+70h+var_68], ax
0x1800086c2  mov     r8d, 2; unsigned int
0x1800086c8  lea     rdx, [rbp+70h+var_68]; unsigned __int8 *
0x1800086cc  mov     rcx, rsi; this
0x1800086cf  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x1800086d4  mov     r9, rdi; unsigned int *
0x1800086d7  mov     r8, [rbp+70h+pv]; struct tagDBPROPSET *
0x1800086db  mov     edx, [rbp+70h+var_6C]; unsigned int
0x1800086de  mov     rcx, rsi; this
0x1800086e1  call    ?SaveProperties@GenADTG@@AEAAXKPEAUtagDBPROPSET@@PEAK@Z; GenADTG::SaveProperties(ulong,tagDBPROPSET *,ulong *)
0x1800086e6  xor     esi, esi
0x1800086e8  cmp     [rbp+70h+var_6C], esi
0x1800086eb  jbe     short loc_18000874B
0x1800086ed  xor     r14d, r14d
0x1800086f0  mov     edi, esi
0x1800086f2  shl     rdi, 5
0x1800086f6  mov     rcx, [rbp+70h+pv]
0x1800086fa  cmp     [rdi+rcx+8], r14d
0x1800086ff  jbe     short loc_180008733
0x180008701  movzx   eax, r14w
0x180008705  lea     rdx, [rax+rax*8]
0x180008709  mov     rax, [rdi+rcx]
0x18000870d  lea     rdx, [rdx+6]
0x180008711  lea     rcx, [rax+rdx*8]; pvarg
0x180008715  call    cs:__imp_VariantClear
0x18000871c  nop     dword ptr [rax+rax+00h]
0x180008721  add     r14w, r12w
0x180008725  movzx   eax, r14w
0x180008729  mov     rcx, [rbp+70h+pv]
0x18000872d  cmp     eax, [rdi+rcx+8]
0x180008731  jb      short loc_180008701
0x180008733  mov     rcx, [rdi+rcx]; pv
0x180008737  call    cs:__imp_CoTaskMemFree
0x18000873e  nop     dword ptr [rax+rax+00h]
0x180008743  add     esi, r12d
0x180008746  cmp     esi, [rbp+70h+var_6C]
0x180008749  jb      short loc_1800086ED
0x18000874b  mov     rcx, rbx; void *
0x18000874e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008753  nop
0x180008754  xor     ecx, ecx; void *
0x180008756  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000875b  nop
0x18000875c  mov     rcx, [rbp+70h+pv]; pv
0x180008760  call    cs:__imp_CoTaskMemFree
0x180008767  nop     dword ptr [rax+rax+00h]
0x18000876c  nop
0x18000876d  lea     rcx, [rbp+70h+var_58]
0x180008771  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180008776  mov     rcx, [rbp+70h+var_40]
0x18000877a  xor     rcx, rbp; StackCookie
0x18000877d  call    __security_check_cookie
0x180008782  lea     rsp, [rbp+48h]
0x180008786  pop     r14
0x180008788  pop     r12
0x18000878a  pop     rdi
0x18000878b  pop     rsi
0x18000878c  pop     rbx
0x18000878d  pop     rbp
0x18000878e  retn
```
