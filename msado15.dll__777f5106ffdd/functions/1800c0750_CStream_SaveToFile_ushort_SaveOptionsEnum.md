# CStream::SaveToFile(ushort *,SaveOptionsEnum)

- ea: `0x1800c0750`
- end: `0x1800c11d3`
- name: `?SaveToFile@CStream@@UEAAJPEAGW4SaveOptionsEnum@@@Z`
- size: `2691`
- prototype: `int(CStream *__hidden this, unsigned __int16 *, enum SaveOptionsEnum)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800a03b0`

## callees

- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x180057bdc`
- `0x18005ce08`
- `0x18006a22c`
- `0x1800bc204`
- `0x1800bc238`
- `0x1800c0750`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800ca894`
- `0x1800caa28`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!GetFileType` at `0x1800c0c94`
- `KERNEL32!GetFileType` at `0x1800c0c94`
- `KERNEL32!CreateFileW` at `0x1800c0c16`
- `KERNEL32!CreateFileW` at `0x1800c0c16`
- `KERNEL32!WriteFile` at `0x1800c0ef8`
- `KERNEL32!WriteFile` at `0x1800c0fc4`
- `KERNEL32!WriteFile` at `0x1800c105b`
- `KERNEL32!WriteFile` at `0x1800c0ef8`
- `KERNEL32!WriteFile` at `0x1800c0fc4`
- `KERNEL32!WriteFile` at `0x1800c105b`
- `KERNEL32!CloseHandle` at `0x1800c0d08`
- `KERNEL32!CloseHandle` at `0x1800c0d08`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0d17`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0d17`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c0816`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c0816`

## pseudocode

```c
__int64 __fastcall CStream::SaveToFile(CStream *this, unsigned __int16 *a2, DWORD a3)
{
  unsigned int BidObjectID; // eax
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdx
  OLECHAR *v11; // r15
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rdx
  unsigned __int16 *v16; // rdx
  HANDLE FileW; // r14
  DWORD FileType; // eax
  unsigned int v19; // eax
  __int64 v20; // rdx
  DWORD v21; // ebx
  unsigned int v22; // eax
  DWORD v23; // ebx
  __int64 v25; // r9
  __int64 v26; // rdx
  CStream *v27; // rcx
  DWORD v28; // r11d
  int *v29; // r8
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+44h] [rbp-BCh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v36[40]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v37; // [rsp+88h] [rbp-78h]
  unsigned __int8 Buffer[2048]; // [rsp+A0h] [rbp-60h] BYREF

  CXLockContext::CXLockContext(
    (CXLockContext *)v36,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 18) + 8LL),
    (const char *)this + 32);
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  v34 = 0;
  v35 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012ADB0[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    bidScopeEnterW(&v35, off_18012ADB0[0], BidObjectID, a2, a3);
  }
  if ( a2 && SysStringLen(a2) || (v31 = -2146825287, !(unsigned int)CContext::Failed((CContext *)v36, &v31)) )
  {
    if ( a3 - 1 > 1 )
    {
      v31 = -2146825287;
      if ( (unsigned int)CContext::Failed((CContext *)v36, &v31) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_71;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v8 = 2472969;
          dwCreationDisposition[0] = 2415;
          goto LABEL_10;
        }
        v9 = 2415;
        v10 = 2472969;
LABEL_12:
        bidTraceW(off_18012A210[0], v10, L"<CStream::SaveToFile|ADO|ERR>  line %d\n", v9);
        goto LABEL_68;
      }
    }
    v11 = 0;
    if ( !*((_QWORD *)this + 21) )
    {
      v31 = -2146824584;
      if ( (unsigned int)CContext::Failed((CContext *)v36, &v31) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_66;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v13 = 2479113;
          dwCreationDisposition[0] = 2421;
LABEL_24:
          bidTraceW(
            off_18012A210[0],
            v13,
            L"<CStream::SaveToFile|ADO|ERR> %u#, line %d\n",
            v12,
            *(_QWORD *)dwCreationDisposition);
          goto LABEL_66;
        }
        v14 = 2421;
        v15 = 2479113;
        goto LABEL_26;
      }
    }
    if ( (*((_DWORD *)this + 48) & 3) == 2 )
    {
      v31 = -2146825069;
      if ( (unsigned int)CContext::Failed((CContext *)v36, &v31) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v13 = 2495497;
            dwCreationDisposition[0] = 2437;
            goto LABEL_24;
          }
          v14 = 2437;
          v15 = 2495497;
          goto LABEL_26;
        }
