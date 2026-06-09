# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x140016d74`
- end: `0x140016dd8`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140016c68`
- `0x140016cbc`

## callees

- `0x140016d74`
- `0x140017d50`
- `0x1400188a8`

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
0x140016d74  mov     [rsp+arg_0], rbx
0x140016d79  mov     [rsp+arg_8], rsi
0x140016d7e  push    rdi; char *
0x140016d7f  sub     rsp, 20h
0x140016d83  mov     rsi, rcx
0x140016d86  mov     rbx, [rcx+20h]
0x140016d8a  mov     rdi, [rcx+28h]
0x140016d8e  mov     rax, rdi
0x140016d91  sub     rax, rbx
0x140016d94  cmp     rax, 10h
0x140016d98  jb      short loc_140016DC8
0x140016d9a  cmp     rbx, rdi
0x140016d9d  jz      short loc_140016DB0
0x140016d9f  mov     rdx, [rbx+8]
0x140016da3  mov     ecx, [rbx]
0x140016da5  call    wil_details_RecordCachedUsage
0x140016daa  add     rbx, 10h
0x140016dae  jmp     short loc_140016D9A
0x140016db0  mov     rax, [rsi+20h]
0x140016db4  mov     [rsi+28h], rax
0x140016db8  xor     r8d, r8d; unsigned int
0x140016dbb  mov     edx, 0FEh; unsigned int
0x140016dc0  xor     ecx, ecx; this
0x140016dc2  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140016dc7  nop
0x140016dc8  mov     rbx, [rsp+28h+arg_0]
0x140016dcd  mov     rsi, [rsp+28h+arg_8]
0x140016dd2  add     rsp, 20h
0x140016dd6  pop     rdi
0x140016dd7  retn
```
