# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReturnAsIBufferIfExistsOrEmptyBufferIfNot(winrt::com_ptr<Windows::Storage::Streams::IBuffer> &)

- ea: `0x18001e190`
- end: `0x18001e210`
- name: `?ReturnAsIBufferIfExistsOrEmptyBufferIfNot@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAA?AUIBuffer@Streams@Storage@67@AEAU?$com_ptr@UIBuffer@Streams@Storage@Windows@@@7@@Z`
- size: `128`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019dc4`
- `0x18001c220`

## callees

- `0x180010e04`
- `0x18001e190`
- `0x18002e2c8`
- `0x180033010`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReturnAsIBufferIfExistsOrEmptyBufferIfNot(
        __int64 a1,
        _QWORD *a2,
        __int64 (__fastcall ****a3)(_QWORD, __int64 *, __int64 *))
{
  __int64 (__fastcall ***v3)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 (__fastcall **v5)(_QWORD, __int64 *, __int64 *); // rax
  signed int v6; // eax
  __int64 v7; // r8
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  __int128 v10; // [rsp+38h] [rbp-20h]
  __int64 v11; // [rsp+60h] [rbp+8h] BYREF

  v11 = a1;
  v3 = *a3;
  if ( *a3 )
  {
    v5 = *v3;
    v11 = 0;
    LODWORD(v9) = 0;
    v10 = 0;
    v6 = (*v5)(v3, winrt::impl::guid_v<winrt::Windows::Storage::Streams::IBuffer>, &v11);
    if ( v6 < 0 )
      winrt::throw_hresult(v6, (unsigned int *)&v9, v7);
    *a2 = v11;
  }
  else
  {
    v9 = 0;
    *(_QWORD *)&v10 = 0;
    winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(a2, (int *)&v9);
  }
  return a2;
}

```

## disassembly

```asm
0x18001e190  mov     rax, rsp
0x18001e193  mov     [rax+8], rcx
0x18001e197  push    rbx
0x18001e198  sub     rsp, 50h
0x18001e19c  mov     rcx, [r8]
0x18001e19f  mov     rbx, rdx
0x18001e1a2  test    rcx, rcx
0x18001e1a5  jnz     short loc_18001E1BD
0x18001e1a7  mov     [rax-28h], rcx
0x18001e1ab  lea     rdx, [rax-28h]
0x18001e1af  mov     [rax-20h], rcx
0x18001e1b3  mov     rcx, rbx
0x18001e1b6  call    ?CreateIBufferOverCallerManagedBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(gsl::span<uchar,-1>)
0x18001e1bb  jmp     short loc_18001E1FA
0x18001e1bd  mov     rax, [rcx]
0x18001e1c0  lea     r8, [rsp+58h+arg_0]
0x18001e1c5  xorps   xmm0, xmm0
0x18001e1c8  mov     [rsp+58h+arg_0], 0
0x18001e1d1  lea     rdx, ??$guid_v@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Storage::Streams::IBuffer>
0x18001e1d8  mov     dword ptr [rsp+58h+var_28], 0
0x18001e1e0  movdqu  [rsp+58h+var_20], xmm0
0x18001e1e6  mov     rax, [rax]
0x18001e1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ee  test    eax, eax
0x18001e1f0  js      short loc_18001E203
0x18001e1f2  mov     rax, [rsp+58h+arg_0]
0x18001e1f7  mov     [rbx], rax
0x18001e1fa  mov     rax, rbx
0x18001e1fd  add     rsp, 50h
0x18001e201  pop     rbx
0x18001e202  retn
0x18001e203  lea     rdx, [rsp+58h+var_28]
0x18001e208  mov     ecx, eax
0x18001e20a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
