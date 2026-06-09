# MessageProxyReconnectAdapter::RuntimeClassInitialize(_GUID const &,ushort const *,IMessageProxyReconnectAdapterOwner *)

- ea: `0x18003a3bc`
- end: `0x18003a5b4`
- name: `?RuntimeClassInitialize@MessageProxyReconnectAdapter@@QEAAJAEBU_GUID@@PEBGPEAUIMessageProxyReconnectAdapterOwner@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(MessageProxyReconnectAdapter *__hidden this, const struct _GUID *, const unsigned __int16 *, struct IMessageProxyReconnectAdapterOwner *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180057f40`
- `0x1800e5c84`
- `0x18013bc74`

## callees

- `0x180012b74`
- `0x18002a230`
- `0x18002a3a0`
- `0x18003a3bc`
- `0x18003b53c`
- `0x18008ead4`
- `0x1801ce010`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x18003a437`
- `CoreMessaging!CoreUICreate` at `0x18003a437`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x18003a515`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x18003a515`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MessageProxyReconnectAdapter::RuntimeClassInitialize(
        MessageProxyReconnectAdapter *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        struct IMessageProxyReconnectAdapterOwner *a4)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, int *); // rbx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  int started; // eax
  __int64 v17; // rdx
  int v19[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  const unsigned __int16 *v21; // [rsp+70h] [rbp+38h] BYREF

  v21 = a3;
  if ( !a3 )
  {
    v6 = 61;
LABEL_3:
    v7 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
      (const char *)v7,
      v19[0]);
    return v7;
  }
  if ( !a4 )
  {
    v6 = 62;
    goto LABEL_3;
  }
  *(struct _GUID *)((char *)this + 24) = *a2;
  v7 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 88, &v21);
  if ( (v7 & 0x80000000) != 0 )
  {
    v6 = 65;
    goto LABEL_4;
  }
  *((_QWORD *)this + 6) = a4;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 72);
  v7 = CoreUICreate((char *)this + 72);
  if ( (v7 & 0x80000000) != 0 )
  {
    v6 = 68;
    goto LABEL_4;
  }
  *(_QWORD *)v19 = 0;
  v8 = *((_QWORD *)this + 9);
  v9 = *(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 40LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v19);
  v10 = v9(v8, v19);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
      (const char *)(unsigned int)v10,
      v19[0]);
    v11 = *(_QWORD *)v19;
    if ( *(_QWORD *)v19 )
    {
      *(_QWORD *)v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v7;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 56LL))(*(_QWORD *)v19);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
      (const char *)(unsigned int)v12,
      v19[0]);
    v13 = *(_QWORD *)v19;
    if ( *(_QWORD *)v19 )
    {
      *(_QWORD *)v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v7;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 56);
  v14 = CoreUIFactoryCreate((char *)this + 56);
  v7 = v14;
  if ( v14 >= 0 )
  {
    started = MessageProxyReconnectAdapter::AttemptPullProxy(this);
    v7 = started;
    if ( started >= 0 )
    {
      if ( *((_QWORD *)this + 8)
        || (started = MessageProxyReconnectAdapter::StartConnectionRetryTimer(this), v7 = started, started >= 0) )
      {
        v7 = 0;
        goto LABEL_30;
      }
      v17 = 83;
    }
    else
    {
      v17 = 79;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
      (const char *)(unsigned int)started,
      v19[0]);
LABEL_30:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v19);
    return v7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4D,
    (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
    (const char *)(unsigned int)v14,
    v19[0]);
  v15 = *(_QWORD *)v19;
  if ( *(_QWORD *)v19 )
  {
    *(_QWORD *)v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return v7;
}

```

## disassembly

