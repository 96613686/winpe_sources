# DAS::DevnodeManagment::DevnodeManager::CloseProvidersDevnodes(std::vector<std::shared_ptr<ProviderContext>,std::allocator<std::shared_ptr<ProviderContext>>>,bool)

- ea: `0x18002b0ec`
- end: `0x18002b55a`
- name: `?CloseProvidersDevnodes@DevnodeManager@DevnodeManagment@DAS@@QEAAJV?$vector@V?$shared_ptr@VProviderContext@@@std@@V?$allocator@V?$shared_ptr@VProviderContext@@@std@@@2@@std@@_N@Z`
- size: `1134`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, _QWORD *, char)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004c480`

## callees

- `0x1800074c0`
- `0x180018ef8`
- `0x180019548`
- `0x180019adc`
- `0x180019b54`
- `0x18001a350`
- `0x18001a478`
- `0x18001dfe0`
- `0x18001eae0`
- `0x180027bf0`
- `0x18002a948`
- `0x18002b0ec`
- `0x18002b560`
- `0x18002d764`
- `0x180033f14`
- `0x18003bc80`
- `0x18004dc64`
- `0x18004dea4`
- `0x18004ecc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b2b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b2b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b161`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b22d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b27a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b32d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b3ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b4a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b511`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b161`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b22d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b27a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b32d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b3ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b4a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b511`

## string_xrefs

