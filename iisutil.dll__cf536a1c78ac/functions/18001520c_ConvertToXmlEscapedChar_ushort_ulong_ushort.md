# ConvertToXmlEscapedChar(ushort,ulong *,ushort *)

- ea: `0x18001520c`
- end: `0x18001530a`
- name: `?ConvertToXmlEscapedChar@@YAJGPEAKPEAG@Z`
- size: `254`
- prototype: `int(unsigned __int16, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012a10`

## callees

- `0x18001520c`
- `0x180015310`
- `0x18002e52e`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800152e3`
- `msvcrt!wcsncpy_s` at `0x1800152e3`

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
0x18001520c  push    rbx
0x18001520e  push    rbp
0x18001520f  push    rsi
0x180015210  push    rdi
0x180015211  push    r14
0x180015213  sub     rsp, 20h
0x180015217  movzx   ebp, cx
0x18001521a  mov     r14, r8
0x18001521d  mov     r8, rdx
0x180015220  test    rdx, rdx
0x180015223  jnz     short loc_18001522F
0x180015225  mov     ebx, 80070057h
0x18001522a  jmp     loc_1800152FC
0x18001522f  movzx   ecx, bp; unsigned __int16
0x180015232  call    ?IsCharXmlEscapable@@YAHG@Z; IsCharXmlEscapable(ushort)
0x180015237  test    eax, eax
0x180015239  jz      short loc_1800152A6
0x18001523b  mov     ecx, ebp
0x18001523d  sub     ecx, 22h ; '"'
0x180015240  jz      short loc_180015298
0x180015242  sub     ecx, 4
0x180015245  jz      short loc_18001528A
0x180015247  sub     ecx, 1
0x18001524a  jz      short loc_18001527C
0x18001524c  sub     ecx, 15h
0x18001524f  jz      short loc_18001526E
0x180015251  cmp     ecx, 2
0x180015254  jz      short loc_180015260
0x180015256  mov     ebx, 8007000Dh
0x18001525b  jmp     loc_1800152FC
0x180015260  mov     eax, 0Ah
0x180015265  lea     rdi, aGt; "&gt;"
0x18001526c  jmp     short loc_1800152AD
0x18001526e  mov     eax, 0Ah
0x180015273  lea     rdi, aLt; "&lt;"
0x18001527a  jmp     short loc_1800152AD
0x18001527c  mov     eax, 0Eh
0x180015281  lea     rdi, aApos; "&apos;"
0x180015288  jmp     short loc_1800152AD
0x18001528a  mov     eax, 0Ch
0x18001528f  lea     rdi, aAmp_0; "&amp;"
0x180015296  jmp     short loc_1800152AD
0x180015298  mov     eax, 0Eh
0x18001529d  lea     rdi, aQuot_0; "&quot;"
0x1800152a4  jmp     short loc_1800152AD
0x1800152a6  mov     eax, 4
0x1800152ab  xor     edi, edi
0x1800152ad  cmp     [r8], eax
0x1800152b0  jnb     short loc_1800152BC
0x1800152b2  mov     [r8], eax
0x1800152b5  mov     ebx, 8007007Ah
0x1800152ba  jmp     short loc_1800152FC
0x1800152bc  mov     esi, [r8]
0x1800152bf  xor     edx, edx; Val
0x1800152c1  mov     r8d, esi; Size
0x1800152c4  mov     rcx, r14; void *
0x1800152c7  xor     ebx, ebx
0x1800152c9  call    memset_0
0x1800152ce  test    rdi, rdi
0x1800152d1  jz      short loc_1800152F1
0x1800152d3  shr     rsi, 1
0x1800152d6  mov     r8, rdi; Source
0x1800152d9  mov     rdx, rsi; SizeInWords
0x1800152dc  mov     rcx, r14; Destination
0x1800152df  lea     r9, [rsi-1]; MaxCount
0x1800152e3  call    cs:__imp_wcsncpy_s
0x1800152ea  nop     dword ptr [rax+rax+00h]
0x1800152ef  jmp     short loc_1800152FC
0x1800152f1  xor     ecx, ecx
0x1800152f3  mov     [r14], bp
0x1800152f7  mov     [r14+2], cx
0x1800152fc  mov     eax, ebx
0x1800152fe  add     rsp, 20h
0x180015302  pop     r14
0x180015304  pop     rdi
0x180015305  pop     rsi
0x180015306  pop     rbp
0x180015307  pop     rbx
0x180015308  retn
```
