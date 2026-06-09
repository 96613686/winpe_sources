# Ipm2WriteFile(void *,void *,ulong,_OVERLAPPED *)

- ea: `0x18002a054`
- end: `0x18002a134`
- name: `?Ipm2WriteFile@@YAJPEAX0KPEAU_OVERLAPPED@@@Z`
- size: `224`
- prototype: `signed int __fastcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPOVERLAPPED lpOverlapped)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002af70`

## callees

- `0x180008000`
- `0x18002a054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a10b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a10b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002a0e4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002a0e4`

## string_xrefs

- `0x18002a0a8`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a087`: `Ipm2WriteFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x18002a093`: `Ipm2WriteFile`

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
0x18002a054  mov     r11, rsp
0x18002a057  push    rbx
0x18002a058  push    rbp
0x18002a059  push    rsi
0x18002a05a  push    rdi
0x18002a05b  sub     rsp, 58h
0x18002a05f  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002a065  mov     rdi, r9
0x18002a068  test    al, 3
0x18002a06a  mov     esi, r8d
0x18002a06d  mov     rbp, rdx
0x18002a070  mov     rbx, rcx
0x18002a073  setnz   r10b
0x18002a077  bt      eax, 1Ch
0x18002a07b  setb    al
0x18002a07e  test    al, r10b
0x18002a081  jz      short loc_18002A0BF
0x18002a083  mov     [r11-38h], r9
0x18002a087  lea     rax, aIpm2writefileC; "Ipm2WriteFile called with hFile=%d, pBu"...
0x18002a08e  mov     [rsp+78h+var_40], r8d
0x18002a093  lea     r9, aIpm2writefile; "Ipm2WriteFile"
0x18002a09a  mov     [r11-48h], rdx
0x18002a09e  mov     r8d, 178h; unsigned int
0x18002a0a4  mov     [r11-50h], rcx
0x18002a0a8  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a0af  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002a0b6  mov     [r11-58h], rax
0x18002a0ba  call    PuDbgPrint
0x18002a0bf  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002a0c3  jz      short loc_18002A125
0x18002a0c5  test    rbp, rbp
0x18002a0c8  jz      short loc_18002A125
0x18002a0ca  test    esi, esi
0x18002a0cc  jz      short loc_18002A125
0x18002a0ce  test    rdi, rdi
0x18002a0d1  jz      short loc_18002A125
0x18002a0d3  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002a0d6  mov     [rsp+78h+lpOverlapped], rdi; lpOverlapped
0x18002a0db  mov     r8d, esi; nNumberOfBytesToWrite
0x18002a0de  mov     rdx, rbp; lpBuffer
0x18002a0e1  mov     rcx, rbx; hFile
0x18002a0e4  call    cs:__imp_WriteFile
0x18002a0eb  nop     dword ptr [rax+rax+00h]
0x18002a0f0  test    eax, eax
0x18002a0f2  jnz     short loc_18002A107
0x18002a0f4  call    cs:__imp_GetLastError
0x18002a0fb  nop     dword ptr [rax+rax+00h]
0x18002a100  cmp     eax, 3E5h
0x18002a105  jnz     short loc_18002A10B
0x18002a107  xor     eax, eax
0x18002a109  jmp     short loc_18002A12A
0x18002a10b  call    cs:__imp_GetLastError
0x18002a112  nop     dword ptr [rax+rax+00h]
0x18002a117  test    eax, eax
0x18002a119  jle     short loc_18002A12A
0x18002a11b  movzx   eax, ax
0x18002a11e  or      eax, 80070000h
0x18002a123  jmp     short loc_18002A12A
0x18002a125  mov     eax, 80070057h
0x18002a12a  add     rsp, 58h
0x18002a12e  pop     rdi
0x18002a12f  pop     rsi
0x18002a130  pop     rbp
0x18002a131  pop     rbx
0x18002a132  retn
```
