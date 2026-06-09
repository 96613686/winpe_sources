# LsadbInitializeRegistryParams(void)

- ea: `0x18003535c`
- end: `0x180035442`
- name: `?LsadbInitializeRegistryParams@@YAJXZ`
- size: `230`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800060b0`

## callees

- `0x180035280`
- `0x18003535c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800353af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800353af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035419`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035429`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035429`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003539b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003539b`
- `LSASRV!LsaIRegisterNotification` at `0x1800353da`
- `LSASRV!LsaIRegisterNotification` at `0x1800353da`

## pseudocode

```c
__int64 LsadbInitializeRegistryParams(void)
{
  HANDLE EventW; // rdi
  void *v1; // rax
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = 0;
  LsaDbRegistryWatchEvent = 0;
  LsaDbRegistryWatchKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 0x20019u, &hKey) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      v1 = (void *)LsaIRegisterNotification(LsaDbRegistryWatch, 0, 2);
      if ( v1 )
      {
        LsaDbRegistryWatchKey = hKey;
        LsaDbRegistryWatchEvent = EventW;
        LsaDbRegistryWatchNotification = v1;
        LsaDbRegistryWatch(0);
        return 0;
      }
      CloseHandle(EventW);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  LsaDbRegistryWatchNotification = 0;
  return 3221225495LL;
}

```

## disassembly

```asm
0x18003535c  mov     r11, rsp
0x18003535f  mov     [r11+10h], rbx
0x180035363  push    rdi
0x180035364  sub     rsp, 40h
0x180035368  xor     ebx, ebx
0x18003536a  lea     rax, [r11+8]
0x18003536e  mov     r9d, 20019h; samDesired
0x180035374  mov     [r11+8], rbx
0x180035378  xor     r8d, r8d; ulOptions
0x18003537b  mov     cs:?LsaDbRegistryWatchEvent@@3PEAXEA, rbx; void * LsaDbRegistryWatchEvent
0x180035382  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Lsa"
0x180035389  mov     cs:?LsaDbRegistryWatchKey@@3PEAUHKEY__@@EA, rbx; HKEY__ * LsaDbRegistryWatchKey
0x180035390  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035397  mov     [r11-28h], rax
0x18003539b  call    cs:__imp_RegOpenKeyExW
0x1800353a1  test    eax, eax
0x1800353a3  jnz     short loc_18003541F
0x1800353a5  xor     r9d, r9d; lpName
0x1800353a8  xor     r8d, r8d; bInitialState
0x1800353ab  xor     edx, edx; bManualReset
0x1800353ad  xor     ecx, ecx; lpEventAttributes
0x1800353af  call    cs:__imp_CreateEventW
0x1800353b5  mov     rdi, rax
0x1800353b8  test    rax, rax
0x1800353bb  jz      short loc_18003541F
0x1800353bd  mov     [rsp+48h+var_18], rax
0x1800353c2  lea     r8d, [rbx+2]
0x1800353c6  mov     [rsp+48h+var_20], ebx
0x1800353ca  lea     rcx, ?LsaDbRegistryWatch@@YAKPEAX@Z; LsaDbRegistryWatch(void *)
0x1800353d1  xor     r9d, r9d
0x1800353d4  mov     [rsp+48h+var_28], ebx
0x1800353d8  xor     edx, edx
0x1800353da  call    cs:__imp_LsaIRegisterNotification
0x1800353e0  mov     rbx, rax
0x1800353e3  test    rax, rax
0x1800353e6  jz      short loc_180035416
0x1800353e8  mov     rcx, [rsp+48h+hKey]
0x1800353ed  mov     cs:?LsaDbRegistryWatchKey@@3PEAUHKEY__@@EA, rcx; HKEY__ * LsaDbRegistryWatchKey
0x1800353f4  mov     cs:?LsaDbRegistryWatchEvent@@3PEAXEA, rdi; void * LsaDbRegistryWatchEvent
0x1800353fb  mov     cs:?LsaDbRegistryWatchNotification@@3PEAXEA, rax; void * LsaDbRegistryWatchNotification
0x180035402  xor     ecx, ecx; void *
0x180035404  call    ?LsaDbRegistryWatch@@YAKPEAX@Z; LsaDbRegistryWatch(void *)
0x180035409  xor     eax, eax
0x18003540b  mov     rbx, [rsp+48h+arg_8]
0x180035410  add     rsp, 40h
0x180035414  pop     rdi
0x180035415  retn
0x180035416  mov     rcx, rdi; hObject
0x180035419  call    cs:__imp_CloseHandle
0x18003541f  mov     rcx, [rsp+48h+hKey]; hKey
0x180035424  test    rcx, rcx
0x180035427  jz      short loc_18003542F
0x180035429  call    cs:__imp_RegCloseKey
0x18003542f  mov     cs:?LsaDbRegistryWatchNotification@@3PEAXEA, rbx; void * LsaDbRegistryWatchNotification
0x180035436  test    rbx, rbx
0x180035439  jnz     short loc_180035402
0x18003543b  mov     eax, 0C0000017h
0x180035440  jmp     short loc_18003540B
```
