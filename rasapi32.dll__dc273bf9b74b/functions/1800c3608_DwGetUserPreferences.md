# DwGetUserPreferences

- ea: `0x1800c3608`
- end: `0x1800c373e`
- name: `DwGetUserPreferences`
- size: `310`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000975c`
- `0x1800c5c58`
- `0x1800cbc04`

## callees

- `0x18003ff38`
- `0x1800c3608`
- `0x1800c3bf4`
- `0x1800c3d0c`
- `0x1800c3e70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c36b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c36b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c36e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c36e4`
- `rtutils!TracePrintfExA` at `0x1800c3636`
- `rtutils!TracePrintfExA` at `0x1800c3706`
- `rtutils!TracePrintfExA` at `0x1800c3726`
- `rtutils!TracePrintfExA` at `0x1800c3636`
- `rtutils!TracePrintfExA` at `0x1800c3706`
- `rtutils!TracePrintfExA` at `0x1800c3726`

## string_xrefs

- `0x1800c36fa`: `RegOpenKeyEx=%d`

## pseudocode

```c
__int64 __fastcall DwGetUserPreferences(void *a1, int a2)
{
  unsigned int v4; // edi
  const WCHAR *v5; // rdx
  __int64 v6; // rcx
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GetUserPreferences(m=%d)", a2);
  if ( a2 )
  {
    if ( a2 == 1 )
      MoveLogonPreferences();
  }
  else
  {
    MoveUserPreferences();
  }
  v4 = SetDefaultUserPreferences(a1);
  if ( !v4 )
  {
    hKey = 0;
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
    v7 = RegOpenKeyExW((HKEY)v6, v5, 0, 0x20019u, &hKey);
    if ( v7 )
    {
      if ( g_dwTraceId == -1 )
        return v4;
      TracePrintfExA(g_dwTraceId, 0xCu, "RegOpenKeyEx=%d", v7);
    }
    else
    {
      if ( (unsigned int)ReadUserPreferences(hKey, (char *)a1) )
        v4 = SetDefaultUserPreferences(a1);
      RegCloseKey(hKey);
    }
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GetUserPreferences=%d", v4);
  return v4;
}

```

## disassembly

```asm
0x1800c3608  mov     [rsp+arg_0], rbx
0x1800c360d  mov     [rsp+arg_8], rsi
0x1800c3612  push    rdi
0x1800c3613  sub     rsp, 30h
0x1800c3617  mov     rsi, rcx
0x1800c361a  mov     ebx, edx
0x1800c361c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c3622  cmp     ecx, 0FFFFFFFFh
0x1800c3625  jz      short loc_1800C363C
0x1800c3627  mov     r9d, edx
0x1800c362a  lea     r8, aGetuserprefere; "GetUserPreferences(m=%d)"
0x1800c3631  mov     edx, 0Ch; dwFlags
0x1800c3636  call    cs:__imp_TracePrintfExA
0x1800c363c  test    ebx, ebx
0x1800c363e  jnz     short loc_1800C3647
0x1800c3640  call    MoveUserPreferences
0x1800c3645  jmp     short loc_1800C3651
0x1800c3647  cmp     ebx, 1
0x1800c364a  jnz     short loc_1800C3651
0x1800c364c  call    MoveLogonPreferences
0x1800c3651  mov     edx, ebx
0x1800c3653  mov     rcx, rsi; void *
0x1800c3656  call    SetDefaultUserPreferences
0x1800c365b  mov     edi, eax
0x1800c365d  test    eax, eax
0x1800c365f  jnz     loc_1800C370C
0x1800c3665  mov     [rsp+38h+hKey], 0
0x1800c366e  test    ebx, ebx
0x1800c3670  jnz     short loc_1800C3682
0x1800c3672  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\RAS Phonebook"
0x1800c3679  mov     rcx, 0FFFFFFFF80000001h
0x1800c3680  jmp     short loc_1800C36A5
0x1800c3682  cmp     ebx, 1
0x1800c3685  jnz     short loc_1800C3697
0x1800c3687  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x1800c368e  mov     rcx, 0FFFFFFFF80000003h
0x1800c3695  jmp     short loc_1800C36A5
0x1800c3697  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Router Phonebook"
0x1800c369e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c36a5  lea     rax, [rsp+38h+hKey]
0x1800c36aa  mov     r9d, 20019h; samDesired
0x1800c36b0  xor     r8d, r8d; ulOptions
0x1800c36b3  mov     [rsp+38h+phkResult], rax; phkResult
0x1800c36b8  call    cs:__imp_RegOpenKeyExW
0x1800c36be  test    eax, eax
0x1800c36c0  jnz     short loc_1800C36EC
0x1800c36c2  mov     rcx, [rsp+38h+hKey]; hKey
0x1800c36c7  mov     rdx, rsi; void *
0x1800c36ca  call    ReadUserPreferences
0x1800c36cf  test    eax, eax
0x1800c36d1  jz      short loc_1800C36DF
0x1800c36d3  mov     edx, ebx
0x1800c36d5  mov     rcx, rsi; void *
0x1800c36d8  call    SetDefaultUserPreferences
0x1800c36dd  mov     edi, eax
0x1800c36df  mov     rcx, [rsp+38h+hKey]; hKey
0x1800c36e4  call    cs:__imp_RegCloseKey
0x1800c36ea  jmp     short loc_1800C370C
0x1800c36ec  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c36f2  cmp     ecx, 0FFFFFFFFh
0x1800c36f5  jz      short loc_1800C372C
0x1800c36f7  mov     r9d, eax
0x1800c36fa  lea     r8, aRegopenkeyexD; "RegOpenKeyEx=%d"
0x1800c3701  mov     edx, 0Ch; dwFlags
0x1800c3706  call    cs:__imp_TracePrintfExA
0x1800c370c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c3712  cmp     ecx, 0FFFFFFFFh
0x1800c3715  jz      short loc_1800C372C
0x1800c3717  mov     r9d, edi
0x1800c371a  lea     r8, aGetuserprefere_0; "GetUserPreferences=%d"
0x1800c3721  mov     edx, 0Ch; dwFlags
0x1800c3726  call    cs:__imp_TracePrintfExA
0x1800c372c  mov     rbx, [rsp+38h+arg_0]
0x1800c3731  mov     eax, edi
0x1800c3733  mov     rsi, [rsp+38h+arg_8]
0x1800c3738  add     rsp, 30h
0x1800c373c  pop     rdi
0x1800c373d  retn
```
