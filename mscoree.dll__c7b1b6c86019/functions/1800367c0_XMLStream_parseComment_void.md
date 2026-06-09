# XMLStream::parseComment(void)

- ea: `0x1800367c0`
- end: `0x180036972`
- name: `?parseComment@XMLStream@@AEAAJXZ`
- size: `434`
- prototype: `__int64 __fastcall(XMLStream *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800367c0`
- `0x1800382a8`
- `0x180038a98`
- `0x180038f2c`

## pseudocode

```c
__int64 __fastcall XMLStream::parseComment(XMLStream *this)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  __int64 result; // rax
  _DWORD *v7; // r8
  int v8; // edx
  int v9; // ecx
  int v10; // ecx
  _BYTE *v11; // rdi
  unsigned __int16 *v12; // rdx
  unsigned __int16 *v13; // rdx

  v2 = *((__int16 *)this + 4);
  if ( !v2 )
  {
    result = BufferedStream::nextChar(
               *((BufferedStream **)this + 11),
               (unsigned __int16 *)this + 61,
               (bool *)this + 130);
    if ( (_DWORD)result )
      return result;
    if ( *((_BYTE *)this + 130) )
      return 3222070625LL;
    if ( *((_WORD *)this + 61) != 45 )
      return 3222070531LL;
    *((_WORD *)this + 4) = 1;
    goto LABEL_11;
  }
  v3 = v2 - 1;
  if ( !v3 )
  {
LABEL_11:
    result = BufferedStream::nextChar(
               *((BufferedStream **)this + 11),
               (unsigned __int16 *)this + 61,
               (bool *)this + 130);
    if ( (_DWORD)result )
      return result;
    v7 = (_DWORD *)*((_QWORD *)this + 11);
    v8 = v7[4];
    v9 = v8 - 1;
    if ( v8 <= 0 )
      v9 = 0;
    v7[7] = v9;
    v10 = v7[11];
    if ( v10 != v8 )
    {
      v7[12] = v7[10];
      v7[13] = v10;
    }
    *((_WORD *)this + 4) = 2;
    goto LABEL_17;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
LABEL_17:
    v11 = (char *)this + 130;
    while ( !*v11 )
    {
      v12 = (unsigned __int16 *)((char *)this + 122);
      if ( *((_WORD *)this + 61) == 45 )
      {
        result = BufferedStream::nextChar(*((BufferedStream **)this + 11), v12, (bool *)this + 130);
        if ( (_DWORD)result )
          return result;
        if ( !*v11 )
        {
          *((_WORD *)this + 4) = 3;
          goto LABEL_27;
        }
        return 3222070625LL;
      }
      if ( !(unsigned int)isCharData(*v12) )
        return 3222070536LL;
      result = BufferedStream::nextChar(*((BufferedStream **)this + 11), v13, (bool *)this + 130);
      if ( (_DWORD)result )
        return result;
    }
    return 3222070625LL;
  }
  v5 = v4 - 1;
  if ( v5 )
  {
    if ( v5 != 1 )
      return 3222070546LL;
LABEL_31:
    if ( !*((_BYTE *)this + 130) )
    {
      if ( *((_WORD *)this + 61) == 62 )
      {
        result = BufferedStream::nextChar(
                   *((BufferedStream **)this + 11),
                   (unsigned __int16 *)this + 61,
                   (bool *)this + 130);
        if ( !(_DWORD)result )
        {
          *((_DWORD *)this + 28) = -3;
          *((_DWORD *)this + 27) = 16;
          return XMLStream::pop(this, 1);
        }
        return result;
      }
      return 3222070531LL;
    }
    return 3222070625LL;
  }
LABEL_27:
  if ( *((_WORD *)this + 61) != 45 )
  {
    *((_WORD *)this + 4) = 2;
    return 0;
  }
  result = BufferedStream::nextChar(*((BufferedStream **)this + 11), (unsigned __int16 *)this + 61, (bool *)this + 130);
  if ( !(_DWORD)result )
  {
    *((_WORD *)this + 4) = 4;
    goto LABEL_31;
  }
  return result;
}

```

## disassembly

