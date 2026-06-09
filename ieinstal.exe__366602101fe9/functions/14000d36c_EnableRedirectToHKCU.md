# EnableRedirectToHKCU

- ea: `0x14000d36c`
- end: `0x14000d4e8`
- name: `EnableRedirectToHKCU`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140005188`

## callees

- `0x1400022a0`
- `0x140002910`
- `0x1400029d0`
- `0x140002fe0`
- `0x14000d36c`
- `0x14000d4f0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000d4ac`
- `ADVAPI32!RegCloseKey` at `0x14000d4bd`
- `ADVAPI32!RegCloseKey` at `0x14000d4ac`
- `ADVAPI32!RegCloseKey` at `0x14000d4bd`
- `ADVAPI32!RegOpenKeyExW` at `0x14000d3e7`
- `ADVAPI32!RegOpenKeyExW` at `0x14000d3e7`
- `ADVAPI32!RegOpenCurrentUser` at `0x14000d385`
- `ADVAPI32!RegOpenCurrentUser` at `0x14000d385`
- `ADVAPI32!RegOverridePredefKey` at `0x14000d3a7`
- `ADVAPI32!RegOverridePredefKey` at `0x14000d409`
- `ADVAPI32!RegOverridePredefKey` at `0x14000d3a7`
- `ADVAPI32!RegOverridePredefKey` at `0x14000d409`
- `KERNEL32!GetCurrentThread` at `0x14000d445`
- `KERNEL32!GetCurrentThread` at `0x14000d445`
- `KERNEL32!LeaveCriticalSection` at `0x14000d49b`
- `KERNEL32!LeaveCriticalSection` at `0x14000d49b`
- `KERNEL32!EnterCriticalSection` at `0x14000d426`
- `KERNEL32!EnterCriticalSection` at `0x14000d426`

## pseudocode

```c
__int64 EnableRedirectToHKCU()
{
  LSTATUS v0; // ebx
  HANDLE CurrentThread; // rax
  HKEY hNewHKey; // [rsp+40h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF

  phkResult = 0;
  v0 = RegOpenCurrentUser(0xF003Fu, &phkResult);
  if ( v0 )
    goto LABEL_12;
  v0 = RegOverridePredefKey(HKEY_LOCAL_MACHINE, phkResult);
  if ( !v0 )
  {
    hNewHKey = 0;
    v0 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Classes", 0, 0xF003Fu, &hNewHKey);
    if ( !v0 )
    {
      v0 = RegOverridePredefKey(HKEY_CLASSES_ROOT, hNewHKey);
      if ( !v0 )
      {
        EnterCriticalSection(&g_DetourCriticalSection);
        if ( !g_fRegisterTypeLibDetoured )
        {
          v0 = DetourTransactionBegin();
          if ( !v0 )
          {
            CurrentThread = GetCurrentThread();
            DetourUpdateThread(CurrentThread);
            DetourAttach(&qword_1400178E0, Detour_RegisterTypeLib);
            DetourAttach(&qword_1400178E8, Detour_UnRegisterTypeLib);
            v0 = DetourTransactionCommit();
            if ( !v0 )
              g_fRegisterTypeLibDetoured = 1;
          }
        }
        LeaveCriticalSection(&g_DetourCriticalSection);
      }
      RegCloseKey(hNewHKey);
    }
  }
  RegCloseKey(phkResult);
  if ( v0 )
  {
LABEL_12:
    DestroyDetoursRedirectToHKCU();
    if ( v0 > 0 )
      return (unsigned __int16)v0 | 0x80070000;
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000d36c  push    rbx
0x14000d36e  sub     rsp, 30h
0x14000d372  lea     rdx, [rsp+38h+phkResult]; phkResult
0x14000d377  mov     [rsp+38h+phkResult], 0
0x14000d380  mov     ecx, 0F003Fh; samDesired
0x14000d385  call    cs:__imp_RegOpenCurrentUser
0x14000d38c  nop     dword ptr [rax+rax+00h]
0x14000d391  mov     ebx, eax
0x14000d393  test    eax, eax
0x14000d395  jnz     loc_14000D4CD
0x14000d39b  mov     rdx, [rsp+38h+phkResult]; hNewHKey
0x14000d3a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000d3a7  call    cs:__imp_RegOverridePredefKey
0x14000d3ae  nop     dword ptr [rax+rax+00h]
0x14000d3b3  mov     ebx, eax
0x14000d3b5  test    eax, eax
0x14000d3b7  jnz     loc_14000D4B8
0x14000d3bd  lea     rax, [rsp+38h+hNewHKey]
0x14000d3c2  mov     [rsp+38h+hNewHKey], 0
0x14000d3cb  mov     r9d, 0F003Fh; samDesired
0x14000d3d1  mov     [rsp+38h+var_18], rax; phkResult
0x14000d3d6  xor     r8d, r8d; ulOptions
0x14000d3d9  lea     rdx, aSoftwareClasse; "Software\\Classes"
0x14000d3e0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000d3e7  call    cs:__imp_RegOpenKeyExW
0x14000d3ee  nop     dword ptr [rax+rax+00h]
0x14000d3f3  mov     ebx, eax
0x14000d3f5  test    eax, eax
0x14000d3f7  jnz     loc_14000D4B8
0x14000d3fd  mov     rdx, [rsp+38h+hNewHKey]; hNewHKey
0x14000d402  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14000d409  call    cs:__imp_RegOverridePredefKey
0x14000d410  nop     dword ptr [rax+rax+00h]
0x14000d415  mov     ebx, eax
0x14000d417  test    eax, eax
0x14000d419  jnz     loc_14000D4A7
0x14000d41f  lea     rcx, ?g_DetourCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000d426  call    cs:__imp_EnterCriticalSection
0x14000d42d  nop     dword ptr [rax+rax+00h]
0x14000d432  cmp     cs:?g_fRegisterTypeLibDetoured@@3HA, ebx; int g_fRegisterTypeLibDetoured
0x14000d438  jnz     short loc_14000D494
0x14000d43a  call    DetourTransactionBegin
0x14000d43f  mov     ebx, eax
0x14000d441  test    eax, eax
0x14000d443  jnz     short loc_14000D494
0x14000d445  call    cs:__imp_GetCurrentThread
0x14000d44c  nop     dword ptr [rax+rax+00h]
0x14000d451  mov     rcx, rax; hThread
0x14000d454  call    DetourUpdateThread
0x14000d459  lea     rdx, ?Detour_RegisterTypeLib@@YAJPEAUITypeLib@@PEAG1@Z; Detour_RegisterTypeLib(ITypeLib *,ushort *,ushort *)
0x14000d460  lea     rcx, qword_1400178E0
0x14000d467  call    DetourAttach
0x14000d46c  lea     rdx, ?Detour_UnRegisterTypeLib@@YAJAEBU_GUID@@GGKW4tagSYSKIND@@@Z; Detour_UnRegisterTypeLib(_GUID const &,ushort,ushort,ulong,tagSYSKIND)
0x14000d473  lea     rcx, qword_1400178E8
0x14000d47a  call    DetourAttach
0x14000d47f  call    DetourTransactionCommit
0x14000d484  mov     ebx, eax
0x14000d486  test    eax, eax
0x14000d488  jnz     short loc_14000D494
0x14000d48a  mov     cs:?g_fRegisterTypeLibDetoured@@3HA, 1; int g_fRegisterTypeLibDetoured
0x14000d494  lea     rcx, ?g_DetourCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000d49b  call    cs:__imp_LeaveCriticalSection
0x14000d4a2  nop     dword ptr [rax+rax+00h]
0x14000d4a7  mov     rcx, [rsp+38h+hNewHKey]; hKey
0x14000d4ac  call    cs:__imp_RegCloseKey
0x14000d4b3  nop     dword ptr [rax+rax+00h]
0x14000d4b8  mov     rcx, [rsp+38h+phkResult]; hKey
0x14000d4bd  call    cs:__imp_RegCloseKey
0x14000d4c4  nop     dword ptr [rax+rax+00h]
0x14000d4c9  test    ebx, ebx
0x14000d4cb  jz      short loc_14000D4DF
0x14000d4cd  call    ?DestroyDetoursRedirectToHKCU@@YAJXZ; DestroyDetoursRedirectToHKCU(void)
0x14000d4d2  test    ebx, ebx
0x14000d4d4  jle     short loc_14000D4DF
0x14000d4d6  movzx   ebx, bx
0x14000d4d9  or      ebx, 80070000h
0x14000d4df  mov     eax, ebx
0x14000d4e1  add     rsp, 30h
0x14000d4e5  pop     rbx
0x14000d4e6  retn
```
