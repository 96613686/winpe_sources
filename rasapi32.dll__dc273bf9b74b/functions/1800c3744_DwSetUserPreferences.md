# DwSetUserPreferences

- ea: `0x1800c3744`
- end: `0x1800c3862`
- name: `DwSetUserPreferences`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c3bf4`
- `0x1800c3d0c`

## callees

- `0x1800c3744`
- `0x1800c4744`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c380f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c380f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c382f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c382f`
- `rtutils!TracePrintfExA` at `0x1800c377e`
- `rtutils!TracePrintfExA` at `0x1800c384f`
- `rtutils!TracePrintfExA` at `0x1800c377e`
- `rtutils!TracePrintfExA` at `0x1800c384f`

## pseudocode

```c
__int64 __fastcall DwSetUserPreferences(int *a1, int a2)
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
  if ( !a1[45] )
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
  v7 = RegCreateKeyExW((HKEY)v6, v5, 0, (LPWSTR)&Data, 0, 0x2000Eu, 0, &hKey, &dwDisposition);
  if ( !v7 )
  {
    v7 = WriteUserPreferences(hKey, a1);
    RegCloseKey(hKey);
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DwSetUserPreferences=%d", v7);
  return v7;
}

```

## disassembly

```asm
0x1800c3744  mov     [rsp+arg_8], rbx
0x1800c3749  push    rdi
0x1800c374a  sub     rsp, 50h
0x1800c374e  mov     rdi, rcx
0x1800c3751  mov     [rsp+58h+dwDisposition], 0
0x1800c3759  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c375f  mov     ebx, edx
0x1800c3761  mov     [rsp+58h+hKey], 0
0x1800c376a  cmp     ecx, 0FFFFFFFFh
0x1800c376d  jz      short loc_1800C3784
0x1800c376f  mov     r9d, edx
0x1800c3772  lea     r8, aDwsetuserprefe_0; "DwSetUserPreferences(m=%d)"
0x1800c3779  mov     edx, 0Ch; dwFlags
0x1800c377e  call    cs:__imp_TracePrintfExA
0x1800c3784  test    rdi, rdi
0x1800c3787  jnz     short loc_1800C3791
0x1800c3789  lea     eax, [rdi+57h]
0x1800c378c  jmp     loc_1800C3857
0x1800c3791  cmp     dword ptr [rdi+0B4h], 0
0x1800c3798  jnz     short loc_1800C37A1
0x1800c379a  xor     eax, eax
0x1800c379c  jmp     loc_1800C3857
0x1800c37a1  test    ebx, ebx
0x1800c37a3  jnz     short loc_1800C37B5
0x1800c37a5  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\RAS Phonebook"
0x1800c37ac  mov     rcx, 0FFFFFFFF80000001h
0x1800c37b3  jmp     short loc_1800C37D8
0x1800c37b5  cmp     ebx, 1
0x1800c37b8  jnz     short loc_1800C37CA
0x1800c37ba  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x1800c37c1  mov     rcx, 0FFFFFFFF80000003h
0x1800c37c8  jmp     short loc_1800C37D8
0x1800c37ca  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Router Phonebook"
0x1800c37d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c37d8  lea     rax, [rsp+58h+dwDisposition]
0x1800c37dd  xor     r8d, r8d; Reserved
0x1800c37e0  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800c37e5  lea     r9, Data; lpClass
0x1800c37ec  lea     rax, [rsp+58h+hKey]
0x1800c37f1  mov     [rsp+58h+phkResult], rax; phkResult
0x1800c37f6  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800c37ff  mov     [rsp+58h+samDesired], 2000Eh; samDesired
0x1800c3807  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800c380f  call    cs:__imp_RegCreateKeyExW
0x1800c3815  mov     ebx, eax
0x1800c3817  test    eax, eax
0x1800c3819  jnz     short loc_1800C3835
0x1800c381b  mov     rcx, [rsp+58h+hKey]; hKey
0x1800c3820  mov     rdx, rdi
0x1800c3823  call    WriteUserPreferences
0x1800c3828  mov     rcx, [rsp+58h+hKey]; hKey
0x1800c382d  mov     ebx, eax
0x1800c382f  call    cs:__imp_RegCloseKey
0x1800c3835  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c383b  cmp     ecx, 0FFFFFFFFh
0x1800c383e  jz      short loc_1800C3855
0x1800c3840  mov     r9d, ebx
0x1800c3843  lea     r8, aDwsetuserprefe; "DwSetUserPreferences=%d"
0x1800c384a  mov     edx, 0Ch; dwFlags
0x1800c384f  call    cs:__imp_TracePrintfExA
0x1800c3855  mov     eax, ebx
0x1800c3857  mov     rbx, [rsp+58h+arg_8]
0x1800c385c  add     rsp, 50h
0x1800c3860  pop     rdi
0x1800c3861  retn
```
