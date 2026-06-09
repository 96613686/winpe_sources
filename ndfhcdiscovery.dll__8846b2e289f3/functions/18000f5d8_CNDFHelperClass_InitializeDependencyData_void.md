# CNDFHelperClass::InitializeDependencyData(void)

- ea: `0x18000f5d8`
- end: `0x18000f967`
- name: `?InitializeDependencyData@CNDFHelperClass@@AEAAJXZ`
- size: `911`
- prototype: `__int64 __fastcall(CNDFHelperClass *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000da20`

## callees

- `0x180003414`
- `0x18000a528`
- `0x18000d2f0`
- `0x18000f5d8`
- `0x180011178`
- `0x1800117e8`
- `0x180011920`
- `0x180013686`
- `0x1800136b0`
- `0x180015010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f7c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f7c3`
- `ADVAPI32!RegCloseKey` at `0x18000f6ac`
- `ADVAPI32!RegCloseKey` at `0x18000f8a6`
- `ADVAPI32!RegCloseKey` at `0x18000f937`
- `ADVAPI32!RegCloseKey` at `0x18000f6ac`
- `ADVAPI32!RegCloseKey` at `0x18000f8a6`
- `ADVAPI32!RegCloseKey` at `0x18000f937`
- `ADVAPI32!RegEnumValueW` at `0x18000f755`
- `ADVAPI32!RegEnumValueW` at `0x18000f755`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f679`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f679`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CNDFHelperClass::InitializeDependencyData(CNDFHelperClass *this)
{
  HKEY v2; // r14
  signed int v3; // ebx
  LSTATUS v4; // eax
  int v5; // ecx
  int v6; // edi
  DWORD v8; // r12d
  __int64 v9; // rax
  int v10; // ecx
  HKEY v11; // rbx
  unsigned int v12; // r8d
  __int64 *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  HKEY hKey; // [rsp+40h] [rbp-4C8h] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-4C0h] BYREF
  int v19; // [rsp+4Ch] [rbp-4BCh]
  __int128 v20; // [rsp+50h] [rbp-4B8h] BYREF
  __int64 v21; // [rsp+60h] [rbp-4A8h]
  HKEY v22; // [rsp+68h] [rbp-4A0h]
  __int64 v23; // [rsp+70h] [rbp-498h]
  __int64 v24; // [rsp+78h] [rbp-490h]
  void *v25[3]; // [rsp+80h] [rbp-488h] BYREF
  unsigned __int64 v26; // [rsp+98h] [rbp-470h]
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-468h] BYREF
  WCHAR ValueName[264]; // [rsp+2B0h] [rbp-258h] BYREF

  v2 = 0;
  v23 = 0;
  v24 = 0;
  memset_0(SubKey, 0, 0x208u);
  v3 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", *((_QWORD *)this + 3), L"Dependencies");
  if ( v3 >= 0 )
  {
    hKey = 0;
    v4 = RegOpenKeyExW(*((HKEY *)this + 4), SubKey, 0, 0x20019u, &hKey);
    v6 = v4;
    if ( !v4 )
      v2 = hKey;
    v22 = v2;
    if ( v4 == 2 )
    {
      *((_DWORD *)this + 34) = 1;
      if ( v2 )
        RegCloseKey(v2);
      return 0;
    }
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    else
      v3 = v4;
    if ( v3 >= 0 )
    {
      v20 = 0;
      v21 = 0;
      v8 = 0;
      while ( !v6 )
      {
        cchValueName = 260;
        v6 = RegEnumValueW(v2, v8, ValueName, &cchValueName, 0, 0, 0, 0);
        v19 = v6;
        if ( v6 )
        {
          if ( v6 != 259 )
          {
            v9 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
            try
            {
              hKey = (HKEY)(v9 + 24);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                &hKey,
                L"Enum Index: %d",
                v8);
              v11 = hKey;
              if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
              {
                if ( v6 > 0 )
                  v12 = (unsigned __int16)v6 | 0x80070000;
                else
                  v12 = v6;
                McTemplateU0qqzz_EventWriteTransfer(
                  v10,
                  (unsigned int)RegistryError,
                  v12,
                  1280,
                  (__int64)SubKey,
                  (__int64)hKey);
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF) <= 1 )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
            }
            catch ( ATL::CAtlException )
            {
              v6 = v19;
              v2 = v22;
            }
            if ( v6 > 0 )
              v6 = (unsigned __int16)v6 | 0x80070000;
            std::vector<std::wstring>::_Tidy(&v20);
            if ( v2 )
              RegCloseKey(v2);
            return (unsigned int)v6;
          }
        }
        else
        {
          v26 = 7;
          v25[2] = 0;
          LOWORD(v25[0]) = 0;
          std::wstring::assign(v25, ValueName);
          std::vector<std::wstring>::push_back(&v20, v25);
          if ( v26 >= 8 )
            operator delete(v25[0]);
        }
        ++v8;
      }
      if ( v6 == 259 )
      {
        v13 = (__int64 *)((char *)this + 144);
        if ( (__int128 *)((char *)this + 144) != &v20 )
        {
          v14 = *v13;
          *v13 = v20;
          *(_QWORD *)&v20 = v14;
          v15 = *((_QWORD *)this + 19);
          *((_QWORD *)this + 19) = *((_QWORD *)&v20 + 1);
          *((_QWORD *)&v20 + 1) = v15;
          v16 = *((_QWORD *)this + 20);
          *((_QWORD *)this + 20) = v21;
          v21 = v16;
        }
        *((_DWORD *)this + 34) = 1;
      }
      else if ( v6 > 0 )
      {
        v3 = (unsigned __int16)v6 | 0x80070000;
      }
      else
      {
        v3 = v6;
      }
      std::vector<std::wstring>::_Tidy(&v20);
    }
    else if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
    {
      McTemplateU0qqzz_EventWriteTransfer(
        v5,
        (unsigned int)RegistryError,
        v3,
        1255,
        (__int64)SubKey,
        (__int64)L"Dependencies");
    }
  }
  if ( v2 )
    RegCloseKey(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000f5d8  push    rbx
0x18000f5da  push    rsi
0x18000f5db  push    rdi
0x18000f5dc  push    r12
0x18000f5de  push    r13
0x18000f5e0  push    r14
0x18000f5e2  sub     rsp, 4D8h
0x18000f5e9  mov     rax, cs:__security_cookie
0x18000f5f0  xor     rax, rsp
0x18000f5f3  mov     [rsp+508h+var_48], rax
0x18000f5fb  mov     r13, rcx
0x18000f5fe  xor     esi, esi
0x18000f600  mov     r14d, esi
0x18000f603  mov     [rsp+508h+var_498], rsi
0x18000f608  mov     [rsp+508h+var_490], rsi
0x18000f60d  xor     edx, edx; Val
0x18000f60f  mov     r8d, 208h; Size
0x18000f615  lea     rcx, [rsp+508h+SubKey]; void *
0x18000f61d  call    memset_0
0x18000f622  lea     r12, aDependencies; "Dependencies"
0x18000f629  mov     [rsp+508h+phkResult], r12
0x18000f62e  mov     r9, [r13+18h]
0x18000f632  lea     r8, aSS; "%s\\%s"
0x18000f639  mov     edx, 104h; unsigned __int64
0x18000f63e  lea     rcx, [rsp+508h+SubKey]; unsigned __int16 *
0x18000f646  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f64b  mov     ebx, eax
0x18000f64d  test    eax, eax
0x18000f64f  js      loc_18000F92F
0x18000f655  mov     [rsp+508h+hKey], rsi
0x18000f65a  lea     rax, [rsp+508h+hKey]
0x18000f65f  mov     [rsp+508h+phkResult], rax; phkResult
0x18000f664  mov     r9d, 20019h; samDesired
0x18000f66a  xor     r8d, r8d; ulOptions
0x18000f66d  lea     rdx, [rsp+508h+SubKey]; lpSubKey
0x18000f675  mov     rcx, [r13+20h]; hKey
0x18000f679  call    cs:__imp_RegOpenKeyExW
0x18000f680  nop     dword ptr [rax+rax+00h]
0x18000f685  mov     edi, eax
0x18000f687  test    eax, eax
0x18000f689  cmovz   r14, [rsp+508h+hKey]
0x18000f68f  mov     [rsp+508h+var_4A0], r14
0x18000f694  cmp     eax, 2
0x18000f697  jnz     short loc_18000F6BF
0x18000f699  mov     dword ptr [r13+88h], 1
0x18000f6a4  test    r14, r14
0x18000f6a7  jz      short loc_18000F6B8
0x18000f6a9  mov     rcx, r14; hKey
0x18000f6ac  call    cs:__imp_RegCloseKey
0x18000f6b3  nop     dword ptr [rax+rax+00h]
0x18000f6b8  xor     eax, eax
0x18000f6ba  jmp     loc_18000F945
0x18000f6bf  test    eax, eax
0x18000f6c1  jg      short loc_18000F6C7
0x18000f6c3  mov     ebx, eax
0x18000f6c5  jmp     short loc_18000F6D0
0x18000f6c7  movzx   ebx, ax
0x18000f6ca  or      ebx, 80070000h
0x18000f6d0  test    ebx, ebx
0x18000f6d2  jns     short loc_18000F70D
0x18000f6d4  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000f6db  jz      loc_18000F92F
0x18000f6e1  mov     [rsp+508h+lpType], r12
0x18000f6e6  lea     rax, [rsp+508h+SubKey]
0x18000f6ee  mov     [rsp+508h+phkResult], rax
0x18000f6f3  mov     r9d, 4E7h
0x18000f6f9  mov     r8d, ebx
0x18000f6fc  lea     rdx, RegistryError
0x18000f703  call    McTemplateU0qqzz_EventWriteTransfer
0x18000f708  jmp     loc_18000F92F
0x18000f70d  xorps   xmm0, xmm0
0x18000f710  movdqu  [rsp+508h+var_4B8], xmm0
0x18000f716  mov     [rsp+508h+var_4A8], rsi
0x18000f71b  mov     r12d, esi
0x18000f71e  test    edi, edi
0x18000f720  jnz     loc_18000F8B9
0x18000f726  mov     [rsp+508h+cchValueName], 104h
0x18000f72e  mov     [rsp+508h+lpcbData], rsi; lpcbData
0x18000f733  mov     [rsp+508h+lpData], rsi; lpData
0x18000f738  mov     [rsp+508h+lpType], rsi; lpType
0x18000f73d  mov     [rsp+508h+phkResult], rsi; lpReserved
0x18000f742  lea     r9, [rsp+508h+cchValueName]; lpcchValueName
0x18000f747  lea     r8, [rsp+508h+ValueName]; lpValueName
0x18000f74f  mov     edx, r12d; dwIndex
0x18000f752  mov     rcx, r14; hKey
0x18000f755  call    cs:__imp_RegEnumValueW
0x18000f75c  nop     dword ptr [rax+rax+00h]
0x18000f761  mov     edi, eax
0x18000f763  mov     [rsp+508h+var_4BC], eax
0x18000f767  test    eax, eax
0x18000f769  jnz     short loc_18000F7D7
0x18000f76b  mov     [rsp+508h+var_470], 7
0x18000f777  mov     [rsp+508h+var_478], rsi
0x18000f77f  mov     word ptr [rsp+508h+var_488], si
0x18000f787  lea     rdx, [rsp+508h+ValueName]; Src
0x18000f78f  lea     rcx, [rsp+508h+var_488]; void *
0x18000f797  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000f79c  nop
0x18000f79d  lea     rdx, [rsp+508h+var_488]
0x18000f7a5  lea     rcx, [rsp+508h+var_4B8]
0x18000f7aa  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18000f7af  nop
0x18000f7b0  cmp     [rsp+508h+var_470], 8
0x18000f7b9  jb      short loc_18000F7CF
0x18000f7bb  mov     rcx, [rsp+508h+var_488]
0x18000f7c3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f7ca  nop     dword ptr [rax+rax+00h]
0x18000f7cf  inc     r12d
0x18000f7d2  jmp     loc_18000F71E
0x18000f7d7  cmp     edi, 103h
0x18000f7dd  jz      short loc_18000F7CF
0x18000f7df  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000f7e6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000f7ed  mov     rax, [rax+18h]
0x18000f7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7f6  add     rax, 18h
0x18000f7fa  mov     [rsp+508h+hKey], rax
0x18000f7ff  mov     r8d, r12d
0x18000f802  lea     rdx, aEnumIndexD; "Enum Index: %d"
0x18000f809  lea     rcx, [rsp+508h+hKey]
0x18000f80e  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000f813  mov     rbx, [rsp+508h+hKey]
0x18000f818  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000f81f  jz      short loc_18000F85A
0x18000f821  test    edi, edi
0x18000f823  jg      short loc_18000F82A
0x18000f825  mov     r8d, edi
0x18000f828  jmp     short loc_18000F835
0x18000f82a  movzx   r8d, di
0x18000f82e  or      r8d, 80070000h
0x18000f835  mov     [rsp+508h+lpType], rbx
0x18000f83a  lea     rax, [rsp+508h+SubKey]
0x18000f842  mov     [rsp+508h+phkResult], rax
0x18000f847  mov     r9d, 500h
0x18000f84d  lea     rdx, RegistryError
0x18000f854  call    McTemplateU0qqzz_EventWriteTransfer
0x18000f859  nop
0x18000f85a  lea     rdx, [rbx-18h]
0x18000f85e  or      eax, 0FFFFFFFFh
0x18000f861  lock xadd [rdx+10h], eax
0x18000f866  sub     eax, 1
0x18000f869  jg      short loc_18000F87B
0x18000f86b  mov     rcx, [rdx]
0x18000f86e  mov     rax, [rcx]
0x18000f871  mov     rax, [rax+8]
0x18000f875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f87a  nop
0x18000f87b  jmp     short loc_18000F886
0x18000f87d  mov     edi, [rsp+508h+var_4BC]
0x18000f881  mov     r14, [rsp+508h+var_4A0]
0x18000f886  test    edi, edi
0x18000f888  jle     short loc_18000F893
0x18000f88a  movzx   edi, di
0x18000f88d  or      edi, 80070000h
0x18000f893  lea     rcx, [rsp+508h+var_4B8]
0x18000f898  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000f89d  nop
0x18000f89e  test    r14, r14
0x18000f8a1  jz      short loc_18000F8B2
0x18000f8a3  mov     rcx, r14; hKey
0x18000f8a6  call    cs:__imp_RegCloseKey
0x18000f8ad  nop     dword ptr [rax+rax+00h]
0x18000f8b2  mov     eax, edi
0x18000f8b4  jmp     loc_18000F945
0x18000f8b9  cmp     edi, 103h
0x18000f8bf  jz      short loc_18000F8D4
0x18000f8c1  test    edi, edi
0x18000f8c3  jg      short loc_18000F8C9
0x18000f8c5  mov     ebx, edi
0x18000f8c7  jmp     short loc_18000F924
0x18000f8c9  movzx   ebx, di
0x18000f8cc  or      ebx, 80070000h
0x18000f8d2  jmp     short loc_18000F924
0x18000f8d4  lea     rdx, [r13+90h]
0x18000f8db  lea     rax, [rsp+508h+var_4B8]
0x18000f8e0  cmp     rdx, rax
0x18000f8e3  jz      short loc_18000F919
0x18000f8e5  mov     rcx, [rdx]
0x18000f8e8  mov     rax, qword ptr [rsp+508h+var_4B8]
0x18000f8ed  mov     [rdx], rax
0x18000f8f0  mov     qword ptr [rsp+508h+var_4B8], rcx
0x18000f8f5  mov     rcx, [rdx+8]
0x18000f8f9  mov     rax, qword ptr [rsp+508h+var_4B8+8]
0x18000f8fe  mov     [rdx+8], rax
0x18000f902  mov     qword ptr [rsp+508h+var_4B8+8], rcx
0x18000f907  mov     rcx, [rdx+10h]
0x18000f90b  mov     rax, [rsp+508h+var_4A8]
0x18000f910  mov     [rdx+10h], rax
0x18000f914  mov     [rsp+508h+var_4A8], rcx
0x18000f919  mov     dword ptr [r13+88h], 1
0x18000f924  lea     rcx, [rsp+508h+var_4B8]
0x18000f929  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000f92e  nop
0x18000f92f  test    r14, r14
0x18000f932  jz      short loc_18000F943
0x18000f934  mov     rcx, r14; hKey
0x18000f937  call    cs:__imp_RegCloseKey
0x18000f93e  nop     dword ptr [rax+rax+00h]
0x18000f943  mov     eax, ebx
0x18000f945  mov     rcx, [rsp+508h+var_48]
0x18000f94d  xor     rcx, rsp; StackCookie
0x18000f950  call    __security_check_cookie
0x18000f955  add     rsp, 4D8h
0x18000f95c  pop     r14
0x18000f95e  pop     r13
0x18000f960  pop     r12
0x18000f962  pop     rdi
0x18000f963  pop     rsi
0x18000f964  pop     rbx
0x18000f965  retn
```
