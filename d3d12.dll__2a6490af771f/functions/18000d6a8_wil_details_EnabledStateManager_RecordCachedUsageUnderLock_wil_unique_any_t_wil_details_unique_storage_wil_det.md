# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000d6a8`
- end: `0x18000d70c`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004838`
- `0x180008ee4`

## callees

- `0x180008a74`
- `0x1800098fc`
- `0x18000d6a8`

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
0x18000d6a8  mov     [rsp+arg_0], rbx
0x18000d6ad  mov     [rsp+arg_8], rsi
0x18000d6b2  push    rdi; char *
0x18000d6b3  sub     rsp, 20h
0x18000d6b7  mov     rsi, rcx
0x18000d6ba  mov     rbx, [rcx+20h]
0x18000d6be  mov     rdi, [rcx+28h]
0x18000d6c2  mov     rax, rdi
0x18000d6c5  sub     rax, rbx
0x18000d6c8  cmp     rax, 10h
0x18000d6cc  jb      short loc_18000D6FC
0x18000d6ce  cmp     rbx, rdi
0x18000d6d1  jz      short loc_18000D6E4
0x18000d6d3  mov     rdx, [rbx+8]
0x18000d6d7  mov     ecx, [rbx]
0x18000d6d9  call    wil_details_RecordCachedUsage
0x18000d6de  add     rbx, 10h
0x18000d6e2  jmp     short loc_18000D6CE
0x18000d6e4  mov     rax, [rsi+20h]
0x18000d6e8  mov     [rsi+28h], rax
0x18000d6ec  xor     r8d, r8d; unsigned int
0x18000d6ef  mov     edx, 0FEh; unsigned int
0x18000d6f4  xor     ecx, ecx; this
0x18000d6f6  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000d6fb  nop
0x18000d6fc  mov     rbx, [rsp+28h+arg_0]
0x18000d701  mov     rsi, [rsp+28h+arg_8]
0x18000d706  add     rsp, 20h
0x18000d70a  pop     rdi
0x18000d70b  retn
```
