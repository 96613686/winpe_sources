# CPL::UsePipe(ushort const *,ushort const *)

- ea: `0x140032f04`
- end: `0x14003330b`
- name: `?UsePipe@CPL@@CAJPEBG0@Z`
- size: `1031`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140032b60`

## callees

- `0x14000706c`
- `0x1400070b0`
- `0x140020420`
- `0x140022070`
- `0x140032f04`
- `0x140061c90`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1400331b1`
- `KERNEL32!WaitForSingleObject` at `0x1400331b1`
- `KERNEL32!GetLastError` at `0x1400330ef`
- `KERNEL32!GetLastError` at `0x140033102`
- `KERNEL32!GetLastError` at `0x140033162`
- `KERNEL32!GetLastError` at `0x140033175`
- `KERNEL32!GetLastError` at `0x1400331d5`
- `KERNEL32!GetLastError` at `0x1400331fb`
- `KERNEL32!GetLastError` at `0x140033221`
- `KERNEL32!GetLastError` at `0x1400330ef`
- `KERNEL32!GetLastError` at `0x140033102`
- `KERNEL32!GetLastError` at `0x140033162`
- `KERNEL32!GetLastError` at `0x140033175`
- `KERNEL32!GetLastError` at `0x1400331d5`
- `KERNEL32!GetLastError` at `0x1400331fb`
- `KERNEL32!GetLastError` at `0x140033221`
- `KERNEL32!CloseHandle` at `0x14003326c`
- `KERNEL32!CloseHandle` at `0x14003328f`
- `KERNEL32!CloseHandle` at `0x1400332b1`
- `KERNEL32!CloseHandle` at `0x14003326c`
- `KERNEL32!CloseHandle` at `0x14003328f`
- `KERNEL32!CloseHandle` at `0x1400332b1`
- `KERNEL32!HeapAlloc` at `0x140032f82`
- `KERNEL32!HeapAlloc` at `0x140032f82`
- `KERNEL32!HeapFree` at `0x1400332d6`
- `KERNEL32!HeapFree` at `0x1400332d6`
- `KERNEL32!GetProcessHeap` at `0x140032f6b`
- `KERNEL32!GetProcessHeap` at `0x1400332c2`
- `KERNEL32!GetProcessHeap` at `0x140032f6b`
- `KERNEL32!GetProcessHeap` at `0x1400332c2`
- `KERNEL32!CreateEventW` at `0x140033080`
- `KERNEL32!CreateEventW` at `0x1400330a8`
- `KERNEL32!CreateEventW` at `0x140033080`
- `KERNEL32!CreateEventW` at `0x1400330a8`
- `KERNEL32!CreateFileW` at `0x140033055`
- `KERNEL32!CreateFileW` at `0x140033055`
- `KERNEL32!WriteFile` at `0x1400330df`
- `KERNEL32!WriteFile` at `0x1400330df`
- `KERNEL32!ReadFile` at `0x14003314f`
- `KERNEL32!ReadFile` at `0x14003314f`

## pseudocode

