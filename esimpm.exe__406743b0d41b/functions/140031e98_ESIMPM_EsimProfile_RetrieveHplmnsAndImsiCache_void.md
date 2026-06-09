# ESIMPM::EsimProfile::RetrieveHplmnsAndImsiCache(void)

- ea: `0x140031e98`
- end: `0x140032114`
- name: `?RetrieveHplmnsAndImsiCache@EsimProfile@ESIMPM@@QEAAXXZ`
- size: `636`
- prototype: `void __fastcall(ESIMPM::EsimProfile *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x14002f214`

## callees

- `0x140002f60`
- `0x140003244`
- `0x14000327c`
- `0x14000dd20`
- `0x140013df8`
- `0x1400167fc`
- `0x140020620`
- `0x1400240fc`
- `0x1400304fc`
- `0x1400307e0`
- `0x14003110c`
- `0x140031e98`

## string_xrefs

- `0x140032034`: `ESIMPM::EsimProfile::RetrieveHplmnsAndImsiCache`
- `0x1400320b8`: `ESIMPM::EsimProfile::RetrieveHplmnsAndImsiCache`
- `0x1400320af`: `get imsi 0x%x : %s`
- `0x140031ee1`: `cache\`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ESIMPM::EsimProfile::RetrieveHplmnsAndImsiCache(ESIMPM::EsimProfile *this)
{
  unsigned __int64 v2; // r8
  _QWORD *v3; // rdx
  __m128i *v4; // rax
  __m128i v5; // xmm6
  __m128i v6; // xmm7
  void *v7; // rbx
  unsigned __int16 **v8; // rdx
  unsigned int Value; // eax
  __int64 v10; // r9
  const unsigned __int16 *v11; // rdx
  unsigned int v12; // eax
  void *v13; // rax
  __int64 v14; // r8
  unsigned __int16 **v15; // rdx
  unsigned int String; // esi
  __int64 v17; // r8
  _QWORD *v18; // rdi
  unsigned int *v19; // [rsp+28h] [rbp-59h]
  unsigned int v20[2]; // [rsp+48h] [rbp-39h] BYREF
  void *v21; // [rsp+50h] [rbp-31h]
  __int128 Src; // [rsp+58h] [rbp-29h] BYREF
  __m128i si128; // [rsp+68h] [rbp-19h]
  unsigned __int16 *v24[2]; // [rsp+78h] [rbp-9h] BYREF
  __m128i v25; // [rsp+88h] [rbp+7h]

  v20[0] = 0;
  Src = 0;
  si128 = 0;
  v2 = -1;
  do
    ++v2;
  while ( ESIMPM::strCache[v2] );
  std::wstring::_Construct<1,unsigned short const *>(&Src, L"cache\\", v2);
  v3 = (_QWORD *)((char *)this + 32);
  if ( *((_QWORD *)this + 7) > 7u )
    v3 = (_QWORD *)*v3;
  v4 = (__m128i *)std::wstring::_Append<unsigned short>(&Src, v3, *((_QWORD *)this + 6));
  v5 = *v4;
  *(__m128i *)v24 = *v4;
  v25 = v4[1];
  v6 = v25;
  v4->m128i_i16[0] = 0;
  v4[1].m128i_i64[0] = 0;
  v4[1].m128i_i64[1] = 7;
  std::wstring::_Tidy_deallocate((char **)&Src);
  v7 = 0;
  v21 = 0;
  v20[1] = 0;
  v8 = v24;
  if ( _mm_srli_si128(v6, 8).m128i_u64[0] > 7 )
    v8 = (unsigned __int16 **)v5.m128i_i64[0];
  Value = StateSeparation::GetValue(
            *((StateSeparation **)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120),
            (const unsigned __int16 *)v8,
            L"hplmns",
            8u,
            &v20[1],
            0,
            v20);
  v10 = Value;
  if ( !Value )
  {
    v7 = operator new[](v20[0], (const struct std::nothrow_t *)std::nothrow);
    v21 = v7;
    v11 = (const unsigned __int16 *)v24;
    if ( v25.m128i_i64[1] > 7uLL )
      v11 = v24[0];
    v12 = StateSeparation::GetValue(
            *((StateSeparation **)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120),
            v11,
            L"hplmns",
            8u,
            &v20[1],
            v7,
            v20);
    v10 = v12;
    if ( !v12 )
    {
      v13 = (void *)*((_QWORD *)this + 2);
      *((_QWORD *)this + 2) = v7;
      v7 = v13;
      v21 = v13;
      *((_DWORD *)this + 6) = v20[0];
      *((_DWORD *)this + 2) = 1;
    }
  }
  LODWORD(v19) = *((_DWORD *)this + 6);
  ESIMPM::Log::Info("ESIMPM::EsimProfile::RetrieveHplmnsAndImsiCache", 0, L"get hplmns 0x%x, size %d", v10, v19);
  ESIMPM::EsimProfile::OutputEFHPLMNwAct(this);
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  v15 = v24;
  if ( v25.m128i_i64[1] > 7uLL )
    v15 = (unsigned __int16 **)v24[0];
  String = StateSeparation::GetString(*((_QWORD *)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120), v15, v14, &Src);
  if ( !String )
    std::wstring::operator=((char **)this + 8, (char **)&Src, v17);
  v18 = (_QWORD *)((char *)this + 64);
  if ( v18[3] > 7u )
    v18 = (_QWORD *)*v18;
  ESIMPM::Log::Info("ESIMPM::EsimProfile::RetrieveHplmnsAndImsiCache", 0, L"get imsi 0x%x : %s", String, v18);
  std::wstring::_Tidy_deallocate((char **)&Src);
  if ( v7 )
    operator delete(v7);
  std::wstring::_Tidy_deallocate((char **)v24);
}

```

