# ReadGeneric

- ea: `0x18001a3bc`
- end: `0x18001a56f`
- name: `ReadGeneric`
- size: `435`
- prototype: ``
- caller_count: `51`
- callee_count: `5`
- tags: ``

## callers

- `0x180007800`
- `0x1800079b8`
- `0x180008714`
- `0x1800089c8`
- `0x180008c68`
- `0x180009010`
- `0x180009544`
- `0x180009978`
- `0x18000a8dc`
- `0x18000b040`
- `0x18000b5d0`
- `0x18000b760`
- `0x18000b888`
- `0x18000bdd4`
- `0x18000c1d0`
- `0x18000c350`
- `0x18000c708`
- `0x18000c874`
- `0x18000d108`
- `0x18000d45c`
- `0x18000db8c`
- `0x18000e014`
- `0x18000e3cc`
- `0x18000e4c8`
- `0x18000e8f4`
- `0x18000ef20`
- `0x18000f0f4`
- `0x18000fad8`
- `0x18000fd08`
- `0x180010088`
- `0x1800109fc`
- `0x180010fd4`
- `0x1800118bc`
- `0x180011f48`
- `0x180012154`
- `0x180012640`
- `0x180013364`
- `0x180014dc0`
- `0x1800154a4`
- `0x1800167ac`
- `0x1800168d0`
- `0x180017b6c`
- `0x180017cd4`
- `0x180017d74`
- `0x180017f04`
- `0x180018b84`
- `0x180019a40`
- `0x180019b9c`
- `0x180019c00`
- `0x180019d28`

## callees

- `0x18001a348`
- `0x18001a380`
- `0x18001a3bc`
- `0x18001a620`
- `0x18001a680`

## pseudocode

```c
__int64 __fastcall ReadGeneric(
        __int64 a1,
        __int64 a2,
        unsigned __int16 a3,
        unsigned __int8 *a4,
        unsigned int a5,
        _WORD *a6)
{
  unsigned int v6; // ebx
  unsigned __int16 v8; // r13
  unsigned __int64 v10; // r12
  unsigned __int16 v11; // di
  int v12; // r10d
  unsigned __int16 v13; // si
  unsigned __int8 v14; // dl
  bool v15; // zf
  __int64 v16; // rdx
  __int64 result; // rax
  __int16 v18; // ax
  __int64 v19; // rdx
  unsigned __int8 *v20; // [rsp+88h] [rbp+20h]

  v20 = a4;
  v6 = a5;
  v8 = *a4;
  v10 = a3;
  v11 = 0;
  LOWORD(v12) = 1;
  v13 = 1;
  while ( v13 <= v8 )
  {
    v14 = a4[v13];
    if ( (v14 & 7) == 1 )
    {
      if ( (unsigned __int64)v11 + 1 > v10 )
        return 1003;
      if ( (v14 & 0x10) != 0 )
      {
        *(_BYTE *)(v11 + a2) = 0;
      }
      else
      {
        result = ReadByte(a1, v11 + a2, v6);
        if ( (_WORD)result )
          return result;
        a4 = v20;
        v6 += v12;
      }
      v18 = v12;
    }
    else if ( (a4[v13] & 7) == 2 )
    {
      if ( (unsigned __int64)v11 + 2 > v10 )
        return 1003;
      if ( (v14 & 0x10) != 0 )
      {
        *(_WORD *)(v11 + a2) = 0;
      }
      else
      {
        v15 = (v14 & 0x20) == 0;
        v19 = v11 + a2;
        if ( v15 )
          result = ReadWord(a1, v19, v6);
        else
          result = ReadBytes(a1, v19, v6, 2);
        if ( (_WORD)result )
          return result;
        a4 = v20;
        v6 += 2;
      }
      v18 = 2;
      LOWORD(v12) = 1;
    }
    else
    {
      if ( (a4[v13] & 7) != 4 || (unsigned __int64)v11 + 4 > v10 )
        return 1003;
      if ( (v14 & 0x10) != 0 )
      {
        *(_DWORD *)(v11 + a2) = 0;
      }
      else
      {
        v15 = (v14 & 0x20) == 0;
        v16 = v11 + a2;
        if ( v15 )
          result = ReadLong(a1, v16, v6);
        else
          result = ReadBytes(a1, v16, v6, 4);
        if ( (_WORD)result )
          return result;
        a4 = v20;
        v6 += 4;
        LOWORD(v12) = 1;
      }
      v18 = 4;
    }
    v13 += v12;
    v11 += v18;
  }
  if ( v11 < (unsigned __int16)v10 )
    return 1003;
  *a6 = v6 - a5;
  return 0;
}

```

## disassembly

