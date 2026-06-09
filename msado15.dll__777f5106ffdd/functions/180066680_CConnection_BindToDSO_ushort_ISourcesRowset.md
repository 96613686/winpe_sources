# CConnection::BindToDSO(ushort *,ISourcesRowset *)

- ea: `0x180066680`
- end: `0x180066bae`
- name: `?BindToDSO@CConnection@@QEAAJPEAGPEAUISourcesRowset@@@Z`
- size: `1326`
- prototype: `int(CConnection *__hidden this, unsigned __int16 *, struct ISourcesRowset *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x180046bc8`

## callees

- `0x18005b950`
- `0x180066680`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `ole32!CreateFileMoniker` at `0x18006692e`
- `ole32!CreateFileMoniker` at `0x18006692e`
- `ole32!CreateBindCtx` at `0x180066897`
- `ole32!CreateBindCtx` at `0x180066897`
- `ole32!CoTaskMemFree` at `0x180066b53`
- `ole32!CoTaskMemFree` at `0x180066b53`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180066a0b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180066a0b`

## pseudocode

```c
__int64 __fastcall CConnection::BindToDSO(CConnection *this, unsigned __int16 *a2, IMoniker *a3)
{
  char *v3; // r15
  bool v4; // zf
  HRESULT DataInit; // ebx
  unsigned int BidObjectID; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // [rsp+20h] [rbp-20h]
  __int64 v21; // [rsp+28h] [rbp-18h]
  LPBC ppbc; // [rsp+70h] [rbp+30h] BYREF
  LPMONIKER ppmk; // [rsp+80h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+48h] BYREF

  ppmk = a3;
  v3 = (char *)this + 968;
  ppbc = 0;
  v4 = *((_QWORD *)this + 121) == 0;
  ppmk = 0;
  pv = 0;
  if ( !v4 )
    return 0;
  DataInit = CConnection::GetDataInit(this);
  if ( DataInit < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_46;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      v10 = 5614601;
      LODWORD(v21) = 5483;
LABEL_7:
      LODWORD(v20) = DataInit;
      bidTraceW(
        off_18012A1C0[0],
        v10,
        L"<CConnection::BindToDSO|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        BidObjectID,
        v20,
        v21);
      goto LABEL_46;
    }
    LODWORD(v20) = 5483;
    v11 = 5614601;
    goto LABEL_9;
  }
  DataInit = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, LPVOID *))(**((_QWORD **)this + 124) + 56LL))(
               *((_QWORD *)this + 124),
               a2,
               &pv);
  if ( DataInit >= 0 )
  {
    DataInit = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, LPVOID, GUID *, char *))(**((_QWORD **)this + 124)
                                                                                          + 24LL))(
                 *((_QWORD *)this + 124),
                 0,
                 23,
                 pv,
                 &IID_IDBInitialize,
                 v3);
    if ( DataInit < 0 && (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        v12 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v13 = 5621769;
        LODWORD(v21) = 5490;
        goto LABEL_15;
      }
      LODWORD(v20) = 5490;
      v14 = 5621769;
LABEL_22:
      bidTraceW(
        off_18012A1C0[0],
        v14,
        L"<CConnection::BindToDSO|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)DataInit,
        v20);
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      v12 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      v13 = 5616649;
      LODWORD(v21) = 5485;
LABEL_15:
      LODWORD(v20) = DataInit;
      bidTraceW(off_18012A1C0[0], v13, L"<CConnection::BindToDSO|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n", v12, v20, v21);
      goto LABEL_23;
    }
    LODWORD(v20) = 5485;
    v14 = 5616649;
    goto LABEL_22;
  }
