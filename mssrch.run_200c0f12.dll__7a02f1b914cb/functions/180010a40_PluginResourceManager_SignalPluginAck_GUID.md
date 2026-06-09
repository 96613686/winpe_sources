# PluginResourceManager::SignalPluginAck(_GUID)

- ea: `0x180010a40`
- end: `0x180010d2f`
- name: `?SignalPluginAck@PluginResourceManager@@UEAAJU_GUID@@@Z`
- size: `751`
- prototype: `int(PluginResourceManager *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000f880`
- `0x180010a40`
- `0x1800110b8`
- `0x1800111e4`
- `0x180012120`
- `0x180012190`
- `0x1800771ac`
- `0x1800fc1f8`
- `0x1801244c0`
- `0x1801249b0`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010c46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010cea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010d08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010c46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010cea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010d08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010a8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010a8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010bbc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010bbc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180010aa6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180010aa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010c37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010cdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010cf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010c37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010cdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010cf7`

## string_xrefs

- `0x180010c7e`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x180010cbf`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PluginResourceManager::SignalPluginAck(PluginResourceManager *this, struct _GUID *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r10
  void **v8; // r8
  __int64 v9; // rdx
  unsigned __int64 i; // rax
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rdi
  _QWORD *v14; // rdx
  void **v15; // rcx
  __int64 v16; // rcx
  LPCRITICAL_SECTION v17; // rcx
  unsigned __int64 v19; // [rsp+20h] [rbp-78h] BYREF
  LPOLESTR lpsz; // [rsp+28h] [rbp-70h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+30h] [rbp-68h] BYREF
  void *Block[2]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v23; // [rsp+50h] [rbp-48h]
  unsigned __int64 v24; // [rsp+58h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( g_pGatheringService )
  {
    SearchIndexerPluginIsolationTelemetry::SignalPluginAck<_GUID &>(a2);
    lpCriticalSection[0] = (LPCRITICAL_SECTION)((char *)this + 152);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    v19 = (unsigned __int64)this + 152;
    lpsz = 0;
    v4 = StringFromCLSID(a2, &lpsz);
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x227,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
        (const char *)(unsigned int)v4,
        v19);
      if ( lpsz )
        CoTaskMemFree(lpsz);
      if ( this != (PluginResourceManager *)-152LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
      return v5;
    }
    else
    {
      *(_OWORD *)Block = 0;
      v23 = 0;
      v24 = 0;
      std::wstring::_Construct_empty(Block);
      v6 = -1;
      do
        ++v6;
      while ( lpsz[v6] );
      try
      {
        std::wstring::_Assign<wchar_t>(Block);
        v7 = v23;
        v8 = Block;
        if ( v24 > 7 )
          v8 = (void **)Block[0];
        v9 = 0xCBF29CE484222325uLL;
        for ( i = 0; i < 2 * v23; ++i )
          v9 = 0x100000001B3LL * (*((unsigned __int8 *)v8 + i) ^ (unsigned __int64)v9);
        v11 = *((_QWORD *)this + 14);
        v12 = *(_QWORD *)(v11 + 16 * (v9 & *((_QWORD *)this + 17)) + 8);
        if ( v12 != *((_QWORD *)this + 12) )
        {
          v13 = *(_QWORD *)(v11 + 16 * (v9 & *((_QWORD *)this + 17)));
          while ( 1 )
          {
            v14 = (_QWORD *)(v12 + 16);
            if ( *(_QWORD *)(v12 + 40) > 7u )
              v14 = (_QWORD *)*v14;
            v15 = Block;
            if ( v24 > 7 )
              v15 = (void **)Block[0];
            if ( v7 == *(_QWORD *)(v12 + 32) )
            {
              if ( !v7 || !(unsigned int)std::_WChar_traits<wchar_t>::compare(v15, v14) )
                goto LABEL_43;
              v7 = v23;
            }
            if ( v12 == v13 )
              break;
            v12 = *(_QWORD *)(v12 + 8);
          }
        }
        v12 = 0;
      }
      catch ( ... )
      {
        indexer::result::details::result_from_caught_exception<1>(
          retaddr,
          558,
          "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx");
      }
LABEL_43:
      if ( v12 && v12 != *((_QWORD *)this + 12) )
      {
        *(_BYTE *)(v12 + 72) = 0;
        *(_QWORD *)(v12 + 64) = GetTickCount64();
        v16 = *(_QWORD *)(v12 + 80);
        *(struct _GUID *)lpCriticalSection = *a2;
        (*(void (__fastcall **)(__int64, LPCRITICAL_SECTION *))(*(_QWORD *)v16 + 88LL))(v16, lpCriticalSection);
      }
      if ( v24 > 7 )
      {
        v19 = 2 * v24 + 2;
        v17 = (LPCRITICAL_SECTION)Block[0];
        lpCriticalSection[0] = (LPCRITICAL_SECTION)Block[0];
        if ( v19 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned((void **)lpCriticalSection, &v19);
          v17 = lpCriticalSection[0];
        }
        operator delete(v17);
      }
      v23 = 0;
      v24 = 7;
      LOWORD(Block[0]) = 0;
      if ( lpsz )
        CoTaskMemFree(lpsz);
      if ( this != (PluginResourceManager *)-152LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
      (const char *)0x80041812LL,
      v19);
    return 2147751954LL;
  }
}