```c
__int64 __fastcall CPL::UsePipe(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  char *FileW; // r15
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rsi
  signed int v7; // ebx
  int v8; // r9d
  int v9; // eax
  int v10; // eax
  unsigned __int64 v11; // r11
  int v12; // eax
  int v13; // ebx
  signed int v14; // eax
  int v15; // r9d
  BOOL v16; // r14d
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  signed int LastError; // eax
  HANDLE v21; // rax
  signed int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Buffer[8]; // [rsp+50h] [rbp-B0h] BYREF
  struct _OVERLAPPED v28; // [rsp+58h] [rbp-A8h] BYREF
  _OVERLAPPED Overlapped; // [rsp+78h] [rbp-88h] BYREF
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF

  v26 = 0;
  NumberOfBytesWritten = 0;
  memset(&v28, 0, sizeof(v28));
  NumberOfBytesRead = 0;
  FileW = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  ProcessHeap = GetProcessHeap();
  v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
  if ( !v6 )
  {
    v7 = -2147024882;
    v8 = 59;
LABEL_39:
    dwCreationDisposition = v7;
    goto LABEL_40;
  }
  v9 = StringCchPrintfW(FileName, 0x104u, L"\\\\.\\pipe\\%s", a1);
  v7 = v9;
  if ( v9 >= 0 )
  {
    v10 = StringCchCopyW(v6, 0x400u, a2);
    v7 = v10;
    if ( v10 < 0 )
    {
      dwCreationDisposition = v10;
      v8 = 65;
      goto LABEL_40;
    }
    v12 = StringCchLengthW(v6, v11, &v26);
    v7 = v12;
    if ( v12 < 0 )
    {
      dwCreationDisposition = v12;
      v8 = 68;
      goto LABEL_40;
    }
    v13 = v26;
    if ( v26 < 2 )
    {
      *(_DWORD *)v6 = 0;
      v13 = 2;
    }
    FileW = (char *)CreateFileW(FileName, 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v8 = 89;
      goto LABEL_39;
    }
    Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
    if ( (unsigned __int64)Overlapped.hEvent - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v19 = GetLastError();
      v7 = v19;
      if ( v19 > 0 )
        v7 = (unsigned __int16)v19 | 0x80070000;
      v15 = 92;
      goto LABEL_20;
    }
    v28.hEvent = CreateEventW(0, 1, 0, 0);
    if ( (unsigned __int64)v28.hEvent - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v18 = GetLastError();
      v7 = v18;
      if ( v18 > 0 )
        v7 = (unsigned __int16)v18 | 0x80070000;
      v15 = 95;
      goto LABEL_20;
    }
    if ( WriteFile(FileW, v6, 2 * v13, &NumberOfBytesWritten, &Overlapped) || GetLastError() == 997 )
      goto LABEL_21;
    v14 = GetLastError();
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    if ( v7 >= 0 )
    {
LABEL_21:
      v16 = ReadFile(FileW, Buffer, 4u, &NumberOfBytesRead, &v28);
      if ( v16 || GetLastError() == 997 )
      {
        v7 = 0;
        if ( v16 )
          goto LABEL_41;
      }
      else
      {
        v17 = GetLastError();
        v7 = v17;
        if ( v17 > 0 )
          v7 = (unsigned __int16)v17 | 0x80070000;
        if ( v7 < 0 )
        {
          v15 = 119;
          goto LABEL_20;
        }
      }
      if ( !WaitForSingleObject(v28.hEvent, 0x1F4u) )
        goto LABEL_41;
      v7 = -2147467259;
      v15 = 128;
    }
    else
    {
      v15 = 107;
    }
LABEL_20:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CPL::UsePipe", v15, v7);
    goto LABEL_41;
  }
  dwCreationDisposition = v9;
  v8 = 62;
LABEL_40:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CPL::UsePipe", v8, dwCreationDisposition);
LABEL_41:
  if ( (unsigned __int64)Overlapped.hEvent - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(Overlapped.hEvent);
    Overlapped.hEvent = 0;
  }
  if ( (unsigned __int64)v28.hEvent - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v28.hEvent);
    v28.hEvent = 0;
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  if ( v6 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v6);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140032f04  mov     [rsp-8+arg_10], rbx
0x140032f09  push    rbp
0x140032f0a  push    rsi
0x140032f0b  push    rdi
0x140032f0c  push    r14
0x140032f0e  push    r15
0x140032f10  lea     rbp, [rsp-1C0h]
0x140032f18  sub     rsp, 2C0h
0x140032f1f  mov     rax, cs:__security_cookie
0x140032f26  xor     rax, rsp
0x140032f29  mov     [rbp+1E0h+var_30], rax
0x140032f30  xorps   xmm0, xmm0
0x140032f33  mov     [rsp+2E0h+var_298], 0
0x140032f3c  xorps   xmm1, xmm1
0x140032f3f  mov     [rsp+2E0h+NumberOfBytesWritten], 0
0x140032f47  movups  xmmword ptr [rsp+2E0h+var_288.Internal], xmm0
0x140032f4c  mov     rdi, rdx
0x140032f4f  mov     rbx, rcx
0x140032f52  movups  xmmword ptr [rsp+2E0h+var_288.10h], xmm0
0x140032f57  mov     [rsp+2E0h+NumberOfBytesRead], 0
0x140032f5f  xor     r15d, r15d
0x140032f62  movups  xmmword ptr [rsp+2E0h+Overlapped.Internal], xmm1
0x140032f67  movups  xmmword ptr [rbp+1E0h+Overlapped.10h], xmm1
0x140032f6b  call    cs:__imp_GetProcessHeap
0x140032f72  nop     dword ptr [rax+rax+00h]
0x140032f77  xor     edx, edx; dwFlags
0x140032f79  mov     r8d, 800h; dwBytes
0x140032f7f  mov     rcx, rax; hHeap
0x140032f82  call    cs:__imp_HeapAlloc
0x140032f89  nop     dword ptr [rax+rax+00h]
0x140032f8e  mov     rsi, rax
0x140032f91  test    rax, rax
0x140032f94  jnz     short loc_140032FA4
0x140032f96  mov     ebx, 8007000Eh
0x140032f9b  lea     r9d, [r15+3Bh]
0x140032f9f  jmp     loc_140033242
0x140032fa4  mov     r9, rbx
0x140032fa7  lea     r8, aPipeS; "\\\\.\\pipe\\%s"
0x140032fae  mov     edx, 104h; unsigned __int64
0x140032fb3  lea     rcx, [rbp+1E0h+FileName]; unsigned __int16 *
0x140032fb7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140032fbc  mov     ebx, eax
0x140032fbe  test    eax, eax
0x140032fc0  jns     short loc_140032FD1
0x140032fc2  mov     [rsp+2E0h+dwCreationDisposition], eax
0x140032fc6  mov     r9d, 3Eh ; '>'
0x140032fcc  jmp     loc_140033246
0x140032fd1  mov     r11d, 400h
0x140032fd7  mov     r8, rdi; unsigned __int16 *
0x140032fda  mov     edx, r11d; unsigned __int64
0x140032fdd  mov     rcx, rsi; unsigned __int16 *
0x140032fe0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140032fe5  mov     ebx, eax
0x140032fe7  test    eax, eax
0x140032fe9  jns     short loc_140032FFA
0x140032feb  mov     [rsp+2E0h+dwCreationDisposition], eax
0x140032fef  mov     r9d, 41h ; 'A'
0x140032ff5  jmp     loc_140033246
0x140032ffa  lea     r8, [rsp+2E0h+var_298]; unsigned __int64 *
0x140032fff  mov     rdx, r11; unsigned __int64
0x140033002  mov     rcx, rsi; unsigned __int16 *
0x140033005  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14003300a  mov     ebx, eax
0x14003300c  test    eax, eax
0x14003300e  jns     short loc_14003301F
0x140033010  mov     [rsp+2E0h+dwCreationDisposition], eax
0x140033014  mov     r9d, 44h ; 'D'
0x14003301a  jmp     loc_140033246
0x14003301f  mov     rbx, [rsp+2E0h+var_298]
0x140033024  cmp     rbx, 2
0x140033028  jnb     short loc_140033031
0x14003302a  xor     eax, eax
0x14003302c  mov     [rsi], eax
0x14003302e  lea     ebx, [rax+2]
0x140033031  mov     [rsp+2E0h+hTemplateFile], r15; hTemplateFile
0x140033036  lea     rcx, [rbp+1E0h+FileName]; lpFileName
0x14003303a  mov     [rsp+2E0h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x140033042  xor     r9d, r9d; lpSecurityAttributes
0x140033045  xor     r8d, r8d; dwShareMode
0x140033048  mov     [rsp+2E0h+dwCreationDisposition], 3; dwCreationDisposition
0x140033050  mov     edx, 0C0000000h; dwDesiredAccess
0x140033055  call    cs:__imp_CreateFileW
0x14003305c  nop     dword ptr [rax+rax+00h]
0x140033061  mov     r15, rax
0x140033064  lea     rcx, [rax-1]
0x140033068  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14003306c  ja      loc_140033221
0x140033072  xor     r9d, r9d; lpName
0x140033075  xor     r8d, r8d; bInitialState
0x140033078  xor     ecx, ecx; lpEventAttributes
0x14003307a  lea     edi, [r9+1]
0x14003307e  mov     edx, edi; bManualReset
0x140033080  call    cs:__imp_CreateEventW
0x140033087  nop     dword ptr [rax+rax+00h]
0x14003308c  mov     [rbp+1E0h+Overlapped.hEvent], rax
0x140033090  lea     rcx, [rax-1]
0x140033094  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140033098  ja      loc_1400331FB
0x14003309e  xor     r9d, r9d; lpName
0x1400330a1  xor     r8d, r8d; bInitialState
0x1400330a4  mov     edx, edi; bManualReset
0x1400330a6  xor     ecx, ecx; lpEventAttributes
0x1400330a8  call    cs:__imp_CreateEventW
0x1400330af  nop     dword ptr [rax+rax+00h]
0x1400330b4  mov     [rsp+2E0h+var_288.hEvent], rax
0x1400330b9  dec     rax
0x1400330bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400330c0  ja      loc_1400331D5
0x1400330c6  lea     rax, [rsp+2E0h+Overlapped]
0x1400330cb  mov     rdx, rsi; lpBuffer
0x1400330ce  lea     r8d, [rbx+rbx]; nNumberOfBytesToWrite
0x1400330d2  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax; lpOverlapped
0x1400330d7  lea     r9, [rsp+2E0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400330dc  mov     rcx, r15; hFile
0x1400330df  call    cs:__imp_WriteFile
0x1400330e6  nop     dword ptr [rax+rax+00h]
0x1400330eb  test    eax, eax
0x1400330ed  jnz     short loc_140033132
0x1400330ef  call    cs:__imp_GetLastError
0x1400330f6  nop     dword ptr [rax+rax+00h]
0x1400330fb  cmp     eax, 3E5h
0x140033100  jz      short loc_140033132
0x140033102  call    cs:__imp_GetLastError
0x140033109  nop     dword ptr [rax+rax+00h]
0x14003310e  mov     ebx, eax
0x140033110  test    eax, eax
0x140033112  jle     short loc_14003311D
0x140033114  movzx   ebx, ax
0x140033117  or      ebx, 80070000h
0x14003311d  test    ebx, ebx
0x14003311f  jns     short loc_140033132
0x140033121  mov     r9d, 6Bh ; 'k'
0x140033127  mov     [rsp+2E0h+dwCreationDisposition], ebx
0x14003312b  mov     ecx, edi
0x14003312d  jmp     loc_14003324B
0x140033132  lea     rax, [rsp+2E0h+var_288]
0x140033137  mov     r8d, 4; nNumberOfBytesToRead
0x14003313d  lea     r9, [rsp+2E0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140033142  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax; lpOverlapped
0x140033147  lea     rdx, [rsp+2E0h+Buffer]; lpBuffer
0x14003314c  mov     rcx, r15; hFile
0x14003314f  call    cs:__imp_ReadFile
0x140033156  nop     dword ptr [rax+rax+00h]
0x14003315b  mov     r14d, eax
0x14003315e  test    eax, eax
0x140033160  jnz     short loc_14003319C
0x140033162  call    cs:__imp_GetLastError
0x140033169  nop     dword ptr [rax+rax+00h]
0x14003316e  cmp     eax, 3E5h
0x140033173  jz      short loc_14003319C
0x140033175  call    cs:__imp_GetLastError
0x14003317c  nop     dword ptr [rax+rax+00h]
0x140033181  mov     ebx, eax
0x140033183  test    eax, eax
0x140033185  jle     short loc_140033190
0x140033187  movzx   ebx, ax
0x14003318a  or      ebx, 80070000h
0x140033190  test    ebx, ebx
0x140033192  jns     short loc_1400331A7
0x140033194  mov     r9d, 77h ; 'w'
0x14003319a  jmp     short loc_140033127
0x14003319c  xor     ebx, ebx
0x14003319e  test    r14d, r14d
0x1400331a1  jnz     loc_14003325E
0x1400331a7  mov     rcx, [rsp+2E0h+var_288.hEvent]; hHandle
0x1400331ac  mov     edx, 1F4h; dwMilliseconds
0x1400331b1  call    cs:__imp_WaitForSingleObject
0x1400331b8  nop     dword ptr [rax+rax+00h]
0x1400331bd  test    eax, eax
0x1400331bf  jz      loc_14003325E
0x1400331c5  mov     ebx, 80004005h
0x1400331ca  mov     r9d, 80h
0x1400331d0  jmp     loc_140033127
0x1400331d5  call    cs:__imp_GetLastError
0x1400331dc  nop     dword ptr [rax+rax+00h]
0x1400331e1  mov     ebx, eax
0x1400331e3  test    eax, eax
0x1400331e5  jle     short loc_1400331F0
0x1400331e7  movzx   ebx, ax
0x1400331ea  or      ebx, 80070000h
0x1400331f0  mov     r9d, 5Fh ; '_'
0x1400331f6  jmp     loc_140033127
0x1400331fb  call    cs:__imp_GetLastError
0x140033202  nop     dword ptr [rax+rax+00h]
0x140033207  mov     ebx, eax
0x140033209  test    eax, eax
0x14003320b  jle     short loc_140033216
0x14003320d  movzx   ebx, ax
0x140033210  or      ebx, 80070000h
0x140033216  mov     r9d, 5Ch ; '\'
0x14003321c  jmp     loc_140033127
0x140033221  call    cs:__imp_GetLastError
0x140033228  nop     dword ptr [rax+rax+00h]
0x14003322d  mov     ebx, eax
0x14003322f  test    eax, eax
0x140033231  jle     short loc_14003323C
0x140033233  movzx   ebx, ax
0x140033236  or      ebx, 80070000h
0x14003323c  mov     r9d, 59h ; 'Y'
0x140033242  mov     [rsp+2E0h+dwCreationDisposition], ebx
0x140033246  mov     ecx, 1; Level
0x14003324b  lea     r8, aCplUsepipe; "CPL::UsePipe"
0x140033252  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140033259  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003325e  mov     rcx, [rbp+1E0h+Overlapped.hEvent]; hObject
0x140033262  lea     rax, [rcx-1]
0x140033266  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003326a  ja      short loc_140033280
0x14003326c  call    cs:__imp_CloseHandle
0x140033273  nop     dword ptr [rax+rax+00h]
0x140033278  mov     [rbp+1E0h+Overlapped.hEvent], 0
0x140033280  mov     rcx, [rsp+2E0h+var_288.hEvent]; hObject
0x140033285  lea     rax, [rcx-1]
0x140033289  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003328d  ja      short loc_1400332A4
0x14003328f  call    cs:__imp_CloseHandle
0x140033296  nop     dword ptr [rax+rax+00h]
0x14003329b  mov     [rsp+2E0h+var_288.hEvent], 0
0x1400332a4  lea     rax, [r15-1]
0x1400332a8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400332ac  ja      short loc_1400332BD
0x1400332ae  mov     rcx, r15; hObject
0x1400332b1  call    cs:__imp_CloseHandle
0x1400332b8  nop     dword ptr [rax+rax+00h]
0x1400332bd  test    rsi, rsi
0x1400332c0  jz      short loc_1400332E2
0x1400332c2  call    cs:__imp_GetProcessHeap
0x1400332c9  nop     dword ptr [rax+rax+00h]
0x1400332ce  mov     r8, rsi; lpMem
0x1400332d1  xor     edx, edx; dwFlags
0x1400332d3  mov     rcx, rax; hHeap
0x1400332d6  call    cs:__imp_HeapFree
0x1400332dd  nop     dword ptr [rax+rax+00h]
0x1400332e2  mov     eax, ebx
0x1400332e4  mov     rcx, [rbp+1E0h+var_30]
0x1400332eb  xor     rcx, rsp; StackCookie
0x1400332ee  call    __security_check_cookie
0x1400332f3  mov     rbx, [rsp+2E0h+arg_10]
0x1400332fb  add     rsp, 2C0h
0x140033302  pop     r15
0x140033304  pop     r14
0x140033306  pop     rdi
0x140033307  pop     rsi
0x140033308  pop     rbp
0x140033309  retn
```
