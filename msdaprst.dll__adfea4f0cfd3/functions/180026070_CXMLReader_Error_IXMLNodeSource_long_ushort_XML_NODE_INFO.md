# CXMLReader::Error(IXMLNodeSource *,long,ushort,_XML_NODE_INFO * *)

- ea: `0x180026070`
- end: `0x18002639b`
- name: `?Error@CXMLReader@@UEAAJPEAUIXMLNodeSource@@JGPEAPEAU_XML_NODE_INFO@@@Z`
- size: `811`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct IXMLNodeSource *, int, unsigned __int16, struct _XML_NODE_INFO **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002770`
- `0x180016584`
- `0x18001b008`
- `0x180026070`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180026386`
- `OLEAUT32!__imp_SysFreeString` at `0x180026386`
- `OLEAUT32!__imp_SysStringLen` at `0x18002611c`
- `OLEAUT32!__imp_SysStringLen` at `0x18002611c`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800260a6`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800260a6`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180026308`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180026308`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180026135`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180026135`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CXMLReader::Error(CXMLReader *this, struct IXMLNodeSource *a2)
{
  int v3; // eax
  int v4; // ebx
  HRESULT v5; // eax
  int v6; // ebx
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  int v13; // eax
  int v14; // ebx
  HRESULT v15; // eax
  int v16; // ebx
  IErrorInfo *perrinfo; // [rsp+30h] [rbp-18h] BYREF
  BSTR pbstr[2]; // [rsp+38h] [rbp-10h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+50h] [rbp+8h] BYREF

  try
  {
    pbstr[0] = 0;
    pperrinfo = 0;
    perrinfo = 0;
    if ( *((_DWORD *)this + 120) <= 1u )
    {
      Exit(-2147467259, 0x8Fu);
    }
    else
    {
      if ( GetErrorInfo(0, &perrinfo) )
      {
        v3 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 56) + 88LL))(
               *((_QWORD *)this + 56),
               pbstr);
        v4 = v3;
        if ( v3 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_180049CF8[0] )
              bidTraceW(off_180049208[0], 2599936, off_180049CF8[0], (unsigned int)v3, 2539);
          }
          ThrowHR(v4);
        }
        if ( SysStringLen(pbstr[0]) )
        {
          v5 = CreateErrorInfo(&pperrinfo);
          v6 = v5;
          if ( v5 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180049CF0[0] )
              bidTraceW(off_180049208[0], 2604032, off_180049CF0[0], (unsigned int)v5, 2543);
            ThrowHR(v6);
          }
          v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, &GUID_NULL);
          v8 = v7;
          if ( v7 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180049CE8[0] )
              bidTraceW(off_180049208[0], 2605056, off_180049CE8[0], (unsigned int)v7, 2544);
            ThrowHR(v8);
          }
          v9 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const wchar_t *))pperrinfo->lpVtbl->SetSource)(
                 pperrinfo,
                 L"Microsoft OLEDB Persistence Provider");
          v10 = v9;
          if ( v9 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180049CE0[0] )
              bidTraceW(off_180049208[0], 2606080, off_180049CE0[0], (unsigned int)v9, 2545);
            ThrowHR(v10);
          }
          v11 = ((__int64 (__fastcall *)(ICreateErrorInfo *, BSTR))pperrinfo->lpVtbl->SetDescription)(
                  pperrinfo,
                  pbstr[0]);
          v12 = v11;
          if ( v11 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180049CD8[0] )
              bidTraceW(off_180049208[0], 2607104, off_180049CD8[0], (unsigned int)v11, 2546);
            ThrowHR(v12);
          }
          v13 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                  pperrinfo,
                  &IID_IErrorInfo,
                  &perrinfo);
          v14 = v13;
          if ( v13 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180049CD0[0] )
              bidTraceW(off_180049208[0], 2608128, off_180049CD0[0], (unsigned int)v13, 2547);
            ThrowHR(v14);
          }
        }
      }
      if ( perrinfo )
      {
        v15 = SetErrorInfo(0, perrinfo);
        v16 = v15;
        if ( v15 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049CC8[0] )
            bidTraceW(off_180049208[0], 2615296, off_180049CC8[0], (unsigned int)v15, 2554);
          ThrowHR(v16);
        }
      }
    }
  }
  catch ( long )
  {
  }
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&perrinfo);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&pperrinfo);
  SysFreeString(pbstr[0]);
  return 0;
}

