# CollectAllSets(void *,_GUID * *,ulong *)

- ea: `0x18000ae28`
- end: `0x18000b287`
- name: `?CollectAllSets@@YAJPEAXPEAPEAU_GUID@@PEAK@Z`
- size: `1119`
- prototype: `__int64 __fastcall(char *hFile, struct _GUID **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000aaac`
- `0x1800229d0`

## callees

- `0x18000ae28`
- `0x18000bde0`
- `0x18001f1c4`
- `0x18001f210`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000aeb1`
- `KERNEL32!GetLastError` at `0x18000af00`
- `KERNEL32!GetLastError` at `0x18000af3d`
- `KERNEL32!GetLastError` at `0x18000af96`
- `KERNEL32!GetLastError` at `0x18000afe5`
- `KERNEL32!GetLastError` at `0x18000b022`
- `KERNEL32!GetLastError` at `0x18000b07b`
- `KERNEL32!GetLastError` at `0x18000b0ca`
- `KERNEL32!GetLastError` at `0x18000b107`
- `KERNEL32!GetLastError` at `0x18000aeb1`
- `KERNEL32!GetLastError` at `0x18000af00`
- `KERNEL32!GetLastError` at `0x18000af3d`
- `KERNEL32!GetLastError` at `0x18000af96`
- `KERNEL32!GetLastError` at `0x18000afe5`
- `KERNEL32!GetLastError` at `0x18000b022`
- `KERNEL32!GetLastError` at `0x18000b07b`
- `KERNEL32!GetLastError` at `0x18000b0ca`
- `KERNEL32!GetLastError` at `0x18000b107`
- `KERNEL32!CreateEventW` at `0x18000ae9c`
- `KERNEL32!CreateEventW` at `0x18000af81`
- `KERNEL32!CreateEventW` at `0x18000b066`
- `KERNEL32!CreateEventW` at `0x18000ae9c`
- `KERNEL32!CreateEventW` at `0x18000af81`
- `KERNEL32!CreateEventW` at `0x18000b066`
- `KERNEL32!CloseHandle` at `0x18000af4d`
- `KERNEL32!CloseHandle` at `0x18000b032`
- `KERNEL32!CloseHandle` at `0x18000b117`
- `KERNEL32!CloseHandle` at `0x18000af4d`
- `KERNEL32!CloseHandle` at `0x18000b032`
- `KERNEL32!CloseHandle` at `0x18000b117`
- `KERNEL32!GetOverlappedResult` at `0x18000af2d`
- `KERNEL32!GetOverlappedResult` at `0x18000b012`
- `KERNEL32!GetOverlappedResult` at `0x18000b0f7`
- `KERNEL32!GetOverlappedResult` at `0x18000af2d`
- `KERNEL32!GetOverlappedResult` at `0x18000b012`
- `KERNEL32!GetOverlappedResult` at `0x18000b0f7`
- `KERNEL32!DeviceIoControl` at `0x18000aef0`
- `KERNEL32!DeviceIoControl` at `0x18000afd5`
- `KERNEL32!DeviceIoControl` at `0x18000b0ba`
- `KERNEL32!DeviceIoControl` at `0x18000aef0`
- `KERNEL32!DeviceIoControl` at `0x18000afd5`
- `KERNEL32!DeviceIoControl` at `0x18000b0ba`

## pseudocode

```c
__int64 __fastcall CollectAllSets(char *hFile, struct _GUID **a2, unsigned int *a3)
{
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  struct _GUID *lpOutBuffer; // rax
  unsigned __int64 v11; // rdx
  DWORD v12; // ecx
  DWORD v13; // r8d
  signed int v14; // eax
  DWORD v15; // r10d
  signed int v16; // eax
  bool v17; // zf
  DWORD v18; // ecx
  DWORD v19; // [rsp+40h] [rbp-40h] BYREF
  GUID InBuffer; // [rsp+48h] [rbp-38h] BYREF
  int v21; // [rsp+58h] [rbp-28h]
  int v22; // [rsp+5Ch] [rbp-24h]
  struct _OVERLAPPED Overlapped; // [rsp+60h] [rbp-20h] BYREF
  DWORD BytesReturned; // [rsp+B0h] [rbp+30h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+C0h] [rbp+40h] BYREF
  DWORD lpBytesReturned; // [rsp+C8h] [rbp+48h] BYREF

  v22 = 256;
  NumberOfBytesTransferred = 0;
  lpBytesReturned = 0;
  v19 = 0;
  *a3 = 0;
  v21 = 0;
  BytesReturned = 0;
  InBuffer = GUID_00000000_0000_0000_0000_000000000000;
  if ( (unsigned __int64)(hFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    memset(&Overlapped, 0, 24);
    Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
    if ( Overlapped.hEvent )
    {
      if ( !DeviceIoControl(hFile, 0x2F0003u, &InBuffer, 0x18u, 0, 0, &BytesReturned, &Overlapped) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError == -2147023899 && !GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
          GetLastError();
      }
      CloseHandle(Overlapped.hEvent);
    }
    else
    {
      GetLastError();
    }
  }
  NumberOfBytesTransferred = 0;
  if ( (unsigned __int64)(hFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    memset(&Overlapped, 0, sizeof(Overlapped));
    Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
    if ( Overlapped.hEvent )
    {
      if ( !DeviceIoControl(hFile, 0x2F000Fu, &InBuffer, 0x18u, 0, 0, &NumberOfBytesTransferred, &Overlapped) )
      {
        v7 = GetLastError();
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        if ( v7 == -2147023899 && !GetOverlappedResult(hFile, &Overlapped, &NumberOfBytesTransferred, 1) )
          GetLastError();
      }
      CloseHandle(Overlapped.hEvent);
    }
    else
    {
      GetLastError();
    }
  }
  lpBytesReturned = 0;
  if ( (unsigned __int64)(hFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    memset(&Overlapped, 0, sizeof(Overlapped));
    Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
    if ( Overlapped.hEvent )
    {
      if ( !DeviceIoControl(hFile, 0x2F0007u, &InBuffer, 0x18u, 0, 0, &lpBytesReturned, &Overlapped) )
      {
        v8 = GetLastError();
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        if ( v8 == -2147023899 && !GetOverlappedResult(hFile, &Overlapped, &lpBytesReturned, 1) )
          GetLastError();
      }
      CloseHandle(Overlapped.hEvent);
    }
    else
    {
      GetLastError();
    }
  }
  if ( !(BytesReturned + lpBytesReturned + NumberOfBytesTransferred) )
    goto LABEL_32;
  lpOutBuffer = (struct _GUID *)operator new[](
                                  saturated_mul(
                                    (unsigned __int64)(BytesReturned + lpBytesReturned + NumberOfBytesTransferred) >> 4,
                                    0x10u));
  *a2 = lpOutBuffer;
  if ( !lpOutBuffer )
    return 2147942414LL;
  v12 = BytesReturned;
  if ( BytesReturned )
  {
    if ( KsSynchronousDeviceControl(hFile, 0x2F0003u, &InBuffer, 0x18u, lpOutBuffer, BytesReturned, &v19) >= 0 )
    {
      v12 = BytesReturned;
    }
    else
    {
      v12 = 0;
      BytesReturned = 0;
    }
  }
  v13 = NumberOfBytesTransferred;
  if ( NumberOfBytesTransferred )
  {
    v14 = KsSynchronousDeviceControl(
            hFile,
            0x2F000Fu,
            &InBuffer,
            0x18u,
            (char *)*a2 + (v12 & 0xFFFFFFF0),
            NumberOfBytesTransferred,
            &v19);
    v12 = BytesReturned;
    if ( v14 >= 0 )
    {
      v13 = NumberOfBytesTransferred;
    }
    else
    {
      v13 = 0;
      NumberOfBytesTransferred = 0;
    }
  }
  v15 = lpBytesReturned;
  if ( lpBytesReturned )
  {
    v16 = KsSynchronousDeviceControl(
            hFile,
            0x2F0007u,
            &InBuffer,
            0x18u,
            (char *)*a2 + ((v13 + v12) & 0xFFFFFFF0),
            lpBytesReturned,
            &v19);
    v12 = BytesReturned;
    v13 = NumberOfBytesTransferred;
    if ( v16 >= 0 )
    {
      v15 = lpBytesReturned;
    }
    else
    {
      v15 = 0;
      lpBytesReturned = 0;
    }
  }
  v17 = v15 + v13 + v12 == 0;
  v18 = v15 + v13 + v12;
  BytesReturned = v18;
  if ( v17 )
  {
    operator delete(*a2, v11);
LABEL_32:
    *a2 = 0;
    return 1170;
  }
  *a3 = v18 >> 4;
  return 0;
}

```

## disassembly

```asm
0x18000ae28  mov     [rsp-28h+arg_8], rbx
0x18000ae2d  push    rbp
0x18000ae2e  push    rsi
0x18000ae2f  push    rdi
0x18000ae30  push    r14
0x18000ae32  push    r15
0x18000ae34  mov     rbp, rsp
0x18000ae37  sub     rsp, 80h
0x18000ae3e  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000ae45  xor     r14d, r14d
0x18000ae48  mov     [rbp+var_24], 100h
0x18000ae4f  lea     rax, [rcx-1]
0x18000ae53  mov     [rbp+NumberOfBytesTransferred], r14d
0x18000ae57  mov     [rbp+arg_18], r14d
0x18000ae5b  mov     rsi, r8
0x18000ae5e  mov     [rbp+var_40], r14d
0x18000ae62  mov     rdi, rdx
0x18000ae65  mov     [r8], r14d
0x18000ae68  lea     r15d, [r14+1]
0x18000ae6c  mov     [rbp+var_28], r14d
0x18000ae70  mov     rbx, rcx
0x18000ae73  mov     [rbp+BytesReturned], r14d
0x18000ae77  movdqu  [rbp+InBuffer], xmm0
0x18000ae7c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ae80  ja      loc_18000AF59
0x18000ae86  xorps   xmm0, xmm0
0x18000ae89  xor     r9d, r9d; lpName
0x18000ae8c  xor     r8d, r8d; bInitialState
0x18000ae8f  mov     edx, r15d; bManualReset
0x18000ae92  xor     ecx, ecx; lpEventAttributes
0x18000ae94  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000ae98  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18000ae9c  call    cs:__imp_CreateEventW
0x18000aea3  nop     dword ptr [rax+rax+00h]
0x18000aea8  mov     [rbp+Overlapped.hEvent], rax
0x18000aeac  test    rax, rax
0x18000aeaf  jnz     short loc_18000AEC2
0x18000aeb1  call    cs:__imp_GetLastError
0x18000aeb8  nop     dword ptr [rax+rax+00h]
0x18000aebd  jmp     loc_18000AF59
0x18000aec2  lea     rax, [rbp+Overlapped]
0x18000aec6  mov     r9d, 18h; nInBufferSize
0x18000aecc  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x18000aed1  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000aed5  lea     rax, [rbp+BytesReturned]
0x18000aed9  mov     edx, 2F0003h; dwIoControlCode
0x18000aede  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x18000aee3  mov     rcx, rbx; hDevice
0x18000aee6  mov     [rsp+80h+nOutBufferSize], r14d; nOutBufferSize
0x18000aeeb  mov     [rsp+80h+lpOutBuffer], r14; lpOutBuffer
0x18000aef0  call    cs:__imp_DeviceIoControl
0x18000aef7  nop     dword ptr [rax+rax+00h]
0x18000aefc  test    eax, eax
0x18000aefe  jnz     short loc_18000AF49
0x18000af00  call    cs:__imp_GetLastError
0x18000af07  nop     dword ptr [rax+rax+00h]
0x18000af0c  test    eax, eax
0x18000af0e  jle     short loc_18000AF18
0x18000af10  movzx   eax, ax
0x18000af13  or      eax, 80070000h
0x18000af18  cmp     eax, 800703E5h
0x18000af1d  jnz     short loc_18000AF49
0x18000af1f  mov     r9d, r15d; bWait
0x18000af22  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x18000af26  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18000af2a  mov     rcx, rbx; hFile
0x18000af2d  call    cs:__imp_GetOverlappedResult
0x18000af34  nop     dword ptr [rax+rax+00h]
0x18000af39  test    eax, eax
0x18000af3b  jnz     short loc_18000AF49
0x18000af3d  call    cs:__imp_GetLastError
0x18000af44  nop     dword ptr [rax+rax+00h]
0x18000af49  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x18000af4d  call    cs:__imp_CloseHandle
0x18000af54  nop     dword ptr [rax+rax+00h]
0x18000af59  lea     rax, [rbx-1]
0x18000af5d  mov     [rbp+NumberOfBytesTransferred], r14d
0x18000af61  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000af65  ja      loc_18000B03E
0x18000af6b  xorps   xmm0, xmm0
0x18000af6e  xor     r9d, r9d; lpName
0x18000af71  xor     r8d, r8d; bInitialState
0x18000af74  mov     edx, r15d; bManualReset
0x18000af77  xor     ecx, ecx; lpEventAttributes
0x18000af79  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000af7d  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18000af81  call    cs:__imp_CreateEventW
0x18000af88  nop     dword ptr [rax+rax+00h]
0x18000af8d  mov     [rbp+Overlapped.hEvent], rax
0x18000af91  test    rax, rax
0x18000af94  jnz     short loc_18000AFA7
0x18000af96  call    cs:__imp_GetLastError
0x18000af9d  nop     dword ptr [rax+rax+00h]
0x18000afa2  jmp     loc_18000B03E
0x18000afa7  lea     rax, [rbp+Overlapped]
0x18000afab  mov     r9d, 18h; nInBufferSize
0x18000afb1  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x18000afb6  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000afba  lea     rax, [rbp+NumberOfBytesTransferred]
0x18000afbe  mov     edx, 2F000Fh; dwIoControlCode
0x18000afc3  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x18000afc8  mov     rcx, rbx; hDevice
0x18000afcb  mov     [rsp+80h+nOutBufferSize], r14d; nOutBufferSize
0x18000afd0  mov     [rsp+80h+lpOutBuffer], r14; lpOutBuffer
0x18000afd5  call    cs:__imp_DeviceIoControl
0x18000afdc  nop     dword ptr [rax+rax+00h]
0x18000afe1  test    eax, eax
0x18000afe3  jnz     short loc_18000B02E
0x18000afe5  call    cs:__imp_GetLastError
0x18000afec  nop     dword ptr [rax+rax+00h]
0x18000aff1  test    eax, eax
0x18000aff3  jle     short loc_18000AFFD
0x18000aff5  movzx   eax, ax
0x18000aff8  or      eax, 80070000h
0x18000affd  cmp     eax, 800703E5h
0x18000b002  jnz     short loc_18000B02E
0x18000b004  mov     r9d, r15d; bWait
0x18000b007  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18000b00b  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18000b00f  mov     rcx, rbx; hFile
0x18000b012  call    cs:__imp_GetOverlappedResult
0x18000b019  nop     dword ptr [rax+rax+00h]
0x18000b01e  test    eax, eax
0x18000b020  jnz     short loc_18000B02E
0x18000b022  call    cs:__imp_GetLastError
0x18000b029  nop     dword ptr [rax+rax+00h]
0x18000b02e  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x18000b032  call    cs:__imp_CloseHandle
0x18000b039  nop     dword ptr [rax+rax+00h]
0x18000b03e  lea     rax, [rbx-1]
0x18000b042  mov     [rbp+arg_18], r14d
0x18000b046  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b04a  ja      loc_18000B123
0x18000b050  xorps   xmm0, xmm0
0x18000b053  xor     r9d, r9d; lpName
0x18000b056  xor     r8d, r8d; bInitialState
0x18000b059  mov     edx, r15d; bManualReset
0x18000b05c  xor     ecx, ecx; lpEventAttributes
0x18000b05e  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000b062  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18000b066  call    cs:__imp_CreateEventW
0x18000b06d  nop     dword ptr [rax+rax+00h]
0x18000b072  mov     [rbp+Overlapped.hEvent], rax
0x18000b076  test    rax, rax
0x18000b079  jnz     short loc_18000B08C
0x18000b07b  call    cs:__imp_GetLastError
0x18000b082  nop     dword ptr [rax+rax+00h]
0x18000b087  jmp     loc_18000B123
0x18000b08c  lea     rax, [rbp+Overlapped]
0x18000b090  mov     r9d, 18h; nInBufferSize
0x18000b096  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x18000b09b  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000b09f  lea     rax, [rbp+arg_18]
0x18000b0a3  mov     edx, 2F0007h; dwIoControlCode
0x18000b0a8  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x18000b0ad  mov     rcx, rbx; hDevice
0x18000b0b0  mov     [rsp+80h+nOutBufferSize], r14d; nOutBufferSize
0x18000b0b5  mov     [rsp+80h+lpOutBuffer], r14; lpOutBuffer
0x18000b0ba  call    cs:__imp_DeviceIoControl
0x18000b0c1  nop     dword ptr [rax+rax+00h]
0x18000b0c6  test    eax, eax
0x18000b0c8  jnz     short loc_18000B113
0x18000b0ca  call    cs:__imp_GetLastError
0x18000b0d1  nop     dword ptr [rax+rax+00h]
0x18000b0d6  test    eax, eax
0x18000b0d8  jle     short loc_18000B0E2
0x18000b0da  movzx   eax, ax
0x18000b0dd  or      eax, 80070000h
0x18000b0e2  cmp     eax, 800703E5h
0x18000b0e7  jnz     short loc_18000B113
0x18000b0e9  mov     r9d, r15d; bWait
0x18000b0ec  lea     r8, [rbp+arg_18]; lpNumberOfBytesTransferred
0x18000b0f0  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18000b0f4  mov     rcx, rbx; hFile
0x18000b0f7  call    cs:__imp_GetOverlappedResult
0x18000b0fe  nop     dword ptr [rax+rax+00h]
0x18000b103  test    eax, eax
0x18000b105  jnz     short loc_18000B113
0x18000b107  call    cs:__imp_GetLastError
0x18000b10e  nop     dword ptr [rax+rax+00h]
0x18000b113  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x18000b117  call    cs:__imp_CloseHandle
0x18000b11e  nop     dword ptr [rax+rax+00h]
0x18000b123  mov     ecx, [rbp+NumberOfBytesTransferred]
0x18000b126  add     ecx, [rbp+arg_18]
0x18000b129  add     ecx, [rbp+BytesReturned]
0x18000b12c  jnz     short loc_18000B13B
0x18000b12e  mov     [rdi], r14
0x18000b131  mov     eax, 492h
0x18000b136  jmp     loc_18000B26F
0x18000b13b  shr     rcx, 4
0x18000b13f  mov     eax, 10h
0x18000b144  mul     rcx
0x18000b147  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b14e  cmovb   rax, rcx
0x18000b152  mov     rcx, rax; unsigned __int64
0x18000b155  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b15a  mov     [rdi], rax
0x18000b15d  test    rax, rax
0x18000b160  jnz     short loc_18000B16C
0x18000b162  mov     eax, 8007000Eh
0x18000b167  jmp     loc_18000B26F
0x18000b16c  mov     ecx, [rbp+BytesReturned]
0x18000b16f  test    ecx, ecx
0x18000b171  jz      short loc_18000B1AB
0x18000b173  lea     r8, [rbp+var_40]
0x18000b177  mov     r9d, 18h; nInBufferSize
0x18000b17d  mov     [rsp+80h+lpBytesReturned], r8; lpNumberOfBytesTransferred
0x18000b182  mov     edx, 2F0003h; dwIoControlCode
0x18000b187  mov     [rsp+80h+nOutBufferSize], ecx; DWORD
0x18000b18b  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000b18f  mov     rcx, rbx; hFile
0x18000b192  mov     [rsp+80h+lpOutBuffer], rax; LPVOID
0x18000b197  call    KsSynchronousDeviceControl
0x18000b19c  test    eax, eax
0x18000b19e  jns     short loc_18000B1A8
0x18000b1a0  mov     ecx, r14d
0x18000b1a3  mov     [rbp+BytesReturned], ecx
0x18000b1a6  jmp     short loc_18000B1AB
0x18000b1a8  mov     ecx, [rbp+BytesReturned]
0x18000b1ab  mov     r8d, [rbp+NumberOfBytesTransferred]
0x18000b1af  test    r8d, r8d
0x18000b1b2  jz      short loc_18000B1FB
0x18000b1b4  mov     eax, ecx
0x18000b1b6  mov     r9d, 18h; nInBufferSize
0x18000b1bc  lea     rcx, [rbp+var_40]
0x18000b1c0  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000b1c4  add     rax, [rdi]
0x18000b1c7  mov     edx, 2F000Fh; dwIoControlCode
0x18000b1cc  mov     [rsp+80h+lpBytesReturned], rcx; lpNumberOfBytesTransferred
0x18000b1d1  mov     rcx, rbx; hFile
0x18000b1d4  mov     [rsp+80h+nOutBufferSize], r8d; DWORD
0x18000b1d9  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000b1dd  mov     [rsp+80h+lpOutBuffer], rax; LPVOID
0x18000b1e2  call    KsSynchronousDeviceControl
0x18000b1e7  mov     ecx, [rbp+BytesReturned]
0x18000b1ea  test    eax, eax
0x18000b1ec  jns     short loc_18000B1F7
0x18000b1ee  mov     r8d, r14d
0x18000b1f1  mov     [rbp+NumberOfBytesTransferred], r14d
0x18000b1f5  jmp     short loc_18000B1FB
0x18000b1f7  mov     r8d, [rbp+NumberOfBytesTransferred]
0x18000b1fb  mov     r10d, [rbp+arg_18]
0x18000b1ff  test    r10d, r10d
0x18000b202  jz      short loc_18000B250
0x18000b204  add     ecx, r8d
0x18000b207  lea     rax, [rbp+var_40]
0x18000b20b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000b20f  mov     [rsp+80h+lpBytesReturned], rax; lpNumberOfBytesTransferred
0x18000b214  add     rcx, [rdi]
0x18000b217  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000b21b  mov     [rsp+80h+nOutBufferSize], r10d; DWORD
0x18000b220  mov     r9d, 18h; nInBufferSize
0x18000b226  mov     [rsp+80h+lpOutBuffer], rcx; LPVOID
0x18000b22b  mov     edx, 2F0007h; dwIoControlCode
0x18000b230  mov     rcx, rbx; hFile
0x18000b233  call    KsSynchronousDeviceControl
0x18000b238  mov     ecx, [rbp+BytesReturned]
0x18000b23b  mov     r8d, [rbp+NumberOfBytesTransferred]
0x18000b23f  test    eax, eax
0x18000b241  jns     short loc_18000B24C
0x18000b243  mov     r10d, r14d
0x18000b246  mov     [rbp+arg_18], r14d
0x18000b24a  jmp     short loc_18000B250
0x18000b24c  mov     r10d, [rbp+arg_18]
0x18000b250  lea     eax, [r10+r8]
0x18000b254  add     ecx, eax
0x18000b256  mov     [rbp+BytesReturned], ecx
0x18000b259  jnz     short loc_18000B268
0x18000b25b  mov     rcx, [rdi]; void *
0x18000b25e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b263  jmp     loc_18000B12E
0x18000b268  shr     ecx, 4
0x18000b26b  mov     [rsi], ecx
0x18000b26d  xor     eax, eax
0x18000b26f  mov     rbx, [rsp+80h+arg_8]
0x18000b277  add     rsp, 80h
0x18000b27e  pop     r15
0x18000b280  pop     r14
0x18000b282  pop     rdi
0x18000b283  pop     rsi
0x18000b284  pop     rbp
0x18000b285  retn
```
