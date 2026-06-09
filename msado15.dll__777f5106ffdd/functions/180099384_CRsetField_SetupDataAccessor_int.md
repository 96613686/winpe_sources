# CRsetField::SetupDataAccessor(int)

- ea: `0x180099384`
- end: `0x180099b86`
- name: `?SetupDataAccessor@CRsetField@@QEAAJH@Z`
- size: `2050`
- prototype: `__int64 __fastcall(CRsetField *__hidden this, int)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180008340`
- `0x1800099e0`
- `0x180097e7c`
- `0x180098458`

## callees

- `0x180001514`
- `0x18000a09c`
- `0x180011530`
- `0x18003d2b0`
- `0x18006a22c`
- `0x180099384`
- `0x180099b8c`
- `0x1800c8f34`
- `0x1800cdaea`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800998bf`
- `MSDART!MpHeapAlloc` at `0x180099967`
- `MSDART!MpHeapAlloc` at `0x1800998bf`
- `MSDART!MpHeapAlloc` at `0x180099967`

## string_xrefs

- `0x1800994ec`: `<CRsetField::SetupDataAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180099659`: `<CRsetField::SetupDataAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18009979c`: `<CRsetField::SetupDataAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18009985d`: `<CRsetField::SetupDataAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180099916`: `<CRsetField::SetupDataAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180099ac9`: `<CRsetField::SetupDataAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180099518`: `<CRsetField::SetupDataAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180099677`: `<CRsetField::SetupDataAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800997ba`: `<CRsetField::SetupDataAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x18009987e`: `<CRsetField::SetupDataAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180099a15`: `<CRsetField::SetupDataAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180099af5`: `<CRsetField::SetupDataAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRsetField::SetupDataAccessor(CRsetField *this, int a2)
{
  _QWORD *v4; // r12
  int v5; // edx
  unsigned __int16 v6; // si
  int v7; // ecx
  __int64 v8; // rax
  __int64 v9; // rax
  int IRowset; // edi
  unsigned int BidObjectID; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  _DWORD *v14; // r14
  _DWORD *v15; // r13
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  unsigned int v20; // eax
  _QWORD *v21; // rsi
  unsigned int v22; // eax
  void *v23; // rcx
  __int64 v24; // rax
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdx
  void *v28; // rcx
  __int64 v29; // rax
  __int64 v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+20h] [rbp-E0h]
  __int64 v35; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+28h] [rbp-D8h]
  __int64 v37; // [rsp+28h] [rbp-D8h]
  __int64 v38; // [rsp+28h] [rbp-D8h]
  __int64 v39; // [rsp+28h] [rbp-D8h]
  struct IRowset *v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v41; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v42; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v45[24]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h]
  char v47; // [rsp+A8h] [rbp-58h]
  _BYTE v48[24]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v49; // [rsp+E8h] [rbp-18h]
  char v50; // [rsp+108h] [rbp+8h]
  _QWORD v51[3]; // [rsp+130h] [rbp+30h] BYREF
  int v52; // [rsp+148h] [rbp+48h]
  __int64 v53; // [rsp+150h] [rbp+50h]
  __int16 v54; // [rsp+158h] [rbp+58h]
  char v55; // [rsp+15Ah] [rbp+5Ah]
  char v56; // [rsp+15Bh] [rbp+5Bh]
  int v57; // [rsp+170h] [rbp+70h]
  __int64 v58; // [rsp+178h] [rbp+78h]

  v43 = 0;
  memset_0(v48, 0, 0x58u);
  memset_0(v45, 0, 0x58u);
  v44 = 0;
  v42 = 0;
  v41 = 0;
  if ( *((_QWORD *)this + 33) )
  {
    v4 = (_QWORD *)((char *)this + 288);
    if ( !*((_QWORD *)this + 36) )
    {
      if ( *((_QWORD *)this + 21) )
      {
        memset_0(v51, 0, 0x50u);
        v40 = 0;
        v5 = *((_DWORD *)this + 33);
        v6 = (v5 & 0x2000) != 0 ? 3 : 0;
        v7 = *((_BYTE *)this + 96) & 4;
        if ( (*((_BYTE *)this + 96) & 4) != 0 )
          v8 = *((_QWORD *)this + 11);
        else
          v8 = 0;
        v51[0] = v8;
        v51[1] = 0;
        v51[2] = *((_QWORD *)this + 13);
        v52 = v5;
        v53 = *((_QWORD *)this + 15);
        v54 = *((_WORD *)this + 56);
        v55 = *((_BYTE *)this + 128);
        v56 = *((_BYTE *)this + 129);
        v57 = 2;
        if ( v7 )
          v9 = *((_QWORD *)this + 11);
        else
          v9 = 0;
        v58 = v9;
        IRowset = CRsetField::GetIRowset(this, &v40);
        if ( IRowset < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
          {
LABEL_62:
            ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v40);
            return (unsigned int)IRowset;
          }
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
            LODWORD(v36) = 1358;
            v12 = 1390601;
LABEL_14:
            LODWORD(v32) = IRowset;
            bidTraceW(
              off_18012A1F0[0],
              v12,
              L"<CRsetField::SetupDataAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
              BidObjectID,
              v32,
              v36);
            goto LABEL_62;
          }
          LODWORD(v32) = 1358;
          v13 = 1390601;
          goto LABEL_16;
        }
        v14 = (_DWORD *)((char *)this + 276);
        IRowset = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct IRowset *, _QWORD *, _BYTE *, unsigned int *, char *))(**((_QWORD **)this + 33) + 24LL))(
                    *((_QWORD *)this + 33),
                    v6,
                    0,
                    v40,
                    v51,
                    v45,
                    &v41,
                    (char *)this + 276);
        if ( IRowset < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_62;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
            LODWORD(v36) = 1367;
            v12 = 1399817;
            goto LABEL_14;
          }
          LODWORD(v32) = 1367;
          v13 = 1399817;
