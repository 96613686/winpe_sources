# TextReadHTMLFile

- ea: `0x100288d0`
- end: `0x10028a5c`
- name: `TextReadHTMLFile`
- size: `396`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x10025cc0`
- `0x10027030`
- `0x100279a0`
- `0x10028640`
- `0x100287b0`

## callees

- `0x1001d550`
- `0x1001d6a0`
- `0x100288d0`
- `0x100295f0`
- `0x1002ba60`

## pseudocode

```c
int __stdcall TextReadHTMLFile(int *a1, int a2, _WORD *a3, int a4)
{
  int v4; // ebp
  int v5; // ebx
  int v6; // ecx
  int v7; // edx
  _WORD *v8; // ebx
  int v10; // eax
  int v11; // esi
  int v12; // eax
  size_t v13; // esi
  __int16 v14; // ax
  unsigned int v15; // [esp+10h] [ebp-4h]

  v4 = a4;
  v5 = 0;
  v15 = 0;
  if ( !a4 )
    return v5;
  v6 = dword_10041B70;
  v7 = dword_10041B74;
  v8 = a3;
  while ( dword_10041B7C )
  {
    if ( !v6 )
    {
      if ( v4 )
        return -14;
      return v15;
    }
LABEL_22:
    v14 = *(&word_10041B80 + v7++);
    *v8++ = v14;
    a3 = v8;
    dword_10041B74 = v7;
    if ( v6 )
      dword_10041B70 = --v6;
    if ( !--v4 )
      return v15;
  }
  if ( v6 )
    goto LABEL_22;
  BFGetFilePosition(*a1, a1 + 1);
  v10 = BFReadFile(*a1, a1 + 17, 0x1000u, (int)&a4);
  v11 = a4;
  v15 = v10;
  if ( v10 == -14 )
  {
    dword_10041B7C = 1;
  }
  else if ( a4 != 4096 )
  {
    return -5;
  }
  if ( !a4 )
  {
    v6 = dword_10041B70;
    v7 = dword_10041B74;
LABEL_21:
    v8 = a3;
    goto LABEL_22;
  }
  dword_10041B78 = 4096;
  if ( !a1[1] )
  {
    a1[11] = 0;
    a1[12] = 0;
  }
  v12 = a1[12];
  if ( v12 )
  {
    v11 += v12;
    a4 = v11;
  }
  v15 = TextConvertToUnicode(
          a2,
          a1 + 11,
          (char *)a1 - a1[12] + 68,
          (size_t *)&a4,
          &word_10041B80,
          (int)&dword_10041B78,
          0);
  if ( !v15 )
  {
    v13 = v11 - a4;
    a1[12] = v13;
    if ( v13 )
      memcpy((char *)a1 - v13 + 68, (char *)a1 - v13 + 4164, v13);
    v6 = dword_10041B78;
    v7 = 0;
    dword_10041B70 = dword_10041B78;
    goto LABEL_21;
  }
  return -5;
}

