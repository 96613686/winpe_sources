# wil::details::CreateCloudStoreDefaultWithWaitTime(Windows::Internal::Storage::Cloud::CloudStoreOptions,Windows::System::IUser *,Windows::Security::Credentials::IWebAccount *,ushort const *,Windows::Internal::Storage::Cloud::WaitTimes const &)

- ea: `0x18001bb38`
- end: `0x18001bd32`
- name: `?CreateCloudStoreDefaultWithWaitTime@details@wil@@YA?AV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@W4CloudStoreOptions@Cloud@Storage@Internal@Windows@@PEAUIUser@System@8@PEAUIWebAccount@Credentials@Security@8@PEBGAEBUWaitTimes@5678@@Z`
- size: `506`
- prototype: `__int64 __fastcall(int, int, int, int, PCWSTR sourceString, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180049238`

## callees

- `0x180003080`
- `0x180007a5c`
- `0x180013fe4`
- `0x18001ae30`
- `0x18001b3a4`
- `0x18001bb38`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bc27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bc27`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall wil::details::CreateCloudStoreDefaultWithWaitTime(
        _QWORD *a1,
        int a2,
        __int64 a3,
        const char *a4,
        PCWSTR sourceString,
        __int64 a6)
{
  wil::details::in1diag3 *v10; // rcx
  unsigned int v11; // r8d
  int v12; // edi
  __int64 *v13; // r13
  unsigned __int64 v14; // rdx
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int v18; // eax
  __int64 v19; // rcx
  int v21; // [rsp+20h] [rbp-99h]
  __int64 *v22; // [rsp+48h] [rbp-71h] BYREF
  __int64 *v23; // [rsp+50h] [rbp-69h]
  __int64 v24; // [rsp+58h] [rbp-61h]
  char v25; // [rsp+60h] [rbp-59h]
  __int64 v26; // [rsp+68h] [rbp-51h]
  const char *v27; // [rsp+70h] [rbp-49h]
  __int64 v28; // [rsp+78h] [rbp-41h]
  __int64 v29; // [rsp+80h] [rbp-39h]
  _QWORD *v30; // [rsp+88h] [rbp-31h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-29h] BYREF
  HSTRING string; // [rsp+A8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+4Fh]

  v27 = a4;
  v28 = a3;
  v30 = a1;
  v26 = a6;
  v10 = retaddr;
  if ( (a2 & 1) != 0 )
LABEL_17:
    wil::details::in1diag3::_FailFast_Unexpected(
      v10,
      (void *)0x75,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
      a4);
  if ( (a2 & 2) != 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
      a4);
  wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(&v22);
  *a1 = 0;
  v12 = a4 == 0 ? 2 : 0;
  v13 = v22;
  v29 = *v22;
  v23 = a1;
  v24 = 0;
  v25 = 1;
  string = 0;
  v14 = -1;
  do
    ++v14;
  while ( sourceString[v14] );
  if ( v14 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v14, v11);
    goto LABEL_17;
  }
  if ( (int)v14 + 1 < (unsigned int)v14 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v14, v11);
    __debugbreak();
  }
  v15 = WindowsCreateStringReference(sourceString, v14, &hstringHeader, &string);
  if ( v15 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
    JUMPOUT(0x18001BD31LL);
  }
  v21 = (int)string;
  v18 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, const char *))(v29 + 56))(
          v13,
          a2 | v12 | (unsigned int)(a3 == 0),
          v28,
          v27);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
      (const char *)(unsigned int)v18,
      v21);
  string = 0;
  if ( v25 )
  {
    v19 = *v23;
    *v23 = v24;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
  return a1;
}

```

## disassembly

