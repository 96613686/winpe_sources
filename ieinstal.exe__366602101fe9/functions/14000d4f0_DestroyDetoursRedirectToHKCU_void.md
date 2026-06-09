# DestroyDetoursRedirectToHKCU(void)

- ea: `0x14000d4f0`
- end: `0x14000d585`
- name: `?DestroyDetoursRedirectToHKCU@@YAJXZ`
- size: `149`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140005188`
- `0x14000d36c`

## callees

- `0x140002790`
- `0x140002910`
- `0x1400029d0`
- `0x140002fe0`
- `0x14000d4f0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x14000d51e`
- `KERNEL32!GetCurrentThread` at `0x14000d51e`
- `KERNEL32!LeaveCriticalSection` at `0x14000d570`
- `KERNEL32!LeaveCriticalSection` at `0x14000d570`
- `KERNEL32!EnterCriticalSection` at `0x14000d4ff`
- `KERNEL32!EnterCriticalSection` at `0x14000d4ff`

## pseudocode

```c
__int64 DestroyDetoursRedirectToHKCU(void)
{
  unsigned int v0; // ebx
  HANDLE CurrentThread; // rax

  v0 = 0;
  EnterCriticalSection(&g_DetourCriticalSection);
  if ( g_fRegisterTypeLibDetoured )
  {
    v0 = DetourTransactionBegin();
    if ( !v0 )
    {
      CurrentThread = GetCurrentThread();
      DetourUpdateThread(CurrentThread);
      DetourDetach(&qword_1400178E0, Detour_RegisterTypeLib);
      DetourDetach(&qword_1400178E8, Detour_UnRegisterTypeLib);
      v0 = DetourTransactionCommit();
      if ( !v0 )
        g_fRegisterTypeLibDetoured = 0;
    }
  }
  LeaveCriticalSection(&g_DetourCriticalSection);
  return v0;
}

```

## disassembly

```asm
0x14000d4f0  push    rbx
0x14000d4f2  sub     rsp, 20h
0x14000d4f6  lea     rcx, ?g_DetourCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000d4fd  xor     ebx, ebx
0x14000d4ff  call    cs:__imp_EnterCriticalSection
0x14000d506  nop     dword ptr [rax+rax+00h]
0x14000d50b  cmp     cs:?g_fRegisterTypeLibDetoured@@3HA, ebx; int g_fRegisterTypeLibDetoured
0x14000d511  jz      short loc_14000D569
0x14000d513  call    DetourTransactionBegin
0x14000d518  mov     ebx, eax
0x14000d51a  test    eax, eax
0x14000d51c  jnz     short loc_14000D569
0x14000d51e  call    cs:__imp_GetCurrentThread
0x14000d525  nop     dword ptr [rax+rax+00h]
0x14000d52a  mov     rcx, rax; hThread
0x14000d52d  call    DetourUpdateThread
0x14000d532  lea     rdx, ?Detour_RegisterTypeLib@@YAJPEAUITypeLib@@PEAG1@Z; Detour_RegisterTypeLib(ITypeLib *,ushort *,ushort *)
0x14000d539  lea     rcx, qword_1400178E0
0x14000d540  call    DetourDetach
0x14000d545  lea     rdx, ?Detour_UnRegisterTypeLib@@YAJAEBU_GUID@@GGKW4tagSYSKIND@@@Z; Detour_UnRegisterTypeLib(_GUID const &,ushort,ushort,ulong,tagSYSKIND)
0x14000d54c  lea     rcx, qword_1400178E8
0x14000d553  call    DetourDetach
0x14000d558  call    DetourTransactionCommit
0x14000d55d  mov     ebx, eax
0x14000d55f  test    eax, eax
0x14000d561  jnz     short loc_14000D569
0x14000d563  mov     cs:?g_fRegisterTypeLibDetoured@@3HA, eax; int g_fRegisterTypeLibDetoured
0x14000d569  lea     rcx, ?g_DetourCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000d570  call    cs:__imp_LeaveCriticalSection
0x14000d577  nop     dword ptr [rax+rax+00h]
0x14000d57c  mov     eax, ebx
0x14000d57e  add     rsp, 20h
0x14000d582  pop     rbx
0x14000d583  retn
```
