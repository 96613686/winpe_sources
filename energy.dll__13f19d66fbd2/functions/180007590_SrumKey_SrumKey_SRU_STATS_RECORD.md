# SrumKey::SrumKey(_SRU_STATS_RECORD *)

- ea: `0x180007590`
- end: `0x1800077e3`
- name: `??0SrumKey@@QEAA@PEAU_SRU_STATS_RECORD@@@Z`
- size: `595`
- prototype: `SrumKey *__fastcall(SrumKey *__hidden this, struct _SRU_STATS_RECORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800523fc`

## callees

- `0x180007590`
- `0x1800087e8`
- `0x1800253e0`
- `0x18003bf74`
- `0x18004ce78`
- `0x18004d12c`
- `0x18004d194`
- `0x18004dea8`
- `0x1800867c0`
- `0x1800907f0`
- `0x180096010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18000762a`
- `ntdll!RtlCopySid` at `0x18000762a`
- `ntdll!RtlLengthSid` at `0x1800075ff`
- `ntdll!RtlLengthSid` at `0x1800075ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000760e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000760e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
SrumKey *__fastcall SrumKey::SrumKey(SrumKey *this, struct _SRU_STATS_RECORD *a2)
{
  __int64 v4; // rcx
  void *v5; // rbx
  ULONG v6; // esi
  HLOCAL v7; // rax
  __int64 *KeyData; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  volatile signed __int32 *v11; // rsi
  __int64 v12; // rbx
  int v13; // ecx
  __int64 v14; // rdx
  volatile signed __int32 *v16; // [rsp+28h] [rbp-40h]
  _QWORD pExceptionObject[4]; // [rsp+30h] [rbp-38h] BYREF

  *(_OWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  std::wstring::_Construct_empty(this);
  *(_QWORD *)(v4 + 32) = 0;
  *(_QWORD *)(v4 + 40) = 0;
  if ( dword_1800C8F30 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800C8F30);
    if ( dword_1800C8F30 == -1 )
    {
      anonymous_namespace_::SrumDataCache::SrumDataCache();
      atexit(``anonymous namespace'::SrumDataCache::GetInstance'::`2'::`dynamic atexit destructor for 'Instance'');
      Init_thread_footer(&dword_1800C8F30);
    }
  }
  v5 = (void *)*((_QWORD *)a2 + 5);
  v6 = RtlLengthSid(v5);
  v7 = LocalAlloc(0x40u, v6);
  if ( !v7 )
  {
    pExceptionObject[2] = 0;
    pExceptionObject[1] = "bad allocation";
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  RtlCopySid(v6, v7, v5);
  KeyData = (__int64 *)anonymous_namespace_::SrumDataCache::GetKeyData((_Mtx_t)&qword_1800C8F40);
  v9 = *KeyData;
  v10 = KeyData[1];
  *KeyData = 0;
  KeyData[1] = 0;
  *((_QWORD *)this + 4) = v9;
  v11 = (volatile signed __int32 *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v10;
  v12 = -1;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)())v16)();
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)())(*(_QWORD *)v16 + 8LL))();
    }
  }
  v13 = *((_DWORD *)a2 + 4);
  if ( v13 )
  {
    if ( (unsigned int)(v13 - 1) < 2 )
      std::wstring::assign(this, *((_QWORD *)a2 + 3));
    else
      std::wstring::assign(this, L"Unknown");
  }
  else
  {
    v14 = *((_QWORD *)a2 + 3);
    do
      ++v12;
    while ( *(_WORD *)(v14 + 2 * v12) );
    std::wstring::_Assign<unsigned short>(this, v14, v12);
  }
  return this;
}

