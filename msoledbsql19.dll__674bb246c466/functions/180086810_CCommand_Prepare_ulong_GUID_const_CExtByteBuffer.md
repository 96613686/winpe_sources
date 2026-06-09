# CCommand::Prepare(ulong,_GUID const *,CExtByteBuffer * *)

- ea: `0x180086810`
- end: `0x180087064`
- name: `?Prepare@CCommand@@QEAAJKPEBU_GUID@@PEAPEAVCExtByteBuffer@@@Z`
- size: `2132`
- prototype: `__int64 __fastcall(CCommand *__hidden this, unsigned int, const struct _GUID *, struct CExtByteBuffer **)`
- caller_count: `11`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180084b40`
- `0x1800f2d70`
- `0x1800f66c0`
- `0x1800fd7b0`
- `0x1800ffed0`
- `0x180101ab0`
- `0x180103030`
- `0x180103560`
- `0x18011c390`
- `0x18011d240`
- `0x18011f6c0`

## callees

- `0x180003030`
- `0x180003824`
- `0x180003d80`
- `0x180009340`
- `0x180009700`
- `0x180009de0`
- `0x1800290c0`
- `0x1800844c0`
- `0x180084650`
- `0x180085360`
- `0x180086170`
- `0x180086730`
- `0x180086810`
- `0x1800890d0`
- `0x180089200`
- `0x1800b9bc0`
- `0x1800bac40`
- `0x1800bb060`
- `0x1800d84b0`
- `0x1800e0340`
- `0x1800e07d0`
- `0x1800e09b0`
- `0x1801336f4`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180086bab`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180086bec`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180086c17`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180086bab`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180086bec`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180086c17`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCommand::Prepare(CCommand *this, int a2, const struct _GUID *a3, struct CExtByteBuffer **a4)
{
  unsigned int v8; // r14d
  struct CExtByteBuffer *v9; // rdi
  int v10; // ecx
  __int64 v12; // rax
  __int64 v13; // rax
  wchar_t *v14; // r15
  unsigned __int64 v15; // rbp
  int v16; // r13d
  unsigned int LexToken; // eax
  int v18; // ecx
  int v19; // edi
  int v20; // eax
  int v21; // eax
  unsigned int v22; // ecx
  int v23; // eax
  char v24; // al
  unsigned int v25; // edi
  int v26; // eax
  CExtBaseBuffer *v27; // rax
  int v28; // eax
  __int64 v29; // rdx
  unsigned __int64 v30; // rax
  unsigned __int64 v31; // rax
  wchar_t *v32; // rdx
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rax
  char v36; // al
  CRowsetProps *v37; // rax
  CRowsetProps *v38; // rax
  int v39; // eax
  int CapableCC; // eax
  int v41; // eax
  CExtBaseBuffer *v42; // rbx
  unsigned __int64 v43; // [rsp+38h] [rbp-60h] BYREF
  CExtBaseBuffer *v44; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 v45; // [rsp+48h] [rbp-50h] BYREF

  v8 = 0;
  v44 = 0;
  v45 = 0;
  v43 = 0;
  if ( *a4 )
  {
    *((_DWORD *)this + 302) &= 0xFFFFFFB7;
    v9 = (struct CExtByteBuffer *)*((_QWORD *)this + 163);
    if ( v9 != *a4 )
    {
      if ( v9 )
      {
        CExtBaseBuffer::~CExtBaseBuffer(*((CExtBaseBuffer **)this + 163));
        operator delete(v9, 0x30u);
        *((_QWORD *)this + 163) = 0;
      }
    }
  }
  v10 = *((_DWORD *)this + 302);
  if ( (a2 & v10) == 0x40 )
    return 0;
  if ( (v10 & 8) != 0 )
  {
    if ( !*((_QWORD *)this + 163) )
    {
      if ( (bidGblFlags & 2) != 0 )
        v39 = bidTraceHR(off_1802603E8[0], 2373641, 2147549183LL);
      else
        v39 = -2147418113;
      goto LABEL_114;
    }
    if ( (a2 & v10) == 0x20 )
      CStmt::SQLFreeStmt(*((CStmt **)this + 150), 1u, 0);
    v35 = *((_QWORD *)this + 163);
    v14 = *(wchar_t **)(v35 + 32);
    v15 = *(_QWORD *)(v35 + 8) >> 1;
    v16 = (*(unsigned __int16 *)(*((_QWORD *)this + 150) + 552LL) >> 6) & 1;
LABEL_73:
    if ( a2 == 32 )
    {
      if ( (*((_DWORD *)this + 302) & 0x40000) != 0 )
      {
        CErrorData::PostStandardError((CCommand *)((char *)this + 1136), 0x9CFAu, 0, 0);
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ICommand.Data1
          && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_ICommand.Data4 )
        {
          v23 = CCommand::PostExecuteErrors(this, (CCommand *)((char *)this + 1136), a3);
          goto LABEL_115;
        }
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ICommandPrepare.Data1
          && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_ICommandPrepare.Data4 )
        {
          v23 = CCommand::PostPrepareErrors(this, (CCommand *)((char *)this + 1136));
          goto LABEL_115;
        }
        v36 = bidGblFlags;
        if ( (bidGblFlags & 2) != 0 )
        {
          v25 = bidTraceHR(off_1802603E8[0], 2398217, 2147500037LL);
          v36 = bidGblFlags;
        }
        else
        {
          v25 = -2147467259;
        }
        if ( (v36 & 2) != 0 )
        {
          v26 = bidTraceHR(off_1802603E8[0], 2399241, v25);
          goto LABEL_37;
        }
        goto LABEL_36;
      }
      v37 = (CRowsetProps *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                              g_pMO,
                              688);
      if ( v37 )
        v38 = CRowsetProps::CRowsetProps(v37, 1u);
      else
        v38 = 0;
      *((_QWORD *)this + 180) = v38;
      if ( !v38 )
      {
        if ( (bidGblFlags & 2) != 0 )
          v39 = bidTraceHR(off_1802603E8[0], 2411529, 2147942414LL);
        else
          v39 = -2147024882;
LABEL_114:
        v23 = CError::PostHResult(g_pCError, v39, a3);
        goto LABEL_115;
      }
      v28 = CRowsetProps::FInit(v38, this, (CCommand *)((char *)this + 448), 0);
      v25 = v28;
      _mm_lfence();
      if ( v28 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_43;
        v29 = 2417673;
        goto LABEL_42;
      }
      *((_DWORD *)this + 362) = 0;
      CapableCC = CRowsetProps::FindCapableCC(
                    *((CRowsetProps **)this + 180),
                    *((struct CStmt **)this + 150),
                    (unsigned int *)this + 362,
                    a3,
                    0,
                    0);
      v25 = CapableCC;
      if ( CapableCC < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802603E8[0], 2426889, (unsigned int)CapableCC);
        }
        goto LABEL_116;
      }
      v8 = CapableCC;
      if ( *((_QWORD *)this + 176) )
      {
        _mm_lfence();
        if ( !(unsigned int)CCommand::FParamInfoComplete(this) )
        {
          _mm_lfence();
          v25 = CCommand::DeriveParamInfo(this, a3);
          if ( (v25 & 0x80000000) != 0 )
          {
LABEL_116:
            v42 = v44;
            if ( v44 )
            {
              CExtBaseBuffer::~CExtBaseBuffer(v44);
              operator delete(v42, 0x30u);
            }
            return v25;
          }
        }
      }
      _mm_lfence();
      if ( !*(_WORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 180) + 48LL) + 40LL) + 320LL)
        || v16
        && ((_mm_lfence(), *(_QWORD *)(*((_QWORD *)this + 150) + 632LL) > 1u)
         || (_mm_lfence(), *(_BYTE *)(*((_QWORD *)this + 150) + 214LL))) )
      {
        _mm_lfence();
        *(_DWORD *)(*((_QWORD *)this + 150) + 192LL) &= ~0x8000000u;
        v41 = CCommand::DoPrepare(this, a3, v14, v15, *((unsigned __int64 **)this + 175));
        v25 = v41;
        if ( v41 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            _mm_lfence();
            bidTraceHR(off_1802603E8[0], 2453513, (unsigned int)v41);
          }
          goto LABEL_116;
        }
      }
      else
      {
        _mm_lfence();
        *(_DWORD *)(*((_QWORD *)this + 150) + 192LL) |= 0x8000000u;
      }
    }
    *((_DWORD *)this + 302) |= a2;
    return v8;
  }
  *(_WORD *)(*((_QWORD *)this + 150) + 552LL) &= 0xF7DFu;
  v12 = (__int64)*a4;
  if ( *a4 )
  {
    if ( *((_QWORD *)this + 163) != v12 )
    {
      *((_QWORD *)this + 163) = v12;
      *a4 = 0;
    }
    *((_DWORD *)this + 302) |= 2u;
    v13 = *((_QWORD *)this + 163);
    v14 = *(wchar_t **)(v13 + 32);
    v15 = *(_QWORD *)(v13 + 8) >> 1;
    goto LABEL_12;
  }
  if ( CCommand::CreateExtBuffer(
         this,
         &v44,
         2LL * *((_QWORD *)this + 162) + 48,
         0x64u,
         *((const void **)this + 161),
         2LL * *((_QWORD *)this + 162)) >= 0 )
  {
    _mm_lfence();
    if ( a2 == 32 || !*(_QWORD *)(*((_QWORD *)this + 150) + 592LL) && !(unsigned int)CCommand::FParamInfoComplete(this) )
      *((_DWORD *)this + 302) |= 0x80u;
    v21 = CCommand::DoSubstitutions(this, v44, *((struct CStmt **)this + 150));
    v22 = *((_DWORD *)this + 302) & 0xFFFFFF7F;
    *((_DWORD *)this + 302) = v22;
    if ( v21 == -1 )
    {
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ICommand.Data1
        && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_ICommand.Data4 )
      {
        _mm_lfence();
        v23 = CCommand::PostExecuteErrors(this, (CCommand *)((char *)this + 1136), a3);
      }
      else
      {
        if ( *(_QWORD *)&a3->Data1 != *(_QWORD *)&IID_ICommandPrepare.Data1
          || *(_QWORD *)a3->Data4 != *(_QWORD *)IID_ICommandPrepare.Data4 )
        {
          _mm_lfence();
          v24 = bidGblFlags;
          if ( (bidGblFlags & 2) != 0 )
          {
            v25 = bidTraceHR(off_1802603E8[0], 2272265, 2147500037LL);
            v24 = bidGblFlags;
          }
          else
          {
            v25 = -2147467259;
          }
          if ( (v24 & 2) != 0 )
          {
            v26 = bidTraceHR(off_1802603E8[0], 2273289, v25);
LABEL_37:
            CError::PostSqlErrors(g_pCError, v26, a3, (CCommand *)((char *)this + 1136));
            goto LABEL_116;
          }
LABEL_36:
          v26 = v25;
          goto LABEL_37;
        }
        _mm_lfence();
        v23 = CCommand::PostPrepareErrors(this, (CCommand *)((char *)this + 1136));
      }
LABEL_115:
      v25 = v23;
      goto LABEL_116;
    }
    v27 = v44;
    *((_QWORD *)this + 163) = v44;
    v44 = 0;
    v14 = (wchar_t *)*((_QWORD *)v27 + 4);
    v15 = *((_QWORD *)v27 + 1) >> 1;
    if ( *((_QWORD *)this + 176) )
    {
      _mm_lfence();
      *((_DWORD *)this + 302) = v22 | 0x10;
      v28 = CCommand::ComputeParamOffsets(this, v14, v15, *((_QWORD *)this + 176), (unsigned __int64 **)this + 175);
      v25 = v28;
      if ( v28 < 0 )
      {
        _mm_lfence();
        if ( (bidGblFlags & 2) == 0 )
        {
LABEL_43:
          CError::PostHResult(g_pCError, v28, a3);
          goto LABEL_116;
        }
        v29 = 2295817;
LABEL_42:
        v28 = bidTraceHR(off_1802603E8[0], v29, (unsigned int)v28);
        goto LABEL_43;
      }
    }
LABEL_12:
    v16 = (*(unsigned __int16 *)(*((_QWORD *)this + 150) + 552LL) >> 6) & 1;
    LexToken = GetLexToken(v14, v15, &v43, &v45);
    v18 = *((_DWORD *)this + 302);
    if ( LexToken != 1 )
    {
      v19 = 0;
      if ( (v18 & 0x100) == 0 )
        *((_DWORD *)this + 302) = v18 | 0x200;
      goto LABEL_57;
    }
    if ( (v18 & 0x40000) != 0 )
      goto LABEL_56;
    v30 = v45;
    if ( v45 == 6 )
    {
      if ( !_wcsnicmp(L"select", &v14[v43], 6u) )
      {
        if ( !(unsigned int)FIsSelectInto(v14, v15) )
        {
          v19 = 1;
          goto LABEL_57;
        }
        goto LABEL_55;
      }
      v30 = v45;
    }
    if ( v30 == 4 )
    {
      if ( !_wcsnicmp(L"exec", &v14[v43], 4u) )
      {
LABEL_56:
        v19 = 0;
LABEL_57:
        if ( (*((_DWORD *)this + 302) & 0x200) == 0 )
        {
          v31 = IndexWChar(0x3Bu, v14, v15);
          v43 = v31;
          if ( v31 + 1 < v15 )
          {
            v32 = &v14[v31 + 1];
            v33 = v15 - v31 - 1;
            if ( v15 - v31 != 1 )
            {
              do
              {
                if ( *v32 != 32 && (unsigned __int16)(*v32 - 9) > 4u )
                  break;
                ++v32;
                --v33;
              }
              while ( v33 );
            }
            if ( v33 )
              *((_DWORD *)this + 302) |= 0x200u;
          }
        }
        if ( v19 )
        {
          v34 = *((_DWORD *)this + 302);
          if ( (v34 & 0x200) == 0 )
            *((_DWORD *)this + 302) = v34 | 0x20000;
        }
        *((_DWORD *)this + 302) |= 8u;
        goto LABEL_73;
      }
      v30 = v45;
    }
    if ( v30 == 7 && !_wcsnicmp(L"execute", &v14[v43], 7u) )
      goto LABEL_56;
LABEL_55:
    *((_DWORD *)this + 302) |= 0x200u;
    goto LABEL_56;
  }
  if ( (bidGblFlags & 2) != 0 )
    v20 = bidTraceHR(off_1802603E8[0], 2254857, 2147942414LL);
  else
    v20 = -2147024882;
  return CError::PostHResult(g_pCError, v20, a3);
}

```

