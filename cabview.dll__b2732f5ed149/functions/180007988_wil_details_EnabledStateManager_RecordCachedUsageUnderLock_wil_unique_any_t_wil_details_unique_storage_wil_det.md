# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180007988`
- end: `0x1800079eb`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800073c0`
- `0x1800074fc`

## callees

- `0x180007988`
- `0x180009630`
- `0x18000aaf0`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 v4; // rdi
  __int64 v6; // rbx
  const char *v7; // [rsp+20h] [rbp-8h]

  v4 = *(_QWORD *)(a1 + 40);
  v6 = *(_QWORD *)(a1 + 32);
  if ( (unsigned __int64)(v4 - v6) >= 0x10 )
  {
    while ( v6 != v4 )
    {
      wil_details_RecordCachedUsage(*(_DWORD *)v6, *(_QWORD *)(v6 + 8));
      v6 += 16;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, a4, v7);
  }
}

```

## disassembly

```asm
0x180007988  mov     [rsp+arg_0], rbx
0x18000798d  mov     [rsp+arg_8], rsi
0x180007992  push    rdi; char *
0x180007993  sub     rsp, 20h
0x180007997  mov     rdi, [rcx+28h]
0x18000799b  mov     rsi, rcx
0x18000799e  mov     rbx, [rcx+20h]
0x1800079a2  mov     rax, rdi
0x1800079a5  sub     rax, rbx
0x1800079a8  cmp     rax, 10h
0x1800079ac  jb      short loc_1800079DB
0x1800079ae  cmp     rbx, rdi
0x1800079b1  jz      short loc_1800079C4
0x1800079b3  mov     rdx, [rbx+8]
0x1800079b7  mov     ecx, [rbx]
0x1800079b9  call    wil_details_RecordCachedUsage
0x1800079be  add     rbx, 10h
0x1800079c2  jmp     short loc_1800079AE
0x1800079c4  mov     rax, [rsi+20h]
0x1800079c8  xor     r8d, r8d; unsigned int
0x1800079cb  mov     edx, 0FEh; unsigned int
0x1800079d0  mov     [rsi+28h], rax
0x1800079d4  xor     ecx, ecx; this
0x1800079d6  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800079db  mov     rbx, [rsp+28h+arg_0]
0x1800079e0  mov     rsi, [rsp+28h+arg_8]
0x1800079e5  add     rsp, 20h
0x1800079e9  pop     rdi
0x1800079ea  retn
```
