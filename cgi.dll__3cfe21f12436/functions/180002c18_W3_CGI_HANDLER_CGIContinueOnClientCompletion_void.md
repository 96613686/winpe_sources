# W3_CGI_HANDLER::CGIContinueOnClientCompletion(void)

- ea: `0x180002c18`
- end: `0x180002d20`
- name: `?CGIContinueOnClientCompletion@W3_CGI_HANDLER@@AEAAJXZ`
- size: `264`
- prototype: `__int64 __fastcall(W3_CGI_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180004678`

## callees

- `0x180002c18`
- `0x180002f10`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cb1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002c4d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002c4d`
- `iisutil!PuDbgPrint` at `0x180002cab`
- `iisutil!PuDbgPrint` at `0x180002cab`

## string_xrefs

- `0x180002c92`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x180002c99`: `WriteFile failed, error %d\n`
- `0x180002c87`: `W3_CGI_HANDLER::CGIWriteCGIInput`

## pseudocode

```c
__int64 __fastcall W3_CGI_HANDLER::CGIContinueOnClientCompletion(W3_CGI_HANDLER *this)
{
  int v2; // edi
  DWORD LastError; // eax
  signed int v4; // eax
  bool v5; // sf
  __int64 v6; // rax

  if ( *((_DWORD *)this + 2) != 1 )
    return W3_CGI_HANDLER::CGIReadCGIOutput(this);
  if ( !WriteFile(
          *((HANDLE *)this + 4),
          (char *)this + 64,
          *((_DWORD *)this + 2076),
          0,
          (LPOVERLAPPED)((char *)this + 8312))
    && GetLastError() != 997 )
  {
    v2 = 3;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
        1548,
        "W3_CGI_HANDLER::CGIWriteCGIInput",
        "WriteFile failed, error %d\n",
        LastError);
    }
    v4 = GetLastError();
    v5 = v4 < 0;
    if ( v4 > 0 )
      v5 = 1;
    if ( v5 )
    {
      if ( *((_DWORD *)this + 2090) )
      {
        v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 32LL))(*((_QWORD *)this + 6));
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 128LL))(v6);
      }
      else
      {
        v2 = 2;
      }
      *((_DWORD *)this + 2) = v2;
      *((_DWORD *)this + 2076) = 0;
      return W3_CGI_HANDLER::CGIReadCGIOutput(this);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180002c18  mov     [rsp+arg_0], rbx
0x180002c1d  push    rdi
0x180002c1e  sub     rsp, 30h
0x180002c22  cmp     dword ptr [rcx+8], 1
0x180002c26  mov     rbx, rcx
0x180002c29  jnz     loc_180002D09
0x180002c2f  mov     r8d, [rcx+2070h]; nNumberOfBytesToWrite
0x180002c36  lea     rax, [rcx+2078h]
0x180002c3d  lea     rdx, [rcx+40h]; lpBuffer
0x180002c41  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x180002c46  mov     rcx, [rcx+20h]; hFile
0x180002c4a  xor     r9d, r9d; lpNumberOfBytesWritten
0x180002c4d  call    cs:__imp_WriteFile
0x180002c53  test    eax, eax
0x180002c55  jnz     loc_180002D1C
0x180002c5b  call    cs:__imp_GetLastError
0x180002c61  cmp     eax, 3E5h
0x180002c66  jz      loc_180002D1C
0x180002c6c  mov     edi, 3
0x180002c71  test    cs:g_dwDebugFlags, dil
0x180002c78  jz      short loc_180002CB1
0x180002c7a  call    cs:__imp_GetLastError
0x180002c80  mov     rcx, cs:g_pDebug
0x180002c87  lea     r9, aW3CgiHandlerCg_0; "W3_CGI_HANDLER::CGIWriteCGIInput"
0x180002c8e  mov     [rsp+38h+var_10], eax
0x180002c92  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002c99  lea     rax, aWritefileFaile; "WriteFile failed, error %d\n"
0x180002ca0  mov     r8d, 60Ch
0x180002ca6  mov     [rsp+38h+lpOverlapped], rax
0x180002cab  call    cs:__imp_PuDbgPrint
0x180002cb1  call    cs:__imp_GetLastError
0x180002cb7  test    eax, eax
0x180002cb9  jle     short loc_180002CC5
0x180002cbb  movzx   eax, ax
0x180002cbe  or      eax, 80070000h
0x180002cc3  test    eax, eax
0x180002cc5  jns     short loc_180002D1C
0x180002cc7  cmp     dword ptr [rbx+20A8h], 0
0x180002cce  jz      short loc_180002CF7
0x180002cd0  mov     rcx, [rbx+30h]
0x180002cd4  mov     rax, [rcx]
0x180002cd7  mov     rax, [rax+20h]
0x180002cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce0  mov     rdx, rax
0x180002ce3  mov     rcx, [rax]
0x180002ce6  mov     rax, [rcx+80h]
0x180002ced  mov     rcx, rdx
0x180002cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf5  jmp     short loc_180002CFC
0x180002cf7  mov     edi, 2
0x180002cfc  mov     [rbx+8], edi
0x180002cff  mov     dword ptr [rbx+2070h], 0
0x180002d09  mov     rcx, rbx; this
0x180002d0c  call    ?CGIReadCGIOutput@W3_CGI_HANDLER@@AEAAJXZ; W3_CGI_HANDLER::CGIReadCGIOutput(void)
0x180002d11  mov     rbx, [rsp+38h+arg_0]
0x180002d16  add     rsp, 30h
0x180002d1a  pop     rdi
0x180002d1b  retn
0x180002d1c  xor     eax, eax
0x180002d1e  jmp     short loc_180002D11
```
