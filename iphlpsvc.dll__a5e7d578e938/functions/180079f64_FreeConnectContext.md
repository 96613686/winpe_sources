# FreeConnectContext

- ea: `0x180079f64`
- end: `0x18007a006`
- name: `FreeConnectContext`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180079f24`
- `0x18007a850`

## callees

- `0x18000d7c0`
- `0x180079f64`
- `0x18007a7f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180079f92`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180079f92`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x180079ffa`
- `webio!__imp_WebCloseHttpRequest` at `0x180079fbf`
- `webio!__imp_WebCloseHttpRequest` at `0x180079fbf`
- `webio!__imp_WebCloseSession` at `0x180079fa8`
- `webio!__imp_WebCloseSession` at `0x180079fa8`
- `webio!__imp_WebDeleteUri` at `0x180079fd4`
- `webio!__imp_WebDeleteUri` at `0x180079fd4`

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
0x180079f64  mov     [rsp+arg_0], rbx
0x180079f69  push    rdi
0x180079f6a  sub     rsp, 20h
0x180079f6e  mov     rbx, rcx
0x180079f71  lea     rdx, aConnctxFreecon; "ConnCtx: FreeConnContext context %p\n"
0x180079f78  mov     r8, rcx
0x180079f7b  mov     ecx, 40000000h
0x180079f80  call    EventWrite0
0x180079f85  mov     rcx, [rbx+20h]; pwk
0x180079f89  mov     rdi, [rbx+30h]
0x180079f8d  test    rcx, rcx
0x180079f90  jz      short loc_180079F9E
0x180079f92  call    cs:__imp_CloseThreadpoolWork
0x180079f99  nop     dword ptr [rax+rax+00h]
0x180079f9e  mov     rcx, [rbx]
0x180079fa1  test    rcx, rcx
0x180079fa4  jz      short loc_180079FB4
0x180079fa6  xor     edx, edx
0x180079fa8  call    cs:__imp_WebCloseSession
0x180079faf  nop     dword ptr [rax+rax+00h]
0x180079fb4  mov     rcx, [rbx+8]
0x180079fb8  test    rcx, rcx
0x180079fbb  jz      short loc_180079FCB
0x180079fbd  xor     edx, edx
0x180079fbf  call    cs:__imp_WebCloseHttpRequest
0x180079fc6  nop     dword ptr [rax+rax+00h]
0x180079fcb  mov     rcx, [rbx+10h]
0x180079fcf  test    rcx, rcx
0x180079fd2  jz      short loc_180079FE0
0x180079fd4  call    cs:__imp_WebDeleteUri
0x180079fdb  nop     dword ptr [rax+rax+00h]
0x180079fe0  test    rdi, rdi
0x180079fe3  jz      short loc_180079FED
0x180079fe5  mov     rcx, rdi
0x180079fe8  call    ProxyHelperDereferenceContextWrapper
0x180079fed  mov     rcx, rbx
0x180079ff0  mov     rbx, [rsp+28h+arg_0]
0x180079ff5  add     rsp, 20h
0x180079ff9  pop     rdi
0x180079ffa  jmp     cs:__imp_ProxyHelperClientFreeMemory
```
