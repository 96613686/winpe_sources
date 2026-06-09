# DisconnectRpcConnectionCallback(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)

- ea: `0x180007d40`
- end: `0x180007e32`
- name: `?DisconnectRpcConnectionCallback@@YAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z`
- size: `242`
- prototype: `void __fastcall(PVOID P, void *, enum _RPC_ASYNC_EVENT)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007bd8`
- `0x180007d40`
- `0x180007f70`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180007e1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007e1a`
- `msrpc!RpcSsDestroyClientContext` at `0x180007dfe`
- `msrpc!RpcSsDestroyClientContext` at `0x180007dfe`
- `msrpc!I_RpcExceptionFilter` at `0x18001144d`
- `msrpc!I_RpcExceptionFilter` at `0x18001144d`
- `msrpc!RpcAsyncCompleteCall` at `0x180007d5e`
- `msrpc!RpcAsyncCompleteCall` at `0x180007d5e`

## pseudocode

```c
void __fastcall DisconnectRpcConnectionCallback(struct _RPC_ASYNC_STATE *P, void *a2, enum _RPC_ASYNC_EVENT a3)
{
  RPC_STATUS v4; // eax
  int v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = 0;
  v4 = RpcAsyncCompleteCall(P, &v5);
  if ( v4 != 259 )
  {
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 10, &WPP_eb14248ea5fd33b72e0b1fd056f42a15_Traceguids);
    }
    else if ( v5 < 0 && P->UserInfo )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_Lq(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          11,
          &WPP_eb14248ea5fd33b72e0b1fd056f42a15_Traceguids,
          (unsigned int)v5,
          P->UserInfo);
      RpcSsDestroyClientContext(&P->UserInfo);
    }
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x180007d40  mov     rax, rsp
0x180007d43  mov     [rax+10h], rbx
0x180007d47  mov     [rax+8], rcx
0x180007d4b  push    rdi
0x180007d4c  sub     rsp, 30h
0x180007d50  mov     rbx, rcx
0x180007d53  mov     dword ptr [rax+20h], 0
0x180007d5a  lea     rdx, [rax+20h]; Reply
0x180007d5e  call    cs:__imp_RpcAsyncCompleteCall
0x180007d65  nop     dword ptr [rax+rax+00h]
0x180007d6a  cmp     eax, 103h
0x180007d6f  jz      loc_180007E26
0x180007d75  test    eax, eax
0x180007d77  jz      short loc_180007DB2
0x180007d79  lea     rdx, WPP_GLOBAL_Control
0x180007d80  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d87  cmp     rcx, rdx
0x180007d8a  jz      loc_180007E15
0x180007d90  mov     edx, [rcx+2Ch]
0x180007d93  test    dl, 1
0x180007d96  jz      short loc_180007E15
0x180007d98  mov     edx, 0Ah
0x180007d9d  mov     r9d, eax
0x180007da0  lea     r8, WPP_eb14248ea5fd33b72e0b1fd056f42a15_Traceguids
0x180007da7  mov     rcx, [rcx+18h]
0x180007dab  call    WPP_SF_D
0x180007db0  jmp     short loc_180007E15
0x180007db2  mov     r9d, [rsp+38h+arg_18]
0x180007db7  test    r9d, r9d
0x180007dba  jns     short loc_180007E15
0x180007dbc  mov     r8, [rbx+18h]
0x180007dc0  test    r8, r8
0x180007dc3  jz      short loc_180007E15
0x180007dc5  lea     rdx, WPP_GLOBAL_Control
0x180007dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dd3  cmp     rcx, rdx
0x180007dd6  jz      short loc_180007DFA
0x180007dd8  mov     eax, [rcx+2Ch]
0x180007ddb  test    al, 1
0x180007ddd  jz      short loc_180007DFA
0x180007ddf  mov     edx, 0Bh
0x180007de4  mov     [rsp+38h+var_18], r8
0x180007de9  lea     r8, WPP_eb14248ea5fd33b72e0b1fd056f42a15_Traceguids
0x180007df0  mov     rcx, [rcx+18h]
0x180007df4  call    WPP_SF_Lq
0x180007df9  nop
0x180007dfa  lea     rcx, [rbx+18h]; ContextHandle
0x180007dfe  call    cs:__imp_RpcSsDestroyClientContext
0x180007e05  nop     dword ptr [rax+rax+00h]
0x180007e0a  jmp     short loc_180007E15
0x180007e0c  mov     [rsp+38h+arg_18], eax
0x180007e10  mov     rbx, [rsp+38h+arg_0]
0x180007e15  xor     edx, edx; Tag
0x180007e17  mov     rcx, rbx; P
0x180007e1a  call    cs:__imp_ExFreePoolWithTag
0x180007e21  nop     dword ptr [rax+rax+00h]
0x180007e26  mov     rbx, [rsp+38h+arg_8]
0x180007e2b  add     rsp, 30h
0x180007e2f  pop     rdi
0x180007e30  retn
0x18001143f  push    rbp
0x180011441  sub     rsp, 30h
0x180011445  mov     rbp, rdx
0x180011448  mov     rcx, [rcx]
0x18001144b  mov     ecx, [rcx]; ExceptionCode
0x18001144d  call    cs:__imp_I_RpcExceptionFilter
0x180011454  nop     dword ptr [rax+rax+00h]
0x180011459  nop
0x18001145a  add     rsp, 30h
0x18001145e  pop     rbp
0x18001145f  retn
```
