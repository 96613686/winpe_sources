# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180014b20`
- end: `0x180014b84`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000af70`
- `0x180014700`

## callees

- `0x180014b20`
- `0x180016404`
- `0x180017010`

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
0x180014b20  mov     [rsp+arg_0], rbx
0x180014b25  mov     [rsp+arg_8], rsi
0x180014b2a  push    rdi; char *
0x180014b2b  sub     rsp, 20h
0x180014b2f  mov     rsi, rcx
0x180014b32  mov     rbx, [rcx+20h]
0x180014b36  mov     rdi, [rcx+28h]
0x180014b3a  mov     rax, rdi
0x180014b3d  sub     rax, rbx
0x180014b40  cmp     rax, 10h
0x180014b44  jb      short loc_180014B74
0x180014b46  cmp     rbx, rdi
0x180014b49  jz      short loc_180014B5C
0x180014b4b  mov     rdx, [rbx+8]
0x180014b4f  mov     ecx, [rbx]
0x180014b51  call    wil_details_RecordCachedUsage
0x180014b56  add     rbx, 10h
0x180014b5a  jmp     short loc_180014B46
0x180014b5c  mov     rax, [rsi+20h]
0x180014b60  mov     [rsi+28h], rax
0x180014b64  xor     r8d, r8d; unsigned int
0x180014b67  mov     edx, 0FEh; unsigned int
0x180014b6c  xor     ecx, ecx; this
0x180014b6e  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180014b73  nop
0x180014b74  mov     rbx, [rsp+28h+arg_0]
0x180014b79  mov     rsi, [rsp+28h+arg_8]
0x180014b7e  add     rsp, 20h
0x180014b82  pop     rdi
0x180014b83  retn
```
