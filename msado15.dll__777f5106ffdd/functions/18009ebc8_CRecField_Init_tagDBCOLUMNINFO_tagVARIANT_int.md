# CRecField::Init(tagDBCOLUMNINFO *,tagVARIANT *,int)

- ea: `0x18009ebc8`
- end: `0x18009f181`
- name: `?Init@CRecField@@QEAAJPEAUtagDBCOLUMNINFO@@PEAUtagVARIANT@@H@Z`
- size: `1465`
- prototype: `__int64 __fastcall(CRecField *__hidden this, struct tagDBCOLUMNINFO *, struct tagVARIANT *, int)`
- caller_count: `3`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x18009f2d0`
- `0x18009fb00`
- `0x1800a1f88`

## callees

- `0x180009240`
- `0x18001a820`
- `0x180020e20`
- `0x1800265d0`
- `0x180027790`
- `0x180045580`
- `0x18004f370`
- `0x18006a22c`
- `0x18009ebc8`
- `0x1800a03c0`
- `0x1800a0450`
- `0x1800a04c0`
- `0x1800c8f34`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18009ef06`
- `MSDART!MpHeapAlloc` at `0x18009ef06`
- `ole32!CoTaskMemFree` at `0x18009ef87`
- `ole32!CoTaskMemFree` at `0x18009ef87`
- `OLEAUT32!__imp_SysAllocString` at `0x18009ee78`
- `OLEAUT32!__imp_SysAllocString` at `0x18009ee78`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRecField::Init(CRecField *this, struct tagDBCOLUMNINFO *a2, struct tagVARIANT *a3, int a4)
{
  unsigned int BidObjectID; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rdx
  LPOLESTR pwszName; // rbx
  unsigned int v13; // eax
  __int64 v14; // rbx
  unsigned int v15; // eax
  GUID *v16; // rbx
  int v17; // eax
  DBTYPE wType; // ax
  unsigned int v19; // ebx
  __int64 v21; // [rsp+20h] [rbp-39h]
  OLECHAR *psz; // [rsp+30h] [rbp-29h] BYREF
  char v23; // [rsp+38h] [rbp-21h]
  __int64 v24; // [rsp+40h] [rbp-19h] BYREF
  char v25; // [rsp+48h] [rbp-11h]
  _BYTE v26[32]; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int64 v27; // [rsp+70h] [rbp+17h]
  unsigned int v28; // [rsp+78h] [rbp+1Fh]
  int v29; // [rsp+C0h] [rbp+67h] BYREF

  v27 = ((unsigned __int64)this + 8) & -(__int64)(this != 0);
  CContext::Init((CContext *)v26);
  v24 = 0;
  v25 = 7;
  psz = 0;
  v23 = 7;
  if ( a2 && (a4 & 0xFFFEFFFF) == 0 && a3 || (v29 = -2146825287, !(unsigned int)CContext::Failed((CContext *)v26, &v29)) )
  {
    if ( a2->pwszName )
    {
      CSysString::operator=(&v24, a2->pwszName);
      if ( (v25 & 4) != 0 )
      {
        CSysString::operator=((char *)this + 104, &v24);
        if ( (unsigned int)CContext::StringFailed((CContext *)v26, (CRecField *)((char *)this + 104)) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_69;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
            LODWORD(v21) = 748;
            v9 = 765961;
            goto LABEL_8;
          }
          v10 = 748;
          v11 = 765961;
          goto LABEL_10;
        }
        if ( (bidGblFlags & 2) != 0 && off_18012A658[0] )
        {
          pwszName = a2->pwszName;
          v13 = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
          bidTraceW(off_18012A200[0], 770048, off_18012A658[0], v13, pwszName);
        }
      }
      else
      {
        v29 = -2147024882;
        if ( (unsigned int)CContext::Failed((CContext *)v26, &v29) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_69;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
            LODWORD(v21) = 743;
            v9 = 760841;
            goto LABEL_8;
          }
          v10 = 743;
          v11 = 760841;
LABEL_10:
          bidTraceW(off_18012A200[0], v11, L"<CRecField::Init|ADO|ERR>  line %d\n", v10);
          goto LABEL_69;
        }
      }
    }
    *((_DWORD *)this + 34) = a2->columnid.eKind;
    if ( (a2->columnid.eKind & 0xFFFFFFFC) != 0 || a2->columnid.eKind == 1 )
    {
      *((_DWORD *)this + 36) = a2->columnid.uName.ulPropid;
    }
    else
    {
      CSysString::operator=(&psz, a2->columnid.uName.pwszName);
      if ( (v23 & 4) != 0 )
      {
        *((_QWORD *)this + 18) = SysAllocString(psz);
        if ( (bidGblFlags & 2) != 0 && off_18012A680[0] )
        {
          v14 = *((_QWORD *)this + 18);
          v15 = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
          bidTraceW(off_18012A200[0], 793600, off_18012A680[0], v15, v14);
        }
      }
      else
      {
        v29 = -2147024882;
        if ( (unsigned int)CContext::Failed((CContext *)v26, &v29) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_69;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
            LODWORD(v21) = 768;
            v9 = 786441;
            goto LABEL_8;
          }
          v10 = 768;
          v11 = 786441;
          goto LABEL_10;
        }
      }
    }
    if ( a2->columnid.eKind - 3 <= 1 )
    {
      v16 = (GUID *)MpHeapAlloc(g_hHeapHandle, 10485760, 16);
      if ( !v16 )
      {
        v29 = -2147024882;
        if ( (unsigned int)CContext::Failed((CContext *)v26, &v29) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_69;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
            LODWORD(v21) = 790;
            v9 = 808969;
            goto LABEL_8;
          }
          v10 = 790;
          v11 = 808969;
          goto LABEL_10;
        }
      }
      *v16 = *a2->columnid.uGuid.pguid;
      CoTaskMemFree(a2->columnid.uGuid.pguid);
      a2->columnid.uGuid.pguid = 0;
      *((_QWORD *)this + 15) = v16;
    }
    else
    {
      *(union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D *)((char *)this + 120) = a2->columnid.uGuid;
    }
    *((_DWORD *)this + 45) = a4;
    if ( a4 )
    {
      if ( a4 != 0x10000 )
        goto LABEL_69;
      v29 = CRecField::SetCurrentValue(this, a3);
      if ( (unsigned int)CContext::Failed((CContext *)v26, &v29) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_69;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
          LODWORD(v21) = 832;
          v9 = 851977;
          goto LABEL_8;
        }
        v10 = 832;
        v11 = 851977;
        goto LABEL_10;
      }
      v29 = CRecField::SetTypeInfo(
              this,
              (enum DataTypeEnum)a2->wType,
              a2->ulColumnSize,
              (enum FieldAttributeEnum)a2->dwFlags);
      if ( (unsigned int)CContext::Failed((CContext *)v26, &v29) && (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
          LODWORD(v21) = 835;
          v9 = 855049;
          goto LABEL_8;
        }
        v10 = 835;
        v11 = 855049;
        goto LABEL_10;
      }
    }
    else
    {
      v17 = *((_DWORD *)this + 46);
      if ( !v17 || (unsigned int)(v17 - 3) <= 1 )
      {
        v29 = CRecField::SetOriginalValue(this, a3);
        if ( (unsigned int)CContext::Failed((CContext *)v26, &v29) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_69;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
            LODWORD(v21) = 815;
            v9 = 834569;
            goto LABEL_8;
          }
          v10 = 815;
          v11 = 834569;
          goto LABEL_10;
        }
        *((_BYTE *)this + 176) = a2->bPrecision;
        *((_BYTE *)this + 177) = a2->bScale;
        wType = a2->wType;
        if ( (wType & 0x1000) != 0 )
          wType |= 0x2000u;
        *((_WORD *)this + 76) = wType & 0x2FFF;
        *((_DWORD *)this + 39) = a2->dwFlags;
        *((_QWORD *)this + 21) = a2->ulColumnSize;
      }
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
      LODWORD(v21) = 735;
      v9 = 752649;
