# PsmpInitializeDiskHandleCache

- ea: `0x1800060f0`
- end: `0x180006456`
- name: `PsmpInitializeDiskHandleCache`
- size: `870`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180007bb0`

## callees

- `0x1800060f0`
- `0x180019cd8`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006262`
- `ntdll!RtlFreeHeap` at `0x180006408`
- `ntdll!RtlFreeHeap` at `0x18000642e`
- `ntdll!RtlFreeHeap` at `0x180006262`
- `ntdll!RtlFreeHeap` at `0x180006408`
- `ntdll!RtlFreeHeap` at `0x18000642e`
- `ntdll!NtClose` at `0x1800063bd`
- `ntdll!NtClose` at `0x1800063e7`
- `ntdll!NtClose` at `0x180006411`
- `ntdll!NtClose` at `0x1800063bd`
- `ntdll!NtClose` at `0x1800063e7`
- `ntdll!NtClose` at `0x180006411`
- `ntdll!RtlAllocateHeap` at `0x1800061d6`
- `ntdll!RtlAllocateHeap` at `0x18000627a`
- `ntdll!RtlAllocateHeap` at `0x1800062ff`
- `ntdll!RtlAllocateHeap` at `0x1800061d6`
- `ntdll!RtlAllocateHeap` at `0x18000627a`
- `ntdll!RtlAllocateHeap` at `0x1800062ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180006127`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180006127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000613b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000638a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000639e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000613b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000638a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000639e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000621a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800062b3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000621a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800062b3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800061ac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006371`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800061ac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006371`

## pseudocode

