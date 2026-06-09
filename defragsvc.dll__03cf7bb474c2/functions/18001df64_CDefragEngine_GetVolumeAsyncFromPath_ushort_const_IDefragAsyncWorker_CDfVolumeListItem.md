# CDefragEngine::_GetVolumeAsyncFromPath(ushort const *,IDefragAsyncWorker * *,CDfVolumeListItem * *)

- ea: `0x18001df64`
- end: `0x18001e421`
- name: `?_GetVolumeAsyncFromPath@CDefragEngine@@AEAAJPEBGPEAPEAUIDefragAsyncWorker@@PEAPEAVCDfVolumeListItem@@@Z`
- size: `1213`
- prototype: `__int64 __fastcall(struct CDfVolumeList **this, const unsigned __int16 *Src, struct IDefragAsyncWorker **, struct CDfVolumeListItem **)`
- caller_count: `3`
- callee_count: `14`
- tags: ``

## callers

- `0x18001de80`
- `0x18003ee70`
- `0x18004275c`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180012cc8`
- `0x180016ea8`
- `0x18001727c`
- `0x180017e50`
- `0x180017e94`
- `0x18001df64`
- `0x18001e998`
- `0x1800239f0`
- `0x18002ca08`
- `0x180067b0a`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e391`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e391`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e08b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e08b`

## string_xrefs