LABEL_16:
          bidTraceW(
            off_18012A1F0[0],
            v13,
            L"<CRsetField::SetupDataAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            (unsigned int)IRowset,
            v32);
          goto LABEL_62;
        }
        v15 = (_DWORD *)((char *)this + 272);
        IRowset = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct IRowset *, _QWORD *, _BYTE *, unsigned int *, char *))(**((_QWORD **)this + 33) + 24LL))(
                    *((_QWORD *)this + 33),
                    v6,
                    0,
                    v40,
                    v51,
                    v48,
                    &v42,
                    (char *)this + 272);
        if ( IRowset < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) == -1 )
            {
              LODWORD(v33) = 1375;
              bidTraceW(
                off_18012A1F0[0],
                1408009,
                L"<CRsetField::SetupDataAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                (unsigned int)IRowset,
                v33);
            }
            else
            {
              v16 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
              LODWORD(v37) = 1375;
              LODWORD(v33) = IRowset;
              bidTraceW(
                off_18012A1F0[0],
                1408009,
                L"<CRsetField::SetupDataAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                v16,
                v33,
                v37);
            }
          }
          ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v40);
          goto LABEL_81;
        }
        if ( !v41 || !v42 )
        {
          IRowset = -2146824867;
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
            {
              v17 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
              LODWORD(v37) = 1381;
              v18 = 1414153;
              goto LABEL_76;
            }
            LODWORD(v33) = 1381;
            v19 = 1414153;
LABEL_78:
            bidTraceW(
              off_18012A1F0[0],
              v19,
              L"<CRsetField::SetupDataAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n",
              (unsigned int)IRowset,
              v33);
          }
LABEL_79:
          ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v40);
LABEL_80:
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 33) + 56LL))(
            *((_QWORD *)this + 33),
            (unsigned int)*v15);
          *v15 = 0;