- `0x18002b145`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x18002b1fb`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x18002b38b`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x18002b442`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DAS::DevnodeManagment::DevnodeManager::CloseProvidersDevnodes(
        RTL_SRWLOCK *this,
        _QWORD *a2,
        char a3)
{
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rdx
  unsigned __int16 *v9; // rcx
  int ProviderNameFromAepId; // eax
  unsigned int v11; // esi
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int i; // esi
  __int64 v15; // rdx
  __int64 v16; // r8
  void *v17; // rcx
  char *v18; // rsi
  __int64 v19; // rdx
  char *v20; // r15
  const unsigned __int16 *v21; // rdx
  int v22; // eax
  unsigned int v23; // r14d
  const unsigned __int16 *v24; // rdx
  int started; // eax
  char *v26; // [rsp+20h] [rbp-98h] BYREF
  __int128 v27; // [rsp+28h] [rbp-90h]
  void *v28; // [rsp+38h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-78h] BYREF
  __int64 v30; // [rsp+48h] [rbp-70h] BYREF
  PSRWLOCK v31; // [rsp+50h] [rbp-68h] BYREF
  _QWORD *v32; // [rsp+58h] [rbp-60h]
  unsigned __int16 *v33[3]; // [rsp+60h] [rbp-58h] BYREF
  unsigned __int64 v34; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v32 = a2;
  wil::AcquireSRWLockShared(&SRWLock, this + 1);
  try
  {
    if ( LOBYTE(this[2].Ptr) )
    {
      std::vector<std::wstring>::vector<std::wstring>(&v26);
      wil::AcquireSRWLockShared(&v31, this + 4);
      v8 = *(_QWORD *)this[5].Ptr;
      v30 = v8;
      while ( !*(_BYTE *)(v8 + 25) )
      {
        std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>(
          (__int64)v33,
          v8 + 32);
        v28 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v28,
          0);
        v9 = (unsigned __int16 *)v33;
        if ( v34 > 7 )
          v9 = v33[0];
        ProviderNameFromAepId = DafGetProviderNameFromAepId(v9);
        v11 = ProviderNameFromAepId;
        if ( ProviderNameFromAepId < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x25E,
            (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
            (const char *)(unsigned int)ProviderNameFromAepId,
            (int)v26);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
          std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>(
            (__int64)v33,
            v12,
            v13);
          if ( v31 )
            ReleaseSRWLockShared(v31);
          if ( v26 )
          {
            std::_Destroy_range<std::allocator<std::wstring>>(v26, v27);
            std::_Deallocate<16>(v26, (*((_QWORD *)&v27 + 1) - (_QWORD)v26) & 0xFFFFFFFFFFFFFFE0uLL);
            v26 = 0;
            v27 = 0;
          }
          if ( SRWLock )
            ReleaseSRWLockShared(SRWLock);
          std::vector<std::shared_ptr<ProviderContext>>::_Tidy(a2);
          return v11;
        }
        for ( i = 0; i < (unsigned __int64)((__int64)(a2[1] - *a2) >> 4); ++i )
        {
          if ( !(unsigned int)_o__wcsicmp(**(_QWORD **)(*a2 + 16LL * i), v28) )
          {
            if ( (_QWORD)v27 == *((_QWORD *)&v27 + 1) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v26, v27, v33);
            }
            else
            {
              std::wstring::wstring(v27, v33);
              *(_QWORD *)&v27 = v27 + 32;
            }
            break;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
        std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>(
          (__int64)v33,
          v15,
          v16);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>>>,std::_Iterator_base0>::operator++(&v30);
        v8 = v30;
      }
      if ( v31 )
        ReleaseSRWLockShared(v31);
      v17 = v26;
      v18 = v26;
      v19 = v27;
      v20 = (char *)v27;
      while ( v18 != v20 )
      {
        std::wstring::wstring(v33, v18);
        v21 = (const unsigned __int16 *)v33;
        if ( v34 > 7 )
          v21 = v33[0];
        v22 = DAS::DevnodeManagment::DevnodeManager::StopDevnodeManagement(
                (DAS::DevnodeManagment::DevnodeManager *)this,
                v21,
                0);
        v23 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x26D,
            (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
            (const char *)(unsigned int)v22,
            (int)v26);
          std::wstring::_Tidy_deallocate((__int64)v33);
          if ( v26 )
          {
            std::_Destroy_range<std::allocator<std::wstring>>(v26, v27);
            std::_Deallocate<16>(v26, (*((_QWORD *)&v27 + 1) - (_QWORD)v26) & 0xFFFFFFFFFFFFFFE0uLL);
            v26 = 0;
            v27 = 0;
          }
          if ( SRWLock )
            ReleaseSRWLockShared(SRWLock);
LABEL_37:
          std::vector<std::shared_ptr<ProviderContext>>::_Tidy(a2);
          return v23;
        }
        if ( a3 )
        {
          v24 = (const unsigned __int16 *)v33;
          if ( v34 > 7 )
            v24 = v33[0];
          started = DAS::DevnodeManagment::DevnodeManager::StartDevnodeManagementUnlocked(
                      (DAS::DevnodeManagment::DevnodeManager *)this,
                      v24,
                      0,
                      0);
          v23 = started;
          if ( started < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x271,
              (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
              (const char *)(unsigned int)started,
              (int)v26);
            std::wstring::_Tidy_deallocate((__int64)v33);
            if ( v26 )
            {
              std::_Destroy_range<std::allocator<std::wstring>>(v26, v27);
              std::_Deallocate<16>(v26, (*((_QWORD *)&v27 + 1) - (_QWORD)v26) & 0xFFFFFFFFFFFFFFE0uLL);
              v26 = 0;
              v27 = 0;
            }
            if ( SRWLock )
              ReleaseSRWLockShared(SRWLock);
            goto LABEL_37;
          }
        }
        std::wstring::_Tidy_deallocate((__int64)v33);
        v18 += 32;
        v19 = v27;
        v17 = v26;
      }
      if ( v17 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v17, v19);
        std::_Deallocate<16>(v26, (*((_QWORD *)&v27 + 1) - (_QWORD)v26) & 0xFFFFFFFFFFFFFFE0uLL);
        v26 = 0;
        v27 = 0;
      }
      if ( SRWLock )
        ReleaseSRWLockShared(SRWLock);
      std::vector<std::shared_ptr<ProviderContext>>::_Tidy(a2);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x254,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
        (const char *)0x80640013LL,
        (int)v26);
      if ( SRWLock )
        ReleaseSRWLockShared(SRWLock);
      std::vector<std::shared_ptr<ProviderContext>>::_Tidy(a2);
      result = 2154037267LL;
    }
  }
  catch ( ... )
  {
    LODWORD(v28) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x277,
                     (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
                     v6);
    std::vector<std::shared_ptr<ProviderContext>>::_Tidy(v32);
    return (unsigned int)v28;
  }
  return result;
}

```

