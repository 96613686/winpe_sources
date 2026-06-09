# DCGetReadonlyEnrollmentIdSidStateKey

- ea: `0x1400575f0`
- end: `0x1400576e9`
- name: `DCGetReadonlyEnrollmentIdSidStateKey`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x1400585f0`
- `0x140058a5c`

## callees

- `0x1400036e4`
- `0x1400575f0`
- `0x140058460`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140057676`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140057676`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400576ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400576ad`

## pseudocode

```c
__int64 __fastcall DCGetReadonlyEnrollmentIdSidStateKey(__int64 a1, __int64 a2, LPCWSTR *a3)
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
    v5 = DCStringCchPrintfAllStrings(&lpSubKey, qword_140085168, 2, a1);
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
0x1400575f0  mov     rax, rsp
0x1400575f3  mov     [rax+8], rbx
0x1400575f7  mov     [rax+10h], rsi
0x1400575fb  push    rdi
0x1400575fc  sub     rsp, 30h
0x140057600  xor     edi, edi
0x140057602  mov     rsi, r8
0x140057605  mov     [rax+18h], rdi
0x140057609  test    r8, r8
0x14005760c  jz      loc_1400576C4
0x140057612  test    rcx, rcx
0x140057615  jz      loc_1400576C4
0x14005761b  test    rdx, rdx
0x14005761e  jz      loc_1400576C4
0x140057624  mov     [r8], rdi
0x140057627  mov     r9, rcx
0x14005762a  mov     [rax-18h], rdx
0x14005762e  lea     r8d, [rdi+2]
0x140057632  mov     rdx, cs:qword_140085168
0x140057639  lea     rcx, [rax+18h]
0x14005763d  call    DCStringCchPrintfAllStrings
0x140057642  mov     rdi, [rsp+38h+lpSubKey]
0x140057647  mov     ebx, eax
0x140057649  test    eax, eax
0x14005764b  js      short loc_1400576C9
0x14005764d  xor     ecx, ecx; hKey
0x14005764f  mov     [rsp+38h+lpSubKey], rcx
0x140057654  test    rdi, rdi
0x140057657  jz      short loc_1400576A3
0x140057659  lea     rax, [rsp+38h+lpSubKey]
0x14005765e  mov     r9d, 20119h; samDesired
0x140057664  xor     r8d, r8d; ulOptions
0x140057667  mov     [rsp+38h+phkResult], rax; phkResult
0x14005766c  mov     rdx, rdi; lpSubKey
0x14005766f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140057676  call    cs:__imp_RegOpenKeyExW
0x14005767d  nop     dword ptr [rax+rax+00h]
0x140057682  mov     ebx, eax
0x140057684  test    eax, eax
0x140057686  jz      short loc_14005769A
0x140057688  jle     short loc_140057693
0x14005768a  movzx   ebx, ax
0x14005768d  or      ebx, 80070000h
0x140057693  mov     rcx, [rsp+38h+lpSubKey]
0x140057698  jmp     short loc_1400576A8
0x14005769a  mov     rax, [rsp+38h+lpSubKey]
0x14005769f  xor     ebx, ebx
0x1400576a1  jmp     short loc_1400576BF
0x1400576a3  mov     ebx, 80070057h
0x1400576a8  test    rcx, rcx
0x1400576ab  jz      short loc_1400576B9
0x1400576ad  call    cs:__imp_RegCloseKey
0x1400576b4  nop     dword ptr [rax+rax+00h]
0x1400576b9  xor     eax, eax
0x1400576bb  test    ebx, ebx
0x1400576bd  js      short loc_1400576C9
0x1400576bf  mov     [rsi], rax
0x1400576c2  jmp     short loc_1400576C9
0x1400576c4  mov     ebx, 80070057h
0x1400576c9  test    rdi, rdi
0x1400576cc  jz      short loc_1400576D6
0x1400576ce  mov     rcx, rdi; Block
0x1400576d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400576d6  mov     rsi, [rsp+38h+arg_8]
0x1400576db  mov     eax, ebx
0x1400576dd  mov     rbx, [rsp+38h+arg_0]
0x1400576e2  add     rsp, 30h
0x1400576e6  pop     rdi
0x1400576e7  retn
```
