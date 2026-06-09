# W3_CGI_HANDLER::CGIReadRequestEntity(int *)

- ea: `0x180002fb0`
- end: `0x180003080`
- name: `?CGIReadRequestEntity@W3_CGI_HANDLER@@AEAAJPEAH@Z`
- size: `208`
- prototype: `__int64 __fastcall(W3_CGI_HANDLER *__hidden this, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002d28`

## callees

- `0x180002fb0`
- `0x180008010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000305b`
- `iisutil!PuDbgPrint` at `0x18000305b`

## string_xrefs

- `0x180003042`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x180003049`: `CGIReadEntity Error reading gateway data, hr %x\n`
- `0x180003037`: `W3_CGI_HANDLER::CGIReadRequestEntity`

## pseudocode

```c
__int64 __fastcall W3_CGI_HANDLER::CGIReadRequestEntity(W3_CGI_HANDLER *this, int *a2)
{
  __int64 v4; // rax
  __int64 v5; // r8
  int v6; // eax
  unsigned int v7; // ebx

  if ( !*((_DWORD *)this + 15) )
    goto LABEL_10;
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6));
  v5 = 0x2000;
  if ( *((_DWORD *)this + 15) < 0x2000u )
    v5 = *((unsigned int *)this + 15);
  v6 = (*(__int64 (__fastcall **)(__int64, char *, __int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v4 + 128LL))(
         v4,
         (char *)this + 64,
         v5,
         1,
         0,
         0);
  v7 = v6;
  if ( v6 >= 0 )
  {
    *a2 = 1;
    return 0;
  }
  if ( v6 == -2147024858 )
  {
LABEL_10:
    *a2 = 0;
    return 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
      1415,
      "W3_CGI_HANDLER::CGIReadRequestEntity",
      "CGIReadEntity Error reading gateway data, hr %x\n",
      v6);
  return v7;
}

```

## disassembly

```asm
0x180002fb0  mov     [rsp+arg_0], rbx
0x180002fb5  push    rdi
0x180002fb6  sub     rsp, 40h
0x180002fba  cmp     dword ptr [rcx+3Ch], 0
0x180002fbe  mov     rdi, rdx
0x180002fc1  mov     rbx, rcx
0x180002fc4  jz      loc_18000306D
0x180002fca  mov     rcx, [rcx+30h]
0x180002fce  mov     rax, [rcx]
0x180002fd1  mov     rax, [rax+18h]
0x180002fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fda  mov     r8d, 2000h
0x180002fe0  mov     [rsp+48h+var_20], 0
0x180002fe9  cmp     [rbx+3Ch], r8d
0x180002fed  lea     rdx, [rbx+40h]
0x180002ff1  mov     r10, rax
0x180002ff4  mov     [rsp+48h+var_28], 0
0x180002ffd  mov     rcx, [rax]
0x180003000  mov     r9d, 1
0x180003006  cmovb   r8d, [rbx+3Ch]
0x18000300b  mov     rax, [rcx+80h]
0x180003012  mov     rcx, r10
0x180003015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000301a  mov     ebx, eax
0x18000301c  test    eax, eax
0x18000301e  jns     short loc_180003065
0x180003020  cmp     eax, 80070026h
0x180003025  jz      short loc_18000306D
0x180003027  test    cs:g_dwDebugFlags, 3
0x18000302e  jz      short loc_180003061
0x180003030  mov     rcx, cs:g_pDebug
0x180003037  lea     r9, aW3CgiHandlerCg_2; "W3_CGI_HANDLER::CGIReadRequestEntity"
0x18000303e  mov     dword ptr [rsp+48h+var_20], eax
0x180003042  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003049  lea     rax, aCgireadentityE; "CGIReadEntity Error reading gateway dat"...
0x180003050  mov     r8d, 587h
0x180003056  mov     [rsp+48h+var_28], rax
0x18000305b  call    cs:__imp_PuDbgPrint
0x180003061  mov     eax, ebx
0x180003063  jmp     short loc_180003075
0x180003065  mov     dword ptr [rdi], 1
0x18000306b  jmp     short loc_180003073
0x18000306d  mov     dword ptr [rdi], 0
0x180003073  xor     eax, eax
0x180003075  mov     rbx, [rsp+48h+arg_0]
0x18000307a  add     rsp, 40h
0x18000307e  pop     rdi
0x18000307f  retn
```
