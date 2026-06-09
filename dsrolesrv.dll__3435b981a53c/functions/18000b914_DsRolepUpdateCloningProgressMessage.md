# DsRolepUpdateCloningProgressMessage

- ea: `0x18000b914`
- end: `0x18000ba64`
- name: `DsRolepUpdateCloningProgressMessage`
- size: `336`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003a80`
- `0x180003ff0`
- `0x18000b1c8`
- `0x180012460`

## callees

- `0x18000b914`
- `0x1800159a0`
- `0x180020dbc`
- `0x18002c050`

## import_xrefs

- `msvcrt!_itow_s` at `0x18000b975`
- `msvcrt!_itow_s` at `0x18000b975`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b948`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b948`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b9b4`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b9b4`
- `ntdll!NtSetEvent` at `0x18000b9ee`
- `ntdll!NtSetEvent` at `0x18000b9ee`
- `ntdll!RtlEnterCriticalSection` at `0x18000b936`
- `ntdll!RtlEnterCriticalSection` at `0x18000b936`

## string_xrefs

- `0x18000b9f6`: `vDCCloningUpdate`
- `0x18000b9fd`: `vDCCloningComplete`

## pseudocode

```c
__int64 DsRolepUpdateCloningProgressMessage()
{
  DWORD v0; // eax
  DWORD v1; // ecx
  DWORD v2; // ebx
  HANDLE v3; // rcx
  unsigned int v4; // ebx
  const wchar_t *v5; // r8
  wchar_t Buffer[72]; // [rsp+30h] [rbp-A8h] BYREF

  RtlEnterCriticalSection(&gcsUpdateMessage);
  if ( gpwszCloningProgressMessage )
  {
    LocalFree(gpwszCloningProgressMessage);
    gpwszCloningProgressMessage = 0;
  }
  if ( (unsigned int)gdwCloningProgress >= 0x64 )
  {
    v1 = 28733;
    if ( gdwCloningProgress != 100 )
      v1 = 28734;
    v0 = DsRolepFormatOperationString(v1, &gpwszCloningProgressMessage);
  }
  else
  {
    _itow_s(gdwCloningProgress, Buffer, 0x41u, 10);
    v0 = DsRolepFormatOperationString(0x703Cu, &gpwszCloningProgressMessage, Buffer);
  }
  v2 = v0;
  RtlLeaveCriticalSection(&gcsUpdateMessage);
  if ( v2 )
    DsRolepLogPrintRoutine(1, "vDC Cloning: Format cloning progress message failed with error: 0x%x (%lu)\n", v2, v2);
  v3 = (HANDLE)ghMessageUpdateEvent;
  if ( (unsigned int)gdwCloningProgress >= 0x64 )
    v3 = ghCloneCompleteEvent;
  v4 = NtSetEvent(v3, 0);
  v5 = L"vDCCloningUpdate";
  if ( v4 )
  {
    if ( (unsigned int)gdwCloningProgress >= 0x64 )
      v5 = L"vDCCloningComplete";
    DsRolepLogPrintRoutine(1, "vDC Cloning: Set %ws event failed with error: 0x%x (%lu)\n", v5, v4, v4);
  }
  else
  {
    if ( (unsigned int)gdwCloningProgress >= 0x64 )
      v5 = L"vDCCloningComplete";
    DsRolepLogPrintRoutine(4, "vDC Cloning: Set %ws event.\n", v5);
  }
  return v4;
}

