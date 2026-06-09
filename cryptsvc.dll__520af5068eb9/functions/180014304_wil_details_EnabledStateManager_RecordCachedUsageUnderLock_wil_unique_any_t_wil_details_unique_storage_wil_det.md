# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180014304`
- end: `0x180014367`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `99`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ccc4`
- `0x18000d38c`

## callees

- `0x18000c884`
- `0x180014304`
- `0x180016320`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int *v4; // rdi
  unsigned int *v6; // rbx
  const char *v7; // [rsp+20h] [rbp-8h]

  v4 = *(unsigned int **)(a1 + 40);
  v6 = *(unsigned int **)(a1 + 32);
  if ( (unsigned __int64)((char *)v4 - (char *)v6) >= 0x10 )
  {
    while ( v6 != v4 )
    {
      wil_details_RecordCachedUsage(*v6, *((_QWORD *)v6 + 1));
      v6 += 4;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, a4, v7);
  }
}

```

## disassembly

```asm
0x180014304  mov     [rsp+arg_0], rbx
0x180014309  mov     [rsp+arg_8], rsi
0x18001430e  push    rdi; char *
0x18001430f  sub     rsp, 20h
0x180014313  mov     rdi, [rcx+28h]
0x180014317  mov     rsi, rcx
0x18001431a  mov     rbx, [rcx+20h]
0x18001431e  mov     rax, rdi
0x180014321  sub     rax, rbx
0x180014324  cmp     rax, 10h
0x180014328  jb      short loc_180014357
0x18001432a  cmp     rbx, rdi
0x18001432d  jz      short loc_180014340
0x18001432f  mov     rdx, [rbx+8]
0x180014333  mov     ecx, [rbx]
0x180014335  call    wil_details_RecordCachedUsage
0x18001433a  add     rbx, 10h
0x18001433e  jmp     short loc_18001432A
0x180014340  mov     rax, [rsi+20h]
0x180014344  xor     r8d, r8d; unsigned int
0x180014347  mov     edx, 0FEh; unsigned int
0x18001434c  mov     [rsi+28h], rax
0x180014350  xor     ecx, ecx; this
0x180014352  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180014357  mov     rbx, [rsp+28h+arg_0]
0x18001435c  mov     rsi, [rsp+28h+arg_8]
0x180014361  add     rsp, 20h
0x180014365  pop     rdi
0x180014366  retn
```
