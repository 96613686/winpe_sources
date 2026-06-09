# CADTGRowset::arInit(IStream *)

- ea: `0x18000f58c`
- end: `0x18000f9f0`
- name: `?arInit@CADTGRowset@@QEAAJPEAUIStream@@@Z`
- size: `1124`
- prototype: `__int64 __fastcall(CADTGRowset *__hidden this, struct IStream *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000c0a0`
- `0x18000e86c`

## callees

- `0x180001dd4`
- `0x1800028b8`
- `0x18000e86c`
- `0x18000f58c`
- `0x18001b008`
- `0x180020bec`
- `0x1800210a4`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x18000f5bd`
- `KERNEL32!GetSystemInfo` at `0x18000f5bd`
- `ole32!CoTaskMemAlloc` at `0x18000f6e9`
- `ole32!CoTaskMemAlloc` at `0x18000f6e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CADTGRowset::arInit(CADTGRowset *this, struct IStream *a2)
{
  unsigned int v4; // r14d
  unsigned __int8 *v5; // rax
  unsigned __int8 *v6; // rbx
  int MetaData; // ebx
  DBID *v8; // rax
  int v9; // ebx
  unsigned int v11; // [rsp+30h] [rbp-68h] BYREF
  struct _SYSTEM_INFO v12[2]; // [rsp+38h] [rbp-60h] BYREF

  v4 = 0;
  memset(v12, 0, 48);
  if ( !g_dwPageSize )
  {
    GetSystemInfo(v12);
    g_dwPageSize = v12[0].dwPageSize;
  }
  try
  {
    if ( !*((_DWORD *)this + 172) )
    {
      *((_DWORD *)this + 150) = 1;
      if ( !a2 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800498D8[0] )
            bidTraceW(off_1800491C8[0], 146432, off_1800498D8[0], 2147942487LL, 143);
        }
        ThrowHR(-2147024809);
      }
      v5 = MMMAlloc(0x18u, (unsigned int)a2);
      v6 = v5;
      if ( v5 )
      {
        *(_QWORD *)v5 = a2;
        ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
        v6[8] = 0;
        *((_DWORD *)v6 + 3) = 0;
        *((_DWORD *)v6 + 4) = 1;
      }
      else
      {
        v6 = 0;
      }
      *((_QWORD *)this + 68) = v6;
      OnNullThrowOOM(v6);
    }
    CRowset::CheckThreadModel(this, **((struct IUnknown ***)this + 68));
    MetaData = CADTGRowset::arGetMetaData(this);
    if ( MetaData < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800498D0[0] )
        bidTraceW(off_1800491C8[0], 153600, off_1800498D0[0], (unsigned int)MetaData, 150);
      ThrowHR(MetaData);
    }
    v8 = (DBID *)CoTaskMemAlloc(0x2A0u);
    if ( !v8 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800498C8[0] )
        bidTraceW(off_1800491C8[0], 157696, off_1800498C8[0], 2147942414LL, 154);
      ThrowHR(-2147024882);
    }
    *v8 = DBCOLUMN_BASECOLUMNNAME;
    v8[1] = DBCOLUMN_BASETABLENAME;
    v8[2] = DBCOLUMN_COLLATINGSEQUENCE;
    v8[3] = DBCOLUMN_COMPUTEMODE;
    v8[4] = DBCOLUMN_DEFAULTVALUE;
    v8[5] = DBCOLUMN_DOMAINNAME;
    v8[6] = DBCOLUMN_HASDEFAULT;
    v8[7] = DBCOLUMN_ISAUTOINCREMENT;
    v8[8] = DBCOLUMN_ISCASESENSITIVE;
    v8[9] = DBCOLUMN_ISSEARCHABLE;
    v8[10] = DBCOLUMN_ISUNIQUE;
    v8[11] = DBCOLUMN_BASECATALOGNAME;
    v8[12] = DBCOLUMN_BASESCHEMANAME;
    v8[13] = DBCOLUMN_DOMAINCATALOG;
    v8[14] = DBCOLUMN_DOMAINSCHEMA;
    v8[15] = DBCOLUMN_DATETIMEPRECISION;
    v8[16] = DBCOLUMN_OCTETLENGTH;
    v8[17] = DBCOLUMN_CLSID;
    v8[18].uGuid = (union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D)xmmword_1800385D0;
    *(_OWORD *)&v8[18].eKind = xmmword_1800385E0;
    v8[19].uGuid = (union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D)xmmword_1800385B0;
    *(_OWORD *)&v8[19].eKind = xmmword_1800385C0;
    v8[20].uGuid = (union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D)xmmword_180038590;
    *(_OWORD *)&v8[20].eKind = xmmword_1800385A0;
    *((_DWORD *)this + 92) = 21;
    *((_QWORD *)this + 47) = v8;
    v9 = CRowset::Init(this);
    if ( v9 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800498C0[0] )
        bidTraceW(off_1800491C8[0], 187392, off_1800498C0[0], (unsigned int)v9, 183);
      ThrowHR(v9);
    }
  }
  catch ( long v11 )
  {
    return v11;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return v4;
}

