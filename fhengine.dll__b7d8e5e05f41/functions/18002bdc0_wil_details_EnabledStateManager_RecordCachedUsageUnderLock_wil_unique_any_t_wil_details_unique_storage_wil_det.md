# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18002bdc0`
- end: `0x18002be24`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002b808`
- `0x18002b900`

## callees

- `0x18002bdc0`
- `0x18002df58`
- `0x18002f270`

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
0x18002bdc0  mov     [rsp+arg_0], rbx
0x18002bdc5  mov     [rsp+arg_8], rsi
0x18002bdca  push    rdi; char *
0x18002bdcb  sub     rsp, 20h
0x18002bdcf  mov     rsi, rcx
0x18002bdd2  mov     rbx, [rcx+20h]
0x18002bdd6  mov     rdi, [rcx+28h]
0x18002bdda  mov     rax, rdi
0x18002bddd  sub     rax, rbx
0x18002bde0  cmp     rax, 10h
0x18002bde4  jb      short loc_18002BE14
0x18002bde6  cmp     rbx, rdi
0x18002bde9  jz      short loc_18002BDFC
0x18002bdeb  mov     rdx, [rbx+8]
0x18002bdef  mov     ecx, [rbx]
0x18002bdf1  call    wil_details_RecordCachedUsage
0x18002bdf6  add     rbx, 10h
0x18002bdfa  jmp     short loc_18002BDE6
0x18002bdfc  mov     rax, [rsi+20h]
0x18002be00  mov     [rsi+28h], rax
0x18002be04  xor     r8d, r8d; unsigned int
0x18002be07  mov     edx, 0FEh; unsigned int
0x18002be0c  xor     ecx, ecx; this
0x18002be0e  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18002be13  nop
0x18002be14  mov     rbx, [rsp+28h+arg_0]
0x18002be19  mov     rsi, [rsp+28h+arg_8]
0x18002be1e  add     rsp, 20h
0x18002be22  pop     rdi
0x18002be23  retn
```
