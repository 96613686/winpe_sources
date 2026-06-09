# DCGetResultReadonlyEnrollmentIdSidStateKey

- ea: `0x140058258`
- end: `0x140058351`
- name: `DCGetResultReadonlyEnrollmentIdSidStateKey`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x140058a5c`

## callees

- `0x1400036e4`
- `0x140058258`
- `0x140058460`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400582de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400582de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058315`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058315`

## pseudocode

```c
__int64 __fastcall DCGetResultReadonlyEnrollmentIdSidStateKey(__int64 a1, __int64 a2, LPCWSTR *a3)
{
  WCHAR *v3; // rdi
  int v5; // eax
  signed int v6; // ebx
  WCHAR *v7; // rcx
  LSTATUS v8; // eax
  LPCWSTR v9; // rax
  LPCWSTR lpSubKey; // [rsp+50h] [rbp+18h] BYREF

  v3 = 0;
  lpSubKey = 0;
  if ( a3 && a1 && a2 )
  {
    *a3 = 0;
    v5 = DCStringCchPrintfAllStrings(&lpSubKey, qword_140085160, 2, a1);
    v3 = (WCHAR *)lpSubKey;
    v6 = v5;
    if ( v5 < 0 )
      goto LABEL_17;
    v7 = 0;
    lpSubKey = 0;
    if ( v3 )
    {
      v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20119u, (PHKEY)&lpSubKey);
      v6 = v8;
      if ( !v8 )
      {
        v9 = lpSubKey;
        v6 = 0;
LABEL_15:
        *a3 = v9;
        goto LABEL_17;
      }
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      v7 = (WCHAR *)lpSubKey;
    }
    else
    {
      v6 = -2147024809;
    }
    if ( v7 )
      RegCloseKey((HKEY)v7);
    v9 = 0;
    if ( v6 >= 0 )
      goto LABEL_15;
  }
  else
  {
    v6 = -2147024809;
  }
LABEL_17:
  if ( v3 )
    operator delete(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140058258  mov     rax, rsp
0x14005825b  mov     [rax+8], rbx
0x14005825f  mov     [rax+10h], rsi
0x140058263  push    rdi
0x140058264  sub     rsp, 30h
0x140058268  xor     edi, edi
0x14005826a  mov     rsi, r8
0x14005826d  mov     [rax+18h], rdi
0x140058271  test    r8, r8
0x140058274  jz      loc_14005832C
0x14005827a  test    rcx, rcx
0x14005827d  jz      loc_14005832C
0x140058283  test    rdx, rdx
0x140058286  jz      loc_14005832C
0x14005828c  mov     [r8], rdi
0x14005828f  mov     r9, rcx
0x140058292  mov     [rax-18h], rdx
0x140058296  lea     r8d, [rdi+2]
0x14005829a  mov     rdx, cs:qword_140085160
0x1400582a1  lea     rcx, [rax+18h]
0x1400582a5  call    DCStringCchPrintfAllStrings
0x1400582aa  mov     rdi, [rsp+38h+lpSubKey]
0x1400582af  mov     ebx, eax
0x1400582b1  test    eax, eax
0x1400582b3  js      short loc_140058331
0x1400582b5  xor     ecx, ecx; hKey
0x1400582b7  mov     [rsp+38h+lpSubKey], rcx
0x1400582bc  test    rdi, rdi
0x1400582bf  jz      short loc_14005830B
0x1400582c1  lea     rax, [rsp+38h+lpSubKey]
0x1400582c6  mov     r9d, 20119h; samDesired
0x1400582cc  xor     r8d, r8d; ulOptions
0x1400582cf  mov     [rsp+38h+phkResult], rax; phkResult
0x1400582d4  mov     rdx, rdi; lpSubKey
0x1400582d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400582de  call    cs:__imp_RegOpenKeyExW
0x1400582e5  nop     dword ptr [rax+rax+00h]
0x1400582ea  mov     ebx, eax
0x1400582ec  test    eax, eax
0x1400582ee  jz      short loc_140058302
0x1400582f0  jle     short loc_1400582FB
0x1400582f2  movzx   ebx, ax
0x1400582f5  or      ebx, 80070000h
0x1400582fb  mov     rcx, [rsp+38h+lpSubKey]
0x140058300  jmp     short loc_140058310
0x140058302  mov     rax, [rsp+38h+lpSubKey]
0x140058307  xor     ebx, ebx
0x140058309  jmp     short loc_140058327
0x14005830b  mov     ebx, 80070057h
0x140058310  test    rcx, rcx
0x140058313  jz      short loc_140058321
0x140058315  call    cs:__imp_RegCloseKey
0x14005831c  nop     dword ptr [rax+rax+00h]
0x140058321  xor     eax, eax
0x140058323  test    ebx, ebx
0x140058325  js      short loc_140058331
0x140058327  mov     [rsi], rax
0x14005832a  jmp     short loc_140058331
0x14005832c  mov     ebx, 80070057h
0x140058331  test    rdi, rdi
0x140058334  jz      short loc_14005833E
0x140058336  mov     rcx, rdi; Block
0x140058339  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005833e  mov     rsi, [rsp+38h+arg_8]
0x140058343  mov     eax, ebx
0x140058345  mov     rbx, [rsp+38h+arg_0]
0x14005834a  add     rsp, 30h
0x14005834e  pop     rdi
0x14005834f  retn
```
