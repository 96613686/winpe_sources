# CflApi::GetTempUserAccountSidsForDeferredProfileCleanup

- ea: `0x18001e684`
- end: `0x18001e967`
- name: `CflApi::GetTempUserAccountSidsForDeferredProfileCleanup`
- size: `739`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c500`

## callees

- `0x180002490`
- `0x1800067c4`
- `0x180008594`
- `0x180008ad0`
- `0x180014fd4`
- `0x18001b128`
- `0x18001e684`
- `0x18001f948`
- `0x18002237c`
- `0x180025cb4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001e87d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001e87d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e728`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e7b1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e728`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e7b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e6e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e6e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e7de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e92d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e7de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e92d`

## string_xrefs

- `0x18001e71b`: `TempUserAccountSids`
- `0x18001e7a4`: `TempUserAccountSids`
- `0x18001e73e`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e89e`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001e913`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
__int64 __fastcall CflApi::GetTempUserAccountSidsForDeferredProfileCleanup(__int64 a1)
{
  unsigned int ValueW; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  const wchar_t *v6; // r15
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rsi
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-59h]
  DWORD pcbData; // [rsp+40h] [rbp-39h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-31h] BYREF
  DWORD pdwType; // [rsp+50h] [rbp-29h] BYREF
  __int128 v17; // [rsp+58h] [rbp-21h] BYREF
  __int64 v18; // [rsp+68h] [rbp-11h]
  PVOID pvData[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v20; // [rsp+80h] [rbp+7h]
  _BYTE v21[32]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_OWORD *)pvData = 0;
  v20 = 0;
  hkey = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\ProfileCleanupData",
             0,
             1u,
             &hkey);
  if ( ValueW )
  {
    v3 = 990;
LABEL_5:
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v3,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
           (const char *)ValueW,
           phkResult);
LABEL_26:
    if ( hkey )
      RegCloseKey(hkey);
LABEL_28:
    std::vector<unsigned short>::~vector<unsigned short>(pvData);
    return v4;
  }
  pdwType = 0;
  pcbData = 0;
  ValueW = RegGetValueW(hkey, 0, L"TempUserAccountSids", 0x20u, &pdwType, 0, &pcbData);
  if ( ValueW )
  {
    v3 = 1002;
    goto LABEL_5;
  }
  if ( pdwType != 7 )
  {
    v4 = -2147024809;
    v5 = 1003;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)v4,
      phkResult);
    goto LABEL_26;
  }
  if ( !pcbData || (pcbData & 1) != 0 )
  {
    v4 = -2147024872;
    v5 = 1006;
    goto LABEL_25;
  }
  std::vector<unsigned short>::resize(pvData, (unsigned __int64)pcbData >> 1);
  ValueW = RegGetValueW(hkey, 0, L"TempUserAccountSids", 0x20u, 0, pvData[0], &pcbData);
  if ( ValueW )
  {
    v3 = 1017;
    goto LABEL_5;
  }
  std::vector<unsigned short>::resize(pvData, (unsigned __int64)pcbData >> 1);
  if ( hkey )
    RegCloseKey(hkey);
  v17 = 0;
  v18 = 0;
  v6 = (const wchar_t *)pvData[0];
  v7 = ((char *)pvData[1] - (char *)pvData[0]) >> 1;
  v8 = 0;
  if ( v7 )
  {
    while ( v6[v8] )
    {
      v9 = std::wstring::wstring(v21, &v6[v8]);
      v10 = v9;
      v11 = *((_QWORD *)&v17 + 1);
      if ( *((_QWORD *)&v17 + 1) == v18 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v17, *((_QWORD *)&v17 + 1), v9);
      }
      else
      {
        **((_OWORD **)&v17 + 1) = 0;
        *(_QWORD *)(v11 + 16) = 0;
        *(_QWORD *)(v11 + 24) = 0;
        *(_OWORD *)v11 = *(_OWORD *)v9;
        *(_OWORD *)(v11 + 16) = *(_OWORD *)(v9 + 16);
        *(_QWORD *)(v9 + 16) = 0;
        *(_QWORD *)(v9 + 24) = 7;
        *(_WORD *)v9 = 0;
        *((_QWORD *)&v17 + 1) += 32LL;
      }
      std::wstring::~wstring(v21, v11, v10);
      v8 += wcsnlen(&v6[v8], v7 - v8) + 1;
      if ( v7 <= v8 )
      {
        v4 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40A,
          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
          (const char *)0x80070057LL,
          phkResult);
        std::vector<std::wstring>::_Tidy(&v17);
        goto LABEL_28;
      }
    }
  }
  if ( (__int128 *)a1 != &v17 )
  {
    std::vector<std::wstring>::_Tidy(a1);
    *(_OWORD *)a1 = v17;
    *(_QWORD *)(a1 + 16) = v18;
    v17 = 0;
    v18 = 0;
  }
  std::vector<std::wstring>::_Tidy(&v17);
  std::vector<unsigned short>::~vector<unsigned short>(pvData);
  return 0;
}

```

## disassembly

