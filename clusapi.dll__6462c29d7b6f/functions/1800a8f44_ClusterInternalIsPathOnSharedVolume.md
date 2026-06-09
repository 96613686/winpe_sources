# ClusterInternalIsPathOnSharedVolume

- ea: `0x1800a8f44`
- end: `0x1800a9160`
- name: `ClusterInternalIsPathOnSharedVolume`
- size: `540`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18002cca0`
- `0x18002cce0`

## callees

- `0x180002f50`
- `0x180003c14`
- `0x18001236c`
- `0x1800a8f44`
- `0x1800a9168`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a90a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a90e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a90a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a90e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9118`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a9127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a9127`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a9094`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a9094`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a90d6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a910e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a90d6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a910e`

## pseudocode

```c
__int64 __fastcall ClusterInternalIsPathOnSharedVolume(wchar_t *a1)
{
  __int64 v2; // rax
  __int16 v3; // ax
  HANDLE FileW; // rdi
  DWORD LastError; // ebx
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-98h] BYREF
  wchar_t v8[56]; // [rsp+50h] [rbp-88h] BYREF

  BytesReturned[0] = 0;
  if ( a1 && *a1 )
  {
    v2 = -1;
    do
      ++v2;
    while ( a1[v2] );
    v3 = 2 * v2;
    if ( (v3 == 96 || v3 == 98 && a1[48] == 92)
      && *a1 == 92
      && (a1[1] == 63 || a1[1] == 92)
      && a1[2] == 63
      && a1[3] == 92
      && a1[4] == 86
      && a1[5] == 111
      && a1[6] == 108
      && a1[7] == 117
      && a1[8] == 109
      && a1[9] == 101
      && a1[10] == 123
      && a1[19] == 45
      && a1[24] == 45
      && a1[29] == 45
      && a1[34] == 45
      && a1[47] == 125 )
    {
      memset_0(v8, 0, 0x64u);
      StringCchCopyW(v8, 0x32u, a1);
      v8[48] = 0;
      return ClusterInternalIsVolumeCsv(v8);
    }
    FileW = CreateFileW(a1, 0x100000u, 3u, 0, 3u, 0x2000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      if ( DeviceIoControl(FileW, 0x90248u, 0, 0, 0, 0, BytesReturned, 0) )
      {
        LastError = 0;
      }
      else
      {
        GetLastError();
        LastError = 0;
        if ( !DeviceIoControl(FileW, 0x9025Cu, 0, 0, 0, 0, BytesReturned, 0) )
          LastError = GetLastError();
      }
      CloseHandle(FileW);
    }
  }
  else
  {
    LastError = 87;
  }
  return LastError == 0;
}

```

## disassembly

