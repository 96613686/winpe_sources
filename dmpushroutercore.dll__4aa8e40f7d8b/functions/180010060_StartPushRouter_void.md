# StartPushRouter(void)

- ea: `0x180010060`
- end: `0x18001024d`
- name: `?StartPushRouter@@YAJXZ`
- size: `493`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180010300`

## callees

- `0x18000ea90`
- `0x18000f798`
- `0x180010060`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180010204`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180010204`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800100c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010129`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010198`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800100c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010129`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010198`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010212`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001022a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001022a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800100be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010121`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010190`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001023a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800100be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010121`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010190`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001023a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010166`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800101d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010166`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800101d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100f3`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001009c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001009c`

## pseudocode

```c
__int64 StartPushRouter(void)
{
  HANDLE v0; // rbx
  unsigned int v1; // edi
  HKEY v2; // rsi
  DWORD LastError; // ebx
  LSTATUS v4; // eax
  bool v5; // sf
  HKEY v6; // rsi
  DWORD v7; // ebx
  LSTATUS v8; // eax
  bool v9; // sf
  HKEY v10; // rsi
  DWORD v11; // ebx
  signed int v12; // eax
  DWORD dwDisposition; // [rsp+80h] [rbp+30h] BYREF
  DWORD ThreadId; // [rsp+88h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF

  ThreadId = 0;
  hKey = 0;
  dwDisposition = 0;
  if ( g_pPushRouter )
  {
    v0 = 0;
    v1 = -2147418113;
  }
  else
  {
    v1 = 0;
    if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
    {
      v2 = hKey;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(v2);
        SetLastError(LastError);
      }
      hKey = 0;
      v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
      v5 = v4 < 0;
      if ( v4 > 0 )
        v5 = 1;
      if ( v5 )
      {
        v6 = hKey;
        if ( hKey )
        {
          v7 = GetLastError();
          RegCloseKey(v6);
          SetLastError(v7);
        }
        hKey = 0;
        v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, qword_180050DF8, 0, 0, 0, 0xF013Fu, 0, &hKey, &dwDisposition);
        v9 = v8 < 0;
        if ( v8 > 0 )
          v9 = 1;
        if ( !v9 )
        {
          v10 = hKey;
          if ( hKey )
          {
            v11 = GetLastError();
            RegCloseKey(v10);
            SetLastError(v11);
          }
          hKey = 0;
          RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 1u, 0xF013Fu, 0, &hKey, &dwDisposition);
          EnsureMdmTasksCreated();
          EnsureUserTasksCreated();
        }
      }
    }
    v0 = CreateThread(0, 0, InitializePushRouterThread, 0, 0, &ThreadId);
    if ( !v0 )
    {
      v12 = GetLastError();
      v1 = v12;
      if ( v12 > 0 )
        v1 = (unsigned __int16)v12 | 0x80070000;
    }
  }
  CloseHandle(v0);
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180010060  push    rbp
0x180010062  push    rbx
0x180010063  push    rsi
0x180010064  push    rdi
0x180010065  push    r12
0x180010067  mov     rbp, rsp
0x18001006a  sub     rsp, 50h
0x18001006e  mov     [rbp+ThreadId], 0
0x180010075  mov     [rbp+hKey], 0
0x18001007d  mov     [rbp+dwDisposition], 0
0x180010084  cmp     cs:?g_pPushRouter@@3PEAVPushRouter@@EA, 0; PushRouter * g_pPushRouter
0x18001008c  jz      short loc_18001009A
0x18001008e  xor     ebx, ebx
0x180010090  mov     edi, 8000FFFFh
0x180010095  jmp     loc_180010227
0x18001009a  xor     edi, edi
0x18001009c  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800100a2  test    al, al
0x1800100a4  jz      loc_1800101E9
0x1800100aa  mov     rsi, [rbp+hKey]
0x1800100ae  test    rsi, rsi
0x1800100b1  jz      short loc_1800100CC
0x1800100b3  call    cs:__imp_GetLastError
0x1800100b9  mov     ebx, eax
0x1800100bb  mov     rcx, rsi; hKey
0x1800100be  call    cs:__imp_RegCloseKey
0x1800100c4  mov     ecx, ebx; dwErrCode
0x1800100c6  call    cs:__imp_SetLastError
0x1800100cc  mov     [rbp+hKey], rdi
0x1800100d0  lea     rax, [rbp+hKey]
0x1800100d4  mov     [rsp+50h+phkResult], rax; phkResult
0x1800100d9  mov     r9d, 20019h; samDesired
0x1800100df  xor     r8d, r8d; ulOptions
0x1800100e2  mov     rdx, cs:lpSubKey; lpSubKey
0x1800100e9  mov     r12, 0FFFFFFFF80000002h
0x1800100f0  mov     rcx, r12; hKey
0x1800100f3  call    cs:__imp_RegOpenKeyExW
0x1800100f9  test    eax, eax
0x1800100fb  jle     short loc_180010107
0x1800100fd  movzx   eax, ax
0x180010100  or      eax, 80070000h
0x180010105  test    eax, eax
0x180010107  jns     loc_1800101E9
0x18001010d  mov     rsi, [rbp+hKey]
0x180010111  test    rsi, rsi
0x180010114  jz      short loc_18001012F
0x180010116  call    cs:__imp_GetLastError
0x18001011c  mov     ebx, eax
0x18001011e  mov     rcx, rsi; hKey
0x180010121  call    cs:__imp_RegCloseKey
0x180010127  mov     ecx, ebx; dwErrCode
0x180010129  call    cs:__imp_SetLastError
0x18001012f  mov     [rbp+hKey], rdi
0x180010133  lea     rax, [rbp+dwDisposition]
0x180010137  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x18001013c  lea     rax, [rbp+hKey]
0x180010140  mov     [rsp+50h+var_18], rax; phkResult
0x180010145  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18001014a  mov     [rsp+50h+samDesired], 0F013Fh; samDesired
0x180010152  mov     dword ptr [rsp+50h+phkResult], edi; dwOptions
0x180010156  xor     r9d, r9d; lpClass
0x180010159  xor     r8d, r8d; Reserved
0x18001015c  mov     rdx, cs:qword_180050DF8; lpSubKey
0x180010163  mov     rcx, r12; hKey
0x180010166  call    cs:__imp_RegCreateKeyExW
0x18001016c  test    eax, eax
0x18001016e  jle     short loc_18001017A
0x180010170  movzx   eax, ax
0x180010173  or      eax, 80070000h
0x180010178  test    eax, eax
0x18001017a  js      short loc_1800101E9
0x18001017c  mov     rsi, [rbp+hKey]
0x180010180  test    rsi, rsi
0x180010183  jz      short loc_18001019E
0x180010185  call    cs:__imp_GetLastError
0x18001018b  mov     ebx, eax
0x18001018d  mov     rcx, rsi; hKey
0x180010190  call    cs:__imp_RegCloseKey
0x180010196  mov     ecx, ebx; dwErrCode
0x180010198  call    cs:__imp_SetLastError
0x18001019e  mov     [rbp+hKey], rdi
0x1800101a2  lea     rax, [rbp+dwDisposition]
0x1800101a6  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x1800101ab  lea     rax, [rbp+hKey]
0x1800101af  mov     [rsp+50h+var_18], rax; phkResult
0x1800101b4  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800101b9  mov     [rsp+50h+samDesired], 0F013Fh; samDesired
0x1800101c1  mov     dword ptr [rsp+50h+phkResult], 1; dwOptions
0x1800101c9  xor     r9d, r9d; lpClass
0x1800101cc  xor     r8d, r8d; Reserved
0x1800101cf  mov     rdx, cs:lpSubKey; lpSubKey
0x1800101d6  mov     rcx, r12; hKey
0x1800101d9  call    cs:__imp_RegCreateKeyExW
0x1800101df  call    ?EnsureMdmTasksCreated@@YAJXZ; EnsureMdmTasksCreated(void)
0x1800101e4  call    ?EnsureUserTasksCreated@@YAJXZ; EnsureUserTasksCreated(void)
0x1800101e9  lea     rax, [rbp+ThreadId]
0x1800101ed  mov     qword ptr [rsp+50h+samDesired], rax; lpThreadId
0x1800101f2  mov     dword ptr [rsp+50h+phkResult], edi; dwCreationFlags
0x1800101f6  xor     r9d, r9d; lpParameter
0x1800101f9  lea     r8, ?InitializePushRouterThread@@YAKPEAX@Z; lpStartAddress
0x180010200  xor     edx, edx; dwStackSize
0x180010202  xor     ecx, ecx; lpThreadAttributes
0x180010204  call    cs:__imp_CreateThread
0x18001020a  mov     rbx, rax
0x18001020d  test    rax, rax
0x180010210  jnz     short loc_180010227
0x180010212  call    cs:__imp_GetLastError
0x180010218  mov     edi, eax
0x18001021a  test    eax, eax
0x18001021c  jle     short loc_180010227
0x18001021e  movzx   edi, ax
0x180010221  or      edi, 80070000h
0x180010227  mov     rcx, rbx; hObject
0x18001022a  call    cs:__imp_CloseHandle
0x180010230  nop
0x180010231  mov     rcx, [rbp+hKey]; hKey
0x180010235  test    rcx, rcx
0x180010238  jz      short loc_180010240
0x18001023a  call    cs:__imp_RegCloseKey
0x180010240  mov     eax, edi
0x180010242  add     rsp, 50h
0x180010246  pop     r12
0x180010248  pop     rdi
0x180010249  pop     rsi
0x18001024a  pop     rbx
0x18001024b  pop     rbp
0x18001024c  retn
```
