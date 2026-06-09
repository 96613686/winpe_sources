# KsSynchronousDeviceControl

- ea: `0x18000bde0`
- end: `0x18000bf80`
- name: `KsSynchronousDeviceControl`
- size: `416`
- prototype: `signed int __fastcall(char *hFile, DWORD dwIoControlCode, LPVOID lpInBuffer, DWORD nInBufferSize, LPVOID lpOutBuffer, DWORD nOutBufferSize, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `79`
- callee_count: `1`
- tags: ``

## callers

- `0x1800043d0`
- `0x180004f70`
- `0x180005850`
- `0x1800063a0`
- `0x180009dd0`
- `0x18000a158`
- `0x18000a260`
- `0x18000a480`
- `0x18000a694`
- `0x18000a72c`
- `0x18000ae28`
- `0x18000b6fc`
- `0x18000c6f0`
- `0x18000cc78`
- `0x18000d430`
- `0x18000eba0`
- `0x1800186d0`
- `0x1800196f0`
- `0x18001bb40`
- `0x18001bfd8`
- `0x18001ee00`
- `0x180020c20`
- `0x180020d70`
- `0x180021278`
- `0x180021340`
- `0x180021c7c`
- `0x180021fa0`
- `0x1800221a0`
- `0x180022670`
- `0x180022820`
- `0x180022b10`
- `0x180022da0`
- `0x180022ec4`
- `0x180023440`
- `0x1800234b0`
- `0x180023650`
- `0x1800236b0`
- `0x180024900`
- `0x180024b80`
- `0x180024fc0`
- `0x180025090`
- `0x1800269c0`
- `0x180027140`
- `0x180027720`
- `0x180027920`
- `0x180027ac0`
- `0x180027f10`
- `0x18002ae50`
- `0x18002b7e0`
- `0x18002b8e0`

## callees

- `0x18000bde0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000be88`
- `KERNEL32!GetLastError` at `0x18000bef1`
- `KERNEL32!GetLastError` at `0x18000bf34`
- `KERNEL32!GetLastError` at `0x18000be88`
- `KERNEL32!GetLastError` at `0x18000bef1`
- `KERNEL32!GetLastError` at `0x18000bf34`
- `KERNEL32!CreateEventW` at `0x18000be1c`
- `KERNEL32!CreateEventW` at `0x18000be1c`
- `KERNEL32!CloseHandle` at `0x18000beb0`
- `KERNEL32!CloseHandle` at `0x18000beb0`
- `KERNEL32!GetOverlappedResult` at `0x18000bf24`
- `KERNEL32!GetOverlappedResult` at `0x18000bf24`
- `KERNEL32!DeviceIoControl` at `0x18000be78`
- `KERNEL32!DeviceIoControl` at `0x18000be78`

## pseudocode

```c
signed int __fastcall KsSynchronousDeviceControl(
        char *hFile,
        DWORD dwIoControlCode,
        LPVOID lpInBuffer,
        DWORD nInBufferSize,
        LPVOID lpOutBuffer,
        DWORD nOutBufferSize,
        LPDWORD lpNumberOfBytesTransferred)
{
  signed int LastError; // eax
  unsigned int v12; // ebx
  signed int result; // eax
  signed int v14; // eax
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-48h] BYREF

  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return -2147024890;
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(
           hFile,
           dwIoControlCode,
           lpInBuffer,
           nInBufferSize,
           lpOutBuffer,
           nOutBufferSize,
           lpNumberOfBytesTransferred,
           &Overlapped) )
    {
      switch ( Overlapped.Internal )
      {
        case 0x101uLL:
          v12 = -2147024875;
          goto LABEL_7;
        case 0x105uLL:
          v12 = -2147024662;
          goto LABEL_7;
        case 0x107uLL:
          v12 = -2147023595;
          goto LABEL_7;
      }
    }
    else
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( v12 != -2147023899 )
        goto LABEL_7;
      if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 1) )
      {
        v14 = GetLastError();
        v12 = v14;
        if ( v14 > 0 )
          v12 = (unsigned __int16)v14 | 0x80070000;
        goto LABEL_7;
      }
    }
    v12 = 0;
LABEL_7:
    CloseHandle(Overlapped.hEvent);
    return v12;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000bde0  push    rbx
