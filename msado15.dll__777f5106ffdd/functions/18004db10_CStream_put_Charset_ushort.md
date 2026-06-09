# CStream::put_Charset(ushort *)

- ea: `0x18004db10`
- end: `0x18004e1c0`
- name: `?put_Charset@CStream@@UEAAJPEAG@Z`
- size: `1712`
- prototype: `int(CStream *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800a4ce0`

## callees

- `0x180020e20`
- `0x180020fc0`
- `0x180048990`
- `0x18004db10`
- `0x18004f1b0`
- `0x18004f2b0`
- `0x18004f370`
- `0x180057bdc`
- `0x18006a22c`
- `0x1800bd8b8`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800cdaea`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x18004dbea`
- `MSDART!UMSEnterCSWraper` at `0x18004dbea`
- `KERNEL32!CompareStringW` at `0x18004de31`
- `KERNEL32!CompareStringW` at `0x18004de64`
- `KERNEL32!CompareStringW` at `0x18004de97`
- `KERNEL32!CompareStringW` at `0x18004dedf`
- `KERNEL32!CompareStringW` at `0x18004de31`
- `KERNEL32!CompareStringW` at `0x18004de64`
- `KERNEL32!CompareStringW` at `0x18004de97`
- `KERNEL32!CompareStringW` at `0x18004dedf`
- `KERNEL32!LeaveCriticalSection` at `0x18004e11a`
- `KERNEL32!LeaveCriticalSection` at `0x18004e11a`
- `KERNEL32!TlsSetValue` at `0x18004dbcd`
- `KERNEL32!TlsSetValue` at `0x18004e17a`
- `KERNEL32!TlsSetValue` at `0x18004dbcd`
- `KERNEL32!TlsSetValue` at `0x18004e17a`
- `KERNEL32!TlsGetValue` at `0x18004db85`
- `KERNEL32!TlsGetValue` at `0x18004db85`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004e142`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004e142`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStream::put_Charset(CStream *this, unsigned __int16 *a2)
{
  __int64 v4; // rsi
  _DWORD *Value; // rax
  unsigned int BidObjectID; // eax
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // edx
  const struct CSysString *v12; // rax
  int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rcx
  _DWORD *v18; // rax
  IErrorInfo *v19; // rdx
  PCNZWCH lpString2; // [rsp+20h] [rbp-A9h]
  int v22; // [rsp+30h] [rbp-99h] BYREF
  _DWORD *TlsValue; // [rsp+38h] [rbp-91h] BYREF
  int v24; // [rsp+40h] [rbp-89h]
  __int64 v25; // [rsp+48h] [rbp-81h]
  int v26; // [rsp+50h] [rbp-79h]
  __int16 v27; // [rsp+54h] [rbp-75h]
  char v28; // [rsp+56h] [rbp-73h]
  unsigned __int64 v29; // [rsp+58h] [rbp-71h]
  int v30; // [rsp+60h] [rbp-69h]
  int v31; // [rsp+64h] [rbp-65h]
  __int64 *v32; // [rsp+68h] [rbp-61h]
  __int64 v33; // [rsp+70h] [rbp-59h] BYREF
  __int64 v34; // [rsp+78h] [rbp-51h] BYREF
  _BYTE v35[4]; // [rsp+80h] [rbp-49h] BYREF
  int v36; // [rsp+84h] [rbp-45h]

  memset_0(v35, 0, 0x6Cu);
  v34 = 0;
  v4 = *((_QWORD *)this + 18) + 8LL;
  v29 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  v31 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v30 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v24 = 1;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v32 = 0;
  UMSEnterCSWraper(v4);
  v32 = (__int64 *)v4;
  v33 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AD78[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    bidScopeEnterW(&v33, off_18012AD78[0], BidObjectID, a2, (_DWORD)lpString2);
  }
  if ( !*((_QWORD *)this + 21) )
    goto LABEL_20;
  v30 = (*(__int64 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 1) + 72LL))((char *)this + 8, &v34);
  if ( v30 >= 0 )
  {
    if ( v34 )
    {
      v22 = -2146825069;
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v22) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_62;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          LODWORD(lpString2) = 1143;
          v8 = 1170441;
          goto LABEL_12;
        }
        v9 = 1143;
        v10 = 1170441;
        goto LABEL_58;
      }
    }
