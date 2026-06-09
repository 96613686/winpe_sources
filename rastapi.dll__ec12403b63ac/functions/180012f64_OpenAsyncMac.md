# OpenAsyncMac

- ea: `0x180012f64`
- end: `0x180013022`
- name: `OpenAsyncMac`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180013ccc`

## callees

- `0x18000d92c`
- `0x180011698`
- `0x180012f64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012fe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012fe1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012fb8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012fb8`

## string_xrefs

- `0x180012fce`: `Failed to createfile asyncmac. rc=0x%x`

## pseudocode

```c
__int64 __fastcall OpenAsyncMac(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  DWORD LastError; // edi
  __int64 FileW; // rsi
  __int64 result; // rax
  HANDLE hObject; // [rsp+58h] [rbp+10h] BYREF

  v4 = -1;
  hObject = (HANDLE)-1LL;
  if ( !(unsigned int)FindDeviceOnInterface(a1, a2, a3, a4, &hObject) )
  {
    FileW = -1;
    LastError = 2;
    RasTapiTrace("FindDeviceOnInterface returned FALSE");
    goto LABEL_5;
  }
  LastError = 0;
  FileW = (__int64)CreateFileW(L"\\\\.\\ASYNCMAC", 0xC0000000, 3u, 0, 3u, 0x40000080u, 0);
  if ( FileW != -1 )
  {
LABEL_5:
    v4 = (__int64)hObject;
    goto LABEL_6;
  }
  LastError = GetLastError();
  RasTapiTrace("Failed to createfile asyncmac. rc=0x%x");
  CloseHandle(hObject);
LABEL_6:
  g_hAsyMac = (HANDLE)FileW;
  result = LastError;
  g_hAsyncMacSwenum = (HANDLE)v4;
  return result;
}

```

## disassembly

```asm
0x180012f64  mov     r11, rsp
0x180012f67  mov     [r11+8], rbx
0x180012f6b  mov     [r11+18h], rsi
0x180012f6f  mov     [r11+10h], rdx
0x180012f73  push    rdi
0x180012f74  sub     rsp, 40h
0x180012f78  lea     rax, [r11+10h]
0x180012f7c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012f80  mov     [r11+10h], rbx
0x180012f84  mov     [r11-28h], rax
0x180012f88  call    FindDeviceOnInterface
0x180012f8d  test    eax, eax
0x180012f8f  jz      short loc_180012FE9
0x180012f91  lea     r8d, [rbx+4]; dwShareMode
0x180012f95  xor     edi, edi
0x180012f97  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x180012f9c  lea     rcx, FileName; "\\\\.\\ASYNCMAC"
0x180012fa3  mov     [rsp+48h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x180012fab  xor     r9d, r9d; lpSecurityAttributes
0x180012fae  mov     edx, 0C0000000h; dwDesiredAccess
0x180012fb3  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180012fb8  call    cs:__imp_CreateFileW
0x180012fbe  mov     rsi, rax
0x180012fc1  cmp     rax, rbx
0x180012fc4  jnz     short loc_180012FFD
0x180012fc6  call    cs:__imp_GetLastError
0x180012fcc  mov     edx, eax
0x180012fce  lea     rcx, aFailedToCreate; "Failed to createfile asyncmac. rc=0x%x"
0x180012fd5  mov     edi, eax
0x180012fd7  call    RasTapiTrace
0x180012fdc  mov     rcx, [rsp+48h+hObject]; hObject
0x180012fe1  call    cs:__imp_CloseHandle
0x180012fe7  jmp     short loc_180013002
0x180012fe9  lea     rcx, aFinddeviceonin_0; "FindDeviceOnInterface returned FALSE"
0x180012ff0  mov     rsi, rbx
0x180012ff3  mov     edi, 2
0x180012ff8  call    RasTapiTrace
0x180012ffd  mov     rbx, [rsp+48h+hObject]
0x180013002  mov     cs:g_hAsyMac, rsi
0x180013009  mov     eax, edi
0x18001300b  mov     rsi, [rsp+48h+arg_10]
0x180013010  mov     cs:g_hAsyncMacSwenum, rbx
0x180013017  mov     rbx, [rsp+48h+arg_0]
0x18001301c  add     rsp, 40h
0x180013020  pop     rdi
0x180013021  retn
```
