# WEBSOCKET_CONTEXT::DoReceiveComplete(long,_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE)

- ea: `0x180005d88`
- end: `0x180005e71`
- name: `?DoReceiveComplete@WEBSOCKET_CONTEXT@@AEAAXJPEAT_WEB_SOCKET_BUFFER@@W4_WEB_SOCKET_BUFFER_TYPE@@@Z`
- size: `233`
- prototype: `int __fastcall(__int64, int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005f50`

## callees

- `0x180005ae8`
- `0x180005d88`
- `0x180006284`
- `0x1800066b4`

## pseudocode

```c
int __fastcall WEBSOCKET_CONTEXT::DoReceiveComplete(__int64 a1, int a2, __int64 a3, unsigned int a4)
{
  int v6; // eax
  int result; // eax
  __int128 v8; // [rsp+30h] [rbp-10h] BYREF
  int v9; // [rsp+60h] [rbp+20h] BYREF
  int v10; // [rsp+68h] [rbp+28h] BYREF
  int v11; // [rsp+78h] [rbp+38h] BYREF

  v9 = 0;
  v10 = 0;
  v11 = 0;
  v8 = 0;
  if ( a2 >= 0 )
  {
    a2 = WEBSOCKET_CONTEXT::ProcessReceivedMessage(a1, a3, a4, &v10);
    if ( a2 >= 0 )
    {
      if ( v10 )
        goto LABEL_13;
      while ( !*(_DWORD *)(a1 + 372) && !*(_DWORD *)(a1 + 356) && *(_DWORD *)(a1 + 352) != 3 )
      {
        a2 = WEBSOCKET_CONTEXT::ReadMessage(
               (WEBSOCKET_CONTEXT *)a1,
               (union _WEB_SOCKET_BUFFER *)&v8,
               (enum _WEB_SOCKET_BUFFER_TYPE *)&v9,
               &v10,
               &v11);
        if ( a2 < 0 || v11 )
          goto LABEL_14;
        v6 = v10;
        if ( v10 )
          goto LABEL_12;
      }
      v6 = v10;
LABEL_12:
      if ( v6 )
LABEL_13:
        _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 368), 0, 1);
    }
  }
LABEL_14:
  result = *(_DWORD *)(a1 + 372);
  if ( result )
  {
    result = -2147467259;
    if ( a2 >= 0 )
      a2 = -2147467259;
  }
  if ( a4 != -2147483643 || a2 < 0 )
    return WEBSOCKET_CONTEXT::CompleteApplicationReadRequest((WEBSOCKET_CONTEXT *)a1, a2);
  return result;
}

```

## disassembly

```asm
0x180005d88  push    rbp
0x180005d8a  push    rbx
0x180005d8b  push    rdi
0x180005d8c  mov     rbp, rsp
0x180005d8f  sub     rsp, 40h
0x180005d93  mov     [rbp+arg_0], 0
0x180005d9a  xorps   xmm0, xmm0
0x180005d9d  mov     [rbp+arg_8], 0
0x180005da4  mov     edi, r9d
0x180005da7  mov     [rbp+arg_18], 0
0x180005dae  mov     rax, r8
0x180005db1  mov     rbx, rcx
0x180005db4  movdqu  [rbp+var_10], xmm0
0x180005db9  test    edx, edx
0x180005dbb  js      loc_180005E41
0x180005dc1  lea     r9, [rbp+arg_8]
0x180005dc5  mov     r8d, edi
0x180005dc8  mov     rdx, rax
0x180005dcb  call    ?ProcessReceivedMessage@WEBSOCKET_CONTEXT@@AEAAJPEAT_WEB_SOCKET_BUFFER@@W4_WEB_SOCKET_BUFFER_TYPE@@PEAH@Z; WEBSOCKET_CONTEXT::ProcessReceivedMessage(_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE,int *)
0x180005dd0  mov     edx, eax
0x180005dd2  test    eax, eax
0x180005dd4  js      short loc_180005E41
0x180005dd6  cmp     [rbp+arg_8], 0
0x180005dda  jnz     short loc_180005E34
0x180005ddc  mov     ecx, [rbx+174h]
0x180005de2  test    ecx, ecx
0x180005de4  jnz     short loc_180005E2D
0x180005de6  mov     ecx, [rbx+164h]
0x180005dec  test    ecx, ecx
0x180005dee  jnz     short loc_180005E2D
0x180005df0  mov     eax, [rbx+160h]
0x180005df6  cmp     eax, 3
0x180005df9  jz      short loc_180005E2D
0x180005dfb  lea     rax, [rbp+arg_18]
0x180005dff  mov     rcx, rbx; this
0x180005e02  lea     r9, [rbp+arg_8]; int *
0x180005e06  mov     [rsp+40h+var_20], rax; int *
0x180005e0b  lea     r8, [rbp+arg_0]; enum _WEB_SOCKET_BUFFER_TYPE *
0x180005e0f  lea     rdx, [rbp+var_10]; union _WEB_SOCKET_BUFFER *
0x180005e13  call    ?ReadMessage@WEBSOCKET_CONTEXT@@AEAAJPEAT_WEB_SOCKET_BUFFER@@PEAW4_WEB_SOCKET_BUFFER_TYPE@@PEAH2@Z; WEBSOCKET_CONTEXT::ReadMessage(_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE *,int *,int *)
0x180005e18  mov     edx, eax
0x180005e1a  test    eax, eax
0x180005e1c  js      short loc_180005E41
0x180005e1e  cmp     [rbp+arg_18], 0
0x180005e22  jnz     short loc_180005E41
0x180005e24  mov     eax, [rbp+arg_8]
0x180005e27  test    eax, eax
0x180005e29  jz      short loc_180005DDC
0x180005e2b  jmp     short loc_180005E30
0x180005e2d  mov     eax, [rbp+arg_8]
0x180005e30  test    eax, eax
0x180005e32  jz      short loc_180005E41
0x180005e34  xor     ecx, ecx
0x180005e36  lea     eax, [rcx+1]
0x180005e39  lock cmpxchg [rbx+170h], ecx
0x180005e41  mov     eax, [rbx+174h]
0x180005e47  test    eax, eax
0x180005e49  jz      short loc_180005E55
0x180005e4b  test    edx, edx
0x180005e4d  mov     eax, 80004005h
0x180005e52  cmovns  edx, eax; int
0x180005e55  cmp     edi, 80000005h
0x180005e5b  jnz     short loc_180005E61
0x180005e5d  test    edx, edx
0x180005e5f  jns     short loc_180005E69
0x180005e61  mov     rcx, rbx; this
0x180005e64  call    ?CompleteApplicationReadRequest@WEBSOCKET_CONTEXT@@AEAAJJ@Z; WEBSOCKET_CONTEXT::CompleteApplicationReadRequest(long)
0x180005e69  add     rsp, 40h
0x180005e6d  pop     rdi
0x180005e6e  pop     rbx
0x180005e6f  pop     rbp
0x180005e70  retn
```