```asm
0x1800a8f44  mov     [rsp+arg_8], rbx
0x1800a8f49  mov     [rsp+arg_10], rsi
0x1800a8f4e  push    rdi
0x1800a8f4f  sub     rsp, 0D0h
0x1800a8f56  mov     rax, cs:__security_cookie
0x1800a8f5d  xor     rax, rsp
0x1800a8f60  mov     [rsp+0D8h+var_18], rax
0x1800a8f68  xor     esi, esi
0x1800a8f6a  mov     rbx, rcx
0x1800a8f6d  mov     [rsp+0D8h+BytesReturned], esi
0x1800a8f71  test    rcx, rcx
0x1800a8f74  jz      loc_1800A912F
0x1800a8f7a  cmp     [rcx], si
0x1800a8f7d  jz      loc_1800A912F
0x1800a8f83  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a8f87  inc     rax
0x1800a8f8a  cmp     [rcx+rax*2], si
0x1800a8f8e  jnz     short loc_1800A8F87
0x1800a8f90  add     ax, ax
0x1800a8f93  mov     cx, 5Ch ; '\'
0x1800a8f97  cmp     ax, 60h ; '`'
0x1800a8f9b  jz      short loc_1800A8FB1
0x1800a8f9d  cmp     ax, 62h ; 'b'
0x1800a8fa1  jnz     loc_1800A9071
0x1800a8fa7  cmp     [rbx+60h], cx
0x1800a8fab  jnz     loc_1800A9071
0x1800a8fb1  cmp     [rbx], cx
0x1800a8fb4  jnz     loc_1800A9071
0x1800a8fba  cmp     word ptr [rbx+2], 3Fh ; '?'
0x1800a8fbf  jz      short loc_1800A8FCB
0x1800a8fc1  cmp     [rbx+2], cx
0x1800a8fc5  jnz     loc_1800A9071
0x1800a8fcb  cmp     word ptr [rbx+4], 3Fh ; '?'
0x1800a8fd0  jnz     loc_1800A9071
0x1800a8fd6  cmp     [rbx+6], cx
0x1800a8fda  jnz     loc_1800A9071
0x1800a8fe0  cmp     word ptr [rbx+8], 56h ; 'V'
0x1800a8fe5  jnz     loc_1800A9071
0x1800a8feb  cmp     word ptr [rbx+0Ah], 6Fh ; 'o'
0x1800a8ff0  jnz     short loc_1800A9071
0x1800a8ff2  cmp     word ptr [rbx+0Ch], 6Ch ; 'l'
0x1800a8ff7  jnz     short loc_1800A9071
0x1800a8ff9  cmp     word ptr [rbx+0Eh], 75h ; 'u'
0x1800a8ffe  jnz     short loc_1800A9071
0x1800a9000  cmp     word ptr [rbx+10h], 6Dh ; 'm'
0x1800a9005  jnz     short loc_1800A9071
0x1800a9007  cmp     word ptr [rbx+12h], 65h ; 'e'
0x1800a900c  jnz     short loc_1800A9071
0x1800a900e  cmp     word ptr [rbx+14h], 7Bh ; '{'
0x1800a9013  jnz     short loc_1800A9071
0x1800a9015  mov     ax, 2Dh ; '-'
0x1800a9019  cmp     [rbx+26h], ax
0x1800a901d  jnz     short loc_1800A9071
0x1800a901f  cmp     [rbx+30h], ax
0x1800a9023  jnz     short loc_1800A9071
0x1800a9025  cmp     [rbx+3Ah], ax
0x1800a9029  jnz     short loc_1800A9071
0x1800a902b  cmp     [rbx+44h], ax
0x1800a902f  jnz     short loc_1800A9071
0x1800a9031  cmp     word ptr [rbx+5Eh], 7Dh ; '}'
0x1800a9036  jnz     short loc_1800A9071
0x1800a9038  xor     edx, edx; Val
0x1800a903a  lea     rcx, [rsp+0D8h+var_88]; void *
0x1800a903f  lea     r8d, [rdx+64h]; Size
0x1800a9043  call    memset_0
0x1800a9048  mov     r8, rbx; wchar_t *
0x1800a904b  lea     rcx, [rsp+0D8h+var_88]; wchar_t *
0x1800a9050  mov     edx, 32h ; '2'; unsigned __int64
0x1800a9055  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a905a  lea     rcx, [rsp+0D8h+var_88]
0x1800a905f  mov     [rsp+0D8h+var_28], si
0x1800a9067  call    ClusterInternalIsVolumeCsv
0x1800a906c  jmp     loc_1800A913B
0x1800a9071  mov     [rsp+0D8h+hTemplateFile], rsi; hTemplateFile
0x1800a9076  mov     r8d, 3; dwShareMode
0x1800a907c  mov     [rsp+0D8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800a9084  xor     r9d, r9d; lpSecurityAttributes
0x1800a9087  mov     edx, 100000h; dwDesiredAccess
0x1800a908c  mov     [rsp+0D8h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800a9091  mov     rcx, rbx; lpFileName
0x1800a9094  call    cs:__imp_CreateFileW
0x1800a909a  mov     rdi, rax
0x1800a909d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a90a1  jnz     short loc_1800A90B0
0x1800a90a3  call    cs:__imp_GetLastError
0x1800a90a9  mov     ebx, eax
0x1800a90ab  jmp     loc_1800A9134
0x1800a90b0  mov     [rsp+0D8h+lpOverlapped], rsi; lpOverlapped
0x1800a90b5  lea     rax, [rsp+0D8h+BytesReturned]
0x1800a90ba  mov     [rsp+0D8h+hTemplateFile], rax; lpBytesReturned
0x1800a90bf  xor     r9d, r9d; nInBufferSize
0x1800a90c2  mov     [rsp+0D8h+dwFlagsAndAttributes], esi; nOutBufferSize
0x1800a90c6  xor     r8d, r8d; lpInBuffer
0x1800a90c9  mov     edx, 90248h; dwIoControlCode
0x1800a90ce  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rsi; lpOutBuffer
0x1800a90d3  mov     rcx, rdi; hDevice
0x1800a90d6  call    cs:__imp_DeviceIoControl
0x1800a90dc  test    eax, eax
0x1800a90de  jnz     short loc_1800A9122
0x1800a90e0  call    cs:__imp_GetLastError
0x1800a90e6  mov     [rsp+0D8h+lpOverlapped], rsi; lpOverlapped
0x1800a90eb  lea     rax, [rsp+0D8h+BytesReturned]
0x1800a90f0  mov     [rsp+0D8h+hTemplateFile], rax; lpBytesReturned
0x1800a90f5  xor     r9d, r9d; nInBufferSize
0x1800a90f8  mov     [rsp+0D8h+dwFlagsAndAttributes], esi; nOutBufferSize
0x1800a90fc  xor     r8d, r8d; lpInBuffer
0x1800a90ff  mov     edx, 9025Ch; dwIoControlCode
0x1800a9104  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rsi; lpOutBuffer
0x1800a9109  mov     rcx, rdi; hDevice
0x1800a910c  mov     ebx, esi
0x1800a910e  call    cs:__imp_DeviceIoControl
0x1800a9114  test    eax, eax
0x1800a9116  jnz     short loc_1800A9124
0x1800a9118  call    cs:__imp_GetLastError
0x1800a911e  mov     ebx, eax
0x1800a9120  jmp     short loc_1800A9124
0x1800a9122  mov     ebx, esi
0x1800a9124  mov     rcx, rdi; hObject
0x1800a9127  call    cs:__imp_CloseHandle
0x1800a912d  jmp     short loc_1800A9134
0x1800a912f  mov     ebx, 57h ; 'W'
0x1800a9134  test    ebx, ebx
0x1800a9136  mov     eax, esi
0x1800a9138  setz    al
0x1800a913b  mov     rcx, [rsp+0D8h+var_18]
0x1800a9143  xor     rcx, rsp; StackCookie
0x1800a9146  call    __security_check_cookie
0x1800a914b  lea     r11, [rsp+0D8h+var_8]
0x1800a9153  mov     rbx, [r11+18h]
0x1800a9157  mov     rsi, [r11+20h]
0x1800a915b  mov     rsp, r11
0x1800a915e  pop     rdi
0x1800a915f  retn
```
