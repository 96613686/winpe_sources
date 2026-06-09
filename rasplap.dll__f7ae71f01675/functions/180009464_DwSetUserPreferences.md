# DwSetUserPreferences

- ea: `0x180009464`
- end: `0x180009582`
- name: `DwSetUserPreferences`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009918`

## callees

- `0x180009464`
- `0x18000a4f0`

## import_xrefs

- `KERNEL32!RegCreateKeyExW` at `0x18000952f`
- `KERNEL32!RegCreateKeyExW` at `0x18000952f`
- `KERNEL32!RegCloseKey` at `0x18000954f`
- `KERNEL32!RegCloseKey` at `0x18000954f`
- `rtutils!TracePrintfExA` at `0x18000949e`
- `rtutils!TracePrintfExA` at `0x18000956f`
- `rtutils!TracePrintfExA` at `0x18000949e`
- `rtutils!TracePrintfExA` at `0x18000956f`

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
0x180009464  mov     [rsp+arg_8], rbx
0x180009469  push    rdi
0x18000946a  sub     rsp, 50h
0x18000946e  mov     rdi, rcx
0x180009471  mov     [rsp+58h+dwDisposition], 0
0x180009479  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000947f  mov     ebx, edx
0x180009481  mov     [rsp+58h+hKey], 0
0x18000948a  cmp     ecx, 0FFFFFFFFh
0x18000948d  jz      short loc_1800094A4
0x18000948f  mov     r9d, edx
0x180009492  lea     r8, aDwsetuserprefe_0; "DwSetUserPreferences(m=%d)"
0x180009499  mov     edx, 0Ch; dwFlags
0x18000949e  call    cs:__imp_TracePrintfExA
0x1800094a4  test    rdi, rdi
0x1800094a7  jnz     short loc_1800094B1
0x1800094a9  lea     eax, [rdi+57h]
0x1800094ac  jmp     loc_180009577
0x1800094b1  cmp     dword ptr [rdi+0B4h], 0
0x1800094b8  jnz     short loc_1800094C1
0x1800094ba  xor     eax, eax
0x1800094bc  jmp     loc_180009577
0x1800094c1  test    ebx, ebx
0x1800094c3  jnz     short loc_1800094D5
0x1800094c5  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\RAS Phonebook"
0x1800094cc  mov     rcx, 0FFFFFFFF80000001h
0x1800094d3  jmp     short loc_1800094F8
0x1800094d5  cmp     ebx, 1
0x1800094d8  jnz     short loc_1800094EA
0x1800094da  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x1800094e1  mov     rcx, 0FFFFFFFF80000003h
0x1800094e8  jmp     short loc_1800094F8
0x1800094ea  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Router Phonebook"
0x1800094f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800094f8  lea     rax, [rsp+58h+dwDisposition]
0x1800094fd  xor     r8d, r8d; Reserved
0x180009500  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180009505  lea     r9, Data; lpClass
0x18000950c  lea     rax, [rsp+58h+hKey]
0x180009511  mov     [rsp+58h+phkResult], rax; phkResult
0x180009516  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000951f  mov     [rsp+58h+samDesired], 2000Eh; samDesired
0x180009527  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000952f  call    cs:__imp_RegCreateKeyExW
0x180009535  mov     ebx, eax
0x180009537  test    eax, eax
0x180009539  jnz     short loc_180009555
0x18000953b  mov     rcx, [rsp+58h+hKey]; hKey
0x180009540  mov     rdx, rdi
0x180009543  call    WriteUserPreferences
0x180009548  mov     rcx, [rsp+58h+hKey]; hKey
0x18000954d  mov     ebx, eax
0x18000954f  call    cs:__imp_RegCloseKey
0x180009555  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000955b  cmp     ecx, 0FFFFFFFFh
0x18000955e  jz      short loc_180009575
0x180009560  mov     r9d, ebx
0x180009563  lea     r8, aDwsetuserprefe; "DwSetUserPreferences=%d"
0x18000956a  mov     edx, 0Ch; dwFlags
0x18000956f  call    cs:__imp_TracePrintfExA
0x180009575  mov     eax, ebx
0x180009577  mov     rbx, [rsp+58h+arg_8]
0x18000957c  add     rsp, 50h
0x180009580  pop     rdi
0x180009581  retn
```
