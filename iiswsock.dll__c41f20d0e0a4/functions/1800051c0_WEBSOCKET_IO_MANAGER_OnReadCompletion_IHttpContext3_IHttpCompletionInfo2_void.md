# WEBSOCKET_IO_MANAGER::OnReadCompletion(IHttpContext3 *,IHttpCompletionInfo2 *,void *)

- ea: `0x1800051c0`
- end: `0x1800052c6`
- name: `?OnReadCompletion@WEBSOCKET_IO_MANAGER@@CA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext3@@PEAVIHttpCompletionInfo2@@PEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x1800051c0`
- `0x180009010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180005215`
- `iisutil!PuDbgPrint` at `0x180005271`
- `iisutil!PuDbgPrint` at `0x180005215`
- `iisutil!PuDbgPrint` at `0x180005271`

## string_xrefs

- `0x1800051fc`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wsio.cxx`
- `0x180005258`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wsio.cxx`
- `0x1800051f1`: `WEBSOCKET_IO_MANAGER::OnReadCompletion`
- `0x18000524d`: `WEBSOCKET_IO_MANAGER::OnReadCompletion`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_IO_MANAGER::OnReadCompletion(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v4; // rbx
  int v6; // eax
  int v7; // eax
  void (__fastcall *v8)(__int64, _QWORD, _QWORD); // rdi
  unsigned int v9; // ebx
  unsigned int v10; // eax

  v4 = *a3;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v6 = (**(__int64 (__fastcall ***)(__int64))a2)(a2);
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wsio.cxx",
      439,
      "WEBSOCKET_IO_MANAGER::OnReadCompletion",
      "Bytes = %08x\n",
      v6);
  }
  if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2) < 0 && (g_dwDebugFlags & 0xF) != 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wsio.cxx",
      445,
      "WEBSOCKET_IO_MANAGER::OnReadCompletion",
      "ERROR = %08x\n",
      v7);
  }
  _InterlockedDecrement((volatile signed __int32 *)(v4 + 16));
  v8 = (void (__fastcall *)(__int64, _QWORD, _QWORD))a3[1];
  v9 = (**(__int64 (__fastcall ***)(__int64))a2)(a2);
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  v8(a3[2], v10, v9);
  operator delete(a3);
  return 1;
}

```

## disassembly

```asm
0x1800051c0  push    rbx
0x1800051c2  push    rsi
0x1800051c3  push    rdi
0x1800051c4  push    r14
0x1800051c6  sub     rsp, 38h
0x1800051ca  test    byte ptr cs:g_dwDebugFlags, 3
0x1800051d1  mov     r14, r8
0x1800051d4  mov     rbx, [r8]
0x1800051d7  mov     rsi, rdx
0x1800051da  jz      short loc_18000521B
0x1800051dc  mov     rax, [rdx]
0x1800051df  mov     rcx, rdx
0x1800051e2  mov     rax, [rax]
0x1800051e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051ea  mov     rcx, cs:g_pDebug
0x1800051f1  lea     r9, aWebsocketIoMan; "WEBSOCKET_IO_MANAGER::OnReadCompletion"
0x1800051f8  mov     [rsp+58h+var_30], eax
0x1800051fc  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005203  lea     rax, aBytes08x; "Bytes = %08x\n"
0x18000520a  mov     r8d, 1B7h
0x180005210  mov     [rsp+58h+var_38], rax
0x180005215  call    cs:__imp_PuDbgPrint
0x18000521b  mov     rax, [rsi]
0x18000521e  mov     rcx, rsi
0x180005221  mov     rax, [rax+8]
0x180005225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000522a  test    eax, eax
0x18000522c  jns     short loc_180005277
0x18000522e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005235  jz      short loc_180005277
0x180005237  mov     rax, [rsi]
0x18000523a  mov     rcx, rsi
0x18000523d  mov     rax, [rax+8]
0x180005241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005246  mov     rcx, cs:g_pDebug
0x18000524d  lea     r9, aWebsocketIoMan; "WEBSOCKET_IO_MANAGER::OnReadCompletion"
0x180005254  mov     [rsp+58h+var_30], eax
0x180005258  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000525f  lea     rax, aError08x; "ERROR = %08x\n"
0x180005266  mov     r8d, 1BDh
0x18000526c  mov     [rsp+58h+var_38], rax
0x180005271  call    cs:__imp_PuDbgPrint
0x180005277  lock dec dword ptr [rbx+10h]
0x18000527b  mov     rcx, rsi
0x18000527e  mov     rax, [rsi]
0x180005281  mov     rdi, [r14+8]
0x180005285  mov     rax, [rax]
0x180005288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528d  mov     rcx, [rsi]
0x180005290  mov     ebx, eax
0x180005292  mov     rax, [rcx+8]
0x180005296  mov     rcx, rsi
0x180005299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000529e  mov     rcx, [r14+10h]
0x1800052a2  mov     edx, eax
0x1800052a4  mov     rax, rdi
0x1800052a7  mov     r8d, ebx
0x1800052aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052af  mov     rcx, r14; Block
0x1800052b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800052b7  mov     eax, 1
0x1800052bc  add     rsp, 38h
0x1800052c0  pop     r14
0x1800052c2  pop     rdi
0x1800052c3  pop     rsi
0x1800052c4  pop     rbx
0x1800052c5  retn
```
