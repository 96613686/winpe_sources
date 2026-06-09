# CMVEngine::ShouldRetryProvisionData(_MVProvisionData const &)

- ea: `0x18001fab8`
- end: `0x18001fde6`
- name: `?ShouldRetryProvisionData@CMVEngine@@AEAA_NAEBU_MVProvisionData@@@Z`
- size: `814`
- prototype: `bool __fastcall(CMVEngine *__hidden this, const struct _MVProvisionData *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x180018698`

## callees

- `0x18000af20`
- `0x18000b030`
- `0x180011460`
- `0x18001fab8`
- `0x180020af4`
- `0x180020c74`
- `0x180021cf4`
- `0x180022088`
- `0x18002f9bc`
- `0x18003cc98`
- `0x18003d1b8`
- `0x18003d28c`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001fb70`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fc7f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fcbd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd1a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fdaf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fb70`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fc7f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fcbd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd1a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fdaf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fc67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fc67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fc2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fc9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fd3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fc2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fc9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fd3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fc34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fc34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc21`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall CMVEngine::ShouldRetryProvisionData(CMVEngine *this, const struct _MVProvisionData *a2)
{
  char *v3; // rdx
  unsigned __int64 v4; // r8
  void **v5; // rax
  HKEY *v6; // r14
  __int64 v7; // rcx
  _WORD *v8; // rcx
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  unsigned __int64 v12; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v17; // [rsp+50h] [rbp-B0h]
  void *v18[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v19; // [rsp+70h] [rbp-90h]
  _QWORD v20[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD *v21; // [rsp+90h] [rbp-70h] BYREF
  __int64 v22; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v23; // [rsp+A8h] [rbp-58h]
  __int16 v24; // [rsp+B0h] [rbp-50h]
  __int64 v25; // [rsp+C0h] [rbp-40h]
  __int64 v26; // [rsp+C8h] [rbp-38h]
  int v27; // [rsp+D4h] [rbp-2Ch]
  unsigned __int64 v28; // [rsp+D8h] [rbp-28h]
  __int64 v29; // [rsp+E8h] [rbp-18h]
  __int64 v30; // [rsp+F0h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v3 = (char *)*((_QWORD *)a2 + 6);
  v17 = 7;
  v16 = 0;
  LOWORD(lpSubKey[0]) = 0;
  if ( *(_WORD *)v3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&v3[2 * v4] );
  }
  else
  {
    v4 = 0;
  }
  std::wstring::assign(lpSubKey, v3, v4);
  v5 = (void **)std::map<std::wstring,std::unique_ptr<ProvResults>>::at((_QWORD *)this + 40, lpSubKey);
  v19 = 7;
  v18[2] = 0;
  LOWORD(v18[0]) = 0;
  std::wstring::assign(v18, v5, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v17 >= 8 )
    operator delete((void *)lpSubKey[0]);
  v17 = 7;
  v16 = 0;
  LOWORD(lpSubKey[0]) = 0;
  v6 = (HKEY *)*std::map<std::wstring,std::unique_ptr<ProvResults>>::at((_QWORD *)this + 38, v18);
  v20[0] = 0;
  v20[1] = 0;
  v20[0] = std::_Tree_alloc<0,std::_Tree_base_types<unsigned int>>::_Buyheadnode(v7);
  v23 = 7;
  v22 = 0;
  LOWORD(v21) = 0;
  v26 = 7;
  v25 = 0;
  v24 = 0;
  v29 = 0;
  v30 = 0;
  v29 = std::_Tree_alloc<0,std::_Tree_base_types<std::wstring>>::_Buyheadnode();
  v8 = &v21;
  if ( v23 >= 8 )
    v8 = v21;
  v22 = 0;
  *v8 = 0;
  v27 = 0;
  v28 = 0;
  if ( !ProvResults::LazyOpenParentKey((ProvResults *)v6) )
    goto LABEL_17;
  ProvResults::GetChildKeyNameFromProvData(lpSubKey);
  hKey = 0;
  v9 = (const WCHAR *)lpSubKey;
  if ( v17 >= 8 )
    v9 = lpSubKey[0];
  v10 = RegOpenKeyExW(v6[9], v9, 0, 1u, &hKey);
  if ( v10 == 2 )
  {
    if ( v17 >= 8 )
      operator delete((void *)lpSubKey[0]);
    v17 = 7;
    v16 = 0;
    LOWORD(lpSubKey[0]) = 0;
    if ( hKey )
      RegCloseKey(hKey);
LABEL_17:
    ResultData::~ResultData((ResultData *)v20);
    if ( v19 >= 8 )
      operator delete(v18[0]);
    return 0;
  }
  if ( v10 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x21E,
      (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v10,
      phkResult);
  ProvResults::ResultDataFromResultKey(lpSubKey, &hKey, v20);
  if ( v17 >= 8 )
    operator delete((void *)lpSubKey[0]);
  v17 = 7;
  v16 = 0;
  LOWORD(lpSubKey[0]) = 0;
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v28 )
    goto LABEL_30;
  v12 = *((_QWORD *)this + 21);
  if ( v12 > 0xFFFFFFFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\retryschedule.cpp",
      v12 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
      phkResult);
  if ( v28 >= (unsigned int)*((_QWORD *)this + 21) + 2 )
  {
LABEL_30:
    if ( !*((_DWORD *)this + 47) || v27 != 44761091 )
      goto LABEL_17;
  }
  ResultData::~ResultData((ResultData *)v20);
  if ( v19 >= 8 )
    operator delete(v18[0]);
  return 1;
}

```

