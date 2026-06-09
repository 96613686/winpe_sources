# CSchema::FInit(ulong,tagVARIANT const * const,ulong,tagDBPROPSET * const,_GUID const &,IUnknown *,IUnknown * *)

- ea: `0x1800b1df0`
- end: `0x1800b2700`
- name: `?FInit@CSchema@@UEAAJKQEBUtagVARIANT@@KQEAUtagDBPROPSET@@AEBU_GUID@@PEAUIUnknown@@PEAPEAU5@@Z`
- size: `2320`
- prototype: `__int64 __usercall@<rax>(CSchema *__hidden this@<rcx>, unsigned int@<edx>, const struct tagVARIANT *const@<r8>, unsigned int@<r9d>, struct tagDBPROPSET *const, const struct _GUID *, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180003030`
- `0x180003d80`
- `0x180009340`
- `0x1800290c0`
- `0x18002ad90`
- `0x180056fa0`
- `0x18005be20`
- `0x180084ef0`
- `0x1800af320`
- `0x1800b1df0`
- `0x1800b3c00`
- `0x1800b3ce0`
- `0x1800b9bc0`
- `0x1800bac40`
- `0x1800bb060`
- `0x1800bd540`
- `0x18013e4b8`
- `0x1801ad6a0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800b1f6a`
- `OLEAUT32!__imp_VariantInit` at `0x1800b1f6a`
- `OLEAUT32!__imp_VariantCopy` at `0x1800b1fcd`
- `OLEAUT32!__imp_VariantCopy` at `0x1800b1fcd`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800b212a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800b212a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSchema::FInit(
        CSchema *this,
        unsigned int a2,
        const struct tagVARIANT *const a3,
        unsigned int a4,
        struct tagDBPROPSET *const a5,
        const struct _GUID *a6,
        struct IUnknown *a7,
        struct IUnknown **a8)
{
  unsigned __int64 v9; // r13
  unsigned int v11; // ebp
  CRowset *v12; // r12
  CRowsetProps *v13; // rsi
  int v14; // eax
  int v15; // ebx
  unsigned __int64 v16; // rbp
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // r13
  const struct tagVARIANT *v21; // rdx
  const struct tagVARIANT *v22; // rbp
  HRESULT v23; // eax
  int v24; // eax
  const struct tagDBPROPSET *v25; // r13
  unsigned int v26; // r10d
  __int64 v27; // rdx
  __int64 v28; // rax
  ULONG cProperties; // r8d
  DBPROP *rgProperties; // r9
  CRowsetProps *v31; // rax
  int v32; // eax
  int OnlyIIDProperty; // eax
  int CapableCC; // eax
  int v35; // eax
  int v36; // eax
  CRowset *v37; // rax
  int v38; // eax
  int v39; // eax
  __int64 v43; // [rsp+68h] [rbp-80h] BYREF
  struct IUnknown **v44; // [rsp+70h] [rbp-78h]
  struct IUnknown *v45; // [rsp+78h] [rbp-70h]
  __int64 v46; // [rsp+80h] [rbp-68h] BYREF
  unsigned int v47; // [rsp+88h] [rbp-60h] BYREF

