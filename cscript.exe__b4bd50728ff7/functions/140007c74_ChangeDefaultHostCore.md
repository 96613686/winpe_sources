# ChangeDefaultHostCore

- ea: `0x140007c74`
- end: `0x140007d26`
- name: `ChangeDefaultHostCore`
- size: `178`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140007010`

## callees

- `0x140007c74`
- `0x14000d9ac`
- `0x14000da0c`
- `0x14000dab0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x140007cae`
- `ADVAPI32!RegOpenKeyExA` at `0x140007cae`
- `ADVAPI32!RegCloseKey` at `0x140007cfe`
- `ADVAPI32!RegCloseKey` at `0x140007cfe`

## pseudocode

```c
__int64 __fastcall ChangeDefaultHostCore(LPCSTR lpSubKey, const BYTE *a2, int a3)
{
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  __int64 v8; // r8
  int v9; // eax
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  v6 = 0;
  v7 = RegOpenKeyExA(HKEY_CLASSES_ROOT, lpSubKey, 0, 0x2001Fu, &hKey);
  if ( v7 )
  {
    if ( !a3 )
    {
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
      else
        return (unsigned int)v7;
    }
  }
  else
  {
    if ( !a3 || (int)RegIsKey(hKey) >= 0 )
    {
      v9 = RegSetKeyString(hKey, "Shell", v8, a2);
      v6 = v9;
      if ( v9 < 0 && (_WORD)v9 == 5 )
        v6 = SetDefaultHostForUser(lpSubKey, a2);
    }
    RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x140007c74  push    rbx
0x140007c76  push    rbp
0x140007c77  push    rsi
0x140007c78  push    rdi
0x140007c79  sub     rsp, 38h
0x140007c7d  mov     rsi, rdx
0x140007c80  mov     [rsp+58h+hKey], 0
0x140007c89  mov     rdx, rcx; lpSubKey
0x140007c8c  lea     rax, [rsp+58h+hKey]
0x140007c91  mov     edi, r8d
0x140007c94  mov     [rsp+58h+phkResult], rax; phkResult
0x140007c99  mov     rbp, rcx
0x140007c9c  mov     r9d, 2001Fh; samDesired
0x140007ca2  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140007ca9  xor     r8d, r8d; ulOptions
0x140007cac  xor     ebx, ebx
0x140007cae  call    cs:__imp_RegOpenKeyExA
0x140007cb4  test    eax, eax
0x140007cb6  jnz     short loc_140007D06
0x140007cb8  test    edi, edi
0x140007cba  jz      short loc_140007CCC
0x140007cbc  mov     rcx, [rsp+58h+hKey]
0x140007cc1  call    RegIsKey
0x140007cc6  not     eax
0x140007cc8  test    eax, eax
0x140007cca  jns     short loc_140007CF9
0x140007ccc  mov     rcx, [rsp+58h+hKey]
0x140007cd1  lea     rdx, aShell; "Shell"
0x140007cd8  mov     r9, rsi
0x140007cdb  call    RegSetKeyString
0x140007ce0  mov     ebx, eax
0x140007ce2  test    eax, eax
0x140007ce4  jns     short loc_140007CF9
0x140007ce6  cmp     ax, 5
0x140007cea  jnz     short loc_140007CF9
0x140007cec  mov     rdx, rsi
0x140007cef  mov     rcx, rbp
0x140007cf2  call    SetDefaultHostForUser
0x140007cf7  mov     ebx, eax
0x140007cf9  mov     rcx, [rsp+58h+hKey]; hKey
0x140007cfe  call    cs:__imp_RegCloseKey
0x140007d04  jmp     short loc_140007D1B
0x140007d06  test    edi, edi
0x140007d08  jnz     short loc_140007D1B
0x140007d0a  test    eax, eax
0x140007d0c  jg      short loc_140007D12
0x140007d0e  mov     ebx, eax
0x140007d10  jmp     short loc_140007D1B
0x140007d12  movzx   ebx, ax
0x140007d15  or      ebx, 80070000h
0x140007d1b  mov     eax, ebx
0x140007d1d  add     rsp, 38h
0x140007d21  pop     rdi
0x140007d22  pop     rsi
0x140007d23  pop     rbp
0x140007d24  pop     rbx
0x140007d25  retn
```
