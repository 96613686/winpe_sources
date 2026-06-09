# LoadSecurityModule

- ea: `0x1800180d8`
- end: `0x180018463`
- name: `LoadSecurityModule`
- size: `907`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b570`

## callees

- `0x1800180d8`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800182ca`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001832f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800182ca`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001832f`
- `KERNEL32!GetProcAddress` at `0x1800183b4`
- `KERNEL32!GetProcAddress` at `0x1800183d4`
- `KERNEL32!GetProcAddress` at `0x1800183b4`
- `KERNEL32!GetProcAddress` at `0x1800183d4`
- `KERNEL32!LoadLibraryExW` at `0x180018345`
- `KERNEL32!LoadLibraryExW` at `0x180018345`
- `KERNEL32!HeapAlloc` at `0x180018217`
- `KERNEL32!HeapAlloc` at `0x1800182f3`
- `KERNEL32!HeapAlloc` at `0x180018217`
- `KERNEL32!HeapAlloc` at `0x1800182f3`
- `KERNEL32!GetLastError` at `0x180018225`
- `KERNEL32!GetLastError` at `0x1800182d7`
- `KERNEL32!GetLastError` at `0x180018302`
- `KERNEL32!GetLastError` at `0x180018357`
- `KERNEL32!GetLastError` at `0x1800183e6`
- `KERNEL32!GetLastError` at `0x180018225`
- `KERNEL32!GetLastError` at `0x1800182d7`
- `KERNEL32!GetLastError` at `0x180018302`
- `KERNEL32!GetLastError` at `0x180018357`
- `KERNEL32!GetLastError` at `0x1800183e6`
- `KERNEL32!HeapFree` at `0x180018429`
- `KERNEL32!HeapFree` at `0x180018441`
- `KERNEL32!HeapFree` at `0x180018429`
- `KERNEL32!HeapFree` at `0x180018441`
- `ADVAPI32!RegOpenKeyW` at `0x18001811a`
- `ADVAPI32!RegOpenKeyW` at `0x18001811a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800181bc`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800181bc`
- `ADVAPI32!RegQueryValueExW` at `0x180018262`
- `ADVAPI32!RegQueryValueExW` at `0x180018262`
- `ADVAPI32!RegCloseKey` at `0x18001844b`
- `ADVAPI32!RegCloseKey` at `0x18001844b`
- `rtutils!RouterLogEventW` at `0x1800181f8`
- `rtutils!RouterLogEventW` at `0x180018296`
- `rtutils!RouterLogEventW` at `0x1800181f8`
- `rtutils!RouterLogEventW` at `0x180018296`
- `rtutils!RouterLogEventStringW` at `0x180018161`
- `rtutils!RouterLogEventStringW` at `0x180018417`
- `rtutils!RouterLogEventStringW` at `0x180018161`
- `rtutils!RouterLogEventStringW` at `0x180018417`

## string_xrefs

- `0x1800180f4`: `Software\Microsoft\RAS\SecurityHost`
- `0x18001825b`: `DllPath`
- `0x1800183aa`: `RasSecurityDialogBegin`
- `0x1800183cd`: `RasSecurityDialogEnd`

## pseudocode

```c
__int64 LoadSecurityModule()
{
  LSTATUS v0; // eax
  DWORD v1; // ebx
  DWORD LastError; // eax
  DWORD v4; // r8d
  BYTE *v5; // rsi
  DWORD v6; // eax
  DWORD v7; // r8d
  DWORD v8; // eax
  DWORD v9; // r14d
  WCHAR *v10; // rax
  DWORD v11; // eax
  HMODULE Library; // rax
  DWORD v13; // eax
  DWORD dwErrorCode; // [rsp+28h] [rbp-31h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp+7h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp+Bh] BYREF
  LPCWSTR lpLibFileName; // [rsp+68h] [rbp+Fh] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+17h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+C0h] [rbp+67h] BYREF
  DWORD cbMaxValueLen; // [rsp+C8h] [rbp+6Fh] BYREF
  DWORD Type; // [rsp+D0h] [rbp+77h] BYREF
  DWORD cValues; // [rsp+D8h] [rbp+7Fh] BYREF

  phkResult = 0;
  cbMaxValueLen = 0;
  cbMaxValueNameLen = 0;
  cValues = 0;
  Type = 0;
  lpLibFileName = 0;
  v0 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\RAS\\SecurityHost", &phkResult);
  v1 = v0;
  if ( v0 == 2 )
    return 0;
  if ( !v0 )
  {
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    LastError = RegQueryInfoKeyW(
                  phkResult,
                  0,
                  0,
                  0,
                  &cSubKeys,
                  &cbMaxSubKeyLen,
                  0,
                  &cValues,
                  &cbMaxValueNameLen,
                  &cbMaxValueLen,
                  0,
                  0);
    v1 = LastError;
    ++cbMaxValueNameLen;
    if ( LastError )
    {
      if ( !dword_1800C84E4 )
      {
LABEL_39:
        if ( lpLibFileName )
          HeapFree(hHeap, 0, (LPVOID)lpLibFileName);
        RegCloseKey(phkResult);
        return v1;
      }
      v4 = 20002;
LABEL_9:
      RouterLogEventW(hLogHandle, 1u, v4, 0, 0, LastError);
      goto LABEL_39;
    }
    v5 = (BYTE *)HeapAlloc(hHeap, 8u, cbMaxValueLen + 2LL);
    if ( !v5 )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( !dword_1800C84E4 )
        goto LABEL_39;
      v4 = 20104;
      goto LABEL_9;
    }
    v6 = RegQueryValueExW(phkResult, L"DllPath", 0, &Type, v5, &cbMaxValueLen);
    v1 = v6;
    if ( !v6 )
    {
      if ( Type - 1 > 1 )
      {
        v1 = 1015;
        if ( dword_1800C84E4 )
        {
          dwErrorCode = 1015;
          goto LABEL_16;
        }
LABEL_38:
        HeapFree(hHeap, 0, v5);
        goto LABEL_39;
      }
      v8 = ExpandEnvironmentStringsW((LPCWSTR)v5, 0, 0);
      v9 = v8;
      if ( v8 )
      {
        v10 = (WCHAR *)HeapAlloc(hHeap, 8u, 2LL * v8);
        lpLibFileName = v10;
        if ( !v10 )
        {
          v11 = GetLastError();
          v1 = v11;
          if ( dword_1800C84E4 )
          {
            dwErrorCode = v11;
            v7 = 20104;
            goto LABEL_17;
          }
          goto LABEL_38;
        }
        if ( ExpandEnvironmentStringsW((LPCWSTR)v5, v10, v9) )
        {
          Library = LoadLibraryExW(lpLibFileName, 0, 0x1000u);
          hModule = Library;
          if ( Library )
          {
            qword_1800C85E0 = (__int64)GetProcAddress(Library, "RasSecurityDialogBegin");
            if ( !qword_1800C85E0 || (qword_1800C85E8 = (__int64)GetProcAddress(hModule, "RasSecurityDialogEnd")) == 0 )
            {
              v13 = GetLastError();
              v1 = v13;
              if ( dword_1800C84E4 )
                RouterLogEventStringW(hLogHandle, 1u, 0x4E7Cu, 0, 0, v13, 0);
            }
          }
          else
          {
            v1 = GetLastError();
            if ( v1 - 191 <= 2 )
            {
              if ( dword_1800C84E4 )
                RouterLogEventW(hLogHandle, 1u, 0x4EEBu, 1u, (LPWSTR *)&lpLibFileName, 0);
            }
            else if ( dword_1800C84E4 )
            {
              RouterLogEventStringW(hLogHandle, 1u, 0x4E7Cu, 0, 0, v1, 0);
            }
          }
          goto LABEL_38;
        }
      }
      v6 = GetLastError();
      v1 = v6;
    }
    if ( dword_1800C84E4 )
    {
      dwErrorCode = v6;
LABEL_16:
      v7 = 20002;
LABEL_17:
      RouterLogEventW(hLogHandle, 1u, v7, 0, 0, dwErrorCode);
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  if ( dword_1800C84E4 )
    RouterLogEventStringW(hLogHandle, 1u, 0x4E7Bu, 0, 0, v0, 0);
  return v1;
}

```

## disassembly

```asm
0x1800180d8  push    rbp
0x1800180da  push    rbx
0x1800180db  push    rsi
0x1800180dc  push    rdi
0x1800180dd  push    r14
0x1800180df  push    r15
0x1800180e1  lea     rbp, [rsp-2Fh]
0x1800180e6  sub     rsp, 88h
0x1800180ed  xor     r15d, r15d
0x1800180f0  lea     r8, [rbp+57h+phkResult]; phkResult
0x1800180f4  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\RAS\\SecurityHost"
0x1800180fb  mov     [rbp+57h+phkResult], r15
0x1800180ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018106  mov     [rbp+57h+cbMaxValueLen], r15d
0x18001810a  mov     [rbp+57h+cbMaxValueNameLen], r15d
0x18001810e  mov     [rbp+57h+cValues], r15d
0x180018112  mov     [rbp+57h+Type], r15d
0x180018116  mov     [rbp+57h+lpLibFileName], r15
0x18001811a  call    cs:__imp_RegOpenKeyW
0x180018120  mov     ebx, eax
0x180018122  cmp     eax, 2
0x180018125  jnz     short loc_18001812E
0x180018127  xor     eax, eax
0x180018129  jmp     loc_180018453
0x18001812e  test    ebx, ebx
0x180018130  jz      short loc_18001816C
0x180018132  cmp     cs:dword_1800C84E4, r15d
0x180018139  jbe     loc_180018451
0x18001813f  mov     rcx, cs:hLogHandle; hLogHandle
0x180018146  xor     r9d, r9d; dwSubStringCount
0x180018149  mov     [rsp+0B0h+dwErrorIndex], r15d; dwErrorIndex
0x18001814e  mov     r8d, 4E7Bh; dwMessageId
0x180018154  mov     [rsp+0B0h+dwErrorCode], ebx; dwErrorCode
0x180018158  mov     [rsp+0B0h+plpszSubStringArray], r15; plpszSubStringArray
0x18001815d  lea     edx, [r9+1]; dwEventType
0x180018161  call    cs:__imp_RouterLogEventStringW
0x180018167  jmp     loc_180018451
0x18001816c  mov     rcx, [rbp+57h+phkResult]; hKey
0x180018170  lea     rax, [rbp+57h+cbMaxValueLen]
0x180018174  mov     [rsp+0B0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180018179  xor     r9d, r9d; lpReserved
0x18001817c  mov     [rsp+0B0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180018181  xor     r8d, r8d; lpcchClass
0x180018184  mov     [rsp+0B0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180018189  xor     edx, edx; lpClass
0x18001818b  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18001818f  mov     [rbp+57h+cSubKeys], r15d
0x180018193  mov     [rsp+0B0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180018198  lea     rax, [rbp+57h+cValues]
0x18001819c  mov     [rsp+0B0h+lpcValues], rax; lpcValues
0x1800181a1  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800181a5  mov     qword ptr [rsp+0B0h+dwErrorIndex], r15; lpcbMaxClassLen
0x1800181aa  mov     qword ptr [rsp+0B0h+dwErrorCode], rax; lpcbMaxSubKeyLen
0x1800181af  lea     rax, [rbp+57h+cSubKeys]
0x1800181b3  mov     [rsp+0B0h+plpszSubStringArray], rax; lpcSubKeys
0x1800181b8  mov     [rbp+57h+cbMaxSubKeyLen], r15d
0x1800181bc  call    cs:__imp_RegQueryInfoKeyW
0x1800181c2  mov     edi, 1
0x1800181c7  mov     ebx, eax
0x1800181c9  add     [rbp+57h+cbMaxValueNameLen], edi
0x1800181cc  test    eax, eax
0x1800181ce  jz      short loc_180018203
0x1800181d0  cmp     cs:dword_1800C84E4, r15d
0x1800181d7  jbe     loc_18001842F
0x1800181dd  mov     r8d, 4E22h; dwMessageId
0x1800181e3  mov     rcx, cs:hLogHandle; hLogHandle
0x1800181ea  xor     r9d, r9d; dwSubStringCount
0x1800181ed  mov     [rsp+0B0h+dwErrorCode], eax; dwErrorCode
0x1800181f1  mov     edx, edi; dwEventType
0x1800181f3  mov     [rsp+0B0h+plpszSubStringArray], r15; plpszSubStringArray
0x1800181f8  call    cs:__imp_RouterLogEventW
0x1800181fe  jmp     loc_18001842F
0x180018203  mov     r8d, [rbp+57h+cbMaxValueLen]
0x180018207  mov     edx, 8; dwFlags
0x18001820c  mov     rcx, cs:hHeap; hHeap
0x180018213  add     r8, 2; dwBytes
0x180018217  call    cs:__imp_HeapAlloc
0x18001821d  mov     rsi, rax
0x180018220  test    rax, rax
0x180018223  jnz     short loc_180018242
0x180018225  call    cs:__imp_GetLastError
0x18001822b  cmp     cs:dword_1800C84E4, r15d
0x180018232  mov     ebx, eax
0x180018234  jbe     loc_18001842F
0x18001823a  mov     r8d, 4E88h
0x180018240  jmp     short loc_1800181E3
0x180018242  mov     rcx, [rbp+57h+phkResult]; hKey
0x180018246  lea     rax, [rbp+57h+cbMaxValueLen]
0x18001824a  mov     qword ptr [rsp+0B0h+dwErrorCode], rax; lpcbData
0x18001824f  lea     r9, [rbp+57h+Type]; lpType
0x180018253  xor     r8d, r8d; lpReserved
0x180018256  mov     [rsp+0B0h+plpszSubStringArray], rsi; lpData
0x18001825b  lea     rdx, aDllpath; "DllPath"
0x180018262  call    cs:__imp_RegQueryValueExW
0x180018268  mov     ebx, eax
0x18001826a  test    eax, eax
0x18001826c  jz      short loc_1800182A1
0x18001826e  cmp     cs:dword_1800C84E4, r15d
0x180018275  jbe     loc_18001841D
0x18001827b  mov     [rsp+0B0h+dwErrorCode], eax; dwErrorCode
0x18001827f  mov     r8d, 4E22h; dwMessageId
0x180018285  xor     r9d, r9d; dwSubStringCount
0x180018288  mov     [rsp+0B0h+plpszSubStringArray], r15; plpszSubStringArray
0x18001828d  mov     rcx, cs:hLogHandle; hLogHandle
0x180018294  mov     edx, edi; dwEventType
0x180018296  call    cs:__imp_RouterLogEventW
0x18001829c  jmp     loc_18001841D
0x1800182a1  mov     eax, [rbp+57h+Type]
0x1800182a4  dec     eax
0x1800182a6  cmp     eax, edi
0x1800182a8  jbe     short loc_1800182C2
0x1800182aa  cmp     cs:dword_1800C84E4, r15d
0x1800182b1  mov     ebx, 3F7h
0x1800182b6  jbe     loc_18001841D
0x1800182bc  mov     [rsp+0B0h+dwErrorCode], ebx
0x1800182c0  jmp     short loc_18001827F
0x1800182c2  xor     r8d, r8d; nSize
0x1800182c5  xor     edx, edx; lpDst
0x1800182c7  mov     rcx, rsi; lpSrc
0x1800182ca  call    cs:__imp_ExpandEnvironmentStringsW
0x1800182d0  mov     r14d, eax
0x1800182d3  test    eax, eax
0x1800182d5  jnz     short loc_1800182E1
0x1800182d7  call    cs:__imp_GetLastError
0x1800182dd  mov     ebx, eax
0x1800182df  jmp     short loc_18001826E
0x1800182e1  mov     rcx, cs:hHeap; hHeap
0x1800182e8  mov     r8, r14
0x1800182eb  add     r8, r8; dwBytes
0x1800182ee  mov     edx, 8; dwFlags
0x1800182f3  call    cs:__imp_HeapAlloc
0x1800182f9  mov     [rbp+57h+lpLibFileName], rax
0x1800182fd  test    rax, rax
0x180018300  jnz     short loc_180018326
0x180018302  call    cs:__imp_GetLastError
0x180018308  cmp     cs:dword_1800C84E4, r15d
0x18001830f  mov     ebx, eax
0x180018311  jbe     loc_18001841D
0x180018317  mov     [rsp+0B0h+dwErrorCode], eax
0x18001831b  mov     r8d, 4E88h
0x180018321  jmp     loc_180018285
0x180018326  mov     r8d, r14d; nSize
0x180018329  mov     rdx, rax; lpDst
0x18001832c  mov     rcx, rsi; lpSrc
0x18001832f  call    cs:__imp_ExpandEnvironmentStringsW
0x180018335  test    eax, eax
0x180018337  jz      short loc_1800182D7
0x180018339  mov     rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x18001833d  xor     edx, edx; hFile
0x18001833f  mov     r8d, 1000h; dwFlags
0x180018345  call    cs:__imp_LoadLibraryExW
0x18001834b  mov     cs:hModule, rax
0x180018352  test    rax, rax
0x180018355  jnz     short loc_1800183AA
0x180018357  call    cs:__imp_GetLastError
0x18001835d  mov     ebx, eax
0x18001835f  add     eax, 0FFFFFF41h
0x180018364  cmp     eax, 2
0x180018367  jbe     short loc_180018381
0x180018369  cmp     cs:dword_1800C84E4, r15d
0x180018370  jbe     loc_18001841D
0x180018376  mov     [rsp+0B0h+dwErrorIndex], r15d
0x18001837b  mov     [rsp+0B0h+dwErrorCode], ebx
0x18001837f  jmp     short loc_180018400
0x180018381  cmp     cs:dword_1800C84E4, r15d
0x180018388  jbe     loc_18001841D
0x18001838e  lea     rax, [rbp+57h+lpLibFileName]
0x180018392  mov     [rsp+0B0h+dwErrorCode], r15d
0x180018397  mov     [rsp+0B0h+plpszSubStringArray], rax
0x18001839c  mov     r9d, edi
0x18001839f  mov     r8d, 4EEBh
0x1800183a5  jmp     loc_18001828D
0x1800183aa  lea     rdx, aRassecuritydia_0; "RasSecurityDialogBegin"
0x1800183b1  mov     rcx, rax; hModule
0x1800183b4  call    cs:__imp_GetProcAddress
0x1800183ba  mov     cs:qword_1800C85E0, rax
0x1800183c1  test    rax, rax
0x1800183c4  jz      short loc_1800183E6
0x1800183c6  mov     rcx, cs:hModule; hModule
0x1800183cd  lea     rdx, aRassecuritydia; "RasSecurityDialogEnd"
0x1800183d4  call    cs:__imp_GetProcAddress
0x1800183da  mov     cs:qword_1800C85E8, rax
0x1800183e1  test    rax, rax
0x1800183e4  jnz     short loc_18001841D
0x1800183e6  call    cs:__imp_GetLastError
0x1800183ec  cmp     cs:dword_1800C84E4, r15d
0x1800183f3  mov     ebx, eax
0x1800183f5  jbe     short loc_18001841D
0x1800183f7  mov     [rsp+0B0h+dwErrorIndex], r15d; dwErrorIndex
0x1800183fc  mov     [rsp+0B0h+dwErrorCode], eax; dwErrorCode
0x180018400  mov     rcx, cs:hLogHandle; hLogHandle
0x180018407  xor     r9d, r9d; dwSubStringCount
0x18001840a  mov     r8d, 4E7Ch; dwMessageId
0x180018410  mov     [rsp+0B0h+plpszSubStringArray], r15; plpszSubStringArray
0x180018415  mov     edx, edi; dwEventType
0x180018417  call    cs:__imp_RouterLogEventStringW
0x18001841d  mov     rcx, cs:hHeap; hHeap
0x180018424  mov     r8, rsi; lpMem
0x180018427  xor     edx, edx; dwFlags
0x180018429  call    cs:__imp_HeapFree
0x18001842f  mov     r8, [rbp+57h+lpLibFileName]; lpMem
0x180018433  test    r8, r8
0x180018436  jz      short loc_180018447
0x180018438  mov     rcx, cs:hHeap; hHeap
0x18001843f  xor     edx, edx; dwFlags
0x180018441  call    cs:__imp_HeapFree
0x180018447  mov     rcx, [rbp+57h+phkResult]; hKey
0x18001844b  call    cs:__imp_RegCloseKey
0x180018451  mov     eax, ebx
0x180018453  add     rsp, 88h
0x18001845a  pop     r15
0x18001845c  pop     r14
0x18001845e  pop     rdi
0x18001845f  pop     rsi
0x180018460  pop     rbx
0x180018461  pop     rbp
0x180018462  retn
```