LABEL_66:
        SysFreeString(v11);
        if ( v34 )
        {
          ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->Release)(v34);
          v34 = 0;
        }
        goto LABEL_68;
      }
    }
    (*(void (__fastcall **)(char *, GUID *, struct IUnknown **))(*((_QWORD *)this + 12) + 32LL))(
      (char *)this + 96,
      &IID_IUnknown,
      &v34);
    if ( (*((_BYTE *)this + 128) & 3) != 0 && !*((_QWORD *)this + 15)
      || (v16 = (unsigned __int16 *)*((_QWORD *)this + 15)) != 0
      && (int)SecurityCheck(a2, v16) < 0
      && (unsigned int)SecurityDialog(v34, *((unsigned __int16 **)this + 15), 1) )
    {
      v31 = -2146824572;
      if ( (unsigned int)CContext::Failed((CContext *)v36, &v31) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_66;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v13 = 2504713;
          dwCreationDisposition[0] = 2446;
          goto LABEL_24;
        }
        v14 = 2446;
        v15 = 2504713;
        goto LABEL_26;
      }
    }
    v11 = UNCEnable(a2);
    if ( !v11 )
    {
      v31 = -2147024882;
      if ( (unsigned int)CContext::Failed((CContext *)v36, &v31) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_66;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v13 = 2513929;
          dwCreationDisposition[0] = 2455;
          goto LABEL_24;
        }
        v14 = 2455;
        v15 = 2513929;
        goto LABEL_26;
      }
    }
    v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 21) + 40LL))(
            *((_QWORD *)this + 21),
            0,
            0,
            0);
    if ( (unsigned int)CContext::Failed((CContext *)v36, &v31) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_66;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v13 = 2519049;
        dwCreationDisposition[0] = 2460;
        goto LABEL_24;
      }
      v14 = 2460;
      v15 = 2519049;
      goto LABEL_26;
    }
    FileW = CreateFileW(v11, 0x40000000u, 0, 0, a3, 0x8000080u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      v31 = -2146825284;
      if ( (unsigned int)CContext::Failed((CContext *)v36, &v31) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_66;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v13 = 2528265;
          dwCreationDisposition[0] = 2469;
          goto LABEL_24;
        }
        v14 = 2469;
        v15 = 2528265;
LABEL_26:
        bidTraceW(off_18012A210[0], v15, L"<CStream::SaveToFile|ADO|ERR>  line %d\n", v14);
        goto LABEL_66;
      }
    }
    FileType = GetFileType(FileW);
    if ( (unsigned int)CContext::OpFailed((CContext *)v36, FileType == 1) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v19 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v20 = 2532361;
          dwCreationDisposition[0] = 2473;
LABEL_64:
          bidTraceW(
            off_18012A210[0],
            v20,
            L"<CStream::SaveToFile|ADO|ERR> %u#, line %d\n",
            v19,
            *(_QWORD *)dwCreationDisposition);
          goto LABEL_65;
        }
        v25 = 2473;
        v26 = 2532361;
        goto LABEL_77;
      }
    }
    else
    {
      v31 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, __int64, DWORD *))(**((_QWORD **)this + 21) + 24LL))(
              *((_QWORD *)this + 21),
              Buffer,
              2048,
              &nNumberOfBytesToWrite);
      if ( (unsigned int)CContext::Failed((CContext *)v36, &v31) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_65;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v19 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v20 = 2535433;
          dwCreationDisposition[0] = 2476;
          goto LABEL_64;
        }
        v25 = 2476;
        v26 = 2535433;
