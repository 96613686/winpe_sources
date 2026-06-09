# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000f980`
- end: `0x18000f9e3`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008980`
- `0x180011fdc`

## callees

- `0x18000f980`
- `0x1800106a4`
- `0x180011000`

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
0x18000f980  mov     [rsp+arg_0], rbx
0x18000f985  mov     [rsp+arg_8], rsi
0x18000f98a  push    rdi; char *
0x18000f98b  sub     rsp, 20h
0x18000f98f  mov     rdi, [rcx+28h]
0x18000f993  mov     rsi, rcx
0x18000f996  mov     rbx, [rcx+20h]
0x18000f99a  mov     rax, rdi
0x18000f99d  sub     rax, rbx
0x18000f9a0  cmp     rax, 10h
0x18000f9a4  jb      short loc_18000F9D3
0x18000f9a6  cmp     rbx, rdi
0x18000f9a9  jz      short loc_18000F9BC
0x18000f9ab  mov     rdx, [rbx+8]
0x18000f9af  mov     ecx, [rbx]
0x18000f9b1  call    wil_details_RecordCachedUsage
0x18000f9b6  add     rbx, 10h
0x18000f9ba  jmp     short loc_18000F9A6
0x18000f9bc  mov     rax, [rsi+20h]
0x18000f9c0  xor     r8d, r8d; unsigned int
0x18000f9c3  mov     edx, 0FEh; unsigned int
0x18000f9c8  mov     [rsi+28h], rax
0x18000f9cc  xor     ecx, ecx; this
0x18000f9ce  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000f9d3  mov     rbx, [rsp+28h+arg_0]
0x18000f9d8  mov     rsi, [rsp+28h+arg_8]
0x18000f9dd  add     rsp, 20h
0x18000f9e1  pop     rdi
0x18000f9e2  retn
```
