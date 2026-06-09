# Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::Instance(void)

- ea: `0x180020d74`
- end: `0x180020f6c`
- name: `?Instance@?$SingletonWithFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@345@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@XZ`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020938`

## callees

- `0x180001bcc`
- `0x180009ce8`
- `0x18001f1cc`
- `0x180020d74`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020f38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020f38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020d97`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020d97`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180020e68`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180020e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e80`

## string_xrefs

- `0x180020f5a`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::Instance(
        __int64 *a1)
{
  __int64 v2; // rdx
  signed __int32 v3; // eax
  signed __int32 v4; // ett
  _DWORD *v5; // rsi
  HANDLE Event; // rbp
  const char *v7; // r9
  volatile signed __int32 *v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rcx
  volatile signed __int32 *v11; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  AcquireSRWLockExclusive(&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_lock);
  *a1 = 0;
  a1[1] = 0;
  v2 = qword_180046430;
  if ( qword_180046430 )
  {
    v3 = *(_DWORD *)(qword_180046430 + 8);
    while ( v3 )
    {
      v4 = v3;
      v3 = _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 8), v3 + 1, v3);
      if ( v4 == v3 )
      {
        *a1 = Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_instance;
        a1[1] = qword_180046430;
        break;
      }
    }
  }
  if ( !*a1 )
  {
    v5 = operator new(0x28u);
    *(_OWORD *)v5 = 0;
    v5[2] = 1;
    v5[3] = 1;
    *(_QWORD *)v5 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>::`vftable';
    *((_OWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 4) = 0;
    *((_QWORD *)v5 + 2) = &Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar::`vftable';
    v5[6] = 0;
    *((_QWORD *)v5 + 4) = 0;
    Event = CreateEventExW(0, 0, 3u, 0x1F0003u);
    if ( !Event )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1C6A,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        v7);
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v5 + 8,
      Event);
    *a1 = (__int64)(v5 + 4);
    v8 = (volatile signed __int32 *)a1[1];
    a1[1] = (__int64)v5;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    v9 = a1[1];
    if ( v9 )
    {
      v10 = *a1;
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 12));
    }
    else
    {
      v9 = 0;
      v10 = 0;
    }
    Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_instance = v10;
    v11 = (volatile signed __int32 *)qword_180046430;
    qword_180046430 = v9;
    if ( v11 && _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
  }
  ReleaseSRWLockExclusive(&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_lock);
  return a1;
}

```

## disassembly

```asm
0x180020d74  mov     [rsp+arg_0], rcx
0x180020d79  push    rbx
0x180020d7a  push    rbp
0x180020d7b  push    rsi
0x180020d7c  push    rdi
0x180020d7d  push    r12
0x180020d7f  push    r14
0x180020d81  sub     rsp, 48h
0x180020d85  mov     rbx, rcx
0x180020d88  and     [rsp+78h+var_58], 0
0x180020d8d  lea     r12, ?s_lock@?$SingletonWithFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@345@@Foundation@Bluetooth@Microsoft@@0Vsrwlock@wil@@A; wil::srwlock Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_lock
0x180020d94  mov     rcx, r12; SRWLock
0x180020d97  call    cs:__imp_AcquireSRWLockExclusive
0x180020d9e  nop     dword ptr [rax+rax+00h]
0x180020da3  mov     [rsp+78h+arg_8], r12
0x180020dab  and     qword ptr [rbx], 0
0x180020daf  and     qword ptr [rbx+8], 0
0x180020db4  mov     rdx, cs:qword_180046430
0x180020dbb  test    rdx, rdx
0x180020dbe  jz      short loc_180020DEA
0x180020dc0  mov     eax, [rdx+8]
0x180020dc3  jmp     short loc_180020DCF
0x180020dc5  lea     ecx, [rax+1]
0x180020dc8  lock cmpxchg [rdx+8], ecx
0x180020dcd  jz      short loc_180020DD5
0x180020dcf  test    eax, eax
0x180020dd1  jnz     short loc_180020DC5
0x180020dd3  jmp     short loc_180020DEA
0x180020dd5  mov     rax, cs:?s_instance@?$SingletonWithFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@345@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@A; std::weak_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_instance
0x180020ddc  mov     [rbx], rax
0x180020ddf  mov     rax, cs:qword_180046430
0x180020de6  mov     [rbx+8], rax
0x180020dea  mov     [rsp+78h+var_58], 1
0x180020df2  cmp     qword ptr [rbx], 0
0x180020df6  jnz     loc_180020F35
0x180020dfc  mov     ecx, 28h ; '('; Size
0x180020e01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020e06  mov     rsi, rax
0x180020e09  mov     [rsp+78h+arg_10], rax
0x180020e11  xorps   xmm0, xmm0
0x180020e14  movups  xmmword ptr [rax], xmm0
0x180020e17  mov     dword ptr [rax+8], 1
0x180020e1e  mov     dword ptr [rax+0Ch], 1
0x180020e25  lea     rax, ??_7?$_Ref_count_obj2@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>::`vftable'
0x180020e2c  mov     [rsi], rax
0x180020e2f  lea     rdi, [rsi+10h]
0x180020e33  xor     eax, eax
0x180020e35  movups  xmmword ptr [rdi], xmm0
0x180020e38  mov     [rdi+10h], rax
0x180020e3c  lea     rax, ??_7ThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar::`vftable'
0x180020e43  mov     [rdi], rax
0x180020e46  and     dword ptr [rdi+8], 0
0x180020e4a  lea     r14, [rdi+10h]
0x180020e4e  mov     [rsp+78h+arg_18], r14
0x180020e56  and     qword ptr [r14], 0
0x180020e5a  xor     edx, edx; lpName
0x180020e5c  xor     ecx, ecx; lpEventAttributes
0x180020e5e  mov     r9d, 1F0003h; dwDesiredAccess
0x180020e64  lea     r8d, [rdx+3]; dwFlags
0x180020e68  call    cs:__imp_CreateEventExW
0x180020e6f  nop     dword ptr [rax+rax+00h]
0x180020e74  mov     rbp, rax
0x180020e77  test    rax, rax
0x180020e7a  jz      loc_180020F55
0x180020e80  call    cs:__imp_GetLastError
0x180020e87  nop     dword ptr [rax+rax+00h]
0x180020e8c  mov     rdx, rbp
0x180020e8f  mov     rcx, r14
0x180020e92  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180020e97  nop
0x180020e98  mov     [rbx], rdi
0x180020e9b  mov     rdi, [rbx+8]
0x180020e9f  mov     [rbx+8], rsi
0x180020ea3  or      esi, 0FFFFFFFFh
0x180020ea6  test    rdi, rdi
0x180020ea9  jz      short loc_180020EDE
0x180020eab  mov     eax, esi
0x180020ead  lock xadd [rdi+8], eax
0x180020eb2  add     eax, esi
0x180020eb4  jnz     short loc_180020EDE
0x180020eb6  mov     rax, [rdi]
0x180020eb9  mov     rcx, rdi
0x180020ebc  mov     rax, [rax]
0x180020ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ec4  mov     eax, esi
0x180020ec6  lock xadd [rdi+0Ch], eax
0x180020ecb  add     eax, esi
0x180020ecd  jnz     short loc_180020EDE
0x180020ecf  mov     rax, [rdi]
0x180020ed2  mov     rcx, rdi
0x180020ed5  mov     rax, [rax+8]
0x180020ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ede  xorps   xmm0, xmm0
0x180020ee1  movdqu  [rsp+78h+var_50], xmm0
0x180020ee7  mov     rax, [rbx+8]
0x180020eeb  test    rax, rax
0x180020eee  jz      short loc_180020EF9
0x180020ef0  mov     rcx, [rbx]
0x180020ef3  lock inc dword ptr [rax+0Ch]
0x180020ef7  jmp     short loc_180020F03
0x180020ef9  mov     rax, qword ptr [rsp+78h+var_50+8]
0x180020efe  mov     rcx, qword ptr [rsp+78h+var_50]
0x180020f03  mov     cs:?s_instance@?$SingletonWithFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@345@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@A, rcx; std::weak_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_instance
0x180020f0a  mov     rcx, cs:qword_180046430
0x180020f11  mov     cs:qword_180046430, rax
0x180020f18  test    rcx, rcx
0x180020f1b  jz      short loc_180020F35
0x180020f1d  mov     eax, esi
0x180020f1f  lock xadd [rcx+0Ch], eax
0x180020f24  add     eax, esi
0x180020f26  jnz     short loc_180020F35
0x180020f28  mov     rax, [rcx]
0x180020f2b  mov     rax, [rax+8]
0x180020f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f34  nop
0x180020f35  mov     rcx, r12; SRWLock
0x180020f38  call    cs:__imp_ReleaseSRWLockExclusive
0x180020f3f  nop     dword ptr [rax+rax+00h]
0x180020f44  mov     rax, rbx
0x180020f47  add     rsp, 48h
0x180020f4b  pop     r14
0x180020f4d  pop     r12
0x180020f4f  pop     rdi
0x180020f50  pop     rsi
0x180020f51  pop     rbp
0x180020f52  pop     rbx
0x180020f53  retn
0x180020f55  mov     rcx, [rsp+78h]; this
0x180020f5a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020f61  mov     edx, 1C6Ah; void *
0x180020f66  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