- `0x18001dfb3`: `CDefragEngine::_GetVolumeAsyncFromPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDefragEngine::_GetVolumeAsyncFromPath(
        struct CDfVolumeList **this,
        const unsigned __int16 *Src,
        struct IDefragAsyncWorker **a3,
        struct CDfVolumeListItem **a4)
{
  struct IDefragAsyncWorker *v8; // rbx
  struct IDefragAsyncWorker *v9; // r15
  struct CDfVolumeListItem *v10; // rsi
  __int16 v11; // ax
  unsigned int v12; // edi
  struct CDfVolumeList *v13; // rcx
  __int16 v14; // ax
  int v15; // eax
  __int16 v16; // cx
  int v17; // r12d
  volatile signed __int32 *v18; // r14
  struct IDefragAsyncWorker *v19; // rdi
  CDfVolumeListItem *v20; // rcx
  __int64 v21; // rcx
  int v22; // r14d
  struct IDefragAsyncWorker *v24; // [rsp+20h] [rbp-E0h] BYREF
  CDfVolumeListItem *v25; // [rsp+28h] [rbp-D8h] BYREF
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  struct CDfVolumeListItem *v27; // [rsp+38h] [rbp-C8h] BYREF
  int inserted; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v29; // [rsp+44h] [rbp-BCh]
  __int16 v30; // [rsp+46h] [rbp-BAh]
  int v31; // [rsp+78h] [rbp-88h] BYREF
  CDfVolumeList *v32[2]; // [rsp+80h] [rbp-80h]
  struct IDefragAsyncWorker *v33; // [rsp+90h] [rbp-70h]
  struct IDefragAsyncWorker **v34; // [rsp+98h] [rbp-68h]
  struct CDfVolumeListItem **v35; // [rsp+A0h] [rbp-60h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A8h] [rbp-58h]
  WCHAR szVolumeName; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v38[526]; // [rsp+B2h] [rbp-4Eh] BYREF

  v35 = a4;
  v34 = a3;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&inserted,
    "CDefragEngine::_GetVolumeAsyncFromPath",
    0xCB6u,
    1u);
  v8 = 0;
  v24 = 0;
  v26 = 1;
  szVolumeName = 0;
  memset_0(v38, 0, 0x206u);
  v9 = 0;
  v33 = 0;
  v25 = 0;
  v10 = 0;
  v27 = 0;
  v31 = 0;
  *(_OWORD *)v32 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v11 = 3269;
  if ( !Src || (v29 = 3269, v11 = 3270, !a3) )
  {
    v12 = -2147024809;
LABEL_7:
    inserted = v12;
    v30 = v11;
    goto LABEL_62;
  }
  inserted = 0;
  v29 = 3270;
  if ( (int)SxGetUniqueVolumeForPath(Src, &szVolumeName, 0x104u) < 0 )
  {
    v12 = -1996488703;
    v11 = 3276;
    goto LABEL_7;
  }
  CDefragEngine::_RefreshVolumeList((CDefragEngine *)this, this[13]);
  lpCriticalSection = (LPCRITICAL_SECTION)(this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 8));
  v13 = this[13];
  if ( !v13 )
  {
    inserted = -2147024809;
    v14 = 3292;
LABEL_60:
    v30 = v14;
    goto LABEL_61;
  }
  v32[1] = this[13];
  _InterlockedIncrement((volatile signed __int32 *)v13 + 10);
  v31 = *(_DWORD *)v13;
  v32[0] = (struct CDfVolumeList *)((char *)v13 + 8);
  inserted = 0;
  v29 = 3292;
  if ( v13 == (struct CDfVolumeList *)-8LL )
  {
    inserted = -2147418113;
    v14 = 3294;
    goto LABEL_60;
  }
  v31 = *(_DWORD *)v13;
  v32[0] = (struct CDfVolumeList *)((char *)v13 + 8);
  inserted = 0;
  v29 = 3294;
  v15 = CSxList<CDfVolumeList,CDfVolumeListItem>::CSxIter::Next(&v31, &v25);
  inserted = v15;
  v16 = 3296;
  if ( v15 >= 0 )
  {
    v17 = 0;
    while ( 1 )
    {
      v29 = v16;
      if ( v15 == 1 || v17 )
        break;
      v18 = (volatile signed __int32 *)v25;
      v19 = (struct IDefragAsyncWorker *)*((_QWORD *)v25 + 1);
      if ( v19 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19 + 8LL))(*((_QWORD *)v25 + 1));
      if ( v9 )
      {
        v33 = 0;
        (*(void (__fastcall **)(struct IDefragAsyncWorker *))(*(_QWORD *)v9 + 16LL))(v9);
      }
      v9 = v19;
      v33 = v19;
      if ( v19
        && (*(int (__fastcall **)(struct IDefragAsyncWorker *, WCHAR *, int *))(*(_QWORD *)v19 + 136LL))(
             v19,
             &szVolumeName,
             &v26) >= 0
        && !v26 )
      {
        v17 = 1;
        (*(void (__fastcall **)(struct IDefragAsyncWorker *))(*(_QWORD *)v19 + 8LL))(v19);
        if ( v8 )
        {
          v24 = 0;
          (*(void (__fastcall **)(struct IDefragAsyncWorker *))(*(_QWORD *)v8 + 16LL))(v8);
        }
        v8 = v19;
        v24 = v19;
        if ( v18 )
          _InterlockedIncrement(v18 + 1);
        if ( v10 )
          CDfVolumeListItem::Release(v10);
        v10 = (struct CDfVolumeListItem *)v18;
        v27 = (struct CDfVolumeListItem *)v18;
      }
      if ( v18 )
      {
        v25 = 0;
        CDfVolumeListItem::Release((CDfVolumeListItem *)v18);
      }
      v15 = CSxList<CDfVolumeList,CDfVolumeListItem>::CSxIter::Next(&v31, &v25);
      inserted = v15;
      if ( v15 < 0 )
      {
        v14 = 3319;
        goto LABEL_60;
      }
      v16 = 3319;
    }
    v20 = v25;
    if ( v25 )
    {
      v25 = 0;
      CDfVolumeListItem::Release(v20);
    }
    if ( v32[1] )
    {
      CDfVolumeList::Release(v32[1]);
      v32[1] = 0;
    }
    v32[0] = 0;
    v31 = 0;
    if ( !v17 )
    {
      if ( v8 )
      {
        v24 = 0;
        (*(void (__fastcall **)(struct IDefragAsyncWorker *))(*(_QWORD *)v8 + 16LL))(v8);
      }
      inserted = CDefragEngine::_CreateAsyncForVolume((CDefragEngine *)this, &szVolumeName, 0, &v24);
      v14 = 3329;
      if ( inserted < 0 )
      {
        v8 = v24;
        goto LABEL_60;
      }
      v29 = 3329;
      if ( v10 )
      {
        v27 = 0;
        CDfVolumeListItem::Release(v10);
      }
      inserted = CDfVolumeListItem::CreateInstance(&v27);
      v8 = v24;
      v10 = v27;
      v14 = 3332;
      if ( inserted < 0 )
        goto LABEL_60;
      v29 = 3332;
      if ( v24 )
        (*(void (__fastcall **)(struct IDefragAsyncWorker *))(*(_QWORD *)v24 + 8LL))(v24);
      v21 = *((_QWORD *)v10 + 1);
      if ( v21 )
      {
        *((_QWORD *)v10 + 1) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      *((_QWORD *)v10 + 1) = v8;
      inserted = CSxList<CDfVolumeList,CDfVolumeListItem>::InsertTail(this[13], v10);
      v14 = 3338;
      if ( inserted < 0 )
        goto LABEL_60;
      v29 = 3338;
    }
    *v34 = v8;
    v8 = 0;
    v24 = 0;
    v22 = (int)v35;
    if ( v35 )
    {
      *v35 = v10;
      v22 = 0;
      v10 = 0;
    }
    inserted = v22;
    goto LABEL_61;
  }
  v30 = 3296;
LABEL_61:
  LeaveCriticalSection(lpCriticalSection);
  v12 = inserted;
LABEL_62:
  if ( v32[1] )
    CDfVolumeList::Release(v32[1]);
  if ( v10 )
    CDfVolumeListItem::Release(v10);
  if ( v25 )
    CDfVolumeListItem::Release(v25);
  if ( v9 )
    (*(void (__fastcall **)(struct IDefragAsyncWorker *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v8 )
    (*(void (__fastcall **)(struct IDefragAsyncWorker *))(*(_QWORD *)v8 + 16LL))(v8);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&inserted);
  return v12;
}

```

