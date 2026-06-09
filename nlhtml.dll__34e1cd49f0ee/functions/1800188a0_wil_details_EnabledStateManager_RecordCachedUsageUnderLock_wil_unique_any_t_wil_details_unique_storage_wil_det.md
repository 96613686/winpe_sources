# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1800188a0`
- end: `0x180018904`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180018488`
- `0x18001ba5c`

## callees

- `0x1800188a0`
- `0x18001a334`
- `0x18001b220`

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
0x1800188a0  mov     [rsp+arg_0], rbx
0x1800188a5  mov     [rsp+arg_8], rsi
0x1800188aa  push    rdi; char *
0x1800188ab  sub     rsp, 20h
0x1800188af  mov     rsi, rcx
0x1800188b2  mov     rbx, [rcx+20h]
0x1800188b6  mov     rdi, [rcx+28h]
0x1800188ba  mov     rax, rdi
0x1800188bd  sub     rax, rbx
0x1800188c0  cmp     rax, 10h
0x1800188c4  jb      short loc_1800188F4
0x1800188c6  cmp     rbx, rdi
0x1800188c9  jz      short loc_1800188DC
0x1800188cb  mov     rdx, [rbx+8]
0x1800188cf  mov     ecx, [rbx]
0x1800188d1  call    wil_details_RecordCachedUsage
0x1800188d6  add     rbx, 10h
0x1800188da  jmp     short loc_1800188C6
0x1800188dc  mov     rax, [rsi+20h]
0x1800188e0  mov     [rsi+28h], rax
0x1800188e4  xor     r8d, r8d; unsigned int
0x1800188e7  mov     edx, 0FEh; unsigned int
0x1800188ec  xor     ecx, ecx; this
0x1800188ee  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800188f3  nop
0x1800188f4  mov     rbx, [rsp+28h+arg_0]
0x1800188f9  mov     rsi, [rsp+28h+arg_8]
0x1800188fe  add     rsp, 20h
0x180018902  pop     rdi
0x180018903  retn
```
