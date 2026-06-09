# DAS::ProviderManagement::ProviderManager::UnregisterProviderStatic(_DAF_PROVIDER_PATH,ushort const *)

- ea: `0x1800618d8`
- end: `0x1800619f0`
- name: `?UnregisterProviderStatic@ProviderManager@ProviderManagement@DAS@@SAJW4_DAF_PROVIDER_PATH@@PEBG@Z`
- size: `280`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180028850`

## callees

- `0x1800074c0`
- `0x18001eae0`
- `0x18002a948`
- `0x1800618b4`
- `0x1800618d8`
- `0x180061b2c`
- `0x180061c68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800619b2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800619b2`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180061981`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800619c6`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180061981`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800619c6`

## string_xrefs

- `0x1800619a8`: `FileCopy`
- `0x1800619bc`: `SOFTWARE\Microsoft\File Copy Provider`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::UnregisterProviderStatic(int a1, unsigned __int16 *a2)
{
  __int64 v3; // rbx
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  unsigned int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp+18h] BYREF

  v3 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids, a2);
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  v4 = DafConcatenateWithDelimiter_3((&off_1800A3088)[3 * v3], a2, L"\\");
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, lpSubKey);
    if ( v6 )
    {
      v7 = 284;
    }
    else
    {
      if ( (unsigned int)_o__wcsicmp(a2, L"FileCopy")
        || (v6 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\File Copy Provider")) == 0 )
      {
        v5 = 0;
        goto LABEL_13;
      }
      v7 = 288;
    }
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v7,
           (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
           (const char *)v6,
           v9);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11B,
      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
      (const char *)(unsigned int)v4,
      v9);
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpSubKey);
  return v5;
}

```

## disassembly

```asm
0x1800618d8  mov     [rsp+arg_0], rbx
0x1800618dd  push    rdi; unsigned int
0x1800618de  sub     rsp, 20h
0x1800618e2  mov     rdi, rdx
0x1800618e5  movsxd  rbx, ecx
0x1800618e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800618ef  lea     rax, WPP_GLOBAL_Control
0x1800618f6  cmp     rcx, rax
0x1800618f9  jz      short loc_180061919
0x1800618fb  cmp     byte ptr [rcx+19h], 4
0x1800618ff  jb      short loc_180061919
0x180061901  mov     rcx, [rcx+10h]
0x180061905  lea     r8, WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids
0x18006190c  mov     edx, 1Ch
0x180061911  mov     r9, rdi
0x180061914  call    WPP_SF_S
0x180061919  xor     edx, edx
0x18006191b  mov     [rsp+28h+lpSubKey], 0
0x180061924  lea     rcx, [rsp+28h+lpSubKey]
0x180061929  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006192e  lea     rax, off_1800A3088; "SOFTWARE\\Microsoft\\Device Association"...
0x180061935  mov     rdx, rdi; unsigned __int16 *
0x180061938  lea     rcx, [rbx+rbx*2]
0x18006193c  mov     rcx, [rax+rcx*8]; unsigned __int16 *
0x180061940  lea     r9, [rsp+28h+lpSubKey]
0x180061945  lea     r8, asc_18008CA3C; "\\"
0x18006194c  call    DafConcatenateWithDelimiter_3
0x180061951  mov     ebx, eax
0x180061953  test    eax, eax
0x180061955  jns     short loc_180061972
0x180061957  mov     rcx, [rsp+28h]; this
0x18006195c  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x180061963  mov     r9d, eax; char *
0x180061966  mov     edx, 11Bh; void *
0x18006196b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061970  jmp     short loc_1800619D9
0x180061972  mov     rdx, [rsp+28h+lpSubKey]; lpSubKey
0x180061977  mov     rbx, 0FFFFFFFF80000002h
0x18006197e  mov     rcx, rbx; hKey
0x180061981  call    cs:__imp_RegDeleteKeyW
0x180061987  test    eax, eax
0x180061989  jz      short loc_1800619A8
0x18006198b  mov     edx, 11Ch; void *
0x180061990  mov     rcx, [rsp+28h]; this
0x180061995  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18006199c  mov     r9d, eax; char *
0x18006199f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800619a4  mov     ebx, eax
0x1800619a6  jmp     short loc_1800619D9
0x1800619a8  lea     rdx, aFilecopy; "FileCopy"
0x1800619af  mov     rcx, rdi
0x1800619b2  call    cs:__imp__o__wcsicmp
0x1800619b8  test    eax, eax
0x1800619ba  jnz     short loc_1800619D7
0x1800619bc  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\File Copy Provider"
0x1800619c3  mov     rcx, rbx; hKey
0x1800619c6  call    cs:__imp_RegDeleteKeyW
0x1800619cc  test    eax, eax
0x1800619ce  jz      short loc_1800619D7
0x1800619d0  mov     edx, 120h
0x1800619d5  jmp     short loc_180061990
0x1800619d7  xor     ebx, ebx
0x1800619d9  lea     rcx, [rsp+28h+lpSubKey]
0x1800619de  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800619e3  mov     eax, ebx
0x1800619e5  mov     rbx, [rsp+28h+arg_0]
0x1800619ea  add     rsp, 20h
0x1800619ee  pop     rdi
0x1800619ef  retn
```
