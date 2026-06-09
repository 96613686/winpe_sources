# RasEapExportMethodId_PopulateSessionInfo(_EAPTLS_CONTROL_BLOCK *,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &,ulong &)

- ea: `0x18001d1d8`
- end: `0x18001d44f`
- name: `?RasEapExportMethodId_PopulateSessionInfo@@YAJPEAU_EAPTLS_CONTROL_BLOCK@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@AEAK@Z`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002c2fc`

## callees

- `0x1800075b0`
- `0x18001d1d8`
- `0x18001d458`
- `0x18002689c`
- `0x18002d260`
- `0x180035680`
- `0x180035a50`
- `0x180035b58`
- `0x1800361ba`
- `0x18003623c`
- `0x180036254`
- `0x18003cfdc`
- `0x180058980`
- `0x18007c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d278`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d3ab`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d278`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d3ab`
- `SspiCli!QueryContextAttributesW` at `0x18001d231`
- `SspiCli!QueryContextAttributesW` at `0x18001d231`

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
  __int64 v11; // rcx
  void *v12; // rbx
  void *v13; // rcx
  int v14; // eax
  unsigned int v15; // r12d
  void *v16; // rdi
  void *v17; // rbx
  const void *v18; // rax
  __int64 v19; // rcx
  void *v20; // rcx
  size_t Size; // [rsp+20h] [rbp-78h] BYREF
  __int64 v23; // [rsp+28h] [rbp-70h] BYREF
  void *v24; // [rsp+30h] [rbp-68h] BYREF
  char v25; // [rsp+38h] [rbp-60h] BYREF
  _OWORD pBuffer[2]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v27; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( *(_BYTE *)(a1 + 849) )
  {
    memset(pBuffer, 0, sizeof(pBuffer));
    v27 = 0;
    ContextAttributesW = QueryContextAttributesW((PCtxtHandle)(a1 + 648), 0x5Du, pBuffer);
    if ( ContextAttributesW < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, v7, v8, (const char *)(unsigned int)ContextAttributesW, Size);
    v9 = DWORD1(pBuffer[0]);
    v10 = operator new[](DWORD1(pBuffer[0]));
    memset_0(v10, 0, v9);
    v12 = v10;
    if ( DWORD1(pBuffer[0]) )
    {
      if ( v10 )
      {
        memcpy_0(v10, (char *)pBuffer + 8, DWORD1(pBuffer[0]));
      }
      else
      {
        *(_DWORD *)_o__errno(v11) = 22;
        invalid_parameter_noinfo();
      }
    }
    if ( a2 == (void **)&v25 || (v12 = 0, v13 = *a2, *a2 = v10, !v13) )
    {
      *a3 = DWORD1(pBuffer[0]);
      if ( v12 )
        operator delete(v12);
    }
    else
    {
      operator delete(v13);
      *a3 = DWORD1(pBuffer[0]);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_a12a621288f636b53cf7c22596c0e71c_Traceguids);
  winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapMethodId(
    a1 + 856,
    &v23);
  LODWORD(Size) = 0;
  LODWORD(pBuffer[0]) = 0;
  *(_OWORD *)((char *)pBuffer + 8) = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, size_t *))(*(_QWORD *)v23 + 56LL))(v23, &Size);
  if ( v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, pBuffer);
  v15 = Size;
  v16 = operator new[]((unsigned int)Size);
  memset_0(v16, 0, v15);
  v17 = v16;
  v24 = v16;
  v18 = (const void *)winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(&v23);
  if ( v15 )
  {
    if ( v16 )
    {
      if ( v18 )
      {
        memcpy_0(v16, v18, v15);
        goto LABEL_23;
      }
      memset_0(v16, 0, v15);
    }
    *(_DWORD *)_o__errno(v19) = 22;
    invalid_parameter_noinfo();
  }
LABEL_23:
  if ( a2 != &v24 )
  {
    v17 = 0;
    v20 = *a2;
    *a2 = v16;
    if ( v20 )
      operator delete(v20);
  }
  *a3 = v15;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_a12a621288f636b53cf7c22596c0e71c_Traceguids);
  if ( v17 )
    operator delete(v17);
  if ( v23 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v23);
  return 0;
}

