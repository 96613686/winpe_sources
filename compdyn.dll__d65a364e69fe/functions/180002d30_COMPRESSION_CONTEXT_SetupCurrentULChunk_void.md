# COMPRESSION_CONTEXT::SetupCurrentULChunk(void)

- ea: `0x180002d30`
- end: `0x180002ee8`
- name: `?SetupCurrentULChunk@COMPRESSION_CONTEXT@@QEAAJXZ`
- size: `440`
- prototype: `__int64 __fastcall(COMPRESSION_CONTEXT *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180002820`
- `0x18000674c`

## callees

- `0x180002d30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057f3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180002e47`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180002e47`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180002dae`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180002dae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002e75`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002e75`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002dd7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002dd7`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180002e90`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180002e90`

## pseudocode

```c
signed int __fastcall COMPRESSION_CONTEXT::SetupCurrentULChunk(COMPRESSION_CONTEXT *this)
{
  unsigned int v2; // ecx
  _DWORD *v3; // rdi
  _DWORD *v4; // rax
  signed int result; // eax
  unsigned int v6; // eax
  LPVOID v7; // rax
  HANDLE EventW; // rax
  __int64 v9; // rcx
  void *v10; // rdx
  DWORD v11; // esi
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  DWORD v14; // ecx
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-28h] BYREF
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 24);
  if ( v2 >= *((_DWORD *)this + 22) )
    return 0;
  v3 = (_DWORD *)((char *)this + 112);
  while ( 1 )
  {
    v4 = (_DWORD *)*((_QWORD *)this + 13);
    if ( !*v4 )
    {
      if ( v4[4] )
      {
        *v3 = 1;
        return 0;
      }
      ++v2;
      v3 = (_DWORD *)((char *)this + 112);
      *((_DWORD *)this + 24) = v2;
      *((_QWORD *)this + 13) = v4 + 8;
      goto LABEL_24;
    }
    v6 = *((_DWORD *)this + 34);
    v3 = (_DWORD *)((char *)this + 112);
    *((_DWORD *)this + 28) = 0;
    if ( *((_DWORD *)this + 35) > v6 )
      return 0;
    if ( !*((_QWORD *)this + 16) )
    {
      v7 = VirtualAlloc(0, 1u, 0x3000u, 4u);
      *((_QWORD *)this + 16) = v7;
      if ( !v7 )
        return -2147024888;
    }
    EventW = (HANDLE)*((_QWORD *)this + 15);
    if ( !EventW )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 15) = EventW;
      if ( !EventW )
        break;
    }
    v9 = *((_QWORD *)this + 13);
    v10 = (void *)*((_QWORD *)this + 16);
    Overlapped.hEvent = EventW;
    memset(&Overlapped, 0, 24);
    v11 = (HTTP_COMPRESSION::sm_dwPageSize - 1) & *(_DWORD *)(v9 + 8);
    Overlapped.Offset = *(_DWORD *)(v9 + 8) & ~(HTTP_COMPRESSION::sm_dwPageSize - 1);
    Overlapped.OffsetHigh = *(_DWORD *)(v9 + 12);
    NumberOfBytesRead = 0;
    if ( ReadFile(*(HANDLE *)(v9 + 24), v10, HTTP_COMPRESSION::sm_dwPageSize, &NumberOfBytesRead, &Overlapped) )
      goto LABEL_17;
    result = GetLastError();
    if ( result != 38 )
    {
      if ( result != 997 )
        goto LABEL_28;
      WaitForSingleObject(Overlapped.hEvent, 0xFFFFFFFF);
      if ( GetOverlappedResult(*(HANDLE *)(*((_QWORD *)this + 13) + 24LL), &Overlapped, &NumberOfBytesRead, 0) )
      {
LABEL_17:
        v12 = *((_QWORD *)this + 13);
        NumberOfBytesRead -= v11;
        v13 = *(_QWORD *)(v12 + 16);
        if ( NumberOfBytesRead > v13 )
          NumberOfBytesRead = *(_QWORD *)(v12 + 16);
        else
          LODWORD(v13) = NumberOfBytesRead;
        *(_QWORD *)(v12 + 16) -= (unsigned int)v13;
        *(_QWORD *)(*((_QWORD *)this + 13) + 8LL) += NumberOfBytesRead;
        v14 = v11 + NumberOfBytesRead;
        *((_DWORD *)this + 34) = v11;
        *((_DWORD *)this + 35) = v14;
        return 0;
      }
      result = GetLastError();
      if ( result != 38 )
        goto LABEL_28;
    }
    *((_QWORD *)this + 13) += 32LL;
    v2 = ++*((_DWORD *)this + 24);
