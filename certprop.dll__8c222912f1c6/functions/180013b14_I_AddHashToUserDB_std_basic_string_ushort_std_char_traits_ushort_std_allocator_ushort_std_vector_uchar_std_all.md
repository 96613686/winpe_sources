# I_AddHashToUserDB(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<uchar,std::allocator<uchar>>)

- ea: `0x180013b14`
- end: `0x180013db2`
- name: `?I_AddHashToUserDB@@YAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@EV?$allocator@E@std@@@2@@Z`
- size: `670`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000971c`

## callees

- `0x180008554`
- `0x1800085dc`
- `0x180008654`
- `0x180013ab0`
- `0x180013b14`
- `0x180013dc4`
- `0x180013e04`
- `0x180013eb4`
- `0x18001466c`
- `0x1800150a8`
- `0x180015854`
- `0x1800158f0`
- `0x180015938`
- `0x180015c30`
- `0x180016090`
- `0x18001cf50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013c8f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013c8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013ca5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013ca5`

## pseudocode

```c
__int64 __fastcall I_AddHashToUserDB(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rbx
  const WCHAR *v8; // rdx
  unsigned int UUIDValue; // ebx
  unsigned int v10; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v14; // [rsp+60h] [rbp-A0h]
  __int64 v15; // [rsp+68h] [rbp-98h]
  _BYTE v16[32]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v17; // [rsp+98h] [rbp-68h]
  LPCWSTR lpSubKey[2]; // [rsp+A0h] [rbp-60h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-50h]
  _QWORD v20[3]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v21; // [rsp+D8h] [rbp-28h]
  _BYTE v22[32]; // [rsp+E0h] [rbp-20h] BYREF

  v17 = a1;
  v15 = a2;
  dwDisposition = 0;
  *(_OWORD *)lpSubKey = 0;
  si128 = 0;
  v4 = std::_WChar_traits<unsigned short>::length(
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{8FD7E19C-3BF7-489B-A72C-84"
          "6AB3678C96}\\V2\\KnownUsers");
  std::wstring::_Construct<1,unsigned short const *>(lpSubKey, v5, v4);
  v6 = std::operator+<unsigned short>(v20, lpSubKey);
  if ( lpSubKey != (LPCWSTR *)v6 )
  {
    std::wstring::_Tidy_deallocate(lpSubKey);
    *(_OWORD *)lpSubKey = *(_OWORD *)v6;
    si128 = *(__m128i *)(v6 + 16);
    *(_QWORD *)(v6 + 16) = 0;
    *(_QWORD *)(v6 + 24) = 7;
    *(_WORD *)v6 = 0;
  }
  if ( v21 > 7 )
    std::_Deallocate<16>(v20[0], 2 * v21 + 2);
  v7 = std::operator+<unsigned short>(v20, lpSubKey, a1);
  if ( lpSubKey != (LPCWSTR *)v7 )
  {
    std::wstring::_Tidy_deallocate(lpSubKey);
    *(_OWORD *)lpSubKey = *(_OWORD *)v7;
    si128 = *(__m128i *)(v7 + 16);
    *(_QWORD *)(v7 + 16) = 0;
    *(_QWORD *)(v7 + 24) = 7;
    *(_WORD *)v7 = 0;
  }
  if ( v21 > 7 )
    std::_Deallocate<16>(v20[0], 2 * v21 + 2);
  hKey = 0;
  v8 = (const WCHAR *)lpSubKey;
  if ( si128.m128i_i64[1] > 7uLL )
    v8 = lpSubKey[0];
  UUIDValue = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  if ( !UUIDValue )
  {
    std::wstring::wstring(v22);
    if ( dwDisposition == 1 )
    {
      UUIDValue = I_GenerateUUIDValue(v22);
      if ( UUIDValue )
        goto LABEL_24;
      v14 = v20;
      std::vector<unsigned char>::vector<unsigned char>(v20, a2);
      std::wstring::wstring(v16, v22);
      v10 = I_StoreCertificateHash(hKey);
    }
    else
    {
      if ( dwDisposition != 2 )
      {
        UUIDValue = -2147467259;
LABEL_24:
        std::wstring::_Tidy_deallocate(v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::wstring::_Tidy_deallocate(lpSubKey);
        goto LABEL_25;
      }
      std::vector<unsigned char>::vector<unsigned char>(v20, a2);
      v10 = I_FindAndStoreCertificateHash(hKey);
    }
    UUIDValue = v10;
    goto LABEL_24;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(lpSubKey[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKey[0]) = 0;
LABEL_25:
  std::wstring::_Tidy_deallocate(a1);
  std::vector<unsigned char>::_Tidy(a2);
  return UUIDValue;
}

```

## disassembly

```asm
0x180013b14  mov     [rsp-8+arg_10], rbx
0x180013b19  push    rbp
0x180013b1a  push    rsi
0x180013b1b  push    rdi
0x180013b1c  lea     rbp, [rsp-10h]
0x180013b21  sub     rsp, 110h
0x180013b28  mov     rax, cs:__security_cookie
0x180013b2f  xor     rax, rsp
0x180013b32  mov     [rbp+20h+var_20], rax
0x180013b36  mov     rdi, rdx
0x180013b39  mov     rsi, rcx
0x180013b3c  mov     [rbp+20h+var_88], rcx
0x180013b40  mov     [rsp+120h+var_B8], rdx
0x180013b45  mov     [rsp+120h+dwDisposition], 0
0x180013b4d  xorps   xmm0, xmm0
0x180013b50  movups  xmmword ptr [rbp+20h+lpSubKey], xmm0
0x180013b54  xorps   xmm1, xmm1
0x180013b57  movdqu  [rbp+20h+var_70], xmm1
0x180013b5c  lea     rcx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180013b63  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180013b68  mov     r8, rax
0x180013b6b  mov     rdx, rcx
0x180013b6e  lea     rcx, [rbp+20h+lpSubKey]
0x180013b72  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013b77  nop
0x180013b78  lea     rdx, [rbp+20h+lpSubKey]
0x180013b7c  lea     rcx, [rbp+20h+var_60]
0x180013b80  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180013b85  mov     rbx, rax
0x180013b88  lea     rax, [rbp+20h+lpSubKey]
0x180013b8c  cmp     rax, rbx
0x180013b8f  jz      short loc_180013BBE
0x180013b91  lea     rcx, [rbp+20h+lpSubKey]
0x180013b95  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013b9a  movups  xmm0, xmmword ptr [rbx]
0x180013b9d  movups  xmmword ptr [rbp+20h+lpSubKey], xmm0
0x180013ba1  movups  xmm1, xmmword ptr [rbx+10h]
0x180013ba5  movups  [rbp+20h+var_70], xmm1
0x180013ba9  mov     qword ptr [rbx+10h], 0
0x180013bb1  mov     qword ptr [rbx+18h], 7
0x180013bb9  xor     eax, eax
0x180013bbb  mov     [rbx], ax
0x180013bbe  mov     rdx, [rbp+20h+var_48]
0x180013bc2  cmp     rdx, 7
0x180013bc6  jbe     short loc_180013BD9
0x180013bc8  lea     rdx, ds:2[rdx*2]
0x180013bd0  mov     rcx, [rbp+20h+var_60]
0x180013bd4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013bd9  mov     r8, rsi
0x180013bdc  lea     rdx, [rbp+20h+lpSubKey]
0x180013be0  lea     rcx, [rbp+20h+var_60]
0x180013be4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x180013be9  mov     rbx, rax
0x180013bec  lea     rax, [rbp+20h+lpSubKey]
0x180013bf0  cmp     rax, rbx
0x180013bf3  jz      short loc_180013C22
0x180013bf5  lea     rcx, [rbp+20h+lpSubKey]
0x180013bf9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013bfe  movups  xmm0, xmmword ptr [rbx]
0x180013c01  movups  xmmword ptr [rbp+20h+lpSubKey], xmm0
0x180013c05  movups  xmm1, xmmword ptr [rbx+10h]
0x180013c09  movups  [rbp+20h+var_70], xmm1
0x180013c0d  mov     qword ptr [rbx+10h], 0
0x180013c15  mov     qword ptr [rbx+18h], 7
0x180013c1d  xor     ecx, ecx
0x180013c1f  mov     [rbx], cx
0x180013c22  mov     rdx, [rbp+20h+var_48]
0x180013c26  cmp     rdx, 7
0x180013c2a  jbe     short loc_180013C3E
0x180013c2c  lea     rdx, ds:2[rdx*2]
0x180013c34  mov     rcx, [rbp+20h+var_60]
0x180013c38  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013c3d  nop
0x180013c3e  mov     [rsp+120h+hKey], 0
0x180013c47  lea     rdx, [rbp+20h+lpSubKey]
0x180013c4b  cmp     qword ptr [rbp+20h+var_70+8], 7
0x180013c50  cmova   rdx, [rbp+20h+lpSubKey]; lpSubKey
0x180013c55  lea     rax, [rsp+120h+dwDisposition]
0x180013c5a  mov     [rsp+120h+lpdwDisposition], rax; lpdwDisposition
0x180013c5f  lea     rax, [rsp+120h+hKey]
0x180013c64  mov     [rsp+120h+phkResult], rax; phkResult
0x180013c69  mov     [rsp+120h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180013c72  mov     [rsp+120h+samDesired], 2001Fh; samDesired
0x180013c7a  mov     [rsp+120h+dwOptions], 0; dwOptions
0x180013c82  xor     r9d, r9d; lpClass
0x180013c85  xor     r8d, r8d; Reserved
0x180013c88  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013c8f  call    cs:__imp_RegCreateKeyExW
0x180013c95  mov     ebx, eax
0x180013c97  test    eax, eax
0x180013c99  jz      short loc_180013CDF
0x180013c9b  mov     rcx, [rsp+120h+hKey]; hKey
0x180013ca0  test    rcx, rcx
0x180013ca3  jz      short loc_180013CAC
0x180013ca5  call    cs:__imp_RegCloseKey
0x180013cab  nop
0x180013cac  mov     rdx, qword ptr [rbp+20h+var_70+8]
0x180013cb0  cmp     rdx, 7
0x180013cb4  jbe     short loc_180013CC7
0x180013cb6  lea     rdx, ds:2[rdx*2]
0x180013cbe  mov     rcx, [rbp+20h+lpSubKey]
0x180013cc2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013cc7  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180013ccf  movdqu  [rbp+20h+var_70], xmm0
0x180013cd4  xor     eax, eax
0x180013cd6  mov     word ptr [rbp+20h+lpSubKey], ax
0x180013cda  jmp     loc_180013D80
0x180013cdf  lea     rcx, [rbp+20h+var_40]
0x180013ce3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180013ce8  nop
0x180013ce9  mov     eax, [rsp+120h+dwDisposition]
0x180013ced  sub     eax, 1
0x180013cf0  jz      short loc_180013D19
0x180013cf2  cmp     eax, 1
0x180013cf5  jz      short loc_180013CFE
0x180013cf7  mov     ebx, 80004005h
0x180013cfc  jmp     short loc_180013D61
0x180013cfe  mov     rdx, rdi
0x180013d01  lea     rcx, [rbp+20h+var_60]
0x180013d05  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180013d0a  mov     rdx, rax
0x180013d0d  mov     rcx, [rsp+120h+hKey]; hKey
0x180013d12  call    ?I_FindAndStoreCertificateHash@@YAKPEAUHKEY__@@V?$vector@EV?$allocator@E@std@@@std@@@Z; I_FindAndStoreCertificateHash(HKEY__ *,std::vector<uchar>)
0x180013d17  jmp     short loc_180013D5F
0x180013d19  lea     rcx, [rbp+20h+var_40]
0x180013d1d  call    ?I_GenerateUUIDValue@@YAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; I_GenerateUUIDValue(std::wstring &)
0x180013d22  mov     ebx, eax
0x180013d24  test    eax, eax
0x180013d26  jnz     short loc_180013D61
0x180013d28  lea     rax, [rbp+20h+var_60]
0x180013d2c  mov     [rsp+120h+var_C0], rax
0x180013d31  mov     rdx, rdi
0x180013d34  lea     rcx, [rbp+20h+var_60]
0x180013d38  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180013d3d  mov     rbx, rax
0x180013d40  lea     rdx, [rbp+20h+var_40]
0x180013d44  lea     rcx, [rsp+120h+var_A8]
0x180013d49  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180013d4e  nop
0x180013d4f  mov     r8, rbx
0x180013d52  mov     rdx, rax
0x180013d55  mov     rcx, [rsp+120h+hKey]; hKey
0x180013d5a  call    ?I_StoreCertificateHash@@YAKPEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@EV?$allocator@E@std@@@3@@Z; I_StoreCertificateHash(HKEY__ *,std::wstring,std::vector<uchar>)
0x180013d5f  mov     ebx, eax
0x180013d61  lea     rcx, [rbp+20h+var_40]
0x180013d65  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013d6a  nop
0x180013d6b  lea     rcx, [rsp+120h+hKey]
0x180013d70  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013d75  nop
0x180013d76  lea     rcx, [rbp+20h+lpSubKey]
0x180013d7a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013d7f  nop
0x180013d80  mov     rcx, rsi
0x180013d83  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013d88  nop
0x180013d89  mov     rcx, rdi
0x180013d8c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180013d91  mov     eax, ebx
0x180013d93  mov     rcx, [rbp+20h+var_20]
0x180013d97  xor     rcx, rsp; StackCookie
0x180013d9a  call    __security_check_cookie
0x180013d9f  mov     rbx, [rsp+120h+arg_10]
0x180013da7  add     rsp, 110h
0x180013dae  pop     rdi
0x180013daf  pop     rsi
0x180013db0  pop     rbp
0x180013db1  retn
```
