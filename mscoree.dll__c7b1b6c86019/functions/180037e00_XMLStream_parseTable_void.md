# XMLStream::parseTable(void)

- ea: `0x180037e00`
- end: `0x1800382a2`
- name: `?parseTable@XMLStream@@AEAAJXZ`
- size: `1186`
- prototype: `__int64 __fastcall(XMLStream *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180037640`
- `0x180037720`
- `0x180037e00`
- `0x1800382a8`
- `0x180038320`
- `0x1800383d0`
- `0x180038a38`
- `0x180038b30`
- `0x180038d48`
- `0x180038ef8`
- `0x180038f2c`
- `0x180039264`

## pseudocode

```c
__int64 __fastcall XMLStream::parseTable(XMLStream *this)
{
  int *v2; // r12
  int v3; // r15d
  __int64 v4; // rsi
  __int64 v5; // rdi
  int v6; // ecx
  unsigned int v7; // r14d
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  BufferedStream *v14; // rcx
  int v15; // r8d
  int v16; // eax
  __int64 result; // rax
  _DWORD *v18; // r8
  int v19; // edx
  int v20; // ecx
  int v21; // ecx
  unsigned __int16 *v22; // rdx
  BufferedStream *v23; // rcx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  __int16 v30; // ax
  _DWORD *v31; // r8
  int v32; // edx
  int v33; // ecx
  int v34; // ecx
  BufferedStream *v35; // rcx
  int v36; // eax
  _DWORD *v37; // r8
  int v38; // edx
  int v39; // ecx
  int v40; // ecx
  BufferedStream *v41; // rcx
  _DWORD *v42; // r8
  int v43; // edx
  int v44; // ecx
  int v45; // ecx
  __int64 (__fastcall *v46)(XMLStream *__hidden); // rdx
  int v47; // [rsp+58h] [rbp+38h] BYREF
  unsigned __int16 *Src; // [rsp+60h] [rbp+40h] BYREF

  v2 = (int *)((char *)this + 108);
  v3 = 0;
  while ( 1 )
  {
    if ( v3 || (v2 = (int *)((char *)this + 108), *((_DWORD *)this + 27)) )
    {
      if ( *v2 == 66 )
        return BufferedStream::UnFreeze(*((BufferedStream **)this + 11));
      return 0;
    }
    v4 = *((_QWORD *)this + 22);
    v5 = 32LL * *((__int16 *)this + 4);
    v6 = *(_DWORD *)(v5 + v4);
    v7 = *(_DWORD *)(v5 + v4 + 16);
    if ( v6 > 10 )
      break;
    if ( v6 == 10 )
    {
      v36 = *(_DWORD *)(v5 + v4 + 24);
      *((_DWORD *)this + 28) = v36;
      if ( !v36 )
      {
        v37 = (_DWORD *)*((_QWORD *)this + 11);
        v38 = v37[4];
        v39 = v38 - 1;
        if ( v38 <= 0 )
          v39 = 0;
        v37[7] = v39;
        v40 = v37[11];
        if ( v40 != v38 )
        {
          v37[12] = v37[10];
          v37[13] = v40;
        }
      }
      result = XMLStream::pop(this, *(_DWORD *)(v5 + v4 + 24) == 0);
      if ( (_DWORD)result )
        return result;
      *v2 = *(_DWORD *)(v5 + v4 + 20);
      return 0;
    }
    if ( !v6 )
      goto LABEL_43;
    v8 = v6 - 1;
    if ( !v8 )
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 11) + 80LL) != *(_DWORD *)(*((_QWORD *)this + 11) + 16LL) )
        return 3222070537LL;
LABEL_43:
      result = XMLStream::push(this, XMLStream::skipWhiteSpace, (unsigned __int16)v7);
      if ( (_DWORD)result )
        return result;
      result = XMLStream::skipWhiteSpace(this);
LABEL_27:
      v3 = result;
      if ( (_DWORD)result )
        return result;
      goto LABEL_20;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      v18 = (_DWORD *)*((_QWORD *)this + 11);
      v19 = v18[4];
      v20 = v19 - 1;
      if ( v19 <= 0 )
        v20 = 0;
      v18[7] = v20;
      v21 = v18[11];
      if ( v21 != v19 )
      {
        v18[12] = v18[10];
        v18[13] = v21;
      }
LABEL_35:
      v22 = (unsigned __int16 *)((char *)this + 122);
      if ( *((_WORD *)this + 61) != **(_WORD **)(v5 + v4 + 8) )
      {
        v7 = *(_DWORD *)(v5 + v4 + 20);
        if ( v7 >= 0xC00CE500
          && *(_DWORD *)(*((_QWORD *)this + 11) + 80LL) == *(_DWORD *)(*((_QWORD *)this + 11) + 16LL) )
        {
          return 3222070547LL;
        }
        goto LABEL_20;
      }
      v23 = (BufferedStream *)*((_QWORD *)this + 11);
LABEL_37:
      result = BufferedStream::nextChar(v23, v22, (bool *)this + 130);
      v3 = result;
      if ( (_DWORD)result )
        return result;
      v7 = *(_DWORD *)(v5 + v4 + 16);
      *v2 = *(_DWORD *)(v5 + v4 + 24);
      goto LABEL_20;
    }
    v10 = v9 - 1;
    if ( !v10 )
      goto LABEL_35;
    v11 = v10 - 1;
    if ( !v11 )
    {
      if ( *((_WORD *)this + 61) == **(_WORD **)(v5 + v4 + 8) )
        goto LABEL_20;
LABEL_30:
      v7 = *(_DWORD *)(v5 + v4 + 20);
      goto LABEL_20;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      result = XMLStream::push(this, XMLStream::parseName, (unsigned __int16)v7);
      if ( (_DWORD)result )
        return result;
      result = XMLStream::parseName(this);
      goto LABEL_27;
    }
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 != 3 )
        goto LABEL_20;
      v14 = (BufferedStream *)*((_QWORD *)this + 11);
      Src = (unsigned __int16 *)&word_180050144;
      v47 = 0;
      BufferedStream::getToken(v14, (const unsigned __int16 **)&Src, &v47);
      v15 = *(_DWORD *)(v5 + v4 + 24);
      if ( v15 >= 0 )
        v15 = 0;
      if ( (unsigned int)CompareUnicodeStrings(
                           *(const unsigned __int16 **)(v5 + v4 + 8),
                           Src,
                           v47 + v15,
                           *((_BYTE *)this + 171)) )
        goto LABEL_23;
      v16 = *(_DWORD *)(v5 + v4 + 24);
      if ( v16 > 0 )
      {
        *v2 = v16;
        *((_DWORD *)this + 28) = 0;
      }
      v7 = *(_DWORD *)(v5 + v4 + 16);
    }
    else
    {
      *v2 = *(_DWORD *)(v5 + v4 + 20);
      *((_DWORD *)this + 28) = *(_DWORD *)(v5 + v4 + 24);
    }
LABEL_20:
    if ( *(__int64 (__fastcall **)(XMLStream *__hidden))this != XMLStream::parseTable )
      return 0;
    if ( v7 >= 0xC00CE500 )
      return v7;
    *((_WORD *)this + 4) = v7;
  }
  v24 = v6 - 17;
  if ( !v24 )
  {
    v46 = XMLStream::parseComment;
    return XMLStream::push(this, v46, (unsigned __int16)v7);
  }
  v25 = v24 - 1;
  if ( !v25 )
  {
    v46 = XMLStream::parseCondSect;
    return XMLStream::push(this, v46, (unsigned __int16)v7);
  }
  v26 = v25 - 1;
  if ( !v26 )
  {
    if ( !(unsigned int)isStartNameChar(*((_WORD *)this + 61)) )
      goto LABEL_30;
    v7 = *(_DWORD *)(v5 + v4 + 16);
    goto LABEL_20;
  }
  v27 = v26 - 1;
  if ( !v27 )
  {
    result = XMLStream::push(this, XMLStream::parseEquals, (unsigned __int16)v7);
    if ( (_DWORD)result )
      return result;
    result = XMLStream::parseEquals(this);
    goto LABEL_27;
  }
  v28 = v27 - 1;
  if ( !v28 )
  {
    v35 = (BufferedStream *)*((_QWORD *)this + 11);
    Src = (unsigned __int16 *)&word_180050144;
    v47 = 0;
    BufferedStream::getToken(v35, (const unsigned __int16 **)&Src, &v47);
    v3 = BufferedStream::switchEncoding(*((BufferedStream **)this + 11), Src, *(_DWORD *)(v5 + v4 + 24) + v47);
    goto LABEL_20;
  }
  v29 = v28 - 1;
  if ( !v29 )
  {
    v31 = (_DWORD *)*((_QWORD *)this + 11);
    v32 = v31[4];
    v33 = v32 - 1;
    if ( v32 <= 0 )
      v33 = 0;
    v31[7] = v33;
    v34 = v31[11];
    if ( v34 != v32 )
    {
      v31[12] = v31[10];
      v31[13] = v34;
    }
    v22 = (unsigned __int16 *)((char *)this + 122);
    v23 = (BufferedStream *)*((_QWORD *)this + 11);
    if ( *((_WORD *)this + 61) != **(_WORD **)(v5 + v4 + 8) )
    {
      if ( *((_DWORD *)v23 + 20) != *((_DWORD *)v23 + 4) )
        return 3222070560LL;
LABEL_23:
      v7 = *(_DWORD *)(v5 + v4 + 20);
      goto LABEL_20;
    }
    goto LABEL_37;
  }
  if ( v29 != 1 )
    goto LABEL_20;
  v30 = *((_WORD *)this + 61);
  if ( v30 != 34 && v30 != 39 )
    return 3222070530LL;
  v41 = (BufferedStream *)*((_QWORD *)this + 11);
  *((_WORD *)this + 63) = v30;
  result = BufferedStream::nextChar(v41, (unsigned __int16 *)this + 61, (bool *)this + 130);
  if ( !(_DWORD)result )
  {
    v42 = (_DWORD *)*((_QWORD *)this + 11);
    v43 = v42[4];
    v44 = v43 - 1;
    if ( v43 <= 0 )
      v44 = 0;
    v42[7] = v44;
    v45 = v42[11];
    if ( v45 != v43 )
    {
      v42[12] = v42[10];
      v42[13] = v45;
    }
    v46 = XMLStream::parseAttrValue;
    *((_BYTE *)this + 206) = *(_DWORD *)(v5 + v4 + 20) == 1;
    return XMLStream::push(this, v46, (unsigned __int16)v7);
  }
  return result;
}

```