## disassembly

```asm
0x180086810  mov     [rsp+arg_8], rbx
0x180086815  push    rbp
0x180086816  push    rsi
0x180086817  push    rdi
0x180086818  push    r12
0x18008681a  push    r13
0x18008681c  push    r14
0x18008681e  push    r15
0x180086820  sub     rsp, 60h
0x180086824  mov     rax, cs:__security_cookie
0x18008682b  xor     rax, rsp
0x18008682e  mov     [rsp+98h+var_48], rax
0x180086833  mov     r15, r9
0x180086836  mov     rsi, r8
0x180086839  mov     r12d, edx
0x18008683c  mov     rbx, rcx
0x18008683f  xor     r14d, r14d
0x180086842  mov     [rsp+98h+var_58], r14
0x180086847  mov     [rsp+98h+var_50], r14
0x18008684c  mov     [rsp+98h+var_60], r14
0x180086851  cmp     [r9], r14
0x180086854  jz      short loc_18008688A
0x180086856  and     dword ptr [rcx+4B8h], 0FFFFFFB7h
0x18008685d  mov     rdi, [rcx+518h]
0x180086864  cmp     rdi, [r9]
0x180086867  jz      short loc_18008688A
0x180086869  test    rdi, rdi
0x18008686c  jz      short loc_18008688A
0x18008686e  mov     rcx, rdi; this
0x180086871  call    ??1CExtBaseBuffer@@IEAA@XZ; CExtBaseBuffer::~CExtBaseBuffer(void)
0x180086876  mov     edx, 30h ; '0'; unsigned __int64
0x18008687b  mov     rcx, rdi; void *
0x18008687e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180086883  mov     [rbx+518h], r14
0x18008688a  mov     ecx, [rbx+4B8h]
0x180086890  mov     eax, ecx
0x180086892  and     eax, r12d
0x180086895  cmp     eax, 40h ; '@'
0x180086898  jnz     short loc_1800868A1
0x18008689a  xor     eax, eax
0x18008689c  jmp     loc_18008703F
0x1800868a1  test    cl, 8
0x1800868a4  jnz     loc_180086CBF
0x1800868aa  mov     rax, [rbx+4B0h]
0x1800868b1  mov     ecx, 0F7DFh
0x1800868b6  and     [rax+228h], cx
0x1800868bd  mov     rax, [r15]
0x1800868c0  test    rax, rax
0x1800868c3  jz      loc_18008694C
0x1800868c9  cmp     [rbx+518h], rax
0x1800868d0  jz      short loc_1800868DC
0x1800868d2  mov     [rbx+518h], rax
0x1800868d9  mov     [r15], r14
0x1800868dc  or      dword ptr [rbx+4B8h], 2
0x1800868e3  mov     rax, [rbx+518h]
0x1800868ea  mov     r15, [rax+20h]
0x1800868ee  mov     rbp, [rax+8]
0x1800868f2  shr     rbp, 1
0x1800868f5  mov     rax, [rbx+4B0h]
0x1800868fc  movzx   r13d, word ptr [rax+228h]
0x180086904  shr     r13d, 6
0x180086908  and     r13d, 1
0x18008690c  lea     r9, [rsp+98h+var_50]; unsigned __int64 *
0x180086911  lea     r8, [rsp+98h+var_60]; unsigned __int64 *
0x180086916  mov     rdx, rbp; unsigned __int64
0x180086919  mov     rcx, r15; wchar_t *
0x18008691c  call    ?GetLexToken@@YAKPEB_W_KPEA_K2@Z; GetLexToken(wchar_t const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x180086921  mov     ecx, [rbx+4B8h]
0x180086927  cmp     eax, 1
0x18008692a  jz      loc_180086B80
0x180086930  mov     edi, r14d
0x180086933  bt      ecx, 8
0x180086937  jb      loc_180086C2E
0x18008693d  bts     ecx, 9
0x180086941  mov     [rbx+4B8h], ecx
0x180086947  jmp     loc_180086C2E
0x18008694c  mov     rax, [rbx+510h]
0x180086953  add     rax, rax
0x180086956  lea     r8, [rax+30h]; unsigned __int64
0x18008695a  mov     [rsp+98h+var_70], rax; unsigned __int64
0x18008695f  mov     rax, [rbx+508h]
0x180086966  mov     [rsp+98h+var_78], rax; void *
0x18008696b  mov     r9d, 64h ; 'd'; unsigned __int64
0x180086971  lea     rdx, [rsp+98h+var_58]; struct CExtByteBuffer **
0x180086976  mov     rcx, rbx; this
0x180086979  call    ?CreateExtBuffer@CCommand@@QEAAJPEAPEAVCExtByteBuffer@@_K1PEBX1@Z; CCommand::CreateExtBuffer(CExtByteBuffer * *,unsigned __int64,unsigned __int64,void const *,unsigned __int64)
0x18008697e  test    eax, eax
0x180086980  jns     short loc_1800869BF
0x180086982  test    byte ptr cs:_bidGblFlags, 2
0x180086989  jz      short loc_1800869A4
0x18008698b  mov     edx, 226809h
0x180086990  mov     r8d, 8007000Eh
0x180086996  mov     rcx, cs:off_1802603E8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18008699d  call    _bidTraceHR
0x1800869a2  jmp     short loc_1800869A9
0x1800869a4  mov     eax, 8007000Eh
0x1800869a9  mov     r8, rsi; struct _GUID *
0x1800869ac  mov     edx, eax; int
0x1800869ae  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x1800869b5  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x1800869ba  jmp     loc_18008703F
0x1800869bf  lfence
0x1800869c2  cmp     r12d, 20h ; ' '
0x1800869c6  jz      short loc_1800869E4
0x1800869c8  mov     rax, [rbx+4B0h]
0x1800869cf  cmp     [rax+250h], r14
0x1800869d6  jnz     short loc_1800869EE
0x1800869d8  mov     rcx, rbx; this
0x1800869db  call    ?FParamInfoComplete@CCommand@@QEAAHXZ; CCommand::FParamInfoComplete(void)
0x1800869e0  test    eax, eax
0x1800869e2  jnz     short loc_1800869EE
0x1800869e4  or      dword ptr [rbx+4B8h], 80h
0x1800869ee  mov     r8, [rbx+4B0h]; struct CStmt *
0x1800869f5  mov     rdx, [rsp+98h+var_58]; struct CExtByteBuffer *
0x1800869fa  mov     rcx, rbx; this
0x1800869fd  call    ?DoSubstitutions@CCommand@@QEAAHPEAVCExtByteBuffer@@PEAVCStmt@@@Z; CCommand::DoSubstitutions(CExtByteBuffer *,CStmt *)
0x180086a02  mov     ecx, [rbx+4B8h]
0x180086a08  btr     ecx, 7
0x180086a0c  mov     [rbx+4B8h], ecx
0x180086a12  cmp     eax, 0FFFFFFFFh
0x180086a15  jnz     loc_180086AEA
0x180086a1b  mov     rax, [rsi]
0x180086a1e  cmp     rax, qword ptr cs:IID_ICommand.Data1
0x180086a25  jnz     short loc_180086A4E
0x180086a27  mov     rax, [rsi+8]
0x180086a2b  cmp     rax, qword ptr cs:IID_ICommand.Data4
0x180086a32  jnz     short loc_180086A4E
0x180086a34  lfence
0x180086a37  lea     rdx, [rbx+470h]; struct CErrorData *
0x180086a3e  mov     r8, rsi; struct _GUID *
0x180086a41  mov     rcx, rbx; this
0x180086a44  call    ?PostExecuteErrors@CCommand@@QEAAJPEAVCErrorData@@PEBU_GUID@@@Z; CCommand::PostExecuteErrors(CErrorData *,_GUID const *)
0x180086a49  jmp     loc_18008701C
0x180086a4e  mov     rax, [rsi]
0x180086a51  cmp     rax, qword ptr cs:IID_ICommandPrepare.Data1
0x180086a58  jnz     short loc_180086A7E
0x180086a5a  mov     rax, [rsi+8]
0x180086a5e  cmp     rax, qword ptr cs:IID_ICommandPrepare.Data4
0x180086a65  jnz     short loc_180086A7E
0x180086a67  lfence
0x180086a6a  lea     rdx, [rbx+470h]; struct CErrorData *
0x180086a71  mov     rcx, rbx; this
0x180086a74  call    ?PostPrepareErrors@CCommand@@QEAAJPEAVCErrorData@@@Z; CCommand::PostPrepareErrors(CErrorData *)
0x180086a79  jmp     loc_18008701C
0x180086a7e  lfence
0x180086a81  mov     eax, cs:_bidGblFlags
0x180086a87  test    al, 2
0x180086a89  jz      short loc_180086AAC
0x180086a8b  mov     edx, 22AC09h
0x180086a90  mov     r8d, 80004005h
0x180086a96  mov     rcx, cs:off_1802603E8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180086a9d  call    _bidTraceHR
0x180086aa2  mov     edi, eax
0x180086aa4  mov     eax, cs:_bidGblFlags
0x180086aaa  jmp     short loc_180086AB1
0x180086aac  mov     edi, 80004005h
0x180086ab1  test    al, 2
0x180086ab3  jz      short loc_180086ACB
0x180086ab5  mov     r8d, edi
0x180086ab8  mov     edx, 22B009h
0x180086abd  mov     rcx, cs:off_1802603E8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180086ac4  call    _bidTraceHR
0x180086ac9  jmp     short loc_180086ACD
0x180086acb  mov     eax, edi
0x180086acd  lea     r9, [rbx+470h]; struct CErrorData *
0x180086ad4  mov     r8, rsi; struct _GUID *
0x180086ad7  mov     edx, eax; int
0x180086ad9  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x180086ae0  call    ?PostSqlErrors@CError@@QEAAJJPEBU_GUID@@PEAVCErrorData@@@Z; CError::PostSqlErrors(long,_GUID const *,CErrorData *)
0x180086ae5  jmp     loc_18008701E
0x180086aea  mov     rax, [rsp+98h+var_58]
0x180086aef  mov     [rbx+518h], rax
0x180086af6  mov     [rsp+98h+var_58], r14
0x180086afb  mov     r15, [rax+20h]
0x180086aff  mov     rbp, [rax+8]
0x180086b03  shr     rbp, 1
0x180086b06  cmp     [rbx+580h], r14
0x180086b0d  jz      loc_1800868F5
0x180086b13  lfence
0x180086b16  or      ecx, 10h
0x180086b19  mov     [rbx+4B8h], ecx
0x180086b1f  lea     rax, [rbx+578h]
0x180086b26  mov     [rsp+98h+var_78], rax; unsigned __int64 **
0x180086b2b  mov     r9, [rbx+580h]; unsigned __int64
0x180086b32  mov     r8, rbp; unsigned __int64
0x180086b35  mov     rdx, r15; wchar_t *
0x180086b38  mov     rcx, rbx; this
0x180086b3b  call    ?ComputeParamOffsets@CCommand@@QEAAJPEB_W_K1PEAPEA_K@Z; CCommand::ComputeParamOffsets(wchar_t const *,unsigned __int64,unsigned __int64,unsigned __int64 * *)
0x180086b40  mov     edi, eax
0x180086b42  test    eax, eax
0x180086b44  jns     loc_1800868F5
0x180086b4a  lfence
0x180086b4d  test    byte ptr cs:_bidGblFlags, 2
0x180086b54  jz      short loc_180086B6A
0x180086b56  mov     edx, 230809h
0x180086b5b  mov     r8d, eax
0x180086b5e  mov     rcx, cs:off_1802603E8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180086b65  call    _bidTraceHR
0x180086b6a  mov     r8, rsi; struct _GUID *
0x180086b6d  mov     edx, eax; int
0x180086b6f  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x180086b76  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x180086b7b  jmp     loc_18008701E
0x180086b80  bt      ecx, 12h
0x180086b84  jb      loc_180086C2B
0x180086b8a  mov     rax, [rsp+98h+var_50]
0x180086b8f  cmp     rax, 6
0x180086b93  jnz     short loc_180086BD0
0x180086b95  mov     rax, [rsp+98h+var_60]
0x180086b9a  lea     rdx, [r15+rax*2]; String2
0x180086b9e  mov     r8d, 6; MaxCount
0x180086ba4  lea     rcx, aSelect_0; "select"
0x180086bab  call    cs:__imp__wcsnicmp
0x180086bb1  test    eax, eax
0x180086bb3  jnz     short loc_180086BCB
0x180086bb5  mov     rdx, rbp; unsigned __int64
0x180086bb8  mov     rcx, r15; wchar_t *
0x180086bbb  call    ?FIsSelectInto@@YAHPEB_W_K@Z; FIsSelectInto(wchar_t const *,unsigned __int64)
0x180086bc0  test    eax, eax
0x180086bc2  jnz     short loc_180086C21
0x180086bc4  mov     edi, 1
0x180086bc9  jmp     short loc_180086C2E
0x180086bcb  mov     rax, [rsp+98h+var_50]
0x180086bd0  cmp     rax, 4
0x180086bd4  jnz     short loc_180086BFB
0x180086bd6  mov     rax, [rsp+98h+var_60]
0x180086bdb  lea     rdx, [r15+rax*2]; String2
0x180086bdf  mov     r8d, 4; MaxCount
0x180086be5  lea     rcx, aExec; "exec"
0x180086bec  call    cs:__imp__wcsnicmp
0x180086bf2  test    eax, eax
0x180086bf4  jz      short loc_180086C2B
0x180086bf6  mov     rax, [rsp+98h+var_50]
0x180086bfb  cmp     rax, 7
0x180086bff  jnz     short loc_180086C21
0x180086c01  mov     rax, [rsp+98h+var_60]
0x180086c06  lea     rdx, [r15+rax*2]; String2
0x180086c0a  mov     r8d, 7; MaxCount
0x180086c10  lea     rcx, aExecute; "execute"
0x180086c17  call    cs:__imp__wcsnicmp
0x180086c1d  test    eax, eax
0x180086c1f  jz      short loc_180086C2B
0x180086c21  or      dword ptr [rbx+4B8h], 200h
0x180086c2b  mov     edi, r14d
0x180086c2e  test    dword ptr [rbx+4B8h], 200h
0x180086c38  jnz     short loc_180086C9C
0x180086c3a  mov     ecx, 3Bh ; ';'; wchar_t
0x180086c3f  mov     r8, rbp; unsigned __int64
0x180086c42  mov     rdx, r15; wchar_t *
0x180086c45  call    ?IndexWChar@@YA_K_WPEB_W_K@Z; IndexWChar(wchar_t,wchar_t const *,unsigned __int64)
0x180086c4a  mov     [rsp+98h+var_60], rax
0x180086c4f  lea     rcx, [rax+1]
0x180086c53  cmp     rcx, rbp
0x180086c56  jnb     short loc_180086C9C
0x180086c58  lea     rdx, [rax+1]
0x180086c5c  lea     rdx, [r15+rdx*2]
0x180086c60  mov     rcx, rbp
0x180086c63  sub     rcx, rax
0x180086c66  sub     rcx, 1
0x180086c6a  jz      short loc_180086C8D
0x180086c6c  nop     dword ptr [rax+00h]
0x180086c70  movzx   eax, word ptr [rdx]
0x180086c73  cmp     ax, 20h ; ' '
0x180086c77  jz      short loc_180086C83
0x180086c79  sub     ax, 9
0x180086c7d  cmp     ax, 4
0x180086c81  ja      short loc_180086C8D
0x180086c83  add     rdx, 2
0x180086c87  sub     rcx, 1
0x180086c8b  jnz     short loc_180086C70
0x180086c8d  test    rcx, rcx
0x180086c90  jz      short loc_180086C9C
0x180086c92  or      dword ptr [rbx+4B8h], 200h
0x180086c9c  test    edi, edi
0x180086c9e  jz      short loc_180086CB6
0x180086ca0  mov     eax, [rbx+4B8h]
0x180086ca6  bt      eax, 9
0x180086caa  jb      short loc_180086CB6
0x180086cac  bts     eax, 11h
0x180086cb0  mov     [rbx+4B8h], eax
0x180086cb6  or      dword ptr [rbx+4B8h], 8
0x180086cbd  jmp     short loc_180086D0E
0x180086cbf  cmp     [rbx+518h], r14
0x180086cc6  jz      loc_180086FE4
0x180086ccc  cmp     eax, 20h ; ' '
0x180086ccf  jnz     short loc_180086CE5
0x180086cd1  mov     edx, 1; unsigned __int16
0x180086cd6  xor     r8d, r8d; unsigned int
0x180086cd9  mov     rcx, [rbx+4B0h]; this
0x180086ce0  call    ?SQLFreeStmt@CStmt@@QEAAHGK@Z; CStmt::SQLFreeStmt(ushort,ulong)
0x180086ce5  mov     rax, [rbx+518h]
0x180086cec  mov     r15, [rax+20h]
0x180086cf0  mov     rbp, [rax+8]
0x180086cf4  shr     rbp, 1
0x180086cf7  mov     rax, [rbx+4B0h]
0x180086cfe  movzx   r13d, word ptr [rax+228h]
0x180086d06  shr     r13d, 6
0x180086d0a  and     r13d, 1
0x180086d0e  cmp     r12d, 20h ; ' '
0x180086d12  jnz     loc_180086F7C
  ... truncated ...
```
