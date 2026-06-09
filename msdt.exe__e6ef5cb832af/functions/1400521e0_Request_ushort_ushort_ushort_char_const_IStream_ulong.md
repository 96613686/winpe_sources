# Request(ushort *,ushort *,ushort *,char const *,IStream *,ulong *)

- ea: `0x1400521e0`
- end: `0x140052452`
- name: `?Request@@YAJPEAG00PEBDPEAUIStream@@PEAK@Z`
- size: `626`
- prototype: `__int64 __fastcall(LPCWSTR lpcwszUrl, LPCWSTR pwszVerb, unsigned __int16 *, const char *, struct IStream *, unsigned int *lpBuffer)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140050dd8`
- `0x140051164`

## callees

- `0x140010eb4`
- `0x1400506ac`
- `0x1400521e0`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140052296`
- `KERNEL32!GetLastError` at `0x1400522ec`
- `KERNEL32!GetLastError` at `0x140052368`
- `KERNEL32!GetLastError` at `0x140052296`
- `KERNEL32!GetLastError` at `0x1400522ec`
- `KERNEL32!GetLastError` at `0x140052368`
- `KERNEL32!HeapAlloc` at `0x140052326`
- `KERNEL32!HeapAlloc` at `0x140052326`
- `KERNEL32!HeapFree` at `0x140052424`
- `KERNEL32!HeapFree` at `0x140052424`
- `KERNEL32!GetProcessHeap` at `0x14005230f`
- `KERNEL32!GetProcessHeap` at `0x140052410`
- `KERNEL32!GetProcessHeap` at `0x14005230f`
- `KERNEL32!GetProcessHeap` at `0x140052410`
- `WINHTTP!WinHttpReceiveResponse` at `0x140052286`
- `WINHTTP!WinHttpReceiveResponse` at `0x140052286`
- `WINHTTP!WinHttpQueryHeaders` at `0x1400522dc`
- `WINHTTP!WinHttpQueryHeaders` at `0x1400522dc`
- `WINHTTP!WinHttpReadData` at `0x140052358`
- `WINHTTP!WinHttpReadData` at `0x140052358`
- `WINHTTP!WinHttpCloseHandle` at `0x1400523d6`
- `WINHTTP!WinHttpCloseHandle` at `0x1400523eb`
- `WINHTTP!WinHttpCloseHandle` at `0x1400523ff`
- `WINHTTP!WinHttpCloseHandle` at `0x1400523d6`
- `WINHTTP!WinHttpCloseHandle` at `0x1400523eb`
- `WINHTTP!WinHttpCloseHandle` at `0x1400523ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Request(
        LPCWSTR lpcwszUrl,
        LPCWSTR pwszVerb,
        unsigned __int16 *a3,
        const char *a4,
        struct IStream *a5,
        unsigned int *lpBuffer)
{
  DWORD v6; // eax
  const unsigned __int16 *v7; // r10
  const WCHAR *v8; // r11
  unsigned __int64 v10; // rcx
  signed int v11; // ebx
  void *v12; // rdi
  int v13; // eax
  unsigned int *v14; // r15
  void *v15; // rsi
  signed int LastError; // eax
  signed int v17; // eax
  HANDLE ProcessHeap; // rax
  struct IStream *v19; // r14
  signed int v20; // eax
  HANDLE v21; // rax
  unsigned int v23; // [rsp+40h] [rbp-38h] BYREF
  int v24; // [rsp+44h] [rbp-34h] BYREF
  HINTERNET hRequest; // [rsp+48h] [rbp-30h] BYREF
  __int64 v26; // [rsp+50h] [rbp-28h]
  HINTERNET hInternet; // [rsp+58h] [rbp-20h] BYREF
  HINTERNET v28; // [rsp+60h] [rbp-18h] BYREF
  DWORD dwBufferLength; // [rsp+C8h] [rbp+50h] BYREF

  v6 = 0;
  v28 = 0;
  v23 = 0;
  v7 = a3;
  dwBufferLength = 0;
  v8 = pwszVerb;
  hRequest = 0;
  v26 = 0;
  hInternet = 0;
  v24 = 0;
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    v11 = ULongLongToULong(v10, &v23);
    if ( v11 < 0 )
      return (unsigned int)v11;
    v6 = v23;
  }
  v12 = 0;
  v13 = Connect(lpcwszUrl, v8, v7, a4, v6, &hInternet, &v28, &hRequest);
  v14 = lpBuffer;
  v11 = v13;
  v15 = hRequest;
  if ( v13 >= 0 )
  {
    if ( WinHttpReceiveResponse(hRequest, 0) )
      goto LABEL_11;
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 >= 0 )
    {
LABEL_11:
      dwBufferLength = 4;
      if ( WinHttpQueryHeaders(v15, 0x20000013u, 0, v14, &dwBufferLength, 0) )
        goto LABEL_15;
      v17 = GetLastError();
      v11 = v17;
      if ( v17 > 0 )
        v11 = (unsigned __int16)v17 | 0x80070000;
      if ( v11 >= 0 )
      {
LABEL_15:
        ProcessHeap = GetProcessHeap();
        v12 = HeapAlloc(ProcessHeap, 0, 0x1000u);
        if ( v12 )
        {
          v19 = a5;
          while ( 1 )
          {
            if ( !WinHttpReadData(v15, v12, 0x1000u, &dwBufferLength) )
            {
              v20 = GetLastError();
              v11 = v20;
              if ( v20 > 0 )
                v11 = (unsigned __int16)v20 | 0x80070000;
              if ( v11 < 0 )
                break;
            }
            if ( dwBufferLength )
            {
              v11 = (*(__int64 (__fastcall **)(struct IStream *, void *, _QWORD, int *))(*(_QWORD *)v19 + 32LL))(
                      v19,
                      v12,
                      dwBufferLength,
                      &v24);
              if ( v11 < 0 )
                break;
              if ( dwBufferLength )
                continue;
            }
            v11 = (*(__int64 (__fastcall **)(struct IStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)v19 + 40LL))(
                    v19,
                    v26,
                    0,
                    0);
            break;
          }
        }
        else
        {
          v11 = -2147024882;
        }
      }
    }
  }
  if ( hInternet )
    WinHttpCloseHandle(hInternet);
  if ( v28 )
    WinHttpCloseHandle(v28);
  if ( v15 )
    WinHttpCloseHandle(v15);
  if ( v12 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v12);
  }
  if ( v11 >= 0 && *v14 != 200 )
    return 1;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400521e0  push    rbp
