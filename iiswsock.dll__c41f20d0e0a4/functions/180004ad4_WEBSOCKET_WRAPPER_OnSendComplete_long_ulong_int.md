# WEBSOCKET_WRAPPER::OnSendComplete(long,ulong,int)

- ea: `0x180004ad4`
- end: `0x180004ba6`
- name: `?OnSendComplete@WEBSOCKET_WRAPPER@@AEAAJJKH@Z`
- size: `210`
- prototype: `__int64 __fastcall(WEBSOCKET_WRAPPER *__hidden this, int, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000477c`
- `0x180005050`

## callees

- `0x180001048`
- `0x180004568`
- `0x180004ad4`
- `0x180009010`

## import_xrefs

- `websocket!WebSocketCompleteAction` at `0x180004b2f`
- `websocket!WebSocketCompleteAction` at `0x180004b2f`
- `websocket!WebSocketAbortHandle` at `0x180004b1a`
- `websocket!WebSocketAbortHandle` at `0x180004b1a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004b08`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004b08`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_WRAPPER::OnSendComplete(WEBSOCKET_WRAPPER *this, int a2, unsigned int a3, int a4)
{
  int v8; // esi
  __int64 i; // rdi
  void *Block[5]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+68h] [rbp+10h] BYREF
  int v13; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  *(_OWORD *)Block = 0;
  v12 = 2;
  *(_QWORD *)this = GetTickCount64();
  if ( a2 < 0 )
    WebSocketAbortHandle(*((_QWORD *)this + 3));
  if ( a4 )
    WebSocketCompleteAction(*((_QWORD *)this + 3), *((_QWORD *)this + 2), a3);
  v8 = WEBSOCKET_WRAPPER::DoSendLoop(this, &v13, 0, (union COMPLETION_CONTEXT **)Block, &v12);
  if ( v8 >= 0 )
  {
    for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))Block[i])(*((_QWORD *)Block[i] + 1), (unsigned int)a2);
      operator delete(Block[i]);
      Block[i] = 0;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004ad4  mov     rax, rsp
0x180004ad7  mov     [rax+8], rbx
0x180004adb  mov     [rax+18h], rbp
0x180004adf  push    rsi
0x180004ae0  push    rdi
0x180004ae1  push    r14
0x180004ae3  sub     rsp, 40h
0x180004ae7  xorps   xmm0, xmm0
0x180004aea  mov     dword ptr [rax+20h], 0
0x180004af1  movups  xmmword ptr [rax-28h], xmm0
0x180004af5  mov     esi, r9d
0x180004af8  mov     dword ptr [rax+10h], 2
0x180004aff  mov     ebp, r8d
0x180004b02  mov     r14d, edx
0x180004b05  mov     rdi, rcx
0x180004b08  call    cs:__imp_GetTickCount64
0x180004b0e  mov     [rdi], rax
0x180004b11  test    r14d, r14d
0x180004b14  jns     short loc_180004B20
0x180004b16  mov     rcx, [rdi+18h]
0x180004b1a  call    cs:__imp_WebSocketAbortHandle
0x180004b20  test    esi, esi
0x180004b22  jz      short loc_180004B35
0x180004b24  mov     rdx, [rdi+10h]
0x180004b28  mov     r8d, ebp
0x180004b2b  mov     rcx, [rdi+18h]
0x180004b2f  call    cs:__imp_WebSocketCompleteAction
0x180004b35  lea     rax, [rsp+58h+arg_8]
0x180004b3a  xor     r8d, r8d; union COMPLETION_CONTEXT *
0x180004b3d  lea     r9, [rsp+58h+Block]; union COMPLETION_CONTEXT **
0x180004b42  mov     [rsp+58h+var_38], rax; unsigned int *
0x180004b47  lea     rdx, [rsp+58h+arg_18]; int *
0x180004b4c  mov     rcx, rdi; this
0x180004b4f  call    ?DoSendLoop@WEBSOCKET_WRAPPER@@AEAAJPEAHPEATCOMPLETION_CONTEXT@@PEAPEAT2@PEAK@Z; WEBSOCKET_WRAPPER::DoSendLoop(int *,COMPLETION_CONTEXT *,COMPLETION_CONTEXT * *,ulong *)
0x180004b54  mov     esi, eax
0x180004b56  test    eax, eax
0x180004b58  js      short loc_180004B91
0x180004b5a  xor     edi, edi
0x180004b5c  cmp     [rsp+58h+arg_8], edi
0x180004b60  jbe     short loc_180004B91
0x180004b62  mov     rcx, [rsp+rdi*8+58h+Block]
0x180004b67  mov     edx, r14d
0x180004b6a  mov     rax, [rcx]
0x180004b6d  mov     rcx, [rcx+8]
0x180004b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b76  mov     rcx, [rsp+rdi*8+58h+Block]; Block
0x180004b7b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004b80  mov     [rsp+rdi*8+58h+Block], 0
0x180004b89  inc     edi
0x180004b8b  cmp     edi, [rsp+58h+arg_8]
0x180004b8f  jb      short loc_180004B62
0x180004b91  mov     rbx, [rsp+58h+arg_0]
0x180004b96  mov     eax, esi
0x180004b98  mov     rbp, [rsp+58h+arg_10]
0x180004b9d  add     rsp, 40h
0x180004ba1  pop     r14
0x180004ba3  pop     rdi
0x180004ba4  pop     rsi
0x180004ba5  retn
```
