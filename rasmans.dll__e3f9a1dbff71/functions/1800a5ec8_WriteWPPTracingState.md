# WriteWPPTracingState

- ea: `0x1800a5ec8`
- end: `0x1800a6110`
- name: `WriteWPPTracingState`
- size: `584`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a5b38`

## callees

- `0x18000e564`
- `0x1800a442c`
- `0x1800a5ec8`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a60e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a60e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a5fe0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a600d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a603a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a6095`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a60d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a5fe0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a600d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a603a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a6095`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a60d1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a5fa8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a5fa8`

## string_xrefs

- `0x1800a5f54`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Tracing\Microsoft\RemoteAccess\`

## pseudocode

```c
__int64 __fastcall WriteWPPTracingState(__int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // rdi
  __int64 v4; // rax
  const BYTE *v5; // rdx
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v9[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v10[524]; // [rsp+64h] [rbp-9Ch] BYREF
  WCHAR SubKey[2]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v12[524]; // [rsp+274h] [rbp+174h] BYREF

  hKey = 0;
  *(_DWORD *)SubKey = 0;
  v2 = 0;
  memset_0(v12, 0, 0x206u);
  *(_DWORD *)v9 = 0;
  memset_0(v10, 0, 0x206u);
  if ( a1 && *(_QWORD *)(a1 + 32) )
  {
    StringCchPrintfW(
      SubKey,
      0x105u,
      L"%s%s",
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\Microsoft\\RemoteAccess\\",
      a1 + 562);
    if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0) )
    {
      *(_DWORD *)Data = *(_DWORD *)a1;
      RegSetValueExW(hKey, L"Active", 0, 4u, Data, 4u);
      *(_DWORD *)Data = *(_DWORD *)(a1 + 4);
      RegSetValueExW(hKey, L"ControlFlags", 0, 4u, Data, 4u);
      *(_DWORD *)Data = *(_DWORD *)(a1 + 8);
      RegSetValueExW(hKey, L"ControlLevel", 0, 4u, Data, 4u);
      ConvertGuid2String(a1 + 12, 261, v9);
      v3 = -1;
      v4 = -1;
      do
        ++v4;
      while ( *(_WORD *)&v9[2 * v4] );
      v2 = 1;
      RegSetValueExW(hKey, L"Guid", 0, 1u, v9, 2 * v4 + 2);
      v5 = (const BYTE *)(*(_QWORD *)(a1 + 32) + *(unsigned int *)(*(_QWORD *)(a1 + 32) + 112LL));
      do
        ++v3;
      while ( *(_WORD *)&v5[2 * v3] );
      RegSetValueExW(hKey, L"LogFileName", 0, 1u, v5, 2 * v3 + 2);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x1800a5ec8  mov     [rsp-8+arg_8], rbx
0x1800a5ecd  mov     [rsp-8+arg_10], rsi
0x1800a5ed2  push    rbp
0x1800a5ed3  push    rdi
0x1800a5ed4  push    r14
0x1800a5ed6  lea     rbp, [rsp-390h]
0x1800a5ede  sub     rsp, 490h
0x1800a5ee5  mov     rax, cs:__security_cookie
0x1800a5eec  xor     rax, rsp
0x1800a5eef  mov     [rbp+3A0h+var_20], rax
0x1800a5ef6  xor     r14d, r14d
0x1800a5ef9  mov     rbx, rcx
0x1800a5efc  mov     edi, 206h
0x1800a5f01  mov     [rsp+4A0h+hKey], r14
0x1800a5f06  mov     r8d, edi; Size
0x1800a5f09  mov     dword ptr [rbp+3A0h+SubKey], r14d
0x1800a5f10  xor     edx, edx; Val
0x1800a5f12  lea     rcx, [rbp+3A0h+var_22C]; void *
0x1800a5f19  mov     esi, r14d
0x1800a5f1c  call    memset_0
0x1800a5f21  mov     r8d, edi; Size
0x1800a5f24  mov     dword ptr [rsp+4A0h+var_440], r14d
0x1800a5f29  xor     edx, edx; Val
0x1800a5f2b  lea     rcx, [rsp+4A0h+var_43C]; void *
0x1800a5f30  call    memset_0
0x1800a5f35  test    rbx, rbx
0x1800a5f38  jz      loc_1800A60E7
0x1800a5f3e  cmp     [rbx+20h], r14
0x1800a5f42  jz      loc_1800A60E7
0x1800a5f48  lea     rax, [rbx+232h]
0x1800a5f4f  mov     edx, 105h; unsigned __int64
0x1800a5f54  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800a5f5b  mov     qword ptr [rsp+4A0h+dwOptions], rax
0x1800a5f60  lea     r8, aSS_0; "%s%s"
0x1800a5f67  lea     rcx, [rbp+3A0h+SubKey]; unsigned __int16 *
0x1800a5f6e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a5f73  mov     [rsp+4A0h+lpdwDisposition], r14; lpdwDisposition
0x1800a5f78  lea     rax, [rsp+4A0h+hKey]
0x1800a5f7d  mov     [rsp+4A0h+phkResult], rax; phkResult
0x1800a5f82  lea     rdx, [rbp+3A0h+SubKey]; lpSubKey
0x1800a5f89  mov     [rsp+4A0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800a5f8e  xor     r9d, r9d; lpClass
0x1800a5f91  mov     [rsp+4A0h+samDesired], 20006h; samDesired
0x1800a5f99  xor     r8d, r8d; Reserved
0x1800a5f9c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a5fa3  mov     [rsp+4A0h+dwOptions], r14d; dwOptions
0x1800a5fa8  call    cs:__imp_RegCreateKeyExW
0x1800a5fae  test    eax, eax
0x1800a5fb0  jnz     loc_1800A60D7
0x1800a5fb6  mov     eax, [rbx]
0x1800a5fb8  lea     edi, [r14+4]
0x1800a5fbc  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800a5fc1  lea     rdx, aActive_0; "Active"
0x1800a5fc8  mov     dword ptr [rsp+4A0h+Data], eax
0x1800a5fcc  mov     r9d, edi; dwType
0x1800a5fcf  lea     rax, [rsp+4A0h+Data]
0x1800a5fd4  mov     [rsp+4A0h+samDesired], edi; cbData
0x1800a5fd8  xor     r8d, r8d; Reserved
0x1800a5fdb  mov     qword ptr [rsp+4A0h+dwOptions], rax; lpData
0x1800a5fe0  call    cs:__imp_RegSetValueExW
0x1800a5fe6  mov     eax, [rbx+4]
0x1800a5fe9  lea     rdx, aControlflags; "ControlFlags"
0x1800a5ff0  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800a5ff5  mov     r9d, edi; dwType
0x1800a5ff8  mov     dword ptr [rsp+4A0h+Data], eax
0x1800a5ffc  xor     r8d, r8d; Reserved
0x1800a5fff  lea     rax, [rsp+4A0h+Data]
0x1800a6004  mov     [rsp+4A0h+samDesired], edi; cbData
0x1800a6008  mov     qword ptr [rsp+4A0h+dwOptions], rax; lpData
0x1800a600d  call    cs:__imp_RegSetValueExW
0x1800a6013  mov     eax, [rbx+8]
0x1800a6016  lea     rdx, aControllevel; "ControlLevel"
0x1800a601d  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800a6022  mov     r9d, edi; dwType
0x1800a6025  mov     dword ptr [rsp+4A0h+Data], eax
0x1800a6029  xor     r8d, r8d; Reserved
0x1800a602c  lea     rax, [rsp+4A0h+Data]
0x1800a6031  mov     [rsp+4A0h+samDesired], edi; cbData
0x1800a6035  mov     qword ptr [rsp+4A0h+dwOptions], rax; lpData
0x1800a603a  call    cs:__imp_RegSetValueExW
0x1800a6040  lea     rcx, [rbx+0Ch]
0x1800a6044  mov     edx, 105h
0x1800a6049  lea     r8, [rsp+4A0h+var_440]
0x1800a604e  call    ConvertGuid2String
0x1800a6053  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a6057  lea     rcx, [rsp+4A0h+var_440]
0x1800a605c  mov     rax, rdi
0x1800a605f  inc     rax
0x1800a6062  cmp     [rcx+rax*2], r14w
0x1800a6067  jnz     short loc_1800A605F
0x1800a6069  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800a606e  lea     eax, ds:2[rax*2]
0x1800a6075  mov     [rsp+4A0h+samDesired], eax; cbData
0x1800a6079  lea     rdx, aGuid_0; "Guid"
0x1800a6080  lea     rax, [rsp+4A0h+var_440]
0x1800a6085  mov     esi, 1
0x1800a608a  mov     r9d, esi; dwType
0x1800a608d  mov     qword ptr [rsp+4A0h+dwOptions], rax; lpData
0x1800a6092  xor     r8d, r8d; Reserved
0x1800a6095  call    cs:__imp_RegSetValueExW
0x1800a609b  mov     rcx, [rbx+20h]
0x1800a609f  mov     edx, [rcx+70h]
0x1800a60a2  add     rdx, rcx
0x1800a60a5  inc     rdi
0x1800a60a8  cmp     [rdx+rdi*2], r14w
0x1800a60ad  jnz     short loc_1800A60A5
0x1800a60af  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800a60b4  lea     eax, ds:2[rdi*2]
0x1800a60bb  mov     [rsp+4A0h+samDesired], eax; cbData
0x1800a60bf  mov     r9d, esi; dwType
0x1800a60c2  mov     qword ptr [rsp+4A0h+dwOptions], rdx; lpData
0x1800a60c7  xor     r8d, r8d; Reserved
0x1800a60ca  lea     rdx, aLogfilename; "LogFileName"
0x1800a60d1  call    cs:__imp_RegSetValueExW
0x1800a60d7  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800a60dc  test    rcx, rcx
0x1800a60df  jz      short loc_1800A60E7
0x1800a60e1  call    cs:__imp_RegCloseKey
0x1800a60e7  mov     eax, esi
0x1800a60e9  mov     rcx, [rbp+3A0h+var_20]
0x1800a60f0  xor     rcx, rsp; StackCookie
0x1800a60f3  call    __security_check_cookie
0x1800a60f8  lea     r11, [rsp+4A0h+var_10]
0x1800a6100  mov     rbx, [r11+28h]
0x1800a6104  mov     rsi, [r11+30h]
0x1800a6108  mov     rsp, r11
0x1800a610b  pop     r14
0x1800a610d  pop     rdi
0x1800a610e  pop     rbp
0x1800a610f  retn
```
