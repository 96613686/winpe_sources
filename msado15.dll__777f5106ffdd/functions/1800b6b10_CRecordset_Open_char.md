# CRecordset::_Open(char)

- ea: `0x1800b6b10`
- end: `0x1800b74a2`
- name: `?_Open@CRecordset@@UEAAJD@Z`
- size: `2450`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, char)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002840`
- `0x180009240`
- `0x18000fcc0`
- `0x18001a820`
- `0x180020e20`
- `0x180027790`
- `0x18002a580`
- `0x180042a04`
- `0x18004f370`
- `0x1800538e8`
- `0x180056dfc`
- `0x18005a16c`
- `0x18005b790`
- `0x18006a22c`
- `0x1800ad30c`
- `0x1800b6b10`
- `0x1800c8f34`
- `0x1800cb51c`
- `0x1800d0010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800b6d46`
- `ole32!CoCreateInstance` at `0x1800b6d46`

## string_xrefs

- `0x1800b6bb9`: `<CRecordset::_Open|ADO|ERR> %u#, line %d\n`
- `0x1800b6ec9`: `<CRecordset::_Open|ADO|ERR> %u#, line %d\n`
- `0x1800b6eec`: `<CRecordset::_Open|ADO|ERR>  line %d\n`
- `0x1800b7464`: `<CRecordset::_Open|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CRecordset::_Open(CRecordset *this, char a2)
{
  bool v4; // zf
  unsigned int BidObjectID; // eax
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rdx
  char v10; // si
  int v11; // eax
  wchar_t *v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned int v18; // edx
  _QWORD *v19; // rcx
  __int64 *v20; // r8
  struct _ADOConnection *v21; // rcx
  __int64 v22; // rcx
  struct _ADOCommand *v23; // rcx
  __int64 v24; // r8
  char v25; // dl
  __int64 v26; // rcx
  __int64 v27; // rax
  int v28; // edi
  unsigned int v29; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-99h]
  int v32; // [rsp+28h] [rbp-91h]
  int v33; // [rsp+30h] [rbp-89h]
  unsigned int v34; // [rsp+38h] [rbp-81h]
  int v35; // [rsp+40h] [rbp-79h]
  __int64 v36; // [rsp+80h] [rbp-39h] BYREF
  __int64 v37; // [rsp+88h] [rbp-31h] BYREF
  struct _ADOCommand *v38; // [rsp+90h] [rbp-29h] BYREF
  __int64 v39; // [rsp+98h] [rbp-21h] BYREF
  char v40; // [rsp+A0h] [rbp-19h]
  _BYTE v41[32]; // [rsp+A8h] [rbp-11h] BYREF
  unsigned __int64 v42; // [rsp+C8h] [rbp+Fh]
  int v43; // [rsp+D0h] [rbp+17h]
  unsigned int v44; // [rsp+120h] [rbp+67h] BYREF
  int v45; // [rsp+130h] [rbp+77h] BYREF
  LPVOID v46; // [rsp+138h] [rbp+7Fh] BYREF

  v42 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  CContext::Init((CContext *)v41);
  v44 = *((_DWORD *)this + 363);
  v4 = *((_DWORD *)this + 315) == 0;
  v37 = 0;
  v36 = 0;
  v38 = 0;
  if ( !(unsigned int)CContext::FailIfOpen((CContext *)v41, v4) )
  {
    v9 = *((_QWORD *)this + 139);
    v10 = 16;
    if ( a2 != 1 )
      v10 = a2;
    if ( v9 )
    {
      v45 = CRecordset::SetRowset(this, v9, 0);
      if ( (unsigned int)CContext::Failed((CContext *)v41, &v45) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_110;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v6 = 7830537;
          LODWORD(ppv) = 7647;
          goto LABEL_5;
        }
        v7 = 7647;
        v8 = 7830537;
LABEL_109:
        bidTraceW(off_18012A208[0], v8, L"<CRecordset::_Open|ADO|ERR>  line %d\n", v7);
        goto LABEL_110;
      }
      v11 = CRecordset::Reconnect(this);
LABEL_16:
      v45 = v11;
      CContext::Failed((CContext *)v41, &v45);
      goto LABEL_110;
    }
    if ( !*((_QWORD *)this + 177) )
    {
      v12 = (*((_BYTE *)this + 1288) & 4) != 0 ? (wchar_t *)*((_QWORD *)this + 160) : 0LL;
      if ( (unsigned int)ContainsURL(v12, 0) )
      {
        v46 = 0;
        CSysString::CSysString((CSysString *)&v39, (CRecordset *)((char *)this + 1264));
        if ( (unsigned int)CContext::StringFailed((CContext *)v41, (const struct CSysString *)&v39) )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
            {
              v13 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              v14 = 7844873;
              LODWORD(ppv) = 7661;
LABEL_41:
              bidTraceW(off_18012A208[0], v14, L"<CRecordset::_Open|ADO|ERR> %u#, line %d\n", v13, ppv);
              goto LABEL_44;
            }
            v15 = 7661;
            v16 = 7844873;
            goto LABEL_43;
          }
          goto LABEL_44;
        }
        v45 = CoCreateInstance(&CLSID_CADOConnection, 0, 3u, &IID_IADOConnection, &v46);
        if ( (unsigned int)CContext::Failed((CContext *)v41, &v45) )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
            {
              v13 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              v14 = 7852041;
              LODWORD(ppv) = 7668;
              goto LABEL_41;
            }
            v15 = 7668;
            v16 = 7852041;
LABEL_43:
            bidTraceW(off_18012A208[0], v16, L"<CRecordset::_Open|ADO|ERR>  line %d\n", v15);
          }
LABEL_44:
          CSysString::~CSysString((CSysString *)&v39);
          goto LABEL_110;
        }
        v45 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v46 + 160LL))(
                v46,
                v39 & -(__int64)((v40 & 4) != 0),
                0,
                0,
                -1);
        CContext::Failed((CContext *)v41, &v45);
        if ( v43 < 0 )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v46 + 16LL))(v46);
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
            {
              v13 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              v14 = 7859209;
              LODWORD(ppv) = 7675;
              goto LABEL_41;
            }
            v15 = 7675;
            v16 = 7859209;
            goto LABEL_43;
          }
          goto LABEL_44;
        }
        v45 = (*(__int64 (__fastcall **)(CRecordset *, LPVOID, __int64))(*(_QWORD *)this + 696LL))(this, v46, 1);
        CContext::Failed((CContext *)v41, &v45);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v46 + 16LL))(v46);
        if ( v43 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
            {
              v13 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              v14 = 7865353;
              LODWORD(ppv) = 7681;
              goto LABEL_41;
            }
            v15 = 7681;
            v16 = 7865353;
            goto LABEL_43;
          }
          goto LABEL_44;
        }
        CSysString::~CSysString((CSysString *)&v39);
      }
    }
    if ( *((_DWORD *)this + 363) == 256
      || !*((_QWORD *)this + 178)
      && !*((_QWORD *)this + 177)
      && !CStdCollection::GetCount((CRecordset *)((char *)this + 1584)) )
    {
      v45 = CRecordset::Load(this, v10);
      v28 = v45;
      if ( v45 < 0 )
      {
        if ( *((_DWORD *)this + 363) == 256 || *((_QWORD *)this + 140) )
        {
          CContext::Failed((CContext *)v41, &v45);
        }
        else
        {
          CContext::ClearCachedError((CContext *)v41);
          v45 = -2146824579;
          CContext::FailedPushWarning((CContext *)v41, &v45);
        }
      }
      if ( *((_DWORD *)this + 363) == 256 && *((_DWORD *)this + 343) == 2 )
        *((_DWORD *)this + 343) = 3;
      if ( v28 >= 0 )
      {
        v45 = CRecordset::Reconnect(this);
        CContext::Failed((CContext *)v41, &v45);
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v6 = 7902217;
          LODWORD(ppv) = 7717;
          goto LABEL_5;
        }
        v7 = 7717;
        v8 = 7902217;
        goto LABEL_109;
      }
      goto LABEL_110;
    }
    v17 = *((_QWORD *)this + 178);
    if ( v17 )
    {
      v18 = v44;
      if ( v44 != -1 )
        goto LABEL_58;
      v45 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 168LL))(v17, &v44);
      if ( (unsigned int)CContext::Failed((CContext *)v41, &v45) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_110;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v6 = 7907337;
          LODWORD(ppv) = 7722;
          goto LABEL_5;
        }
        v7 = 7722;
        v8 = 7907337;
        goto LABEL_109;
      }
    }
    v18 = v44;
    if ( v44 == -1 )
    {
LABEL_59:
      v19 = (_QWORD *)*((_QWORD *)this + 178);
      if ( v19 && v19 + 4 != (_QWORD *)v19[8] && v19[8] )
      {
        v20 = &v37;
        LOBYTE(v20) = v10;
        LOBYTE(ppv) = *((_BYTE *)this + 1457);
        v45 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *, _QWORD, _DWORD, _DWORD, _DWORD, unsigned int, _DWORD, _QWORD, _QWORD, CRecordset *, __int64 *, __int64 *))(*v19 + 288LL))(
                v19,
                3,
                v20,
                0,
                (_DWORD)ppv,
                *((_DWORD *)this + 362),
                *((_DWORD *)this + 343),
                v18,
                *((_DWORD *)this + 360),
                0,
                0,
                this,
                &v37,
                &v36);
        if ( (unsigned int)CContext::Failed((CContext *)v41, &v45) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_110;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            v6 = 7930889;
            LODWORD(ppv) = 7745;
            goto LABEL_5;
          }
          v7 = 7745;
          v8 = 7930889;
          goto LABEL_109;
        }
        goto LABEL_88;
      }
LABEL_67:
      if ( v18 == -1 || (v18 & 0x200) == 0 )
      {
        v21 = (struct _ADOConnection *)*((_QWORD *)this + 177);
        if ( v21 )
        {
          v45 = CreateCommand(v21, (CRecordset *)((char *)this + 1264), 0, &v38);
          if ( !(unsigned int)CContext::Failed((CContext *)v41, &v45) )
          {
            v22 = *((_QWORD *)this + 178);
            if ( v22 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            v23 = v38;
            v24 = v44;
            v35 = *((_DWORD *)this + 360);
            v34 = v44;
            LOBYTE(v24) = v10;
            v33 = *((_DWORD *)this + 343);
            v32 = *((_DWORD *)this + 362);
            v25 = *((_BYTE *)this + 1457);
            *((_QWORD *)this + 178) = v38;
            *((_BYTE *)this + 1432) = 1;
            LOBYTE(ppv) = v25;
            v45 = (*(__int64 (__fastcall **)(struct _ADOCommand *, __int64, __int64, _QWORD, _DWORD, int, int, unsigned int, int, _QWORD, _QWORD, CRecordset *, __int64 *, __int64 *))(*(_QWORD *)v23 + 288LL))(
                    v23,
                    3,
                    v24,
                    0,
                    (_DWORD)ppv,
                    v32,
                    v33,
                    v34,
                    v35,
                    0,
                    0,
                    this,
                    &v37,
                    &v36);
            if ( (unsigned int)CContext::Failed((CContext *)v41, &v45) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_110;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
              {
                BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                v6 = 7957513;
                LODWORD(ppv) = 7771;
                goto LABEL_5;
              }
              v7 = 7771;
              v8 = 7957513;
              goto LABEL_109;
            }
            goto LABEL_88;
          }
          v18 = v44;
        }
      }
      v26 = *((_QWORD *)this + 177);
      if ( !v26 )
      {
        if ( !CStdCollection::GetCount((CRecordset *)((char *)this + 1584)) )
        {
          v45 = -2146824579;
          CContext::FailedPushWarning((CContext *)v41, &v45);
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_110;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            v6 = 7990281;
            LODWORD(ppv) = 7803;
            goto LABEL_5;
          }
          v7 = 7803;
          v8 = 7990281;
          goto LABEL_109;
        }
        v11 = (*(__int64 (__fastcall **)(CRecordset *))(*(_QWORD *)this + 784LL))(this);
        goto LABEL_16;
      }
      if ( (*((_BYTE *)this + 1272) & 4) != 0 )
        v27 = *((_QWORD *)this + 158);
      else
        v27 = 0;
      v45 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, _DWORD, unsigned int, char, _BYTE, _DWORD, CRecordset *, __int64 *, __int64 *))(*(_QWORD *)v26 + 368LL))(
              v26,
              v27,
              3,
              *((unsigned int *)this + 362),
              *((_DWORD *)this + 343),
              v18,
              v10,
              0,
              *((_DWORD *)this + 360),
              this,
              &v37,
              &v36);
      if ( (unsigned int)CContext::Failed((CContext *)v41, &v45) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_110;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v6 = 7975945;
          LODWORD(ppv) = 7789;
          goto LABEL_5;
        }
        v7 = 7789;
        v8 = 7975945;
        goto LABEL_109;
      }
LABEL_88:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      goto LABEL_110;
    }
LABEL_58:
    if ( (v18 & 0x200) != 0 )
      goto LABEL_67;
    goto LABEL_59;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      v6 = 7817225;
      LODWORD(ppv) = 7634;
LABEL_5:
      bidTraceW(off_18012A208[0], v6, L"<CRecordset::_Open|ADO|ERR> %u#, line %d\n", BidObjectID, ppv);
      goto LABEL_110;
    }
    v7 = 7634;
    v8 = 7817225;
    goto LABEL_109;
  }
LABEL_110:
  *((_DWORD *)this + 451) = 1;
  *((_DWORD *)this + 417) = 1;
  v29 = v43;
  CContext::~CContext((CContext *)v41);
  return v29;
}

```

