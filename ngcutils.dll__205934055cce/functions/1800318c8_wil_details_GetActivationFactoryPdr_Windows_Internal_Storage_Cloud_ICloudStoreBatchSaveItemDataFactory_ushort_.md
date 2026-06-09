# wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreBatchSaveItemDataFactory>(ushort const *)

- ea: `0x1800318c8`
- end: `0x180031974`
- name: `??$GetActivationFactoryPdr@UICloudStoreBatchSaveItemDataFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreBatchSaveItemDataFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z`
- size: `172`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001fb70`
- `0x180020cb0`
- `0x180021de0`
- `0x18002ba90`
- `0x18002c8d0`
- `0x18002d710`

## callees

- `0x180003080`
- `0x180013fe4`
- `0x18001ae30`
- `0x1800318c8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180031919`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180031919`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031932`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031932`

## pseudocode

```c
_QWORD *__fastcall wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreBatchSaveItemDataFactory>(
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
  v2 = WindowsCreateStringReference(L"Windows.Internal.Storage.Cloud.CloudStoreBatchSaveItemData", 0x3Au, &v7, &v8);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x180031973LL);
  }
  ActivationFactory = RoGetActivationFactory(v8, &GUID_b842c17c_5375_485c_90dd_25e01e9b0bea, a1);
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
0x1800318c8  mov     r11, rsp
0x1800318cb  push    rbx
0x1800318cc  sub     rsp, 60h
0x1800318d0  mov     rax, cs:__security_cookie
0x1800318d7  xor     rax, rsp
0x1800318da  mov     [rsp+68h+var_18], rax
0x1800318df  mov     rbx, rcx
0x1800318e2  mov     [r11-40h], rcx
0x1800318e6  mov     [rsp+68h+var_48], 0
0x1800318ee  mov     [rsp+68h+var_48], 1; int
0x1800318f6  mov     qword ptr [rcx], 0
0x1800318fd  mov     qword ptr [r11-20h], 0
0x180031905  lea     r9, [r11-20h]; string
0x180031909  lea     r8, [r11-38h]; hstringHeader
0x18003190d  mov     edx, 3Ah ; ':'; length
0x180031912  lea     rcx, ?RuntimeClass_Windows_Internal_Storage_Cloud_CloudStoreBatchSaveItemData@@3QBGB; "Windows.Internal.Storage.Cloud.CloudSto"...
0x180031919  call    cs:__imp_WindowsCreateStringReference
0x18003191f  test    eax, eax
0x180031921  js      short loc_18003196C
0x180031923  mov     r8, rbx
0x180031926  lea     rdx, _GUID_b842c17c_5375_485c_90dd_25e01e9b0bea
0x18003192d  mov     rcx, [rsp+68h+var_20]
0x180031932  call    cs:__imp_RoGetActivationFactory
0x180031938  mov     rcx, [rsp+68h]; this
0x18003193d  test    eax, eax
0x18003193f  js      short loc_180031957
0x180031941  mov     rax, rbx
0x180031944  mov     rcx, [rsp+68h+var_18]
0x180031949  xor     rcx, rsp; StackCookie
0x18003194c  call    __security_check_cookie
0x180031951  add     rsp, 60h
0x180031955  pop     rbx
0x180031956  retn
0x180031957  mov     r9d, eax; char *
0x18003195a  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180031961  mov     edx, 67h ; 'g'; void *
0x180031966  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003196c  mov     ecx, eax; this
0x18003196e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
