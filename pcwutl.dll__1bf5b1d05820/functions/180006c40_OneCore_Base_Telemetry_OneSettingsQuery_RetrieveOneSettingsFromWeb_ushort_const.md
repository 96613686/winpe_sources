# OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(ushort const *)

- ea: `0x180006c40`
- end: `0x180006eaa`
- name: `?RetrieveOneSettingsFromWeb@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG@Z`
- size: `618`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003388`

## callees

- `0x18000312c`
- `0x180004ef4`
- `0x180006c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006cab`
- `KERNEL32!GetLastError` at `0x180006d42`
- `KERNEL32!GetLastError` at `0x180006df9`
- `KERNEL32!GetLastError` at `0x180006cab`
- `KERNEL32!GetLastError` at `0x180006d42`
- `KERNEL32!GetLastError` at `0x180006df9`
- `KERNEL32!HeapAlloc` at `0x180006d65`
- `KERNEL32!HeapAlloc` at `0x180006dd2`
- `KERNEL32!HeapAlloc` at `0x180006d65`
- `KERNEL32!HeapAlloc` at `0x180006dd2`
- `KERNEL32!GetProcessHeap` at `0x180006d54`
- `KERNEL32!GetProcessHeap` at `0x180006dc1`
- `KERNEL32!GetProcessHeap` at `0x180006e24`
- `KERNEL32!GetProcessHeap` at `0x180006e88`
- `KERNEL32!GetProcessHeap` at `0x180006d54`
- `KERNEL32!GetProcessHeap` at `0x180006dc1`
- `KERNEL32!GetProcessHeap` at `0x180006e24`
- `KERNEL32!GetProcessHeap` at `0x180006e88`
- `KERNEL32!HeapFree` at `0x180006e32`
- `KERNEL32!HeapFree` at `0x180006e97`
- `KERNEL32!HeapFree` at `0x180006e32`
- `KERNEL32!HeapFree` at `0x180006e97`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180006e5f`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180006e5f`
- `WINHTTP!WinHttpReadData` at `0x180006def`
- `WINHTTP!WinHttpReadData` at `0x180006def`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180006dae`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180006dae`
- `WINHTTP!WinHttpQueryHeaders` at `0x180006cfe`
- `WINHTTP!WinHttpQueryHeaders` at `0x180006d38`
- `WINHTTP!WinHttpQueryHeaders` at `0x180006d98`
- `WINHTTP!WinHttpQueryHeaders` at `0x180006cfe`
- `WINHTTP!WinHttpQueryHeaders` at `0x180006d38`
- `WINHTTP!WinHttpQueryHeaders` at `0x180006d98`
- `WINHTTP!WinHttpReceiveResponse` at `0x180006ccf`
- `WINHTTP!WinHttpReceiveResponse` at `0x180006ccf`
- `WINHTTP!WinHttpSendRequest` at `0x180006ca1`
- `WINHTTP!WinHttpSendRequest` at `0x180006ca1`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(
        HINTERNET *this,
        const unsigned __int16 *a2)
{
  signed int Headers; // ebx
  signed int LastError; // eax
  void *v5; // rcx
  void *v6; // rcx
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  DWORD v10; // ebx
  HANDLE v11; // rax
  char *v12; // rax
  char *v13; // rsi
  signed int v14; // eax
  HANDLE v15; // rax
  HANDLE v16; // rax
  DWORD pdwAuthTarget; // [rsp+40h] [rbp-10h] BYREF
  DWORD dwFirstScheme; // [rsp+44h] [rbp-Ch] BYREF
  LPCWSTR lpszHeaders; // [rsp+48h] [rbp-8h] BYREF
  DWORD dwBufferLength; // [rsp+88h] [rbp+38h] BYREF
  int v22; // [rsp+8Ch] [rbp+3Ch]
  int Buffer; // [rsp+90h] [rbp+40h] BYREF
  DWORD dwSupportedSchemes; // [rsp+98h] [rbp+48h] BYREF

  v22 = HIDWORD(a2);
  lpszHeaders = 0;
  Buffer = 0;
  dwBufferLength = 0;
  dwSupportedSchemes = 0;
  dwFirstScheme = 0;
  pdwAuthTarget = 0;
  Headers = OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(
              (OneCore::Base::Telemetry::OneSettingsQuery *)this,
              a2,
              (unsigned __int16 **)&lpszHeaders);
  if ( Headers < 0 )
    goto LABEL_26;
  if ( !WinHttpSendRequest(this[2], lpszHeaders, 0xFFFFFFFF, 0, 0, 0, 0) )
    goto LABEL_3;
  if ( !WinHttpReceiveResponse(this[2], 0) )
    goto LABEL_3;
  v5 = this[2];
  dwBufferLength = 4;
  if ( !WinHttpQueryHeaders(v5, 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
    goto LABEL_3;
  if ( Buffer != 200 )
  {
    if ( Buffer == 304 )
    {
      Headers = 1;
    }
    else if ( Buffer != 407
           || (WinHttpQueryAuthSchemes(this[2], &dwSupportedSchemes, &dwFirstScheme, &pdwAuthTarget),
               (dwSupportedSchemes & 1) == 0)
           || (Headers = -2147024891, pdwAuthTarget != 1) )
    {
      Headers = -2147467259;
    }
    goto LABEL_26;
  }
  v6 = this[2];
  dwBufferLength = 0;
  if ( !WinHttpQueryHeaders(v6, 0x36u, 0, 0, &dwBufferLength, 0) && GetLastError() != 122 )
    goto LABEL_3;
  v7 = dwBufferLength;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, v7);
  this[4] = v9;
  if ( !v9 )
  {
LABEL_11:
    Headers = -2147024882;
    goto LABEL_26;
  }
  if ( !WinHttpQueryHeaders(this[2], 0x36u, 0, v9, &dwBufferLength, 0)
    || !WinHttpQueryDataAvailable(this[2], &dwBufferLength) )
  {
LABEL_3:
    LastError = GetLastError();
    Headers = LastError;
    if ( LastError > 0 )
      Headers = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_26;
  }
  v10 = dwBufferLength + 1;
  v11 = GetProcessHeap();
  v12 = (char *)HeapAlloc(v11, 8u, v10);
  v13 = v12;
  if ( !v12 )
    goto LABEL_11;
  if ( WinHttpReadData(this[2], v12, dwBufferLength, &dwBufferLength) )
  {
    v13[dwBufferLength] = 0;
    Headers = OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(
                (OneCore::Base::Telemetry::OneSettingsQuery *)this,
                v13);
  }
  else
  {
    v14 = GetLastError();
    Headers = v14;
    if ( v14 > 0 )
      Headers = (unsigned __int16)v14 | 0x80070000;
  }
  v15 = GetProcessHeap();
  HeapFree(v15, 0, v13);
LABEL_26:
  if ( lpszHeaders )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, (LPVOID)lpszHeaders);
  }
  return (unsigned int)Headers;
}

```