```asm
0x18001bb38  push    rbp
0x18001bb3a  push    rbx
0x18001bb3b  push    rsi
0x18001bb3c  push    rdi
0x18001bb3d  push    r12
0x18001bb3f  push    r13
0x18001bb41  push    r14
0x18001bb43  push    r15
0x18001bb45  lea     rbp, [rsp-0Fh]
0x18001bb4a  sub     rsp, 0C8h
0x18001bb51  mov     rax, cs:__security_cookie
0x18001bb58  xor     rax, rsp
0x18001bb5b  mov     [rbp+47h+var_50], rax
0x18001bb5f  mov     rdi, r9
0x18001bb62  mov     [rbp+47h+var_90], r9
0x18001bb66  mov     r12, r8
0x18001bb69  mov     [rbp+47h+var_88], r8
0x18001bb6d  mov     esi, edx
0x18001bb6f  mov     rbx, rcx
0x18001bb72  mov     [rbp+47h+var_78], rcx
0x18001bb76  mov     r15, [rbp+47h+sourceString]
0x18001bb7a  mov     rax, [rbp+47h+arg_28]
0x18001bb7e  mov     [rbp+47h+var_98], rax
0x18001bb82  mov     [rbp+47h+var_C0], 0
0x18001bb89  mov     rcx, [rbp+4Fh]
0x18001bb8d  test    dl, 1
0x18001bb90  jnz     loc_18001BCFB
0x18001bb96  mov     rcx, [rbp+4Fh]; this
0x18001bb9a  test    sil, 2
0x18001bb9e  jnz     loc_18001BD0D
0x18001bba4  lea     rcx, [rbp+47h+var_B8]
0x18001bba8  call    ??$GetActivationFactoryPdr@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z; wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreFactory>(ushort const *)
0x18001bbad  nop
0x18001bbae  xor     ecx, ecx
0x18001bbb0  mov     [rbx], rcx
0x18001bbb3  mov     [rbp+47h+var_C0], 1
0x18001bbba  mov     rax, rdi
0x18001bbbd  neg     rax
0x18001bbc0  sbb     edi, edi
0x18001bbc2  not     edi
0x18001bbc4  and     edi, 2
0x18001bbc7  mov     r14d, ecx
0x18001bbca  test    r12, r12
0x18001bbcd  setz    r14b
0x18001bbd1  mov     r13, [rbp+47h+var_B8]
0x18001bbd5  mov     rax, [r13+0]
0x18001bbd9  mov     [rbp+47h+var_80], rax
0x18001bbdd  mov     [rbp+47h+var_B0], rbx
0x18001bbe1  mov     [rbp+47h+var_A8], rcx
0x18001bbe5  mov     [rbp+47h+var_A0], 1
0x18001bbe9  mov     [rbp+47h+string], rcx
0x18001bbed  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001bbf1  inc     rdx; int
0x18001bbf4  cmp     [r15+rdx*2], cx
0x18001bbf9  jnz     short loc_18001BBF1
0x18001bbfb  mov     eax, 0FFFFFFFFh
0x18001bc00  cmp     rdx, rax
0x18001bc03  ja      loc_18001BCF0
0x18001bc09  lea     eax, [rdx+1]
0x18001bc0c  cmp     eax, edx
0x18001bc0e  jb      loc_18001BD1F
0x18001bc14  mov     r12, [rbp+47h+var_98]
0x18001bc18  mov     r12, [r12]
0x18001bc1c  lea     r9, [rbp+47h+string]; string
0x18001bc20  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x18001bc24  mov     rcx, r15; sourceString
0x18001bc27  call    cs:__imp_WindowsCreateStringReference
0x18001bc2d  xor     r15d, r15d
0x18001bc30  test    eax, eax
0x18001bc32  js      loc_18001BD2A
0x18001bc38  or      r14d, edi
0x18001bc3b  or      r14d, esi
0x18001bc3e  lea     rax, [rbp+47h+var_A8]
0x18001bc42  mov     [rsp+100h+var_D0], rax
0x18001bc47  mov     [rsp+100h+var_D8], r12
0x18001bc4c  mov     rax, [rbp+47h+string]
0x18001bc50  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18001bc55  mov     r9, [rbp+47h+var_90]
0x18001bc59  mov     r8, [rbp+47h+var_88]
0x18001bc5d  mov     edx, r14d
0x18001bc60  mov     rcx, r13
0x18001bc63  mov     rax, [rbp+47h+var_80]
0x18001bc67  mov     rax, [rax+38h]
0x18001bc6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc70  mov     rcx, [rbp+4Fh]; this
0x18001bc74  test    eax, eax
0x18001bc76  js      short loc_18001BCDB
0x18001bc78  mov     [rbp+47h+string], r15
0x18001bc7c  cmp     [rbp+47h+var_A0], r15b
0x18001bc80  jz      short loc_18001BCA2
0x18001bc82  mov     rdx, [rbp+47h+var_A8]
0x18001bc86  mov     rax, [rbp+47h+var_B0]
0x18001bc8a  mov     rcx, [rax]
0x18001bc8d  mov     [rax], rdx
0x18001bc90  test    rcx, rcx
0x18001bc93  jz      short loc_18001BCA2
0x18001bc95  mov     rax, [rcx]
0x18001bc98  mov     rax, [rax+10h]
0x18001bc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bca1  nop
0x18001bca2  mov     rcx, [rbp+47h+var_B8]
0x18001bca6  test    rcx, rcx
0x18001bca9  jz      short loc_18001BCB8
0x18001bcab  mov     rdx, [rcx]
0x18001bcae  mov     rax, [rdx+10h]
0x18001bcb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcb7  nop
0x18001bcb8  mov     rax, rbx
0x18001bcbb  mov     rcx, [rbp+47h+var_50]
0x18001bcbf  xor     rcx, rsp; StackCookie
0x18001bcc2  call    __security_check_cookie
0x18001bcc7  add     rsp, 0C8h
0x18001bcce  pop     r15
0x18001bcd0  pop     r14
0x18001bcd2  pop     r13
0x18001bcd4  pop     r12
0x18001bcd6  pop     rdi
0x18001bcd7  pop     rsi
0x18001bcd8  pop     rbx
0x18001bcd9  pop     rbp
0x18001bcda  retn
0x18001bcdb  mov     r9d, eax; char *
0x18001bcde  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18001bce5  mov     edx, 89h; void *
0x18001bcea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001bcf0  mov     ecx, 80070216h; this
0x18001bcf5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001bcfa  nop
0x18001bcfb  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18001bd02  mov     edx, 75h ; 'u'; void *
0x18001bd07  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001bd0d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18001bd14  mov     edx, 76h ; 'v'; void *
0x18001bd19  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001bd1f  mov     ecx, 80070216h; this
0x18001bd24  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001bd29  int     3; Trap to Debugger
0x18001bd2a  mov     ecx, eax; this
0x18001bd2c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
