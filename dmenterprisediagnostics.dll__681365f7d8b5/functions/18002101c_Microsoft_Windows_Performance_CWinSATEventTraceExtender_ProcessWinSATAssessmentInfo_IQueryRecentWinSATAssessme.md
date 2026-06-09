# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002101c`
- end: `0x18002147d`
- name: `?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z`
- size: `1121`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *__hidden this, struct IQueryRecentWinSATAssessment *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002, unsigned __int8, const unsigned __int16 *, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021484`

## callees

- `0x180001800`
- `0x1800023e0`
- `0x1800029d5`
- `0x180007e30`
- `0x180007ea4`
- `0x18000938c`
- `0x180009cd8`
- `0x18000c6e4`
- `0x18000c980`
- `0x18001f9e8`
- `0x18002101c`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002126e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021331`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002126e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021331`
- `OLEAUT32!__imp_SysFreeString` at `0x1800210b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800211c1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002120e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800210b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800211c1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002120e`

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
  _QWORD *v13; // rax
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
  __int64 v28; // [rsp+58h] [rbp-E0h] BYREF
  __int64 v29; // [rsp+60h] [rbp-D8h] BYREF
  void *Src; // [rsp+68h] [rbp-D0h] BYREF
  BSTR v31; // [rsp+70h] [rbp-C8h] BYREF
  BSTR bstrString[3]; // [rsp+78h] [rbp-C0h] BYREF
  _WORD v33[2]; // [rsp+90h] [rbp-A8h] BYREF
  char v34; // [rsp+94h] [rbp-A4h]
  char v35; // [rsp+95h] [rbp-A3h]
  __int16 v36; // [rsp+96h] [rbp-A2h]
  union _LARGE_INTEGER v37; // [rsp+A0h] [rbp-98h]
  struct _GUID v38; // [rsp+A8h] [rbp-90h]
  void *v39; // [rsp+D8h] [rbp-60h]
  unsigned int v40; // [rsp+E0h] [rbp-58h]
  unsigned int v41; // [rsp+E4h] [rbp-54h]

  if ( !a2 )
    return 2147500035LL;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&Src);
  v29 = 0;
  v28 = 0;
  get_XML = a2->lpVtbl->get_XML;
  v13 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a5);
  v14 = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, _QWORD, _QWORD, __int64 *))get_XML)(
          a2,
          *v13,
          0,
          &v29);
  SysFreeString(bstrString[0]);
  if ( v14 < 0 )
    goto LABEL_4;
  if ( !v29 )
    goto LABEL_6;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 72LL))(v29, &v28);
  if ( v14 < 0 )
  {
LABEL_4:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    ATL::CStringData::Release((ATL::CStringData *)((char *)Src - 24));
    return (unsigned int)v14;
  }
  if ( !v28 )
  {
LABEL_6:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    ATL::CStringData::Release((ATL::CStringData *)((char *)Src - 24));
    return 1;
  }
  v31 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v28 + 272LL))(v28, &v31);
  if ( v15 < 0 )
  {
    SysFreeString(v31);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    ATL::CStringData::Release((ATL::CStringData *)((char *)Src - 24));
    return (unsigned int)v15;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&Src, v31);
  SysFreeString(v31);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  v16 = Src;
  v17 = (ATL::CStringData *)((char *)Src - 24);
  v18 = 2 * *((_DWORD *)Src - 4) + 2;
  if ( v18 >= 8 && !*((_BYTE *)this + 33) )
  {
    v19 = 2 * *((_DWORD *)Src - 4) - 6;
    v20 = (void **)((char *)this + 72);
    if ( *((_DWORD *)this + 20) < v19 )
    {
      free(*v20);
      *v20 = 0;
      *((_DWORD *)this + 20) = 0;
      if ( !(unsigned __int8)ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(
                               (char *)this + 72,
                               v18) )
      {
LABEL_27:
        v21 = -2147024882;
        goto LABEL_32;
      }
      *((_DWORD *)this + 20) = v18;
    }
    if ( !(unsigned int)Performance::RtlCompression::CRtlCompressBuffer::operator()(
                          (int)this + 40,
                          *(_DWORD *)v20 + 8,
                          (_DWORD)v16,
                          v18,
                          (__int64)*v20 + 8,
                          v19) )
    {
      switch ( a4 )
      {
        case ' ':
          a4 = 33;
          goto LABEL_24;
        case '"':
          a4 = 35;
          goto LABEL_24;
        case '$':
          a4 = 37;
LABEL_24:
          v22 = *v20;
          *v22 = a3;
          v22[1] = v18;
          v23 = 8;
          goto LABEL_30;
      }
      v21 = -2147467263;
LABEL_32:
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
    if ( !(unsigned __int8)ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(
                             (char *)this + 88,
                             v24) )
      goto LABEL_27;
    *((_DWORD *)this + 24) = v24;
  }
  v25 = *v20;
  *v25 = a3;
  memcpy_0(v25 + 1, v16, v18);
  v23 = *((_DWORD *)this + 24);
LABEL_30:
  v26 = *v20;
  if ( v23 >= 0xFFFF )
  {
    v21 = 1;
    goto LABEL_32;
  }
  memset_0(v33, 0, 0x58u);
  v33[0] = a8;
  v37 = a6;
  v38 = WinSATAssessmentGuid;
  v34 = a4;
  v36 = 0;
  v35 = 0;
  v39 = v26;
  v40 = v23;
  v41 = a7;
  (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
    *((_QWORD *)this + 2),
    v33,
    0,
    0);
  ATL::CStringData::Release(v17);
  return 0;
}

```

