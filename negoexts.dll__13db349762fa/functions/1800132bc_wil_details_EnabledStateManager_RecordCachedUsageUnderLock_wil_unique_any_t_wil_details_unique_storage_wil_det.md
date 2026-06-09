# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1800132bc`
- end: `0x18001331f`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e1d4`
- `0x180012ea0`

## callees

- `0x1800132bc`
- `0x180014dc8`
- `0x1800166d8`

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
0x1800132bc  mov     [rsp+arg_0], rbx
0x1800132c1  mov     [rsp+arg_8], rsi
0x1800132c6  push    rdi; char *
0x1800132c7  sub     rsp, 20h
0x1800132cb  mov     rdi, [rcx+28h]
0x1800132cf  mov     rsi, rcx
0x1800132d2  mov     rbx, [rcx+20h]
0x1800132d6  mov     rax, rdi
0x1800132d9  sub     rax, rbx
0x1800132dc  cmp     rax, 10h
0x1800132e0  jb      short loc_18001330F
0x1800132e2  cmp     rbx, rdi
0x1800132e5  jz      short loc_1800132F8
0x1800132e7  mov     rdx, [rbx+8]
0x1800132eb  mov     ecx, [rbx]
0x1800132ed  call    wil_details_RecordCachedUsage
0x1800132f2  add     rbx, 10h
0x1800132f6  jmp     short loc_1800132E2
0x1800132f8  mov     rax, [rsi+20h]
0x1800132fc  xor     r8d, r8d; unsigned int
0x1800132ff  mov     edx, 0FEh; unsigned int
0x180013304  mov     [rsi+28h], rax
0x180013308  xor     ecx, ecx; this
0x18001330a  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18001330f  mov     rbx, [rsp+28h+arg_0]
0x180013314  mov     rsi, [rsp+28h+arg_8]
0x180013319  add     rsp, 20h
0x18001331d  pop     rdi
0x18001331e  retn
```
