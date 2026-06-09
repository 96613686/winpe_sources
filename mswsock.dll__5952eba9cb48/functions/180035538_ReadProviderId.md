# ReadProviderId

- ea: `0x180035538`
- end: `0x1800355db`
- name: `ReadProviderId`
- size: `163`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180032294`
- `0x1800328c0`
- `0x180035bc0`

## callees

- `0x1800327a8`
- `0x18003281c`
- `0x180034d30`
- `0x180035538`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800355bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800355bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035567`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035567`

## string_xrefs

- `0x18003557c`: `WARNING: Failed to open provider key`
- `0x1800355a4`: `Failed to read provider ID`

## pseudocode

```c
__int64 __fastcall ReadProviderId(HKEY a1, const WCHAR *a2, __int64 a3)
{
  unsigned int v5; // ebx
  unsigned int Guid; // eax
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  v5 = RegOpenKeyExW(a1, a2, 0, 0xF003Fu, &hKey);
  if ( v5 )
  {
    LogMsgWithProvider(L"WARNING: Failed to open provider key", a2);
  }
  else
  {
    Guid = ReadGuid(hKey, L"WinSock 2.0 Provider ID", a3);
    v5 = Guid;
    if ( Guid )
      LogError(Guid, L"Failed to read provider ID");
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180035538  mov     r11, rsp
0x18003553b  mov     [r11+8], rbx
0x18003553f  mov     [r11+10h], rsi
0x180035543  push    rdi
0x180035544  sub     rsp, 30h
0x180035548  mov     rsi, r8
0x18003554b  mov     qword ptr [r11+20h], 0
0x180035553  lea     rax, [r11+20h]
0x180035557  xor     r8d, r8d; ulOptions
0x18003555a  mov     r9d, 0F003Fh; samDesired
0x180035560  mov     [r11-18h], rax
0x180035564  mov     rdi, rdx
0x180035567  call    cs:__imp_RegOpenKeyExW
0x18003556e  nop     dword ptr [rax+rax+00h]
0x180035573  mov     ebx, eax
0x180035575  test    eax, eax
0x180035577  jz      short loc_18003558A
0x180035579  mov     rdx, rdi
0x18003557c  lea     rcx, aWarningFailedT; "WARNING: Failed to open provider key"
0x180035583  call    LogMsgWithProvider
0x180035588  jmp     short loc_1800355B2
0x18003558a  mov     rcx, [rsp+38h+hKey]
0x18003558f  lea     rdx, aWinsock20Provi; "WinSock 2.0 Provider ID"
0x180035596  mov     r8, rsi
0x180035599  call    ReadGuid
0x18003559e  mov     ebx, eax
0x1800355a0  test    eax, eax
0x1800355a2  jz      short loc_1800355B2
0x1800355a4  lea     rdx, aFailedToReadPr; "Failed to read provider ID"
0x1800355ab  mov     ecx, eax
0x1800355ad  call    LogError
0x1800355b2  mov     rcx, [rsp+38h+hKey]; hKey
0x1800355b7  test    rcx, rcx
0x1800355ba  jz      short loc_1800355C8
0x1800355bc  call    cs:__imp_RegCloseKey
0x1800355c3  nop     dword ptr [rax+rax+00h]
0x1800355c8  mov     rsi, [rsp+38h+arg_8]
0x1800355cd  mov     eax, ebx
0x1800355cf  mov     rbx, [rsp+38h+arg_0]
0x1800355d4  add     rsp, 30h
0x1800355d8  pop     rdi
0x1800355d9  retn
```
