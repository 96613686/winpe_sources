# CxPlatTlsResetSchannel

- ea: `0x14003609c`
- end: `0x140036130`
- name: `CxPlatTlsResetSchannel`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140036cd0`

## callees

- `0x14003609c`
- `0x14003ce00`

## import_xrefs

- `ksecdd!SspiDeleteSecurityContextAsync` at `0x1400360e0`
- `ksecdd!SspiDeleteSecurityContextAsync` at `0x1400360e0`
- `ksecdd!SspiCreateAsyncContext` at `0x1400360c6`
- `ksecdd!SspiCreateAsyncContext` at `0x1400360c6`
- `ksecdd!SspiFreeAsyncContext` at `0x1400360f6`
- `ksecdd!SspiFreeAsyncContext` at `0x1400360f6`

## pseudocode

```c
void __fastcall CxPlatTlsResetSchannel(struct _SecHandle *a1)
{
  struct _SecHandle *v1; // rdi
  SspiAsyncContext *AsyncContext; // rax
  SspiAsyncContext *v4; // rsi

  v1 = a1 + 1;
  if ( a1[1].dwLower != -1 && a1[1].dwUpper != -1 )
  {
    AsyncContext = SspiCreateAsyncContext();
    v4 = AsyncContext;
    if ( AsyncContext )
    {
      SspiDeleteSecurityContextAsync(AsyncContext, v1);
      a1[1].dwUpper = -1;
      v1->dwLower = -1;
      SspiFreeAsyncContext(v4);
    }
    a1[1].dwUpper = -1;
    v1->dwLower = -1;
    memset(&a1[5], 0, 0x828u);
  }
}

```

## disassembly

```asm
0x14003609c  mov     [rsp+arg_0], rbx
0x1400360a1  mov     [rsp+arg_8], rbp
0x1400360a6  mov     [rsp+arg_10], rsi
0x1400360ab  push    rdi
0x1400360ac  sub     rsp, 20h
0x1400360b0  lea     rdi, [rcx+10h]
0x1400360b4  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400360b8  mov     rbx, rcx
0x1400360bb  cmp     [rdi], rbp
0x1400360be  jz      short loc_14003611A
0x1400360c0  cmp     [rcx+18h], rbp
0x1400360c4  jz      short loc_14003611A
0x1400360c6  call    cs:__imp_SspiCreateAsyncContext
0x1400360cd  nop     dword ptr [rax+rax+00h]
0x1400360d2  mov     rsi, rax
0x1400360d5  test    rax, rax
0x1400360d8  jz      short loc_140036102
0x1400360da  mov     rdx, rdi; phContext
0x1400360dd  mov     rcx, rax; AsyncContext
0x1400360e0  call    cs:__imp_SspiDeleteSecurityContextAsync
0x1400360e7  nop     dword ptr [rax+rax+00h]
0x1400360ec  mov     rcx, rsi; Handle
0x1400360ef  mov     [rbx+18h], rbp
0x1400360f3  mov     [rdi], rbp
0x1400360f6  call    cs:__imp_SspiFreeAsyncContext
0x1400360fd  nop     dword ptr [rax+rax+00h]
0x140036102  lea     rcx, [rbx+50h]; void *
0x140036106  mov     [rbx+18h], rbp
0x14003610a  xor     edx, edx; Val
0x14003610c  mov     [rdi], rbp
0x14003610f  mov     r8d, 828h; Size
0x140036115  call    memset
0x14003611a  mov     rbx, [rsp+28h+arg_0]
0x14003611f  mov     rbp, [rsp+28h+arg_8]
0x140036124  mov     rsi, [rsp+28h+arg_10]
0x140036129  add     rsp, 20h
0x14003612d  pop     rdi
0x14003612e  retn
```
