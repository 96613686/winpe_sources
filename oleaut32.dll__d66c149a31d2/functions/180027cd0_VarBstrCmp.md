# VarBstrCmp

- ea: `0x180027cd0`
- end: `0x180027d96`
- name: `VarBstrCmp`
- size: `198`
- prototype: `HRESULT __stdcall(BSTR bstrLeft, BSTR bstrRight, LCID lcid, ULONG dwFlags)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026a04`
- `0x180026c10`

## callees

- `0x180027cd0`
- `0x180027d9c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027d26`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027d26`

## pseudocode

```c
HRESULT __stdcall VarBstrCmp(BSTR bstrLeft, BSTR bstrRight, LCID lcid, ULONG dwFlags)
{
  unsigned int v6; // edi
  unsigned int cchCount2; // ebx
  unsigned int v8; // esi
  LCID v9; // ecx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  unsigned __int8 v13; // al

  if ( bstrLeft )
    v6 = *((_DWORD *)bstrLeft - 1);
  else
    v6 = 0;
  if ( bstrRight )
    cchCount2 = *((_DWORD *)bstrRight - 1);
  else
    cchCount2 = 0;
  v8 = v6;
  if ( v6 >= cchCount2 )
    v8 = cchCount2;
  if ( !lcid )
  {
    if ( v8 )
    {
      v11 = wmemcmp(bstrLeft, bstrRight, (unsigned __int64)v8 >> 1);
      if ( v11 > 0 )
      {
LABEL_18:
        LODWORD(v10) = 2;
        return v10;
      }
      if ( v11 < 0 )
      {
        LODWORD(v10) = 0;
        return v10;
      }
      if ( (v8 & 1) != 0 )
      {
        v12 = v8 - 1;
        v13 = *((_BYTE *)bstrRight + v12);
        if ( *((_BYTE *)bstrLeft + v12) != v13 )
        {
          LODWORD(v10) = *((_BYTE *)bstrLeft + v12) < v13 ? 0 : 2;
          return v10;
        }
      }
    }
LABEL_22:
    if ( v6 <= cchCount2 )
      return v6 >= cchCount2;
    goto LABEL_18;
  }
  v6 >>= 1;
  cchCount2 >>= 1;
  if ( !v8 )
    goto LABEL_22;
  v9 = 1024;
  if ( lcid != 1 )
    v9 = lcid;
  LODWORD(v10) = CompareStringW(v9, dwFlags, bstrLeft, v6, bstrRight, cchCount2) - 1;
  if ( (_DWORD)v10 == -1 )
    LODWORD(v10) = -2147024809;
  return v10;
}

```

## disassembly

```asm
0x180027cd0  push    rbx
0x180027cd2  push    rbp
0x180027cd3  push    rsi
0x180027cd4  push    rdi
0x180027cd5  push    r14
0x180027cd7  sub     rsp, 30h
0x180027cdb  mov     eax, r9d
0x180027cde  mov     rbp, rdx
0x180027ce1  mov     r14, rcx
0x180027ce4  test    rcx, rcx
0x180027ce7  jz      short loc_180027D44
0x180027ce9  mov     edi, [rcx-4]
0x180027cec  test    rbp, rbp
0x180027cef  jz      short loc_180027D48
0x180027cf1  mov     ebx, [rdx-4]
0x180027cf4  cmp     edi, ebx
0x180027cf6  mov     esi, edi
0x180027cf8  cmovnb  esi, ebx
0x180027cfb  test    r8d, r8d
0x180027cfe  jz      short loc_180027D4C
0x180027d00  shr     edi, 1
0x180027d02  shr     ebx, 1
0x180027d04  test    esi, esi
0x180027d06  jz      short loc_180027D72
0x180027d08  cmp     r8d, 1
0x180027d0c  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x180027d10  mov     ecx, 400h
0x180027d15  mov     [rsp+58h+lpString2], rbp; lpString2
0x180027d1a  cmovnz  ecx, r8d; Locale
0x180027d1e  mov     r9d, edi; cchCount1
0x180027d21  mov     r8, r14; lpString1
0x180027d24  mov     edx, eax; dwCmpFlags
0x180027d26  call    cs:__imp_CompareStringW
0x180027d2c  dec     eax
0x180027d2e  mov     ecx, 80070057h; S1
0x180027d33  cmp     eax, 0FFFFFFFFh
0x180027d36  cmovz   eax, ecx
0x180027d39  add     rsp, 30h
0x180027d3d  pop     r14
0x180027d3f  pop     rdi
0x180027d40  pop     rsi
0x180027d41  pop     rbp
0x180027d42  pop     rbx
0x180027d43  retn
0x180027d44  xor     edi, edi
0x180027d46  jmp     short loc_180027CEC
0x180027d48  xor     ebx, ebx
0x180027d4a  jmp     short loc_180027CF4
0x180027d4c  test    esi, esi
0x180027d4e  jz      short loc_180027D72
0x180027d50  mov     r8d, esi
0x180027d53  shr     r8, 1; N
0x180027d56  call    wmemcmp
0x180027d5b  test    eax, eax
0x180027d5d  jle     short loc_180027D66
0x180027d5f  mov     eax, 2
0x180027d64  jmp     short loc_180027D39
0x180027d66  jns     short loc_180027D6C
0x180027d68  xor     eax, eax
0x180027d6a  jmp     short loc_180027D39
0x180027d6c  test    sil, 1
0x180027d70  jnz     short loc_180027D7F
0x180027d72  cmp     edi, ebx
0x180027d74  ja      short loc_180027D5F
0x180027d76  xor     eax, eax
0x180027d78  cmp     edi, ebx
0x180027d7a  setnb   al
0x180027d7d  jmp     short loc_180027D39
0x180027d7f  lea     eax, [rsi-1]
0x180027d82  mov     ecx, eax
0x180027d84  mov     al, [rax+rbp]
0x180027d87  cmp     [rcx+r14], al
0x180027d8b  jz      short loc_180027D72
0x180027d8d  sbb     eax, eax
0x180027d8f  not     eax
0x180027d91  and     eax, 2
0x180027d94  jmp     short loc_180027D39
```