LABEL_23:
  if ( DataInit == -2147287038 || DataInit == -2147286788 || DataInit == -2147287035 )
  {
    SetErrorInfo(0, 0);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) == -1 )
      {
        bidTraceW(off_18012A1C0[0], 5626889, L"<CConnection::BindToDSO|ADO|ERR>  line %d\n", 5495);
      }
      else
      {
        v16 = (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        LODWORD(v20) = 5495;
        bidTraceW(off_18012A1C0[0], 5626889, L"<CConnection::BindToDSO|ADO|ERR> %u#, line %d\n", v16, v20);
      }
    }
  }
  else
  {
    if ( DataInit >= 0 )
      goto LABEL_46;
    DataInit = CreateBindCtx(0, &ppbc);
    if ( DataInit < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) == -1 )
        {
          LODWORD(v20) = 5502;
          bidTraceW(
            off_18012A1C0[0],
            5634057,
            L"<CConnection::BindToDSO|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            (unsigned int)DataInit,
            v20);
        }
        else
        {
          v15 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          LODWORD(v21) = 5502;
          LODWORD(v20) = DataInit;
          bidTraceW(
            off_18012A1C0[0],
            5634057,
            L"<CConnection::BindToDSO|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v15,
            v20,
            v21);
        }
      }
      return (unsigned int)DataInit;
    }
    DataInit = CreateFileMoniker(a2, &ppmk);
    if ( DataInit < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_46;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v10 = 5646345;
        LODWORD(v21) = 5514;
        goto LABEL_7;
      }
      LODWORD(v20) = 5514;
      v11 = 5646345;
      goto LABEL_9;
    }
    DataInit = ((__int64 (__fastcall *)(LPMONIKER, LPBC, _QWORD, GUID *, char *))ppmk->lpVtbl->BindToObject)(
                 ppmk,
                 ppbc,
                 0,
                 &IID_IDBInitialize,
                 v3);
    if ( DataInit < 0 && (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v10 = 5650441;
        LODWORD(v21) = 5518;
        goto LABEL_7;
      }
      LODWORD(v20) = 5518;
      v11 = 5650441;
LABEL_9:
      bidTraceW(
        off_18012A1C0[0],
        v11,
        L"<CConnection::BindToDSO|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)DataInit,
        v20);
    }
  }
LABEL_46:
  if ( DataInit != -2147221014 )
  {
    if ( DataInit != -2147221164 )
      goto LABEL_58;
    DataInit = -2146824582;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_58;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      v17 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      v18 = 5661705;
      LODWORD(v21) = 5529;
      goto LABEL_50;
    }
    LODWORD(v20) = 5529;
    v19 = 5661705;
LABEL_57:
    bidTraceW(
      off_18012A1C0[0],
      v19,
      L"<CConnection::BindToDSO|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      (unsigned int)DataInit,
      v20);
    goto LABEL_58;
  }
  DataInit = -2147287038;
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      v17 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      v18 = 5657609;
      LODWORD(v21) = 5525;
LABEL_50:
      LODWORD(v20) = DataInit;
      bidTraceW(off_18012A1C0[0], v18, L"<CConnection::BindToDSO|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n", v17, v20, v21);
      goto LABEL_58;
    }
    LODWORD(v20) = 5525;
    v19 = 5657609;
    goto LABEL_57;
  }
LABEL_58:
  if ( pv )
    CoTaskMemFree(pv);
  if ( ppmk )
  {
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
    ppmk = 0;
  }
  if ( ppbc )
  {
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    ppbc = 0;
  }
  return (unsigned int)DataInit;
}