## disassembly

```asm
0x18002b0ec  mov     [rsp+arg_10], rbx
0x18002b0f1  push    rsi
0x18002b0f2  push    rdi
0x18002b0f3  push    r12
0x18002b0f5  push    r14
0x18002b0f7  push    r15
0x18002b0f9  sub     rsp, 90h
0x18002b100  mov     rax, cs:__security_cookie
0x18002b107  xor     rax, rsp
0x18002b10a  mov     [rsp+0B8h+var_30], rax
0x18002b112  mov     r12b, r8b
0x18002b115  mov     rbx, rdx
0x18002b118  mov     rdi, rcx
0x18002b11b  mov     [rsp+0B8h+var_60], rdx
0x18002b120  lea     rdx, [rcx+8]
0x18002b124  lea     rcx, [rsp+0B8h+SRWLock]
0x18002b129  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x18002b12e  nop
0x18002b12f  cmp     byte ptr [rdi+10h], 0
0x18002b133  jnz     short loc_18002B177
0x18002b135  mov     rcx, [rsp+0B8h]; this
0x18002b13d  mov     edi, 80640013h
0x18002b142  mov     r9d, edi; char *
0x18002b145  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18002b14c  mov     edx, 254h; void *
0x18002b151  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b156  nop
0x18002b157  mov     rcx, [rsp+0B8h+SRWLock]; SRWLock
0x18002b15c  test    rcx, rcx
0x18002b15f  jz      short loc_18002B168
0x18002b161  call    cs:__imp_ReleaseSRWLockShared
0x18002b167  nop
0x18002b168  mov     rcx, rbx
0x18002b16b  call    ?_Tidy@?$vector@V?$shared_ptr@VProviderContext@@@std@@V?$allocator@V?$shared_ptr@VProviderContext@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<ProviderContext>>::_Tidy(void)
0x18002b170  mov     eax, edi
0x18002b172  jmp     loc_18002B532
0x18002b177  lea     rcx, [rsp+0B8h+var_98]
0x18002b17c  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18002b181  nop
0x18002b182  lea     rdx, [rdi+20h]
0x18002b186  lea     rcx, [rsp+0B8h+var_68]
0x18002b18b  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x18002b190  nop
0x18002b191  mov     rdx, [rdi+28h]
0x18002b195  mov     rdx, [rdx]
0x18002b198  mov     [rsp+0B8h+var_70], rdx
0x18002b19d  cmp     byte ptr [rdx+19h], 0
0x18002b1a1  jnz     loc_18002B323
0x18002b1a7  add     rdx, 20h ; ' '
0x18002b1ab  lea     rcx, [rsp+0B8h+var_58]
0x18002b1b0  call    ??0?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VDevnodeFactory@DevnodeManagment@DAS@@@WRL@Microsoft@@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>(std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>> const &)
0x18002b1b5  nop
0x18002b1b6  mov     [rsp+0B8h+var_80], 0
0x18002b1bf  xor     edx, edx
0x18002b1c1  lea     rcx, [rsp+0B8h+var_80]
0x18002b1c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002b1cb  lea     rcx, [rsp+0B8h+var_58]
0x18002b1d0  cmp     [rsp+0B8h+var_40], 7
0x18002b1d6  cmova   rcx, [rsp+0B8h+var_58]; unsigned __int16 *
0x18002b1dc  lea     rdx, [rsp+0B8h+var_80]
0x18002b1e1  call    DafGetProviderNameFromAepId
0x18002b1e6  mov     esi, eax
0x18002b1e8  test    eax, eax
0x18002b1ea  jns     loc_18002B290
0x18002b1f0  mov     rcx, [rsp+0B8h]; this
0x18002b1f8  mov     r9d, eax; char *
0x18002b1fb  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18002b202  mov     edx, 25Eh; void *
0x18002b207  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b20c  nop
0x18002b20d  lea     rcx, [rsp+0B8h+var_80]
0x18002b212  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b217  nop
0x18002b218  lea     rcx, [rsp+0B8h+var_58]
0x18002b21d  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VDevnodeFactory@DevnodeManagment@DAS@@@WRL@Microsoft@@@std@@QEAA@XZ; std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>(void)
0x18002b222  nop
0x18002b223  mov     rcx, [rsp+0B8h+var_68]; SRWLock
0x18002b228  test    rcx, rcx
0x18002b22b  jz      short loc_18002B234
0x18002b22d  call    cs:__imp_ReleaseSRWLockShared
0x18002b233  nop
0x18002b234  mov     rcx, [rsp+0B8h+var_98]
0x18002b239  test    rcx, rcx
0x18002b23c  jz      short loc_18002B270
0x18002b23e  mov     rdx, qword ptr [rsp+0B8h+var_90]
0x18002b243  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002b248  mov     rcx, [rsp+0B8h+var_98]
0x18002b24d  mov     rdx, qword ptr [rsp+0B8h+var_90+8]
0x18002b252  sub     rdx, rcx
0x18002b255  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002b259  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b25e  mov     [rsp+0B8h+var_98], 0
0x18002b267  xorps   xmm0, xmm0
0x18002b26a  movdqu  [rsp+0B8h+var_90], xmm0
0x18002b270  mov     rcx, [rsp+0B8h+SRWLock]; SRWLock
0x18002b275  test    rcx, rcx
0x18002b278  jz      short loc_18002B281
0x18002b27a  call    cs:__imp_ReleaseSRWLockShared
0x18002b280  nop
0x18002b281  mov     rcx, rbx
0x18002b284  call    ?_Tidy@?$vector@V?$shared_ptr@VProviderContext@@@std@@V?$allocator@V?$shared_ptr@VProviderContext@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<ProviderContext>>::_Tidy(void)
0x18002b289  mov     eax, esi
0x18002b28b  jmp     loc_18002B532
0x18002b290  xor     esi, esi
0x18002b292  mov     rdx, [rbx]
0x18002b295  mov     ecx, esi
0x18002b297  mov     rax, [rbx+8]
0x18002b29b  sub     rax, rdx
0x18002b29e  sar     rax, 4
0x18002b2a2  cmp     rcx, rax
0x18002b2a5  jnb     short loc_18002B2DF
0x18002b2a7  add     rcx, rcx
0x18002b2aa  mov     rcx, [rdx+rcx*8]
0x18002b2ae  mov     rdx, [rsp+0B8h+var_80]
0x18002b2b3  mov     rcx, [rcx]
0x18002b2b6  call    cs:__imp__o__wcsicmp
0x18002b2bc  test    eax, eax
0x18002b2be  jnz     short loc_18002B31C
0x18002b2c0  mov     rax, qword ptr [rsp+0B8h+var_90]
0x18002b2c5  cmp     rax, qword ptr [rsp+0B8h+var_90+8]
0x18002b2ca  jz      short loc_18002B308
0x18002b2cc  lea     rdx, [rsp+0B8h+var_58]
0x18002b2d1  mov     rcx, rax
0x18002b2d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002b2d9  add     qword ptr [rsp+0B8h+var_90], 20h ; ' '
0x18002b2df  lea     rcx, [rsp+0B8h+var_80]
0x18002b2e4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b2e9  nop
0x18002b2ea  lea     rcx, [rsp+0B8h+var_58]
0x18002b2ef  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VDevnodeFactory@DevnodeManagment@DAS@@@WRL@Microsoft@@@std@@QEAA@XZ; std::pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>>(void)
0x18002b2f4  lea     rcx, [rsp+0B8h+var_70]
0x18002b2f9  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VProviderContext@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>>>,std::_Iterator_base0>::operator++(void)
0x18002b2fe  mov     rdx, [rsp+0B8h+var_70]
0x18002b303  jmp     loc_18002B19D
0x18002b308  lea     r8, [rsp+0B8h+var_58]
0x18002b30d  mov     rdx, rax
0x18002b310  lea     rcx, [rsp+0B8h+var_98]
0x18002b315  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18002b31a  jmp     short loc_18002B2DF
0x18002b31c  inc     esi
0x18002b31e  jmp     loc_18002B292
0x18002b323  mov     rcx, [rsp+0B8h+var_68]; SRWLock
0x18002b328  test    rcx, rcx
0x18002b32b  jz      short loc_18002B333
0x18002b32d  call    cs:__imp_ReleaseSRWLockShared
0x18002b333  mov     rcx, [rsp+0B8h+var_98]
0x18002b338  mov     rsi, rcx
0x18002b33b  mov     rdx, qword ptr [rsp+0B8h+var_90]
0x18002b340  mov     r15, rdx
0x18002b343  cmp     rsi, r15
0x18002b346  jz      loc_18002B4D5
0x18002b34c  mov     rdx, rsi
0x18002b34f  lea     rcx, [rsp+0B8h+var_58]
0x18002b354  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002b359  lea     rdx, [rsp+0B8h+var_58]
0x18002b35e  cmp     [rsp+0B8h+var_40], 7
0x18002b364  cmova   rdx, [rsp+0B8h+var_58]; unsigned __int16 *
0x18002b36a  xor     r8d, r8d; unsigned __int16 *
0x18002b36d  mov     rcx, rdi; this
0x18002b370  call    ?StopDevnodeManagement@DevnodeManager@DevnodeManagment@DAS@@QEAAJPEBG0@Z; DAS::DevnodeManagment::DevnodeManager::StopDevnodeManagement(ushort const *,ushort const *)
0x18002b375  mov     r14d, eax
0x18002b378  test    eax, eax
0x18002b37a  jns     loc_18002B404
0x18002b380  mov     rcx, [rsp+0B8h]; this
0x18002b388  mov     r9d, eax; char *
0x18002b38b  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18002b392  mov     edx, 26Dh; void *
0x18002b397  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b39c  lea     rcx, [rsp+0B8h+var_58]
0x18002b3a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b3a6  nop
0x18002b3a7  mov     rcx, [rsp+0B8h+var_98]
0x18002b3ac  test    rcx, rcx
0x18002b3af  jz      short loc_18002B3E3
0x18002b3b1  mov     rdx, qword ptr [rsp+0B8h+var_90]
0x18002b3b6  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002b3bb  mov     rcx, [rsp+0B8h+var_98]
0x18002b3c0  mov     rdx, qword ptr [rsp+0B8h+var_90+8]
0x18002b3c5  sub     rdx, rcx
0x18002b3c8  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002b3cc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b3d1  mov     [rsp+0B8h+var_98], 0
0x18002b3da  xorps   xmm0, xmm0
0x18002b3dd  movdqu  [rsp+0B8h+var_90], xmm0
0x18002b3e3  mov     rcx, [rsp+0B8h+SRWLock]; SRWLock
0x18002b3e8  test    rcx, rcx
0x18002b3eb  jz      short loc_18002B3F4
0x18002b3ed  call    cs:__imp_ReleaseSRWLockShared
0x18002b3f3  nop
0x18002b3f4  mov     rcx, rbx
0x18002b3f7  call    ?_Tidy@?$vector@V?$shared_ptr@VProviderContext@@@std@@V?$allocator@V?$shared_ptr@VProviderContext@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<ProviderContext>>::_Tidy(void)
0x18002b3fc  mov     eax, r14d
0x18002b3ff  jmp     loc_18002B532
0x18002b404  test    r12b, r12b
0x18002b407  jz      loc_18002B4B8
0x18002b40d  lea     rdx, [rsp+0B8h+var_58]
0x18002b412  cmp     [rsp+0B8h+var_40], 7
0x18002b418  cmova   rdx, [rsp+0B8h+var_58]; unsigned __int16 *
0x18002b41e  xor     r9d, r9d; void *
0x18002b421  xor     r8d, r8d; unsigned __int16 *
0x18002b424  mov     rcx, rdi; this
0x18002b427  call    ?StartDevnodeManagementUnlocked@DevnodeManager@DevnodeManagment@DAS@@AEAAJPEBG0PEAX@Z; DAS::DevnodeManagment::DevnodeManager::StartDevnodeManagementUnlocked(ushort const *,ushort const *,void *)
0x18002b42c  mov     r14d, eax
0x18002b42f  test    eax, eax
0x18002b431  jns     loc_18002B4B8
0x18002b437  mov     rcx, [rsp+0B8h]; this
0x18002b43f  mov     r9d, eax; char *
0x18002b442  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18002b449  mov     edx, 271h; void *
0x18002b44e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b453  lea     rcx, [rsp+0B8h+var_58]
0x18002b458  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b45d  nop
0x18002b45e  mov     rcx, [rsp+0B8h+var_98]
0x18002b463  test    rcx, rcx
0x18002b466  jz      short loc_18002B49A
0x18002b468  mov     rdx, qword ptr [rsp+0B8h+var_90]
0x18002b46d  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002b472  mov     rcx, [rsp+0B8h+var_98]
0x18002b477  mov     rdx, qword ptr [rsp+0B8h+var_90+8]
0x18002b47c  sub     rdx, rcx
0x18002b47f  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002b483  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b488  mov     [rsp+0B8h+var_98], 0
0x18002b491  xorps   xmm0, xmm0
0x18002b494  movdqu  [rsp+0B8h+var_90], xmm0
0x18002b49a  mov     rcx, [rsp+0B8h+SRWLock]; SRWLock
0x18002b49f  test    rcx, rcx
0x18002b4a2  jz      short loc_18002B4AB
0x18002b4a4  call    cs:__imp_ReleaseSRWLockShared
0x18002b4aa  nop
0x18002b4ab  mov     rcx, rbx
0x18002b4ae  call    ?_Tidy@?$vector@V?$shared_ptr@VProviderContext@@@std@@V?$allocator@V?$shared_ptr@VProviderContext@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<ProviderContext>>::_Tidy(void)
0x18002b4b3  mov     eax, r14d
0x18002b4b6  jmp     short loc_18002B532
0x18002b4b8  lea     rcx, [rsp+0B8h+var_58]
0x18002b4bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b4c2  add     rsi, 20h ; ' '
0x18002b4c6  mov     rdx, qword ptr [rsp+0B8h+var_90]
0x18002b4cb  mov     rcx, [rsp+0B8h+var_98]
0x18002b4d0  jmp     loc_18002B343
0x18002b4d5  test    rcx, rcx
0x18002b4d8  jz      short loc_18002B507
0x18002b4da  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002b4df  mov     rcx, [rsp+0B8h+var_98]
0x18002b4e4  mov     rdx, qword ptr [rsp+0B8h+var_90+8]
0x18002b4e9  sub     rdx, rcx
0x18002b4ec  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002b4f0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b4f5  mov     [rsp+0B8h+var_98], 0
0x18002b4fe  xorps   xmm0, xmm0
0x18002b501  movdqu  [rsp+0B8h+var_90], xmm0
0x18002b507  mov     rcx, [rsp+0B8h+SRWLock]; SRWLock
0x18002b50c  test    rcx, rcx
0x18002b50f  jz      short loc_18002B518
0x18002b511  call    cs:__imp_ReleaseSRWLockShared
0x18002b517  nop
0x18002b518  mov     rcx, rbx
0x18002b51b  call    ?_Tidy@?$vector@V?$shared_ptr@VProviderContext@@@std@@V?$allocator@V?$shared_ptr@VProviderContext@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<ProviderContext>>::_Tidy(void)
0x18002b520  xor     eax, eax
0x18002b522  jmp     short loc_18002B532
0x18002b524  mov     rcx, [rsp+0B8h+var_60]
0x18002b529  call    ?_Tidy@?$vector@V?$shared_ptr@VProviderContext@@@std@@V?$allocator@V?$shared_ptr@VProviderContext@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<ProviderContext>>::_Tidy(void)
0x18002b52e  mov     eax, dword ptr [rsp+0B8h+var_80]
0x18002b532  mov     rcx, [rsp+0B8h+var_30]
0x18002b53a  xor     rcx, rsp; StackCookie
0x18002b53d  call    __security_check_cookie
0x18002b542  mov     rbx, [rsp+0B8h+arg_10]
0x18002b54a  add     rsp, 90h
0x18002b551  pop     r15
0x18002b553  pop     r14
0x18002b555  pop     r12
0x18002b557  pop     rdi
0x18002b558  pop     rsi
0x18002b559  retn
```
