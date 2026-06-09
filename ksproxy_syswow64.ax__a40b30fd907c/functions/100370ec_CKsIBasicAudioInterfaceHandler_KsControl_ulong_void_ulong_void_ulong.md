# CKsIBasicAudioInterfaceHandler::KsControl(ulong,void *,ulong,void *,ulong)

- ea: `0x100370ec`
- end: `0x10037179`
- name: `?KsControl@CKsIBasicAudioInterfaceHandler@@AAE_NKPAXK0K@Z`
- size: `141`
- prototype: `bool __thiscall(CKsIBasicAudioInterfaceHandler *__hidden this, unsigned int, void *lpInBuffer, unsigned int, void *lpOutBuffer, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x10037030`
- `0x10037180`
- `0x10037210`

## callees

- `0x100370ec`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10037146`
- `KERNEL32!GetLastError` at `0x10037146`
- `KERNEL32!CreateEventW` at `0x1003710e`
- `KERNEL32!CreateEventW` at `0x1003710e`
- `KERNEL32!CloseHandle` at `0x10037167`
- `KERNEL32!CloseHandle` at `0x10037167`
- `KERNEL32!WaitForSingleObject` at `0x10037158`
- `KERNEL32!WaitForSingleObject` at `0x10037158`
- `KERNEL32!DeviceIoControl` at `0x10037137`
- `KERNEL32!DeviceIoControl` at `0x10037137`

## pseudocode

```c
bool __thiscall CKsIBasicAudioInterfaceHandler::KsControl(
        CKsIBasicAudioInterfaceHandler *this,
        unsigned int a2,
        void *lpInBuffer,
        unsigned int a4,
        void *lpOutBuffer,
        unsigned int a6)
{
  BOOL v7; // eax
  bool v8; // bl
  struct _OVERLAPPED Overlapped; // [esp+4h] [ebp-18h] BYREF
  DWORD BytesReturned; // [esp+18h] [ebp-4h] BYREF

  if ( !this->m_hKsObject )
    return 0;
  memset(&Overlapped, 0, 16);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( !Overlapped.hEvent )
    return 0;
  v7 = DeviceIoControl(this->m_hKsObject, 0x2F0003u, lpInBuffer, 0x18u, lpOutBuffer, 8u, &BytesReturned, &Overlapped);
  v8 = v7;
  if ( !v7 )
  {
    if ( GetLastError() == 997 )
    {
      WaitForSingleObject(Overlapped.hEvent, 0xFFFFFFFF);
      v8 = 1;
    }
    else
    {
      v8 = 0;
    }
  }
  CloseHandle(Overlapped.hEvent);
  return v8;
}

```

## disassembly

```asm
0x100370ec  mov     edi, edi
0x100370ee  push    ebp
0x100370ef  mov     ebp, esp
0x100370f1  sub     esp, 18h
0x100370f4  push    esi
0x100370f5  mov     esi, ecx
0x100370f7  xor     ecx, ecx
0x100370f9  cmp     [esi+20h], ecx
0x100370fc  jz      short loc_10037172
0x100370fe  push    edi
0x100370ff  xor     eax, eax
0x10037101  lea     edi, [ebp+Overlapped]
0x10037104  stosd
0x10037105  push    ecx; lpName
0x10037106  push    ecx; bInitialState
0x10037107  push    1; bManualReset
0x10037109  stosd
0x1003710a  push    ecx; lpEventAttributes
0x1003710b  stosd
0x1003710c  stosd
0x1003710d  stosd
0x1003710e  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10037114  mov     [ebp+Overlapped.hEvent], eax
0x10037117  pop     edi
0x10037118  test    eax, eax
0x1003711a  jz      short loc_10037172
0x1003711c  push    ebx
0x1003711d  lea     eax, [ebp+Overlapped]
0x10037120  push    eax; lpOverlapped
0x10037121  lea     eax, [ebp+BytesReturned]
0x10037124  push    eax; lpBytesReturned
0x10037125  push    8; nOutBufferSize
0x10037127  push    [ebp+lpOutBuffer]; lpOutBuffer
0x1003712a  push    18h; nInBufferSize
0x1003712c  push    [ebp+lpInBuffer]; lpInBuffer
0x1003712f  push    2F0003h; dwIoControlCode
0x10037134  push    dword ptr [esi+20h]; hDevice
0x10037137  call    ds:__imp__DeviceIoControl@32; DeviceIoControl(x,x,x,x,x,x,x,x)
0x1003713d  test    eax, eax
0x1003713f  setnz   bl
0x10037142  test    eax, eax
0x10037144  jnz     short loc_10037164
0x10037146  call    ds:__imp__GetLastError@0; GetLastError()
0x1003714c  cmp     eax, 3E5h
0x10037151  jnz     short loc_10037162
0x10037153  push    0FFFFFFFFh; dwMilliseconds
0x10037155  push    [ebp+Overlapped.hEvent]; hHandle
0x10037158  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x1003715e  mov     bl, 1
0x10037160  jmp     short loc_10037164
0x10037162  xor     bl, bl
0x10037164  push    [ebp+Overlapped.hEvent]; hObject
0x10037167  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1003716d  mov     al, bl
0x1003716f  pop     ebx
0x10037170  jmp     short loc_10037174
0x10037172  xor     al, al
0x10037174  pop     esi
0x10037175  leave
0x10037176  retn    14h
```