## disassembly

```asm
0x18002101c  push    rbx
0x18002101e  push    rsi
0x18002101f  push    rdi
0x180021020  push    r12
0x180021022  push    r13
0x180021024  push    r14
0x180021026  push    r15
0x180021028  sub     rsp, 100h
0x18002102f  mov     rax, cs:__security_cookie
0x180021036  xor     rax, rsp
0x180021039  mov     [rsp+138h+var_48], rax
0x180021041  mov     r15b, r9b
0x180021044  mov     [rsp+138h+var_E4], r8d
0x180021049  mov     rbx, rdx
0x18002104c  mov     r14, rcx
0x18002104f  mov     rdi, [rsp+138h+arg_20]
0x180021057  xor     r12d, r12d
0x18002105a  test    rdx, rdx
0x18002105d  jnz     short loc_180021069
0x18002105f  mov     eax, 80004003h
0x180021064  jmp     loc_180021459
0x180021069  lea     rcx, [rsp+138h+Src]
0x18002106e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180021073  nop
0x180021074  mov     [rsp+138h+var_D8], r12
0x180021079  mov     [rsp+138h+var_E0], r12
0x18002107e  mov     rax, [rbx]
0x180021081  mov     rsi, [rax+38h]
0x180021085  mov     rdx, rdi; unsigned __int16 *
0x180021088  lea     rcx, [rsp+138h+bstrString]; this
0x18002108d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180021092  nop
0x180021093  lea     r9, [rsp+138h+var_D8]
0x180021098  xor     r8d, r8d
0x18002109b  mov     rdx, [rax]
0x18002109e  mov     rcx, rbx
0x1800210a1  mov     rax, rsi
0x1800210a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210a9  mov     ebx, eax
0x1800210ab  mov     rcx, [rsp+138h+bstrString]; bstrString
0x1800210b0  call    cs:__imp_SysFreeString
0x1800210b7  nop     dword ptr [rax+rax+00h]
0x1800210bc  test    ebx, ebx
0x1800210be  jns     short loc_1800210EB
0x1800210c0  lea     rcx, [rsp+138h+var_E0]
0x1800210c5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800210ca  nop
0x1800210cb  lea     rcx, [rsp+138h+var_D8]
0x1800210d0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800210d5  nop
0x1800210d6  mov     rcx, [rsp+138h+Src]
0x1800210db  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800210df  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800210e4  mov     eax, ebx
0x1800210e6  jmp     loc_180021459
0x1800210eb  mov     rcx, [rsp+138h+var_D8]
0x1800210f0  test    rcx, rcx
0x1800210f3  jnz     short loc_180021123
0x1800210f5  lea     rcx, [rsp+138h+var_E0]
0x1800210fa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800210ff  nop
0x180021100  lea     rcx, [rsp+138h+var_D8]
0x180021105  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002110a  nop
0x18002110b  mov     rcx, [rsp+138h+Src]
0x180021110  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180021114  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021119  mov     eax, 1
0x18002111e  jmp     loc_180021459
0x180021123  mov     rax, [rcx]
0x180021126  lea     rdx, [rsp+138h+var_E0]
0x18002112b  mov     rax, [rax+48h]
0x18002112f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021134  mov     ebx, eax
0x180021136  test    eax, eax
0x180021138  jns     short loc_180021165
0x18002113a  lea     rcx, [rsp+138h+var_E0]
0x18002113f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021144  nop
0x180021145  lea     rcx, [rsp+138h+var_D8]
0x18002114a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002114f  nop
0x180021150  mov     rcx, [rsp+138h+Src]
0x180021155  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180021159  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002115e  mov     eax, ebx
0x180021160  jmp     loc_180021459
0x180021165  mov     rcx, [rsp+138h+var_E0]
0x18002116a  test    rcx, rcx
0x18002116d  jnz     short loc_18002119D
0x18002116f  lea     rcx, [rsp+138h+var_E0]
0x180021174  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021179  nop
0x18002117a  lea     rcx, [rsp+138h+var_D8]
0x18002117f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021184  nop
0x180021185  mov     rcx, [rsp+138h+Src]
0x18002118a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002118e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021193  mov     eax, 1
0x180021198  jmp     loc_180021459
0x18002119d  mov     [rsp+138h+var_C8], r12
0x1800211a2  mov     rax, [rcx]
0x1800211a5  lea     rdx, [rsp+138h+var_C8]
0x1800211aa  mov     rax, [rax+110h]
0x1800211b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211b6  mov     ebx, eax
0x1800211b8  test    eax, eax
0x1800211ba  jns     short loc_1800211F9
0x1800211bc  mov     rcx, [rsp+138h+var_C8]; bstrString
0x1800211c1  call    cs:__imp_SysFreeString
0x1800211c8  nop     dword ptr [rax+rax+00h]
0x1800211cd  nop
0x1800211ce  lea     rcx, [rsp+138h+var_E0]
0x1800211d3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800211d8  nop
0x1800211d9  lea     rcx, [rsp+138h+var_D8]
0x1800211de  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800211e3  nop
0x1800211e4  mov     rcx, [rsp+138h+Src]
0x1800211e9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800211ed  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800211f2  mov     eax, ebx
0x1800211f4  jmp     loc_180021459
0x1800211f9  mov     rdx, [rsp+138h+var_C8]
0x1800211fe  lea     rcx, [rsp+138h+Src]
0x180021203  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180021208  nop
0x180021209  mov     rcx, [rsp+138h+var_C8]; bstrString
0x18002120e  call    cs:__imp_SysFreeString
0x180021215  nop     dword ptr [rax+rax+00h]
0x18002121a  nop
0x18002121b  lea     rcx, [rsp+138h+var_E0]
0x180021220  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021225  nop
0x180021226  lea     rcx, [rsp+138h+var_D8]
0x18002122b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021230  nop
0x180021231  mov     rbx, [rsp+138h+Src]
0x180021236  lea     r13, [rbx-18h]
0x18002123a  mov     eax, [r13+8]
0x18002123e  lea     edi, ds:2[rax*2]
0x180021245  mov     [rsp+138h+var_E8], r12d
0x18002124a  cmp     edi, 8
0x18002124d  jb      loc_180021320
0x180021253  cmp     [r14+21h], r12b
0x180021257  jnz     loc_180021320
0x18002125d  lea     r12d, [rdi-8]
0x180021261  lea     rsi, [r14+48h]
0x180021265  cmp     [rsi+8], r12d
0x180021269  jnb     short loc_18002129E
0x18002126b  mov     rcx, [rsi]; Block
0x18002126e  call    cs:__imp_free
0x180021275  nop     dword ptr [rax+rax+00h]
0x18002127a  mov     qword ptr [rsi], 0
0x180021281  mov     dword ptr [rsi+8], 0
0x180021288  mov     edx, edi
0x18002128a  mov     rcx, rsi
0x18002128d  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x180021292  test    al, al
0x180021294  jz      loc_18002135A
0x18002129a  mov     [r14+50h], edi
0x18002129e  mov     rdx, [rsi]
0x1800212a1  add     rdx, 8
0x1800212a5  lea     rcx, [r14+28h]
0x1800212a9  mov     rax, [r14+38h]
0x1800212ad  mov     [rsp+138h+var_F8], rax
0x1800212b2  lea     rax, [rsp+138h+var_E8]
0x1800212b7  mov     [rsp+138h+var_100], rax
0x1800212bc  mov     [rsp+138h+var_110], r12d
0x1800212c1  mov     [rsp+138h+var_118], rdx
0x1800212c6  mov     r9d, edi
0x1800212c9  mov     r8, rbx
0x1800212cc  call    ??RCRtlCompressBuffer@RtlCompression@Performance@@QEBAJGPEBXKPEAXKKPEAK1@Z; Performance::RtlCompression::CRtlCompressBuffer::operator()(ushort,void const *,ulong,void *,ulong,ulong,ulong *,void *)
0x1800212d1  test    eax, eax
0x1800212d3  jnz     short loc_180021320
0x1800212d5  mov     eax, [rsp+138h+var_E8]
0x1800212d9  cmp     eax, r12d
0x1800212dc  ja      short loc_180021320
0x1800212de  add     eax, 8
0x1800212e1  mov     [rsp+138h+var_E8], eax
0x1800212e5  cmp     r15b, 20h ; ' '
0x1800212e9  jz      short loc_18002130B
0x1800212eb  cmp     r15b, 22h ; '"'
0x1800212ef  jz      short loc_180021306
0x1800212f1  cmp     r15b, 24h ; '$'
0x1800212f5  jnz     short loc_1800212FC
0x1800212f7  mov     r15b, 25h ; '%'
0x1800212fa  jmp     short loc_18002130E
0x1800212fc  mov     ebx, 80004001h
0x180021301  jmp     loc_180021391
0x180021306  mov     r15b, 23h ; '#'
0x180021309  jmp     short loc_18002130E
0x18002130b  mov     r15b, 21h ; '!'
0x18002130e  mov     rax, [rsi]
0x180021311  mov     edx, [rsp+138h+var_E4]
0x180021315  mov     [rax], edx
0x180021317  mov     [rax+4], edi
0x18002131a  mov     ebx, [rsp+138h+var_E8]
0x18002131e  jmp     short loc_180021381
0x180021320  lea     r12d, [rdi+4]
0x180021324  lea     rsi, [r14+58h]
0x180021328  cmp     [rsi+8], r12d
0x18002132c  jnb     short loc_180021365
0x18002132e  mov     rcx, [rsi]; Block
0x180021331  call    cs:__imp_free
0x180021338  nop     dword ptr [rax+rax+00h]
0x18002133d  mov     qword ptr [rsi], 0
0x180021344  mov     dword ptr [rsi+8], 0
0x18002134b  mov     edx, r12d
0x18002134e  mov     rcx, rsi
0x180021351  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x180021356  test    al, al
0x180021358  jnz     short loc_180021361
0x18002135a  mov     ebx, 8007000Eh
0x18002135f  jmp     short loc_180021391
0x180021361  mov     [r14+60h], r12d
0x180021365  mov     rcx, [rsi]
0x180021368  mov     edx, [rsp+138h+var_E4]
0x18002136c  mov     [rcx], edx
0x18002136e  mov     r8d, edi; Size
0x180021371  add     rcx, 4; void *
0x180021375  mov     rdx, rbx; Src
0x180021378  call    memcpy_0
0x18002137d  mov     ebx, [r14+60h]
0x180021381  mov     rdi, [rsi]
0x180021384  cmp     ebx, 0FFFFh
0x18002138a  jb      short loc_1800213A0
0x18002138c  mov     ebx, 1
0x180021391  mov     rcx, r13; this
0x180021394  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021399  mov     eax, ebx
0x18002139b  jmp     loc_180021459
0x1800213a0  xor     edx, edx; Val
0x1800213a2  lea     r8d, [rdx+58h]; Size
0x1800213a6  lea     rcx, [rsp+138h+var_A8]; void *
0x1800213ae  call    memset_0
0x1800213b3  movzx   eax, word ptr [rsp+138h+arg_38]
0x1800213bb  mov     [rsp+138h+var_A8], ax
0x1800213c3  mov     rax, qword ptr [rsp+138h+arg_28]
0x1800213cb  mov     [rsp+138h+var_98], rax
0x1800213d3  movups  xmm0, xmmword ptr cs:WinSATAssessmentGuid.Data1
0x1800213da  movdqu  [rsp+138h+var_90], xmm0
0x1800213e3  mov     [rsp+138h+var_A4], r15b
0x1800213eb  xor     eax, eax
0x1800213ed  mov     [rsp+138h+var_A2], ax
0x1800213f5  mov     [rsp+138h+var_A3], al
0x1800213fc  mov     [rsp+138h+var_60], rdi
0x180021404  mov     [rsp+138h+var_58], ebx
0x18002140b  mov     eax, [rsp+138h+arg_30]
0x180021412  mov     [rsp+138h+var_54], eax
0x180021419  mov     rcx, [r14+10h]
0x18002141d  mov     rax, [rcx]
0x180021420  xor     r9d, r9d
0x180021423  xor     r8d, r8d
0x180021426  lea     rdx, [rsp+138h+var_A8]
0x18002142e  mov     rax, [rax+0C0h]
0x180021435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002143a  nop
0x18002143b  mov     rcx, r13; this
0x18002143e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021443  xor     eax, eax
0x180021445  jmp     short loc_180021459
0x180021447  mov     rcx, [rsp+138h+Src]
0x18002144c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180021450  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021455  mov     eax, [rsp+138h+var_E4]
0x180021459  mov     rcx, [rsp+138h+var_48]
0x180021461  xor     rcx, rsp; StackCookie
0x180021464  call    __security_check_cookie
0x180021469  add     rsp, 100h
0x180021470  pop     r15
0x180021472  pop     r14
0x180021474  pop     r13
0x180021476  pop     r12
0x180021478  pop     rdi
0x180021479  pop     rsi
0x18002147a  pop     rbx
0x18002147b  retn
```
