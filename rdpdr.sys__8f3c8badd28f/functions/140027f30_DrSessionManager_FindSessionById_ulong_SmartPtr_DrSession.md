# DrSessionManager::FindSessionById(ulong,SmartPtr<DrSession> &)

- ea: `0x140027f30`
- end: `0x140027fd9`
- name: `?FindSessionById@DrSessionManager@@QEAAHKAEAV?$SmartPtr@VDrSession@@@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x1400112e0`
- `0x140019720`
- `0x140019aa4`
- `0x14001ac10`
- `0x14001d938`
- `0x14001dafc`
- `0x14001dc18`

## callees

- `0x140001660`
- `0x140001890`
- `0x140001c50`
- `0x140001ef0`
- `0x140006560`
- `0x140027f30`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140027f47`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140027f47`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140027f59`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140027f59`

## pseudocode

```c
_BOOL8 __fastcall DrSessionManager::FindSessionById(__int64 a1, int a2, RefCount **a3)
{
  struct ListEntry *i; // rax
  RefCount *v7; // rbx

  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)(a1 + 64), 1u);
  for ( i = DoubleList::First((DoubleList *)(a1 + 16)); i; i = DoubleList::Next((DoubleList *)(a1 + 16), i) )
  {
    v7 = (RefCount *)*((_QWORD *)i + 2);
    if ( *((_DWORD *)v7 + 282) == a2 )
    {
      if ( *a3 )
        RefCount::Release(*a3);
      *a3 = v7;
      RefCount::AddRef(v7);
      break;
    }
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 48) + 32LL))(a1 + 48);
  return *a3 != 0;
}

```

## disassembly

```asm
0x140027f30  mov     [rsp+arg_8], rbp
0x140027f35  mov     [rsp+arg_10], rsi
0x140027f3a  push    rdi
0x140027f3b  sub     rsp, 20h
0x140027f3f  mov     rsi, r8
0x140027f42  mov     edi, edx
0x140027f44  mov     rbp, rcx
0x140027f47  call    cs:__imp_KeEnterCriticalRegion
0x140027f4e  nop     dword ptr [rax+rax+00h]
0x140027f53  lea     rcx, [rbp+40h]; Resource
0x140027f57  mov     dl, 1; Wait
0x140027f59  call    cs:__imp_ExAcquireResourceSharedLite
0x140027f60  nop     dword ptr [rax+rax+00h]
0x140027f65  lea     rcx, [rbp+10h]; this
0x140027f69  call    ?First@DoubleList@@QEAAPEAVListEntry@@XZ; DoubleList::First(void)
0x140027f6e  mov     [rsp+28h+arg_0], rbx
0x140027f73  test    rax, rax
0x140027f76  jz      short loc_140027FAA
0x140027f78  mov     rbx, [rax+10h]
0x140027f7c  cmp     [rbx+468h], edi
0x140027f82  jz      short loc_140027F92
0x140027f84  mov     rdx, rax; struct ListEntry *
0x140027f87  lea     rcx, [rbp+10h]; this
0x140027f8b  call    ?Next@DoubleList@@QEAAPEAVListEntry@@PEAV2@@Z; DoubleList::Next(ListEntry *)
0x140027f90  jmp     short loc_140027F73
0x140027f92  mov     rcx, [rsi]; this
0x140027f95  test    rcx, rcx
0x140027f98  jz      short loc_140027F9F
0x140027f9a  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140027f9f  mov     rcx, rbx; this
0x140027fa2  mov     [rsi], rbx
0x140027fa5  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140027faa  mov     rax, [rbp+30h]
0x140027fae  lea     rcx, [rbp+30h]
0x140027fb2  mov     rax, [rax+20h]
0x140027fb6  call    _guard_dispatch_icall
0x140027fbb  mov     rbx, [rsp+28h+arg_0]
0x140027fc0  xor     eax, eax
0x140027fc2  cmp     [rsi], rax
0x140027fc5  mov     rbp, [rsp+28h+arg_8]
0x140027fca  mov     rsi, [rsp+28h+arg_10]
0x140027fcf  setnz   al
0x140027fd2  add     rsp, 20h
0x140027fd6  pop     rdi
0x140027fd7  retn
```
