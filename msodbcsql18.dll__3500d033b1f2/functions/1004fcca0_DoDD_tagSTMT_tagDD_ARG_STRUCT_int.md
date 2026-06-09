# DoDD(tagSTMT *,tagDD_ARG_STRUCT *,int)

- ea: `0x1004fcca0`
- end: `0x1004fdb5d`
- name: `?DoDD@@YAFPEAUtagSTMT@@PEAUtagDD_ARG_STRUCT@@H@Z`
- size: `3773`
- prototype: `__int16 __fastcall(struct tagSTMT *, struct tagDD_ARG_STRUCT *, int)`
- caller_count: `11`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x1004fcca0`
- `0x1004fe280`
- `0x1004fe590`
- `0x1004fe880`
- `0x1004ff6e0`
- `0x1004ff960`
- `0x1004ffc80`
- `0x1004fff40`
- `0x1005002c0`
- `0x1005005e0`
- `0x100500890`

## callees

- `0x100405718`
- `0x10045839c`
- `0x100459968`
- `0x10045be64`
- `0x100493378`
- `0x10049ecd4`
- `0x1004c8dc0`
- `0x1004f3e20`
- `0x1004fca6c`
- `0x1004fcac4`
- `0x1004fcca0`
- `0x1004fdb64`
- `0x1004fde20`
- `0x10051fc98`
- `0x10051ff30`
- `0x100520370`
- `0x1005212b4`
- `0x100522824`
- `0x100522dcc`
- `0x100529630`
- `0x100534c7c`
- `0x100538aa8`
- `0x100538c74`
- `0x100546a7c`
- `0x100548140`
- `0x100548210`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004fce27`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004fce27`

## string_xrefs

- `0x1004fd268`: `sp_ddopen`
- `0x1004fd261`: `sp_cursoropen`
- `0x1004fd2b8`: `[dbo].sp_cursoropen`
- `0x1004fd2bf`: `[dbo].sp_ddopen`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DoDD(struct tagSTMT *a1, struct tagDD_ARG_STRUCT *a2, int a3)
{
  struct tagDBC *v5; // r13
  int v6; // r15d
  int v7; // r14d
  unsigned __int16 BatchCtxOrRecover; // bx
  struct BATCHCTX *v9; // r12
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned __int16 v14; // dx
  const unsigned __int16 *v15; // r15
  __int64 v16; // rax
  const wchar_t *v17; // rax
  int v18; // eax
  CRPCRequest **v19; // r14
  const wchar_t *v20; // rcx
  const unsigned __int16 *v21; // rax
  int v22; // eax
  const unsigned __int16 *v23; // r8
  __int64 v24; // rax
  unsigned __int16 v25; // r15
  unsigned __int16 v26; // r12
  CRPCRequest **v27; // rbx
  unsigned __int16 *v28; // rcx
  unsigned __int16 v29; // dx
  unsigned __int8 v30; // r13
  int v31; // eax
  __int64 v32; // rax
  BOOL v33; // edx
  int v34; // eax
  __int64 v35; // rdx
  char v36; // cl
  char v37; // al
  CRPCRequest *v38; // rcx
  int v40; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 v41; // [rsp+6Ch] [rbp-9Ch] BYREF
  int v42; // [rsp+70h] [rbp-98h] BYREF
  char v43; // [rsp+74h] [rbp-94h] BYREF
  bool v44; // [rsp+75h] [rbp-93h] BYREF
  unsigned __int16 v45[2]; // [rsp+78h] [rbp-90h] BYREF
  int v46; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v47; // [rsp+80h] [rbp-88h]
  unsigned __int64 v48; // [rsp+88h] [rbp-80h] BYREF
  int v49; // [rsp+90h] [rbp-78h] BYREF
  int v50; // [rsp+94h] [rbp-74h]
  __int64 v51; // [rsp+98h] [rbp-70h]
  unsigned int v52[2]; // [rsp+A0h] [rbp-68h] BYREF
  struct tagDBC *v53; // [rsp+A8h] [rbp-60h]
  __int128 v54; // [rsp+B0h] [rbp-58h] BYREF
  _OWORD Destination[3]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v56; // [rsp+F0h] [rbp-18h]
  __int64 v57; // [rsp+F8h] [rbp-10h]
  unsigned __int16 v58[168]; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int16 v59; // [rsp+258h] [rbp+150h] BYREF
  char v60; // [rsp+25Ah] [rbp+152h] BYREF
  unsigned __int16 v61[392]; // [rsp+468h] [rbp+360h] BYREF
  unsigned __int16 v62[392]; // [rsp+778h] [rbp+670h] BYREF

  v57 = -2;
  v42 = a3;
  v41 = 0;
  v5 = (struct tagDBC *)*((_QWORD *)a1 + 14);
  v53 = v5;
  v48 = 0;
  memset(Destination, 0, sizeof(Destination));
  v56 = 0;
  v6 = *((_DWORD *)a1 + 480);
  v50 = v6;
  v47 = 0;
  LOBYTE(v40) = *((_BYTE *)a1 + 2024);
  v7 = 0;
  memset_0(v58, 0, 0x142u);
  memset_0(&v59, 0, 0x206u);
  *(_QWORD *)v52 = 0;
  v54 = 0;
  if ( (*((_BYTE *)a1 + 24) & 0x10) != 0 )
    FreeErrors(a1);
  if ( (*((_BYTE *)a1 + 1516) & 0x30) == 0x30 )
  {
    BatchCtxOrRecover = AsyncPostExec(a1, *((_BYTE *)a2 + 136));
    goto LABEL_164;
  }
  BatchCtxOrRecover = GetBatchCtxOrRecover(
                        a1,
                        (struct CAutoBatchCtx_ODBC *)&v54,
                        *((_BYTE *)a2 + 136),
                        *((_DWORD *)a1 + 377),
                        0,
                        0);
  v9 = (struct BATCHCTX *)*((_QWORD *)a1 + 141);
  if ( BatchCtxOrRecover != 2 )
  {
    if ( (BatchCtxOrRecover & 0xFFFE) != 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 1474569);
      goto LABEL_164;
    }
    v10 = *((_QWORD *)a1 + 14);
    if ( *(_QWORD *)(v10 + 464) )
    {
      memcpy_s((char *)Destination + 8, 5u, (const void *const)(v10 + 1388), 5u);
    }
    else
    {
      DWORD2(Destination[0]) = 0;
      BYTE12(Destination[0]) = 0;
    }
    if ( (*((_DWORD *)a1 + 379) & 0x900) != 0 || *((_DWORD *)a1 + 520) == 1 )
    {
      v41 = -25406;
      BatchCtxOrRecover = -1;
      if ( (bidGblFlags & 2) != 0 )
      {
        bidTraceMark(0, 1484809);
        goto LABEL_163;
      }
      goto LABEL_42;
    }
    if ( (unsigned int)CheckBusy(a1, &v41) )
    {
      BatchCtxOrRecover = -1;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_163;
      v11 = 1489929;
      goto LABEL_17;
    }
    if ( *((__int16 *)a1 + 408) > 0 || *((_DWORD *)a1 + 378) != -1 )
      DropPrepHandle(a1, 1);
    v51 = 0;
    if ( (*((_BYTE *)a2 + 130) & 9) == 1 )
    {
      v12 = *((_QWORD *)a2 + 5);
      if ( v12 != 1 || **((_WORD **)a2 + 12) != 37 || *((_QWORD *)a2 + 3) || (v51 = 0, *((_QWORD *)a2 + 4)) )
      {
        v49 = 0;
        if ( (*((_BYTE *)v5 + 2488) & 4) != 0 || *((_BYTE *)a2 + 136) != 27 )
          goto LABEL_32;
        BatchCtxOrRecover = ConvertArgument(
                              *((const unsigned __int16 **)a2 + 12),
                              v12,
                              1,
                              a2,
                              v5,
                              v62,
                              0x181u,
                              v6,
                              &v49);
        if ( BatchCtxOrRecover == 0xFFFF )
          goto LABEL_163;
        if ( v49 )
        {
          *((_BYTE *)a2 + 136) = 37;
          v51 = 0;
        }
        else
        {
LABEL_32:
          v13 = *((_QWORD *)a2 + 5);
          v51 = 0;
          if ( v13 )
          {
            v7 = 1;
            ValidateSearchPattern(*((const unsigned __int16 **)a2 + 12), v13, &v59, 0x103u, (unsigned __int64 *)v52);
            v51 = 1;
          }
        }
      }
    }
    if ( (_BYTE)v40 == 1 )
    {
      if ( ((*((_BYTE *)a2 + 136) - 27) & 0xFA) != 0 || *((_BYTE *)a2 + 136) == 32 )
      {
        v41 = -25374;
        BatchCtxOrRecover = -1;
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 1551369);
LABEL_40:
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 1950729);
LABEL_42:
        PostSQLErrorEx(a1, v41, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
        goto LABEL_164;
      }
      v14 = 2;
    }
    else
    {
      v14 = (*((_WORD *)a2 + 65) & 1) == 0;
    }
    if ( *((_QWORD *)v5 + 8) && *(_BYTE *)(*((_QWORD *)v5 + 8) + 3878LL) >= 9u )
      v47 = *((_DWORD *)&off_1005D12A0 + *((unsigned __int8 *)a2 + 136) + 1);
    if ( *(_DWORD *)(*((_QWORD *)v9 + 9) + 448LL) )
    {
      v15 = (const unsigned __int16 *)*(&g_pwchKauaiProcNamesArr + 3 * *((unsigned __int8 *)a2 + 136) + v14 - 81);
    }
    else if ( !*((_QWORD *)v5 + 8)
           || (v16 = *((_QWORD *)v5 + 8), *(_BYTE *)(v16 + 3878) < 0xAu)
           || (*(_BYTE *)(v16 + 416) & 2) != 0 )
    {
      if ( *((_QWORD *)v5 + 8) && *(_BYTE *)(*((_QWORD *)v5 + 8) + 3878LL) >= 9u )
        v15 = (&off_1005D1250[2 * *((unsigned __int8 *)a2 + 136)])[v14];
      else
        v15 = (const unsigned __int16 *)qword_1005D1190[2 * *((unsigned __int8 *)a2 + 136) + v14];
    }
    else
    {
      v15 = (const unsigned __int16 *)*(&g_pwchKatmaiProcNamesArr + 3 * *((unsigned __int8 *)a2 + 136) + v14 - 81);
    }
    if ( !(unsigned int)IsCursorOn(a1) )
    {
      if ( v7 )
      {
        if ( !*((_QWORD *)v5 + 8) || (v17 = &szDefault, *(_BYTE *)(*((_QWORD *)v5 + 8) + 3878LL) < 9u) )
          v17 = L".";
        v18 = StringCchPrintfExW(v58, 0xA1u, 0, &v48, 0, L"%s.%s%s", &v59, v17, v15);
      }
      else
      {
        v18 = StringCchCopyExW(v58, 0xA1u, v15, 0, &v48, 0);
      }
      if ( v18 < 0 )
      {
        BatchCtxOrRecover = -1;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_163;
        v11 = 1626121;
        goto LABEL_17;
      }
      if ( (int)AddRpcCmdFromStmt(v9, a1, v58, 161 - (int)v48, 0, 0) < 0 )
      {
        BatchCtxOrRecover = -1;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_163;
        v11 = 1635337;
        goto LABEL_17;
      }
      v19 = (CRPCRequest **)((char *)a1 + 1120);
LABEL_106:
      v25 = *((_WORD *)a2 + 65) & 1;
      v26 = v25 + 1;
      v27 = v19;
      if ( v25 < *((_WORD *)a2 + 64) )
      {
        while ( 1 )
        {
          memset_0(v61, 0, 0x302u);
          v28 = 0;
          v29 = 0;
          v46 = 0;
          v30 = (v26 & *((_WORD *)a2 + 66)) != 0 ? -17 : -25;
          if ( (v26 & *((_WORD *)a2 + 65)) == 0 )
            break;
          v29 = 256;
          v31 = 0;
LABEL_124:
          v27 = (CRPCRequest **)((char *)a1 + 1120);
          v34 = CRPCRequest::AddParam(
                  *((CRPCRequest **)a1 + 140),
                  0,
                  v29,
                  v30,
                  v31,
                  v31,
                  v28,
                  (const struct RPCPARAMEXINFO *)Destination,
                  0,
                  0,
                  0);
          if ( v34 < 0 && v34 != -2147023436 && v34 != -2147023899 )
          {
            BatchCtxOrRecover = -1;
            if ( (bidGblFlags & 2) != 0 )
            {
              v35 = 1829897;
              goto LABEL_137;
            }
            goto LABEL_163;
          }
          ++v25;
          v26 *= 2;
          if ( v25 >= *((_WORD *)a2 + 64) )
          {
            v5 = v53;
            goto LABEL_129;
          }
        }
        if ( *((_BYTE *)a2 + 136) == 27 )
        {
          if ( v25 == 4 )
          {
            v28 = (unsigned __int16 *)*((_QWORD *)a2 + 13);
            LODWORD(v32) = *((_DWORD *)a2 + 12);
            goto LABEL_123;
          }
          if ( v51 && v25 == 3 )
          {
            v28 = (unsigned __int16 *)&v60;
            LODWORD(v32) = v52[0] - 2;
LABEL_123:
            v31 = 2 * v32;
            goto LABEL_124;
          }
        }
        v33 = v50 && !v47;
        BatchCtxOrRecover = ConvertArgument(
                              *((const unsigned __int16 **)a2 + v25 + 9),
                              *((_QWORD *)a2 + v25 + 2),
                              v26 & *((_WORD *)a2 + 67),
                              a2,
                              v53,
                              v61,
                              0x181u,
                              v33,
                              0);
        if ( BatchCtxOrRecover == 0xFFFF )
          goto LABEL_163;
        v28 = v61;
        v32 = -1;
        do
          ++v32;
        while ( v61[v32] );
        v29 = v46;
        goto LABEL_123;
      }
LABEL_129:
      if ( *((_BYTE *)a2 + 136) == 28 )
      {
        if ( (_BYTE)v40 == 2 || (v27 = v19, (_BYTE)v40 == 3) )
        {
          if ( (int)CRPCRequest::AddParam(*v27, L"@NameScope", 0, 0x30u, 1u, 1u, &v40, 0, 0, 0, 0) < 0 )
          {
            BatchCtxOrRecover = -1;
            if ( (bidGblFlags & 2) != 0 )
            {
              v35 = 1848329;
              goto LABEL_137;
            }
            goto LABEL_163;
          }
        }
      }
      if ( (*((_BYTE *)v5 + 2488) & 4) != 0
        || (*((_BYTE *)a2 + 130) & 1) == 0
        || (v36 = *((_BYTE *)a2 + 136), ((v36 - 28) & 0xF5) != 0)
        || v36 == 38
        || (v43 = 3, (int)CRPCRequest::AddParam(*v19, L"@ODBCVer", 0, 0x30u, 1u, 1u, &v43, 0, 0, 0, 0) >= 0) )
      {
        if ( v47 )
        {
          v44 = v50 == 0;
          if ( (int)CRPCRequest::AddParam(*v19, L"@fUsePattern", 0, 0x68u, 1u, 1u, &v44, 0, 0, 0, 0) < 0 )
          {
            BatchCtxOrRecover = -1;
            if ( (bidGblFlags & 2) != 0 )
              bidTraceMark(0, 1885193);
            goto LABEL_163;
          }
        }
        *((_DWORD *)a1 + 379) = *((_DWORD *)a1 + 379) & 0xFFFFFFF0 | 3;
        CleanUphStmt(a1, 1u);
        FreeErrors(a1);
        *((_WORD *)a1 + 406) &= ~0x200u;
        *((_DWORD *)a1 + 202) = 0;
        if ( (unsigned int)IsCursorOn(a1) )
        {
          *((_BYTE *)a1 + 2346) = 1;
          *((_DWORD *)a1 + 379) = *((_DWORD *)a1 + 379) & 0xFFF7FBFF | 0x400;
        }
        *((_WORD *)a1 + 406) |= 0x480u;
        BatchCtxOrRecover = SQLExecDirectW(a1, 0, 0);
        *((_WORD *)a1 + 406) &= ~0x400u;
        if ( BatchCtxOrRecover != 0xFFFF )
        {
          if ( BatchCtxOrRecover == 2 )
          {
            v37 = *((_BYTE *)a2 + 136);
            if ( v37 == 37 )
              v37 = 27;
            *((_BYTE *)a1 + 2347) = v37;
          }
          goto LABEL_163;
        }
        v45[0] = 0;
        v46 = 0;
        PeekError(a1, v45, &v46);
        if ( (*((_BYTE *)a2 + 130) & 8) == 0 )
        {
          if ( v45[0] != 0x9E18 )
          {
            FreeErrors(a1);
            *((_QWORD *)a2 + 10) = g_szSpace;
            *((_QWORD *)a2 + 3) = 1;
            *((_WORD *)a2 + 65) &= ~2u;
            *((_QWORD *)a2 + 12) = g_szNull;
            *((_QWORD *)a2 + 5) = 4;
            *((_WORD *)a2 + 65) |= 8u;
            BatchCtxOrRecover = DoDD(a1, a2, 0);
          }
          goto LABEL_163;
        }
        if ( v46 != 2812 )
          goto LABEL_163;
        FreeErrors(a1);
        v41 = -25390;
      }
      else
      {
        BatchCtxOrRecover = -1;
        if ( (bidGblFlags & 2) != 0 )
        {
          v35 = 1866761;
LABEL_137:
          bidTraceMark(0, v35);
        }
LABEL_163:
        if ( !v41 )
          goto LABEL_164;
      }
      goto LABEL_40;
    }
    if ( v7 )
    {
      if ( !*((_QWORD *)v5 + 8) || (v20 = L"sys", *(_BYTE *)(*((_QWORD *)v5 + 8) + 3878LL) < 9u) )
        v20 = L"dbo";
      v21 = L"sp_ddopen";
      if ( v42 )
        v21 = L"sp_cursoropen";
      v22 = StringCchPrintfExW(v58, 0xA1u, 0, &v48, 0, L"%s.[%s].%s", &v59, v20, v21);
    }
    else
    {
      v23 = L"[dbo].sp_ddopen";
      if ( v42 )
        v23 = L"[dbo].sp_cursoropen";
      v22 = StringCchCopyExW(v58, 0xA1u, v23, 0, &v48, 0);
    }
    if ( v22 >= 0 )
    {
      if ( (int)AddRpcCmdFromStmt(v9, a1, v58, 161 - (int)v48, 0, 0) >= 0 )
      {
        _mm_lfence();
        v42 = 0;
        v19 = (CRPCRequest **)((char *)a1 + 1120);
        BatchCtxOrRecover = -1;
        if ( (int)CRPCRequest::AddParam(*((CRPCRequest **)a1 + 140), 0, 1u, 0x38u, 4u, 4u, &v42, 0, 0, 0, 0) >= 0 )
        {
          _mm_lfence();
          v24 = -1;
          do
            ++v24;
          while ( v15[v24] );
          if ( (int)CRPCRequest::AddParam(
                      *v19,
                      0,
                      0,
                      0xE7u,
                      2 * (int)v24,
                      2 * (int)v24,
                      v15,
                      (const struct RPCPARAMEXINFO *)Destination,
                      0,
                      0,
                      0) >= 0 )
          {
            _mm_lfence();
            *((_DWORD *)a1 + 47) = 3;
            *((_DWORD *)a1 + 49) = 1;
            v42 = 8;
            if ( (int)CRPCRequest::AddParam(*v19, 0, 1u, 0x38u, 4u, 4u, &v42, 0, 0, 0, 0) >= 0 )
            {
              _mm_lfence();
              v42 = 1;
              if ( (int)CRPCRequest::AddParam(*v19, 0, 1u, 0x38u, 4u, 4u, &v42, 0, 0, 0, 0) >= 0 )
              {
                _mm_lfence();
                v42 = 0;
                if ( (int)CRPCRequest::AddParam(*v19, 0, 1u, 0x38u, 4u, 4u, &v42, 0, 0, 0, 0) >= 0 )
                {
                  if ( g_fPerfStatLogEnabled )
                    IncrementPerf(1u, 8u);
                  goto LABEL_106;
                }
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_163;
                v11 = 1747977;
              }
              else
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_163;
                v11 = 1734665;
              }
            }
            else
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_163;
              v11 = 1721353;
            }
          }
          else
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_163;
            v11 = 1704969;
          }
        }
        else
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_163;
          v11 = 1690633;
        }
      }
      else
      {
        BatchCtxOrRecover = -1;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_163;
        v11 = 1676297;
      }
    }
    else
    {
      BatchCtxOrRecover = -1;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_163;
      v11 = 1668105;
    }
LABEL_17:
    bidTraceMark(0, v11);
    goto LABEL_163;
  }
LABEL_164:
  if ( (BatchCtxOrRecover & 0xFFFE) != 0 )
  {
    if ( BatchCtxOrRecover == 0xFFFF )
    {
      v38 = (CRPCRequest *)*((_QWORD *)a1 + 140);
      if ( v38 )
        CRPCRequest::RemoveAllCommands(v38, a1);
    }
  }
  else
  {
    if ( *(_DWORD *)a2 )
      ClearNullable(a1, *(_DWORD *)a2);
    BatchCtxOrRecover = SetColNames(a1, *((_DWORD *)a2 + 1), *((_DWORD *)a2 + 2));
  }
  if ( (bidGblFlags & 2) != 0 )
    BatchCtxOrRecover = _bidx_SNACOdbc_ErrCode(0, 0x1E0C09u, BatchCtxOrRecover);
  CAutoBatchCtx_ODBC::Reset((CAutoBatchCtx_ODBC *)&v54);
  return BatchCtxOrRecover;
}

```