```

## disassembly

```asm
0x100288d0  push    ecx
0x100288d1  push    ebx
0x100288d2  push    ebp
0x100288d3  mov     ebp, [esp+0Ch+arg_C]
0x100288d7  xor     ebx, ebx
0x100288d9  mov     [esp+0Ch+var_4], ebx
0x100288dd  push    esi
0x100288de  push    edi
0x100288df  test    ebp, ebp
0x100288e1  jz      loc_10028A45
0x100288e7  mov     edi, [esp+14h+arg_0]
0x100288eb  mov     ecx, dword_10041B70
0x100288f1  mov     edx, dword_10041B74
0x100288f7  mov     ebx, [esp+14h+arg_8]
0x100288fb  jmp     short loc_10028900
0x10028900  cmp     dword_10041B7C, 0
0x10028907  jz      short loc_10028924
0x10028909  test    ecx, ecx
0x1002890b  jnz     loc_10028A15
0x10028911  test    ebp, ebp
0x10028913  jz      loc_10028A41
0x10028919  pop     edi
0x1002891a  pop     esi
0x1002891b  pop     ebp
0x1002891c  lea     eax, [ecx-0Eh]
0x1002891f  pop     ebx
0x10028920  pop     ecx
0x10028921  retn    10h
0x10028924  test    ecx, ecx
0x10028926  jnz     loc_10028A15
0x1002892c  lea     ebx, [edi+4]
0x1002892f  push    ebx
0x10028930  push    dword ptr [edi]
0x10028932  call    _BFGetFilePosition@8; BFGetFilePosition(x,x)
0x10028937  lea     eax, [esp+14h+arg_C]
0x1002893b  push    eax; int
0x1002893c  push    1000h; Size
0x10028941  lea     eax, [edi+44h]
0x10028944  push    eax; void *
0x10028945  push    dword ptr [edi]; int
0x10028947  call    _BFReadFile@16; BFReadFile(x,x,x,x)
0x1002894c  mov     esi, [esp+14h+arg_C]
0x10028950  mov     [esp+14h+var_4], eax
0x10028954  cmp     eax, 0FFFFFFF2h
0x10028957  jnz     short loc_10028965
0x10028959  mov     dword_10041B7C, 1
0x10028963  jmp     short loc_10028971
0x10028965  cmp     esi, 1000h
0x1002896b  jnz     loc_10028A4F
0x10028971  test    esi, esi
0x10028973  jz      loc_10028A05
0x10028979  mov     dword_10041B78, 1000h
0x10028983  cmp     dword ptr [ebx], 0
0x10028986  jnz     short loc_10028996
0x10028988  mov     dword ptr [edi+2Ch], 0
0x1002898f  mov     dword ptr [edi+30h], 0
0x10028996  mov     eax, [edi+30h]
0x10028999  test    eax, eax
0x1002899b  jz      short loc_100289A3
0x1002899d  add     esi, eax
0x1002899f  mov     [esp+14h+arg_C], esi
0x100289a3  push    0; int
0x100289a5  push    offset dword_10041B78; int
0x100289aa  push    offset word_10041B80; lpWideCharStr
0x100289af  lea     eax, [esp+20h+arg_C]
0x100289b3  push    eax; int
0x100289b4  mov     eax, edi
0x100289b6  sub     eax, [edi+30h]
0x100289b9  add     eax, 44h ; 'D'
0x100289bc  push    eax; Src
0x100289bd  lea     eax, [edi+2Ch]
0x100289c0  push    eax; int
0x100289c1  push    [esp+2Ch+arg_4]; int
0x100289c5  call    _TextConvertToUnicode@28; TextConvertToUnicode(x,x,x,x,x,x,x)
0x100289ca  mov     ebx, eax
0x100289cc  mov     [esp+14h+var_4], ebx
0x100289d0  test    ebx, ebx
0x100289d2  jnz     short loc_10028A4F
0x100289d4  sub     esi, [esp+14h+arg_C]
0x100289d8  mov     [edi+30h], esi
0x100289db  jz      short loc_100289F5
0x100289dd  mov     ecx, edi
0x100289df  sub     ecx, esi
0x100289e1  push    esi; Size
0x100289e2  lea     eax, [ecx+1044h]
0x100289e8  push    eax; Src
0x100289e9  lea     eax, [ecx+44h]
0x100289ec  push    eax; void *
0x100289ed  call    _memcpy
0x100289f2  add     esp, 0Ch
0x100289f5  mov     ecx, dword_10041B78
0x100289fb  xor     edx, edx
0x100289fd  mov     dword_10041B70, ecx
0x10028a03  jmp     short loc_10028A11
0x10028a05  mov     ecx, dword_10041B70
0x10028a0b  mov     edx, dword_10041B74
0x10028a11  mov     ebx, [esp+14h+arg_8]
0x10028a15  mov     ax, word_10041B80[edx*2]
0x10028a1d  inc     edx
0x10028a1e  mov     [ebx], ax
0x10028a21  add     ebx, 2
0x10028a24  mov     [esp+14h+arg_8], ebx
0x10028a28  mov     dword_10041B74, edx
0x10028a2e  cmp     ecx, 1
0x10028a31  jb      short loc_10028A3A
0x10028a33  dec     ecx
0x10028a34  mov     dword_10041B70, ecx
0x10028a3a  dec     ebp
0x10028a3b  jnz     loc_10028900
0x10028a41  mov     ebx, [esp+14h+var_4]
0x10028a45  pop     edi
0x10028a46  pop     esi
0x10028a47  pop     ebp
0x10028a48  mov     eax, ebx
0x10028a4a  pop     ebx
0x10028a4b  pop     ecx
0x10028a4c  retn    10h
0x10028a4f  pop     edi
0x10028a50  pop     esi
0x10028a51  pop     ebp
0x10028a52  mov     eax, 0FFFFFFFBh
0x10028a57  pop     ebx
0x10028a58  pop     ecx
0x10028a59  retn    10h
```