0x1400521e2  push    rbx
0x1400521e3  push    rsi
0x1400521e4  push    rdi
0x1400521e5  push    r14
0x1400521e7  push    r15
0x1400521e9  mov     rbp, rsp
0x1400521ec  sub     rsp, 78h
0x1400521f0  xor     eax, eax
0x1400521f2  mov     [rbp+var_18], 0
0x1400521fa  mov     [rbp+var_38], eax
0x1400521fd  mov     r10, r8
0x140052200  mov     [rbp+dwBufferLength], eax
0x140052203  mov     r11, rdx
0x140052206  mov     [rbp+hRequest], rax
0x14005220a  mov     rsi, rcx
0x14005220d  mov     [rbp+var_28], rax
0x140052211  mov     [rbp+hInternet], rax
0x140052215  mov     [rbp+var_34], eax
0x140052218  test    r9, r9
0x14005221b  jz      short loc_140052240
0x14005221d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140052221  inc     rcx; unsigned __int64
0x140052224  cmp     [r9+rcx], al
0x140052228  jnz     short loc_140052221
0x14005222a  lea     rdx, [rbp+var_38]; unsigned int *
0x14005222e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140052233  mov     ebx, eax
0x140052235  test    eax, eax
0x140052237  js      loc_140052442
0x14005223d  mov     eax, [rbp+var_38]
0x140052240  lea     rcx, [rbp+hRequest]
0x140052244  mov     r8, r10; unsigned __int16 *
0x140052247  mov     [rsp+78h+var_40], rcx; void **
0x14005224c  mov     rdx, r11; pwszVerb
0x14005224f  lea     rcx, [rbp+var_18]
0x140052253  xor     edi, edi
0x140052255  mov     [rsp+78h+var_48], rcx; void **
0x14005225a  lea     rcx, [rbp+hInternet]
0x14005225e  mov     [rsp+78h+lpdwIndex], rcx; void **
0x140052263  mov     rcx, rsi; lpcwszUrl
0x140052266  mov     dword ptr [rsp+78h+lpdwBufferLength], eax; dwOptionalLength
0x14005226a  call    ?Connect@@YAJPEBG00PEBDKPEAPEAX22@Z; Connect(ushort const *,ushort const *,ushort const *,char const *,ulong,void * *,void * *,void * *)
0x14005226f  mov     r15, [rbp+lpBuffer]
0x140052273  mov     ebx, eax
0x140052275  mov     rsi, [rbp+hRequest]
0x140052279  test    eax, eax
0x14005227b  js      loc_1400523CD
0x140052281  xor     edx, edx; lpReserved
0x140052283  mov     rcx, rsi; hRequest
0x140052286  call    cs:__imp_WinHttpReceiveResponse
0x14005228d  nop     dword ptr [rax+rax+00h]
0x140052292  test    eax, eax
0x140052294  jnz     short loc_1400522B9
0x140052296  call    cs:__imp_GetLastError
0x14005229d  nop     dword ptr [rax+rax+00h]
0x1400522a2  mov     ebx, eax
0x1400522a4  test    eax, eax
0x1400522a6  jle     short loc_1400522B1
0x1400522a8  movzx   ebx, ax
0x1400522ab  or      ebx, 80070000h
0x1400522b1  test    ebx, ebx
0x1400522b3  js      loc_1400523CD
0x1400522b9  lea     rax, [rbp+dwBufferLength]
0x1400522bd  mov     [rsp+78h+lpdwIndex], rdi; lpdwIndex
0x1400522c2  mov     r9, r15; lpBuffer
0x1400522c5  mov     [rsp+78h+lpdwBufferLength], rax; lpdwBufferLength
0x1400522ca  xor     r8d, r8d; pwszName
0x1400522cd  mov     [rbp+dwBufferLength], 4
0x1400522d4  mov     edx, 20000013h; dwInfoLevel
0x1400522d9  mov     rcx, rsi; hRequest
0x1400522dc  call    cs:__imp_WinHttpQueryHeaders
0x1400522e3  nop     dword ptr [rax+rax+00h]
0x1400522e8  test    eax, eax
0x1400522ea  jnz     short loc_14005230F
0x1400522ec  call    cs:__imp_GetLastError
0x1400522f3  nop     dword ptr [rax+rax+00h]
0x1400522f8  mov     ebx, eax
0x1400522fa  test    eax, eax
0x1400522fc  jle     short loc_140052307
0x1400522fe  movzx   ebx, ax
0x140052301  or      ebx, 80070000h
0x140052307  test    ebx, ebx
0x140052309  js      loc_1400523CD
0x14005230f  call    cs:__imp_GetProcessHeap
0x140052316  nop     dword ptr [rax+rax+00h]
0x14005231b  xor     edx, edx; dwFlags
0x14005231d  mov     r8d, 1000h; dwBytes
0x140052323  mov     rcx, rax; hHeap
0x140052326  call    cs:__imp_HeapAlloc
0x14005232d  nop     dword ptr [rax+rax+00h]
0x140052332  mov     rdi, rax
0x140052335  test    rax, rax
0x140052338  jnz     short loc_140052344
0x14005233a  mov     ebx, 8007000Eh
0x14005233f  jmp     loc_1400523CD
0x140052344  mov     r14, [rbp+arg_20]
0x140052348  lea     r9, [rbp+dwBufferLength]; lpdwNumberOfBytesRead
0x14005234c  mov     r8d, 1000h; dwNumberOfBytesToRead
0x140052352  mov     rdx, rdi; lpBuffer
0x140052355  mov     rcx, rsi; hRequest
0x140052358  call    cs:__imp_WinHttpReadData
0x14005235f  nop     dword ptr [rax+rax+00h]
0x140052364  test    eax, eax
0x140052366  jnz     short loc_140052387
0x140052368  call    cs:__imp_GetLastError
0x14005236f  nop     dword ptr [rax+rax+00h]
0x140052374  mov     ebx, eax
0x140052376  test    eax, eax
0x140052378  jle     short loc_140052383
0x14005237a  movzx   ebx, ax
0x14005237d  or      ebx, 80070000h
0x140052383  test    ebx, ebx
0x140052385  js      short loc_1400523CD
0x140052387  mov     r8d, [rbp+dwBufferLength]
0x14005238b  test    r8d, r8d
0x14005238e  jz      short loc_1400523B2
0x140052390  mov     rax, [r14]
0x140052393  lea     r9, [rbp+var_34]
0x140052397  mov     rdx, rdi
0x14005239a  mov     rcx, r14
0x14005239d  mov     rax, [rax+20h]
0x1400523a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400523a6  mov     ebx, eax
0x1400523a8  test    eax, eax
0x1400523aa  js      short loc_1400523CD
0x1400523ac  cmp     [rbp+dwBufferLength], 0
0x1400523b0  ja      short loc_140052348
0x1400523b2  mov     rax, [r14]
0x1400523b5  xor     r9d, r9d
0x1400523b8  mov     rdx, [rbp+var_28]
0x1400523bc  xor     r8d, r8d
0x1400523bf  mov     rcx, r14
0x1400523c2  mov     rax, [rax+28h]
0x1400523c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400523cb  mov     ebx, eax
0x1400523cd  mov     rcx, [rbp+hInternet]; hInternet
0x1400523d1  test    rcx, rcx
0x1400523d4  jz      short loc_1400523E2
0x1400523d6  call    cs:__imp_WinHttpCloseHandle
0x1400523dd  nop     dword ptr [rax+rax+00h]
0x1400523e2  mov     rcx, [rbp+var_18]; hInternet
0x1400523e6  test    rcx, rcx
0x1400523e9  jz      short loc_1400523F7
0x1400523eb  call    cs:__imp_WinHttpCloseHandle
0x1400523f2  nop     dword ptr [rax+rax+00h]
0x1400523f7  test    rsi, rsi
0x1400523fa  jz      short loc_14005240B
0x1400523fc  mov     rcx, rsi; hInternet
0x1400523ff  call    cs:__imp_WinHttpCloseHandle
0x140052406  nop     dword ptr [rax+rax+00h]
0x14005240b  test    rdi, rdi
0x14005240e  jz      short loc_140052430
0x140052410  call    cs:__imp_GetProcessHeap
0x140052417  nop     dword ptr [rax+rax+00h]
0x14005241c  mov     r8, rdi; lpMem
0x14005241f  xor     edx, edx; dwFlags
0x140052421  mov     rcx, rax; hHeap
0x140052424  call    cs:__imp_HeapFree
0x14005242b  nop     dword ptr [rax+rax+00h]
0x140052430  test    ebx, ebx
0x140052432  js      short loc_140052442
0x140052434  cmp     dword ptr [r15], 0C8h
0x14005243b  jz      short loc_140052442
0x14005243d  mov     ebx, 1
0x140052442  mov     eax, ebx
0x140052444  add     rsp, 78h
0x140052448  pop     r15
0x14005244a  pop     r14
0x14005244c  pop     rdi
0x14005244d  pop     rsi
0x14005244e  pop     rbx
0x14005244f  pop     rbp
0x140052450  retn
```
