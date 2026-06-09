# IssueHsmControl

- ea: `0x18001cd74`
- end: `0x18001cf98`
- name: `IssueHsmControl`
- size: `548`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, DWORD, LPDWORD lpNumberOfBytesTransferred, __int64)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c80`
- `0x18000b960`
- `0x18000bb90`
- `0x18000dfe0`
- `0x18000e250`
- `0x18000e560`
- `0x18000e740`
- `0x18000e830`
- `0x18000e980`
- `0x18000eaf0`
- `0x18000ec20`
- `0x18000edb0`
- `0x18000ef50`
- `0x18000f100`
- `0x18000f540`
- `0x18000f5f0`
- `0x180010294`
- `0x180010d50`
- `0x180010e40`
- `0x180010fb0`
- `0x180011080`
- `0x180012354`

## callees

- `0x18001cd74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cde9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cde9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf2d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cdd0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cdd0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001cefe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001cefe`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001ce6e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001ce6e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001cf19`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001cf19`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001ceb0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001ceb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cf7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cf7a`

## pseudocode

```c
__int64 __fastcall IssueHsmControl(
        unsigned __int64 hFile,
        void *a2,
        DWORD a3,
        void *a4,
        DWORD nOutBufferSize,
        LPDWORD lpNumberOfBytesTransferred,
        struct _OVERLAPPED *a7)
{
  DWORD *lpBytesReturned; // r12
  __int64 EventW; // rdi
  signed int v10; // ebx
  signed int LastError; // eax
  struct _OVERLAPPED *lpOverlapped; // rbp
  unsigned int v13; // esi
  DWORD v14; // ecx
  signed int v15; // eax
  HANDLE hEvent; // rcx
  signed int v17; // eax
  int v19; // [rsp+40h] [rbp-68h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-60h] BYREF

  v19 = 0;
  lpBytesReturned = (DWORD *)&v19;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( lpNumberOfBytesTransferred )
    lpBytesReturned = lpNumberOfBytesTransferred;
  if ( a7 )
  {
    lpOverlapped = a7;
    v10 = 0;
    EventW = -1;
  }
  else
  {
    EventW = (__int64)CreateEventW(0, 1, 0, 0);
    if ( EventW == -1 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v10 = 0;
    }
    if ( v10 < 0 )
      goto LABEL_40;
    Overlapped.hEvent = (HANDLE)EventW;
    lpOverlapped = &Overlapped;
  }
  v13 = 0;
  if ( hFile != -1 && (hFile & 1) != 0 )
  {
    lpOverlapped->hEvent = (HANDLE)((unsigned __int64)lpOverlapped->hEvent | 1);
    hFile = *(_QWORD *)(hFile & 0xFFFFFFFFFFFFFFFEuLL);
  }
  while ( 1 )
  {
    if ( v10 == -2147023659 )
    {
      if ( v13 )
      {
        if ( v13 == 1 )
          v14 = 400;
        else
          v14 = 1000;
      }
      else
      {
        v14 = 100;
      }
      Sleep(v14);
      ++v13;
    }
    if ( DeviceIoControl((HANDLE)hFile, 0x903BCu, a2, a3, a4, nOutBufferSize, lpBytesReturned, lpOverlapped) )
    {
      v10 = 0;
    }
    else
    {
      v15 = GetLastError();
      v10 = v15;
      if ( v15 > 0 )
        v10 = (unsigned __int16)v15 | 0x80070000;
    }
    if ( a7 )
      break;
    if ( v10 == -2147023899 )
    {
      hEvent = lpOverlapped->hEvent;
      if ( hEvent )
        WaitForSingleObject(hEvent, 0xFFFFFFFF);
      if ( GetOverlappedResult((HANDLE)hFile, lpOverlapped, lpBytesReturned, 1) )
      {
        v10 = 0;
      }
      else
      {
        v17 = GetLastError();
        v10 = v17;
        if ( v17 > 0 )
          v10 = (unsigned __int16)v17 | 0x80070000;
      }
      if ( v10 < 0 )
        goto LABEL_40;
    }
    if ( v10 != -2147023659 )
      goto LABEL_40;
    if ( v13 >= 0xA )
      goto LABEL_39;
  }
  if ( v10 == -2147023659 && v13 >= 0xA )
LABEL_39:
    v10 = -2147024726;
LABEL_40:
  if ( EventW != -1 )
    CloseHandle((HANDLE)EventW);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001cd74  mov     rax, rsp
0x18001cd77  mov     [rax+20h], r9
0x18001cd7b  mov     [rax+18h], r8d
0x18001cd7f  mov     [rax+10h], rdx
0x18001cd83  push    rbx
0x18001cd84  push    rbp
0x18001cd85  push    rsi
0x18001cd86  push    rdi
0x18001cd87  push    r12
0x18001cd89  push    r13
0x18001cd8b  push    r14
0x18001cd8d  sub     rsp, 70h
0x18001cd91  xorps   xmm0, xmm0
0x18001cd94  mov     dword ptr [rax-68h], 0
0x18001cd9b  lea     r12, [rax-68h]
0x18001cd9f  mov     r14, rcx
0x18001cda2  movups  xmmword ptr [rax-60h], xmm0
0x18001cda6  movups  xmmword ptr [rax-50h], xmm0
0x18001cdaa  mov     rax, [rsp+0A8h+lpNumberOfBytesTransferred]
0x18001cdb2  test    rax, rax
0x18001cdb5  cmovnz  r12, rax
0x18001cdb9  cmp     [rsp+0A8h+arg_30], 0
0x18001cdc2  jnz     short loc_18001CE18
0x18001cdc4  xor     r9d, r9d; lpName
0x18001cdc7  xor     r8d, r8d; bInitialState
0x18001cdca  xor     ecx, ecx; lpEventAttributes
0x18001cdcc  lea     edx, [r9+1]; bManualReset
0x18001cdd0  call    cs:__imp_CreateEventW
0x18001cdd7  nop     dword ptr [rax+rax+00h]
0x18001cddc  mov     rdi, rax
0x18001cddf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001cde3  jz      short loc_18001CDE9
0x18001cde5  xor     ebx, ebx
0x18001cde7  jmp     short loc_18001CE04
0x18001cde9  call    cs:__imp_GetLastError
0x18001cdf0  nop     dword ptr [rax+rax+00h]
0x18001cdf5  mov     ebx, eax
0x18001cdf7  test    eax, eax
0x18001cdf9  jle     short loc_18001CE04
0x18001cdfb  movzx   ebx, ax
0x18001cdfe  or      ebx, 80070000h
0x18001ce04  test    ebx, ebx
0x18001ce06  js      loc_18001CF71
0x18001ce0c  mov     [rsp+0A8h+Overlapped.hEvent], rdi
0x18001ce11  lea     rbp, [rsp+0A8h+Overlapped]
0x18001ce16  jmp     short loc_18001CE26
0x18001ce18  mov     rbp, [rsp+0A8h+arg_30]
0x18001ce20  xor     ebx, ebx
0x18001ce22  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001ce26  xor     esi, esi
0x18001ce28  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18001ce2c  jz      short loc_18001CE40
0x18001ce2e  test    r14b, 1
0x18001ce32  jz      short loc_18001CE40
0x18001ce34  or      qword ptr [rbp+18h], 1
0x18001ce39  and     r14, 0FFFFFFFFFFFFFFFEh
0x18001ce3d  mov     r14, [r14]
0x18001ce40  mov     r13d, [rsp+0A8h+arg_20]
0x18001ce48  cmp     ebx, 800704D5h
0x18001ce4e  jnz     short loc_18001CE7C
0x18001ce50  mov     eax, esi
0x18001ce52  test    esi, esi
0x18001ce54  jz      short loc_18001CE69
0x18001ce56  cmp     eax, 1
0x18001ce59  jz      short loc_18001CE62
0x18001ce5b  mov     ecx, 3E8h
0x18001ce60  jmp     short loc_18001CE6E
0x18001ce62  mov     ecx, 190h
0x18001ce67  jmp     short loc_18001CE6E
0x18001ce69  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18001ce6e  call    cs:__imp_Sleep
0x18001ce75  nop     dword ptr [rax+rax+00h]
0x18001ce7a  inc     esi
0x18001ce7c  mov     rax, [rsp+0A8h+arg_18]
0x18001ce84  mov     edx, 903BCh; dwIoControlCode
0x18001ce89  mov     r9d, [rsp+0A8h+nInBufferSize]; nInBufferSize
0x18001ce91  mov     rcx, r14; hDevice
0x18001ce94  mov     r8, [rsp+0A8h+lpInBuffer]; lpInBuffer
0x18001ce9c  mov     [rsp+0A8h+lpOverlapped], rbp; lpOverlapped
0x18001cea1  mov     [rsp+0A8h+lpBytesReturned], r12; lpBytesReturned
0x18001cea6  mov     [rsp+0A8h+nOutBufferSize], r13d; nOutBufferSize
0x18001ceab  mov     [rsp+0A8h+lpOutBuffer], rax; lpOutBuffer
0x18001ceb0  call    cs:__imp_DeviceIoControl
0x18001ceb7  nop     dword ptr [rax+rax+00h]
0x18001cebc  test    eax, eax
0x18001cebe  jz      short loc_18001CEC4
0x18001cec0  xor     ebx, ebx
0x18001cec2  jmp     short loc_18001CEDF
0x18001cec4  call    cs:__imp_GetLastError
0x18001cecb  nop     dword ptr [rax+rax+00h]
0x18001ced0  mov     ebx, eax
0x18001ced2  test    eax, eax
0x18001ced4  jle     short loc_18001CEDF
0x18001ced6  movzx   ebx, ax
0x18001ced9  or      ebx, 80070000h
0x18001cedf  cmp     [rsp+0A8h+arg_30], 0
0x18001cee8  jnz     short loc_18001CF5F
0x18001ceea  cmp     ebx, 800703E5h
0x18001cef0  jnz     short loc_18001CF4C
0x18001cef2  mov     rcx, [rbp+18h]; hHandle
0x18001cef6  test    rcx, rcx
0x18001cef9  jz      short loc_18001CF0A
0x18001cefb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001cefe  call    cs:__imp_WaitForSingleObject
0x18001cf05  nop     dword ptr [rax+rax+00h]
0x18001cf0a  mov     r9d, 1; bWait
0x18001cf10  mov     r8, r12; lpNumberOfBytesTransferred
0x18001cf13  mov     rdx, rbp; lpOverlapped
0x18001cf16  mov     rcx, r14; hFile
0x18001cf19  call    cs:__imp_GetOverlappedResult
0x18001cf20  nop     dword ptr [rax+rax+00h]
0x18001cf25  test    eax, eax
0x18001cf27  jz      short loc_18001CF2D
0x18001cf29  xor     ebx, ebx
0x18001cf2b  jmp     short loc_18001CF48
0x18001cf2d  call    cs:__imp_GetLastError
0x18001cf34  nop     dword ptr [rax+rax+00h]
0x18001cf39  mov     ebx, eax
0x18001cf3b  test    eax, eax
0x18001cf3d  jle     short loc_18001CF48
0x18001cf3f  movzx   ebx, ax
0x18001cf42  or      ebx, 80070000h
0x18001cf48  test    ebx, ebx
0x18001cf4a  js      short loc_18001CF71
0x18001cf4c  cmp     ebx, 800704D5h
0x18001cf52  jnz     short loc_18001CF71
0x18001cf54  cmp     esi, 0Ah
0x18001cf57  jb      loc_18001CE48
0x18001cf5d  jmp     short loc_18001CF6C
0x18001cf5f  cmp     ebx, 800704D5h
0x18001cf65  jnz     short loc_18001CF71
0x18001cf67  cmp     esi, 0Ah
0x18001cf6a  jb      short loc_18001CF71
0x18001cf6c  mov     ebx, 800700AAh
0x18001cf71  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001cf75  jz      short loc_18001CF86
0x18001cf77  mov     rcx, rdi; hObject
0x18001cf7a  call    cs:__imp_CloseHandle
0x18001cf81  nop     dword ptr [rax+rax+00h]
0x18001cf86  mov     eax, ebx
0x18001cf88  add     rsp, 70h
0x18001cf8c  pop     r14
0x18001cf8e  pop     r13
0x18001cf90  pop     r12
0x18001cf92  pop     rdi
0x18001cf93  pop     rsi
0x18001cf94  pop     rbp
0x18001cf95  pop     rbx
0x18001cf96  retn
```
