# CFveApiBase::DevicePathToVolumeGuidName(ushort const *,ushort * *)

- ea: `0x18000be40`
- end: `0x18000c384`
- name: `?DevicePathToVolumeGuidName@CFveApiBase@@SAJPEBGPEAPEAG@Z`
- size: `1348`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callers

- `0x180006cc0`
- `0x18000ba70`
- `0x18007ccb8`
- `0x1800aaf90`

## callees

- `0x180005410`
- `0x18000b640`
- `0x18000ba30`
- `0x18000be40`
- `0x18000c38c`
- `0x18000ca50`
- `0x180060196`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bf44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c00e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bf44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c00e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c118`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c2bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fa93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c2bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fa93`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c1dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c1dd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000bf96`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000bf96`

## string_xrefs

- `0x18000c1d6`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall CFveApiBase::DevicePathToVolumeGuidName(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 FileW; // rsi
  _DWORD *lpOutBuffer; // r15
  DWORD nOutBufferSize; // ebx
  unsigned __int16 *v6; // r14
  __int64 v7; // rax
  __int64 v8; // rax
  const unsigned __int16 *v9; // rcx
  signed int LastHresultError; // edi
  const unsigned __int16 **v11; // r8
  __int64 i; // rsi
  _DWORD *v13; // rbx
  unsigned __int16 v14; // ax
  int v15; // eax
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdx
  unsigned __int16 *v19; // rcx
  __int64 v20; // r10
  unsigned __int16 v21; // r9
  signed int LastError; // eax
  __int64 v23; // r13
  SIZE_T v24; // r8
  unsigned __int16 *v26; // rax
  __int64 v27; // [rsp+48h] [rbp-2E0h]
  __int64 v28; // [rsp+68h] [rbp-2C0h]
  __int64 v29; // [rsp+70h] [rbp-2B8h]
  DWORD BytesReturned; // [rsp+C8h] [rbp-260h] BYREF
  int InBuffer; // [rsp+D0h] [rbp-258h] BYREF
  __int16 v34; // [rsp+D4h] [rbp-254h]
  int v35; // [rsp+D8h] [rbp-250h]
  __int16 v36; // [rsp+DCh] [rbp-24Ch]
  int v37; // [rsp+E0h] [rbp-248h]
  __int16 v38; // [rsp+E4h] [rbp-244h]
  char v39[520]; // [rsp+E8h] [rbp-240h] BYREF

  FileW = -1;
  memset_0(&InBuffer, 0, 0x220u);
  lpOutBuffer = 0;
  nOutBufferSize = 1088;
  BytesReturned = 0;
  v6 = 0;
  InBuffer = 0;
  v34 = 0;
  v7 = 0;
  if ( a1 )
  {
    v8 = 130;
    v9 = a1;
    LastHresultError = 0;
    while ( v8 && *v9 )
    {
      ++v9;
      --v8;
    }
    if ( !v8 )
      LastHresultError = -2147024809;
    if ( LastHresultError < 0 )
      v29 = 0;
    else
      v29 = 130 - v8;
    v7 = v29;
  }
  else
  {
    LastHresultError = -2147024809;
  }
  if ( LastHresultError < 0 )
    v28 = 0;
  else
    v28 = 2 * v7;
  if ( LastHresultError >= 0 )
  {
    v35 = 0;
    v36 = 0;
    v37 = 24;
    v23 = v28;
    v38 = v28;
    memcpy_0(v39, a1, (unsigned __int16)v28);
    FileW = (__int64)CreateFileW(L"\\\\.\\MountPointManager", 0, 3u, 0, 3u, 0, 0);
    v27 = FileW;
    if ( FileW == -1 )
    {
      LastHresultError = GetLastHresultError();
    }
    else
    {
      while ( 1 )
      {
        if ( lpOutBuffer )
          CFveApiBase::FastFree(lpOutBuffer);
        v24 = 1;
        if ( nOutBufferSize )
          v24 = nOutBufferSize;
        lpOutBuffer = HeapAlloc(CFveApiBase::_ProcessHeap, 0, v24);
        if ( !lpOutBuffer )
        {
          LastHresultError = -2147024882;
          goto LABEL_60;
        }
        if ( DeviceIoControl(
               (HANDLE)FileW,
               0x6D0008u,
               &InBuffer,
               0x220u,
               lpOutBuffer,
               nOutBufferSize,
               &BytesReturned,
               0) )
        {
          break;
        }
        LastError = GetLastError();
        if ( LastError != 122 && LastError != 234 )
        {
          if ( LastError == 87 )
            LastError = 0;
LABEL_33:
          if ( LastError <= 0 )
            LastHresultError = LastError;
          else
            LastHresultError = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_60;
        }
        if ( 2 * nOutBufferSize <= nOutBufferSize )
          goto LABEL_33;
        nOutBufferSize *= 2;
      }
      for ( i = 0; (unsigned int)i < lpOutBuffer[1] && !v6; i = (unsigned int)(i + 1) )
      {
        v13 = &lpOutBuffer[6 * i];
        v14 = *((_WORD *)v13 + 6);
        if ( v14 )
        {
          v15 = CFveApiBase::CheckVolumeNameGuid(
                  (const unsigned __int16 *)((char *)lpOutBuffer + (unsigned int)v13[2]),
                  v14,
                  v11);
          LastHresultError = v15;
          if ( v15 < 0 )
            break;
          if ( v15 )
          {
            LastHresultError = 0;
          }
          else
          {
            v6 = (unsigned __int16 *)HeapAlloc(CFveApiBase::_ProcessHeap, 0, *((unsigned __int16 *)v13 + 6) + 2LL);
            if ( !v6 )
            {
              LastHresultError = -2147024882;
              break;
            }
            v16 = *((unsigned __int16 *)v13 + 6);
            v17 = (v16 + 2) >> 1;
            if ( v17 )
            {
              v11 = (const unsigned __int16 **)((char *)lpOutBuffer + (unsigned int)v13[2]);
              v18 = v16 >> 1;
              v19 = v6;
              LastHresultError = 0;
              v20 = 0;
              while ( v17 )
              {
                if ( !v18 )
                  goto LABEL_21;
                v21 = *(_WORD *)v11;
                if ( !*(_WORD *)v11 )
                  goto LABEL_21;
                v11 = (const unsigned __int16 **)((char *)v11 + 2);
                *v19++ = v21;
                --v17;
                --v18;
                ++v20;
              }
              --v19;
              LastHresultError = -2147024774;
LABEL_21:
              *v19 = 0;
            }
            else
            {
              LastHresultError = -2147024809;
            }
            if ( LastHresultError < 0 )
              break;
            if ( v6[1] == 63 )
              v6[1] = 92;
          }
        }
      }
      FileW = v27;
    }
  }
  else
  {
    v23 = v28;
  }
LABEL_60:
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( lpOutBuffer && !HeapFree(CFveApiBase::_ProcessHeap, 0, lpOutBuffer) )
    GetLastHresultError();
  if ( LastHresultError < 0 )
    goto LABEL_73;
  if ( !v6 )
  {
    v26 = (unsigned __int16 *)CFveApiBase::FastAlloc(v23 + 30);
    v6 = v26;
    if ( !v26 )
    {
      LastHresultError = -2147024882;
      goto LABEL_73;
    }
    LastHresultError = StringCbPrintfW(v26, v23 + 30, L"\\\\?\\GlobalRoot%s", a1);
  }
  if ( LastHresultError >= 0 )
  {
    *a2 = v6;
    return (unsigned int)LastHresultError;
  }
LABEL_73:
  if ( v6 )
    CFveApiBase::FastFree(v6);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x18000be40  mov     [rsp+arg_10], rbx
0x18000be45  mov     [rsp+arg_18], rsi
0x18000be4a  push    rdi
0x18000be4b  push    r12
0x18000be4d  push    r13
0x18000be4f  push    r14
0x18000be51  push    r15
0x18000be53  sub     rsp, 300h
0x18000be5a  mov     rax, cs:__security_cookie
0x18000be61  xor     rax, rsp
0x18000be64  mov     [rsp+328h+var_38], rax
0x18000be6c  mov     [rsp+328h+var_270], rdx
0x18000be74  mov     rdi, rcx
0x18000be77  mov     [rsp+328h+Src], rcx
0x18000be7f  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000be86  mov     [rsp+328h+var_2E0], rsi
0x18000be8b  xor     edx, edx; Val
0x18000be8d  mov     r8d, 220h; Size
0x18000be93  lea     rcx, [rsp+328h+InBuffer]; void *
0x18000be9b  call    memset_0
0x18000bea0  xor     r10d, r10d
0x18000bea3  mov     r15d, r10d
0x18000bea6  mov     [rsp+328h+var_2D0], r10
0x18000beab  mov     ebx, 440h
0x18000beb0  mov     [rsp+328h+BytesReturned], r10d
0x18000beb8  mov     [rsp+328h+var_2C0], r10
0x18000bebd  mov     r14d, r10d
0x18000bec0  mov     [rsp+328h+InBuffer], r10d
0x18000bec8  mov     [rsp+328h+var_254], r10w
0x18000bed1  lea     r9, [rsp+328h+var_2C0]
0x18000bed6  mov     eax, r10d
0x18000bed9  mov     [rsp+328h+var_2B8], rax
0x18000bede  test    rdi, rdi
0x18000bee1  jz      loc_18000C26B
0x18000bee7  lea     r8, [rsp+328h+var_2B8]
0x18000beec  mov     edx, 82h
0x18000bef1  mov     eax, edx
0x18000bef3  mov     [rsp+328h+var_290], rdx
0x18000befb  mov     rcx, rdi
0x18000befe  mov     [rsp+328h+var_298], rcx
0x18000bf06  mov     edi, r10d
0x18000bf09  nop     dword ptr [rax+00000000h]
0x18000bf10  test    rax, rax
0x18000bf13  jz      loc_18000C22D
0x18000bf19  cmp     [rcx], di
0x18000bf1c  jz      loc_18000C22D
0x18000bf22  add     rcx, 2
0x18000bf26  mov     [rsp+328h+var_298], rcx
0x18000bf2e  dec     rax
0x18000bf31  mov     [rsp+328h+var_290], rax
0x18000bf39  jmp     short loc_18000BF10
0x18000bf3b  xor     edx, edx; dwFlags
0x18000bf3d  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x18000bf44  call    cs:__imp_HeapAlloc
0x18000bf4b  nop     dword ptr [rax+rax+00h]
0x18000bf50  mov     r15, rax
0x18000bf53  mov     [rsp+328h+var_2D0], rax
0x18000bf58  test    rax, rax
0x18000bf5b  jz      loc_18000C291
0x18000bf61  mov     [rsp+328h+lpOverlapped], 0; lpOverlapped
0x18000bf6a  lea     rax, [rsp+328h+BytesReturned]
0x18000bf72  mov     [rsp+328h+lpBytesReturned], rax; lpBytesReturned
0x18000bf77  mov     [rsp+328h+nOutBufferSize], ebx; nOutBufferSize
0x18000bf7b  mov     [rsp+328h+lpOutBuffer], r15; lpOutBuffer
0x18000bf80  mov     r9d, 220h; nInBufferSize
0x18000bf86  lea     r8, [rsp+328h+InBuffer]; lpInBuffer
0x18000bf8e  mov     edx, 6D0008h; dwIoControlCode
0x18000bf93  mov     rcx, rsi; hDevice
0x18000bf96  call    cs:__imp_DeviceIoControl
0x18000bf9d  nop     dword ptr [rax+rax+00h]
0x18000bfa2  test    eax, eax
0x18000bfa4  jz      loc_18000C118
0x18000bfaa  xor     esi, esi
0x18000bfac  mov     [rsp+328h+var_2C8], esi
0x18000bfb0  cmp     esi, [r15+4]
0x18000bfb4  jnb     loc_18000C2A5
0x18000bfba  test    r14, r14
0x18000bfbd  jnz     loc_18000C2A5
0x18000bfc3  mov     eax, esi
0x18000bfc5  lea     rcx, [rsi+rsi*2]
0x18000bfc9  lea     rbx, [r15+rcx*8]
0x18000bfcd  movzx   eax, word ptr [rbx+0Ch]
0x18000bfd1  test    ax, ax
0x18000bfd4  jz      loc_18000C116
0x18000bfda  movzx   edx, ax; unsigned int
0x18000bfdd  mov     ecx, [rbx+8]
0x18000bfe0  add     rcx, r15; unsigned __int16 *
0x18000bfe3  call    ?CheckVolumeNameGuid@CFveApiBase@@SAJPEBGKPEAPEBG@Z; CFveApiBase::CheckVolumeNameGuid(ushort const *,ulong,ushort const * *)
0x18000bfe8  mov     edi, eax
0x18000bfea  mov     [rsp+328h+var_2E8], eax
0x18000bfee  test    eax, eax
0x18000bff0  js      loc_18000C2A5
0x18000bff6  jnz     loc_18000C110
0x18000bffc  movzx   r8d, word ptr [rbx+0Ch]
0x18000c001  add     r8, 2; dwBytes
0x18000c005  xor     edx, edx; dwFlags
0x18000c007  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x18000c00e  call    cs:__imp_HeapAlloc
0x18000c015  nop     dword ptr [rax+rax+00h]
0x18000c01a  mov     r14, rax
0x18000c01d  mov     [rsp+328h+var_268], rax
0x18000c025  test    rax, rax
0x18000c028  jz      loc_18000C29C
0x18000c02e  movzx   edx, word ptr [rbx+0Ch]
0x18000c032  lea     rax, [rdx+2]
0x18000c036  shr     rax, 1
0x18000c039  jz      loc_18000C2AC
0x18000c03f  mov     r8d, [rbx+8]
0x18000c043  add     r8, r15
0x18000c046  shr     rdx, 1
0x18000c049  mov     [rsp+328h+var_278], rdx
0x18000c051  mov     [rsp+328h+var_288], r8
0x18000c059  mov     [rsp+328h+var_280], rax
0x18000c061  mov     rcx, r14
0x18000c064  mov     [rsp+328h+var_2B0], rcx
0x18000c069  xor     edi, edi
0x18000c06b  xor     r10d, r10d
0x18000c06e  mov     [rsp+328h+var_2A8], r10
0x18000c076  test    rax, rax
0x18000c079  jz      short loc_18000C0F5
0x18000c07b  test    rdx, rdx
0x18000c07e  jz      short loc_18000C0C6
0x18000c080  movzx   r9d, word ptr [r8]
0x18000c084  test    r9w, r9w
0x18000c088  jz      short loc_18000C0C6
0x18000c08a  add     r8, 2
0x18000c08e  mov     [rsp+328h+var_288], r8
0x18000c096  mov     [rcx], r9w
0x18000c09a  add     rcx, 2
0x18000c09e  mov     [rsp+328h+var_2B0], rcx
0x18000c0a3  dec     rax
0x18000c0a6  mov     [rsp+328h+var_280], rax
0x18000c0ae  dec     rdx
0x18000c0b1  mov     [rsp+328h+var_278], rdx
0x18000c0b9  inc     r10
0x18000c0bc  mov     [rsp+328h+var_2A8], r10
0x18000c0c4  jmp     short loc_18000C076
0x18000c0c6  test    rax, rax
0x18000c0c9  jz      short loc_18000C0F5
0x18000c0cb  xor     eax, eax
0x18000c0cd  mov     [rcx], ax
0x18000c0d0  mov     [rsp+328h+var_2E8], edi
0x18000c0d4  test    edi, edi
0x18000c0d6  js      loc_18000C2A5
0x18000c0dc  cmp     word ptr [r14+2], 3Fh ; '?'
0x18000c0e2  jnz     short loc_18000C0EE
0x18000c0e4  mov     eax, 5Ch ; '\'
0x18000c0e9  mov     [r14+2], ax
0x18000c0ee  inc     esi
0x18000c0f0  jmp     loc_18000BFAC
0x18000c0f5  sub     rcx, 2
0x18000c0f9  mov     [rsp+328h+var_2B0], rcx
0x18000c0fe  dec     r10
0x18000c101  mov     [rsp+328h+var_2A8], r10
0x18000c109  mov     edi, 8007007Ah
0x18000c10e  jmp     short loc_18000C0CB
0x18000c110  xor     edi, edi
0x18000c112  mov     [rsp+328h+var_2E8], edi
0x18000c116  jmp     short loc_18000C0EE
0x18000c118  call    cs:__imp_GetLastError
0x18000c11f  nop     dword ptr [rax+rax+00h]
0x18000c124  mov     [rsp+328h+var_2D8], eax
0x18000c128  cmp     eax, 7Ah ; 'z'
0x18000c12b  jz      short loc_18000C159
0x18000c12d  cmp     eax, 0EAh
0x18000c132  jz      short loc_18000C159
0x18000c134  cmp     eax, 57h ; 'W'
0x18000c137  jnz     short loc_18000C13F
0x18000c139  xor     eax, eax
0x18000c13b  mov     [rsp+328h+var_2D8], eax
0x18000c13f  test    eax, eax
0x18000c141  jle     loc_18000C212
0x18000c147  movzx   edi, ax
0x18000c14a  or      edi, 80070000h
0x18000c150  mov     [rsp+328h+var_2E8], edi
0x18000c154  jmp     loc_18000C2B4
0x18000c159  lea     ecx, [rbx+rbx]
0x18000c15c  cmp     ecx, ebx
0x18000c15e  jbe     short loc_18000C13F
0x18000c160  mov     ebx, ecx
0x18000c162  mov     [rsp+328h+var_2D8], 0
0x18000c16a  jmp     loc_18000C1F7
0x18000c16f  mov     [rsp+328h+var_250], r10d
0x18000c177  mov     [rsp+328h+var_24C], r10w
0x18000c180  mov     [rsp+328h+var_248], 18h
0x18000c18b  mov     r13, [rsp+328h+var_2C0]
0x18000c190  mov     [rsp+328h+var_244], r13w
0x18000c199  movzx   r8d, r13w; Size
0x18000c19d  mov     rdx, [rsp+328h+Src]; Src
0x18000c1a5  lea     rcx, [rsp+328h+var_240]; void *
0x18000c1ad  call    memcpy_0
0x18000c1b2  mov     [rsp+328h+lpBytesReturned], 0; hTemplateFile
0x18000c1bb  mov     [rsp+328h+nOutBufferSize], 0; dwFlagsAndAttributes
0x18000c1c3  mov     dword ptr [rsp+328h+lpOutBuffer], 3; dwCreationDisposition
0x18000c1cb  xor     r9d, r9d; lpSecurityAttributes
0x18000c1ce  xor     edx, edx; dwDesiredAccess
0x18000c1d0  mov     r8d, 3; dwShareMode
0x18000c1d6  lea     rcx, aMountpointmana; "\\\\.\\MountPointManager"
0x18000c1dd  call    cs:__imp_CreateFileW
0x18000c1e4  nop     dword ptr [rax+rax+00h]
0x18000c1e9  mov     rsi, rax
0x18000c1ec  mov     [rsp+328h+var_2E0], rax
0x18000c1f1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c1f5  jz      short loc_18000C21D
0x18000c1f7  test    r15, r15
0x18000c1fa  jnz     short loc_18000C27B
0x18000c1fc  test    ebx, ebx
0x18000c1fe  mov     r8d, 1; dwBytes
0x18000c204  jz      loc_18000BF3B
0x18000c20a  mov     r8d, ebx
0x18000c20d  jmp     loc_18000BF3B
0x18000c212  mov     edi, eax
0x18000c214  mov     [rsp+328h+var_2E8], eax
0x18000c218  jmp     loc_18000C2B4
0x18000c21d  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18000c222  mov     edi, eax
0x18000c224  mov     [rsp+328h+var_2E8], eax
0x18000c228  jmp     loc_18000C2B4
0x18000c22d  mov     r12d, 80070057h
0x18000c233  test    rax, rax
0x18000c236  cmovz   edi, r12d
0x18000c23a  test    edi, edi
0x18000c23c  js      short loc_18000C266
0x18000c23e  sub     rdx, rax
0x18000c241  mov     [r8], rdx
0x18000c244  mov     rax, [rsp+328h+var_2B8]
0x18000c249  test    edi, edi
0x18000c24b  js      short loc_18000C276
0x18000c24d  add     rax, rax
0x18000c250  mov     [r9], rax
0x18000c253  mov     [rsp+328h+var_2E8], edi
0x18000c257  test    edi, edi
0x18000c259  jns     loc_18000C16F
0x18000c25f  mov     r13, [rsp+328h+var_2C0]
0x18000c264  jmp     short loc_18000C2B4
0x18000c266  mov     [r8], r10
0x18000c269  jmp     short loc_18000C244
0x18000c26b  mov     r12d, 80070057h
0x18000c271  mov     edi, r12d
0x18000c274  jmp     short loc_18000C249
0x18000c276  mov     [r9], r10
0x18000c279  jmp     short loc_18000C253
0x18000c27b  mov     rcx, r15; lpMem
0x18000c27e  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18000c283  mov     [rsp+328h+var_2D0], 0
0x18000c28c  jmp     loc_18000C1FC
0x18000c291  mov     edi, 8007000Eh
0x18000c296  mov     [rsp+328h+var_2E8], edi
0x18000c29a  jmp     short loc_18000C2B4
0x18000c29c  mov     edi, 8007000Eh
0x18000c2a1  mov     [rsp+328h+var_2E8], edi
0x18000c2a5  mov     rsi, [rsp+328h+var_2E0]
0x18000c2aa  jmp     short loc_18000C2B4
0x18000c2ac  mov     edi, r12d
0x18000c2af  jmp     loc_18000C0D0
0x18000c2b4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000c2b8  jz      short loc_18000C2C9
0x18000c2ba  mov     rcx, rsi; hObject
0x18000c2bd  call    cs:__imp_CloseHandle
0x18000c2c4  nop     dword ptr [rax+rax+00h]
0x18000c2c9  test    r15, r15
0x18000c2cc  jz      short loc_18000C2EE
0x18000c2ce  mov     r8, r15; lpMem
0x18000c2d1  xor     edx, edx; dwFlags
0x18000c2d3  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x18000c2da  call    cs:__imp_HeapFree
0x18000c2e1  nop     dword ptr [rax+rax+00h]
0x18000c2e6  test    eax, eax
0x18000c2e8  jz      loc_18000C37A
0x18000c2ee  test    edi, edi
0x18000c2f0  js      short loc_18000C36B
0x18000c2f2  test    r14, r14
0x18000c2f5  jz      short loc_18000C336
0x18000c2f7  test    edi, edi
0x18000c2f9  js      short loc_18000C36B
0x18000c2fb  mov     rax, [rsp+328h+var_270]
0x18000c303  mov     [rax], r14
0x18000c306  mov     eax, edi
0x18000c308  mov     rcx, [rsp+328h+var_38]
0x18000c310  xor     rcx, rsp; StackCookie
0x18000c313  call    __security_check_cookie
0x18000c318  lea     r11, [rsp+328h+var_28]
0x18000c320  mov     rbx, [r11+40h]
0x18000c324  mov     rsi, [r11+48h]
0x18000c328  mov     rsp, r11
0x18000c32b  pop     r15
0x18000c32d  pop     r14
0x18000c32f  pop     r13
0x18000c331  pop     r12
0x18000c333  pop     rdi
0x18000c334  retn
0x18000c336  lea     rcx, [r13+1Eh]; unsigned __int64
0x18000c33a  call    ?FastAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::FastAlloc(unsigned __int64)
0x18000c33f  mov     r14, rax
0x18000c342  test    rax, rax
0x18000c345  jz      short loc_18000C366
0x18000c347  mov     r9, [rsp+328h+Src]
0x18000c34f  lea     r8, aGlobalrootS_0; "\\\\?\\GlobalRoot%s"
0x18000c356  lea     rdx, [r13+1Eh]; unsigned __int64
0x18000c35a  mov     rcx, rax; unsigned __int16 *
  ... truncated ...
```
