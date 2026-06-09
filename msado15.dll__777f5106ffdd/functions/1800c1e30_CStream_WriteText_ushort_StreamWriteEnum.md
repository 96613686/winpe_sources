# CStream::WriteText(ushort *,StreamWriteEnum)

- ea: `0x1800c1e30`
- end: `0x1800c2648`
- name: `?WriteText@CStream@@UEAAJPEAGW4StreamWriteEnum@@@Z`
- size: `2072`
- prototype: `__int64 __fastcall(CStream *__hidden this, unsigned __int16 *Src, enum StreamWriteEnum)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800a1db0`

## callees

- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x18004f2b0`
- `0x18006a22c`
- `0x1800bc878`
- `0x1800c1860`
- `0x1800c1e30`
- `0x1800c4538`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800cdad2`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapFree` at `0x1800c2592`
- `MSDART!MpHeapFree` at `0x1800c2592`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c21fd`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c21fd`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800c2326`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800c2326`

## string_xrefs

- `0x1800c1f44`: `<CStream::WriteText|ADO|ERR> %u#, line %d\n`
- `0x1800c245a`: `<CStream::WriteText|ADO|ERR> %u#, line %d\n`
- `0x1800c1f6a`: `<CStream::WriteText|ADO|ERR>  line %d\n`
- `0x1800c2572`: `<CStream::WriteText|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CStream::WriteText(CStream *this, unsigned __int8 *Src, unsigned int a3, const char *a4)
{
  unsigned __int8 *v4; // r15
  __int64 v6; // r8
  unsigned int BidObjectID; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // r13d
  bool v15; // si
  int v16; // eax
  UINT v17; // eax
  unsigned int v18; // r9d
  __int64 v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 v23; // rdx
  int v24; // r14d
  int v25; // eax
  unsigned int v26; // esi
  unsigned __int8 *v27; // rax
  __int64 v28; // rcx
  unsigned int v29; // ebx
  unsigned int v30; // eax
  unsigned int v31; // ebx
  unsigned __int8 *Srca; // [rsp+20h] [rbp-69h]
  int v34; // [rsp+40h] [rbp-49h] BYREF
  int v35; // [rsp+44h] [rbp-45h] BYREF
  int v36; // [rsp+48h] [rbp-41h] BYREF
  unsigned int v37; // [rsp+4Ch] [rbp-3Dh] BYREF
  __int64 v38; // [rsp+50h] [rbp-39h] BYREF
  __int64 v39; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v40[40]; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v41; // [rsp+88h] [rbp-1h]
  unsigned __int8 *v42[2]; // [rsp+98h] [rbp+Fh] BYREF

  v35 = 0;
  v4 = 0;
  v6 = *((_QWORD *)this + 18);
  v42[0] = 0;
  v38 = 0;
  v37 = 0;
  CXLockContext::CXLockContext(
    (CXLockContext *)v40,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(v6 + 8),
    a4);
  v39 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AD88[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    bidScopeEnterW(&v39, off_18012AD88[0], BidObjectID, a3, (_DWORD)Srca);
  }
  if ( Src && a3 <= 1 || (v34 = -2146825287, !(unsigned int)CContext::Failed((CContext *)v40, &v34)) )
  {
    if ( !*((_QWORD *)this + 21) )
    {
      v34 = -2146824584;
      if ( (unsigned int)CContext::Failed((CContext *)v40, &v34) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_93;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v11 = 2991113;
          LODWORD(Srca) = 2921;
          goto LABEL_10;
        }
        v12 = 2921;
        v13 = 2991113;
LABEL_12:
        bidTraceW(off_18012A210[0], v13, L"<CStream::WriteText|ADO|ERR>  line %d\n", v12);
        goto LABEL_90;
      }
    }
    if ( *((_DWORD *)this + 46) != 2 )
    {
      v34 = -2146825069;
      if ( (unsigned int)CContext::Failed((CContext *)v40, &v34) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_93;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v11 = 3007497;
          LODWORD(Srca) = 2937;
          goto LABEL_10;
        }
        v12 = 2937;
        v13 = 3007497;
        goto LABEL_12;
      }
    }
    if ( (*((_DWORD *)this + 48) & 3) == 1 )
    {
      v34 = -2147287035;
      if ( (unsigned int)CContext::Failed((CContext *)v40, &v34) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_93;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v11 = 3012617;
          LODWORD(Srca) = 2942;
          goto LABEL_10;
        }
        v12 = 2942;
        v13 = 3012617;
        goto LABEL_12;
      }
    }
    v34 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(**((_QWORD **)this + 21) + 40LL))(
            *((_QWORD *)this + 21),
            0,
            1,
            &v38);
    if ( (unsigned int)CContext::Failed((CContext *)v40, &v34) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_93;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v11 = 3016713;
        LODWORD(Srca) = 2946;
        goto LABEL_10;
      }
      v12 = 2946;
      v13 = 3016713;
      goto LABEL_12;
    }
    v14 = 0;
    v15 = v38 == 0;
    v16 = *((_DWORD *)this + 54);
    if ( v16 == 1200 )
    {
      v4 = Src;
      v35 = SysStringByteLen((BSTR)Src);
      if ( v15 )
      {
        v36 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, _QWORD))(**((_QWORD **)this + 21) + 32LL))(
                *((_QWORD *)this + 21),
                (char *)&g_ByteOrderMark + 2 * *((int *)this + 55),
                2,
                0);
        if ( (unsigned int)CContext::Failed((CContext *)v40, &v36) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_93;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v11 = 3051529;
            LODWORD(Srca) = 2980;
            goto LABEL_10;
          }
          v12 = 2980;
          v13 = 3051529;
          goto LABEL_12;
        }
      }
      if ( *((_DWORD *)this + 55) )
        CStream::TranslateByteOrder(v19, Src, (unsigned int)v35, 0, *((_DWORD *)this + 55));
    }
    else
    {
      if ( !v38 && v16 == 65001 )
      {
        v34 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 near **, __int64))(**((_QWORD **)this + 21) + 32LL))(
                *((_QWORD *)this + 21),
                &g_ByteOrderUTF8Mark,
                3);
        if ( (unsigned int)CContext::Failed((CContext *)v40, &v34) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_93;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v11 = 3024905;
            LODWORD(Srca) = 2954;
            goto LABEL_10;
          }
          v12 = 2954;
          v13 = 3024905;
          goto LABEL_12;
        }
      }
      v17 = SysStringLen((BSTR)Src);
      if ( v17 )
      {
        v18 = *((_DWORD *)this + 54);
        v36 = 2 * v17;
        v34 = CStream::ConvertString(this, &v37, 0x4B0u, v18, Src, &v36, v42, &v35);
        if ( v34 == -2146825037 )
        {
          if ( (unsigned int)CContext::FailedDescription((CContext *)v40, &v34, 0x272Eu) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_93;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
            {
              v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              v11 = 3037193;
              LODWORD(Srca) = 2966;
              goto LABEL_10;
            }
            v12 = 2966;
            v13 = 3037193;
            goto LABEL_12;
          }
        }
        else if ( (unsigned int)CContext::Failed((CContext *)v40, &v34) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_93;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v11 = 3039241;
            LODWORD(Srca) = 2968;
            goto LABEL_10;
          }
          v12 = 2968;
          v13 = 3039241;
          goto LABEL_12;
        }
        v4 = v42[0];
        v14 = 1;
      }
    }
    if ( v35
      && (v34 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, _QWORD))(**((_QWORD **)this + 21) + 32LL))(
                  *((_QWORD *)this + 21),
                  v4,
                  (unsigned int)v35,
                  0),
          (unsigned int)CContext::Failed((CContext *)v40, &v34)) )
    {
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_87:
        if ( v14 && v4 )
          MpHeapFree(g_hHeapHandle, v4);
        goto LABEL_90;
      }
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v20 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v21 = 3060745;
        LODWORD(Srca) = 2989;
LABEL_70:
        bidTraceW(off_18012A210[0], v21, L"<CStream::WriteText|ADO|ERR> %u#, line %d\n", v20, Srca);
        goto LABEL_87;
      }
      v22 = 2989;
      v23 = 3060745;
    }
    else
    {
      if ( a3 != 1 )
        goto LABEL_87;
      v24 = *((_DWORD *)this + 54);
      v25 = *((_DWORD *)this + 47);
      v26 = (v24 == 1200) + 1;
      if ( v25 == -1 )
      {
        v26 *= 2;
      }
      else if ( v25 != 10 && v25 != 13 )
      {
        v26 = 0;
      }
      v35 = v26;
      v27 = CStream::strEOL(this, 0);
      memcpy_0(v42, v27, v26);
      if ( v24 == 1200 && *((_DWORD *)this + 55) )
        CStream::TranslateByteOrder(v28, v42, v26, 0, *((_DWORD *)this + 55));
      v34 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 **, _QWORD, _QWORD))(**((_QWORD **)this + 21) + 32LL))(
              *((_QWORD *)this + 21),
              v42,
              v26,
              0);
      if ( !(unsigned int)CContext::Failed((CContext *)v40, &v34) || (bidGblFlags & 2) == 0 )
        goto LABEL_87;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v20 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v21 = 3074057;
        LODWORD(Srca) = 3002;
        goto LABEL_70;
      }
      v22 = 3002;
      v23 = 3074057;
    }
    bidTraceW(off_18012A210[0], v23, L"<CStream::WriteText|ADO|ERR>  line %d\n", v22);
    goto LABEL_87;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_93;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
  {
    v12 = 2915;
    v13 = 2984969;
    goto LABEL_12;
  }
  v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
  v11 = 2984969;
  LODWORD(Srca) = 2915;
LABEL_10:
  bidTraceW(off_18012A210[0], v11, L"<CStream::WriteText|ADO|ERR> %u#, line %d\n", v10, Srca);
LABEL_90:
  if ( (bidGblFlags & 2) != 0 && off_18012A8C8[0] )
  {
    v29 = v41;
    v30 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    LODWORD(Srca) = v29;
    bidTraceW(off_18012A210[0], 3082240, off_18012A8C8[0], v30, Srca);
  }
LABEL_93:
  if ( (bidGblFlags & 4) != 0 && v39 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v39);
  v31 = v41;
  CXLockContext::~CXLockContext((CXLockContext *)v40);
  return v31;
}

```

