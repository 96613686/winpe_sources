# RegGetCheckStatus(int *,HKEY__ *,ushort const *,ushort const *,int)

- ea: `0x18003c0c4`
- end: `0x18003c1ca`
- name: `?RegGetCheckStatus@@YAKPEAHPEAUHKEY__@@PEBG2H@Z`
- size: `262`
- prototype: `unsigned int(int *, HKEY, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003d2d0`

## callees

- `0x18003c0c4`
- `0x18003e5c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003c188`
- `msvcrt!_wcsicmp` at `0x18003c188`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003c144`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003c144`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c106`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c106`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c19f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c19f`

## pseudocode

```c
__int64 __fastcall RegGetCheckStatus(int *a1, HKEY a2, const unsigned __int16 *a3, const unsigned __int16 *a4)
{
  int v5; // edi
  unsigned int v6; // ebx
  DWORD cbData; // [rsp+30h] [rbp-40h] BYREF
  DWORD Type; // [rsp+34h] [rbp-3Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  wchar_t Data[16]; // [rsp+40h] [rbp-30h] BYREF

  v5 = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(a2, a3, 0, 1u, &hKey);
  if ( !v6 )
  {
    Type = 0;
    cbData = 32;
    v6 = RegQueryValueExW(hKey, L"RunInvalidSignatures", 0, &Type, (LPBYTE)Data, &cbData);
    if ( !v6 )
    {
      if ( Type == 1 )
      {
        if ( cbData && !*((_BYTE *)&hKey + ((unsigned __int64)cbData >> 1) + 7) )
        {
          LOBYTE(v5) = _wcsicmp(L"yes", Data) == 0;
          goto LABEL_11;
        }
      }
      else if ( Type == 4 && cbData == 4 )
      {
        LOBYTE(v5) = *(_DWORD *)Data != 0;
        goto LABEL_11;
      }
      v6 = 11;
    }
LABEL_11:
    RegCloseKey(hKey);
  }
  if ( a1 )
    *a1 = v5;
  return v6;
}

```

## disassembly

```asm
0x18003c0c4  mov     [rsp-18h+arg_18], rbx
0x18003c0c9  push    rbp
0x18003c0ca  push    rsi
0x18003c0cb  push    rdi
0x18003c0cc  mov     rbp, rsp
0x18003c0cf  sub     rsp, 70h
0x18003c0d3  mov     rax, cs:__security_cookie
0x18003c0da  xor     rax, rsp
0x18003c0dd  mov     [rbp+var_10], rax
0x18003c0e1  mov     rsi, rcx
0x18003c0e4  mov     r10, r8
0x18003c0e7  mov     rax, rdx
0x18003c0ea  lea     rcx, [rbp+hKey]
0x18003c0ee  xor     edi, edi
0x18003c0f0  mov     [rsp+70h+phkResult], rcx; phkResult
0x18003c0f5  xor     r8d, r8d; ulOptions
0x18003c0f8  mov     [rbp+hKey], rdi
0x18003c0fc  mov     rdx, r10; lpSubKey
0x18003c0ff  mov     rcx, rax; hKey
0x18003c102  lea     r9d, [rdi+1]; samDesired
0x18003c106  call    cs:__imp_RegOpenKeyExW
0x18003c10c  mov     ebx, eax
0x18003c10e  test    eax, eax
0x18003c110  jnz     loc_18003C1A5
0x18003c116  mov     rcx, [rbp+hKey]; hKey
0x18003c11a  lea     rax, [rbp+cbData]
0x18003c11e  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18003c123  lea     r9, [rbp+Type]; lpType
0x18003c127  lea     rax, [rbp+Data]
0x18003c12b  mov     [rbp+Type], edi
0x18003c12e  xor     r8d, r8d; lpReserved
0x18003c131  mov     [rsp+70h+phkResult], rax; lpData
0x18003c136  lea     rdx, aRuninvalidsign; "RunInvalidSignatures"
0x18003c13d  mov     [rbp+cbData], 20h ; ' '
0x18003c144  call    cs:__imp_RegQueryValueExW
0x18003c14a  mov     ebx, eax
0x18003c14c  test    eax, eax
0x18003c14e  jnz     short loc_18003C19B
0x18003c150  mov     eax, [rbp+Type]
0x18003c153  sub     eax, 1
0x18003c156  jz      short loc_18003C16C
0x18003c158  cmp     eax, 3
0x18003c15b  jnz     short loc_18003C196
0x18003c15d  cmp     [rbp+cbData], 4
0x18003c161  jnz     short loc_18003C196
0x18003c163  cmp     dword ptr [rbp+Data], edi
0x18003c166  setnz   dil
0x18003c16a  jmp     short loc_18003C19B
0x18003c16c  mov     eax, [rbp+cbData]
0x18003c16f  test    eax, eax
0x18003c171  jz      short loc_18003C196
0x18003c173  shr     rax, 1
0x18003c176  cmp     byte ptr [rbp+rax+hKey+7], dil
0x18003c17b  jnz     short loc_18003C196
0x18003c17d  lea     rdx, [rbp+Data]; String2
0x18003c181  lea     rcx, aYes; "yes"
0x18003c188  call    cs:__imp__wcsicmp
0x18003c18e  test    eax, eax
0x18003c190  setz    dil
0x18003c194  jmp     short loc_18003C19B
0x18003c196  mov     ebx, 0Bh
0x18003c19b  mov     rcx, [rbp+hKey]; hKey
0x18003c19f  call    cs:__imp_RegCloseKey
0x18003c1a5  test    rsi, rsi
0x18003c1a8  jz      short loc_18003C1AC
0x18003c1aa  mov     [rsi], edi
0x18003c1ac  mov     eax, ebx
0x18003c1ae  mov     rcx, [rbp+var_10]
0x18003c1b2  xor     rcx, rsp; StackCookie
0x18003c1b5  call    __security_check_cookie
0x18003c1ba  mov     rbx, [rsp+70h+arg_18]
0x18003c1c2  add     rsp, 70h
0x18003c1c6  pop     rdi
0x18003c1c7  pop     rsi
0x18003c1c8  pop     rbp
0x18003c1c9  retn
```
