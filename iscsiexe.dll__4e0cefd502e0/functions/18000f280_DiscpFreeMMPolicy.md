# DiscpFreeMMPolicy

- ea: `0x18000f280`
- end: `0x18000f30a`
- name: `DiscpFreeMMPolicy`
- size: `138`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800066f0`
- `0x18000eeb0`
- `0x1800112b8`
- `0x180012348`

## callees

- `0x180006870`
- `0x18000f280`
- `0x180016bb4`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000f2f2`
- `ntdll!RtlLeaveCriticalSection` at `0x18000f2f2`
- `ntdll!RtlEnterCriticalSection` at `0x18000f2d0`
- `ntdll!RtlEnterCriticalSection` at `0x18000f2d0`

## pseudocode

```c
__int64 __fastcall DiscpFreeMMPolicy(__int64 a1)
{
  GUID *v1; // rdi
  unsigned int v2; // esi

  v1 = (GUID *)(a1 + 100);
  v2 = 0;
  if ( *(_QWORD *)(a1 + 100) || *(_QWORD *)(a1 + 108) != _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] )
    v2 = DiscpRemovePolicy(v1);
  *(_DWORD *)(a1 + 20) &= ~4u;
  *v1 = 0;
  RtlEnterCriticalSection(&DiscpCritSection);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
    DiscpFreeTargetAddress(a1);
  RtlLeaveCriticalSection(&DiscpCritSection);
  return v2;
}

```

## disassembly

```asm
0x18000f280  mov     [rsp+arg_0], rbx
0x18000f285  mov     [rsp+arg_8], rsi
0x18000f28a  push    rdi
0x18000f28b  sub     rsp, 20h
0x18000f28f  xorps   xmm0, xmm0
0x18000f292  lea     rdi, [rcx+64h]
0x18000f296  movq    rax, xmm0
0x18000f29b  xor     esi, esi
0x18000f29d  mov     rbx, rcx
0x18000f2a0  cmp     [rdi], rax
0x18000f2a3  jnz     short loc_18000F2B5
0x18000f2a5  psrldq  xmm0, 8
0x18000f2aa  movq    rax, xmm0
0x18000f2af  cmp     [rdi+8], rax
0x18000f2b3  jz      short loc_18000F2BF
0x18000f2b5  mov     rcx, rdi; key
0x18000f2b8  call    DiscpRemovePolicy
0x18000f2bd  mov     esi, eax
0x18000f2bf  and     dword ptr [rbx+14h], 0FFFFFFFBh
0x18000f2c3  lea     rcx, DiscpCritSection; CriticalSection
0x18000f2ca  xorps   xmm0, xmm0
0x18000f2cd  movups  xmmword ptr [rdi], xmm0
0x18000f2d0  call    cs:__imp_RtlEnterCriticalSection
0x18000f2d6  or      edx, 0FFFFFFFFh
0x18000f2d9  lock xadd [rbx+10h], edx
0x18000f2de  cmp     edx, 1
0x18000f2e1  jnz     short loc_18000F2EB
0x18000f2e3  mov     rcx, rbx
0x18000f2e6  call    DiscpFreeTargetAddress
0x18000f2eb  lea     rcx, DiscpCritSection; CriticalSection
0x18000f2f2  call    cs:__imp_RtlLeaveCriticalSection
0x18000f2f8  mov     rbx, [rsp+28h+arg_0]
0x18000f2fd  mov     eax, esi
0x18000f2ff  mov     rsi, [rsp+28h+arg_8]
0x18000f304  add     rsp, 20h
0x18000f308  pop     rdi
0x18000f309  retn
```
