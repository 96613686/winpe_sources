# DwGetUserPreferences

- ea: `0x180009368`
- end: `0x18000945b`
- name: `DwGetUserPreferences`
- size: `243`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005d70`

## callees

- `0x180009368`
- `0x180009918`
- `0x180009a30`
- `0x18000a0c4`

## import_xrefs

- `KERNEL32!RegCloseKey` at `0x180009406`
- `KERNEL32!RegCloseKey` at `0x180009406`
- `KERNEL32!RegOpenKeyExW` at `0x1800093d9`
- `KERNEL32!RegOpenKeyExW` at `0x1800093d9`
- `rtutils!TracePrintfExA` at `0x180009391`
- `rtutils!TracePrintfExA` at `0x180009428`
- `rtutils!TracePrintfExA` at `0x180009448`
- `rtutils!TracePrintfExA` at `0x180009391`
- `rtutils!TracePrintfExA` at `0x180009428`
- `rtutils!TracePrintfExA` at `0x180009448`

## string_xrefs

- `0x18000941c`: `RegOpenKeyEx=%d`

## pseudocode

```c
__int64 __fastcall DwGetUserPreferences(void *a1)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GetUserPreferences(m=%d)", 1);
  MoveLogonPreferences();
  v2 = SetDefaultUserPreferences(a1);
  if ( !v2 )
  {
    hKey = 0;
    v3 = RegOpenKeyExW(HKEY_USERS, L".DEFAULT\\Software\\Microsoft\\RAS Logon Phonebook", 0, 0x20019u, &hKey);
    if ( v3 )
    {
      if ( g_dwTraceId == -1 )
        return v2;
      TracePrintfExA(g_dwTraceId, 0xCu, "RegOpenKeyEx=%d", v3);
    }
    else
    {
      if ( (unsigned int)ReadUserPreferences(hKey, (char *)a1) )
        v2 = SetDefaultUserPreferences(a1);
      RegCloseKey(hKey);
    }
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GetUserPreferences=%d", v2);
  return v2;
}

```

## disassembly

```asm
0x180009368  mov     [rsp+arg_0], rbx
0x18000936d  push    rdi
0x18000936e  sub     rsp, 30h
0x180009372  mov     rdi, rcx
0x180009375  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000937b  cmp     ecx, 0FFFFFFFFh
0x18000937e  jz      short loc_180009397
0x180009380  mov     r9d, 1
0x180009386  lea     r8, aGetuserprefere; "GetUserPreferences(m=%d)"
0x18000938d  lea     edx, [r9+0Bh]; dwFlags
0x180009391  call    cs:__imp_TracePrintfExA
0x180009397  call    MoveLogonPreferences
0x18000939c  mov     edx, 1
0x1800093a1  mov     rcx, rdi; void *
0x1800093a4  call    SetDefaultUserPreferences
0x1800093a9  mov     ebx, eax
0x1800093ab  test    eax, eax
0x1800093ad  jnz     short loc_18000942E
0x1800093af  lea     rax, [rsp+38h+hKey]
0x1800093b4  mov     [rsp+38h+hKey], 0
0x1800093bd  mov     r9d, 20019h; samDesired
0x1800093c3  mov     [rsp+38h+phkResult], rax; phkResult
0x1800093c8  xor     r8d, r8d; ulOptions
0x1800093cb  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x1800093d2  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800093d9  call    cs:__imp_RegOpenKeyExW
0x1800093df  test    eax, eax
0x1800093e1  jnz     short loc_18000940E
0x1800093e3  mov     rcx, [rsp+38h+hKey]; hKey
0x1800093e8  mov     rdx, rdi; void *
0x1800093eb  call    ReadUserPreferences
0x1800093f0  test    eax, eax
0x1800093f2  jz      short loc_180009401
0x1800093f4  lea     edx, [rbx+1]
0x1800093f7  mov     rcx, rdi; void *
0x1800093fa  call    SetDefaultUserPreferences
0x1800093ff  mov     ebx, eax
0x180009401  mov     rcx, [rsp+38h+hKey]; hKey
0x180009406  call    cs:__imp_RegCloseKey
0x18000940c  jmp     short loc_18000942E
0x18000940e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180009414  cmp     ecx, 0FFFFFFFFh
0x180009417  jz      short loc_18000944E
0x180009419  mov     r9d, eax
0x18000941c  lea     r8, aRegopenkeyexD; "RegOpenKeyEx=%d"
0x180009423  mov     edx, 0Ch; dwFlags
0x180009428  call    cs:__imp_TracePrintfExA
0x18000942e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180009434  cmp     ecx, 0FFFFFFFFh
0x180009437  jz      short loc_18000944E
0x180009439  mov     r9d, ebx
0x18000943c  lea     r8, aGetuserprefere_0; "GetUserPreferences=%d"
0x180009443  mov     edx, 0Ch; dwFlags
0x180009448  call    cs:__imp_TracePrintfExA
0x18000944e  mov     eax, ebx
0x180009450  mov     rbx, [rsp+38h+arg_0]
0x180009455  add     rsp, 30h
0x180009459  pop     rdi
0x18000945a  retn
```