LABEL_24:
    if ( v2 >= *((_DWORD *)this + 22) )
      return 0;
  }
  result = GetLastError();
LABEL_28:
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002d30  mov     [rsp+arg_8], rbx
0x180002d35  mov     [rsp+arg_10], rsi
0x180002d3a  push    rdi
0x180002d3b  sub     rsp, 50h
0x180002d3f  mov     rbx, rcx
0x180002d42  mov     ecx, [rcx+60h]
0x180002d45  cmp     ecx, [rbx+58h]
0x180002d48  jnb     short loc_180002D67
0x180002d4a  lea     rdi, [rbx+70h]
0x180002d4e  mov     rax, [rbx+68h]
0x180002d52  cmp     dword ptr [rax], 0
0x180002d55  jnz     short loc_180002D79
0x180002d57  cmp     dword ptr [rax+10h], 0
0x180002d5b  jz      loc_1800057B2
0x180002d61  mov     dword ptr [rdi], 1
0x180002d67  xor     eax, eax
0x180002d69  mov     rbx, [rsp+58h+arg_8]
0x180002d6e  mov     rsi, [rsp+58h+arg_10]
0x180002d73  add     rsp, 50h
0x180002d77  pop     rdi
0x180002d78  retn
0x180002d79  mov     eax, [rbx+88h]
0x180002d7f  lea     rdi, [rbx+70h]
0x180002d83  mov     dword ptr [rdi], 0
0x180002d89  cmp     [rbx+8Ch], eax
0x180002d8f  ja      short loc_180002D67
0x180002d91  cmp     qword ptr [rbx+80h], 0
0x180002d99  jnz     short loc_180002DC4
0x180002d9b  mov     edx, 1; dwSize
0x180002da0  xor     ecx, ecx; lpAddress
0x180002da2  mov     r9d, 4; flProtect
0x180002da8  mov     r8d, 3000h; flAllocationType
0x180002dae  call    cs:__imp_VirtualAlloc
0x180002db4  mov     [rbx+80h], rax
0x180002dbb  test    rax, rax
0x180002dbe  jz      loc_1800057E9
0x180002dc4  mov     rax, [rbx+78h]
0x180002dc8  test    rax, rax
0x180002dcb  jnz     short loc_180002DEA
0x180002dcd  xor     r9d, r9d; lpName
0x180002dd0  xor     r8d, r8d; bInitialState
0x180002dd3  xor     edx, edx; bManualReset
0x180002dd5  xor     ecx, ecx; lpEventAttributes
0x180002dd7  call    cs:__imp_CreateEventW
0x180002ddd  mov     [rbx+78h], rax
0x180002de1  test    rax, rax
0x180002de4  jz      loc_1800057F3
0x180002dea  mov     rcx, [rbx+68h]
0x180002dee  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180002df3  mov     r8d, cs:?sm_dwPageSize@HTTP_COMPRESSION@@2KA; nNumberOfBytesToRead
0x180002dfa  xorps   xmm0, xmm0
0x180002dfd  mov     rdx, [rbx+80h]; lpBuffer
0x180002e04  mov     [rsp+58h+Overlapped.hEvent], rax
0x180002e09  movdqu  xmmword ptr [rsp+58h+Overlapped.InternalHigh], xmm0
0x180002e0f  mov     [rsp+58h+Overlapped.Internal], 0
0x180002e18  lea     eax, [r8-1]
0x180002e1c  mov     esi, [rcx+8]
0x180002e1f  and     esi, eax
0x180002e21  not     eax
0x180002e23  and     eax, [rcx+8]
0x180002e26  mov     dword ptr [rsp+58h+Overlapped.10h], eax
0x180002e2a  mov     eax, [rcx+0Ch]
0x180002e2d  mov     dword ptr [rsp+58h+Overlapped.10h+4], eax
0x180002e31  lea     rax, [rsp+58h+Overlapped]
0x180002e36  mov     [rsp+58h+NumberOfBytesRead], 0
0x180002e3e  mov     rcx, [rcx+18h]; hFile
0x180002e42  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x180002e47  call    cs:__imp_ReadFile
0x180002e4d  test    eax, eax
0x180002e4f  jnz     short loc_180002E9E
0x180002e51  call    cs:__imp_GetLastError
0x180002e57  cmp     eax, 26h ; '&'
0x180002e5a  jz      loc_1800057D0
0x180002e60  cmp     eax, 3E5h
0x180002e65  jnz     loc_1800057F9
0x180002e6b  mov     rcx, [rsp+58h+Overlapped.hEvent]; hHandle
0x180002e70  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180002e75  call    cs:__imp_WaitForSingleObject
0x180002e7b  mov     rcx, [rbx+68h]
0x180002e7f  lea     r8, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x180002e84  xor     r9d, r9d; bWait
0x180002e87  lea     rdx, [rsp+58h+Overlapped]; lpOverlapped
0x180002e8c  mov     rcx, [rcx+18h]; hFile
0x180002e90  call    cs:__imp_GetOverlappedResult
0x180002e96  test    eax, eax
0x180002e98  jz      loc_1800057C5
0x180002e9e  mov     eax, [rsp+58h+NumberOfBytesRead]
0x180002ea2  mov     rcx, [rbx+68h]
0x180002ea6  sub     eax, esi
0x180002ea8  mov     edx, eax
0x180002eaa  mov     [rsp+58h+NumberOfBytesRead], eax
0x180002eae  mov     rax, [rcx+10h]
0x180002eb2  cmp     rdx, rax
0x180002eb5  ja      short loc_180002EE2
0x180002eb7  mov     eax, edx
0x180002eb9  mov     eax, eax
0x180002ebb  sub     [rcx+10h], rax
0x180002ebf  mov     rcx, [rbx+68h]
0x180002ec3  mov     eax, [rsp+58h+NumberOfBytesRead]
0x180002ec7  add     [rcx+8], rax
0x180002ecb  mov     ecx, [rsp+58h+NumberOfBytesRead]
0x180002ecf  add     ecx, esi
0x180002ed1  mov     [rbx+88h], esi
0x180002ed7  mov     [rbx+8Ch], ecx
0x180002edd  jmp     loc_180002D67
0x180002ee2  mov     [rsp+58h+NumberOfBytesRead], eax
0x180002ee6  jmp     short loc_180002EB9
0x1800057b2  inc     ecx
0x1800057b4  lea     rdi, [rbx+70h]
0x1800057b8  add     rax, 20h ; ' '
0x1800057bc  mov     [rbx+60h], ecx
0x1800057bf  mov     [rbx+68h], rax
0x1800057c3  jmp     short loc_1800057DB
0x1800057c5  call    cs:__imp_GetLastError
0x1800057cb  cmp     eax, 26h ; '&'
0x1800057ce  jnz     short loc_1800057F9
0x1800057d0  add     qword ptr [rbx+68h], 20h ; ' '
0x1800057d5  inc     dword ptr [rbx+60h]
0x1800057d8  mov     ecx, [rbx+60h]
0x1800057db  cmp     ecx, [rbx+58h]
0x1800057de  jb      loc_180002D4E
0x1800057e4  jmp     loc_180002D67
0x1800057e9  mov     eax, 80070008h
0x1800057ee  jmp     loc_180002D69
0x1800057f3  call    cs:__imp_GetLastError
0x1800057f9  test    eax, eax
0x1800057fb  jle     loc_180002D69
0x180005801  movzx   eax, ax
0x180005804  or      eax, 80070000h
0x180005809  jmp     loc_180002D69
```