  v9 = a2;
  v45 = a7;
  v44 = a8;
  v11 = 0;
  v47 = 0;
  v46 = 0;
  v12 = 0;
  v13 = 0;
  v43 = -1;
  v14 = CCommand::FInit(this, 1u, 0);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_180260468, 178185, (unsigned int)v14);
      goto LABEL_103;
    }
    goto LABEL_105;
  }
  _mm_lfence();
  *(GUID *)((char *)this + 1256) = IID_IDBSchemaRowset;
  CCommand::ApplyGeneralTimeout(this);
  if ( !(_DWORD)v9 )
    goto LABEL_18;
  *((_DWORD *)this + 386) = v9;
  v16 = v9;
  v17 = 24 * v9;
  if ( !is_mul_ok(v9, 0x18u) )
    v17 = -1;
  v18 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, v17);
  *((_QWORD *)this + 194) = v18;
  if ( !v18 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v15 = bidTraceHR(off_180260468, 193545, 2147942414LL);
      goto LABEL_103;
    }
    goto LABEL_10;
  }
  v19 = 0;
  do
  {
    VariantInit((VARIANTARG *)(v19 + *((_QWORD *)this + 194)));
    v19 += 24;
    --v16;
  }
  while ( v16 );
  v20 = 0;
  v21 = a3;
  v22 = a3;
  while ( 2 )
  {
    switch ( v22->vt )
    {
      case 0u:
      case 1u:
      case 2u:
      case 3u:
      case 8u:
      case 0xBu:
      case 0x10u:
      case 0x11u:
      case 0x12u:
      case 0x13u:
      case 0x16u:
      case 0x17u:
        v23 = VariantCopy((VARIANTARG *)(*((_QWORD *)this + 194) + 24 * v20), &v21[v20]);
        v15 = v23;
        if ( v23 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_105;
          _mm_lfence();
          bidTraceHR(off_180260468, 220169, (unsigned int)v23);
          goto LABEL_103;
        }
        v20 = (unsigned int)(v20 + 1);
        ++v22;
        v21 = a3;
        if ( (unsigned int)v20 < a2 )
          continue;
        v11 = 0;
LABEL_18:
        if ( !a4 )
        {
          v25 = a5;
          goto LABEL_44;
        }
        _mm_lfence();
        v24 = (**(__int64 (__fastcall ***)(CSchema *, GUID *, __int64 *))this)(this, &IID_ICommandProperties, &v46);
        v15 = v24;
        if ( v24 >= 0 )
        {
          v25 = a5;
          v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagDBPROPSET *const))(*(_QWORD *)v46 + 32LL))(
                  v46,
                  a4,
                  a5);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
          if ( v15 == -2147217887 || v15 == 265946 )
          {
            SetErrorInfo(0, 0);
            v26 = 0;
            while ( 1 )
            {
              v27 = 0;
              v28 = v26;
              cProperties = a5[v28].cProperties;
              if ( cProperties )
                break;
LABEL_38:
              if ( ++v26 >= a4 )
              {
                v11 = 265946;
                goto LABEL_44;
              }
            }
            rgProperties = a5[v28].rgProperties;
            while ( !rgProperties[v27].dwStatus || rgProperties[v27].dwOptions == 1 )
            {
              v27 = (unsigned int)(v27 + 1);
              if ( (unsigned int)v27 >= cProperties )
                goto LABEL_38;
            }
            if ( (bidGblFlags & 2) != 0 )
              v15 = bidTraceHR(off_180260468, 253961, 2147749409LL);
            else
              v15 = -2147217887;
            goto LABEL_103;
          }
          if ( v15 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_105;
            _mm_lfence();
            bidTraceHR(off_180260468, 263177, (unsigned int)v15);
            goto LABEL_103;
          }
