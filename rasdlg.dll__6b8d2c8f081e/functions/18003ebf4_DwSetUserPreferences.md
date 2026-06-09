# DwSetUserPreferences

- ea: `0x18003ebf4`
- end: `0x18003ed12`
- name: `DwSetUserPreferences`
- size: `286`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003f18c`
- `0x18003f2a4`
- `0x180045270`

## callees

- `0x18003ebf4`
- `0x18003ff50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ecbf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ecbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ecdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ecdf`
- `rtutils!TracePrintfExA` at `0x18003ec2e`
- `rtutils!TracePrintfExA` at `0x18003ecff`
- `rtutils!TracePrintfExA` at `0x18003ec2e`
- `rtutils!TracePrintfExA` at `0x18003ecff`

## pseudocode

```c
__int64 __fastcall DwSetUserPreferences(__int64 a1, int a2)
{
  const WCHAR *v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  dwDisposition = 0;
  hKey = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DwSetUserPreferences(m=%d)", a2);
  if ( !a1 )
    return 87;
  if ( !*(_DWORD *)(a1 + 180) )
    return 0;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v5 = L".DEFAULT\\Software\\Microsoft\\RAS Logon Phonebook";
      v6 = -2147483645;
    }
    else
    {
      v5 = L"Software\\Microsoft\\Router Phonebook";
      v6 = -2147483646;
    }
  }
  else
  {
    v5 = L"Software\\Microsoft\\RAS Phonebook";
    v6 = -2147483647;
  }
  v7 = RegCreateKeyExW((HKEY)v6, v5, 0, (LPWSTR)&WideCharStr, 0, 0x2000Eu, 0, &hKey, &dwDisposition);
  if ( !v7 )
  {
    v7 = WriteUserPreferences(hKey);
    RegCloseKey(hKey);
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DwSetUserPreferences=%d", v7);
  return v7;
}

```

## disassembly

```asm
0x18003ebf4  mov     [rsp+arg_8], rbx
0x18003ebf9  push    rdi
0x18003ebfa  sub     rsp, 50h
0x18003ebfe  mov     rdi, rcx
0x18003ec01  mov     [rsp+58h+dwDisposition], 0
0x18003ec09  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003ec0f  mov     ebx, edx
0x18003ec11  mov     [rsp+58h+hKey], 0
0x18003ec1a  cmp     ecx, 0FFFFFFFFh
0x18003ec1d  jz      short loc_18003EC34
0x18003ec1f  mov     r9d, edx
0x18003ec22  lea     r8, aDwsetuserprefe_0; "DwSetUserPreferences(m=%d)"
0x18003ec29  mov     edx, 0Ch; dwFlags
0x18003ec2e  call    cs:__imp_TracePrintfExA
0x18003ec34  test    rdi, rdi
0x18003ec37  jnz     short loc_18003EC41
0x18003ec39  lea     eax, [rdi+57h]
0x18003ec3c  jmp     loc_18003ED07
0x18003ec41  cmp     dword ptr [rdi+0B4h], 0
0x18003ec48  jnz     short loc_18003EC51
0x18003ec4a  xor     eax, eax
0x18003ec4c  jmp     loc_18003ED07
0x18003ec51  test    ebx, ebx
0x18003ec53  jnz     short loc_18003EC65
0x18003ec55  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\RAS Phonebook"
0x18003ec5c  mov     rcx, 0FFFFFFFF80000001h
0x18003ec63  jmp     short loc_18003EC88
0x18003ec65  cmp     ebx, 1
0x18003ec68  jnz     short loc_18003EC7A
0x18003ec6a  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x18003ec71  mov     rcx, 0FFFFFFFF80000003h
0x18003ec78  jmp     short loc_18003EC88
0x18003ec7a  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Router Phonebook"
0x18003ec81  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ec88  lea     rax, [rsp+58h+dwDisposition]
0x18003ec8d  xor     r8d, r8d; Reserved
0x18003ec90  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18003ec95  lea     r9, WideCharStr; lpClass
0x18003ec9c  lea     rax, [rsp+58h+hKey]
0x18003eca1  mov     [rsp+58h+phkResult], rax; phkResult
0x18003eca6  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003ecaf  mov     [rsp+58h+samDesired], 2000Eh; samDesired
0x18003ecb7  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18003ecbf  call    cs:__imp_RegCreateKeyExW
0x18003ecc5  mov     ebx, eax
0x18003ecc7  test    eax, eax
0x18003ecc9  jnz     short loc_18003ECE5
0x18003eccb  mov     rcx, [rsp+58h+hKey]; hKey
0x18003ecd0  mov     rdx, rdi
0x18003ecd3  call    WriteUserPreferences
0x18003ecd8  mov     rcx, [rsp+58h+hKey]; hKey
0x18003ecdd  mov     ebx, eax
0x18003ecdf  call    cs:__imp_RegCloseKey
0x18003ece5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003eceb  cmp     ecx, 0FFFFFFFFh
0x18003ecee  jz      short loc_18003ED05
0x18003ecf0  mov     r9d, ebx
0x18003ecf3  lea     r8, aDwsetuserprefe; "DwSetUserPreferences=%d"
0x18003ecfa  mov     edx, 0Ch; dwFlags
0x18003ecff  call    cs:__imp_TracePrintfExA
0x18003ed05  mov     eax, ebx
0x18003ed07  mov     rbx, [rsp+58h+arg_8]
0x18003ed0c  add     rsp, 50h
0x18003ed10  pop     rdi
0x18003ed11  retn
```
