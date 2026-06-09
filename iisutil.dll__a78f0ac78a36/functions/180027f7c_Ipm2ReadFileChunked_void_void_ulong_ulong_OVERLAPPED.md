# Ipm2ReadFileChunked(void *,void *,ulong,ulong,_OVERLAPPED *)

- ea: `0x180027f7c`
- end: `0x180028285`
- name: `?Ipm2ReadFileChunked@@YAJPEAX0KKPEAU_OVERLAPPED@@@Z`
- size: `777`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028630`

## callees

- `0x180007300`
- `0x180027f7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002816f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002816f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281fb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180028076`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180028076`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800280a7`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800280a7`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x180028102`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x180028145`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x180028102`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x180028145`

## string_xrefs

- `0x180028234`: `Error ReadFile, hFile=%d, dwBufferPos=%d, dwBytesToRead=%d, hr=%x\n`
- `0x1800281b3`: `Error GetOverlappedResult, hFile=%d, dwBytesToRead=%d, hr=%x\n`
- `0x180027fe7`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800281c9`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002824a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180027fc7`: `Ipm2ReadFileChunked called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x180027fd2`: `Ipm2ReadFileChunked`
- `0x1800281be`: `Ipm2ReadFileChunked`
- `0x18002823f`: `Ipm2ReadFileChunked`

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
0x180027f7c  mov     r11, rsp
0x180027f7f  push    rbx
0x180027f80  push    rbp
0x180027f81  push    rsi
0x180027f82  push    rdi
0x180027f83  push    r12
0x180027f85  push    r13
0x180027f87  push    r14
0x180027f89  push    r15
0x180027f8b  sub     rsp, 68h
0x180027f8f  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180027f95  mov     r14d, r9d
0x180027f98  mov     r12, [rsp+0A8h+arg_20]
0x180027fa0  test    al, 3
0x180027fa2  mov     r15d, r8d
0x180027fa5  mov     dword ptr [r11+8], 0
0x180027fad  setnz   r10b
0x180027fb1  mov     r13, rdx
0x180027fb4  bt      eax, 1Ch
0x180027fb8  mov     rsi, rcx
0x180027fbb  setb    al
0x180027fbe  test    al, r10b
0x180027fc1  jz      short loc_180027FFF
0x180027fc3  mov     [r11-68h], r12
0x180027fc7  lea     rax, aIpm2readfilech; "Ipm2ReadFileChunked called with hFile=%"...
0x180027fce  mov     [r11-70h], r8d
0x180027fd2  lea     r9, aIpm2readfilech_0; "Ipm2ReadFileChunked"
0x180027fd9  mov     [r11-78h], rdx
0x180027fdd  mov     r8d, 0C7h; unsigned int
0x180027fe3  mov     [r11-80h], rcx
0x180027fe7  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027fee  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180027ff5  mov     [rsp+0A8h+lpOverlapped], rax; char *
0x180027ffa  call    PuDbgPrint
0x180027fff  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180028003  jz      loc_18002826F
0x180028009  test    r13, r13
0x18002800c  jz      loc_18002826F
0x180028012  test    r15d, r15d
0x180028015  jz      loc_18002826F
0x18002801b  xor     ebx, ebx
0x18002801d  xor     edi, edi
0x18002801f  xor     ebp, ebp
0x180028021  test    r12, r12
0x180028024  jz      loc_18002826F
0x18002802a  cmp     r14d, r15d
0x18002802d  jnb     loc_18002826B
0x180028033  mov     [rsp+0A8h+NumberOfBytesRead], 0
0x18002803e  test    ebp, ebp
0x180028040  jnz     short loc_18002805B
0x180028042  lea     eax, [r14+10000h]
0x180028049  cmp     eax, r15d
0x18002804c  jbe     short loc_180028056
0x18002804e  mov     edi, r15d
0x180028051  sub     edi, r14d
0x180028054  jmp     short loc_18002805B
0x180028056  mov     edi, 10000h
0x18002805b  mov     edx, r14d
0x18002805e  lea     r9, [rsp+0A8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180028066  add     rdx, r13; lpBuffer
0x180028069  mov     [rsp+0A8h+lpOverlapped], r12; lpOverlapped
0x18002806e  mov     r8d, edi; nNumberOfBytesToRead
0x180028071  mov     rcx, rsi; hFile
0x180028074  xor     ebp, ebp
0x180028076  call    cs:__imp_ReadFile
0x18002807c  test    eax, eax
0x18002807e  jnz     loc_180028162
0x180028084  call    cs:__imp_GetLastError
0x18002808a  cmp     eax, 3E5h
0x18002808f  jnz     loc_18002811C
0x180028095  lea     r9d, [rbp+1]; bWait
0x180028099  mov     rdx, r12; lpOverlapped
0x18002809c  lea     r8, [rsp+0A8h+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x1800280a4  mov     rcx, rsi; hFile
0x1800280a7  call    cs:__imp_GetOverlappedResult
0x1800280ad  test    eax, eax
0x1800280af  jnz     loc_180028162
0x1800280b5  call    cs:__imp_GetLastError
0x1800280bb  test    eax, eax
0x1800280bd  jz      loc_18002818D
0x1800280c3  call    cs:__imp_GetLastError
0x1800280c9  mov     ebx, eax
0x1800280cb  test    eax, eax
0x1800280cd  jle     short loc_1800280D8
0x1800280cf  movzx   ebx, ax
0x1800280d2  or      ebx, 80070000h
0x1800280d8  cmp     ebx, 800700EAh
0x1800280de  jnz     loc_180028192
0x1800280e4  lea     rax, [rsp+0A8h+BytesLeftThisMessage]
0x1800280e9  mov     [rsp+0A8h+BytesLeftThisMessage], ebp
0x1800280ed  mov     [rsp+0A8h+lpBytesLeftThisMessage], rax; lpBytesLeftThisMessage
0x1800280f2  xor     r9d, r9d; lpBytesRead
0x1800280f5  xor     r8d, r8d; nBufferSize
0x1800280f8  mov     [rsp+0A8h+lpOverlapped], rbp; lpTotalBytesAvail
0x1800280fd  xor     edx, edx; lpBuffer
0x1800280ff  mov     rcx, rsi; hNamedPipe
0x180028102  call    cs:__imp_PeekNamedPipe
0x180028108  test    eax, eax
0x18002810a  jz      short loc_18002816F
0x18002810c  cmp     [rsp+0A8h+BytesLeftThisMessage], edi
0x180028110  jb      short loc_180028159
0x180028112  mov     ebx, 800703E5h
0x180028117  jmp     loc_18002826B
0x18002811c  cmp     eax, 0EAh
0x180028121  jnz     loc_1800281F1
0x180028127  lea     rax, [rsp+0A8h+BytesLeftThisMessage]
0x18002812c  mov     [rsp+0A8h+BytesLeftThisMessage], ebp
0x180028130  mov     [rsp+0A8h+lpBytesLeftThisMessage], rax; lpBytesLeftThisMessage
0x180028135  xor     r9d, r9d; lpBytesRead
0x180028138  xor     r8d, r8d; nBufferSize
0x18002813b  mov     [rsp+0A8h+lpOverlapped], rbp; lpTotalBytesAvail
0x180028140  xor     edx, edx; lpBuffer
0x180028142  mov     rcx, rsi; hNamedPipe
0x180028145  call    cs:__imp_PeekNamedPipe
0x18002814b  test    eax, eax
0x18002814d  jz      short loc_18002816F
0x18002814f  cmp     [rsp+0A8h+BytesLeftThisMessage], edi
0x180028153  jnb     loc_1800281EA
0x180028159  mov     edi, [rsp+0A8h+BytesLeftThisMessage]
0x18002815d  mov     ebp, 1
0x180028162  add     r14d, [rsp+0A8h+NumberOfBytesRead]
0x18002816a  jmp     loc_18002802A
0x18002816f  call    cs:__imp_GetLastError
0x180028175  mov     ebx, eax
0x180028177  test    eax, eax
0x180028179  jle     loc_18002826B
0x18002817f  movzx   ebx, ax
0x180028182  or      ebx, 80070000h
0x180028188  jmp     loc_18002826B
0x18002818d  mov     ebx, 80004005h
0x180028192  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180028198  test    al, 3
0x18002819a  setnz   cl
0x18002819d  bt      eax, 1Ch
0x1800281a1  setb    al
0x1800281a4  test    al, cl
0x1800281a6  jz      loc_18002826B
0x1800281ac  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800281b3  lea     rax, aErrorGetoverla; "Error GetOverlappedResult, hFile=%d, dw"...
0x1800281ba  mov     [rsp+0A8h+var_70], ebx
0x1800281be  lea     r9, aIpm2readfilech_0; "Ipm2ReadFileChunked"
0x1800281c5  mov     [rsp+0A8h+var_78], edi
0x1800281c9  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800281d0  mov     [rsp+0A8h+lpBytesLeftThisMessage], rsi; char
0x1800281d5  mov     r8d, 11Ah; unsigned int
0x1800281db  mov     [rsp+0A8h+lpOverlapped], rax; char *
0x1800281e0  call    PuDbgPrint
0x1800281e5  jmp     loc_18002826B
0x1800281ea  mov     ebx, 800700EAh
0x1800281ef  jmp     short loc_18002826B
0x1800281f1  call    cs:__imp_GetLastError
0x1800281f7  test    eax, eax
0x1800281f9  jz      short loc_180028212
0x1800281fb  call    cs:__imp_GetLastError
0x180028201  mov     ebx, eax
0x180028203  test    eax, eax
0x180028205  jle     short loc_180028217
0x180028207  movzx   ebx, ax
0x18002820a  or      ebx, 80070000h
0x180028210  jmp     short loc_180028217
0x180028212  mov     ebx, 80004005h
0x180028217  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002821d  test    al, 3
0x18002821f  setnz   cl
0x180028222  bt      eax, 1Ch
0x180028226  setb    al
0x180028229  test    al, cl
0x18002822b  jz      short loc_18002826B
0x18002822d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028234  lea     rax, aErrorReadfileH; "Error ReadFile, hFile=%d, dwBufferPos=%"...
0x18002823b  mov     [rsp+0A8h+var_68], ebx
0x18002823f  lea     r9, aIpm2readfilech_0; "Ipm2ReadFileChunked"
0x180028246  mov     [rsp+0A8h+var_70], edi
0x18002824a  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028251  mov     [rsp+0A8h+var_78], r14d
0x180028256  mov     r8d, 143h; unsigned int
0x18002825c  mov     [rsp+0A8h+lpBytesLeftThisMessage], rsi; char
0x180028261  mov     [rsp+0A8h+lpOverlapped], rax; char *
0x180028266  call    PuDbgPrint
0x18002826b  mov     eax, ebx
0x18002826d  jmp     short loc_180028274
0x18002826f  mov     eax, 80070057h
0x180028274  add     rsp, 68h
0x180028278  pop     r15
0x18002827a  pop     r14
0x18002827c  pop     r13
0x18002827e  pop     r12
0x180028280  pop     rdi
0x180028281  pop     rsi
0x180028282  pop     rbp
0x180028283  pop     rbx
0x180028284  retn
```
