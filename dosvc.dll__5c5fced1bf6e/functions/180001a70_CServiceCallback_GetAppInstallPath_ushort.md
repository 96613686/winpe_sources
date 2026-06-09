# CServiceCallback::GetAppInstallPath(ushort * *)

- ea: `0x180001a70`
- end: `0x180001c18`
- name: `?GetAppInstallPath@CServiceCallback@@EEBAJPEAPEAG@Z`
- size: `424`
- prototype: `__int64 __fastcall(CServiceCallback *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180001a70`
- `0x180001d00`
- `0x180003290`
- `0x180005020`
- `0x180005b2c`
- `0x180005d78`

## import_xrefs

- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x180001b55`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x180001b55`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageSettings` at `0x180001b09`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageSettings` at `0x180001b09`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageInstanceCount` at `0x180001abd`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageInstanceCount` at `0x180001abd`

## string_xrefs

- `0x180001ad1`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`
- `0x180001b69`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`
- `0x180001bcc`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`

## pseudocode

```c
__int64 __fastcall CServiceCallback::GetAppInstallPath(CServiceCallback *this, unsigned __int16 **a2)
{
  int StorageInstanceCount; // eax
  unsigned int v5; // edi
  int v6; // eax
  unsigned int v7; // edi
  int StorageDeviceInfo; // eax
  unsigned int v9; // edi
  int v10; // [rsp+20h] [rbp-488h] BYREF
  unsigned __int16 *v11; // [rsp+28h] [rbp-480h] BYREF
  int v12; // [rsp+30h] [rbp-478h] BYREF
  _BYTE v13[524]; // [rsp+34h] [rbp-474h] BYREF
  int v14; // [rsp+240h] [rbp-268h]
  int v15; // [rsp+248h] [rbp-260h]
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+0h]

  *a2 = 0;
  if ( !(unsigned __int8)IsGetStorageInstanceCountPresent(this) )
    return 2147500033LL;
  v10 = 0;
  StorageInstanceCount = GetStorageInstanceCount(0, &v10);
  v5 = StorageInstanceCount;
  if ( StorageInstanceCount < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\servicecallback\\servicecallback.cpp",
      (const char *)(unsigned int)StorageInstanceCount,
      v10);
    return v5;
  }
  v6 = v10;
  v7 = 0;
  if ( v10 )
  {
    while ( 1 )
    {
      LODWORD(v11) = 0;
      if ( (int)GetStorageSettings(0, v7, 2, &v11) >= 0 && ((unsigned __int8)v11 & 0x10) != 0 )
        break;
      v6 = v10;
      if ( ++v7 >= v10 )
        goto LABEL_11;
    }
    v6 = v10;
  }
LABEL_11:
  if ( v7 == v6 )
    return 2147943568LL;
  memset_0(v13, 0, 0x454u);
  v12 = 1112;
  StorageDeviceInfo = GetStorageDeviceInfo(0, v7, &v12);
  v9 = StorageDeviceInfo;
  if ( StorageDeviceInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\servicecallback\\servicecallback.cpp",
      (const char *)(unsigned int)StorageDeviceInfo,
      v10);
    return v9;
  }
  if ( (v13[520] & 1) != 0 || v14 || v15 )
    return 2147943568LL;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v11,
    v13,
    -1);
  if ( v11 )
  {
    *a2 = v11;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\servicecallback\\servicecallback.cpp",
      (const char *)0x8007000ELL,
      v10);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180001a70  mov     [rsp+arg_10], rbx
