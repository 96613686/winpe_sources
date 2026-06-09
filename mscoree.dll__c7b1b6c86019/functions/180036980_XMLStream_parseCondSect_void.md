# XMLStream::parseCondSect(void)

- ea: `0x180036980`
- end: `0x180036b92`
- name: `?parseCondSect@XMLStream@@AEAAJXZ`
- size: `530`
- prototype: `__int64 __fastcall(XMLStream *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180036600`
- `0x180036980`
- `0x180037720`
- `0x1800382a8`
- `0x180038320`
- `0x1800383d0`
- `0x180038ef8`
- `0x180038f2c`

## pseudocode

```c
__int64 __fastcall XMLStream::parseCondSect(XMLStream *this)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  __int64 result; // rax
  __int16 v8; // cx
  _WORD *v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // edi
  int v13; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 *v14; // [rsp+48h] [rbp+10h] BYREF

  v2 = *((__int16 *)this + 4);
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
          if ( !v6 )
          {
            BufferedStream::getToken(*((BufferedStream **)this + 11), (const unsigned __int16 **)&v14, &v13);
            return 3222070545LL;
          }
          if ( v6 != 1 )
            return 3222070546LL;
          while ( 1 )
          {
            v8 = **((_WORD **)this + 19);
            v9 = (_WORD *)((char *)this + 122);
            if ( !v8 )
              break;
            if ( *v9 != v8 || *((_BYTE *)this + 130) )
            {
              *((_WORD *)this + 4) = 2;
              return 0;
            }
            result = BufferedStream::nextChar(
                       *((BufferedStream **)this + 11),
                       (unsigned __int16 *)this + 61,
                       (bool *)this + 130);
            if ( (_DWORD)result )
              return result;
            *((_QWORD *)this + 19) += 2LL;
            if ( *((_BYTE *)this + 130) )
              return 3222070627LL;
          }
          if ( *v9 == 91 )
          {
            if ( *((_BYTE *)this + 204) )
              return 3222070648LL;
            v10 = *((_DWORD *)this + 8);
            if ( !v10 )
              return 2147549183LL;
            v11 = *((_DWORD *)this + 4) * (v10 - 1) + *((_QWORD *)this + 3);
            if ( !v11 )
              return 2147549183LL;
            v12 = *((_DWORD *)this + 20);
            *((_DWORD *)this + 20) = *(_DWORD *)(v11 + 24);
            result = XMLStream::pop(this, 0);
            if ( !(_DWORD)result )
            {
              result = XMLStream::push((__int64)this, (__int64)XMLStream::parseCData, *((_WORD *)this + 4));
              if ( !(_DWORD)result )
              {
                *((_DWORD *)this + 20) = v12;
                return XMLStream::parseCData(this);
              }
            }
            return result;
          }
          return 3222070544LL;
        }
        if ( !*((_BYTE *)this + 130) )
        {
          result = XMLStream::push((__int64)this, (__int64)XMLStream::parseName, 4);
          if ( !(_DWORD)result )
            return XMLStream::parseName(this);
          return result;
        }
        return 3222070627LL;
      }
      goto LABEL_36;
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
    *((_WORD *)this + 4) = 1;
  }
  if ( *((_BYTE *)this + 130) )
    return 3222070627LL;
  if ( *((_WORD *)this + 61) == 67 )
  {
    *((_WORD *)this + 4) = 5;
    *((_QWORD *)this + 19) = L"CDATA";
    return 0;
  }
  *((_WORD *)this + 4) = 2;
LABEL_36:
  if ( *((_BYTE *)this + 130) )
    return 3222070544LL;
  result = XMLStream::push((__int64)this, (__int64)XMLStream::skipWhiteSpace, 3);
  if ( !(_DWORD)result )
    return XMLStream::skipWhiteSpace(this);
  return result;
}

```

## disassembly

