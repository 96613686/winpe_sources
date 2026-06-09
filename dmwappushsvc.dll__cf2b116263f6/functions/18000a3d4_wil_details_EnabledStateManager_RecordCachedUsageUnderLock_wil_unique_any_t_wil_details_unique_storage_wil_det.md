# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000a3d4`
- end: `0x18000a438`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009bf4`
- `0x180009cec`

## callees

- `0x18000a3d4`
- `0x18000bfd0`
- `0x18000db88`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int *v5; // rbx
  unsigned int *v6; // rdi
  const char *v7; // [rsp+20h] [rbp-8h]

  v5 = *(unsigned int **)(a1 + 32);
  v6 = *(unsigned int **)(a1 + 40);
  if ( (unsigned __int64)((char *)v6 - (char *)v5) >= 0x10 )
  {
    while ( v5 != v6 )
    {
      wil_details_RecordCachedUsage(*v5, *((_QWORD *)v5 + 1));
      v5 += 4;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, a4, v7);
  }
}

```

## disassembly

```asm
0x18000a3d4  mov     [rsp+arg_0], rbx
0x18000a3d9  mov     [rsp+arg_8], rsi
0x18000a3de  push    rdi; char *
0x18000a3df  sub     rsp, 20h
0x18000a3e3  mov     rsi, rcx
0x18000a3e6  mov     rbx, [rcx+20h]
0x18000a3ea  mov     rdi, [rcx+28h]
0x18000a3ee  mov     rax, rdi
0x18000a3f1  sub     rax, rbx
0x18000a3f4  cmp     rax, 10h
0x18000a3f8  jb      short loc_18000A428
0x18000a3fa  cmp     rbx, rdi
0x18000a3fd  jz      short loc_18000A410
0x18000a3ff  mov     rdx, [rbx+8]
0x18000a403  mov     ecx, [rbx]
0x18000a405  call    wil_details_RecordCachedUsage
0x18000a40a  add     rbx, 10h
0x18000a40e  jmp     short loc_18000A3FA
0x18000a410  mov     rax, [rsi+20h]
0x18000a414  mov     [rsi+28h], rax
0x18000a418  xor     r8d, r8d; unsigned int
0x18000a41b  mov     edx, 0FEh; unsigned int
0x18000a420  xor     ecx, ecx; this
0x18000a422  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000a427  nop
0x18000a428  mov     rbx, [rsp+28h+arg_0]
0x18000a42d  mov     rsi, [rsp+28h+arg_8]
0x18000a432  add     rsp, 20h
0x18000a436  pop     rdi
0x18000a437  retn
```