```

## disassembly

```asm
0x180010a40  mov     [rsp+arg_10], rbx
0x180010a45  push    rsi
0x180010a46  push    rdi
0x180010a47  push    r12
0x180010a49  push    r14
0x180010a4b  push    r15
0x180010a4d  sub     rsp, 70h
0x180010a51  mov     rax, cs:__security_cookie
0x180010a58  xor     rax, rsp
0x180010a5b  mov     [rsp+98h+var_38], rax
0x180010a60  mov     r15, rdx
0x180010a63  mov     r14, rcx
0x180010a66  cmp     cs:?g_pGatheringService@@3PEAVCGatheringService@@EA, 0; CGatheringService * g_pGatheringService
0x180010a6e  jz      loc_180010C70
0x180010a74  mov     rcx, rdx
0x180010a77  call    ??$SignalPluginAck@AEAU_GUID@@@SearchIndexerPluginIsolationTelemetry@@SAXAEAU_GUID@@@Z; SearchIndexerPluginIsolationTelemetry::SignalPluginAck<_GUID &>(_GUID &)
0x180010a7c  lea     rsi, [r14+98h]
0x180010a83  mov     [rsp+98h+lpCriticalSection], rsi
0x180010a88  mov     rcx, rsi; lpCriticalSection
0x180010a8b  call    cs:__imp_EnterCriticalSection
0x180010a91  mov     [rsp+98h+var_78], rsi; int
0x180010a96  xor     r12d, r12d
0x180010a99  mov     [rsp+98h+lpsz], r12
0x180010a9e  lea     rdx, [rsp+98h+lpsz]; lplpsz
0x180010aa3  mov     rcx, r15; rclsid
0x180010aa6  call    cs:__imp_StringFromCLSID
0x180010aac  mov     ebx, eax
0x180010aae  test    eax, eax
0x180010ab0  js      loc_180010CB4
0x180010ab6  xorps   xmm0, xmm0
0x180010ab9  movups  xmmword ptr [rsp+98h+Block], xmm0
0x180010abe  mov     [rsp+98h+var_48], r12
0x180010ac3  mov     [rsp+98h+var_40], r12
0x180010ac8  lea     rcx, [rsp+98h+Block]
0x180010acd  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180010ad2  nop
0x180010ad3  mov     rdx, [rsp+98h+lpsz]
0x180010ad8  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180010adf  nop
0x180010ae0  inc     r8
0x180010ae3  cmp     word ptr [rdx+r8*2], 0
0x180010ae9  jnz     short loc_180010AE0
0x180010aeb  lea     rcx, [rsp+98h+Block]
0x180010af0  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180010af5  nop
0x180010af6  mov     r10, [rsp+98h+var_48]
0x180010afb  lea     r8, [rsp+98h+Block]
0x180010b00  cmp     [rsp+98h+var_40], 7
0x180010b06  cmova   r8, [rsp+98h+Block]
0x180010b0c  mov     rdx, 0CBF29CE484222325h
0x180010b16  lea     r9, [r10+r10]
0x180010b1a  mov     rax, r12
0x180010b1d  test    r9, r9
0x180010b20  jz      short loc_180010B44
0x180010b22  mov     r11, 100000001B3h
0x180010b2c  nop     dword ptr [rax+00h]
0x180010b30  movzx   ecx, byte ptr [r8+rax]
0x180010b35  xor     rdx, rcx
0x180010b38  imul    rdx, r11
0x180010b3c  inc     rax
0x180010b3f  cmp     rax, r9
0x180010b42  jb      short loc_180010B30
0x180010b44  mov     rcx, [r14+88h]
0x180010b4b  and     rcx, rdx
0x180010b4e  add     rcx, rcx
0x180010b51  mov     rax, [r14+70h]
0x180010b55  mov     rbx, [rax+rcx*8+8]
0x180010b5a  cmp     rbx, [r14+60h]
0x180010b5e  jz      short loc_180010BAA
0x180010b60  mov     rdi, [rax+rcx*8]
0x180010b64  lea     rdx, [rbx+10h]
0x180010b68  cmp     qword ptr [rbx+28h], 7
0x180010b6d  jbe     short loc_180010B72
0x180010b6f  mov     rdx, [rdx]
0x180010b72  lea     rcx, [rsp+98h+Block]
0x180010b77  cmp     [rsp+98h+var_40], 7
0x180010b7d  cmova   rcx, [rsp+98h+Block]
0x180010b83  cmp     r10, [rbx+20h]
0x180010b87  jnz     short loc_180010B9F
0x180010b89  test    r10, r10
0x180010b8c  jz      short loc_180010BAD
0x180010b8e  mov     r8, r10
0x180010b91  call    ?compare@?$_WChar_traits@_W@std@@SAHQEB_W0_K@Z; std::_WChar_traits<wchar_t>::compare(wchar_t const * const,wchar_t const * const,unsigned __int64)
0x180010b96  test    eax, eax
0x180010b98  jz      short loc_180010BAD
0x180010b9a  mov     r10, [rsp+98h+var_48]
0x180010b9f  cmp     rbx, rdi
0x180010ba2  jz      short loc_180010BAA
0x180010ba4  mov     rbx, [rbx+8]
0x180010ba8  jmp     short loc_180010B64
0x180010baa  mov     rbx, r12
0x180010bad  test    rbx, rbx
0x180010bb0  jz      short loc_180010BE5
0x180010bb2  cmp     rbx, [r14+60h]
0x180010bb6  jz      short loc_180010BE5
0x180010bb8  mov     byte ptr [rbx+48h], 0
0x180010bbc  call    cs:__imp_GetTickCount64
0x180010bc2  mov     [rbx+40h], rax
0x180010bc6  mov     rcx, [rbx+50h]
0x180010bca  movups  xmm0, xmmword ptr [r15]
0x180010bce  movaps  xmmword ptr [rsp+98h+lpCriticalSection], xmm0
0x180010bd3  mov     rax, [rcx]
0x180010bd6  lea     rdx, [rsp+98h+lpCriticalSection]
0x180010bdb  mov     rax, [rax+58h]
0x180010bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010be4  nop
0x180010be5  mov     rdx, [rsp+98h+var_40]
0x180010bea  cmp     rdx, 7
0x180010bee  jbe     short loc_180010C19
0x180010bf0  lea     rdx, ds:2[rdx*2]
0x180010bf8  mov     [rsp+98h+var_78], rdx
0x180010bfd  mov     rcx, [rsp+98h+Block]; Block
0x180010c02  mov     [rsp+98h+lpCriticalSection], rcx
0x180010c07  cmp     rdx, 1000h
0x180010c0e  jnb     loc_180010C96
0x180010c14  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010c19  mov     [rsp+98h+var_48], r12
0x180010c1e  mov     [rsp+98h+var_40], 7
0x180010c27  mov     word ptr [rsp+98h+Block], r12w
0x180010c2d  mov     rcx, [rsp+98h+lpsz]; pv
0x180010c32  test    rcx, rcx
0x180010c35  jz      short loc_180010C3E
0x180010c37  call    cs:__imp_CoTaskMemFree
0x180010c3d  nop
0x180010c3e  test    rsi, rsi
0x180010c41  jz      short loc_180010C4C
0x180010c43  mov     rcx, rsi; lpCriticalSection
0x180010c46  call    cs:__imp_LeaveCriticalSection
0x180010c4c  xor     eax, eax
0x180010c4e  mov     rcx, [rsp+98h+var_38]
0x180010c53  xor     rcx, rsp; StackCookie
0x180010c56  call    __security_check_cookie
0x180010c5b  mov     rbx, [rsp+98h+arg_10]
0x180010c63  add     rsp, 70h
0x180010c67  pop     r15
0x180010c69  pop     r14
0x180010c6b  pop     r12
0x180010c6d  pop     rdi
0x180010c6e  pop     rsi
0x180010c6f  retn
0x180010c70  mov     rcx, [rsp+98h]; this
0x180010c78  mov     r9d, 80041812h; char *
0x180010c7e  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180010c85  mov     edx, 221h; void *
0x180010c8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c8f  mov     eax, 80041812h
0x180010c94  jmp     short loc_180010C4E
0x180010c96  lea     rdx, [rsp+98h+var_78]; unsigned __int64 *
0x180010c9b  lea     rcx, [rsp+98h+lpCriticalSection]; void **
0x180010ca0  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180010ca5  mov     rdx, [rsp+98h+var_78]
0x180010caa  mov     rcx, [rsp+98h+lpCriticalSection]
0x180010caf  jmp     loc_180010C14
0x180010cb4  mov     rcx, [rsp+98h]; this
0x180010cbc  mov     r9d, ebx; char *
0x180010cbf  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180010cc6  mov     edx, 227h; void *
0x180010ccb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010cd0  nop
0x180010cd1  mov     rcx, [rsp+98h+lpsz]; pv
0x180010cd6  test    rcx, rcx
0x180010cd9  jz      short loc_180010CE2
0x180010cdb  call    cs:__imp_CoTaskMemFree
0x180010ce1  nop
0x180010ce2  test    rsi, rsi
0x180010ce5  jz      short loc_180010CF0
0x180010ce7  mov     rcx, rsi; lpCriticalSection
0x180010cea  call    cs:__imp_LeaveCriticalSection
0x180010cf0  mov     eax, ebx
0x180010cf2  jmp     loc_180010C4E
0x180010cf7  call    cs:__imp_CoTaskMemFree
0x180010cfd  nop
0x180010cfe  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x180010d03  test    rcx, rcx
0x180010d06  jz      short loc_180010D0E
0x180010d08  call    cs:__imp_LeaveCriticalSection
0x180010d0e  mov     eax, dword ptr [rsp+98h+var_78]
0x180010d12  jmp     loc_180010C4E
0x180010d17  lea     rcx, [rsp+98h+Block]; this
0x180010d1c  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x180010d21  nop
0x180010d22  mov     rcx, [rsp+98h+lpsz]; pv
0x180010d27  test    rcx, rcx
0x180010d2a  jz      short loc_180010CFE
0x180010d2c  jmp     short loc_180010CF7
```
