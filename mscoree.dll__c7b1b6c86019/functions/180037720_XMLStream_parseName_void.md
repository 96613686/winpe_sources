# XMLStream::parseName(void)

- ea: `0x180037720`
- end: `0x1800377e7`
- name: `?parseName@XMLStream@@AEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(XMLStream *__hidden this)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800362f0`
- `0x180036980`
- `0x180036cd0`
- `0x180036ee0`
- `0x180037050`
- `0x180037970`
- `0x180037e00`

## callees

- `0x180037720`
- `0x1800382a8`
- `0x180038ae0`
- `0x180038b30`
- `0x180038f2c`

## pseudocode

```c
__int64 __fastcall XMLStream::parseName(XMLStream *this)
{
  int v2; // ecx
  __int64 result; // rax
  int started; // eax
  _DWORD *v5; // r8
  unsigned int v6; // ecx
  int v7; // edx
  int v8; // ecx
  int v9; // ecx

  v2 = *((__int16 *)this + 4);
  if ( v2 )
  {
    if ( v2 != 1 )
      return 3222070546LL;
    goto LABEL_13;
  }
  started = isStartNameChar(*((_WORD *)this + 61));
  v5 = (_DWORD *)*((_QWORD *)this + 11);
  if ( started )
  {
    v7 = v5[4];
    v8 = v7 - 1;
    if ( v7 <= 0 )
      v8 = 0;
    v5[7] = v8;
    v9 = v5[11];
    if ( v9 != v7 )
    {
      v5[12] = v5[10];
      v5[13] = v9;
    }
    *((_WORD *)this + 4) = 1;
LABEL_13:
    *(_QWORD *)((char *)this + 132) = 0;
    while ( (unsigned int)isNameChar(*((_WORD *)this + 61)) && !*((_BYTE *)this + 130) )
    {
      result = BufferedStream::nextChar(
                 *((BufferedStream **)this + 11),
                 (unsigned __int16 *)this + 61,
                 (bool *)this + 130);
      if ( (_DWORD)result )
        return result;
    }
    return (unsigned int)XMLStream::pop(this, 0);
  }
  v6 = -1072896749;
  if ( v5[20] != v5[4] )
    return (unsigned int)-1072896764;
  return v6;
}

```

## disassembly

```asm
0x180037720  mov     [rsp+arg_0], rbx
0x180037725  push    rdi
0x180037726  sub     rsp, 20h
0x18003772a  mov     rbx, rcx
0x18003772d  movsx   ecx, word ptr [rcx+8]
0x180037731  test    ecx, ecx
0x180037733  jz      short loc_180037744
0x180037735  cmp     ecx, 1
0x180037738  jz      short loc_180037796
0x18003773a  mov     eax, 0C00CE512h
0x18003773f  jmp     loc_1800377DC
0x180037744  movzx   ecx, word ptr [rbx+7Ah]; unsigned __int16
0x180037748  call    ?isStartNameChar@@YAHG@Z; isStartNameChar(ushort)
0x18003774d  mov     r8, [rbx+58h]
0x180037751  test    eax, eax
0x180037753  jnz     short loc_18003776A
0x180037755  mov     eax, [r8+10h]
0x180037759  mov     ecx, 0C00CE513h
0x18003775e  cmp     [r8+50h], eax
0x180037762  lea     edx, [rcx-0Fh]
0x180037765  cmovnz  ecx, edx
0x180037768  jmp     short loc_1800377DA
0x18003776a  mov     edx, [r8+10h]
0x18003776e  xor     eax, eax
0x180037770  test    edx, edx
0x180037772  lea     ecx, [rdx-1]
0x180037775  cmovle  ecx, eax
0x180037778  mov     [r8+1Ch], ecx
0x18003777c  mov     ecx, [r8+2Ch]
0x180037780  cmp     ecx, edx
0x180037782  jz      short loc_180037790
0x180037784  mov     eax, [r8+28h]
0x180037788  mov     [r8+30h], eax
0x18003778c  mov     [r8+34h], ecx
0x180037790  mov     word ptr [rbx+8], 1
0x180037796  mov     qword ptr [rbx+84h], 0
0x1800377a1  movzx   ecx, word ptr [rbx+7Ah]; unsigned __int16
0x1800377a5  call    ?isNameChar@@YAHG@Z; isNameChar(ushort)
0x1800377aa  test    eax, eax
0x1800377ac  jz      short loc_1800377CE
0x1800377ae  lea     r8, [rbx+82h]; bool *
0x1800377b5  cmp     byte ptr [r8], 0
0x1800377b9  jnz     short loc_1800377CE
0x1800377bb  mov     rcx, [rbx+58h]; this
0x1800377bf  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x1800377c3  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x1800377c8  test    eax, eax
0x1800377ca  jz      short loc_1800377A1
0x1800377cc  jmp     short loc_1800377DC
0x1800377ce  xor     edx, edx; bool
0x1800377d0  mov     rcx, rbx; this
0x1800377d3  call    ?pop@XMLStream@@AEAAJ_N@Z; XMLStream::pop(bool)
0x1800377d8  mov     ecx, eax
0x1800377da  mov     eax, ecx
0x1800377dc  mov     rbx, [rsp+28h+arg_0]
0x1800377e1  add     rsp, 20h
0x1800377e5  pop     rdi
0x1800377e6  retn
```