LABEL_44:
          v31 = (CRowsetProps *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                                  g_pMO,
                                  688);
          if ( v31 )
            v13 = CRowsetProps::CRowsetProps(v31, 1u);
          else
            v13 = 0;
          if ( v13 )
          {
            v32 = CRowsetProps::FInit(v13, this, (CSchema *)((char *)this + 448), 1u);
            v15 = v32;
            if ( v32 < 0 )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_105;
              _mm_lfence();
              bidTraceHR(off_180260468, 275465, (unsigned int)v32);
              goto LABEL_103;
            }
            if ( (*(_QWORD *)&a6->Data1 != *(_QWORD *)&IID_IRowset.Data1
               || *(_QWORD *)a6->Data4 != *(_QWORD *)IID_IRowset.Data4)
              && (*(_QWORD *)&a6->Data1 != *(_QWORD *)&IID_IColumnsInfo.Data1
               || *(_QWORD *)a6->Data4 != *(_QWORD *)IID_IColumnsInfo.Data4)
              && (*(_QWORD *)&a6->Data1 != *(_QWORD *)&IID_IAccessor.Data1
               || *(_QWORD *)a6->Data4 != *(_QWORD *)IID_IAccessor.Data4)
              && (*(_QWORD *)&a6->Data1 != *(_QWORD *)&IID_IRowsetInfo.Data1
               || *(_QWORD *)a6->Data4 != *(_QWORD *)IID_IRowsetInfo.Data4)
              && (*(_QWORD *)&a6->Data1 != *(_QWORD *)&IID_IUnknown.Data1
               || *(_QWORD *)a6->Data4 != *(_QWORD *)IID_IUnknown.Data4)
              && (*(_QWORD *)&a6->Data1 != *(_QWORD *)&IID_IMultipleResults.Data1
               || *(_QWORD *)a6->Data4 != *(_QWORD *)IID_IMultipleResults.Data4) )
            {
              _mm_lfence();
              OnlyIIDProperty = CSchema::SetReadOnlyIIDProperty(this, v13, a6);
              v15 = OnlyIIDProperty;
              if ( OnlyIIDProperty < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_105;
                _mm_lfence();
                bidTraceHR(off_180260468, 287753, (unsigned int)OnlyIIDProperty);
                goto LABEL_103;
              }
            }
            _mm_lfence();
            CapableCC = CRowsetProps::FindCapableCC(v13, *((struct CStmt **)this + 150), &v47, a6, 0, 0);
            v15 = CapableCC;
            if ( CapableCC < 0 )
            {
              if ( CapableCC == -2147217887 && a4 )
              {
                _mm_lfence();
                CUtlProps2::SetPropertyStatus(v13, a4, v25);
              }
              goto LABEL_103;
            }
            _mm_lfence();
            v35 = CStmt::HandleFirehoseModeAtExecute(*((CStmt **)this + 150), &IID_IDBSchemaRowset, 0, 1);
            v15 = v35;
            if ( v35 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                _mm_lfence();
                bidTraceHR(off_180260468, 308233, (unsigned int)v35);
              }
              goto LABEL_107;
            }
            _mm_lfence();
            v15 = (*(__int64 (__fastcall **)(CSchema *))(*(_QWORD *)this + 48LL))(this);
            if ( v15 < 0 )
              goto LABEL_102;
            _mm_lfence();
            v36 = CRowsetProps::ReValidate(v13, *((struct CStmt **)this + 150), &v47, 0, &IID_IDBSchemaRowset);
            v15 = v36;
            if ( (v36 == -2147217887 || v36 == 265946) && a4 )
            {
              _mm_lfence();
              CUtlProps2::SetPropertyStatus(v13, a4, v25);
            }
            if ( v15 < 0 )
            {
LABEL_102:
              _mm_lfence();
              CStmt::SQLFreeStmt(*((CStmt **)this + 150), 0, 0);
              goto LABEL_103;
            }
            _mm_lfence();
            if ( v15 == 265946 )
              v11 = 265946;
            CStmt::SQLCursorRowCount(*((CStmt **)this + 150), &v43);
            v37 = (CRowset *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                               g_pMO,
                               840);
            if ( v37 )
              v12 = CRowset::CRowset(v37, v45, v43);
            else
              v12 = 0;
            _mm_lfence();
            if ( v12 )
            {
              (*(void (__fastcall **)(CRowset *))(*(_QWORD *)v12 + 8LL))(v12);
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 55) + 8LL))(*((_QWORD *)this + 55));
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 55) + 40LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 55) + 40LL));
              (*(void (__fastcall **)(CSchema *))(*(_QWORD *)this + 8LL))(this);
              v15 = CRowset::FInit(
                      v12,
                      v13,
                      v47,
                      *((struct CStmt **)this + 150),
                      *((struct CBaseObj **)this + 55),
                      *((struct CDBSession **)this + 55),
                      this,
                      0,
                      0);
              if ( v15 >= 0 )
              {
                _mm_lfence();
                if ( v15 == 265946 )
                {
                  v11 = 265946;
                  if ( a4 )
                  {
                    _mm_lfence();
                    CUtlProps2::SetPropertyStatus(v13, a4, v25);
                  }
                }
                v13 = 0;
                v38 = (**(__int64 (__fastcall ***)(CRowset *, const struct _GUID *, struct IUnknown **))v12)(
                        v12,
                        a6,
                        v44);
                v15 = v38;
                if ( v38 >= 0 )
                {
                  _mm_lfence();
                  (*(void (__fastcall **)(CRowset *))(*(_QWORD *)v12 + 16LL))(v12);
                  if ( !v15 )
                    return v11;
                  return (unsigned int)v15;
                }
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_105;
                _mm_lfence();
                bidTraceHR(off_180260468, 392201, (unsigned int)v38);
              }
              else
              {
                if ( a4 )
                {
                  _mm_lfence();
                  CUtlProps2::SetPropertyStatus(v13, a4, v25);
                }
                v13 = 0;
              }