## disassembly

```asm
0x18001fab8  mov     [rsp-8+arg_10], rbx
0x18001fabd  mov     [rsp-8+arg_18], rsi
0x18001fac2  push    rbp
0x18001fac3  push    rdi
0x18001fac4  push    r12
0x18001fac6  push    r14
0x18001fac8  push    r15
0x18001faca  lea     rbp, [rsp-10h]
0x18001facf  sub     rsp, 110h
0x18001fad6  mov     rax, cs:__security_cookie
0x18001fadd  xor     rax, rsp
0x18001fae0  mov     [rbp+30h+var_30], rax
0x18001fae4  mov     rbx, rdx
0x18001fae7  mov     rsi, rcx
0x18001faea  mov     rdx, [rdx+30h]; Src
0x18001faee  mov     r12d, 7
0x18001faf4  mov     [rsp+130h+var_E0], r12
0x18001faf9  xor     r15d, r15d
0x18001fafc  mov     [rsp+130h+var_E8], r15
0x18001fb01  mov     word ptr [rsp+130h+lpSubKey], r15w
0x18001fb07  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001fb0b  cmp     [rdx], r15w
0x18001fb0f  jnz     short loc_18001FB16
0x18001fb11  mov     r8d, r15d
0x18001fb14  jmp     short loc_18001FB23
0x18001fb16  mov     r8, rdi
0x18001fb19  inc     r8
0x18001fb1c  cmp     [rdx+r8*2], r15w
0x18001fb21  jnz     short loc_18001FB19
0x18001fb23  lea     rcx, [rsp+130h+lpSubKey]; void *
0x18001fb28  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001fb2d  nop
0x18001fb2e  lea     rcx, [rsi+140h]
0x18001fb35  lea     rdx, [rsp+130h+lpSubKey]
0x18001fb3a  call    ?at@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::map<std::wstring,std::unique_ptr<ProvResults>>::at(std::wstring const &)
0x18001fb3f  mov     [rsp+130h+var_C0], r12
0x18001fb44  mov     [rsp+130h+var_C8], r15
0x18001fb49  mov     word ptr [rsp+130h+var_D8], r15w
0x18001fb4f  mov     r9, rdi
0x18001fb52  xor     r8d, r8d
0x18001fb55  mov     rdx, rax
0x18001fb58  lea     rcx, [rsp+130h+var_D8]; void *
0x18001fb5d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001fb62  nop
0x18001fb63  cmp     [rsp+130h+var_E0], 8
0x18001fb69  jb      short loc_18001FB76
0x18001fb6b  mov     rcx, [rsp+130h+lpSubKey]
0x18001fb70  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fb76  mov     [rsp+130h+var_E0], r12
0x18001fb7b  mov     [rsp+130h+var_E8], r15
0x18001fb80  mov     word ptr [rsp+130h+lpSubKey], r15w
0x18001fb86  lea     rcx, [rsi+130h]
0x18001fb8d  lea     rdx, [rsp+130h+var_D8]
0x18001fb92  call    ?at@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::map<std::wstring,std::unique_ptr<ProvResults>>::at(std::wstring const &)
0x18001fb97  mov     r14, [rax]
0x18001fb9a  mov     [rbp+30h+var_B0], r15
0x18001fb9e  mov     [rbp+30h+var_A8], r15
0x18001fba2  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@IV?$allocator@I@std@@@std@@@std@@QEAAPEAU?$_Tree_node@IPEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<uint>>::_Buyheadnode(void)
0x18001fba7  mov     [rbp+30h+var_B0], rax
0x18001fbab  mov     [rbp+30h+var_88], r12
0x18001fbaf  mov     [rbp+30h+var_90], r15
0x18001fbb3  mov     word ptr [rbp+30h+var_A0], r15w
0x18001fbb8  mov     [rbp+30h+var_68], r12
0x18001fbbc  mov     [rbp+30h+var_70], r15
0x18001fbc0  mov     [rbp+30h+var_80], r15w
0x18001fbc5  mov     [rbp+30h+var_48], r15
0x18001fbc9  mov     [rbp+30h+var_40], r15
0x18001fbcd  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::wstring>>::_Buyheadnode(void)
0x18001fbd2  mov     [rbp+30h+var_48], rax
0x18001fbd6  lea     rcx, [rbp+30h+var_A0]
0x18001fbda  cmp     [rbp+30h+var_88], 8
0x18001fbdf  cmovnb  rcx, [rbp+30h+var_A0]
0x18001fbe4  mov     [rbp+30h+var_90], r15
0x18001fbe8  mov     [rcx], r15w
0x18001fbec  mov     [rbp+30h+var_5C], r15d
0x18001fbf0  mov     [rbp+30h+var_58], r15
0x18001fbf4  mov     rcx, r14; this
0x18001fbf7  call    ?LazyOpenParentKey@ProvResults@@AEBA_NXZ; ProvResults::LazyOpenParentKey(void)
0x18001fbfc  test    al, al
0x18001fbfe  jz      loc_18001FCA6
0x18001fc04  mov     [rsp+130h+hKey], r15
0x18001fc09  mov     rdx, rbx
0x18001fc0c  lea     rcx, [rsp+130h+lpSubKey]; void *
0x18001fc11  call    ?GetChildKeyNameFromProvData@ProvResults@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_MVProvisionData@@@Z; ProvResults::GetChildKeyNameFromProvData(_MVProvisionData const &)
0x18001fc16  nop
0x18001fc17  mov     rdi, [rsp+130h+hKey]
0x18001fc1c  test    rdi, rdi
0x18001fc1f  jz      short loc_18001FC3A
0x18001fc21  call    cs:__imp_GetLastError
0x18001fc27  mov     ebx, eax
0x18001fc29  mov     rcx, rdi; hKey
0x18001fc2c  call    cs:__imp_RegCloseKey
0x18001fc32  mov     ecx, ebx; dwErrCode
0x18001fc34  call    cs:__imp_SetLastError
0x18001fc3a  mov     [rsp+130h+hKey], r15
0x18001fc3f  lea     rdx, [rsp+130h+lpSubKey]
0x18001fc44  cmp     [rsp+130h+var_E0], 8
0x18001fc4a  cmovnb  rdx, [rsp+130h+lpSubKey]; lpSubKey
0x18001fc50  lea     rax, [rsp+130h+hKey]
0x18001fc55  mov     qword ptr [rsp+130h+phkResult], rax; unsigned int
0x18001fc5a  mov     r9d, 1; samDesired
0x18001fc60  xor     r8d, r8d; ulOptions
0x18001fc63  mov     rcx, [r14+48h]; hKey
0x18001fc67  call    cs:__imp_RegOpenKeyExW
0x18001fc6d  cmp     eax, 2
0x18001fc70  jnz     short loc_18001FCED
0x18001fc72  cmp     [rsp+130h+var_E0], 8
0x18001fc78  jb      short loc_18001FC85
0x18001fc7a  mov     rcx, [rsp+130h+lpSubKey]
0x18001fc7f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fc85  mov     [rsp+130h+var_E0], r12
0x18001fc8a  mov     [rsp+130h+var_E8], r15
0x18001fc8f  mov     word ptr [rsp+130h+lpSubKey], r15w
0x18001fc95  mov     rcx, [rsp+130h+hKey]; hKey
0x18001fc9a  test    rcx, rcx
0x18001fc9d  jz      short loc_18001FCA6
0x18001fc9f  call    cs:__imp_RegCloseKey
0x18001fca5  nop
0x18001fca6  lea     rcx, [rbp+30h+var_B0]; this
0x18001fcaa  call    ??1ResultData@@QEAA@XZ; ResultData::~ResultData(void)
0x18001fcaf  nop
0x18001fcb0  cmp     [rsp+130h+var_C0], 8
0x18001fcb6  jb      short loc_18001FCC3
0x18001fcb8  mov     rcx, [rsp+130h+var_D8]
0x18001fcbd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fcc3  xor     al, al
0x18001fcc5  mov     rcx, [rbp+30h+var_30]
0x18001fcc9  xor     rcx, rsp; StackCookie
0x18001fccc  call    __security_check_cookie
0x18001fcd1  lea     r11, [rsp+130h+var_20]
0x18001fcd9  mov     rbx, [r11+40h]
0x18001fcdd  mov     rsi, [r11+48h]
0x18001fce1  mov     rsp, r11
0x18001fce4  pop     r15
0x18001fce6  pop     r14
0x18001fce8  pop     r12
0x18001fcea  pop     rdi
0x18001fceb  pop     rbp
0x18001fcec  retn
0x18001fced  mov     rcx, [rbp+38h]; this
0x18001fcf1  test    eax, eax
0x18001fcf3  jnz     loc_18001FDD1
0x18001fcf9  lea     r8, [rbp+30h+var_B0]
0x18001fcfd  lea     rdx, [rsp+130h+hKey]
0x18001fd02  lea     rcx, [rsp+130h+lpSubKey]
0x18001fd07  call    ?ResultDataFromResultKey@ProvResults@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUResultData@@@Z; ProvResults::ResultDataFromResultKey(std::wstring const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,ResultData *)
0x18001fd0c  nop
0x18001fd0d  cmp     [rsp+130h+var_E0], 8
0x18001fd13  jb      short loc_18001FD20
0x18001fd15  mov     rcx, [rsp+130h+lpSubKey]
0x18001fd1a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fd20  mov     [rsp+130h+var_E0], r12
0x18001fd25  mov     [rsp+130h+var_E8], r15
0x18001fd2a  mov     word ptr [rsp+130h+lpSubKey], r15w
0x18001fd30  mov     rcx, [rsp+130h+hKey]; hKey
0x18001fd35  test    rcx, rcx
0x18001fd38  jz      short loc_18001FD40
0x18001fd3a  call    cs:__imp_RegCloseKey
0x18001fd40  mov     rdx, [rbp+30h+var_58]
0x18001fd44  test    rdx, rdx
0x18001fd47  jz      short loc_18001FD7E
0x18001fd49  mov     rax, [rsi+0A8h]
0x18001fd50  mov     r8d, 0FFFFFFFFh
0x18001fd56  cmp     rax, r8
0x18001fd59  mov     ecx, eax
0x18001fd5b  jbe     short loc_18001FD60
0x18001fd5d  mov     ecx, r8d
0x18001fd60  cmp     r8, rax
0x18001fd63  sbb     r9d, r9d
0x18001fd66  and     r9d, 80070216h; char *
0x18001fd6d  mov     r10, [rbp+38h]
0x18001fd71  cmp     rax, r8
0x18001fd74  ja      short loc_18001FDBC
0x18001fd76  add     ecx, 2
0x18001fd79  cmp     rdx, rcx
0x18001fd7c  jb      short loc_18001FD98
0x18001fd7e  cmp     [rsi+0BCh], r15d
0x18001fd85  jz      loc_18001FCA6
0x18001fd8b  cmp     [rbp+30h+var_5C], 2AB0003h
0x18001fd92  jnz     loc_18001FCA6
0x18001fd98  lea     rcx, [rbp+30h+var_B0]; this
0x18001fd9c  call    ??1ResultData@@QEAA@XZ; ResultData::~ResultData(void)
0x18001fda1  nop
0x18001fda2  cmp     [rsp+130h+var_C0], 8
0x18001fda8  jb      short loc_18001FDB5
0x18001fdaa  mov     rcx, [rsp+130h+var_D8]
0x18001fdaf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fdb5  mov     al, 1
0x18001fdb7  jmp     loc_18001FCC5
0x18001fdbc  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\retrysche"...
0x18001fdc3  mov     edx, 2Ch ; ','; void *
0x18001fdc8  mov     rcx, r10; this
0x18001fdcb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001fdd1  mov     r9d, eax; char *
0x18001fdd4  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18001fddb  mov     edx, 21Eh; void *
0x18001fde0  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
