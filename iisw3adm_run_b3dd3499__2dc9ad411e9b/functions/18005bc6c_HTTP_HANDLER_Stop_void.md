# HTTP_HANDLER::Stop(void)

- ea: `0x18005bc6c`
- end: `0x18005bd12`
- name: `?Stop@HTTP_HANDLER@@QEAAXXZ`
- size: `166`
- prototype: `void __fastcall(HTTP_HANDLER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006798`
- `0x18005b188`

## callees

- `0x18005bc6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bcbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bcbe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18005bc8e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18005bc8e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18005bc98`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18005bc98`
- `HTTPAPI!HttpCloseUrlGroup` at `0x18005bcc7`
- `HTTPAPI!HttpCloseUrlGroup` at `0x18005bcc7`
- `HTTPAPI!HttpCloseRequestQueue` at `0x18005bcdd`
- `HTTPAPI!HttpCloseRequestQueue` at `0x18005bcfe`
- `HTTPAPI!HttpCloseRequestQueue` at `0x18005bcdd`
- `HTTPAPI!HttpCloseRequestQueue` at `0x18005bcfe`
- `HTTPAPI!HttpRemoveUrlFromUrlGroup` at `0x18005bcb4`
- `HTTPAPI!HttpRemoveUrlFromUrlGroup` at `0x18005bcb4`
- `HTTPAPI!HttpShutdownRequestQueue` at `0x18005bcf4`
- `HTTPAPI!HttpShutdownRequestQueue` at `0x18005bcf4`

## pseudocode

```c
void __fastcall HTTP_HANDLER::Stop(HTTP_HANDLER *this)
{
  struct _TP_IO *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  _InterlockedExchange((volatile __int32 *)this + 43, 1);
  v2 = (struct _TP_IO *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    WaitForThreadpoolIoCallbacks(v2, 1);
    CloseThreadpoolIo(*((PTP_IO *)this + 3));
    *((_QWORD *)this + 3) = 0;
  }
  if ( *(_QWORD *)this )
  {
    if ( HttpRemoveUrlFromUrlGroup(*(_QWORD *)this, 0, 1u) )
      GetLastError();
    HttpCloseUrlGroup(*(_QWORD *)this);
    *(_QWORD *)this = 0;
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    HttpCloseRequestQueue(v3);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    HttpShutdownRequestQueue(v4);
    HttpCloseRequestQueue(*((HANDLE *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18005bc6c  push    rbx
0x18005bc6e  sub     rsp, 20h
0x18005bc72  mov     eax, 1
0x18005bc77  mov     rbx, rcx
0x18005bc7a  xchg    eax, [rcx+0ACh]
0x18005bc80  mov     rcx, [rcx+18h]; pio
0x18005bc84  test    rcx, rcx
0x18005bc87  jz      short loc_18005BCA6
0x18005bc89  mov     edx, 1; fCancelPendingCallbacks
0x18005bc8e  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18005bc94  mov     rcx, [rbx+18h]; pio
0x18005bc98  call    cs:__imp_CloseThreadpoolIo
0x18005bc9e  mov     qword ptr [rbx+18h], 0
0x18005bca6  mov     rcx, [rbx]; UrlGroupId
0x18005bca9  test    rcx, rcx
0x18005bcac  jz      short loc_18005BCD4
0x18005bcae  xor     edx, edx; pFullyQualifiedUrl
0x18005bcb0  lea     r8d, [rdx+1]; Flags
0x18005bcb4  call    cs:__imp_HttpRemoveUrlFromUrlGroup
0x18005bcba  test    eax, eax
0x18005bcbc  jz      short loc_18005BCC4
0x18005bcbe  call    cs:__imp_GetLastError
0x18005bcc4  mov     rcx, [rbx]; UrlGroupId
0x18005bcc7  call    cs:__imp_HttpCloseUrlGroup
0x18005bccd  mov     qword ptr [rbx], 0
0x18005bcd4  mov     rcx, [rbx+10h]; RequestQueueHandle
0x18005bcd8  test    rcx, rcx
0x18005bcdb  jz      short loc_18005BCEB
0x18005bcdd  call    cs:__imp_HttpCloseRequestQueue
0x18005bce3  mov     qword ptr [rbx+10h], 0
0x18005bceb  mov     rcx, [rbx+8]; RequestQueueHandle
0x18005bcef  test    rcx, rcx
0x18005bcf2  jz      short loc_18005BD0C
0x18005bcf4  call    cs:__imp_HttpShutdownRequestQueue
0x18005bcfa  mov     rcx, [rbx+8]; RequestQueueHandle
0x18005bcfe  call    cs:__imp_HttpCloseRequestQueue
0x18005bd04  mov     qword ptr [rbx+8], 0
0x18005bd0c  add     rsp, 20h
0x18005bd10  pop     rbx
0x18005bd11  retn
```
