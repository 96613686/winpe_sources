# CUiaHyperlink::GetTextStartCp(void)

- ea: `0x180109a20`
- end: `0x180109b00`
- name: `?GetTextStartCp@CUiaHyperlink@@UEAAJXZ`
- size: `224`
- prototype: `__int64 __fastcall(CUiaHyperlink *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180043e7c`
- `0x180109a20`
- `0x180109b08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180109aa4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180109aa4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180109a88`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180109a88`

## string_xrefs

- `0x180109a81`: `HYPERLINK "`

## pseudocode

```c
__int64 __fastcall CUiaHyperlink::GetTextStartCp(CUiaHyperlink *this)
{
  unsigned int v1; // ebx
  LPCWCH v2; // rcx
  const WCHAR *v3; // rdi
  wchar_t *v4; // rax
  __int64 v5; // rcx
  unsigned __int16 *v6; // rdx
  LPCWCH lpString2; // [rsp+40h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 4);
  lpString2 = 0;
  if ( (int)CUiaHyperlink::GetLinkText(this, (unsigned __int16 **)&lpString2) < 0 )
    goto LABEL_11;
  v2 = lpString2 + 1;
  if ( *lpString2 != 0xFDDF )
    v2 = lpString2;
  v3 = v2 + 1;
  if ( *v2 != 32 )
    v3 = v2;
  if ( CompareStringOrdinal(L"HYPERLINK \"", -1, v3, 11, 1) == 2 && (v4 = wcschr(v3 + 12, 0x22u)) != 0 )
  {
    v5 = 4;
    v6 = (unsigned __int16 *)lpString2;
    if ( v4[1] != 32 )
      v5 = 2;
    v1 += ((__int64)v4 + v5 - (__int64)lpString2) >> 1;
  }
  else
  {
LABEL_11:
    v6 = (unsigned __int16 *)lpString2;
  }
  if ( v6 )
  {
    lpString2 = 0;
    CW32System::SysFreeString(v6);
  }
  return v1;
}

```

## disassembly

```asm
0x180109a20  mov     rax, rsp
0x180109a23  mov     [rax+10h], rbx
0x180109a27  mov     [rax+18h], rsi
0x180109a2b  push    rdi
0x180109a2c  sub     rsp, 30h
0x180109a30  mov     ebx, [rcx+10h]
0x180109a33  lea     rdx, [rax+8]; unsigned __int16 **
0x180109a37  mov     qword ptr [rax+8], 0
0x180109a3f  call    ?GetLinkText@CUiaHyperlink@@QEAAJPEAPEAG@Z; CUiaHyperlink::GetLinkText(ushort * *)
0x180109a44  test    eax, eax
0x180109a46  js      loc_180109AD2
0x180109a4c  mov     rax, [rsp+38h+lpString2]
0x180109a51  mov     edx, 0FDDFh
0x180109a56  mov     r9d, 0Bh; cchCount2
0x180109a5c  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180109a64  cmp     [rax], dx
0x180109a67  lea     rcx, [rax+2]
0x180109a6b  cmovnz  rcx, rax
0x180109a6f  cmp     word ptr [rcx], 20h ; ' '
0x180109a73  lea     rdi, [rcx+2]
0x180109a77  cmovnz  rdi, rcx
0x180109a7b  or      edx, 0FFFFFFFFh; cchCount1
0x180109a7e  mov     r8, rdi; lpString2
0x180109a81  lea     rcx, ?cszLinkPrefix@@3QBGB; "HYPERLINK \""
0x180109a88  call    cs:__imp_CompareStringOrdinal
0x180109a8f  nop     dword ptr [rax+rax+00h]
0x180109a94  mov     esi, 2
0x180109a99  cmp     eax, esi
0x180109a9b  jnz     short loc_180109AD2
0x180109a9d  lea     edx, [rsi+20h]; Ch
0x180109aa0  lea     rcx, [rdi+18h]; Str
0x180109aa4  call    cs:__imp_wcschr
0x180109aab  nop     dword ptr [rax+rax+00h]
0x180109ab0  test    rax, rax
0x180109ab3  jz      short loc_180109AD2
0x180109ab5  cmp     word ptr [rax+2], 20h ; ' '
0x180109aba  lea     ecx, [rsi+2]
0x180109abd  mov     rdx, [rsp+38h+lpString2]
0x180109ac2  cmovnz  ecx, esi
0x180109ac5  sub     rcx, rdx
0x180109ac8  add     rcx, rax
0x180109acb  sar     rcx, 1
0x180109ace  add     ebx, ecx
0x180109ad0  jmp     short loc_180109AD7
0x180109ad2  mov     rdx, [rsp+38h+lpString2]
0x180109ad7  test    rdx, rdx
0x180109ada  jz      short loc_180109AED
0x180109adc  mov     rcx, rdx; unsigned __int16 *
0x180109adf  mov     [rsp+38h+lpString2], 0
0x180109ae8  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x180109aed  mov     rsi, [rsp+38h+arg_10]
0x180109af2  mov     eax, ebx
0x180109af4  mov     rbx, [rsp+38h+arg_8]
0x180109af9  add     rsp, 30h
0x180109afd  pop     rdi
0x180109afe  retn
```
