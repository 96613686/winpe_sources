# Ipm2ReadFileChunked(void *,void *,ulong,ulong,_OVERLAPPED *)

- ea: `0x180029d04`
- end: `0x18002a04d`
- name: `?Ipm2ReadFileChunked@@YAJPEAX0KKPEAU_OVERLAPPED@@@Z`
- size: `841`
- prototype: `__int64 __fastcall(void *, char *, unsigned int, unsigned int, LPOVERLAPPED)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002a430`

## callees

- `0x180008000`
- `0x180029d04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029fbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029fbc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180029dfe`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180029dfe`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180029e3b`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180029e3b`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x180029ea8`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x180029ef1`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x180029ea8`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x180029ef1`

## string_xrefs

- `0x180029ffb`: `Error ReadFile, hFile=%d, dwBufferPos=%d, dwBytesToRead=%d, hr=%x\n`
- `0x180029f6b`: `Error GetOverlappedResult, hFile=%d, dwBytesToRead=%d, hr=%x\n`
- `0x180029d6f`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180029f81`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a011`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180029d4f`: `Ipm2ReadFileChunked called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x180029d5a`: `Ipm2ReadFileChunked`
- `0x180029f76`: `Ipm2ReadFileChunked`
- `0x18002a006`: `Ipm2ReadFileChunked`

## pseudocode

