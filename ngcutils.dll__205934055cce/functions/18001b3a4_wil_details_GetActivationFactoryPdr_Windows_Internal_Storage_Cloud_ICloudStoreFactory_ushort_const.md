# wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(ushort const *)

- ea: `0x18001b3a4`
- end: `0x18001b450`
- name: `??$GetActivationFactoryPdr@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001bb38`

## callees

- `0x180003080`
- `0x180013fe4`
- `0x18001ae30`
- `0x18001b3a4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b3f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b3f5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b40e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b40e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(
        _QWORD *a1)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int ActivationFactory; // eax
  HSTRING_HEADER v7; // [rsp+30h] [rbp-38h] BYREF
  HSTRING v8; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a1 = 0;
  v8 = 0;
  v2 = WindowsCreateStringReference(L"Windows.Internal.Storage.Cloud.CloudStore", 0x29u, &v7, &v8);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x18001B44FLL);
  }
  ActivationFactory = RoGetActivationFactory(v8, &GUID_fc73907e_e219_4b15_9c14_90c3add7ad22, a1);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
      (const char *)(unsigned int)ActivationFactory,
      1);
  return a1;
}

```

## disassembly

```asm
0x18001b3a4  mov     r11, rsp
0x18001b3a7  push    rbx
0x18001b3a8  sub     rsp, 60h
0x18001b3ac  mov     rax, cs:__security_cookie
0x18001b3b3  xor     rax, rsp
0x18001b3b6  mov     [rsp+68h+var_18], rax
0x18001b3bb  mov     rbx, rcx
0x18001b3be  mov     [r11-40h], rcx
0x18001b3c2  mov     [rsp+68h+var_48], 0
0x18001b3ca  mov     [rsp+68h+var_48], 1; int
0x18001b3d2  mov     qword ptr [rcx], 0
0x18001b3d9  mov     qword ptr [r11-20h], 0
0x18001b3e1  lea     r9, [r11-20h]; string
0x18001b3e5  lea     r8, [r11-38h]; hstringHeader
0x18001b3e9  mov     edx, 29h ; ')'; length
0x18001b3ee  lea     rcx, ?RuntimeClass_Windows_Internal_Storage_Cloud_CloudStore@@3QBGB; "Windows.Internal.Storage.Cloud.CloudSto"...
0x18001b3f5  call    cs:__imp_WindowsCreateStringReference
0x18001b3fb  test    eax, eax
0x18001b3fd  js      short loc_18001B448
0x18001b3ff  mov     r8, rbx
0x18001b402  lea     rdx, _GUID_fc73907e_e219_4b15_9c14_90c3add7ad22
0x18001b409  mov     rcx, [rsp+68h+var_20]
0x18001b40e  call    cs:__imp_RoGetActivationFactory
0x18001b414  mov     rcx, [rsp+68h]; this
0x18001b419  test    eax, eax
0x18001b41b  js      short loc_18001B433
0x18001b41d  mov     rax, rbx
0x18001b420  mov     rcx, [rsp+68h+var_18]
0x18001b425  xor     rcx, rsp; StackCookie
0x18001b428  call    __security_check_cookie
0x18001b42d  add     rsp, 60h
0x18001b431  pop     rbx
0x18001b432  retn
0x18001b433  mov     r9d, eax; char *
0x18001b436  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18001b43d  mov     edx, 67h ; 'g'; void *
0x18001b442  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b448  mov     ecx, eax; this
0x18001b44a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