```

## disassembly

```asm
0x18000b914  push    rbx
0x18000b916  sub     rsp, 0D0h
0x18000b91d  mov     rax, cs:__security_cookie
0x18000b924  xor     rax, rsp
0x18000b927  mov     [rsp+0D8h+var_18], rax
0x18000b92f  lea     rcx, gcsUpdateMessage; CriticalSection
0x18000b936  call    cs:__imp_RtlEnterCriticalSection
0x18000b93c  mov     rcx, cs:gpwszCloningProgressMessage; hMem
0x18000b943  test    rcx, rcx
0x18000b946  jz      short loc_18000B959
0x18000b948  call    cs:__imp_LocalFree
0x18000b94e  mov     cs:gpwszCloningProgressMessage, 0
0x18000b959  mov     eax, cs:gdwCloningProgress
0x18000b95f  cmp     eax, 64h ; 'd'
0x18000b962  jnb     short loc_18000B993
0x18000b964  mov     r9d, 0Ah; Radix
0x18000b96a  lea     rdx, [rsp+0D8h+Buffer]; Buffer
0x18000b96f  mov     ecx, eax; Value
0x18000b971  lea     r8d, [r9+37h]; BufferCount
0x18000b975  call    cs:__imp__itow_s
0x18000b97b  lea     r8, [rsp+0D8h+Buffer]
0x18000b980  mov     ecx, 703Ch; dwMessageId
0x18000b985  lea     rdx, gpwszCloningProgressMessage
0x18000b98c  call    DsRolepFormatOperationString
0x18000b991  jmp     short loc_18000B9AB
0x18000b993  lea     rdx, gpwszCloningProgressMessage
0x18000b99a  mov     ecx, 703Dh
0x18000b99f  jz      short loc_18000B9A6
0x18000b9a1  mov     ecx, 703Eh; dwMessageId
0x18000b9a6  call    DsRolepFormatOperationString
0x18000b9ab  lea     rcx, gcsUpdateMessage; CriticalSection
0x18000b9b2  mov     ebx, eax
0x18000b9b4  call    cs:__imp_RtlLeaveCriticalSection
0x18000b9ba  test    ebx, ebx
0x18000b9bc  jz      short loc_18000B9D5
0x18000b9be  mov     r9d, ebx
0x18000b9c1  lea     rdx, aVdcCloningForm; "vDC Cloning: Format cloning progress me"...
0x18000b9c8  mov     r8d, ebx
0x18000b9cb  mov     ecx, 1
0x18000b9d0  call    DsRolepLogPrintRoutine
0x18000b9d5  mov     rcx, cs:ghMessageUpdateEvent
0x18000b9dc  xor     edx, edx; PreviousState
0x18000b9de  cmp     cs:gdwCloningProgress, 64h ; 'd'
0x18000b9e5  jb      short loc_18000B9EE
0x18000b9e7  mov     rcx, cs:ghCloneCompleteEvent; EventHandle
0x18000b9ee  call    cs:__imp_NtSetEvent
0x18000b9f4  mov     ebx, eax
0x18000b9f6  lea     r8, aVdccloningupda; "vDCCloningUpdate"
0x18000b9fd  lea     rax, aVdccloningcomp; "vDCCloningComplete"
0x18000ba04  test    ebx, ebx
0x18000ba06  jz      short loc_18000BA2D
0x18000ba08  cmp     cs:gdwCloningProgress, 64h ; 'd'
0x18000ba0f  lea     rdx, aVdcCloningSetW; "vDC Cloning: Set %ws event failed with "...
0x18000ba16  mov     r9d, ebx
0x18000ba19  mov     [rsp+0D8h+var_B8], ebx
0x18000ba1d  cmovnb  r8, rax
0x18000ba21  mov     ecx, 1
0x18000ba26  call    DsRolepLogPrintRoutine
0x18000ba2b  jmp     short loc_18000BA49
0x18000ba2d  cmp     cs:gdwCloningProgress, 64h ; 'd'
0x18000ba34  lea     rdx, aVdcCloningSetW_0; "vDC Cloning: Set %ws event.\n"
0x18000ba3b  mov     ecx, 4
0x18000ba40  cmovnb  r8, rax
0x18000ba44  call    DsRolepLogPrintRoutine
0x18000ba49  mov     eax, ebx
0x18000ba4b  mov     rcx, [rsp+0D8h+var_18]
0x18000ba53  xor     rcx, rsp; StackCookie
0x18000ba56  call    __security_check_cookie
0x18000ba5b  add     rsp, 0D0h
0x18000ba62  pop     rbx
0x18000ba63  retn
```
