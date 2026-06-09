# BuildMsgQueueVolumePath(ushort *,ulong)

- ea: `0x18000ea20`
- end: `0x18000ea89`
- name: `?BuildMsgQueueVolumePath@@YAJPEAGK@Z`
- size: `105`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f694`
- `0x18000f9f0`

## callees

- `0x18000c63c`
- `0x18000ea20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ea76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ea76`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18000ea4a`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18000ea4a`

## pseudocode

```c
__int64 __fastcall BuildMsgQueueVolumePath(unsigned __int16 *a1)
{
  HRESULT v2; // ebx
  PWSTR ppszPath; // [rsp+40h] [rbp+18h] BYREF

  ppszPath = 0;
  v2 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0x8000u, 0, &ppszPath);
  if ( v2 >= 0 )
    v2 = StringCchPrintfW(a1, 0x104u, L"%s\\PushRouter", ppszPath);
  CoTaskMemFree(ppszPath);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000ea20  mov     [rsp+arg_0], rbx
0x18000ea25  push    rdi
0x18000ea26  sub     rsp, 20h
0x18000ea2a  mov     rdi, rcx
0x18000ea2d  mov     [rsp+28h+ppszPath], 0
0x18000ea36  lea     rcx, FOLDERID_LocalAppData; rfid
0x18000ea3d  xor     r8d, r8d; hToken
0x18000ea40  lea     r9, [rsp+28h+ppszPath]; ppszPath
0x18000ea45  mov     edx, 8000h; dwFlags
0x18000ea4a  call    cs:__imp_SHGetKnownFolderPath
0x18000ea50  mov     ebx, eax
0x18000ea52  test    eax, eax
0x18000ea54  js      short loc_18000EA71
0x18000ea56  mov     r9, [rsp+28h+ppszPath]
0x18000ea5b  lea     r8, aSPushrouter; "%s\\PushRouter"
0x18000ea62  mov     edx, 104h; unsigned __int64
0x18000ea67  mov     rcx, rdi; unsigned __int16 *
0x18000ea6a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ea6f  mov     ebx, eax
0x18000ea71  mov     rcx, [rsp+28h+ppszPath]; pv
0x18000ea76  call    cs:__imp_CoTaskMemFree
0x18000ea7c  mov     eax, ebx
0x18000ea7e  mov     rbx, [rsp+28h+arg_0]
0x18000ea83  add     rsp, 20h
0x18000ea87  pop     rdi
0x18000ea88  retn
```