```

## disassembly

```asm
0x180007590  mov     [rsp+arg_10], rbx
0x180007595  mov     [rsp+arg_18], rbp
0x18000759a  mov     [rsp+arg_0], rcx
0x18000759f  push    rsi
0x1800075a0  push    rdi
0x1800075a1  push    r14
0x1800075a3  sub     rsp, 50h
0x1800075a7  mov     rbp, rdx
0x1800075aa  mov     rdi, rcx
0x1800075ad  xor     r14d, r14d
0x1800075b0  xorps   xmm0, xmm0
0x1800075b3  movups  xmmword ptr [rcx], xmm0
0x1800075b6  mov     [rcx+10h], r14
0x1800075ba  mov     [rcx+18h], r14
0x1800075be  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800075c3  nop
0x1800075c4  mov     [rcx+20h], r14
0x1800075c8  mov     [rcx+28h], r14
0x1800075cc  mov     ecx, cs:_tls_index
0x1800075d2  mov     rax, gs:58h
0x1800075db  mov     edx, 4
0x1800075e0  mov     rax, [rax+rcx*8]
0x1800075e4  mov     eax, [rdx+rax]
0x1800075e7  cmp     cs:dword_1800C8F30, eax
0x1800075ed  jg      loc_180007705
0x1800075f3  mov     rbx, [rbp+28h]
0x1800075f7  mov     [rsp+68h+arg_8], r14
0x1800075fc  mov     rcx, rbx; Sid
0x1800075ff  call    cs:__imp_RtlLengthSid
0x180007605  mov     esi, eax
0x180007607  mov     edx, eax; uBytes
0x180007609  mov     ecx, 40h ; '@'; uFlags
0x18000760e  call    cs:__imp_LocalAlloc
0x180007614  mov     [rsp+68h+arg_8], rax
0x180007619  test    rax, rax
0x18000761c  jz      loc_1800076D3
0x180007622  mov     r8, rbx; SourceSid
0x180007625  mov     rdx, rax; DestinationSid
0x180007628  mov     ecx, esi; DestinationSidLength
0x18000762a  call    cs:__imp_RtlCopySid
0x180007630  lea     r8, [rsp+68h+arg_8]
0x180007635  lea     rdx, [rsp+68h+var_48]
0x18000763a  lea     rcx, qword_1800C8F40; _Mtx_t
0x180007641  call    _anonymous_namespace___SrumDataCache__GetKeyData
0x180007646  mov     rcx, [rax]
0x180007649  mov     rdx, [rax+8]
0x18000764d  mov     [rax], r14
0x180007650  mov     [rax+8], r14
0x180007654  mov     [rdi+20h], rcx
0x180007658  mov     rsi, [rdi+28h]
0x18000765c  mov     [rdi+28h], rdx
0x180007660  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180007667  test    rsi, rsi
0x18000766a  jz      short loc_18000767C
0x18000766c  mov     eax, ebx
0x18000766e  lock xadd [rsi+8], eax
0x180007673  cmp     eax, 1
0x180007676  jz      loc_180007741
0x18000767c  mov     rsi, [rsp+68h+var_40]
0x180007681  test    rsi, rsi
0x180007684  jz      short loc_180007696
0x180007686  mov     eax, ebx
0x180007688  lock xadd [rsi+8], eax
0x18000768d  cmp     eax, 1
0x180007690  jz      loc_180007773
0x180007696  mov     ecx, [rbp+10h]
0x180007699  test    ecx, ecx
0x18000769b  jnz     loc_1800077A5
0x1800076a1  mov     rdx, [rbp+18h]
0x1800076a5  inc     rbx
0x1800076a8  cmp     word ptr [rdx+rbx*2], 0
0x1800076ad  jnz     short loc_1800076A5
0x1800076af  mov     r8, rbx
0x1800076b2  mov     rcx, rdi
0x1800076b5  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800076ba  nop
0x1800076bb  mov     rax, rdi
0x1800076be  lea     r11, [rsp+68h+var_18]
0x1800076c3  mov     rbx, [r11+30h]
0x1800076c7  mov     rbp, [r11+38h]
0x1800076cb  mov     rsp, r11
0x1800076ce  pop     r14
0x1800076d0  pop     rdi
0x1800076d1  pop     rsi
0x1800076d2  retn
0x1800076d3  xorps   xmm0, xmm0
0x1800076d6  movups  [rsp+68h+var_30], xmm0
0x1800076db  lea     rax, aBadAllocation; "bad allocation"
0x1800076e2  mov     qword ptr [rsp+68h+var_30], rax
0x1800076e7  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800076ee  mov     [rsp+68h+pExceptionObject], rax
0x1800076f3  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800076fa  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800076ff  call    _CxxThrowException_0
0x180007705  lea     rcx, dword_1800C8F30
0x18000770c  call    _Init_thread_header
0x180007711  cmp     cs:dword_1800C8F30, 0FFFFFFFFh
0x180007718  jnz     loc_1800075F3
0x18000771e  call    _anonymous_namespace___SrumDataCache__SrumDataCache
0x180007723  lea     rcx, ??__FInstance@?1??GetInstance@SrumDataCache@?A0xf40bffff@@SAAEAV12@XZ@YAXXZ; void (__cdecl *)()
0x18000772a  call    atexit
0x18000772f  nop
0x180007730  lea     rcx, dword_1800C8F30
0x180007737  call    _Init_thread_footer
0x18000773c  jmp     loc_1800075F3
0x180007741  mov     rax, [rsi]
0x180007744  mov     rcx, rsi
0x180007747  mov     rax, [rax]
0x18000774a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000774f  mov     eax, ebx
0x180007751  lock xadd [rsi+0Ch], eax
0x180007756  cmp     eax, 1
0x180007759  jnz     loc_18000767C
0x18000775f  mov     rax, [rsi]
0x180007762  mov     rcx, rsi
0x180007765  mov     rax, [rax+8]
0x180007769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000776e  jmp     loc_18000767C
0x180007773  mov     rax, [rsi]
0x180007776  mov     rcx, rsi
0x180007779  mov     rax, [rax]
0x18000777c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007781  mov     eax, ebx
0x180007783  lock xadd [rsi+0Ch], eax
0x180007788  cmp     eax, 1
0x18000778b  jnz     loc_180007696
0x180007791  mov     rax, [rsi]
0x180007794  mov     rcx, rsi
0x180007797  mov     rax, [rax+8]
0x18000779b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077a0  jmp     loc_180007696
0x1800077a5  sub     ecx, 1
0x1800077a8  jz      short loc_1800077D1
0x1800077aa  cmp     ecx, 1
0x1800077ad  mov     rcx, rdi
0x1800077b0  jz      short loc_1800077C3
0x1800077b2  lea     rdx, aUnknown_1; "Unknown"
0x1800077b9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800077be  jmp     loc_1800076BB
0x1800077c3  mov     rdx, [rbp+18h]
0x1800077c7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800077cc  jmp     loc_1800076BB
0x1800077d1  mov     rdx, [rbp+18h]
0x1800077d5  mov     rcx, rdi
0x1800077d8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800077dd  jmp     loc_1800076BB
```
