# HTMLWriteRowBegin(x,x,x)

- ea: `0x10026bf0`
- end: `0x10026c60`
- name: `_HTMLWriteRowBegin@12`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1001e1e0`

## callees

- `0x10026bf0`
- `0x10028bb0`

## pseudocode

```c
int __stdcall HTMLWriteRowBegin(int a1, int a2, int a3)
{
  int v3; // eax
  unsigned int v4; // eax
  int result; // eax
  bool v6; // sf
  int v7; // eax
  unsigned int v8; // eax

  v3 = TextWriteHTMLFile(a1, a2, L"<TR>", 4, a3, 1);
  if ( v3 )
  {
    v4 = -v3;
    if ( v4 >= 0x10 )
      goto LABEL_7;
    result = dword_100038B8[v4];
    v6 = result < 0;
    if ( result )
      goto LABEL_9;
  }
  v7 = TextWriteHTMLFile(a1, a2, asc_1003F048, 2, a3, 0);
  if ( v7 )
  {
    v8 = -v7;
    if ( v8 < 0x10 )
    {
      result = dword_100038B8[v8];
LABEL_8:
      v6 = result < 0;
LABEL_9:
      if ( v6 )
        return result;
      return 0;
    }
LABEL_7:
    result = -5016;
    goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x10026bf0  push    1; int
0x10026bf2  push    [esp+4+arg_8]; int
0x10026bf6  push    4; int
0x10026bf8  push    offset aTr_2; "<TR>"
0x10026bfd  push    [esp+10h+arg_4]; int
0x10026c01  push    [esp+14h+arg_0]; int
0x10026c05  call    TextWriteHTMLFile
0x10026c0a  test    eax, eax
0x10026c0c  jz      short loc_10026C22
0x10026c0e  neg     eax
0x10026c10  js      short loc_10026C52
0x10026c12  cmp     eax, 0Fh
0x10026c15  ja      short loc_10026C52
0x10026c17  mov     eax, ds:dword_100038B8[eax*4]
0x10026c1e  test    eax, eax
0x10026c20  jnz     short loc_10026C59
0x10026c22  push    0; int
0x10026c24  push    [esp+4+arg_8]; int
0x10026c28  push    2; int
0x10026c2a  push    offset asc_1003F048; "\r\n"
0x10026c2f  push    [esp+10h+arg_4]; int
0x10026c33  push    [esp+14h+arg_0]; int
0x10026c37  call    TextWriteHTMLFile
0x10026c3c  test    eax, eax
0x10026c3e  jz      short loc_10026C5B
0x10026c40  neg     eax
0x10026c42  js      short loc_10026C52
0x10026c44  cmp     eax, 0Fh
0x10026c47  ja      short loc_10026C52
0x10026c49  mov     eax, ds:dword_100038B8[eax*4]
0x10026c50  jmp     short loc_10026C57
0x10026c52  mov     eax, 0FFFFEC68h
0x10026c57  test    eax, eax
0x10026c59  js      short locret_10026C5D
0x10026c5b  xor     eax, eax
0x10026c5d  retn    0Ch
```
