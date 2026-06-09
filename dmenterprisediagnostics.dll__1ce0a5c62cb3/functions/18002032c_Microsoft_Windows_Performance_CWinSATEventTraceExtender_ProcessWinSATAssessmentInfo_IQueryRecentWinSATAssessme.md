# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002032c`
- end: `0x18002076e`
- name: `?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z`
- size: `1090`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *__hidden this, struct IQueryRecentWinSATAssessment *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002, unsigned __int8, const unsigned __int16 *, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020774`

## callees

- `0x1800017e0`
- `0x1800023c0`
- `0x1800029b5`
- `0x180007ac8`
- `0x180007b34`
- `0x180008f10`
- `0x180009810`
- `0x18000c120`
- `0x18000c3b0`
- `0x18001ee04`
- `0x18002032c`
- `0x180026010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002056c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020629`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002056c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020629`
- `OLEAUT32!__imp_SysFreeString` at `0x1800203c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800204cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180020512`
- `OLEAUT32!__imp_SysFreeString` at `0x1800203c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800204cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180020512`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this,
        struct IQueryRecentWinSATAssessment *a2,
        enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 a3,
        char a4,
        unsigned __int16 *a5,
        union _LARGE_INTEGER a6,
        unsigned int a7,
        __int16 a8)
{
  HRESULT (__stdcall *get_XML)(IQueryRecentWinSATAssessment *, BSTR, BSTR, IXMLDOMNodeList **); // rsi
  ATL::CComBSTR *v13; // rax
  int v14; // ebx
  int v15; // ebx
  void *v16; // rbx
  ATL::CStringData *v17; // r13
  unsigned int v18; // edi
  unsigned int v19; // r12d
  void **v20; // rsi
  unsigned int v21; // ebx
  _DWORD *v22; // rax
  unsigned int v23; // ebx
  unsigned int v24; // r12d
  _DWORD *v25; // rcx
  void *v26; // rdi
  int v27; // [rsp+30h] [rbp-108h]
  unsigned int v28; // [rsp+50h] [rbp-E8h] BYREF
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v29; // [rsp+54h] [rbp-E4h]
  __int64 v30; // [rsp+58h] [rbp-E0h] BYREF
  __int64 v31; // [rsp+60h] [rbp-D8h] BYREF
  void *Src; // [rsp+68h] [rbp-D0h] BYREF
  BSTR v33; // [rsp+70h] [rbp-C8h] BYREF
  BSTR bstrString[3]; // [rsp+78h] [rbp-C0h] BYREF
  _WORD v35[2]; // [rsp+90h] [rbp-A8h] BYREF
  char v36; // [rsp+94h] [rbp-A4h]
  char v37; // [rsp+95h] [rbp-A3h]
  __int16 v38; // [rsp+96h] [rbp-A2h]
  union _LARGE_INTEGER v39; // [rsp+A0h] [rbp-98h]
  struct _GUID v40; // [rsp+A8h] [rbp-90h]
  void *v41; // [rsp+D8h] [rbp-60h]
  unsigned int v42; // [rsp+E0h] [rbp-58h]
  unsigned int v43; // [rsp+E4h] [rbp-54h]

  v29 = a3;
  if ( !a2 )
    return 2147500035LL;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&Src);
  v31 = 0;
  v30 = 0;
  get_XML = a2->lpVtbl->get_XML;
  v13 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a5);
  v14 = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, _QWORD, _QWORD, __int64 *))get_XML)(
          a2,
          *(_QWORD *)v13,
          0,
          &v31);
  SysFreeString(bstrString[0]);
  if ( v14 < 0 )
    goto LABEL_4;
  if ( !v31 )
    goto LABEL_6;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 72LL))(v31, &v30);
  if ( v14 < 0 )
  {
LABEL_4:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    ATL::CStringData::Release((ATL::CStringData *)((char *)Src - 24));
    return (unsigned int)v14;
  }
  if ( !v30 )
  {
LABEL_6:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    ATL::CStringData::Release((ATL::CStringData *)((char *)Src - 24));
    return 1;
  }
  v33 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v30 + 272LL))(v30, &v33);
  if ( v15 < 0 )
  {
    SysFreeString(v33);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    ATL::CStringData::Release((ATL::CStringData *)((char *)Src - 24));
    return (unsigned int)v15;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&Src, v33);
  SysFreeString(v33);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  v16 = Src;
  v17 = (ATL::CStringData *)((char *)Src - 24);
  v18 = 2 * *((_DWORD *)Src - 4) + 2;
  v28 = 0;
  if ( v18 >= 8 && !*((_BYTE *)this + 33) )
  {
    v19 = v18 - 8;
    v20 = (void **)((char *)this + 72);
    if ( *((_DWORD *)this + 20) < v18 - 8 )
    {
      free(*v20);
      *v20 = 0;
      *((_DWORD *)this + 20) = 0;
      if ( !ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes((_QWORD *)this + 9, v18) )
      {
LABEL_28:
        v21 = -2147024882;
        goto LABEL_33;
      }
      *((_DWORD *)this + 20) = v18;
    }
    if ( !(unsigned int)Performance::RtlCompression::CRtlCompressBuffer::operator()(
                          (__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, int, int, __int64, __int64))this
                        + 5,
                          (__int64)*v20 + 8,
                          (__int64)v16,
                          v18,
                          (__int64)*v20 + 8,
                          v19,
                          v27,
                          (__int64)&v28,
                          *((_QWORD *)this + 7))
      && v28 <= v19 )
    {
      v28 += 8;
      switch ( a4 )
      {
        case ' ':
          a4 = 33;
          goto LABEL_25;
        case '"':
          a4 = 35;
          goto LABEL_25;
        case '$':
          a4 = 37;
LABEL_25:
          v22 = *v20;
          *v22 = v29;
          v22[1] = v18;
          v23 = v28;
          goto LABEL_31;
      }
      v21 = -2147467263;
LABEL_33:
      ATL::CStringData::Release(v17);
      return v21;
    }
  }
  v24 = v18 + 4;
  v20 = (void **)((char *)this + 88);
  if ( *((_DWORD *)this + 24) < v18 + 4 )
  {
    free(*v20);
    *v20 = 0;
    *((_DWORD *)this + 24) = 0;
    if ( !ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes((_QWORD *)this + 11, v24) )
      goto LABEL_28;
    *((_DWORD *)this + 24) = v24;
  }
  v25 = *v20;
  *v25 = v29;
  memcpy_0(v25 + 1, v16, v18);
  v23 = *((_DWORD *)this + 24);
