# CUiaHyperlink::GetHyperlinkData(ushort * *,ushort * *)

- ea: `0x1801f2100`
- end: `0x1801f224b`
- name: `?GetHyperlinkData@CUiaHyperlink@@QEAAJPEAPEAG0@Z`
- size: `331`
- prototype: `int(CUiaHyperlink *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801f2550`
- `0x1801f262c`
- `0x1801f2910`

## callees

- `0x180043e7c`
- `0x1800440f0`
- `0x180109b08`
- `0x1801f1ed8`
- `0x1801f2100`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801f2198`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801f2198`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f217d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801f217d`

## string_xrefs

- `0x1801f2170`: `HYPERLINK "`

## pseudocode

```c
__int64 __fastcall CUiaHyperlink::GetHyperlinkData(CUiaHyperlink *this, unsigned __int16 **a2, unsigned __int16 **a3)
{
  signed int LinkText; // ebx
  LPCWCH v6; // rbp
  const unsigned __int16 *v7; // r14
  wchar_t *v8; // rax
  wchar_t *v9; // rbp
  const unsigned __int16 *i; // rcx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rcx
  LPCWCH lpString2; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  lpString2 = 0;
  LinkText = CUiaHyperlink::GetLinkText(this, (unsigned __int16 **)&lpString2);
  if ( LinkText >= 0 )
  {
    LinkText = 0;
    v6 = lpString2 + 1;
    if ( *lpString2 != 0xFDDF )
      v6 = lpString2;
    if ( CompareStringOrdinal(L"HYPERLINK \"", -1, v6, 11, 1) == 2 )
    {
      v7 = v6 + 11;
      v8 = wcschr(v6 + 11, 0x22u);
      v9 = v8;
      if ( v8 )
      {
        for ( i = v8 + 1; *i == 32; ++i )
          ;
        if ( a2 )
          LinkText = HrSysAllocString(i, a2);
        if ( a3 )
        {
          v11 = CW32System::SysAllocStringLen(v7, v9 - v7);
          *a3 = v11;
          LinkText = v11 == 0 ? 0x8007000E : 0;
        }
      }
      else
      {
        LinkText = -2147467259;
      }
    }
    else
    {
      if ( a2 )
        LinkText = HrSysAllocString(v6, a2);
      if ( a3 )
        LinkText = HrSysAllocString(v6, a3);
    }
  }
  v12 = (unsigned __int16 *)lpString2;
  if ( lpString2 )
  {
    lpString2 = 0;
    CW32System::SysFreeString(v12);
  }
  return (unsigned int)LinkText;
}

```

## disassembly