## disassembly

```asm
0x18001df64  push    rbp
0x18001df66  push    rbx
0x18001df67  push    rsi
0x18001df68  push    rdi
0x18001df69  push    r12
0x18001df6b  push    r13
0x18001df6d  push    r14
0x18001df6f  push    r15
0x18001df71  lea     rbp, [rsp-1D8h]
0x18001df79  sub     rsp, 2D8h
0x18001df80  mov     rax, cs:__security_cookie
0x18001df87  xor     rax, rsp
0x18001df8a  mov     [rbp+210h+var_50], rax
0x18001df91  mov     r14, r9
0x18001df94  mov     [rbp+210h+var_270], r9
0x18001df98  mov     r12, r8
0x18001df9b  mov     [rbp+210h+var_278], r8
0x18001df9f  mov     rdi, rdx
0x18001dfa2  mov     r13, rcx
0x18001dfa5  mov     esi, 1
0x18001dfaa  mov     r9d, esi; unsigned __int16
0x18001dfad  mov     r8d, 0CB6h; unsigned __int16
0x18001dfb3  lea     rdx, aCdefragengineG_5; "CDefragEngine::_GetVolumeAsyncFromPath"
0x18001dfba  lea     rcx, [rsp+310h+var_2D0]; this
0x18001dfbf  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001dfc4  nop
0x18001dfc5  xor     ebx, ebx
0x18001dfc7  mov     [rsp+310h+var_2F0], rbx
0x18001dfcc  mov     [rsp+310h+var_2E0], esi
0x18001dfd0  xor     eax, eax
0x18001dfd2  mov     [rbp+210h+szVolumeName], ax
0x18001dfd6  xor     edx, edx; Val
0x18001dfd8  mov     r8d, 206h; Size
0x18001dfde  lea     rcx, [rbp+210h+var_25E]; void *
0x18001dfe2  call    memset_0
0x18001dfe7  xor     eax, eax
0x18001dfe9  mov     r15d, eax
0x18001dfec  mov     [rbp+210h+var_280], rax
0x18001dff0  mov     [rsp+310h+var_2E8], rax
0x18001dff5  mov     esi, eax
0x18001dff7  mov     [rsp+310h+var_2D8], rax
0x18001dffc  mov     [rsp+310h+var_298], eax
0x18001e000  xorps   xmm0, xmm0
0x18001e003  movdqu  xmmword ptr [rbp+210h+var_290], xmm0
0x18001e008  test    r12, r12
0x18001e00b  jz      short loc_18001E011
0x18001e00d  mov     [r12], rax
0x18001e011  test    r14, r14
0x18001e014  jz      short loc_18001E019
0x18001e016  mov     [r14], rax
0x18001e019  xor     r14d, r14d
0x18001e01c  mov     eax, 0CC5h
0x18001e021  test    rdi, rdi
0x18001e024  jnz     short loc_18001E039
0x18001e026  mov     edi, 80070057h
0x18001e02b  mov     [rsp+310h+var_2D0], edi
0x18001e02f  mov     [rsp+310h+var_2CA], ax
0x18001e034  jmp     loc_18001E39B
0x18001e039  mov     [rsp+310h+var_2CC], ax
0x18001e03e  mov     eax, 0CC6h
0x18001e043  test    r12, r12
0x18001e046  jz      short loc_18001E026
0x18001e048  mov     [rsp+310h+var_2D0], r14d
0x18001e04d  mov     [rsp+310h+var_2CC], ax
0x18001e052  mov     r8d, 104h; unsigned int
0x18001e058  lea     rdx, [rbp+210h+szVolumeName]; lpszVolumeName
0x18001e05c  mov     rcx, rdi; Src
0x18001e05f  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x18001e064  test    eax, eax
0x18001e066  jns     short loc_18001E074
0x18001e068  mov     edi, 89000001h
0x18001e06d  mov     eax, 0CCCh
0x18001e072  jmp     short loc_18001E02B
0x18001e074  mov     rdx, [r13+68h]; struct CDfVolumeList *
0x18001e078  mov     rcx, r13; this
0x18001e07b  call    ?_RefreshVolumeList@CDefragEngine@@AEAAJPEAVCDfVolumeList@@@Z; CDefragEngine::_RefreshVolumeList(CDfVolumeList *)
0x18001e080  lea     rax, [r13+40h]
0x18001e084  mov     [rbp+210h+lpCriticalSection], rax
0x18001e088  mov     rcx, rax; lpCriticalSection
0x18001e08b  call    cs:__imp_EnterCriticalSection
0x18001e091  mov     rcx, [r13+68h]
0x18001e095  test    rcx, rcx
0x18001e098  jnz     short loc_18001E0AD
0x18001e09a  mov     edi, 80070057h
0x18001e09f  mov     [rsp+310h+var_2D0], edi
0x18001e0a3  mov     eax, 0CDCh
0x18001e0a8  jmp     loc_18001E388
0x18001e0ad  mov     [rbp+210h+var_290+8], rcx
0x18001e0b1  lock inc dword ptr [rcx+28h]
0x18001e0b5  mov     eax, [rcx]
0x18001e0b7  mov     [rsp+310h+var_298], eax
0x18001e0bb  lea     rdx, [rcx+8]
0x18001e0bf  mov     [rbp+210h+var_290], rdx
0x18001e0c3  mov     [rsp+310h+var_2D0], r14d
0x18001e0c8  mov     eax, 0CDCh
0x18001e0cd  mov     [rsp+310h+var_2CC], ax
0x18001e0d2  test    rdx, rdx
0x18001e0d5  jz      loc_18001E37B
0x18001e0db  mov     eax, [rcx]
0x18001e0dd  mov     [rsp+310h+var_298], eax
0x18001e0e1  mov     [rbp+210h+var_290], rdx
0x18001e0e5  mov     [rsp+310h+var_2D0], r14d
0x18001e0ea  mov     eax, 0CDEh
0x18001e0ef  mov     [rsp+310h+var_2CC], ax
0x18001e0f4  lea     rdx, [rsp+310h+var_2E8]
0x18001e0f9  lea     rcx, [rsp+310h+var_298]
0x18001e0fe  call    ?Next@CSxIter@?$CSxList@VCDfVolumeList@@VCDfVolumeListItem@@@@QEAAJPEAPEAVCDfVolumeListItem@@@Z; CSxList<CDfVolumeList,CDfVolumeListItem>::CSxIter::Next(CDfVolumeListItem * *)
0x18001e103  mov     [rsp+310h+var_2D0], eax
0x18001e107  mov     ecx, 0CE0h
0x18001e10c  test    eax, eax
0x18001e10e  jns     short loc_18001E11A
0x18001e110  mov     [rsp+310h+var_2CA], cx
0x18001e115  jmp     loc_18001E38D
0x18001e11a  mov     r12d, r14d
0x18001e11d  mov     [rsp+310h+var_2CC], cx
0x18001e122  cmp     eax, 1
0x18001e125  jz      loc_18001E244
0x18001e12b  test    r12d, r12d
0x18001e12e  jnz     loc_18001E244
0x18001e134  mov     r14, [rsp+310h+var_2E8]
0x18001e139  mov     rdi, [r14+8]
0x18001e13d  test    rdi, rdi
0x18001e140  jz      short loc_18001E152
0x18001e142  mov     rax, [rdi]
0x18001e145  mov     rcx, rdi
0x18001e148  mov     rax, [rax+8]
0x18001e14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e151  nop
0x18001e152  test    r15, r15
0x18001e155  jz      short loc_18001E16F
0x18001e157  mov     [rbp+210h+var_280], 0
0x18001e15f  mov     rax, [r15]
0x18001e162  mov     rcx, r15
0x18001e165  mov     rax, [rax+10h]
0x18001e169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e16e  nop
0x18001e16f  mov     r15, rdi
0x18001e172  mov     [rbp+210h+var_280], rdi
0x18001e176  test    rdi, rdi
0x18001e179  jz      loc_18001E200
0x18001e17f  mov     rax, [rdi]
0x18001e182  lea     r8, [rsp+310h+var_2E0]
0x18001e187  lea     rdx, [rbp+210h+szVolumeName]
0x18001e18b  mov     rcx, rdi
0x18001e18e  mov     rax, [rax+88h]
0x18001e195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e19a  test    eax, eax
0x18001e19c  js      short loc_18001E200
0x18001e19e  cmp     [rsp+310h+var_2E0], 0
0x18001e1a3  jnz     short loc_18001E200
0x18001e1a5  mov     r12d, 1
0x18001e1ab  mov     rax, [rdi]
0x18001e1ae  mov     rcx, rdi
0x18001e1b1  mov     rax, [rax+8]
0x18001e1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ba  nop
0x18001e1bb  test    rbx, rbx
0x18001e1be  jz      short loc_18001E1D9
0x18001e1c0  mov     [rsp+310h+var_2F0], 0
0x18001e1c9  mov     rax, [rbx]
0x18001e1cc  mov     rcx, rbx
0x18001e1cf  mov     rax, [rax+10h]
0x18001e1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1d8  nop
0x18001e1d9  mov     rbx, rdi
0x18001e1dc  mov     [rsp+310h+var_2F0], rbx
0x18001e1e1  test    r14, r14
0x18001e1e4  jz      short loc_18001E1EB
0x18001e1e6  lock inc dword ptr [r14+4]
0x18001e1eb  test    rsi, rsi
0x18001e1ee  jz      short loc_18001E1F8
0x18001e1f0  mov     rcx, rsi; this
0x18001e1f3  call    ?Release@CDfVolumeListItem@@QEAAKXZ; CDfVolumeListItem::Release(void)
0x18001e1f8  mov     rsi, r14
0x18001e1fb  mov     [rsp+310h+var_2D8], r14
0x18001e200  test    r14, r14
0x18001e203  jz      short loc_18001E216
0x18001e205  mov     [rsp+310h+var_2E8], 0
0x18001e20e  mov     rcx, r14; this
0x18001e211  call    ?Release@CDfVolumeListItem@@QEAAKXZ; CDfVolumeListItem::Release(void)
0x18001e216  lea     rdx, [rsp+310h+var_2E8]
0x18001e21b  lea     rcx, [rsp+310h+var_298]
0x18001e220  call    ?Next@CSxIter@?$CSxList@VCDfVolumeList@@VCDfVolumeListItem@@@@QEAAJPEAPEAVCDfVolumeListItem@@@Z; CSxList<CDfVolumeList,CDfVolumeListItem>::CSxIter::Next(CDfVolumeListItem * *)
0x18001e225  mov     [rsp+310h+var_2D0], eax
0x18001e229  xor     r14d, r14d
0x18001e22c  test    eax, eax
0x18001e22e  js      short loc_18001E23A
0x18001e230  mov     ecx, 0CF7h
0x18001e235  jmp     loc_18001E11D
0x18001e23a  mov     eax, 0CF7h
0x18001e23f  jmp     loc_18001E388
0x18001e244  mov     rcx, [rsp+310h+var_2E8]; this
0x18001e249  test    rcx, rcx
0x18001e24c  jz      short loc_18001E258
0x18001e24e  mov     [rsp+310h+var_2E8], r14
0x18001e253  call    ?Release@CDfVolumeListItem@@QEAAKXZ; CDfVolumeListItem::Release(void)
0x18001e258  mov     rcx, [rbp+210h+var_290+8]; this
0x18001e25c  test    rcx, rcx
0x18001e25f  jz      short loc_18001E26A
0x18001e261  call    ?Release@CDfVolumeList@@QEAAKXZ; CDfVolumeList::Release(void)
0x18001e266  mov     [rbp+210h+var_290+8], r14
0x18001e26a  mov     [rbp+210h+var_290], r14
0x18001e26e  mov     [rsp+310h+var_298], r14d
0x18001e273  test    r12d, r12d
0x18001e276  jnz     loc_18001E353
0x18001e27c  test    rbx, rbx
0x18001e27f  jz      short loc_18001E296
0x18001e281  mov     [rsp+310h+var_2F0], r14
0x18001e286  mov     rax, [rbx]
0x18001e289  mov     rcx, rbx
0x18001e28c  mov     rax, [rax+10h]
0x18001e290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e295  nop
0x18001e296  lea     r9, [rsp+310h+var_2F0]; struct IDefragAsyncWorker **
0x18001e29b  xor     r8d, r8d; int *
0x18001e29e  lea     rdx, [rbp+210h+szVolumeName]; unsigned __int16 *
0x18001e2a2  mov     rcx, r13; this
0x18001e2a5  call    ?_CreateAsyncForVolume@CDefragEngine@@AEAAJPEAGPEAHPEAPEAUIDefragAsyncWorker@@@Z; CDefragEngine::_CreateAsyncForVolume(ushort *,int *,IDefragAsyncWorker * *)
0x18001e2aa  mov     [rsp+310h+var_2D0], eax
0x18001e2ae  test    eax, eax
0x18001e2b0  mov     eax, 0D01h
0x18001e2b5  jns     short loc_18001E2C1
0x18001e2b7  mov     rbx, [rsp+310h+var_2F0]
0x18001e2bc  jmp     loc_18001E388
0x18001e2c1  mov     [rsp+310h+var_2CC], ax
0x18001e2c6  test    rsi, rsi
0x18001e2c9  jz      short loc_18001E2D8
0x18001e2cb  mov     [rsp+310h+var_2D8], r14
0x18001e2d0  mov     rcx, rsi; this
0x18001e2d3  call    ?Release@CDfVolumeListItem@@QEAAKXZ; CDfVolumeListItem::Release(void)
0x18001e2d8  lea     rcx, [rsp+310h+var_2D8]; struct CDfVolumeListItem **
0x18001e2dd  call    ?CreateInstance@CDfVolumeListItem@@SAJPEAPEAV1@@Z; CDfVolumeListItem::CreateInstance(CDfVolumeListItem * *)
0x18001e2e2  mov     [rsp+310h+var_2D0], eax
0x18001e2e6  mov     rbx, [rsp+310h+var_2F0]
0x18001e2eb  mov     rsi, [rsp+310h+var_2D8]
0x18001e2f0  test    eax, eax
0x18001e2f2  mov     eax, 0D04h
0x18001e2f7  js      loc_18001E388
0x18001e2fd  mov     [rsp+310h+var_2CC], ax
0x18001e302  test    rbx, rbx
0x18001e305  jz      short loc_18001E317
0x18001e307  mov     rax, [rbx]
0x18001e30a  mov     rcx, rbx
0x18001e30d  mov     rax, [rax+8]
0x18001e311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e316  nop
0x18001e317  mov     rcx, [rsi+8]
0x18001e31b  test    rcx, rcx
0x18001e31e  jz      short loc_18001E331
0x18001e320  mov     [rsi+8], r14
0x18001e324  mov     rax, [rcx]
0x18001e327  mov     rax, [rax+10h]
0x18001e32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e330  nop
0x18001e331  mov     [rsi+8], rbx
0x18001e335  mov     rdx, rsi
0x18001e338  mov     rcx, [r13+68h]
0x18001e33c  call    ?InsertTail@?$CSxList@VCDfVolumeList@@VCDfVolumeListItem@@@@QEAAJPEAVCDfVolumeListItem@@@Z; CSxList<CDfVolumeList,CDfVolumeListItem>::InsertTail(CDfVolumeListItem *)
0x18001e341  mov     [rsp+310h+var_2D0], eax
0x18001e345  test    eax, eax
0x18001e347  mov     eax, 0D0Ah
0x18001e34c  js      short loc_18001E388
0x18001e34e  mov     [rsp+310h+var_2CC], ax
0x18001e353  mov     rax, [rbp+210h+var_278]
0x18001e357  mov     [rax], rbx
0x18001e35a  mov     rbx, r14
0x18001e35d  mov     [rsp+310h+var_2F0], rbx
0x18001e362  mov     r14, [rbp+210h+var_270]
0x18001e366  test    r14, r14
0x18001e369  jz      short loc_18001E374
0x18001e36b  mov     [r14], rsi
0x18001e36e  xor     r14d, r14d
0x18001e371  mov     esi, r14d
0x18001e374  mov     [rsp+310h+var_2D0], r14d
0x18001e379  jmp     short loc_18001E38D
0x18001e37b  mov     [rsp+310h+var_2D0], 8000FFFFh
0x18001e383  mov     eax, 0CDEh
0x18001e388  mov     [rsp+310h+var_2CA], ax
0x18001e38d  mov     rcx, [rbp+210h+lpCriticalSection]; lpCriticalSection
0x18001e391  call    cs:__imp_LeaveCriticalSection
0x18001e397  mov     edi, [rsp+310h+var_2D0]
0x18001e39b  mov     rcx, [rbp+210h+var_290+8]; this
0x18001e39f  test    rcx, rcx
0x18001e3a2  jz      short loc_18001E3AA
0x18001e3a4  call    ?Release@CDfVolumeList@@QEAAKXZ; CDfVolumeList::Release(void)
0x18001e3a9  nop
0x18001e3aa  test    rsi, rsi
0x18001e3ad  jz      short loc_18001E3B8
0x18001e3af  mov     rcx, rsi; this
0x18001e3b2  call    ?Release@CDfVolumeListItem@@QEAAKXZ; CDfVolumeListItem::Release(void)
0x18001e3b7  nop
0x18001e3b8  mov     rcx, [rsp+310h+var_2E8]; this
0x18001e3bd  test    rcx, rcx
0x18001e3c0  jz      short loc_18001E3C8
0x18001e3c2  call    ?Release@CDfVolumeListItem@@QEAAKXZ; CDfVolumeListItem::Release(void)
0x18001e3c7  nop
0x18001e3c8  test    r15, r15
0x18001e3cb  jz      short loc_18001E3DD
0x18001e3cd  mov     rax, [r15]
0x18001e3d0  mov     rcx, r15
  ... truncated ...
```
