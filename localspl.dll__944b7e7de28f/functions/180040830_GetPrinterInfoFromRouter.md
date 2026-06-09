# GetPrinterInfoFromRouter

- ea: `0x180040830`
- end: `0x1800408fc`
- name: `GetPrinterInfoFromRouter`
- size: `204`
- prototype: `__int64 __fastcall(HANDLE hPrinter)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18005bf50`
- `0x18005c0b4`

## callees

- `0x180040830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800408d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800408d6`
- `SPOOLSS!DllFreeSplMem` at `0x180040893`
- `SPOOLSS!DllFreeSplMem` at `0x1800408ea`
- `SPOOLSS!DllFreeSplMem` at `0x180040893`
- `SPOOLSS!DllFreeSplMem` at `0x1800408ea`
- `SPOOLSS!DllAllocSplMem` at `0x18004084f`
- `SPOOLSS!DllAllocSplMem` at `0x18004089f`
- `SPOOLSS!DllAllocSplMem` at `0x18004084f`
- `SPOOLSS!DllAllocSplMem` at `0x18004089f`
- `SPOOLSS!GetPrinterW` at `0x180040875`
- `SPOOLSS!GetPrinterW` at `0x1800408cc`
- `SPOOLSS!GetPrinterW` at `0x180040875`
- `SPOOLSS!GetPrinterW` at `0x1800408cc`

## pseudocode

```c
__int64 __fastcall GetPrinterInfoFromRouter(HANDLE hPrinter, BYTE **a2)
{
  BYTE *v4; // rdi
  DWORD LastError; // ebx
  DWORD v6; // ebx
  DWORD cbBuf; // [rsp+70h] [rbp+18h] BYREF

  cbBuf = 0;
  v4 = (BYTE *)DllAllocSplMem(4096);
  if ( !v4 )
    goto LABEL_6;
  if ( GetPrinterW(hPrinter, 2u, v4, 0x1000u, &cbBuf) )
  {
LABEL_3:
    LastError = 0;
LABEL_10:
    *a2 = v4;
    v4 = 0;
    goto LABEL_11;
  }
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    DllFreeSplMem(v4);
    v6 = cbBuf;
    v4 = (BYTE *)DllAllocSplMem(cbBuf);
    if ( !v4 )
    {
LABEL_6:
      LastError = 14;
      goto LABEL_11;
    }
    if ( GetPrinterW(hPrinter, 2u, v4, v6, &cbBuf) )
      goto LABEL_3;
    LastError = GetLastError();
  }
  if ( !LastError )
    goto LABEL_10;
LABEL_11:
  DllFreeSplMem(v4);
  return LastError;
}

```

## disassembly

```asm
0x180040830  push    rbx
0x180040832  push    rsi
0x180040833  push    rdi
0x180040834  push    r14
0x180040836  sub     rsp, 38h
0x18004083a  mov     rsi, rcx
0x18004083d  mov     [rsp+58h+cbBuf], 0
0x180040845  mov     ebx, 1000h
0x18004084a  mov     r14, rdx
0x18004084d  mov     ecx, ebx
0x18004084f  call    cs:__imp_DllAllocSplMem
0x180040855  mov     rdi, rax
0x180040858  test    rax, rax
0x18004085b  jz      short loc_1800408AD
0x18004085d  lea     rax, [rsp+58h+cbBuf]
0x180040862  mov     r9d, ebx; cbBuf
0x180040865  mov     r8, rdi; pPrinter
0x180040868  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x18004086d  mov     edx, 2; Level
0x180040872  mov     rcx, rsi; hPrinter
0x180040875  call    cs:__imp_GetPrinterW
0x18004087b  test    eax, eax
0x18004087d  jz      short loc_180040883
0x18004087f  xor     ebx, ebx
0x180040881  jmp     short loc_1800408E2
0x180040883  call    cs:__imp_GetLastError
0x180040889  mov     ebx, eax
0x18004088b  cmp     eax, 7Ah ; 'z'
0x18004088e  jnz     short loc_1800408DE
0x180040890  mov     rcx, rdi
0x180040893  call    cs:__imp_DllFreeSplMem
0x180040899  mov     ebx, [rsp+58h+cbBuf]
0x18004089d  mov     ecx, ebx
0x18004089f  call    cs:__imp_DllAllocSplMem
0x1800408a5  mov     rdi, rax
0x1800408a8  test    rax, rax
0x1800408ab  jnz     short loc_1800408B4
0x1800408ad  mov     ebx, 0Eh
0x1800408b2  jmp     short loc_1800408E7
0x1800408b4  lea     rax, [rsp+58h+cbBuf]
0x1800408b9  mov     r9d, ebx; cbBuf
0x1800408bc  mov     r8, rdi; pPrinter
0x1800408bf  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x1800408c4  mov     edx, 2; Level
0x1800408c9  mov     rcx, rsi; hPrinter
0x1800408cc  call    cs:__imp_GetPrinterW
0x1800408d2  test    eax, eax
0x1800408d4  jnz     short loc_18004087F
0x1800408d6  call    cs:__imp_GetLastError
0x1800408dc  mov     ebx, eax
0x1800408de  test    ebx, ebx
0x1800408e0  jnz     short loc_1800408E7
0x1800408e2  mov     [r14], rdi
0x1800408e5  xor     edi, edi
0x1800408e7  mov     rcx, rdi
0x1800408ea  call    cs:__imp_DllFreeSplMem
0x1800408f0  mov     eax, ebx
0x1800408f2  add     rsp, 38h
0x1800408f6  pop     r14
0x1800408f8  pop     rdi
0x1800408f9  pop     rsi
0x1800408fa  pop     rbx
0x1800408fb  retn
```
