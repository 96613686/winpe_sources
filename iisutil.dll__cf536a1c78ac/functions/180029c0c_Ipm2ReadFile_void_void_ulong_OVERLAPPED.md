# Ipm2ReadFile(void *,void *,ulong,_OVERLAPPED *)

- ea: `0x180029c0c`
- end: `0x180029cfc`
- name: `?Ipm2ReadFile@@YAJPEAX0KPEAU_OVERLAPPED@@@Z`
- size: `240`
- prototype: `signed int __fastcall(HANDLE hFile, void *lpBuffer, DWORD nNumberOfBytesToRead, LPOVERLAPPED lpOverlapped)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002a430`
- `0x18002aad0`

## callees

- `0x180008000`
- `0x180029c0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cd3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029cc3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029cc3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180029c9c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180029c9c`

## string_xrefs

- `0x180029c60`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180029c3f`: `Ipm2ReadFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x180029c4b`: `Ipm2ReadFile`

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
0x180029c0c  mov     r11, rsp
0x180029c0f  push    rbx
0x180029c10  push    rbp
0x180029c11  push    rsi
0x180029c12  push    rdi
0x180029c13  sub     rsp, 58h
0x180029c17  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180029c1d  mov     rbx, r9
0x180029c20  test    al, 3
0x180029c22  mov     esi, r8d
0x180029c25  mov     rbp, rdx
0x180029c28  mov     rdi, rcx
0x180029c2b  setnz   r10b
0x180029c2f  bt      eax, 1Ch
0x180029c33  setb    al
0x180029c36  test    al, r10b
0x180029c39  jz      short loc_180029C77
0x180029c3b  mov     [r11-38h], rbx
0x180029c3f  lea     rax, aIpm2readfileCa; "Ipm2ReadFile called with hFile=%d, pBuf"...
0x180029c46  mov     [rsp+78h+var_40], r8d
0x180029c4b  lea     r9, aIpm2readfile; "Ipm2ReadFile"
0x180029c52  mov     [r11-48h], rdx
0x180029c56  mov     r8d, 7Bh ; '{'; unsigned int
0x180029c5c  mov     [r11-50h], rcx
0x180029c60  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029c67  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029c6e  mov     [r11-58h], rax
0x180029c72  call    PuDbgPrint
0x180029c77  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180029c7b  jz      short loc_180029CED
0x180029c7d  test    rbp, rbp
0x180029c80  jz      short loc_180029CED
0x180029c82  test    esi, esi
0x180029c84  jz      short loc_180029CED
0x180029c86  test    rbx, rbx
0x180029c89  jz      short loc_180029CED
0x180029c8b  xor     r9d, r9d; lpNumberOfBytesRead
0x180029c8e  mov     [rsp+78h+lpOverlapped], rbx; lpOverlapped
0x180029c93  mov     r8d, esi; nNumberOfBytesToRead
0x180029c96  mov     rdx, rbp; lpBuffer
0x180029c99  mov     rcx, rdi; hFile
0x180029c9c  call    cs:__imp_ReadFile
0x180029ca3  nop     dword ptr [rax+rax+00h]
0x180029ca8  test    eax, eax
0x180029caa  jnz     short loc_180029CCF
0x180029cac  call    cs:__imp_GetLastError
0x180029cb3  nop     dword ptr [rax+rax+00h]
0x180029cb8  cmp     eax, 0EAh
0x180029cbd  jnz     short loc_180029CD3
0x180029cbf  mov     rcx, [rbx+18h]; hEvent
0x180029cc3  call    cs:__imp_SetEvent
0x180029cca  nop     dword ptr [rax+rax+00h]
0x180029ccf  xor     eax, eax
0x180029cd1  jmp     short loc_180029CF2
0x180029cd3  call    cs:__imp_GetLastError
0x180029cda  nop     dword ptr [rax+rax+00h]
0x180029cdf  test    eax, eax
0x180029ce1  jle     short loc_180029CF2
0x180029ce3  movzx   eax, ax
0x180029ce6  or      eax, 80070000h
0x180029ceb  jmp     short loc_180029CF2
0x180029ced  mov     eax, 80070057h
0x180029cf2  add     rsp, 58h
0x180029cf6  pop     rdi
0x180029cf7  pop     rsi
0x180029cf8  pop     rbp
0x180029cf9  pop     rbx
0x180029cfa  retn
```
