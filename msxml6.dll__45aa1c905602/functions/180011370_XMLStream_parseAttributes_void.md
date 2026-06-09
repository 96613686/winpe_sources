# XMLStream::parseAttributes(void)

- ea: `0x180011370`
- end: `0x180011dc8`
- name: `?parseAttributes@XMLStream@@AEAAJXZ`
- size: `2648`
- prototype: `HRESULT __fastcall(XMLStream *this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180010274`
- `0x180010f20`
- `0x180011370`
- `0x180011dd0`
- `0x180011f80`
- `0x180012fe0`
- `0x180013164`
- `0x180013180`
- `0x180013460`
- `0x18001368c`
- `0x1800136c8`
- `0x180054874`
- `0x1800549c4`

## string_xrefs

- `0x18001199b`: `xml:space`
- `0x1800119b8`: `xml:lang`
- `0x1800119da`: `xmlns`
- `0x1800119f0`: `xmlns`
- `0x180011d87`: `xmlns`

## pseudocode

```c
HRESULT __fastcall XMLStream::parseAttributes(XMLStream *this)
{
  unsigned int sSubState; // eax
  wchar_t v3; // ax
  HRESULT result; // eax
  int v5; // esi
  unsigned int ncUsed; // r8d
  __int64 v7; // rcx
  char *v8; // rcx
  wchar_t chLookahead; // ax
  unsigned int v10; // r8d
  __int64 v11; // rcx
  char *v12; // rcx
  BufferedStream *p; // rax
  int lCurrent; // ecx
  wchar_t *p_chLookahead; // r8
  BufferedStream *v16; // rdi
  int lUsed; // r9d
  __int64 v18; // rdx
  unsigned int v19; // r9d
  int v20; // edx
  bool v21; // zf
  BufferedStream *v22; // rdi
  wchar_t v23; // ax
  int v24; // r9d
  __int64 v25; // rdx
  unsigned int v26; // r8d
  int v27; // edx
  bool v28; // zf
  BufferedStream *v29; // rcx
  int v30; // eax
  int v31; // edx
  int lLinepos; // edx
  char *v33; // rax
  char *v34; // rcx
  wchar_t *pchBuffer; // rdx
  __int64 lMark; // rsi
  const wchar_t *v37; // rdi
  int v38; // esi
  int v39; // eax
  int NewStart; // eax
  BufferedStream *v41; // rax
  int v42; // ecx
  int v43; // ecx
  __int128 v44; // [rsp+20h] [rbp-18h] BYREF

  sSubState = this->_sSubState;
  if ( !sSubState )
  {
    result = this->_hrErr;
    v5 = 0;
    this->_nAttrType = 0;
    this->_fCheckAttribute = 0;
    if ( result )
    {
      if ( result < 0 )
        return result;
    }
    else
    {
      ncUsed = this->_pStack._ncUsed;
      if ( this->_pStack._ncSize == ncUsed )
      {
        v8 = RawStack::__push(&this->_pStack);
      }
      else
      {
        v7 = this->_pStack._lEntrySize * ncUsed;
        this->_pStack._ncUsed = ncUsed + 1;
        v8 = &this->_pStack._pStack[v7];
      }
      if ( !v8 )
        return -2147024882;
      *((_DWORD *)v8 + 4) = 1;
      *(_OWORD *)v8 = this->_fnState;
      *((_QWORD *)v8 + 3) = this->_pTable;
      *((_DWORD *)v8 + 8) = this->_lEOFError;
      *((_DWORD *)v8 + 9) = this->_cStreamDepth;
      *(_QWORD *)&this->_fnState = XMLStream::skipWhiteSpace;
      HIDWORD(this->_fnState) = HIDWORD(v44);
      this->_sSubState = 0;
      DWORD2(this->_fnState) = 0;
    }
    result = XMLStream::skipWhiteSpace(this);
    if ( result < 0 )
      return result;
    this->_sSubState = 1;
LABEL_16:
    chLookahead = this->_chLookahead;
    if ( chLookahead == this->_chEndChar || chLookahead == 62 )
    {
      v34 = RawStack::_peek(&this->_pStack);
      if ( !v34 )
        return -1072896750;
      result = this->_hrErr;
      if ( !result )
      {
        if ( this->_fDTD
          && !this->_fParsingAttDef
          && !this->_fParseLiteral
          && this->_cStreamDepth != *((_DWORD *)v34 + 9) )
        {
          return -1072896677;
        }
LABEL_95:
        this->_fnState = *(_OWORD *)v34;
        this->_sSubState = *((_DWORD *)v34 + 4);
        this->_pTable = (const StateEntry *)*((_QWORD *)v34 + 3);
        this->_lEOFError = *((_DWORD *)v34 + 8);
        RawStack::_pop(&this->_pStack);
        return 0;
      }
      if ( result < 0 )
        return result;
      return 0;
    }
    if ( chLookahead == 120 )
      this->_fCheckAttribute = 1;
    result = this->_hrErr;
    if ( result )
    {
      if ( result < 0 )
        return result;
    }
    else
    {
      v10 = this->_pStack._ncUsed;
      if ( this->_pStack._ncSize == v10 )
      {
        v12 = RawStack::__push(&this->_pStack);
      }
      else
      {
        v11 = this->_pStack._lEntrySize * v10;
        this->_pStack._ncUsed = v10 + 1;
        v12 = &this->_pStack._pStack[v11];
      }
      if ( !v12 )
        return -2147024882;
      *((_DWORD *)v12 + 4) = 2;
      *(_OWORD *)v12 = this->_fnState;
      *((_QWORD *)v12 + 3) = this->_pTable;
      *((_DWORD *)v12 + 8) = this->_lEOFError;
      *((_DWORD *)v12 + 9) = this->_cStreamDepth;
      *(_QWORD *)&this->_fnState = XMLStream::parseName;
      HIDWORD(this->_fnState) = HIDWORD(v44);
      this->_sSubState = 0;
      DWORD2(this->_fnState) = 0;
    }
    result = XMLStream::parseName(this);
    if ( result < 0 )
      return result;
    if ( this->_pInput._p->_lLastWhiteSpace != this->_pInput._p->_lCurrent && this->_chLookahead != 61 )
      return -1072896763;
    this->_sSubState = 2;
LABEL_29:
    p = this->_pInput._p;
    lCurrent = p->_lCurrent;
    if ( p->_lLastWhiteSpace == lCurrent )
    {
      this->_sSubState = 7;
      return 0;
    }
    if ( this->_fEOF )
      return -1072896674;
    if ( this->_fCheckAttribute )
    {
      pchBuffer = p->_pchBuffer;
      if ( pchBuffer )
      {
        lMark = p->_lMark;
        v37 = &pchBuffer[lMark];
        v5 = lCurrent + ~(_DWORD)lMark;
      }
      else
      {
        v37 = &pwchNamespaceUri;
      }
      v38 = this->_lLengthDelta + v5;
      if ( StringEquals(L"xml:space", v37, v38) )
      {
        this->_nToken = 32;
        goto LABEL_33;
      }
      if ( StringEquals(L"xml:lang", v37, v38) )
      {
        this->_nToken = 33;
        goto LABEL_33;
      }
      if ( this->_lNslen == 5 && StringEquals(L"xmlns", v37, 5) || StringEquals(L"xmlns", v37, v38) )
      {
        if ( v38 == 11 && StringEquals(L"xmlns", v37 + 6, 5) )
          return -1072896664;
        this->_nToken = 31;
        goto LABEL_33;
      }
    }
    this->_nToken = 2;
LABEL_33:
    this->_sSubState = 3;
    return 0;
  }
  if ( sSubState == 3 )
  {
    if ( this->_pInput._p->_lLastWhiteSpace == this->_pInput._p->_lCurrent )
      return -1072896749;
    this->_fWhitespace = 0;
    this->_sSubState = 4;
$LN61:
    p_chLookahead = &this->_chLookahead;
    if ( this->_chLookahead != 61 )
      return -1072896767;
    if ( this->_fDTD )
    {
      result = XMLStream::DTDAdvance(this);
      goto LABEL_48;
    }
    v16 = this->_pInput._p;
    lUsed = v16->_lUsed;
    if ( v16->_lCurrent >= lUsed )
    {
      if ( v16->_fEof )
      {
        this->_fEOF = 1;
        result = 0;
        goto LABEL_48;
      }
      if ( !v16->_fNotified
        && lUsed > 0
        && ((v16->_fNotified = 1, !v16->_fFrozen) ? (v39 = BufferedStream::getNewStart(v16)) : (v39 = 0),
            result = XMLStream::ErrorCallback(v16->_pXMLStream, (v39 + v16->_lSize - lUsed < 4097) - 1072896512),
            v21 = result == 0,
            result < 0)
        || (result = BufferedStream::fillBuffer(v16), v21 = result == 0, result < 0) )
      {
LABEL_49:
        if ( !v21 )
          return result;
        if ( this->_pInput._p->_lLastWhiteSpace == this->_pInput._p->_lCurrent )
        {
          DWORD2(v44) = 0;
          *(_QWORD *)&v44 = XMLStream::skipWhiteSpace;
          result = XMLStream::push(this, &v44, 5u);
          if ( result < 0 )
            return result;
          result = XMLStream::skipWhiteSpace(this);
          if ( result < 0 )
            return result;
        }
        this->_sSubState = 5;
LABEL_52:
        v22 = this->_pInput._p;
        if ( v22->_lLastWhiteSpace != v22->_lCurrent )
        {
          v23 = this->_chLookahead;
          if ( v23 != 34 && v23 != 39 )
            return -1072896766;
          v21 = !this->_fDTD;
          this->_chTerminator = v23;
          if ( !v21 )
          {
            result = XMLStream::DTDAdvance(this);
            goto LABEL_63;
          }
          v24 = v22->_lUsed;
          if ( v22->_lCurrent >= v24 )
          {
            if ( v22->_fEof )
            {
              this->_fEOF = 1;
              result = 0;
              goto LABEL_63;
            }
            if ( !v22->_fNotified
              && v24 > 0
              && ((v21 = !v22->_fFrozen, v22->_fNotified = 1, v21)
                ? (NewStart = BufferedStream::getNewStart(v22))
                : (NewStart = 0),
                  result = XMLStream::ErrorCallback(
                             v22->_pXMLStream,
                             (NewStart + v22->_lSize - v24 < 4097) - 1072896512),
                  v28 = result == 0,
                  result < 0)
              || (result = BufferedStream::fillBuffer(v22), v28 = result == 0, result < 0) )
            {
LABEL_64:
              if ( !v28 )
                return result;
              v29 = this->_pInput._p;
              v30 = v29->_lCurrent;
              if ( v30 <= 0 )
                v31 = 0;
              else
                v31 = v30 - 1;
              v29->_lMark = v31;
              lLinepos = v29->_lLinepos;
              if ( lLinepos != v30 )
              {
                v29->_lMarkedline = v29->_lLine;
                v29->_lMarkedlinepos = lLinepos;
              }
              result = this->_hrErr;
              if ( result )
                return result;
              v33 = RawStack::_push(&this->_pStack);
              if ( v33 )
              {
                *((_DWORD *)v33 + 4) = 6;
                *(_OWORD *)v33 = this->_fnState;
                *((_QWORD *)v33 + 3) = this->_pTable;
                *((_DWORD *)v33 + 8) = this->_lEOFError;
                *((_DWORD *)v33 + 9) = this->_cStreamDepth;
                *(_QWORD *)&this->_fnState = XMLStream::parseAttrValue;
                HIDWORD(this->_fnState) = HIDWORD(v44);
                result = 0;
                this->_sSubState = 0;
                DWORD2(this->_fnState) = 0;
                return result;
              }
              return -2147024882;
            }
            if ( v22->_fEof )
            {
              this->_fEOF = 1;
              result = 0;
              goto LABEL_63;
            }
            v22->_fNotified = 0;
          }
          v25 = v22->_lCurrent;
          v26 = v22->_pchBuffer[v25];
          v27 = v25 + 1;
          v22->_lCurrent = v27;
          if ( v26 <= 0x20 )
          {
            if ( v26 != 32 && v26 != 9 )
            {
              if ( v26 != 10 && v26 != 13 )
                goto LABEL_61;
              if ( v26 == 13 || v22->_chLast != 13 )
                ++v22->_lLine;
              v22->_lLinepos = v27;
              v22->_chLast = v26;
            }
            v22->_lLastWhiteSpace = v27;
            goto LABEL_85;
          }
          if ( v26 - 65534 <= 1 )
            goto LABEL_62;
LABEL_61:
          if ( v26 < 0x20 )
          {
LABEL_62:
            result = -1072896760;
LABEL_63:
            v28 = result == 0;
            goto LABEL_64;
          }
LABEL_85:
          this->_chLookahead = v26;
          result = 0;
          goto LABEL_63;
        }
        return -1072896749;
      }
      if ( v16->_fEof )
      {
        this->_fEOF = 1;
        result = 0;
        goto LABEL_48;
      }
      v16->_fNotified = 0;
      p_chLookahead = &this->_chLookahead;
    }
    v18 = v16->_lCurrent;
    v19 = v16->_pchBuffer[v18];
    v20 = v18 + 1;
    v16->_lCurrent = v20;
    if ( v19 <= 0x20 )
    {
      if ( v19 != 32 && v19 != 9 )
      {
        if ( v19 != 10 && v19 != 13 )
          goto LABEL_46;
        if ( v19 == 13 || v16->_chLast != 13 )
        {
          ++v16->_lLine;
          p_chLookahead = &this->_chLookahead;
        }
        v16->_lLinepos = v20;
        v16->_chLast = v19;
      }
      v16->_lLastWhiteSpace = v20;
      goto LABEL_80;
    }
    if ( v19 - 65534 <= 1 )
      goto LABEL_47;
LABEL_46:
    if ( v19 < 0x20 )
    {
LABEL_47:
      result = -1072896760;
LABEL_48:
      v21 = result == 0;
      goto LABEL_49;
    }
LABEL_80:
    *p_chLookahead = v19;
    result = 0;
    goto LABEL_48;
  }
  if ( sSubState != 6 )
  {
    switch ( sSubState )
    {
      case 1u:
        v5 = 0;
        goto LABEL_16;
      case 2u:
        v5 = 0;
        goto LABEL_29;
      case 4u:
        goto $LN61;
      case 5u:
        goto LABEL_52;
      case 7u:
        v41 = this->_pInput._p;
        DWORD2(v44) = 0;
        v42 = v41->_lCurrent + ~v41->_lMark;
        *(_QWORD *)&v44 = XMLStream::skipWhiteSpace;
        LODWORD(v41) = HIDWORD(v44);
        this->_lLengthDelta = v42;
        HIDWORD(v44) = (_DWORD)v41;
        result = XMLStream::push(this, &v44, 8u);
        if ( result < 0 )
          return result;
        result = XMLStream::skipWhiteSpace(this);
        if ( result < 0 )
          return result;
        this->_sSubState = 8;
$LN80_0:
        if ( this->_fEOF )
          return -1072896674;
        v43 = this->_pInput._p->_lMark - this->_pInput._p->_lCurrent + 1;
        this->_sSubState = 2;
        this->_lLengthDelta += v43;
        break;
      case 8u:
        goto $LN80_0;
      default:
        return -1072896750;
    }
    return 0;
  }
  if ( this->_fEOF )
    return -1072896674;
  v3 = this->_chLookahead;
  if ( v3 != this->_chEndChar && v3 != 62 )
  {
    if ( this->_pInput._p->_lLastWhiteSpace != this->_pInput._p->_lCurrent )
      return -1072896759;
    this->_sSubState = 0;
    return 0;
  }
  v34 = RawStack::_peek(&this->_pStack);
  if ( !v34 )
    return -1072896750;
  result = this->_hrErr;
  if ( !result )
  {
    if ( this->_fDTD && !this->_fParsingAttDef && !this->_fParseLiteral && this->_cStreamDepth != *((_DWORD *)v34 + 9) )
      return -1072896677;
    goto LABEL_95;
  }
  if ( result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180011370  mov     [rsp+arg_0], rbx
0x180011375  mov     [rsp+arg_8], rsi
0x18001137a  push    rdi
0x18001137b  sub     rsp, 30h
0x18001137f  mov     eax, [this+28h]
0x180011382  mov     rbx, this
0x180011385  test    eax, eax
0x180011387  jz      short loc_1800113EE
0x180011389  cmp     eax, 3
0x18001138c  jz      loc_1800115A5
0x180011392  cmp     eax, 6
0x180011395  jnz     loc_180011799
0x18001139b  cmp     byte ptr [this+0A4h], 0
0x1800113a2  jnz     loc_180011A8C
0x1800113a8  movzx   eax, word ptr [this+9Ah]
0x1800113af  cmp     ax, [this+0A2h]
0x1800113b6  jz      loc_18001185D
0x1800113bc  cmp     ax, 3Eh ; '>'
0x1800113c0  jz      loc_18001185D
0x1800113c6  mov     this, [this+78h]
0x1800113ca  mov     eax, [this+28h]
0x1800113cd  cmp     [this+64h], eax
0x1800113d0  jnz     loc_180011950
0x1800113d6  xor     esi, esi
0x1800113d8  mov     [rbx+28h], esi
0x1800113db  xor     eax, eax
0x1800113dd  mov     rbx, [rsp+38h+arg_0]
0x1800113e2  mov     rsi, [rsp+38h+arg_8]
0x1800113e7  add     rsp, 30h
0x1800113eb  pop     rdi
0x1800113ec  retn
0x1800113ee  mov     eax, [this+128h]
0x1800113f4  xor     esi, esi
0x1800113f6  mov     [this+0C8h], esi
0x1800113fc  mov     [this+101h], sil
0x180011403  test    eax, eax
0x180011405  jnz     loc_180011838
0x18001140b  mov     r8d, [this+40h]
0x18001140f  cmp     [this+44h], r8d
0x180011413  jz      loc_180011A6C
0x180011419  mov     ecx, r8d
0x18001141c  lea     eax, [r8+1]
0x180011420  imul    ecx, [rbx+30h]
0x180011424  mov     [rbx+40h], eax
0x180011427  add     this, [rbx+38h]
0x18001142b  test    this, this
0x18001142e  jz      loc_180011D73
0x180011434  mov     dword ptr [this+10h], 1
0x18001143b  movups  xmm0, xmmword ptr [rbx+18h]
0x18001143f  movups  xmmword ptr [this], xmm0
0x180011442  mov     rax, [rbx+0E0h]
0x180011449  mov     [this+18h], rax
0x18001144d  mov     eax, [rbx+0E8h]
0x180011453  mov     [this+20h], eax
0x180011456  mov     eax, [rbx+70h]
0x180011459  mov     [this+24h], eax
0x18001145c  lea     rax, ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180011463  mov     [rbx+18h], rax
0x180011467  mov     eax, [rsp+38h+var_C]
0x18001146b  mov     [rbx+24h], eax
0x18001146e  mov     [rbx+28h], esi
0x180011471  mov     [rbx+20h], esi
0x180011474  mov     this, rbx; this
0x180011477  call    ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x18001147c  test    eax, eax
0x18001147e  js      loc_180011594
0x180011484  mov     dword ptr [rbx+28h], 1
0x18001148b  movzx   eax, word ptr [rbx+9Ah]
0x180011492  cmp     ax, [rbx+0A2h]
0x180011499  jz      loc_1800118F7
0x18001149f  cmp     ax, 3Eh ; '>'
0x1800114a3  jz      loc_1800118F7
0x1800114a9  cmp     ax, 78h ; 'x'
0x1800114ad  jz      loc_1800118EB
0x1800114b3  mov     eax, [rbx+128h]
0x1800114b9  test    eax, eax
0x1800114bb  jnz     loc_1800117C2
0x1800114c1  mov     r8d, [rbx+40h]
0x1800114c5  cmp     [rbx+44h], r8d
0x1800114c9  jz      loc_180011A5B
0x1800114cf  mov     ecx, r8d
0x1800114d2  lea     eax, [r8+1]
0x1800114d6  imul    ecx, [rbx+30h]
0x1800114da  mov     [rbx+40h], eax
0x1800114dd  add     this, [rbx+38h]
0x1800114e1  test    this, this
0x1800114e4  jz      loc_180011D73
0x1800114ea  mov     dword ptr [this+10h], 2
0x1800114f1  movups  xmm0, xmmword ptr [rbx+18h]
0x1800114f5  movups  xmmword ptr [this], xmm0
0x1800114f8  mov     rax, [rbx+0E0h]
0x1800114ff  mov     [this+18h], rax
0x180011503  mov     eax, [rbx+0E8h]
0x180011509  mov     [this+20h], eax
0x18001150c  mov     eax, [rbx+70h]
0x18001150f  mov     [this+24h], eax
0x180011512  lea     rax, ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180011519  mov     [rbx+18h], rax
0x18001151d  mov     eax, [rsp+38h+var_C]
0x180011521  mov     [rbx+24h], eax
0x180011524  mov     [rbx+28h], esi
0x180011527  mov     [rbx+20h], esi
0x18001152a  mov     this, rbx; this
0x18001152d  call    ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180011532  test    eax, eax
0x180011534  js      short loc_180011594
0x180011536  mov     this, [rbx+78h]
0x18001153a  mov     eax, [this+28h]
0x18001153d  cmp     [this+64h], eax
0x180011540  jz      short loc_180011550
0x180011542  cmp     word ptr [rbx+9Ah], 3Dh ; '='
0x18001154a  jnz     loc_180011AAF
0x180011550  mov     dword ptr [rbx+28h], 2
0x180011557  mov     rax, [rbx+78h]
0x18001155b  mov     ecx, [rax+28h]
0x18001155e  cmp     [rax+64h], ecx
0x180011561  jz      loc_180011ADB
0x180011567  cmp     byte ptr [rbx+0A4h], 0
0x18001156e  jnz     loc_180011A8C
0x180011574  cmp     byte ptr [rbx+101h], 0
0x18001157b  jnz     loc_18001197C
0x180011581  mov     dword ptr [rbx+8Ch], 2
0x18001158b  mov     dword ptr [rbx+28h], 3
0x180011592  xor     eax, eax
0x180011594  mov     rbx, [rsp+38h+arg_0]
0x180011599  mov     rsi, [rsp+38h+arg_8]
0x18001159e  add     rsp, 30h
0x1800115a2  pop     rdi
0x1800115a3  retn
0x1800115a5  mov     this, [this+78h]
0x1800115a9  mov     eax, [this+28h]
0x1800115ac  cmp     [this+64h], eax
0x1800115af  jz      loc_180011AC5
0x1800115b5  mov     byte ptr [rbx+9Ch], 0
0x1800115bc  mov     dword ptr [rbx+28h], 4
0x1800115c3  lea     r8, [rbx+9Ah]; jumptable 00000001800117B5 case 4
0x1800115ca  cmp     word ptr [r8], 3Dh ; '='
0x1800115cf  jnz     loc_180011D21
0x1800115d5  xor     esi, esi
0x1800115d7  cmp     [rbx+102h], sil
0x1800115de  jnz     loc_180011A4E
0x1800115e4  mov     rdi, [rbx+78h]
0x1800115e8  mov     r9d, [rdi+34h]
0x1800115ec  cmp     [rdi+28h], r9d
0x1800115f0  jge     loc_1800118BB
0x1800115f6  movsxd  rdx, dword ptr [rdi+28h]
0x1800115fa  mov     rax, [rdi+20h]
0x1800115fe  movzx   r9d, word ptr [rax+rdx*2]
0x180011603  inc     edx
0x180011605  mov     [rdi+28h], edx
0x180011608  mov     ecx, r9d
0x18001160b  cmp     r9d, 20h ; ' '
0x18001160f  ja      loc_18001181E
0x180011615  jz      loc_1800117E9
0x18001161b  sub     ecx, 9
0x18001161e  jz      loc_1800117E9
0x180011624  sub     ecx, 1
0x180011627  jz      loc_1800117CD
0x18001162d  cmp     ecx, 3
0x180011630  jz      loc_1800117CD
0x180011636  cmp     r9d, 20h ; ' '
0x18001163a  jnb     loc_1800117EC
0x180011640  mov     eax, 0C00CE508h
0x180011645  test    eax, eax
0x180011647  jnz     loc_180011594
0x18001164d  mov     this, [rbx+78h]
0x180011651  mov     eax, [this+28h]
0x180011654  cmp     [this+64h], eax
0x180011657  jz      loc_180011D2B
0x18001165d  mov     dword ptr [rbx+28h], 5
0x180011664  mov     rdi, [rbx+78h]
0x180011668  mov     eax, [rdi+28h]
0x18001166b  cmp     [rdi+64h], eax
0x18001166e  jz      loc_180011AC5
0x180011674  movzx   eax, word ptr [rbx+9Ah]
0x18001167b  cmp     ax, 22h ; '"'
0x18001167f  jnz     loc_180011A2E
0x180011685  cmp     byte ptr [rbx+102h], 0
0x18001168c  mov     [rbx+9Eh], ax
0x180011693  jnz     loc_180011AA2
0x180011699  mov     r9d, [rdi+34h]
0x18001169d  cmp     [rdi+28h], r9d
0x1800116a1  jge     loc_1800118D3
0x1800116a7  movsxd  rdx, dword ptr [rdi+28h]
0x1800116ab  mov     rax, [rdi+20h]
0x1800116af  movzx   r8d, word ptr [rax+rdx*2]
0x1800116b4  inc     edx
0x1800116b6  mov     [rdi+28h], edx
0x1800116b9  mov     ecx, r8d
0x1800116bc  cmp     r8d, 20h ; ' '
0x1800116c0  ja      loc_180011843
0x1800116c6  jz      loc_18001180C
0x1800116cc  sub     ecx, 9
0x1800116cf  jz      loc_18001180C
0x1800116d5  sub     ecx, 1
0x1800116d8  jz      loc_1800117F7
0x1800116de  cmp     ecx, 3
0x1800116e1  jz      loc_1800117F7
0x1800116e7  cmp     r8d, 20h ; ' '
0x1800116eb  jnb     loc_18001180F
0x1800116f1  mov     eax, 0C00CE508h
0x1800116f6  test    eax, eax
0x1800116f8  jnz     loc_180011594
0x1800116fe  mov     this, [rbx+78h]
0x180011702  mov     eax, [this+28h]
0x180011705  test    eax, eax
0x180011707  jle     loc_180011AF5
0x18001170d  lea     edx, [rax-1]
0x180011710  mov     [this+30h], edx
0x180011713  mov     edx, [this+40h]
0x180011716  cmp     edx, eax
0x180011718  jz      short loc_180011723
0x18001171a  mov     eax, [this+3Ch]
0x18001171d  mov     [this+44h], eax
0x180011720  mov     [this+48h], edx
0x180011723  mov     eax, [rbx+128h]
0x180011729  test    eax, eax
0x18001172b  jnz     loc_180011594
0x180011731  lea     this, [rbx+30h]; this
0x180011735  call    ?_push@RawStack@@IEAAPEADXZ; RawStack::_push(void)
0x18001173a  mov     this, rax
0x18001173d  test    rax, rax
0x180011740  jz      loc_180011D73
0x180011746  mov     dword ptr [rax+10h], 6
0x18001174d  movups  xmm0, xmmword ptr [rbx+18h]
0x180011751  movups  xmmword ptr [rax], xmm0
0x180011754  mov     rax, [rbx+0E0h]
0x18001175b  mov     [this+18h], rax
0x18001175f  mov     eax, [rbx+0E8h]
0x180011765  mov     [this+20h], eax
0x180011768  mov     eax, [rbx+70h]
0x18001176b  mov     [this+24h], eax
0x18001176e  lea     rax, ?parseAttrValue@XMLStream@@AEAAJXZ; XMLStream::parseAttrValue(void)
0x180011775  mov     [rbx+18h], rax
0x180011779  mov     eax, [rsp+38h+var_C]
0x18001177d  mov     [rbx+24h], eax
0x180011780  mov     eax, esi
0x180011782  mov     [rbx+28h], esi
0x180011785  mov     [rbx+20h], esi
0x180011788  mov     rbx, [rsp+38h+arg_0]
0x18001178d  mov     rsi, [rsp+38h+arg_8]
0x180011792  add     rsp, 30h
0x180011796  pop     rdi
0x180011797  retn
0x180011799  dec     eax; switch 8 cases
0x18001179b  cmp     eax, 7
0x18001179e  ja      def_1800117B5; jumptable 00000001800117B5 default case, cases 3,6
0x1800117a4  lea     this, __ImageBase
0x1800117ab  mov     eax, ds:(jpt_1800117B5 - 180000000h)[this+rax*4]
0x1800117b2  add     rax, this
0x1800117b5  jmp     rax; switch jump
0x1800117bb  xor     esi, esi; jumptable 00000001800117B5 case 1
0x1800117bd  jmp     loc_18001148B
0x1800117c2  js      loc_180011594
0x1800117c8  jmp     loc_18001152A
0x1800117cd  cmp     r9d, 0Dh
0x1800117d1  jnz     loc_180011C01
0x1800117d7  inc     dword ptr [rdi+3Ch]
0x1800117da  lea     r8, [rbx+9Ah]
0x1800117e1  mov     [rdi+40h], edx
0x1800117e4  mov     [rdi+38h], r9w
0x1800117e9  mov     [rdi+64h], edx
0x1800117ec  mov     [r8], r9w
0x1800117f0  mov     eax, esi
0x1800117f2  jmp     loc_180011645
0x1800117f7  cmp     r8d, 0Dh
0x1800117fb  jnz     loc_180011C11
0x180011801  inc     dword ptr [rdi+3Ch]
0x180011804  mov     [rdi+40h], edx
0x180011807  mov     [rdi+38h], r8w
0x18001180c  mov     [rdi+64h], edx
0x18001180f  mov     [rbx+9Ah], r8w
0x180011817  mov     eax, esi
0x180011819  jmp     loc_1800116F6
0x18001181e  sub     ecx, 0FFFEh
0x180011824  jz      loc_180011640
0x18001182a  cmp     ecx, 1
0x18001182d  jnz     loc_180011636
0x180011833  jmp     loc_180011640
0x180011838  jns     loc_180011474
0x18001183e  jmp     loc_180011594
0x180011843  sub     ecx, 0FFFEh
0x180011849  jz      loc_1800116F1
0x18001184f  cmp     ecx, 1
0x180011852  jnz     loc_1800116E7
0x180011858  jmp     loc_1800116F1
0x18001185d  add     this, 30h ; '0'; this
0x180011861  call    ?_peek@RawStack@@IEAAPEADXZ; RawStack::_peek(void)
0x180011866  mov     this, rax
0x180011869  test    rax, rax
0x18001186c  jz      def_1800117B5; jumptable 00000001800117B5 default case, cases 3,6
0x180011872  mov     eax, [rbx+128h]
0x180011878  test    eax, eax
0x18001187a  jnz     loc_180011C3B
0x180011880  cmp     [rbx+102h], al
0x180011886  jnz     loc_180011CF6
0x18001188c  movups  xmm0, xmmword ptr [this]
0x18001188f  movups  xmmword ptr [rbx+18h], xmm0
0x180011893  mov     eax, [this+10h]
0x180011896  mov     [rbx+28h], eax
  ... truncated ...
```