```asm
0x18001a3bc  mov     [rsp+arg_18], r9
0x18001a3c1  push    rbx
0x18001a3c2  push    rbp
0x18001a3c3  push    rsi
0x18001a3c4  push    rdi
0x18001a3c5  push    r12
0x18001a3c7  push    r13
0x18001a3c9  push    r14
0x18001a3cb  push    r15
0x18001a3cd  sub     rsp, 28h
0x18001a3d1  mov     ebx, [rsp+68h+arg_20]
0x18001a3d8  mov     rbp, rdx
0x18001a3db  movzx   r13d, byte ptr [r9]
0x18001a3df  mov     r14, rcx
0x18001a3e2  movzx   r12d, r8w
0x18001a3e6  xor     r8d, r8d
0x18001a3e9  mov     edi, r8d
0x18001a3ec  lea     r10d, [r8+1]
0x18001a3f0  movzx   esi, r10w
0x18001a3f4  lea     r11d, [r8+4]
0x18001a3f8  cmp     si, r13w
0x18001a3fc  ja      loc_18001A53B
0x18001a402  movzx   eax, si
0x18001a405  movzx   edx, byte ptr [rax+r9]
0x18001a40a  mov     ecx, edx
0x18001a40c  and     ecx, 7
0x18001a40f  sub     ecx, 1
0x18001a412  jz      loc_18001A4EE
0x18001a418  sub     ecx, 1
0x18001a41b  jz      short loc_18001A489
0x18001a41d  cmp     ecx, 2
0x18001a420  jnz     loc_18001A541
0x18001a426  movzx   ecx, di
0x18001a429  lea     rax, [rcx+4]
0x18001a42d  cmp     rax, r12
0x18001a430  ja      loc_18001A541
0x18001a436  lea     rax, [rcx+rbp]
0x18001a43a  test    dl, 10h
0x18001a43d  jz      short loc_18001A444
0x18001a43f  mov     [rax], r8d
0x18001a442  jmp     short loc_18001A480
0x18001a444  test    dl, 20h
0x18001a447  mov     r8d, ebx
0x18001a44a  mov     rdx, rax
0x18001a44d  mov     rcx, r14
0x18001a450  jz      short loc_18001A45C
0x18001a452  mov     r9, r11
0x18001a455  call    ReadBytes
0x18001a45a  jmp     short loc_18001A461
0x18001a45c  call    ReadLong
0x18001a461  xor     r8d, r8d
0x18001a464  test    ax, ax
0x18001a467  jnz     loc_18001A55E
0x18001a46d  mov     r9, [rsp+68h+arg_18]
0x18001a475  lea     r11d, [r8+4]
0x18001a479  add     ebx, r11d
0x18001a47c  lea     r10d, [r8+1]
0x18001a480  movzx   eax, r11w
0x18001a484  jmp     loc_18001A52F
0x18001a489  movzx   ecx, di
0x18001a48c  lea     rax, [rcx+2]
0x18001a490  cmp     rax, r12
0x18001a493  ja      loc_18001A541
0x18001a499  lea     r10, [rcx+rbp]
0x18001a49d  test    dl, 10h
0x18001a4a0  jz      short loc_18001A4A8
0x18001a4a2  mov     [r10], r8w
0x18001a4a6  jmp     short loc_18001A4E3
0x18001a4a8  test    dl, 20h
0x18001a4ab  mov     r8d, ebx
0x18001a4ae  mov     rdx, r10
0x18001a4b1  mov     rcx, r14
0x18001a4b4  jz      short loc_18001A4C3
0x18001a4b6  mov     r9d, 2
0x18001a4bc  call    ReadBytes
0x18001a4c1  jmp     short loc_18001A4C8
0x18001a4c3  call    ReadWord
0x18001a4c8  xor     r8d, r8d
0x18001a4cb  test    ax, ax
0x18001a4ce  jnz     loc_18001A55E
0x18001a4d4  mov     r9, [rsp+68h+arg_18]
0x18001a4dc  lea     r11d, [r8+4]
0x18001a4e0  add     ebx, 2
0x18001a4e3  mov     eax, 2
0x18001a4e8  lea     r10d, [rax-1]
0x18001a4ec  jmp     short loc_18001A52F
0x18001a4ee  movzx   ecx, di
0x18001a4f1  lea     rax, [rcx+1]
0x18001a4f5  cmp     rax, r12
0x18001a4f8  ja      short loc_18001A541
0x18001a4fa  test    dl, 10h
0x18001a4fd  jz      short loc_18001A505
0x18001a4ff  mov     [rcx+rbp], r8b
0x18001a503  jmp     short loc_18001A52B
0x18001a505  lea     rdx, [rcx+rbp]
0x18001a509  mov     r8d, ebx
0x18001a50c  mov     rcx, r14
0x18001a50f  call    ReadByte
0x18001a514  xor     r8d, r8d
0x18001a517  test    ax, ax
0x18001a51a  jnz     short loc_18001A55E
0x18001a51c  mov     r9, [rsp+68h+arg_18]
0x18001a524  lea     r11d, [r8+4]
0x18001a528  add     ebx, r10d
0x18001a52b  movzx   eax, r10w
0x18001a52f  add     si, r10w
0x18001a533  add     di, ax
0x18001a536  jmp     loc_18001A3F8
0x18001a53b  cmp     di, r12w
0x18001a53f  jnb     short loc_18001A548
0x18001a541  mov     eax, 3EBh
0x18001a546  jmp     short loc_18001A55E
0x18001a548  mov     rax, [rsp+68h+arg_28]
0x18001a550  sub     bx, word ptr [rsp+68h+arg_20]
0x18001a558  mov     [rax], bx
0x18001a55b  mov     eax, r8d
0x18001a55e  add     rsp, 28h
0x18001a562  pop     r15
0x18001a564  pop     r14
0x18001a566  pop     r13
0x18001a568  pop     r12
0x18001a56a  pop     rdi
0x18001a56b  pop     rsi
0x18001a56c  pop     rbp
0x18001a56d  pop     rbx
0x18001a56e  retn
```
