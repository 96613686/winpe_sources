# Registry::readMultipleSettings(Registry::ReadSettings const *)

- ea: `0x180076cdc`
- end: `0x180076e13`
- name: `?readMultipleSettings@Registry@@SAXPEBUReadSettings@1@@Z`
- size: `311`
- prototype: `void __fastcall(const Registry::ReadSettings *pSettings)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180020de0`
- `0x1800769ec`
- `0x180076a6c`
- `0x1800bde70`
- `0x1801253e0`

## callees

- `0x180076cdc`
- `0x1800966bc`
- `0x1800d96b0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076da6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076db7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076da6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076db7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076d7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076d7c`

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
0x180076cdc  push    rbx
0x180076cde  push    rbp
0x180076cdf  push    rsi
0x180076ce0  push    rdi
0x180076ce1  push    r14
0x180076ce3  sub     rsp, 30h
0x180076ce7  xor     ebx, ebx
0x180076ce9  xor     ebp, ebp
0x180076ceb  xor     sil, sil
0x180076cee  mov     [rsp+58h+rk._hKey], rbx
0x180076cf3  xor     r14d, r14d
0x180076cf6  mov     [rsp+58h+dwValue], ebx
0x180076cfa  mov     rdi, pSettings
0x180076cfd  cmp     [pSettings+8], rbx
0x180076d01  jz      short loc_180076D42
0x180076d03  cmp     r14, [rdi+8]
0x180076d07  jnz     short loc_180076D4E
0x180076d09  cmp     rbp, [rdi]
0x180076d0c  jnz     short loc_180076D4E
0x180076d0e  cmp     dword ptr [rdi+18h], 4
0x180076d12  jnz     short loc_180076D32
0x180076d14  xor     al, al
0x180076d16  test    sil, sil
0x180076d19  jnz     loc_180076DE2
0x180076d1f  xor     r8d, r8d
0x180076d22  mov     edx, [rsp+58h+dwValue]
0x180076d26  mov     ecx, [rdi+1Ch]
0x180076d29  mov     rax, [rdi+20h]
0x180076d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d32  add     rdi, 28h ; '('
0x180076d36  cmp     qword ptr [rdi+8], 0
0x180076d3b  jnz     short loc_180076D03
0x180076d3d  test    rbx, rbx
0x180076d40  jnz     short loc_180076DA3
0x180076d42  add     rsp, 30h
0x180076d46  pop     r14
0x180076d48  pop     rdi
0x180076d49  pop     rsi
0x180076d4a  pop     rbp
0x180076d4b  pop     rbx
0x180076d4c  retn
0x180076d4e  mov     rbp, [rdi]
0x180076d51  test    rbx, rbx
0x180076d54  jnz     short loc_180076DB4
0x180076d56  mov     r14, [rdi+8]
0x180076d5a  lea     rax, [rsp+58h+arg_10]
0x180076d5f  mov     pSettings, [rdi]; hKey
0x180076d62  mov     rdx, r14; lpSubKey
0x180076d65  mov     r9d, 1; samDesired
0x180076d6b  mov     [rsp+58h+arg_10], 0
0x180076d74  xor     r8d, r8d; ulOptions
0x180076d77  mov     [rsp+58h+phkResult], rax; phkResult
0x180076d7c  call    cs:__imp_RegOpenKeyExW
0x180076d83  nop     dword ptr [rax+rax+00h]
0x180076d88  test    eax, eax
0x180076d8a  jle     short loc_180076D96
0x180076d8c  movzx   eax, ax
0x180076d8f  or      eax, 80070000h
0x180076d94  test    eax, eax
0x180076d96  jz      short loc_180076DCC
0x180076d98  test    eax, eax
0x180076d9a  setns   sil
0x180076d9e  jmp     loc_180076D0E
0x180076da3  mov     pSettings, rbx; hKey
0x180076da6  call    cs:__imp_RegCloseKey
0x180076dad  nop     dword ptr [rax+rax+00h]
0x180076db2  jmp     short loc_180076D42
0x180076db4  mov     pSettings, rbx; hKey
0x180076db7  call    cs:__imp_RegCloseKey
0x180076dbe  nop     dword ptr [rax+rax+00h]
0x180076dc3  xor     ebx, ebx
0x180076dc5  mov     [rsp+58h+rk._hKey], rbx
0x180076dca  jmp     short loc_180076D56
0x180076dcc  lea     pSettings, [rsp+58h+rk]; this
0x180076dd1  call    ?Close@CRegKey@@QEAAJXZ; CRegKey::Close(void)
0x180076dd6  mov     rbx, [rsp+58h+arg_10]
0x180076ddb  mov     [rsp+58h+rk._hKey], rbx
0x180076de0  jmp     short loc_180076D98
0x180076de2  mov     r8, [rdi+10h]; lpszValueName
0x180076de6  lea     rdx, [rsp+58h+dwValue]; dwValue
0x180076deb  lea     pSettings, [rsp+58h+rk]; this
0x180076df0  call    ?QueryValue@CRegKey@@QEAAJAEAKPEBG@Z; CRegKey::QueryValue(ulong &,ushort const *)
0x180076df5  test    eax, eax
0x180076df7  setns   al
0x180076dfa  test    sil, sil
0x180076dfd  jz      loc_180076D1F
0x180076e03  test    al, al
0x180076e05  jz      loc_180076D1F
0x180076e0b  mov     r8b, 1
0x180076e0e  jmp     loc_180076D22
```