LABEL_8:
      bidTraceW(off_18012A200[0], v9, L"<CRecField::Init|ADO|ERR> %u#, line %d\n", BidObjectID, v21);
      goto LABEL_69;
    }
    v10 = 735;
    v11 = 752649;
    goto LABEL_10;
  }
LABEL_69:
  v19 = v28;
  CSysString::~CSysString((CSysString *)&psz);
  CSysString::~CSysString((CSysString *)&v24);
  CContext::~CContext((CContext *)v26);
  return v19;
}

```

## disassembly

```asm
0x18009ebc8  push    rbp
0x18009ebca  push    rbx
0x18009ebcb  push    rsi
0x18009ebcc  push    rdi
0x18009ebcd  push    r12
0x18009ebcf  push    r15
0x18009ebd1  lea     rbp, [rsp-2Fh]
0x18009ebd6  sub     rsp, 88h
0x18009ebdd  mov     r15d, r9d
0x18009ebe0  mov     r12, r8
0x18009ebe3  mov     rsi, rdx
0x18009ebe6  mov     rdi, rcx
0x18009ebe9  mov     rax, rcx
0x18009ebec  lea     r11, [rcx+8]
0x18009ebf0  neg     rax
0x18009ebf3  sbb     r10, r10
0x18009ebf6  and     r10, r11
0x18009ebf9  mov     [rbp+57h+var_40], r10
0x18009ebfd  lea     rcx, [rbp+57h+var_60]; this
0x18009ec01  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x18009ec06  nop
0x18009ec07  mov     [rbp+57h+var_70], 0
0x18009ec0f  mov     [rbp+57h+var_68], 7
0x18009ec13  mov     [rbp+57h+psz], 0
0x18009ec1b  mov     [rbp+57h+var_78], 7
0x18009ec1f  test    rsi, rsi
0x18009ec22  jz      short loc_18009EC36
0x18009ec24  test    r15d, 0FFFEFFFFh
0x18009ec2b  jnz     short loc_18009EC36
0x18009ec2d  test    r12, r12
0x18009ec30  jnz     loc_18009ECBD
0x18009ec36  mov     [rbp+57h+arg_0], 800A0BB9h
0x18009ec3d  lea     rdx, [rbp+57h+arg_0]; int *
0x18009ec41  lea     rcx, [rbp+57h+var_60]; this
0x18009ec45  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009ec4a  test    eax, eax
0x18009ec4c  jz      short loc_18009ECBD
0x18009ec4e  test    byte ptr cs:_bidGblFlags, 2
0x18009ec55  jz      loc_18009F14E
0x18009ec5b  lea     rcx, [rdi+58h]; this
0x18009ec5f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009ec64  cmp     eax, 0FFFFFFFFh
0x18009ec67  jz      short loc_18009EC9A
0x18009ec69  lea     rcx, [rdi+58h]; this
0x18009ec6d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009ec72  mov     dword ptr [rsp+0B0h+var_90], 2DFh
0x18009ec7a  mov     edx, 0B7C09h
0x18009ec7f  lea     r8, aCrecfieldInitA_0; "<CRecField::Init|ADO|ERR> %u#, line %d"...
0x18009ec86  mov     r9d, eax
0x18009ec89  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009ec90  call    _bidTraceW
0x18009ec95  jmp     loc_18009F14E
0x18009ec9a  mov     r9d, 2DFh
0x18009eca0  mov     edx, 0B7C09h
0x18009eca5  lea     r8, aCrecfieldInitA; "<CRecField::Init|ADO|ERR>  line %d\n"
0x18009ecac  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009ecb3  call    _bidTraceW
0x18009ecb8  jmp     loc_18009F14E
0x18009ecbd  mov     rdx, [rsi]
0x18009ecc0  test    rdx, rdx
0x18009ecc3  jz      loc_18009EDDF
0x18009ecc9  lea     rcx, [rbp+57h+var_70]
0x18009eccd  call    ??4CSysString@@QEAAAEBV0@PEBG@Z; CSysString::operator=(ushort const *)
0x18009ecd2  test    [rbp+57h+var_68], 4
0x18009ecd6  jnz     short loc_18009ED3A
0x18009ecd8  mov     [rbp+57h+arg_0], 8007000Eh
0x18009ecdf  lea     rdx, [rbp+57h+arg_0]; int *
0x18009ece3  lea     rcx, [rbp+57h+var_60]; this
0x18009ece7  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009ecec  test    eax, eax
0x18009ecee  jz      loc_18009EDDF
0x18009ecf4  test    byte ptr cs:_bidGblFlags, 2
0x18009ecfb  jz      loc_18009F14E
0x18009ed01  lea     rcx, [rdi+58h]; this
0x18009ed05  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009ed0a  cmp     eax, 0FFFFFFFFh
0x18009ed0d  jz      short loc_18009ED2A
0x18009ed0f  lea     rcx, [rdi+58h]; this
0x18009ed13  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009ed18  mov     dword ptr [rsp+0B0h+var_90], 2E7h
0x18009ed20  mov     edx, 0B9C09h
0x18009ed25  jmp     loc_18009EC7F
0x18009ed2a  mov     r9d, 2E7h
0x18009ed30  mov     edx, 0B9C09h
0x18009ed35  jmp     loc_18009ECA5
0x18009ed3a  lea     rdx, [rbp+57h+var_70]
0x18009ed3e  lea     rcx, [rdi+68h]
0x18009ed42  call    ??4CSysString@@QEAAAEBV0@AEBV0@@Z; CSysString::operator=(CSysString const &)
0x18009ed47  lea     rdx, [rdi+68h]; struct CSysString *
0x18009ed4b  lea     rcx, [rbp+57h+var_60]; this
0x18009ed4f  call    ?StringFailed@CContext@@QEAAHAEBVCSysString@@@Z; CContext::StringFailed(CSysString const &)
0x18009ed54  test    eax, eax
0x18009ed56  jz      short loc_18009ED9E
0x18009ed58  test    byte ptr cs:_bidGblFlags, 2
0x18009ed5f  jz      loc_18009F14E
0x18009ed65  lea     rcx, [rdi+58h]; this
0x18009ed69  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009ed6e  cmp     eax, 0FFFFFFFFh
0x18009ed71  jz      short loc_18009ED8E
0x18009ed73  lea     rcx, [rdi+58h]; this
0x18009ed77  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009ed7c  mov     dword ptr [rsp+0B0h+var_90], 2ECh
0x18009ed84  mov     edx, 0BB009h
0x18009ed89  jmp     loc_18009EC7F
0x18009ed8e  mov     r9d, 2ECh
0x18009ed94  mov     edx, 0BB009h
0x18009ed99  jmp     loc_18009ECA5
0x18009ed9e  test    byte ptr cs:_bidGblFlags, 2
0x18009eda5  jz      short loc_18009EDDF
0x18009eda7  mov     rax, cs:off_18012A658; "<CRecField::Init|INFO|ADO> %u#, Name: "...
0x18009edae  test    rax, rax
0x18009edb1  jz      short loc_18009EDDF
0x18009edb3  mov     rbx, [rsi]
0x18009edb6  lea     rcx, [rdi+58h]; this
0x18009edba  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009edbf  mov     r8, cs:off_18012A658; "<CRecField::Init|INFO|ADO> %u#, Name: "...
0x18009edc6  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009edcd  mov     [rsp+0B0h+var_90], rbx
0x18009edd2  mov     r9d, eax
0x18009edd5  mov     edx, 0BC000h
0x18009edda  call    _bidTraceW
0x18009eddf  mov     eax, [rsi+40h]
0x18009ede2  mov     [rdi+88h], eax
0x18009ede8  test    dword ptr [rsi+40h], 0FFFFFFFCh
0x18009edef  jnz     loc_18009EED2
0x18009edf5  cmp     dword ptr [rsi+40h], 1
0x18009edf9  jz      loc_18009EED2
0x18009edff  mov     rdx, [rsi+48h]
0x18009ee03  lea     rcx, [rbp+57h+psz]
0x18009ee07  call    ??4CSysString@@QEAAAEBV0@PEBG@Z; CSysString::operator=(ushort const *)
0x18009ee0c  test    [rbp+57h+var_78], 4
0x18009ee10  jnz     short loc_18009EE74
0x18009ee12  mov     [rbp+57h+arg_0], 8007000Eh
0x18009ee19  lea     rdx, [rbp+57h+arg_0]; int *
0x18009ee1d  lea     rcx, [rbp+57h+var_60]; this
0x18009ee21  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009ee26  test    eax, eax
0x18009ee28  jz      loc_18009EEDB
0x18009ee2e  test    byte ptr cs:_bidGblFlags, 2
0x18009ee35  jz      loc_18009F14E
0x18009ee3b  lea     rcx, [rdi+58h]; this
0x18009ee3f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009ee44  cmp     eax, 0FFFFFFFFh
0x18009ee47  jz      short loc_18009EE64
0x18009ee49  lea     rcx, [rdi+58h]; this
0x18009ee4d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009ee52  mov     dword ptr [rsp+0B0h+var_90], 300h
0x18009ee5a  mov     edx, 0C0009h
0x18009ee5f  jmp     loc_18009EC7F
0x18009ee64  mov     r9d, 300h
0x18009ee6a  mov     edx, 0C0009h
0x18009ee6f  jmp     loc_18009ECA5
0x18009ee74  mov     rcx, [rbp+57h+psz]; psz
0x18009ee78  call    cs:__imp_SysAllocString
0x18009ee7f  nop     dword ptr [rax+rax+00h]
0x18009ee84  mov     [rdi+90h], rax
0x18009ee8b  test    byte ptr cs:_bidGblFlags, 2
0x18009ee92  jz      short loc_18009EEDB
0x18009ee94  mov     rax, cs:off_18012A680; "<CRecField::Init|INFO|ADO> %u#, m_id.uN"...
0x18009ee9b  test    rax, rax
0x18009ee9e  jz      short loc_18009EEDB
0x18009eea0  mov     rbx, [rdi+90h]
0x18009eea7  lea     rcx, [rdi+58h]; this
0x18009eeab  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009eeb0  mov     r8, cs:off_18012A680; "<CRecField::Init|INFO|ADO> %u#, m_id.uN"...
0x18009eeb7  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009eebe  mov     [rsp+0B0h+var_90], rbx
0x18009eec3  mov     r9d, eax
0x18009eec6  mov     edx, 0C1C00h
0x18009eecb  call    _bidTraceW
0x18009eed0  jmp     short loc_18009EEDB
0x18009eed2  mov     eax, [rsi+48h]
0x18009eed5  mov     [rdi+90h], eax
0x18009eedb  mov     eax, [rsi+40h]
0x18009eede  sub     eax, 3
0x18009eee1  cmp     eax, 1
0x18009eee4  jbe     short loc_18009EEF4
0x18009eee6  movups  xmm0, xmmword ptr [rsi+30h]
0x18009eeea  movdqu  xmmword ptr [rdi+78h], xmm0
0x18009eeef  jmp     loc_18009EF9F
0x18009eef4  mov     edx, 0A00000h
0x18009eef9  mov     r8d, 10h
0x18009eeff  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18009ef06  call    cs:__imp_MpHeapAlloc
0x18009ef0d  nop     dword ptr [rax+rax+00h]
0x18009ef12  mov     rbx, rax
0x18009ef15  test    rax, rax
0x18009ef18  jnz     short loc_18009EF78
0x18009ef1a  mov     [rbp+57h+arg_0], 8007000Eh
0x18009ef21  lea     rdx, [rbp+57h+arg_0]; int *
0x18009ef25  lea     rcx, [rbp+57h+var_60]; this
0x18009ef29  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009ef2e  test    eax, eax
0x18009ef30  jz      short loc_18009EF78
0x18009ef32  test    byte ptr cs:_bidGblFlags, 2
0x18009ef39  jz      loc_18009F14E
0x18009ef3f  lea     rcx, [rdi+58h]; this
0x18009ef43  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009ef48  cmp     eax, 0FFFFFFFFh
0x18009ef4b  jz      short loc_18009EF68
0x18009ef4d  lea     rcx, [rdi+58h]; this
0x18009ef51  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009ef56  mov     dword ptr [rsp+0B0h+var_90], 316h
0x18009ef5e  mov     edx, 0C5809h
0x18009ef63  jmp     loc_18009EC7F
0x18009ef68  mov     r9d, 316h
0x18009ef6e  mov     edx, 0C5809h
0x18009ef73  jmp     loc_18009ECA5
0x18009ef78  mov     rax, [rsi+30h]
0x18009ef7c  movups  xmm0, xmmword ptr [rax]
0x18009ef7f  movdqu  xmmword ptr [rbx], xmm0
0x18009ef83  mov     rcx, [rsi+30h]; pv
0x18009ef87  call    cs:__imp_CoTaskMemFree
0x18009ef8e  nop     dword ptr [rax+rax+00h]
0x18009ef93  mov     qword ptr [rsi+30h], 0
0x18009ef9b  mov     [rdi+78h], rbx
0x18009ef9f  mov     [rdi+0B4h], r15d
0x18009efa6  test    r15d, r15d
0x18009efa9  jz      loc_18009F093
0x18009efaf  cmp     r15d, 10000h
0x18009efb6  jnz     loc_18009F14E
0x18009efbc  mov     rdx, r12; struct tagVARIANT *
0x18009efbf  mov     rcx, rdi; this
0x18009efc2  call    ?SetCurrentValue@CRecField@@AEAAJAEBUtagVARIANT@@@Z; CRecField::SetCurrentValue(tagVARIANT const &)
0x18009efc7  mov     [rbp+57h+arg_0], eax
0x18009efca  lea     rdx, [rbp+57h+arg_0]; int *
0x18009efce  lea     rcx, [rbp+57h+var_60]; this
0x18009efd2  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009efd7  test    eax, eax
0x18009efd9  jz      short loc_18009F021
0x18009efdb  test    byte ptr cs:_bidGblFlags, 2
0x18009efe2  jz      loc_18009F14E
0x18009efe8  lea     rcx, [rdi+58h]; this
0x18009efec  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009eff1  cmp     eax, 0FFFFFFFFh
0x18009eff4  jz      short loc_18009F011
0x18009eff6  lea     rcx, [rdi+58h]; this
0x18009effa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009efff  mov     dword ptr [rsp+0B0h+var_90], 340h
0x18009f007  mov     edx, 0D0009h
0x18009f00c  jmp     loc_18009EC7F
0x18009f011  mov     r9d, 340h
0x18009f017  mov     edx, 0D0009h
0x18009f01c  jmp     loc_18009ECA5
0x18009f021  movzx   edx, word ptr [rsi+28h]; enum DataTypeEnum
0x18009f025  mov     r9d, [rsi+18h]; enum FieldAttributeEnum
0x18009f029  mov     r8, [rsi+20h]; unsigned __int64
0x18009f02d  mov     rcx, rdi; this
0x18009f030  call    ?SetTypeInfo@CRecField@@QEAAJW4DataTypeEnum@@_KW4FieldAttributeEnum@@@Z; CRecField::SetTypeInfo(DataTypeEnum,unsigned __int64,FieldAttributeEnum)
0x18009f035  mov     [rbp+57h+arg_0], eax
0x18009f038  lea     rdx, [rbp+57h+arg_0]; int *
0x18009f03c  lea     rcx, [rbp+57h+var_60]; this
0x18009f040  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009f045  test    eax, eax
0x18009f047  jz      loc_18009F14E
0x18009f04d  test    byte ptr cs:_bidGblFlags, 2
0x18009f054  jz      loc_18009F14E
0x18009f05a  lea     rcx, [rdi+58h]; this
0x18009f05e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009f063  cmp     eax, 0FFFFFFFFh
0x18009f066  jz      short loc_18009F083
0x18009f068  lea     rcx, [rdi+58h]; this
0x18009f06c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009f071  mov     dword ptr [rsp+0B0h+var_90], 343h
0x18009f079  mov     edx, 0D0C09h
0x18009f07e  jmp     loc_18009EC7F
0x18009f083  mov     r9d, 343h
0x18009f089  mov     edx, 0D0C09h
0x18009f08e  jmp     loc_18009ECA5
0x18009f093  mov     eax, [rdi+0B8h]
0x18009f099  test    eax, eax
0x18009f09b  jz      short loc_18009F0A9
0x18009f09d  add     eax, 0FFFFFFFDh
0x18009f0a0  cmp     eax, 1
0x18009f0a3  ja      loc_18009F14E
0x18009f0a9  mov     rdx, r12; struct tagVARIANT *
0x18009f0ac  mov     rcx, rdi; this
0x18009f0af  call    ?SetOriginalValue@CRecField@@AEAAJAEBUtagVARIANT@@@Z; CRecField::SetOriginalValue(tagVARIANT const &)
0x18009f0b4  mov     [rbp+57h+arg_0], eax
0x18009f0b7  lea     rdx, [rbp+57h+arg_0]; int *
0x18009f0bb  lea     rcx, [rbp+57h+var_60]; this
0x18009f0bf  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009f0c4  test    eax, eax
0x18009f0c6  jz      short loc_18009F10A
0x18009f0c8  test    byte ptr cs:_bidGblFlags, 2
0x18009f0cf  jz      short loc_18009F14E
0x18009f0d1  lea     rcx, [rdi+58h]; this
0x18009f0d5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009f0da  cmp     eax, 0FFFFFFFFh
0x18009f0dd  jz      short loc_18009F0FA
0x18009f0df  lea     rcx, [rdi+58h]; this
0x18009f0e3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009f0e8  mov     dword ptr [rsp+0B0h+var_90], 32Fh
0x18009f0f0  mov     edx, 0CBC09h
0x18009f0f5  jmp     loc_18009EC7F
0x18009f0fa  mov     r9d, 32Fh
0x18009f100  mov     edx, 0CBC09h
0x18009f105  jmp     loc_18009ECA5
0x18009f10a  mov     al, [rsi+2Ah]
0x18009f10d  mov     [rdi+0B0h], al
  ... truncated ...
```
