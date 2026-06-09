# SockCreateAsyncQueuePort

- ea: `0x18001e14c`
- end: `0x18001e1d6`
- name: `SockCreateAsyncQueuePort`
- size: `138`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002650`
- `0x1800028b8`
- `0x180019054`
- `0x180044380`

## callees

- `0x18001e14c`
- `0x18003ae8c`

## import_xrefs

- `ntdll!NtCreateIoCompletion` at `0x18001e16c`
- `ntdll!NtCreateIoCompletion` at `0x18001e16c`
- `ntdll!NtSetInformationObject` at `0x18001e19b`
- `ntdll!NtSetInformationObject` at `0x18001e19b`

## pseudocode

```c
__int64 SockCreateAsyncQueuePort()
{
  NTSTATUS IoCompletion; // eax
  unsigned int v1; // ebx
  __int16 ObjectInformation; // [rsp+30h] [rbp+8h] BYREF

  ObjectInformation = 0;
  IoCompletion = NtCreateIoCompletion(&SockAsyncQueuePort, 0x1F0003u, 0, 0xFFFFFFFF);
  v1 = IoCompletion;
  if ( IoCompletion < 0 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_d(1025, 10, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids, (unsigned int)IoCompletion);
  }
  else
  {
    ObjectInformation = 256;
    NtSetInformationObject(SockAsyncQueuePort, ObjectHandleFlagInformation, &ObjectInformation, 2u);
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x18001e14c  push    rbx
0x18001e14e  sub     rsp, 20h
0x18001e152  xor     eax, eax
0x18001e154  lea     rcx, SockAsyncQueuePort; IoCompletionHandle
0x18001e15b  or      r9d, 0FFFFFFFFh; NumberOfConcurrentThreads
0x18001e15f  mov     [rsp+28h+ObjectInformation], ax
0x18001e164  xor     r8d, r8d; ObjectAttributes
0x18001e167  mov     edx, 1F0003h; DesiredAccess
0x18001e16c  call    cs:__imp_NtCreateIoCompletion
0x18001e173  nop     dword ptr [rax+rax+00h]
0x18001e178  mov     ebx, eax
0x18001e17a  test    eax, eax
0x18001e17c  js      short loc_18001E1AB
0x18001e17e  mov     rcx, cs:SockAsyncQueuePort; ObjectHandle
0x18001e185  lea     r8, [rsp+28h+ObjectInformation]; ObjectInformation
0x18001e18a  mov     r9d, 2; Length
0x18001e190  mov     [rsp+28h+ObjectInformation], 100h
0x18001e197  lea     edx, [r9+2]; ObjectInformationClass
0x18001e19b  call    cs:__imp_NtSetInformationObject
0x18001e1a2  nop     dword ptr [rax+rax+00h]
0x18001e1a7  xor     ebx, ebx
0x18001e1a9  jmp     short loc_18001E1CD
0x18001e1ab  test    byte ptr cs:xmmword_180063D60, 2
0x18001e1b2  jz      short loc_18001E1CD
0x18001e1b4  mov     edx, 0Ah
0x18001e1b9  lea     r8, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids
0x18001e1c0  mov     ecx, 401h
0x18001e1c5  mov     r9d, eax
0x18001e1c8  call    WPP_SF_d
0x18001e1cd  mov     eax, ebx
0x18001e1cf  add     rsp, 20h
0x18001e1d3  pop     rbx
0x18001e1d4  retn
```
