# XMLStream::parsePI(void)

- ea: `0x180037970`
- end: `0x180037deb`
- name: `?parsePI@XMLStream@@AEAAJXZ`
- size: `1147`
- prototype: `__int64 __fastcall(XMLStream *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180036ba0`

## callees

- `0x180037720`
- `0x180037970`
- `0x1800382a8`
- `0x180038320`
- `0x18003838c`
- `0x1800383d0`
- `0x180038a98`
- `0x180038ae0`
- `0x180038d1c`
- `0x180038d48`
- `0x180038ef8`
- `0x180038f2c`
- `0x180041a6c`

## pseudocode

```c
__int64 __fastcall XMLStream::parsePI(XMLStream *this)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  __int64 result; // rax
  _DWORD *v8; // rdx
  int v9; // ecx
  int v10; // r8d
  int v11; // eax
  bool *v12; // rsi
  unsigned __int16 *v13; // r14
  _DWORD *v14; // rdx
  int v15; // ecx
  int v16; // r8d
  int v17; // eax
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  unsigned __int16 *v23; // rsi
  unsigned int v24; // r9d
  BufferedStream *v25; // rcx
  int v26; // [rsp+50h] [rbp+8h] BYREF
  wchar_t *String2; // [rsp+58h] [rbp+10h] BYREF

  v2 = *((__int16 *)this + 4);
  if ( v2 <= 6 )
  {
    if ( v2 == 6 )
    {
      v12 = (bool *)this + 130;
      goto LABEL_51;
    }
    if ( v2 )
    {
      v3 = v2 - 1;
      if ( v3 )
      {
        v4 = v3 - 1;
        if ( v4 )
        {
          v5 = v4 - 1;
          if ( v5 )
          {
            v6 = v5 - 1;
            if ( v6 )
            {
              if ( v6 != 1 )
                return 3222070546LL;
LABEL_23:
              v12 = (bool *)this + 130;
              if ( *((_BYTE *)this + 130) )
                goto LABEL_32;
              v13 = (unsigned __int16 *)((char *)this + 122);
              while ( *v13 != 63 )
              {
                if ( !(unsigned int)isCharData(*v13) )
                  return 3222070554LL;
                result = BufferedStream::nextChar(
                           *((BufferedStream **)this + 11),
                           (unsigned __int16 *)this + 61,
                           (bool *)this + 130);
                if ( (_DWORD)result )
                  return result;
                if ( *v12 )
                  goto LABEL_32;
              }
              result = BufferedStream::nextChar(
                         *((BufferedStream **)this + 11),
                         (unsigned __int16 *)this + 61,
                         (bool *)this + 130);
              if ( !(_DWORD)result )
              {
LABEL_32:
                *((_WORD *)this + 4) = 6;
LABEL_51:
                if ( *v12 )
                  return 3222070621LL;
                if ( *((_WORD *)this + 61) == 62 )
                {
                  result = BufferedStream::nextChar(*((BufferedStream **)this + 11), (unsigned __int16 *)this + 61, v12);
                  if ( (_DWORD)result )
                    return result;
                  *((_DWORD *)this + 28) = -2;
                  *((_DWORD *)this + 27) = 64;
                  goto LABEL_56;
                }
                *((_WORD *)this + 4) = 5;
                return 0;
              }
              return result;
            }
          }
          else
          {
            if ( *((_WORD *)this + 61) == 63 )
            {
              result = BufferedStream::nextChar(
                         *((BufferedStream **)this + 11),
                         (unsigned __int16 *)this + 61,
                         (bool *)this + 130);
              if ( (_DWORD)result )
                return result;
              if ( *((_WORD *)this + 61) != 62 )
                return 3222070538LL;
              *((_WORD *)this + 4) = 6;
              return 0;
            }
            result = XMLStream::push(this, XMLStream::skipWhiteSpace, 4);
            if ( (_DWORD)result )
              return result;
            result = XMLStream::skipWhiteSpace(this);
            if ( (_DWORD)result )
              return result;
            *((_WORD *)this + 4) = 4;
          }
          v8 = (_DWORD *)*((_QWORD *)this + 11);
          v9 = v8[4];
          v10 = v8[11];
          v11 = v9 - 1;
          if ( v9 <= 0 )
            v11 = 0;
          v8[7] = v11;
          if ( v10 != v9 )
          {
            v8[12] = v8[10];
            v8[13] = v10;
          }
          *((_WORD *)this + 4) = 5;
          goto LABEL_23;
        }
LABEL_44:
        if ( *((_BYTE *)this + 130) )
          return 3222070621LL;
        if ( *((_WORD *)this + 61) != 63
          && *(_DWORD *)(*((_QWORD *)this + 11) + 80LL) != *(_DWORD *)(*((_QWORD *)this + 11) + 16LL) )
        {
          return 3222070533LL;
        }
        *((_DWORD *)this + 27) = 3;
        *((_WORD *)this + 4) = 3;
        return 0;
      }
    }
    else
    {
      result = BufferedStream::nextChar(
                 *((BufferedStream **)this + 11),
                 (unsigned __int16 *)this + 61,
                 (bool *)this + 130);
      if ( (_DWORD)result )
        return result;
      result = BufferedStream::Freeze(*((BufferedStream **)this + 11));
      if ( (_DWORD)result )
        return result;
      v14 = (_DWORD *)*((_QWORD *)this + 11);
      v15 = v14[4];
      v16 = v14[11];
      v17 = v15 - 1;
      if ( v15 <= 0 )
        v17 = 0;
      v14[7] = v17;
      if ( v16 != v15 )
      {
        v14[12] = v14[10];
        v14[13] = v16;
      }
      if ( ((*((_WORD *)this + 61) - 88) & 0xFFDF) == 0 )
      {
        *((_WORD *)this + 4) = 7;
        return 0;
      }
      *((_WORD *)this + 4) = 1;
    }
    result = XMLStream::push(this, XMLStream::parseName, 2);
    if ( (_DWORD)result )
      return result;
    result = XMLStream::parseName(this);
    if ( (_DWORD)result )
      return result;
    *((_WORD *)this + 4) = 2;
    goto LABEL_44;
  }
  v18 = v2 - 7;
  if ( !v18 )
  {
    result = BufferedStream::nextChar(
               *((BufferedStream **)this + 11),
               (unsigned __int16 *)this + 61,
               (bool *)this + 130);
    if ( (_DWORD)result )
      return result;
    if ( ((*((_WORD *)this + 61) - 77) & 0xFFDF) != 0 )
      goto LABEL_88;
    *((_WORD *)this + 4) = 8;
    goto LABEL_76;
  }
  v19 = v18 - 1;
  if ( !v19 )
  {
LABEL_76:
    result = BufferedStream::nextChar(
               *((BufferedStream **)this + 11),
               (unsigned __int16 *)this + 61,
               (bool *)this + 130);
    if ( (_DWORD)result )
      return result;
    if ( ((*((_WORD *)this + 61) - 76) & 0xFFDF) != 0 )
      goto LABEL_88;
    *((_WORD *)this + 4) = 9;
    goto LABEL_79;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
LABEL_79:
    v23 = (unsigned __int16 *)((char *)this + 122);
    result = BufferedStream::nextChar(
               *((BufferedStream **)this + 11),
               (unsigned __int16 *)this + 61,
               (bool *)this + 130);
    if ( (_DWORD)result )
      return result;
    v25 = (BufferedStream *)*((_QWORD *)this + 11);
    if ( *((_DWORD *)v25 + 20) == *((_DWORD *)v25 + 4) )
    {
      if ( *((_BYTE *)this + 171) )
        return XMLStream::pushTable(this, 10, (const struct StateEntry *)&unk_180048E40, v24);
      String2 = 0;
      BufferedStream::getToken(v25, (const unsigned __int16 **)&String2, &v26);
      if ( !wcsncmp(L"xml", String2, 3u) )
        return XMLStream::pushTable(this, 10, (const struct StateEntry *)&unk_180048E40, v24);
      else
        return 3222070646LL;
    }
    if ( !(unsigned int)isNameChar(*v23) && *v23 != 58 )
      return 3222070535LL;
LABEL_88:
    *((_WORD *)this + 4) = 11;
    return 0;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
LABEL_56:
    result = XMLStream::pop(this, 1);
    if ( !(_DWORD)result )
      return BufferedStream::UnFreeze(*((BufferedStream **)this + 11));
    return result;
  }
  v22 = v21 - 1;
  if ( v22 )
  {
    if ( v22 != 1 )
      return 3222070546LL;
  }
  else
  {
    if ( *((_WORD *)this + 61) == 58 )
    {
      result = BufferedStream::nextChar(
                 *((BufferedStream **)this + 11),
                 (unsigned __int16 *)this + 61,
                 (bool *)this + 130);
      if ( (_DWORD)result )
        return result;
    }
    *((_WORD *)this + 4) = 12;
  }
  if ( !(unsigned int)isNameChar(*((_WORD *)this + 61)) )
  {
    *((_WORD *)this + 4) = 2;
    return 0;
  }
  result = XMLStream::push(this, XMLStream::parseName, 2);
  if ( !(_DWORD)result )
  {
    *((_WORD *)this + 4) = 1;
    return XMLStream::parseName(this);
  }
  return result;
}

```

