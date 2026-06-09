# DwGetInstalledProtocolsEx

- ea: `0x180015230`
- end: `0x1800153a0`
- name: `DwGetInstalledProtocolsEx`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012ff8`
- `0x180015644`

## callees

- `0x180015230`
- `0x1800c0aac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001527d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800152ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015335`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001527d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800152ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015335`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001535f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015374`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001535f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015374`
- `rtutils!TracePrintfExA` at `0x180015395`
- `rtutils!TracePrintfExA` at `0x180015395`

## string_xrefs

- `0x180015389`: `GetInstalledProtocolsEx=0x%x. `
- `0x1800152e1`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

## pseudocode

```c
__int64 __fastcall DwGetInstalledProtocolsEx(unsigned int a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebx
  unsigned int i; // edi
  unsigned int j; // edi
  const WCHAR *v9; // rdx
  HKEY phkResult; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  hKey = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)qword_1800E1000[3 * (int)i + 1], 0, 0x2000000u, &hKey) )
    {
      v3 |= LODWORD(qword_1800E1000[3 * (int)i]);
      RegCloseKey(hKey);
    }
  }
  if ( (a1 || a3) && v3 )
  {
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
           0,
           0x2000000u,
           &hKey) )
    {
      v3 = 0;
    }
    else
    {
      for ( j = 0; j < 2; ++j )
      {
        if ( (v3 & qword_1800E1000[3 * (int)j]) != 0 )
        {
          v9 = (const WCHAR *)qword_1800E1000[3 * (int)j + 2];
          phkResult = 0;
          if ( !RegOpenKeyExW(hKey, v9, 0, 0x2000000u, &phkResult) )
          {
            if ( !(unsigned int)FProtocolEnabled(phkResult, a3, a1) )
              v3 &= ~LODWORD(qword_1800E1000[3 * (int)j]);
            RegCloseKey(phkResult);
          }
        }
      }
      RegCloseKey(hKey);
    }
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GetInstalledProtocolsEx=0x%x. ", v3);
  return v3;
}

```

## disassembly

```asm
0x180015230  mov     rax, rsp
0x180015233  push    rbx
0x180015234  push    rbp
0x180015235  push    rsi
0x180015236  push    rdi
0x180015237  push    r14
0x180015239  push    r15
0x18001523b  sub     rsp, 48h
0x18001523f  xor     ebx, ebx
0x180015241  lea     r15, qword_1800E1000
0x180015248  mov     [rax+20h], rbx
0x18001524c  xor     edi, edi
0x18001524e  mov     ebp, r8d
0x180015251  mov     r14d, ecx
0x180015254  movsxd  rax, edi
0x180015257  mov     r9d, 2000000h; samDesired
0x18001525d  xor     r8d, r8d; ulOptions
0x180015260  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015267  lea     rsi, [rax+rax*2]
0x18001526b  mov     rdx, [r15+rsi*8+8]; lpSubKey
0x180015270  lea     rax, [rsp+78h+hKey]
0x180015278  mov     [rsp+78h+phkResult], rax; phkResult
0x18001527d  call    cs:__imp_RegOpenKeyExW
0x180015283  test    eax, eax
0x180015285  jnz     short loc_180015299
0x180015287  or      ebx, [r15+rsi*8]
0x18001528b  mov     rcx, [rsp+78h+hKey]; hKey
0x180015293  call    cs:__imp_RegCloseKey
0x180015299  inc     edi
0x18001529b  cmp     edi, 2
0x18001529e  jb      short loc_180015254
0x1800152a0  test    r14d, r14d
0x1800152a3  jnz     short loc_1800152C7
0x1800152a5  test    ebp, ebp
0x1800152a7  jnz     short loc_1800152C7
0x1800152a9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800152af  cmp     ecx, 0FFFFFFFFh
0x1800152b2  jnz     loc_180015386
0x1800152b8  mov     eax, ebx
0x1800152ba  add     rsp, 48h
0x1800152be  pop     r15
0x1800152c0  pop     r14
0x1800152c2  pop     rdi
0x1800152c3  pop     rsi
0x1800152c4  pop     rbp
0x1800152c5  pop     rbx
0x1800152c6  retn
0x1800152c7  test    ebx, ebx
0x1800152c9  jz      short loc_1800152A9
0x1800152cb  lea     rax, [rsp+78h+hKey]
0x1800152d3  mov     r9d, 2000000h; samDesired
0x1800152d9  xor     r8d, r8d; ulOptions
0x1800152dc  mov     [rsp+78h+phkResult], rax; phkResult
0x1800152e1  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x1800152e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800152ef  call    cs:__imp_RegOpenKeyExW
0x1800152f5  test    eax, eax
0x1800152f7  jnz     loc_18001537F
0x1800152fd  xor     edi, edi
0x1800152ff  movsxd  rax, edi
0x180015302  lea     rsi, [rax+rax*2]
0x180015306  test    [r15+rsi*8], ebx
0x18001530a  jz      short loc_180015365
0x18001530c  mov     rdx, [r15+rsi*8+10h]; lpSubKey
0x180015311  lea     rax, [rsp+78h+var_48]
0x180015316  mov     rcx, [rsp+78h+hKey]; hKey
0x18001531e  mov     r9d, 2000000h; samDesired
0x180015324  xor     r8d, r8d; ulOptions
0x180015327  mov     [rsp+78h+phkResult], rax; phkResult
0x18001532c  mov     [rsp+78h+var_48], 0
0x180015335  call    cs:__imp_RegOpenKeyExW
0x18001533b  test    eax, eax
0x18001533d  jnz     short loc_180015365
0x18001533f  mov     rcx, [rsp+78h+var_48]
0x180015344  mov     r8d, r14d
0x180015347  mov     edx, ebp
0x180015349  call    FProtocolEnabled
0x18001534e  test    eax, eax
0x180015350  jnz     short loc_18001535A
0x180015352  mov     eax, [r15+rsi*8]
0x180015356  not     eax
0x180015358  and     ebx, eax
0x18001535a  mov     rcx, [rsp+78h+var_48]; hKey
0x18001535f  call    cs:__imp_RegCloseKey
0x180015365  inc     edi
0x180015367  cmp     edi, 2
0x18001536a  jb      short loc_1800152FF
0x18001536c  mov     rcx, [rsp+78h+hKey]; hKey
0x180015374  call    cs:__imp_RegCloseKey
0x18001537a  jmp     loc_1800152A9
0x18001537f  xor     ebx, ebx
0x180015381  jmp     loc_1800152A9
0x180015386  mov     r9d, ebx
0x180015389  lea     r8, aGetinstalledpr; "GetInstalledProtocolsEx=0x%x. "
0x180015390  mov     edx, 0Ch; dwFlags
0x180015395  call    cs:__imp_TracePrintfExA
0x18001539b  jmp     loc_1800152B8
```
