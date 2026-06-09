# GetState(void *,KSSTATE *)

- ea: `0x18000f2a8`
- end: `0x18000f503`
- name: `?GetState@@YAJPEAXPEAW4KSSTATE@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(char *hFile, enum KSSTATE *lpOutBuffer)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000eff4`
- `0x18000f150`
- `0x180018060`

## callees

- `0x18000f2a8`
- `0x180025b0c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f36a`
- `KERNEL32!GetLastError` at `0x18000f40b`
- `KERNEL32!GetLastError` at `0x18000f44c`
- `KERNEL32!GetLastError` at `0x18000f36a`
- `KERNEL32!GetLastError` at `0x18000f40b`
- `KERNEL32!GetLastError` at `0x18000f44c`
- `KERNEL32!CreateEventW` at `0x18000f30c`
- `KERNEL32!CreateEventW` at `0x18000f30c`
- `KERNEL32!CloseHandle` at `0x18000f396`
- `KERNEL32!CloseHandle` at `0x18000f396`
- `KERNEL32!GetOverlappedResult` at `0x18000f43c`
- `KERNEL32!GetOverlappedResult` at `0x18000f43c`
- `KERNEL32!DeviceIoControl` at `0x18000f356`
- `KERNEL32!DeviceIoControl` at `0x18000f356`

## pseudocode

