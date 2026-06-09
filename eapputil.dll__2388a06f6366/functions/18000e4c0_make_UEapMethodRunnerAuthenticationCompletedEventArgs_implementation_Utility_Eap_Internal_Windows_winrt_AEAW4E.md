# ??$make@UEapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@AEAW4EapAuthenticationStatus@34567@AEA_NAEAUtagEapHostPeerMethodResult@@AEAV?$optional@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@winrt@@YA?A_PAEAW4EapAuthenticationStatus@Utility@Eap@Internal@Windows@0@AEA_NAEAUtagEapHostPeerMethodResult@@AEAV?$optional@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@Z

- ea: `0x18000e4c0`
- end: `0x18000e5ac`
- name: `??$make@UEapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@AEAW4EapAuthenticationStatus@34567@AEA_NAEAUtagEapHostPeerMethodResult@@AEAV?$optional@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@winrt@@YA?A_PAEAW4EapAuthenticationStatus@Utility@Eap@Internal@Windows@0@AEA_NAEAUtagEapHostPeerMethodResult@@AEAV?$optional@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@Z`
- size: `236`
- prototype: `_QWORD *__fastcall(_QWORD *, int *, char *, int, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f900`

## callees

- `0x1800037dc`
- `0x1800083ec`
- `0x18000e4c0`
- `0x18002f008`
- `0x180033010`

## pseudocode

```c
_QWORD *__fastcall winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs,enum winrt::Windows::Internal::Eap::Utility::EapAuthenticationStatus &,bool &,tagEapHostPeerMethodResult &,std::optional<winrt::Windows::Storage::Streams::IBuffer> &>(
        _QWORD *a1,
        int *a2,
        char *a3,
        int a4,
        __int64 *a5)
{
  _QWORD *v9; // rbx
  int v10; // r8d
  char v11; // dl
  __int64 v12; // rcx
  char v13; // si
  int v14; // r14d
  __int64 v16; // [rsp+38h] [rbp-28h] BYREF
  char v17; // [rsp+40h] [rbp-20h]
  __int64 v18; // [rsp+48h] [rbp-18h] BYREF
  char v19; // [rsp+50h] [rbp-10h]

  v9 = operator new(0x78u);
  v11 = 0;
  v17 = 0;
  if ( *((_BYTE *)a5 + 8) )
  {
    v12 = *a5;
    v16 = v12;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    v11 = 1;
    v17 = 1;
  }
  v13 = *a3;
  v14 = *a2;
  v19 = 0;
  if ( v11 )
  {
    v18 = v16;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    v19 = 1;
  }
  LOBYTE(v10) = v13;
  winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::EapMethodRunnerAuthenticationCompletedEventArgs(
    (_DWORD)v9,
    v14,
    v10,
    a4,
    (__int64)&v18);
  *v9 = &winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs>::`vftable';
  if ( v17 && v16 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v16);
  *a1 = v9 + 2;
  return a1;
}

```

## disassembly

```asm
0x18000e4c0  mov     [rsp-28h+arg_10], rbx
0x18000e4c5  mov     [rsp-28h+arg_0], rcx
0x18000e4ca  push    rbp
0x18000e4cb  push    rsi
0x18000e4cc  push    rdi
0x18000e4cd  push    r14
0x18000e4cf  push    r15
0x18000e4d1  mov     rbp, rsp
0x18000e4d4  sub     rsp, 60h
0x18000e4d8  mov     r15, r9
0x18000e4db  mov     rsi, r8
0x18000e4de  mov     r14, rdx
0x18000e4e1  mov     rdi, rcx
0x18000e4e4  mov     ecx, 78h ; 'x'; Size
0x18000e4e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e4ee  mov     rbx, rax
0x18000e4f1  mov     [rbp+arg_0], rax
0x18000e4f5  xor     dl, dl
0x18000e4f7  mov     [rbp+var_20], dl
0x18000e4fa  mov     rcx, [rbp+arg_20]
0x18000e4fe  cmp     [rcx+8], dl
0x18000e501  jz      short loc_18000E520
0x18000e503  mov     rcx, [rcx]
0x18000e506  mov     [rbp+var_28], rcx
0x18000e50a  test    rcx, rcx
0x18000e50d  jz      short loc_18000E51B
0x18000e50f  mov     rax, [rcx]
0x18000e512  mov     rax, [rax+8]
0x18000e516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e51b  mov     dl, 1
0x18000e51d  mov     [rbp+var_20], dl
0x18000e520  lea     rax, [rbp+var_28]
0x18000e524  mov     [rbp+arg_20], rax
0x18000e528  mov     sil, [rsi]
0x18000e52b  mov     r14d, [r14]
0x18000e52e  mov     [rbp+var_10], 0
0x18000e532  test    dl, dl
0x18000e534  jz      short loc_18000E553
0x18000e536  mov     rcx, [rbp+var_28]
0x18000e53a  mov     [rbp+var_18], rcx
0x18000e53e  test    rcx, rcx
0x18000e541  jz      short loc_18000E54F
0x18000e543  mov     rax, [rcx]
0x18000e546  mov     rax, [rax+8]
0x18000e54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e54f  mov     [rbp+var_10], 1
0x18000e553  lea     rax, [rbp+var_18]
0x18000e557  mov     [rsp+60h+var_40], rax
0x18000e55c  mov     r9, r15
0x18000e55f  mov     r8b, sil
0x18000e562  mov     edx, r14d
0x18000e565  mov     rcx, rbx
0x18000e568  call    ??0EapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@QEAA@W4EapAuthenticationStatus@23456@_NAEBUtagEapHostPeerMethodResult@@V?$optional@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::EapMethodRunnerAuthenticationCompletedEventArgs(winrt::Windows::Internal::Eap::Utility::EapAuthenticationStatus,bool,tagEapHostPeerMethodResult const &,std::optional<winrt::Windows::Storage::Streams::IBuffer>)
0x18000e56d  lea     rax, ??_7?$heap_implements@UEapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs>::`vftable'
0x18000e574  mov     [rbx], rax
0x18000e577  cmp     [rbp+var_20], 0
0x18000e57b  jz      short loc_18000E58E
0x18000e57d  cmp     [rbp+var_28], 0
0x18000e582  jz      short loc_18000E58E
0x18000e584  lea     rcx, [rbp+var_28]
0x18000e588  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000e58d  nop
0x18000e58e  lea     rax, [rbx+10h]
0x18000e592  mov     [rdi], rax
0x18000e595  mov     rax, rdi
0x18000e598  mov     rbx, [rsp+60h+arg_10]
0x18000e5a0  add     rsp, 60h
0x18000e5a4  pop     r15
0x18000e5a6  pop     r14
0x18000e5a8  pop     rdi
0x18000e5a9  pop     rsi
0x18000e5aa  pop     rbp
0x18000e5ab  retn
```
