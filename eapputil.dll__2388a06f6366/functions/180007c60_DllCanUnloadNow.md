# DllCanUnloadNow

- ea: `0x180007c60`
- end: `0x180007cfd`
- name: `DllCanUnloadNow`
- size: `157`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003971`
- `0x180007c60`
- `0x180033010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  PSLIST_ENTRY v1; // r8
  struct _SLIST_ENTRY *Next; // r9
  struct _SLIST_ENTRY *v3; // rsi
  __int128 v4; // rt0
  unsigned __int8 v5; // tt

  if ( `winrt::get_module_lock'::`2'::s_lock )
    return 1;
  v1 = WINRT_IMPL_InterlockedFlushSList(&`winrt::impl::get_factory_cache'::`2'::cache);
  if ( v1 )
  {
    do
    {
      Next = v1[-1].Next;
      v3 = v1->Next;
      if ( Next )
      {
        v4 = (unsigned __int64)v1[-1].Next;
        v5 = _InterlockedCompareExchange128((volatile signed __int64 *)&v1[-1], 0, 0, (signed __int64 *)&v4);
        if ( v5 != 0 )
          ((void (__fastcall *)(struct _SLIST_ENTRY *))Next->Next[1].Next)(Next);
      }
      v1 = v3;
    }
    while ( v3 );
  }
  return 0;
}

```

## disassembly

```asm
0x180007c60  mov     [rsp+arg_0], rbx
0x180007c65  mov     [rsp+arg_8], rsi
0x180007c6a  push    rdi
0x180007c6b  sub     rsp, 30h
0x180007c6f  mov     eax, cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180007c75  nop
0x180007c76  test    eax, eax
0x180007c78  jz      short loc_180007C81
0x180007c7a  mov     edi, 1
0x180007c7f  jmp     short loc_180007CEB
0x180007c81  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180007c88  call    WINRT_IMPL_InterlockedFlushSList
0x180007c8d  mov     r8, rax
0x180007c90  test    rax, rax
0x180007c93  jz      short loc_180007CE9
0x180007c95  mov     edi, 1
0x180007c9a  mov     r9, [r8-10h]
0x180007c9e  mov     rsi, [r8]
0x180007ca1  nop
0x180007ca2  test    r9, r9
0x180007ca5  jz      short loc_180007CE1
0x180007ca7  xor     edx, edx
0x180007ca9  mov     [rsp+38h+var_18], r9
0x180007cae  xor     ecx, ecx
0x180007cb0  mov     [rsp+38h+var_10], rdx
0x180007cb5  xor     ebx, ebx
0x180007cb7  mov     rax, r9
0x180007cba  lock cmpxchg16b xmmword ptr [r8-10h]
0x180007cc0  mov     [rsp+38h+var_18], rax
0x180007cc5  setz    al
0x180007cc8  mov     [rsp+38h+var_10], rdx
0x180007ccd  cmp     al, dil
0x180007cd0  jnz     short loc_180007CE1
0x180007cd2  mov     rax, [r9]
0x180007cd5  mov     rcx, r9
0x180007cd8  mov     rax, [rax+10h]
0x180007cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce1  mov     r8, rsi
0x180007ce4  test    rsi, rsi
0x180007ce7  jnz     short loc_180007C9A
0x180007ce9  xor     edi, edi
0x180007ceb  mov     rbx, [rsp+38h+arg_0]
0x180007cf0  mov     eax, edi
0x180007cf2  mov     rsi, [rsp+38h+arg_8]
0x180007cf7  add     rsp, 30h
0x180007cfb  pop     rdi
0x180007cfc  retn
```
