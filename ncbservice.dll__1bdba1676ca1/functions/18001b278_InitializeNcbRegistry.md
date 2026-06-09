# InitializeNcbRegistry

- ea: `0x18001b278`
- end: `0x18001b4e9`
- name: `InitializeNcbRegistry`
- size: `625`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800159b8`
- `0x18001ae2c`

## callees

- `0x18001b278`
- `0x18001b52c`
- `0x18001b630`
- `0x18001b670`
- `0x18001b744`
- `0x18001c0a4`
- `0x18001c548`
- `0x18001d8e0`
- `0x18001d910`
- `0x18001dcec`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001b2bd`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001b313`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001b2bd`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001b313`

## string_xrefs

- `0x18001b2af`: `System\CurrentControlSet\Services\NcbService\NCB`
- `0x18001b305`: `System\CurrentControlSet\Services\NcbService\NCB`
- `0x18001b2b6`: `NetworkConnectionBroker`
- `0x18001b30c`: `NetworkConnectionBroker`
- `0x18001b437`: `KapiNlmCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 InitializeNcbRegistry()
{
  __int64 result; // rax
  __int64 v1; // rdi
  _WORD *v2; // rbx
  unsigned int PersistedRegistryLocationW; // esi
  LPCWSTR *v4; // rdi
  __int64 v5; // rdx
  LPCWSTR *v6; // r8
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned int v10; // [rsp+30h] [rbp-88h] BYREF
  _WORD *v11; // [rsp+38h] [rbp-80h] BYREF
  __int128 v12; // [rsp+40h] [rbp-78h] BYREF
  __int128 v13; // [rsp+50h] [rbp-68h]
  __int128 v14; // [rsp+60h] [rbp-58h] BYREF
  __int128 v15; // [rsp+70h] [rbp-48h]

  v10 = 0;
  result = GetPersistedRegistryLocationW(
             L"NetworkConnectionBroker",
             L"System\\CurrentControlSet\\Services\\NcbService\\NCB",
             0,
             0,
             &v10);
  if ( (_DWORD)result == 234 )
  {
    v1 = -1;
    v2 = operator new[](saturated_mul((unsigned __int64)v10 >> 1, 2u));
    v11 = v2;
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                   L"NetworkConnectionBroker",
                                   L"System\\CurrentControlSet\\Services\\NcbService\\NCB",
                                   v2,
                                   v10,
                                   0);
    if ( PersistedRegistryLocationW )
    {
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v11);
      return PersistedRegistryLocationW;
    }
    else
    {
      v12 = 0;
      v13 = 0u;
      do
        ++v1;
      while ( v2[v1] );
      std::wstring::_Construct<1,unsigned short const *>(&v12, v2, v1);
      v4 = &lpSubKey;
      std::wstring::_Tidy_deallocate(&lpSubKey);
      *(_OWORD *)&lpSubKey = v12;
      xmmword_18004D9D0 = v13;
      v12 = 0;
      v13 = 0u;
      std::wstring::_Construct<1,unsigned short const *>(&v12, L"KAHints", 7);
      v6 = &lpSubKey;
      if ( *((_QWORD *)&xmmword_18004D9D0 + 1) > 7u )
        v6 = (LPCWSTR *)lpSubKey;
      v7 = std::wstring::_Insert<unsigned short>(&v12, v5, v6, xmmword_18004D9D0);
      std::wstring::wstring(&v14, v7);
      std::wstring::_Tidy_deallocate(&xmmword_18004D9A0);
      xmmword_18004D9A0 = v14;
      *(_OWORD *)byte_18004D9B0 = v15;
      if ( *((_QWORD *)&v13 + 1) > 7u )
        std::_Deallocate<16>(v12, 2LL * *((_QWORD *)&v13 + 1) + 2);
      v12 = 0;
      v13 = 0u;
      std::wstring::_Construct<1,unsigned short const *>(&v12, L"KapiNlmCache", 12);
      if ( *((_QWORD *)&xmmword_18004D9D0 + 1) > 7u )
        v4 = (LPCWSTR *)lpSubKey;
      v9 = std::wstring::_Insert<unsigned short>(&v12, v8, v4, xmmword_18004D9D0);
      std::wstring::wstring(&v14, v9);
      std::wstring::_Tidy_deallocate(&xmmword_18004D980);
      xmmword_18004D980 = v14;
      *(_OWORD *)byte_18004D990 = v15;
      if ( *((_QWORD *)&v13 + 1) > 7u )
        std::_Deallocate<16>(v12, 2LL * *((_QWORD *)&v13 + 1) + 2);
      operator delete(v2);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b278  push    rbx
0x18001b27a  push    rsi
0x18001b27b  push    rdi
0x18001b27c  push    r14
0x18001b27e  sub     rsp, 98h
0x18001b285  mov     rax, cs:__security_cookie
0x18001b28c  xor     rax, rsp
0x18001b28f  mov     [rsp+0B8h+var_38], rax
0x18001b297  xor     r14d, r14d
0x18001b29a  mov     [rsp+0B8h+var_88], r14d
0x18001b29f  lea     rax, [rsp+0B8h+var_88]
0x18001b2a4  mov     [rsp+0B8h+var_98], rax
0x18001b2a9  xor     r9d, r9d
0x18001b2ac  xor     r8d, r8d
0x18001b2af  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Nc"...
0x18001b2b6  lea     rcx, aNetworkconnect; "NetworkConnectionBroker"
0x18001b2bd  call    cs:__imp_GetPersistedRegistryLocationW
0x18001b2c3  cmp     eax, 0EAh
0x18001b2c8  jnz     loc_18001B4CB
0x18001b2ce  mov     ecx, [rsp+0B8h+var_88]
0x18001b2d2  shr     rcx, 1
0x18001b2d5  mov     eax, 2
0x18001b2da  mul     rcx
0x18001b2dd  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001b2e4  cmovb   rax, rdi
0x18001b2e8  mov     rcx, rax; unsigned __int64
0x18001b2eb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001b2f0  mov     rbx, rax
0x18001b2f3  mov     [rsp+0B8h+var_80], rax
0x18001b2f8  mov     [rsp+0B8h+var_98], r14
0x18001b2fd  mov     r9d, [rsp+0B8h+var_88]
0x18001b302  mov     r8, rax
0x18001b305  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Nc"...
0x18001b30c  lea     rcx, aNetworkconnect; "NetworkConnectionBroker"
0x18001b313  call    cs:__imp_GetPersistedRegistryLocationW
0x18001b319  mov     esi, eax
0x18001b31b  test    eax, eax
0x18001b31d  jz      short loc_18001B330
0x18001b31f  lea     rcx, [rsp+0B8h+var_80]
0x18001b324  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001b329  mov     eax, esi
0x18001b32b  jmp     loc_18001B4CB
0x18001b330  xorps   xmm0, xmm0
0x18001b333  movups  [rsp+0B8h+var_78], xmm0
0x18001b338  mov     qword ptr [rsp+0B8h+var_68], r14
0x18001b33d  mov     qword ptr [rsp+0B8h+var_68+8], r14
0x18001b342  inc     rdi
0x18001b345  cmp     [rbx+rdi*2], r14w
0x18001b34a  jnz     short loc_18001B342
0x18001b34c  mov     r8, rdi
0x18001b34f  mov     rdx, rbx
0x18001b352  lea     rcx, [rsp+0B8h+var_78]
0x18001b357  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b35c  lea     rdi, lpSubKey
0x18001b363  mov     rcx, rdi
0x18001b366  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b36b  movups  xmm0, [rsp+0B8h+var_78]
0x18001b370  movaps  cs:lpSubKey, xmm0
0x18001b377  movups  xmm1, [rsp+0B8h+var_68]
0x18001b37c  movaps  cs:xmmword_18004D9D0, xmm1
0x18001b383  xorps   xmm0, xmm0
0x18001b386  movups  [rsp+0B8h+var_78], xmm0
0x18001b38b  mov     qword ptr [rsp+0B8h+var_68], r14
0x18001b390  mov     qword ptr [rsp+0B8h+var_68+8], r14
0x18001b395  mov     esi, 7
0x18001b39a  mov     r8d, esi
0x18001b39d  lea     rdx, aKahints; "KAHints"
0x18001b3a4  lea     rcx, [rsp+0B8h+var_78]
0x18001b3a9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b3ae  nop
0x18001b3af  mov     r8, rdi
0x18001b3b2  cmp     qword ptr cs:xmmword_18004D9D0+8, rsi
0x18001b3b9  cmova   r8, qword ptr cs:lpSubKey
0x18001b3c1  mov     r9, qword ptr cs:xmmword_18004D9D0
0x18001b3c8  lea     rcx, [rsp+0B8h+var_78]
0x18001b3cd  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x18001b3d2  mov     rdx, rax
0x18001b3d5  lea     rcx, [rsp+0B8h+var_58]
0x18001b3da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18001b3df  lea     rcx, xmmword_18004D9A0
0x18001b3e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b3eb  movups  xmm0, [rsp+0B8h+var_58]
0x18001b3f0  movaps  cs:xmmword_18004D9A0, xmm0
0x18001b3f7  movups  xmm1, [rsp+0B8h+var_48]
0x18001b3fc  movaps  xmmword ptr cs:byte_18004D9B0, xmm1
0x18001b403  mov     rdx, qword ptr [rsp+0B8h+var_68+8]
0x18001b408  cmp     rdx, rsi
0x18001b40b  jbe     short loc_18001B41F
0x18001b40d  lea     rdx, ds:2[rdx*2]
0x18001b415  mov     rcx, qword ptr [rsp+0B8h+var_78]
0x18001b41a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b41f  xorps   xmm0, xmm0
0x18001b422  movups  [rsp+0B8h+var_78], xmm0
0x18001b427  mov     qword ptr [rsp+0B8h+var_68], r14
0x18001b42c  mov     qword ptr [rsp+0B8h+var_68+8], r14
0x18001b431  mov     r8d, 0Ch
0x18001b437  lea     rdx, aKapinlmcache; "KapiNlmCache"
0x18001b43e  lea     rcx, [rsp+0B8h+var_78]
0x18001b443  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b448  nop
0x18001b449  cmp     qword ptr cs:xmmword_18004D9D0+8, rsi
0x18001b450  cmova   rdi, qword ptr cs:lpSubKey
0x18001b458  mov     r9, qword ptr cs:xmmword_18004D9D0
0x18001b45f  mov     r8, rdi
0x18001b462  lea     rcx, [rsp+0B8h+var_78]
0x18001b467  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x18001b46c  mov     rdx, rax
0x18001b46f  lea     rcx, [rsp+0B8h+var_58]
0x18001b474  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18001b479  lea     rcx, xmmword_18004D980
0x18001b480  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b485  movups  xmm0, [rsp+0B8h+var_58]
0x18001b48a  movaps  cs:xmmword_18004D980, xmm0
0x18001b491  movups  xmm1, [rsp+0B8h+var_48]
0x18001b496  movaps  xmmword ptr cs:byte_18004D990, xmm1
0x18001b49d  mov     rdx, qword ptr [rsp+0B8h+var_68+8]
0x18001b4a2  cmp     rdx, rsi
0x18001b4a5  jbe     short loc_18001B4BA
0x18001b4a7  lea     rdx, ds:2[rdx*2]
0x18001b4af  mov     rcx, qword ptr [rsp+0B8h+var_78]
0x18001b4b4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b4b9  nop
0x18001b4ba  mov     rcx, rbx; Block
0x18001b4bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b4c2  xor     eax, eax
0x18001b4c4  jmp     short loc_18001B4CB
0x18001b4c6  mov     eax, 0Eh
0x18001b4cb  mov     rcx, [rsp+0B8h+var_38]
0x18001b4d3  xor     rcx, rsp; StackCookie
0x18001b4d6  call    __security_check_cookie
0x18001b4db  add     rsp, 98h
0x18001b4e2  pop     r14
0x18001b4e4  pop     rdi
0x18001b4e5  pop     rsi
0x18001b4e6  pop     rbx
0x18001b4e7  retn
```
