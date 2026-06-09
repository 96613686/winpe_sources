# CSimpleTable4ui::UpdateStore(void)

- ea: `0x180039b60`
- end: `0x18003a3e0`
- name: `?UpdateStore@CSimpleTable4ui@@UEAAJXZ`
- size: `2176`
- prototype: `__int64 __fastcall(CSimpleTable4ui *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800033e0`
- `0x180006344`
- `0x180007644`
- `0x18000847c`
- `0x180009ba0`
- `0x18002ebf0`
- `0x18002ee0c`
- `0x180039b60`
- `0x180054fa8`
- `0x18005551a`
- `0x180058010`

## import_xrefs

- `CLBCatQ!SetupSave` at `0x18003a2d7`
- `CLBCatQ!SetupSave` at `0x18003a2d7`
- `CLBCatQ!SetupOpen` at `0x180039bcf`
- `CLBCatQ!SetupOpen` at `0x180039bcf`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180039f79`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x18003a20f`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180039f79`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x18003a20f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a34e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a360`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a372`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a384`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a3a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a3b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a3c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a34e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a360`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a372`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a384`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a3a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a3b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a3c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039c8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039cd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a064`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a0a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a0bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a0da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a0f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039c8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039cd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a064`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a0a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a0bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a0da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a0f8`

## pseudocode