## disassembly

```asm
0x180006c40  mov     qword ptr [rsp-28h+dwBufferLength], rdx
0x180006c45  push    rbp
0x180006c46  push    rbx
0x180006c47  push    rsi
0x180006c48  push    rdi
0x180006c49  push    r15
0x180006c4b  mov     rbp, rsp
0x180006c4e  sub     rsp, 50h
0x180006c52  xor     r15d, r15d
0x180006c55  lea     r8, [rbp+lpszHeaders]; unsigned __int16 **
0x180006c59  mov     [rbp+lpszHeaders], r15
0x180006c5d  mov     rdi, rcx
0x180006c60  mov     [rbp+Buffer], r15d
0x180006c64  mov     [rbp+dwBufferLength], r15d
0x180006c68  mov     [rbp+dwSupportedSchemes], r15d
0x180006c6c  mov     [rbp+dwFirstScheme], r15d
0x180006c70  mov     [rbp+pdwAuthTarget], r15d
0x180006c74  call    ?CreateHeaders@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAPEAG@Z; OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(ushort const *,ushort * *)
0x180006c79  mov     ebx, eax
0x180006c7b  test    eax, eax
0x180006c7d  js      loc_180006E82
0x180006c83  mov     rdx, [rbp+lpszHeaders]; lpszHeaders
0x180006c87  xor     r9d, r9d; lpOptional
0x180006c8a  mov     rcx, [rdi+10h]; hRequest
0x180006c8e  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180006c92  mov     [rsp+50h+dwContext], r15; dwContext
0x180006c97  mov     [rsp+50h+dwTotalLength], r15d; dwTotalLength
0x180006c9c  mov     [rsp+50h+dwOptionalLength], r15d; dwOptionalLength
0x180006ca1  call    cs:__imp_WinHttpSendRequest
0x180006ca7  test    eax, eax
0x180006ca9  jnz     short loc_180006CC9
0x180006cab  call    cs:__imp_GetLastError
0x180006cb1  mov     ebx, eax
0x180006cb3  test    eax, eax
0x180006cb5  jle     loc_180006E82
0x180006cbb  movzx   ebx, ax
0x180006cbe  or      ebx, 80070000h
0x180006cc4  jmp     loc_180006E82
0x180006cc9  mov     rcx, [rdi+10h]; hRequest
0x180006ccd  xor     edx, edx; lpReserved
0x180006ccf  call    cs:__imp_WinHttpReceiveResponse
0x180006cd5  test    eax, eax
0x180006cd7  jz      short loc_180006CAB
0x180006cd9  mov     rcx, [rdi+10h]; hRequest
0x180006cdd  lea     rax, [rbp+dwBufferLength]
0x180006ce1  mov     qword ptr [rsp+50h+dwTotalLength], r15; lpdwIndex
0x180006ce6  lea     r9, [rbp+Buffer]; lpBuffer
0x180006cea  xor     r8d, r8d; pwszName
0x180006ced  mov     qword ptr [rsp+50h+dwOptionalLength], rax; lpdwBufferLength
0x180006cf2  mov     edx, 20000013h; dwInfoLevel
0x180006cf7  mov     [rbp+dwBufferLength], 4
0x180006cfe  call    cs:__imp_WinHttpQueryHeaders
0x180006d04  test    eax, eax
0x180006d06  jz      short loc_180006CAB
0x180006d08  mov     eax, [rbp+Buffer]
0x180006d0b  cmp     eax, 0C8h
0x180006d10  jnz     loc_180006E3A
0x180006d16  mov     rcx, [rdi+10h]; hRequest
0x180006d1a  lea     rax, [rbp+dwBufferLength]
0x180006d1e  xor     r9d, r9d; lpBuffer
0x180006d21  mov     qword ptr [rsp+50h+dwTotalLength], r15; lpdwIndex
0x180006d26  xor     r8d, r8d; pwszName
0x180006d29  mov     [rbp+dwBufferLength], r15d
0x180006d2d  mov     qword ptr [rsp+50h+dwOptionalLength], rax; lpdwBufferLength
0x180006d32  lea     esi, [r9+36h]
0x180006d36  mov     edx, esi; dwInfoLevel
0x180006d38  call    cs:__imp_WinHttpQueryHeaders
0x180006d3e  test    eax, eax
0x180006d40  jnz     short loc_180006D51
0x180006d42  call    cs:__imp_GetLastError
0x180006d48  cmp     eax, 7Ah ; 'z'
0x180006d4b  jnz     loc_180006CAB
0x180006d51  mov     ebx, [rbp+dwBufferLength]
0x180006d54  call    cs:__imp_GetProcessHeap
0x180006d5a  mov     r8d, ebx; dwBytes
0x180006d5d  mov     edx, 8; dwFlags
0x180006d62  mov     rcx, rax; hHeap
0x180006d65  call    cs:__imp_HeapAlloc
0x180006d6b  mov     [rdi+20h], rax
0x180006d6f  test    rax, rax
0x180006d72  jnz     short loc_180006D7E
0x180006d74  mov     ebx, 8007000Eh
0x180006d79  jmp     loc_180006E82
0x180006d7e  lea     rcx, [rbp+dwBufferLength]
0x180006d82  mov     qword ptr [rsp+50h+dwTotalLength], r15; lpdwIndex
0x180006d87  mov     qword ptr [rsp+50h+dwOptionalLength], rcx; lpdwBufferLength
0x180006d8c  mov     r9, rax; lpBuffer
0x180006d8f  mov     rcx, [rdi+10h]; hRequest
0x180006d93  xor     r8d, r8d; pwszName
0x180006d96  mov     edx, esi; dwInfoLevel
0x180006d98  call    cs:__imp_WinHttpQueryHeaders
0x180006d9e  test    eax, eax
0x180006da0  jz      loc_180006CAB
0x180006da6  mov     rcx, [rdi+10h]; hRequest
0x180006daa  lea     rdx, [rbp+dwBufferLength]; lpdwNumberOfBytesAvailable
0x180006dae  call    cs:__imp_WinHttpQueryDataAvailable
0x180006db4  test    eax, eax
0x180006db6  jz      loc_180006CAB
0x180006dbc  mov     ebx, [rbp+dwBufferLength]
0x180006dbf  inc     ebx
0x180006dc1  call    cs:__imp_GetProcessHeap
0x180006dc7  mov     r8d, ebx; dwBytes
0x180006dca  mov     edx, 8; dwFlags
0x180006dcf  mov     rcx, rax; hHeap
0x180006dd2  call    cs:__imp_HeapAlloc
0x180006dd8  mov     rsi, rax
0x180006ddb  test    rax, rax
0x180006dde  jz      short loc_180006D74
0x180006de0  mov     r8d, [rbp+dwBufferLength]; dwNumberOfBytesToRead
0x180006de4  lea     r9, [rbp+dwBufferLength]; lpdwNumberOfBytesRead
0x180006de8  mov     rcx, [rdi+10h]; hRequest
0x180006dec  mov     rdx, rax; lpBuffer
0x180006def  call    cs:__imp_WinHttpReadData
0x180006df5  test    eax, eax
0x180006df7  jnz     short loc_180006E10
0x180006df9  call    cs:__imp_GetLastError
0x180006dff  mov     ebx, eax
0x180006e01  test    eax, eax
0x180006e03  jle     short loc_180006E24
0x180006e05  movzx   ebx, ax
0x180006e08  or      ebx, 80070000h
0x180006e0e  jmp     short loc_180006E24
0x180006e10  mov     eax, [rbp+dwBufferLength]
0x180006e13  mov     rdx, rsi; char *
0x180006e16  mov     rcx, rdi; this
0x180006e19  mov     [rax+rsi], r15b
0x180006e1d  call    ?ParseJsonResult@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAD@Z; OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(char *)
0x180006e22  mov     ebx, eax
0x180006e24  call    cs:__imp_GetProcessHeap
0x180006e2a  mov     r8, rsi; lpMem
0x180006e2d  xor     edx, edx; dwFlags
0x180006e2f  mov     rcx, rax; hHeap
0x180006e32  call    cs:__imp_HeapFree
0x180006e38  jmp     short loc_180006E82
0x180006e3a  cmp     eax, 130h
0x180006e3f  jnz     short loc_180006E48
0x180006e41  mov     ebx, 1
0x180006e46  jmp     short loc_180006E82
0x180006e48  cmp     eax, 197h
0x180006e4d  jnz     short loc_180006E7D
0x180006e4f  mov     rcx, [rdi+10h]; hRequest
0x180006e53  lea     r9, [rbp+pdwAuthTarget]; pdwAuthTarget
0x180006e57  lea     r8, [rbp+dwFirstScheme]; lpdwFirstScheme
0x180006e5b  lea     rdx, [rbp+dwSupportedSchemes]; lpdwSupportedSchemes
0x180006e5f  call    cs:__imp_WinHttpQueryAuthSchemes
0x180006e65  mov     eax, [rbp+dwSupportedSchemes]
0x180006e68  mov     ebx, 1
0x180006e6d  and     eax, ebx
0x180006e6f  test    al, al
0x180006e71  jz      short loc_180006E7D
0x180006e73  cmp     [rbp+pdwAuthTarget], ebx
0x180006e76  mov     ebx, 80070005h
0x180006e7b  jz      short loc_180006E82
0x180006e7d  mov     ebx, 80004005h
0x180006e82  cmp     [rbp+lpszHeaders], r15
0x180006e86  jz      short loc_180006E9D
0x180006e88  call    cs:__imp_GetProcessHeap
0x180006e8e  mov     r8, [rbp+lpszHeaders]; lpMem
0x180006e92  xor     edx, edx; dwFlags
0x180006e94  mov     rcx, rax; hHeap
0x180006e97  call    cs:__imp_HeapFree
0x180006e9d  mov     eax, ebx
0x180006e9f  add     rsp, 50h
0x180006ea3  pop     r15
0x180006ea5  pop     rdi
0x180006ea6  pop     rsi
0x180006ea7  pop     rbx
0x180006ea8  pop     rbp
0x180006ea9  retn
```
