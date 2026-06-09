# CdpConvertClientDesiredAccess

- ea: `0x14000bc70`
- end: `0x14000bcd1`
- name: `CdpConvertClientDesiredAccess`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b4d0`

## callees

- `0x14000bc70`

## pseudocode

```c
__int64 __fastcall CdpConvertClientDesiredAccess(int *a1, int a2)
{
  unsigned int v2; // r8d
  int v3; // r9d
  int v4; // eax

  v2 = 0x80000000;
  if ( (a2 & 0x120089) != 0x120089 )
    v2 = 0;
  v3 = v2 | 0x40000000;
  if ( (a2 & 0x120116) != 0x120116 )
    v3 = v2;
  v4 = v3 | 0x20000000;
  if ( (a2 & 0x1200A0) != 0x1200A0 )
    v4 = v3;
  if ( (a2 & 0xFFEDFE40) != 0 )
    return 3221225506LL;
  *a1 = v4;
  return 0;
}

```

## disassembly

```asm
0x14000bc70  mov     r10, rcx
0x14000bc73  mov     eax, edx
0x14000bc75  and     eax, 120089h
0x14000bc7a  xor     ecx, ecx
0x14000bc7c  cmp     eax, 120089h
0x14000bc81  mov     r8d, 80000000h
0x14000bc87  mov     eax, edx
0x14000bc89  cmovnz  r8d, ecx
0x14000bc8d  and     eax, 120116h
0x14000bc92  mov     r9d, r8d
0x14000bc95  mov     ecx, edx
0x14000bc97  bts     r9d, 1Eh
0x14000bc9c  cmp     eax, 120116h
0x14000bca1  cmovnz  r9d, r8d
0x14000bca5  and     ecx, 1200A0h
0x14000bcab  mov     eax, r9d
0x14000bcae  bts     eax, 1Dh
0x14000bcb2  cmp     ecx, 1200A0h
0x14000bcb8  cmovnz  eax, r9d
0x14000bcbc  test    edx, 0FFEDFE40h
0x14000bcc2  jnz     short loc_14000BCCB
0x14000bcc4  mov     [r10], eax
0x14000bcc7  xor     eax, eax
0x14000bcc9  retn
0x14000bccb  mov     eax, 0C0000022h
0x14000bcd0  retn
```
