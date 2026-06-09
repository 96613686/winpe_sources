# HrLoadRAS(void)

- ea: `0x1800a83d4`
- end: `0x1800a8668`
- name: `?HrLoadRAS@@YAJXZ`
- size: `660`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a7ad0`
- `0x1800a8270`

## callees

- `0x1800a83d4`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x1800a8482`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a8482`
- `ADVAPI32!RegCloseKey` at `0x1800a849b`
- `ADVAPI32!RegCloseKey` at `0x1800a849b`
- `KERNEL32!LoadLibraryA` at `0x1800a84b5`
- `KERNEL32!LoadLibraryA` at `0x1800a84b5`
- `KERNEL32!GetProcAddress` at `0x1800a84dd`
- `KERNEL32!GetProcAddress` at `0x1800a84f8`
- `KERNEL32!GetProcAddress` at `0x1800a8513`
- `KERNEL32!GetProcAddress` at `0x1800a852e`
- `KERNEL32!GetProcAddress` at `0x1800a8549`
- `KERNEL32!GetProcAddress` at `0x1800a8564`
- `KERNEL32!GetProcAddress` at `0x1800a857f`
- `KERNEL32!GetProcAddress` at `0x1800a859a`
- `KERNEL32!GetProcAddress` at `0x1800a85b5`
- `KERNEL32!GetProcAddress` at `0x1800a85d0`
- `KERNEL32!GetProcAddress` at `0x1800a84dd`
- `KERNEL32!GetProcAddress` at `0x1800a84f8`
- `KERNEL32!GetProcAddress` at `0x1800a8513`
- `KERNEL32!GetProcAddress` at `0x1800a852e`
- `KERNEL32!GetProcAddress` at `0x1800a8549`
- `KERNEL32!GetProcAddress` at `0x1800a8564`
- `KERNEL32!GetProcAddress` at `0x1800a857f`
- `KERNEL32!GetProcAddress` at `0x1800a859a`
- `KERNEL32!GetProcAddress` at `0x1800a85b5`
- `KERNEL32!GetProcAddress` at `0x1800a85d0`
- `KERNEL32!LeaveCriticalSection` at `0x1800a863f`
- `KERNEL32!LeaveCriticalSection` at `0x1800a863f`
- `KERNEL32!EnterCriticalSection` at `0x1800a83fc`
- `KERNEL32!EnterCriticalSection` at `0x1800a83fc`
- `KERNEL32!GetVersionExA` at `0x1800a842e`
- `KERNEL32!GetVersionExA` at `0x1800a842e`
- `KERNEL32!SetErrorMode` at `0x1800a84a6`
- `KERNEL32!SetErrorMode` at `0x1800a84c4`
- `KERNEL32!SetErrorMode` at `0x1800a84a6`
- `KERNEL32!SetErrorMode` at `0x1800a84c4`

## string_xrefs

- `0x1800a85a7`: `RasCreatePhonebookEntryA`
- `0x1800a84ac`: `RASAPI32.DLL`

## pseudocode

```c
__int64 HrLoadRAS(void)
{
  unsigned int v0; // edi
  UINT v1; // ebx
  FARPROC ProcAddress; // rax
  HKEY hKey; // [rsp+30h] [rbp-D8h] BYREF
  struct _OSVERSIONINFOA VersionInformation; // [rsp+40h] [rbp-C8h] BYREF
  CHAR SubKey[24]; // [rsp+E0h] [rbp-28h] BYREF

  v0 = 0;
  EnterCriticalSection(&g_csRAS);
  if ( !g_hinstRAS )
  {
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x90u);
    VersionInformation.dwOSVersionInfoSize = 148;
    GetVersionExA(&VersionInformation);
    if ( VersionInformation.dwPlatformId == 2 )
    {
      strcpy(SubKey, "SOFTWARE\\Microsoft\\RAS");
      hKey = 0;
      if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
      {
LABEL_4:
        v0 = -2146644798;
        goto LABEL_18;
      }
      RegCloseKey(hKey);
    }
    v1 = SetErrorMode(0x8000u);
    g_hinstRAS = LoadLibraryA("RASAPI32.DLL");
    SetErrorMode(v1);
    if ( !g_hinstRAS )
      goto LABEL_4;
    qword_1800F3498 = (__int64)GetProcAddress(g_hinstRAS, "RasDialA");
    qword_1800F3490 = (__int64)GetProcAddress(g_hinstRAS, "RasEnumConnectionsA");
    qword_1800F3488 = (__int64)GetProcAddress(g_hinstRAS, "RasEnumEntriesA");
    qword_1800F3480 = (__int64)GetProcAddress(g_hinstRAS, "RasGetConnectStatusA");
    qword_1800F3478 = (__int64)GetProcAddress(g_hinstRAS, "RasGetErrorStringA");
    qword_1800F3470 = (__int64)GetProcAddress(g_hinstRAS, "RasHangUpA");
    qword_1800F3468 = (__int64)GetProcAddress(g_hinstRAS, "RasSetEntryDialParamsA");
    qword_1800F3460 = (__int64)GetProcAddress(g_hinstRAS, "RasGetEntryDialParamsA");
    qword_1800F3458 = (__int64)GetProcAddress(g_hinstRAS, "RasCreatePhonebookEntryA");
    ProcAddress = GetProcAddress(g_hinstRAS, "RasEditPhonebookEntryA");
    qword_1800F3450 = (__int64)ProcAddress;
    if ( !qword_1800F3498
      || !qword_1800F3490
      || !qword_1800F3488
      || !qword_1800F3480
      || !qword_1800F3478
      || !qword_1800F3470
      || !qword_1800F3468
      || !qword_1800F3460
      || !qword_1800F3458
      || !ProcAddress )
    {
      v0 = -2146644797;
    }
  }