```

## disassembly

```asm
0x18001d1d8  mov     [rsp+arg_18], rbx
0x18001d1dd  push    rsi
0x18001d1de  push    rdi
0x18001d1df  push    r12
0x18001d1e1  push    r14
0x18001d1e3  push    r15
0x18001d1e5  sub     rsp, 70h
0x18001d1e9  mov     rax, cs:__security_cookie
0x18001d1f0  xor     rax, rsp
0x18001d1f3  mov     [rsp+98h+var_30], rax
0x18001d1f8  mov     r15, r8
0x18001d1fb  mov     rsi, rdx
0x18001d1fe  mov     rbx, rcx
0x18001d201  cmp     byte ptr [rcx+351h], 0
0x18001d208  jz      loc_18001D2DD
0x18001d20e  xorps   xmm0, xmm0
0x18001d211  xor     eax, eax
0x18001d213  movups  [rsp+98h+pBuffer], xmm0
0x18001d218  movups  [rsp+98h+var_48], xmm0
0x18001d21d  mov     [rsp+98h+var_38], rax
0x18001d222  add     rcx, 288h; phContext
0x18001d229  lea     r8, [rsp+98h+pBuffer]; pBuffer
0x18001d22e  lea     edx, [rax+5Dh]; ulAttribute
0x18001d231  call    cs:__imp_QueryContextAttributesW
0x18001d237  mov     rcx, [rsp+98h]; this
0x18001d23f  test    eax, eax
0x18001d241  jns     short loc_18001D24B
0x18001d243  mov     r9d, eax; char *
0x18001d246  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18001d24b  mov     ebx, dword ptr [rsp+98h+pBuffer+4]
0x18001d24f  mov     ecx, ebx; unsigned __int64
0x18001d251  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001d256  mov     rdi, rax
0x18001d259  mov     r8d, ebx; Size
0x18001d25c  xor     edx, edx; Val
0x18001d25e  mov     rcx, rax; void *
0x18001d261  call    memset_0
0x18001d266  mov     rbx, rdi
0x18001d269  mov     r8d, dword ptr [rsp+98h+pBuffer+4]; Size
0x18001d26e  test    r8, r8
0x18001d271  jz      short loc_18001D298
0x18001d273  test    rdi, rdi
0x18001d276  jnz     short loc_18001D28B
0x18001d278  call    cs:__imp__o__errno
0x18001d27e  mov     dword ptr [rax], 16h
0x18001d284  call    _invalid_parameter_noinfo
0x18001d289  jmp     short loc_18001D298
0x18001d28b  lea     rdx, [rsp+98h+pBuffer+8]; Src
0x18001d290  mov     rcx, rdi; void *
0x18001d293  call    memcpy_0
0x18001d298  lea     rax, [rsp+98h+var_60]
0x18001d29d  cmp     rsi, rax
0x18001d2a0  jz      short loc_18001D2C0
0x18001d2a2  xor     ebx, ebx
0x18001d2a4  mov     rcx, [rsi]; Block
0x18001d2a7  mov     [rsi], rdi
0x18001d2aa  test    rcx, rcx
0x18001d2ad  jz      short loc_18001D2C0
0x18001d2af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d2b4  mov     eax, dword ptr [rsp+98h+pBuffer+4]
0x18001d2b8  mov     [r15], eax
0x18001d2bb  jmp     loc_18001D424
0x18001d2c0  mov     eax, dword ptr [rsp+98h+pBuffer+4]
0x18001d2c4  mov     [r15], eax
0x18001d2c7  test    rbx, rbx
0x18001d2ca  jz      loc_18001D424
0x18001d2d0  mov     rcx, rbx; Block
0x18001d2d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d2d8  jmp     loc_18001D424
0x18001d2dd  lea     rax, WPP_GLOBAL_Control
0x18001d2e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2eb  cmp     rcx, rax
0x18001d2ee  jz      short loc_18001D305
0x18001d2f0  mov     edx, 22h ; '"'
0x18001d2f5  lea     r8, WPP_a12a621288f636b53cf7c22596c0e71c_Traceguids
0x18001d2fc  mov     rcx, [rcx+10h]
0x18001d300  call    WPP_SF_
0x18001d305  lea     rcx, [rbx+358h]
0x18001d30c  lea     rdx, [rsp+98h+var_70]
0x18001d311  call    ?ExportEapMethodId@?$consume_Windows_Internal_Eap_Utility_IEapSchannelUtil@UIEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapMethodId(void)
0x18001d316  nop
0x18001d317  mov     dword ptr [rsp+98h+Size], 0
0x18001d31f  mov     rcx, [rsp+98h+var_70]
0x18001d324  mov     dword ptr [rsp+98h+pBuffer], 0
0x18001d32c  xorps   xmm0, xmm0
0x18001d32f  movdqu  [rsp+98h+pBuffer+8], xmm0
0x18001d335  mov     rax, [rcx]
0x18001d338  lea     rdx, [rsp+98h+Size]
0x18001d33d  mov     rax, [rax+38h]
0x18001d341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d346  test    eax, eax
0x18001d348  jns     short loc_18001D356
0x18001d34a  lea     rdx, [rsp+98h+pBuffer]
0x18001d34f  mov     ecx, eax
0x18001d351  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001d356  mov     r12d, dword ptr [rsp+98h+Size]
0x18001d35b  mov     ecx, r12d; unsigned __int64
0x18001d35e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001d363  mov     rdi, rax
0x18001d366  mov     r8d, r12d; Size
0x18001d369  xor     edx, edx; Val
0x18001d36b  mov     rcx, rax; void *
0x18001d36e  call    memset_0
0x18001d373  mov     rbx, rdi
0x18001d376  mov     [rsp+98h+var_68], rbx
0x18001d37b  lea     rcx, [rsp+98h+var_70]
0x18001d380  call    ?data@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(void)
0x18001d385  test    r12d, r12d
0x18001d388  jz      short loc_18001D3BC
0x18001d38a  test    rdi, rdi
0x18001d38d  jz      short loc_18001D3AB
0x18001d38f  mov     r8d, r12d; Size
0x18001d392  mov     rcx, rdi; void *
0x18001d395  test    rax, rax
0x18001d398  jz      short loc_18001D3A4
0x18001d39a  mov     rdx, rax; Src
0x18001d39d  call    memcpy_0
0x18001d3a2  jmp     short loc_18001D3BC
0x18001d3a4  xor     edx, edx; Val
0x18001d3a6  call    memset_0
0x18001d3ab  call    cs:__imp__o__errno
0x18001d3b1  mov     dword ptr [rax], 16h
0x18001d3b7  call    _invalid_parameter_noinfo
0x18001d3bc  lea     rax, [rsp+98h+var_68]
0x18001d3c1  cmp     rsi, rax
0x18001d3c4  jz      short loc_18001D3D8
0x18001d3c6  xor     ebx, ebx
0x18001d3c8  mov     rcx, [rsi]; Block
0x18001d3cb  mov     [rsi], rdi
0x18001d3ce  test    rcx, rcx
0x18001d3d1  jz      short loc_18001D3D8
0x18001d3d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d3d8  mov     [r15], r12d
0x18001d3db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3e2  lea     rax, WPP_GLOBAL_Control
0x18001d3e9  cmp     rcx, rax
0x18001d3ec  jz      short loc_18001D404
0x18001d3ee  mov     edx, 23h ; '#'
0x18001d3f3  lea     r8, WPP_a12a621288f636b53cf7c22596c0e71c_Traceguids
0x18001d3fa  mov     rcx, [rcx+10h]
0x18001d3fe  call    WPP_SF_
0x18001d403  nop
0x18001d404  test    rbx, rbx
0x18001d407  jz      short loc_18001D412
0x18001d409  mov     rcx, rbx; Block
0x18001d40c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d411  nop
0x18001d412  cmp     [rsp+98h+var_70], 0
0x18001d418  jz      short loc_18001D424
0x18001d41a  lea     rcx, [rsp+98h+var_70]
0x18001d41f  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001d424  xor     eax, eax
0x18001d426  jmp     short loc_18001D42C
0x18001d428  mov     eax, dword ptr [rsp+98h+Size]
0x18001d42c  mov     rcx, [rsp+98h+var_30]
0x18001d431  xor     rcx, rsp; StackCookie
0x18001d434  call    __security_check_cookie
0x18001d439  mov     rbx, [rsp+98h+arg_18]
0x18001d441  add     rsp, 70h
0x18001d445  pop     r15
0x18001d447  pop     r14
0x18001d449  pop     r12
0x18001d44b  pop     rdi
0x18001d44c  pop     rsi
0x18001d44d  retn
```