LABEL_81:
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 33) + 56LL))(
            *((_QWORD *)this + 33),
            (unsigned int)*v14);
          *v14 = 0;
          return (unsigned int)IRowset;
        }
        IRowset = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))v40->lpVtbl->QueryInterface)(
                    v40,
                    &IID_IAccessor,
                    &v43);
        if ( IRowset < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
            {
              v17 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
              LODWORD(v37) = 1384;
              v18 = 1417225;
LABEL_76:
              LODWORD(v33) = IRowset;
              bidTraceW(
                off_18012A1F0[0],
                v18,
                L"<CRsetField::SetupDataAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                v17,
                v33,
                v37);
              goto LABEL_79;
            }
            LODWORD(v33) = 1384;
            v19 = 1417225;
            goto LABEL_78;
          }
          goto LABEL_79;
        }
        IRowset = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *, _QWORD, char *, int *))(*(_QWORD *)v43 + 32LL))(
                    v43,
                    2,
                    1,
                    v45,
                    0,
                    (char *)this + 288,
                    &v44);
        if ( IRowset < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) == -1 )
            {
              LODWORD(v34) = 1387;
              bidTraceW(
                off_18012A1F0[0],
                1420297,
                L"<CRsetField::SetupDataAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                (unsigned int)IRowset,
                v34);
            }
            else
            {
              v20 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
              LODWORD(v38) = 1387;
              LODWORD(v34) = IRowset;
              bidTraceW(
                off_18012A1F0[0],
                1420297,
                L"<CRsetField::SetupDataAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                v20,
                v34,
                v38);
            }
          }
          v21 = (_QWORD *)((char *)this + 280);
          goto LABEL_68;
        }
        v21 = (_QWORD *)((char *)this + 280);
        IRowset = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *, _QWORD, char *, int *))(*(_QWORD *)v43 + 32LL))(
                    v43,
                    2,
                    1,
                    v48,
                    0,
                    (char *)this + 280,
                    &v44);
        if ( IRowset < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) == -1 )
            {
              LODWORD(v35) = 1390;
              bidTraceW(
                off_18012A1F0[0],
                1423369,
                L"<CRsetField::SetupDataAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                (unsigned int)IRowset,
                v35);
            }
            else
            {
              v22 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
              LODWORD(v39) = 1390;
              LODWORD(v35) = IRowset;
              bidTraceW(
                off_18012A1F0[0],
                1423369,
                L"<CRsetField::SetupDataAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                v22,
                v35,
                v39);
            }
          }
          goto LABEL_68;
        }
        v23 = (void *)*((_QWORD *)this + 38);
        if ( v23 )
          operator delete(v23);
        v24 = MpHeapAlloc(g_hHeapHandle, 10485760, v41);
        *((_QWORD *)this + 38) = v24;
        if ( v24 )
        {
          v28 = (void *)*((_QWORD *)this + 37);
          if ( v28 )
            operator delete(v28);
          v29 = MpHeapAlloc(g_hHeapHandle, 10485760, v42);
          *((_QWORD *)this + 37) = v29;
          if ( v29 )
          {
            IRowset = 0;
            if ( (v47 & 4) != 0 )
              *((_QWORD *)this + 25) = v46;
            if ( (v50 & 4) != 0 )
              *((_QWORD *)this + 26) = v49;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
            goto LABEL_62;
          }
          IRowset = -2147024882;
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_68;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
          {
            v25 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
            LODWORD(v39) = 1400;
            v26 = 1433609;
            goto LABEL_52;
          }
          LODWORD(v35) = 1400;
          v27 = 1433609;
        }
        else
        {
          IRowset = -2147024882;
          if ( (bidGblFlags & 2) == 0 )
          {
LABEL_68:
            ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v40);
            if ( *v21 )
            {
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v43 + 48LL))(v43, *v21, 0);
              *v21 = 0;
            }
            if ( *v4 )
            {
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v43 + 48LL))(v43, *v4, 0);
              *v4 = 0;
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
            v14 = (_DWORD *)((char *)this + 276);
            goto LABEL_80;
          }
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
          {
            v25 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
            LODWORD(v39) = 1395;
            v26 = 1428489;
LABEL_52:
            LODWORD(v35) = -2147024882;
            bidTraceW(
              off_18012A1F0[0],
              v26,
              L"<CRsetField::SetupDataAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
              v25,
              v35,
              v39);
            goto LABEL_68;
          }
          LODWORD(v35) = 1395;
          v27 = 1428489;
        }
        bidTraceW(
          off_18012A1F0[0],
          v27,
          L"<CRsetField::SetupDataAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          2147942414LL,
          v35);
        goto LABEL_68;
      }
    }
  }
  if ( a2 )
    return (unsigned int)CRsetField::SetupDefaultGetDataAccessor(this, 0);
  else
    return (unsigned int)CRsetField::SetupDefaultSetDataAccessor(this);
}

