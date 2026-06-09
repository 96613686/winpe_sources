# ESIMPM::EsimProfile::SetHplmns(_WWAN_UICCCARD_EF_FILE_INFO *,ulong)

- ea: `0x140032218`
- end: `0x14003242c`
- name: `?SetHplmns@EsimProfile@ESIMPM@@QEAAXPEAU_WWAN_UICCCARD_EF_FILE_INFO@@K@Z`
- size: `532`
- prototype: `void __fastcall(ESIMPM::EsimProfile *__hidden this, struct _WWAN_UICCCARD_EF_FILE_INFO *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x14003211c`

## callees

- `0x140002f60`
- `0x140003244`
- `0x14000327c`
- `0x14000dd20`
- `0x140013df8`
- `0x1400143c8`
- `0x140014f64`
- `0x1400167fc`
- `0x140020620`
- `0x14003110c`
- `0x140032218`
- `0x14003287c`

## string_xrefs

- `0x140032252`: `cache\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ESIMPM::EsimProfile::SetHplmns(
        ESIMPM::EsimProfile *this,
        struct _WWAN_UICCCARD_EF_FILE_INFO *a2,
        unsigned int a3)
{
  unsigned __int64 v6; // r8
  _QWORD *v7; // rdx
  _QWORD *v8; // rax
  unsigned int v9; // eax
  void *v10; // rax
  void *v11; // rcx
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // eax
  void *v14; // rcx
  const unsigned __int16 *v15; // rdx
  unsigned __int16 *v16[2]; // [rsp+38h] [rbp-48h] BYREF
  __int128 v17; // [rsp+48h] [rbp-38h]
  _OWORD Src[2]; // [rsp+58h] [rbp-28h] BYREF

  memset(Src, 0, sizeof(Src));
  v6 = -1;
  do
    ++v6;
  while ( ESIMPM::strCache[v6] );
  std::wstring::_Construct<1,unsigned short const *>(Src, L"cache\\", v6);
  v7 = (_QWORD *)((char *)this + 32);
  if ( *((_QWORD *)this + 7) > 7u )
    v7 = (_QWORD *)*v7;
  v8 = std::wstring::_Append<unsigned short>(Src, v7, *((_QWORD *)this + 6));
  *(_OWORD *)v16 = *(_OWORD *)v8;
  v17 = *((_OWORD *)v8 + 1);
  *(_WORD *)v8 = 0;
  v8[2] = 0;
  v8[3] = 7;
  std::wstring::_Tidy_deallocate((char **)Src);
  if ( a2 && a3 )
  {
    v9 = *((_DWORD *)a2 + 2);
    if ( a3 > v9 && v9 )
    {
      v10 = operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
      v11 = (void *)*((_QWORD *)this + 2);
      *((_QWORD *)this + 2) = v10;
      if ( v11 )
        operator delete(v11);
      memcpy_s(*((void *const *)this + 2), *((unsigned int *)a2 + 2), (char *)a2 + 12, *((unsigned int *)a2 + 2));
      *((_DWORD *)this + 6) = *((_DWORD *)a2 + 2);
      *((_DWORD *)this + 2) = 2;
      v12 = (const unsigned __int16 *)v16;
      if ( *((_QWORD *)&v17 + 1) > 7u )
        v12 = v16[0];
      v13 = StateSeparation::SetValue(
              *((StateSeparation **)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120),
              v12,
              L"hplmns",
              3u,
              (const unsigned __int8 *)a2 + 12,
              *((_DWORD *)a2 + 2));
      ESIMPM::Log::Info("ESIMPM::EsimProfile::SetHplmns", 0, L"ret 0x%x", v13);
      ESIMPM::EsimProfile::OutputEFHPLMNwAct(this);
    }
    else
    {
      ESIMPM::Log::Error(
        "ESIMPM::EsimProfile::SetHplmns",
        0,
        L"wrong size, dwSize %d, pEFFileInfo->len %d, return",
        a3,
        *((_DWORD *)a2 + 2));
    }
  }
  else
  {
    v14 = (void *)*((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = 0;
    if ( v14 )
      operator delete(v14);
    *((_DWORD *)this + 6) = 0;
    *((_DWORD *)this + 2) = 2;
    v15 = (const unsigned __int16 *)v16;
    if ( *((_QWORD *)&v17 + 1) > 7u )
      v15 = v16[0];
    StateSeparation::SetValue(*((StateSeparation **)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120), v15, L"hplmns", 3u, 0, 0);
    ESIMPM::Log::Info("ESIMPM::EsimProfile::SetHplmns", 0, L"%s hplmns size 0", *(_QWORD *)this + 12LL);
  }
  std::wstring::_Tidy_deallocate((char **)v16);
}

```

