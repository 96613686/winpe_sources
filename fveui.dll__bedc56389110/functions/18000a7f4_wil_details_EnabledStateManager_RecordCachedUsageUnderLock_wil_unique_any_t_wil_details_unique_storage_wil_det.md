# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000a7f4`
- end: `0x18000a858`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a394`
- `0x180018390`

## callees

- `0x18000a7f4`
- `0x18000c5f4`
- `0x18000ea70`

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
0x18000a7f4  mov     [rsp+arg_0], rbx
0x18000a7f9  mov     [rsp+arg_8], rsi
0x18000a7fe  push    rdi; char *
0x18000a7ff  sub     rsp, 20h
0x18000a803  mov     rsi, rcx
0x18000a806  mov     rbx, [rcx+20h]
0x18000a80a  mov     rdi, [rcx+28h]
0x18000a80e  mov     rax, rdi
0x18000a811  sub     rax, rbx
0x18000a814  cmp     rax, 10h
0x18000a818  jb      short loc_18000A848
0x18000a81a  cmp     rbx, rdi
0x18000a81d  jz      short loc_18000A830
0x18000a81f  mov     rdx, [rbx+8]
0x18000a823  mov     ecx, [rbx]
0x18000a825  call    wil_details_RecordCachedUsage
0x18000a82a  add     rbx, 10h
0x18000a82e  jmp     short loc_18000A81A
0x18000a830  mov     rax, [rsi+20h]
0x18000a834  mov     [rsi+28h], rax
0x18000a838  xor     r8d, r8d; unsigned int
0x18000a83b  mov     edx, 0FEh; unsigned int
0x18000a840  xor     ecx, ecx; this
0x18000a842  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000a847  nop
0x18000a848  mov     rbx, [rsp+28h+arg_0]
0x18000a84d  mov     rsi, [rsp+28h+arg_8]
0x18000a852  add     rsp, 20h
0x18000a856  pop     rdi
0x18000a857  retn
```
