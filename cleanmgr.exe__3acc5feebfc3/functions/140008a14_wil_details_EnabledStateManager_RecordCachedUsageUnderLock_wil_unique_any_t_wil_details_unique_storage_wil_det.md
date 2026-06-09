# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x140008a14`
- end: `0x140008a78`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140008054`
- `0x1400084cc`

## callees

- `0x140008a14`
- `0x140009c88`
- `0x14000b3d0`

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
0x140008a14  mov     [rsp+arg_0], rbx
0x140008a19  mov     [rsp+arg_8], rsi
0x140008a1e  push    rdi; char *
0x140008a1f  sub     rsp, 20h
0x140008a23  mov     rsi, rcx
0x140008a26  mov     rbx, [rcx+20h]
0x140008a2a  mov     rdi, [rcx+28h]
0x140008a2e  mov     rax, rdi
0x140008a31  sub     rax, rbx
0x140008a34  cmp     rax, 10h
0x140008a38  jb      short loc_140008A68
0x140008a3a  cmp     rbx, rdi
0x140008a3d  jz      short loc_140008A50
0x140008a3f  mov     rdx, [rbx+8]
0x140008a43  mov     ecx, [rbx]
0x140008a45  call    wil_details_RecordCachedUsage
0x140008a4a  add     rbx, 10h
0x140008a4e  jmp     short loc_140008A3A
0x140008a50  mov     rax, [rsi+20h]
0x140008a54  mov     [rsi+28h], rax
0x140008a58  xor     r8d, r8d; unsigned int
0x140008a5b  mov     edx, 0FEh; unsigned int
0x140008a60  xor     ecx, ecx; this
0x140008a62  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140008a67  nop
0x140008a68  mov     rbx, [rsp+28h+arg_0]
0x140008a6d  mov     rsi, [rsp+28h+arg_8]
0x140008a72  add     rsp, 20h
0x140008a76  pop     rdi
0x140008a77  retn
```
