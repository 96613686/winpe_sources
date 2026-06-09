# ESIMPM::EsimProfile::CleanupCache(void)

- ea: `0x14002f9e0`
- end: `0x14002fb43`
- name: `?CleanupCache@EsimProfile@ESIMPM@@QEAAXXZ`
- size: `355`
- prototype: `void __fastcall(ESIMPM::EsimProfile *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14003154c`

## callees

- `0x140002f60`
- `0x140003244`
- `0x14000dd20`
- `0x140013df8`
- `0x1400167fc`
- `0x140020620`
- `0x14002f9e0`
- `0x14002fc08`

## string_xrefs

- `0x14002facb`: `esim profile id %s, CleanupCache 0x%x`
- `0x14002fad4`: `ESIMPM::EsimProfile::CleanupCache`
- `0x14002fa20`: `cache\`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ESIMPM::EsimProfile::CleanupCache(ESIMPM::EsimProfile *this)
{
  __int64 v2; // r8
  _QWORD *v3; // rbx
  __int64 v4; // rax
  __int128 v5; // xmm6
  __m128i v6; // xmm7
  const unsigned __int16 *v7; // rdx
  int v8; // eax
  void *v9; // rcx
  _QWORD *v10; // rcx
  _OWORD Src[2]; // [rsp+38h] [rbp-70h] BYREF
  __int128 v12; // [rsp+58h] [rbp-50h] BYREF
  __m128i v13; // [rsp+68h] [rbp-40h]

  memset(Src, 0, sizeof(Src));
  v2 = -1;
  do
    ++v2;
  while ( ESIMPM::strCache[v2] );
  std::wstring::_Construct<1,unsigned short const *>(Src, L"cache\\");
  v3 = (_QWORD *)((char *)this + 32);
  v4 = std::wstring::_Append<unsigned short>(Src);
  v5 = *(_OWORD *)v4;
  v12 = *(_OWORD *)v4;
  v13 = *(__m128i *)(v4 + 16);
  v6 = v13;
  *(_WORD *)v4 = 0;
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = 7;
  std::wstring::_Tidy_deallocate(Src);
  v7 = (const unsigned __int16 *)&v12;
  if ( _mm_srli_si128(v6, 8).m128i_u64[0] > 7 )
    v7 = (const unsigned __int16 *)v5;
  v8 = StateSeparation::DeleteTree(*((StateSeparation **)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120), v7);
  if ( *((_QWORD *)this + 7) > 7u )
    v3 = (_QWORD *)*v3;
  ESIMPM::Log::Info("ESIMPM::EsimProfile::CleanupCache", 0, L"esim profile id %s, CleanupCache 0x%x", v3, v8);
  *((_DWORD *)this + 2) = 0;
  v9 = (void *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v9 )
    operator delete(v9);
  v10 = (_QWORD *)((char *)this + 64);
  *((_QWORD *)this + 10) = 0;
  if ( *((_QWORD *)this + 11) > 7u )
    v10 = (_QWORD *)*v10;
  *(_WORD *)v10 = 0;
  *((_DWORD *)this + 6) = 0;
  std::wstring::_Tidy_deallocate(&v12);
}

```

## disassembly