```

## disassembly

```asm
0x180026070  mov     rax, rsp
0x180026073  push    rbx
0x180026074  sub     rsp, 40h
0x180026078  mov     rbx, rcx
0x18002607b  mov     qword ptr [rax-10h], 0
0x180026083  mov     qword ptr [rax+8], 0
0x18002608b  mov     qword ptr [rax-18h], 0
0x180026093  cmp     dword ptr [rcx+1E0h], 1
0x18002609a  jbe     loc_180026359
0x1800260a0  lea     rdx, [rax-18h]; pperrinfo
0x1800260a4  xor     ecx, ecx; dwReserved
0x1800260a6  call    cs:__imp_GetErrorInfo
0x1800260ad  nop     dword ptr [rax+rax+00h]
0x1800260b2  test    eax, eax
0x1800260b4  jz      loc_1800262FC
0x1800260ba  mov     rcx, [rbx+1C0h]
0x1800260c1  mov     rax, [rcx]
0x1800260c4  lea     rdx, [rsp+48h+pbstr]
0x1800260c9  mov     rax, [rax+58h]
0x1800260cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260d2  mov     ebx, eax
0x1800260d4  test    eax, eax
0x1800260d6  jns     short loc_180026117
0x1800260d8  test    byte ptr cs:_bidGblFlags, 2
0x1800260df  jz      short loc_180026110
0x1800260e1  mov     rcx, cs:off_180049CF8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800260e8  test    rcx, rcx
0x1800260eb  jz      short loc_180026110
0x1800260ed  mov     [rsp+48h+var_28], 9EBh
0x1800260f5  mov     r9d, eax
0x1800260f8  mov     r8, cs:off_180049CF8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800260ff  mov     edx, 27AC00h
0x180026104  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002610b  call    _bidTraceW
0x180026110  mov     ecx, ebx; int
0x180026112  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180026117  mov     rcx, [rsp+48h+pbstr]; pbstr
0x18002611c  call    cs:__imp_SysStringLen
0x180026123  nop     dword ptr [rax+rax+00h]
0x180026128  test    eax, eax
0x18002612a  jz      loc_1800262FC
0x180026130  lea     rcx, [rsp+48h+pperrinfo]; pperrinfo
0x180026135  call    cs:__imp_CreateErrorInfo
0x18002613c  nop     dword ptr [rax+rax+00h]
0x180026141  mov     ebx, eax
0x180026143  test    eax, eax
0x180026145  jns     short loc_180026186
0x180026147  test    byte ptr cs:_bidGblFlags, 2
0x18002614e  jz      short loc_18002617F
0x180026150  mov     rcx, cs:off_180049CF0; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x180026157  test    rcx, rcx
0x18002615a  jz      short loc_18002617F
0x18002615c  mov     [rsp+48h+var_28], 9EFh
0x180026164  mov     r9d, eax
0x180026167  mov     r8, cs:off_180049CF0; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x18002616e  mov     edx, 27BC00h
0x180026173  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002617a  call    _bidTraceW
0x18002617f  mov     ecx, ebx; int
0x180026181  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180026186  mov     rcx, [rsp+48h+pperrinfo]
0x18002618b  mov     rax, [rcx]
0x18002618e  lea     rdx, GUID_NULL
0x180026195  mov     rax, [rax+18h]
0x180026199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002619e  mov     ebx, eax
0x1800261a0  test    eax, eax
0x1800261a2  jns     short loc_1800261E3
0x1800261a4  test    byte ptr cs:_bidGblFlags, 2
0x1800261ab  jz      short loc_1800261DC
0x1800261ad  mov     rcx, cs:off_180049CE8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800261b4  test    rcx, rcx
0x1800261b7  jz      short loc_1800261DC
0x1800261b9  mov     [rsp+48h+var_28], 9F0h
0x1800261c1  mov     r9d, eax
0x1800261c4  mov     r8, cs:off_180049CE8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800261cb  mov     edx, 27C000h
0x1800261d0  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800261d7  call    _bidTraceW
0x1800261dc  mov     ecx, ebx; int
0x1800261de  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800261e3  mov     rcx, [rsp+48h+pperrinfo]
0x1800261e8  mov     rax, [rcx]
0x1800261eb  lea     rdx, aMicrosoftOledb; "Microsoft OLEDB Persistence Provider"
0x1800261f2  mov     rax, [rax+20h]
0x1800261f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261fb  mov     ebx, eax
0x1800261fd  test    eax, eax
0x1800261ff  jns     short loc_180026240
0x180026201  test    byte ptr cs:_bidGblFlags, 2
0x180026208  jz      short loc_180026239
0x18002620a  mov     rcx, cs:off_180049CE0; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x180026211  test    rcx, rcx
0x180026214  jz      short loc_180026239
0x180026216  mov     [rsp+48h+var_28], 9F1h
0x18002621e  mov     r9d, eax
0x180026221  mov     r8, cs:off_180049CE0; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x180026228  mov     edx, 27C400h
0x18002622d  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180026234  call    _bidTraceW
0x180026239  mov     ecx, ebx; int
0x18002623b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180026240  mov     rcx, [rsp+48h+pperrinfo]
0x180026245  mov     rax, [rcx]
0x180026248  mov     rdx, [rsp+48h+pbstr]
0x18002624d  mov     rax, [rax+28h]
0x180026251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026256  mov     ebx, eax
0x180026258  test    eax, eax
0x18002625a  jns     short loc_18002629B
0x18002625c  test    byte ptr cs:_bidGblFlags, 2
0x180026263  jz      short loc_180026294
0x180026265  mov     rcx, cs:off_180049CD8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x18002626c  test    rcx, rcx
0x18002626f  jz      short loc_180026294
0x180026271  mov     [rsp+48h+var_28], 9F2h
0x180026279  mov     r9d, eax
0x18002627c  mov     r8, cs:off_180049CD8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x180026283  mov     edx, 27C800h
0x180026288  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002628f  call    _bidTraceW
0x180026294  mov     ecx, ebx; int
0x180026296  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002629b  mov     rcx, [rsp+48h+pperrinfo]
0x1800262a0  mov     rax, [rcx]
0x1800262a3  lea     r8, [rsp+48h+perrinfo]
0x1800262a8  lea     rdx, IID_IErrorInfo
0x1800262af  mov     rax, [rax]
0x1800262b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262b7  mov     ebx, eax
0x1800262b9  test    eax, eax
0x1800262bb  jns     short loc_1800262FC
0x1800262bd  test    byte ptr cs:_bidGblFlags, 2
0x1800262c4  jz      short loc_1800262F5
0x1800262c6  mov     rcx, cs:off_180049CD0; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800262cd  test    rcx, rcx
0x1800262d0  jz      short loc_1800262F5
0x1800262d2  mov     [rsp+48h+var_28], 9F3h
0x1800262da  mov     r9d, eax
0x1800262dd  mov     r8, cs:off_180049CD0; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800262e4  mov     edx, 27CC00h
0x1800262e9  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800262f0  call    _bidTraceW
0x1800262f5  mov     ecx, ebx; int
0x1800262f7  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800262fc  mov     rdx, [rsp+48h+perrinfo]; perrinfo
0x180026301  test    rdx, rdx
0x180026304  jz      short loc_180026369
0x180026306  xor     ecx, ecx; dwReserved
0x180026308  call    cs:__imp_SetErrorInfo
0x18002630f  nop     dword ptr [rax+rax+00h]
0x180026314  mov     ebx, eax
0x180026316  test    eax, eax
0x180026318  jns     short loc_180026369
0x18002631a  test    byte ptr cs:_bidGblFlags, 2
0x180026321  jz      short loc_180026352
0x180026323  mov     rcx, cs:off_180049CC8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x18002632a  test    rcx, rcx
0x18002632d  jz      short loc_180026352
0x18002632f  mov     [rsp+48h+var_28], 9FAh
0x180026337  mov     r9d, eax
0x18002633a  mov     r8, cs:off_180049CC8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x180026341  mov     edx, 27E800h
0x180026346  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002634d  call    _bidTraceW
0x180026352  mov     ecx, ebx; int
0x180026354  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180026359  mov     edx, 8Fh; unsigned int
0x18002635e  mov     ecx, 80004005h; int
0x180026363  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180026368  nop
0x180026369  jmp     short $+2
0x18002636b  lea     rcx, [rsp+48h+perrinfo]
0x180026370  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180026375  nop
0x180026376  lea     rcx, [rsp+48h+pperrinfo]
0x18002637b  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180026380  nop
0x180026381  mov     rcx, [rsp+48h+pbstr]; bstrString
0x180026386  call    cs:__imp_SysFreeString
0x18002638d  nop     dword ptr [rax+rax+00h]
0x180026392  xor     eax, eax
0x180026394  add     rsp, 40h
0x180026398  pop     rbx
0x180026399  retn
```
