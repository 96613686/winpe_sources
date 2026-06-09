# IsPathUnderKnownFolder(ushort const *,_GUID const &)

- ea: `0x18000f71c`
- end: `0x18000f783`
- name: `?IsPathUnderKnownFolder@@YAHPEBGAEBU_GUID@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(const unsigned __int16 *, KNOWNFOLDERID *rfid)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ad78`

## callees

- `0x18000a8b0`
- `0x18000f71c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f769`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18000f740`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18000f740`

## pseudocode

```c
__int64 __fastcall IsPathUnderKnownFolder(const unsigned __int16 *a1, KNOWNFOLDERID *rfid)
{
  unsigned int IsSubFolder; // ebx
  PWSTR ppszPath; // [rsp+40h] [rbp+18h] BYREF

  IsSubFolder = 0;
  ppszPath = 0;
  if ( SHGetKnownFolderPath(rfid, 0, 0, &ppszPath) >= 0 )
    IsSubFolder = PathIsSubFolder(ppszPath, a1);
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return IsSubFolder;
}

```

## disassembly

```asm
0x18000f71c  mov     [rsp+arg_0], rbx
0x18000f721  push    rdi
0x18000f722  sub     rsp, 20h
0x18000f726  mov     rax, rdx
0x18000f729  lea     r9, [rsp+28h+ppszPath]; ppszPath
0x18000f72e  mov     rdi, rcx
0x18000f731  xor     ebx, ebx
0x18000f733  mov     rcx, rax; rfid
0x18000f736  mov     [rsp+28h+ppszPath], rbx
0x18000f73b  xor     r8d, r8d; hToken
0x18000f73e  xor     edx, edx; dwFlags
0x18000f740  call    cs:__imp_SHGetKnownFolderPath
0x18000f747  nop     dword ptr [rax+rax+00h]
0x18000f74c  test    eax, eax
0x18000f74e  js      short loc_18000F75F
0x18000f750  mov     rcx, [rsp+28h+ppszPath]; unsigned __int16 *
0x18000f755  mov     rdx, rdi; unsigned __int16 *
0x18000f758  call    ?PathIsSubFolder@@YAHPEBG0@Z; PathIsSubFolder(ushort const *,ushort const *)
0x18000f75d  mov     ebx, eax
0x18000f75f  mov     rcx, [rsp+28h+ppszPath]; pv
0x18000f764  test    rcx, rcx
0x18000f767  jz      short loc_18000F775
0x18000f769  call    cs:__imp_CoTaskMemFree
0x18000f770  nop     dword ptr [rax+rax+00h]
0x18000f775  mov     eax, ebx
0x18000f777  mov     rbx, [rsp+28h+arg_0]
0x18000f77c  add     rsp, 20h
0x18000f780  pop     rdi
0x18000f781  retn
```
