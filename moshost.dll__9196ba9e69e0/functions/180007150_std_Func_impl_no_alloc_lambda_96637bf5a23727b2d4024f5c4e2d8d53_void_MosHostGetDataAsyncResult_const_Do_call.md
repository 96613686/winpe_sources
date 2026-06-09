# std::_Func_impl_no_alloc__lambda_96637bf5a23727b2d4024f5c4e2d8d53__void_MosHostGetDataAsyncResult_const_&_::_Do_call

- ea: `0x180007150`
- end: `0x180007230`
- name: `std::_Func_impl_no_alloc__lambda_96637bf5a23727b2d4024f5c4e2d8d53__void_MosHostGetDataAsyncResult_const_&_::_Do_call`
- size: `224`
- prototype: `RPC_STATUS __fastcall(__int64, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007150`
- `0x18000d010`

## import_xrefs

- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180007211`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180007211`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000721f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000721f`

## pseudocode

```c
RPC_STATUS __fastcall std::_Func_impl_no_alloc__lambda_96637bf5a23727b2d4024f5c4e2d8d53__void_MosHostGetDataAsyncResult_const___::_Do_call(
        __int64 a1,
        int *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  struct _RPC_ASYNC_STATE *v6; // rbx
  unsigned int NotificationsQueued; // [rsp+50h] [rbp+8h] BYREF
  int Reply; // [rsp+58h] [rbp+10h] BYREF

  **(_DWORD **)(a1 + 32) = a2[1];
  **(_DWORD **)(a1 + 40) = a2[2];
  **(_DWORD **)(a1 + 48) = a2[3];
  **(_QWORD **)(a1 + 64) = 0;
  **(_DWORD **)(a1 + 56) = 0;
  v4 = *((_QWORD *)a2 + 3);
  if ( v4 )
  {
    v5 = *(_QWORD *)(v4 + 8);
    if ( *(_QWORD *)v4 != v5 )
    {
      **(_DWORD **)(a1 + 56) = v5 - *(_DWORD *)v4;
      **(_QWORD **)(a1 + 64) = **((_QWORD **)a2 + 3);
    }
  }
  if ( *a2 != -2147023673 )
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, int))(*(_QWORD *)qword_1800185D0 + 272LL))(
      qword_1800185D0,
      *(unsigned int *)(a1 + 16),
      0,
      *(unsigned int *)(a1 + 24),
      *(_DWORD *)(a1 + 28),
      a2[4]);
  v6 = *(struct _RPC_ASYNC_STATE **)(a1 + 8);
  Reply = *a2;
  NotificationsQueued = 0;
  RpcServerUnsubscribeForNotification(v6->RuntimeInfo, RpcNotificationCallCancel, &NotificationsQueued);
  return RpcAsyncCompleteCall(v6, &Reply);
}

```

## disassembly

```asm
0x180007150  mov     [rsp+arg_10], rbx
0x180007155  push    rdi
0x180007156  sub     rsp, 40h
0x18000715a  mov     eax, [rdx+4]
0x18000715d  mov     rdi, rdx
0x180007160  mov     r8, [rcx+20h]
0x180007164  mov     rbx, rcx
0x180007167  mov     [r8], eax
0x18000716a  mov     eax, [rdx+8]
0x18000716d  mov     r8, [rcx+28h]
0x180007171  mov     [r8], eax
0x180007174  mov     eax, [rdx+0Ch]
0x180007177  mov     r8, [rcx+30h]
0x18000717b  mov     [r8], eax
0x18000717e  mov     rax, [rcx+40h]
0x180007182  mov     qword ptr [rax], 0
0x180007189  mov     rax, [rcx+38h]
0x18000718d  mov     dword ptr [rax], 0
0x180007193  mov     rax, [rdx+18h]
0x180007197  test    rax, rax
0x18000719a  jz      short loc_1800071BB
0x18000719c  mov     rcx, [rax+8]
0x1800071a0  cmp     [rax], rcx
0x1800071a3  jz      short loc_1800071BB
0x1800071a5  sub     ecx, [rax]
0x1800071a7  mov     rax, [rbx+38h]
0x1800071ab  mov     [rax], ecx
0x1800071ad  mov     rax, [rdx+18h]
0x1800071b1  mov     rcx, [rbx+40h]
0x1800071b5  mov     rax, [rax]
0x1800071b8  mov     [rcx], rax
0x1800071bb  cmp     dword ptr [rdx], 800704C7h
0x1800071c1  jz      short loc_1800071F1
0x1800071c3  mov     edx, [rdx+10h]
0x1800071c6  xor     r8d, r8d
0x1800071c9  mov     rcx, cs:qword_1800185D0
0x1800071d0  mov     r9d, [rbx+18h]
0x1800071d4  mov     [rsp+48h+var_20], edx
0x1800071d8  mov     edx, [rbx+1Ch]
0x1800071db  mov     rax, [rcx]
0x1800071de  mov     [rsp+48h+var_28], edx
0x1800071e2  mov     edx, [rbx+10h]
0x1800071e5  mov     rax, [rax+110h]
0x1800071ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071f1  mov     rbx, [rbx+8]
0x1800071f5  lea     r8, [rsp+48h+NotificationsQueued]; NotificationsQueued
0x1800071fa  mov     eax, [rdi]
0x1800071fc  mov     edx, 2; Notification
0x180007201  mov     [rsp+48h+Reply], eax
0x180007205  mov     [rsp+48h+NotificationsQueued], 0
0x18000720d  mov     rcx, [rbx+20h]; Binding
0x180007211  call    cs:__imp_RpcServerUnsubscribeForNotification
0x180007217  lea     rdx, [rsp+48h+Reply]; Reply
0x18000721c  mov     rcx, rbx; pAsync
0x18000721f  call    cs:__imp_RpcAsyncCompleteCall
0x180007225  mov     rbx, [rsp+48h+arg_10]
0x18000722a  add     rsp, 40h
0x18000722e  pop     rdi
0x18000722f  retn
```