```asm
0x18001e684  mov     [rsp-8+arg_8], rbx
0x18001e689  mov     [rsp-8+arg_10], rsi
0x18001e68e  push    rbp
0x18001e68f  push    rdi
0x18001e690  push    r12
0x18001e692  push    r14
0x18001e694  push    r15
0x18001e696  lea     rbp, [rsp-37h]
0x18001e69b  sub     rsp, 0B0h
0x18001e6a2  mov     rax, cs:__security_cookie
0x18001e6a9  xor     rax, rsp
0x18001e6ac  mov     [rbp+57h+var_28], rax
0x18001e6b0  mov     rbx, rcx
0x18001e6b3  xorps   xmm0, xmm0
0x18001e6b6  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18001e6bb  xor     r12d, r12d
0x18001e6be  mov     [rbp+57h+var_50], r12
0x18001e6c2  mov     [rbp+57h+hkey], r12
0x18001e6c6  lea     rax, [rbp+57h+hkey]
0x18001e6ca  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18001e6cf  lea     r9d, [r12+1]; samDesired
0x18001e6d4  xor     r8d, r8d; ulOptions
0x18001e6d7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001e6de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e6e5  call    cs:__imp_RegOpenKeyExW
0x18001e6eb  test    eax, eax
0x18001e6ed  jz      short loc_18001E6F6
0x18001e6ef  mov     edx, 3DEh
0x18001e6f4  jmp     short loc_18001E737
0x18001e6f6  mov     [rbp+57h+pdwType], r12d
0x18001e6fa  mov     [rbp+57h+var_90], r12d
0x18001e6fe  lea     rax, [rbp+57h+var_90]
0x18001e702  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18001e707  mov     [rsp+0D0h+pvData], r12; pvData
0x18001e70c  lea     rax, [rbp+57h+pdwType]
0x18001e710  mov     [rsp+0D0h+phkResult], rax; int
0x18001e715  mov     r9d, 20h ; ' '; dwFlags
0x18001e71b  lea     r8, ValueName; "TempUserAccountSids"
0x18001e722  xor     edx, edx; lpSubKey
0x18001e724  mov     rcx, [rbp+57h+hkey]; hkey
0x18001e728  call    cs:__imp_RegGetValueW
0x18001e72e  test    eax, eax
0x18001e730  jz      short loc_18001E751
0x18001e732  mov     edx, 3EAh; void *
0x18001e737  mov     rcx, [rbp+5Fh]; this
0x18001e73b  mov     r9d, eax; char *
0x18001e73e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001e745  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001e74a  mov     ebx, eax
0x18001e74c  jmp     loc_18001E924
0x18001e751  cmp     [rbp+57h+pdwType], 7
0x18001e755  jz      short loc_18001E766
0x18001e757  mov     ebx, 80070057h
0x18001e75c  mov     edx, 3EBh
0x18001e761  jmp     loc_18001E910
0x18001e766  mov     eax, [rbp+57h+var_90]
0x18001e769  test    eax, eax
0x18001e76b  jz      loc_18001E906
0x18001e771  test    al, 1
0x18001e773  jnz     loc_18001E906
0x18001e779  mov     edx, eax
0x18001e77b  shr     rdx, 1
0x18001e77e  lea     rcx, [rbp+57h+var_60]
0x18001e782  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18001e787  mov     rax, [rbp+57h+var_60]
0x18001e78b  lea     rcx, [rbp+57h+var_90]
0x18001e78f  mov     [rsp+0D0h+pcbData], rcx; pcbData
0x18001e794  mov     [rsp+0D0h+pvData], rax; pvData
0x18001e799  mov     [rsp+0D0h+phkResult], r12; int
0x18001e79e  mov     r9d, 20h ; ' '; dwFlags
0x18001e7a4  lea     r8, ValueName; "TempUserAccountSids"
0x18001e7ab  xor     edx, edx; lpSubKey
0x18001e7ad  mov     rcx, [rbp+57h+hkey]; hkey
0x18001e7b1  call    cs:__imp_RegGetValueW
0x18001e7b7  test    eax, eax
0x18001e7b9  jz      short loc_18001E7C5
0x18001e7bb  mov     edx, 3F9h
0x18001e7c0  jmp     loc_18001E737
0x18001e7c5  mov     edx, [rbp+57h+var_90]
0x18001e7c8  shr     rdx, 1
0x18001e7cb  lea     rcx, [rbp+57h+var_60]
0x18001e7cf  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18001e7d4  nop
0x18001e7d5  mov     rcx, [rbp+57h+hkey]; hKey
0x18001e7d9  test    rcx, rcx
0x18001e7dc  jz      short loc_18001E7E4
0x18001e7de  call    cs:__imp_RegCloseKey
0x18001e7e4  xorps   xmm0, xmm0
0x18001e7e7  movdqu  [rbp+57h+var_78], xmm0
0x18001e7ec  mov     [rbp+57h+var_68], r12
0x18001e7f0  mov     r15, [rbp+57h+var_60]
0x18001e7f4  mov     rdi, [rbp+57h+var_60+8]
0x18001e7f8  sub     rdi, r15
0x18001e7fb  sar     rdi, 1
0x18001e7fe  mov     rsi, r12
0x18001e801  jz      loc_18001E8BB
0x18001e807  lea     r14, [r15+rsi*2]
0x18001e80b  cmp     [r14], r12w
0x18001e80f  jz      loc_18001E8BB
0x18001e815  mov     rdx, r14
0x18001e818  lea     rcx, [rbp+57h+var_48]
0x18001e81c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001e821  mov     r8, rax
0x18001e824  mov     rdx, qword ptr [rbp+57h+var_78+8]
0x18001e828  cmp     rdx, [rbp+57h+var_68]
0x18001e82c  jz      short loc_18001E861
0x18001e82e  xorps   xmm0, xmm0
0x18001e831  movups  xmmword ptr [rdx], xmm0
0x18001e834  mov     [rdx+10h], r12
0x18001e838  mov     [rdx+18h], r12
0x18001e83c  movups  xmm0, xmmword ptr [rax]
0x18001e83f  movups  xmmword ptr [rdx], xmm0
0x18001e842  movups  xmm1, xmmword ptr [rax+10h]
0x18001e846  movups  xmmword ptr [rdx+10h], xmm1
0x18001e84a  mov     [rax+10h], r12
0x18001e84e  mov     qword ptr [rax+18h], 7
0x18001e856  mov     [rax], r12w
0x18001e85a  add     qword ptr [rbp+57h+var_78+8], 20h ; ' '
0x18001e85f  jmp     short loc_18001E86B
0x18001e861  lea     rcx, [rbp+57h+var_78]
0x18001e865  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18001e86a  nop
0x18001e86b  lea     rcx, [rbp+57h+var_48]
0x18001e86f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e874  mov     rdx, rdi
0x18001e877  sub     rdx, rsi; MaxCount
0x18001e87a  mov     rcx, r14; Source
0x18001e87d  call    cs:__imp_wcsnlen
0x18001e883  inc     rsi
0x18001e886  add     rsi, rax
0x18001e889  cmp     rdi, rsi
0x18001e88c  ja      loc_18001E807
0x18001e892  mov     rcx, [rbp+5Fh]; this
0x18001e896  mov     ebx, 80070057h
0x18001e89b  mov     r9d, ebx; char *
0x18001e89e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001e8a5  mov     edx, 40Ah; void *
0x18001e8aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e8af  nop
0x18001e8b0  lea     rcx, [rbp+57h+var_78]
0x18001e8b4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001e8b9  jmp     short loc_18001E934
0x18001e8bb  lea     rax, [rbp+57h+var_78]
0x18001e8bf  cmp     rbx, rax
0x18001e8c2  jz      short loc_18001E8EF
0x18001e8c4  mov     rcx, rbx
0x18001e8c7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001e8cc  mov     rax, qword ptr [rbp+57h+var_78]
0x18001e8d0  mov     [rbx], rax
0x18001e8d3  mov     rax, qword ptr [rbp+57h+var_78+8]
0x18001e8d7  mov     [rbx+8], rax
0x18001e8db  mov     rax, [rbp+57h+var_68]
0x18001e8df  mov     [rbx+10h], rax
0x18001e8e3  xorps   xmm0, xmm0
0x18001e8e6  movdqu  [rbp+57h+var_78], xmm0
0x18001e8eb  mov     [rbp+57h+var_68], r12
0x18001e8ef  lea     rcx, [rbp+57h+var_78]
0x18001e8f3  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001e8f8  nop
0x18001e8f9  lea     rcx, [rbp+57h+var_60]
0x18001e8fd  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001e902  xor     eax, eax
0x18001e904  jmp     short loc_18001E93F
0x18001e906  mov     ebx, 80070018h
0x18001e90b  mov     edx, 3EEh; void *
0x18001e910  mov     r9d, ebx; char *
0x18001e913  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001e91a  mov     rcx, [rbp+5Fh]; this
0x18001e91e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e923  nop
0x18001e924  mov     rcx, [rbp+57h+hkey]; hKey
0x18001e928  test    rcx, rcx
0x18001e92b  jz      short loc_18001E934
0x18001e92d  call    cs:__imp_RegCloseKey
0x18001e933  nop
0x18001e934  lea     rcx, [rbp+57h+var_60]
0x18001e938  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001e93d  mov     eax, ebx
0x18001e93f  mov     rcx, [rbp+57h+var_28]
0x18001e943  xor     rcx, rsp; StackCookie
0x18001e946  call    __security_check_cookie
0x18001e94b  lea     r11, [rsp+0D0h+var_20]
0x18001e953  mov     rbx, [r11+38h]
0x18001e957  mov     rsi, [r11+40h]
0x18001e95b  mov     rsp, r11
0x18001e95e  pop     r15
0x18001e960  pop     r14
0x18001e962  pop     r12
0x18001e964  pop     rdi
0x18001e965  pop     rbp
0x18001e966  retn
```
