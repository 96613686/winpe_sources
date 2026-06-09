# WEBSOCKET_IO_MANAGER::OnWriteCompletion(IHttpContext3 *,IHttpCompletionInfo2 *,void *)

- ea: `0x1800052d0`
- end: `0x18000538c`
- name: `?OnWriteCompletion@WEBSOCKET_IO_MANAGER@@CA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext3@@PEAVIHttpCompletionInfo2@@PEAX@Z`
- size: `188`
- prototype: `__int64 __fastcall(__int64, __int64, volatile signed __int32 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x1800050cc`
- `0x1800052d0`
- `0x180009010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180005325`
- `iisutil!PuDbgPrint` at `0x180005325`

## string_xrefs

- `0x18000530c`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wsio.cxx`
- `0x180005301`: `WEBSOCKET_IO_MANAGER::OnWriteCompletion`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_IO_MANAGER::OnWriteCompletion(__int64 a1, __int64 a2, volatile signed __int32 **a3)
{
  volatile signed __int32 *v4; // rbx
  int v6; // eax
  volatile signed __int32 *v7; // rdi
  unsigned int v8; // ebx
  unsigned int v9; // eax

  v4 = *a3;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v6 = (**(__int64 (__fastcall ***)(__int64))a2)(a2);
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wsio.cxx",
      300,
      "WEBSOCKET_IO_MANAGER::OnWriteCompletion",
      "Bytes = %08x\n",
      v6);
  }
  _InterlockedDecrement(v4 + 4);
  _InterlockedCompareExchange(v4 + 6, 0, 1);
  WEBSOCKET_IO_MANAGER::InitiateNextQueuedSend((WEBSOCKET_IO_MANAGER *)v4);
  v7 = a3[1];
  v8 = (**(__int64 (__fastcall ***)(__int64))a2)(a2);
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  ((void (__fastcall *)(volatile signed __int32 *, _QWORD, _QWORD))v7)(a3[2], v9, v8);
  operator delete(a3);
  return 1;
}

```

## disassembly

```asm
0x1800052d0  push    rbx
0x1800052d2  push    rsi
0x1800052d3  push    rdi
0x1800052d4  push    r14
0x1800052d6  sub     rsp, 38h
0x1800052da  test    byte ptr cs:g_dwDebugFlags, 3
0x1800052e1  mov     r14, r8
0x1800052e4  mov     rbx, [r8]
0x1800052e7  mov     rsi, rdx
0x1800052ea  jz      short loc_18000532B
0x1800052ec  mov     rax, [rdx]
0x1800052ef  mov     rcx, rdx
0x1800052f2  mov     rax, [rax]
0x1800052f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052fa  mov     rcx, cs:g_pDebug
0x180005301  lea     r9, aWebsocketIoMan_3; "WEBSOCKET_IO_MANAGER::OnWriteCompletion"
0x180005308  mov     [rsp+58h+var_30], eax
0x18000530c  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005313  lea     rax, aBytes08x; "Bytes = %08x\n"
0x18000531a  mov     r8d, 12Ch
0x180005320  mov     [rsp+58h+var_38], rax
0x180005325  call    cs:__imp_PuDbgPrint
0x18000532b  lock dec dword ptr [rbx+10h]
0x18000532f  xor     ecx, ecx
0x180005331  lea     eax, [rcx+1]
0x180005334  lock cmpxchg [rbx+18h], ecx
0x180005339  mov     rcx, rbx; this
0x18000533c  call    ?InitiateNextQueuedSend@WEBSOCKET_IO_MANAGER@@AEAAJXZ; WEBSOCKET_IO_MANAGER::InitiateNextQueuedSend(void)
0x180005341  mov     rax, [rsi]
0x180005344  mov     rcx, rsi
0x180005347  mov     rdi, [r14+8]
0x18000534b  mov     rax, [rax]
0x18000534e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005353  mov     rcx, [rsi]
0x180005356  mov     ebx, eax
0x180005358  mov     rax, [rcx+8]
0x18000535c  mov     rcx, rsi
0x18000535f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005364  mov     rcx, [r14+10h]
0x180005368  mov     edx, eax
0x18000536a  mov     rax, rdi
0x18000536d  mov     r8d, ebx
0x180005370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005375  mov     rcx, r14; Block
0x180005378  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000537d  mov     eax, 1
0x180005382  add     rsp, 38h
0x180005386  pop     r14
0x180005388  pop     rdi
0x180005389  pop     rsi
0x18000538a  pop     rbx
0x18000538b  retn
```
