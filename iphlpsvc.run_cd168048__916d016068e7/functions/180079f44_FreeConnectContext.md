# FreeConnectContext

- ea: `0x180079f44`
- end: `0x180079fe6`
- name: `FreeConnectContext`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180079f04`
- `0x18007a830`

## callees

- `0x18000d7b0`
- `0x180079f44`
- `0x18007a7d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180079f72`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180079f72`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x180079fda`
- `webio!__imp_WebCloseHttpRequest` at `0x180079f9f`
- `webio!__imp_WebCloseHttpRequest` at `0x180079f9f`
- `webio!__imp_WebCloseSession` at `0x180079f88`
- `webio!__imp_WebCloseSession` at `0x180079f88`
- `webio!__imp_WebDeleteUri` at `0x180079fb4`
- `webio!__imp_WebDeleteUri` at `0x180079fb4`

## pseudocode

```c
__int64 __fastcall FreeConnectContext(_QWORD *a1)
{
  struct _TP_WORK *v2; // rcx
  __int64 v3; // rdi
  __int64 v4; // rcx

  EventWrite0(0x40000000, L"ConnCtx: FreeConnContext context %p\n", a1);
  v2 = (struct _TP_WORK *)a1[4];
  v3 = a1[6];
  if ( v2 )
    CloseThreadpoolWork(v2);
  if ( *a1 )
    WebCloseSession(*a1, 0);
  v4 = a1[1];
  if ( v4 )
    WebCloseHttpRequest(v4, 0);
  if ( a1[2] )
    WebDeleteUri();
  if ( v3 )
    ProxyHelperDereferenceContextWrapper(v3);
  return ProxyHelperClientFreeMemory(a1);
}

```

## disassembly

```asm
0x180079f44  mov     [rsp+arg_0], rbx
0x180079f49  push    rdi
0x180079f4a  sub     rsp, 20h
0x180079f4e  mov     rbx, rcx
0x180079f51  lea     rdx, aConnctxFreecon; "ConnCtx: FreeConnContext context %p\n"
0x180079f58  mov     r8, rcx
0x180079f5b  mov     ecx, 40000000h
0x180079f60  call    EventWrite0
0x180079f65  mov     rcx, [rbx+20h]; pwk
0x180079f69  mov     rdi, [rbx+30h]
0x180079f6d  test    rcx, rcx
0x180079f70  jz      short loc_180079F7E
0x180079f72  call    cs:__imp_CloseThreadpoolWork
0x180079f79  nop     dword ptr [rax+rax+00h]
0x180079f7e  mov     rcx, [rbx]
0x180079f81  test    rcx, rcx
0x180079f84  jz      short loc_180079F94
0x180079f86  xor     edx, edx
0x180079f88  call    cs:__imp_WebCloseSession
0x180079f8f  nop     dword ptr [rax+rax+00h]
0x180079f94  mov     rcx, [rbx+8]
0x180079f98  test    rcx, rcx
0x180079f9b  jz      short loc_180079FAB
0x180079f9d  xor     edx, edx
0x180079f9f  call    cs:__imp_WebCloseHttpRequest
0x180079fa6  nop     dword ptr [rax+rax+00h]
0x180079fab  mov     rcx, [rbx+10h]
0x180079faf  test    rcx, rcx
0x180079fb2  jz      short loc_180079FC0
0x180079fb4  call    cs:__imp_WebDeleteUri
0x180079fbb  nop     dword ptr [rax+rax+00h]
0x180079fc0  test    rdi, rdi
0x180079fc3  jz      short loc_180079FCD
0x180079fc5  mov     rcx, rdi
0x180079fc8  call    ProxyHelperDereferenceContextWrapper
0x180079fcd  mov     rcx, rbx
0x180079fd0  mov     rbx, [rsp+28h+arg_0]
0x180079fd5  add     rsp, 20h
0x180079fd9  pop     rdi
0x180079fda  jmp     cs:__imp_ProxyHelperClientFreeMemory
```