```c
__int64 __fastcall CSimpleTable4ui::UpdateStore(CSimpleTable4ui *this)
{
  bool v2; // zf
  void *v3; // r12
  void *v4; // r15
  void *v5; // r13
  struct IComponentRecords **v6; // rsi
  int ColumnMeta; // ebx
  _BYTE *v8; // rax
  void *v9; // rax
  unsigned int v10; // esi
  __int64 k; // r15
  _DWORD *v12; // rbx
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  bool v16; // sf
  __int64 v17; // rcx
  __int64 v18; // rdx
  unsigned int j; // esi
  __int64 v20; // rcx
  void *v21; // rax
  unsigned __int64 v22; // rcx
  void *v23; // rbx
  LPVOID v24; // rax
  unsigned __int64 v25; // rcx
  void *v26; // r15
  void *v27; // rax
  unsigned __int64 v28; // rcx
  void *v29; // rax
  unsigned __int64 v30; // rcx
  void *v31; // rsi
  void *v32; // rax
  _DWORD *v33; // r12
  char *v34; // rbx
  __int64 v35; // rsi
  unsigned int *v36; // r12
  __int64 i; // rcx
  unsigned int *v39; // [rsp+20h] [rbp-A9h]
  unsigned int v40; // [rsp+70h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-51h]
  void *v42; // [rsp+80h] [rbp-49h]
  LPWSTR lpsz; // [rsp+88h] [rbp-41h] BYREF
  unsigned int v44; // [rsp+90h] [rbp-39h] BYREF
  int v45; // [rsp+94h] [rbp-35h] BYREF
  int v46; // [rsp+98h] [rbp-31h]
  __int64 v47; // [rsp+A0h] [rbp-29h] BYREF
  void *v48; // [rsp+A8h] [rbp-21h]
  int v49; // [rsp+B0h] [rbp-19h]
  int v50; // [rsp+B4h] [rbp-15h] BYREF
  LPVOID v51; // [rsp+B8h] [rbp-11h]
  LPVOID v52; // [rsp+C0h] [rbp-9h]
  LPVOID v53; // [rsp+C8h] [rbp-1h]
  LPVOID v54; // [rsp+D0h] [rbp+7h]
  unsigned int v55; // [rsp+130h] [rbp+67h] BYREF
  unsigned int v56; // [rsp+138h] [rbp+6Fh] BYREF
  unsigned int v57; // [rsp+140h] [rbp+77h] BYREF
  unsigned int v58; // [rsp+148h] [rbp+7Fh] BYREF

  v2 = *((_DWORD *)this + 25) == 1;
  v3 = 0;
  v58 = 0;
  v4 = 0;
  v48 = 0;
  v5 = 0;
  pv = 0;
  v47 = 0;
  v55 = 0;
  v56 = 0;
  v50 = 0;
  lpsz = 0;
  v57 = 0;
  v44 = 0;
  v52 = 0;
  v42 = 0;
  v51 = 0;
  v54 = 0;
  v53 = 0;
  if ( v2 )
  {
    v6 = (struct IComponentRecords **)((char *)this + 264);
    if ( *((_QWORD *)this + 33) && !(unsigned int)SetupOpen() && dword_180072FE8 )
    {
      (*(void (__fastcall **)(struct IComponentRecords *))(*(_QWORD *)*v6 + 16LL))(*v6);
      *v6 = 0;
    }
    ColumnMeta = RegSrvrOpenForWrite(v6);
    if ( ColumnMeta < 0 )
      goto LABEL_95;
    ColumnMeta = (*(__int64 (__fastcall **)(struct IComponentRecords *, void *, _QWORD, char *))(*(_QWORD *)*v6 + 384LL))(
                   *v6,
                   &COMRegSchema,
                   *((unsigned int *)this + 22),
                   (char *)this + 80);
    if ( ColumnMeta < 0 )
      goto LABEL_95;
  }
  v8 = (_BYTE *)*((_QWORD *)this + 3);
  if ( (*v8 & 1) != 0 || (v8[40] & 4) == 0 )
  {
    ColumnMeta = -2147467263;
LABEL_94:
    if ( ColumnMeta >= 0 )
      goto LABEL_98;
    goto LABEL_95;
  }
  if ( *((char *)this + 32) < 0 )
  {
    ColumnMeta = -2146367483;
    goto LABEL_94;
  }
  ColumnMeta = CSimpleDataTableCursor::InternalRestartWriteRow((CSimpleTable4ui *)((char *)this + 24));
  if ( ColumnMeta < 0 )
  {
LABEL_95:
    if ( *((_QWORD *)this + 33) )
    {
      RegSrvrCancelWrite((struct IComponentRecords **)this + 33);
      *((_QWORD *)this + 33) = 0;
    }
    v4 = v42;
    v3 = v48;
LABEL_98:
    if ( !v3 )
      goto LABEL_100;
    goto LABEL_99;
  }
  v9 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 56), 8u));
  v48 = v9;
  v3 = v9;
  if ( !v9
    || (memset_0(v9, 0, 8LL * *((unsigned int *)this + 56)),
        (pv = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 56), 4u))) == 0) )
  {
LABEL_14:
    ColumnMeta = -2147024882;
    goto LABEL_95;
  }
  v46 = 0;
LABEL_17:
  while ( !(unsigned int)CSimpleDataTableCursor::InternalMoveToNextWriteRow(
                           (CSimpleTable4ui *)((char *)this + 24),
                           &v58) )
  {
    v10 = v58;
    if ( v58 - 1 > 2 )
    {
LABEL_34:
      if ( v10 )
      {
        if ( v10 == 1 )
        {
          LODWORD(v39) = 0;
          ColumnMeta = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, _QWORD, unsigned int *, _QWORD))(**((_QWORD **)this + 33) + 24LL))(
                         *((_QWORD *)this + 33),
                         *((_QWORD *)this + 10),
                         &v47,
                         0,
                         v39,
                         0);
          if ( ColumnMeta < 0 )
            goto LABEL_95;
          if ( v52 )
          {
            v33 = v53;
            v34 = (char *)v51;
          }
          else
          {
            v21 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 23), 2u));
            v22 = *((unsigned int *)this + 23);
            v23 = v21;
            v52 = v21;
            v24 = CoTaskMemAlloc(saturated_mul(v22, 8u));
            v25 = *((unsigned int *)this + 23);
            v26 = v24;
            v42 = v24;
            v27 = CoTaskMemAlloc(saturated_mul(v25, 4u));
            v28 = *((unsigned int *)this + 23);
            v51 = v27;
            v29 = CoTaskMemAlloc(saturated_mul(v28, 4u));
            v30 = *((unsigned int *)this + 23);
            v31 = v29;
            v54 = v29;
            v5 = CoTaskMemAlloc(saturated_mul(v30, 4u));
            v32 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 23), 4u));
            v53 = v32;
            v33 = v32;
            if ( !v23 )
              goto LABEL_14;
            if ( !v26 )
              goto LABEL_14;
            v34 = (char *)v51;
            if ( !v51 || !v31 || !v5 || !v32 )
              goto LABEL_14;
            memset_0(v26, 0, 8LL * *((unsigned int *)this + 23));
          }
          memset_0(v5, 0, 4LL * *((unsigned int *)this + 23));
          v35 = 0;
          while ( (unsigned int)v35 < *((_DWORD *)this + 23) )
          {
            v40 = 0;
            v33[v35] = v35 + 1;
            v36 = (unsigned int *)&v34[4 * v35];
            ColumnMeta = CSimpleDataTableCursor::InternalGetWriteColumn(
                           (CSimpleTable4ui *)((char *)this + 24),
                           v35,
                           &v57,
                           &v55,
                           v36,
                           (void **)&lpsz);
            if ( ColumnMeta < 0 )
              goto LABEL_95;
            *((_WORD *)v52 + v35) = v55;
            ColumnMeta = CSimpleDataTableCursor::InternalGetColumnMeta(
                           (CSimpleTable4ui *)((char *)this + 24),
                           v35,
                           0,
                           0,
                           &v40);
            if ( ColumnMeta < 0 )
              goto LABEL_95;
            if ( !lpsz || (v40 & 8) != 0 )
            {
              *((_DWORD *)v5 + v35) = 3;
            }
            else
            {
              if ( v55 == 130 )
              {
                v2 = (v40 & 0x20) == 0;
                *v36 = -1;
                if ( !v2 )
                  CharLowerW(lpsz);
              }
              *((_QWORD *)v42 + v35) = lpsz;
            }
            v33 = v53;
            v35 = (unsigned int)(v35 + 1);
            v34 = (char *)v51;
          }
          v4 = v42;
          ColumnMeta = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 33) + 72LL))(
                         *((_QWORD *)this + 33),
                         *((_QWORD *)this + 10),
                         v47);
          if ( ColumnMeta < 0 )
            goto LABEL_95;
          for ( i = 0; (unsigned int)i < *((_DWORD *)this + 23); i = (unsigned int)(i + 1) )
          {
            ColumnMeta = *((_DWORD *)v5 + i);
            if ( ColumnMeta < 0 )
              goto LABEL_95;
          }
          v3 = v48;
        }
        else
        {
          if ( v10 - 2 > 1 )
          {
            ColumnMeta = -2147418113;
            goto LABEL_95;
          }
          if ( v10 != 3 )
          {
            for ( j = *((_DWORD *)this + 56); ; ++j )
            {
              if ( j >= *((_DWORD *)this + 23) )
                goto LABEL_17;
              v45 = 0;
              ColumnMeta = CSimpleDataTableCursor::InternalGetWriteColumn(
                             (CSimpleTable4ui *)((char *)this + 24),
                             j,
                             &v57,
                             &v55,
                             &v56,
                             (void **)&lpsz);
              if ( ColumnMeta < 0 )
                goto LABEL_95;
              if ( (v57 & 4) == 0 && (!v46 || (v57 & 2) != 0) )
              {
                v40 = 0;
                ColumnMeta = CSimpleDataTableCursor::InternalGetColumnMeta(
                               (CSimpleTable4ui *)((char *)this + 24),
                               j,
                               0,
                               0,
                               &v40);
                if ( ColumnMeta < 0 )
                  goto LABEL_95;
                if ( lpsz )
                {
                  if ( (v40 & 8) != 0 )
                    goto LABEL_55;
                  if ( v55 == 130 )
                  {
                    v56 = -1;
                    if ( (v40 & 0x20) != 0 )
                      CharLowerW(lpsz);
                  }
                }
                else
                {
                  v45 = 3;
                }
                v20 = *((_QWORD *)this + 33);
                v44 = j + 1;
                ColumnMeta = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, int, unsigned int *, LPWSTR *, unsigned int *, int *, int *, unsigned int *))(*(_QWORD *)v20 + 72LL))(
                               v20,
                               *((_QWORD *)this + 10),
                               v47,
                               1,
                               1,
                               &v55,
                               &lpsz,
                               &v56,
                               &v50,
                               &v45,
                               &v44);
                if ( ColumnMeta < 0 )
                  goto LABEL_95;
              }
LABEL_55:
              ColumnMeta = v45;
              if ( v45 < 0 )
                goto LABEL_95;
            }
          }
          v17 = *((_QWORD *)this + 33);
          v18 = *((_QWORD *)this + 10);
          v40 = 0;
          ColumnMeta = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned int *))(*(_QWORD *)v17 + 104LL))(
                         v17,
                         v18,
                         v47,
                         &v40);
          if ( ColumnMeta < 0 )
            goto LABEL_95;
          ColumnMeta = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 33) + 336LL))(
                         *((_QWORD *)this + 33),
                         *((_QWORD *)this + 10),
                         v40);
          if ( ColumnMeta < 0 )
            goto LABEL_95;
        }
      }
    }
    else
    {
      for ( k = 0; (unsigned int)k < *((_DWORD *)this + 56); k = (unsigned int)(k + 1) )
      {
        ColumnMeta = CSimpleDataTableCursor::InternalGetWriteColumn(
                       (CSimpleTable4ui *)((char *)this + 24),
                       *(_DWORD *)(*((_QWORD *)this + 29) + 4 * k) - 1,
                       &v57,
                       &v55,
                       &v56,
                       (void **)&lpsz);
        if ( ColumnMeta < 0 )
          goto LABEL_95;
        v12 = pv;
        *((_QWORD *)v48 + k) = lpsz;
        v12[k] = v56;
      }
      v13 = (__int64 *)*((_QWORD *)this + 33);
      v49 = 0;
      v14 = *v13;
      v46 = 0;
      v3 = v48;
      v39 = (unsigned int *)*((_QWORD *)this + 29);
      v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, char *))(v14 + 120))(
              v13,
              *((_QWORD *)this + 10),
              (char *)this + 248);
      ColumnMeta = v15;
      if ( v15 != -2147217360 )
      {
        if ( v10 == 1 )
        {
          v16 = v15 < 0;
          if ( !v15 )
          {
            if ( v49 > 0 )
            {
              v10 = 2;
              v46 = 1;
              v58 = 2;
            }
LABEL_33:
            v4 = v42;
            goto LABEL_34;
          }
        }
        else
        {
          v16 = v15 < 0;
        }
        if ( v16 )
          goto LABEL_95;
        goto LABEL_33;
      }
      v4 = v42;
      if ( v10 != 3 )
      {
        if ( v10 == 2 )
        {
          v10 = 1;
          v58 = 1;
        }
        goto LABEL_34;
      }
    }
  }
  ColumnMeta = CSimpleDataTableCursor::InternalPostUpdateStore((CSimpleTable4ui *)((char *)this + 24));
  if ( ColumnMeta < 0 )
    goto LABEL_95;
  if ( *((_DWORD *)this + 25) != 1 || !*((_QWORD *)this + 33) || (unsigned int)SetupSave() )
  {
    ColumnMeta = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 33) + 408LL))(
                   *((_QWORD *)this + 33),
                   0);
    goto LABEL_94;
  }
  ColumnMeta = RegSrvrSave((struct IComponentRecords **)this + 33);
  if ( ColumnMeta < 0 )
    goto LABEL_95;
  *((_QWORD *)this + 33) = 0;
LABEL_99:
  CoTaskMemFree(v3);
LABEL_100:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v51 )
    CoTaskMemFree(v51);
  if ( v54 )
    CoTaskMemFree(v54);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v53 )
    CoTaskMemFree(v53);
  if ( v52 )
    CoTaskMemFree(v52);
  if ( v4 )
    CoTaskMemFree(v4);
  return (unsigned int)ColumnMeta;
}

```