```

## disassembly

```asm
0x180099384  push    rbp
0x180099386  push    rbx
0x180099387  push    rsi
0x180099388  push    rdi
0x180099389  push    r12
0x18009938b  push    r13
0x18009938d  push    r14
0x18009938f  push    r15
0x180099391  lea     rbp, [rsp-98h]
0x180099399  sub     rsp, 198h
0x1800993a0  mov     rax, cs:__security_cookie
0x1800993a7  xor     rax, rsp
0x1800993aa  mov     [rbp+0D0h+var_50], rax
0x1800993b1  mov     edi, edx
0x1800993b3  mov     rbx, rcx
0x1800993b6  xor     r15d, r15d
0x1800993b9  mov     [rsp+1D0h+var_170], r15
0x1800993be  lea     esi, [r15+58h]
0x1800993c2  mov     r8d, esi; Size
0x1800993c5  xor     edx, edx; Val
0x1800993c7  lea     rcx, [rbp+0D0h+var_100]; void *
0x1800993cb  call    memset_0
0x1800993d0  mov     r8d, esi; Size
0x1800993d3  xor     edx, edx; Val
0x1800993d5  lea     rcx, [rsp+1D0h+var_160]; void *
0x1800993da  call    memset_0
0x1800993df  mov     [rsp+1D0h+var_168], r15d
0x1800993e4  mov     [rsp+1D0h+var_174], r15d
0x1800993e9  mov     [rsp+1D0h+var_178], r15d
0x1800993ee  cmp     [rbx+108h], r15
0x1800993f5  jz      loc_180099B49
0x1800993fb  lea     r12, [rbx+120h]
0x180099402  cmp     [r12], r15
0x180099406  jnz     loc_180099B49
0x18009940c  cmp     [rbx+0A8h], r15
0x180099413  jz      loc_180099B49
0x180099419  xor     edx, edx; Val
0x18009941b  lea     r8d, [r15+50h]; Size
0x18009941f  lea     rcx, [rbp+0D0h+var_A0]; void *
0x180099423  call    memset_0
0x180099428  mov     [rsp+1D0h+var_180], r15
0x18009942d  mov     edx, [rbx+84h]
0x180099433  mov     eax, edx
0x180099435  and     eax, 2000h
0x18009943a  neg     eax
0x18009943c  sbb     si, si
0x18009943f  and     si, 3
0x180099443  movzx   ecx, byte ptr [rbx+60h]
0x180099447  and     ecx, 4
0x18009944a  jz      short loc_180099452
0x18009944c  mov     rax, [rbx+58h]
0x180099450  jmp     short loc_180099455
0x180099452  mov     rax, r15
0x180099455  mov     [rbp+0D0h+var_A0], rax
0x180099459  mov     [rbp+0D0h+var_98], r15
0x18009945d  mov     rax, [rbx+68h]
0x180099461  mov     [rbp+0D0h+var_90], rax
0x180099465  mov     [rbp+0D0h+var_88], edx
0x180099468  mov     rax, [rbx+78h]
0x18009946c  mov     [rbp+0D0h+var_80], rax
0x180099470  movzx   eax, word ptr [rbx+70h]
0x180099474  mov     [rbp+0D0h+var_78], ax
0x180099478  mov     al, [rbx+80h]
0x18009947e  mov     [rbp+0D0h+var_76], al
0x180099481  mov     al, [rbx+81h]
0x180099487  mov     [rbp+0D0h+var_75], al
0x18009948a  mov     [rbp+0D0h+var_60], 2
0x180099491  test    ecx, ecx
0x180099493  jz      short loc_18009949B
0x180099495  mov     rax, [rbx+58h]
0x180099499  jmp     short loc_18009949E
0x18009949b  mov     rax, r15
0x18009949e  mov     [rbp+0D0h+var_58], rax
0x1800994a2  lea     rdx, [rsp+1D0h+var_180]; struct IRowset **
0x1800994a7  mov     rcx, rbx; this
0x1800994aa  call    ?GetIRowset@CRsetField@@QEAAJPEAPEAUIRowset@@@Z; CRsetField::GetIRowset(IRowset * *)
0x1800994af  mov     edi, eax
0x1800994b1  test    eax, eax
0x1800994b3  jns     short loc_180099533
0x1800994b5  test    byte ptr cs:_bidGblFlags, 2
0x1800994bc  jz      loc_1800999B6
0x1800994c2  lea     rcx, [rbx+138h]; this
0x1800994c9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800994ce  cmp     eax, 0FFFFFFFFh
0x1800994d1  jz      short loc_18009950B
0x1800994d3  lea     rcx, [rbx+138h]; this
0x1800994da  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800994df  mov     dword ptr [rsp+1D0h+var_1A8], 54Eh
0x1800994e7  mov     edx, 153809h
0x1800994ec  lea     r8, aCrsetfieldSetu; "<CRsetField::SetupDataAccessor|ADO|ERR>"...
0x1800994f3  mov     r9d, eax
0x1800994f6  mov     dword ptr [rsp+1D0h+var_1B0], edi
0x1800994fa  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180099501  call    _bidTraceW
0x180099506  jmp     loc_1800999B6
0x18009950b  mov     dword ptr [rsp+1D0h+var_1B0], 54Eh
0x180099513  mov     edx, 153809h
0x180099518  lea     r8, aCrsetfieldSetu_5; "<CRsetField::SetupDataAccessor|ADO|ERR>"...
0x18009951f  mov     r9d, edi
0x180099522  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180099529  call    _bidTraceW
0x18009952e  jmp     loc_1800999B6
0x180099533  mov     rcx, [rbx+108h]
0x18009953a  lea     r14, [rbx+114h]
0x180099541  mov     rax, [rcx]
0x180099544  mov     [rsp+1D0h+var_198], r14
0x180099549  lea     rdx, [rsp+1D0h+var_178]
0x18009954e  mov     [rsp+1D0h+var_1A0], rdx
0x180099553  lea     rdx, [rsp+1D0h+var_160]
0x180099558  mov     [rsp+1D0h+var_1A8], rdx
0x18009955d  lea     rdx, [rbp+0D0h+var_A0]
0x180099561  mov     [rsp+1D0h+var_1B0], rdx
0x180099566  mov     r9, [rsp+1D0h+var_180]
0x18009956b  xor     r8d, r8d
0x18009956e  movzx   edx, si
0x180099571  mov     rax, [rax+18h]
0x180099575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009957a  mov     edi, eax
0x18009957c  test    eax, eax
0x18009957e  jns     short loc_1800995CE
0x180099580  test    byte ptr cs:_bidGblFlags, 2
0x180099587  jz      loc_1800999B6
0x18009958d  lea     rcx, [rbx+138h]; this
0x180099594  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180099599  cmp     eax, 0FFFFFFFFh
0x18009959c  jz      short loc_1800995BC
0x18009959e  lea     rcx, [rbx+138h]; this
0x1800995a5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800995aa  mov     dword ptr [rsp+1D0h+var_1A8], 557h
0x1800995b2  mov     edx, 155C09h
0x1800995b7  jmp     loc_1800994EC
0x1800995bc  mov     dword ptr [rsp+1D0h+var_1B0], 557h
0x1800995c4  mov     edx, 155C09h
0x1800995c9  jmp     loc_180099518
0x1800995ce  mov     rcx, [rbx+108h]
0x1800995d5  lea     r13, [rbx+110h]
0x1800995dc  mov     rax, [rcx]
0x1800995df  mov     [rsp+1D0h+var_198], r13
0x1800995e4  lea     rdx, [rsp+1D0h+var_174]
0x1800995e9  mov     [rsp+1D0h+var_1A0], rdx
0x1800995ee  lea     rdx, [rbp+0D0h+var_100]
0x1800995f2  mov     [rsp+1D0h+var_1A8], rdx
0x1800995f7  lea     rdx, [rbp+0D0h+var_A0]
0x1800995fb  mov     [rsp+1D0h+var_1B0], rdx
0x180099600  mov     r9, [rsp+1D0h+var_180]
0x180099605  xor     r8d, r8d
0x180099608  movzx   edx, si
0x18009960b  mov     rax, [rax+18h]
0x18009960f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099614  mov     edi, eax
0x180099616  test    eax, eax
0x180099618  jns     loc_18009969F
0x18009961e  test    byte ptr cs:_bidGblFlags, 2
0x180099625  jz      short loc_180099690
0x180099627  lea     rsi, [rbx+138h]
0x18009962e  mov     rcx, rsi; this
0x180099631  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180099636  cmp     eax, 0FFFFFFFFh
0x180099639  jz      short loc_18009966C
0x18009963b  mov     rcx, rsi; this
0x18009963e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180099643  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009964a  mov     dword ptr [rsp+1D0h+var_1A8], 55Fh
0x180099652  mov     dword ptr [rsp+1D0h+var_1B0], edi
0x180099656  mov     r9d, eax
0x180099659  lea     r8, aCrsetfieldSetu; "<CRsetField::SetupDataAccessor|ADO|ERR>"...
0x180099660  mov     edx, 157C09h
0x180099665  call    _bidTraceW
0x18009966a  jmp     short loc_180099690
0x18009966c  mov     dword ptr [rsp+1D0h+var_1B0], 55Fh
0x180099674  mov     r9d, edi
0x180099677  lea     r8, aCrsetfieldSetu_5; "<CRsetField::SetupDataAccessor|ADO|ERR>"...
0x18009967e  mov     edx, 157C09h
0x180099683  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009968a  call    _bidTraceW
0x18009968f  nop
0x180099690  lea     rcx, [rsp+1D0h+var_180]
0x180099695  call    ??1?$CComPtr@UIDBCreateSession@@@ATL@@QEAA@XZ; ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(void)
0x18009969a  jmp     loc_180099B2E
0x18009969f  cmp     [rsp+1D0h+var_178], r15d
0x1800996a4  jbe     loc_180099A92
0x1800996aa  cmp     [rsp+1D0h+var_174], r15d
0x1800996af  jbe     loc_180099A92
0x1800996b5  mov     rcx, [rsp+1D0h+var_180]
0x1800996ba  mov     rax, [rcx]
0x1800996bd  lea     r8, [rsp+1D0h+var_170]
0x1800996c2  lea     rdx, IID_IAccessor
0x1800996c9  mov     rax, [rax]
0x1800996cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800996d1  mov     edi, eax
0x1800996d3  test    eax, eax
0x1800996d5  jns     short loc_180099724
0x1800996d7  test    byte ptr cs:_bidGblFlags, 2
0x1800996de  jz      loc_180099B09
0x1800996e4  lea     rsi, [rbx+138h]
0x1800996eb  mov     rcx, rsi; this
0x1800996ee  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800996f3  cmp     eax, 0FFFFFFFFh
0x1800996f6  jz      short loc_180099712
0x1800996f8  mov     rcx, rsi; this
0x1800996fb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180099700  mov     dword ptr [rsp+1D0h+var_1A8], 568h
0x180099708  mov     edx, 15A009h
0x18009970d  jmp     loc_180099AC9
0x180099712  mov     dword ptr [rsp+1D0h+var_1B0], 568h
0x18009971a  mov     edx, 15A009h
0x18009971f  jmp     loc_180099AF2
0x180099724  mov     rcx, [rsp+1D0h+var_170]
0x180099729  mov     rax, [rcx]
0x18009972c  lea     rdx, [rsp+1D0h+var_168]
0x180099731  mov     [rsp+1D0h+var_1A0], rdx
0x180099736  mov     [rsp+1D0h+var_1A8], r12
0x18009973b  mov     [rsp+1D0h+var_1B0], r15
0x180099740  lea     r9, [rsp+1D0h+var_160]
0x180099745  mov     r8d, 1
0x18009974b  lea     r14d, [r8+1]
0x18009974f  mov     edx, r14d
0x180099752  mov     rax, [rax+20h]
0x180099756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009975b  mov     edi, eax
0x18009975d  test    eax, eax
0x18009975f  jns     short loc_1800997DF
0x180099761  test    byte ptr cs:_bidGblFlags, r14b
0x180099768  jz      short loc_1800997D3
0x18009976a  lea     rsi, [rbx+138h]
0x180099771  mov     rcx, rsi; this
0x180099774  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180099779  cmp     eax, 0FFFFFFFFh
0x18009977c  jz      short loc_1800997AF
0x18009977e  mov     rcx, rsi; this
0x180099781  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180099786  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009978d  mov     dword ptr [rsp+1D0h+var_1A8], 56Bh
0x180099795  mov     dword ptr [rsp+1D0h+var_1B0], edi
0x180099799  mov     r9d, eax
0x18009979c  lea     r8, aCrsetfieldSetu; "<CRsetField::SetupDataAccessor|ADO|ERR>"...
0x1800997a3  mov     edx, 15AC09h
0x1800997a8  call    _bidTraceW
0x1800997ad  jmp     short loc_1800997D3
0x1800997af  mov     dword ptr [rsp+1D0h+var_1B0], 56Bh
0x1800997b7  mov     r9d, edi
0x1800997ba  lea     r8, aCrsetfieldSetu_5; "<CRsetField::SetupDataAccessor|ADO|ERR>"...
0x1800997c1  mov     edx, 15AC09h
0x1800997c6  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800997cd  call    _bidTraceW
0x1800997d2  nop
0x1800997d3  lea     rsi, [rbx+118h]
0x1800997da  jmp     loc_180099A2B
0x1800997df  lea     rsi, [rbx+118h]
0x1800997e6  mov     rcx, [rsp+1D0h+var_170]
0x1800997eb  mov     rax, [rcx]
0x1800997ee  lea     rdx, [rsp+1D0h+var_168]
0x1800997f3  mov     [rsp+1D0h+var_1A0], rdx
0x1800997f8  mov     [rsp+1D0h+var_1A8], rsi
0x1800997fd  mov     [rsp+1D0h+var_1B0], r15
0x180099802  lea     r9, [rbp+0D0h+var_100]
0x180099806  mov     r8d, 1
0x18009980c  mov     edx, r14d
0x18009980f  mov     rax, [rax+20h]
0x180099813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099818  mov     edi, eax
0x18009981a  test    eax, eax
0x18009981c  jns     short loc_18009989B
0x18009981e  test    byte ptr cs:_bidGblFlags, r14b
0x180099825  jz      loc_180099A2B
0x18009982b  lea     r14, [rbx+138h]
0x180099832  mov     rcx, r14; this
0x180099835  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009983a  cmp     eax, 0FFFFFFFFh
0x18009983d  jz      short loc_180099873
0x18009983f  mov     rcx, r14; this
0x180099842  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180099847  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009984e  mov     dword ptr [rsp+1D0h+var_1A8], 56Eh
0x180099856  mov     dword ptr [rsp+1D0h+var_1B0], edi
0x18009985a  mov     r9d, eax
0x18009985d  lea     r8, aCrsetfieldSetu; "<CRsetField::SetupDataAccessor|ADO|ERR>"...
0x180099864  mov     edx, 15B809h
0x180099869  call    _bidTraceW
0x18009986e  jmp     loc_180099A2B
0x180099873  mov     dword ptr [rsp+1D0h+var_1B0], 56Eh
0x18009987b  mov     r9d, edi
0x18009987e  lea     r8, aCrsetfieldSetu_5; "<CRsetField::SetupDataAccessor|ADO|ERR>"...
0x180099885  mov     edx, 15B809h
0x18009988a  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180099891  call    _bidTraceW
0x180099896  jmp     loc_180099A2B
0x18009989b  mov     rcx, [rbx+130h]; void *
0x1800998a2  test    rcx, rcx
0x1800998a5  jz      short loc_1800998AC
0x1800998a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800998ac  mov     r8d, [rsp+1D0h+var_178]
0x1800998b1  mov     edi, 0A00000h
0x1800998b6  mov     edx, edi
0x1800998b8  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800998bf  call    cs:__imp_MpHeapAlloc
0x1800998c6  nop     dword ptr [rax+rax+00h]
0x1800998cb  mov     [rbx+130h], rax
0x1800998d2  test    rax, rax
0x1800998d5  jnz     short loc_180099948
  ... truncated ...
```