0x180001a75  push    rsi
0x180001a76  sub     rsp, 4A0h
0x180001a7d  mov     rax, cs:__security_cookie
0x180001a84  xor     rax, rsp
0x180001a87  mov     [rsp+4A8h+var_18], rax
0x180001a8f  xor     esi, esi
0x180001a91  mov     rbx, rdx
0x180001a94  mov     [rdx], rsi
0x180001a97  call    IsGetStorageInstanceCountPresent
0x180001a9c  test    al, al
0x180001a9e  jnz     short loc_180001AAA
0x180001aa0  mov     eax, 80004001h
0x180001aa5  jmp     loc_180001BF7
0x180001aaa  lea     rdx, [rsp+4A8h+var_488]
0x180001aaf  mov     [rsp+4A8h+arg_0], rdi
0x180001ab7  xor     ecx, ecx
0x180001ab9  mov     [rsp+4A8h+var_488], esi; int
0x180001abd  call    cs:__imp_GetStorageInstanceCount
0x180001ac3  mov     edi, eax
0x180001ac5  test    eax, eax
0x180001ac7  jns     short loc_180001AEC
0x180001ac9  mov     rcx, [rsp+4A8h]; this
0x180001ad1  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x180001ad8  mov     r9d, eax; char *
0x180001adb  mov     edx, 30h ; '0'; void *
0x180001ae0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001ae5  mov     eax, edi
0x180001ae7  jmp     loc_180001BEF
0x180001aec  mov     eax, [rsp+4A8h+var_488]
0x180001af0  mov     edi, esi
0x180001af2  test    eax, eax
0x180001af4  jz      short loc_180001B2A
0x180001af6  lea     r9, [rsp+4A8h+var_480]
0x180001afb  mov     dword ptr [rsp+4A8h+var_480], esi
0x180001aff  mov     r8d, 2
0x180001b05  mov     edx, edi
0x180001b07  xor     ecx, ecx
0x180001b09  call    cs:__imp_GetStorageSettings
0x180001b0f  test    eax, eax
0x180001b11  js      short loc_180001B1A
0x180001b13  test    byte ptr [rsp+4A8h+var_480], 10h
0x180001b18  jnz     short loc_180001B26
0x180001b1a  mov     eax, [rsp+4A8h+var_488]
0x180001b1e  inc     edi
0x180001b20  cmp     edi, eax
0x180001b22  jb      short loc_180001AF6
0x180001b24  jmp     short loc_180001B2A
0x180001b26  mov     eax, [rsp+4A8h+var_488]
0x180001b2a  cmp     edi, eax
0x180001b2c  jz      loc_180001BEA
0x180001b32  xor     edx, edx; Val
0x180001b34  lea     rcx, [rsp+4A8h+var_474]; void *
0x180001b39  mov     r8d, 454h; Size
0x180001b3f  call    memset_0
0x180001b44  lea     r8, [rsp+4A8h+var_478]
0x180001b49  mov     [rsp+4A8h+var_478], 458h
0x180001b51  mov     edx, edi
0x180001b53  xor     ecx, ecx
0x180001b55  call    cs:__imp_GetStorageDeviceInfo
0x180001b5b  mov     edi, eax
0x180001b5d  test    eax, eax
0x180001b5f  jns     short loc_180001B81
0x180001b61  mov     rcx, [rsp+4A8h]; this
0x180001b69  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x180001b70  mov     r9d, eax; char *
0x180001b73  mov     edx, 42h ; 'B'; void *
0x180001b78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001b7d  mov     eax, edi
0x180001b7f  jmp     short loc_180001BEF
0x180001b81  test    [rsp+4A8h+var_26C], 1
0x180001b89  jnz     short loc_180001BEA
0x180001b8b  cmp     [rsp+4A8h+var_268], esi
0x180001b92  jnz     short loc_180001BEA
0x180001b94  cmp     [rsp+4A8h+var_260], esi
0x180001b9b  jnz     short loc_180001BEA
0x180001b9d  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180001ba4  lea     rdx, [rsp+4A8h+var_474]
0x180001ba9  lea     rcx, [rsp+4A8h+var_480]
0x180001bae  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180001bb3  mov     rax, [rsp+4A8h+var_480]
0x180001bb8  test    rax, rax
0x180001bbb  jz      short loc_180001BC4
0x180001bbd  mov     [rbx], rax
0x180001bc0  xor     eax, eax
0x180001bc2  jmp     short loc_180001BEF
0x180001bc4  mov     rcx, [rsp+4A8h]; this
0x180001bcc  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x180001bd3  mov     r9d, 8007000Eh; char *
0x180001bd9  mov     edx, 49h ; 'I'; void *
0x180001bde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001be3  mov     eax, 8007000Eh
0x180001be8  jmp     short loc_180001BEF
0x180001bea  mov     eax, 80070490h
0x180001bef  mov     rdi, [rsp+4A8h+arg_0]
0x180001bf7  mov     rcx, [rsp+4A8h+var_18]
0x180001bff  xor     rcx, rsp; StackCookie
0x180001c02  call    __security_check_cookie
0x180001c07  mov     rbx, [rsp+4A8h+arg_10]
0x180001c0f  add     rsp, 4A0h
0x180001c16  pop     rsi
0x180001c17  retn
```
