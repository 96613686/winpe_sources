# Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_5cc8d34cc960c5039eaefe99ff092a9a_____lambda_5cc8d34cc960c5039eaefe99ff092a9a___

- ea: `0x180043768`
- end: `0x180043807`
- name: `Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_5cc8d34cc960c5039eaefe99ff092a9a_____lambda_5cc8d34cc960c5039eaefe99ff092a9a___`
- size: `159`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800438b8`

## callees

- `0x180018874`
- `0x18001ce50`
- `0x18001f644`
- `0x180043768`
- `0x180043850`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_5cc8d34cc960c5039eaefe99ff092a9a_____lambda_5cc8d34cc960c5039eaefe99ff092a9a___(
        __int64 *a1,
        __int64 *a2)
{
  void *v4; // rax
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
    *v5 = off_180047F70;
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
0x180043768  mov     [rsp+arg_8], rbx
0x18004376d  mov     [rsp+arg_10], rsi
0x180043772  push    rdi
0x180043773  sub     rsp, 20h
0x180043777  mov     rsi, rdx
0x18004377a  mov     qword ptr [rcx], 0
0x180043781  mov     rdi, rcx
0x180043784  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004378b  mov     ecx, 28h ; '('; unsigned __int64
0x180043790  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180043795  mov     [rsp+28h+arg_0], rax
0x18004379a  mov     rbx, rax
0x18004379d  test    rax, rax
0x1800437a0  jz      short loc_1800437E9
0x1800437a2  mov     rcx, rax
0x1800437a5  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x1800437aa  mov     rcx, [rsi]
0x1800437ad  lea     rax, off_180047F70
0x1800437b4  mov     qword ptr [rsi], 0
0x1800437bb  mov     [rbx+10h], rcx
0x1800437bf  mov     rcx, [rsi+8]
0x1800437c3  mov     [rbx+18h], rcx
0x1800437c7  mov     ecx, [rsi+10h]
0x1800437ca  mov     [rbx+20h], ecx
0x1800437cd  mov     [rbx], rax
0x1800437d0  mov     rcx, [rdi]
0x1800437d3  test    rcx, rcx
0x1800437d6  jz      short loc_1800437DD
0x1800437d8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800437dd  mov     [rdi], rbx
0x1800437e0  mov     [rsp+28h+arg_0], 0
0x1800437e9  lea     rcx, [rsp+28h+arg_0]
0x1800437ee  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d_____
0x1800437f3  mov     rbx, [rsp+28h+arg_8]
0x1800437f8  mov     rax, rdi
0x1800437fb  mov     rsi, [rsp+28h+arg_10]
0x180043800  add     rsp, 20h
0x180043804  pop     rdi
0x180043805  retn
```