## disassembly

```asm
0x140032218  push    rbp
0x14003221a  push    rbx
0x14003221b  push    rsi
0x14003221c  push    rdi
0x14003221d  push    r14
0x14003221f  mov     rbp, rsp
0x140032222  sub     rsp, 80h
0x140032229  mov     rax, cs:__security_cookie
0x140032230  xor     rax, rsp
0x140032233  mov     [rbp+var_8], rax
0x140032237  mov     ebx, r8d
0x14003223a  mov     rsi, rdx
0x14003223d  mov     rdi, rcx
0x140032240  xor     r14d, r14d
0x140032243  xorps   xmm0, xmm0
0x140032246  movups  [rbp+Src], xmm0
0x14003224a  xorps   xmm1, xmm1
0x14003224d  movdqu  [rbp+var_18], xmm1
0x140032252  lea     rdx, ?strCache@ESIMPM@@3QBGB; "cache\\"
0x140032259  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003225d  inc     r8
0x140032260  cmp     [rdx+r8*2], r14w
0x140032265  jnz     short loc_14003225D
0x140032267  lea     rcx, [rbp+Src]
0x14003226b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140032270  nop
0x140032271  lea     rdx, [rdi+20h]
0x140032275  mov     r8, [rdx+10h]
0x140032279  cmp     qword ptr [rdx+18h], 7
0x14003227e  jbe     short loc_140032283
0x140032280  mov     rdx, [rdx]
0x140032283  lea     rcx, [rbp+Src]; Src
0x140032287  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x14003228c  movups  xmm0, xmmword ptr [rax]
0x14003228f  movups  xmmword ptr [rbp+var_48], xmm0
0x140032293  movups  xmm1, xmmword ptr [rax+10h]
0x140032297  movups  [rbp+var_38], xmm1
0x14003229b  mov     [rax], r14w
0x14003229f  mov     [rax+10h], r14
0x1400322a3  mov     qword ptr [rax+18h], 7
0x1400322ab  lea     rcx, [rbp+Src]
0x1400322af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400322b4  test    rsi, rsi
0x1400322b7  jz      loc_140032398
0x1400322bd  test    ebx, ebx
0x1400322bf  jz      loc_140032398
0x1400322c5  mov     eax, [rsi+8]
0x1400322c8  cmp     ebx, eax
0x1400322ca  jbe     loc_14003237A
0x1400322d0  test    eax, eax
0x1400322d2  jz      loc_14003237A
0x1400322d8  mov     ecx, eax; unsigned __int64
0x1400322da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400322e1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400322e6  mov     rcx, [rdi+10h]; Block
0x1400322ea  mov     [rdi+10h], rax
0x1400322ee  test    rcx, rcx
0x1400322f1  jz      short loc_1400322F8
0x1400322f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400322f8  mov     edx, [rsi+8]; DestinationSize
0x1400322fb  lea     rbx, [rsi+0Ch]
0x1400322ff  mov     r9d, edx; SourceSize
0x140032302  mov     r8, rbx; Source
0x140032305  mov     rcx, [rdi+10h]; Destination
0x140032309  call    memcpy_s
0x14003230e  mov     eax, [rsi+8]
0x140032311  mov     [rdi+18h], eax
0x140032314  mov     dword ptr [rdi+8], 2
0x14003231b  mov     rax, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x140032322  mov     rcx, [rax+3C0h]; this
0x140032329  mov     eax, [rsi+8]
0x14003232c  lea     rdx, [rbp+var_48]
0x140032330  cmp     qword ptr [rbp+var_38+8], 7
0x140032335  cmova   rdx, [rbp+var_48]; unsigned __int16 *
0x14003233a  mov     [rsp+80h+var_58], eax; unsigned int
0x14003233e  mov     [rsp+80h+var_60], rbx; unsigned __int8 *
0x140032343  mov     r9d, 3; unsigned int
0x140032349  lea     r8, ?strHplmns@ESIMPM@@3QBGB; "hplmns"
0x140032350  call    ?SetValue@StateSeparation@@QEAAKPEBG0KPEBEK@Z; StateSeparation::SetValue(ushort const *,ushort const *,ulong,uchar const *,ulong)
0x140032355  mov     r9d, eax
0x140032358  lea     r8, aRet0xX; "ret 0x%x"
0x14003235f  xor     edx, edx; struct _GUID *
0x140032361  lea     rcx, aEsimpmEsimprof_4; "ESIMPM::EsimProfile::SetHplmns"
0x140032368  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14003236d  mov     rcx, rdi; this
0x140032370  call    ?OutputEFHPLMNwAct@EsimProfile@ESIMPM@@AEBAXXZ; ESIMPM::EsimProfile::OutputEFHPLMNwAct(void)
0x140032375  jmp     loc_140032409
0x14003237a  mov     dword ptr [rsp+80h+var_60], eax
0x14003237e  mov     r9d, ebx
0x140032381  lea     r8, aWrongSizeDwsiz; "wrong size, dwSize %d, pEFFileInfo->len"...
0x140032388  xor     edx, edx; struct _GUID *
0x14003238a  lea     rcx, aEsimpmEsimprof_4; "ESIMPM::EsimProfile::SetHplmns"
0x140032391  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x140032396  jmp     short loc_140032409
0x140032398  mov     rcx, [rdi+10h]; Block
0x14003239c  mov     [rdi+10h], r14
0x1400323a0  test    rcx, rcx
0x1400323a3  jz      short loc_1400323AA
0x1400323a5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400323aa  mov     [rdi+18h], r14d
0x1400323ae  mov     dword ptr [rdi+8], 2
0x1400323b5  mov     rax, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x1400323bc  lea     rdx, [rbp+var_48]
0x1400323c0  cmp     qword ptr [rbp+var_38+8], 7
0x1400323c5  cmova   rdx, [rbp+var_48]; unsigned __int16 *
0x1400323ca  mov     [rsp+80h+var_58], r14d; unsigned int
0x1400323cf  mov     [rsp+80h+var_60], r14; unsigned __int8 *
0x1400323d4  mov     r9d, 3; unsigned int
0x1400323da  lea     r8, ?strHplmns@ESIMPM@@3QBGB; "hplmns"
0x1400323e1  mov     rcx, [rax+3C0h]; this
0x1400323e8  call    ?SetValue@StateSeparation@@QEAAKPEBG0KPEBEK@Z; StateSeparation::SetValue(ushort const *,ushort const *,ulong,uchar const *,ulong)
0x1400323ed  mov     r9, [rdi]
0x1400323f0  add     r9, 0Ch
0x1400323f4  lea     r8, aSHplmnsSize0; "%s hplmns size 0"
0x1400323fb  xor     edx, edx; struct _GUID *
0x1400323fd  lea     rcx, aEsimpmEsimprof_4; "ESIMPM::EsimProfile::SetHplmns"
0x140032404  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140032409  lea     rcx, [rbp+var_48]
0x14003240d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140032412  mov     rcx, [rbp+var_8]
0x140032416  xor     rcx, rsp; StackCookie
0x140032419  call    __security_check_cookie
0x14003241e  add     rsp, 80h
0x140032425  pop     r14
0x140032427  pop     rdi
0x140032428  pop     rsi
0x140032429  pop     rbx
0x14003242a  pop     rbp
0x14003242b  retn
```