LABEL_103:
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_105;
              v39 = bidTraceHR(off_180260468, 399369, (unsigned int)v15);
              goto LABEL_106;
            }
            CStmt::SQLFreeStmt(*((CStmt **)this + 150), 0, 0);
            if ( (bidGblFlags & 2) != 0 )
            {
              v15 = bidTraceHR(off_180260468, 338953, 2147942414LL);
              goto LABEL_103;
            }
          }
          else if ( (bidGblFlags & 2) != 0 )
          {
            v15 = bidTraceHR(off_180260468, 271369, 2147942414LL);
            goto LABEL_103;
          }
LABEL_10:
          v15 = -2147024882;
          goto LABEL_103;
        }
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_180260468, 234505, (unsigned int)v24);
          goto LABEL_103;
        }
LABEL_105:
        v39 = v15;
LABEL_106:
        CError::PostHResult(g_pCError, v39, &IID_IDBSchemaRowset);
        if ( v13 )
LABEL_107:
          (*(void (__fastcall **)(CRowsetProps *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 1);
        if ( v12 )
          (*(void (__fastcall **)(CRowset *))(*(_QWORD *)v12 + 16LL))(v12);
        return (unsigned int)v15;
      default:
        if ( (bidGblFlags & 2) != 0 )
          v15 = bidTraceHR(off_180260468, 224265, 2147942487LL);
        else
          v15 = -2147024809;
        goto LABEL_103;
    }
  }
}

