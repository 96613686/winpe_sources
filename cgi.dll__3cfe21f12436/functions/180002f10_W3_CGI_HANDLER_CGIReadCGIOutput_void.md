# W3_CGI_HANDLER::CGIReadCGIOutput(void)

- ea: `0x180002f10`
- end: `0x180002faa`
- name: `?CGIReadCGIOutput@W3_CGI_HANDLER@@AEAAJXZ`
- size: `154`
- prototype: `__int64 __fastcall(W3_CGI_HANDLER *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180002c18`
- `0x180002d28`
- `0x1800047f0`
- `0x180004e50`

## callees

- `0x180002f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f5a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180002f33`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180002f33`
- `iisutil!PuDbgPrint` at `0x180002f8b`
- `iisutil!PuDbgPrint` at `0x180002f8b`

## string_xrefs

- `0x180002f72`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x180002f79`: `ReadFile from child stdout failed, error %d\n`
- `0x180002f67`: `W3_CGI_HANDLER::CGIReadCGIOutput`

## pseudocode

```c
__int64 __fastcall W3_CGI_HANDLER::CGIReadCGIOutput(W3_CGI_HANDLER *this)
{
  DWORD LastError; // eax
  int v2; // ebx
  DWORD v3; // eax

  if ( ReadFile(*((HANDLE *)this + 3), (char *)this + 64, 0x2000u, 0, (LPOVERLAPPED)((char *)this + 8312)) )
    return 0;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError == 997 )
    return 0;
  if ( LastError == 109 )
    return (unsigned __int16)v2 | 0x80070000;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v3 = GetLastError();
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
      1514,
      "W3_CGI_HANDLER::CGIReadCGIOutput",
      "ReadFile from child stdout failed, error %d\n",
      v3);
  }
  if ( v2 > 0 )
    return (unsigned __int16)v2 | 0x80070000;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180002f10  push    rbx
0x180002f12  sub     rsp, 30h
0x180002f16  lea     rax, [rcx+2078h]
0x180002f1d  xor     r9d, r9d; lpNumberOfBytesRead
0x180002f20  lea     rdx, [rcx+40h]; lpBuffer
0x180002f24  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x180002f29  mov     rcx, [rcx+18h]; hFile
0x180002f2d  mov     r8d, 2000h; nNumberOfBytesToRead
0x180002f33  call    cs:__imp_ReadFile
0x180002f39  test    eax, eax
0x180002f3b  jnz     short loc_180002FA2
0x180002f3d  call    cs:__imp_GetLastError
0x180002f43  mov     ebx, eax
0x180002f45  cmp     eax, 3E5h
0x180002f4a  jz      short loc_180002FA2
0x180002f4c  cmp     eax, 6Dh ; 'm'
0x180002f4f  jz      short loc_180002F95
0x180002f51  test    cs:g_dwDebugFlags, 3
0x180002f58  jz      short loc_180002F91
0x180002f5a  call    cs:__imp_GetLastError
0x180002f60  mov     rcx, cs:g_pDebug
0x180002f67  lea     r9, aW3CgiHandlerCg; "W3_CGI_HANDLER::CGIReadCGIOutput"
0x180002f6e  mov     [rsp+38h+var_10], eax
0x180002f72  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002f79  lea     rax, aReadfileFromCh; "ReadFile from child stdout failed, erro"...
0x180002f80  mov     r8d, 5EAh
0x180002f86  mov     [rsp+38h+lpOverlapped], rax
0x180002f8b  call    cs:__imp_PuDbgPrint
0x180002f91  test    ebx, ebx
0x180002f93  jle     short loc_180002F9E
0x180002f95  movzx   ebx, bx
0x180002f98  or      ebx, 80070000h
0x180002f9e  mov     eax, ebx
0x180002fa0  jmp     short loc_180002FA4
0x180002fa2  xor     eax, eax
0x180002fa4  add     rsp, 30h
0x180002fa8  pop     rbx
0x180002fa9  retn
```
