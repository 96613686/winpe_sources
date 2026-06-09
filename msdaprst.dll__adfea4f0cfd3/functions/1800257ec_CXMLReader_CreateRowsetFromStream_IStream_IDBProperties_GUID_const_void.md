# CXMLReader::CreateRowsetFromStream(IStream *,IDBProperties *,_GUID const &,void * *)

- ea: `0x1800257ec`
- end: `0x180025e0f`
- name: `?CreateRowsetFromStream@CXMLReader@@QEAAJPEAUIStream@@PEAUIDBProperties@@AEBU_GUID@@PEAPEAX@Z`
- size: `1571`
- prototype: `__int64 __usercall@<rax>(CXMLReader *__hidden this@<rcx>, struct IStream *@<rdx>, struct IDBProperties *@<r8>, const struct _GUID *@<r9>, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014bd0`

## callees

- `0x180001dd4`
- `0x180002770`
- `0x180016584`
- `0x18001b008`
- `0x180020fbc`
- `0x1800257ec`
- `0x180026dc0`
- `0x180027164`
- `0x18002873c`
- `0x180029e94`
- `0x180029ecc`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180025aff`
- `ole32!CoCreateInstance` at `0x180025aff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXMLReader::CreateRowsetFromStream(
        CXMLReader *this,
        struct IStream *a2,
        struct IDBProperties *a3,
        const struct _GUID *a4,
        void **a5)
{
  unsigned int v7; // r12d
  struct IDataConvert **v8; // rcx
  int DataConvert; // eax
  int v10; // esi
  int v11; // eax
  int v12; // esi
  int v13; // eax
  unsigned int v14; // edx
  int v15; // esi
  unsigned __int8 *v16; // rax
  int v17; // eax
  int v18; // esi
  int v19; // eax
  int v20; // esi
  int v21; // eax
  int v22; // esi
  int Maps; // eax
  int v24; // esi
  _QWORD *v25; // r15
  HRESULT Instance; // eax
  int v27; // esi
  int v28; // eax
  int v29; // r14d
  int v30; // eax
  int v31; // r14d
  int v32; // eax
  int inited; // eax
  int v34; // r14d
  int v35; // eax
  int v36; // r14d
  unsigned int v37; // ebx
  int v39; // [rsp+30h] [rbp-58h]
  int v40; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v41[8]; // [rsp+48h] [rbp-40h] BYREF

  v7 = 0;
  v39 = 0;
  v41[0] = 0;
  v8 = (struct IDataConvert **)((char *)this + 488);
  try
  {
    DataConvert = GetDataConvert(v8);
    v10 = DataConvert;
    if ( DataConvert < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049DD0[0] )
          bidTraceW(off_180049208[0], 294912, off_180049DD0[0], (unsigned int)DataConvert, 288);
      }
      ThrowHR(v10);
    }
    v11 = CCollectionList::Reserve((CXMLReader *)((char *)this + 160), 5u);
    v12 = v11;
    if ( v11 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049DC8[0] )
        bidTraceW(off_180049208[0], 297984, off_180049DC8[0], (unsigned int)v11, 291);
      ThrowHR(v12);
    }
    v13 = CDynamicArray::Reserve((CXMLReader *)((char *)this + 416), 0xAu);
    v15 = v13;
    if ( v13 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049DC0[0] )
        bidTraceW(off_180049208[0], 299008, off_180049DC0[0], (unsigned int)v13, 292);
      ThrowHR(v15);
    }
    v16 = MMMAlloc(0x20u, v14);
    if ( v16 )
    {
      *((_QWORD *)v16 + 2) = 0;
      *((_QWORD *)v16 + 3) = 0;
      *(_QWORD *)v16 = 0;
      *((_QWORD *)v16 + 1) = 0;
    }
    else
    {
      v16 = 0;
    }
    *((_QWORD *)this + 51) = v16;
    if ( !v16 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049DB8[0] )
        bidTraceW(off_180049208[0], 305152, off_180049DB8[0], 2147942414LL, 298);
      ThrowHR(-2147024882);
    }
    v17 = CNodePool::Reserve((CNodePool *)v16, 0xFu);
    v18 = v17;
    if ( v17 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049DB0[0] )
        bidTraceW(off_180049208[0], 308224, off_180049DB0[0], (unsigned int)v17, 301);
      ThrowHR(v18);
    }
    v19 = CCollectionList::Reserve((CXMLReader *)((char *)this + 24), 5u);
    v20 = v19;
    if ( v19 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049DA8[0] )
        bidTraceW(off_180049208[0], 310272, off_180049DA8[0], (unsigned int)v19, 303);
      ThrowHR(v20);
    }
    v21 = CCollectionList::Reserve((CXMLReader *)((char *)this + 80), 5u);
    v22 = v21;
    if ( v21 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049DA0[0] )
        bidTraceW(off_180049208[0], 311296, off_180049DA0[0], (unsigned int)v21, 304);
      ThrowHR(v22);
    }
    Maps = CXMLReader::LoadMaps(this);
    v24 = Maps;
    if ( Maps < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049D98[0] )
        bidTraceW(off_180049208[0], 314368, off_180049D98[0], (unsigned int)Maps, 307);
      ThrowHR(v24);
    }
    v25 = (_QWORD *)((char *)this + 448);
    Instance = CoCreateInstance(
                 &GUID_f5078f31_c551_11d3_89b9_0000f81fe221,
                 0,
                 1u,
                 &GUID_d242361e_51a0_11d2_9caf_0060b0ec3d39,
                 (LPVOID *)this + 56);
    v27 = Instance;
    if ( Instance == -2147221164 || Instance == -2147467262 )
    {
      v7 = 138;
      v39 = 138;
    }
    if ( Instance < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049D90[0] )
        bidTraceW(off_180049208[0], 338944, off_180049D90[0], (unsigned int)Instance, 331);
      ThrowHR(v27);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v25 + 224LL))(*v25, 983312);
    v28 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *))(*(_QWORD *)*v25 + 128LL))(*v25, a2);
    v29 = v28;
    if ( v28 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049D88[0] )
        bidTraceW(off_180049208[0], 343040, off_180049D88[0], (unsigned int)v28, 335);
      ThrowHR(v29);
    }
    (*(void (__fastcall **)(_QWORD, CXMLReader *))(*(_QWORD *)*v25 + 24LL))(*v25, this);
    v30 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v25 + 192LL))(*v25, 0xFFFFFFFFLL);
    v31 = v30;
    if ( v30 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049D80[0] )
        bidTraceW(off_180049208[0], 347136, off_180049D80[0], (unsigned int)v30, 339);
      ThrowHR(v31);
    }
    v32 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 200LL))(*v25);
    if ( (v32 & 0xFFFFFFFA) == 0 && v32 != 4 )
    {
      inited = CXMLReader::InitRowsets(this, (char *)this + 24, a2, v41);
      v34 = inited;
      if ( inited < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049D78[0] )
          bidTraceW(off_180049208[0], 360448, off_180049D78[0], (unsigned int)inited, 352);
        ThrowHR(v34);
      }
    }
    if ( !v41[0] )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049D70[0] )
        bidTraceW(off_180049208[0], 367616, off_180049D70[0], 2147500037LL, 359);
      ThrowHR(-2147467259);
    }
    *(_QWORD *)(v41[0] + 536LL) = a3;
    ((void (__fastcall *)(struct IDBProperties *))a3->lpVtbl->AddRef)(a3);
    v35 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))v41[0])(v41[0], a4, a5);
    v36 = v35;
    if ( v35 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049D68[0] )
        bidTraceW(off_180049208[0], 374784, off_180049D68[0], (unsigned int)v35, 366);
      ThrowHR(v36);
    }
    *((_QWORD *)this + 17) = (char *)this + 24;
  }
  catch ( long v40 )
  {
    v25 = (_QWORD *)((char *)this + 448);
    v27 = v40;
    v7 = v39;
  }
  catch ( ... )
  {
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v41);
    return 2147500037LL;
  }
  if ( *v25 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 16LL))(*v25);
  v37 = Exit(v27, v7);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v41);
  return v37;
}