LABEL_20:
    if ( !a2 || (v11 = 1, !*a2) )
      v11 = 0;
    if ( (unsigned int)CContext::ArgFailed((CContext *)&TlsValue, v11) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_62;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        LODWORD(lpString2) = 1147;
        v8 = 1174537;
        goto LABEL_12;
      }
      v9 = 1147;
      v10 = 1174537;
    }
    else
    {
      if ( !(unsigned int)CContext::OpFailed((CContext *)&TlsValue, *((_DWORD *)this + 46) == 2) )
      {
        if ( CompareStringW(0x400u, 0x30001u, a2, -1, L"Unicode", -1) == 2
          || CompareStringW(0x400u, 0x30001u, a2, -1, L"UnicodeFFFE", -1) == 2 )
        {
          *((_QWORD *)this + 27) = 1200;
        }
        else if ( CompareStringW(0x400u, 0x30001u, a2, -1, L"UnicodeFEFF", -1) == 2 )
        {
          *((_DWORD *)this + 54) = 1200;
          *((_DWORD *)this + 55) = 1;
        }
        else if ( CompareStringW(0x400u, 0x30001u, a2, -1, L"UnicodeFFFF", -1) == 2 )
        {
          *((_DWORD *)this + 54) = 1200;
          *((_DWORD *)this + 55) = 2;
        }
        else
        {
          if ( !*((_QWORD *)this + 28) )
          {
            v22 = ((int)EnableMLangSupport((LPVOID *)this + 28) >> 31) & 0x800A0CB3;
            if ( (unsigned int)CContext::FailedDescription((CContext *)&TlsValue, &v22, 0x272Eu) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_62;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
              {
                v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                LODWORD(lpString2) = 1170;
                v8 = 1198089;
                goto LABEL_12;
              }
              v9 = 1170;
              v10 = 1198089;
              goto LABEL_58;
            }
          }
          if ( (*(int (__fastcall **)(_QWORD, unsigned __int16 *, _BYTE *))(**((_QWORD **)this + 28) + 56LL))(
                 *((_QWORD *)this + 28),
                 a2,
                 v35) < 0 )
          {
            v22 = -2146825287;
            if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v22) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_62;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
              {
                v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                LODWORD(lpString2) = 1174;
                v8 = 1202185;
                goto LABEL_12;
              }
              v9 = 1174;
              v10 = 1202185;
              goto LABEL_58;
            }
          }
          *((_DWORD *)this + 54) = v36;
        }
        v12 = (const struct CSysString *)CSysString::operator=((char *)this + 200, a2);
        if ( !(unsigned int)CContext::StringFailed((CContext *)&TlsValue, v12) )
          goto LABEL_59;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_62;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          LODWORD(lpString2) = 1180;
          v8 = 1208329;
          goto LABEL_12;
        }
        v9 = 1180;
        v10 = 1208329;
        goto LABEL_58;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_62;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        LODWORD(lpString2) = 1148;
        v8 = 1175561;
        goto LABEL_12;
      }
      v9 = 1148;
      v10 = 1175561;
    }
LABEL_58:
    bidTraceW(off_18012A210[0], v10, L"<CStream::put_Charset|ADO|ERR>  line %d\n", v9);
    goto LABEL_59;
  }
  CContext::PushError((CContext *)&TlsValue);
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_62;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
  {
    v9 = 1140;
    v10 = 1167369;
    goto LABEL_58;
  }
  v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
  LODWORD(lpString2) = 1140;
  v8 = 1167369;
LABEL_12:
  bidTraceW(off_18012A210[0], v8, L"<CStream::put_Charset|ADO|ERR> %u#, line %d\n", v7, lpString2);
LABEL_59:
  if ( (bidGblFlags & 2) != 0 && off_18012A8F0[0] )
  {
    v13 = v30;
    v14 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    LODWORD(lpString2) = v13;
    bidTraceW(off_18012A210[0], 1213440, off_18012A8F0[0], v14, lpString2);
  }
