# _ParseReportUriValue

- ea: `0x180016a54`
- end: `0x180016b29`
- name: `_ParseReportUriValue`
- size: `213`
- prototype: `void __fastcall(LPCCH lpMultiByteStr, int cbMultiByte, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016bf4`

## callees

- `0x1800033a0`
- `0x1800068b0`
- `0x180016a54`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180016aa0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180016ae7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180016aa0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180016ae7`

## pseudocode

```c
void __fastcall ParseReportUriValue(LPCCH lpMultiByteStr, int cbMultiByte, _DWORD *a3)
{
  HLOCAL *v3; // rdi
  int v7; // eax
  int cchWideChar; // r14d
  WCHAR *lpWideCharStr; // rax
  WCHAR *v10; // rsi

  v3 = (HLOCAL *)(a3 + 8);
  if ( !cbMultiByte || *v3 )
  {
    *a3 |= 0x10u;
    if ( *v3 )
    {
      PkiFree(*v3);
      *v3 = 0;
    }
  }
  else
  {
    v7 = MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, cbMultiByte, 0, 0);
    cchWideChar = v7;
    if ( v7 > 1 )
    {
      lpWideCharStr = (WCHAR *)PkiZeroAlloc(2LL * (v7 + 1));
      v10 = lpWideCharStr;
      if ( lpWideCharStr )
      {
        if ( MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, cbMultiByte, lpWideCharStr, cchWideChar) >= 1 )
        {
          *v3 = v10;
        }
        else
        {
          *a3 |= 0x10u;
          PkiFree(v10);
        }
      }
      else
      {
        *a3 |= 2u;
      }
    }
    else
    {
      *a3 |= 0x10u;
    }
  }
}

```

## disassembly

```asm
0x180016a54  push    rbx
0x180016a56  push    rbp
0x180016a57  push    rsi
0x180016a58  push    rdi
0x180016a59  push    r14
0x180016a5b  push    r15
0x180016a5d  sub     rsp, 38h
0x180016a61  lea     rdi, [r8+20h]
0x180016a65  mov     rbx, r8
0x180016a68  mov     ebp, edx
0x180016a6a  mov     r15, rcx
0x180016a6d  test    edx, edx
0x180016a6f  jz      loc_180016B04
0x180016a75  cmp     qword ptr [rdi], 0
0x180016a79  jnz     loc_180016B04
0x180016a7f  mov     r9d, edx; cbMultiByte
0x180016a82  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x180016a8a  mov     r8, rcx; lpMultiByteStr
0x180016a8d  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x180016a96  mov     edx, 8; dwFlags
0x180016a9b  mov     ecx, 0FDE9h; CodePage
0x180016aa0  call    cs:__imp_MultiByteToWideChar
0x180016aa6  mov     r14d, eax
0x180016aa9  cmp     eax, 1
0x180016aac  jg      short loc_180016AB3
0x180016aae  or      dword ptr [rbx], 10h
0x180016ab1  jmp     short loc_180016B1C
0x180016ab3  inc     eax
0x180016ab5  movsxd  rcx, eax
0x180016ab8  add     rcx, rcx; uBytes
0x180016abb  call    PkiZeroAlloc
0x180016ac0  mov     rsi, rax
0x180016ac3  test    rax, rax
0x180016ac6  jnz     short loc_180016ACD
0x180016ac8  or      dword ptr [rbx], 2
0x180016acb  jmp     short loc_180016B1C
0x180016acd  mov     [rsp+68h+cchWideChar], r14d; cchWideChar
0x180016ad2  mov     r9d, ebp; cbMultiByte
0x180016ad5  mov     r8, r15; lpMultiByteStr
0x180016ad8  mov     [rsp+68h+lpWideCharStr], rsi; lpWideCharStr
0x180016add  mov     edx, 8; dwFlags
0x180016ae2  mov     ecx, 0FDE9h; CodePage
0x180016ae7  call    cs:__imp_MultiByteToWideChar
0x180016aed  cmp     eax, 1
0x180016af0  jge     short loc_180016AFF
0x180016af2  or      dword ptr [rbx], 10h
0x180016af5  mov     rcx, rsi; hMem
0x180016af8  call    PkiFree
0x180016afd  jmp     short loc_180016B1C
0x180016aff  mov     [rdi], rsi
0x180016b02  jmp     short loc_180016B1C
0x180016b04  or      dword ptr [r8], 10h
0x180016b08  mov     rcx, [rdi]; hMem
0x180016b0b  test    rcx, rcx
0x180016b0e  jz      short loc_180016B1C
0x180016b10  call    PkiFree
0x180016b15  mov     qword ptr [rdi], 0
0x180016b1c  add     rsp, 38h
0x180016b20  pop     r15
0x180016b22  pop     r14
0x180016b24  pop     rdi
0x180016b25  pop     rsi
0x180016b26  pop     rbp
0x180016b27  pop     rbx
0x180016b28  retn
```
