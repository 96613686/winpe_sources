# winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)

- ea: `0x18000e0a0`
- end: `0x18000e0ed`
- name: `?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ddfc`

## callees

- `0x1800025a0`
- `0x18000e0a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000e0e6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000e0e6`

## pseudocode

```c
void __fastcall winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(volatile signed __int32 **a1)
{
  volatile signed __int32 *v1; // r8

  v1 = *a1;
  *a1 = 0;
  if ( _InterlockedExchangeAdd(v1 + 7, 0xFFFFFFFF) == 1 && v1 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    operator delete((void *)v1);
  }
}

```

## disassembly

```asm
0x18000e0a0  sub     rsp, 28h
0x18000e0a4  mov     r8, [rcx]
0x18000e0a7  mov     qword ptr [rcx], 0
0x18000e0ae  or      ecx, 0FFFFFFFFh
0x18000e0b1  mov     eax, ecx
0x18000e0b3  lock xadd [r8+1Ch], eax
0x18000e0b9  cmp     eax, 1
0x18000e0bc  jnz     short loc_18000E0DD
0x18000e0be  test    r8, r8
0x18000e0c1  jz      short loc_18000E0DD
0x18000e0c3  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000e0cb  sub     ecx, eax
0x18000e0cd  jnz     short loc_18000E0E2
0x18000e0cf  nop
0x18000e0d0  mov     edx, 20h ; ' '; unsigned __int64
0x18000e0d5  mov     rcx, r8; void *
0x18000e0d8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e0dd  add     rsp, 28h
0x18000e0e1  retn
0x18000e0e2  test    ecx, ecx
0x18000e0e4  jns     short loc_18000E0D0
0x18000e0e6  call    cs:__imp_abort
```
