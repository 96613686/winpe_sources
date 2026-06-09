# Microsoft::Basix::HTTP::SSPIAuthenticationHandler::SSPIAuthenticationHandler(std::function<void (Microsoft::Basix::HTTP::CredentialsCompletion &&)>,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>> const &)

- ea: `0x1802e0dfc`
- end: `0x1802e1026`
- name: `??0SSPIAuthenticationHandler@HTTP@Basix@Microsoft@@QEAA@V?$function@$$A6AX$$QEAVCredentialsCompletion@HTTP@Basix@Microsoft@@@Z@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@5@@Z`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1802fe854`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180037690`
- `0x1801418b8`
- `0x1802e0bac`
- `0x1802e0dfc`
- `0x1802e14b8`
- `0x1802eb658`
- `0x1802ff690`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## import_xrefs

- `Secur32!InitSecurityInterfaceW` at `0x1802e0fc7`
- `Secur32!InitSecurityInterfaceW` at `0x1802e0fc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Microsoft::Basix::HTTP::SSPIAuthenticationHandler::SSPIAuthenticationHandler(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  __int64 (__fastcall ***v10)(_QWORD, _BYTE *); // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  char v17; // [rsp+20h] [rbp-A9h]
  _OWORD v18[2]; // [rsp+30h] [rbp-99h] BYREF
  __int64 v19; // [rsp+50h] [rbp-79h]
  _BYTE v20[56]; // [rsp+58h] [rbp-71h] BYREF
  __int64 v21; // [rsp+90h] [rbp-39h]
  _BYTE v22[32]; // [rsp+98h] [rbp-31h] BYREF
  __int64 v23; // [rsp+B8h] [rbp-11h]

  v19 = a1;
  v23 = a2;
  if ( a6 )
  {
    *(_QWORD *)(a1 + 8) = &Microsoft::Basix::HTTP::SSPIAuthenticationHandler::`vbtable';
    *(_QWORD *)(a1 + 280) = 0;
    *(_QWORD *)(a1 + 288) = 0;
    *(_QWORD *)(a1 + 272) = &Microsoft::Basix::SharedFromThisVirtualBase::`vftable';
  }
  v21 = 0;
  v10 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a2 + 56);
  if ( v10 )
    v21 = (**v10)(v10, v20);
  Microsoft::Basix::HTTP::IAuthenticationHandler::IAuthenticationHandler(a1, v20, 0);
  *(_QWORD *)a1 = &Microsoft::Basix::HTTP::SSPIAuthenticationHandler::`vftable'{for `Microsoft::Basix::HTTP::IAuthenticationHandler'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 4LL) + a1 + 8) = &Microsoft::Basix::HTTP::SSPIAuthenticationHandler::`vftable'{for `Microsoft::Basix::SharedFromThis'};
  *(_OWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 15;
  *(_BYTE *)(a1 + 80) = 0;
  v11 = Microsoft::Basix::ToU16String(v20, a3);
  memset(v18, 0, sizeof(v18));
  std::string::_Construct<1,char const *>(v18, "HTTP/", 5);
  v12 = Microsoft::Basix::ToU16String(v22, v18);
  LOBYTE(v13) = v17;
  std::basic_string<char16_t>::basic_string<char16_t>(a1 + 112, v13, v12, v11);
  std::basic_string<short>::_Tidy_deallocate(v22);
  std::string::_Tidy_deallocate(v18);
  std::basic_string<short>::_Tidy_deallocate(v20);
  *(_OWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 7;
  *(_WORD *)(a1 + 144) = 0;
  Microsoft::Basix::Containers::FlexIBuffer::FlexIBuffer((Microsoft::Basix::Containers::FlexIBuffer *)(a1 + 176));
  *(_BYTE *)(a1 + 224) = 1;
  *(_OWORD *)(a1 + 256) = 0;
  *(_OWORD *)(a1 + 240) = 0;
  if ( !qword_18053DF98 )
    qword_18053DF98 = (__int64)InitSecurityInterfaceW();
  Microsoft::Basix::HTTP::SSPIAuthenticationHandler::Continue(a1, a4, a5);
  v15 = *(_QWORD *)(a2 + 56);
  if ( v15 )
  {
    LOBYTE(v14) = v15 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 32LL))(v15, v14);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1802e0dfc  push    rbp
0x1802e0dfe  push    rbx
0x1802e0dff  push    rsi
0x1802e0e00  push    rdi
0x1802e0e01  push    r12
0x1802e0e03  push    r13
0x1802e0e05  push    r14
0x1802e0e07  push    r15
0x1802e0e09  lea     rbp, [rsp-0Fh]
0x1802e0e0e  mov     eax, 0D8h
0x1802e0e13  call    _alloca_probe
0x1802e0e18  sub     rsp, rax
0x1802e0e1b  mov     rax, cs:__security_cookie
0x1802e0e22  xor     rax, rsp
0x1802e0e25  mov     [rbp+47h+var_50], rax
0x1802e0e29  mov     r15, r9
0x1802e0e2c  mov     rbx, r8
0x1802e0e2f  mov     rsi, rdx
0x1802e0e32  mov     rdi, rcx
0x1802e0e35  mov     [rbp+47h+var_C0], rcx
0x1802e0e39  mov     [rbp+47h+var_58], rdx
0x1802e0e3d  mov     r12, [rbp+47h+arg_20]
0x1802e0e41  xor     r13d, r13d
0x1802e0e44  mov     r14d, r13d
0x1802e0e47  mov     [rsp+110h+var_EC], r13d
0x1802e0e4c  cmp     [rbp+47h+arg_28], r13d
0x1802e0e50  jz      short loc_1802E0E82
0x1802e0e52  lea     rax, ??_8SSPIAuthenticationHandler@HTTP@Basix@Microsoft@@7B@; const Microsoft::Basix::HTTP::SSPIAuthenticationHandler::`vbtable'
0x1802e0e59  mov     [rcx+8], rax
0x1802e0e5d  mov     [rcx+118h], r13
0x1802e0e64  mov     [rcx+120h], r13
0x1802e0e6b  lea     rax, ??_7SharedFromThisVirtualBase@Basix@Microsoft@@6B@; const Microsoft::Basix::SharedFromThisVirtualBase::`vftable'
0x1802e0e72  mov     [rcx+110h], rax
0x1802e0e79  lea     r14d, [r13+1]
0x1802e0e7d  mov     [rsp+110h+var_EC], r14d
0x1802e0e82  lea     rax, [rbp+47h+var_B8]
0x1802e0e86  mov     [rsp+110h+var_E8], rax
0x1802e0e8b  mov     [rbp+47h+var_80], r13
0x1802e0e8f  mov     rcx, [rdx+38h]
0x1802e0e93  test    rcx, rcx
0x1802e0e96  jz      short loc_1802E0EAC
0x1802e0e98  mov     rax, [rcx]
0x1802e0e9b  lea     rdx, [rbp+47h+var_B8]
0x1802e0e9f  mov     rax, [rax]
0x1802e0ea2  call    cs:__guard_dispatch_icall_fptr
0x1802e0ea8  mov     [rbp+47h+var_80], rax
0x1802e0eac  xor     r8d, r8d
0x1802e0eaf  lea     rdx, [rbp+47h+var_B8]
0x1802e0eb3  mov     rcx, rdi
0x1802e0eb6  call    ??0IAuthenticationHandler@HTTP@Basix@Microsoft@@QEAA@V?$function@$$A6AX$$QEAVCredentialsCompletion@HTTP@Basix@Microsoft@@@Z@std@@@Z; Microsoft::Basix::HTTP::IAuthenticationHandler::IAuthenticationHandler(std::function<void (Microsoft::Basix::HTTP::CredentialsCompletion &&)>)
0x1802e0ebb  nop
0x1802e0ebc  lea     rax, ??_7SSPIAuthenticationHandler@HTTP@Basix@Microsoft@@6BIAuthenticationHandler@123@@; const Microsoft::Basix::HTTP::SSPIAuthenticationHandler::`vftable'{for `Microsoft::Basix::HTTP::IAuthenticationHandler'}
0x1802e0ec3  mov     [rdi], rax
0x1802e0ec6  mov     rax, [rdi+8]
0x1802e0eca  movsxd  rcx, dword ptr [rax+4]
0x1802e0ece  lea     rax, ??_7SSPIAuthenticationHandler@HTTP@Basix@Microsoft@@6BSharedFromThis@23@@; const Microsoft::Basix::HTTP::SSPIAuthenticationHandler::`vftable'{for `Microsoft::Basix::SharedFromThis'}
0x1802e0ed5  mov     [rcx+rdi+8], rax
0x1802e0eda  xorps   xmm0, xmm0
0x1802e0edd  movups  xmmword ptr [rdi+50h], xmm0
0x1802e0ee1  mov     [rdi+60h], r13
0x1802e0ee5  mov     qword ptr [rdi+68h], 0Fh
0x1802e0eed  mov     [rdi+50h], r13b
0x1802e0ef1  mov     rdx, rbx
0x1802e0ef4  lea     rcx, [rbp+47h+var_B8]
0x1802e0ef8  call    ?ToU16String@Basix@Microsoft@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Microsoft::Basix::ToU16String(std::string const &)
0x1802e0efd  mov     rbx, rax
0x1802e0f00  xorps   xmm0, xmm0
0x1802e0f03  movups  [rsp+110h+var_E0], xmm0
0x1802e0f08  xorps   xmm1, xmm1
0x1802e0f0b  movdqu  [rsp+110h+var_D0], xmm1
0x1802e0f11  mov     r8d, 5
0x1802e0f17  lea     rdx, aHttp_1; "HTTP/"
0x1802e0f1e  lea     rcx, [rsp+110h+var_E0]
0x1802e0f23  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1802e0f28  nop
0x1802e0f29  lea     rdx, [rsp+110h+var_E0]
0x1802e0f2e  lea     rcx, [rbp+47h+var_78]
0x1802e0f32  call    ?ToU16String@Basix@Microsoft@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Microsoft::Basix::ToU16String(std::string const &)
0x1802e0f37  nop
0x1802e0f38  lea     rcx, [rdi+70h]
0x1802e0f3c  mov     r9, rbx
0x1802e0f3f  mov     r8, rax
0x1802e0f42  mov     dl, [rsp+110h+var_F0]
0x1802e0f46  call    ??0?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::basic_string<char16_t>::basic_string<char16_t>(std::_String_constructor_concat_tag,std::basic_string<char16_t> &,std::basic_string<char16_t> &)
0x1802e0f4b  or      r14d, 2
0x1802e0f4f  mov     [rsp+110h+var_EC], r14d
0x1802e0f54  lea     rcx, [rbp+47h+var_78]
0x1802e0f58  call    ?_Tidy_deallocate@?$basic_string@FU?$char_traits@F@std@@V?$allocator@F@2@@std@@AEAAXXZ; std::basic_string<short>::_Tidy_deallocate(void)
0x1802e0f5d  nop
0x1802e0f5e  lea     rcx, [rsp+110h+var_E0]
0x1802e0f63  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1802e0f68  nop
0x1802e0f69  lea     rcx, [rbp+47h+var_B8]
0x1802e0f6d  call    ?_Tidy_deallocate@?$basic_string@FU?$char_traits@F@std@@V?$allocator@F@2@@std@@AEAAXXZ; std::basic_string<short>::_Tidy_deallocate(void)
0x1802e0f72  xorps   xmm0, xmm0
0x1802e0f75  movups  xmmword ptr [rdi+90h], xmm0
0x1802e0f7c  mov     [rdi+0A0h], r13
0x1802e0f83  mov     qword ptr [rdi+0A8h], 7
0x1802e0f8e  mov     [rdi+90h], r13w
0x1802e0f96  lea     rcx, [rdi+0B0h]; this
0x1802e0f9d  call    ??0FlexIBuffer@Containers@Basix@Microsoft@@QEAA@XZ; Microsoft::Basix::Containers::FlexIBuffer::FlexIBuffer(void)
0x1802e0fa2  nop
0x1802e0fa3  mov     byte ptr [rdi+0E0h], 1
0x1802e0faa  xorps   xmm0, xmm0
0x1802e0fad  movups  xmmword ptr [rdi+100h], xmm0
0x1802e0fb4  xorps   xmm1, xmm1
0x1802e0fb7  movups  xmmword ptr [rdi+0F0h], xmm1
0x1802e0fbe  cmp     cs:qword_18053DF98, r13
0x1802e0fc5  jnz     short loc_1802E0FD4
0x1802e0fc7  call    cs:__imp_InitSecurityInterfaceW
0x1802e0fcd  mov     cs:qword_18053DF98, rax
0x1802e0fd4  mov     r8, r12
0x1802e0fd7  mov     rdx, r15
0x1802e0fda  mov     rcx, rdi
0x1802e0fdd  call    ?Continue@SSPIAuthenticationHandler@HTTP@Basix@Microsoft@@QEAA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@6@@Z; Microsoft::Basix::HTTP::SSPIAuthenticationHandler::Continue(std::string const &,std::map<std::string,std::string> const &)
0x1802e0fe2  nop
0x1802e0fe3  mov     rcx, [rsi+38h]
0x1802e0fe7  test    rcx, rcx
0x1802e0fea  jz      short loc_1802E1003
0x1802e0fec  cmp     rcx, rsi
0x1802e0fef  setnz   dl
0x1802e0ff2  mov     r8, [rcx]
0x1802e0ff5  mov     rax, [r8+20h]
0x1802e0ff9  call    cs:__guard_dispatch_icall_fptr
0x1802e0fff  mov     [rsi+38h], r13
0x1802e1003  mov     rax, rdi
0x1802e1006  mov     rcx, [rbp+47h+var_50]
0x1802e100a  xor     rcx, rsp; StackCookie
0x1802e100d  call    __security_check_cookie
0x1802e1012  add     rsp, 0D8h
0x1802e1019  pop     r15
0x1802e101b  pop     r14
0x1802e101d  pop     r13
0x1802e101f  pop     r12
0x1802e1021  pop     rdi
0x1802e1022  pop     rsi
0x1802e1023  pop     rbx
0x1802e1024  pop     rbp
0x1802e1025  retn
```
