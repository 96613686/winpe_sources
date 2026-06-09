# RasEapExportMethodId_PopulateSessionInfo(_EAPTLS_CONTROL_BLOCK *,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &,ulong &)

- ea: `0x18001ecdc`
- end: `0x18001ef65`
- name: `?RasEapExportMethodId_PopulateSessionInfo@@YAJPEAU_EAPTLS_CONTROL_BLOCK@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@AEAK@Z`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002e7a8`

## callees

- `0x180007d00`
- `0x18001ecdc`
- `0x18001ef6c`
- `0x180028420`
- `0x18002f800`
- `0x180038270`
- `0x180038640`
- `0x180038748`
- `0x180038dca`
- `0x180038e4c`
- `0x180038e64`
- `0x18003ff44`
- `0x18005bbbc`
- `0x180082010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001ed82`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001eebb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001ed82`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001eebb`
- `SspiCli!QueryContextAttributesW` at `0x18001ed35`
- `SspiCli!QueryContextAttributesW` at `0x18001ed35`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall RasEapExportMethodId_PopulateSessionInfo(__int64 a1, void **a2, unsigned int *a3)
{
  SECURITY_STATUS ContextAttributesW; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  unsigned int v9; // ebx
  void *v10; // rdi
  void *v11; // rbx
  void *v12; // rcx
  int v13; // eax
  unsigned int v14; // r12d
  void *v15; // rdi
  void *v16; // rbx
  const void *v17; // rax
  void *v18; // rcx
  size_t Size; // [rsp+20h] [rbp-78h] BYREF
  __int64 v21; // [rsp+28h] [rbp-70h] BYREF
  void *v22; // [rsp+30h] [rbp-68h] BYREF
  char v23; // [rsp+38h] [rbp-60h] BYREF
  _OWORD pBuffer[2]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v25; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( *(_BYTE *)(a1 + 849) )
  {
    memset(pBuffer, 0, sizeof(pBuffer));
    v25 = 0;
    ContextAttributesW = QueryContextAttributesW((PCtxtHandle)(a1 + 648), 0x5Du, pBuffer);
    if ( ContextAttributesW < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, v7, v8, (const char *)(unsigned int)ContextAttributesW, Size);
    v9 = DWORD1(pBuffer[0]);
    v10 = operator new[](DWORD1(pBuffer[0]));
    memset_0(v10, 0, v9);
    v11 = v10;
    if ( DWORD1(pBuffer[0]) )
    {
      if ( v10 )
      {
        memcpy_0(v10, (char *)pBuffer + 8, DWORD1(pBuffer[0]));
      }
      else
      {
        *(_DWORD *)_o__errno() = 22;
        invalid_parameter_noinfo();
      }
    }
    if ( a2 == (void **)&v23 || (v11 = 0, v12 = *a2, *a2 = v10, !v12) )
    {
      *a3 = DWORD1(pBuffer[0]);
      if ( v11 )
        operator delete(v11);
    }
    else
    {
      operator delete(v12);
      *a3 = DWORD1(pBuffer[0]);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_253d6767ad5c33bd246c71206321af56_Traceguids);
  winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapMethodId(
    a1 + 856,
    &v21);
  LODWORD(Size) = 0;
  LODWORD(pBuffer[0]) = 0;
  *(_OWORD *)((char *)pBuffer + 8) = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, size_t *))(*(_QWORD *)v21 + 56LL))(v21, &Size);
  if ( v13 < 0 )
    winrt::throw_hresult((unsigned int)v13, pBuffer);
  v14 = Size;
  v15 = operator new[]((unsigned int)Size);
  memset_0(v15, 0, v14);
  v16 = v15;
  v22 = v15;
  v17 = (const void *)winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(&v21);
  if ( v14 )
  {
    if ( v15 )
    {
      if ( v17 )
      {
        memcpy_0(v15, v17, v14);
        goto LABEL_23;
      }
      memset_0(v15, 0, v14);
    }
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
  }
LABEL_23:
  if ( a2 != &v22 )
  {
    v16 = 0;
    v18 = *a2;
    *a2 = v15;
    if ( v18 )
      operator delete(v18);
  }
  *a3 = v14;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_253d6767ad5c33bd246c71206321af56_Traceguids);
  if ( v16 )
    operator delete(v16);
  if ( v21 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v21);
  return 0;
}

```

## disassembly