```c
__int64 __fastcall Ipm2ReadFileChunked(void *a1, char *a2, unsigned int a3, unsigned int a4, LPOVERLAPPED a5)
{
  struct _OVERLAPPED *lpOverlapped; // r12
  unsigned int v10; // ebx
  DWORD v11; // edi
  int v12; // ebp
  DWORD LastError; // eax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  DWORD BytesLeftThisMessage[22]; // [rsp+50h] [rbp-58h] BYREF
  DWORD NumberOfBytesRead; // [rsp+B0h] [rbp+8h] BYREF

  lpOverlapped = a5;
  NumberOfBytesRead = 0;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0xC7u,
      "Ipm2ReadFileChunked",
      "Ipm2ReadFileChunked called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n",
      (char)a1);
  if ( a1 != (void *)-1LL )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        v10 = 0;
        v11 = 0;
        v12 = 0;
        if ( lpOverlapped )
        {
          while ( 1 )
          {
            if ( a4 >= a3 )
              return v10;
            NumberOfBytesRead = 0;
            if ( !v12 )
            {
              if ( a4 + 0x10000 <= a3 )
                v11 = 0x10000;
              else
                v11 = a3 - a4;
            }
            v12 = 0;
            if ( !ReadFile(a1, &a2[a4], v11, &NumberOfBytesRead, lpOverlapped) )
            {
              LastError = GetLastError();
              if ( LastError == 997 )
              {
                if ( GetOverlappedResult(a1, lpOverlapped, &NumberOfBytesRead, 1) )
                  goto LABEL_26;
                if ( !GetLastError() )
                {
                  v10 = -2147467259;
LABEL_30:
                  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
                    PuDbgPrint(
                      (struct _DEBUG_PRINTS *)g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
                      0x11Au,
                      "Ipm2ReadFileChunked",
                      "Error GetOverlappedResult, hFile=%d, dwBytesToRead=%d, hr=%x\n",
                      (char)a1);
                  return v10;
                }
                v14 = GetLastError();
                v10 = v14;
                if ( v14 > 0 )
                  v10 = (unsigned __int16)v14 | 0x80070000;
                if ( v10 != -2147024662 )
                  goto LABEL_30;
                BytesLeftThisMessage[0] = 0;
                if ( !PeekNamedPipe(a1, 0, 0, 0, 0, BytesLeftThisMessage) )
                  goto LABEL_27;
                if ( BytesLeftThisMessage[0] >= v11 )
                  return (unsigned int)-2147023899;
              }
              else
              {
                if ( LastError != 234 )
                {
                  if ( GetLastError() )
                  {
                    v16 = GetLastError();
                    v10 = v16;
                    if ( v16 > 0 )
                      v10 = (unsigned __int16)v16 | 0x80070000;
                  }
                  else
                  {
                    v10 = -2147467259;
                  }
                  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
                    PuDbgPrint(
                      (struct _DEBUG_PRINTS *)g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
                      0x143u,
                      "Ipm2ReadFileChunked",
                      "Error ReadFile, hFile=%d, dwBufferPos=%d, dwBytesToRead=%d, hr=%x\n",
                      (char)a1);
                  return v10;
                }
                BytesLeftThisMessage[0] = 0;
                if ( !PeekNamedPipe(a1, 0, 0, 0, 0, BytesLeftThisMessage) )
                {
LABEL_27:
                  v15 = GetLastError();
                  v10 = v15;
                  if ( v15 > 0 )
                    return (unsigned __int16)v15 | 0x80070000;
                  return v10;
                }
                if ( BytesLeftThisMessage[0] >= v11 )
                  return (unsigned int)-2147024662;
              }
              v11 = BytesLeftThisMessage[0];
              v12 = 1;
            }
LABEL_26:
            a4 += NumberOfBytesRead;
          }
        }
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180029d04  mov     r11, rsp
0x180029d07  push    rbx
0x180029d08  push    rbp
0x180029d09  push    rsi
0x180029d0a  push    rdi
0x180029d0b  push    r12
0x180029d0d  push    r13
0x180029d0f  push    r14
0x180029d11  push    r15
0x180029d13  sub     rsp, 68h
0x180029d17  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180029d1d  mov     r14d, r9d
0x180029d20  mov     r12, [rsp+0A8h+arg_20]
0x180029d28  test    al, 3
0x180029d2a  mov     r15d, r8d
0x180029d2d  mov     dword ptr [r11+8], 0
0x180029d35  setnz   r10b
0x180029d39  mov     r13, rdx
0x180029d3c  bt      eax, 1Ch
0x180029d40  mov     rsi, rcx
0x180029d43  setb    al
0x180029d46  test    al, r10b
0x180029d49  jz      short loc_180029D87
0x180029d4b  mov     [r11-68h], r12
0x180029d4f  lea     rax, aIpm2readfilech; "Ipm2ReadFileChunked called with hFile=%"...
0x180029d56  mov     [r11-70h], r8d
0x180029d5a  lea     r9, aIpm2readfilech_0; "Ipm2ReadFileChunked"
0x180029d61  mov     [r11-78h], rdx
0x180029d65  mov     r8d, 0C7h; unsigned int
0x180029d6b  mov     [r11-80h], rcx
0x180029d6f  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029d76  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029d7d  mov     [rsp+0A8h+lpOverlapped], rax; char *
0x180029d82  call    PuDbgPrint
0x180029d87  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180029d8b  jz      loc_18002A036
0x180029d91  test    r13, r13
0x180029d94  jz      loc_18002A036
0x180029d9a  test    r15d, r15d
0x180029d9d  jz      loc_18002A036
0x180029da3  xor     ebx, ebx
0x180029da5  xor     edi, edi
0x180029da7  xor     ebp, ebp
0x180029da9  test    r12, r12
0x180029dac  jz      loc_18002A036
0x180029db2  cmp     r14d, r15d
0x180029db5  jnb     loc_18002A032
0x180029dbb  mov     [rsp+0A8h+NumberOfBytesRead], 0
0x180029dc6  test    ebp, ebp
0x180029dc8  jnz     short loc_180029DE3
0x180029dca  lea     eax, [r14+10000h]
0x180029dd1  cmp     eax, r15d
0x180029dd4  jbe     short loc_180029DDE
0x180029dd6  mov     edi, r15d
0x180029dd9  sub     edi, r14d
0x180029ddc  jmp     short loc_180029DE3
0x180029dde  mov     edi, 10000h
0x180029de3  mov     edx, r14d
0x180029de6  lea     r9, [rsp+0A8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180029dee  add     rdx, r13; lpBuffer
0x180029df1  mov     [rsp+0A8h+lpOverlapped], r12; lpOverlapped
0x180029df6  mov     r8d, edi; nNumberOfBytesToRead
0x180029df9  mov     rcx, rsi; hFile
0x180029dfc  xor     ebp, ebp
0x180029dfe  call    cs:__imp_ReadFile
0x180029e05  nop     dword ptr [rax+rax+00h]
0x180029e0a  test    eax, eax
0x180029e0c  jnz     loc_180029F14
0x180029e12  call    cs:__imp_GetLastError
0x180029e19  nop     dword ptr [rax+rax+00h]
0x180029e1e  cmp     eax, 3E5h
0x180029e23  jnz     loc_180029EC8
0x180029e29  lea     r9d, [rbp+1]; bWait
0x180029e2d  mov     rdx, r12; lpOverlapped
0x180029e30  lea     r8, [rsp+0A8h+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x180029e38  mov     rcx, rsi; hFile
0x180029e3b  call    cs:__imp_GetOverlappedResult
0x180029e42  nop     dword ptr [rax+rax+00h]
0x180029e47  test    eax, eax
0x180029e49  jnz     loc_180029F14
0x180029e4f  call    cs:__imp_GetLastError
0x180029e56  nop     dword ptr [rax+rax+00h]
0x180029e5b  test    eax, eax
0x180029e5d  jz      loc_180029F45
0x180029e63  call    cs:__imp_GetLastError
0x180029e6a  nop     dword ptr [rax+rax+00h]
0x180029e6f  mov     ebx, eax
0x180029e71  test    eax, eax
0x180029e73  jle     short loc_180029E7E
0x180029e75  movzx   ebx, ax
0x180029e78  or      ebx, 80070000h
0x180029e7e  cmp     ebx, 800700EAh
0x180029e84  jnz     loc_180029F4A
0x180029e8a  lea     rax, [rsp+0A8h+BytesLeftThisMessage]
0x180029e8f  mov     [rsp+0A8h+BytesLeftThisMessage], ebp
0x180029e93  mov     [rsp+0A8h+lpBytesLeftThisMessage], rax; lpBytesLeftThisMessage
0x180029e98  xor     r9d, r9d; lpBytesRead
0x180029e9b  xor     r8d, r8d; nBufferSize
0x180029e9e  mov     [rsp+0A8h+lpOverlapped], rbp; lpTotalBytesAvail
0x180029ea3  xor     edx, edx; lpBuffer
0x180029ea5  mov     rcx, rsi; hNamedPipe
0x180029ea8  call    cs:__imp_PeekNamedPipe
0x180029eaf  nop     dword ptr [rax+rax+00h]
0x180029eb4  test    eax, eax
0x180029eb6  jz      short loc_180029F21
0x180029eb8  cmp     [rsp+0A8h+BytesLeftThisMessage], edi
0x180029ebc  jb      short loc_180029F0B
0x180029ebe  mov     ebx, 800703E5h
0x180029ec3  jmp     loc_18002A032
0x180029ec8  cmp     eax, 0EAh
0x180029ecd  jnz     loc_180029FAC
0x180029ed3  lea     rax, [rsp+0A8h+BytesLeftThisMessage]
0x180029ed8  mov     [rsp+0A8h+BytesLeftThisMessage], ebp
0x180029edc  mov     [rsp+0A8h+lpBytesLeftThisMessage], rax; lpBytesLeftThisMessage
0x180029ee1  xor     r9d, r9d; lpBytesRead
0x180029ee4  xor     r8d, r8d; nBufferSize
0x180029ee7  mov     [rsp+0A8h+lpOverlapped], rbp; lpTotalBytesAvail
0x180029eec  xor     edx, edx; lpBuffer
0x180029eee  mov     rcx, rsi; hNamedPipe
0x180029ef1  call    cs:__imp_PeekNamedPipe
0x180029ef8  nop     dword ptr [rax+rax+00h]
0x180029efd  test    eax, eax
0x180029eff  jz      short loc_180029F21
0x180029f01  cmp     [rsp+0A8h+BytesLeftThisMessage], edi
0x180029f05  jnb     loc_180029FA2
0x180029f0b  mov     edi, [rsp+0A8h+BytesLeftThisMessage]
0x180029f0f  mov     ebp, 1
0x180029f14  add     r14d, [rsp+0A8h+NumberOfBytesRead]
0x180029f1c  jmp     loc_180029DB2
0x180029f21  call    cs:__imp_GetLastError
0x180029f28  nop     dword ptr [rax+rax+00h]
0x180029f2d  mov     ebx, eax
0x180029f2f  test    eax, eax
0x180029f31  jle     loc_18002A032
0x180029f37  movzx   ebx, ax
0x180029f3a  or      ebx, 80070000h
0x180029f40  jmp     loc_18002A032
0x180029f45  mov     ebx, 80004005h
0x180029f4a  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180029f50  test    al, 3
0x180029f52  setnz   cl
0x180029f55  bt      eax, 1Ch
0x180029f59  setb    al
0x180029f5c  test    al, cl
0x180029f5e  jz      loc_18002A032
0x180029f64  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029f6b  lea     rax, aErrorGetoverla; "Error GetOverlappedResult, hFile=%d, dw"...
0x180029f72  mov     [rsp+0A8h+var_70], ebx
0x180029f76  lea     r9, aIpm2readfilech_0; "Ipm2ReadFileChunked"
0x180029f7d  mov     [rsp+0A8h+var_78], edi
0x180029f81  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029f88  mov     [rsp+0A8h+lpBytesLeftThisMessage], rsi; char
0x180029f8d  mov     r8d, 11Ah; unsigned int
0x180029f93  mov     [rsp+0A8h+lpOverlapped], rax; char *
0x180029f98  call    PuDbgPrint
0x180029f9d  jmp     loc_18002A032
0x180029fa2  mov     ebx, 800700EAh
0x180029fa7  jmp     loc_18002A032
0x180029fac  call    cs:__imp_GetLastError
0x180029fb3  nop     dword ptr [rax+rax+00h]
0x180029fb8  test    eax, eax
0x180029fba  jz      short loc_180029FD9
0x180029fbc  call    cs:__imp_GetLastError
0x180029fc3  nop     dword ptr [rax+rax+00h]
0x180029fc8  mov     ebx, eax
0x180029fca  test    eax, eax
0x180029fcc  jle     short loc_180029FDE
0x180029fce  movzx   ebx, ax
0x180029fd1  or      ebx, 80070000h
0x180029fd7  jmp     short loc_180029FDE
0x180029fd9  mov     ebx, 80004005h
0x180029fde  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180029fe4  test    al, 3
0x180029fe6  setnz   cl
0x180029fe9  bt      eax, 1Ch
0x180029fed  setb    al
0x180029ff0  test    al, cl
0x180029ff2  jz      short loc_18002A032
0x180029ff4  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029ffb  lea     rax, aErrorReadfileH; "Error ReadFile, hFile=%d, dwBufferPos=%"...
0x18002a002  mov     [rsp+0A8h+var_68], ebx
0x18002a006  lea     r9, aIpm2readfilech_0; "Ipm2ReadFileChunked"
0x18002a00d  mov     [rsp+0A8h+var_70], edi
0x18002a011  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a018  mov     [rsp+0A8h+var_78], r14d
0x18002a01d  mov     r8d, 143h; unsigned int
0x18002a023  mov     [rsp+0A8h+lpBytesLeftThisMessage], rsi; char
0x18002a028  mov     [rsp+0A8h+lpOverlapped], rax; char *
0x18002a02d  call    PuDbgPrint
0x18002a032  mov     eax, ebx
0x18002a034  jmp     short loc_18002A03B
0x18002a036  mov     eax, 80070057h
0x18002a03b  add     rsp, 68h
0x18002a03f  pop     r15
0x18002a041  pop     r14
0x18002a043  pop     r13
0x18002a045  pop     r12
0x18002a047  pop     rdi
0x18002a048  pop     rsi
0x18002a049  pop     rbp
0x18002a04a  pop     rbx
0x18002a04b  retn
```