```asm
0x14002f9e0  mov     rax, rsp
0x14002f9e3  mov     [rax+10h], rbx
0x14002f9e7  mov     [rax+18h], rsi
0x14002f9eb  push    rdi
0x14002f9ec  sub     rsp, 0A0h
0x14002f9f3  movaps  xmmword ptr [rax-18h], xmm6
0x14002f9f7  movaps  xmmword ptr [rax-28h], xmm7
0x14002f9fb  mov     rax, cs:__security_cookie
0x14002fa02  xor     rax, rsp
0x14002fa05  mov     [rsp+0A8h+var_30], rax
0x14002fa0a  mov     rdi, rcx
0x14002fa0d  xor     esi, esi
0x14002fa0f  xorps   xmm0, xmm0
0x14002fa12  movups  [rsp+0A8h+Src], xmm0
0x14002fa17  xorps   xmm1, xmm1
0x14002fa1a  movdqu  [rsp+0A8h+var_60], xmm1
0x14002fa20  lea     rdx, ?strCache@ESIMPM@@3QBGB; "cache\\"
0x14002fa27  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002fa2b  inc     r8
0x14002fa2e  cmp     [rdx+r8*2], si
0x14002fa33  jnz     short loc_14002FA2B
0x14002fa35  lea     rcx, [rsp+0A8h+Src]
0x14002fa3a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002fa3f  nop
0x14002fa40  lea     rbx, [rdi+20h]
0x14002fa44  cmp     qword ptr [rbx+18h], 7
0x14002fa49  jbe     short loc_14002FA50
0x14002fa4b  mov     rdx, [rbx]
0x14002fa4e  jmp     short loc_14002FA53
0x14002fa50  mov     rdx, rbx
0x14002fa53  mov     r8, [rbx+10h]
0x14002fa57  lea     rcx, [rsp+0A8h+Src]; Src
0x14002fa5c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x14002fa61  movups  xmm6, xmmword ptr [rax]
0x14002fa64  movups  [rsp+0A8h+var_50], xmm6
0x14002fa69  movups  xmm7, xmmword ptr [rax+10h]
0x14002fa6d  movups  [rsp+0A8h+var_40], xmm7
0x14002fa72  mov     [rax], si
0x14002fa75  mov     [rax+10h], rsi
0x14002fa79  mov     qword ptr [rax+18h], 7
0x14002fa81  lea     rcx, [rsp+0A8h+Src]
0x14002fa86  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002fa8b  mov     rax, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x14002fa92  mov     rcx, [rax+3C0h]; this
0x14002fa99  lea     rdx, [rsp+0A8h+var_50]
0x14002fa9e  movq    r8, xmm6
0x14002faa3  psrldq  xmm7, 8
0x14002faa8  movq    rax, xmm7
0x14002faad  cmp     rax, 7
0x14002fab1  cmova   rdx, r8; unsigned __int16 *
0x14002fab5  call    ?DeleteTree@StateSeparation@@QEAAKPEBG@Z; StateSeparation::DeleteTree(ushort const *)
0x14002faba  cmp     qword ptr [rbx+18h], 7
0x14002fabf  jbe     short loc_14002FAC4
0x14002fac1  mov     rbx, [rbx]
0x14002fac4  mov     [rsp+0A8h+var_88], eax
0x14002fac8  mov     r9, rbx
0x14002facb  lea     r8, aEsimProfileIdS_0; "esim profile id %s, CleanupCache 0x%x"
0x14002fad2  xor     edx, edx; struct _GUID *
0x14002fad4  lea     rcx, aEsimpmEsimprof; "ESIMPM::EsimProfile::CleanupCache"
0x14002fadb  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002fae0  mov     [rdi+8], esi
0x14002fae3  mov     rcx, [rdi+10h]; Block
0x14002fae7  mov     [rdi+10h], rsi
0x14002faeb  test    rcx, rcx
0x14002faee  jz      short loc_14002FAF5
0x14002faf0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002faf5  lea     rcx, [rdi+40h]
0x14002faf9  mov     [rcx+10h], rsi
0x14002fafd  cmp     qword ptr [rcx+18h], 7
0x14002fb02  jbe     short loc_14002FB07
0x14002fb04  mov     rcx, [rcx]
0x14002fb07  mov     [rcx], si
0x14002fb0a  mov     [rdi+18h], esi
0x14002fb0d  lea     rcx, [rsp+0A8h+var_50]
0x14002fb12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002fb17  mov     rcx, [rsp+0A8h+var_30]
0x14002fb1c  xor     rcx, rsp; StackCookie
0x14002fb1f  call    __security_check_cookie
0x14002fb24  lea     r11, [rsp+0A8h+var_8]
0x14002fb2c  mov     rbx, [r11+18h]
0x14002fb30  mov     rsi, [r11+20h]
0x14002fb34  movaps  xmm6, xmmword ptr [r11-10h]
0x14002fb39  movaps  xmm7, xmmword ptr [r11-20h]
0x14002fb3e  mov     rsp, r11
0x14002fb41  pop     rdi
0x14002fb42  retn
```
