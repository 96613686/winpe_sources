# std::sys::sync::rwlock::futex::RwLock::wake_writer_or_readers

- ea: `0x180319ee0`
- end: `0x180319f95`
- name: `std::sys::sync::rwlock::futex::RwLock::wake_writer_or_readers`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d6df0`

## callees

- `0x180316ae0`
- `0x180319ee0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x180319f51`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x180319f18`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x180319f51`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180319f6d`

## string_xrefs

- `0x180319f7c`: `assertion failed: is_unlocked(state)dbghelp.dll`

## pseudocode

```c
void __fastcall std::sys::sync::rwlock::futex::RwLock::wake_writer_or_readers(
        volatile signed __int32 *a1,
        signed __int32 a2)
{
  signed __int32 v2; // eax
  volatile signed __int32 *v3; // rsi

  if ( (a2 & 0x3FFFFFFF) != 0 )
    core::panicking::panic("assertion failed: is_unlocked(state)dbghelp.dll", 36, &off_180343C78);
  if ( __OFSUB__(-a2, 1) )
  {
    v2 = _InterlockedCompareExchange(a1, 0, 0x80000000);
    if ( v2 == 0x80000000 )
    {
      _InterlockedIncrement(a1 + 1);
      WakeByAddressSingle((PVOID)(a1 + 1));
      return;
    }
    a2 = v2;
  }
  if ( a2 == -1073741824 )
  {
    if ( _InterlockedCompareExchange(a1, 0x40000000, -1073741824) != -1073741824 )
      return;
    _InterlockedIncrement(a1 + 1);
    v3 = a1;
    WakeByAddressSingle((PVOID)(a1 + 1));
    a1 = v3;
  }
  else if ( a2 != 0x40000000 )
  {
    return;
  }
  if ( _InterlockedCompareExchange(a1, 0, 0x40000000) == 0x40000000 )
    WakeByAddressAll((PVOID)a1);
}

```

## disassembly

```asm
0x180319ee0  push    rbp
0x180319ee1  push    rsi
0x180319ee2  sub     rsp, 28h
0x180319ee6  lea     rbp, [rsp+20h]
0x180319eeb  test    edx, 3FFFFFFFh
0x180319ef1  jnz     loc_180319F7C
0x180319ef7  mov     eax, edx
0x180319ef9  neg     eax
0x180319efb  jno     short loc_180319F21
0x180319efd  xor     edx, edx
0x180319eff  mov     eax, 80000000h
0x180319f04  lock cmpxchg [rcx], edx
0x180319f08  jnz     short loc_180319F1F
0x180319f0a  lock inc dword ptr [rcx+4]
0x180319f0e  add     rcx, 4
0x180319f12  add     rsp, 28h
0x180319f16  pop     rsi
0x180319f17  pop     rbp
0x180319f18  jmp     cs:__imp_WakeByAddressSingle
0x180319f1f  mov     edx, eax
0x180319f21  cmp     edx, 0C0000000h
0x180319f27  jz      short loc_180319F33
0x180319f29  cmp     edx, 40000000h
0x180319f2f  jz      short loc_180319F5A
0x180319f31  jmp     short loc_180319F74
0x180319f33  mov     edx, 40000000h
0x180319f38  mov     eax, 0C0000000h
0x180319f3d  lock cmpxchg [rcx], edx
0x180319f41  jnz     short loc_180319F74
0x180319f43  lea     rax, [rcx+4]
0x180319f47  lock inc dword ptr [rcx+4]
0x180319f4b  mov     rsi, rcx
0x180319f4e  mov     rcx, rax; Address
0x180319f51  call    cs:__imp_WakeByAddressSingle
0x180319f57  mov     rcx, rsi
0x180319f5a  xor     edx, edx
0x180319f5c  mov     eax, 40000000h
0x180319f61  lock cmpxchg [rcx], edx
0x180319f65  jnz     short loc_180319F74
0x180319f67  add     rsp, 28h
0x180319f6b  pop     rsi
0x180319f6c  pop     rbp
0x180319f6d  jmp     cs:__imp_WakeByAddressAll
0x180319f74  nop
0x180319f75  add     rsp, 28h
0x180319f79  pop     rsi
0x180319f7a  pop     rbp
0x180319f7b  retn
0x180319f7c  lea     rcx, aAssertionFaile_54; "assertion failed: is_unlocked(state)dbg"...
0x180319f83  lea     r8, off_180343C78; "library\\std\\src\\sys\\sync\\rwlock\\f"...
0x180319f8a  mov     edx, 24h ; '$'
0x180319f8f  call    core__panicking__panic
```