```c
__int64 PsmpInitializeDiskHandleCache()
{
  signed int v0; // ebx
  HANDLE FileW; // r15
  _DWORD *Heap; // rsi
  signed int LastError; // eax
  DWORD v4; // edi
  _BYTE *v5; // rax
  _BYTE *v6; // rdi
  __int64 i; // rbp
  HANDLE v8; // rax
  __int64 j; // rbp
  __int64 k; // rbp
  DWORD BytesReturned; // [rsp+40h] [rbp-2B8h] BYREF
  WCHAR FileName[12]; // [rsp+48h] [rbp-2B0h] BYREF
  WCHAR v14[32]; // [rsp+60h] [rbp-298h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-258h] BYREF

  BytesReturned = 0;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_2;
  v0 = RtlStringCchPrintfW(FileName, 10, L"\\\\.\\%c:", Buffer[0]);
  if ( v0 < 0 )
    return (unsigned int)v0;
  FileW = CreateFileW(FileName, 0, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_2:
    if ( (int)GetLastError() > 0 )
      return (unsigned __int16)GetLastError() | 0xC0070000;
    else
      return GetLastError();
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
  if ( !Heap )
    goto LABEL_8;
  if ( DeviceIoControl(FileW, 0x560000u, 0, 0, Heap, 0x20u, &BytesReturned, 0) )
    goto LABEL_19;
  LastError = GetLastError();
  if ( LastError != 234 )
  {
    if ( LastError <= 0 )
    {
LABEL_12:
      v0 = LastError;
      goto LABEL_36;
    }
    goto LABEL_18;
  }
  v4 = 24 * *Heap + 8;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( !Heap )
  {
LABEL_8:
    v0 = -1073741801;
    goto LABEL_36;
  }
  if ( DeviceIoControl(FileW, 0x560000u, 0, 0, Heap, v4, &BytesReturned, 0) )
  {
LABEL_19:
    v5 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(8 * *Heap + 8));
    v6 = v5;
    if ( v5 )
    {
      *v5 = 0;
      for ( i = 0; (unsigned int)i < *Heap; i = (unsigned int)(i + 1) )
      {
        v0 = RtlStringCchPrintfW(v14, 30, L"\\\\.\\PhysicalDrive%u", (unsigned int)Heap[6 * i + 2]);
        if ( v0 < 0 )
          goto LABEL_29;
        v8 = CreateFileW(v14, 0, 3u, 0, 3u, 0, 0);
        if ( v8 == (HANDLE)-1LL )
        {
          if ( (int)GetLastError() > 0 )
            v0 = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            v0 = GetLastError();
          if ( v0 < 0 )
          {
LABEL_29:
            for ( j = 0; (unsigned int)j < (unsigned __int8)*v6; j = (unsigned int)(j + 1) )
              NtClose(*(HANDLE *)&v6[8 * j + 8]);
            goto LABEL_35;
          }
          break;
        }
        *(_QWORD *)&v6[8 * i + 8] = v8;
        v0 = 0;
        ++*v6;
      }
      if ( !_InterlockedCompareExchange64(&PsmpDiskHandleCache, (signed __int64)v6, 0) )
        goto LABEL_36;
      for ( k = 0; (unsigned int)k < (unsigned __int8)*v6; k = (unsigned int)(k + 1) )
        NtClose(*(HANDLE *)&v6[8 * k + 8]);
LABEL_35:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      goto LABEL_36;
    }
    goto LABEL_8;
  }
  if ( (int)GetLastError() <= 0 )
  {
    LastError = GetLastError();
    goto LABEL_12;
  }
  LOWORD(LastError) = GetLastError();
LABEL_18:
  v0 = (unsigned __int16)LastError | 0xC0070000;
LABEL_36:
  NtClose(FileW);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800060f0  push    rbx
0x1800060f2  push    rbp
0x1800060f3  push    rsi
0x1800060f4  push    rdi
0x1800060f5  push    r14
0x1800060f7  push    r15
0x1800060f9  sub     rsp, 2C8h
0x180006100  mov     rax, cs:__security_cookie
0x180006107  xor     rax, rsp
0x18000610a  mov     [rsp+2F8h+var_48], rax
0x180006112  mov     edx, 104h; uSize
0x180006117  mov     [rsp+2F8h+BytesReturned], 0
0x18000611f  lea     rcx, [rsp+2F8h+Buffer]; lpBuffer
0x180006127  call    cs:__imp_GetSystemDirectoryW
0x18000612d  test    eax, eax
0x18000612f  jnz     short loc_18000615C
0x180006131  call    cs:__imp_GetLastError
0x180006137  test    eax, eax
0x180006139  jg      short loc_180006148
0x18000613b  call    cs:__imp_GetLastError
0x180006141  mov     ebx, eax
0x180006143  jmp     loc_180006434
0x180006148  call    cs:__imp_GetLastError
0x18000614e  movzx   ebx, ax
0x180006151  or      ebx, 0C0070000h
0x180006157  jmp     loc_180006434
0x18000615c  movzx   r9d, [rsp+2F8h+Buffer]
0x180006165  lea     r8, aC; "\\\\.\\%c:"
0x18000616c  mov     edx, 0Ah
0x180006171  lea     rcx, [rsp+2F8h+FileName]
0x180006176  call    RtlStringCchPrintfW
0x18000617b  mov     ebx, eax
0x18000617d  test    eax, eax
0x18000617f  js      loc_180006434
0x180006185  xor     r9d, r9d; lpSecurityAttributes
0x180006188  mov     [rsp+2F8h+hTemplateFile], 0; hTemplateFile
0x180006191  mov     [rsp+2F8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180006199  lea     rcx, [rsp+2F8h+FileName]; lpFileName
0x18000619e  xor     edx, edx; dwDesiredAccess
0x1800061a0  mov     [rsp+2F8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800061a8  lea     r8d, [r9+3]; dwShareMode
0x1800061ac  call    cs:__imp_CreateFileW
0x1800061b2  mov     r15, rax
0x1800061b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800061b9  jz      loc_180006131
0x1800061bf  mov     rcx, gs:60h
0x1800061c8  mov     edi, 20h ; ' '
0x1800061cd  mov     r8d, edi; Size
0x1800061d0  xor     edx, edx; Flags
0x1800061d2  mov     rcx, [rcx+30h]; HeapHandle
0x1800061d6  call    cs:__imp_RtlAllocateHeap
0x1800061dc  mov     rsi, rax
0x1800061df  test    rax, rax
0x1800061e2  jnz     short loc_1800061EE
0x1800061e4  mov     ebx, 0C0000017h
0x1800061e9  jmp     loc_18000640E
0x1800061ee  mov     [rsp+2F8h+lpOverlapped], 0; lpOverlapped
0x1800061f7  lea     rax, [rsp+2F8h+BytesReturned]
0x1800061fc  mov     [rsp+2F8h+hTemplateFile], rax; lpBytesReturned
0x180006201  mov     ebp, 560000h
0x180006206  mov     [rsp+2F8h+dwFlagsAndAttributes], edi; nOutBufferSize
0x18000620a  xor     r9d, r9d; nInBufferSize
0x18000620d  xor     r8d, r8d; lpInBuffer
0x180006210  mov     qword ptr [rsp+2F8h+dwCreationDisposition], rsi; lpOutBuffer
0x180006215  mov     edx, ebp; dwIoControlCode
0x180006217  mov     rcx, r15; hDevice
0x18000621a  call    cs:__imp_DeviceIoControl
0x180006220  test    eax, eax
0x180006222  jnz     loc_1800062E6
0x180006228  call    cs:__imp_GetLastError
0x18000622e  cmp     eax, 0EAh
0x180006233  jz      short loc_180006244
0x180006235  test    eax, eax
0x180006237  jg      loc_1800062D8
0x18000623d  mov     ebx, eax
0x18000623f  jmp     loc_18000640E
0x180006244  mov     eax, [rsi]
0x180006246  mov     r8, rsi; P
0x180006249  xor     edx, edx; Flags
0x18000624b  lea     ecx, [rax+rax*2]
0x18000624e  lea     edi, ds:8[rcx*8]
0x180006255  mov     rcx, gs:60h
0x18000625e  mov     rcx, [rcx+30h]; HeapHandle
0x180006262  call    cs:__imp_RtlFreeHeap
0x180006268  mov     rcx, gs:60h
0x180006271  xor     edx, edx; Flags
0x180006273  mov     r8d, edi; Size
0x180006276  mov     rcx, [rcx+30h]; HeapHandle
0x18000627a  call    cs:__imp_RtlAllocateHeap
0x180006280  mov     rsi, rax
0x180006283  test    rax, rax
0x180006286  jz      loc_1800061E4
0x18000628c  mov     [rsp+2F8h+lpOverlapped], 0; lpOverlapped
0x180006295  lea     rax, [rsp+2F8h+BytesReturned]
0x18000629a  mov     [rsp+2F8h+hTemplateFile], rax; lpBytesReturned
0x18000629f  xor     r9d, r9d; nInBufferSize
0x1800062a2  mov     [rsp+2F8h+dwFlagsAndAttributes], edi; nOutBufferSize
0x1800062a6  xor     r8d, r8d; lpInBuffer
0x1800062a9  mov     edx, ebp; dwIoControlCode
0x1800062ab  mov     qword ptr [rsp+2F8h+dwCreationDisposition], rsi; lpOutBuffer
0x1800062b0  mov     rcx, r15; hDevice
0x1800062b3  call    cs:__imp_DeviceIoControl
0x1800062b9  test    eax, eax
0x1800062bb  jnz     short loc_1800062E6
0x1800062bd  call    cs:__imp_GetLastError
0x1800062c3  test    eax, eax
0x1800062c5  jg      short loc_1800062D2
0x1800062c7  call    cs:__imp_GetLastError
0x1800062cd  jmp     loc_18000623D
0x1800062d2  call    cs:__imp_GetLastError
0x1800062d8  movzx   ebx, ax
0x1800062db  or      ebx, 0C0070000h
0x1800062e1  jmp     loc_18000640E
0x1800062e6  mov     eax, [rsi]
0x1800062e8  xor     edx, edx; Flags
0x1800062ea  mov     rcx, gs:60h
0x1800062f3  lea     r8d, ds:8[rax*8]; Size
0x1800062fb  mov     rcx, [rcx+30h]; HeapHandle
0x1800062ff  call    cs:__imp_RtlAllocateHeap
0x180006305  mov     rdi, rax
0x180006308  test    rax, rax
0x18000630b  jz      loc_1800061E4
0x180006311  mov     byte ptr [rax], 0
0x180006314  xor     ebp, ebp
0x180006316  cmp     ebp, [rsi]
0x180006318  jnb     loc_1800063CE
0x18000631e  lea     r9, ds:0[rbp*2]
0x180006326  mov     edx, 1Eh
0x18000632b  add     r9, rbp
0x18000632e  lea     r8, aPhysicaldriveU; "\\\\.\\PhysicalDrive%u"
0x180006335  lea     rcx, [rsp+2F8h+var_298]
0x18000633a  mov     r9d, [rsi+r9*8+8]
0x18000633f  call    RtlStringCchPrintfW
0x180006344  mov     ebx, eax
0x180006346  test    eax, eax
0x180006348  js      short loc_1800063B1
0x18000634a  xor     r9d, r9d; lpSecurityAttributes
0x18000634d  mov     [rsp+2F8h+hTemplateFile], 0; hTemplateFile
0x180006356  mov     [rsp+2F8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000635e  lea     rcx, [rsp+2F8h+var_298]; lpFileName
0x180006363  xor     edx, edx; dwDesiredAccess
0x180006365  mov     [rsp+2F8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000636d  lea     r8d, [r9+3]; dwShareMode
0x180006371  call    cs:__imp_CreateFileW
0x180006377  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000637b  jz      short loc_18000638A
0x18000637d  mov     [rdi+rbp*8+8], rax
0x180006382  xor     ebx, ebx
0x180006384  inc     byte ptr [rdi]
0x180006386  inc     ebp
0x180006388  jmp     short loc_180006316
0x18000638a  call    cs:__imp_GetLastError
0x180006390  test    eax, eax
0x180006392  jg      short loc_18000639E
0x180006394  call    cs:__imp_GetLastError
0x18000639a  mov     ebx, eax
0x18000639c  jmp     short loc_1800063AD
0x18000639e  call    cs:__imp_GetLastError
0x1800063a4  movzx   ebx, ax
0x1800063a7  or      ebx, 0C0070000h
0x1800063ad  test    ebx, ebx
0x1800063af  jns     short loc_1800063CE
0x1800063b1  xor     ebp, ebp
0x1800063b3  cmp     [rdi], bpl
0x1800063b6  jbe     short loc_1800063F6
0x1800063b8  mov     rcx, [rdi+rbp*8+8]; Handle
0x1800063bd  call    cs:__imp_NtClose
0x1800063c3  movzx   eax, byte ptr [rdi]
0x1800063c6  inc     ebp
0x1800063c8  cmp     ebp, eax
0x1800063ca  jb      short loc_1800063B8
0x1800063cc  jmp     short loc_1800063F6
0x1800063ce  xor     eax, eax
0x1800063d0  lock cmpxchg cs:PsmpDiskHandleCache, rdi
0x1800063d9  jz      short loc_18000640E
0x1800063db  xor     ebp, ebp
0x1800063dd  cmp     [rdi], bpl
0x1800063e0  jbe     short loc_1800063F6
0x1800063e2  mov     rcx, [rdi+rbp*8+8]; Handle
0x1800063e7  call    cs:__imp_NtClose
0x1800063ed  movzx   eax, byte ptr [rdi]
0x1800063f0  inc     ebp
0x1800063f2  cmp     ebp, eax
0x1800063f4  jb      short loc_1800063E2
0x1800063f6  mov     rcx, gs:60h
0x1800063ff  mov     r8, rdi; P
0x180006402  xor     edx, edx; Flags
0x180006404  mov     rcx, [rcx+30h]; HeapHandle
0x180006408  call    cs:__imp_RtlFreeHeap
0x18000640e  mov     rcx, r15; Handle
0x180006411  call    cs:__imp_NtClose
0x180006417  test    rsi, rsi
0x18000641a  jz      short loc_180006434
0x18000641c  mov     rcx, gs:60h
0x180006425  mov     r8, rsi; P
0x180006428  xor     edx, edx; Flags
0x18000642a  mov     rcx, [rcx+30h]; HeapHandle
0x18000642e  call    cs:__imp_RtlFreeHeap
0x180006434  mov     eax, ebx
0x180006436  mov     rcx, [rsp+2F8h+var_48]
0x18000643e  xor     rcx, rsp; StackCookie
0x180006441  call    __security_check_cookie
0x180006446  add     rsp, 2C8h
0x18000644d  pop     r15
0x18000644f  pop     r14
0x180006451  pop     rdi
0x180006452  pop     rsi
0x180006453  pop     rbp
0x180006454  pop     rbx
0x180006455  retn
```