```c
__int64 __fastcall GetState(char *hFile, enum KSSTATE *lpOutBuffer)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  signed int v7; // eax
  signed int v8; // eax
  GUID InBuffer; // [rsp+40h] [rbp-40h] BYREF
  int v10; // [rsp+50h] [rbp-30h]
  int v11; // [rsp+54h] [rbp-2Ch]
  struct _OVERLAPPED Overlapped; // [rsp+58h] [rbp-28h] BYREF
  DWORD BytesReturned; // [rsp+A0h] [rbp+20h] BYREF

  BytesReturned = 0;
  v10 = 0;
  v11 = 1;
  InBuffer = GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000;
  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v5 = -2147024890;
    goto LABEL_8;
  }
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(hFile, 0x2F0003u, &InBuffer, 0x18u, lpOutBuffer, 4u, &BytesReturned, &Overlapped) )
    {
      switch ( Overlapped.Internal )
      {
        case 0x101uLL:
          v5 = -2147024875;
          goto LABEL_7;
        case 0x105uLL:
          v5 = -2147024662;
          goto LABEL_7;
        case 0x107uLL:
          v5 = -2147023595;
          goto LABEL_7;
      }
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 != -2147023899 )
        goto LABEL_7;
      if ( !GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
      {
        v8 = GetLastError();
        v5 = v8;
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
        goto LABEL_7;
      }
    }
    v5 = 0;
LABEL_7:
    CloseHandle(Overlapped.hEvent);
    goto LABEL_8;
  }
  v7 = GetLastError();
  v5 = v7;
  if ( v7 > 0 )
    v5 = (unsigned __int16)v7 | 0x80070000;
LABEL_8:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_qdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
      hFile,
      *lpOutBuffer,
      v5);
  if ( ((v5 + 2147023728) & 0xFFFFFFFD) == 0 )
  {
    v5 = 0;
    *lpOutBuffer = KSSTATE_RUN;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_qdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, hFile, 3, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x18000f2a8  mov     [rsp-18h+arg_8], rbx
0x18000f2ad  mov     [rsp-18h+arg_10], rsi
0x18000f2b2  push    rbp
0x18000f2b3  push    rdi
0x18000f2b4  push    r14
0x18000f2b6  mov     rbp, rsp
0x18000f2b9  sub     rsp, 80h
0x18000f2c0  movups  xmm0, xmmword ptr cs:_GUID_1d58c920_ac9b_11cf_a5d6_28db04c10000.Data1
0x18000f2c7  lea     rax, [rcx-1]
0x18000f2cb  mov     [rbp+BytesReturned], 0
0x18000f2d2  mov     [rbp+var_30], 0
0x18000f2d9  mov     r14, rdx
0x18000f2dc  mov     [rbp+var_2C], 1
0x18000f2e3  mov     rsi, rcx
0x18000f2e6  movdqu  [rbp+InBuffer], xmm0
0x18000f2eb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f2ef  ja      loc_18000F48A
0x18000f2f5  xorps   xmm0, xmm0
0x18000f2f8  xor     r9d, r9d; lpName
0x18000f2fb  xor     r8d, r8d; bInitialState
0x18000f2fe  xor     ecx, ecx; lpEventAttributes
0x18000f300  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000f304  lea     edx, [r9+1]; bManualReset
0x18000f308  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18000f30c  call    cs:__imp_CreateEventW
0x18000f313  nop     dword ptr [rax+rax+00h]
0x18000f318  mov     [rbp+Overlapped.hEvent], rax
0x18000f31c  test    rax, rax
0x18000f31f  jz      loc_18000F40B
0x18000f325  lea     rax, [rbp+Overlapped]
0x18000f329  mov     r9d, 18h; nInBufferSize
0x18000f32f  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x18000f334  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000f338  lea     rax, [rbp+BytesReturned]
0x18000f33c  mov     edx, 2F0003h; dwIoControlCode
0x18000f341  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x18000f346  mov     rcx, rsi; hDevice
0x18000f349  mov     [rsp+80h+nOutBufferSize], 4; nOutBufferSize
0x18000f351  mov     [rsp+80h+lpOutBuffer], r14; lpOutBuffer
0x18000f356  call    cs:__imp_DeviceIoControl
0x18000f35d  nop     dword ptr [rax+rax+00h]
0x18000f362  test    eax, eax
0x18000f364  jnz     loc_18000F3EB
0x18000f36a  call    cs:__imp_GetLastError
0x18000f371  nop     dword ptr [rax+rax+00h]
0x18000f376  mov     ebx, eax
0x18000f378  mov     edi, 80070000h
0x18000f37d  test    eax, eax
0x18000f37f  jle     short loc_18000F386
0x18000f381  movzx   ebx, ax
0x18000f384  or      ebx, edi
0x18000f386  cmp     ebx, 800703E5h
0x18000f38c  jz      loc_18000F42B
0x18000f392  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x18000f396  call    cs:__imp_CloseHandle
0x18000f39d  nop     dword ptr [rax+rax+00h]
0x18000f3a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3a9  lea     rdi, WPP_GLOBAL_Control
0x18000f3b0  cmp     rcx, rdi
0x18000f3b3  jz      short loc_18000F3BF
0x18000f3b5  cmp     byte ptr [rcx+19h], 2
0x18000f3b9  jnb     loc_18000F494
0x18000f3bf  lea     eax, [rbx+7FF8FB70h]
0x18000f3c5  test    eax, 0FFFFFFFDh
0x18000f3ca  jz      loc_18000F4BC
0x18000f3d0  lea     r11, [rsp+80h+var_s0]
0x18000f3d8  mov     eax, ebx
0x18000f3da  mov     rbx, [r11+28h]
0x18000f3de  mov     rsi, [r11+30h]
0x18000f3e2  mov     rsp, r11
0x18000f3e5  pop     r14
0x18000f3e7  pop     rdi
0x18000f3e8  pop     rbp
0x18000f3e9  retn
0x18000f3eb  mov     rax, [rbp+Overlapped.Internal]
0x18000f3ef  sub     rax, 101h
0x18000f3f5  jz      loc_18000F480
0x18000f3fb  sub     rax, 4
0x18000f3ff  jz      short loc_18000F476
0x18000f401  cmp     rax, 2
0x18000f405  jz      short loc_18000F46C
0x18000f407  xor     ebx, ebx
0x18000f409  jmp     short loc_18000F392
0x18000f40b  call    cs:__imp_GetLastError
0x18000f412  nop     dword ptr [rax+rax+00h]
0x18000f417  mov     ebx, eax
0x18000f419  test    eax, eax
0x18000f41b  jle     short loc_18000F3A2
0x18000f41d  movzx   ebx, ax
0x18000f420  or      ebx, 80070000h
0x18000f426  jmp     loc_18000F3A2
0x18000f42b  mov     r9d, 1; bWait
0x18000f431  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x18000f435  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18000f439  mov     rcx, rsi; hFile
0x18000f43c  call    cs:__imp_GetOverlappedResult
0x18000f443  nop     dword ptr [rax+rax+00h]
0x18000f448  test    eax, eax
0x18000f44a  jnz     short loc_18000F407
0x18000f44c  call    cs:__imp_GetLastError
0x18000f453  nop     dword ptr [rax+rax+00h]
0x18000f458  mov     ebx, eax
0x18000f45a  test    eax, eax
0x18000f45c  jle     loc_18000F392
0x18000f462  movzx   ebx, ax
0x18000f465  or      ebx, edi
0x18000f467  jmp     loc_18000F392
0x18000f46c  mov     ebx, 80070515h
0x18000f471  jmp     loc_18000F392
0x18000f476  mov     ebx, 800700EAh
0x18000f47b  jmp     loc_18000F392
0x18000f480  mov     ebx, 80070015h
0x18000f485  jmp     loc_18000F392
0x18000f48a  mov     ebx, 80070006h
0x18000f48f  jmp     loc_18000F3A2
0x18000f494  mov     eax, [r14]
0x18000f497  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x18000f49e  mov     rcx, [rcx+10h]
0x18000f4a2  mov     edx, 0Ah
0x18000f4a7  mov     [rsp+80h+nOutBufferSize], ebx
0x18000f4ab  mov     r9, rsi
0x18000f4ae  mov     dword ptr [rsp+80h+lpOutBuffer], eax
0x18000f4b2  call    WPP_SF_qdD
0x18000f4b7  jmp     loc_18000F3BF
0x18000f4bc  mov     eax, 3
0x18000f4c1  xor     ebx, ebx
0x18000f4c3  mov     [r14], eax
0x18000f4c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4cd  cmp     rcx, rdi
0x18000f4d0  jz      loc_18000F3D0
0x18000f4d6  cmp     byte ptr [rcx+19h], 2
0x18000f4da  jb      loc_18000F3D0
0x18000f4e0  mov     rcx, [rcx+10h]
0x18000f4e4  lea     edx, [rax+8]
0x18000f4e7  mov     [rsp+80h+nOutBufferSize], ebx
0x18000f4eb  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x18000f4f2  mov     r9, rsi
0x18000f4f5  mov     dword ptr [rsp+80h+lpOutBuffer], eax
0x18000f4f9  call    WPP_SF_qdD
0x18000f4fe  jmp     loc_18000F3D0
```
