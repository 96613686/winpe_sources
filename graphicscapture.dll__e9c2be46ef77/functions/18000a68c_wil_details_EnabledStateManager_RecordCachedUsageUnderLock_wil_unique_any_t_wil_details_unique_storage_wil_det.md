# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000a68c`
- end: `0x18000a6f0`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a2c0`
- `0x180010cc0`

## callees

- `0x18000a68c`
- `0x18000c234`
- `0x18000d3c0`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  const char *v7; // [rsp+20h] [rbp-8h]

  v5 = *(_QWORD *)(a1 + 32);
  v6 = *(_QWORD *)(a1 + 40);
  if ( (unsigned __int64)(v6 - v5) >= 0x10 )
  {
    while ( v5 != v6 )
    {
      wil_details_RecordCachedUsage(*(_DWORD *)v5, *(_QWORD *)(v5 + 8));
      v5 += 16;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, a4, v7);
  }
}

```

## disassembly

```asm
0x18000a68c  mov     [rsp+arg_0], rbx
0x18000a691  mov     [rsp+arg_8], rsi
0x18000a696  push    rdi; char *
0x18000a697  sub     rsp, 20h
0x18000a69b  mov     rsi, rcx
0x18000a69e  mov     rbx, [rcx+20h]
0x18000a6a2  mov     rdi, [rcx+28h]
0x18000a6a6  mov     rax, rdi
0x18000a6a9  sub     rax, rbx
0x18000a6ac  cmp     rax, 10h
0x18000a6b0  jb      short loc_18000A6E0
0x18000a6b2  cmp     rbx, rdi
0x18000a6b5  jz      short loc_18000A6C8
0x18000a6b7  mov     rdx, [rbx+8]
0x18000a6bb  mov     ecx, [rbx]
0x18000a6bd  call    wil_details_RecordCachedUsage
0x18000a6c2  add     rbx, 10h
0x18000a6c6  jmp     short loc_18000A6B2
0x18000a6c8  mov     rax, [rsi+20h]
0x18000a6cc  mov     [rsi+28h], rax
0x18000a6d0  xor     r8d, r8d; unsigned int
0x18000a6d3  mov     edx, 0FEh; unsigned int
0x18000a6d8  xor     ecx, ecx; this
0x18000a6da  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000a6df  nop
0x18000a6e0  mov     rbx, [rsp+28h+arg_0]
0x18000a6e5  mov     rsi, [rsp+28h+arg_8]
0x18000a6ea  add     rsp, 20h
0x18000a6ee  pop     rdi
0x18000a6ef  retn
```