```asm
0x1800367c0  push    rbx
0x1800367c2  push    rsi
0x1800367c3  push    rdi
0x1800367c4  push    r14
0x1800367c6  push    r15
0x1800367c8  sub     rsp, 20h
0x1800367cc  mov     r15d, 1
0x1800367d2  mov     rbx, rcx
0x1800367d5  movsx   ecx, word ptr [rcx+8]
0x1800367d9  lea     r14d, [r15+1]
0x1800367dd  test    ecx, ecx
0x1800367df  jz      short loc_18003680B
0x1800367e1  sub     ecx, r15d
0x1800367e4  jz      short loc_180036842
0x1800367e6  sub     ecx, r15d
0x1800367e9  jz      loc_18003688B
0x1800367ef  sub     ecx, r15d
0x1800367f2  jz      loc_1800368EE
0x1800367f8  cmp     ecx, r15d
0x1800367fb  jz      loc_18003691B
0x180036801  mov     eax, 0C00CE512h
0x180036806  jmp     loc_180036966
0x18003680b  mov     rcx, [rbx+58h]; this
0x18003680f  lea     rdi, [rbx+82h]
0x180036816  mov     r8, rdi; bool *
0x180036819  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x18003681d  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180036822  test    eax, eax
0x180036824  jnz     loc_180036966
0x18003682a  cmp     [rdi], al
0x18003682c  jnz     loc_180036961
0x180036832  cmp     word ptr [rbx+7Ah], 2Dh ; '-'
0x180036837  jnz     loc_18003695A
0x18003683d  mov     [rbx+8], r15w
0x180036842  mov     rcx, [rbx+58h]; this
0x180036846  lea     r8, [rbx+82h]; bool *
0x18003684d  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x180036851  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180036856  test    eax, eax
0x180036858  jnz     loc_180036966
0x18003685e  mov     r8, [rbx+58h]
0x180036862  mov     edx, [r8+10h]
0x180036866  test    edx, edx
0x180036868  lea     ecx, [rdx-1]
0x18003686b  cmovle  ecx, eax
0x18003686e  mov     [r8+1Ch], ecx
0x180036872  mov     ecx, [r8+2Ch]
0x180036876  cmp     ecx, edx
0x180036878  jz      short loc_180036886
0x18003687a  mov     eax, [r8+28h]
0x18003687e  mov     [r8+30h], eax
0x180036882  mov     [r8+34h], ecx
0x180036886  mov     [rbx+8], r14w
0x18003688b  lea     rdi, [rbx+82h]
0x180036892  cmp     byte ptr [rdi], 0
0x180036895  jnz     loc_180036961
0x18003689b  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x18003689f  cmp     word ptr [rdx], 2Dh ; '-'
0x1800368a3  jz      short loc_1800368D0
0x1800368a5  movzx   ecx, word ptr [rdx]; unsigned __int16
0x1800368a8  call    ?isCharData@@YAHG@Z; isCharData(ushort)
0x1800368ad  test    eax, eax
0x1800368af  jz      short loc_1800368C6
0x1800368b1  mov     rcx, [rbx+58h]; this
0x1800368b5  mov     r8, rdi; bool *
0x1800368b8  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x1800368bd  test    eax, eax
0x1800368bf  jz      short loc_180036892
0x1800368c1  jmp     loc_180036966
0x1800368c6  mov     eax, 0C00CE508h
0x1800368cb  jmp     loc_180036966
0x1800368d0  mov     rcx, [rbx+58h]; this
0x1800368d4  mov     r8, rdi; bool *
0x1800368d7  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x1800368dc  test    eax, eax
0x1800368de  jnz     loc_180036966
0x1800368e4  cmp     [rdi], al
0x1800368e6  jnz     short loc_180036961
0x1800368e8  mov     word ptr [rbx+8], 3
0x1800368ee  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x1800368f2  cmp     word ptr [rdx], 2Dh ; '-'
0x1800368f6  jz      short loc_180036901
0x1800368f8  mov     [rbx+8], r14w
0x1800368fd  xor     eax, eax
0x1800368ff  jmp     short loc_180036966
0x180036901  mov     rcx, [rbx+58h]; this
0x180036905  lea     r8, [rbx+82h]; bool *
0x18003690c  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180036911  test    eax, eax
0x180036913  jnz     short loc_180036966
0x180036915  mov     word ptr [rbx+8], 4
0x18003691b  lea     r8, [rbx+82h]; bool *
0x180036922  cmp     byte ptr [r8], 0
0x180036926  jnz     short loc_180036961
0x180036928  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x18003692c  cmp     word ptr [rdx], 3Eh ; '>'
0x180036930  jnz     short loc_18003695A
0x180036932  mov     rcx, [rbx+58h]; this
0x180036936  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x18003693b  test    eax, eax
0x18003693d  jnz     short loc_180036966
0x18003693f  mov     dl, r15b; bool
0x180036942  mov     dword ptr [rbx+70h], 0FFFFFFFDh
0x180036949  mov     rcx, rbx; this
0x18003694c  mov     dword ptr [rbx+6Ch], 10h
0x180036953  call    ?pop@XMLStream@@AEAAJ_N@Z; XMLStream::pop(bool)
0x180036958  jmp     short loc_180036966
0x18003695a  mov     eax, 0C00CE503h
0x18003695f  jmp     short loc_180036966
0x180036961  mov     eax, 0C00CE561h
0x180036966  add     rsp, 20h
0x18003696a  pop     r15
0x18003696c  pop     r14
0x18003696e  pop     rdi
0x18003696f  pop     rsi
0x180036970  pop     rbx
0x180036971  retn
```
