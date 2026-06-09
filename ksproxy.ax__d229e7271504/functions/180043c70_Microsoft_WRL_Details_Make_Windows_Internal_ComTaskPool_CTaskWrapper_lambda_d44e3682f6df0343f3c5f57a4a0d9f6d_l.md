# Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d_____lambda_d44e3682f6df0343f3c5f57a4a0d9f6d___

- ea: `0x180043c70`
- end: `0x180043d0f`
- name: `Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d_____lambda_d44e3682f6df0343f3c5f57a4a0d9f6d___`
- size: `159`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043e30`

## callees

- `0x180018874`
- `0x18001ce50`
- `0x18001f644`
- `0x180043850`
- `0x180043c70`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d_____lambda_d44e3682f6df0343f3c5f57a4a0d9f6d___(
        __int64 *a1,
        __int64 *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  volatile int *v6; // rdx
  __int64 v7; // rcx
  void *v9; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x28u, &std::nothrow);
  v9 = v4;
  v5 = v4;
  if ( v4 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v4);
    v7 = *a2;
    *a2 = 0;
    v5[2] = v7;
    v5[3] = a2[1];
    *((_DWORD *)v5 + 8) = *((_DWORD *)a2 + 4);
    *v5 = off_180048030;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(
        *a1,
        v6);
    *a1 = (__int64)v5;
    v9 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d_____(&v9);
  return a1;
}

```

## disassembly

```asm
0x180043c70  mov     [rsp+arg_8], rbx
0x180043c75  mov     [rsp+arg_10], rsi
0x180043c7a  push    rdi
0x180043c7b  sub     rsp, 20h
0x180043c7f  mov     rsi, rdx
0x180043c82  mov     qword ptr [rcx], 0
0x180043c89  mov     rdi, rcx
0x180043c8c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180043c93  mov     ecx, 28h ; '('; unsigned __int64
0x180043c98  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180043c9d  mov     [rsp+28h+arg_0], rax
0x180043ca2  mov     rbx, rax
0x180043ca5  test    rax, rax
0x180043ca8  jz      short loc_180043CF1
0x180043caa  mov     rcx, rax
0x180043cad  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x180043cb2  mov     rcx, [rsi]
0x180043cb5  lea     rax, off_180048030
0x180043cbc  mov     qword ptr [rsi], 0
0x180043cc3  mov     [rbx+10h], rcx
0x180043cc7  mov     rcx, [rsi+8]
0x180043ccb  mov     [rbx+18h], rcx
0x180043ccf  mov     ecx, [rsi+10h]
0x180043cd2  mov     [rbx+20h], ecx
0x180043cd5  mov     [rbx], rax
0x180043cd8  mov     rcx, [rdi]
0x180043cdb  test    rcx, rcx
0x180043cde  jz      short loc_180043CE5
0x180043ce0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180043ce5  mov     [rdi], rbx
0x180043ce8  mov     [rsp+28h+arg_0], 0
0x180043cf1  lea     rcx, [rsp+28h+arg_0]
0x180043cf6  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d_____
0x180043cfb  mov     rbx, [rsp+28h+arg_8]
0x180043d00  mov     rax, rdi
0x180043d03  mov     rsi, [rsp+28h+arg_10]
0x180043d08  add     rsp, 20h
0x180043d0c  pop     rdi
0x180043d0d  retn
```
