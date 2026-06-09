# CloseAndDeleteFileIfEmpty

- ea: `0x180040134`
- end: `0x180040252`
- name: `CloseAndDeleteFileIfEmpty`
- size: `286`
- prototype: `__int64 __fastcall(int, const WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800078ac`
- `0x1800d07e0`

## callees

- `0x18000e3c4`
- `0x180040134`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004023a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004023a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004017f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004017f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004018e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004018e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040222`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180040218`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180040218`
- `rtutils!TracePrintfExA` at `0x18004016c`
- `rtutils!TracePrintfExA` at `0x1800401b4`
- `rtutils!TracePrintfExA` at `0x18004020f`
- `rtutils!TracePrintfExA` at `0x18004016c`
- `rtutils!TracePrintfExA` at `0x1800401b4`
- `rtutils!TracePrintfExA` at `0x18004020f`

## string_xrefs

- `0x180040160`: `CloseAndDeleteFileIfEmpty: g_hmutexPb not initialized`
- `0x1800401a8`: `CloseAndDeleteFileIfEmpty: Acquire mutex failed = %d`
- `0x180040203`: `CloseAndDeleteFileIfEmpty: File is empty. Delete it.`

## pseudocode

```c
__int64 __fastcall CloseAndDeleteFileIfEmpty(int a1, const WCHAR *a2)
{
  __int64 v2; // rsi
  DWORD v5; // edi
  DWORD LastError; // eax
  __int64 ***v7; // rcx
  __int64 *i; // rax

  v2 = a1;
  if ( g_hmutexPb )
  {
    v5 = WaitForSingleObject(g_hmutexPb, 0xFFFFFFFF);
    if ( (v5 & 0xFFFFFF7F) != 0 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CloseAndDeleteFileIfEmpty: Acquire mutex failed = %d", LastError);
    }
    else
    {
      if ( (unsigned int)v2 <= 0x1F3 && (v7 = (__int64 ***)gpRasfiles[v2]) != 0 )
      {
        for ( i = **v7; i != (__int64 *)*v7; i = (__int64 *)*i )
        {
          if ( (*((_BYTE *)i + 25) & 1) != 0 )
            goto LABEL_19;
        }
        if ( (unsigned int)RasfileClose((unsigned int)v2) )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "CloseAndDeleteFileIfEmpty: File is empty. Delete it.");
          if ( !DeleteFileW(a2) )
            v5 = GetLastError();
        }
      }
      else
      {
LABEL_19:
        RasfileClose((unsigned int)v2);
      }
      ReleaseMutex(g_hmutexPb);
    }
    return v5;
  }
  else
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "CloseAndDeleteFileIfEmpty: g_hmutexPb not initialized");
    return 10;
  }
}

```

## disassembly

```asm
0x180040134  mov     [rsp+arg_0], rbp
0x180040139  mov     [rsp+arg_8], rsi
0x18004013e  push    rdi
0x18004013f  sub     rsp, 20h
0x180040143  movsxd  rsi, ecx
0x180040146  mov     rbp, rdx
0x180040149  mov     rcx, cs:g_hmutexPb; hHandle
0x180040150  test    rcx, rcx
0x180040153  jnz     short loc_18004017C
0x180040155  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18004015b  cmp     ecx, 0FFFFFFFFh
0x18004015e  jz      short loc_180040172
0x180040160  lea     r8, aCloseanddelete_0; "CloseAndDeleteFileIfEmpty: g_hmutexPb n"...
0x180040167  mov     edx, 0Ch; dwFlags
0x18004016c  call    cs:__imp_TracePrintfExA
0x180040172  mov     eax, 0Ah
0x180040177  jmp     loc_180040242
0x18004017c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004017f  call    cs:__imp_WaitForSingleObject
0x180040185  mov     edi, eax
0x180040187  test    eax, 0FFFFFF7Fh
0x18004018c  jz      short loc_1800401BF
0x18004018e  call    cs:__imp_GetLastError
0x180040194  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18004019a  mov     edi, eax
0x18004019c  cmp     ecx, 0FFFFFFFFh
0x18004019f  jz      loc_180040240
0x1800401a5  mov     r9d, eax
0x1800401a8  lea     r8, aCloseanddelete_1; "CloseAndDeleteFileIfEmpty: Acquire mute"...
0x1800401af  mov     edx, 0Ch; dwFlags
0x1800401b4  call    cs:__imp_TracePrintfExA
0x1800401ba  jmp     loc_180040240
0x1800401bf  cmp     esi, 1F3h
0x1800401c5  ja      short loc_18004022C
0x1800401c7  lea     rcx, gpRasfiles
0x1800401ce  mov     rcx, [rcx+rsi*8]
0x1800401d2  test    rcx, rcx
0x1800401d5  jz      short loc_18004022C
0x1800401d7  mov     rdx, [rcx]
0x1800401da  mov     rax, [rdx]
0x1800401dd  cmp     rax, rdx
0x1800401e0  jz      short loc_1800401ED
0x1800401e2  test    byte ptr [rax+19h], 1
0x1800401e6  jnz     short loc_18004022C
0x1800401e8  mov     rax, [rax]
0x1800401eb  jmp     short loc_1800401DD
0x1800401ed  mov     ecx, esi
0x1800401ef  call    RasfileClose
0x1800401f4  test    eax, eax
0x1800401f6  jz      short loc_180040233
0x1800401f8  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800401fe  cmp     ecx, 0FFFFFFFFh
0x180040201  jz      short loc_180040215
0x180040203  lea     r8, aCloseanddelete; "CloseAndDeleteFileIfEmpty: File is empt"...
0x18004020a  mov     edx, 0Ch; dwFlags
0x18004020f  call    cs:__imp_TracePrintfExA
0x180040215  mov     rcx, rbp; lpFileName
0x180040218  call    cs:__imp_DeleteFileW
0x18004021e  test    eax, eax
0x180040220  jnz     short loc_180040233
0x180040222  call    cs:__imp_GetLastError
0x180040228  mov     edi, eax
0x18004022a  jmp     short loc_180040233
0x18004022c  mov     ecx, esi
0x18004022e  call    RasfileClose
0x180040233  mov     rcx, cs:g_hmutexPb; hMutex
0x18004023a  call    cs:__imp_ReleaseMutex
0x180040240  mov     eax, edi
0x180040242  mov     rbp, [rsp+28h+arg_0]
0x180040247  mov     rsi, [rsp+28h+arg_8]
0x18004024c  add     rsp, 20h
0x180040250  pop     rdi
0x180040251  retn
```