LABEL_62:
  if ( (bidGblFlags & 4) != 0 && v33 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v33);
  v15 = v30;
  v16 = *v32;
  --*(_DWORD *)(v16 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 8));
  if ( TlsValue[2]-- == 1 )
  {
    v18 = TlsValue;
    v19 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v19 )
    {
      SetErrorInfo(0, v19);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v18 = TlsValue;
    }
    if ( *((_BYTE *)v18 + 30) )
    {
      *((_QWORD *)v18 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v15;
}

```

## disassembly

```asm
0x18004db10  mov     [rsp-8+arg_10], rbx
0x18004db15  mov     [rsp-8+arg_18], rsi
0x18004db1a  push    rbp
0x18004db1b  push    rdi
0x18004db1c  push    r12
0x18004db1e  push    r14
0x18004db20  push    r15
0x18004db22  lea     rbp, [rsp-37h]
0x18004db27  sub     rsp, 100h
0x18004db2e  mov     rax, cs:__security_cookie
0x18004db35  xor     rax, rsp
0x18004db38  mov     [rbp+57h+var_30], rax
0x18004db3c  mov     rbx, rdx
0x18004db3f  mov     rdi, rcx
0x18004db42  xor     edx, edx; Val
0x18004db44  lea     r8d, [rdx+6Ch]; Size
0x18004db48  lea     rcx, [rbp+57h+var_A0]; void *
0x18004db4c  call    memset_0
0x18004db51  xor     r14d, r14d
0x18004db54  mov     [rbp+57h+var_A8], r14
0x18004db58  mov     rsi, [rdi+90h]
0x18004db5f  add     rsi, 8
0x18004db63  mov     rax, rdi
0x18004db66  lea     rdx, [rdi+20h]
0x18004db6a  neg     rax
0x18004db6d  sbb     rcx, rcx
0x18004db70  and     rcx, rdx
0x18004db73  mov     [rbp+57h+var_C8], rcx
0x18004db77  mov     [rbp+57h+var_BC], r14d
0x18004db7b  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18004db82  mov     ecx, [rcx+14h]; dwTlsIndex
0x18004db85  call    cs:__imp_TlsGetValue
0x18004db8c  nop     dword ptr [rax+rax+00h]
0x18004db91  mov     [rsp+120h+TlsValue], rax
0x18004db96  mov     [rbp+57h+var_C0], r14d
0x18004db9a  test    rax, rax
0x18004db9d  jz      short loc_18004DBA4
0x18004db9f  inc     dword ptr [rax+8]
0x18004dba2  jmp     short loc_18004DBE3
0x18004dba4  mov     [rsp+120h+var_E0], 1
0x18004dbac  mov     [rsp+120h+var_D8], r14
0x18004dbb1  mov     [rbp+57h+var_D0], r14d
0x18004dbb5  mov     [rbp+57h+var_CC], r14w
0x18004dbba  mov     [rbp+57h+var_CA], r14b
0x18004dbbe  lea     rdx, [rsp+120h+TlsValue]; lpTlsValue
0x18004dbc3  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18004dbca  mov     ecx, [rcx+14h]; dwTlsIndex
0x18004dbcd  call    cs:__imp_TlsSetValue
0x18004dbd4  nop     dword ptr [rax+rax+00h]
0x18004dbd9  lea     rax, [rsp+120h+TlsValue]
0x18004dbde  mov     [rsp+120h+TlsValue], rax
0x18004dbe3  mov     [rbp+57h+var_B8], r14
0x18004dbe7  mov     rcx, rsi
0x18004dbea  call    cs:__imp_UMSEnterCSWraper
0x18004dbf1  nop     dword ptr [rax+rax+00h]
0x18004dbf6  mov     [rbp+57h+var_B8], rsi
0x18004dbfa  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004dbfe  mov     [rbp+57h+var_B0], r15
0x18004dc02  test    byte ptr cs:_bidGblFlags, 4
0x18004dc09  jz      short loc_18004DC39
0x18004dc0b  mov     rax, cs:off_18012AD78; "<CStream::put_Charset|API|ADO> %u#, Cha"...
0x18004dc12  test    rax, rax
0x18004dc15  jz      short loc_18004DC39
0x18004dc17  lea     rcx, [rdi+98h]; this
0x18004dc1e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004dc23  mov     rdx, cs:off_18012AD78; "<CStream::put_Charset|API|ADO> %u#, Cha"...
0x18004dc2a  mov     r9, rbx
0x18004dc2d  mov     r8d, eax
0x18004dc30  lea     rcx, [rbp+57h+var_B0]
0x18004dc34  call    _bidScopeEnterW
0x18004dc39  or      r12d, 0FFFFFFFFh
0x18004dc3d  cmp     [rdi+0A8h], r14
0x18004dc44  jz      loc_18004DD3C
0x18004dc4a  lea     rcx, [rdi+8]
0x18004dc4e  mov     rax, [rcx]
0x18004dc51  lea     rdx, [rbp+57h+var_A8]
0x18004dc55  mov     rax, [rax+48h]
0x18004dc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc5e  mov     [rbp+57h+var_C0], eax
0x18004dc61  test    eax, eax
0x18004dc63  jns     short loc_18004DCD0
0x18004dc65  lea     rcx, [rsp+120h+TlsValue]; this
0x18004dc6a  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18004dc6f  test    byte ptr cs:_bidGblFlags, 2
0x18004dc76  jz      loc_18004E0D8
0x18004dc7c  lea     rbx, [rdi+98h]
0x18004dc83  mov     rcx, rbx; this
0x18004dc86  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004dc8b  cmp     eax, r12d
0x18004dc8e  jz      short loc_18004DCC0
0x18004dc90  mov     rcx, rbx; this
0x18004dc93  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004dc98  mov     dword ptr [rsp+120h+lpString2], 474h
0x18004dca0  mov     edx, 11D009h
0x18004dca5  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004dcac  mov     r9d, eax
0x18004dcaf  lea     r8, aCstreamPutChar_2; "<CStream::put_Charset|ADO|ERR> %u#, lin"...
0x18004dcb6  call    _bidTraceW
0x18004dcbb  jmp     loc_18004E095
0x18004dcc0  mov     r9d, 474h
0x18004dcc6  mov     edx, 11D009h
0x18004dccb  jmp     loc_18004E082
0x18004dcd0  cmp     [rbp+57h+var_A8], r14
0x18004dcd4  jz      short loc_18004DD3C
0x18004dcd6  mov     [rsp+120h+var_F0], 800A0C93h
0x18004dcde  lea     rdx, [rsp+120h+var_F0]; int *
0x18004dce3  lea     rcx, [rsp+120h+TlsValue]; this
0x18004dce8  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18004dced  test    eax, eax
0x18004dcef  jz      short loc_18004DD3C
0x18004dcf1  test    byte ptr cs:_bidGblFlags, 2
0x18004dcf8  jz      loc_18004E0D8
0x18004dcfe  lea     rbx, [rdi+98h]
0x18004dd05  mov     rcx, rbx; this
0x18004dd08  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004dd0d  cmp     eax, r12d
0x18004dd10  jz      short loc_18004DD2C
0x18004dd12  mov     rcx, rbx; this
0x18004dd15  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004dd1a  mov     dword ptr [rsp+120h+lpString2], 477h
0x18004dd22  mov     edx, 11DC09h
0x18004dd27  jmp     loc_18004DCA5
0x18004dd2c  mov     r9d, 477h
0x18004dd32  mov     edx, 11DC09h
0x18004dd37  jmp     loc_18004E082
0x18004dd3c  test    rbx, rbx
0x18004dd3f  jz      short loc_18004DD4C
0x18004dd41  cmp     [rbx], r14w
0x18004dd45  mov     edx, 1
0x18004dd4a  jnz     short loc_18004DD4F
0x18004dd4c  mov     edx, r14d; int
0x18004dd4f  lea     rcx, [rsp+120h+TlsValue]; this
0x18004dd54  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x18004dd59  test    eax, eax
0x18004dd5b  jz      short loc_18004DDA8
0x18004dd5d  test    byte ptr cs:_bidGblFlags, 2
0x18004dd64  jz      loc_18004E0D8
0x18004dd6a  lea     rbx, [rdi+98h]
0x18004dd71  mov     rcx, rbx; this
0x18004dd74  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004dd79  cmp     eax, r12d
0x18004dd7c  jz      short loc_18004DD98
0x18004dd7e  mov     rcx, rbx; this
0x18004dd81  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004dd86  mov     dword ptr [rsp+120h+lpString2], 47Bh
0x18004dd8e  mov     edx, 11EC09h
0x18004dd93  jmp     loc_18004DCA5
0x18004dd98  mov     r9d, 47Bh
0x18004dd9e  mov     edx, 11EC09h
0x18004dda3  jmp     loc_18004E082
0x18004dda8  mov     edx, r14d
0x18004ddab  cmp     dword ptr [rdi+0B8h], 2
0x18004ddb2  setz    dl; int
0x18004ddb5  lea     rcx, [rsp+120h+TlsValue]; this
0x18004ddba  call    ?OpFailed@CContext@@QEAAHH@Z; CContext::OpFailed(int)
0x18004ddbf  test    eax, eax
0x18004ddc1  jz      short loc_18004DE0E
0x18004ddc3  test    byte ptr cs:_bidGblFlags, 2
0x18004ddca  jz      loc_18004E0D8
0x18004ddd0  lea     rbx, [rdi+98h]
0x18004ddd7  mov     rcx, rbx; this
0x18004ddda  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004dddf  cmp     eax, r12d
0x18004dde2  jz      short loc_18004DDFE
0x18004dde4  mov     rcx, rbx; this
0x18004dde7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004ddec  mov     dword ptr [rsp+120h+lpString2], 47Ch
0x18004ddf4  mov     edx, 11F009h
0x18004ddf9  jmp     loc_18004DCA5
0x18004ddfe  mov     r9d, 47Ch
0x18004de04  mov     edx, 11F009h
0x18004de09  jmp     loc_18004E082
0x18004de0e  mov     [rsp+120h+cchCount2], r15d; cchCount2
0x18004de13  lea     rax, aUnicode; "Unicode"
0x18004de1a  mov     [rsp+120h+lpString2], rax; lpString2
0x18004de1f  mov     r9d, r15d; cchCount1
0x18004de22  mov     r8, rbx; lpString1
0x18004de25  mov     esi, 30001h
0x18004de2a  mov     edx, esi; dwCmpFlags
0x18004de2c  mov     ecx, 400h; Locale
0x18004de31  call    cs:__imp_CompareStringW
0x18004de38  nop     dword ptr [rax+rax+00h]
0x18004de3d  cmp     eax, 2
0x18004de40  jz      loc_18004E011
0x18004de46  mov     [rsp+120h+cchCount2], r15d; cchCount2
0x18004de4b  lea     rax, aUnicodefffe; "UnicodeFFFE"
0x18004de52  mov     [rsp+120h+lpString2], rax; lpString2
0x18004de57  mov     r9d, r15d; cchCount1
0x18004de5a  mov     r8, rbx; lpString1
0x18004de5d  mov     edx, esi; dwCmpFlags
0x18004de5f  mov     ecx, 400h; Locale
0x18004de64  call    cs:__imp_CompareStringW
0x18004de6b  nop     dword ptr [rax+rax+00h]
0x18004de70  cmp     eax, 2
0x18004de73  jz      loc_18004E011
0x18004de79  mov     [rsp+120h+cchCount2], r15d; cchCount2
0x18004de7e  lea     rax, aUnicodefeff; "UnicodeFEFF"
0x18004de85  mov     [rsp+120h+lpString2], rax; lpString2
0x18004de8a  mov     r9d, r15d; cchCount1
0x18004de8d  mov     r8, rbx; lpString1
0x18004de90  mov     edx, esi; dwCmpFlags
0x18004de92  mov     ecx, 400h; Locale
0x18004de97  call    cs:__imp_CompareStringW
0x18004de9e  nop     dword ptr [rax+rax+00h]
0x18004dea3  cmp     eax, 2
0x18004dea6  jnz     short loc_18004DEC1
0x18004dea8  mov     dword ptr [rdi+0D8h], 4B0h
0x18004deb2  mov     dword ptr [rdi+0DCh], 1
0x18004debc  jmp     loc_18004E01C
0x18004dec1  mov     [rsp+120h+cchCount2], r15d; cchCount2
0x18004dec6  lea     rax, aUnicodeffff; "UnicodeFFFF"
0x18004decd  mov     [rsp+120h+lpString2], rax; lpString2
0x18004ded2  mov     r9d, r15d; cchCount1
0x18004ded5  mov     r8, rbx; lpString1
0x18004ded8  mov     edx, esi; dwCmpFlags
0x18004deda  mov     ecx, 400h; Locale
0x18004dedf  call    cs:__imp_CompareStringW
0x18004dee6  nop     dword ptr [rax+rax+00h]
0x18004deeb  cmp     eax, 2
0x18004deee  jnz     short loc_18004DF05
0x18004def0  mov     dword ptr [rdi+0D8h], 4B0h
0x18004defa  mov     [rdi+0DCh], eax
0x18004df00  jmp     loc_18004E01C
0x18004df05  lea     rsi, [rdi+0E0h]
0x18004df0c  cmp     [rsi], r14
0x18004df0f  jnz     short loc_18004DF89
0x18004df11  mov     rcx, rsi; ppv
0x18004df14  call    ?EnableMLangSupport@@YAJPEAPEAX@Z; EnableMLangSupport(void * *)
0x18004df19  sar     eax, 1Fh
0x18004df1c  and     eax, 800A0CB3h
0x18004df21  mov     [rsp+120h+var_F0], eax
0x18004df25  mov     r8d, 272Eh; unsigned int
0x18004df2b  lea     rdx, [rsp+120h+var_F0]; int *
0x18004df30  lea     rcx, [rsp+120h+TlsValue]; this
0x18004df35  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x18004df3a  test    eax, eax
0x18004df3c  jz      short loc_18004DF89
0x18004df3e  test    byte ptr cs:_bidGblFlags, 2
0x18004df45  jz      loc_18004E0D8
0x18004df4b  lea     rbx, [rdi+98h]
0x18004df52  mov     rcx, rbx; this
0x18004df55  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004df5a  cmp     eax, r12d
0x18004df5d  jz      short loc_18004DF79
0x18004df5f  mov     rcx, rbx; this
0x18004df62  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004df67  mov     dword ptr [rsp+120h+lpString2], 492h
0x18004df6f  mov     edx, 124809h
0x18004df74  jmp     loc_18004DCA5
0x18004df79  mov     r9d, 492h
0x18004df7f  mov     edx, 124809h
0x18004df84  jmp     loc_18004E082
0x18004df89  mov     rcx, [rsi]
0x18004df8c  mov     rax, [rcx]
0x18004df8f  lea     r8, [rbp+57h+var_A0]
0x18004df93  mov     rdx, rbx
0x18004df96  mov     rax, [rax+38h]
0x18004df9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df9f  test    eax, eax
0x18004dfa1  jns     short loc_18004E006
0x18004dfa3  mov     [rsp+120h+var_F0], 800A0BB9h
0x18004dfab  lea     rdx, [rsp+120h+var_F0]; int *
0x18004dfb0  lea     rcx, [rsp+120h+TlsValue]; this
0x18004dfb5  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18004dfba  test    eax, eax
0x18004dfbc  jz      short loc_18004E006
0x18004dfbe  test    byte ptr cs:_bidGblFlags, 2
0x18004dfc5  jz      loc_18004E0D8
0x18004dfcb  lea     rbx, [rdi+98h]
0x18004dfd2  mov     rcx, rbx; this
0x18004dfd5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004dfda  cmp     eax, r12d
0x18004dfdd  jz      short loc_18004DFF9
0x18004dfdf  mov     rcx, rbx; this
0x18004dfe2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004dfe7  mov     dword ptr [rsp+120h+lpString2], 496h
0x18004dfef  mov     edx, 125809h
0x18004dff4  jmp     loc_18004DCA5
0x18004dff9  mov     r9d, 496h
0x18004dfff  mov     edx, 125809h
0x18004e004  jmp     short loc_18004E082
0x18004e006  mov     eax, [rbp+57h+var_9C]
0x18004e009  mov     [rdi+0D8h], eax
0x18004e00f  jmp     short loc_18004E01C
0x18004e011  mov     qword ptr [rdi+0D8h], 4B0h
0x18004e01c  lea     rcx, [rdi+0C8h]
0x18004e023  mov     rdx, rbx
0x18004e026  call    ??4CSysString@@QEAAAEBV0@QEAG@Z; CSysString::operator=(ushort * const)
0x18004e02b  mov     rdx, rax; struct CSysString *
0x18004e02e  lea     rcx, [rsp+120h+TlsValue]; this
0x18004e033  call    ?StringFailed@CContext@@QEAAHAEBVCSysString@@@Z; CContext::StringFailed(CSysString const &)
0x18004e038  test    eax, eax
0x18004e03a  jz      short loc_18004E095
0x18004e03c  test    byte ptr cs:_bidGblFlags, 2
0x18004e043  jz      loc_18004E0D8
0x18004e049  lea     rbx, [rdi+98h]
0x18004e050  mov     rcx, rbx; this
0x18004e053  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e058  cmp     eax, r12d
0x18004e05b  jz      short loc_18004E077
  ... truncated ...
```
