# FveEasNetworkStatusImpl::Initialize(void)

- ea: `0x180017dec`
- end: `0x180017ea4`
- name: `?Initialize@FveEasNetworkStatusImpl@@QEAAJXZ`
- size: `184`
- prototype: `__int64 __fastcall(FveEasNetworkStatusImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015820`

## callees

- `0x180001bb0`
- `0x1800037a0`
- `0x180017dec`
- `0x18001808c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180017e33`
- `KERNEL32!RaiseException` at `0x180017e33`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017e52`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017e1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017e1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FveEasNetworkStatusImpl::Initialize(FveEasNetworkStatusImpl *this)
{
  unsigned int ActivationFactory; // ebx
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF

  if ( WindowsCreateStringReference(
         L"Windows.Networking.Connectivity.NetworkInformation",
         0x32u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  Microsoft::WRL::ComPtr<FveEasNetworkStatusChangeNotificationHandler>::InternalRelease((char *)this + 8);
  ActivationFactory = RoGetActivationFactory(string, &GUID_5074f851_950d_4165_9c15_365619481eea, (char *)this + 8);
  if ( ActivationFactory
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      148,
      &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
      ActivationFactory);
  }
  return ActivationFactory;
}

```

## disassembly

```asm
0x180017dec  push    rbx
0x180017dee  sub     rsp, 50h
0x180017df2  mov     rax, cs:__security_cookie
0x180017df9  xor     rax, rsp
0x180017dfc  mov     [rsp+58h+var_18], rax
0x180017e01  mov     rbx, rcx
0x180017e04  lea     r9, [rsp+58h+string]; string
0x180017e09  lea     rcx, ?RuntimeClass_Windows_Networking_Connectivity_NetworkInformation@@3QBGB; "Windows.Networking.Connectivity.Network"...
0x180017e10  mov     edx, 32h ; '2'; length
0x180017e15  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180017e1a  call    cs:__imp_WindowsCreateStringReference
0x180017e20  test    eax, eax
0x180017e22  jns     short loc_180017E39
0x180017e24  xor     r9d, r9d; lpArguments
0x180017e27  xor     r8d, r8d; nNumberOfArguments
0x180017e2a  mov     ecx, 0C000000Dh; dwExceptionCode
0x180017e2f  lea     edx, [r9+1]; dwExceptionFlags
0x180017e33  call    cs:__imp_RaiseException
0x180017e39  lea     rcx, [rbx+8]
0x180017e3d  call    ?InternalRelease@?$ComPtr@VFveEasNetworkStatusChangeNotificationHandler@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<FveEasNetworkStatusChangeNotificationHandler>::InternalRelease(void)
0x180017e42  mov     rcx, [rsp+58h+string]
0x180017e47  lea     r8, [rbx+8]
0x180017e4b  lea     rdx, _GUID_5074f851_950d_4165_9c15_365619481eea
0x180017e52  call    cs:__imp_RoGetActivationFactory
0x180017e58  mov     ebx, eax
0x180017e5a  test    eax, eax
0x180017e5c  jz      short loc_180017E8F
0x180017e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e65  lea     rax, WPP_GLOBAL_Control
0x180017e6c  cmp     rcx, rax
0x180017e6f  jz      short loc_180017E8F
0x180017e71  test    byte ptr [rcx+1Ch], 40h
0x180017e75  jz      short loc_180017E8F
0x180017e77  mov     rcx, [rcx+10h]
0x180017e7b  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180017e82  mov     edx, 94h
0x180017e87  mov     r9d, ebx
0x180017e8a  call    WPP_SF_d
0x180017e8f  mov     eax, ebx
0x180017e91  mov     rcx, [rsp+58h+var_18]
0x180017e96  xor     rcx, rsp; StackCookie
0x180017e99  call    __security_check_cookie
0x180017e9e  add     rsp, 50h
0x180017ea2  pop     rbx
0x180017ea3  retn
```
