# DeleteIPSECPolicy

- ea: `0x1800a5950`
- end: `0x1800a5a10`
- name: `DeleteIPSECPolicy`
- size: `192`
- prototype: `__int64 __fastcall(GUID *key)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800a45d0`
- `0x1800a4674`
- `0x1800a5890`

## callees

- `0x1800a5950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a5971`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a5971`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a5a04`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x1800a59ad`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x1800a59d9`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x1800a59ad`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x1800a59d9`

## pseudocode

```c
void __fastcall DeleteIPSECPolicy(GUID *key)
{
  unsigned __int64 v2; // xmm0_8
  unsigned __int64 v3; // rax
  unsigned __int64 v4; // rbx

  AcquireSRWLockShared(&stru_180111D48);
  v2 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  v3 = -*(_QWORD *)&key->Data1;
  if ( !*(_QWORD *)&key->Data1 )
    v3 = v2 - *(_QWORD *)key->Data4;
  if ( v3 )
  {
    FwpmProviderContextDeleteByKey0(engineHandle, key);
    *key = 0;
  }
  v4 = -*(_QWORD *)&key[1].Data1;
  if ( !*(_QWORD *)&key[1].Data1 )
    v4 = v2 - *(_QWORD *)key[1].Data4;
  if ( v4 )
  {
    FwpmProviderContextDeleteByKey0(engineHandle, key + 1);
    *key = 0;
  }
  ReleaseSRWLockShared(&stru_180111D48);
}

```

## disassembly

```asm
0x1800a5950  mov     [rsp+arg_0], rbx
0x1800a5955  mov     [rsp+arg_8], rsi
0x1800a595a  push    rdi
0x1800a595b  sub     rsp, 30h
0x1800a595f  mov     rdi, rcx
0x1800a5962  movaps  [rsp+38h+var_18], xmm6
0x1800a5967  lea     rcx, stru_180111D48; SRWLock
0x1800a596e  xorps   xmm6, xmm6
0x1800a5971  call    cs:__imp_AcquireSRWLockShared
0x1800a5978  nop     dword ptr [rax+rax+00h]
0x1800a597d  movq    rbx, xmm6
0x1800a5982  xorps   xmm0, xmm0
0x1800a5985  mov     rax, rbx
0x1800a5988  psrldq  xmm0, 8
0x1800a598d  movq    rsi, xmm0
0x1800a5992  sub     rax, [rdi]
0x1800a5995  jnz     short loc_1800A599E
0x1800a5997  mov     rax, rsi
0x1800a599a  sub     rax, [rdi+8]
0x1800a599e  test    rax, rax
0x1800a59a1  jz      short loc_1800A59BD
0x1800a59a3  mov     rcx, cs:engineHandle; engineHandle
0x1800a59aa  mov     rdx, rdi; key
0x1800a59ad  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x1800a59b4  nop     dword ptr [rax+rax+00h]
0x1800a59b9  movdqu  xmmword ptr [rdi], xmm6
0x1800a59bd  lea     rdx, [rdi+10h]; key
0x1800a59c1  sub     rbx, [rdx]
0x1800a59c4  jnz     short loc_1800A59CD
0x1800a59c6  mov     rbx, rsi
0x1800a59c9  sub     rbx, [rdx+8]
0x1800a59cd  test    rbx, rbx
0x1800a59d0  jz      short loc_1800A59E9
0x1800a59d2  mov     rcx, cs:engineHandle; engineHandle
0x1800a59d9  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x1800a59e0  nop     dword ptr [rax+rax+00h]
0x1800a59e5  movdqu  xmmword ptr [rdi], xmm6
0x1800a59e9  lea     rcx, stru_180111D48
0x1800a59f0  mov     rbx, [rsp+38h+arg_0]
0x1800a59f5  mov     rsi, [rsp+38h+arg_8]
0x1800a59fa  movaps  xmm6, [rsp+38h+var_18]
0x1800a59ff  add     rsp, 30h
0x1800a5a03  pop     rdi
0x1800a5a04  jmp     cs:__imp_ReleaseSRWLockShared
```
