# CKsIBasicAudioInterfaceHandler::KsControl(ulong,void *,ulong,void *,ulong)

- ea: `0x1800423e4`
- end: `0x1800424e6`
- name: `?KsControl@CKsIBasicAudioInterfaceHandler@@AEAA_NKPEAXK0K@Z`
- size: `258`
- prototype: `char __fastcall(CKsIBasicAudioInterfaceHandler *this, __int64, void *, DWORD, void *lpOutBuffer)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180042560`
- `0x180042700`
- `0x180042810`

## callees

- `0x1800423e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180042493`
- `KERNEL32!GetLastError` at `0x180042493`
- `KERNEL32!CreateEventW` at `0x180042422`
- `KERNEL32!CreateEventW` at `0x180042422`
- `KERNEL32!CloseHandle` at `0x1800424c3`
- `KERNEL32!CloseHandle` at `0x1800424c3`
- `KERNEL32!WaitForSingleObject` at `0x1800424ae`
- `KERNEL32!WaitForSingleObject` at `0x1800424ae`
- `KERNEL32!DeviceIoControl` at `0x180042483`
- `KERNEL32!DeviceIoControl` at `0x180042483`

## pseudocode

```c
char __fastcall CKsIBasicAudioInterfaceHandler::KsControl(
        CKsIBasicAudioInterfaceHandler *this,
        __int64 a2,
        void *a3,
        DWORD a4,
        void *lpOutBuffer)
{
  char v7; // bl
  void *m_hKsObject; // rcx
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-28h] BYREF
  DWORD BytesReturned; // [rsp+88h] [rbp+20h] BYREF

  BytesReturned = a4;
  if ( !this->m_hKsObject )
    return 0;
  memset(&Overlapped, 0, 24);
  v7 = 1;
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( !Overlapped.hEvent )
    return 0;
  m_hKsObject = this->m_hKsObject;
  BytesReturned = 0;
  if ( !DeviceIoControl(m_hKsObject, 0x2F0003u, a3, 0x18u, lpOutBuffer, 8u, &BytesReturned, &Overlapped) )
  {
    if ( GetLastError() == 997 )
      WaitForSingleObject(Overlapped.hEvent, 0xFFFFFFFF);
    else
      v7 = 0;
  }
  CloseHandle(Overlapped.hEvent);
  return v7;
}

```

## disassembly

```asm
0x1800423e4  mov     rax, rsp
0x1800423e7  mov     [rax+8], rbx
0x1800423eb  mov     [rax+10h], rsi
0x1800423ef  mov     [rax+20h], r9d
0x1800423f3  push    rdi
0x1800423f4  sub     rsp, 60h
0x1800423f8  cmp     qword ptr [rcx+40h], 0
0x1800423fd  mov     rsi, r8
0x180042400  mov     rdi, rcx
0x180042403  jz      loc_1800424D3
0x180042409  xorps   xmm0, xmm0
0x18004240c  xor     r9d, r9d; lpName
0x18004240f  xor     r8d, r8d; bInitialState
0x180042412  xor     ecx, ecx; lpEventAttributes
0x180042414  movups  xmmword ptr [rax-28h], xmm0
0x180042418  lea     ebx, [r9+1]
0x18004241c  mov     edx, ebx; bManualReset
0x18004241e  movups  xmmword ptr [rax-18h], xmm0
0x180042422  call    cs:__imp_CreateEventW
0x180042429  nop     dword ptr [rax+rax+00h]
0x18004242e  mov     [rsp+68h+Overlapped.hEvent], rax
0x180042433  test    rax, rax
0x180042436  jz      loc_1800424D3
0x18004243c  mov     rcx, [rdi+40h]; hDevice
0x180042440  lea     rax, [rsp+68h+Overlapped]
0x180042445  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18004244a  lea     r9d, [rbx+17h]; nInBufferSize
0x18004244e  lea     rax, [rsp+68h+BytesReturned]
0x180042456  mov     [rsp+68h+BytesReturned], 0
0x180042461  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x180042466  mov     r8, rsi; lpInBuffer
0x180042469  mov     rax, [rsp+68h+arg_20]
0x180042471  mov     edx, 2F0003h; dwIoControlCode
0x180042476  mov     [rsp+68h+nOutBufferSize], 8; nOutBufferSize
0x18004247e  mov     [rsp+68h+lpOutBuffer], rax; lpOutBuffer
0x180042483  call    cs:__imp_DeviceIoControl
0x18004248a  nop     dword ptr [rax+rax+00h]
0x18004248f  test    eax, eax
0x180042491  jnz     short loc_1800424BE
0x180042493  call    cs:__imp_GetLastError
0x18004249a  nop     dword ptr [rax+rax+00h]
0x18004249f  cmp     eax, 3E5h
0x1800424a4  jnz     short loc_1800424BC
0x1800424a6  mov     rcx, [rsp+68h+Overlapped.hEvent]; hHandle
0x1800424ab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800424ae  call    cs:__imp_WaitForSingleObject
0x1800424b5  nop     dword ptr [rax+rax+00h]
0x1800424ba  jmp     short loc_1800424BE
0x1800424bc  xor     bl, bl
0x1800424be  mov     rcx, [rsp+68h+Overlapped.hEvent]; hObject
0x1800424c3  call    cs:__imp_CloseHandle
0x1800424ca  nop     dword ptr [rax+rax+00h]
0x1800424cf  mov     al, bl
0x1800424d1  jmp     short loc_1800424D5
0x1800424d3  xor     al, al
0x1800424d5  mov     rbx, [rsp+68h+arg_0]
0x1800424da  mov     rsi, [rsp+68h+arg_8]
0x1800424df  add     rsp, 60h
0x1800424e3  pop     rdi
0x1800424e4  retn
```