## disassembly

```asm
0x1800c1e30  mov     [rsp-8+arg_18], rbx
0x1800c1e35  push    rbp
0x1800c1e36  push    rsi
0x1800c1e37  push    rdi
0x1800c1e38  push    r12
0x1800c1e3a  push    r13
0x1800c1e3c  push    r14
0x1800c1e3e  push    r15
0x1800c1e40  lea     rbp, [rsp-27h]
0x1800c1e45  sub     rsp, 0B0h
0x1800c1e4c  mov     rax, cs:__security_cookie
0x1800c1e53  xor     rax, rsp
0x1800c1e56  mov     [rbp+57h+var_38], rax
0x1800c1e5a  mov     rax, rcx
0x1800c1e5d  mov     [rbp+57h+var_9C], 0
0x1800c1e64  xor     r15d, r15d
0x1800c1e67  mov     r12d, r8d
0x1800c1e6a  mov     r8, [rcx+90h]
0x1800c1e71  mov     rdi, rcx
0x1800c1e74  add     rcx, 20h ; ' '
0x1800c1e78  mov     [rbp+57h+var_48], r15
0x1800c1e7c  mov     r14, rdx
0x1800c1e7f  mov     [rbp+57h+var_90], r15
0x1800c1e83  add     r8, 8; struct CCriticalSection **
0x1800c1e87  mov     [rbp+57h+var_94], r15d
0x1800c1e8b  neg     rax
0x1800c1e8e  sbb     rdx, rdx
0x1800c1e91  and     rdx, rcx; struct CStdComObjectRoot *
0x1800c1e94  lea     rcx, [rbp+57h+var_80]; this
0x1800c1e98  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800c1e9d  test    byte ptr cs:_bidGblFlags, 4
0x1800c1ea4  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFFh
0x1800c1eac  jz      short loc_1800C1EDC
0x1800c1eae  mov     rax, cs:off_18012AD88; "<CStream::WriteText|API|ADO> %u#, write"...
0x1800c1eb5  test    rax, rax
0x1800c1eb8  jz      short loc_1800C1EDC
0x1800c1eba  lea     rcx, [rdi+98h]; this
0x1800c1ec1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c1ec6  mov     rdx, cs:off_18012AD88; "<CStream::WriteText|API|ADO> %u#, write"...
0x1800c1ecd  lea     rcx, [rbp+57h+var_88]
0x1800c1ed1  mov     r9d, r12d
0x1800c1ed4  mov     r8d, eax
0x1800c1ed7  call    _bidScopeEnterW
0x1800c1edc  test    r14, r14
0x1800c1edf  jz      short loc_1800C1EEB
0x1800c1ee1  cmp     r12d, 1
0x1800c1ee5  jbe     loc_1800C1F7B
0x1800c1eeb  lea     rdx, [rbp+57h+var_A0]; int *
0x1800c1eef  mov     [rbp+57h+var_A0], 800A0BB9h
0x1800c1ef6  lea     rcx, [rbp+57h+var_80]; this
0x1800c1efa  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c1eff  test    eax, eax
0x1800c1f01  jz      short loc_1800C1F7B
0x1800c1f03  mov     ebx, 2
0x1800c1f08  test    byte ptr cs:_bidGblFlags, bl
0x1800c1f0e  jz      loc_1800C25E0
0x1800c1f14  lea     rsi, [rdi+98h]
0x1800c1f1b  mov     rcx, rsi; this
0x1800c1f1e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c1f23  cmp     eax, 0FFFFFFFFh
0x1800c1f26  jz      short loc_1800C1F58
0x1800c1f28  mov     rcx, rsi; this
0x1800c1f2b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c1f30  mov     edx, 2D8C09h
0x1800c1f35  mov     dword ptr [rsp+0E0h+Src], 0B63h
0x1800c1f3d  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800c1f44  lea     r8, aCstreamWritete_2; "<CStream::WriteText|ADO|ERR> %u#, line "...
0x1800c1f4b  mov     r9d, eax
0x1800c1f4e  call    _bidTraceW
0x1800c1f53  jmp     loc_1800C259E
0x1800c1f58  mov     r9d, 0B63h
0x1800c1f5e  mov     edx, 2D8C09h
0x1800c1f63  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800c1f6a  lea     r8, aCstreamWritete_0; "<CStream::WriteText|ADO|ERR>  line %d\n"
0x1800c1f71  call    _bidTraceW
0x1800c1f76  jmp     loc_1800C259E
0x1800c1f7b  cmp     [rdi+0A8h], r15
0x1800c1f82  jnz     short loc_1800C1FEB
0x1800c1f84  lea     rdx, [rbp+57h+var_A0]; int *
0x1800c1f88  mov     [rbp+57h+var_A0], 800A0E78h
0x1800c1f8f  lea     rcx, [rbp+57h+var_80]; this
0x1800c1f93  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c1f98  test    eax, eax
0x1800c1f9a  jz      short loc_1800C1FEB
0x1800c1f9c  mov     ebx, 2
0x1800c1fa1  test    byte ptr cs:_bidGblFlags, bl
0x1800c1fa7  jz      loc_1800C25E0
0x1800c1fad  lea     rsi, [rdi+98h]
0x1800c1fb4  mov     rcx, rsi; this
0x1800c1fb7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c1fbc  cmp     eax, 0FFFFFFFFh
0x1800c1fbf  jz      short loc_1800C1FDB
0x1800c1fc1  mov     rcx, rsi; this
0x1800c1fc4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c1fc9  mov     edx, 2DA409h
0x1800c1fce  mov     dword ptr [rsp+0E0h+Src], 0B69h
0x1800c1fd6  jmp     loc_1800C1F3D
0x1800c1fdb  mov     r9d, 0B69h
0x1800c1fe1  mov     edx, 2DA409h
0x1800c1fe6  jmp     loc_1800C1F63
0x1800c1feb  mov     ebx, 2
0x1800c1ff0  cmp     [rdi+0B8h], ebx
0x1800c1ff6  jz      short loc_1800C205A
0x1800c1ff8  lea     rdx, [rbp+57h+var_A0]; int *
0x1800c1ffc  mov     [rbp+57h+var_A0], 800A0C93h
0x1800c2003  lea     rcx, [rbp+57h+var_80]; this
0x1800c2007  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c200c  test    eax, eax
0x1800c200e  jz      short loc_1800C205A
0x1800c2010  test    byte ptr cs:_bidGblFlags, bl
0x1800c2016  jz      loc_1800C25E0
0x1800c201c  lea     rsi, [rdi+98h]
0x1800c2023  mov     rcx, rsi; this
0x1800c2026  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c202b  cmp     eax, 0FFFFFFFFh
0x1800c202e  jz      short loc_1800C204A
0x1800c2030  mov     rcx, rsi; this
0x1800c2033  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c2038  mov     edx, 2DE409h
0x1800c203d  mov     dword ptr [rsp+0E0h+Src], 0B79h
0x1800c2045  jmp     loc_1800C1F3D
0x1800c204a  mov     r9d, 0B79h
0x1800c2050  mov     edx, 2DE409h
0x1800c2055  jmp     loc_1800C1F63
0x1800c205a  mov     eax, [rdi+0C0h]
0x1800c2060  and     al, 3
0x1800c2062  cmp     al, 1
0x1800c2064  jnz     short loc_1800C20C8
0x1800c2066  lea     rdx, [rbp+57h+var_A0]; int *
0x1800c206a  mov     [rbp+57h+var_A0], 80030005h
0x1800c2071  lea     rcx, [rbp+57h+var_80]; this
0x1800c2075  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c207a  test    eax, eax
0x1800c207c  jz      short loc_1800C20C8
0x1800c207e  test    byte ptr cs:_bidGblFlags, bl
0x1800c2084  jz      loc_1800C25E0
0x1800c208a  lea     rsi, [rdi+98h]
0x1800c2091  mov     rcx, rsi; this
0x1800c2094  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c2099  cmp     eax, 0FFFFFFFFh
0x1800c209c  jz      short loc_1800C20B8
0x1800c209e  mov     rcx, rsi; this
0x1800c20a1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c20a6  mov     edx, 2DF809h
0x1800c20ab  mov     dword ptr [rsp+0E0h+Src], 0B7Eh
0x1800c20b3  jmp     loc_1800C1F3D
0x1800c20b8  mov     r9d, 0B7Eh
0x1800c20be  mov     edx, 2DF809h
0x1800c20c3  jmp     loc_1800C1F63
0x1800c20c8  mov     rcx, [rdi+0A8h]
0x1800c20cf  lea     r9, [rbp+57h+var_90]
0x1800c20d3  xor     edx, edx
0x1800c20d5  mov     rax, [rcx]
0x1800c20d8  lea     r8d, [rdx+1]
0x1800c20dc  mov     rax, [rax+28h]
0x1800c20e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c20e5  lea     rdx, [rbp+57h+var_A0]; int *
0x1800c20e9  mov     [rbp+57h+var_A0], eax
0x1800c20ec  lea     rcx, [rbp+57h+var_80]; this
0x1800c20f0  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c20f5  test    eax, eax
0x1800c20f7  jz      short loc_1800C2143
0x1800c20f9  test    byte ptr cs:_bidGblFlags, bl
0x1800c20ff  jz      loc_1800C25E0
0x1800c2105  lea     rsi, [rdi+98h]
0x1800c210c  mov     rcx, rsi; this
0x1800c210f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c2114  cmp     eax, 0FFFFFFFFh
0x1800c2117  jz      short loc_1800C2133
0x1800c2119  mov     rcx, rsi; this
0x1800c211c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c2121  mov     edx, 2E0809h
0x1800c2126  mov     dword ptr [rsp+0E0h+Src], 0B82h
0x1800c212e  jmp     loc_1800C1F3D
0x1800c2133  mov     r9d, 0B82h
0x1800c2139  mov     edx, 2E0809h
0x1800c213e  jmp     loc_1800C1F63
0x1800c2143  xor     r13d, r13d
0x1800c2146  cmp     dword ptr [rbp+57h+var_90+4], r13d
0x1800c214a  jnz     short loc_1800C2157
0x1800c214c  cmp     dword ptr [rbp+57h+var_90], r13d
0x1800c2150  jnz     short loc_1800C2157
0x1800c2152  mov     sil, 1
0x1800c2155  jmp     short loc_1800C215A
0x1800c2157  xor     sil, sil
0x1800c215a  mov     eax, [rdi+0D8h]
0x1800c2160  cmp     eax, 4B0h
0x1800c2165  jz      loc_1800C2320
0x1800c216b  test    sil, sil
0x1800c216e  jz      loc_1800C21FA
0x1800c2174  cmp     eax, 0FDE9h
0x1800c2179  jnz     short loc_1800C21FA
0x1800c217b  mov     rcx, [rdi+0A8h]
0x1800c2182  lea     rdx, ?g_ByteOrderUTF8Mark@@3PAEA; uchar near * g_ByteOrderUTF8Mark
0x1800c2189  xor     r9d, r9d
0x1800c218c  mov     rax, [rcx]
0x1800c218f  lea     r8d, [r9+3]
0x1800c2193  mov     rax, [rax+20h]
0x1800c2197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c219c  lea     rdx, [rbp+57h+var_A0]; int *
0x1800c21a0  mov     [rbp+57h+var_A0], eax
0x1800c21a3  lea     rcx, [rbp+57h+var_80]; this
0x1800c21a7  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c21ac  test    eax, eax
0x1800c21ae  jz      short loc_1800C21FA
0x1800c21b0  test    byte ptr cs:_bidGblFlags, bl
0x1800c21b6  jz      loc_1800C25E0
0x1800c21bc  lea     rsi, [rdi+98h]
0x1800c21c3  mov     rcx, rsi; this
0x1800c21c6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c21cb  cmp     eax, 0FFFFFFFFh
0x1800c21ce  jz      short loc_1800C21EA
0x1800c21d0  mov     rcx, rsi; this
0x1800c21d3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c21d8  mov     edx, 2E2809h
0x1800c21dd  mov     dword ptr [rsp+0E0h+Src], 0B8Ah
0x1800c21e5  jmp     loc_1800C1F3D
0x1800c21ea  mov     r9d, 0B8Ah
0x1800c21f0  mov     edx, 2E2809h
0x1800c21f5  jmp     loc_1800C1F63
0x1800c21fa  mov     rcx, r14; pbstr
0x1800c21fd  call    cs:__imp_SysStringLen
0x1800c2204  nop     dword ptr [rax+rax+00h]
0x1800c2209  test    eax, eax
0x1800c220b  jz      loc_1800C23E4
0x1800c2211  mov     r9d, [rdi+0D8h]; unsigned int
0x1800c2218  lea     rdx, [rbp+57h+var_94]; unsigned int *
0x1800c221c  add     eax, eax
0x1800c221e  mov     r8d, 4B0h; unsigned int
0x1800c2224  mov     [rbp+57h+var_98], eax
0x1800c2227  mov     rcx, rdi; this
0x1800c222a  lea     rax, [rbp+57h+var_9C]
0x1800c222e  mov     [rsp+0E0h+var_A8], rax; int *
0x1800c2233  lea     rax, [rbp+57h+var_48]
0x1800c2237  mov     [rsp+0E0h+var_B0], rax; unsigned __int8 **
0x1800c223c  lea     rax, [rbp+57h+var_98]
0x1800c2240  mov     [rsp+0E0h+var_B8], rax; int *
0x1800c2245  mov     [rsp+0E0h+Src], r14; Src
0x1800c224a  call    ?ConvertString@CStream@@AEAAJPEAKKKPEAEPEAHPEAPEAE2@Z; CStream::ConvertString(ulong *,ulong,ulong,uchar *,int *,uchar * *,int *)
0x1800c224f  mov     [rbp+57h+var_A0], eax
0x1800c2252  lea     rdx, [rbp+57h+var_A0]; int *
0x1800c2256  lea     rcx, [rbp+57h+var_80]; this
0x1800c225a  cmp     eax, 800A0CB3h
0x1800c225f  jnz     short loc_1800C22BE
0x1800c2261  mov     r8d, 272Eh; unsigned int
0x1800c2267  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x1800c226c  test    eax, eax
0x1800c226e  jz      loc_1800C2311
0x1800c2274  test    byte ptr cs:_bidGblFlags, bl
0x1800c227a  jz      loc_1800C25E0
0x1800c2280  lea     rsi, [rdi+98h]
0x1800c2287  mov     rcx, rsi; this
0x1800c228a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c228f  cmp     eax, 0FFFFFFFFh
0x1800c2292  jz      short loc_1800C22AE
0x1800c2294  mov     rcx, rsi; this
0x1800c2297  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c229c  mov     edx, 2E5809h
0x1800c22a1  mov     dword ptr [rsp+0E0h+Src], 0B96h
0x1800c22a9  jmp     loc_1800C1F3D
0x1800c22ae  mov     r9d, 0B96h
0x1800c22b4  mov     edx, 2E5809h
0x1800c22b9  jmp     loc_1800C1F63
0x1800c22be  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c22c3  test    eax, eax
0x1800c22c5  jz      short loc_1800C2311
0x1800c22c7  test    byte ptr cs:_bidGblFlags, bl
0x1800c22cd  jz      loc_1800C25E0
0x1800c22d3  lea     rsi, [rdi+98h]
0x1800c22da  mov     rcx, rsi; this
0x1800c22dd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c22e2  cmp     eax, 0FFFFFFFFh
0x1800c22e5  jz      short loc_1800C2301
0x1800c22e7  mov     rcx, rsi; this
0x1800c22ea  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c22ef  mov     edx, 2E6009h
0x1800c22f4  mov     dword ptr [rsp+0E0h+Src], 0B98h
0x1800c22fc  jmp     loc_1800C1F3D
0x1800c2301  mov     r9d, 0B98h
0x1800c2307  mov     edx, 2E6009h
0x1800c230c  jmp     loc_1800C1F63
0x1800c2311  mov     r15, [rbp+57h+var_48]
0x1800c2315  mov     r13d, 1
0x1800c231b  jmp     loc_1800C23E4
0x1800c2320  mov     rcx, r14; bstr
0x1800c2323  mov     r15, r14
0x1800c2326  call    cs:__imp_SysStringByteLen
0x1800c232d  nop     dword ptr [rax+rax+00h]
0x1800c2332  mov     [rbp+57h+var_9C], eax
0x1800c2335  test    sil, sil
0x1800c2338  jz      loc_1800C23C7
0x1800c233e  movsxd  rax, dword ptr [rdi+0DCh]
0x1800c2345  lea     rdx, ?g_ByteOrderMark@@3PAY01EA; uchar (near * g_ByteOrderMark)[2]
0x1800c234c  mov     rcx, [rdi+0A8h]
0x1800c2353  xor     r9d, r9d
0x1800c2356  lea     rdx, [rdx+rax*2]
0x1800c235a  mov     r8, [rcx]
0x1800c235d  mov     rax, [r8+20h]
0x1800c2361  mov     r8d, ebx
0x1800c2364  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