## disassembly

```asm
0x1004fcca0  mov     rax, rsp
0x1004fcca3  push    rbp
0x1004fcca4  push    rsi
0x1004fcca5  push    rdi
0x1004fcca6  push    r12
0x1004fcca8  push    r13
0x1004fccaa  push    r14
0x1004fccac  push    r15
0x1004fccae  lea     rbp, [rax-9C8h]
0x1004fccb5  sub     rsp, 0A90h
0x1004fccbc  mov     [rbp+9C0h+var_9D0], 0FFFFFFFFFFFFFFFEh
0x1004fccc4  mov     [rax+20h], rbx
0x1004fccc8  mov     rax, cs:__security_cookie
0x1004fcccf  xor     rax, rsp
0x1004fccd2  mov     [rbp+9C0h+var_40], rax
0x1004fccd9  mov     [rsp+0AC0h+var_A58], r8d
0x1004fccde  mov     rsi, rdx
0x1004fcce1  mov     rdi, rcx
0x1004fcce4  xor     r12d, r12d
0x1004fcce7  mov     [rsp+0AC0h+var_A5C], r12w
0x1004fcced  mov     r13, [rcx+70h]
0x1004fccf1  mov     [rbp+9C0h+var_A20], r13
0x1004fccf5  mov     [rbp+9C0h+var_A40], r12
0x1004fccf9  xorps   xmm0, xmm0
0x1004fccfc  xor     eax, eax
0x1004fccfe  movups  [rbp+9C0h+Destination], xmm0
0x1004fcd02  movups  [rbp+9C0h+var_9F8], xmm0
0x1004fcd06  movups  [rbp+9C0h+var_9E8], xmm0
0x1004fcd0a  mov     [rbp+9C0h+var_9D8], rax
0x1004fcd0e  mov     r15d, [rcx+780h]
0x1004fcd15  mov     [rbp+9C0h+var_A34], r15d
0x1004fcd19  mov     [rsp+0AC0h+var_A48], r12d
0x1004fcd1e  mov     al, [rcx+7E8h]
0x1004fcd24  mov     byte ptr [rsp+0AC0h+var_A60], al
0x1004fcd28  mov     r14d, r12d
0x1004fcd2b  xor     edx, edx; Val
0x1004fcd2d  mov     r8d, 142h; Size
0x1004fcd33  lea     rcx, [rbp+9C0h+var_9C0]; void *
0x1004fcd37  call    memset_0
0x1004fcd3c  xor     edx, edx; Val
0x1004fcd3e  mov     r8d, 206h; Size
0x1004fcd44  lea     rcx, [rbp+9C0h+var_870]; void *
0x1004fcd4b  call    memset_0
0x1004fcd50  mov     qword ptr [rbp+9C0h+var_A28], r12
0x1004fcd54  xorps   xmm0, xmm0
0x1004fcd57  movdqu  [rbp+9C0h+var_A18], xmm0
0x1004fcd5c  test    byte ptr [rdi+18h], 10h
0x1004fcd60  jz      short loc_1004FCD6A
0x1004fcd62  mov     rcx, rdi; struct tagOBJBASE *
0x1004fcd65  call    ?FreeErrors@@YAXPEAUtagOBJBASE@@@Z; FreeErrors(tagOBJBASE *)
0x1004fcd6a  mov     eax, [rdi+5ECh]
0x1004fcd70  and     eax, 30h
0x1004fcd73  mov     rcx, rdi; struct tagSTMT *
0x1004fcd76  cmp     al, 30h ; '0'
0x1004fcd78  jnz     short loc_1004FCD93
0x1004fcd7a  mov     dl, [rsi+88h]; unsigned __int8
0x1004fcd80  call    ?AsyncPostExec@@YAFPEAUtagSTMT@@E@Z; AsyncPostExec(tagSTMT *,uchar)
0x1004fcd85  movzx   ebx, ax
0x1004fcd88  mov     r15d, 2
0x1004fcd8e  jmp     loc_1004FDABF
0x1004fcd93  mov     dword ptr [rsp+0AC0h+var_A98], r12d; unsigned int
0x1004fcd98  mov     [rsp+0AC0h+DestinationSize], r12; unsigned int *
0x1004fcd9d  mov     r9d, [rdi+5E4h]; unsigned int
0x1004fcda4  mov     r8b, [rsi+88h]; unsigned __int8
0x1004fcdab  lea     rdx, [rbp+9C0h+var_A18]; struct CAutoBatchCtx_ODBC *
0x1004fcdaf  call    ?GetBatchCtxOrRecover@@YAFPEAUtagSTMT@@PEAVCAutoBatchCtx_ODBC@@EKPEAKK@Z; GetBatchCtxOrRecover(tagSTMT *,CAutoBatchCtx_ODBC *,uchar,ulong,ulong *,ulong)
0x1004fcdb4  movzx   ebx, ax
0x1004fcdb7  mov     r12, [rdi+468h]
0x1004fcdbe  mov     eax, 2
0x1004fcdc3  cmp     bx, ax
0x1004fcdc6  jz      loc_1004FDABC
0x1004fcdcc  mov     eax, 0FFFEh
0x1004fcdd1  test    ax, bx
0x1004fcdd4  jz      short loc_1004FCDFA
0x1004fcdd6  mov     r15d, 2
0x1004fcddc  test    byte ptr cs:_bidGblFlags, r15b
0x1004fcde3  jz      loc_1004FDABF
0x1004fcde9  mov     edx, 168009h
0x1004fcdee  xor     ecx, ecx
0x1004fcdf0  call    _bidTraceMark
0x1004fcdf5  jmp     loc_1004FDABF
0x1004fcdfa  mov     r8, [rdi+70h]
0x1004fcdfe  xor     r9d, r9d
0x1004fce01  cmp     [r8+1D0h], r9
0x1004fce08  jnz     short loc_1004FCE14
0x1004fce0a  xor     eax, eax
0x1004fce0c  mov     dword ptr [rbp+9C0h+Destination+8], eax
0x1004fce0f  mov     byte ptr [rbp+9C0h+Destination+0Ch], al
0x1004fce12  jmp     short loc_1004FCE2D
0x1004fce14  add     r8, 56Ch; Source
0x1004fce1b  mov     edx, 5; DestinationSize
0x1004fce20  mov     r9d, edx; SourceSize
0x1004fce23  lea     rcx, [rbp+9C0h+Destination+8]; Destination
0x1004fce27  call    cs:__imp_memcpy_s
0x1004fce2d  test    dword ptr [rdi+5ECh], 900h
0x1004fce37  jnz     loc_1004FDA7D
0x1004fce3d  mov     ebx, 1
0x1004fce42  cmp     [rdi+820h], ebx
0x1004fce48  jz      loc_1004FDA7D
0x1004fce4e  lea     rdx, [rsp+0AC0h+var_A5C]; unsigned __int16 *
0x1004fce53  mov     rcx, rdi; struct tagSTMT *
0x1004fce56  call    ?CheckBusy@@YAHPEAUtagSTMT@@PEAG@Z; CheckBusy(tagSTMT *,ushort *)
0x1004fce5b  xor     r9d, r9d
0x1004fce5e  test    eax, eax
0x1004fce60  jz      short loc_1004FCE8F
0x1004fce62  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1004fce66  lea     eax, [rbx+3]
0x1004fce69  test    byte ptr cs:_bidGblFlags, al
0x1004fce6f  jz      short loc_1004FCE7D
0x1004fce71  mov     edx, 16BC09h
0x1004fce76  xor     ecx, ecx
0x1004fce78  call    _bidTraceMark
0x1004fce7d  mov     r15d, 2
0x1004fce83  xor     r12d, r12d
0x1004fce86  or      r14, 0FFFFFFFFFFFFFFFFh
0x1004fce8a  jmp     loc_1004FDAAF
0x1004fce8f  cmp     [rdi+330h], r9w
0x1004fce97  jg      short loc_1004FCEA2
0x1004fce99  cmp     dword ptr [rdi+5E8h], 0FFFFFFFFh
0x1004fcea0  jz      short loc_1004FCEAF
0x1004fcea2  mov     edx, ebx; int
0x1004fcea4  mov     rcx, rdi; struct tagSTMT *
0x1004fcea7  call    ?DropPrepHandle@@YAXPEAUtagSTMT@@H@Z; DropPrepHandle(tagSTMT *,int)
0x1004fceac  xor     r9d, r9d
0x1004fceaf  mov     [rbp+9C0h+var_A30], r9
0x1004fceb3  mov     al, [rsi+82h]
0x1004fceb9  and     al, 9
0x1004fcebb  mov     ecx, 4
0x1004fcec0  lea     r8d, [rcx+17h]
0x1004fcec4  cmp     al, bl
0x1004fcec6  jnz     loc_1004FCFA1
0x1004fcecc  mov     rdx, [rsi+28h]; unsigned __int64
0x1004fced0  cmp     rdx, rbx
0x1004fced3  jnz     short loc_1004FCEF3
0x1004fced5  mov     rax, [rsi+60h]
0x1004fced9  cmp     word ptr [rax], 25h ; '%'
0x1004fcedd  jnz     short loc_1004FCEF3
0x1004fcedf  cmp     [rsi+18h], r9
0x1004fcee3  jnz     short loc_1004FCEF3
0x1004fcee5  mov     [rbp+9C0h+var_A30], r9
0x1004fcee9  cmp     [rsi+20h], r9
0x1004fceed  jz      loc_1004FCFA1
0x1004fcef3  mov     [rbp+9C0h+var_A38], r9d
0x1004fcef7  test    [r13+9B8h], cl
0x1004fcefe  jnz     short loc_1004FCF6B
0x1004fcf00  cmp     [rsi+88h], r8b
0x1004fcf07  jnz     short loc_1004FCF6B
0x1004fcf09  lea     rax, [rbp+9C0h+var_A38]
0x1004fcf0d  mov     [rsp+0AC0h+var_A80], rax; int *
0x1004fcf12  mov     dword ptr [rsp+0AC0h+var_A88], r15d; int
0x1004fcf17  mov     [rsp+0AC0h+var_A90], 181h; unsigned __int64
0x1004fcf20  lea     rax, [rbp+9C0h+var_350]
0x1004fcf27  mov     [rsp+0AC0h+var_A98], rax; unsigned __int16 *
0x1004fcf2c  mov     [rsp+0AC0h+DestinationSize], r13; struct tagDBC *
0x1004fcf31  mov     r9, rsi; struct tagDD_ARG_STRUCT *
0x1004fcf34  mov     r8d, ebx; int
0x1004fcf37  mov     rcx, [rsi+60h]; unsigned __int16 *
0x1004fcf3b  call    ?ConvertArgument@@YAFPEBG_KHPEAUtagDD_ARG_STRUCT@@PEAUtagDBC@@PEAG1HPEAH@Z; ConvertArgument(ushort const *,unsigned __int64,int,tagDD_ARG_STRUCT *,tagDBC *,ushort *,unsigned __int64,int,int *)
0x1004fcf40  movzx   ebx, ax
0x1004fcf43  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1004fcf47  cmp     ax, dx
0x1004fcf4a  jz      loc_1004FCE7D
0x1004fcf50  xor     r9d, r9d
0x1004fcf53  cmp     [rbp+9C0h+var_A38], r9d
0x1004fcf57  jz      short loc_1004FCF66
0x1004fcf59  mov     byte ptr [rsi+88h], 25h ; '%'
0x1004fcf60  mov     [rbp+9C0h+var_A30], r9
0x1004fcf64  jmp     short loc_1004FCFA5
0x1004fcf66  mov     ebx, 1
0x1004fcf6b  mov     rdx, [rsi+28h]; unsigned __int64
0x1004fcf6f  mov     [rbp+9C0h+var_A30], r9
0x1004fcf73  test    rdx, rdx
0x1004fcf76  jz      short loc_1004FCFA1
0x1004fcf78  mov     r14d, ebx
0x1004fcf7b  lea     rax, [rbp+9C0h+var_A28]
0x1004fcf7f  mov     [rsp+0AC0h+DestinationSize], rax; unsigned int
0x1004fcf84  mov     r9d, 103h; unsigned __int64
0x1004fcf8a  lea     r8, [rbp+9C0h+var_870]; unsigned __int16 *
0x1004fcf91  mov     rcx, [rsi+60h]; unsigned __int16 *
0x1004fcf95  call    ?ValidateSearchPattern@@YA_KPEBG_KPEAG1PEA_K@Z; ValidateSearchPattern(ushort const *,unsigned __int64,ushort *,unsigned __int64,unsigned __int64 *)
0x1004fcf9a  mov     [rbp+9C0h+var_A30], rbx
0x1004fcf9e  xor     r9d, r9d
0x1004fcfa1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1004fcfa5  mov     eax, 1
0x1004fcfaa  lea     r8d, [rax+1Ah]
0x1004fcfae  cmp     byte ptr [rsp+0AC0h+var_A60], al
0x1004fcfb2  jnz     short loc_1004FD02F
0x1004fcfb4  mov     cl, [rsi+88h]
0x1004fcfba  mov     al, cl
0x1004fcfbc  sub     al, r8b
0x1004fcfbf  test    al, 0FAh
0x1004fcfc1  jnz     short loc_1004FCFD1
0x1004fcfc3  cmp     cl, 20h ; ' '
0x1004fcfc6  jz      short loc_1004FCFD1
0x1004fcfc8  lea     ecx, [r8-19h]
0x1004fcfcc  movzx   edx, cx
0x1004fcfcf  jmp     short loc_1004FD041
0x1004fcfd1  mov     eax, 9CE2h
0x1004fcfd6  mov     [rsp+0AC0h+var_A5C], ax
0x1004fcfdb  movzx   ebx, dx
0x1004fcfde  mov     r15d, 2
0x1004fcfe4  test    byte ptr cs:_bidGblFlags, r15b
0x1004fcfeb  jz      short loc_1004FCFF9
0x1004fcfed  mov     edx, 17AC09h
0x1004fcff2  xor     ecx, ecx
0x1004fcff4  call    _bidTraceMark
0x1004fcff9  or      r14, 0FFFFFFFFFFFFFFFFh
0x1004fcffd  test    byte ptr cs:_bidGblFlags, r15b
0x1004fd004  jz      short loc_1004FD012
0x1004fd006  mov     edx, 1DC409h
0x1004fd00b  xor     ecx, ecx
0x1004fd00d  call    _bidTraceMark
0x1004fd012  or      dword ptr [rsp+0AC0h+DestinationSize], 0FFFFFFFFh
0x1004fd017  mov     r9, r14; unsigned __int64
0x1004fd01a  xor     r8d, r8d; int
0x1004fd01d  movzx   edx, [rsp+0AC0h+var_A5C]; unsigned __int16
0x1004fd022  mov     rcx, rdi; struct tagOBJBASE *
0x1004fd025  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x1004fd02a  jmp     loc_1004FDAC3
0x1004fd02f  movzx   edx, word ptr [rsi+82h]
0x1004fd036  not     dx
0x1004fd039  and     dx, ax
0x1004fd03c  mov     ecx, 2
0x1004fd041  mov     rax, [r13+40h]
0x1004fd045  lea     r15, __ImageBase
0x1004fd04c  test    rax, rax
0x1004fd04f  jz      short loc_1004FD071
0x1004fd051  mov     rax, [r13+40h]
0x1004fd055  cmp     byte ptr [rax+0F26h], 9
0x1004fd05c  jb      short loc_1004FD071
0x1004fd05e  movzx   eax, byte ptr [rsi+88h]
0x1004fd065  mov     eax, dword ptr (rva off_1005D12A0+4)[r15+rax*4]
0x1004fd06d  mov     [rsp+0AC0h+var_A48], eax
0x1004fd071  mov     rax, [r12+48h]
0x1004fd076  cmp     [rax+1C0h], r9d
0x1004fd07d  jz      short loc_1004FD0A0
0x1004fd07f  movzx   eax, byte ptr [rsi+88h]
0x1004fd086  sub     rax, r8
0x1004fd089  lea     rcx, [rax+rax*2]
0x1004fd08d  movzx   eax, dx
0x1004fd090  add     rcx, rax
0x1004fd093  mov     r15, rva ?g_pwchKauaiProcNamesArr@@3PAY02PEAGA[r15+rcx*8]; ushort * (near * g_pwchKauaiProcNamesArr)[3] ...
0x1004fd09b  jmp     loc_1004FD120
0x1004fd0a0  mov     rax, [r13+40h]
0x1004fd0a4  test    rax, rax
0x1004fd0a7  jz      short loc_1004FD0DC
0x1004fd0a9  mov     rax, [r13+40h]
0x1004fd0ad  cmp     byte ptr [rax+0F26h], 0Ah
0x1004fd0b4  jb      short loc_1004FD0DC
0x1004fd0b6  test    [rax+1A0h], cl
0x1004fd0bc  jnz     short loc_1004FD0DC
0x1004fd0be  movzx   eax, byte ptr [rsi+88h]
0x1004fd0c5  sub     rax, r8
0x1004fd0c8  lea     rcx, [rax+rax*2]
0x1004fd0cc  movzx   eax, dx
0x1004fd0cf  add     rcx, rax
0x1004fd0d2  mov     r15, rva ?g_pwchKatmaiProcNamesArr@@3PAY02PEAGA[r15+rcx*8]; ushort * (near * g_pwchKatmaiProcNamesArr)[3] ...
0x1004fd0da  jmp     short loc_1004FD120
0x1004fd0dc  mov     rax, [r13+40h]
0x1004fd0e0  test    rax, rax
0x1004fd0e3  jz      short loc_1004FD10A
0x1004fd0e5  mov     rax, [r13+40h]
0x1004fd0e9  cmp     byte ptr [rax+0F26h], 9
0x1004fd0f0  jb      short loc_1004FD10A
0x1004fd0f2  movzx   ecx, byte ptr [rsi+88h]
0x1004fd0f9  movzx   eax, dx
0x1004fd0fc  lea     rdx, [rax+rcx*2]
0x1004fd100  mov     r15, rva off_1005D1250[r15+rdx*8]; "[sys].sp_pkeys" ...
0x1004fd108  jmp     short loc_1004FD120
0x1004fd10a  movzx   ecx, byte ptr [rsi+88h]
0x1004fd111  movzx   eax, dx
0x1004fd114  lea     rdx, [rax+rcx*2]
0x1004fd118  mov     r15, rva qword_1005D1190[r15+rdx*8]
0x1004fd120  mov     rcx, rdi; struct tagSTMT *
0x1004fd123  call    ?IsCursorOn@@YAHPEAUtagSTMT@@@Z; IsCursorOn(tagSTMT *)
0x1004fd128  xor     r9d, r9d; unsigned __int16 **
0x1004fd12b  test    eax, eax
0x1004fd12d  jnz     loc_1004FD238
0x1004fd133  test    r14d, r14d
0x1004fd136  jz      short loc_1004FD19C
0x1004fd138  mov     rax, [r13+40h]
0x1004fd13c  test    rax, rax
0x1004fd13f  jz      short loc_1004FD155
0x1004fd141  mov     rax, [r13+40h]
0x1004fd145  cmp     byte ptr [rax+0F26h], 9
0x1004fd14c  lea     rax, szDefault
0x1004fd153  jnb     short loc_1004FD15C
0x1004fd155  lea     rax, asc_100581260; "."
0x1004fd15c  mov     [rsp+0AC0h+var_A80], r15
0x1004fd161  mov     [rsp+0AC0h+var_A88], rax
0x1004fd166  lea     rax, [rbp+9C0h+var_870]
0x1004fd16d  mov     [rsp+0AC0h+var_A90], rax
0x1004fd172  lea     rax, aSSS; "%s.%s%s"
0x1004fd179  mov     [rsp+0AC0h+var_A98], rax; unsigned __int16 *
0x1004fd17e  mov     [rsp+0AC0h+DestinationSize], r9; unsigned int
0x1004fd183  lea     r9, [rbp+9C0h+var_A40]; unsigned __int64 *
0x1004fd187  xor     r8d, r8d; unsigned __int16 **
0x1004fd18a  mov     ebx, 0A1h
0x1004fd18f  mov     edx, ebx; unsigned __int64
0x1004fd191  lea     rcx, [rbp+9C0h+var_9C0]; unsigned __int16 *
  ... truncated ...
```
