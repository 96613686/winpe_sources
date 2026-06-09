# winrt::Windows::Security::Cryptography::CryptographicBuffer::CreateFromByteArray(winrt::array_view<uchar const>)

- ea: `0x180019c04`
- end: `0x180019cb0`
- name: `?CreateFromByteArray@CryptographicBuffer@Cryptography@Security@Windows@winrt@@SA@U?$array_view@$$CBE@5@@Z`
- size: `172`
- prototype: `signed __int64 *__fastcall(signed __int64 *, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001e42c`
- `0x180027044`
- `0x180027230`
- `0x180028100`
- `0x1800296e4`

## callees

- `0x180010e04`
- `0x180015bec`
- `0x180019c04`
- `0x180033010`

## pseudocode

```c
signed __int64 *__fastcall winrt::Windows::Security::Cryptography::CryptographicBuffer::CreateFromByteArray(
        signed __int64 *a1,
        __int64 a2)
{
  __int64 v3; // r8
  int v4; // eax
  int v6; // [rsp+38h] [rbp-20h] BYREF
  __int128 v7; // [rsp+40h] [rbp-18h]
  __int64 *v8; // [rsp+68h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+70h] [rbp+18h]

  v8 = (__int64 *)a2;
  v9 = &qword_180043E68;
  v3 = 1;
  _InterlockedAdd64(&qword_180043E68, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics> )
  {
    v8 = 0;
    v6 = 0;
    v7 = 0;
    if ( *(_DWORD *)(a2 + 8) )
      v3 = *(_QWORD *)a2;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>
                                                                         + 72LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>,
           *(unsigned int *)(a2 + 8),
           v3,
           &v8);
    if ( v4 < 0 )
      winrt::throw_hresult((unsigned int)v4, &v6);
    *a1 = (signed __int64)v8;
    _InterlockedDecrement64(&qword_180043E68);
  }
  else
  {
    _InterlockedDecrement64(&qword_180043E68);
    winrt::impl::factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>::call<_lambda_68f4e1807e21da409e6a8eb51a4b2cb0_ &>(
      0,
      a1,
      &v8);
  }
  return a1;
}

```

## disassembly

```asm
0x180019c04  push    rbx
0x180019c06  sub     rsp, 50h
0x180019c0a  mov     rbx, rcx
0x180019c0d  mov     [rsp+58h+arg_8], rdx
0x180019c12  lea     rax, qword_180043E68
0x180019c19  mov     [rsp+58h+arg_10], rax
0x180019c1e  mov     r8d, 1
0x180019c24  lock add cs:qword_180043E68, r8
0x180019c2c  mov     rcx, cs:??$factory_cache_entry_v@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>::winrt::factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>
0x180019c33  test    rcx, rcx
0x180019c36  jz      short loc_180019C85
0x180019c38  mov     [rsp+58h+arg_8], 0
0x180019c41  mov     [rsp+58h+var_20], 0
0x180019c49  xorps   xmm0, xmm0
0x180019c4c  movdqu  [rsp+58h+var_18], xmm0
0x180019c52  mov     rax, [rcx]
0x180019c55  cmp     dword ptr [rdx+8], 0
0x180019c59  jz      short loc_180019C5E
0x180019c5b  mov     r8, [rdx]
0x180019c5e  lea     r9, [rsp+58h+arg_8]
0x180019c63  mov     edx, [rdx+8]
0x180019c66  mov     rax, [rax+48h]
0x180019c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c6f  test    eax, eax
0x180019c71  js      short loc_180019CA3
0x180019c73  mov     rax, [rsp+58h+arg_8]
0x180019c78  mov     [rbx], rax
0x180019c7b  lock dec cs:qword_180043E68
0x180019c83  jmp     short loc_180019C9A
0x180019c85  lock dec cs:qword_180043E68
0x180019c8d  lea     r8, [rsp+58h+arg_8]
0x180019c92  mov     rdx, rbx
0x180019c95  call    ??$call@AEAV_lambda_68f4e1807e21da409e6a8eb51a4b2cb0_@@@?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_68f4e1807e21da409e6a8eb51a4b2cb0_@@@Z
0x180019c9a  mov     rax, rbx
0x180019c9d  add     rsp, 50h
0x180019ca1  pop     rbx
0x180019ca2  retn
0x180019ca3  lea     rdx, [rsp+58h+var_20]
0x180019ca8  mov     ecx, eax
0x180019caa  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