## disassembly

```asm
0x180037970  mov     [rsp+arg_10], rbx
0x180037975  push    rbp
0x180037976  push    rsi
0x180037977  push    rdi
0x180037978  push    r14
0x18003797a  push    r15
0x18003797c  sub     rsp, 20h
0x180037980  mov     rbx, rcx
0x180037983  mov     ebp, 6
0x180037988  movsx   ecx, word ptr [rcx+8]
0x18003798c  xor     edi, edi
0x18003798e  cmp     ecx, ebp
0x180037990  jg      loc_180037C2A
0x180037996  lea     r15d, [rbp-1]
0x18003799a  jz      loc_180037BBB
0x1800379a0  test    ecx, ecx
0x1800379a2  jz      loc_180037AD9
0x1800379a8  sub     ecx, 1
0x1800379ab  jz      loc_180037B43
0x1800379b1  sub     ecx, 1
0x1800379b4  jz      loc_180037B76
0x1800379ba  sub     ecx, 1
0x1800379bd  jz      short loc_1800379D2
0x1800379bf  sub     ecx, 1
0x1800379c2  jz      short loc_180037A43
0x1800379c4  cmp     ecx, 1
0x1800379c7  jz      loc_180037A6D
0x1800379cd  jmp     loc_180037C59
0x1800379d2  lea     rsi, [rbx+7Ah]
0x1800379d6  cmp     word ptr [rsi], 3Fh ; '?'
0x1800379da  jnz     short loc_180037A10
0x1800379dc  mov     rcx, [rbx+58h]; this
0x1800379e0  lea     r8, [rbx+82h]; bool *
0x1800379e7  mov     rdx, rsi; unsigned __int16 *
0x1800379ea  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x1800379ef  test    eax, eax
0x1800379f1  jnz     loc_180037DDA
0x1800379f7  cmp     word ptr [rsi], 3Eh ; '>'
0x1800379fb  jnz     short loc_180037A06
0x1800379fd  mov     [rbx+8], bp
0x180037a01  jmp     loc_180037DD8
0x180037a06  mov     eax, 0C00CE50Ah
0x180037a0b  jmp     loc_180037DDA
0x180037a10  mov     esi, 4
0x180037a15  lea     rdx, ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180037a1c  mov     r8d, esi
0x180037a1f  mov     rcx, rbx
0x180037a22  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180037a27  test    eax, eax
0x180037a29  jnz     loc_180037DDA
0x180037a2f  mov     rcx, rbx; this
0x180037a32  call    ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180037a37  test    eax, eax
0x180037a39  jnz     loc_180037DDA
0x180037a3f  mov     [rbx+8], si
0x180037a43  mov     rdx, [rbx+58h]
0x180037a47  mov     ecx, [rdx+10h]
0x180037a4a  test    ecx, ecx
0x180037a4c  mov     r8d, [rdx+2Ch]
0x180037a50  lea     eax, [rcx-1]
0x180037a53  cmovle  eax, edi
0x180037a56  mov     [rdx+1Ch], eax
0x180037a59  cmp     r8d, ecx
0x180037a5c  jz      short loc_180037A68
0x180037a5e  mov     eax, [rdx+28h]
0x180037a61  mov     [rdx+30h], eax
0x180037a64  mov     [rdx+34h], r8d
0x180037a68  mov     [rbx+8], r15w
0x180037a6d  lea     rsi, [rbx+82h]
0x180037a74  cmp     [rsi], dil
0x180037a77  jnz     short loc_180037AD0
0x180037a79  lea     r14, [rbx+7Ah]
0x180037a7d  cmp     word ptr [r14], 3Fh ; '?'
0x180037a82  jz      short loc_180037AB9
0x180037a84  movzx   ecx, word ptr [r14]; unsigned __int16
0x180037a88  call    ?isCharData@@YAHG@Z; isCharData(ushort)
0x180037a8d  test    eax, eax
0x180037a8f  jz      short loc_180037AAF
0x180037a91  mov     rcx, [rbx+58h]; this
0x180037a95  mov     r8, rsi; bool *
0x180037a98  mov     rdx, r14; unsigned __int16 *
0x180037a9b  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180037aa0  test    eax, eax
0x180037aa2  jnz     loc_180037DDA
0x180037aa8  cmp     [rsi], dil
0x180037aab  jz      short loc_180037A7D
0x180037aad  jmp     short loc_180037AD0
0x180037aaf  mov     eax, 0C00CE51Ah
0x180037ab4  jmp     loc_180037DDA
0x180037ab9  mov     rcx, [rbx+58h]; this
0x180037abd  mov     r8, rsi; bool *
0x180037ac0  mov     rdx, r14; unsigned __int16 *
0x180037ac3  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180037ac8  test    eax, eax
0x180037aca  jnz     loc_180037DDA
0x180037ad0  mov     [rbx+8], bp
0x180037ad4  jmp     loc_180037BC2
0x180037ad9  mov     rcx, [rbx+58h]; this
0x180037add  lea     r8, [rbx+82h]; bool *
0x180037ae4  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x180037ae8  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180037aed  test    eax, eax
0x180037aef  jnz     loc_180037DDA
0x180037af5  mov     rcx, [rbx+58h]; this
0x180037af9  call    ?Freeze@BufferedStream@@QEAAJXZ; BufferedStream::Freeze(void)
0x180037afe  test    eax, eax
0x180037b00  jnz     loc_180037DDA
0x180037b06  mov     rdx, [rbx+58h]
0x180037b0a  mov     ecx, [rdx+10h]
0x180037b0d  test    ecx, ecx
0x180037b0f  mov     r8d, [rdx+2Ch]
0x180037b13  lea     eax, [rcx-1]
0x180037b16  cmovle  eax, edi
0x180037b19  mov     [rdx+1Ch], eax
0x180037b1c  cmp     r8d, ecx
0x180037b1f  jz      short loc_180037B2B
0x180037b21  mov     eax, [rdx+28h]
0x180037b24  mov     [rdx+30h], eax
0x180037b27  mov     [rdx+34h], r8d
0x180037b2b  movzx   eax, word ptr [rbx+7Ah]
0x180037b2f  mov     esi, 0FFDFh
0x180037b34  sub     ax, 58h ; 'X'
0x180037b38  test    si, ax
0x180037b3b  jz      short loc_180037BB0
0x180037b3d  mov     word ptr [rbx+8], 1
0x180037b43  mov     esi, 2
0x180037b48  lea     rdx, ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180037b4f  mov     r8d, esi
0x180037b52  mov     rcx, rbx
0x180037b55  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180037b5a  test    eax, eax
0x180037b5c  jnz     loc_180037DDA
0x180037b62  mov     rcx, rbx; this
0x180037b65  call    ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180037b6a  test    eax, eax
0x180037b6c  jnz     loc_180037DDA
0x180037b72  mov     [rbx+8], si
0x180037b76  cmp     [rbx+82h], dil
0x180037b7d  jnz     short loc_180037BC7
0x180037b7f  cmp     word ptr [rbx+7Ah], 3Fh ; '?'
0x180037b84  jz      short loc_180037B9C
0x180037b86  mov     rcx, [rbx+58h]
0x180037b8a  mov     eax, [rcx+10h]
0x180037b8d  cmp     [rcx+50h], eax
0x180037b90  jz      short loc_180037B9C
0x180037b92  mov     eax, 0C00CE505h
0x180037b97  jmp     loc_180037DDA
0x180037b9c  mov     r8d, 3
0x180037ba2  mov     [rbx+6Ch], r8d
0x180037ba6  mov     [rbx+8], r8w
0x180037bab  jmp     loc_180037DD8
0x180037bb0  mov     word ptr [rbx+8], 7
0x180037bb6  jmp     loc_180037DD8
0x180037bbb  lea     rsi, [rbx+82h]
0x180037bc2  cmp     [rsi], dil
0x180037bc5  jz      short loc_180037BD1
0x180037bc7  mov     eax, 0C00CE55Dh
0x180037bcc  jmp     loc_180037DDA
0x180037bd1  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x180037bd5  cmp     word ptr [rdx], 3Eh ; '>'
0x180037bd9  jnz     short loc_180037C20
0x180037bdb  mov     rcx, [rbx+58h]; this
0x180037bdf  mov     r8, rsi; bool *
0x180037be2  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180037be7  test    eax, eax
0x180037be9  jnz     loc_180037DDA
0x180037bef  mov     dword ptr [rbx+70h], 0FFFFFFFEh
0x180037bf6  mov     dword ptr [rbx+6Ch], 40h ; '@'
0x180037bfd  mov     edx, 1; bool
0x180037c02  mov     rcx, rbx; this
0x180037c05  call    ?pop@XMLStream@@AEAAJ_N@Z; XMLStream::pop(bool)
0x180037c0a  test    eax, eax
0x180037c0c  jnz     loc_180037DDA
0x180037c12  mov     rcx, [rbx+58h]; this
0x180037c16  call    ?UnFreeze@BufferedStream@@QEAAJXZ; BufferedStream::UnFreeze(void)
0x180037c1b  jmp     loc_180037DDA
0x180037c20  mov     [rbx+8], r15w
0x180037c25  jmp     loc_180037DD8
0x180037c2a  mov     esi, 0FFDFh
0x180037c2f  sub     ecx, 7
0x180037c32  jz      loc_180037CD3
0x180037c38  sub     ecx, 1
0x180037c3b  jz      loc_180037D06
0x180037c41  sub     ecx, 1
0x180037c44  jz      loc_180037D39
0x180037c4a  sub     ecx, 1
0x180037c4d  jz      short loc_180037BFD
0x180037c4f  sub     ecx, 1
0x180037c52  jz      short loc_180037C63
0x180037c54  cmp     ecx, 1
0x180037c57  jz      short loc_180037C8B
0x180037c59  mov     eax, 0C00CE512h
0x180037c5e  jmp     loc_180037DDA
0x180037c63  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x180037c67  cmp     word ptr [rdx], 3Ah ; ':'
0x180037c6b  jnz     short loc_180037C85
0x180037c6d  mov     rcx, [rbx+58h]; this
0x180037c71  lea     r8, [rbx+82h]; bool *
0x180037c78  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180037c7d  test    eax, eax
0x180037c7f  jnz     loc_180037DDA
0x180037c85  mov     word ptr [rbx+8], 0Ch
0x180037c8b  movzx   ecx, word ptr [rbx+7Ah]; unsigned __int16
0x180037c8f  call    ?isNameChar@@YAHG@Z; isNameChar(ushort)
0x180037c94  test    eax, eax
0x180037c96  jz      short loc_180037CC8
0x180037c98  mov     r8d, 2
0x180037c9e  lea     rdx, ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180037ca5  mov     rcx, rbx
0x180037ca8  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180037cad  test    eax, eax
0x180037caf  jnz     loc_180037DDA
0x180037cb5  mov     rcx, rbx; this
0x180037cb8  mov     word ptr [rbx+8], 1
0x180037cbe  call    ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180037cc3  jmp     loc_180037DDA
0x180037cc8  mov     word ptr [rbx+8], 2
0x180037cce  jmp     loc_180037DD8
0x180037cd3  mov     rcx, [rbx+58h]; this
0x180037cd7  lea     r8, [rbx+82h]; bool *
0x180037cde  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x180037ce2  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180037ce7  test    eax, eax
0x180037ce9  jnz     loc_180037DDA
0x180037cef  movzx   eax, word ptr [rbx+7Ah]
0x180037cf3  sub     ax, 4Dh ; 'M'
0x180037cf7  test    si, ax
0x180037cfa  jnz     loc_180037DD2
0x180037d00  mov     word ptr [rbx+8], 8
0x180037d06  mov     rcx, [rbx+58h]; this
0x180037d0a  lea     r8, [rbx+82h]; bool *
0x180037d11  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x180037d15  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180037d1a  test    eax, eax
0x180037d1c  jnz     loc_180037DDA
0x180037d22  movzx   eax, word ptr [rbx+7Ah]
0x180037d26  sub     ax, 4Ch ; 'L'
0x180037d2a  test    si, ax
0x180037d2d  jnz     loc_180037DD2
0x180037d33  mov     word ptr [rbx+8], 9
0x180037d39  mov     rcx, [rbx+58h]; this
0x180037d3d  lea     rsi, [rbx+7Ah]
0x180037d41  mov     rdx, rsi; unsigned __int16 *
0x180037d44  lea     r8, [rbx+82h]; bool *
0x180037d4b  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180037d50  test    eax, eax
0x180037d52  jnz     loc_180037DDA
0x180037d58  mov     rcx, [rbx+58h]; this
0x180037d5c  mov     eax, [rcx+10h]
0x180037d5f  cmp     [rcx+50h], eax
0x180037d62  jnz     short loc_180037DB9
0x180037d64  cmp     [rbx+0ABh], dil
0x180037d6b  jnz     short loc_180037DA3
0x180037d6d  lea     r8, [rsp+48h+arg_0]; int *
0x180037d72  mov     [rsp+48h+String2], rdi
0x180037d77  lea     rdx, [rsp+48h+String2]; unsigned __int16 **
0x180037d7c  call    ?getToken@BufferedStream@@QEAAJPEAPEBGPEAJ@Z; BufferedStream::getToken(ushort const * *,long *)
0x180037d81  mov     rdx, [rsp+48h+String2]; String2
0x180037d86  lea     rcx, aXml; "xml"
0x180037d8d  mov     r8d, 3; MaxCount
0x180037d93  call    wcsncmp
0x180037d98  test    eax, eax
0x180037d9a  jz      short loc_180037DA3
0x180037d9c  mov     eax, 0C00CE576h
0x180037da1  jmp     short loc_180037DDA
0x180037da3  mov     edx, 0Ah; __int16
0x180037da8  lea     r8, unk_180048E40; struct StateEntry *
0x180037daf  mov     rcx, rbx; this
0x180037db2  call    ?pushTable@XMLStream@@AEAAJFPEBUStateEntry@@K@Z; XMLStream::pushTable(short,StateEntry const *,ulong)
0x180037db7  jmp     short loc_180037DDA
0x180037db9  movzx   ecx, word ptr [rsi]; unsigned __int16
0x180037dbc  call    ?isNameChar@@YAHG@Z; isNameChar(ushort)
0x180037dc1  test    eax, eax
0x180037dc3  jnz     short loc_180037DD2
0x180037dc5  cmp     word ptr [rsi], 3Ah ; ':'
0x180037dc9  jz      short loc_180037DD2
0x180037dcb  mov     eax, 0C00CE507h
0x180037dd0  jmp     short loc_180037DDA
0x180037dd2  mov     word ptr [rbx+8], 0Bh
0x180037dd8  xor     eax, eax
0x180037dda  mov     rbx, [rsp+48h+arg_10]
0x180037ddf  add     rsp, 20h
0x180037de3  pop     r15
0x180037de5  pop     r14
0x180037de7  pop     rdi
0x180037de8  pop     rsi
0x180037de9  pop     rbp
0x180037dea  retn
```