## disassembly

```asm
0x140031e98  mov     rax, rsp
0x140031e9b  mov     [rax+10h], rbx
0x140031e9f  mov     [rax+18h], rsi
0x140031ea3  push    rbp
0x140031ea4  push    rdi
0x140031ea5  push    r14
0x140031ea7  lea     rbp, [rax-5Fh]
0x140031eab  sub     rsp, 0C0h
0x140031eb2  movaps  xmmword ptr [rax-28h], xmm6
0x140031eb6  movaps  xmmword ptr [rax-38h], xmm7
0x140031eba  mov     rax, cs:__security_cookie
0x140031ec1  xor     rax, rsp
0x140031ec4  mov     [rbp+57h+var_40], rax
0x140031ec8  mov     rdi, rcx
0x140031ecb  xor     r14d, r14d
0x140031ece  mov     [rbp+57h+var_90], r14d
0x140031ed2  xorps   xmm0, xmm0
0x140031ed5  movups  [rbp+57h+Src], xmm0
0x140031ed9  xorps   xmm1, xmm1
0x140031edc  movdqu  [rbp+57h+var_70], xmm1
0x140031ee1  lea     rdx, ?strCache@ESIMPM@@3QBGB; "cache\\"
0x140031ee8  or      r8, 0FFFFFFFFFFFFFFFFh
0x140031eec  inc     r8
0x140031eef  cmp     [rdx+r8*2], r14w
0x140031ef4  jnz     short loc_140031EEC
0x140031ef6  lea     rcx, [rbp+57h+Src]
0x140031efa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140031eff  nop
0x140031f00  lea     rdx, [rdi+20h]
0x140031f04  mov     r8, [rdx+10h]
0x140031f08  cmp     qword ptr [rdx+18h], 7
0x140031f0d  jbe     short loc_140031F12
0x140031f0f  mov     rdx, [rdx]
0x140031f12  lea     rcx, [rbp+57h+Src]; Src
0x140031f16  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x140031f1b  movups  xmm6, xmmword ptr [rax]
0x140031f1e  movups  xmmword ptr [rbp+57h+var_60], xmm6
0x140031f22  movups  xmm7, xmmword ptr [rax+10h]
0x140031f26  movups  [rbp+57h+var_50], xmm7
0x140031f2a  mov     [rax], r14w
0x140031f2e  mov     [rax+10h], r14
0x140031f32  mov     qword ptr [rax+18h], 7
0x140031f3a  lea     rcx, [rbp+57h+Src]
0x140031f3e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140031f43  mov     rbx, r14
0x140031f46  mov     [rbp+57h+var_88], rbx
0x140031f4a  mov     [rbp+57h+var_90+4], r14d
0x140031f4e  mov     rax, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x140031f55  mov     rcx, [rax+3C0h]; this
0x140031f5c  lea     rdx, [rbp+57h+var_60]
0x140031f60  movq    r8, xmm6
0x140031f65  psrldq  xmm7, 8
0x140031f6a  movq    rax, xmm7
0x140031f6f  cmp     rax, 7
0x140031f73  cmova   rdx, r8; unsigned __int16 *
0x140031f77  lea     rax, [rbp+57h+var_90]
0x140031f7b  mov     [rsp+0D0h+var_A0], rax; unsigned int *
0x140031f80  mov     [rsp+0D0h+var_A8], r14; void *
0x140031f85  lea     rax, [rbp+57h+var_90+4]
0x140031f89  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x140031f8e  mov     esi, 8
0x140031f93  mov     r9d, esi; unsigned int
0x140031f96  lea     r8, ?strHplmns@ESIMPM@@3QBGB; "hplmns"
0x140031f9d  call    ?GetValue@StateSeparation@@QEAAKPEBG0KPEAKPEAX1@Z; StateSeparation::GetValue(ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x140031fa2  mov     r9d, eax
0x140031fa5  test    eax, eax
0x140031fa7  jnz     short loc_140032024
0x140031fa9  mov     ecx, [rbp+57h+var_90]; unsigned __int64
0x140031fac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140031fb3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140031fb8  mov     rbx, rax
0x140031fbb  mov     [rbp+57h+var_88], rax
0x140031fbf  mov     rax, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x140031fc6  lea     rdx, [rbp+57h+var_60]
0x140031fca  cmp     qword ptr [rbp+57h+var_50+8], 7
0x140031fcf  cmova   rdx, [rbp+57h+var_60]; unsigned __int16 *
0x140031fd4  lea     rcx, [rbp+57h+var_90]
0x140031fd8  mov     [rsp+0D0h+var_A0], rcx; unsigned int *
0x140031fdd  mov     [rsp+0D0h+var_A8], rbx; void *
0x140031fe2  lea     rcx, [rbp+57h+var_90+4]
0x140031fe6  mov     [rsp+0D0h+var_B0], rcx; unsigned int *
0x140031feb  mov     r9d, esi; unsigned int
0x140031fee  lea     r8, ?strHplmns@ESIMPM@@3QBGB; "hplmns"
0x140031ff5  mov     rcx, [rax+3C0h]; this
0x140031ffc  call    ?GetValue@StateSeparation@@QEAAKPEBG0KPEAKPEAX1@Z; StateSeparation::GetValue(ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x140032001  mov     r9d, eax
0x140032004  test    eax, eax
0x140032006  jnz     short loc_140032024
0x140032008  mov     rax, [rdi+10h]
0x14003200c  mov     [rdi+10h], rbx
0x140032010  mov     rbx, rax
0x140032013  mov     [rbp+57h+var_88], rax
0x140032017  mov     eax, [rbp+57h+var_90]
0x14003201a  mov     [rdi+18h], eax
0x14003201d  mov     dword ptr [rdi+8], 1
0x140032024  mov     eax, [rdi+18h]
0x140032027  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14003202b  lea     r8, aGetHplmns0xXSi; "get hplmns 0x%x, size %d"
0x140032032  xor     edx, edx; struct _GUID *
0x140032034  lea     rcx, aEsimpmEsimprof_2; "ESIMPM::EsimProfile::RetrieveHplmnsAndI"...
0x14003203b  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140032040  mov     rcx, rdi; this
0x140032043  call    ?OutputEFHPLMNwAct@EsimProfile@ESIMPM@@AEBAXXZ; ESIMPM::EsimProfile::OutputEFHPLMNwAct(void)
0x140032048  xorps   xmm0, xmm0
0x14003204b  movups  [rbp+57h+Src], xmm0
0x14003204f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140032057  movdqu  [rbp+57h+var_70], xmm1
0x14003205c  mov     word ptr [rbp+57h+Src], r14w
0x140032061  mov     rax, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x140032068  lea     rdx, [rbp+57h+var_60]
0x14003206c  cmp     qword ptr [rbp+57h+var_50+8], 7
0x140032071  cmova   rdx, [rbp+57h+var_60]
0x140032076  lea     r9, [rbp+57h+Src]
0x14003207a  mov     rcx, [rax+3C0h]
0x140032081  call    ?GetString@StateSeparation@@QEAAKPEBG0PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StateSeparation::GetString(ushort const *,ushort const *,std::wstring *)
0x140032086  mov     esi, eax
0x140032088  test    eax, eax
0x14003208a  jnz     short loc_140032099
0x14003208c  lea     rcx, [rdi+40h]
0x140032090  lea     rdx, [rbp+57h+Src]
0x140032094  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140032099  add     rdi, 40h ; '@'
0x14003209d  cmp     qword ptr [rdi+18h], 7
0x1400320a2  jbe     short loc_1400320A7
0x1400320a4  mov     rdi, [rdi]
0x1400320a7  mov     [rsp+0D0h+var_B0], rdi
0x1400320ac  mov     r9d, esi
0x1400320af  lea     r8, aGetImsi0xXS; "get imsi 0x%x : %s"
0x1400320b6  xor     edx, edx; struct _GUID *
0x1400320b8  lea     rcx, aEsimpmEsimprof_2; "ESIMPM::EsimProfile::RetrieveHplmnsAndI"...
0x1400320bf  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x1400320c4  nop
0x1400320c5  lea     rcx, [rbp+57h+Src]
0x1400320c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400320ce  nop
0x1400320cf  test    rbx, rbx
0x1400320d2  jz      short loc_1400320DD
0x1400320d4  mov     rcx, rbx; Block
0x1400320d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400320dc  nop
0x1400320dd  lea     rcx, [rbp+57h+var_60]
0x1400320e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400320e6  mov     rcx, [rbp+57h+var_40]
0x1400320ea  xor     rcx, rsp; StackCookie
0x1400320ed  call    __security_check_cookie
0x1400320f2  lea     r11, [rsp+0D0h+var_10]
0x1400320fa  mov     rbx, [r11+28h]
0x1400320fe  mov     rsi, [r11+30h]
0x140032102  movaps  xmm6, xmmword ptr [r11-10h]
0x140032107  movaps  xmm7, xmmword ptr [r11-20h]
0x14003210c  mov     rsp, r11
0x14003210f  pop     r14
0x140032111  pop     rdi
0x140032112  pop     rbp
0x140032113  retn
```
