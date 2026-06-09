# Registry::readMultipleSettings(Registry::ReadSettings const *)

- ea: `0x18007797c`
- end: `0x180077aa0`
- name: `?readMultipleSettings@Registry@@SAXPEBUReadSettings@1@@Z`
- size: `292`
- prototype: `void __fastcall(const Registry::ReadSettings *pSettings)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180014550`
- `0x1800776b0`
- `0x18007772c`
- `0x1800bc810`
- `0x180122860`

## callees

- `0x18007797c`
- `0x180096274`
- `0x1800d797c`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077a3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077a4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077a3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077a4a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077a1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077a1b`

## pseudocode

```c
void __fastcall Registry::readMultipleSettings(const Registry::ReadSettings *pSettings)
{
  HKEY__ *v1; // rbx
  HKEY__ *hKey; // rbp
  bool v3; // si
  const wchar_t *pwszKeyName; // r14
  const Registry::ReadSettings *v5; // rdi
  _BOOL8 v6; // r8
  HKEY v7; // rcx
  int v8; // eax
  bool v9; // zf
  unsigned int dwValue; // [rsp+60h] [rbp+8h] BYREF
  CRegKey rk; // [rsp+68h] [rbp+10h] BYREF
  HKEY__ *phkResult; // [rsp+70h] [rbp+18h] BYREF

  v1 = 0;
  hKey = 0;
  v3 = 0;
  rk._hKey = 0;
  pwszKeyName = 0;
  dwValue = 0;
  v5 = pSettings;
  if ( pSettings->_pwszKeyName )
  {
    do
    {
      if ( pwszKeyName != v5->_pwszKeyName || hKey != v5->_hKey )
      {
        hKey = v5->_hKey;
        if ( v1 )
        {
          RegCloseKey(v1);
          v1 = 0;
          rk._hKey = 0;
        }
        pwszKeyName = v5->_pwszKeyName;
        v7 = v5->_hKey;
        phkResult = 0;
        v8 = RegOpenKeyExW(v7, pwszKeyName, 0, 1u, &phkResult);
        v9 = v8 == 0;
        if ( v8 > 0 )
        {
          v8 = (unsigned __int16)v8 | 0x80070000;
          v9 = v8 == 0;
        }
        if ( v9 )
        {
          v8 = CRegKey::Close(&rk);
          v1 = phkResult;
          rk._hKey = phkResult;
        }
        v3 = v8 >= 0;
      }
      if ( v5->_dwValueType == 4 )
      {
        if ( v3 && CRegKey::QueryValue(&rk, &dwValue, v5->_pwszValueName) >= 0 )
          LOBYTE(v6) = 1;
        else
          v6 = 0;
        v5->_pDWORDFunc(v5->_dwID, dwValue, v6);
      }
      ++v5;
    }
    while ( v5->_pwszKeyName );
    if ( v1 )
      RegCloseKey(v1);
  }
}

```

## disassembly

```asm
0x18007797c  push    rbx
0x18007797e  push    rbp
0x18007797f  push    rsi
0x180077980  push    rdi
0x180077981  push    r14
0x180077983  sub     rsp, 30h
0x180077987  xor     ebx, ebx
0x180077989  xor     ebp, ebp
0x18007798b  xor     sil, sil
0x18007798e  mov     [rsp+58h+rk._hKey], rbx
0x180077993  xor     r14d, r14d
0x180077996  mov     [rsp+58h+dwValue], ebx
0x18007799a  mov     rdi, pSettings
0x18007799d  cmp     [pSettings+8], rbx
0x1800779a1  jz      short loc_1800779E2
0x1800779a3  cmp     r14, [rdi+8]
0x1800779a7  jnz     short loc_1800779ED
0x1800779a9  cmp     rbp, [rdi]
0x1800779ac  jnz     short loc_1800779ED
0x1800779ae  cmp     dword ptr [rdi+18h], 4
0x1800779b2  jnz     short loc_1800779D2
0x1800779b4  xor     al, al
0x1800779b6  test    sil, sil
0x1800779b9  jnz     loc_180077A6F
0x1800779bf  xor     r8d, r8d
0x1800779c2  mov     edx, [rsp+58h+dwValue]
0x1800779c6  mov     ecx, [rdi+1Ch]
0x1800779c9  mov     rax, [rdi+20h]
0x1800779cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800779d2  add     rdi, 28h ; '('
0x1800779d6  cmp     qword ptr [rdi+8], 0
0x1800779db  jnz     short loc_1800779A3
0x1800779dd  test    rbx, rbx
0x1800779e0  jnz     short loc_180077A3C
0x1800779e2  add     rsp, 30h
0x1800779e6  pop     r14
0x1800779e8  pop     rdi
0x1800779e9  pop     rsi
0x1800779ea  pop     rbp
0x1800779eb  pop     rbx
0x1800779ec  retn
0x1800779ed  mov     rbp, [rdi]
0x1800779f0  test    rbx, rbx
0x1800779f3  jnz     short loc_180077A47
0x1800779f5  mov     r14, [rdi+8]
0x1800779f9  lea     rax, [rsp+58h+arg_10]
0x1800779fe  mov     pSettings, [rdi]; hKey
0x180077a01  mov     rdx, r14; lpSubKey
0x180077a04  mov     r9d, 1; samDesired
0x180077a0a  mov     [rsp+58h+arg_10], 0
0x180077a13  xor     r8d, r8d; ulOptions
0x180077a16  mov     [rsp+58h+phkResult], rax; phkResult
0x180077a1b  call    cs:__imp_RegOpenKeyExW
0x180077a21  test    eax, eax
0x180077a23  jle     short loc_180077A2F
0x180077a25  movzx   eax, ax
0x180077a28  or      eax, 80070000h
0x180077a2d  test    eax, eax
0x180077a2f  jz      short loc_180077A59
0x180077a31  test    eax, eax
0x180077a33  setns   sil
0x180077a37  jmp     loc_1800779AE
0x180077a3c  mov     pSettings, rbx; hKey
0x180077a3f  call    cs:__imp_RegCloseKey
0x180077a45  jmp     short loc_1800779E2
0x180077a47  mov     pSettings, rbx; hKey
0x180077a4a  call    cs:__imp_RegCloseKey
0x180077a50  xor     ebx, ebx
0x180077a52  mov     [rsp+58h+rk._hKey], rbx
0x180077a57  jmp     short loc_1800779F5
0x180077a59  lea     pSettings, [rsp+58h+rk]; this
0x180077a5e  call    ?Close@CRegKey@@QEAAJXZ; CRegKey::Close(void)
0x180077a63  mov     rbx, [rsp+58h+arg_10]
0x180077a68  mov     [rsp+58h+rk._hKey], rbx
0x180077a6d  jmp     short loc_180077A31
0x180077a6f  mov     r8, [rdi+10h]; lpszValueName
0x180077a73  lea     rdx, [rsp+58h+dwValue]; dwValue
0x180077a78  lea     pSettings, [rsp+58h+rk]; this
0x180077a7d  call    ?QueryValue@CRegKey@@QEAAJAEAKPEBG@Z; CRegKey::QueryValue(ulong &,ushort const *)
0x180077a82  test    eax, eax
0x180077a84  setns   al
0x180077a87  test    sil, sil
0x180077a8a  jz      loc_1800779BF
0x180077a90  test    al, al
0x180077a92  jz      loc_1800779BF
0x180077a98  mov     r8b, 1
0x180077a9b  jmp     loc_1800779C2
```