0x18000bde2  push    rbp
0x18000bde3  push    rsi
0x18000bde4  push    rdi
0x18000bde5  sub     rsp, 68h
0x18000bde9  lea     rax, [rcx-1]
0x18000bded  mov     ebx, r9d
0x18000bdf0  mov     rsi, r8
0x18000bdf3  mov     ebp, edx
0x18000bdf5  mov     rdi, rcx
0x18000bdf8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bdfc  ja      loc_18000BF76
0x18000be02  xorps   xmm0, xmm0
0x18000be05  xor     r9d, r9d; lpName
0x18000be08  xor     r8d, r8d; bInitialState
0x18000be0b  mov     edx, 1; bManualReset
0x18000be10  xor     ecx, ecx; lpEventAttributes
0x18000be12  movups  xmmword ptr [rsp+88h+Overlapped.Internal], xmm0
0x18000be17  movups  xmmword ptr [rsp+88h+Overlapped.10h], xmm0
0x18000be1c  call    cs:__imp_CreateEventW
0x18000be23  nop     dword ptr [rax+rax+00h]
0x18000be28  mov     [rsp+88h+Overlapped.hEvent], rax
0x18000be2d  test    rax, rax
0x18000be30  jz      loc_18000BEF1
0x18000be36  lea     rax, [rsp+88h+Overlapped]
0x18000be3b  mov     [rsp+88h+arg_0], r14
0x18000be43  mov     r14, [rsp+88h+lpNumberOfBytesTransferred]
0x18000be4b  mov     r9d, ebx; nInBufferSize
0x18000be4e  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x18000be53  mov     r8, rsi; lpInBuffer
0x18000be56  mov     eax, [rsp+88h+arg_28]
0x18000be5d  mov     edx, ebp; dwIoControlCode
0x18000be5f  mov     [rsp+88h+lpBytesReturned], r14; lpBytesReturned
0x18000be64  mov     rcx, rdi; hDevice
0x18000be67  mov     [rsp+88h+nOutBufferSize], eax; nOutBufferSize
0x18000be6b  mov     rax, [rsp+88h+arg_20]
0x18000be73  mov     [rsp+88h+lpOutBuffer], rax; lpOutBuffer
0x18000be78  call    cs:__imp_DeviceIoControl
0x18000be7f  nop     dword ptr [rax+rax+00h]
0x18000be84  test    eax, eax
0x18000be86  jnz     short loc_18000BED0
0x18000be88  call    cs:__imp_GetLastError
0x18000be8f  nop     dword ptr [rax+rax+00h]
0x18000be94  mov     ebx, eax
0x18000be96  test    eax, eax
0x18000be98  jle     short loc_18000BEA3
0x18000be9a  movzx   ebx, ax
0x18000be9d  or      ebx, 80070000h
0x18000bea3  cmp     ebx, 800703E5h
0x18000bea9  jz      short loc_18000BF13
0x18000beab  mov     rcx, [rsp+88h+Overlapped.hEvent]; hObject
0x18000beb0  call    cs:__imp_CloseHandle
0x18000beb7  nop     dword ptr [rax+rax+00h]
0x18000bebc  mov     r14, [rsp+88h+arg_0]
0x18000bec4  mov     eax, ebx
0x18000bec6  add     rsp, 68h
0x18000beca  pop     rdi
0x18000becb  pop     rsi
0x18000becc  pop     rbp
0x18000becd  pop     rbx
0x18000bece  retn
0x18000bed0  mov     rax, [rsp+88h+Overlapped.Internal]
0x18000bed5  sub     rax, 101h
0x18000bedb  jz      loc_18000BF6C
0x18000bee1  sub     rax, 4
0x18000bee5  jz      short loc_18000BF62
0x18000bee7  cmp     rax, 2
0x18000beeb  jz      short loc_18000BF58
0x18000beed  xor     ebx, ebx
0x18000beef  jmp     short loc_18000BEAB
0x18000bef1  call    cs:__imp_GetLastError
0x18000bef8  nop     dword ptr [rax+rax+00h]
0x18000befd  test    eax, eax
0x18000beff  jle     short loc_18000BEC6
0x18000bf01  movzx   eax, ax
0x18000bf04  or      eax, 80070000h
0x18000bf09  add     rsp, 68h
0x18000bf0d  pop     rdi
0x18000bf0e  pop     rsi
0x18000bf0f  pop     rbp
0x18000bf10  pop     rbx
0x18000bf11  retn
0x18000bf13  mov     r9d, 1; bWait
0x18000bf19  lea     rdx, [rsp+88h+Overlapped]; lpOverlapped
0x18000bf1e  mov     r8, r14; lpNumberOfBytesTransferred
0x18000bf21  mov     rcx, rdi; hFile
0x18000bf24  call    cs:__imp_GetOverlappedResult
0x18000bf2b  nop     dword ptr [rax+rax+00h]
0x18000bf30  test    eax, eax
0x18000bf32  jnz     short loc_18000BEED
0x18000bf34  call    cs:__imp_GetLastError
0x18000bf3b  nop     dword ptr [rax+rax+00h]
0x18000bf40  mov     ebx, eax
0x18000bf42  test    eax, eax
0x18000bf44  jle     loc_18000BEAB
0x18000bf4a  movzx   ebx, ax
0x18000bf4d  or      ebx, 80070000h
0x18000bf53  jmp     loc_18000BEAB
0x18000bf58  mov     ebx, 80070515h
0x18000bf5d  jmp     loc_18000BEAB
0x18000bf62  mov     ebx, 800700EAh
0x18000bf67  jmp     loc_18000BEAB
0x18000bf6c  mov     ebx, 80070015h
0x18000bf71  jmp     loc_18000BEAB
0x18000bf76  mov     eax, 80070006h
0x18000bf7b  jmp     loc_18000BEC6
```