LABEL_31:
  v26 = *v20;
  if ( v23 >= 0xFFFF )
  {
    v21 = 1;
    goto LABEL_33;
  }
  memset_0(v35, 0, 0x58u);
  v35[0] = a8;
  v39 = a6;
  v40 = WinSATAssessmentGuid;
  v36 = a4;
  v38 = 0;
  v37 = 0;
  v41 = v26;
  v42 = v23;
  v43 = a7;
  (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
    *((_QWORD *)this + 2),
    v35,
    0,
    0);
  ATL::CStringData::Release(v17);
  return 0;
}

```

## disassembly

```asm
0x18002032c  push    rbx
0x18002032e  push    rsi
0x18002032f  push    rdi
0x180020330  push    r12
0x180020332  push    r13
0x180020334  push    r14
0x180020336  push    r15
0x180020338  sub     rsp, 100h
0x18002033f  mov     rax, cs:__security_cookie
0x180020346  xor     rax, rsp
0x180020349  mov     [rsp+138h+var_48], rax
0x180020351  mov     r15b, r9b
0x180020354  mov     [rsp+138h+var_E4], r8d
0x180020359  mov     rbx, rdx
0x18002035c  mov     r14, rcx
0x18002035f  mov     rdi, [rsp+138h+arg_20]
0x180020367  xor     r12d, r12d
0x18002036a  test    rdx, rdx
0x18002036d  jnz     short loc_180020379
0x18002036f  mov     eax, 80004003h
0x180020374  jmp     loc_18002074B
0x180020379  lea     rcx, [rsp+138h+Src]
0x18002037e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180020383  nop
0x180020384  mov     [rsp+138h+var_D8], r12
0x180020389  mov     [rsp+138h+var_E0], r12
0x18002038e  mov     rax, [rbx]
0x180020391  mov     rsi, [rax+38h]
0x180020395  mov     rdx, rdi; unsigned __int16 *
0x180020398  lea     rcx, [rsp+138h+bstrString]; this
0x18002039d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800203a2  nop
0x1800203a3  lea     r9, [rsp+138h+var_D8]
0x1800203a8  xor     r8d, r8d
0x1800203ab  mov     rdx, [rax]
0x1800203ae  mov     rcx, rbx
0x1800203b1  mov     rax, rsi
0x1800203b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203b9  mov     ebx, eax
0x1800203bb  mov     rcx, [rsp+138h+bstrString]; bstrString
0x1800203c0  call    cs:__imp_SysFreeString
0x1800203c6  test    ebx, ebx
0x1800203c8  jns     short loc_1800203F5
0x1800203ca  lea     rcx, [rsp+138h+var_E0]
0x1800203cf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800203d4  nop
0x1800203d5  lea     rcx, [rsp+138h+var_D8]
0x1800203da  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800203df  nop
0x1800203e0  mov     rcx, [rsp+138h+Src]
0x1800203e5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800203e9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800203ee  mov     eax, ebx
0x1800203f0  jmp     loc_18002074B
0x1800203f5  mov     rcx, [rsp+138h+var_D8]
0x1800203fa  test    rcx, rcx
0x1800203fd  jnz     short loc_18002042D
0x1800203ff  lea     rcx, [rsp+138h+var_E0]
0x180020404  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020409  nop
0x18002040a  lea     rcx, [rsp+138h+var_D8]
0x18002040f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020414  nop
0x180020415  mov     rcx, [rsp+138h+Src]
0x18002041a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002041e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020423  mov     eax, 1
0x180020428  jmp     loc_18002074B
0x18002042d  mov     rax, [rcx]
0x180020430  lea     rdx, [rsp+138h+var_E0]
0x180020435  mov     rax, [rax+48h]
0x180020439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002043e  mov     ebx, eax
0x180020440  test    eax, eax
0x180020442  jns     short loc_18002046F
0x180020444  lea     rcx, [rsp+138h+var_E0]
0x180020449  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002044e  nop
0x18002044f  lea     rcx, [rsp+138h+var_D8]
0x180020454  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020459  nop
0x18002045a  mov     rcx, [rsp+138h+Src]
0x18002045f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020463  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020468  mov     eax, ebx
0x18002046a  jmp     loc_18002074B
0x18002046f  mov     rcx, [rsp+138h+var_E0]
0x180020474  test    rcx, rcx
0x180020477  jnz     short loc_1800204A7
0x180020479  lea     rcx, [rsp+138h+var_E0]
0x18002047e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020483  nop
0x180020484  lea     rcx, [rsp+138h+var_D8]
0x180020489  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002048e  nop
0x18002048f  mov     rcx, [rsp+138h+Src]
0x180020494  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020498  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002049d  mov     eax, 1
0x1800204a2  jmp     loc_18002074B
0x1800204a7  mov     [rsp+138h+var_C8], r12
0x1800204ac  mov     rax, [rcx]
0x1800204af  lea     rdx, [rsp+138h+var_C8]
0x1800204b4  mov     rax, [rax+110h]
0x1800204bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204c0  mov     ebx, eax
0x1800204c2  test    eax, eax
0x1800204c4  jns     short loc_1800204FD
0x1800204c6  mov     rcx, [rsp+138h+var_C8]; bstrString
0x1800204cb  call    cs:__imp_SysFreeString
0x1800204d1  nop
0x1800204d2  lea     rcx, [rsp+138h+var_E0]
0x1800204d7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800204dc  nop
0x1800204dd  lea     rcx, [rsp+138h+var_D8]
0x1800204e2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800204e7  nop
0x1800204e8  mov     rcx, [rsp+138h+Src]
0x1800204ed  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800204f1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800204f6  mov     eax, ebx
0x1800204f8  jmp     loc_18002074B
0x1800204fd  mov     rdx, [rsp+138h+var_C8]
0x180020502  lea     rcx, [rsp+138h+Src]
0x180020507  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18002050c  nop
0x18002050d  mov     rcx, [rsp+138h+var_C8]; bstrString
0x180020512  call    cs:__imp_SysFreeString
0x180020518  nop
0x180020519  lea     rcx, [rsp+138h+var_E0]
0x18002051e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020523  nop
0x180020524  lea     rcx, [rsp+138h+var_D8]
0x180020529  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002052e  nop
0x18002052f  mov     rbx, [rsp+138h+Src]
0x180020534  lea     r13, [rbx-18h]
0x180020538  mov     eax, [r13+8]
0x18002053c  lea     edi, ds:2[rax*2]
0x180020543  mov     [rsp+138h+var_E8], r12d
0x180020548  cmp     edi, 8
0x18002054b  jb      loc_180020618
0x180020551  cmp     [r14+21h], r12b
0x180020555  jnz     loc_180020618
0x18002055b  lea     r12d, [rdi-8]
0x18002055f  lea     rsi, [r14+48h]
0x180020563  cmp     [rsi+8], r12d
0x180020567  jnb     short loc_180020596
0x180020569  mov     rcx, [rsi]; Block
0x18002056c  call    cs:__imp_free
0x180020572  mov     qword ptr [rsi], 0
0x180020579  mov     dword ptr [rsi+8], 0
0x180020580  mov     edx, edi
0x180020582  mov     rcx, rsi
0x180020585  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x18002058a  test    al, al
0x18002058c  jz      loc_18002064C
0x180020592  mov     [r14+50h], edi
0x180020596  mov     rdx, [rsi]
0x180020599  add     rdx, 8
0x18002059d  lea     rcx, [r14+28h]
0x1800205a1  mov     rax, [r14+38h]
0x1800205a5  mov     [rsp+138h+var_F8], rax
0x1800205aa  lea     rax, [rsp+138h+var_E8]
0x1800205af  mov     [rsp+138h+var_100], rax
0x1800205b4  mov     [rsp+138h+var_110], r12d
0x1800205b9  mov     [rsp+138h+var_118], rdx
0x1800205be  mov     r9d, edi
0x1800205c1  mov     r8, rbx
0x1800205c4  call    ??RCRtlCompressBuffer@RtlCompression@Performance@@QEBAJGPEBXKPEAXKKPEAK1@Z; Performance::RtlCompression::CRtlCompressBuffer::operator()(ushort,void const *,ulong,void *,ulong,ulong,ulong *,void *)
0x1800205c9  test    eax, eax
0x1800205cb  jnz     short loc_180020618
0x1800205cd  mov     eax, [rsp+138h+var_E8]
0x1800205d1  cmp     eax, r12d
0x1800205d4  ja      short loc_180020618
0x1800205d6  add     eax, 8
0x1800205d9  mov     [rsp+138h+var_E8], eax
0x1800205dd  cmp     r15b, 20h ; ' '
0x1800205e1  jz      short loc_180020603
0x1800205e3  cmp     r15b, 22h ; '"'
0x1800205e7  jz      short loc_1800205FE
0x1800205e9  cmp     r15b, 24h ; '$'
0x1800205ed  jnz     short loc_1800205F4
0x1800205ef  mov     r15b, 25h ; '%'
0x1800205f2  jmp     short loc_180020606
0x1800205f4  mov     ebx, 80004001h
0x1800205f9  jmp     loc_180020683
0x1800205fe  mov     r15b, 23h ; '#'
0x180020601  jmp     short loc_180020606
0x180020603  mov     r15b, 21h ; '!'
0x180020606  mov     rax, [rsi]
0x180020609  mov     edx, [rsp+138h+var_E4]
0x18002060d  mov     [rax], edx
0x18002060f  mov     [rax+4], edi
0x180020612  mov     ebx, [rsp+138h+var_E8]
0x180020616  jmp     short loc_180020673
0x180020618  lea     r12d, [rdi+4]
0x18002061c  lea     rsi, [r14+58h]
0x180020620  cmp     [rsi+8], r12d
0x180020624  jnb     short loc_180020657
0x180020626  mov     rcx, [rsi]; Block
0x180020629  call    cs:__imp_free
0x18002062f  mov     qword ptr [rsi], 0
0x180020636  mov     dword ptr [rsi+8], 0
0x18002063d  mov     edx, r12d
0x180020640  mov     rcx, rsi
0x180020643  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x180020648  test    al, al
0x18002064a  jnz     short loc_180020653
0x18002064c  mov     ebx, 8007000Eh
0x180020651  jmp     short loc_180020683
0x180020653  mov     [r14+60h], r12d
0x180020657  mov     rcx, [rsi]
0x18002065a  mov     edx, [rsp+138h+var_E4]
0x18002065e  mov     [rcx], edx
0x180020660  mov     r8d, edi; Size
0x180020663  add     rcx, 4; void *
0x180020667  mov     rdx, rbx; Src
0x18002066a  call    memcpy_0
0x18002066f  mov     ebx, [r14+60h]
0x180020673  mov     rdi, [rsi]
0x180020676  cmp     ebx, 0FFFFh
0x18002067c  jb      short loc_180020692
0x18002067e  mov     ebx, 1
0x180020683  mov     rcx, r13; this
0x180020686  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002068b  mov     eax, ebx
0x18002068d  jmp     loc_18002074B
0x180020692  xor     edx, edx; Val
0x180020694  lea     r8d, [rdx+58h]; Size
0x180020698  lea     rcx, [rsp+138h+var_A8]; void *
0x1800206a0  call    memset_0
0x1800206a5  movzx   eax, word ptr [rsp+138h+arg_38]
0x1800206ad  mov     [rsp+138h+var_A8], ax
0x1800206b5  mov     rax, qword ptr [rsp+138h+arg_28]
0x1800206bd  mov     [rsp+138h+var_98], rax
0x1800206c5  movups  xmm0, xmmword ptr cs:WinSATAssessmentGuid.Data1
0x1800206cc  movdqu  [rsp+138h+var_90], xmm0
0x1800206d5  mov     [rsp+138h+var_A4], r15b
0x1800206dd  xor     eax, eax
0x1800206df  mov     [rsp+138h+var_A2], ax
0x1800206e7  mov     [rsp+138h+var_A3], al
0x1800206ee  mov     [rsp+138h+var_60], rdi
0x1800206f6  mov     [rsp+138h+var_58], ebx
0x1800206fd  mov     eax, [rsp+138h+arg_30]
0x180020704  mov     [rsp+138h+var_54], eax
0x18002070b  mov     rcx, [r14+10h]
0x18002070f  mov     rax, [rcx]
0x180020712  xor     r9d, r9d
0x180020715  xor     r8d, r8d
0x180020718  lea     rdx, [rsp+138h+var_A8]
0x180020720  mov     rax, [rax+0C0h]
0x180020727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002072c  nop
0x18002072d  mov     rcx, r13; this
0x180020730  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020735  xor     eax, eax
0x180020737  jmp     short loc_18002074B
0x180020739  mov     rcx, [rsp+138h+Src]
0x18002073e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020742  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020747  mov     eax, [rsp+138h+var_E4]
0x18002074b  mov     rcx, [rsp+138h+var_48]
0x180020753  xor     rcx, rsp; StackCookie
0x180020756  call    __security_check_cookie
0x18002075b  add     rsp, 100h
0x180020762  pop     r15
0x180020764  pop     r14
0x180020766  pop     r13
0x180020768  pop     r12
0x18002076a  pop     rdi
0x18002076b  pop     rsi
0x18002076c  pop     rbx
0x18002076d  retn
```
