# CStream::ReadText(long,ushort * *)

- ea: `0x18004e370`
- end: `0x18004f04b`
- name: `?ReadText@CStream@@UEAAJJPEAPEAG@Z`
- size: `3291`
- prototype: `__int64 __fastcall(CStream *__hidden this, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x18009faf0`

## callees

- `0x180020e20`
- `0x180020fc0`
- `0x18004e370`
- `0x18004f2b0`
- `0x180054098`
- `0x18006a22c`
- `0x1800bc204`
- `0x1800bc238`
- `0x1800bc554`
- `0x1800bc878`
- `0x1800bd930`
- `0x1800bdbec`
- `0x1800c1860`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800cdad2`
- `0x1800cdb20`
- `0x1800cdbe0`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x18004e47b`
- `MSDART!UMSEnterCSWraper` at `0x18004e47b`
- `MSDART!MpHeapFree` at `0x18004ef0f`
- `MSDART!MpHeapFree` at `0x18004ef0f`
- `KERNEL32!LeaveCriticalSection` at `0x18004efa1`
- `KERNEL32!LeaveCriticalSection` at `0x18004efa1`
- `KERNEL32!TlsSetValue` at `0x18004e45c`
- `KERNEL32!TlsSetValue` at `0x18004effd`
- `KERNEL32!TlsSetValue` at `0x18004e45c`
- `KERNEL32!TlsSetValue` at `0x18004effd`
- `KERNEL32!TlsGetValue` at `0x18004e40c`
- `KERNEL32!TlsGetValue` at `0x18004e40c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004ee84`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004ee84`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004efc7`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004efc7`

## string_xrefs

- `0x18004e658`: `<CStream::ReadText|ADO|ERR> %u#, line %d\n`
- `0x18004e969`: `<CStream::ReadText|ADO|ERR> %u#, line %d\n`
- `0x18004e532`: `<CStream::ReadText|ADO|ERR>  line %d\n`
- `0x18004eee9`: `<CStream::ReadText|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStream::ReadText(CStream *this, unsigned int a2, unsigned __int16 **a3)
{
  __int64 v4; // r15
  __int64 v6; // rsi
  _DWORD *Value; // rax
  char v8; // bl
  unsigned int BidObjectID; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rdx
  bool v14; // zf
  unsigned int v15; // eax
  CStream *v16; // rcx
  unsigned int v17; // r12d
  unsigned int v18; // r11d
  int v19; // r14d
  int v20; // r13d
  unsigned __int64 v21; // rsi
  unsigned int v22; // r11d
  __int64 v23; // rcx
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r9
  int v27; // r10d
  char *v28; // rbx
  unsigned int v29; // ecx
  __int64 v30; // rax
  __int64 v31; // r9
  __int64 v32; // rdx
  unsigned int v33; // r9d
  unsigned int v34; // r8d
  BSTR v35; // rax
  int v36; // ebx
  unsigned int v37; // eax
  unsigned int v38; // ebx
  __int64 v39; // rcx
  _DWORD *v40; // rax
  IErrorInfo *v41; // rdx
  unsigned __int16 *v43; // [rsp+20h] [rbp-E0h]
  unsigned int v44; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v45; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v46; // [rsp+58h] [rbp-A8h]
  size_t Size; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v48; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int8 *v49; // [rsp+68h] [rbp-98h] BYREF
  int v50; // [rsp+70h] [rbp-90h]
  __int64 v51; // [rsp+78h] [rbp-88h] BYREF
  int v52; // [rsp+80h] [rbp-80h] BYREF
  _DWORD *TlsValue; // [rsp+88h] [rbp-78h] BYREF
  int v54; // [rsp+90h] [rbp-70h]
  __int64 v55; // [rsp+98h] [rbp-68h]
  int v56; // [rsp+A0h] [rbp-60h]
  __int16 v57; // [rsp+A4h] [rbp-5Ch]
  char v58; // [rsp+A6h] [rbp-5Ah]
  unsigned __int64 v59; // [rsp+A8h] [rbp-58h]
  int v60; // [rsp+B0h] [rbp-50h]
  int v61; // [rsp+B4h] [rbp-4Ch]
  __int64 *v62; // [rsp+B8h] [rbp-48h]
  OLECHAR *strIn; // [rsp+C0h] [rbp-40h]
  unsigned int v64; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 **v66; // [rsp+D8h] [rbp-28h]
  unsigned __int8 v67[2048]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 Src[8192]; // [rsp+8E0h] [rbp+7E0h] BYREF

  v66 = a3;
  v4 = a2;
  v46 = 0;
  Size = 0;
  v48 = 0;
  v51 = 0;
  v6 = *((_QWORD *)this + 18) + 8LL;
  v59 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  v61 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v60 = 0;
  v8 = 1;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v54 = 1;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v62 = 0;
  UMSEnterCSWraper(v6);
  v62 = (__int64 *)v6;
  v64 = *((_DWORD *)this + 58);
  v65 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012ADA0[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    bidScopeEnterW(&v65, off_18012ADA0[0], BidObjectID, (unsigned int)v4, (_DWORD)v43);
  }
  if ( *((_DWORD *)this + 46) != 2 )
  {
    v60 = -2146825069;
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_137;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
    {
      v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      LODWORD(v43) = 2709;
      v11 = 2774025;
LABEL_31:
      bidTraceW(off_18012A210[0], v11, L"<CStream::ReadText|ADO|ERR> %u#, line %d\n", v10, v43);
      goto LABEL_134;
    }
    v12 = 2709;
    v13 = 2774025;
    goto LABEL_12;
  }
  if ( !a3 || (v14 = (_DWORD)v4 == -2, (int)v4 < -2) )
  {
    v44 = -2146825287;
    if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v44) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_137;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        LODWORD(v43) = 2714;
        v11 = 2779145;
        goto LABEL_31;
      }
      v12 = 2714;
      v13 = 2779145;
      goto LABEL_12;
    }
    v14 = (_DWORD)v4 == -2;
  }
  if ( v14 )
  {
    v15 = (*(__int64 (__fastcall **)(CStream *, unsigned __int16 **))(*(_QWORD *)this + 272LL))(this, a3);
LABEL_23:
    v44 = v15;
    CContext::Failed((CContext *)&TlsValue, (const int *)&v44);
    goto LABEL_134;
  }
  if ( (_DWORD)v4 == -1 )
  {
    v15 = (*(__int64 (__fastcall **)(CStream *, unsigned __int16 **))(*(_QWORD *)this + 280LL))(this, a3);
    goto LABEL_23;
  }
  if ( *((_QWORD *)this + 21)
    || (v44 = -2146824584, !(unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v44)) )
  {
    if ( (*((_DWORD *)this + 48) & 3) == 2
      && (v44 = -2146825069, (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v44)) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_137;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        LODWORD(v43) = 2746;
        v11 = 2811913;
        goto LABEL_31;
      }
      v12 = 2746;
      v13 = 2811913;
    }
    else
    {
      v44 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(**((_QWORD **)this + 21) + 40LL))(
              *((_QWORD *)this + 21),
              0,
              1,
              &v51);
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v44) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_137;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          LODWORD(v43) = 2750;
          v11 = 2816009;
          goto LABEL_31;
        }
        v12 = 2750;
        v13 = 2816009;
      }
      else
      {
        if ( v51 )
          v8 = 0;
        v44 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, __int64, char *))(**((_QWORD **)this + 21) + 24LL))(
                *((_QWORD *)this + 21),
                v67,
                2048,
                (char *)&Size + 4);
        if ( !(unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v44) )
        {
          strIn = 0;
          v17 = 0;
          v50 = 0;
          v18 = HIDWORD(Size);
          if ( *((_DWORD *)this + 54) == 1200
            && v8
            && HIDWORD(Size) >= 2
            && CStream::CheckUnicodeByteOrderMark(v16, v67, (CStream *)((char *)this + 220)) )
          {
            v19 = 2;
            LODWORD(v51) = 2;
          }
          else
          {
            v19 = 0;
            if ( *((_DWORD *)this + 54) == 65001 && v8 && v18 >= 3 && (unsigned int)CheckUTF8Mark(v67) )
            {
              v19 = 3;
              LODWORD(v51) = 3;
            }
          }
          v20 = *((_DWORD *)this + 54);
          v49 = (unsigned __int8 *)Src;
          LODWORD(v21) = v4;
          while ( 1 )
          {
            v22 = v18 - v19;
            if ( !v22 )
              goto LABEL_123;
            if ( !(v22 + v17) )
              goto LABEL_74;
            v48 = v22 + v17;
            LODWORD(Size) = 0x2000;
            v45 = CStream::ConvertString(
                    this,
                    &v64,
                    *((_DWORD *)this + 54),
                    0x4B0u,
                    &v67[v19],
                    (int *)&v48,
                    &v49,
                    (int *)&Size);
            if ( v45 == -2146825037 )
            {
              if ( (unsigned int)CContext::FailedDescription((CContext *)&TlsValue, (const int *)&v45, 0x272Eu) )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_132;
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
                {
                  v31 = 2781;
                  v32 = 2847753;
                  goto LABEL_131;
                }
                v24 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                LODWORD(v43) = 2781;
                v25 = 2847753;
                goto LABEL_69;
              }
            }
            else if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v45) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_132;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
              {
                v31 = 2783;
                v32 = 2849801;
                goto LABEL_131;
              }
              v24 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              LODWORD(v43) = 2783;
              v25 = 2849801;
              goto LABEL_69;
            }
            if ( *((_DWORD *)this + 54) == 1200 && (v26 = *((unsigned int *)this + 55), (_DWORD)v26) )
              CStream::TranslateByteOrder(v23, Src, (unsigned int)Size, v26, 0);
            else
LABEL_74:
              v27 = Size;
            v28 = (char *)MEMREALLOC(strIn, v27 + v46);
            if ( (unsigned int)CContext::MemFailed((CContext *)&TlsValue, v28) )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                {
                  v24 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                  LODWORD(v43) = 2791;
                  v25 = 2857993;
                  goto LABEL_69;
                }
                v31 = 2791;
                v32 = 2857993;
                goto LABEL_131;
              }
              goto LABEL_132;
            }
            strIn = (OLECHAR *)v28;
            memcpy_0(&v28[v46], Src, (unsigned int)Size);
            v29 = Size + v46;
            v46 = v29;
            v30 = 2 * v4;
            if ( v29 >= (unsigned __int64)(2 * v4) && &v28[v30] )
            {
              v45 = 0;
              v44 = 0;
              v33 = *((_DWORD *)this + 54);
              v34 = 2 * v4;
              if ( v33 == 1200 )
              {
                v45 = 2 * v4;
                goto LABEL_106;
              }
              if ( v20 == 50220 )
              {
                v52 = 0;
                LODWORD(v49) = CStream::ConvertEscapedString(
                                 this,
                                 &v44,
                                 Size + v30 - v29,
                                 v33,
                                 Src,
                                 (unsigned __int8)Size + (unsigned __int8)v30 - (unsigned __int8)v29,
                                 v67,
                                 v48,
                                 &v45,
                                 (enum ESCAPEMODE *)&v52);
                if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v49) )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_132;
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
                  {
                    v31 = 2855;
                    v32 = 2923529;
                    goto LABEL_131;
                  }
                  v24 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                  LODWORD(v43) = 2855;
                  v25 = 2923529;
                  goto LABEL_69;
                }
                v34 = v50 + v45;
                v45 += v50;
                if ( v52 )
                  *((_DWORD *)this + 58) = EscMode(*((unsigned int *)this + 54));
              }
              else
              {
                v46 = 2 * v4;
                HIDWORD(v43) = HIDWORD(v28);
                LODWORD(v49) = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, __int64))(**((_QWORD **)this + 28)
                                                                                          + 72LL))(
                                 *((_QWORD *)this + 28),
                                 &v44,
                                 1200);
                if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v49) )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_132;
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
                  {
                    v31 = 2870;
                    v32 = 2938889;
                    goto LABEL_131;
                  }
                  v24 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                  LODWORD(v43) = 2870;
                  v25 = 2938889;
                  goto LABEL_69;
                }
                v34 = v45;
              }
LABEL_106:
              LODWORD(v49) = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 21) + 40LL))(
                               *((_QWORD *)this + 21),
                               v51 + v34,
                               0,
                               0);
              if ( !(unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v49) )
              {
LABEL_123:
                v29 = v46;
LABEL_124:
                if ( v29 >> 1 < (unsigned int)v4 )
                  v21 = (unsigned __int64)v29 >> 1;
                v35 = SysAllocStringLen(strIn, v21);
                *v66 = v35;
                if ( (unsigned int)CContext::MemFailed((CContext *)&TlsValue, v35) && (bidGblFlags & 2) != 0 )
                {
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                  {
                    v24 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                    LODWORD(v43) = 2878;
                    v25 = 2947081;
                    goto LABEL_69;
                  }
                  v31 = 2878;
                  v32 = 2947081;
                  goto LABEL_131;
                }
                goto LABEL_132;
              }
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_132;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
              {
                v31 = 2875;
                v32 = 2944009;
                goto LABEL_131;
              }
              v24 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              LODWORD(v43) = 2875;
              v25 = 2944009;
LABEL_69:
              bidTraceW(off_18012A210[0], v25, L"<CStream::ReadText|ADO|ERR> %u#, line %d\n", v24, v43);
              goto LABEL_132;
            }
            if ( HIDWORD(Size) < 2048 - v17 )
              goto LABEL_124;
            if ( v20 == 50220 )
              v50 += v48;
            v17 += HIDWORD(Size) - v48 - v19;
            if ( v17 > 0x800 )
            {
              v44 = -2147024882;
              if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v44) )
                break;
            }
            memcpy_0(v67, (char *)Src - v17, v17);
            v44 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, char *))(**((_QWORD **)this + 21) + 24LL))(
                    *((_QWORD *)this + 21),
                    &v67[v17],
                    2048 - v17,
                    (char *)&Size + 4);
            if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v44) )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                {
                  v24 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                  LODWORD(v43) = 2822;
                  v25 = 2889737;
                  goto LABEL_69;
                }
                v31 = 2822;
                v32 = 2889737;
                goto LABEL_131;
              }
              goto LABEL_132;
            }
            v19 = 0;
            v18 = HIDWORD(Size);
          }
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
            {
              v24 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              LODWORD(v43) = 2818;
              v25 = 2885641;
              goto LABEL_69;
            }
            v31 = 2818;
            v32 = 2885641;
LABEL_131:
            bidTraceW(off_18012A210[0], v32, L"<CStream::ReadText|ADO|ERR>  line %d\n", v31);
          }
LABEL_132:
          if ( strIn )
            MpHeapFree(g_hHeapHandle, strIn);
          goto LABEL_134;
        }
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_137;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          LODWORD(v43) = 2753;
          v11 = 2819081;
          goto LABEL_31;
        }
        v12 = 2753;
        v13 = 2819081;
      }
    }
  }
  else
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_137;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
    {
      v10 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      LODWORD(v43) = 2730;
      v11 = 2795529;
      goto LABEL_31;
    }
    v12 = 2730;
    v13 = 2795529;
  }
LABEL_12:
  bidTraceW(off_18012A210[0], v13, L"<CStream::ReadText|ADO|ERR>  line %d\n", v12);
LABEL_134:
  if ( (bidGblFlags & 2) != 0 && off_18012A940[0] )
  {
    v36 = v60;
    v37 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    LODWORD(v43) = v36;
    bidTraceW(off_18012A210[0], 2961408, off_18012A940[0], v37, v43);
  }
LABEL_137:
  if ( (bidGblFlags & 4) != 0 && v65 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v65);
  v38 = v60;
  v39 = *v62;
  --*(_DWORD *)(v39 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v39 + 8));
  v14 = TlsValue[2]-- == 1;
  if ( v14 )
  {
    v40 = TlsValue;
    v41 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v41 )
    {
      SetErrorInfo(0, v41);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v40 = TlsValue;
    }
    if ( *((_BYTE *)v40 + 30) )
    {
      *((_QWORD *)v40 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v38;
}

```