## disassembly

```asm
0x1800b6b10  push    rbp
0x1800b6b12  push    rbx
0x1800b6b13  push    rsi
0x1800b6b14  push    rdi
0x1800b6b15  push    r13
0x1800b6b17  push    r14
0x1800b6b19  push    r15
0x1800b6b1b  lea     rbp, [rsp-27h]
0x1800b6b20  sub     rsp, 0E0h
0x1800b6b27  mov     rax, rcx
0x1800b6b2a  movzx   edi, dl
0x1800b6b2d  lea     r9, [rcx+20h]
0x1800b6b31  neg     rax
0x1800b6b34  mov     rbx, rcx
0x1800b6b37  lea     rcx, [rbp+57h+var_68]; this
0x1800b6b3b  sbb     r8, r8
0x1800b6b3e  and     r8, r9
0x1800b6b41  mov     [rbp+57h+var_48], r8
0x1800b6b45  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x1800b6b4a  mov     eax, [rbx+5ACh]
0x1800b6b50  lea     rcx, [rbp+57h+var_68]; this
0x1800b6b54  xor     r14d, r14d
0x1800b6b57  mov     [rbp+57h+arg_0], eax
0x1800b6b5a  cmp     [rbx+4ECh], r14d
0x1800b6b61  mov     edx, r14d
0x1800b6b64  mov     [rbp+57h+var_88], r14
0x1800b6b68  setz    dl; int
0x1800b6b6b  mov     [rbp+57h+var_90], r14
0x1800b6b6f  mov     [rbp+57h+var_80], r14
0x1800b6b73  call    ?FailIfOpen@CContext@@QEAAHH@Z; CContext::FailIfOpen(int)
0x1800b6b78  test    eax, eax
0x1800b6b7a  jz      short loc_1800B6BDD
0x1800b6b7c  test    byte ptr cs:_bidGblFlags, 2
0x1800b6b83  jz      loc_1800B7470
0x1800b6b89  lea     rdi, [rbx+618h]
0x1800b6b90  mov     rcx, rdi; this
0x1800b6b93  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6b98  cmp     eax, 0FFFFFFFFh
0x1800b6b9b  jz      short loc_1800B6BCD
0x1800b6b9d  mov     rcx, rdi; this
0x1800b6ba0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6ba5  mov     edx, 774809h
0x1800b6baa  mov     dword ptr [rsp+110h+ppv], 1DD2h
0x1800b6bb2  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b6bb9  lea     r8, aCrecordsetOpen_3; "<CRecordset::_Open|ADO|ERR> %u#, line %"...
0x1800b6bc0  mov     r9d, eax
0x1800b6bc3  call    _bidTraceW
0x1800b6bc8  jmp     loc_1800B7470
0x1800b6bcd  mov     r9d, 1DD2h
0x1800b6bd3  mov     edx, 774809h
0x1800b6bd8  jmp     loc_1800B745D
0x1800b6bdd  mov     rdx, [rbx+458h]
0x1800b6be4  cmp     dil, 1
0x1800b6be8  mov     esi, 10h
0x1800b6bed  cmovnz  esi, edi
0x1800b6bf0  test    rdx, rdx
0x1800b6bf3  jz      loc_1800B6C80
0x1800b6bf9  xor     r8d, r8d
0x1800b6bfc  mov     rcx, rbx
0x1800b6bff  call    ?SetRowset@CRecordset@@QEAAJPEAUIUnknown@@W4PointerFormat@@@Z; CRecordset::SetRowset(IUnknown *,PointerFormat)
0x1800b6c04  lea     rdx, [rbp+57h+arg_10]; int *
0x1800b6c08  mov     [rbp+57h+arg_10], eax
0x1800b6c0b  lea     rcx, [rbp+57h+var_68]; this
0x1800b6c0f  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b6c14  test    eax, eax
0x1800b6c16  jz      short loc_1800B6C63
0x1800b6c18  test    byte ptr cs:_bidGblFlags, 2
0x1800b6c1f  jz      loc_1800B7470
0x1800b6c25  lea     rdi, [rbx+618h]
0x1800b6c2c  mov     rcx, rdi; this
0x1800b6c2f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6c34  cmp     eax, 0FFFFFFFFh
0x1800b6c37  jz      short loc_1800B6C53
0x1800b6c39  mov     rcx, rdi; this
0x1800b6c3c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6c41  mov     edx, 777C09h
0x1800b6c46  mov     dword ptr [rsp+110h+ppv], 1DDFh
0x1800b6c4e  jmp     loc_1800B6BB2
0x1800b6c53  mov     r9d, 1DDFh
0x1800b6c59  mov     edx, 777C09h
0x1800b6c5e  jmp     loc_1800B745D
0x1800b6c63  mov     rcx, rbx; this
0x1800b6c66  call    ?Reconnect@CRecordset@@QEAAJXZ; CRecordset::Reconnect(void)
0x1800b6c6b  lea     rdx, [rbp+57h+arg_10]; int *
0x1800b6c6f  mov     [rbp+57h+arg_10], eax
0x1800b6c72  lea     rcx, [rbp+57h+var_68]; this
0x1800b6c76  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b6c7b  jmp     loc_1800B7470
0x1800b6c80  or      edi, 0FFFFFFFFh
0x1800b6c83  mov     r13d, 3
0x1800b6c89  cmp     [rbx+588h], r14
0x1800b6c90  jnz     loc_1800B6F0F
0x1800b6c96  test    byte ptr [rbx+508h], 4
0x1800b6c9d  jz      short loc_1800B6CA8
0x1800b6c9f  mov     rcx, [rbx+500h]
0x1800b6ca6  jmp     short loc_1800B6CAB
0x1800b6ca8  mov     rcx, r14; String1
0x1800b6cab  xor     edx, edx; unsigned int *
0x1800b6cad  call    ?ContainsURL@@YAHPEBGPEAK@Z; ContainsURL(ushort const *,ulong *)
0x1800b6cb2  test    eax, eax
0x1800b6cb4  jz      loc_1800B6F0F
0x1800b6cba  lea     rdx, [rbx+4F0h]; struct CSysString *
0x1800b6cc1  mov     [rbp+57h+arg_18], r14
0x1800b6cc5  lea     rcx, [rbp+57h+var_78]; this
0x1800b6cc9  call    ??0CSysString@@QEAA@AEBV0@@Z; CSysString::CSysString(CSysString const &)
0x1800b6cce  lea     rdx, [rbp+57h+var_78]; struct CSysString *
0x1800b6cd2  lea     rcx, [rbp+57h+var_68]; this
0x1800b6cd6  call    ?StringFailed@CContext@@QEAAHAEBVCSysString@@@Z; CContext::StringFailed(CSysString const &)
0x1800b6cdb  test    eax, eax
0x1800b6cdd  jz      short loc_1800B6D2A
0x1800b6cdf  test    byte ptr cs:_bidGblFlags, 2
0x1800b6ce6  jz      loc_1800B6EF8
0x1800b6cec  lea     rdi, [rbx+618h]
0x1800b6cf3  mov     rcx, rdi; this
0x1800b6cf6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6cfb  cmp     eax, 0FFFFFFFFh
0x1800b6cfe  jz      short loc_1800B6D1A
0x1800b6d00  mov     rcx, rdi; this
0x1800b6d03  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6d08  mov     edx, 77B409h
0x1800b6d0d  mov     dword ptr [rsp+110h+ppv], 1DEDh
0x1800b6d15  jmp     loc_1800B6EC2
0x1800b6d1a  mov     r9d, 1DEDh
0x1800b6d20  mov     edx, 77B409h
0x1800b6d25  jmp     loc_1800B6EE5
0x1800b6d2a  lea     rax, [rbp+57h+arg_18]
0x1800b6d2e  mov     r8d, r13d; dwClsContext
0x1800b6d31  lea     r9, IID_IADOConnection; riid
0x1800b6d38  mov     [rsp+110h+ppv], rax; ppv
0x1800b6d3d  xor     edx, edx; pUnkOuter
0x1800b6d3f  lea     rcx, CLSID_CADOConnection; rclsid
0x1800b6d46  call    cs:__imp_CoCreateInstance
0x1800b6d4d  nop     dword ptr [rax+rax+00h]
0x1800b6d52  lea     rdx, [rbp+57h+arg_10]; int *
0x1800b6d56  mov     [rbp+57h+arg_10], eax
0x1800b6d59  lea     rcx, [rbp+57h+var_68]; this
0x1800b6d5d  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b6d62  test    eax, eax
0x1800b6d64  jz      short loc_1800B6DB1
0x1800b6d66  test    byte ptr cs:_bidGblFlags, 2
0x1800b6d6d  jz      loc_1800B6EF8
0x1800b6d73  lea     rdi, [rbx+618h]
0x1800b6d7a  mov     rcx, rdi; this
0x1800b6d7d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6d82  cmp     eax, 0FFFFFFFFh
0x1800b6d85  jz      short loc_1800B6DA1
0x1800b6d87  mov     rcx, rdi; this
0x1800b6d8a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6d8f  mov     edx, 77D009h
0x1800b6d94  mov     dword ptr [rsp+110h+ppv], 1DF4h
0x1800b6d9c  jmp     loc_1800B6EC2
0x1800b6da1  mov     r9d, 1DF4h
0x1800b6da7  mov     edx, 77D009h
0x1800b6dac  jmp     loc_1800B6EE5
0x1800b6db1  mov     rcx, [rbp+57h+arg_18]
0x1800b6db5  mov     dl, [rbp+57h+var_70]
0x1800b6db8  and     dl, 4
0x1800b6dbb  mov     dword ptr [rsp+110h+ppv], edi
0x1800b6dbf  neg     dl
0x1800b6dc1  mov     rax, [rcx]
0x1800b6dc4  sbb     rdx, rdx
0x1800b6dc7  xor     r9d, r9d
0x1800b6dca  and     rdx, [rbp+57h+var_78]
0x1800b6dce  xor     r8d, r8d
0x1800b6dd1  mov     rax, [rax+0A0h]
0x1800b6dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6ddd  lea     rdx, [rbp+57h+arg_10]; int *
0x1800b6de1  mov     [rbp+57h+arg_10], eax
0x1800b6de4  lea     rcx, [rbp+57h+var_68]; this
0x1800b6de8  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b6ded  cmp     [rbp+57h+var_40], r14d
0x1800b6df1  jge     short loc_1800B6E4E
0x1800b6df3  mov     rcx, [rbp+57h+arg_18]
0x1800b6df7  mov     rax, [rcx]
0x1800b6dfa  mov     rax, [rax+10h]
0x1800b6dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6e03  test    byte ptr cs:_bidGblFlags, 2
0x1800b6e0a  jz      loc_1800B6EF8
0x1800b6e10  lea     rdi, [rbx+618h]
0x1800b6e17  mov     rcx, rdi; this
0x1800b6e1a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6e1f  cmp     eax, 0FFFFFFFFh
0x1800b6e22  jz      short loc_1800B6E3E
0x1800b6e24  mov     rcx, rdi; this
0x1800b6e27  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6e2c  mov     edx, 77EC09h
0x1800b6e31  mov     dword ptr [rsp+110h+ppv], 1DFBh
0x1800b6e39  jmp     loc_1800B6EC2
0x1800b6e3e  mov     r9d, 1DFBh
0x1800b6e44  mov     edx, 77EC09h
0x1800b6e49  jmp     loc_1800B6EE5
0x1800b6e4e  mov     rax, [rbx]
0x1800b6e51  mov     r8d, 1
0x1800b6e57  mov     rdx, [rbp+57h+arg_18]
0x1800b6e5b  mov     rcx, rbx
0x1800b6e5e  mov     rax, [rax+2B8h]
0x1800b6e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6e6a  lea     rdx, [rbp+57h+arg_10]; int *
0x1800b6e6e  mov     [rbp+57h+arg_10], eax
0x1800b6e71  lea     rcx, [rbp+57h+var_68]; this
0x1800b6e75  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b6e7a  mov     rcx, [rbp+57h+arg_18]
0x1800b6e7e  mov     rax, [rcx]
0x1800b6e81  mov     rax, [rax+10h]
0x1800b6e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6e8a  cmp     [rbp+57h+var_40], r14d
0x1800b6e8e  jge     short loc_1800B6F06
0x1800b6e90  test    byte ptr cs:_bidGblFlags, 2
0x1800b6e97  jz      short loc_1800B6EF8
0x1800b6e99  lea     rdi, [rbx+618h]
0x1800b6ea0  mov     rcx, rdi; this
0x1800b6ea3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6ea8  cmp     eax, 0FFFFFFFFh
0x1800b6eab  jz      short loc_1800B6EDA
0x1800b6ead  mov     rcx, rdi; this
0x1800b6eb0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6eb5  mov     edx, 780409h
0x1800b6eba  mov     dword ptr [rsp+110h+ppv], 1E01h
0x1800b6ec2  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b6ec9  lea     r8, aCrecordsetOpen_3; "<CRecordset::_Open|ADO|ERR> %u#, line %"...
0x1800b6ed0  mov     r9d, eax
0x1800b6ed3  call    _bidTraceW
0x1800b6ed8  jmp     short loc_1800B6EF8
0x1800b6eda  mov     r9d, 1E01h
0x1800b6ee0  mov     edx, 780409h
0x1800b6ee5  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b6eec  lea     r8, aCrecordsetOpen_9; "<CRecordset::_Open|ADO|ERR>  line %d\n"
0x1800b6ef3  call    _bidTraceW
0x1800b6ef8  lea     rcx, [rbp+57h+var_78]; this
0x1800b6efc  call    ??1CSysString@@QEAA@XZ; CSysString::~CSysString(void)
0x1800b6f01  jmp     loc_1800B7470
0x1800b6f06  lea     rcx, [rbp+57h+var_78]; this
0x1800b6f0a  call    ??1CSysString@@QEAA@XZ; CSysString::~CSysString(void)
0x1800b6f0f  mov     r15d, 100h
0x1800b6f15  cmp     [rbx+5ACh], r15d
0x1800b6f1c  jz      loc_1800B7394
0x1800b6f22  cmp     [rbx+590h], r14
0x1800b6f29  jnz     short loc_1800B6F48
0x1800b6f2b  cmp     [rbx+588h], r14
0x1800b6f32  jnz     short loc_1800B6F48
0x1800b6f34  lea     rcx, [rbx+630h]; this
0x1800b6f3b  call    ?GetCount@CStdCollection@@UEAAKXZ; CStdCollection::GetCount(void)
0x1800b6f40  test    eax, eax
0x1800b6f42  jz      loc_1800B7394
0x1800b6f48  mov     rcx, [rbx+590h]
0x1800b6f4f  test    rcx, rcx
0x1800b6f52  jz      short loc_1800B6FCD
0x1800b6f54  mov     edx, [rbp+57h+arg_0]
0x1800b6f57  cmp     edx, edi
0x1800b6f59  jnz     short loc_1800B6FD4
0x1800b6f5b  mov     rax, [rcx]
0x1800b6f5e  lea     rdx, [rbp+57h+arg_0]
0x1800b6f62  mov     rax, [rax+0A8h]
0x1800b6f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6f6e  lea     rdx, [rbp+57h+arg_10]; int *
0x1800b6f72  mov     [rbp+57h+arg_10], eax
0x1800b6f75  lea     rcx, [rbp+57h+var_68]; this
0x1800b6f79  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b6f7e  test    eax, eax
0x1800b6f80  jz      short loc_1800B6FCD
0x1800b6f82  test    byte ptr cs:_bidGblFlags, 2
0x1800b6f89  jz      loc_1800B7470
0x1800b6f8f  lea     rdi, [rbx+618h]
0x1800b6f96  mov     rcx, rdi; this
0x1800b6f99  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6f9e  cmp     eax, 0FFFFFFFFh
0x1800b6fa1  jz      short loc_1800B6FBD
0x1800b6fa3  mov     rcx, rdi; this
0x1800b6fa6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b6fab  mov     edx, 78A809h
0x1800b6fb0  mov     dword ptr [rsp+110h+ppv], 1E2Ah
0x1800b6fb8  jmp     loc_1800B6BB2
0x1800b6fbd  mov     r9d, 1E2Ah
0x1800b6fc3  mov     edx, 78A809h
0x1800b6fc8  jmp     loc_1800B745D
0x1800b6fcd  mov     edx, [rbp+57h+arg_0]
0x1800b6fd0  cmp     edx, edi
0x1800b6fd2  jz      short loc_1800B6FDE
0x1800b6fd4  bt      edx, 9
0x1800b6fd8  jb      loc_1800B70D6
0x1800b6fde  mov     rcx, [rbx+590h]
0x1800b6fe5  test    rcx, rcx
0x1800b6fe8  jz      loc_1800B70D6
0x1800b6fee  lea     rax, [rcx+20h]
0x1800b6ff2  cmp     rax, [rax+20h]
0x1800b6ff6  jz      loc_1800B70D6
0x1800b6ffc  cmp     [rax+20h], r14
0x1800b7000  jz      loc_1800B70D6
0x1800b7006  mov     r9d, [rbx+5A0h]
0x1800b700d  lea     r8, [rbp+57h+var_90]
0x1800b7011  mov     rax, [rcx]
0x1800b7014  mov     [rsp+110h+var_A8], r8
0x1800b7019  lea     r8, [rbp+57h+var_88]
0x1800b701d  mov     [rsp+110h+var_B0], r8
0x1800b7022  mov     r8b, sil
0x1800b7025  mov     [rsp+110h+var_B8], rbx
0x1800b702a  mov     rax, [rax+120h]
0x1800b7031  mov     [rsp+110h+var_C0], r14
0x1800b7036  mov     [rsp+110h+var_C8], r14
0x1800b703b  mov     [rsp+110h+var_D0], r9d
  ... truncated ...
```
