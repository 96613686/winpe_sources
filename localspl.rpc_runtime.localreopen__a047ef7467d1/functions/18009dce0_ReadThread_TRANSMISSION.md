# ReadThread(_TRANSMISSION *)

- ea: `0x18009dce0`
- end: `0x18009dee5`
- name: `?ReadThread@@YAXPEAU_TRANSMISSION@@@Z`
- size: `517`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x18003ea2c`
- `0x180054638`
- `0x18009dce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18009dea5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18009dea5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dda3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009de22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009de4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009de64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009deaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dda3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009de22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009de4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009de64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009deaf`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009dd26`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009de16`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009dd26`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009de16`
- `api-ms-win-core-namedpipe-l1-1-0!ImpersonateNamedPipeClient` at `0x18009dd3e`
- `api-ms-win-core-namedpipe-l1-1-0!ImpersonateNamedPipeClient` at `0x18009dd3e`
- `SPOOLSS!DllFreeSplStr` at `0x18009de82`
- `SPOOLSS!DllFreeSplStr` at `0x18009de82`
- `SPOOLSS!DllFreeSplMem` at `0x18009deca`
- `SPOOLSS!DllFreeSplMem` at `0x18009deca`
- `SPOOLSS!ClosePrinter` at `0x18009de94`
- `SPOOLSS!ClosePrinter` at `0x18009de94`
- `SPOOLSS!AllocSplStr` at `0x18009dd77`
- `SPOOLSS!AllocSplStr` at `0x18009dd77`
- `SPOOLSS!OpenPrinterW` at `0x18009dd99`
- `SPOOLSS!OpenPrinterW` at `0x18009dd99`
- `SPOOLSS!WritePrinter` at `0x18009ddf2`
- `SPOOLSS!WritePrinter` at `0x18009ddf2`
- `SPOOLSS!EndDocPrinter` at `0x18009de40`
- `SPOOLSS!EndDocPrinter` at `0x18009de40`
- `SPOOLSS!StartDocPrinterW` at `0x18009ddcf`
- `SPOOLSS!StartDocPrinterW` at `0x18009ddcf`

## string_xrefs

- `0x18009dda9`: `OpenPrinter %ws failed with error %d`
- `0x18009dd2c`: `ReadThread`
- `0x18009dd4e`: `ImpersonateNamedPipeClient failed with error %d`
- `0x18009de2b`: `WritePrinter %ws failed with error %d`

## pseudocode

```c
__int64 __fastcall ReadThread(char *Parameter)
{
  char *v1; // rbp
  void *v3; // rcx
  WCHAR *v4; // rdi
  DWORD v5; // eax
  WCHAR *v6; // rax
  HANDLE *v7; // rsi
  DWORD v8; // eax
  HANDLE v9; // rcx
  DWORD LastError; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  void *v13; // rcx
  DWORD v14; // eax
  BYTE pDocInfo[16]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17; // [rsp+40h] [rbp-28h]
  DWORD cbBuf; // [rsp+70h] [rbp+8h] BYREF
  DWORD pcWritten; // [rsp+78h] [rbp+10h] BYREF

  v1 = Parameter + 8;
  cbBuf = 0;
  pcWritten = 0;
  v3 = *(void **)Parameter;
  *(_OWORD *)pDocInfo = 0;
  v17 = 0;
  v4 = 0;
  if ( ReadFile(v3, v1, 0x400u, &cbBuf, 0) )
  {
    if ( ImpersonateNamedPipeClient(*(HANDLE *)Parameter) )
    {
      v6 = (WCHAR *)AllocSplStr(*(_QWORD *)(**(_QWORD **)(*((_QWORD *)Parameter + 132) + 88LL) + 24LL));
      v4 = v6;
      if ( v6 )
      {
        v7 = (HANDLE *)(Parameter + 1040);
        if ( OpenPrinterW(v6, (LPHANDLE)Parameter + 130, 0) )
        {
          v9 = *v7;
          *(_OWORD *)pDocInfo = 0;
          v17 = 0;
          if ( StartDocPrinterW(v9, 1u, pDocInfo) )
          {
            while ( cbBuf )
            {
              if ( !WritePrinter(*v7, v1, cbBuf, &pcWritten) )
              {
                LastError = GetLastError();
                LocalSpoolerTelemetry::WriteDbgTraceError(
                  "ReadThread",
                  L"WritePrinter %ws failed with error %d",
                  v4,
                  LastError);
                break;
              }
              if ( !ReadFile(*(HANDLE *)Parameter, v1, 0x400u, &cbBuf, 0) )
                break;
            }
            if ( !EndDocPrinter(*v7) )
            {
              v11 = GetLastError();
              LocalSpoolerTelemetry::WriteDbgTraceWarning("ReadThread", L"EndDocPrinter failed: Error %d", v11);
            }
          }
          else
          {
            v12 = GetLastError();
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "ReadThread",
              L"StartDocPrinter %ws failed with error %d",
              v4,
              v12);
          }
        }
        else
        {
          v8 = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceError("ReadThread", L"OpenPrinter %ws failed with error %d", v4, v8);
        }
      }
    }
    else
    {
      v5 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError("ReadThread", L"ImpersonateNamedPipeClient failed with error %d", v5);
    }
  }
  DllFreeSplStr(v4);
  v13 = (void *)*((_QWORD *)Parameter + 130);
  if ( v13 )
    ClosePrinter(v13);
  if ( !SetEvent(*(HANDLE *)(*((_QWORD *)Parameter + 129) + 24LL)) )
  {
    v14 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError("ReadThread", L"SetEvent failed: Error %d", v14);
  }
  return DllFreeSplMem(Parameter);
}

