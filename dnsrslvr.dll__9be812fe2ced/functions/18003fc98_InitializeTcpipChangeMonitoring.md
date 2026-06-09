# InitializeTcpipChangeMonitoring

- ea: `0x18003fc98`
- end: `0x18003fe34`
- name: `InitializeTcpipChangeMonitoring`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002c980`

## callees

- `0x18003fc98`
- `0x180046ec0`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fdef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fdef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fdff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fdff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fd11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fd11`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18003fdba`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18003fdba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003fd69`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003fd69`

## string_xrefs

- `0x18003fce3`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x18003fcec`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall InitializeTcpipChangeMonitoring(unsigned int a1)
{
  const WCHAR *v2; // rdx
  unsigned int v3; // eax
  void *v4; // rdi
  unsigned int v5; // ebx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  unsigned int v8; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 10, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids, a1);
  v2 = L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces";
  if ( !a1 )
    v2 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces";
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x20019u, &hKey);
  if ( v3 )
  {
    v4 = 0;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 11, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids, v3);
    v5 = 0;
    goto LABEL_9;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v4 = EventW;
  if ( EventW )
  {
    v8 = RegNotifyChangeKeyValue(hKey, 1, 4u, EventW, 1);
    v5 = v8;
    if ( !v8 )
    {
LABEL_9:
      if ( a1 )
      {
        g_hTcpipv6Key = hKey;
        g_hTcpipv6Change = v4;
      }
      else
      {
        g_hTcpipv4Key = hKey;
        g_hTcpipv4Change = v4;
      }
      return v5;
    }
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 13, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids, v8);
    CloseHandle(v4);
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 12, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids, LastError);
    if ( !v5 )
      goto LABEL_9;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x18003fc98  mov     [rsp+arg_8], rbx
0x18003fc9d  mov     [rsp+arg_10], rsi
0x18003fca2  push    rdi
0x18003fca3  sub     rsp, 40h
0x18003fca7  mov     rax, cs:__security_cookie
0x18003fcae  xor     rax, rsp
0x18003fcb1  mov     [rsp+48h+var_10], rax
0x18003fcb6  mov     esi, ecx
0x18003fcb8  mov     [rsp+48h+hKey], 0
0x18003fcc1  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003fcc8  jz      short loc_18003FCE3
0x18003fcca  mov     edx, 0Ah
0x18003fccf  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18003fcd6  mov     ecx, 40Bh
0x18003fcdb  mov     r9d, esi
0x18003fcde  call    WPP_SF_d
0x18003fce3  lea     rax, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Tc"...
0x18003fcea  test    esi, esi
0x18003fcec  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Tc"...
0x18003fcf3  mov     r9d, 20019h; samDesired
0x18003fcf9  cmovz   rdx, rax; lpSubKey
0x18003fcfd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003fd04  lea     rax, [rsp+48h+hKey]
0x18003fd09  xor     r8d, r8d; ulOptions
0x18003fd0c  mov     [rsp+48h+phkResult], rax; phkResult
0x18003fd11  call    cs:__imp_RegOpenKeyExW
0x18003fd17  test    eax, eax
0x18003fd19  jz      short loc_18003FD5F
0x18003fd1b  xor     edi, edi
0x18003fd1d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003fd24  jz      short loc_18003FD3D
0x18003fd26  lea     edx, [rdi+0Bh]
0x18003fd29  mov     ecx, 40Bh
0x18003fd2e  mov     r9d, eax
0x18003fd31  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18003fd38  call    WPP_SF_d
0x18003fd3d  xor     ebx, ebx
0x18003fd3f  mov     rax, [rsp+48h+hKey]
0x18003fd44  test    esi, esi
0x18003fd46  jz      loc_18003FE07
0x18003fd4c  mov     cs:g_hTcpipv6Key, rax
0x18003fd53  mov     cs:g_hTcpipv6Change, rdi
0x18003fd5a  jmp     loc_18003FE15
0x18003fd5f  xor     r9d, r9d; lpName
0x18003fd62  xor     r8d, r8d; bInitialState
0x18003fd65  xor     edx, edx; bManualReset
0x18003fd67  xor     ecx, ecx; lpEventAttributes
0x18003fd69  call    cs:__imp_CreateEventW
0x18003fd6f  mov     rdi, rax
0x18003fd72  test    rax, rax
0x18003fd75  jnz     short loc_18003FDA5
0x18003fd77  call    cs:__imp_GetLastError
0x18003fd7d  mov     ebx, eax
0x18003fd7f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003fd86  jz      short loc_18003FD9F
0x18003fd88  lea     edx, [rdi+0Ch]
0x18003fd8b  mov     ecx, 40Bh
0x18003fd90  mov     r9d, eax
0x18003fd93  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18003fd9a  call    WPP_SF_d
0x18003fd9f  test    ebx, ebx
0x18003fda1  jnz     short loc_18003FDF5
0x18003fda3  jmp     short loc_18003FD3F
0x18003fda5  mov     rcx, [rsp+48h+hKey]; hKey
0x18003fdaa  mov     edx, 1; bWatchSubtree
0x18003fdaf  mov     r9, rdi; hEvent
0x18003fdb2  mov     dword ptr [rsp+48h+phkResult], edx; fAsynchronous
0x18003fdb6  lea     r8d, [rdx+3]; dwNotifyFilter
0x18003fdba  call    cs:__imp_RegNotifyChangeKeyValue
0x18003fdc0  mov     ebx, eax
0x18003fdc2  test    eax, eax
0x18003fdc4  jz      loc_18003FD3F
0x18003fdca  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003fdd1  jz      short loc_18003FDEC
0x18003fdd3  mov     edx, 0Dh
0x18003fdd8  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18003fddf  mov     ecx, 40Bh
0x18003fde4  mov     r9d, eax
0x18003fde7  call    WPP_SF_d
0x18003fdec  mov     rcx, rdi; hObject
0x18003fdef  call    cs:__imp_CloseHandle
0x18003fdf5  mov     rcx, [rsp+48h+hKey]; hKey
0x18003fdfa  test    rcx, rcx
0x18003fdfd  jz      short loc_18003FE15
0x18003fdff  call    cs:__imp_RegCloseKey
0x18003fe05  jmp     short loc_18003FE15
0x18003fe07  mov     cs:g_hTcpipv4Key, rax
0x18003fe0e  mov     cs:g_hTcpipv4Change, rdi
0x18003fe15  mov     eax, ebx
0x18003fe17  mov     rcx, [rsp+48h+var_10]
0x18003fe1c  xor     rcx, rsp; StackCookie
0x18003fe1f  call    __security_check_cookie
0x18003fe24  mov     rbx, [rsp+48h+arg_8]
0x18003fe29  mov     rsi, [rsp+48h+arg_10]
0x18003fe2e  add     rsp, 40h
0x18003fe32  pop     rdi
0x18003fe33  retn
```
