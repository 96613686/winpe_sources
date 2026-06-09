# GetResultsEnrollmentIdSidStateDocIdVersionKey

- ea: `0x14005d570`
- end: `0x14005d66c`
- name: `GetResultsEnrollmentIdSidStateDocIdVersionKey`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x14005c570`

## callees

- `0x1400036e4`
- `0x140058460`
- `0x14005d570`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005d5f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005d5f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005d630`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005d630`

## pseudocode

```c
__int64 __fastcall GetResultsEnrollmentIdSidStateDocIdVersionKey(_QWORD *a1, __int64 a2, __int64 a3, LPCWSTR *a4)
{
  WCHAR *v4; // rdi
  int v6; // eax
  signed int v7; // ebx
  WCHAR *v8; // rcx
  LSTATUS v9; // eax
  LPCWSTR v10; // rax
  LPCWSTR lpSubKey; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  lpSubKey = 0;
  if ( a4 && a1 )
  {
    *a4 = 0;
    v6 = DCStringCchPrintfAllStrings(&lpSubKey, qword_140085178, 4, *a1);
    v4 = (WCHAR *)lpSubKey;
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_16;
    v8 = 0;
    lpSubKey = 0;
    if ( v4 )
    {
      v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x2011Fu, (PHKEY)&lpSubKey);
      v7 = v9;
      if ( !v9 )
      {
        v10 = lpSubKey;
        v7 = 0;
LABEL_14:
        *a4 = v10;
        goto LABEL_16;
      }
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      v8 = (WCHAR *)lpSubKey;
    }
    else
    {
      v7 = -2147024809;
    }
    if ( v8 )
      RegCloseKey((HKEY)v8);
    v10 = 0;
    if ( v7 >= 0 )
      goto LABEL_14;
  }
  else
  {
    v7 = -2147024809;
  }
LABEL_16:
  if ( v4 )
    operator delete(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14005d570  mov     r11, rsp
0x14005d573  mov     [r11+8], rbx
0x14005d577  mov     [r11+10h], rsi
0x14005d57b  push    rdi
0x14005d57c  sub     rsp, 40h
0x14005d580  xor     edi, edi
0x14005d582  mov     rsi, r9
0x14005d585  mov     [r11+20h], rdi
0x14005d589  test    r9, r9
0x14005d58c  jz      loc_14005D647
0x14005d592  test    rcx, rcx
0x14005d595  jz      loc_14005D647
0x14005d59b  mov     [r11-18h], r8
0x14005d59f  lea     r8d, [rdi+4]
0x14005d5a3  mov     [r9], rdi
0x14005d5a6  mov     rax, [rcx+8]
0x14005d5aa  mov     r9, [rcx]
0x14005d5ad  lea     rcx, [r11+20h]
0x14005d5b1  mov     [r11-20h], rdx
0x14005d5b5  mov     rdx, cs:qword_140085178
0x14005d5bc  mov     [r11-28h], rax
0x14005d5c0  call    DCStringCchPrintfAllStrings
0x14005d5c5  mov     rdi, [rsp+48h+lpSubKey]
0x14005d5ca  mov     ebx, eax
0x14005d5cc  test    eax, eax
0x14005d5ce  js      short loc_14005D64C
0x14005d5d0  xor     ecx, ecx; hKey
0x14005d5d2  mov     [rsp+48h+lpSubKey], rcx
0x14005d5d7  test    rdi, rdi
0x14005d5da  jz      short loc_14005D626
0x14005d5dc  lea     rax, [rsp+48h+lpSubKey]
0x14005d5e1  mov     r9d, 2011Fh; samDesired
0x14005d5e7  xor     r8d, r8d; ulOptions
0x14005d5ea  mov     [rsp+48h+phkResult], rax; phkResult
0x14005d5ef  mov     rdx, rdi; lpSubKey
0x14005d5f2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005d5f9  call    cs:__imp_RegOpenKeyExW
0x14005d600  nop     dword ptr [rax+rax+00h]
0x14005d605  mov     ebx, eax
0x14005d607  test    eax, eax
0x14005d609  jz      short loc_14005D61D
0x14005d60b  jle     short loc_14005D616
0x14005d60d  movzx   ebx, ax
0x14005d610  or      ebx, 80070000h
0x14005d616  mov     rcx, [rsp+48h+lpSubKey]
0x14005d61b  jmp     short loc_14005D62B
0x14005d61d  mov     rax, [rsp+48h+lpSubKey]
0x14005d622  xor     ebx, ebx
0x14005d624  jmp     short loc_14005D642
0x14005d626  mov     ebx, 80070057h
0x14005d62b  test    rcx, rcx
0x14005d62e  jz      short loc_14005D63C
0x14005d630  call    cs:__imp_RegCloseKey
0x14005d637  nop     dword ptr [rax+rax+00h]
0x14005d63c  xor     eax, eax
0x14005d63e  test    ebx, ebx
0x14005d640  js      short loc_14005D64C
0x14005d642  mov     [rsi], rax
0x14005d645  jmp     short loc_14005D64C
0x14005d647  mov     ebx, 80070057h
0x14005d64c  test    rdi, rdi
0x14005d64f  jz      short loc_14005D659
0x14005d651  mov     rcx, rdi; Block
0x14005d654  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005d659  mov     rsi, [rsp+48h+arg_8]
0x14005d65e  mov     eax, ebx
0x14005d660  mov     rbx, [rsp+48h+arg_0]
0x14005d665  add     rsp, 40h
0x14005d669  pop     rdi
0x14005d66a  retn
```