## disassembly

```asm
0x180039b60  push    rbp
0x180039b62  push    rbx
0x180039b63  push    rsi
0x180039b64  push    rdi
0x180039b65  push    r12
0x180039b67  push    r13
0x180039b69  push    r14
0x180039b6b  push    r15
0x180039b6d  lea     rbp, [rsp-1Fh]
0x180039b72  sub     rsp, 0E8h
0x180039b79  xor     ebx, ebx
0x180039b7b  mov     rdi, rcx
0x180039b7e  cmp     dword ptr [rcx+64h], 1
0x180039b82  mov     r12d, ebx
0x180039b85  mov     [rbp+57h+arg_18], ebx
0x180039b88  mov     r15d, ebx
0x180039b8b  mov     [rbp+57h+var_78], rbx
0x180039b8f  mov     r13d, ebx
0x180039b92  mov     [rbp+57h+pv], rbx
0x180039b96  mov     [rbp+57h+var_80], rbx
0x180039b9a  mov     [rbp+57h+arg_0], ebx
0x180039b9d  mov     [rbp+57h+arg_8], ebx
0x180039ba0  mov     [rbp+57h+var_6C], ebx
0x180039ba3  mov     [rbp+57h+lpsz], rbx
0x180039ba7  mov     [rbp+57h+arg_10], ebx
0x180039baa  mov     [rbp+57h+var_90], ebx
0x180039bad  mov     [rbp+57h+var_60], rbx
0x180039bb1  mov     [rbp+57h+var_A0], rbx
0x180039bb5  mov     [rbp+57h+var_68], rbx
0x180039bb9  mov     [rbp+57h+var_50], rbx
0x180039bbd  mov     [rbp+57h+var_58], rbx
0x180039bc1  jnz     short loc_180039C32
0x180039bc3  lea     rsi, [rcx+108h]
0x180039bca  cmp     [rsi], rbx
0x180039bcd  jz      short loc_180039BF3
0x180039bcf  call    cs:__imp_SetupOpen
0x180039bd5  test    eax, eax
0x180039bd7  jnz     short loc_180039BF3
0x180039bd9  cmp     cs:dword_180072FE8, ebx
0x180039bdf  jz      short loc_180039BF3
0x180039be1  mov     rcx, [rsi]
0x180039be4  mov     rax, [rcx]
0x180039be7  mov     rax, [rax+10h]
0x180039beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039bf0  mov     [rsi], rbx
0x180039bf3  mov     rcx, rsi; struct IComponentRecords **
0x180039bf6  call    ?RegSrvrOpenForWrite@@YAJPEAPEAUIComponentRecords@@@Z; RegSrvrOpenForWrite(IComponentRecords * *)
0x180039bfb  mov     ebx, eax
0x180039bfd  test    eax, eax
0x180039bff  js      loc_18003A31D
0x180039c05  mov     rcx, [rsi]
0x180039c08  lea     r9, [rdi+50h]
0x180039c0c  mov     r8d, [rdi+58h]
0x180039c10  lea     rdx, ?COMRegSchema@@3U_tagCOMPLIBSCHEMA@@B; _tagCOMPLIBSCHEMA const COMRegSchema
0x180039c17  mov     rax, [rcx]
0x180039c1a  mov     rax, [rax+180h]
0x180039c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c26  mov     ebx, eax
0x180039c28  test    eax, eax
0x180039c2a  js      loc_18003A31D
0x180039c30  xor     ebx, ebx
0x180039c32  lea     r14, [rdi+18h]
0x180039c36  mov     rax, [r14]
0x180039c39  test    byte ptr [rax], 1
0x180039c3c  jnz     loc_18003A314
0x180039c42  test    byte ptr [rax+28h], 4
0x180039c46  jz      loc_18003A314
0x180039c4c  cmp     [r14+8], bl
0x180039c50  jge     short loc_180039C5C
0x180039c52  mov     ebx, 80110805h
0x180039c57  jmp     loc_18003A319
0x180039c5c  mov     rcx, r14; this
0x180039c5f  call    ?InternalRestartWriteRow@CSimpleDataTableCursor@@QEAAJXZ; CSimpleDataTableCursor::InternalRestartWriteRow(void)
0x180039c64  mov     ebx, eax
0x180039c66  test    eax, eax
0x180039c68  js      loc_18003A31D
0x180039c6e  mov     ecx, [rdi+0E0h]
0x180039c74  mov     eax, 8
0x180039c79  mul     rcx
0x180039c7c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180039c83  cmovb   rax, rbx
0x180039c87  mov     rcx, rax; cb
0x180039c8a  call    cs:__imp_CoTaskMemAlloc
0x180039c90  mov     [rbp+57h+var_78], rax
0x180039c94  mov     r12, rax
0x180039c97  test    rax, rax
0x180039c9a  jnz     short loc_180039CA6
0x180039c9c  mov     ebx, 8007000Eh
0x180039ca1  jmp     loc_18003A31D
0x180039ca6  mov     r8d, [rdi+0E0h]
0x180039cad  xor     edx, edx; Val
0x180039caf  shl     r8, 3; Size
0x180039cb3  mov     rcx, rax; void *
0x180039cb6  call    memset_0
0x180039cbb  mov     ecx, [rdi+0E0h]
0x180039cc1  mov     eax, 4
0x180039cc6  mul     rcx
0x180039cc9  cmovb   rax, rbx
0x180039ccd  mov     rcx, rax; cb
0x180039cd0  call    cs:__imp_CoTaskMemAlloc
0x180039cd6  mov     [rbp+57h+pv], rax
0x180039cda  mov     rbx, rax
0x180039cdd  test    rax, rax
0x180039ce0  jz      short loc_180039C9C
0x180039ce2  mov     [rbp+57h+var_88], r13d
0x180039ce6  lea     rdx, [rbp+57h+arg_18]; unsigned int *
0x180039cea  mov     rcx, r14; this
0x180039ced  call    ?InternalMoveToNextWriteRow@CSimpleDataTableCursor@@QEAAJPEAK@Z; CSimpleDataTableCursor::InternalMoveToNextWriteRow(ulong *)
0x180039cf2  test    eax, eax
0x180039cf4  jnz     loc_18003A2B6
0x180039cfa  mov     esi, [rbp+57h+arg_18]
0x180039cfd  lea     eax, [rsi-1]
0x180039d00  cmp     eax, 2
0x180039d03  ja      loc_180039E3D
0x180039d09  xor     r15d, r15d
0x180039d0c  mov     r9d, [rdi+0E0h]
0x180039d13  cmp     r15d, r9d
0x180039d16  jnb     short loc_180039D6D
0x180039d18  mov     rax, [rdi+0E8h]
0x180039d1f  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180039d23  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x180039d27  mov     rcx, r14; this
0x180039d2a  mov     edx, [rax+r15*4]
0x180039d2e  lea     rax, [rbp+57h+lpsz]
0x180039d32  mov     [rsp+120h+var_F8], rax; void **
0x180039d37  dec     edx; unsigned int
0x180039d39  lea     rax, [rbp+57h+arg_8]
0x180039d3d  mov     [rsp+120h+var_100], rax; unsigned int *
0x180039d42  call    ?InternalGetWriteColumn@CSimpleDataTableCursor@@QEAAJKPEAK00PEAPEAX@Z; CSimpleDataTableCursor::InternalGetWriteColumn(ulong,ulong *,ulong *,ulong *,void * *)
0x180039d47  mov     ebx, eax
0x180039d49  test    eax, eax
0x180039d4b  js      loc_18003A31D
0x180039d51  mov     rax, [rbp+57h+lpsz]
0x180039d55  mov     rcx, [rbp+57h+var_78]
0x180039d59  mov     rbx, [rbp+57h+pv]
0x180039d5d  mov     [rcx+r15*8], rax
0x180039d61  mov     eax, [rbp+57h+arg_8]
0x180039d64  mov     [rbx+r15*4], eax
0x180039d68  inc     r15d
0x180039d6b  jmp     short loc_180039D0C
0x180039d6d  mov     rcx, [rdi+108h]
0x180039d74  lea     rdx, [rbp+57h+var_70]
0x180039d78  mov     [rsp+120h+var_C0], rdx
0x180039d7d  lea     r8, [rdi+0F8h]
0x180039d84  xor     r12d, r12d
0x180039d87  lea     rdx, [rbp+57h+var_80]
0x180039d8b  mov     [rsp+120h+var_C8], r12
0x180039d90  mov     [rbp+57h+var_70], r12d
0x180039d94  mov     rax, [rcx]
0x180039d97  lea     r15d, [r12+1]
0x180039d9c  mov     [rbp+57h+var_88], r12d
0x180039da0  mov     r12, [rbp+57h+var_78]
0x180039da4  mov     dword ptr [rsp+120h+var_D0], r15d
0x180039da9  mov     rax, [rax+78h]
0x180039dad  mov     [rsp+120h+var_D8], rdx
0x180039db2  mov     rdx, [rdi+0F0h]
0x180039db9  mov     [rsp+120h+var_E0], rdx
0x180039dbe  mov     rdx, [rdi+0E8h]
0x180039dc5  mov     [rsp+120h+var_E8], rbx
0x180039dca  mov     [rsp+120h+var_F0], r12
0x180039dcf  mov     [rsp+120h+var_F8], 0
0x180039dd8  mov     [rsp+120h+var_100], rdx
0x180039ddd  mov     rdx, [rdi+50h]
0x180039de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039de6  mov     ebx, eax
0x180039de8  cmp     eax, 80041030h
0x180039ded  jnz     short loc_180039E0F
0x180039def  mov     r15, [rbp+57h+var_A0]
0x180039df3  mov     rbx, [rbp+57h+pv]
0x180039df7  cmp     esi, 3
0x180039dfa  jz      loc_180039CE6
0x180039e00  cmp     esi, 2
0x180039e03  jnz     short loc_180039E3D
0x180039e05  mov     esi, 1
0x180039e0a  mov     [rbp+57h+arg_18], esi
0x180039e0d  jmp     short loc_180039E3D
0x180039e0f  cmp     esi, r15d
0x180039e12  jnz     short loc_180039E2D
0x180039e14  test    eax, eax
0x180039e16  jnz     short loc_180039E2F
0x180039e18  mov     rbx, [rbp+57h+pv]
0x180039e1c  cmp     [rbp+57h+var_70], eax
0x180039e1f  jle     short loc_180039E39
0x180039e21  lea     esi, [rax+2]
0x180039e24  mov     [rbp+57h+var_88], r15d
0x180039e28  mov     [rbp+57h+arg_18], esi
0x180039e2b  jmp     short loc_180039E39
0x180039e2d  test    eax, eax
0x180039e2f  js      loc_18003A31D
0x180039e35  mov     rbx, [rbp+57h+pv]
0x180039e39  mov     r15, [rbp+57h+var_A0]
0x180039e3d  mov     eax, esi
0x180039e3f  test    esi, esi
0x180039e41  jz      loc_180039CE6
0x180039e47  sub     eax, 1
0x180039e4a  jz      loc_18003A007
0x180039e50  sub     eax, 1
0x180039e53  jz      short loc_180039E5E
0x180039e55  cmp     eax, 1
0x180039e58  jnz     loc_18003A2AF
0x180039e5e  cmp     esi, 3
0x180039e61  jnz     short loc_180039EC4
0x180039e63  mov     rcx, [rdi+108h]
0x180039e6a  lea     r9, [rbp+57h+var_B0]
0x180039e6e  mov     r8, [rbp+57h+var_80]
0x180039e72  mov     rdx, [rdi+50h]
0x180039e76  mov     [rbp+57h+var_B0], 0
0x180039e7d  mov     rax, [rcx]
0x180039e80  mov     rax, [rax+68h]
0x180039e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e89  mov     ebx, eax
0x180039e8b  test    eax, eax
0x180039e8d  js      loc_18003A31D
0x180039e93  mov     rcx, [rdi+108h]
0x180039e9a  mov     r8d, [rbp+57h+var_B0]
0x180039e9e  mov     rdx, [rdi+50h]
0x180039ea2  mov     rax, [rcx]
0x180039ea5  mov     rax, [rax+150h]
0x180039eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039eb1  mov     ebx, eax
0x180039eb3  test    eax, eax
0x180039eb5  js      loc_18003A31D
0x180039ebb  mov     rbx, [rbp+57h+pv]
0x180039ebf  jmp     loc_180039CE6
0x180039ec4  mov     esi, [rdi+0E0h]
0x180039eca  mov     rbx, [rbp+57h+pv]
0x180039ece  cmp     esi, [rdi+5Ch]
0x180039ed1  jnb     loc_180039CE6
0x180039ed7  lea     rax, [rbp+57h+lpsz]
0x180039edb  mov     [rbp+57h+var_8C], 0
0x180039ee2  mov     [rsp+120h+var_F8], rax; void **
0x180039ee7  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180039eeb  lea     rax, [rbp+57h+arg_8]
0x180039eef  mov     edx, esi; unsigned int
0x180039ef1  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x180039ef5  mov     [rsp+120h+var_100], rax; unsigned int *
0x180039efa  mov     rcx, r14; this
0x180039efd  call    ?InternalGetWriteColumn@CSimpleDataTableCursor@@QEAAJKPEAK00PEAPEAX@Z; CSimpleDataTableCursor::InternalGetWriteColumn(ulong,ulong *,ulong *,ulong *,void * *)
0x180039f02  mov     ebx, eax
0x180039f04  test    eax, eax
0x180039f06  js      loc_18003A31D
0x180039f0c  test    byte ptr [rbp+57h+arg_10], 4
0x180039f10  jnz     loc_180039FF5
0x180039f16  cmp     [rbp+57h+var_88], 0
0x180039f1a  jz      short loc_180039F26
0x180039f1c  test    byte ptr [rbp+57h+arg_10], 2
0x180039f20  jz      loc_180039FF5
0x180039f26  lea     rax, [rbp+57h+var_B0]
0x180039f2a  mov     [rbp+57h+var_B0], 0
0x180039f31  xor     r9d, r9d; unsigned int *
0x180039f34  mov     [rsp+120h+var_100], rax; unsigned int *
0x180039f39  xor     r8d, r8d; unsigned int *
0x180039f3c  mov     edx, esi; unsigned int
0x180039f3e  mov     rcx, r14; this
0x180039f41  call    ?InternalGetColumnMeta@CSimpleDataTableCursor@@QEAAJKPEAK00@Z; CSimpleDataTableCursor::InternalGetColumnMeta(ulong,ulong *,ulong *,ulong *)
0x180039f46  mov     ebx, eax
0x180039f48  test    eax, eax
0x180039f4a  js      loc_18003A31D
0x180039f50  mov     rcx, [rbp+57h+lpsz]; lpsz
0x180039f54  test    rcx, rcx
0x180039f57  jz      short loc_180039F81
0x180039f59  test    byte ptr [rbp+57h+var_B0], 8
0x180039f5d  jnz     loc_180039FF5
0x180039f63  cmp     [rbp+57h+arg_0], 82h
0x180039f6a  jnz     short loc_180039F88
0x180039f6c  test    byte ptr [rbp+57h+var_B0], 20h
0x180039f70  mov     [rbp+57h+arg_8], 0FFFFFFFFh
0x180039f77  jz      short loc_180039F88
0x180039f79  call    cs:__imp_CharLowerW
0x180039f7f  jmp     short loc_180039F88
0x180039f81  mov     [rbp+57h+var_8C], 3
0x180039f88  mov     rcx, [rdi+108h]
0x180039f8f  lea     rdx, [rbp+57h+var_90]
0x180039f93  mov     r8, [rbp+57h+var_80]
0x180039f97  lea     eax, [rsi+1]
0x180039f9a  mov     [rsp+120h+var_D0], rdx
0x180039f9f  lea     rdx, [rbp+57h+var_8C]
0x180039fa3  mov     [rsp+120h+var_D8], rdx
0x180039fa8  lea     rdx, [rbp+57h+var_6C]
0x180039fac  mov     [rsp+120h+var_E0], rdx
0x180039fb1  lea     rdx, [rbp+57h+arg_8]
0x180039fb5  mov     [rsp+120h+var_E8], rdx
0x180039fba  lea     rdx, [rbp+57h+lpsz]
0x180039fbe  mov     [rsp+120h+var_F0], rdx
0x180039fc3  lea     rdx, [rbp+57h+arg_0]
0x180039fc7  mov     [rsp+120h+var_F8], rdx
0x180039fcc  mov     edx, 1
0x180039fd1  mov     [rbp+57h+var_90], eax
0x180039fd4  mov     r9d, edx
0x180039fd7  mov     rax, [rcx]
0x180039fda  mov     dword ptr [rsp+120h+var_100], edx
0x180039fde  mov     rdx, [rdi+50h]
0x180039fe2  mov     rax, [rax+48h]
0x180039fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039feb  mov     ebx, eax
0x180039fed  test    eax, eax
0x180039fef  js      loc_18003A31D
0x180039ff5  mov     ebx, [rbp+57h+var_8C]
0x180039ff8  test    ebx, ebx
0x180039ffa  js      loc_18003A31D
  ... truncated ...
```
