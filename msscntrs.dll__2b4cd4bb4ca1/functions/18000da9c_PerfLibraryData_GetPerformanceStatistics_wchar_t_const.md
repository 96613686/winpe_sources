# PerfLibraryData::GetPerformanceStatistics(wchar_t const *)

- ea: `0x18000da9c`
- end: `0x18000dcc7`
- name: `?GetPerformanceStatistics@PerfLibraryData@@QEAAHPEB_W@Z`
- size: `555`
- prototype: `__int64 __fastcall(PerfLibraryData *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180010db0`

## callees

- `0x1800024a0`
- `0x18000da9c`
- `0x18000e55c`
- `0x18001067c`
- `0x18001085c`
- `0x18001353c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000db21`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc58`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc8c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000db21`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc58`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc8c`

## string_xrefs

- `0x18000dbef`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmcntrs\\pkmcntrs.cxx"`
- `0x18000dbfb`: `[UtilCommon] MSSCNTRS: found object %ls with no instances.`
- `0x18000dc1c`: `[UtilCommon] MSSCNTRS: found object %ls with %d instances.`

## pseudocode

```c
__int64 __fastcall PerfLibraryData::GetPerformanceStatistics(PerfLibraryData *this, const wchar_t *a2)
{
  int *v4; // rax
  int v5; // ecx
  __int64 v6; // rsi
  _QWORD *v7; // rbx
  const wchar_t *v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // [rsp+20h] [rbp-E0h]
  void **v14; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v15; // [rsp+38h] [rbp-C8h]
  __int64 v16; // [rsp+40h] [rbp-C0h]
  _WORD v17[68]; // [rsp+48h] [rbp-B8h] BYREF
  void **v18; // [rsp+D0h] [rbp-30h] BYREF
  void *Block; // [rsp+D8h] [rbp-28h]
  __int64 v20; // [rsp+E0h] [rbp-20h]
  _WORD v21[68]; // [rsp+E8h] [rbp-18h] BYREF

  Block = v21;
  v20 = 65;
  v21[0] = 0;
  v18 = &TLMString<64,64,32767>::`vftable';
  if ( (int)PerfNameToObjectName(a2, &v18) >= 0 && SharedMemory::OpenSharedMemory(this, (const wchar_t *)Block) )
  {
    v4 = (int *)*((_QWORD *)this + 1);
    v5 = *v4;
    *((_DWORD *)this + 4) = *v4;
    *((_QWORD *)this + 3) = v4 + 1;
    v6 = 0;
    if ( v5 )
    {
      do
      {
        v7 = (_QWORD *)((char *)this + 80 * v6);
        v8 = (const wchar_t *)(32LL * (unsigned int)v6 + *((_QWORD *)this + 3));
        v7[7] = v8;
        v15 = v17;
        v16 = 65;
        v17[0] = 0;
        v14 = &TLMString<64,64,32767>::`vftable';
        if ( (int)PerfNameToObjectName(v8, &v14) >= 0 && SharedMemory::OpenSharedMemory((SharedMemory *)(v7 + 4), v15) )
        {
          v9 = v7[5];
          v7[8] = v9;
          v7[9] = v9 + 64;
          v10 = v9 + 8 * (5LL * *(unsigned int *)(v9 + 32) + 8);
          v7[10] = v10;
          v7[11] = v10 + 4;
          if ( *(_DWORD *)(v9 + 40) == -1 )
          {
            SearchIndexerTrace::Verbose(
              (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
              (const wchar_t *)0xD4,
              (unsigned int)L"[UtilCommon] MSSCNTRS: found object %ls with no instances.",
              v8);
            v11 = 0;
            v12 = v7[10] + 8LL;
          }
          else
          {
            LODWORD(v13) = *(_DWORD *)(v9 + 40);
            SearchIndexerTrace::Verbose(
              (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
              (const wchar_t *)0xDB,
              (unsigned int)L"[UtilCommon] MSSCNTRS: found object %ls with %d instances.",
              v8,
              v13);
            v11 = v7[10] + 8LL;
            v12 = 0;
          }
          v7[12] = v12;
          v7[13] = v11;
        }
        v14 = &TLMString<64,64,32767>::`vftable';
        if ( v15 && v15 != v17 )
        {
          free(v15);
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
        }
        v6 = (unsigned int)(v6 + 1);
      }
      while ( (unsigned int)v6 < *((_DWORD *)this + 4) );
    }
    v18 = &TLMString<64,64,32767>::`vftable';
    if ( Block && Block != v21 )
    {
      free(Block);
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
    }
    return 1;
  }
  else
  {
    v18 = &TLMString<64,64,32767>::`vftable';
    if ( Block )
    {
      if ( Block != v21 )
      {
        free(Block);
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18000da9c  mov     [rsp-8+arg_10], rbx
0x18000daa1  push    rbp
0x18000daa2  push    rsi
0x18000daa3  push    rdi
0x18000daa4  push    r14
0x18000daa6  push    r15
0x18000daa8  lea     rbp, [rsp-80h]
0x18000daad  sub     rsp, 180h
0x18000dab4  mov     rax, cs:__security_cookie
0x18000dabb  xor     rax, rsp
0x18000dabe  mov     [rbp+0A0h+var_30], rax
0x18000dac2  mov     r8, rdx
0x18000dac5  mov     rdi, rcx
0x18000dac8  lea     rax, [rbp+0A0h+var_B8]
0x18000dacc  mov     [rbp+0A0h+Block], rax
0x18000dad0  mov     [rbp+0A0h+var_C0], 41h ; 'A'
0x18000dad8  xor     eax, eax
0x18000dada  mov     [rbp+0A0h+var_B8], ax
0x18000dade  lea     r15, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x18000dae5  mov     [rbp+0A0h+var_D0], r15
0x18000dae9  lea     rdx, [rbp+0A0h+var_D0]
0x18000daed  mov     rcx, r8
0x18000daf0  call    ?PerfNameToObjectName@@YAJPEB_WAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z; PerfNameToObjectName(wchar_t const *,TLMString<64,64,32767> &)
0x18000daf5  test    eax, eax
0x18000daf7  jns     short loc_18000DAFB
0x18000daf9  jmp     short loc_18000DB0B
0x18000dafb  mov     rdx, [rbp+0A0h+Block]; wchar_t *
0x18000daff  mov     rcx, rdi; this
0x18000db02  call    ?OpenSharedMemory@SharedMemory@@QEAAHPEB_W@Z; SharedMemory::OpenSharedMemory(wchar_t const *)
0x18000db07  test    eax, eax
0x18000db09  jnz     short loc_18000DB3B
0x18000db0b  mov     rcx, [rbp+0A0h+Block]; Block
0x18000db0f  test    rcx, rcx
0x18000db12  mov     [rbp+0A0h+var_D0], r15
0x18000db16  jz      short loc_18000DB34
0x18000db18  lea     rax, [rbp+0A0h+var_B8]
0x18000db1c  cmp     rcx, rax
0x18000db1f  jz      short loc_18000DB34
0x18000db21  call    cs:__imp_free
0x18000db27  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56494824@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824> `wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl(void)'::`2'::impl
0x18000db2e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)
0x18000db33  nop
0x18000db34  xor     eax, eax
0x18000db36  jmp     loc_18000DCA4
0x18000db3b  mov     rax, [rdi+8]
0x18000db3f  mov     ecx, [rax]
0x18000db41  mov     [rdi+10h], ecx
0x18000db44  add     rax, 4
0x18000db48  mov     [rdi+18h], rax
0x18000db4c  xor     esi, esi
0x18000db4e  test    ecx, ecx
0x18000db50  jz      loc_18000DC76
0x18000db56  mov     ecx, esi
0x18000db58  lea     rbx, [rsi+rsi*4]
0x18000db5c  shl     rbx, 4
0x18000db60  add     rbx, rdi
0x18000db63  shl     rcx, 5
0x18000db67  mov     r14, [rdi+18h]
0x18000db6b  add     r14, rcx
0x18000db6e  mov     [rbx+38h], r14
0x18000db72  lea     rax, [rsp+1A0h+var_158]
0x18000db77  mov     [rsp+1A0h+var_168], rax
0x18000db7c  mov     [rsp+1A0h+var_160], 41h ; 'A'
0x18000db85  xor     eax, eax
0x18000db87  mov     [rsp+1A0h+var_158], ax
0x18000db8c  mov     [rsp+1A0h+var_170], r15
0x18000db91  lea     rdx, [rsp+1A0h+var_170]
0x18000db96  mov     rcx, r14
0x18000db99  call    ?PerfNameToObjectName@@YAJPEB_WAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z; PerfNameToObjectName(wchar_t const *,TLMString<64,64,32767> &)
0x18000db9e  test    eax, eax
0x18000dba0  jns     short loc_18000DBA7
0x18000dba2  jmp     loc_18000DC3F
0x18000dba7  mov     rdx, [rsp+1A0h+var_168]; wchar_t *
0x18000dbac  lea     rcx, [rbx+20h]; this
0x18000dbb0  call    ?OpenSharedMemory@SharedMemory@@QEAAHPEB_W@Z; SharedMemory::OpenSharedMemory(wchar_t const *)
0x18000dbb5  test    eax, eax
0x18000dbb7  jnz     short loc_18000DBBE
0x18000dbb9  jmp     loc_18000DC3F
0x18000dbbe  mov     rdx, [rbx+28h]
0x18000dbc2  mov     [rbx+40h], rdx
0x18000dbc6  lea     rax, [rdx+40h]
0x18000dbca  mov     [rbx+48h], rax
0x18000dbce  mov     eax, [rdx+20h]
0x18000dbd1  lea     rax, [rax+rax*4]
0x18000dbd5  lea     rax, [rax+8]
0x18000dbd9  lea     rax, [rdx+rax*8]
0x18000dbdd  mov     [rbx+50h], rax
0x18000dbe1  add     rax, 4
0x18000dbe5  mov     [rbx+58h], rax
0x18000dbe9  mov     eax, [rdx+28h]
0x18000dbec  mov     r9, r14; wchar_t *
0x18000dbef  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000dbf6  cmp     eax, 0FFFFFFFFh
0x18000dbf9  jnz     short loc_18000DC18
0x18000dbfb  lea     r8, aUtilcommonMssc; "[UtilCommon] MSSCNTRS: found object %ls"...
0x18000dc02  mov     edx, 0D4h; wchar_t *
0x18000dc07  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000dc0c  xor     ecx, ecx
0x18000dc0e  mov     rax, [rbx+50h]
0x18000dc12  add     rax, 8
0x18000dc16  jmp     short loc_18000DC37
0x18000dc18  mov     [rsp+1A0h+var_180], eax
0x18000dc1c  lea     r8, aUtilcommonMssc_0; "[UtilCommon] MSSCNTRS: found object %ls"...
0x18000dc23  mov     edx, 0DBh; wchar_t *
0x18000dc28  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000dc2d  mov     rcx, [rbx+50h]
0x18000dc31  add     rcx, 8
0x18000dc35  xor     eax, eax
0x18000dc37  mov     [rbx+60h], rax
0x18000dc3b  mov     [rbx+68h], rcx
0x18000dc3f  mov     rcx, [rsp+1A0h+var_168]; Block
0x18000dc44  mov     [rsp+1A0h+var_170], r15
0x18000dc49  test    rcx, rcx
0x18000dc4c  jz      short loc_18000DC6B
0x18000dc4e  lea     rax, [rsp+1A0h+var_158]
0x18000dc53  cmp     rcx, rax
0x18000dc56  jz      short loc_18000DC6B
0x18000dc58  call    cs:__imp_free
0x18000dc5e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56494824@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824> `wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl(void)'::`2'::impl
0x18000dc65  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)
0x18000dc6a  nop
0x18000dc6b  inc     esi
0x18000dc6d  cmp     esi, [rdi+10h]
0x18000dc70  jb      loc_18000DB56
0x18000dc76  mov     [rbp+0A0h+var_D0], r15
0x18000dc7a  mov     rcx, [rbp+0A0h+Block]; Block
0x18000dc7e  test    rcx, rcx
0x18000dc81  jz      short loc_18000DC9F
0x18000dc83  lea     rdx, [rbp+0A0h+var_B8]
0x18000dc87  cmp     rcx, rdx
0x18000dc8a  jz      short loc_18000DC9F
0x18000dc8c  call    cs:__imp_free
0x18000dc92  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56494824@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824> `wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl(void)'::`2'::impl
0x18000dc99  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)
0x18000dc9e  nop
0x18000dc9f  mov     eax, 1
0x18000dca4  mov     rcx, [rbp+0A0h+var_30]
0x18000dca8  xor     rcx, rsp; StackCookie
0x18000dcab  call    __security_check_cookie
0x18000dcb0  mov     rbx, [rsp+1A0h+arg_10]
0x18000dcb8  add     rsp, 180h
0x18000dcbf  pop     r15
0x18000dcc1  pop     r14
0x18000dcc3  pop     rdi
0x18000dcc4  pop     rsi
0x18000dcc5  pop     rbp
0x18000dcc6  retn
```
