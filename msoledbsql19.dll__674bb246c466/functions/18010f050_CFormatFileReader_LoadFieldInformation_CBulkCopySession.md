# CFormatFileReader::LoadFieldInformation(CBulkCopySession *)

- ea: `0x18010f050`
- end: `0x18010fea0`
- name: `?LoadFieldInformation@CFormatFileReader@@QEAAJPEAVCBulkCopySession@@@Z`
- size: `3664`
- prototype: `__int64 __fastcall(CFormatFileReader *__hidden this, struct CBulkCopySession *)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting`

## callers

- `0x180112a70`

## callees

- `0x180003030`
- `0x180003d80`
- `0x18000bec0`
- `0x18006d690`
- `0x18010e8c0`
- `0x18010f050`
- `0x180112620`
- `0x180113250`
- `0x180116f40`
- `0x180116ff0`
- `0x1801179d0`
- `0x180117a10`
- `0x180117b40`
- `0x180118260`
- `0x180118340`
- `0x180129020`
- `0x1801336f4`
- `0x180133bcc`
- `0x1801341ec`
- `0x1801345a0`
- `0x180143d70`
- `0x1801447c0`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x18010f158`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x18010f178`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x18010f198`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x18010f1b8`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x18010f1d8`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x18010f1f4`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x18010f158`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x18010f178`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x18010f198`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x18010f1b8`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x18010f1d8`
- `api-ms-win-crt-string-l1-1-0!strncmp` at `0x18010f1f4`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x18010f2e0`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x18010f488`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x18010f531`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x18010f788`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x18010f2e0`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x18010f488`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x18010f531`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x18010f788`
- `api-ms-win-crt-convert-l1-1-0!atol` at `0x18010f588`
- `api-ms-win-crt-convert-l1-1-0!atol` at `0x18010f588`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFormatFileReader::LoadFieldInformation(CFormatFileReader *this, struct CBulkCopySession *a2)
{
  int v4; // r15d
  int v5; // ebx
  int v6; // eax
  char v7; // al
  int v8; // eax
  int Number; // eax
  int v10; // edi
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // ecx
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  __int64 v16; // rax
  int v17; // ecx
  int v18; // r14d
  __int64 v19; // rcx
  struct CBulkCopySession *v20; // rdi
  int Chars; // eax
  unsigned __int8 v22; // al
  int v23; // edi
  int v24; // r13d
  unsigned __int8 v25; // al
  const unsigned __int8 *v26; // r12
  int v27; // r14d
  int v28; // edi
  __int64 v29; // rdx
  char *v30; // rcx
  char v31; // al
  char *v32; // rax
  unsigned __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rax
  void (__fastcall ***v37)(_QWORD, __int64); // [rsp+30h] [rbp-D0h]
  unsigned __int8 v38; // [rsp+38h] [rbp-C8h]
  int v39; // [rsp+3Ch] [rbp-C4h]
  __int64 v40; // [rsp+40h] [rbp-C0h]
  CBCPField *v42; // [rsp+50h] [rbp-B0h]
  __int64 v43; // [rsp+58h] [rbp-A8h]
  __int64 v44; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v45[4]; // [rsp+68h] [rbp-98h] BYREF
  char Str1[4]; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int64 v47[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v48[2]; // [rsp+80h] [rbp-80h]
  unsigned __int8 *v49[2]; // [rsp+90h] [rbp-70h]
  char String; // [rsp+A0h] [rbp-60h] BYREF
  char v51; // [rsp+A1h] [rbp-5Fh]
  char v52; // [rsp+A2h] [rbp-5Eh]
  char v53[144]; // [rsp+170h] [rbp+70h] BYREF
  wchar_t v54[136]; // [rsp+200h] [rbp+100h] BYREF

  v4 = 0;
  *(_DWORD *)Str1 = 0;
  v47[0] = 0;
  v47[1] = 0;
  v48[0] = 0;
  v48[1] = 0;
  *(_OWORD *)v49 = 0;
  if ( !(unsigned int)CExtByteBuffer::FInit((CExtByteBuffer *)v47, 0xC8u, 0x100u) )
  {
    v5 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605B8[0], 8943625, 2147942414LL);
    }
    goto LABEL_198;
  }
  v6 = (*(__int64 (__fastcall **)(CFormatFileReader *, __int64, char *))(*(_QWORD *)this + 16LL))(this, 4, Str1);
  v5 = v6;
  if ( v6 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605B8[0], 8949769, (unsigned int)v6);
    }
    goto LABEL_198;
  }
  if ( strncmp(Str1, "19.4", 4u)
    && strncmp(Str1, "11.0", 4u)
    && strncmp(Str1, "10.0", 4u)
    && strncmp(Str1, "9.0", 3u)
    && strncmp(Str1, "8.0", 3u)
    && strncmp(Str1, "7.0", 3u) )
  {
    v7 = bidGblFlags;
    if ( (bidGblFlags & 2) != 0 )
    {
      v5 = bidTraceHR(off_1802605B8[0], 9311241, 2147746055LL);
      v7 = bidGblFlags;
    }
    else
    {
      v5 = -2147221241;
    }
    if ( v5 < 0 )
    {
      if ( (v7 & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_1802605B8[0], 8953865, (unsigned int)v5);
      }
      goto LABEL_198;
    }
  }
  _mm_lfence();
  v8 = CFormatFileReader::SkipWhiteSpaces(this, 1);
  v5 = v8;
  if ( v8 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605B8[0], 8957961, (unsigned int)v8);
    }
    goto LABEL_198;
  }
  _mm_lfence();
  Number = CFormatFileReader::ReadNumber(this, (unsigned __int8 *)&String, 0xC8u);
  v5 = Number;
  if ( Number < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605B8[0], 8962057, (unsigned int)Number);
    }
    goto LABEL_198;
  }
  _mm_lfence();
  v10 = atoi(&String);
  v44 = v10;
  v11 = CBulkCopySession::InitializeFieldInfo(a2, v10);
  v5 = v11;
  if ( v11 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605B8[0], 8969225, (unsigned int)v11);
    }
    goto LABEL_198;
  }
  _mm_lfence();
  v12 = *(unsigned int *)(*((_QWORD *)a2 + 104) + 1148LL);
  if ( (unsigned int)v12 >= 0xC42C && (unsigned int)IsW2CSpecialCodePage(v12) )
  {
    v13 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(g_pMO, 40);
    v37 = (void (__fastcall ***)(_QWORD, __int64))v13;
    if ( v13 )
    {
      v14 = *(_DWORD *)(*((_QWORD *)a2 + 104) + 1148LL);
      *(_QWORD *)(v13 + 16) = this;
      *(_DWORD *)(v13 + 24) = v14;
      *(_WORD *)(v13 + 8) = 0;
      *(_DWORD *)(v13 + 12) = 0;
      *(_QWORD *)v13 = &NS_BCP_OLEDB::CColumnNameProcessor4Byte::`vftable';
      *(_DWORD *)(v13 + 32) = 0;
      v15 = (void (__fastcall ***)(_QWORD, __int64))v13;
      goto LABEL_35;
    }
  }
  else
  {
    v16 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(g_pMO, 40);
    v37 = (void (__fastcall ***)(_QWORD, __int64))v16;
    if ( v16 )
    {
      v17 = *(_DWORD *)(*((_QWORD *)a2 + 104) + 1148LL);
      *(_QWORD *)(v16 + 16) = this;
      *(_DWORD *)(v16 + 24) = v17;
      *(_WORD *)(v16 + 8) = 0;
      *(_DWORD *)(v16 + 12) = 0;
      *(_QWORD *)v16 = &NS_BCP_OLEDB::CColumnNameProcessorDBCS::`vftable';
      *(_WORD *)(v16 + 32) = 0;
      v15 = (void (__fastcall ***)(_QWORD, __int64))v16;
      goto LABEL_35;
    }
  }
  v15 = 0;
  v37 = 0;
LABEL_35:
  if ( v15 )
  {
    if ( v10 > 0 )
    {
      v43 = 0;
      v18 = 1;
      v39 = 1;
      v19 = 0;
      v40 = 0;
      v20 = a2;
      while ( 1 )
      {
        v42 = (CBCPField *)(v19 + *((_QWORD *)v20 + 340));
        Chars = CFormatFileReader::SkipWhiteSpaces(this, 1);
        v5 = Chars;
        if ( Chars < 0 )
          break;
        _mm_lfence();
        Chars = CFormatFileReader::ReadNumber(this, (unsigned __int8 *)&String, 0xC8u);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 8990729;
          goto LABEL_195;
        }
        if ( atoi(&String) != v18 )
        {
          v5 = -2147221246;
          goto LABEL_196;
        }
        _mm_lfence();
        Chars = CFormatFileReader::SkipWhiteSpaces(this, 0);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 8998921;
          goto LABEL_195;
        }
        _mm_lfence();
        Chars = CFormatFileReader::ReadChars(this, (unsigned __int8 *)&String, 0xC8u);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9003017;
          goto LABEL_195;
        }
        v22 = FieldNameToTDSTypeA(&String);
        v23 = v22;
        v38 = v22;
        if ( !v22 )
        {
          v5 = -2147221245;
          goto LABEL_196;
        }
        _mm_lfence();
        Chars = CFormatFileReader::SkipWhiteSpaces(this, 0);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9012233;
          goto LABEL_195;
        }
        _mm_lfence();
        Chars = CFormatFileReader::ReadNumber(this, (unsigned __int8 *)&String, 0xC8u);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9016329;
          goto LABEL_195;
        }
        if ( String != 48 || v51 )
        {
          v24 = atoi(&String);
          if ( !v24 )
          {
            v5 = -2147221279;
            goto LABEL_196;
          }
        }
        else
        {
          v24 = 0;
        }
        _mm_lfence();
        Chars = CFormatFileReader::SkipWhiteSpaces(this, 0);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9030665;
          goto LABEL_195;
        }
        _mm_lfence();
        Chars = CFormatFileReader::ReadNumber(this, (unsigned __int8 *)&String, 0xC8u);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9034761;
          goto LABEL_195;
        }
        if ( String != 48 || v51 )
        {
          v4 = atol(&String);
          if ( !v4 )
          {
            v5 = -2147221278;
            goto LABEL_196;
          }
        }
        _mm_lfence();
        if ( v4 )
        {
          switch ( v23 )
          {
            case 34:
            case 35:
            case 37:
            case 38:
            case 39:
            case 45:
            case 47:
            case 99:
            case 109:
            case 110:
            case 111:
            case 231:
            case 239:
            case 240:
            case 241:
              break;
            default:
              v4 = -10;
              break;
          }
        }
        Chars = CFormatFileReader::SkipWhiteSpaces(this, 0);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9076745;
          goto LABEL_195;
        }
        _mm_lfence();
        Chars = (*(__int64 (__fastcall **)(CFormatFileReader *, __int64, char *))(*(_QWORD *)this + 16LL))(
                  this,
                  1,
                  &String);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9080841;
          goto LABEL_195;
        }
        if ( String != 34 )
          goto LABEL_165;
        if ( !(unsigned int)CExtBaseBuffer::ReInit((CExtBaseBuffer *)v47, v48[0], 0) )
        {
          v5 = -2147467259;
          goto LABEL_196;
        }
        _mm_lfence();
        v45[0] = 0;
        Chars = (*(__int64 (__fastcall **)(CFormatFileReader *, __int64, unsigned __int8 *))(*(_QWORD *)this + 16LL))(
                  this,
                  1,
                  v45);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9098249;
          goto LABEL_195;
        }
        _mm_lfence();
        v25 = v45[0];
        if ( v45[0] != 34 )
        {
          while ( 1 )
          {
            Chars = CExtByteBuffer::WriteByteToExtBuffer((CExtByteBuffer *)v47, v25);
            v5 = Chars;
            if ( Chars < 0 )
              break;
            if ( v45[0] == 92 )
            {
              Chars = (*(__int64 (__fastcall **)(CFormatFileReader *, __int64, unsigned __int8 *))(*(_QWORD *)this + 16LL))(
                        this,
                        1,
                        v45);
              v5 = Chars;
              if ( Chars < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_196;
                v34 = 9108489;
                goto LABEL_195;
              }
              Chars = CExtByteBuffer::WriteByteToExtBuffer((CExtByteBuffer *)v47, v45[0]);
              v5 = Chars;
              if ( Chars < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_196;
                v34 = 9110537;
                goto LABEL_195;
              }
            }
            Chars = (*(__int64 (__fastcall **)(CFormatFileReader *, __int64, unsigned __int8 *))(*(_QWORD *)this + 16LL))(
                      this,
                      1,
                      v45);
            v5 = Chars;
            if ( Chars < 0 )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_196;
              v34 = 9114633;
              goto LABEL_195;
            }
            if ( v47[1] > 0x7FFFFFFF )
            {
              v5 = CBCPErrorHandler::PostBCPErrors(0, -2147221281);
              goto LABEL_196;
            }
            v25 = v45[0];
            if ( v45[0] == 34 )
              goto LABEL_72;
          }
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9103369;
          goto LABEL_195;
        }
LABEL_72:
        Chars = CExtByteBuffer::WriteByteToExtBuffer((CExtByteBuffer *)v47, 0);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9125897;
          goto LABEL_195;
        }
        v26 = v49[0];
        v27 = ConvertTerminatorToBinary(v49[0], v49[0], v47[1]);
        if ( v27 == -1 )
        {
LABEL_165:
          v5 = -2147221244;
          goto LABEL_196;
        }
        Chars = CFormatFileReader::SkipWhiteSpaces(this, 0);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9144329;
          goto LABEL_195;
        }
        _mm_lfence();
        Chars = CFormatFileReader::ReadNumber(this, (unsigned __int8 *)&String, 0xC8u);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9148425;
          goto LABEL_195;
        }
        if ( String != 48 || v51 )
        {
          v28 = atoi(&String);
          if ( !v28 )
          {
            v5 = -2147221243;
            goto LABEL_196;
          }
          if ( !*((_DWORD *)a2 + 660) && v28 != v39 )
          {
            *((_DWORD *)a2 + 696) = 1;
            if ( *((_QWORD *)a2 + 333) )
            {
              v5 = -2147221242;
              goto LABEL_196;
            }
          }
        }
        else
        {
          v28 = 0;
        }
        _mm_lfence();
        Chars = CFormatFileReader::SkipWhiteSpaces(this, 0);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9170953;
          goto LABEL_195;
        }
        Chars = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v37)[1])(v37);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9175049;
          goto LABEL_195;
        }
        _mm_lfence();
        Chars = CFormatFileReader::SkipChars(this);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9179145;
          goto LABEL_195;
        }
        if ( Str1[0] == 49 || (unsigned __int8)(Str1[0] - 56) <= 1u )
        {
          _mm_lfence();
          Chars = CFormatFileReader::SkipWhiteSpaces(this, 0);
          v5 = Chars;
          if ( Chars < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_196;
            v34 = 9188361;
            goto LABEL_195;
          }
          _mm_lfence();
          Chars = CFormatFileReader::ReadChars(this, (unsigned __int8 *)&String, 0xC8u);
          v5 = Chars;
          if ( Chars < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_196;
            v34 = 9192457;
            goto LABEL_195;
          }
          if ( String == 34 && v51 == 34 && !v52 )
          {
            v53[0] = 0;
          }
          else
          {
            v29 = 129;
            v30 = v53;
            do
            {
              if ( v29 == -2147483517 )
                break;
              v31 = *(v30 - 208);
              if ( !v31 )
                break;
              *v30++ = v31;
              --v29;
            }
            while ( v29 );
            v32 = v30 - 1;
            if ( v29 )
              v32 = v30;
            *v32 = 0;
          }
        }
        else
        {
          v53[0] = 0;
        }
        if ( !v24 )
        {
          if ( v38 == 39 )
          {
            v38 = 47;
            v24 = 2;
          }
          else if ( v38 == 37 )
          {
            v38 = 45;
            v24 = 2;
          }
          else if ( !v4 && v27 > 0 )
          {
            v4 = -10;
          }
        }
        v33 = v28;
        v20 = a2;
        Chars = CBCPField::SetColumn(
                  v42,
                  v33,
                  *((struct CBCPColumn **)a2 + 337),
                  *((_WORD *)a2 + 1346),
                  *((_DWORD *)a2 + 660));
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9247753;
          goto LABEL_195;
        }
        _mm_lfence();
        Chars = CBCPField::SetPrefixLength(v42, v24);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9250825;
          goto LABEL_195;
        }
        _mm_lfence();
        Chars = CBCPField::SetTerminator(v42, v26, v27);
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9253897;
          goto LABEL_195;
        }
        if ( v4 >= -1 || v4 == -10 )
        {
          *((_DWORD *)v42 + 5) = v4;
        }
        else
        {
          _mm_lfence();
          Chars = CBCPErrorHandler::PostBCPErrors(0, -2147221278);
          v5 = Chars;
          if ( Chars < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_196;
            v34 = 9256969;
            goto LABEL_195;
          }
        }
        _mm_lfence();
        Chars = CBCPField::SetType(v42, v38, *((_DWORD *)a2 + 670), *((_DWORD *)a2 + 671), 0, *((_BYTE *)a2 + 2648));
        v5 = Chars;
        if ( Chars < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_196;
          v34 = 9266185;
          goto LABEL_195;
        }
        if ( Str1[0] == 49 || (unsigned __int8)(Str1[0] - 56) <= 1u )
        {
          if ( !(unsigned int)FastMultiByteToWideChar(*(_DWORD *)(*((_QWORD *)a2 + 104) + 1148LL), 0, v53, -1, v54, 129) )
          {
            v5 = -2147221265;
            goto LABEL_196;
          }
          _mm_lfence();
          v35 = -1;
          do
            ++v35;
          while ( v54[v35] );
          Chars = CBCPField::SetCollationName(v42, v54, (unsigned int)v35);
          v5 = Chars;
          if ( Chars < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_196;
            v34 = 9283593;
            goto LABEL_195;
          }
          *((_DWORD *)v42 + 7) = 0;
          *((_BYTE *)v42 + 32) = 0;
        }
        v18 = ++v39;
        ++v43;
        v19 = v40 + 408;
        v40 += 408;
        if ( v43 >= v44 )
          goto LABEL_196;
        v4 = 0;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_196;
      v34 = 8986633;
LABEL_195:
      _mm_lfence();
      bidTraceHR(off_1802605B8[0], v34, (unsigned int)Chars);
LABEL_196:
      v15 = v37;
    }
    (**v15)(v15, 1);
  }
  else
  {
    v5 = -2147024882;
  }
LABEL_198:
  CExtBaseBuffer::~CExtBaseBuffer((CExtBaseBuffer *)v47);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18010f050  mov     [rsp-8+arg_10], rbx
0x18010f055  push    rbp
0x18010f056  push    rsi
0x18010f057  push    rdi
0x18010f058  push    r12
0x18010f05a  push    r13
0x18010f05c  push    r14
0x18010f05e  push    r15
0x18010f060  lea     rbp, [rsp-220h]
0x18010f068  sub     rsp, 320h
0x18010f06f  mov     rax, cs:__security_cookie
0x18010f076  xor     rax, rsp
0x18010f079  mov     [rbp+250h+var_40], rax
0x18010f080  mov     r14, rdx
0x18010f083  mov     [rsp+350h+var_308], rdx
0x18010f088  mov     rsi, rcx
0x18010f08b  xor     r15d, r15d
0x18010f08e  mov     dword ptr [rsp+350h+Str1], r15d
0x18010f093  xorps   xmm0, xmm0
0x18010f096  movups  xmmword ptr [rsp+350h+var_2E0], xmm0
0x18010f09b  movups  xmmword ptr [rbp+250h+var_2D0], xmm0
0x18010f09f  mov     [rsp+350h+var_2E0], r15
0x18010f0a4  mov     [rsp+350h+var_2E0+8], r15
0x18010f0a9  mov     [rbp+250h+var_2D0], r15
0x18010f0ad  mov     [rbp+250h+var_2D0+8], r15
0x18010f0b1  movdqu  xmmword ptr [rbp+250h+var_2C0], xmm0
0x18010f0b6  mov     edx, 0C8h; unsigned __int64
0x18010f0bb  mov     r8d, 100h; unsigned __int64
0x18010f0c1  lea     rcx, [rsp+350h+var_2E0]; this
0x18010f0c6  call    ?FInit@CExtByteBuffer@@QEAAH_K0@Z; CExtByteBuffer::FInit(unsigned __int64,unsigned __int64)
0x18010f0cb  test    eax, eax
0x18010f0cd  jnz     short loc_18010F0FD
0x18010f0cf  mov     ebx, 8007000Eh
0x18010f0d4  test    byte ptr cs:_bidGblFlags, 2
0x18010f0db  jz      loc_18010FD90
0x18010f0e1  lfence
0x18010f0e4  mov     r8d, ebx
0x18010f0e7  mov     edx, 887809h
0x18010f0ec  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18010f0f3  call    _bidTraceHR
0x18010f0f8  jmp     loc_18010FD90
0x18010f0fd  mov     rax, [rsi]
0x18010f100  lea     r8, [rsp+350h+Str1]
0x18010f105  mov     edx, 4
0x18010f10a  mov     rcx, rsi
0x18010f10d  mov     rax, [rax+10h]
0x18010f111  call    cs:__guard_dispatch_icall_fptr
0x18010f117  mov     ebx, eax
0x18010f119  test    eax, eax
0x18010f11b  jns     short loc_18010F146
0x18010f11d  test    byte ptr cs:_bidGblFlags, 2
0x18010f124  jz      loc_18010FD90
0x18010f12a  lfence
0x18010f12d  mov     r8d, eax
0x18010f130  mov     edx, 889009h
0x18010f135  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18010f13c  call    _bidTraceHR
0x18010f141  jmp     loc_18010FD90
0x18010f146  mov     r8d, 4; MaxCount
0x18010f14c  lea     rdx, Str2; "19.4"
0x18010f153  lea     rcx, [rsp+350h+Str1]; Str1
0x18010f158  call    cs:__imp_strncmp
0x18010f15e  test    eax, eax
0x18010f160  jz      loc_18010F256
0x18010f166  mov     r8d, 4; MaxCount
0x18010f16c  lea     rdx, a110_1; "11.0"
0x18010f173  lea     rcx, [rsp+350h+Str1]; Str1
0x18010f178  call    cs:__imp_strncmp
0x18010f17e  test    eax, eax
0x18010f180  jz      loc_18010F256
0x18010f186  mov     r8d, 4; MaxCount
0x18010f18c  lea     rdx, a100; "10.0"
0x18010f193  lea     rcx, [rsp+350h+Str1]; Str1
0x18010f198  call    cs:__imp_strncmp
0x18010f19e  test    eax, eax
0x18010f1a0  jz      loc_18010F256
0x18010f1a6  mov     r8d, 3; MaxCount
0x18010f1ac  lea     rdx, a90_0; "9.0"
0x18010f1b3  lea     rcx, [rsp+350h+Str1]; Str1
0x18010f1b8  call    cs:__imp_strncmp
0x18010f1be  test    eax, eax
0x18010f1c0  jz      loc_18010F256
0x18010f1c6  mov     r8d, 3; MaxCount
0x18010f1cc  lea     rdx, a80_0; "8.0"
0x18010f1d3  lea     rcx, [rsp+350h+Str1]; Str1
0x18010f1d8  call    cs:__imp_strncmp
0x18010f1de  test    eax, eax
0x18010f1e0  jz      short loc_18010F256
0x18010f1e2  mov     r8d, 3; MaxCount
0x18010f1e8  lea     rdx, a70; "7.0"
0x18010f1ef  lea     rcx, [rsp+350h+Str1]; Str1
0x18010f1f4  call    cs:__imp_strncmp
0x18010f1fa  test    eax, eax
0x18010f1fc  jz      short loc_18010F256
0x18010f1fe  mov     eax, cs:_bidGblFlags
0x18010f204  test    al, 2
0x18010f206  jz      short loc_18010F229
0x18010f208  mov     edx, 8E1409h
0x18010f20d  mov     r8d, 80040107h
0x18010f213  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18010f21a  call    _bidTraceHR
0x18010f21f  mov     ebx, eax
0x18010f221  mov     eax, cs:_bidGblFlags
0x18010f227  jmp     short loc_18010F22E
0x18010f229  mov     ebx, 80040107h
0x18010f22e  test    ebx, ebx
0x18010f230  jns     short loc_18010F256
0x18010f232  test    al, 2
0x18010f234  jz      loc_18010FD90
0x18010f23a  lfence
0x18010f23d  mov     r8d, ebx
0x18010f240  mov     edx, 88A009h
0x18010f245  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18010f24c  call    _bidTraceHR
0x18010f251  jmp     loc_18010FD90
0x18010f256  lfence
0x18010f259  mov     edx, 1; int
0x18010f25e  mov     rcx, rsi; this
0x18010f261  call    ?SkipWhiteSpaces@CFormatFileReader@@QEAAJH@Z; CFormatFileReader::SkipWhiteSpaces(int)
0x18010f266  mov     ebx, eax
0x18010f268  test    eax, eax
0x18010f26a  jns     short loc_18010F295
0x18010f26c  test    byte ptr cs:_bidGblFlags, 2
0x18010f273  jz      loc_18010FD90
0x18010f279  lfence
0x18010f27c  mov     r8d, eax
0x18010f27f  mov     edx, 88B009h
0x18010f284  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18010f28b  call    _bidTraceHR
0x18010f290  jmp     loc_18010FD90
0x18010f295  lfence
0x18010f298  mov     r8d, 0C8h; unsigned __int64
0x18010f29e  lea     rdx, [rbp+250h+String]; unsigned __int8 *
0x18010f2a2  mov     rcx, rsi; this
0x18010f2a5  call    ?ReadNumber@CFormatFileReader@@QEAAJPEAE_K@Z; CFormatFileReader::ReadNumber(uchar *,unsigned __int64)
0x18010f2aa  mov     ebx, eax
0x18010f2ac  test    eax, eax
0x18010f2ae  jns     short loc_18010F2D9
0x18010f2b0  test    byte ptr cs:_bidGblFlags, 2
0x18010f2b7  jz      loc_18010FD90
0x18010f2bd  lfence
0x18010f2c0  mov     r8d, eax
0x18010f2c3  mov     edx, 88C009h
0x18010f2c8  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18010f2cf  call    _bidTraceHR
0x18010f2d4  jmp     loc_18010FD90
0x18010f2d9  lfence
0x18010f2dc  lea     rcx, [rbp+250h+String]; String
0x18010f2e0  call    cs:__imp_atoi
0x18010f2e6  movsxd  rdi, eax
0x18010f2e9  mov     [rsp+350h+var_2F0], rdi
0x18010f2ee  mov     rdx, rdi; unsigned __int64
0x18010f2f1  mov     rcx, r14; this
0x18010f2f4  call    ?InitializeFieldInfo@CBulkCopySession@@QEAAJ_K@Z; CBulkCopySession::InitializeFieldInfo(unsigned __int64)
0x18010f2f9  mov     ebx, eax
0x18010f2fb  test    eax, eax
0x18010f2fd  jns     short loc_18010F328
0x18010f2ff  test    byte ptr cs:_bidGblFlags, 2
0x18010f306  jz      loc_18010FD90
0x18010f30c  lfence
0x18010f30f  mov     r8d, eax
0x18010f312  mov     edx, 88DC09h
0x18010f317  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18010f31e  call    _bidTraceHR
0x18010f323  jmp     loc_18010FD90
0x18010f328  lfence
0x18010f32b  mov     rax, [r14+340h]
0x18010f332  mov     ecx, [rax+47Ch]
0x18010f338  cmp     ecx, 0C42Ch
0x18010f33e  jb      short loc_18010F3A4
0x18010f340  call    _IsW2CSpecialCodePage
0x18010f345  test    eax, eax
0x18010f347  jz      short loc_18010F3A4
0x18010f349  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x18010f350  mov     rax, [rcx]
0x18010f353  mov     edx, 28h ; '('
0x18010f358  mov     rax, [rax+58h]
0x18010f35c  call    cs:__guard_dispatch_icall_fptr
0x18010f362  mov     rdx, rax
0x18010f365  mov     [rsp+350h+var_320], rax
0x18010f36a  test    rax, rax
0x18010f36d  jz      loc_18010F3FC
0x18010f373  mov     rax, [r14+340h]
0x18010f37a  mov     ecx, [rax+47Ch]
0x18010f380  mov     [rdx+10h], rsi
0x18010f384  mov     [rdx+18h], ecx
0x18010f387  mov     [rdx+8], r15w
0x18010f38c  mov     [rdx+0Ch], r15d
0x18010f390  lea     rax, ??_7CColumnNameProcessor4Byte@NS_BCP_OLEDB@@6B@; const NS_BCP_OLEDB::CColumnNameProcessor4Byte::`vftable'
0x18010f397  mov     [rdx], rax
0x18010f39a  xor     eax, eax
0x18010f39c  mov     [rdx+20h], eax
0x18010f39f  mov     rcx, rdx
0x18010f3a2  jmp     short loc_18010F404
0x18010f3a4  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x18010f3ab  mov     rax, [rcx]
0x18010f3ae  mov     edx, 28h ; '('
0x18010f3b3  mov     rax, [rax+58h]
0x18010f3b7  call    cs:__guard_dispatch_icall_fptr
0x18010f3bd  mov     rdx, rax
0x18010f3c0  mov     [rsp+350h+var_320], rax
0x18010f3c5  test    rax, rax
0x18010f3c8  jz      short loc_18010F3FC
0x18010f3ca  mov     rax, [r14+340h]
0x18010f3d1  mov     ecx, [rax+47Ch]
0x18010f3d7  mov     [rdx+10h], rsi
0x18010f3db  mov     [rdx+18h], ecx
0x18010f3de  mov     [rdx+8], r15w
0x18010f3e3  mov     [rdx+0Ch], r15d
0x18010f3e7  lea     rax, ??_7CColumnNameProcessorDBCS@NS_BCP_OLEDB@@6B@; const NS_BCP_OLEDB::CColumnNameProcessorDBCS::`vftable'
0x18010f3ee  mov     [rdx], rax
0x18010f3f1  xor     eax, eax
0x18010f3f3  mov     [rdx+20h], ax
0x18010f3f7  mov     rcx, rdx
0x18010f3fa  jmp     short loc_18010F404
0x18010f3fc  mov     rcx, r15
0x18010f3ff  mov     [rsp+350h+var_320], rcx
0x18010f404  test    rcx, rcx
0x18010f407  jnz     short loc_18010F413
0x18010f409  mov     ebx, 8007000Eh
0x18010f40e  jmp     loc_18010FD90
0x18010f413  test    edi, edi
0x18010f415  jle     loc_18010FD7E
0x18010f41b  mov     [rsp+350h+var_2F8], r15
0x18010f420  mov     r14d, 1
0x18010f426  mov     [rsp+350h+var_314], r14d
0x18010f42b  mov     rcx, r15
0x18010f42e  mov     [rsp+350h+var_310], rcx
0x18010f433  mov     rdi, [rsp+350h+var_308]
0x18010f438  lea     r12, cs:180000000h
0x18010f43f  mov     rax, [rdi+0AA0h]
0x18010f446  add     rax, rcx
0x18010f449  mov     [rsp+350h+var_300], rax
0x18010f44e  mov     edx, 1; int
0x18010f453  mov     rcx, rsi; this
0x18010f456  call    ?SkipWhiteSpaces@CFormatFileReader@@QEAAJH@Z; CFormatFileReader::SkipWhiteSpaces(int)
0x18010f45b  mov     ebx, eax
0x18010f45d  test    eax, eax
0x18010f45f  js      loc_18010FD59
0x18010f465  lfence
0x18010f468  mov     r8d, 0C8h; unsigned __int64
0x18010f46e  lea     rdx, [rbp+250h+String]; unsigned __int8 *
0x18010f472  mov     rcx, rsi; this
0x18010f475  call    ?ReadNumber@CFormatFileReader@@QEAAJPEAE_K@Z; CFormatFileReader::ReadNumber(uchar *,unsigned __int64)
0x18010f47a  mov     ebx, eax
0x18010f47c  test    eax, eax
0x18010f47e  js      loc_18010FD49
0x18010f484  lea     rcx, [rbp+250h+String]; String
0x18010f488  call    cs:__imp_atoi
0x18010f48e  cmp     eax, r14d
0x18010f491  jnz     loc_18010FD42
0x18010f497  lfence
0x18010f49a  xor     edx, edx; int
0x18010f49c  mov     rcx, rsi; this
0x18010f49f  call    ?SkipWhiteSpaces@CFormatFileReader@@QEAAJH@Z; CFormatFileReader::SkipWhiteSpaces(int)
0x18010f4a4  mov     ebx, eax
0x18010f4a6  test    eax, eax
0x18010f4a8  js      loc_18010FD32
0x18010f4ae  lfence
0x18010f4b1  mov     r8d, 0C8h; unsigned __int64
0x18010f4b7  lea     rdx, [rbp+250h+String]; unsigned __int8 *
0x18010f4bb  mov     rcx, rsi; this
0x18010f4be  call    ?ReadChars@CFormatFileReader@@QEAAJPEAE_K@Z; CFormatFileReader::ReadChars(uchar *,unsigned __int64)
0x18010f4c3  mov     ebx, eax
0x18010f4c5  test    eax, eax
0x18010f4c7  js      loc_18010FD22
0x18010f4cd  lea     rcx, [rbp+250h+String]; lpMultiByteStr
0x18010f4d1  call    ?FieldNameToTDSTypeA@@YAEPEBD@Z; FieldNameToTDSTypeA(char const *)
0x18010f4d6  movzx   edi, al
0x18010f4d9  mov     [rsp+350h+var_318], dil
0x18010f4de  test    al, al
0x18010f4e0  jz      loc_18010FD1B
0x18010f4e6  lfence
0x18010f4e9  xor     edx, edx; int
0x18010f4eb  mov     rcx, rsi; this
0x18010f4ee  call    ?SkipWhiteSpaces@CFormatFileReader@@QEAAJH@Z; CFormatFileReader::SkipWhiteSpaces(int)
0x18010f4f3  mov     ebx, eax
0x18010f4f5  test    eax, eax
0x18010f4f7  js      loc_18010FD0B
0x18010f4fd  lfence
0x18010f500  mov     r8d, 0C8h; unsigned __int64
0x18010f506  lea     rdx, [rbp+250h+String]; unsigned __int8 *
0x18010f50a  mov     rcx, rsi; this
0x18010f50d  call    ?ReadNumber@CFormatFileReader@@QEAAJPEAE_K@Z; CFormatFileReader::ReadNumber(uchar *,unsigned __int64)
0x18010f512  mov     ebx, eax
0x18010f514  test    eax, eax
0x18010f516  js      loc_18010FCFB
0x18010f51c  cmp     [rbp+250h+String], 30h ; '0'
0x18010f520  jnz     short loc_18010F52D
0x18010f522  cmp     [rbp+250h+var_2AF], 0
0x18010f526  jnz     short loc_18010F52D
0x18010f528  mov     r13d, r15d
0x18010f52b  jmp     short loc_18010F542
0x18010f52d  lea     rcx, [rbp+250h+String]; String
0x18010f531  call    cs:__imp_atoi
0x18010f537  mov     r13d, eax
0x18010f53a  test    eax, eax
0x18010f53c  jz      loc_18010FCF4
0x18010f542  lfence
0x18010f545  xor     edx, edx; int
  ... truncated ...
```