## disassembly

```asm
0x18004e370  mov     [rsp-8+arg_18], rbx
0x18004e375  push    rbp
0x18004e376  push    rsi
0x18004e377  push    rdi
0x18004e378  push    r12
0x18004e37a  push    r13
0x18004e37c  push    r14
0x18004e37e  push    r15
0x18004e380  lea     rbp, [rsp-47F0h]
0x18004e388  mov     eax, 48F0h
0x18004e38d  call    _alloca_probe
0x18004e392  sub     rsp, rax
0x18004e395  mov     rax, cs:__security_cookie
0x18004e39c  xor     rax, rsp
0x18004e39f  mov     [rbp+4820h+var_40], rax
0x18004e3a6  mov     r14, r8
0x18004e3a9  mov     [rbp+4820h+var_4848], r8
0x18004e3ad  mov     r15d, edx
0x18004e3b0  mov     rdi, rcx
0x18004e3b3  mov     [rsp+4920h+var_48C8], 0
0x18004e3bb  mov     dword ptr [rsp+4920h+Size+4], 0
0x18004e3c3  mov     dword ptr [rsp+4920h+Size], 0
0x18004e3cb  mov     [rsp+4920h+var_48BC], 0
0x18004e3d3  mov     [rsp+4920h+var_48A8], 0
0x18004e3dc  mov     rsi, [rcx+90h]
0x18004e3e3  add     rsi, 8
0x18004e3e7  mov     rax, rcx
0x18004e3ea  lea     rdx, [rcx+20h]
0x18004e3ee  neg     rax
0x18004e3f1  sbb     rcx, rcx
0x18004e3f4  and     rcx, rdx
0x18004e3f7  mov     [rbp+4820h+var_4878], rcx
0x18004e3fb  mov     [rbp+4820h+var_486C], 0
0x18004e402  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18004e409  mov     ecx, [rcx+14h]; dwTlsIndex
0x18004e40c  call    cs:__imp_TlsGetValue
0x18004e413  nop     dword ptr [rax+rax+00h]
0x18004e418  mov     [rbp+4820h+TlsValue], rax
0x18004e41c  mov     [rbp+4820h+var_4870], 0
0x18004e423  mov     ebx, 1
0x18004e428  test    rax, rax
0x18004e42b  jz      short loc_18004E432
0x18004e42d  add     [rax+8], ebx
0x18004e430  jmp     short loc_18004E470
0x18004e432  mov     [rbp+4820h+var_4890], ebx
0x18004e435  mov     [rbp+4820h+var_4888], 0
0x18004e43d  mov     [rbp+4820h+var_4880], 0
0x18004e444  mov     [rbp+4820h+var_487C], 0
0x18004e44a  mov     [rbp+4820h+var_487A], 0
0x18004e44e  lea     rdx, [rbp+4820h+TlsValue]; lpTlsValue
0x18004e452  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18004e459  mov     ecx, [rcx+14h]; dwTlsIndex
0x18004e45c  call    cs:__imp_TlsSetValue
0x18004e463  nop     dword ptr [rax+rax+00h]
0x18004e468  lea     rax, [rbp+4820h+TlsValue]
0x18004e46c  mov     [rbp+4820h+TlsValue], rax
0x18004e470  mov     [rbp+4820h+var_4868], 0
0x18004e478  mov     rcx, rsi
0x18004e47b  call    cs:__imp_UMSEnterCSWraper
0x18004e482  nop     dword ptr [rax+rax+00h]
0x18004e487  mov     [rbp+4820h+var_4868], rsi
0x18004e48b  mov     eax, [rdi+0E8h]
0x18004e491  mov     [rbp+4820h+var_4858], eax
0x18004e494  mov     [rbp+4820h+var_4850], 0FFFFFFFFFFFFFFFFh
0x18004e49c  test    byte ptr cs:_bidGblFlags, 4
0x18004e4a3  jz      short loc_18004E4D3
0x18004e4a5  mov     rax, cs:off_18012ADA0; "<CStream::ReadText|API|ADO> %u#, NumByt"...
0x18004e4ac  test    rax, rax
0x18004e4af  jz      short loc_18004E4D3
0x18004e4b1  lea     rcx, [rdi+98h]; this
0x18004e4b8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e4bd  mov     rdx, cs:off_18012ADA0; "<CStream::ReadText|API|ADO> %u#, NumByt"...
0x18004e4c4  mov     r9d, r15d
0x18004e4c7  mov     r8d, eax
0x18004e4ca  lea     rcx, [rbp+4820h+var_4850]
0x18004e4ce  call    _bidScopeEnterW
0x18004e4d3  cmp     dword ptr [rdi+0B8h], 2
0x18004e4da  jz      short loc_18004E54A
0x18004e4dc  mov     [rbp+4820h+var_4870], 800A0C93h
0x18004e4e3  lea     rcx, [rbp+4820h+TlsValue]; this
0x18004e4e7  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18004e4ec  test    byte ptr cs:_bidGblFlags, 2
0x18004e4f3  jz      loc_18004EF5E
0x18004e4f9  lea     rbx, [rdi+98h]
0x18004e500  mov     rcx, rbx; this
0x18004e503  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e508  cmp     eax, 0FFFFFFFFh
0x18004e50b  jz      short loc_18004E527
0x18004e50d  mov     rcx, rbx; this
0x18004e510  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e515  mov     dword ptr [rsp+4920h+var_4900], 0A95h
0x18004e51d  mov     edx, 2A5409h
0x18004e522  jmp     loc_18004E658
0x18004e527  mov     r9d, 0A95h
0x18004e52d  mov     edx, 2A5409h
0x18004e532  lea     r8, aCstreamReadtex_2; "<CStream::ReadText|ADO|ERR>  line %d\n"
0x18004e539  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004e540  call    _bidTraceW
0x18004e545  jmp     loc_18004EF1B
0x18004e54a  test    r14, r14
0x18004e54d  jz      short loc_18004E555
0x18004e54f  cmp     r15d, 0FFFFFFFEh
0x18004e553  jge     short loc_18004E5BE
0x18004e555  mov     [rsp+4920h+var_48D0], 800A0BB9h
0x18004e55d  lea     rdx, [rsp+4920h+var_48D0]; int *
0x18004e562  lea     rcx, [rbp+4820h+TlsValue]; this
0x18004e566  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18004e56b  test    eax, eax
0x18004e56d  jz      short loc_18004E5BA
0x18004e56f  test    byte ptr cs:_bidGblFlags, 2
0x18004e576  jz      loc_18004EF5E
0x18004e57c  lea     rbx, [rdi+98h]
0x18004e583  mov     rcx, rbx; this
0x18004e586  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e58b  cmp     eax, 0FFFFFFFFh
0x18004e58e  jz      short loc_18004E5AA
0x18004e590  mov     rcx, rbx; this
0x18004e593  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e598  mov     dword ptr [rsp+4920h+var_4900], 0A9Ah
0x18004e5a0  mov     edx, 2A6809h
0x18004e5a5  jmp     loc_18004E658
0x18004e5aa  mov     r9d, 0A9Ah
0x18004e5b0  mov     edx, 2A6809h
0x18004e5b5  jmp     loc_18004E532
0x18004e5ba  cmp     r15d, 0FFFFFFFEh
0x18004e5be  jnz     short loc_18004E5EC
0x18004e5c0  mov     rax, [rdi]
0x18004e5c3  mov     rax, [rax+110h]
0x18004e5ca  mov     rcx, rdi
0x18004e5cd  mov     rdx, r14
0x18004e5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5d5  mov     [rsp+4920h+var_48D0], eax
0x18004e5d9  lea     rdx, [rsp+4920h+var_48D0]; int *
0x18004e5de  lea     rcx, [rbp+4820h+TlsValue]; this
0x18004e5e2  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18004e5e7  jmp     loc_18004EF1B
0x18004e5ec  cmp     r15d, 0FFFFFFFFh
0x18004e5f0  jnz     short loc_18004E5FE
0x18004e5f2  mov     rax, [rdi]
0x18004e5f5  mov     rax, [rax+118h]
0x18004e5fc  jmp     short loc_18004E5CA
0x18004e5fe  cmp     qword ptr [rdi+0A8h], 0
0x18004e606  jnz     short loc_18004E683
0x18004e608  mov     [rsp+4920h+var_48D0], 800A0E78h
0x18004e610  lea     rdx, [rsp+4920h+var_48D0]; int *
0x18004e615  lea     rcx, [rbp+4820h+TlsValue]; this
0x18004e619  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18004e61e  test    eax, eax
0x18004e620  jz      short loc_18004E683
0x18004e622  test    byte ptr cs:_bidGblFlags, 2
0x18004e629  jz      loc_18004EF5E
0x18004e62f  lea     rbx, [rdi+98h]
0x18004e636  mov     rcx, rbx; this
0x18004e639  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e63e  cmp     eax, 0FFFFFFFFh
0x18004e641  jz      short loc_18004E673
0x18004e643  mov     rcx, rbx; this
0x18004e646  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e64b  mov     dword ptr [rsp+4920h+var_4900], 0AAAh
0x18004e653  mov     edx, 2AA809h
0x18004e658  lea     r8, aCstreamReadtex_0; "<CStream::ReadText|ADO|ERR> %u#, line %"...
0x18004e65f  mov     r9d, eax
0x18004e662  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004e669  call    _bidTraceW
0x18004e66e  jmp     loc_18004EF1B
0x18004e673  mov     r9d, 0AAAh
0x18004e679  mov     edx, 2AA809h
0x18004e67e  jmp     loc_18004E532
0x18004e683  mov     eax, [rdi+0C0h]
0x18004e689  mov     esi, 3
0x18004e68e  and     al, sil
0x18004e691  cmp     al, 2
0x18004e693  jnz     short loc_18004E6FA
0x18004e695  mov     [rsp+4920h+var_48D0], 800A0C93h
0x18004e69d  lea     rdx, [rsp+4920h+var_48D0]; int *
0x18004e6a2  lea     rcx, [rbp+4820h+TlsValue]; this
0x18004e6a6  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18004e6ab  test    eax, eax
0x18004e6ad  jz      short loc_18004E6FA
0x18004e6af  test    byte ptr cs:_bidGblFlags, 2
0x18004e6b6  jz      loc_18004EF5E
0x18004e6bc  lea     rbx, [rdi+98h]
0x18004e6c3  mov     rcx, rbx; this
0x18004e6c6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e6cb  cmp     eax, 0FFFFFFFFh
0x18004e6ce  jz      short loc_18004E6EA
0x18004e6d0  mov     rcx, rbx; this
0x18004e6d3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e6d8  mov     dword ptr [rsp+4920h+var_4900], 0ABAh
0x18004e6e0  mov     edx, 2AE809h
0x18004e6e5  jmp     loc_18004E658
0x18004e6ea  mov     r9d, 0ABAh
0x18004e6f0  mov     edx, 2AE809h
0x18004e6f5  jmp     loc_18004E532
0x18004e6fa  xor     edx, edx
0x18004e6fc  mov     rcx, [rdi+0A8h]
0x18004e703  mov     rax, [rcx]
0x18004e706  lea     r9, [rsp+4920h+var_48A8]
0x18004e70b  mov     r8d, ebx
0x18004e70e  mov     rax, [rax+28h]
0x18004e712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e717  mov     [rsp+4920h+var_48D0], eax
0x18004e71b  lea     rdx, [rsp+4920h+var_48D0]; int *
0x18004e720  lea     rcx, [rbp+4820h+TlsValue]; this
0x18004e724  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18004e729  test    eax, eax
0x18004e72b  jz      short loc_18004E778
0x18004e72d  test    byte ptr cs:_bidGblFlags, 2
0x18004e734  jz      loc_18004EF5E
0x18004e73a  lea     rbx, [rdi+98h]
0x18004e741  mov     rcx, rbx; this
0x18004e744  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e749  cmp     eax, 0FFFFFFFFh
0x18004e74c  jz      short loc_18004E768
0x18004e74e  mov     rcx, rbx; this
0x18004e751  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e756  mov     dword ptr [rsp+4920h+var_4900], 0ABEh
0x18004e75e  mov     edx, 2AF809h
0x18004e763  jmp     loc_18004E658
0x18004e768  mov     r9d, 0ABEh
0x18004e76e  mov     edx, 2AF809h
0x18004e773  jmp     loc_18004E532
0x18004e778  cmp     dword ptr [rsp+4920h+var_48A8+4], 0
0x18004e77d  jnz     short loc_18004E786
0x18004e77f  cmp     dword ptr [rsp+4920h+var_48A8], 0
0x18004e784  jz      short loc_18004E788
0x18004e786  xor     bl, bl
0x18004e788  mov     rcx, [rdi+0A8h]
0x18004e78f  mov     rax, [rcx]
0x18004e792  lea     r9, [rsp+4920h+Size+4]
0x18004e797  mov     r8d, 800h
0x18004e79d  lea     rdx, [rbp+4820h+var_4840]
0x18004e7a1  mov     rax, [rax+18h]
0x18004e7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7aa  mov     [rsp+4920h+var_48D0], eax
0x18004e7ae  lea     rdx, [rsp+4920h+var_48D0]; int *
0x18004e7b3  lea     rcx, [rbp+4820h+TlsValue]; this
0x18004e7b7  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18004e7bc  test    eax, eax
0x18004e7be  jz      short loc_18004E80B
0x18004e7c0  test    byte ptr cs:_bidGblFlags, 2
0x18004e7c7  jz      loc_18004EF5E
0x18004e7cd  lea     rbx, [rdi+98h]
0x18004e7d4  mov     rcx, rbx; this
0x18004e7d7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e7dc  cmp     eax, 0FFFFFFFFh
0x18004e7df  jz      short loc_18004E7FB
0x18004e7e1  mov     rcx, rbx; this
0x18004e7e4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004e7e9  mov     dword ptr [rsp+4920h+var_4900], 0AC1h
0x18004e7f1  mov     edx, 2B0409h
0x18004e7f6  jmp     loc_18004E658
0x18004e7fb  mov     r9d, 0AC1h
0x18004e801  mov     edx, 2B0409h
0x18004e806  jmp     loc_18004E532
0x18004e80b  mov     [rbp+4820h+strIn], 0
0x18004e813  xor     r12d, r12d
0x18004e816  xor     eax, eax
0x18004e818  mov     [rsp+4920h+var_48B0], eax
0x18004e81c  mov     r11d, dword ptr [rsp+4920h+Size+4]
0x18004e821  cmp     dword ptr [rdi+0D8h], 4B0h
0x18004e82b  jnz     short loc_18004E857
0x18004e82d  test    bl, bl
0x18004e82f  jz      short loc_18004E857
0x18004e831  cmp     r11d, 2
0x18004e835  jb      short loc_18004E857
0x18004e837  lea     r8, [rdi+0DCh]; enum BYTEORDER *
0x18004e83e  lea     rdx, [rbp+4820h+var_4840]; unsigned __int8 *
0x18004e842  call    ?CheckUnicodeByteOrderMark@CStream@@QEAA_NPEAEPEAW4BYTEORDER@@@Z; CStream::CheckUnicodeByteOrderMark(uchar *,BYTEORDER *)
0x18004e847  test    al, al
0x18004e849  jz      short loc_18004E857
0x18004e84b  lea     r14d, [r12+2]
0x18004e850  mov     dword ptr [rsp+4920h+var_48A8], r14d
0x18004e855  jmp     short loc_18004E883
0x18004e857  xor     r14d, r14d
0x18004e85a  cmp     dword ptr [rdi+0D8h], 0FDE9h
0x18004e864  jnz     short loc_18004E883
0x18004e866  test    bl, bl
0x18004e868  jz      short loc_18004E883
0x18004e86a  cmp     r11d, esi
0x18004e86d  jb      short loc_18004E883
0x18004e86f  lea     rcx, [rbp+4820h+var_4840]; unsigned __int8 *
0x18004e873  call    ?CheckUTF8Mark@@YAHPEAE@Z; CheckUTF8Mark(uchar *)
0x18004e878  test    eax, eax
0x18004e87a  jz      short loc_18004E883
0x18004e87c  mov     r14d, esi
0x18004e87f  mov     dword ptr [rsp+4920h+var_48A8], esi
0x18004e883  mov     r13d, [rdi+0D8h]
0x18004e88a  lea     rax, [rbp+4820h+Src]
0x18004e891  mov     [rsp+4920h+var_48B8], rax
0x18004e896  mov     rsi, r15
0x18004e899  sub     r11d, r14d
0x18004e89c  jz      loc_18004EE6C
0x18004e8a2  lea     eax, [r11+r12]
0x18004e8a6  test    eax, eax
0x18004e8a8  jz      loc_18004E9B9
0x18004e8ae  mov     [rsp+4920h+var_48BC], eax
0x18004e8b2  mov     dword ptr [rsp+4920h+Size], 2000h
0x18004e8ba  mov     eax, r14d
0x18004e8bd  lea     rcx, [rbp+4820h+var_4840]
  ... truncated ...
```
