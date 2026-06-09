# ConvertToXmlEscapedChar(ushort,ulong *,ushort *)

- ea: `0x1800146fc`
- end: `0x1800147f3`
- name: `?ConvertToXmlEscapedChar@@YAJGPEAKPEAG@Z`
- size: `247`
- prototype: `int(unsigned __int16, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800120c0`

## callees

- `0x1800146fc`
- `0x1800147fc`
- `0x18002c48e`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800147d3`
- `msvcrt!wcsncpy_s` at `0x1800147d3`

## pseudocode

```c
__int64 __fastcall ConvertToXmlEscapedChar(unsigned __int16 a1, unsigned int *a2, unsigned __int16 *a3)
{
  int v3; // ebp
  unsigned int v5; // ebx
  unsigned int *v6; // r8
  unsigned int v7; // eax
  const wchar_t *v8; // rdi
  size_t v9; // rsi

  v3 = a1;
  if ( a2 )
  {
    if ( (unsigned int)IsCharXmlEscapable(a1) )
    {
      switch ( v3 )
      {
        case '"':
          v7 = 14;
          v8 = L"&quot;";
          break;
        case '&':
          v7 = 12;
          v8 = L"&amp;";
          break;
        case '\'':
          v7 = 14;
          v8 = L"&apos;";
          break;
        case '<':
          v7 = 10;
          v8 = L"&lt;";
          break;
        case '>':
          v7 = 10;
          v8 = L"&gt;";
          break;
        default:
          return (unsigned int)-2147024883;
      }
    }
    else
    {
      v7 = 4;
      v8 = 0;
    }
    if ( *v6 >= v7 )
    {
      v9 = *v6;
      v5 = 0;
      memset_0(a3, 0, v9);
      if ( v8 )
      {
        wcsncpy_s(a3, v9 >> 1, v8, (v9 >> 1) - 1);
      }
      else
      {
        *a3 = v3;
        a3[1] = 0;
      }
    }
    else
    {
      *v6 = v7;
      return (unsigned int)-2147024774;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x1800146fc  push    rbx
0x1800146fe  push    rbp
0x1800146ff  push    rsi
0x180014700  push    rdi
0x180014701  push    r14
0x180014703  sub     rsp, 20h
0x180014707  movzx   ebp, cx
0x18001470a  mov     r14, r8
0x18001470d  mov     r8, rdx
0x180014710  test    rdx, rdx
0x180014713  jnz     short loc_18001471F
0x180014715  mov     ebx, 80070057h
0x18001471a  jmp     loc_1800147E6
0x18001471f  movzx   ecx, bp; unsigned __int16
0x180014722  call    ?IsCharXmlEscapable@@YAHG@Z; IsCharXmlEscapable(ushort)
0x180014727  test    eax, eax
0x180014729  jz      short loc_180014796
0x18001472b  mov     ecx, ebp
0x18001472d  sub     ecx, 22h ; '"'
0x180014730  jz      short loc_180014788
0x180014732  sub     ecx, 4
0x180014735  jz      short loc_18001477A
0x180014737  sub     ecx, 1
0x18001473a  jz      short loc_18001476C
0x18001473c  sub     ecx, 15h
0x18001473f  jz      short loc_18001475E
0x180014741  cmp     ecx, 2
0x180014744  jz      short loc_180014750
0x180014746  mov     ebx, 8007000Dh
0x18001474b  jmp     loc_1800147E6
0x180014750  mov     eax, 0Ah
0x180014755  lea     rdi, aGt; "&gt;"
0x18001475c  jmp     short loc_18001479D
0x18001475e  mov     eax, 0Ah
0x180014763  lea     rdi, aLt; "&lt;"
0x18001476a  jmp     short loc_18001479D
0x18001476c  mov     eax, 0Eh
0x180014771  lea     rdi, aApos; "&apos;"
0x180014778  jmp     short loc_18001479D
0x18001477a  mov     eax, 0Ch
0x18001477f  lea     rdi, aAmp_0; "&amp;"
0x180014786  jmp     short loc_18001479D
0x180014788  mov     eax, 0Eh
0x18001478d  lea     rdi, aQuot_0; "&quot;"
0x180014794  jmp     short loc_18001479D
0x180014796  mov     eax, 4
0x18001479b  xor     edi, edi
0x18001479d  cmp     [r8], eax
0x1800147a0  jnb     short loc_1800147AC
0x1800147a2  mov     [r8], eax
0x1800147a5  mov     ebx, 8007007Ah
0x1800147aa  jmp     short loc_1800147E6
0x1800147ac  mov     esi, [r8]
0x1800147af  xor     edx, edx; Val
0x1800147b1  mov     r8d, esi; Size
0x1800147b4  mov     rcx, r14; void *
0x1800147b7  xor     ebx, ebx
0x1800147b9  call    memset_0
0x1800147be  test    rdi, rdi
0x1800147c1  jz      short loc_1800147DB
0x1800147c3  shr     rsi, 1
0x1800147c6  mov     r8, rdi; Source
0x1800147c9  mov     rdx, rsi; SizeInWords
0x1800147cc  mov     rcx, r14; Destination
0x1800147cf  lea     r9, [rsi-1]; MaxCount
0x1800147d3  call    cs:__imp_wcsncpy_s
0x1800147d9  jmp     short loc_1800147E6
0x1800147db  xor     ecx, ecx
0x1800147dd  mov     [r14], bp
0x1800147e1  mov     [r14+2], cx
0x1800147e6  mov     eax, ebx
0x1800147e8  add     rsp, 20h
0x1800147ec  pop     r14
0x1800147ee  pop     rdi
0x1800147ef  pop     rsi
0x1800147f0  pop     rbp
0x1800147f1  pop     rbx
0x1800147f2  retn
```
