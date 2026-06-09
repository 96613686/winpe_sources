# CheckElevatedLUAAndInitialize(ushort const *,unsigned __int64,int,void * *,void * *)

- ea: `0x18002a104`
- end: `0x18002a305`
- name: `?CheckElevatedLUAAndInitialize@@YAJPEBG_KHPEAPEAX2@Z`
- size: `513`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpName@<rcx>, SIZE_T dwNumberOfBytesToMap@<rdx>, int@<r8d>, void **@<r9>, void **)`
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18002bcf0`
- `0x18002bdc0`
- `0x18002bee0`
- `0x18002bfc0`
- `0x18002c0f0`

## callees

- `0x18000b200`
- `0x18002a104`
- `0x18002b6f0`
- `0x18002c3d0`
- `0x180035208`
- `0x180036664`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a226`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002a1d5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002a26c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002a1d5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002a26c`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002a200`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002a200`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18002a183`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18002a183`

## string_xrefs

- `0x18002a1ab`: `OpenFileMapping failed`

## pseudocode

```c
__int64 __fastcall CheckElevatedLUAAndInitialize(
        LPCWSTR lpName,
        SIZE_T dwNumberOfBytesToMap,
        int a3,
        void **a4,
        void **a5)
{
  void **v9; // rsi
  signed int v10; // ebx
  NCoreLibrary *v11; // rcx
  int LastErrorAsFailHR; // eax
  unsigned int v13; // eax
  unsigned int v14; // ecx
  NCoreLibrary *v15; // rcx
  void *v16; // rdi
  SIZE_T v17; // r12
  NCoreLibrary *v18; // rcx
  signed int LastError; // eax
  unsigned int v20; // edi
  DWORD v21; // eax
  NCoreLibrary *v22; // rcx
  unsigned int v23; // eax
  void *v25; // [rsp+40h] [rbp-18h] BYREF
  void *v26; // [rsp+48h] [rbp-10h] BYREF
  int v27; // [rsp+A0h] [rbp+48h] BYREF

  v27 = 0;
  v26 = 0;
  v25 = 0;
  if ( !lpName || !a4 || (v9 = a5) == 0 )
  {
    v10 = -2147024809;
    goto LABEL_26;
  }
  *a4 = 0;
  *v9 = 0;
  v10 = RunningAsLUA(&v27);
  if ( v10 >= 0 )
  {
    if ( v27 )
    {
      v10 = -2147024846;
      goto LABEL_26;
    }
    v26 = OpenFileMappingW(6u, 0, lpName);
    if ( !v26 )
    {
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v11);
      v10 = LastErrorAsFailHR;
      if ( LastErrorAsFailHR < 0 )
      {
        v13 = StatusFromHResult((unsigned int)LastErrorAsFailHR);
        SplLogPrinterSetupGenericEvent(
          &SETUP_PRINTER_OPERATION_FAILED,
          L"CheckElevatedLUAAndInitialize",
          L"OpenFileMapping failed",
          lpName,
          0,
          v13,
          v14);
        goto LABEL_26;
      }
    }
    v25 = MapViewOfFile(v26, 6u, 0, 0, dwNumberOfBytesToMap);
    v16 = v25;
    if ( v25 )
    {
      v10 = 0;
    }
    else
    {
      v10 = NCoreLibrary::GetLastErrorAsFailHR(v15);
      if ( v10 < 0 )
        goto LABEL_21;
    }
    if ( !a3 )
    {
LABEL_24:
      *a4 = v26;
      v26 = 0;
      *v9 = v16;
      v25 = 0;
      goto LABEL_26;
    }
    v17 = *(_QWORD *)v25;
    if ( !UnmapViewOfFile(v25) )
    {
      v10 = NCoreLibrary::GetLastErrorAsFailHR(v18);
      LastError = GetLastError();
      v20 = LastError;
      if ( LastError > 0 )
        v20 = (unsigned __int16)LastError | 0x80070000;
      v21 = GetLastError();
      SplLogPrinterSetupGenericEvent(
        &SETUP_PRINTER_OPERATION_FAILED,
        L"CheckElevatedLUAAndInitialize",
        L"UnmapViewOfFile failed",
        0,
        0,
        v21,
        v20);
    }
    if ( v10 >= 0 )
    {
      v25 = MapViewOfFile(v26, 6u, 0, 0, v17);
      v16 = v25;
      if ( v25 )
      {
        v10 = 0;
        goto LABEL_24;
      }
      v10 = NCoreLibrary::GetLastErrorAsFailHR(v22);
      if ( v10 >= 0 )
        goto LABEL_24;
    }
LABEL_21:
    v23 = StatusFromHResult((unsigned int)v10);
    SplLogPrinterSetupGenericEvent(
      &SETUP_PRINTER_OPERATION_FAILED,
      L"CheckElevatedLUAAndInitialize",
      L"MapViewOfFile failed",
      0,
      0,
      v23,
      v10);
  }
LABEL_26:
  FreeSharedMemory(&v25, &v26);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002a104  push    rbp
0x18002a106  push    rbx
0x18002a107  push    rsi
0x18002a108  push    rdi
0x18002a109  push    r12
0x18002a10b  push    r13
0x18002a10d  push    r14
0x18002a10f  push    r15
0x18002a111  mov     rbp, rsp
0x18002a114  sub     rsp, 58h
0x18002a118  xor     r14d, r14d
0x18002a11b  mov     r15, r9
0x18002a11e  mov     [rbp+arg_0], r14d
0x18002a122  mov     r12d, r8d
0x18002a125  mov     [rbp+var_10], r14
0x18002a129  mov     r13, rdx
0x18002a12c  mov     [rbp+var_18], r14
0x18002a130  mov     rdi, rcx
0x18002a133  test    rcx, rcx
0x18002a136  jz      loc_18002A2E0
0x18002a13c  test    r9, r9
0x18002a13f  jz      loc_18002A2E0
0x18002a145  mov     rsi, [rbp+arg_20]
0x18002a149  test    rsi, rsi
0x18002a14c  jz      loc_18002A2E0
0x18002a152  lea     rcx, [rbp+arg_0]; int *
0x18002a156  mov     [r9], r14
0x18002a159  mov     [rsi], r14
0x18002a15c  call    ?RunningAsLUA@@YAJPEAH@Z; RunningAsLUA(int *)
0x18002a161  mov     ebx, eax
0x18002a163  test    eax, eax
0x18002a165  js      loc_18002A2E5
0x18002a16b  cmp     [rbp+arg_0], r14d
0x18002a16f  jz      short loc_18002A17B
0x18002a171  mov     ebx, 80070032h
0x18002a176  jmp     loc_18002A2E5
0x18002a17b  xor     edx, edx; bInheritHandle
0x18002a17d  mov     r8, rdi; lpName
0x18002a180  lea     ecx, [rdx+6]; dwDesiredAccess
0x18002a183  call    cs:__imp_OpenFileMappingW
0x18002a189  mov     [rbp+var_10], rax
0x18002a18d  mov     r14, rax
0x18002a190  test    rax, rax
0x18002a193  jnz     short loc_18002A1C3
0x18002a195  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002a19a  mov     ebx, eax
0x18002a19c  test    eax, eax
0x18002a19e  jns     short loc_18002A1C3
0x18002a1a0  mov     ecx, eax
0x18002a1a2  call    StatusFromHResult
0x18002a1a7  mov     [rsp+58h+var_28], ecx
0x18002a1ab  lea     r8, aOpenfilemappin; "OpenFileMapping failed"
0x18002a1b2  mov     [rsp+58h+var_30], eax
0x18002a1b6  mov     r9, rdi
0x18002a1b9  mov     [rsp+58h+dwNumberOfBytesToMap], r14
0x18002a1be  jmp     loc_18002A2B0
0x18002a1c3  xor     r9d, r9d; dwFileOffsetLow
0x18002a1c6  mov     [rsp+58h+dwNumberOfBytesToMap], r13; dwNumberOfBytesToMap
0x18002a1cb  xor     r8d, r8d; dwFileOffsetHigh
0x18002a1ce  mov     rcx, r14; hFileMappingObject
0x18002a1d1  lea     edx, [r9+6]; dwDesiredAccess
0x18002a1d5  call    cs:__imp_MapViewOfFile
0x18002a1db  xor     r13d, r13d
0x18002a1de  mov     [rbp+var_18], rax
0x18002a1e2  mov     rdi, rax
0x18002a1e5  test    rax, rax
0x18002a1e8  jz      loc_18002A283
0x18002a1ee  mov     ebx, r13d
0x18002a1f1  test    r12d, r12d
0x18002a1f4  jz      loc_18002A2D0
0x18002a1fa  mov     r12, [rdi]
0x18002a1fd  mov     rcx, rdi; lpBaseAddress
0x18002a200  call    cs:__imp_UnmapViewOfFile
0x18002a206  test    eax, eax
0x18002a208  jnz     short loc_18002A256
0x18002a20a  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002a20f  mov     ebx, eax
0x18002a211  call    cs:__imp_GetLastError
0x18002a217  mov     edi, eax
0x18002a219  test    eax, eax
0x18002a21b  jle     short loc_18002A226
0x18002a21d  movzx   edi, ax
0x18002a220  or      edi, 80070000h
0x18002a226  call    cs:__imp_GetLastError
0x18002a22c  mov     [rsp+58h+var_28], edi; unsigned int
0x18002a230  lea     r8, aUnmapviewoffil; "UnmapViewOfFile failed"
0x18002a237  mov     [rsp+58h+var_30], eax; unsigned int
0x18002a23b  lea     rdx, aCheckelevatedl; "CheckElevatedLUAAndInitialize"
0x18002a242  xor     r9d, r9d; unsigned __int16 *
0x18002a245  mov     [rsp+58h+dwNumberOfBytesToMap], r13; unsigned __int16 *
0x18002a24a  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18002a251  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18002a256  test    ebx, ebx
0x18002a258  js      short loc_18002A292
0x18002a25a  xor     r9d, r9d; dwFileOffsetLow
0x18002a25d  mov     [rsp+58h+dwNumberOfBytesToMap], r12; dwNumberOfBytesToMap
0x18002a262  xor     r8d, r8d; dwFileOffsetHigh
0x18002a265  mov     rcx, r14; hFileMappingObject
0x18002a268  lea     edx, [r9+6]; dwDesiredAccess
0x18002a26c  call    cs:__imp_MapViewOfFile
0x18002a272  mov     [rbp+var_18], rax
0x18002a276  mov     rdi, rax
0x18002a279  test    rax, rax
0x18002a27c  jz      short loc_18002A2C5
0x18002a27e  mov     ebx, r13d
0x18002a281  jmp     short loc_18002A2D0
0x18002a283  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002a288  mov     ebx, eax
0x18002a28a  test    eax, eax
0x18002a28c  jns     loc_18002A1F1
0x18002a292  mov     ecx, ebx
0x18002a294  call    StatusFromHResult
0x18002a299  mov     [rsp+58h+var_28], ebx; unsigned int
0x18002a29d  lea     r8, aMapviewoffileF; "MapViewOfFile failed"
0x18002a2a4  mov     [rsp+58h+var_30], eax; unsigned int
0x18002a2a8  xor     r9d, r9d; unsigned __int16 *
0x18002a2ab  mov     [rsp+58h+dwNumberOfBytesToMap], r13; unsigned __int16 *
0x18002a2b0  lea     rdx, aCheckelevatedl; "CheckElevatedLUAAndInitialize"
0x18002a2b7  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18002a2be  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18002a2c3  jmp     short loc_18002A2E5
0x18002a2c5  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002a2ca  mov     ebx, eax
0x18002a2cc  test    eax, eax
0x18002a2ce  js      short loc_18002A292
0x18002a2d0  mov     [r15], r14
0x18002a2d3  mov     [rbp+var_10], r13
0x18002a2d7  mov     [rsi], rdi
0x18002a2da  mov     [rbp+var_18], r13
0x18002a2de  jmp     short loc_18002A2E5
0x18002a2e0  mov     ebx, 80070057h
0x18002a2e5  lea     rdx, [rbp+var_10]; void **
0x18002a2e9  lea     rcx, [rbp+var_18]; void **
0x18002a2ed  call    ?FreeSharedMemory@@YAXPEAPEAX0@Z; FreeSharedMemory(void * *,void * *)
0x18002a2f2  mov     eax, ebx
0x18002a2f4  add     rsp, 58h
0x18002a2f8  pop     r15
0x18002a2fa  pop     r14
0x18002a2fc  pop     r13
0x18002a2fe  pop     r12
0x18002a300  pop     rdi
0x18002a301  pop     rsi
0x18002a302  pop     rbx
0x18002a303  pop     rbp
0x18002a304  retn
```