LABEL_18:
  LeaveCriticalSection(&g_csRAS);
  return v0;
}

```

## disassembly

```asm
0x1800a83d4  mov     [rsp+arg_0], rbx
0x1800a83d9  push    rdi
0x1800a83da  sub     rsp, 100h
0x1800a83e1  mov     rax, cs:__security_cookie
0x1800a83e8  xor     rax, rsp
0x1800a83eb  mov     [rsp+108h+var_10], rax
0x1800a83f3  lea     rcx, ?g_csRAS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a83fa  xor     edi, edi
0x1800a83fc  call    cs:__imp_EnterCriticalSection
0x1800a8402  cmp     cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hinstRAS
0x1800a8409  jnz     loc_1800A8638
0x1800a840f  xor     edx, edx; Val
0x1800a8411  lea     rcx, [rsp+108h+VersionInformation.dwMajorVersion]; void *
0x1800a8416  mov     r8d, 90h; Size
0x1800a841c  call    memset_0
0x1800a8421  lea     rcx, [rsp+108h+VersionInformation]; lpVersionInformation
0x1800a8426  mov     [rsp+108h+VersionInformation.dwOSVersionInfoSize], 94h
0x1800a842e  call    cs:__imp_GetVersionExA
0x1800a8434  cmp     [rsp+108h+VersionInformation.dwPlatformId], 2
0x1800a8439  jnz     short loc_1800A84A1
0x1800a843b  movups  xmm0, xmmword ptr cs:aSoftwareMicros; "SOFTWARE\\Microsoft\\RAS"
0x1800a8442  lea     rax, [rsp+108h+hKey]
0x1800a8447  mov     r9d, 20019h; samDesired
0x1800a844d  movsd   xmm1, qword ptr cs:aSoftwareMicros+0Fh; "oft\\RAS"
0x1800a8455  lea     rdx, [rsp+108h+SubKey]; lpSubKey
0x1800a845d  movups  xmmword ptr [rsp+108h+SubKey], xmm0
0x1800a8465  xor     r8d, r8d; ulOptions
0x1800a8468  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a846f  movsd   qword ptr [rsp+108h+SubKey+0Fh], xmm1
0x1800a8478  mov     [rsp+108h+hKey], rdi
0x1800a847d  mov     [rsp+108h+phkResult], rax; phkResult
0x1800a8482  call    cs:__imp_RegOpenKeyExA
0x1800a8488  test    eax, eax
0x1800a848a  jz      short loc_1800A8496
0x1800a848c  mov     edi, 800CCCC2h
0x1800a8491  jmp     loc_1800A8638
0x1800a8496  mov     rcx, [rsp+108h+hKey]; hKey
0x1800a849b  call    cs:__imp_RegCloseKey
0x1800a84a1  mov     ecx, 8000h; uMode
0x1800a84a6  call    cs:__imp_SetErrorMode
0x1800a84ac  lea     rcx, aRasapi32Dll; "RASAPI32.DLL"
0x1800a84b3  mov     ebx, eax
0x1800a84b5  call    cs:__imp_LoadLibraryA
0x1800a84bb  mov     ecx, ebx; uMode
0x1800a84bd  mov     cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hinstRAS
0x1800a84c4  call    cs:__imp_SetErrorMode
0x1800a84ca  mov     rcx, cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA; hModule
0x1800a84d1  test    rcx, rcx
0x1800a84d4  jz      short loc_1800A848C
0x1800a84d6  lea     rdx, c_szRasDial; "RasDialA"
0x1800a84dd  call    cs:__imp_GetProcAddress
0x1800a84e3  mov     rcx, cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA; hModule
0x1800a84ea  lea     rdx, c_szRasEnumConnections; "RasEnumConnectionsA"
0x1800a84f1  mov     cs:qword_1800F3498, rax
0x1800a84f8  call    cs:__imp_GetProcAddress
0x1800a84fe  mov     rcx, cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA; hModule
0x1800a8505  lea     rdx, c_szRasEnumEntries; "RasEnumEntriesA"
0x1800a850c  mov     cs:qword_1800F3490, rax
0x1800a8513  call    cs:__imp_GetProcAddress
0x1800a8519  mov     rcx, cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA; hModule
0x1800a8520  lea     rdx, c_szRasGetConnectStatus; "RasGetConnectStatusA"
0x1800a8527  mov     cs:qword_1800F3488, rax
0x1800a852e  call    cs:__imp_GetProcAddress
0x1800a8534  mov     rcx, cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA; hModule
0x1800a853b  lea     rdx, c_szRasGetErrorString; "RasGetErrorStringA"
0x1800a8542  mov     cs:qword_1800F3480, rax
0x1800a8549  call    cs:__imp_GetProcAddress
0x1800a854f  mov     rcx, cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA; hModule
0x1800a8556  lea     rdx, c_szRasHangup; "RasHangUpA"
0x1800a855d  mov     cs:qword_1800F3478, rax
0x1800a8564  call    cs:__imp_GetProcAddress
0x1800a856a  mov     rcx, cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA; hModule
0x1800a8571  lea     rdx, c_szRasSetEntryDialParams; "RasSetEntryDialParamsA"
0x1800a8578  mov     cs:qword_1800F3470, rax
0x1800a857f  call    cs:__imp_GetProcAddress
0x1800a8585  mov     rcx, cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA; hModule
0x1800a858c  lea     rdx, c_szRasGetEntryDialParams; "RasGetEntryDialParamsA"
0x1800a8593  mov     cs:qword_1800F3468, rax
0x1800a859a  call    cs:__imp_GetProcAddress
0x1800a85a0  mov     rcx, cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA; hModule
0x1800a85a7  lea     rdx, c_szRasCreatePhonebookEntry; "RasCreatePhonebookEntryA"
0x1800a85ae  mov     cs:qword_1800F3460, rax
0x1800a85b5  call    cs:__imp_GetProcAddress
0x1800a85bb  mov     rcx, cs:?g_hinstRAS@@3PEAUHINSTANCE__@@EA; hModule
0x1800a85c2  lea     rdx, c_szRasEditPhonebookEntry; "RasEditPhonebookEntryA"
0x1800a85c9  mov     cs:qword_1800F3458, rax
0x1800a85d0  call    cs:__imp_GetProcAddress
0x1800a85d6  cmp     cs:qword_1800F3498, rdi
0x1800a85dd  mov     cs:qword_1800F3450, rax
0x1800a85e4  jz      short loc_1800A8633
0x1800a85e6  cmp     cs:qword_1800F3490, rdi
0x1800a85ed  jz      short loc_1800A8633
0x1800a85ef  cmp     cs:qword_1800F3488, rdi
0x1800a85f6  jz      short loc_1800A8633
0x1800a85f8  cmp     cs:qword_1800F3480, rdi
0x1800a85ff  jz      short loc_1800A8633
0x1800a8601  cmp     cs:qword_1800F3478, rdi
0x1800a8608  jz      short loc_1800A8633
0x1800a860a  cmp     cs:qword_1800F3470, rdi
0x1800a8611  jz      short loc_1800A8633
0x1800a8613  cmp     cs:qword_1800F3468, rdi
0x1800a861a  jz      short loc_1800A8633
0x1800a861c  cmp     cs:qword_1800F3460, rdi
0x1800a8623  jz      short loc_1800A8633
0x1800a8625  cmp     cs:qword_1800F3458, rdi
0x1800a862c  jz      short loc_1800A8633
0x1800a862e  test    rax, rax
0x1800a8631  jnz     short loc_1800A8638
0x1800a8633  mov     edi, 800CCCC3h
0x1800a8638  lea     rcx, ?g_csRAS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a863f  call    cs:__imp_LeaveCriticalSection
0x1800a8645  mov     eax, edi
0x1800a8647  mov     rcx, [rsp+108h+var_10]
0x1800a864f  xor     rcx, rsp; StackCookie
0x1800a8652  call    __security_check_cookie
0x1800a8657  mov     rbx, [rsp+108h+arg_0]
0x1800a865f  add     rsp, 100h
0x1800a8666  pop     rdi
0x1800a8667  retn
```
