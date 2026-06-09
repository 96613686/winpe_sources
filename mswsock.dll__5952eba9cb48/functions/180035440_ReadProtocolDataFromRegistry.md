# ReadProtocolDataFromRegistry

- ea: `0x180035440`
- end: `0x180035530`
- name: `ReadProtocolDataFromRegistry`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800328c0`

## callees

- `0x1800327a8`
- `0x180034b9c`
- `0x180035440`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003550a`
- `ntdll!RtlFreeHeap` at `0x18003550a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800354e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800354e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035479`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035479`

## string_xrefs

- `0x18003548b`: `Failed to open provider`
- `0x1800354bc`: `Failed to read provider data`

## pseudocode

```c
__int64 __fastcall ReadProtocolDataFromRegistry(HKEY a1, const WCHAR *a2, _QWORD *a3, _DWORD *a4)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int Binary; // eax
  HKEY hKey; // [rsp+40h] [rbp-38h] BYREF

  hKey = 0;
  v6 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 )
  {
    LogError(v6, L"Failed to open provider");
  }
  else
  {
    Binary = ReadBinary(hKey, L"WinSock 1.1 Provider Data");
    v7 = Binary;
    if ( Binary )
    {
      LogError(Binary, L"Failed to read provider data");
    }
    else
    {
      *a3 = 0;
      *a4 = 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v7 )
  {
    *a3 = 0;
    *a4 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180035440  mov     rax, rsp
0x180035443  push    rbx
0x180035444  push    rsi
0x180035445  push    rdi
0x180035446  push    r14
0x180035448  sub     rsp, 58h
0x18003544c  mov     dword ptr [rax-48h], 0
0x180035453  mov     rsi, r9
0x180035456  mov     qword ptr [rax-38h], 0
0x18003545e  lea     rax, [rax-38h]
0x180035462  mov     r14, r8
0x180035465  mov     [rsp+78h+phkResult], rax; phkResult
0x18003546a  xor     edi, edi
0x18003546c  mov     r9d, 20019h; samDesired
0x180035472  mov     [rax-8], rdi
0x180035476  xor     r8d, r8d; ulOptions
0x180035479  call    cs:__imp_RegOpenKeyExW
0x180035480  nop     dword ptr [rax+rax+00h]
0x180035485  mov     ebx, eax
0x180035487  test    eax, eax
0x180035489  jz      short loc_18003549B
0x18003548b  lea     rdx, aFailedToOpenPr_2; "Failed to open provider"
0x180035492  mov     ecx, eax
0x180035494  call    LogError
0x180035499  jmp     short loc_1800354DF
0x18003549b  mov     rcx, [rsp+78h+hKey]; hKey
0x1800354a0  lea     r9, [rsp+78h+var_48]
0x1800354a5  lea     r8, [rsp+78h+var_40]
0x1800354aa  lea     rdx, aWinsock11Provi; "WinSock 1.1 Provider Data"
0x1800354b1  call    ReadBinary
0x1800354b6  mov     ebx, eax
0x1800354b8  test    eax, eax
0x1800354ba  jz      short loc_1800354D1
0x1800354bc  lea     rdx, aFailedToReadPr_0; "Failed to read provider data"
0x1800354c3  mov     ecx, eax
0x1800354c5  call    LogError
0x1800354ca  mov     rdi, [rsp+78h+var_40]
0x1800354cf  jmp     short loc_1800354DF
0x1800354d1  mov     rdi, [rsp+78h+var_40]
0x1800354d6  mov     eax, [rsp+78h+var_48]
0x1800354da  mov     [r14], rdi
0x1800354dd  mov     [rsi], eax
0x1800354df  mov     rcx, [rsp+78h+hKey]; hKey
0x1800354e4  test    rcx, rcx
0x1800354e7  jz      short loc_1800354F5
0x1800354e9  call    cs:__imp_RegCloseKey
0x1800354f0  nop     dword ptr [rax+rax+00h]
0x1800354f5  test    ebx, ebx
0x1800354f7  jz      short loc_180035523
0x1800354f9  test    rdi, rdi
0x1800354fc  jz      short loc_180035516
0x1800354fe  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180035505  mov     r8, rdi; P
0x180035508  xor     edx, edx; Flags
0x18003550a  call    cs:__imp_RtlFreeHeap
0x180035511  nop     dword ptr [rax+rax+00h]
0x180035516  mov     qword ptr [r14], 0
0x18003551d  mov     dword ptr [rsi], 0
0x180035523  mov     eax, ebx
0x180035525  add     rsp, 58h
0x180035529  pop     r14
0x18003552b  pop     rdi
0x18003552c  pop     rsi
0x18003552d  pop     rbx
0x18003552e  retn
```