```

## disassembly

```asm
0x1800b1df0  mov     r11, rsp
0x1800b1df3  push    rbx
0x1800b1df4  push    rbp
0x1800b1df5  push    rsi
0x1800b1df6  push    rdi
0x1800b1df7  push    r12
0x1800b1df9  push    r13
0x1800b1dfb  push    r14
0x1800b1dfd  push    r15
0x1800b1dff  sub     rsp, 0A8h
0x1800b1e06  mov     rax, cs:__security_cookie
0x1800b1e0d  xor     rax, rsp
0x1800b1e10  mov     [rsp+0E8h+var_58], rax
0x1800b1e18  mov     r14d, r9d
0x1800b1e1b  mov     [rsp+0E8h+var_88], r8
0x1800b1e20  mov     r13d, edx
0x1800b1e23  mov     [rsp+0E8h+var_94], r13d
0x1800b1e28  mov     rdi, rcx
0x1800b1e2b  mov     rax, [rsp+0E8h+arg_20]
0x1800b1e33  mov     [rsp+0E8h+var_90], rax
0x1800b1e38  mov     r15, [rsp+0E8h+arg_28]
0x1800b1e40  mov     rax, [rsp+0E8h+arg_30]
0x1800b1e48  mov     [rsp+0E8h+var_70], rax
0x1800b1e4d  mov     rax, [rsp+0E8h+arg_38]
0x1800b1e55  mov     [rsp+0E8h+var_78], rax
0x1800b1e5a  xor     eax, eax
0x1800b1e5c  mov     ebp, eax
0x1800b1e5e  mov     [rsp+0E8h+var_98], eax
0x1800b1e62  mov     [r11-60h], eax
0x1800b1e66  mov     [r11-68h], rax
0x1800b1e6a  mov     r12d, eax
0x1800b1e6d  mov     esi, eax
0x1800b1e6f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800b1e76  mov     [r11-80h], rax
0x1800b1e7a  mov     edx, 1; unsigned __int16
0x1800b1e7f  xor     r8d, r8d; struct CRowsetProps *
0x1800b1e82  call    ?FInit@CCommand@@QEAAJGPEAVCRowsetProps@@@Z; CCommand::FInit(ushort,CRowsetProps *)
0x1800b1e87  mov     ebx, eax
0x1800b1e89  test    eax, eax
0x1800b1e8b  jns     short loc_1800B1EB6
0x1800b1e8d  test    byte ptr cs:_bidGblFlags, 2
0x1800b1e94  jz      loc_1800B2672
0x1800b1e9a  lfence
0x1800b1e9d  mov     r8d, eax
0x1800b1ea0  mov     edx, 2B809h
0x1800b1ea5  mov     rcx, cs:off_180260468; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800b1eac  call    _bidTraceHR
0x1800b1eb1  jmp     loc_1800B2653
0x1800b1eb6  lfence
0x1800b1eb9  movups  xmm0, xmmword ptr cs:IID_IDBSchemaRowset.Data1
0x1800b1ec0  movups  xmmword ptr [rdi+4E8h], xmm0
0x1800b1ec7  mov     rcx, rdi; this
0x1800b1eca  call    ?ApplyGeneralTimeout@CCommand@@QEAAXXZ; CCommand::ApplyGeneralTimeout(void)
0x1800b1ecf  test    r13d, r13d
0x1800b1ed2  jz      loc_1800B1FF7
0x1800b1ed8  mov     [rdi+608h], r13d
0x1800b1edf  mov     rbp, r13
0x1800b1ee2  mov     eax, 18h
0x1800b1ee7  mul     r13
0x1800b1eea  mov     rdx, rax
0x1800b1eed  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800b1ef4  cmovb   rdx, rax
0x1800b1ef8  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1800b1eff  mov     rax, [rcx]
0x1800b1f02  mov     rax, [rax+70h]
0x1800b1f06  call    cs:__guard_dispatch_icall_fptr
0x1800b1f0c  nop
0x1800b1f0d  mov     [rdi+610h], rax
0x1800b1f14  test    rax, rax
0x1800b1f17  jnz     short loc_1800B1F4A
0x1800b1f19  test    byte ptr cs:_bidGblFlags, 2
0x1800b1f20  jz      short loc_1800B1F40
0x1800b1f22  mov     edx, 2F409h
0x1800b1f27  mov     r8d, 8007000Eh
0x1800b1f2d  mov     rcx, cs:off_180260468; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800b1f34  call    _bidTraceHR
0x1800b1f39  mov     ebx, eax
0x1800b1f3b  jmp     loc_1800B2653
0x1800b1f40  mov     ebx, 8007000Eh
0x1800b1f45  jmp     loc_1800B2653
0x1800b1f4a  test    r13d, r13d
0x1800b1f4d  jz      loc_1800B1FF3
0x1800b1f53  xor     ebx, ebx
0x1800b1f55  nop     word ptr [rax+rax+00000000h]
0x1800b1f60  mov     rcx, [rdi+610h]
0x1800b1f67  add     rcx, rbx; pvarg
0x1800b1f6a  call    cs:__imp_VariantInit
0x1800b1f70  add     rbx, 18h
0x1800b1f74  sub     rbp, 1
0x1800b1f78  jnz     short loc_1800B1F60
0x1800b1f7a  xor     r13d, r13d
0x1800b1f7d  mov     rdx, [rsp+0E8h+var_88]
0x1800b1f82  mov     rbp, rdx
0x1800b1f85  lea     r8, cs:180000000h
0x1800b1f8c  nop     dword ptr [rax+00h]
0x1800b1f90  movzx   eax, word ptr [rbp+0]
0x1800b1f94  cmp     eax, 17h; switch 24 cases
0x1800b1f97  ja      def_1800B1FB1; jumptable 00000001800B1FB1 default case, cases 4-7,9,10,12-15,20,21
0x1800b1f9d  movzx   eax, ds:(byte_1800B26E8 - 180000000h)[r8+rax]
0x1800b1fa6  mov     ecx, ds:(jpt_1800B1FB1 - 180000000h)[r8+rax*4]
0x1800b1fae  add     rcx, r8
0x1800b1fb1  jmp     rcx; switch jump
0x1800b1fb3  lea     rcx, ds:0[r13*2]; jumptable 00000001800B1FB1 cases 0-3,8,11,16-19,22,23
0x1800b1fbb  add     rcx, r13
0x1800b1fbe  lea     rdx, [rdx+rcx*8]; pvargSrc
0x1800b1fc2  mov     rax, [rdi+610h]
0x1800b1fc9  lea     rcx, [rax+rcx*8]; pvargDest
0x1800b1fcd  call    cs:__imp_VariantCopy
0x1800b1fd3  mov     ebx, eax
0x1800b1fd5  test    eax, eax
0x1800b1fd7  js      short loc_1800B2054
0x1800b1fd9  inc     r13d
0x1800b1fdc  add     rbp, 18h
0x1800b1fe0  cmp     r13d, [rsp+0E8h+var_94]
0x1800b1fe5  mov     rdx, [rsp+0E8h+var_88]
0x1800b1fea  lea     r8, cs:180000000h
0x1800b1ff1  jb      short loc_1800B1F90
0x1800b1ff3  mov     ebp, [rsp+0E8h+var_98]
0x1800b1ff7  test    r14d, r14d
0x1800b1ffa  jz      loc_1800B21BB
0x1800b2000  lfence
0x1800b2003  mov     rax, [rdi]
0x1800b2006  lea     r8, [rsp+0E8h+var_68]
0x1800b200e  lea     rdx, IID_ICommandProperties
0x1800b2015  mov     rcx, rdi
0x1800b2018  mov     rax, [rax]
0x1800b201b  call    cs:__guard_dispatch_icall_fptr
0x1800b2021  mov     ebx, eax
0x1800b2023  test    eax, eax
0x1800b2025  jns     loc_1800B20AE
0x1800b202b  test    byte ptr cs:_bidGblFlags, 2
0x1800b2032  jz      loc_1800B2672
0x1800b2038  lfence
0x1800b203b  mov     r8d, eax
0x1800b203e  mov     edx, 39409h
0x1800b2043  mov     rcx, cs:off_180260468; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800b204a  call    _bidTraceHR
0x1800b204f  jmp     loc_1800B2653
0x1800b2054  test    byte ptr cs:_bidGblFlags, 2
0x1800b205b  jz      loc_1800B2672
0x1800b2061  lfence
0x1800b2064  mov     r8d, eax
0x1800b2067  mov     edx, 35C09h
0x1800b206c  mov     rcx, cs:off_180260468; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800b2073  call    _bidTraceHR
0x1800b2078  jmp     loc_1800B2653
0x1800b207d  test    byte ptr cs:_bidGblFlags, 2; jumptable 00000001800B1FB1 default case, cases 4-7,9,10,12-15,20,21
0x1800b2084  jz      short loc_1800B20A4
0x1800b2086  mov     edx, 36C09h
0x1800b208b  mov     r8d, 80070057h
0x1800b2091  mov     rcx, cs:off_180260468; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800b2098  call    _bidTraceHR
0x1800b209d  mov     ebx, eax
0x1800b209f  jmp     loc_1800B2653
0x1800b20a4  mov     ebx, 80070057h
0x1800b20a9  jmp     loc_1800B2653
0x1800b20ae  mov     rcx, [rsp+0E8h+var_68]
0x1800b20b6  mov     rax, [rcx]
0x1800b20b9  mov     r13, [rsp+0E8h+var_90]
0x1800b20be  mov     r8, r13
0x1800b20c1  mov     edx, r14d
0x1800b20c4  mov     rax, [rax+20h]
0x1800b20c8  call    cs:__guard_dispatch_icall_fptr
0x1800b20ce  mov     ebx, eax
0x1800b20d0  mov     rcx, [rsp+0E8h+var_68]
0x1800b20d8  mov     rax, [rcx]
0x1800b20db  mov     rax, [rax+10h]
0x1800b20df  call    cs:__guard_dispatch_icall_fptr
0x1800b20e5  cmp     ebx, 80040E21h
0x1800b20eb  jz      short loc_1800B2126
0x1800b20ed  cmp     ebx, 40EDAh
0x1800b20f3  jz      short loc_1800B2126
0x1800b20f5  test    ebx, ebx
0x1800b20f7  jns     loc_1800B21C0
0x1800b20fd  test    byte ptr cs:_bidGblFlags, 2
0x1800b2104  jz      loc_1800B2672
0x1800b210a  lfence
0x1800b210d  mov     r8d, ebx
0x1800b2110  mov     edx, 40409h
0x1800b2115  mov     rcx, cs:off_180260468; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800b211c  call    _bidTraceHR
0x1800b2121  jmp     loc_1800B2653
0x1800b2126  xor     edx, edx; perrinfo
0x1800b2128  xor     ecx, ecx; dwReserved
0x1800b212a  call    cs:__imp_SetErrorInfo
0x1800b2130  xor     r10d, r10d
0x1800b2133  nop     dword ptr [rax+00h]
0x1800b2137  nop     word ptr [rax+rax+00000000h]
0x1800b2140  xor     edx, edx
0x1800b2142  mov     eax, r10d
0x1800b2145  shl     rax, 5
0x1800b2149  mov     r8d, [rax+r13+8]
0x1800b214e  test    r8d, r8d
0x1800b2151  jz      short loc_1800B217B
0x1800b2153  mov     r9, [rax+r13]
0x1800b2157  nop     word ptr [rax+rax+00000000h]
0x1800b2160  lea     rcx, [rdx+rdx*8]
0x1800b2164  cmp     dword ptr [r9+rcx*8+8], 0
0x1800b216a  jz      short loc_1800B2174
0x1800b216c  cmp     dword ptr [r9+rcx*8+4], 1
0x1800b2172  jnz     short loc_1800B218A
0x1800b2174  inc     edx
0x1800b2176  cmp     edx, r8d
0x1800b2179  jb      short loc_1800B2160
0x1800b217b  inc     r10d
0x1800b217e  cmp     r10d, r14d
0x1800b2181  jb      short loc_1800B2140
0x1800b2183  mov     ebp, 40EDAh
0x1800b2188  jmp     short loc_1800B21C0
0x1800b218a  test    byte ptr cs:_bidGblFlags, 2
0x1800b2191  jz      short loc_1800B21B1
0x1800b2193  mov     edx, 3E009h
0x1800b2198  mov     r8d, 80040E21h
0x1800b219e  mov     rcx, cs:off_180260468; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800b21a5  call    _bidTraceHR
0x1800b21aa  mov     ebx, eax
0x1800b21ac  jmp     loc_1800B2653
0x1800b21b1  mov     ebx, 80040E21h
0x1800b21b6  jmp     loc_1800B2653
0x1800b21bb  mov     r13, [rsp+0E8h+var_90]
0x1800b21c0  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1800b21c7  mov     rax, [rcx]
0x1800b21ca  mov     edx, 2B0h
0x1800b21cf  mov     rax, [rax+58h]
0x1800b21d3  call    cs:__guard_dispatch_icall_fptr
0x1800b21d9  nop
0x1800b21da  mov     [rsp+0E8h+var_90], rax
0x1800b21df  test    rax, rax
0x1800b21e2  jz      short loc_1800B21F6
0x1800b21e4  mov     edx, 1; unsigned int
0x1800b21e9  mov     rcx, rax; this
0x1800b21ec  call    ??0CRowsetProps@@QEAA@K@Z; CRowsetProps::CRowsetProps(ulong)
0x1800b21f1  mov     rsi, rax
0x1800b21f4  jmp     short loc_1800B21F8
0x1800b21f6  xor     esi, esi
0x1800b21f8  test    rsi, rsi
0x1800b21fb  jnz     short loc_1800B2228
0x1800b21fd  test    byte ptr cs:_bidGblFlags, 2
0x1800b2204  jz      loc_1800B1F40
0x1800b220a  mov     edx, 42409h
0x1800b220f  mov     r8d, 8007000Eh
0x1800b2215  mov     rcx, cs:off_180260468; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800b221c  call    _bidTraceHR
0x1800b2221  mov     ebx, eax
0x1800b2223  jmp     loc_1800B2653
0x1800b2228  mov     r9d, 1; unsigned __int16
0x1800b222e  lea     r8, [rdi+1C0h]; struct CRowsetProps *
0x1800b2235  mov     rdx, rdi; struct CCommand *
0x1800b2238  mov     rcx, rsi; this
0x1800b223b  call    ?FInit@CRowsetProps@@QEAAJPEAVCCommand@@PEBV1@G@Z; CRowsetProps::FInit(CCommand *,CRowsetProps const *,ushort)
0x1800b2240  mov     ebx, eax
0x1800b2242  test    eax, eax
0x1800b2244  jns     short loc_1800B226F
0x1800b2246  test    byte ptr cs:_bidGblFlags, 2
0x1800b224d  jz      loc_1800B2672
0x1800b2253  lfence
0x1800b2256  mov     r8d, eax
0x1800b2259  mov     edx, 43409h
0x1800b225e  mov     rcx, cs:off_180260468; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800b2265  call    _bidTraceHR
0x1800b226a  jmp     loc_1800B2653
0x1800b226f  mov     rax, [r15]
0x1800b2272  cmp     rax, qword ptr cs:IID_IRowset.Data1
0x1800b2279  jnz     short loc_1800B228C
0x1800b227b  mov     rax, [r15+8]
0x1800b227f  cmp     rax, qword ptr cs:IID_IRowset.Data4
0x1800b2286  jz      loc_1800B2351
0x1800b228c  mov     rax, [r15]
0x1800b228f  cmp     rax, qword ptr cs:IID_IColumnsInfo.Data1
0x1800b2296  jnz     short loc_1800B22A9
0x1800b2298  mov     rax, [r15+8]
0x1800b229c  cmp     rax, qword ptr cs:IID_IColumnsInfo.Data4
0x1800b22a3  jz      loc_1800B2351
0x1800b22a9  mov     rax, [r15]
0x1800b22ac  cmp     rax, qword ptr cs:IID_IAccessor.Data1
0x1800b22b3  jnz     short loc_1800B22C6
0x1800b22b5  mov     rax, [r15+8]
0x1800b22b9  cmp     rax, qword ptr cs:IID_IAccessor.Data4
0x1800b22c0  jz      loc_1800B2351
0x1800b22c6  mov     rax, [r15]
0x1800b22c9  cmp     rax, qword ptr cs:IID_IRowsetInfo.Data1
0x1800b22d0  jnz     short loc_1800B22DF
0x1800b22d2  mov     rax, [r15+8]
0x1800b22d6  cmp     rax, qword ptr cs:IID_IRowsetInfo.Data4
0x1800b22dd  jz      short loc_1800B2351
0x1800b22df  mov     rax, [r15]
0x1800b22e2  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800b22e9  jnz     short loc_1800B22F8
0x1800b22eb  mov     rax, [r15+8]
0x1800b22ef  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800b22f6  jz      short loc_1800B2351
0x1800b22f8  mov     rax, [r15]
0x1800b22fb  cmp     rax, qword ptr cs:IID_IMultipleResults.Data1
0x1800b2302  jnz     short loc_1800B2311
0x1800b2304  mov     rax, [r15+8]
0x1800b2308  cmp     rax, qword ptr cs:IID_IMultipleResults.Data4
0x1800b230f  jz      short loc_1800B2351
0x1800b2311  lfence
0x1800b2314  mov     r8, r15; struct _GUID *
0x1800b2317  mov     rdx, rsi; struct CRowsetProps *
  ... truncated ...
```