```

## disassembly

```asm
0x18000f58c  mov     rax, rsp
0x18000f58f  push    rbx
0x18000f590  push    rsi
0x18000f591  push    rdi
0x18000f592  push    r14
0x18000f594  sub     rsp, 78h
0x18000f598  mov     rsi, rdx
0x18000f59b  mov     rdi, rcx
0x18000f59e  xor     r14d, r14d
0x18000f5a1  xorps   xmm0, xmm0
0x18000f5a4  movups  xmmword ptr [rax-60h], xmm0
0x18000f5a8  movups  xmmword ptr [rax-50h], xmm0
0x18000f5ac  movups  xmmword ptr [rax-40h], xmm0
0x18000f5b0  cmp     cs:?g_dwPageSize@@3KA, r14d; ulong g_dwPageSize
0x18000f5b7  jnz     short loc_18000F5D3
0x18000f5b9  lea     rcx, [rax-60h]; lpSystemInfo
0x18000f5bd  call    cs:__imp_GetSystemInfo
0x18000f5c4  nop     dword ptr [rax+rax+00h]
0x18000f5c9  mov     eax, [rsp+98h+var_5C]
0x18000f5cd  mov     cs:?g_dwPageSize@@3KA, eax; ulong g_dwPageSize
0x18000f5d3  cmp     dword ptr [rdi+2B0h], 0
0x18000f5da  jnz     loc_18000F685
0x18000f5e0  mov     dword ptr [rdi+258h], 1
0x18000f5ea  test    rsi, rsi
0x18000f5ed  jnz     short loc_18000F634
0x18000f5ef  test    byte ptr cs:_bidGblFlags, 2
0x18000f5f6  jz      short loc_18000F62A
0x18000f5f8  mov     rax, cs:off_1800498D8; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f5ff  test    rax, rax
0x18000f602  jz      short loc_18000F62A
0x18000f604  mov     [rsp+98h+var_78], 8Fh
0x18000f60c  mov     r9d, 80070057h
0x18000f612  mov     r8, cs:off_1800498D8; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f619  mov     edx, 23C00h
0x18000f61e  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000f625  call    _bidTraceW
0x18000f62a  mov     ecx, 80070057h; int
0x18000f62f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000f634  mov     ecx, 18h; unsigned int
0x18000f639  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000f63e  mov     rbx, rax
0x18000f641  mov     [rsp+98h+arg_0], rax
0x18000f649  test    rax, rax
0x18000f64c  jz      short loc_18000F674
0x18000f64e  mov     [rax], rsi
0x18000f651  mov     rax, [rsi]
0x18000f654  mov     rcx, rsi
0x18000f657  mov     rax, [rax+8]
0x18000f65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f660  mov     byte ptr [rbx+8], 0
0x18000f664  mov     dword ptr [rbx+0Ch], 0
0x18000f66b  mov     dword ptr [rbx+10h], 1
0x18000f672  jmp     short loc_18000F676
0x18000f674  xor     ebx, ebx
0x18000f676  mov     [rdi+220h], rbx
0x18000f67d  mov     rcx, rbx; void *
0x18000f680  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000f685  mov     rdx, [rdi+220h]
0x18000f68c  mov     rdx, [rdx]; struct IUnknown *
0x18000f68f  mov     rcx, rdi; this
0x18000f692  call    ?CheckThreadModel@CRowset@@QEAAXPEAUIUnknown@@@Z; CRowset::CheckThreadModel(IUnknown *)
0x18000f697  mov     rcx, rdi; this
0x18000f69a  call    ?arGetMetaData@CADTGRowset@@AEAAJXZ; CADTGRowset::arGetMetaData(void)
0x18000f69f  mov     ebx, eax
0x18000f6a1  test    eax, eax
0x18000f6a3  jns     short loc_18000F6E4
0x18000f6a5  test    byte ptr cs:_bidGblFlags, 2
0x18000f6ac  jz      short loc_18000F6DD
0x18000f6ae  mov     rax, cs:off_1800498D0; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f6b5  test    rax, rax
0x18000f6b8  jz      short loc_18000F6DD
0x18000f6ba  mov     [rsp+98h+var_78], 96h
0x18000f6c2  mov     r9d, ebx
0x18000f6c5  mov     r8, cs:off_1800498D0; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f6cc  mov     edx, 25800h
0x18000f6d1  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000f6d8  call    _bidTraceW
0x18000f6dd  mov     ecx, ebx; int
0x18000f6df  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000f6e4  mov     ecx, 2A0h; cb
0x18000f6e9  call    cs:__imp_CoTaskMemAlloc
0x18000f6f0  nop     dword ptr [rax+rax+00h]
0x18000f6f5  test    rax, rax
0x18000f6f8  jnz     short loc_18000F73F
0x18000f6fa  test    byte ptr cs:_bidGblFlags, 2
0x18000f701  jz      short loc_18000F735
0x18000f703  mov     rax, cs:off_1800498C8; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f70a  test    rax, rax
0x18000f70d  jz      short loc_18000F735
0x18000f70f  mov     [rsp+98h+var_78], 9Ah
0x18000f717  mov     r9d, 8007000Eh
0x18000f71d  mov     r8, cs:off_1800498C8; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f724  mov     edx, 26800h
0x18000f729  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000f730  call    _bidTraceW
0x18000f735  mov     ecx, 8007000Eh; int
0x18000f73a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000f73f  movups  xmm0, xmmword ptr cs:DBCOLUMN_BASECOLUMNNAME.uGuid
0x18000f746  movups  xmmword ptr [rax], xmm0
0x18000f749  movups  xmm1, xmmword ptr cs:DBCOLUMN_BASECOLUMNNAME.eKind
0x18000f750  movups  xmmword ptr [rax+10h], xmm1
0x18000f754  movups  xmm0, xmmword ptr cs:DBCOLUMN_BASETABLENAME.uGuid
0x18000f75b  movups  xmmword ptr [rax+20h], xmm0
0x18000f75f  movups  xmm1, xmmword ptr cs:DBCOLUMN_BASETABLENAME.eKind
0x18000f766  movups  xmmword ptr [rax+30h], xmm1
0x18000f76a  movups  xmm0, xmmword ptr cs:DBCOLUMN_COLLATINGSEQUENCE.uGuid
0x18000f771  movups  xmmword ptr [rax+40h], xmm0
0x18000f775  movups  xmm1, xmmword ptr cs:DBCOLUMN_COLLATINGSEQUENCE.eKind
0x18000f77c  movups  xmmword ptr [rax+50h], xmm1
0x18000f780  movups  xmm0, xmmword ptr cs:DBCOLUMN_COMPUTEMODE.uGuid
0x18000f787  movups  xmmword ptr [rax+60h], xmm0
0x18000f78b  movups  xmm1, xmmword ptr cs:DBCOLUMN_COMPUTEMODE.eKind
0x18000f792  movups  xmmword ptr [rax+70h], xmm1
0x18000f796  movups  xmm0, xmmword ptr cs:DBCOLUMN_DEFAULTVALUE.uGuid
0x18000f79d  movups  xmmword ptr [rax+80h], xmm0
0x18000f7a4  movups  xmm1, xmmword ptr cs:DBCOLUMN_DEFAULTVALUE.eKind
0x18000f7ab  movups  xmmword ptr [rax+90h], xmm1
0x18000f7b2  movups  xmm0, xmmword ptr cs:DBCOLUMN_DOMAINNAME.uGuid
0x18000f7b9  movups  xmmword ptr [rax+0A0h], xmm0
0x18000f7c0  movups  xmm1, xmmword ptr cs:DBCOLUMN_DOMAINNAME.eKind
0x18000f7c7  movups  xmmword ptr [rax+0B0h], xmm1
0x18000f7ce  movups  xmm0, xmmword ptr cs:DBCOLUMN_HASDEFAULT.uGuid
0x18000f7d5  movups  xmmword ptr [rax+0C0h], xmm0
0x18000f7dc  movups  xmm1, xmmword ptr cs:DBCOLUMN_HASDEFAULT.eKind
0x18000f7e3  movups  xmmword ptr [rax+0D0h], xmm1
0x18000f7ea  movups  xmm0, xmmword ptr cs:DBCOLUMN_ISAUTOINCREMENT.uGuid
0x18000f7f1  movups  xmmword ptr [rax+0E0h], xmm0
0x18000f7f8  movups  xmm1, xmmword ptr cs:DBCOLUMN_ISAUTOINCREMENT.eKind
0x18000f7ff  movups  xmmword ptr [rax+0F0h], xmm1
0x18000f806  movups  xmm0, xmmword ptr cs:DBCOLUMN_ISCASESENSITIVE.uGuid
0x18000f80d  movups  xmmword ptr [rax+100h], xmm0
0x18000f814  movups  xmm1, xmmword ptr cs:DBCOLUMN_ISCASESENSITIVE.eKind
0x18000f81b  movups  xmmword ptr [rax+110h], xmm1
0x18000f822  movups  xmm0, xmmword ptr cs:DBCOLUMN_ISSEARCHABLE.uGuid
0x18000f829  movups  xmmword ptr [rax+120h], xmm0
0x18000f830  movups  xmm1, xmmword ptr cs:DBCOLUMN_ISSEARCHABLE.eKind
0x18000f837  movups  xmmword ptr [rax+130h], xmm1
0x18000f83e  movups  xmm0, xmmword ptr cs:DBCOLUMN_ISUNIQUE.uGuid
0x18000f845  movups  xmmword ptr [rax+140h], xmm0
0x18000f84c  movups  xmm1, xmmword ptr cs:DBCOLUMN_ISUNIQUE.eKind
0x18000f853  movups  xmmword ptr [rax+150h], xmm1
0x18000f85a  movups  xmm0, xmmword ptr cs:DBCOLUMN_BASECATALOGNAME.uGuid
0x18000f861  movups  xmmword ptr [rax+160h], xmm0
0x18000f868  movups  xmm1, xmmword ptr cs:DBCOLUMN_BASECATALOGNAME.eKind
0x18000f86f  movups  xmmword ptr [rax+170h], xmm1
0x18000f876  movups  xmm0, xmmword ptr cs:DBCOLUMN_BASESCHEMANAME.uGuid
0x18000f87d  movups  xmmword ptr [rax+180h], xmm0
0x18000f884  movups  xmm1, xmmword ptr cs:DBCOLUMN_BASESCHEMANAME.eKind
0x18000f88b  movups  xmmword ptr [rax+190h], xmm1
0x18000f892  movups  xmm0, xmmword ptr cs:DBCOLUMN_DOMAINCATALOG.uGuid
0x18000f899  movups  xmmword ptr [rax+1A0h], xmm0
0x18000f8a0  movups  xmm1, xmmword ptr cs:DBCOLUMN_DOMAINCATALOG.eKind
0x18000f8a7  movups  xmmword ptr [rax+1B0h], xmm1
0x18000f8ae  movups  xmm0, xmmword ptr cs:DBCOLUMN_DOMAINSCHEMA.uGuid
0x18000f8b5  movups  xmmword ptr [rax+1C0h], xmm0
0x18000f8bc  movups  xmm1, xmmword ptr cs:DBCOLUMN_DOMAINSCHEMA.eKind
0x18000f8c3  movups  xmmword ptr [rax+1D0h], xmm1
0x18000f8ca  movups  xmm0, xmmword ptr cs:DBCOLUMN_DATETIMEPRECISION.uGuid
0x18000f8d1  movups  xmmword ptr [rax+1E0h], xmm0
0x18000f8d8  movups  xmm1, xmmword ptr cs:DBCOLUMN_DATETIMEPRECISION.eKind
0x18000f8df  movups  xmmword ptr [rax+1F0h], xmm1
0x18000f8e6  movups  xmm0, xmmword ptr cs:DBCOLUMN_OCTETLENGTH.uGuid
0x18000f8ed  movups  xmmword ptr [rax+200h], xmm0
0x18000f8f4  movups  xmm1, xmmword ptr cs:DBCOLUMN_OCTETLENGTH.eKind
0x18000f8fb  movups  xmmword ptr [rax+210h], xmm1
0x18000f902  movups  xmm0, xmmword ptr cs:DBCOLUMN_CLSID.uGuid
0x18000f909  movups  xmmword ptr [rax+220h], xmm0
0x18000f910  movups  xmm1, xmmword ptr cs:DBCOLUMN_CLSID.eKind
0x18000f917  movups  xmmword ptr [rax+230h], xmm1
0x18000f91e  movups  xmm0, cs:xmmword_1800385D0
0x18000f925  movups  xmmword ptr [rax+240h], xmm0
0x18000f92c  movups  xmm1, cs:xmmword_1800385E0
0x18000f933  movups  xmmword ptr [rax+250h], xmm1
0x18000f93a  movups  xmm0, cs:xmmword_1800385B0
0x18000f941  movups  xmmword ptr [rax+260h], xmm0
0x18000f948  movups  xmm1, cs:xmmword_1800385C0
0x18000f94f  movups  xmmword ptr [rax+270h], xmm1
0x18000f956  movups  xmm0, cs:xmmword_180038590
0x18000f95d  movups  xmmword ptr [rax+280h], xmm0
0x18000f964  movups  xmm1, cs:xmmword_1800385A0
0x18000f96b  movups  xmmword ptr [rax+290h], xmm1
0x18000f972  mov     dword ptr [rdi+170h], 15h
0x18000f97c  mov     [rdi+178h], rax
0x18000f983  mov     rcx, rdi; this
0x18000f986  call    ?Init@CRowset@@QEAAJXZ; CRowset::Init(void)
0x18000f98b  mov     ebx, eax
0x18000f98d  test    eax, eax
0x18000f98f  jns     short loc_18000F9D1
0x18000f991  test    byte ptr cs:_bidGblFlags, 2
0x18000f998  jz      short loc_18000F9C9
0x18000f99a  mov     rax, cs:off_1800498C0; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f9a1  test    rax, rax
0x18000f9a4  jz      short loc_18000F9C9
0x18000f9a6  mov     [rsp+98h+var_78], 0B7h
0x18000f9ae  mov     r9d, ebx
0x18000f9b1  mov     r8, cs:off_1800498C0; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f9b8  mov     edx, 2DC00h
0x18000f9bd  mov     rcx, cs:off_1800491C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000f9c4  call    _bidTraceW
0x18000f9c9  mov     ecx, ebx; int
0x18000f9cb  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000f9d1  jmp     short loc_18000F9DB
0x18000f9d3  mov     r14d, dword ptr [rsp+98h+arg_0]
0x18000f9db  mov     eax, r14d
0x18000f9de  jmp     short loc_18000F9E5
0x18000f9e0  mov     eax, 80004005h
0x18000f9e5  add     rsp, 78h
0x18000f9e9  pop     r14
0x18000f9eb  pop     rdi
0x18000f9ec  pop     rsi
0x18000f9ed  pop     rbx
0x18000f9ee  retn
```
