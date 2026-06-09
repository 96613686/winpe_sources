# Ipm2WriteFileChunked(void *,void *,ulong,_OVERLAPPED *)

- ea: `0x180028360`
- end: `0x1800284a9`
- name: `?Ipm2WriteFileChunked@@YAJPEAX0KPEAU_OVERLAPPED@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer, unsigned int, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029130`

## callees

- `0x180007300`
- `0x180028360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002846e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002846e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028482`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028426`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028426`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180028451`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180028451`

## string_xrefs

- `0x1800283c0`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002839f`: `Ipm2WriteFileChunked called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x1800283ab`: `Ipm2WriteFileChunked`

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
0x180028360  mov     r11, rsp
0x180028363  push    rbx
0x180028364  push    rbp
0x180028365  push    rsi
0x180028366  push    rdi
0x180028367  push    r14
0x180028369  push    r15
0x18002836b  sub     rsp, 58h
0x18002836f  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180028375  mov     rbp, r9
0x180028378  test    al, 3
0x18002837a  mov     dword ptr [r11+8], 0
0x180028382  mov     esi, r8d
0x180028385  mov     rbx, rdx
0x180028388  setnz   r10b
0x18002838c  mov     r14, rcx
0x18002838f  bt      eax, 1Ch
0x180028393  setb    al
0x180028396  test    al, r10b
0x180028399  jz      short loc_1800283D7
0x18002839b  mov     [r11-48h], r9
0x18002839f  lea     rax, aIpm2writefilec; "Ipm2WriteFileChunked called with hFile="...
0x1800283a6  mov     [rsp+88h+var_50], r8d
0x1800283ab  lea     r9, aIpm2writefilec_0; "Ipm2WriteFileChunked"
0x1800283b2  mov     [r11-58h], rdx
0x1800283b6  mov     r8d, 1C1h; unsigned int
0x1800283bc  mov     [r11-60h], rcx
0x1800283c0  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800283c7  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800283ce  mov     [r11-68h], rax
0x1800283d2  call    PuDbgPrint
0x1800283d7  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800283db  jz      loc_180028497
0x1800283e1  test    rbx, rbx
0x1800283e4  jz      loc_180028497
0x1800283ea  test    esi, esi
0x1800283ec  jz      loc_180028497
0x1800283f2  test    rbp, rbp
0x1800283f5  jz      loc_180028497
0x1800283fb  xor     edi, edi
0x1800283fd  mov     r15d, 10000h
0x180028403  cmp     edi, esi
0x180028405  jnb     loc_180028493
0x18002840b  mov     r8d, esi
0x18002840e  mov     [rsp+88h+lpOverlapped], rbp; lpOverlapped
0x180028413  sub     r8d, edi
0x180028416  mov     rdx, rbx; lpBuffer
0x180028419  cmp     r8d, r15d
0x18002841c  mov     rcx, r14; hFile
0x18002841f  cmova   r8d, r15d; nNumberOfBytesToWrite
0x180028423  xor     r9d, r9d; lpNumberOfBytesWritten
0x180028426  call    cs:__imp_WriteFile
0x18002842c  test    eax, eax
0x18002842e  jnz     short loc_18002843D
0x180028430  call    cs:__imp_GetLastError
0x180028436  cmp     eax, 3E5h
0x18002843b  jnz     short loc_18002846E
0x18002843d  mov     r9d, 1; bWait
0x180028443  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002844b  mov     rdx, rbp; lpOverlapped
0x18002844e  mov     rcx, r14; hFile
0x180028451  call    cs:__imp_GetOverlappedResult
0x180028457  test    eax, eax
0x180028459  jz      short loc_180028482
0x18002845b  mov     eax, [rsp+88h+NumberOfBytesTransferred]
0x180028462  add     rbx, rax
0x180028465  add     edi, [rsp+88h+NumberOfBytesTransferred]
0x18002846c  jmp     short loc_180028403
0x18002846e  call    cs:__imp_GetLastError
0x180028474  test    eax, eax
0x180028476  jle     short loc_18002849C
0x180028478  movzx   eax, ax
0x18002847b  or      eax, 80070000h
0x180028480  jmp     short loc_18002849C
0x180028482  call    cs:__imp_GetLastError
0x180028488  test    eax, eax
0x18002848a  jnz     short loc_18002846E
0x18002848c  mov     eax, 80004005h
0x180028491  jmp     short loc_18002849C
0x180028493  xor     eax, eax
0x180028495  jmp     short loc_18002849C
0x180028497  mov     eax, 80070057h
0x18002849c  add     rsp, 58h
0x1800284a0  pop     r15
0x1800284a2  pop     r14
0x1800284a4  pop     rdi
0x1800284a5  pop     rsi
0x1800284a6  pop     rbp
0x1800284a7  pop     rbx
0x1800284a8  retn
```
