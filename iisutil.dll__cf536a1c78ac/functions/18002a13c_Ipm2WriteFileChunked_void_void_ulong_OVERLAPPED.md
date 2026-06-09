# Ipm2WriteFileChunked(void *,void *,ulong,_OVERLAPPED *)

- ea: `0x18002a13c`
- end: `0x18002a2a4`
- name: `?Ipm2WriteFileChunked@@YAJPEAX0KPEAU_OVERLAPPED@@@Z`
- size: `360`
- prototype: `signed int __fastcall(HANDLE hFile, char *lpBuffer, unsigned int, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002af70`

## callees

- `0x180008000`
- `0x18002a13c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a25c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a25c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a276`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002a202`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002a202`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002a239`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002a239`

## string_xrefs

- `0x18002a19c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a17b`: `Ipm2WriteFileChunked called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x18002a187`: `Ipm2WriteFileChunked`

## pseudocode

```c
signed int __fastcall Ipm2WriteFileChunked(HANDLE hFile, char *lpBuffer, unsigned int a3, struct _OVERLAPPED *a4)
{
  unsigned int i; // edi
  DWORD v9; // r8d
  signed int result; // eax
  DWORD NumberOfBytesTransferred; // [rsp+90h] [rbp+8h] BYREF

  NumberOfBytesTransferred = 0;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x1C1u,
      "Ipm2WriteFileChunked",
      "Ipm2WriteFileChunked called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n",
      (char)hFile);
  if ( hFile == (HANDLE)-1LL || !lpBuffer || !a3 || !a4 )
    return -2147024809;
  for ( i = 0; ; i += NumberOfBytesTransferred )
  {
    if ( i >= a3 )
      return 0;
    v9 = a3 - i;
    if ( a3 - i > 0x10000 )
      v9 = 0x10000;
    if ( !WriteFile(hFile, lpBuffer, v9, 0, a4) && GetLastError() != 997 )
      break;
    if ( !GetOverlappedResult(hFile, a4, &NumberOfBytesTransferred, 1) )
    {
      if ( !GetLastError() )
        return -2147467259;
      break;
    }
    lpBuffer += NumberOfBytesTransferred;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002a13c  mov     r11, rsp
0x18002a13f  push    rbx
0x18002a140  push    rbp
0x18002a141  push    rsi
0x18002a142  push    rdi
0x18002a143  push    r14
0x18002a145  push    r15
0x18002a147  sub     rsp, 58h
0x18002a14b  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002a151  mov     rbp, r9
0x18002a154  test    al, 3
0x18002a156  mov     dword ptr [r11+8], 0
0x18002a15e  mov     esi, r8d
0x18002a161  mov     rbx, rdx
0x18002a164  setnz   r10b
0x18002a168  mov     r14, rcx
0x18002a16b  bt      eax, 1Ch
0x18002a16f  setb    al
0x18002a172  test    al, r10b
0x18002a175  jz      short loc_18002A1B3
0x18002a177  mov     [r11-48h], r9
0x18002a17b  lea     rax, aIpm2writefilec; "Ipm2WriteFileChunked called with hFile="...
0x18002a182  mov     [rsp+88h+var_50], r8d
0x18002a187  lea     r9, aIpm2writefilec_0; "Ipm2WriteFileChunked"
0x18002a18e  mov     [r11-58h], rdx
0x18002a192  mov     r8d, 1C1h; unsigned int
0x18002a198  mov     [r11-60h], rcx
0x18002a19c  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a1a3  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002a1aa  mov     [r11-68h], rax
0x18002a1ae  call    PuDbgPrint
0x18002a1b3  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002a1b7  jz      loc_18002A291
0x18002a1bd  test    rbx, rbx
0x18002a1c0  jz      loc_18002A291
0x18002a1c6  test    esi, esi
0x18002a1c8  jz      loc_18002A291
0x18002a1ce  test    rbp, rbp
0x18002a1d1  jz      loc_18002A291
0x18002a1d7  xor     edi, edi
0x18002a1d9  mov     r15d, 10000h
0x18002a1df  cmp     edi, esi
0x18002a1e1  jnb     loc_18002A28D
0x18002a1e7  mov     r8d, esi
0x18002a1ea  mov     [rsp+88h+lpOverlapped], rbp; lpOverlapped
0x18002a1ef  sub     r8d, edi
0x18002a1f2  mov     rdx, rbx; lpBuffer
0x18002a1f5  cmp     r8d, r15d
0x18002a1f8  mov     rcx, r14; hFile
0x18002a1fb  cmova   r8d, r15d; nNumberOfBytesToWrite
0x18002a1ff  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002a202  call    cs:__imp_WriteFile
0x18002a209  nop     dword ptr [rax+rax+00h]
0x18002a20e  test    eax, eax
0x18002a210  jnz     short loc_18002A225
0x18002a212  call    cs:__imp_GetLastError
0x18002a219  nop     dword ptr [rax+rax+00h]
0x18002a21e  cmp     eax, 3E5h
0x18002a223  jnz     short loc_18002A25C
0x18002a225  mov     r9d, 1; bWait
0x18002a22b  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002a233  mov     rdx, rbp; lpOverlapped
0x18002a236  mov     rcx, r14; hFile
0x18002a239  call    cs:__imp_GetOverlappedResult
0x18002a240  nop     dword ptr [rax+rax+00h]
0x18002a245  test    eax, eax
0x18002a247  jz      short loc_18002A276
0x18002a249  mov     eax, [rsp+88h+NumberOfBytesTransferred]
0x18002a250  add     rbx, rax
0x18002a253  add     edi, [rsp+88h+NumberOfBytesTransferred]
0x18002a25a  jmp     short loc_18002A1DF
0x18002a25c  call    cs:__imp_GetLastError
0x18002a263  nop     dword ptr [rax+rax+00h]
0x18002a268  test    eax, eax
0x18002a26a  jle     short loc_18002A296
0x18002a26c  movzx   eax, ax
0x18002a26f  or      eax, 80070000h
0x18002a274  jmp     short loc_18002A296
0x18002a276  call    cs:__imp_GetLastError
0x18002a27d  nop     dword ptr [rax+rax+00h]
0x18002a282  test    eax, eax
0x18002a284  jnz     short loc_18002A25C
0x18002a286  mov     eax, 80004005h
0x18002a28b  jmp     short loc_18002A296
0x18002a28d  xor     eax, eax
0x18002a28f  jmp     short loc_18002A296
0x18002a291  mov     eax, 80070057h
0x18002a296  add     rsp, 58h
0x18002a29a  pop     r15
0x18002a29c  pop     r14
0x18002a29e  pop     rdi
0x18002a29f  pop     rsi
0x18002a2a0  pop     rbp
0x18002a2a1  pop     rbx
0x18002a2a2  retn
```
