# HTMLWriteRowEnd(x,x,x)

- ea: `0x10026c60`
- end: `0x10026cd0`
- name: `_HTMLWriteRowEnd@12`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1001e1e0`

## callees

- `0x10026c60`
- `0x10028bb0`

## pseudocode

```c
int __stdcall HTMLWriteRowEnd(int a1, int a2, int a3)
{
  int v3; // eax
  unsigned int v4; // eax
  int result; // eax
  bool v6; // sf
  int v7; // eax
  unsigned int v8; // eax

  v3 = TextWriteHTMLFile(a1, a2, L"</TR>", 5, a3, 1);
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
0x10026c60  push    1; int
0x10026c62  push    [esp+4+arg_8]; int
0x10026c66  push    5; int
0x10026c68  push    offset aTr_1; "</TR>"
0x10026c6d  push    [esp+10h+arg_4]; int
0x10026c71  push    [esp+14h+arg_0]; int
0x10026c75  call    TextWriteHTMLFile
0x10026c7a  test    eax, eax
0x10026c7c  jz      short loc_10026C92
0x10026c7e  neg     eax
0x10026c80  js      short loc_10026CC2
0x10026c82  cmp     eax, 0Fh
0x10026c85  ja      short loc_10026CC2
0x10026c87  mov     eax, ds:dword_100038B8[eax*4]
0x10026c8e  test    eax, eax
0x10026c90  jnz     short loc_10026CC9
0x10026c92  push    0; int
0x10026c94  push    [esp+4+arg_8]; int
0x10026c98  push    2; int
0x10026c9a  push    offset asc_1003F048; "\r\n"
0x10026c9f  push    [esp+10h+arg_4]; int
0x10026ca3  push    [esp+14h+arg_0]; int
0x10026ca7  call    TextWriteHTMLFile
0x10026cac  test    eax, eax
0x10026cae  jz      short loc_10026CCB
0x10026cb0  neg     eax
0x10026cb2  js      short loc_10026CC2
0x10026cb4  cmp     eax, 0Fh
0x10026cb7  ja      short loc_10026CC2
0x10026cb9  mov     eax, ds:dword_100038B8[eax*4]
0x10026cc0  jmp     short loc_10026CC7
0x10026cc2  mov     eax, 0FFFFEC68h
0x10026cc7  test    eax, eax
0x10026cc9  js      short locret_10026CCD
0x10026ccb  xor     eax, eax
0x10026ccd  retn    0Ch
```
