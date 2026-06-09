# HTMLWriteFileEnd(x,x,x)

- ea: `0x10026b10`
- end: `0x10026bef`
- name: `_HTMLWriteFileEnd@12`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100215c0`

## callees

- `0x10026b10`
- `0x10028bb0`
- `0x10028f80`

## pseudocode

```c
int __stdcall HTMLWriteFileEnd(int a1, int a2, int a3)
{
  int v3; // eax
  unsigned int v4; // eax
  int result; // eax
  bool v6; // sf
  int v7; // eax
  unsigned int v8; // eax
  int v9; // eax
  unsigned int v10; // eax
  bool v11; // sf
  int v12; // eax
  unsigned int v13; // eax
  int v14; // eax
  int v15; // ecx

  v3 = TextWriteHTMLFile(a1, a2, L"</TABLE>", 8, a3, 1);
  if ( v3 )
  {
    v4 = -v3;
    if ( v4 >= 0x10 )
    {
LABEL_7:
      result = -5016;
      goto LABEL_8;
    }
    result = dword_100038B8[v4];
    v6 = result < 0;
    if ( result )
      goto LABEL_9;
  }
  v7 = TextWriteHTMLFile(a1, a2, asc_1003F048, 2, a3, 0);
  if ( !v7 )
    goto LABEL_10;
  v8 = -v7;
  if ( v8 >= 0x10 )
    goto LABEL_7;
  result = dword_100038B8[v8];
LABEL_8:
  v6 = result < 0;
LABEL_9:
  if ( v6 )
    return result;
LABEL_10:
  v9 = TextWriteHTMLFile(a1, a2, L"</BODY>", 7, a3, 1);
  if ( v9 )
  {
    v10 = -v9;
    if ( v10 >= 0x10 )
      goto LABEL_16;
    result = dword_100038B8[v10];
    v11 = result < 0;
    if ( result )
      goto LABEL_18;
  }
  v12 = TextWriteHTMLFile(a1, a2, asc_1003F048, 2, a3, 0);
  if ( v12 )
  {
    v13 = -v12;
    if ( v13 < 0x10 )
    {
      result = dword_100038B8[v13];
LABEL_17:
      v11 = result < 0;
LABEL_18:
      if ( v11 )
        return result;
      goto LABEL_19;
    }
LABEL_16:
    result = -5016;
    goto LABEL_17;
  }
LABEL_19:
  v14 = WriteString(a1, a2, L"</HTML>", 1, a3);
  v15 = 0;
  if ( v14 < 0 )
    return v14;
  return v15;
}

```

## disassembly

```asm
0x10026b10  push    ebx
0x10026b11  mov     ebx, [esp+4+arg_0]
0x10026b15  push    esi
0x10026b16  mov     esi, [esp+8+arg_8]
0x10026b1a  push    edi
0x10026b1b  mov     edi, [esp+0Ch+arg_4]
0x10026b1f  push    1; int
0x10026b21  push    esi; int
0x10026b22  push    8; int
0x10026b24  push    offset aTable_0; "</TABLE>"
0x10026b29  push    edi; int
0x10026b2a  push    ebx; int
0x10026b2b  call    TextWriteHTMLFile
0x10026b30  test    eax, eax
0x10026b32  jz      short loc_10026B48
0x10026b34  neg     eax
0x10026b36  js      short loc_10026B6F
0x10026b38  cmp     eax, 0Fh
0x10026b3b  ja      short loc_10026B6F
0x10026b3d  mov     eax, ds:dword_100038B8[eax*4]
0x10026b44  test    eax, eax
0x10026b46  jnz     short loc_10026B76
0x10026b48  push    0; int
0x10026b4a  push    esi; int
0x10026b4b  push    2; int
0x10026b4d  push    offset asc_1003F048; "\r\n"
0x10026b52  push    edi; int
0x10026b53  push    ebx; int
0x10026b54  call    TextWriteHTMLFile
0x10026b59  test    eax, eax
0x10026b5b  jz      short loc_10026B78
0x10026b5d  neg     eax
0x10026b5f  js      short loc_10026B6F
0x10026b61  cmp     eax, 0Fh
0x10026b64  ja      short loc_10026B6F
0x10026b66  mov     eax, ds:dword_100038B8[eax*4]
0x10026b6d  jmp     short loc_10026B74
0x10026b6f  mov     eax, 0FFFFEC68h
0x10026b74  test    eax, eax
0x10026b76  js      short loc_10026BE9
0x10026b78  push    1; int
0x10026b7a  push    esi; int
0x10026b7b  push    7; int
0x10026b7d  push    offset aBody; "</BODY>"
0x10026b82  push    edi; int
0x10026b83  push    ebx; int
0x10026b84  call    TextWriteHTMLFile
0x10026b89  test    eax, eax
0x10026b8b  jz      short loc_10026BA1
0x10026b8d  neg     eax
0x10026b8f  js      short loc_10026BC8
0x10026b91  cmp     eax, 0Fh
0x10026b94  ja      short loc_10026BC8
0x10026b96  mov     eax, ds:dword_100038B8[eax*4]
0x10026b9d  test    eax, eax
0x10026b9f  jnz     short loc_10026BCF
0x10026ba1  push    0; int
0x10026ba3  push    esi; int
0x10026ba4  push    2; int
0x10026ba6  push    offset asc_1003F048; "\r\n"
0x10026bab  push    edi; int
0x10026bac  push    ebx; int
0x10026bad  call    TextWriteHTMLFile
0x10026bb2  test    eax, eax
0x10026bb4  jz      short loc_10026BD1
0x10026bb6  neg     eax
0x10026bb8  js      short loc_10026BC8
0x10026bba  cmp     eax, 0Fh
0x10026bbd  ja      short loc_10026BC8
0x10026bbf  mov     eax, ds:dword_100038B8[eax*4]
0x10026bc6  jmp     short loc_10026BCD
0x10026bc8  mov     eax, 0FFFFEC68h
0x10026bcd  test    eax, eax
0x10026bcf  js      short loc_10026BE9
0x10026bd1  push    esi; int
0x10026bd2  push    1; int
0x10026bd4  push    offset aHtml_1; "</HTML>"
0x10026bd9  push    edi; int
0x10026bda  push    ebx; int
0x10026bdb  call    WriteString
0x10026be0  xor     ecx, ecx
0x10026be2  test    eax, eax
0x10026be4  cmovs   ecx, eax
0x10026be7  mov     eax, ecx
0x10026be9  pop     edi
0x10026bea  pop     esi
0x10026beb  pop     ebx
0x10026bec  retn    0Ch
```