## disassembly

```asm
0x180037e00  mov     [rsp-28h+arg_0], rbx
0x180037e05  mov     [rsp-28h+arg_18], rsi
0x180037e0a  push    rbp
0x180037e0b  push    rdi
0x180037e0c  push    r12
0x180037e0e  push    r14
0x180037e10  push    r15
0x180037e12  mov     rbp, rsp
0x180037e15  sub     rsp, 20h
0x180037e19  mov     rbx, rcx
0x180037e1c  lea     r12, [rcx+6Ch]
0x180037e20  xor     r15d, r15d
0x180037e23  lea     rdx, word_180050144
0x180037e2a  test    r15d, r15d
0x180037e2d  jnz     loc_180038289
0x180037e33  lea     r12, [rbx+6Ch]
0x180037e37  cmp     [r12], r15d
0x180037e3b  jnz     loc_180038289
0x180037e41  mov     rsi, [rbx+0B0h]
0x180037e48  movsx   rdi, word ptr [rbx+8]
0x180037e4d  shl     rdi, 5
0x180037e51  mov     ecx, [rdi+rsi]
0x180037e54  mov     r14d, [rdi+rsi+10h]
0x180037e59  cmp     ecx, 0Ah
0x180037e5c  jg      loc_18003805E
0x180037e62  jz      loc_1800381A4
0x180037e68  test    ecx, ecx
0x180037e6a  jz      loc_180038036
0x180037e70  sub     ecx, 1
0x180037e73  jz      loc_180038026
0x180037e79  sub     ecx, 1
0x180037e7c  jz      loc_180037F92
0x180037e82  sub     ecx, 1
0x180037e85  jz      loc_180037FBC
0x180037e8b  sub     ecx, 1
0x180037e8e  jz      loc_180037F7A
0x180037e94  sub     ecx, 1
0x180037e97  jz      loc_180037F4A
0x180037e9d  sub     ecx, 1
0x180037ea0  jz      loc_180037F39
0x180037ea6  cmp     ecx, 3
0x180037ea9  jnz     short loc_180037F0B
0x180037eab  mov     rcx, [rbx+58h]; this
0x180037eaf  lea     r8, [rbp+arg_8]; int *
0x180037eb3  mov     [rbp+Src], rdx
0x180037eb7  lea     rdx, [rbp+Src]; unsigned __int16 **
0x180037ebb  mov     [rbp+arg_8], r15d
0x180037ebf  call    ?getToken@BufferedStream@@QEAAJPEAPEBGPEAJ@Z; BufferedStream::getToken(ushort const * *,long *)
0x180037ec4  mov     r8d, [rdi+rsi+18h]
0x180037ec9  xor     eax, eax
0x180037ecb  mov     r9b, [rbx+0ABh]; bool
0x180037ed2  test    r8d, r8d
0x180037ed5  mov     rdx, [rbp+Src]; unsigned __int16 *
0x180037ed9  mov     rcx, [rdi+rsi+8]; unsigned __int16 *
0x180037ede  cmovns  r8d, eax
0x180037ee2  add     r8d, [rbp+arg_8]; int
0x180037ee6  call    ?CompareUnicodeStrings@@YAHPEBG0H_N@Z; CompareUnicodeStrings(ushort const *,ushort const *,int,bool)
0x180037eeb  test    eax, eax
0x180037eed  jnz     short loc_180037F32
0x180037eef  mov     eax, [rdi+rsi+18h]
0x180037ef3  test    eax, eax
0x180037ef5  jle     short loc_180037EFF
0x180037ef7  mov     [r12], eax
0x180037efb  mov     [rbx+70h], r15d
0x180037eff  mov     r14d, [rdi+rsi+10h]
0x180037f04  lea     rdx, word_180050144
0x180037f0b  lea     rax, ?parseTable@XMLStream@@AEAAJXZ; XMLStream::parseTable(void)
0x180037f12  cmp     [rbx], rax
0x180037f15  jnz     loc_1800381F3
0x180037f1b  cmp     r14d, 0C00CE500h
0x180037f22  jnb     loc_180038263
0x180037f28  mov     [rbx+8], r14w
0x180037f2d  jmp     loc_180037E2A
0x180037f32  mov     r14d, [rdi+rsi+14h]
0x180037f37  jmp     short loc_180037F04
0x180037f39  mov     eax, [rdi+rsi+14h]
0x180037f3d  mov     [r12], eax
0x180037f41  mov     eax, [rdi+rsi+18h]
0x180037f45  mov     [rbx+70h], eax
0x180037f48  jmp     short loc_180037F0B
0x180037f4a  movzx   r8d, r14w
0x180037f4e  lea     rdx, ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180037f55  mov     rcx, rbx
0x180037f58  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180037f5d  test    eax, eax
0x180037f5f  jnz     loc_1800381F5
0x180037f65  mov     rcx, rbx; this
0x180037f68  call    ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180037f6d  mov     r15d, eax
0x180037f70  test    eax, eax
0x180037f72  jnz     loc_1800381F5
0x180037f78  jmp     short loc_180037F04
0x180037f7a  mov     rax, [rdi+rsi+8]
0x180037f7f  movzx   ecx, word ptr [rax]
0x180037f82  cmp     [rbx+7Ah], cx
0x180037f86  jz      short loc_180037F0B
0x180037f88  mov     r14d, [rdi+rsi+14h]
0x180037f8d  jmp     loc_180037F0B
0x180037f92  mov     r8, [rbx+58h]
0x180037f96  xor     eax, eax
0x180037f98  mov     edx, [r8+10h]
0x180037f9c  test    edx, edx
0x180037f9e  lea     ecx, [rdx-1]
0x180037fa1  cmovle  ecx, eax
0x180037fa4  mov     [r8+1Ch], ecx
0x180037fa8  mov     ecx, [r8+2Ch]
0x180037fac  cmp     ecx, edx
0x180037fae  jz      short loc_180037FBC
0x180037fb0  mov     eax, [r8+28h]
0x180037fb4  mov     [r8+30h], eax
0x180037fb8  mov     [r8+34h], ecx
0x180037fbc  mov     rax, [rdi+rsi+8]
0x180037fc1  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x180037fc5  movzx   ecx, word ptr [rax]
0x180037fc8  cmp     [rdx], cx
0x180037fcb  jnz     short loc_180037FFA
0x180037fcd  mov     rcx, [rbx+58h]; this
0x180037fd1  lea     r8, [rbx+82h]; bool *
0x180037fd8  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180037fdd  mov     r15d, eax
0x180037fe0  test    eax, eax
0x180037fe2  jnz     loc_1800381F5
0x180037fe8  mov     r14d, [rdi+rsi+10h]
0x180037fed  mov     eax, [rdi+rsi+18h]
0x180037ff1  mov     [r12], eax
0x180037ff5  jmp     loc_180037F04
0x180037ffa  mov     r14d, [rdi+rsi+14h]
0x180037fff  cmp     r14d, 0C00CE500h
0x180038006  jb      loc_180037F04
0x18003800c  mov     rcx, [rbx+58h]
0x180038010  mov     eax, [rcx+10h]
0x180038013  cmp     [rcx+50h], eax
0x180038016  jnz     loc_180037F04
0x18003801c  mov     eax, 0C00CE513h
0x180038021  jmp     loc_1800381F5
0x180038026  mov     rcx, [rbx+58h]
0x18003802a  mov     eax, [rcx+10h]
0x18003802d  cmp     [rcx+50h], eax
0x180038030  jnz     loc_18003819D
0x180038036  movzx   r8d, r14w
0x18003803a  lea     rdx, ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180038041  mov     rcx, rbx
0x180038044  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180038049  test    eax, eax
0x18003804b  jnz     loc_1800381F5
0x180038051  mov     rcx, rbx; this
0x180038054  call    ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180038059  jmp     loc_180037F6D
0x18003805e  sub     ecx, 11h
0x180038061  jz      loc_180038271
0x180038067  sub     ecx, 1
0x18003806a  jz      loc_180038268
0x180038070  sub     ecx, 1
0x180038073  jz      loc_18003817B
0x180038079  sub     ecx, 1
0x18003807c  jz      loc_180038153
0x180038082  sub     ecx, 1
0x180038085  jz      loc_180038119
0x18003808b  sub     ecx, 1
0x18003808e  jz      short loc_1800380BE
0x180038090  cmp     ecx, 1
0x180038093  jnz     loc_180037F0B
0x180038099  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x18003809d  movzx   eax, word ptr [rdx]
0x1800380a0  cmp     ax, 22h ; '"'
0x1800380a4  jz      loc_18003820C
0x1800380aa  cmp     ax, 27h ; '''
0x1800380ae  jz      loc_18003820C
0x1800380b4  mov     eax, 0C00CE502h
0x1800380b9  jmp     loc_1800381F5
0x1800380be  mov     r8, [rbx+58h]
0x1800380c2  xor     eax, eax
0x1800380c4  mov     edx, [r8+10h]
0x1800380c8  test    edx, edx
0x1800380ca  lea     ecx, [rdx-1]
0x1800380cd  cmovle  ecx, eax
0x1800380d0  mov     [r8+1Ch], ecx
0x1800380d4  mov     ecx, [r8+2Ch]
0x1800380d8  cmp     ecx, edx
0x1800380da  jz      short loc_1800380E8
0x1800380dc  mov     eax, [r8+28h]
0x1800380e0  mov     [r8+30h], eax
0x1800380e4  mov     [r8+34h], ecx
0x1800380e8  mov     rax, [rdi+rsi+8]
0x1800380ed  lea     rdx, [rbx+7Ah]
0x1800380f1  mov     rcx, [rbx+58h]
0x1800380f5  movzx   r8d, word ptr [rax]
0x1800380f9  cmp     [rdx], r8w
0x1800380fd  jz      loc_180037FD1
0x180038103  mov     eax, [rcx+10h]
0x180038106  cmp     [rcx+50h], eax
0x180038109  jz      loc_180037F32
0x18003810f  mov     eax, 0C00CE520h
0x180038114  jmp     loc_1800381F5
0x180038119  mov     rcx, [rbx+58h]; this
0x18003811d  lea     r8, [rbp+arg_8]; int *
0x180038121  mov     [rbp+Src], rdx
0x180038125  lea     rdx, [rbp+Src]; unsigned __int16 **
0x180038129  mov     [rbp+arg_8], 0
0x180038130  call    ?getToken@BufferedStream@@QEAAJPEAPEBGPEAJ@Z; BufferedStream::getToken(ushort const * *,long *)
0x180038135  mov     r8d, [rbp+arg_8]
0x180038139  add     r8d, [rdi+rsi+18h]; unsigned int
0x18003813e  mov     rdx, [rbp+Src]; Src
0x180038142  mov     rcx, [rbx+58h]; this
0x180038146  call    ?switchEncoding@BufferedStream@@QEAAJPEBGK@Z; BufferedStream::switchEncoding(ushort const *,ulong)
0x18003814b  mov     r15d, eax
0x18003814e  jmp     loc_180037F04
0x180038153  movzx   r8d, r14w
0x180038157  lea     rdx, ?parseEquals@XMLStream@@AEAAJXZ; XMLStream::parseEquals(void)
0x18003815e  mov     rcx, rbx
0x180038161  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180038166  test    eax, eax
0x180038168  jnz     loc_1800381F5
0x18003816e  mov     rcx, rbx; this
0x180038171  call    ?parseEquals@XMLStream@@AEAAJXZ; XMLStream::parseEquals(void)
0x180038176  jmp     loc_180037F6D
0x18003817b  movzx   ecx, word ptr [rbx+7Ah]; unsigned __int16
0x18003817f  call    ?isStartNameChar@@YAHG@Z; isStartNameChar(ushort)
0x180038184  lea     rdx, word_180050144
0x18003818b  test    eax, eax
0x18003818d  jz      loc_180037F88
0x180038193  mov     r14d, [rdi+rsi+10h]
0x180038198  jmp     loc_180037F0B
0x18003819d  mov     eax, 0C00CE509h
0x1800381a2  jmp     short loc_1800381F5
0x1800381a4  mov     eax, [rdi+rsi+18h]
0x1800381a8  mov     [rbx+70h], eax
0x1800381ab  test    eax, eax
0x1800381ad  jnz     short loc_1800381D7
0x1800381af  mov     r8, [rbx+58h]
0x1800381b3  mov     edx, [r8+10h]
0x1800381b7  test    edx, edx
0x1800381b9  lea     ecx, [rdx-1]
0x1800381bc  cmovle  ecx, eax
0x1800381bf  mov     [r8+1Ch], ecx
0x1800381c3  mov     ecx, [r8+2Ch]
0x1800381c7  cmp     ecx, edx
0x1800381c9  jz      short loc_1800381D7
0x1800381cb  mov     eax, [r8+28h]
0x1800381cf  mov     [r8+30h], eax
0x1800381d3  mov     [r8+34h], ecx
0x1800381d7  cmp     dword ptr [rdi+rsi+18h], 0
0x1800381dc  mov     rcx, rbx; this
0x1800381df  setz    dl; bool
0x1800381e2  call    ?pop@XMLStream@@AEAAJ_N@Z; XMLStream::pop(bool)
0x1800381e7  test    eax, eax
0x1800381e9  jnz     short loc_1800381F5
0x1800381eb  mov     eax, [rdi+rsi+14h]
0x1800381ef  mov     [r12], eax
0x1800381f3  xor     eax, eax
0x1800381f5  mov     rbx, [rsp+20h+arg_0]
0x1800381fa  mov     rsi, [rsp+20h+arg_18]
0x1800381ff  add     rsp, 20h
0x180038203  pop     r15
0x180038205  pop     r14
0x180038207  pop     r12
0x180038209  pop     rdi
0x18003820a  pop     rbp
0x18003820b  retn
0x18003820c  mov     rcx, [rbx+58h]; this
0x180038210  lea     r8, [rbx+82h]; bool *
0x180038217  mov     [rbx+7Eh], ax
0x18003821b  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180038220  test    eax, eax
0x180038222  jnz     short loc_1800381F5
0x180038224  mov     r8, [rbx+58h]
0x180038228  mov     edx, [r8+10h]
0x18003822c  test    edx, edx
0x18003822e  lea     ecx, [rdx-1]
0x180038231  cmovle  ecx, eax
0x180038234  mov     [r8+1Ch], ecx
0x180038238  mov     ecx, [r8+2Ch]
0x18003823c  cmp     ecx, edx
0x18003823e  jz      short loc_18003824C
0x180038240  mov     eax, [r8+28h]
0x180038244  mov     [r8+30h], eax
0x180038248  mov     [r8+34h], ecx
0x18003824c  cmp     dword ptr [rdi+rsi+14h], 1
0x180038251  lea     rdx, ?parseAttrValue@XMLStream@@AEAAJXZ; XMLStream::parseAttrValue(void)
0x180038258  setz    al
0x18003825b  mov     [rbx+0CEh], al
0x180038261  jmp     short loc_180038278
0x180038263  mov     eax, r14d
0x180038266  jmp     short loc_1800381F5
0x180038268  lea     rdx, ?parseCondSect@XMLStream@@AEAAJXZ; XMLStream::parseCondSect(void)
0x18003826f  jmp     short loc_180038278
0x180038271  lea     rdx, ?parseComment@XMLStream@@AEAAJXZ; XMLStream::parseComment(void)
0x180038278  movzx   r8d, r14w
0x18003827c  mov     rcx, rbx
0x18003827f  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180038284  jmp     loc_1800381F5
0x180038289  cmp     dword ptr [r12], 42h ; 'B'
0x18003828e  jnz     loc_1800381F3
0x180038294  mov     rcx, [rbx+58h]; this
0x180038298  call    ?UnFreeze@BufferedStream@@QEAAJXZ; BufferedStream::UnFreeze(void)
0x18003829d  jmp     loc_1800381F5
```