```asm
0x180036980  mov     [rsp+arg_10], rbx
0x180036985  push    rbp
0x180036986  push    rsi
0x180036987  push    rdi
0x180036988  sub     rsp, 20h
0x18003698c  mov     rbx, rcx
0x18003698f  xor     ebp, ebp
0x180036991  movsx   ecx, word ptr [rcx+8]
0x180036995  test    ecx, ecx
0x180036997  jz      loc_180036B01
0x18003699d  sub     ecx, 1
0x1800369a0  jz      loc_180036B1F
0x1800369a6  sub     ecx, 1
0x1800369a9  jz      loc_180036B54
0x1800369af  sub     ecx, 1
0x1800369b2  jz      loc_180036ACE
0x1800369b8  sub     ecx, 1
0x1800369bb  jz      loc_180036AB1
0x1800369c1  cmp     ecx, 1
0x1800369c4  jz      short loc_1800369D0
0x1800369c6  mov     eax, 0C00CE512h
0x1800369cb  jmp     loc_180036B85
0x1800369d0  mov     edi, 2
0x1800369d5  mov     rax, [rbx+98h]
0x1800369dc  movzx   ecx, word ptr [rax]
0x1800369df  lea     rax, [rbx+7Ah]
0x1800369e3  test    cx, cx
0x1800369e6  jz      short loc_180036A2A
0x1800369e8  cmp     [rax], cx
0x1800369eb  jnz     short loc_180036A21
0x1800369ed  lea     rsi, [rbx+82h]
0x1800369f4  cmp     [rsi], bpl
0x1800369f7  jnz     short loc_180036A21
0x1800369f9  mov     rcx, [rbx+58h]; this
0x1800369fd  mov     r8, rsi; bool *
0x180036a00  mov     rdx, rax; unsigned __int16 *
0x180036a03  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180036a08  test    eax, eax
0x180036a0a  jnz     loc_180036B85
0x180036a10  add     [rbx+98h], rdi
0x180036a17  cmp     [rsi], bpl
0x180036a1a  jz      short loc_1800369D5
0x180036a1c  jmp     loc_180036B28
0x180036a21  mov     [rbx+8], di
0x180036a25  jmp     loc_180036B4A
0x180036a2a  cmp     word ptr [rax], 5Bh ; '['
0x180036a2e  jnz     loc_180036B5D
0x180036a34  cmp     [rbx+0CCh], bpl
0x180036a3b  jz      short loc_180036A47
0x180036a3d  mov     eax, 0C00CE578h
0x180036a42  jmp     loc_180036B85
0x180036a47  mov     eax, [rbx+20h]
0x180036a4a  test    eax, eax
0x180036a4c  jz      short loc_180036AA7
0x180036a4e  dec     eax
0x180036a50  imul    eax, [rbx+10h]
0x180036a54  movsxd  rcx, eax
0x180036a57  mov     rax, [rbx+18h]
0x180036a5b  add     rax, rcx
0x180036a5e  jz      short loc_180036AA7
0x180036a60  mov     edi, [rbx+50h]
0x180036a63  xor     edx, edx; bool
0x180036a65  mov     eax, [rax+18h]
0x180036a68  mov     rcx, rbx; this
0x180036a6b  mov     [rbx+50h], eax
0x180036a6e  call    ?pop@XMLStream@@AEAAJ_N@Z; XMLStream::pop(bool)
0x180036a73  test    eax, eax
0x180036a75  jnz     loc_180036B85
0x180036a7b  movzx   r8d, word ptr [rbx+8]
0x180036a80  lea     rdx, ?parseCData@XMLStream@@AEAAJXZ; XMLStream::parseCData(void)
0x180036a87  mov     rcx, rbx
0x180036a8a  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180036a8f  test    eax, eax
0x180036a91  jnz     loc_180036B85
0x180036a97  mov     rcx, rbx; this
0x180036a9a  mov     [rbx+50h], edi
0x180036a9d  call    ?parseCData@XMLStream@@AEAAJXZ; XMLStream::parseCData(void)
0x180036aa2  jmp     loc_180036B85
0x180036aa7  mov     eax, 8000FFFFh
0x180036aac  jmp     loc_180036B85
0x180036ab1  mov     rcx, [rbx+58h]; this
0x180036ab5  lea     r8, [rsp+38h+arg_0]; int *
0x180036aba  lea     rdx, [rsp+38h+arg_8]; unsigned __int16 **
0x180036abf  call    ?getToken@BufferedStream@@QEAAJPEAPEBGPEAJ@Z; BufferedStream::getToken(ushort const * *,long *)
0x180036ac4  mov     eax, 0C00CE511h
0x180036ac9  jmp     loc_180036B85
0x180036ace  cmp     [rbx+82h], bpl
0x180036ad5  jnz     short loc_180036B28
0x180036ad7  mov     r8d, 4
0x180036add  lea     rdx, ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180036ae4  mov     rcx, rbx
0x180036ae7  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180036aec  test    eax, eax
0x180036aee  jnz     loc_180036B85
0x180036af4  mov     rcx, rbx; this
0x180036af7  call    ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180036afc  jmp     loc_180036B85
0x180036b01  mov     rcx, [rbx+58h]; this
0x180036b05  lea     r8, [rbx+82h]; bool *
0x180036b0c  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x180036b10  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180036b15  test    eax, eax
0x180036b17  jnz     short loc_180036B85
0x180036b19  mov     word ptr [rbx+8], 1
0x180036b1f  cmp     [rbx+82h], bpl
0x180036b26  jz      short loc_180036B2F
0x180036b28  mov     eax, 0C00CE563h
0x180036b2d  jmp     short loc_180036B85
0x180036b2f  cmp     word ptr [rbx+7Ah], 43h ; 'C'
0x180036b34  jnz     short loc_180036B4E
0x180036b36  lea     rax, aCdata; "CDATA"
0x180036b3d  mov     word ptr [rbx+8], 5
0x180036b43  mov     [rbx+98h], rax
0x180036b4a  xor     eax, eax
0x180036b4c  jmp     short loc_180036B85
0x180036b4e  mov     word ptr [rbx+8], 2
0x180036b54  cmp     [rbx+82h], bpl
0x180036b5b  jz      short loc_180036B64
0x180036b5d  mov     eax, 0C00CE510h
0x180036b62  jmp     short loc_180036B85
0x180036b64  mov     r8d, 3
0x180036b6a  lea     rdx, ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180036b71  mov     rcx, rbx
0x180036b74  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180036b79  test    eax, eax
0x180036b7b  jnz     short loc_180036B85
0x180036b7d  mov     rcx, rbx; this
0x180036b80  call    ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180036b85  mov     rbx, [rsp+38h+arg_10]
0x180036b8a  add     rsp, 20h
0x180036b8e  pop     rdi
0x180036b8f  pop     rsi
0x180036b90  pop     rbp
0x180036b91  retn
```
