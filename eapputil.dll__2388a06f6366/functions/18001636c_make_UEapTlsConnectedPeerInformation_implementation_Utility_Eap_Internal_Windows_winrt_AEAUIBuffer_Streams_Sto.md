# ??$make@UEapTlsConnectedPeerInformation@implementation@Utility@Eap@Internal@Windows@winrt@@AEAUIBuffer@Streams@Storage@67@AEAU_SecPkgContext_StreamSizes@@AEAK@winrt@@YA?A_PAEAUIBuffer@Streams@Storage@Windows@0@AEAU_SecPkgContext_StreamSizes@@AEAK@Z

- ea: `0x18001636c`
- end: `0x18001644f`
- name: `??$make@UEapTlsConnectedPeerInformation@implementation@Utility@Eap@Internal@Windows@winrt@@AEAUIBuffer@Streams@Storage@67@AEAU_SecPkgContext_StreamSizes@@AEAK@winrt@@YA?A_PAEAUIBuffer@Streams@Storage@Windows@0@AEAU_SecPkgContext_StreamSizes@@AEAK@Z`
- size: `227`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *, _DWORD *, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180018e1c`
- `0x18001e330`
- `0x1800294d0`

## callees

- `0x1800037dc`
- `0x18001636c`
- `0x180033010`

## pseudocode

```c
_QWORD *__fastcall winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsConnectedPeerInformation,winrt::Windows::Storage::Streams::IBuffer &,_SecPkgContext_StreamSizes &,unsigned long &>(
        _QWORD *a1,
        __int64 *a2,
        _DWORD *a3,
        int *a4)
{
  _QWORD *v8; // r14
  int v9; // ebx
  __int64 v10; // rcx

  v8 = operator new(0x48u);
  v9 = *a4;
  v8[2] = &winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsConnectedPeerInformation,winrt::Windows::Internal::Eap::Utility::IEapTlsConnectedPeerInformation>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v8[1] = 1;
  *v8 = &winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsConnectedPeerInformation>::`vftable';
  v8[3] = 0;
  v8[5] = 0;
  *((_DWORD *)v8 + 12) = *a3;
  *((_DWORD *)v8 + 13) = a3[1];
  *((_DWORD *)v8 + 14) = a3[2];
  v10 = *a2;
  v8[8] = *a2;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  if ( (v9 & 0xC0) != 0 )
  {
    *((_DWORD *)v8 + 15) = 1;
  }
  else if ( (v9 & 0x300) != 0 )
  {
    *((_DWORD *)v8 + 15) = 2;
  }
  else
  {
    *((_DWORD *)v8 + 15) = (v9 & 0xC00) != 0 ? 4 : 8;
  }
  *a1 = v8 + 2;
  *v8 = &winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsConnectedPeerInformation>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x18001636c  push    rbx
0x18001636e  push    rbp
0x18001636f  push    rsi
0x180016370  push    rdi
0x180016371  push    r14
0x180016373  push    r15
0x180016375  sub     rsp, 38h
0x180016379  mov     r15, rcx
0x18001637c  mov     rbx, r9
0x18001637f  mov     ecx, 48h ; 'H'; Size
0x180016384  mov     rdi, r8
0x180016387  mov     rsi, rdx
0x18001638a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001638f  mov     [rsp+68h+arg_0], rax
0x180016394  mov     r14, rax
0x180016397  mov     ebx, [rbx]
0x180016399  lea     rbp, [rax+10h]
0x18001639d  lea     rax, ??_7?$produce@UEapTlsConnectedPeerInformation@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapTlsConnectedPeerInformation@34567@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsConnectedPeerInformation,winrt::Windows::Internal::Eap::Utility::IEapTlsConnectedPeerInformation>::`vftable'
0x1800163a4  mov     [rbp+0], rax
0x1800163a8  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800163af  mov     qword ptr [r14+8], 1
0x1800163b7  lea     rax, ??_7?$heap_implements@UEapTlsConnectedPeerInformation@implementation@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsConnectedPeerInformation>::`vftable'
0x1800163be  mov     [r14], rax
0x1800163c1  mov     qword ptr [r14+18h], 0
0x1800163c9  mov     qword ptr [r14+28h], 0
0x1800163d1  mov     ecx, [rdi]
0x1800163d3  mov     [r14+30h], ecx
0x1800163d7  mov     eax, [rdi+4]
0x1800163da  mov     [r14+34h], eax
0x1800163de  mov     eax, [rdi+8]
0x1800163e1  mov     [r14+38h], eax
0x1800163e5  mov     rcx, [rsi]
0x1800163e8  mov     [r14+40h], rcx
0x1800163ec  test    rcx, rcx
0x1800163ef  jz      short loc_1800163FD
0x1800163f1  mov     rax, [rcx]
0x1800163f4  mov     rax, [rax+8]
0x1800163f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163fd  test    bl, 0C0h
0x180016400  jz      short loc_18001640C
0x180016402  mov     dword ptr [r14+3Ch], 1
0x18001640a  jmp     short loc_180016432
0x18001640c  test    ebx, 300h
0x180016412  jz      short loc_18001641E
0x180016414  mov     dword ptr [r14+3Ch], 2
0x18001641c  jmp     short loc_180016432
0x18001641e  and     ebx, 0C00h
0x180016424  neg     ebx
0x180016426  sbb     eax, eax
0x180016428  and     eax, 0FFFFFFFCh
0x18001642b  add     eax, 8
0x18001642e  mov     [r14+3Ch], eax
0x180016432  lea     rax, ??_7?$heap_implements@UEapTlsConnectedPeerInformation@implementation@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsConnectedPeerInformation>::`vftable'
0x180016439  mov     [r15], rbp
0x18001643c  mov     [r14], rax
0x18001643f  mov     rax, r15
0x180016442  add     rsp, 38h
0x180016446  pop     r15
0x180016448  pop     r14
0x18001644a  pop     rdi
0x18001644b  pop     rsi
0x18001644c  pop     rbp
0x18001644d  pop     rbx
0x18001644e  retn
```