```asm
0x1801f2100  mov     [rsp+arg_0], rbx
0x1801f2105  mov     [rsp+arg_10], rbp
0x1801f210a  push    rsi
0x1801f210b  push    rdi
0x1801f210c  push    r14
0x1801f210e  sub     rsp, 30h
0x1801f2112  mov     rdi, r8
0x1801f2115  mov     rsi, rdx
0x1801f2118  test    rdx, rdx
0x1801f211b  jz      short loc_1801F2124
0x1801f211d  mov     qword ptr [rdx], 0
0x1801f2124  test    rdi, rdi
0x1801f2127  jz      short loc_1801F2130
0x1801f2129  mov     qword ptr [r8], 0
0x1801f2130  lea     rdx, [rsp+48h+lpString2]; unsigned __int16 **
0x1801f2135  mov     [rsp+48h+lpString2], 0
0x1801f213e  call    ?GetLinkText@CUiaHyperlink@@QEAAJPEAPEAG@Z; CUiaHyperlink::GetLinkText(ushort * *)
0x1801f2143  mov     ebx, eax
0x1801f2145  test    eax, eax
0x1801f2147  js      loc_1801F221D
0x1801f214d  mov     rax, [rsp+48h+lpString2]
0x1801f2152  xor     ebx, ebx
0x1801f2154  mov     ecx, 0FDDFh
0x1801f2159  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x1801f2161  cmp     [rax], cx
0x1801f2164  lea     rbp, [rax+2]
0x1801f2168  lea     r9d, [rbx+0Bh]; cchCount2
0x1801f216c  cmovnz  rbp, rax
0x1801f2170  lea     rcx, ?cszLinkPrefix@@3QBGB; "HYPERLINK \""
0x1801f2177  mov     r8, rbp; lpString2
0x1801f217a  or      edx, 0FFFFFFFFh; cchCount1
0x1801f217d  call    cs:__imp_CompareStringOrdinal
0x1801f2184  nop     dword ptr [rax+rax+00h]
0x1801f2189  cmp     eax, 2
0x1801f218c  jnz     short loc_1801F21F9
0x1801f218e  lea     r14, [rbp+16h]
0x1801f2192  mov     rcx, r14; Str
0x1801f2195  lea     edx, [rbx+22h]; Ch
0x1801f2198  call    cs:__imp_wcschr
0x1801f219f  nop     dword ptr [rax+rax+00h]
0x1801f21a4  mov     rbp, rax
0x1801f21a7  test    rax, rax
0x1801f21aa  jz      short loc_1801F21F2
0x1801f21ac  lea     rcx, [rax+2]
0x1801f21b0  jmp     short loc_1801F21B6
0x1801f21b2  add     rcx, 2; unsigned __int16 *
0x1801f21b6  cmp     word ptr [rcx], 20h ; ' '
0x1801f21ba  jz      short loc_1801F21B2
0x1801f21bc  test    rsi, rsi
0x1801f21bf  jz      short loc_1801F21CB
0x1801f21c1  mov     rdx, rsi; unsigned __int16 **
0x1801f21c4  call    ?HrSysAllocString@@YAJPEBGPEAPEAG@Z; HrSysAllocString(ushort const *,ushort * *)
0x1801f21c9  mov     ebx, eax
0x1801f21cb  test    rdi, rdi
0x1801f21ce  jz      short loc_1801F221D
0x1801f21d0  sub     rbp, r14
0x1801f21d3  mov     rcx, r14; unsigned __int16 *
0x1801f21d6  sar     rbp, 1
0x1801f21d9  mov     edx, ebp; unsigned int
0x1801f21db  call    ?SysAllocStringLen@CW32System@@SAPEAGPEBGI@Z; CW32System::SysAllocStringLen(ushort const *,uint)
0x1801f21e0  mov     [rdi], rax
0x1801f21e3  neg     rax
0x1801f21e6  sbb     ebx, ebx
0x1801f21e8  not     ebx
0x1801f21ea  and     ebx, 8007000Eh
0x1801f21f0  jmp     short loc_1801F221D
0x1801f21f2  mov     ebx, 80004005h
0x1801f21f7  jmp     short loc_1801F221D
0x1801f21f9  test    rsi, rsi
0x1801f21fc  jz      short loc_1801F220B
0x1801f21fe  mov     rdx, rsi; unsigned __int16 **
0x1801f2201  mov     rcx, rbp; unsigned __int16 *
0x1801f2204  call    ?HrSysAllocString@@YAJPEBGPEAPEAG@Z; HrSysAllocString(ushort const *,ushort * *)
0x1801f2209  mov     ebx, eax
0x1801f220b  test    rdi, rdi
0x1801f220e  jz      short loc_1801F221D
0x1801f2210  mov     rdx, rdi; unsigned __int16 **
0x1801f2213  mov     rcx, rbp; unsigned __int16 *
0x1801f2216  call    ?HrSysAllocString@@YAJPEBGPEAPEAG@Z; HrSysAllocString(ushort const *,ushort * *)
0x1801f221b  mov     ebx, eax
0x1801f221d  mov     rcx, [rsp+48h+lpString2]; unsigned __int16 *
0x1801f2222  test    rcx, rcx
0x1801f2225  jz      short loc_1801F2235
0x1801f2227  mov     [rsp+48h+lpString2], 0
0x1801f2230  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1801f2235  mov     rbp, [rsp+48h+arg_10]
0x1801f223a  mov     eax, ebx
0x1801f223c  mov     rbx, [rsp+48h+arg_0]
0x1801f2241  add     rsp, 30h
0x1801f2245  pop     r14
0x1801f2247  pop     rdi
0x1801f2248  pop     rsi
0x1801f2249  retn
```
