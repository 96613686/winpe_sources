# Ipm2WriteFile(void *,void *,ulong,_OVERLAPPED *)

- ea: `0x18002828c`
- end: `0x180028359`
- name: `?Ipm2WriteFile@@YAJPEAX0KPEAU_OVERLAPPED@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPOVERLAPPED lpOverlapped)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029130`

## callees

- `0x180007300`
- `0x18002828c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028337`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002831c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002831c`

## string_xrefs

- `0x1800282e0`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800282bf`: `Ipm2WriteFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x1800282cb`: `Ipm2WriteFile`

## pseudocode

```c
signed int __fastcall Ipm2WriteFile(
        HANDLE hFile,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
        LPOVERLAPPED lpOverlapped)
{
  signed int result; // eax

  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x178u,
      "Ipm2WriteFile",
      "Ipm2WriteFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n",
      (char)hFile);
  if ( hFile == (HANDLE)-1LL || !lpBuffer || !nNumberOfBytesToWrite || !lpOverlapped )
    return -2147024809;
  if ( WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, 0, lpOverlapped) || GetLastError() == 997 )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002828c  mov     r11, rsp
0x18002828f  push    rbx
0x180028290  push    rbp
0x180028291  push    rsi
0x180028292  push    rdi
0x180028293  sub     rsp, 58h
0x180028297  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002829d  mov     rdi, r9
0x1800282a0  test    al, 3
0x1800282a2  mov     esi, r8d
0x1800282a5  mov     rbp, rdx
0x1800282a8  mov     rbx, rcx
0x1800282ab  setnz   r10b
0x1800282af  bt      eax, 1Ch
0x1800282b3  setb    al
0x1800282b6  test    al, r10b
0x1800282b9  jz      short loc_1800282F7
0x1800282bb  mov     [r11-38h], r9
0x1800282bf  lea     rax, aIpm2writefileC; "Ipm2WriteFile called with hFile=%d, pBu"...
0x1800282c6  mov     [rsp+78h+var_40], r8d
0x1800282cb  lea     r9, aIpm2writefile; "Ipm2WriteFile"
0x1800282d2  mov     [r11-48h], rdx
0x1800282d6  mov     r8d, 178h; unsigned int
0x1800282dc  mov     [r11-50h], rcx
0x1800282e0  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800282e7  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800282ee  mov     [r11-58h], rax
0x1800282f2  call    PuDbgPrint
0x1800282f7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800282fb  jz      short loc_18002834B
0x1800282fd  test    rbp, rbp
0x180028300  jz      short loc_18002834B
0x180028302  test    esi, esi
0x180028304  jz      short loc_18002834B
0x180028306  test    rdi, rdi
0x180028309  jz      short loc_18002834B
0x18002830b  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002830e  mov     [rsp+78h+lpOverlapped], rdi; lpOverlapped
0x180028313  mov     r8d, esi; nNumberOfBytesToWrite
0x180028316  mov     rdx, rbp; lpBuffer
0x180028319  mov     rcx, rbx; hFile
0x18002831c  call    cs:__imp_WriteFile
0x180028322  test    eax, eax
0x180028324  jnz     short loc_180028333
0x180028326  call    cs:__imp_GetLastError
0x18002832c  cmp     eax, 3E5h
0x180028331  jnz     short loc_180028337
0x180028333  xor     eax, eax
0x180028335  jmp     short loc_180028350
0x180028337  call    cs:__imp_GetLastError
0x18002833d  test    eax, eax
0x18002833f  jle     short loc_180028350
0x180028341  movzx   eax, ax
0x180028344  or      eax, 80070000h
0x180028349  jmp     short loc_180028350
0x18002834b  mov     eax, 80070057h
0x180028350  add     rsp, 58h
0x180028354  pop     rdi
0x180028355  pop     rsi
0x180028356  pop     rbp
0x180028357  pop     rbx
0x180028358  retn
```