```

## disassembly

```asm
0x18009dce0  mov     r11, rsp
0x18009dce3  mov     [r11+18h], rbx
0x18009dce7  mov     [r11+20h], rbp
0x18009dceb  push    rsi
0x18009dcec  push    rdi
0x18009dced  push    r15
0x18009dcef  sub     rsp, 50h
0x18009dcf3  xor     eax, eax
0x18009dcf5  lea     rbp, [rcx+8]
0x18009dcf9  xorps   xmm0, xmm0
0x18009dcfc  mov     [rsp+68h+cbBuf], eax
0x18009dd00  mov     rbx, rcx
0x18009dd03  mov     [rsp+68h+pcWritten], eax
0x18009dd07  mov     rcx, [rcx]; hFile
0x18009dd0a  lea     r9, [r11+8]; lpNumberOfBytesRead
0x18009dd0e  movups  xmmword ptr [rsp+68h+pDocInfo], xmm0
0x18009dd13  mov     rdx, rbp; lpBuffer
0x18009dd16  mov     [r11-28h], rax
0x18009dd1a  mov     r8d, 400h; nNumberOfBytesToRead
0x18009dd20  mov     [r11-48h], rax
0x18009dd24  xor     edi, edi
0x18009dd26  call    cs:__imp_ReadFile
0x18009dd2c  lea     r15, aReadthread; "ReadThread"
0x18009dd33  test    eax, eax
0x18009dd35  jz      loc_18009DE7F
0x18009dd3b  mov     rcx, [rbx]; hNamedPipe
0x18009dd3e  call    cs:__imp_ImpersonateNamedPipeClient
0x18009dd44  test    eax, eax
0x18009dd46  jnz     short loc_18009DD65
0x18009dd48  call    cs:__imp_GetLastError
0x18009dd4e  lea     rdx, aImpersonatenam; "ImpersonateNamedPipeClient failed with "...
0x18009dd55  mov     rcx, r15; char *
0x18009dd58  mov     r8d, eax
0x18009dd5b  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009dd60  jmp     loc_18009DE7F
0x18009dd65  mov     rax, [rbx+420h]
0x18009dd6c  mov     rcx, [rax+58h]
0x18009dd70  mov     rcx, [rcx]
0x18009dd73  mov     rcx, [rcx+18h]
0x18009dd77  call    cs:__imp_AllocSplStr
0x18009dd7d  mov     rdi, rax
0x18009dd80  test    rax, rax
0x18009dd83  jz      loc_18009DE7F
0x18009dd89  lea     rsi, [rbx+410h]
0x18009dd90  xor     r8d, r8d; pDefault
0x18009dd93  mov     rdx, rsi; phPrinter
0x18009dd96  mov     rcx, rax; pPrinterName
0x18009dd99  call    cs:__imp_OpenPrinterW
0x18009dd9f  test    eax, eax
0x18009dda1  jnz     short loc_18009DDB5
0x18009dda3  call    cs:__imp_GetLastError
0x18009dda9  lea     rdx, aOpenprinterWsF; "OpenPrinter %ws failed with error %d"
0x18009ddb0  jmp     loc_18009DE71
0x18009ddb5  mov     rcx, [rsi]; hPrinter
0x18009ddb8  lea     r8, [rsp+68h+pDocInfo]; pDocInfo
0x18009ddbd  xor     eax, eax
0x18009ddbf  xorps   xmm0, xmm0
0x18009ddc2  movups  xmmword ptr [rsp+68h+pDocInfo], xmm0
0x18009ddc7  mov     [rsp+68h+var_28], rax
0x18009ddcc  lea     edx, [rax+1]; Level
0x18009ddcf  call    cs:__imp_StartDocPrinterW
0x18009ddd5  test    eax, eax
0x18009ddd7  jz      loc_18009DE64
0x18009dddd  mov     r8d, [rsp+68h+cbBuf]; cbBuf
0x18009dde2  test    r8d, r8d
0x18009dde5  jz      short loc_18009DE3D
0x18009dde7  mov     rcx, [rsi]; hPrinter
0x18009ddea  lea     r9, [rsp+68h+pcWritten]; pcWritten
0x18009ddef  mov     rdx, rbp; pBuf
0x18009ddf2  call    cs:__imp_WritePrinter
0x18009ddf8  test    eax, eax
0x18009ddfa  jz      short loc_18009DE22
0x18009ddfc  mov     rcx, [rbx]; hFile
0x18009ddff  lea     r9, [rsp+68h+cbBuf]; lpNumberOfBytesRead
0x18009de04  mov     r8d, 400h; nNumberOfBytesToRead
0x18009de0a  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18009de13  mov     rdx, rbp; lpBuffer
0x18009de16  call    cs:__imp_ReadFile
0x18009de1c  test    eax, eax
0x18009de1e  jnz     short loc_18009DDDD
0x18009de20  jmp     short loc_18009DE3D
0x18009de22  call    cs:__imp_GetLastError
0x18009de28  mov     r8, rdi
0x18009de2b  lea     rdx, aWriteprinterWs; "WritePrinter %ws failed with error %d"
0x18009de32  mov     r9d, eax
0x18009de35  mov     rcx, r15; char *
0x18009de38  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009de3d  mov     rcx, [rsi]; hPrinter
0x18009de40  call    cs:__imp_EndDocPrinter
0x18009de46  test    eax, eax
0x18009de48  jnz     short loc_18009DE7F
0x18009de4a  call    cs:__imp_GetLastError
0x18009de50  lea     rdx, aEnddocprinterF; "EndDocPrinter failed: Error %d"
0x18009de57  mov     rcx, r15; char *
0x18009de5a  mov     r8d, eax
0x18009de5d  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18009de62  jmp     short loc_18009DE7F
0x18009de64  call    cs:__imp_GetLastError
0x18009de6a  lea     rdx, aStartdocprinte; "StartDocPrinter %ws failed with error %"...
0x18009de71  mov     r9d, eax
0x18009de74  mov     r8, rdi
0x18009de77  mov     rcx, r15; char *
0x18009de7a  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009de7f  mov     rcx, rdi
0x18009de82  call    cs:__imp_DllFreeSplStr
0x18009de88  mov     rcx, [rbx+410h]; hPrinter
0x18009de8f  test    rcx, rcx
0x18009de92  jz      short loc_18009DE9A
0x18009de94  call    cs:__imp_ClosePrinter
0x18009de9a  mov     rcx, [rbx+408h]
0x18009dea1  mov     rcx, [rcx+18h]; hEvent
0x18009dea5  call    cs:__imp_SetEvent
0x18009deab  test    eax, eax
0x18009dead  jnz     short loc_18009DEC7
0x18009deaf  call    cs:__imp_GetLastError
0x18009deb5  lea     rdx, aSeteventFailed; "SetEvent failed: Error %d"
0x18009debc  mov     rcx, r15; char *
0x18009debf  mov     r8d, eax
0x18009dec2  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009dec7  mov     rcx, rbx
0x18009deca  call    cs:__imp_DllFreeSplMem
0x18009ded0  lea     r11, [rsp+68h+var_18]
0x18009ded5  mov     rbx, [r11+30h]
0x18009ded9  mov     rbp, [r11+38h]
0x18009dedd  mov     rsp, r11
0x18009dee0  pop     r15
0x18009dee2  pop     rdi
0x18009dee3  pop     rsi
0x18009dee4  retn
```