```

## disassembly

```asm
0x180066680  mov     [rsp-28h+arg_8], rbx
0x180066685  mov     [rsp-28h+ppmk], r8
0x18006668a  push    rbp
0x18006668b  push    rdi
0x18006668c  push    r12
0x18006668e  push    r14
0x180066690  push    r15
0x180066692  mov     rbp, rsp
0x180066695  sub     rsp, 40h
0x180066699  lea     r15, [rcx+3C8h]
0x1800666a0  mov     [rbp+ppbc], 0
0x1800666a8  cmp     qword ptr [r15], 0
0x1800666ac  mov     r12, rdx
0x1800666af  mov     rdi, rcx
0x1800666b2  mov     [rbp+ppmk], 0
0x1800666ba  mov     [rbp+pv], 0
0x1800666c2  jz      short loc_1800666CB
0x1800666c4  xor     eax, eax
0x1800666c6  jmp     loc_180066B9B
0x1800666cb  call    ?GetDataInit@CConnection@@QEAAJXZ; CConnection::GetDataInit(void)
0x1800666d0  mov     ebx, eax
0x1800666d2  test    eax, eax
0x1800666d4  jns     short loc_180066753
0x1800666d6  test    byte ptr cs:_bidGblFlags, 2
0x1800666dd  jz      loc_180066A76
0x1800666e3  lea     r14, [rdi+100h]
0x1800666ea  mov     rcx, r14; this
0x1800666ed  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800666f2  cmp     eax, 0FFFFFFFFh
0x1800666f5  jz      short loc_18006672B
0x1800666f7  mov     rcx, r14; this
0x1800666fa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800666ff  mov     edx, 55AC09h
0x180066704  mov     dword ptr [rsp+40h+var_18], 156Bh
0x18006670c  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180066713  lea     r8, aCconnectionBin_6; "<CConnection::BindToDSO|ADO|ERR> %u#,0x"...
0x18006671a  mov     r9d, eax
0x18006671d  mov     dword ptr [rsp+40h+var_20], ebx
0x180066721  call    _bidTraceW
0x180066726  jmp     loc_180066A76
0x18006672b  mov     dword ptr [rsp+40h+var_20], 156Bh
0x180066733  mov     edx, 55AC09h
0x180066738  mov     r9d, ebx
0x18006673b  lea     r8, aCconnectionBin_2; "<CConnection::BindToDSO|ADO|ERR> 0x%08x"...
0x180066742  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180066749  call    _bidTraceW
0x18006674e  jmp     loc_180066A76
0x180066753  mov     rcx, [rdi+3E0h]
0x18006675a  lea     r8, [rbp+pv]
0x18006675e  mov     rdx, r12
0x180066761  mov     rax, [rcx]
0x180066764  mov     rax, [rax+38h]
0x180066768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006676d  lea     rdx, IID_IDBInitialize
0x180066774  mov     ebx, eax
0x180066776  test    eax, eax
0x180066778  jns     short loc_1800667DE
0x18006677a  test    byte ptr cs:_bidGblFlags, 2
0x180066781  jz      loc_180066865
0x180066787  lea     r14, [rdi+100h]
0x18006678e  mov     rcx, r14; this
0x180066791  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180066796  cmp     eax, 0FFFFFFFFh
0x180066799  jz      short loc_1800667CF
0x18006679b  mov     rcx, r14; this
0x18006679e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800667a3  mov     edx, 55B409h
0x1800667a8  mov     dword ptr [rsp+40h+var_18], 156Dh
0x1800667b0  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800667b7  lea     r8, aCconnectionBin_6; "<CConnection::BindToDSO|ADO|ERR> %u#,0x"...
0x1800667be  mov     r9d, eax
0x1800667c1  mov     dword ptr [rsp+40h+var_20], ebx
0x1800667c5  call    _bidTraceW
0x1800667ca  jmp     loc_180066865
0x1800667cf  mov     dword ptr [rsp+40h+var_20], 156Dh
0x1800667d7  mov     edx, 55B409h
0x1800667dc  jmp     short loc_18006684F
0x1800667de  mov     rcx, [rdi+3E0h]
0x1800667e5  mov     r9, [rbp+pv]
0x1800667e9  mov     [rsp+40h+var_18], r15
0x1800667ee  mov     [rsp+40h+var_20], rdx
0x1800667f3  xor     edx, edx
0x1800667f5  mov     rax, [rcx]
0x1800667f8  lea     r8d, [rdx+17h]
0x1800667fc  mov     rax, [rax+18h]
0x180066800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066805  mov     ebx, eax
0x180066807  test    eax, eax
0x180066809  jns     short loc_180066865
0x18006680b  test    byte ptr cs:_bidGblFlags, 2
0x180066812  jz      short loc_180066865
0x180066814  lea     r14, [rdi+100h]
0x18006681b  mov     rcx, r14; this
0x18006681e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180066823  cmp     eax, 0FFFFFFFFh
0x180066826  jz      short loc_180066842
0x180066828  mov     rcx, r14; this
0x18006682b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180066830  mov     edx, 55C809h
0x180066835  mov     dword ptr [rsp+40h+var_18], 1572h
0x18006683d  jmp     loc_1800667B0
0x180066842  mov     dword ptr [rsp+40h+var_20], 1572h
0x18006684a  mov     edx, 55C809h
0x18006684f  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180066856  lea     r8, aCconnectionBin_2; "<CConnection::BindToDSO|ADO|ERR> 0x%08x"...
0x18006685d  mov     r9d, ebx
0x180066860  call    _bidTraceW
0x180066865  cmp     ebx, 80030002h
0x18006686b  jz      loc_180066A07
0x180066871  cmp     ebx, 800300FCh
0x180066877  jz      loc_180066A07
0x18006687d  cmp     ebx, 80030005h
0x180066883  jz      loc_180066A07
0x180066889  test    ebx, ebx
0x18006688b  jns     loc_180066A76
0x180066891  lea     rdx, [rbp+ppbc]; ppbc
0x180066895  xor     ecx, ecx; reserved
0x180066897  call    cs:__imp_CreateBindCtx
0x18006689e  nop     dword ptr [rax+rax+00h]
0x1800668a3  mov     ebx, eax
0x1800668a5  test    eax, eax
0x1800668a7  jns     short loc_180066927
0x1800668a9  test    byte ptr cs:_bidGblFlags, 2
0x1800668b0  jz      loc_180066B99
0x1800668b6  lea     rcx, [rdi+100h]; this
0x1800668bd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800668c2  cmp     eax, 0FFFFFFFFh
0x1800668c5  jz      short loc_1800668FF
0x1800668c7  lea     rcx, [rdi+100h]; this
0x1800668ce  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800668d3  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800668da  lea     r8, aCconnectionBin_6; "<CConnection::BindToDSO|ADO|ERR> %u#,0x"...
0x1800668e1  mov     r9d, eax
0x1800668e4  mov     dword ptr [rsp+40h+var_18], 157Eh
0x1800668ec  mov     edx, 55F809h
0x1800668f1  mov     dword ptr [rsp+40h+var_20], ebx
0x1800668f5  call    _bidTraceW
0x1800668fa  jmp     loc_180066B99
0x1800668ff  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180066906  lea     r8, aCconnectionBin_2; "<CConnection::BindToDSO|ADO|ERR> 0x%08x"...
0x18006690d  mov     r9d, ebx
0x180066910  mov     dword ptr [rsp+40h+var_20], 157Eh
0x180066918  mov     edx, 55F809h
0x18006691d  call    _bidTraceW
0x180066922  jmp     loc_180066B99
0x180066927  lea     rdx, [rbp+ppmk]; ppmk
0x18006692b  mov     rcx, r12; lpszPathName
0x18006692e  call    cs:__imp_CreateFileMoniker
0x180066935  nop     dword ptr [rax+rax+00h]
0x18006693a  mov     ebx, eax
0x18006693c  test    eax, eax
0x18006693e  jns     short loc_18006698D
0x180066940  test    byte ptr cs:_bidGblFlags, 2
0x180066947  jz      loc_180066A76
0x18006694d  lea     r14, [rdi+100h]
0x180066954  mov     rcx, r14; this
0x180066957  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006695c  cmp     eax, 0FFFFFFFFh
0x18006695f  jz      short loc_18006697B
0x180066961  mov     rcx, r14; this
0x180066964  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180066969  mov     edx, 562809h
0x18006696e  mov     dword ptr [rsp+40h+var_18], 158Ah
0x180066976  jmp     loc_18006670C
0x18006697b  mov     dword ptr [rsp+40h+var_20], 158Ah
0x180066983  mov     edx, 562809h
0x180066988  jmp     loc_180066738
0x18006698d  mov     rcx, [rbp+ppmk]
0x180066991  lea     r9, IID_IDBInitialize
0x180066998  mov     rdx, [rbp+ppbc]
0x18006699c  xor     r8d, r8d
0x18006699f  mov     [rsp+40h+var_20], r15
0x1800669a4  mov     rax, [rcx]
0x1800669a7  mov     rax, [rax+40h]
0x1800669ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669b0  mov     ebx, eax
0x1800669b2  test    eax, eax
0x1800669b4  jns     loc_180066A76
0x1800669ba  test    byte ptr cs:_bidGblFlags, 2
0x1800669c1  jz      loc_180066A76
0x1800669c7  lea     r14, [rdi+100h]
0x1800669ce  mov     rcx, r14; this
0x1800669d1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800669d6  cmp     eax, 0FFFFFFFFh
0x1800669d9  jz      short loc_1800669F5
0x1800669db  mov     rcx, r14; this
0x1800669de  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800669e3  mov     edx, 563809h
0x1800669e8  mov     dword ptr [rsp+40h+var_18], 158Eh
0x1800669f0  jmp     loc_18006670C
0x1800669f5  mov     dword ptr [rsp+40h+var_20], 158Eh
0x1800669fd  mov     edx, 563809h
0x180066a02  jmp     loc_180066738
0x180066a07  xor     edx, edx; perrinfo
0x180066a09  xor     ecx, ecx; dwReserved
0x180066a0b  call    cs:__imp_SetErrorInfo
0x180066a12  nop     dword ptr [rax+rax+00h]
0x180066a17  test    byte ptr cs:_bidGblFlags, 2
0x180066a1e  jz      short loc_180066A76
0x180066a20  lea     r14, [rdi+100h]
0x180066a27  mov     rcx, r14; this
0x180066a2a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180066a2f  cmp     eax, 0FFFFFFFFh
0x180066a32  jz      short loc_180066A58
0x180066a34  mov     rcx, r14; this
0x180066a37  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180066a3c  mov     r9d, eax
0x180066a3f  mov     dword ptr [rsp+40h+var_20], 1577h
0x180066a47  lea     r8, aCconnectionBin_1; "<CConnection::BindToDSO|ADO|ERR> %u#, l"...
0x180066a4e  mov     edx, 55DC09h
0x180066a53  jmp     loc_180066742
0x180066a58  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180066a5f  lea     r8, aCconnectionBin_4; "<CConnection::BindToDSO|ADO|ERR>  line "...
0x180066a66  mov     r9d, 1577h
0x180066a6c  mov     edx, 55DC09h
0x180066a71  call    _bidTraceW
0x180066a76  cmp     ebx, 800401EAh
0x180066a7c  jnz     short loc_180066AE5
0x180066a7e  test    byte ptr cs:_bidGblFlags, 2
0x180066a85  mov     ebx, 80030002h
0x180066a8a  jz      loc_180066B4A
0x180066a90  lea     rcx, [rdi+100h]; this
0x180066a97  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180066a9c  cmp     eax, 0FFFFFFFFh
0x180066a9f  jz      short loc_180066AD6
0x180066aa1  lea     rcx, [rdi+100h]; this
0x180066aa8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180066aad  mov     edx, 565409h
0x180066ab2  mov     dword ptr [rsp+40h+var_18], 1595h
0x180066aba  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180066ac1  lea     r8, aCconnectionBin_6; "<CConnection::BindToDSO|ADO|ERR> %u#,0x"...
0x180066ac8  mov     r9d, eax
0x180066acb  mov     dword ptr [rsp+40h+var_20], ebx
0x180066acf  call    _bidTraceW
0x180066ad4  jmp     short loc_180066B4A
0x180066ad6  mov     dword ptr [rsp+40h+var_20], 1595h
0x180066ade  mov     edx, 565409h
0x180066ae3  jmp     short loc_180066B34
0x180066ae5  cmp     ebx, 80040154h
0x180066aeb  jnz     short loc_180066B4A
0x180066aed  test    byte ptr cs:_bidGblFlags, 2
0x180066af4  mov     ebx, 800A0E7Ah
0x180066af9  jz      short loc_180066B4A
0x180066afb  lea     rcx, [rdi+100h]; this
0x180066b02  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180066b07  cmp     eax, 0FFFFFFFFh
0x180066b0a  jz      short loc_180066B27
0x180066b0c  lea     rcx, [rdi+100h]; this
0x180066b13  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180066b18  mov     edx, 566409h
0x180066b1d  mov     dword ptr [rsp+40h+var_18], 1599h
0x180066b25  jmp     short loc_180066ABA
0x180066b27  mov     dword ptr [rsp+40h+var_20], 1599h
0x180066b2f  mov     edx, 566409h
0x180066b34  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180066b3b  lea     r8, aCconnectionBin_2; "<CConnection::BindToDSO|ADO|ERR> 0x%08x"...
0x180066b42  mov     r9d, ebx
0x180066b45  call    _bidTraceW
0x180066b4a  mov     rcx, [rbp+pv]; pv
0x180066b4e  test    rcx, rcx
0x180066b51  jz      short loc_180066B5F
0x180066b53  call    cs:__imp_CoTaskMemFree
0x180066b5a  nop     dword ptr [rax+rax+00h]
0x180066b5f  mov     rcx, [rbp+ppmk]
0x180066b63  test    rcx, rcx
0x180066b66  jz      short loc_180066B7C
0x180066b68  mov     rax, [rcx]
0x180066b6b  mov     rax, [rax+10h]
0x180066b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b74  mov     [rbp+ppmk], 0
0x180066b7c  mov     rcx, [rbp+ppbc]
0x180066b80  test    rcx, rcx
0x180066b83  jz      short loc_180066B99
0x180066b85  mov     rax, [rcx]
0x180066b88  mov     rax, [rax+10h]
0x180066b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b91  mov     [rbp+ppbc], 0
0x180066b99  mov     eax, ebx
0x180066b9b  mov     rbx, [rsp+40h+arg_8]
0x180066ba0  add     rsp, 40h
0x180066ba4  pop     r15
0x180066ba6  pop     r14
0x180066ba8  pop     r12
0x180066baa  pop     rdi
0x180066bab  pop     rbp
0x180066bac  retn
```