LABEL_77:
        bidTraceW(off_18012A210[0], v26, L"<CStream::SaveToFile|ADO|ERR>  line %d\n", v25);
        goto LABEL_65;
      }
      v28 = nNumberOfBytesToWrite;
      if ( *((_DWORD *)this + 46) != 2 )
        goto LABEL_104;
      if ( *((_DWORD *)this + 54) == 1200
        && nNumberOfBytesToWrite >= 2
        && !CStream::CheckUnicodeByteOrderMark(v27, Buffer, (CStream *)((char *)this + 220)) )
      {
        if ( WriteFile(FileW, (char *)&g_ByteOrderMark + 2 * *v29, 2u, &NumberOfBytesWritten, 0) )
          goto LABEL_103;
        v31 = -2146825284;
        if ( !(unsigned int)CContext::Failed((CContext *)v36, &v31) )
          goto LABEL_103;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_65;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v19 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v20 = 2543625;
          dwCreationDisposition[0] = 2484;
          goto LABEL_64;
        }
        v25 = 2484;
        v26 = 2543625;
        goto LABEL_77;
      }
      if ( *((_DWORD *)this + 46) != 2
        || *((_DWORD *)this + 54) != 65001
        || v28 < 3
        || (unsigned int)CheckUTF8Mark(Buffer) )
      {
        goto LABEL_104;
      }
      if ( WriteFile(FileW, &g_ByteOrderUTF8Mark, 3u, &NumberOfBytesWritten, 0)
        || (v31 = -2146825284, !(unsigned int)CContext::Failed((CContext *)v36, &v31)) )
      {
LABEL_103:
        while ( 1 )
        {
          v28 = nNumberOfBytesToWrite;
LABEL_104:
          if ( !v28 )
            break;
          if ( !WriteFile(FileW, Buffer, v28, &NumberOfBytesWritten, 0) )
          {
            v31 = -2146825284;
            if ( (unsigned int)CContext::Failed((CContext *)v36, &v31) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_65;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
              {
                v19 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                v20 = 2562057;
                dwCreationDisposition[0] = 2502;
                goto LABEL_64;
              }
              v25 = 2502;
              v26 = 2562057;
              goto LABEL_77;
            }
          }
          v31 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, __int64, DWORD *))(**((_QWORD **)this + 21) + 24LL))(
                  *((_QWORD *)this + 21),
                  Buffer,
                  2048,
                  &nNumberOfBytesToWrite);
          if ( (unsigned int)CContext::Failed((CContext *)v36, &v31) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_65;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
            {
              v19 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              v20 = 2565129;
              dwCreationDisposition[0] = 2505;
              goto LABEL_64;
            }
            v25 = 2505;
            v26 = 2565129;
            goto LABEL_77;
          }
        }
        v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 21) + 40LL))(
                *((_QWORD *)this + 21),
                0,
                0,
                0);
        if ( !(unsigned int)CContext::Failed((CContext *)v36, &v31) )
          goto LABEL_65;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_66;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v13 = 2570249;
          dwCreationDisposition[0] = 2510;
          goto LABEL_24;
        }
        v14 = 2510;
        v15 = 2570249;
        goto LABEL_26;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v19 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v20 = 2551817;
          dwCreationDisposition[0] = 2492;
          goto LABEL_64;
        }
        v25 = 2492;
        v26 = 2551817;
        goto LABEL_77;
      }
    }
LABEL_65:
    CloseHandle(FileW);
    goto LABEL_66;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_71;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
  {
    v9 = 2406;
    v10 = 2463753;
    goto LABEL_12;
  }
  v7 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
  v8 = 2463753;
  dwCreationDisposition[0] = 2406;
LABEL_10:
  bidTraceW(off_18012A210[0], v8, L"<CStream::SaveToFile|ADO|ERR> %u#, line %d\n", v7, *(_QWORD *)dwCreationDisposition);
LABEL_68:
  if ( (bidGblFlags & 2) != 0 && off_18012A928[0] )
  {
    v21 = v37;
    v22 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    dwCreationDisposition[0] = v21;
    bidTraceW(off_18012A210[0], 2578432, off_18012A928[0], v22, *(_QWORD *)dwCreationDisposition);
  }
LABEL_71:
  if ( (bidGblFlags & 4) != 0 && v35 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v35);
  v23 = v37;
  CXLockContext::~CXLockContext((CXLockContext *)v36);
  return v23;
}

