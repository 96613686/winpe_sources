# WriteString

- ea: `0x10028f80`
- end: `0x10028fff`
- name: `WriteString`
- size: `127`
- prototype: `int __stdcall(int, int, void *, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x10026500`
- `0x100268c0`
- `0x10026b10`

## callees

- `0x10028bb0`
- `0x10028ee0`
- `0x10028f80`

## pseudocode

```c
int __stdcall WriteString(int a1, int a2, unsigned __int16 *a3, char a4, int a5)
{
  int result; // eax
  int v6; // eax
  unsigned int v7; // eax

  result = WriteBytes(a1, a2, a3, wcslen(a3), a4, a5);
  if ( !result )
  {
    if ( (a4 & 1) != 0 && (v6 = TextWriteHTMLFile(a1, a2, asc_1003F048, 2, a5, 0)) != 0 )
    {
      v7 = -v6;
      if ( v7 >= 0x10 )
        return -5016;
      else
        return dword_100038B8[v7];
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10028f80  mov     edx, [esp+arg_8]
0x10028f84  mov     ecx, edx
0x10028f86  push    esi
0x10028f87  lea     esi, [ecx+2]
0x10028f8a  lea     ebx, [ebx+0]
0x10028f90  mov     ax, [ecx]
0x10028f93  add     ecx, 2
0x10028f96  test    ax, ax
0x10028f99  jnz     short loc_10028F90
0x10028f9b  sub     ecx, esi
0x10028f9d  mov     esi, [esp+4+arg_10]
0x10028fa1  push    esi; int
0x10028fa2  push    [esp+8+arg_C]; int
0x10028fa6  sar     ecx, 1
0x10028fa8  push    ecx; int
0x10028fa9  push    edx; void *
0x10028faa  push    [esp+14h+arg_4]; int
0x10028fae  push    [esp+18h+arg_0]; int
0x10028fb2  call    WriteBytes
0x10028fb7  test    eax, eax
0x10028fb9  jnz     short loc_10028FFB
0x10028fbb  test    byte ptr [esp+4+arg_C], 1
0x10028fc0  jz      short loc_10028FF9
0x10028fc2  push    eax; int
0x10028fc3  push    esi; int
0x10028fc4  push    2; int
0x10028fc6  push    offset asc_1003F048; "\r\n"
0x10028fcb  push    [esp+14h+arg_4]; int
0x10028fcf  push    [esp+18h+arg_0]; int
0x10028fd3  call    TextWriteHTMLFile
0x10028fd8  test    eax, eax
0x10028fda  jz      short loc_10028FF9
0x10028fdc  neg     eax
0x10028fde  js      short loc_10028FF0
0x10028fe0  cmp     eax, 0Fh
0x10028fe3  ja      short loc_10028FF0
0x10028fe5  mov     eax, ds:dword_100038B8[eax*4]
0x10028fec  pop     esi
0x10028fed  retn    14h
0x10028ff0  mov     eax, 0FFFFEC68h
0x10028ff5  pop     esi
0x10028ff6  retn    14h
0x10028ff9  xor     eax, eax
0x10028ffb  pop     esi
0x10028ffc  retn    14h
```
