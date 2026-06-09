# IsTpm12(void)

- ea: `0x18003c6f0`
- end: `0x18003c7d1`
- name: `?IsTpm12@@YA_NXZ`
- size: `225`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009570`
- `0x18003c2ec`

## callees

- `0x1800167f8`
- `0x180028418`
- `0x18003c6f0`
- `0x180046ce0`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x18003c783`
- `ncrypt!NCryptOpenStorageProvider` at `0x18003c783`
- `tbs!Tbsi_GetDeviceInfo` at `0x18003c72c`
- `tbs!Tbsi_GetDeviceInfo` at `0x18003c72c`

## string_xrefs

- `0x18003c73b`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`

## pseudocode

```c
bool IsTpm12(void)
{
  unsigned int DeviceInfo; // eax
  bool v2; // bl
  NCRYPT_PROV_HANDLE phProvider; // [rsp+20h] [rbp-28h] BYREF
  __int128 v4; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( dword_18006EE70 )
    return dword_18006EE70 == 1;
  v4 = 0;
  DeviceInfo = Tbsi_GetDeviceInfo(16, &v4);
  if ( DeviceInfo )
  {
    v2 = 0;
    if ( (int)wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xAA,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
                (const char *)DeviceInfo,
                phProvider) < 0 )
    {
      dword_18006EE70 = 3;
      return 0;
    }
  }
  else
  {
    v2 = DWORD1(v4) == 1;
  }
  phProvider = 0;
  if ( NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0) < 0 )
  {
    dword_18006EE70 = 3;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    return 0;
  }
  dword_18006EE70 = !v2 + 1;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  return v2;
}

```

## disassembly

```asm
0x18003c6f0  push    rbx
0x18003c6f2  sub     rsp, 40h
0x18003c6f6  mov     rax, cs:__security_cookie
0x18003c6fd  xor     rax, rsp
0x18003c700  mov     [rsp+48h+var_10], rax
0x18003c705  mov     eax, cs:dword_18006EE70
0x18003c70b  test    eax, eax
0x18003c70d  jz      short loc_18003C71A
0x18003c70f  cmp     eax, 1
0x18003c712  setz    al
0x18003c715  jmp     loc_18003C7BE
0x18003c71a  xorps   xmm0, xmm0
0x18003c71d  lea     rdx, [rsp+48h+var_20]
0x18003c722  mov     ecx, 10h
0x18003c727  movups  [rsp+48h+var_20], xmm0
0x18003c72c  call    cs:__imp_Tbsi_GetDeviceInfo
0x18003c732  test    eax, eax
0x18003c734  jz      short loc_18003C763
0x18003c736  mov     rcx, [rsp+48h]; this
0x18003c73b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18003c742  mov     r9d, eax; char *
0x18003c745  mov     edx, 0AAh; void *
0x18003c74a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003c74f  xor     bl, bl
0x18003c751  test    eax, eax
0x18003c753  jns     short loc_18003C76B
0x18003c755  mov     cs:dword_18006EE70, 3
0x18003c75f  xor     al, al
0x18003c761  jmp     short loc_18003C7BE
0x18003c763  cmp     dword ptr [rsp+48h+var_20+4], 1
0x18003c768  setz    bl
0x18003c76b  xor     r8d, r8d; dwFlags
0x18003c76e  mov     [rsp+48h+phProvider], 0
0x18003c777  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18003c77e  lea     rcx, [rsp+48h+phProvider]; phProvider
0x18003c783  call    cs:__imp_NCryptOpenStorageProvider
0x18003c789  lea     rcx, [rsp+48h+phProvider]
0x18003c78e  test    eax, eax
0x18003c790  jns     short loc_18003C7A3
0x18003c792  mov     cs:dword_18006EE70, 3
0x18003c79c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18003c7a1  jmp     short loc_18003C75F
0x18003c7a3  movzx   eax, bl
0x18003c7a6  xor     eax, 1
0x18003c7a9  inc     eax
0x18003c7ab  cmp     eax, 1
0x18003c7ae  mov     cs:dword_18006EE70, eax
0x18003c7b4  setz    bl
0x18003c7b7  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18003c7bc  mov     al, bl
0x18003c7be  mov     rcx, [rsp+48h+var_10]
0x18003c7c3  xor     rcx, rsp; StackCookie
0x18003c7c6  call    __security_check_cookie
0x18003c7cb  add     rsp, 40h
0x18003c7cf  pop     rbx
0x18003c7d0  retn
```