```asm
0x18001ecdc  mov     [rsp+arg_18], rbx
0x18001ece1  push    rsi
0x18001ece2  push    rdi
0x18001ece3  push    r12
0x18001ece5  push    r14
0x18001ece7  push    r15
0x18001ece9  sub     rsp, 70h
0x18001eced  mov     rax, cs:__security_cookie
0x18001ecf4  xor     rax, rsp
0x18001ecf7  mov     [rsp+98h+var_30], rax
0x18001ecfc  mov     r15, r8
0x18001ecff  mov     rsi, rdx
0x18001ed02  mov     rbx, rcx
0x18001ed05  cmp     byte ptr [rcx+351h], 0
0x18001ed0c  jz      loc_18001EDED
0x18001ed12  xorps   xmm0, xmm0
0x18001ed15  xor     eax, eax
0x18001ed17  movups  [rsp+98h+pBuffer], xmm0
0x18001ed1c  movups  [rsp+98h+var_48], xmm0
0x18001ed21  mov     [rsp+98h+var_38], rax
0x18001ed26  add     rcx, 288h; phContext
0x18001ed2d  lea     r8, [rsp+98h+pBuffer]; pBuffer
0x18001ed32  lea     edx, [rax+5Dh]; ulAttribute
0x18001ed35  call    cs:__imp_QueryContextAttributesW
0x18001ed3c  nop     dword ptr [rax+rax+00h]
0x18001ed41  mov     rcx, [rsp+98h]; this
0x18001ed49  test    eax, eax
0x18001ed4b  jns     short loc_18001ED55
0x18001ed4d  mov     r9d, eax; char *
0x18001ed50  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18001ed55  mov     ebx, dword ptr [rsp+98h+pBuffer+4]
0x18001ed59  mov     ecx, ebx; unsigned __int64
0x18001ed5b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001ed60  mov     rdi, rax
0x18001ed63  mov     r8d, ebx; Size
0x18001ed66  xor     edx, edx; Val
0x18001ed68  mov     rcx, rax; void *
0x18001ed6b  call    memset_0
0x18001ed70  mov     rbx, rdi
0x18001ed73  mov     r8d, dword ptr [rsp+98h+pBuffer+4]; Size
0x18001ed78  test    r8, r8
0x18001ed7b  jz      short loc_18001EDA8
0x18001ed7d  test    rdi, rdi
0x18001ed80  jnz     short loc_18001ED9B
0x18001ed82  call    cs:__imp__o__errno
0x18001ed89  nop     dword ptr [rax+rax+00h]
0x18001ed8e  mov     dword ptr [rax], 16h
0x18001ed94  call    _invalid_parameter_noinfo
0x18001ed99  jmp     short loc_18001EDA8
0x18001ed9b  lea     rdx, [rsp+98h+pBuffer+8]; Src
0x18001eda0  mov     rcx, rdi; void *
0x18001eda3  call    memcpy_0
0x18001eda8  lea     rax, [rsp+98h+var_60]
0x18001edad  cmp     rsi, rax
0x18001edb0  jz      short loc_18001EDD0
0x18001edb2  xor     ebx, ebx
0x18001edb4  mov     rcx, [rsi]; Block
0x18001edb7  mov     [rsi], rdi
0x18001edba  test    rcx, rcx
0x18001edbd  jz      short loc_18001EDD0
0x18001edbf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001edc4  mov     eax, dword ptr [rsp+98h+pBuffer+4]
0x18001edc8  mov     [r15], eax
0x18001edcb  jmp     loc_18001EF3A
0x18001edd0  mov     eax, dword ptr [rsp+98h+pBuffer+4]
0x18001edd4  mov     [r15], eax
0x18001edd7  test    rbx, rbx
0x18001edda  jz      loc_18001EF3A
0x18001ede0  mov     rcx, rbx; Block
0x18001ede3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ede8  jmp     loc_18001EF3A
0x18001eded  lea     rax, WPP_GLOBAL_Control
0x18001edf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edfb  cmp     rcx, rax
0x18001edfe  jz      short loc_18001EE15
0x18001ee00  mov     edx, 22h ; '"'
0x18001ee05  lea     r8, WPP_253d6767ad5c33bd246c71206321af56_Traceguids
0x18001ee0c  mov     rcx, [rcx+10h]
0x18001ee10  call    WPP_SF_
0x18001ee15  lea     rcx, [rbx+358h]
0x18001ee1c  lea     rdx, [rsp+98h+var_70]
0x18001ee21  call    ?ExportEapMethodId@?$consume_Windows_Internal_Eap_Utility_IEapSchannelUtil@UIEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapMethodId(void)
0x18001ee26  nop
0x18001ee27  mov     dword ptr [rsp+98h+Size], 0
0x18001ee2f  mov     rcx, [rsp+98h+var_70]
0x18001ee34  mov     dword ptr [rsp+98h+pBuffer], 0
0x18001ee3c  xorps   xmm0, xmm0
0x18001ee3f  movdqu  [rsp+98h+pBuffer+8], xmm0
0x18001ee45  mov     rax, [rcx]
0x18001ee48  lea     rdx, [rsp+98h+Size]
0x18001ee4d  mov     rax, [rax+38h]
0x18001ee51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee56  test    eax, eax
0x18001ee58  jns     short loc_18001EE66
0x18001ee5a  lea     rdx, [rsp+98h+pBuffer]
0x18001ee5f  mov     ecx, eax
0x18001ee61  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001ee66  mov     r12d, dword ptr [rsp+98h+Size]
0x18001ee6b  mov     ecx, r12d; unsigned __int64
0x18001ee6e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001ee73  mov     rdi, rax
0x18001ee76  mov     r8d, r12d; Size
0x18001ee79  xor     edx, edx; Val
0x18001ee7b  mov     rcx, rax; void *
0x18001ee7e  call    memset_0
0x18001ee83  mov     rbx, rdi
0x18001ee86  mov     [rsp+98h+var_68], rbx
0x18001ee8b  lea     rcx, [rsp+98h+var_70]
0x18001ee90  call    ?data@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(void)
0x18001ee95  test    r12d, r12d
0x18001ee98  jz      short loc_18001EED2
0x18001ee9a  test    rdi, rdi
0x18001ee9d  jz      short loc_18001EEBB
0x18001ee9f  mov     r8d, r12d; Size
0x18001eea2  mov     rcx, rdi; void *
0x18001eea5  test    rax, rax
0x18001eea8  jz      short loc_18001EEB4
0x18001eeaa  mov     rdx, rax; Src
0x18001eead  call    memcpy_0
0x18001eeb2  jmp     short loc_18001EED2
0x18001eeb4  xor     edx, edx; Val
0x18001eeb6  call    memset_0
0x18001eebb  call    cs:__imp__o__errno
0x18001eec2  nop     dword ptr [rax+rax+00h]
0x18001eec7  mov     dword ptr [rax], 16h
0x18001eecd  call    _invalid_parameter_noinfo
0x18001eed2  lea     rax, [rsp+98h+var_68]
0x18001eed7  cmp     rsi, rax
0x18001eeda  jz      short loc_18001EEEE
0x18001eedc  xor     ebx, ebx
0x18001eede  mov     rcx, [rsi]; Block
0x18001eee1  mov     [rsi], rdi
0x18001eee4  test    rcx, rcx
0x18001eee7  jz      short loc_18001EEEE
0x18001eee9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001eeee  mov     [r15], r12d
0x18001eef1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eef8  lea     rax, WPP_GLOBAL_Control
0x18001eeff  cmp     rcx, rax
0x18001ef02  jz      short loc_18001EF1A
0x18001ef04  mov     edx, 23h ; '#'
0x18001ef09  lea     r8, WPP_253d6767ad5c33bd246c71206321af56_Traceguids
0x18001ef10  mov     rcx, [rcx+10h]
0x18001ef14  call    WPP_SF_
0x18001ef19  nop
0x18001ef1a  test    rbx, rbx
0x18001ef1d  jz      short loc_18001EF28
0x18001ef1f  mov     rcx, rbx; Block
0x18001ef22  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ef27  nop
0x18001ef28  cmp     [rsp+98h+var_70], 0
0x18001ef2e  jz      short loc_18001EF3A
0x18001ef30  lea     rcx, [rsp+98h+var_70]
0x18001ef35  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001ef3a  xor     eax, eax
0x18001ef3c  jmp     short loc_18001EF42
0x18001ef3e  mov     eax, dword ptr [rsp+98h+Size]
0x18001ef42  mov     rcx, [rsp+98h+var_30]
0x18001ef47  xor     rcx, rsp; StackCookie
0x18001ef4a  call    __security_check_cookie
0x18001ef4f  mov     rbx, [rsp+98h+arg_18]
0x18001ef57  add     rsp, 70h
0x18001ef5b  pop     r15
0x18001ef5d  pop     r14
0x18001ef5f  pop     r12
0x18001ef61  pop     rdi
0x18001ef62  pop     rsi
0x18001ef63  retn
```