```asm
0x18003a3bc  mov     [rsp-20h+arg_10], r8
0x18003a3c1  push    rbp
0x18003a3c2  push    rbx
0x18003a3c3  push    rsi
0x18003a3c4  push    rdi
0x18003a3c5  mov     rbp, rsp
0x18003a3c8  sub     rsp, 38h
0x18003a3cc  mov     rdi, r9
0x18003a3cf  mov     rsi, rcx
0x18003a3d2  test    r8, r8
0x18003a3d5  jnz     short loc_18003A3F8
0x18003a3d7  lea     edx, [r8+3Dh]; void *
0x18003a3db  mov     ebx, 80070057h
0x18003a3e0  lea     r8, aMincoreTextinp; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x18003a3e7  mov     r9d, ebx; char *
0x18003a3ea  mov     rcx, [rbp+20h]; this
0x18003a3ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a3f3  jmp     loc_18003A5A9
0x18003a3f8  test    rdi, rdi
0x18003a3fb  jnz     short loc_18003A402
0x18003a3fd  lea     edx, [rdi+3Eh]
0x18003a400  jmp     short loc_18003A3DB
0x18003a402  movups  xmm0, xmmword ptr [rdx]
0x18003a405  movdqu  xmmword ptr [rcx+18h], xmm0
0x18003a40a  add     rcx, 58h ; 'X'
0x18003a40e  lea     rdx, [rbp+arg_10]
0x18003a412  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003a417  mov     ebx, eax
0x18003a419  test    eax, eax
0x18003a41b  jns     short loc_18003A424
0x18003a41d  mov     edx, 41h ; 'A'
0x18003a422  jmp     short loc_18003A3E0
0x18003a424  mov     [rsi+30h], rdi
0x18003a428  lea     rdi, [rsi+48h]
0x18003a42c  mov     rcx, rdi
0x18003a42f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a434  mov     rcx, rdi
0x18003a437  call    cs:__imp_CoreUICreate
0x18003a43d  mov     ebx, eax
0x18003a43f  test    eax, eax
0x18003a441  jns     short loc_18003A44A
0x18003a443  mov     edx, 44h ; 'D'
0x18003a448  jmp     short loc_18003A3E0
0x18003a44a  mov     qword ptr [rbp+var_18], 0
0x18003a452  mov     rdi, [rdi]
0x18003a455  mov     rax, [rdi]
0x18003a458  mov     rbx, [rax+28h]
0x18003a45c  lea     rcx, [rbp+var_18]
0x18003a460  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a465  lea     rdx, [rbp+var_18]
0x18003a469  mov     rcx, rdi
0x18003a46c  mov     rax, rbx
0x18003a46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a474  mov     ebx, eax
0x18003a476  test    eax, eax
0x18003a478  jns     short loc_18003A4B6
0x18003a47a  mov     rcx, [rbp+20h]; this
0x18003a47e  mov     r9d, eax; char *
0x18003a481  lea     r8, aMincoreTextinp; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x18003a488  mov     edx, 4Ah ; 'J'; void *
0x18003a48d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a492  nop
0x18003a493  mov     rcx, qword ptr [rbp+var_18]
0x18003a497  test    rcx, rcx
0x18003a49a  jz      short loc_18003A4B1
0x18003a49c  mov     qword ptr [rbp+var_18], 0
0x18003a4a4  mov     rax, [rcx]
0x18003a4a7  mov     rax, [rax+10h]
0x18003a4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4b0  nop
0x18003a4b1  jmp     loc_18003A5A9
0x18003a4b6  mov     rcx, qword ptr [rbp+var_18]
0x18003a4ba  mov     rax, [rcx]
0x18003a4bd  mov     rax, [rax+38h]
0x18003a4c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4c6  mov     ebx, eax
0x18003a4c8  test    eax, eax
0x18003a4ca  jns     short loc_18003A508
0x18003a4cc  mov     rcx, [rbp+20h]; this
0x18003a4d0  mov     r9d, eax; char *
0x18003a4d3  lea     r8, aMincoreTextinp; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x18003a4da  mov     edx, 4Bh ; 'K'; void *
0x18003a4df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a4e4  nop
0x18003a4e5  mov     rcx, qword ptr [rbp+var_18]
0x18003a4e9  test    rcx, rcx
0x18003a4ec  jz      short loc_18003A503
0x18003a4ee  mov     qword ptr [rbp+var_18], 0
0x18003a4f6  mov     rax, [rcx]
0x18003a4f9  mov     rax, [rax+10h]
0x18003a4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a502  nop
0x18003a503  jmp     loc_18003A5A9
0x18003a508  lea     rcx, [rsi+38h]
0x18003a50c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a511  lea     rcx, [rsi+38h]
0x18003a515  call    cs:__imp_CoreUIFactoryCreate
0x18003a51b  mov     ebx, eax
0x18003a51d  test    eax, eax
0x18003a51f  jns     short loc_18003A55A
0x18003a521  mov     rcx, [rbp+20h]; this
0x18003a525  mov     r9d, eax; char *
0x18003a528  lea     r8, aMincoreTextinp; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x18003a52f  mov     edx, 4Dh ; 'M'; void *
0x18003a534  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a539  nop
0x18003a53a  mov     rcx, qword ptr [rbp+var_18]
0x18003a53e  test    rcx, rcx
0x18003a541  jz      short loc_18003A558
0x18003a543  mov     qword ptr [rbp+var_18], 0
0x18003a54b  mov     rax, [rcx]
0x18003a54e  mov     rax, [rax+10h]
0x18003a552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a557  nop
0x18003a558  jmp     short loc_18003A5A9
0x18003a55a  mov     rcx, rsi; this
0x18003a55d  call    ?AttemptPullProxy@MessageProxyReconnectAdapter@@AEAAJXZ; MessageProxyReconnectAdapter::AttemptPullProxy(void)
0x18003a562  mov     ebx, eax
0x18003a564  test    eax, eax
0x18003a566  jns     short loc_18003A56F
0x18003a568  mov     edx, 4Fh ; 'O'
0x18003a56d  jmp     short loc_18003A589
0x18003a56f  cmp     qword ptr [rsi+40h], 0
0x18003a574  jnz     short loc_18003A59E
0x18003a576  mov     rcx, rsi; this
0x18003a579  call    ?StartConnectionRetryTimer@MessageProxyReconnectAdapter@@AEAAJXZ; MessageProxyReconnectAdapter::StartConnectionRetryTimer(void)
0x18003a57e  mov     ebx, eax
0x18003a580  test    eax, eax
0x18003a582  jns     short loc_18003A59E
0x18003a584  mov     edx, 53h ; 'S'; void *
0x18003a589  lea     r8, aMincoreTextinp; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x18003a590  mov     r9d, eax; char *
0x18003a593  mov     rcx, [rbp+20h]; this
0x18003a597  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a59c  jmp     short loc_18003A5A0
0x18003a59e  xor     ebx, ebx
0x18003a5a0  lea     rcx, [rbp+var_18]
0x18003a5a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a5a9  mov     eax, ebx
0x18003a5ab  add     rsp, 38h
0x18003a5af  pop     rdi
0x18003a5b0  pop     rsi
0x18003a5b1  pop     rbx
0x18003a5b2  pop     rbp
0x18003a5b3  retn
```