```

## disassembly

```asm
0x1800c0750  mov     [rsp-8+arg_18], rbx
0x1800c0755  push    rbp
0x1800c0756  push    rsi
0x1800c0757  push    rdi
0x1800c0758  push    r14
0x1800c075a  push    r15
0x1800c075c  lea     rbp, [rsp-7B0h]
0x1800c0764  sub     rsp, 8B0h
0x1800c076b  mov     rax, cs:__security_cookie
0x1800c0772  xor     rax, rsp
0x1800c0775  mov     [rbp+7D0h+var_30], rax
0x1800c077c  mov     r14d, r8d
0x1800c077f  lea     r9, [rcx+20h]; char *
0x1800c0783  mov     r8, [rcx+90h]
0x1800c078a  mov     rax, rcx
0x1800c078d  mov     rsi, rdx
0x1800c0790  add     r8, 8; struct CCriticalSection **
0x1800c0794  neg     rax
0x1800c0797  mov     rdi, rcx
0x1800c079a  lea     rcx, [rsp+8D0h+var_870]; this
0x1800c079f  sbb     rdx, rdx
0x1800c07a2  and     rdx, r9; struct CStdComObjectRoot *
0x1800c07a5  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800c07aa  test    byte ptr cs:_bidGblFlags, 4
0x1800c07b1  mov     [rsp+8D0h+nNumberOfBytesToWrite], 0
0x1800c07b9  mov     [rsp+8D0h+NumberOfBytesWritten], 0
0x1800c07c1  mov     [rsp+8D0h+var_880], 0
0x1800c07ca  mov     [rsp+8D0h+var_878], 0FFFFFFFFFFFFFFFFh
0x1800c07d3  jz      short loc_1800C0809
0x1800c07d5  mov     rax, cs:off_18012ADB0; "<CStream::SaveToFile|API|ADO> %u#, File"...
0x1800c07dc  test    rax, rax
0x1800c07df  jz      short loc_1800C0809
0x1800c07e1  lea     rcx, [rdi+98h]; this
0x1800c07e8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c07ed  mov     rdx, cs:off_18012ADB0; "<CStream::SaveToFile|API|ADO> %u#, File"...
0x1800c07f4  lea     rcx, [rsp+8D0h+var_878]
0x1800c07f9  mov     r9, rsi
0x1800c07fc  mov     [rsp+8D0h+dwCreationDisposition], r14d
0x1800c0801  mov     r8d, eax
0x1800c0804  call    _bidScopeEnterW
0x1800c0809  mov     ebx, 800A0BB9h
0x1800c080e  test    rsi, rsi
0x1800c0811  jz      short loc_1800C082A
0x1800c0813  mov     rcx, rsi; pbstr
0x1800c0816  call    cs:__imp_SysStringLen
0x1800c081d  nop     dword ptr [rax+rax+00h]
0x1800c0822  test    eax, eax
0x1800c0824  jnz     loc_1800C08B9
0x1800c082a  lea     rdx, [rsp+8D0h+var_890]; int *
0x1800c082f  mov     [rsp+8D0h+var_890], ebx
0x1800c0833  lea     rcx, [rsp+8D0h+var_870]; this
0x1800c0838  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c083d  test    eax, eax
0x1800c083f  jz      short loc_1800C08B9
0x1800c0841  mov     ebx, 2
0x1800c0846  test    byte ptr cs:_bidGblFlags, bl
0x1800c084c  jz      loc_1800C0D84
0x1800c0852  lea     rsi, [rdi+98h]
0x1800c0859  mov     rcx, rsi; this
0x1800c085c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0861  cmp     eax, 0FFFFFFFFh
0x1800c0864  jz      short loc_1800C0896
0x1800c0866  mov     rcx, rsi; this
0x1800c0869  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c086e  mov     edx, 259809h
0x1800c0873  mov     [rsp+8D0h+dwCreationDisposition], 966h
0x1800c087b  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800c0882  lea     r8, aCstreamSavetof_0; "<CStream::SaveToFile|ADO|ERR> %u#, line"...
0x1800c0889  mov     r9d, eax
0x1800c088c  call    _bidTraceW
0x1800c0891  jmp     loc_1800C0D42
0x1800c0896  mov     r9d, 966h
0x1800c089c  mov     edx, 259809h
0x1800c08a1  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800c08a8  lea     r8, aCstreamSavetof_1; "<CStream::SaveToFile|ADO|ERR>  line %d"...
0x1800c08af  call    _bidTraceW
0x1800c08b4  jmp     loc_1800C0D42
0x1800c08b9  lea     eax, [r14-1]
0x1800c08bd  cmp     eax, 1
0x1800c08c0  jbe     short loc_1800C0928
0x1800c08c2  lea     rdx, [rsp+8D0h+var_890]; int *
0x1800c08c7  mov     [rsp+8D0h+var_890], ebx
0x1800c08cb  lea     rcx, [rsp+8D0h+var_870]; this
0x1800c08d0  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c08d5  test    eax, eax
0x1800c08d7  jz      short loc_1800C0928
0x1800c08d9  mov     ebx, 2
0x1800c08de  test    byte ptr cs:_bidGblFlags, bl
0x1800c08e4  jz      loc_1800C0D84
0x1800c08ea  lea     rsi, [rdi+98h]
0x1800c08f1  mov     rcx, rsi; this
0x1800c08f4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c08f9  cmp     eax, 0FFFFFFFFh
0x1800c08fc  jz      short loc_1800C0918
0x1800c08fe  mov     rcx, rsi; this
0x1800c0901  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0906  mov     edx, 25BC09h
0x1800c090b  mov     [rsp+8D0h+dwCreationDisposition], 96Fh
0x1800c0913  jmp     loc_1800C087B
0x1800c0918  mov     r9d, 96Fh
0x1800c091e  mov     edx, 25BC09h
0x1800c0923  jmp     loc_1800C08A1
0x1800c0928  xor     r15d, r15d
0x1800c092b  cmp     [rdi+0A8h], r15
0x1800c0932  jnz     loc_1800C09CA
0x1800c0938  lea     rdx, [rsp+8D0h+var_890]; int *
0x1800c093d  mov     [rsp+8D0h+var_890], 800A0E78h
0x1800c0945  lea     rcx, [rsp+8D0h+var_870]; this
0x1800c094a  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c094f  test    eax, eax
0x1800c0951  jz      short loc_1800C09CA
0x1800c0953  lea     ebx, [r15+2]
0x1800c0957  test    byte ptr cs:_bidGblFlags, bl
0x1800c095d  jz      loc_1800C0D14
0x1800c0963  lea     rsi, [rdi+98h]
0x1800c096a  mov     rcx, rsi; this
0x1800c096d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0972  cmp     eax, 0FFFFFFFFh
0x1800c0975  jz      short loc_1800C09A7
0x1800c0977  mov     rcx, rsi; this
0x1800c097a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c097f  mov     edx, 25D409h
0x1800c0984  mov     [rsp+8D0h+dwCreationDisposition], 975h
0x1800c098c  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800c0993  lea     r8, aCstreamSavetof_0; "<CStream::SaveToFile|ADO|ERR> %u#, line"...
0x1800c099a  mov     r9d, eax
0x1800c099d  call    _bidTraceW
0x1800c09a2  jmp     loc_1800C0D14
0x1800c09a7  mov     r9d, 975h
0x1800c09ad  mov     edx, 25D409h
0x1800c09b2  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800c09b9  lea     r8, aCstreamSavetof_1; "<CStream::SaveToFile|ADO|ERR>  line %d"...
0x1800c09c0  call    _bidTraceW
0x1800c09c5  jmp     loc_1800C0D14
0x1800c09ca  mov     eax, [rdi+0C0h]
0x1800c09d0  mov     ebx, 2
0x1800c09d5  and     al, 3
0x1800c09d7  cmp     al, bl
0x1800c09d9  jnz     short loc_1800C0A40
0x1800c09db  lea     rdx, [rsp+8D0h+var_890]; int *
0x1800c09e0  mov     [rsp+8D0h+var_890], 800A0C93h
0x1800c09e8  lea     rcx, [rsp+8D0h+var_870]; this
0x1800c09ed  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c09f2  test    eax, eax
0x1800c09f4  jz      short loc_1800C0A40
0x1800c09f6  test    byte ptr cs:_bidGblFlags, bl
0x1800c09fc  jz      loc_1800C0D14
0x1800c0a02  lea     rsi, [rdi+98h]
0x1800c0a09  mov     rcx, rsi; this
0x1800c0a0c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0a11  cmp     eax, 0FFFFFFFFh
0x1800c0a14  jz      short loc_1800C0A30
0x1800c0a16  mov     rcx, rsi; this
0x1800c0a19  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0a1e  mov     edx, 261409h
0x1800c0a23  mov     [rsp+8D0h+dwCreationDisposition], 985h
0x1800c0a2b  jmp     loc_1800C098C
0x1800c0a30  mov     r9d, 985h
0x1800c0a36  mov     edx, 261409h
0x1800c0a3b  jmp     loc_1800C09B2
0x1800c0a40  lea     rcx, [rdi+60h]
0x1800c0a44  mov     rax, [rcx]
0x1800c0a47  lea     r8, [rsp+8D0h+var_880]
0x1800c0a4c  lea     rdx, IID_IUnknown
0x1800c0a53  mov     rax, [rax+20h]
0x1800c0a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0a5c  test    byte ptr [rdi+80h], 3
0x1800c0a63  jz      short loc_1800C0A6B
0x1800c0a65  cmp     [rdi+78h], r15
0x1800c0a69  jz      short loc_1800C0A9C
0x1800c0a6b  mov     rdx, [rdi+78h]; unsigned __int16 *
0x1800c0a6f  test    rdx, rdx
0x1800c0a72  jz      loc_1800C0B01
0x1800c0a78  mov     rcx, rsi; unsigned __int16 *
0x1800c0a7b  call    ?SecurityCheck@@YAJPEBGPEAG@Z; SecurityCheck(ushort const *,ushort *)
0x1800c0a80  test    eax, eax
0x1800c0a82  jns     short loc_1800C0B01
0x1800c0a84  mov     rdx, [rdi+78h]; unsigned __int16 *
0x1800c0a88  mov     r8d, 1; int
0x1800c0a8e  mov     rcx, [rsp+8D0h+var_880]; struct IUnknown *
0x1800c0a93  call    ?SecurityDialog@@YAJPEAUIUnknown@@PEAGH@Z; SecurityDialog(IUnknown *,ushort *,int)
0x1800c0a98  test    eax, eax
0x1800c0a9a  jz      short loc_1800C0B01
0x1800c0a9c  lea     rdx, [rsp+8D0h+var_890]; int *
0x1800c0aa1  mov     [rsp+8D0h+var_890], 800A0E84h
0x1800c0aa9  lea     rcx, [rsp+8D0h+var_870]; this
0x1800c0aae  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c0ab3  test    eax, eax
0x1800c0ab5  jz      short loc_1800C0B01
0x1800c0ab7  test    byte ptr cs:_bidGblFlags, bl
0x1800c0abd  jz      loc_1800C0D14
0x1800c0ac3  lea     rsi, [rdi+98h]
0x1800c0aca  mov     rcx, rsi; this
0x1800c0acd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0ad2  cmp     eax, 0FFFFFFFFh
0x1800c0ad5  jz      short loc_1800C0AF1
0x1800c0ad7  mov     rcx, rsi; this
0x1800c0ada  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0adf  mov     edx, 263809h
0x1800c0ae4  mov     [rsp+8D0h+dwCreationDisposition], 98Eh
0x1800c0aec  jmp     loc_1800C098C
0x1800c0af1  mov     r9d, 98Eh
0x1800c0af7  mov     edx, 263809h
0x1800c0afc  jmp     loc_1800C09B2
0x1800c0b01  mov     rcx, rsi; String2
0x1800c0b04  call    ?UNCEnable@@YAPEAGPEAG@Z; UNCEnable(ushort *)
0x1800c0b09  mov     r15, rax
0x1800c0b0c  test    rax, rax
0x1800c0b0f  jnz     short loc_1800C0B76
0x1800c0b11  lea     rdx, [rsp+8D0h+var_890]; int *
0x1800c0b16  mov     [rsp+8D0h+var_890], 8007000Eh
0x1800c0b1e  lea     rcx, [rsp+8D0h+var_870]; this
0x1800c0b23  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c0b28  test    eax, eax
0x1800c0b2a  jz      short loc_1800C0B76
0x1800c0b2c  test    byte ptr cs:_bidGblFlags, bl
0x1800c0b32  jz      loc_1800C0D14
0x1800c0b38  lea     rsi, [rdi+98h]
0x1800c0b3f  mov     rcx, rsi; this
0x1800c0b42  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0b47  cmp     eax, 0FFFFFFFFh
0x1800c0b4a  jz      short loc_1800C0B66
0x1800c0b4c  mov     rcx, rsi; this
0x1800c0b4f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0b54  mov     edx, 265C09h
0x1800c0b59  mov     [rsp+8D0h+dwCreationDisposition], 997h
0x1800c0b61  jmp     loc_1800C098C
0x1800c0b66  mov     r9d, 997h
0x1800c0b6c  mov     edx, 265C09h
0x1800c0b71  jmp     loc_1800C09B2
0x1800c0b76  mov     rcx, [rdi+0A8h]
0x1800c0b7d  xor     edx, edx
0x1800c0b7f  xor     r9d, r9d
0x1800c0b82  xor     r8d, r8d
0x1800c0b85  mov     rax, [rcx]
0x1800c0b88  mov     rax, [rax+28h]
0x1800c0b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0b91  lea     rdx, [rsp+8D0h+var_890]; int *
0x1800c0b96  mov     [rsp+8D0h+var_890], eax
0x1800c0b9a  lea     rcx, [rsp+8D0h+var_870]; this
0x1800c0b9f  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c0ba4  test    eax, eax
0x1800c0ba6  jz      short loc_1800C0BF2
0x1800c0ba8  test    byte ptr cs:_bidGblFlags, bl
0x1800c0bae  jz      loc_1800C0D14
0x1800c0bb4  lea     rsi, [rdi+98h]
0x1800c0bbb  mov     rcx, rsi; this
0x1800c0bbe  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0bc3  cmp     eax, 0FFFFFFFFh
0x1800c0bc6  jz      short loc_1800C0BE2
0x1800c0bc8  mov     rcx, rsi; this
0x1800c0bcb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0bd0  mov     edx, 267009h
0x1800c0bd5  mov     [rsp+8D0h+dwCreationDisposition], 99Ch
0x1800c0bdd  jmp     loc_1800C098C
0x1800c0be2  mov     r9d, 99Ch
0x1800c0be8  mov     edx, 267009h
0x1800c0bed  jmp     loc_1800C09B2
0x1800c0bf2  mov     [rsp+8D0h+hTemplateFile], 0; hTemplateFile
0x1800c0bfb  xor     r9d, r9d; lpSecurityAttributes
0x1800c0bfe  mov     [rsp+8D0h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x1800c0c06  xor     r8d, r8d; dwShareMode
0x1800c0c09  mov     edx, 40000000h; dwDesiredAccess
0x1800c0c0e  mov     [rsp+8D0h+dwCreationDisposition], r14d; dwCreationDisposition
0x1800c0c13  mov     rcx, r15; lpFileName
0x1800c0c16  call    cs:__imp_CreateFileW
0x1800c0c1d  nop     dword ptr [rax+rax+00h]
0x1800c0c22  mov     r14, rax
0x1800c0c25  mov     esi, 800A0BBCh
0x1800c0c2a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c0c2e  jnz     short loc_1800C0C91
0x1800c0c30  lea     rdx, [rsp+8D0h+var_890]; int *
0x1800c0c35  mov     [rsp+8D0h+var_890], esi
0x1800c0c39  lea     rcx, [rsp+8D0h+var_870]; this
0x1800c0c3e  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800c0c43  test    eax, eax
0x1800c0c45  jz      short loc_1800C0C91
0x1800c0c47  test    byte ptr cs:_bidGblFlags, bl
0x1800c0c4d  jz      loc_1800C0D14
0x1800c0c53  lea     rsi, [rdi+98h]
0x1800c0c5a  mov     rcx, rsi; this
0x1800c0c5d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0c62  cmp     eax, 0FFFFFFFFh
0x1800c0c65  jz      short loc_1800C0C81
0x1800c0c67  mov     rcx, rsi; this
0x1800c0c6a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800c0c6f  mov     edx, 269409h
0x1800c0c74  mov     [rsp+8D0h+dwCreationDisposition], 9A5h
0x1800c0c7c  jmp     loc_1800C098C
0x1800c0c81  mov     r9d, 9A5h
0x1800c0c87  mov     edx, 269409h
0x1800c0c8c  jmp     loc_1800C09B2
0x1800c0c91  mov     rcx, r14; hFile
0x1800c0c94  call    cs:__imp_GetFileType
0x1800c0c9b  nop     dword ptr [rax+rax+00h]
0x1800c0ca0  xor     edx, edx
0x1800c0ca2  lea     rcx, [rsp+8D0h+var_870]; this
0x1800c0ca7  cmp     eax, 1
0x1800c0caa  setz    dl; int
0x1800c0cad  call    ?OpFailed@CContext@@QEAAHH@Z; CContext::OpFailed(int)
  ... truncated ...
```
