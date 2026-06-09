# Ipm2ReadFile(void *,void *,ulong,_OVERLAPPED *)

- ea: `0x180027e9c`
- end: `0x180027f73`
- name: `?Ipm2ReadFile@@YAJPEAX0KPEAU_OVERLAPPED@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(HANDLE hFile, void *lpBuffer, DWORD nNumberOfBytesToRead, LPOVERLAPPED lpOverlapped)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028630`
- `0x180028ca0`

## callees

- `0x180007300`
- `0x180027e9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f51`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027f47`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027f47`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180027f2c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180027f2c`

## string_xrefs

- `0x180027ef0`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180027ecf`: `Ipm2ReadFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x180027edb`: `Ipm2ReadFile`

## pseudocode

```c
signed int __fastcall Ipm2ReadFile(HANDLE hFile, void *lpBuffer, DWORD nNumberOfBytesToRead, LPOVERLAPPED lpOverlapped)
{
  signed int result; // eax

  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x7Bu,
      "Ipm2ReadFile",
      "Ipm2ReadFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n",
      (char)hFile);
  if ( hFile == (HANDLE)-1LL || !lpBuffer || !nNumberOfBytesToRead || !lpOverlapped )
    return -2147024809;
  if ( ReadFile(hFile, lpBuffer, nNumberOfBytesToRead, 0, lpOverlapped) )
    return 0;
  if ( GetLastError() == 234 )
  {
    SetEvent(lpOverlapped->hEvent);
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180027e9c  mov     r11, rsp
0x180027e9f  push    rbx
0x180027ea0  push    rbp
0x180027ea1  push    rsi
0x180027ea2  push    rdi
0x180027ea3  sub     rsp, 58h
0x180027ea7  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180027ead  mov     rbx, r9
0x180027eb0  test    al, 3
0x180027eb2  mov     esi, r8d
0x180027eb5  mov     rbp, rdx
0x180027eb8  mov     rdi, rcx
0x180027ebb  setnz   r10b
0x180027ebf  bt      eax, 1Ch
0x180027ec3  setb    al
0x180027ec6  test    al, r10b
0x180027ec9  jz      short loc_180027F07
0x180027ecb  mov     [r11-38h], rbx
0x180027ecf  lea     rax, aIpm2readfileCa; "Ipm2ReadFile called with hFile=%d, pBuf"...
0x180027ed6  mov     [rsp+78h+var_40], r8d
0x180027edb  lea     r9, aIpm2readfile; "Ipm2ReadFile"
0x180027ee2  mov     [r11-48h], rdx
0x180027ee6  mov     r8d, 7Bh ; '{'; unsigned int
0x180027eec  mov     [r11-50h], rcx
0x180027ef0  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027ef7  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180027efe  mov     [r11-58h], rax
0x180027f02  call    PuDbgPrint
0x180027f07  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180027f0b  jz      short loc_180027F65
0x180027f0d  test    rbp, rbp
0x180027f10  jz      short loc_180027F65
0x180027f12  test    esi, esi
0x180027f14  jz      short loc_180027F65
0x180027f16  test    rbx, rbx
0x180027f19  jz      short loc_180027F65
0x180027f1b  xor     r9d, r9d; lpNumberOfBytesRead
0x180027f1e  mov     [rsp+78h+lpOverlapped], rbx; lpOverlapped
0x180027f23  mov     r8d, esi; nNumberOfBytesToRead
0x180027f26  mov     rdx, rbp; lpBuffer
0x180027f29  mov     rcx, rdi; hFile
0x180027f2c  call    cs:__imp_ReadFile
0x180027f32  test    eax, eax
0x180027f34  jnz     short loc_180027F4D
0x180027f36  call    cs:__imp_GetLastError
0x180027f3c  cmp     eax, 0EAh
0x180027f41  jnz     short loc_180027F51
0x180027f43  mov     rcx, [rbx+18h]; hEvent
0x180027f47  call    cs:__imp_SetEvent
0x180027f4d  xor     eax, eax
0x180027f4f  jmp     short loc_180027F6A
0x180027f51  call    cs:__imp_GetLastError
0x180027f57  test    eax, eax
0x180027f59  jle     short loc_180027F6A
0x180027f5b  movzx   eax, ax
0x180027f5e  or      eax, 80070000h
0x180027f63  jmp     short loc_180027F6A
0x180027f65  mov     eax, 80070057h
0x180027f6a  add     rsp, 58h
0x180027f6e  pop     rdi
0x180027f6f  pop     rsi
0x180027f70  pop     rbp
0x180027f71  pop     rbx
0x180027f72  retn
```
