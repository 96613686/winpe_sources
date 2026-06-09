# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x140017a74`
- end: `0x140017afd`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `137`
- prototype: `void __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000abb0`
- `0x14000ff00`
- `0x140015090`

## callees

- `0x14000a020`
- `0x140017a74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140017a98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140017a98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140017aec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140017aec`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  RTL_SRWLOCK *v8; // rbx
  _DWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v10; // [rsp+28h] [rbp-30h]

  if ( *(_DWORD *)a1 )
  {
    v8 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    if ( !a4
      || a4 != *(_DWORD *)(a1 + 28)
      || (v9[1] = 0,
          v9[0] = a3,
          v10 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(a1 + 64), v9, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
  }
}

```

## disassembly

```asm
0x140017a74  push    rbx
0x140017a76  push    rbp
0x140017a77  push    rsi
0x140017a78  push    rdi
0x140017a79  push    r14
0x140017a7b  sub     rsp, 30h
0x140017a7f  mov     eax, [rcx]
0x140017a81  mov     ebp, r9d
0x140017a84  mov     edi, r8d
0x140017a87  mov     rsi, rdx
0x140017a8a  mov     r14, rcx
0x140017a8d  test    eax, eax
0x140017a8f  jz      short loc_140017AF2
0x140017a91  lea     rbx, [rcx+8]
0x140017a95  mov     rcx, rbx; SRWLock
0x140017a98  call    cs:__imp_AcquireSRWLockExclusive
0x140017a9e  mov     eax, [r14+1Ch]
0x140017aa2  test    ebp, ebp
0x140017aa4  jz      short loc_140017AD3
0x140017aa6  cmp     ebp, eax
0x140017aa8  jnz     short loc_140017AD3
0x140017aaa  lea     rcx, [r14+40h]; this
0x140017aae  mov     [rsp+58h+var_34], 0
0x140017ab6  mov     r8d, 10h; unsigned __int64
0x140017abc  mov     [rsp+58h+var_38], edi
0x140017ac0  lea     rdx, [rsp+58h+var_38]; void *
0x140017ac5  mov     [rsp+58h+var_30], rsi
0x140017aca  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140017acf  test    al, al
0x140017ad1  jnz     short loc_140017AE4
0x140017ad3  neg     edi
0x140017ad5  sbb     eax, eax
0x140017ad7  and     eax, 83Ah
0x140017adc  add     eax, 0FFFFF7C1h
0x140017ae1  lock and [rsi], eax
0x140017ae4  test    rbx, rbx
0x140017ae7  jz      short loc_140017AF2
0x140017ae9  mov     rcx, rbx; SRWLock
0x140017aec  call    cs:__imp_ReleaseSRWLockExclusive
0x140017af2  add     rsp, 30h
0x140017af6  pop     r14
0x140017af8  pop     rdi
0x140017af9  pop     rsi
0x140017afa  pop     rbp
0x140017afb  pop     rbx
0x140017afc  retn
```
