# CreateAndAddToBeRunServiceStopJob

- ea: `0x18000fbec`
- end: `0x18000fc70`
- name: `CreateAndAddToBeRunServiceStopJob`
- size: `132`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c8b4`

## callees

- `0x180004180`
- `0x1800068f0`
- `0x18000fbec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000fc10`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000fc10`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fc47`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fc47`

## pseudocode

```c
__int64 CreateAndAddToBeRunServiceStopJob()
{
  HANDLE EventA; // rax
  unsigned int v1; // ebx
  _OWORD v3[2]; // [rsp+20h] [rbp-38h] BYREF
  HANDLE hHandle; // [rsp+40h] [rbp-18h]

  memset(v3, 0, sizeof(v3));
  EventA = CreateEventA(0, 0, 0, 0);
  hHandle = EventA;
  if ( EventA )
  {
    v1 = 1;
    if ( (unsigned int)AddToBeRunJobEx((FILETIME)v3, 5, 0, 1) )
    {
      WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
      EventA = hHandle;
      goto LABEL_6;
    }
    EventA = hHandle;
  }
  v1 = 0;
LABEL_6:
  if ( EventA )
    I_UrlCacheCloseHandle(EventA);
  return v1;
}

```

## disassembly

```asm
0x18000fbec  push    rbx
0x18000fbee  sub     rsp, 50h
0x18000fbf2  xorps   xmm0, xmm0
0x18000fbf5  xor     eax, eax
0x18000fbf7  xor     r9d, r9d; lpName
0x18000fbfa  mov     [rsp+58h+hHandle], rax
0x18000fbff  xor     r8d, r8d; bInitialState
0x18000fc02  xor     edx, edx; bManualReset
0x18000fc04  xor     ecx, ecx; lpEventAttributes
0x18000fc06  movups  [rsp+58h+var_38], xmm0
0x18000fc0b  movups  [rsp+58h+var_28], xmm0
0x18000fc10  call    cs:__imp_CreateEventA
0x18000fc16  mov     [rsp+58h+hHandle], rax
0x18000fc1b  test    rax, rax
0x18000fc1e  jz      short loc_18000FC59
0x18000fc20  mov     ebx, 1
0x18000fc25  lea     rcx, [rsp+58h+var_38]
0x18000fc2a  mov     r9d, ebx
0x18000fc2d  xor     r8d, r8d
0x18000fc30  lea     edx, [rbx+4]
0x18000fc33  call    AddToBeRunJobEx
0x18000fc38  test    eax, eax
0x18000fc3a  jz      short loc_18000FC54
0x18000fc3c  mov     rcx, [rsp+58h+hHandle]; hHandle
0x18000fc41  xor     r8d, r8d; bAlertable
0x18000fc44  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000fc47  call    cs:__imp_WaitForSingleObjectEx
0x18000fc4d  mov     rax, [rsp+58h+hHandle]
0x18000fc52  jmp     short loc_18000FC5B
0x18000fc54  mov     rax, [rsp+58h+hHandle]
0x18000fc59  xor     ebx, ebx
0x18000fc5b  test    rax, rax
0x18000fc5e  jz      short loc_18000FC68
0x18000fc60  mov     rcx, rax; hObject
0x18000fc63  call    I_UrlCacheCloseHandle
0x18000fc68  mov     eax, ebx
0x18000fc6a  add     rsp, 50h
0x18000fc6e  pop     rbx
0x18000fc6f  retn
```