```

## disassembly

```asm
0x1800257ec  mov     rax, rsp
0x1800257ef  mov     [rax+20h], r9
0x1800257f3  mov     [rax+18h], r8
0x1800257f7  mov     [rax+10h], rdx
0x1800257fb  mov     [rax+8], rcx
0x1800257ff  push    rbx
0x180025800  push    rsi
0x180025801  push    rdi
0x180025802  push    r12
0x180025804  push    r13
0x180025806  push    r14
0x180025808  push    r15
0x18002580a  sub     rsp, 50h
0x18002580e  mov     r14, rdx
0x180025811  mov     rdi, rcx
0x180025814  xor     ebx, ebx
0x180025816  mov     r12d, ebx
0x180025819  mov     [rsp+88h+var_58], ebx
0x18002581d  mov     [rax-40h], rbx
0x180025821  add     rcx, 1E8h; struct IDataConvert **
0x180025828  call    ?GetDataConvert@@YAJPEAPEAUIDataConvert@@@Z; GetDataConvert(IDataConvert * *)
0x18002582d  mov     esi, eax
0x18002582f  test    eax, eax
0x180025831  jns     short loc_180025872
0x180025833  test    byte ptr cs:_bidGblFlags, 2
0x18002583a  jz      short loc_18002586B
0x18002583c  mov     rcx, cs:off_180049DD0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025843  test    rcx, rcx
0x180025846  jz      short loc_18002586B
0x180025848  mov     dword ptr [rsp+88h+ppv], 120h
0x180025850  mov     r9d, eax
0x180025853  mov     r8, cs:off_180049DD0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x18002585a  mov     edx, 48000h
0x18002585f  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025866  call    _bidTraceW
0x18002586b  mov     ecx, esi; int
0x18002586d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025872  lea     rcx, [rdi+0A0h]; this
0x180025879  mov     r15d, 5
0x18002587f  mov     edx, r15d; unsigned int
0x180025882  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x180025887  mov     esi, eax
0x180025889  test    eax, eax
0x18002588b  jns     short loc_1800258CC
0x18002588d  test    byte ptr cs:_bidGblFlags, 2
0x180025894  jz      short loc_1800258C5
0x180025896  mov     rcx, cs:off_180049DC8; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x18002589d  test    rcx, rcx
0x1800258a0  jz      short loc_1800258C5
0x1800258a2  mov     dword ptr [rsp+88h+ppv], 123h
0x1800258aa  mov     r9d, eax
0x1800258ad  mov     r8, cs:off_180049DC8; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x1800258b4  mov     edx, 48C00h
0x1800258b9  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800258c0  call    _bidTraceW
0x1800258c5  mov     ecx, esi; int
0x1800258c7  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800258cc  lea     rcx, [rdi+1A0h]; this
0x1800258d3  mov     edx, 0Ah; unsigned int
0x1800258d8  call    ?Reserve@CDynamicArray@@QEAAJK@Z; CDynamicArray::Reserve(ulong)
0x1800258dd  mov     esi, eax
0x1800258df  test    eax, eax
0x1800258e1  jns     short loc_180025922
0x1800258e3  test    byte ptr cs:_bidGblFlags, 2
0x1800258ea  jz      short loc_18002591B
0x1800258ec  mov     rcx, cs:off_180049DC0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x1800258f3  test    rcx, rcx
0x1800258f6  jz      short loc_18002591B
0x1800258f8  mov     dword ptr [rsp+88h+ppv], 124h
0x180025900  mov     r9d, eax
0x180025903  mov     r8, cs:off_180049DC0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x18002590a  mov     edx, 49000h
0x18002590f  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025916  call    _bidTraceW
0x18002591b  mov     ecx, esi; int
0x18002591d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025922  mov     ecx, 20h ; ' '; unsigned int
0x180025927  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18002592c  mov     [rsp+88h+var_50], rax
0x180025931  test    rax, rax
0x180025934  jz      short loc_180025947
0x180025936  mov     [rax+10h], rbx
0x18002593a  mov     [rax+18h], rbx
0x18002593e  mov     [rax], rbx
0x180025941  mov     [rax+8], rbx
0x180025945  jmp     short loc_18002594A
0x180025947  mov     rax, rbx
0x18002594a  mov     [rdi+198h], rax
0x180025951  test    rax, rax
0x180025954  jnz     short loc_18002599B
0x180025956  test    byte ptr cs:_bidGblFlags, 2
0x18002595d  jz      short loc_180025991
0x18002595f  mov     rax, cs:off_180049DB8; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025966  test    rax, rax
0x180025969  jz      short loc_180025991
0x18002596b  mov     dword ptr [rsp+88h+ppv], 12Ah
0x180025973  mov     r9d, 8007000Eh
0x180025979  mov     r8, cs:off_180049DB8; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025980  mov     edx, 4A800h
0x180025985  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002598c  call    _bidTraceW
0x180025991  mov     ecx, 8007000Eh; int
0x180025996  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002599b  mov     edx, 0Fh; unsigned int
0x1800259a0  mov     rcx, rax; this
0x1800259a3  call    ?Reserve@CNodePool@@QEAAJK@Z; CNodePool::Reserve(ulong)
0x1800259a8  mov     esi, eax
0x1800259aa  test    eax, eax
0x1800259ac  jns     short loc_1800259ED
0x1800259ae  test    byte ptr cs:_bidGblFlags, 2
0x1800259b5  jz      short loc_1800259E6
0x1800259b7  mov     rcx, cs:off_180049DB0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x1800259be  test    rcx, rcx
0x1800259c1  jz      short loc_1800259E6
0x1800259c3  mov     dword ptr [rsp+88h+ppv], 12Dh
0x1800259cb  mov     r9d, eax
0x1800259ce  mov     r8, cs:off_180049DB0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x1800259d5  mov     edx, 4B400h
0x1800259da  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800259e1  call    _bidTraceW
0x1800259e6  mov     ecx, esi; int
0x1800259e8  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800259ed  lea     r13, [rdi+18h]
0x1800259f1  mov     edx, r15d; unsigned int
0x1800259f4  mov     rcx, r13; this
0x1800259f7  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x1800259fc  mov     esi, eax
0x1800259fe  test    eax, eax
0x180025a00  jns     short loc_180025A41
0x180025a02  test    byte ptr cs:_bidGblFlags, 2
0x180025a09  jz      short loc_180025A3A
0x180025a0b  mov     rcx, cs:off_180049DA8; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025a12  test    rcx, rcx
0x180025a15  jz      short loc_180025A3A
0x180025a17  mov     dword ptr [rsp+88h+ppv], 12Fh
0x180025a1f  mov     r9d, eax
0x180025a22  mov     r8, cs:off_180049DA8; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025a29  mov     edx, 4BC00h
0x180025a2e  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025a35  call    _bidTraceW
0x180025a3a  mov     ecx, esi; int
0x180025a3c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025a41  lea     rcx, [rdi+50h]; this
0x180025a45  mov     edx, r15d; unsigned int
0x180025a48  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x180025a4d  mov     esi, eax
0x180025a4f  test    eax, eax
0x180025a51  jns     short loc_180025A92
0x180025a53  test    byte ptr cs:_bidGblFlags, 2
0x180025a5a  jz      short loc_180025A8B
0x180025a5c  mov     rcx, cs:off_180049DA0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025a63  test    rcx, rcx
0x180025a66  jz      short loc_180025A8B
0x180025a68  mov     dword ptr [rsp+88h+ppv], 130h
0x180025a70  mov     r9d, eax
0x180025a73  mov     r8, cs:off_180049DA0; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025a7a  mov     edx, 4C000h
0x180025a7f  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025a86  call    _bidTraceW
0x180025a8b  mov     ecx, esi; int
0x180025a8d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025a92  mov     rcx, rdi; this
0x180025a95  call    ?LoadMaps@CXMLReader@@AEAAJXZ; CXMLReader::LoadMaps(void)
0x180025a9a  mov     esi, eax
0x180025a9c  test    eax, eax
0x180025a9e  jns     short loc_180025ADF
0x180025aa0  test    byte ptr cs:_bidGblFlags, 2
0x180025aa7  jz      short loc_180025AD8
0x180025aa9  mov     rcx, cs:off_180049D98; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025ab0  test    rcx, rcx
0x180025ab3  jz      short loc_180025AD8
0x180025ab5  mov     dword ptr [rsp+88h+ppv], 133h
0x180025abd  mov     r9d, eax
0x180025ac0  mov     r8, cs:off_180049D98; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025ac7  mov     edx, 4CC00h
0x180025acc  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025ad3  call    _bidTraceW
0x180025ad8  mov     ecx, esi; int
0x180025ada  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025adf  lea     r15, [rdi+1C0h]
0x180025ae6  mov     [rsp+88h+ppv], r15; ppv
0x180025aeb  lea     r9, _GUID_d242361e_51a0_11d2_9caf_0060b0ec3d39; riid
0x180025af2  xor     edx, edx; pUnkOuter
0x180025af4  lea     r8d, [rdx+1]; dwClsContext
0x180025af8  lea     rcx, _GUID_f5078f31_c551_11d3_89b9_0000f81fe221; rclsid
0x180025aff  call    cs:__imp_CoCreateInstance
0x180025b06  nop     dword ptr [rax+rax+00h]
0x180025b0b  mov     esi, eax
0x180025b0d  cmp     eax, 80040154h
0x180025b12  jz      short loc_180025B1B
0x180025b14  cmp     eax, 80004002h
0x180025b19  jnz     short loc_180025B26
0x180025b1b  mov     r12d, 8Ah
0x180025b21  mov     [rsp+88h+var_58], r12d
0x180025b26  test    esi, esi
0x180025b28  jns     short loc_180025B69
0x180025b2a  test    byte ptr cs:_bidGblFlags, 2
0x180025b31  jz      short loc_180025B62
0x180025b33  mov     rax, cs:off_180049D90; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025b3a  test    rax, rax
0x180025b3d  jz      short loc_180025B62
0x180025b3f  mov     dword ptr [rsp+88h+ppv], 14Bh
0x180025b47  mov     r9d, esi
0x180025b4a  mov     r8, cs:off_180049D90; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025b51  mov     edx, 52C00h
0x180025b56  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025b5d  call    _bidTraceW
0x180025b62  mov     ecx, esi; int
0x180025b64  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025b69  mov     rcx, [r15]
0x180025b6c  mov     rax, [rcx]
0x180025b6f  mov     edx, 0F0110h
0x180025b74  mov     rax, [rax+0E0h]
0x180025b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b80  mov     rcx, [r15]
0x180025b83  mov     rax, [rcx]
0x180025b86  mov     rdx, r14
0x180025b89  mov     rax, [rax+80h]
0x180025b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b95  mov     r14d, eax
0x180025b98  test    eax, eax
0x180025b9a  jns     short loc_180025BDC
0x180025b9c  test    byte ptr cs:_bidGblFlags, 2
0x180025ba3  jz      short loc_180025BD4
0x180025ba5  mov     rcx, cs:off_180049D88; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025bac  test    rcx, rcx
0x180025baf  jz      short loc_180025BD4
0x180025bb1  mov     dword ptr [rsp+88h+ppv], 14Fh
0x180025bb9  mov     r9d, eax
0x180025bbc  mov     r8, cs:off_180049D88; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025bc3  mov     edx, 53C00h
0x180025bc8  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025bcf  call    _bidTraceW
0x180025bd4  mov     ecx, r14d; int
0x180025bd7  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025bdc  mov     rcx, [r15]
0x180025bdf  mov     rax, [rcx]
0x180025be2  mov     rdx, rdi
0x180025be5  mov     rax, [rax+18h]
0x180025be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bee  mov     rcx, [r15]
0x180025bf1  mov     rax, [rcx]
0x180025bf4  or      edx, 0FFFFFFFFh
0x180025bf7  mov     rax, [rax+0C0h]
0x180025bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c03  mov     r14d, eax
0x180025c06  test    eax, eax
0x180025c08  jns     short loc_180025C4A
0x180025c0a  test    byte ptr cs:_bidGblFlags, 2
0x180025c11  jz      short loc_180025C42
0x180025c13  mov     rcx, cs:off_180049D80; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025c1a  test    rcx, rcx
0x180025c1d  jz      short loc_180025C42
0x180025c1f  mov     dword ptr [rsp+88h+ppv], 153h
0x180025c27  mov     r9d, eax
0x180025c2a  mov     r8, cs:off_180049D80; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025c31  mov     edx, 54C00h
0x180025c36  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025c3d  call    _bidTraceW
0x180025c42  mov     ecx, r14d; int
0x180025c45  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025c4a  mov     rcx, [r15]
0x180025c4d  mov     rax, [rcx]
0x180025c50  mov     rax, [rax+0C8h]
0x180025c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c5c  test    eax, 0FFFFFFFAh
0x180025c61  jnz     short loc_180025CC7
0x180025c63  cmp     eax, 4
0x180025c66  jz      short loc_180025CC7
0x180025c68  lea     r9, [rsp+88h+var_40]
0x180025c6d  mov     r8, [rsp+88h+arg_8]
0x180025c75  mov     rdx, r13
0x180025c78  mov     rcx, rdi
0x180025c7b  call    ?InitRowsets@CXMLReader@@AEAAJPEAVCScope@@PEAUIStream@@PEAPEAV?$CComObject@VCXMLRowset@@@ATL@@@Z; CXMLReader::InitRowsets(CScope *,IStream *,ATL::CComObject<CXMLRowset> * *)
0x180025c80  mov     r14d, eax
0x180025c83  test    eax, eax
0x180025c85  jns     short loc_180025CC7
0x180025c87  test    byte ptr cs:_bidGblFlags, 2
0x180025c8e  jz      short loc_180025CBF
0x180025c90  mov     rcx, cs:off_180049D78; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025c97  test    rcx, rcx
0x180025c9a  jz      short loc_180025CBF
0x180025c9c  mov     dword ptr [rsp+88h+ppv], 160h
0x180025ca4  mov     r9d, eax
0x180025ca7  mov     r8, cs:off_180049D78; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025cae  mov     edx, 58000h
0x180025cb3  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025cba  call    _bidTraceW
0x180025cbf  mov     ecx, r14d; int
0x180025cc2  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025cc7  mov     rax, [rsp+88h+var_40]
0x180025ccc  test    rax, rax
0x180025ccf  jnz     short loc_180025D1E
0x180025cd1  mov     [rsp+88h+var_58], 91h
0x180025cd9  test    byte ptr cs:_bidGblFlags, 2
0x180025ce0  jz      short loc_180025D14
0x180025ce2  mov     rax, cs:off_180049D70; "<CXMLReader::CreateRowsetFromStream|ADO"...
0x180025ce9  test    rax, rax
0x180025cec  jz      short loc_180025D14
0x180025cee  mov     dword ptr [rsp+88h+ppv], 167h
  ... truncated ...
```
