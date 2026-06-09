# GetEnrollmentIdSidStateDocIdVersionRawKey

- ea: `0x14005d46c`
- end: `0x14005d568`
- name: `GetEnrollmentIdSidStateDocIdVersionRawKey`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x140058a5c`

## callees

- `0x1400036e4`
- `0x140058460`
- `0x14005d46c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005d4f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005d4f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005d52c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005d52c`

## pseudocode

```c
__int64 __fastcall GetEnrollmentIdSidStateDocIdVersionRawKey(_QWORD *a1, __int64 a2, __int64 a3, LPCWSTR *a4)
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
    v6 = DCStringCchPrintfAllStrings(&lpSubKey, qword_140085180, 4, *a1);
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
0x14005d46c  mov     r11, rsp
0x14005d46f  mov     [r11+8], rbx
0x14005d473  mov     [r11+10h], rsi
0x14005d477  push    rdi
0x14005d478  sub     rsp, 40h
0x14005d47c  xor     edi, edi
0x14005d47e  mov     rsi, r9
0x14005d481  mov     [r11+20h], rdi
0x14005d485  test    r9, r9
0x14005d488  jz      loc_14005D543
0x14005d48e  test    rcx, rcx
0x14005d491  jz      loc_14005D543
0x14005d497  mov     [r11-18h], r8
0x14005d49b  lea     r8d, [rdi+4]
0x14005d49f  mov     [r9], rdi
0x14005d4a2  mov     rax, [rcx+8]
0x14005d4a6  mov     r9, [rcx]
0x14005d4a9  lea     rcx, [r11+20h]
0x14005d4ad  mov     [r11-20h], rdx
0x14005d4b1  mov     rdx, cs:qword_140085180
0x14005d4b8  mov     [r11-28h], rax
0x14005d4bc  call    DCStringCchPrintfAllStrings
0x14005d4c1  mov     rdi, [rsp+48h+lpSubKey]
0x14005d4c6  mov     ebx, eax
0x14005d4c8  test    eax, eax
0x14005d4ca  js      short loc_14005D548
0x14005d4cc  xor     ecx, ecx; hKey
0x14005d4ce  mov     [rsp+48h+lpSubKey], rcx
0x14005d4d3  test    rdi, rdi
0x14005d4d6  jz      short loc_14005D522
0x14005d4d8  lea     rax, [rsp+48h+lpSubKey]
0x14005d4dd  mov     r9d, 2011Fh; samDesired
0x14005d4e3  xor     r8d, r8d; ulOptions
0x14005d4e6  mov     [rsp+48h+phkResult], rax; phkResult
0x14005d4eb  mov     rdx, rdi; lpSubKey
0x14005d4ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005d4f5  call    cs:__imp_RegOpenKeyExW
0x14005d4fc  nop     dword ptr [rax+rax+00h]
0x14005d501  mov     ebx, eax
0x14005d503  test    eax, eax
0x14005d505  jz      short loc_14005D519
0x14005d507  jle     short loc_14005D512
0x14005d509  movzx   ebx, ax
0x14005d50c  or      ebx, 80070000h
0x14005d512  mov     rcx, [rsp+48h+lpSubKey]
0x14005d517  jmp     short loc_14005D527
0x14005d519  mov     rax, [rsp+48h+lpSubKey]
0x14005d51e  xor     ebx, ebx
0x14005d520  jmp     short loc_14005D53E
0x14005d522  mov     ebx, 80070057h
0x14005d527  test    rcx, rcx
0x14005d52a  jz      short loc_14005D538
0x14005d52c  call    cs:__imp_RegCloseKey
0x14005d533  nop     dword ptr [rax+rax+00h]
0x14005d538  xor     eax, eax
0x14005d53a  test    ebx, ebx
0x14005d53c  js      short loc_14005D548
0x14005d53e  mov     [rsi], rax
0x14005d541  jmp     short loc_14005D548
0x14005d543  mov     ebx, 80070057h
0x14005d548  test    rdi, rdi
0x14005d54b  jz      short loc_14005D555
0x14005d54d  mov     rcx, rdi; Block
0x14005d550  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005d555  mov     rsi, [rsp+48h+arg_8]
0x14005d55a  mov     eax, ebx
0x14005d55c  mov     rbx, [rsp+48h+arg_0]
0x14005d561  add     rsp, 40h
0x14005d565  pop     rdi
0x14005d566  retn
```
