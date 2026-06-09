# EapLm::Peer::LegacyEapMethodRuntime::GetIdentityHelper(ObjectHandle const &,uint,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &)

- ea: `0x180013bfc`
- end: `0x180013ecd`
- name: `?GetIdentityHelper@LegacyEapMethodRuntime@Peer@EapLm@@AEAAKAEBVObjectHandle@@IAEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@@Z`
- size: `721`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013980`

## callees

- `0x180005410`
- `0x18000a21c`
- `0x18000a24c`
- `0x18001296c`
- `0x180013bfc`
- `0x18001da14`
- `0x18001e7c0`
- `0x180030f54`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013eaa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013cc6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013cc6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013db7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013db7`

## string_xrefs

- `0x180013eb9`: `ImpersonateLoggedOnUser()`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::LegacyEapMethodRuntime::GetIdentityHelper(
        __int64 a1,
        __int64 a2,
        int a3,
        _QWORD *a4,
        __int64 *a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v11; // rax
  char v12; // r15
  __int64 (__fastcall *v13)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int, __int64, int, _QWORD *, unsigned int *, __int64 *); // r13
  void (__fastcall *v14)(__int64); // r14
  __int64 *v15; // rbx
  int v16; // edi
  __int64 v17; // rbx
  int v18; // eax
  unsigned int v19; // ebx
  EapHost::Peer::Host *v20; // rcx
  DWORD v21; // eax
  DWORD LastError; // eax
  _QWORD v24[9]; // [rsp+70h] [rbp-48h] BYREF
  unsigned int v25; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v26; // [rsp+C8h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
  }
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 304), a2);
  v11 = *(_QWORD *)(a1 + 304);
  v12 = 0;
  v13 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int, __int64, int, _QWORD *, unsigned int *, __int64 *))(v11 + 216);
  v14 = *(void (__fastcall **)(__int64))(v11 + 232);
  v25 = 0;
  v24[0] = 0;
  v26 = 0;
  if ( *(_QWORD *)(a2 + 8) && (a3 & 0x21) == 0 )
  {
    v12 = 1;
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
    }
    if ( !ImpersonateLoggedOnUser(*(HANDLE *)(a2 + 8)) )
    {
      LastError = GetLastError();
      EapHost::EapException::Throw(L"LegacyEapMethodRuntime::GetIdentity()", L"ImpersonateLoggedOnUser()", LastError);
    }
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
  }
  v15 = a5;
  v16 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a5[1]);
  v17 = *v15;
  v18 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a4[1]);
  v19 = v13(*(unsigned __int8 *)(a1 + 16), 0, a3 | 2u, 0, 0, *a4, v18, v17, v16, v24, &v25, &v26);
  if ( !v12 )
    goto LABEL_21;
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
  }
  if ( RevertToSelf() )
    goto LABEL_21;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v21 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids, v21);
LABEL_21:
    v20 = WPP_GLOBAL_Control;
  }
  if ( !v19 )
  {
    if ( v20 != (EapHost::Peer::Host *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v20 + 2), 25, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
    BasicSimpleString<wchar_t>::Assign(a7, v26);
    v14(v26);
    if ( v24[0] && v25 )
    {
      TempBuffer<0>::Assign(a6, v25);
      v14(v24[0]);
    }
  }
  return v19;
}

```

## disassembly

```asm
0x180013bfc  mov     [rsp+arg_10], rbx
0x180013c01  push    rbp
0x180013c02  push    rsi
0x180013c03  push    rdi
0x180013c04  push    r12
0x180013c06  push    r13
0x180013c08  push    r14
0x180013c0a  push    r15
0x180013c0c  sub     rsp, 80h
0x180013c13  mov     r12, r9
0x180013c16  mov     ebp, r8d
0x180013c19  mov     rbx, rdx
0x180013c1c  mov     rsi, rcx
0x180013c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c26  lea     rax, WPP_GLOBAL_Control
0x180013c2d  cmp     rcx, rax
0x180013c30  jz      short loc_180013C4D
0x180013c32  test    byte ptr [rcx+1Ch], 4
0x180013c36  jz      short loc_180013C4D
0x180013c38  mov     rcx, [rcx+10h]
0x180013c3c  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013c43  mov     edx, 14h
0x180013c48  call    WPP_SF_
0x180013c4d  mov     rcx, [rsi+130h]; this
0x180013c54  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x180013c59  mov     rax, [rsi+130h]
0x180013c60  xor     edi, edi
0x180013c62  mov     r15b, dil
0x180013c65  mov     r13, [rax+0D8h]
0x180013c6c  mov     r14, [rax+0E8h]
0x180013c73  mov     [rsp+0B8h+arg_0], edi
0x180013c7a  mov     [rsp+0B8h+var_48], rdi
0x180013c7f  mov     [rsp+0B8h+arg_8], rdi
0x180013c87  cmp     [rbx+8], rdi
0x180013c8b  jz      short loc_180013CDA
0x180013c8d  test    bpl, 21h
0x180013c91  jnz     short loc_180013CDA
0x180013c93  mov     r15b, 1
0x180013c96  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c9d  lea     rax, WPP_GLOBAL_Control
0x180013ca4  cmp     rcx, rax
0x180013ca7  jz      short loc_180013CC2
0x180013ca9  test    byte ptr [rcx+1Ch], 4
0x180013cad  jz      short loc_180013CC2
0x180013caf  mov     rcx, [rcx+10h]
0x180013cb3  lea     edx, [rdi+15h]
0x180013cb6  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013cbd  call    WPP_SF_
0x180013cc2  mov     rcx, [rbx+8]; hToken
0x180013cc6  call    cs:__imp_ImpersonateLoggedOnUser
0x180013ccd  nop     dword ptr [rax+rax+00h]
0x180013cd2  test    eax, eax
0x180013cd4  jz      loc_180013EAA
0x180013cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ce1  lea     rax, WPP_GLOBAL_Control
0x180013ce8  cmp     rcx, rax
0x180013ceb  jz      short loc_180013D08
0x180013ced  test    byte ptr [rcx+1Ch], 4
0x180013cf1  jz      short loc_180013D08
0x180013cf3  mov     rcx, [rcx+10h]
0x180013cf7  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013cfe  mov     edx, 16h
0x180013d03  call    WPP_SF_
0x180013d08  mov     rbx, [rsp+0B8h+arg_20]
0x180013d10  mov     rcx, [rbx+8]
0x180013d14  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180013d19  mov     rcx, [r12+8]
0x180013d1e  mov     edi, eax
0x180013d20  mov     rbx, [rbx]
0x180013d23  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180013d28  movzx   ecx, byte ptr [rsi+10h]
0x180013d2c  lea     rdx, [rsp+0B8h+arg_8]
0x180013d34  mov     [rsp+0B8h+var_60], rdx
0x180013d39  or      ebp, 2
0x180013d3c  lea     rdx, [rsp+0B8h+arg_0]
0x180013d44  xor     r9d, r9d
0x180013d47  mov     [rsp+0B8h+var_68], rdx
0x180013d4c  mov     r8d, ebp
0x180013d4f  lea     rdx, [rsp+0B8h+var_48]
0x180013d54  mov     [rsp+0B8h+var_70], rdx
0x180013d59  mov     rdx, [r12]
0x180013d5d  mov     [rsp+0B8h+var_78], edi
0x180013d61  mov     [rsp+0B8h+var_80], rbx
0x180013d66  mov     [rsp+0B8h+var_88], eax
0x180013d6a  mov     rax, r13
0x180013d6d  mov     [rsp+0B8h+var_90], rdx
0x180013d72  xor     edx, edx
0x180013d74  mov     [rsp+0B8h+var_98], 0
0x180013d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d82  mov     ebx, eax
0x180013d84  test    r15b, r15b
0x180013d87  jz      short loc_180013E06
0x180013d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d90  lea     rdi, WPP_GLOBAL_Control
0x180013d97  cmp     rcx, rdi
0x180013d9a  jz      short loc_180013DB7
0x180013d9c  test    byte ptr [rcx+1Ch], 4
0x180013da0  jz      short loc_180013DB7
0x180013da2  mov     rcx, [rcx+10h]
0x180013da6  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013dad  mov     edx, 17h
0x180013db2  call    WPP_SF_
0x180013db7  call    cs:__imp_RevertToSelf
0x180013dbe  nop     dword ptr [rax+rax+00h]
0x180013dc3  test    eax, eax
0x180013dc5  jnz     short loc_180013E0D
0x180013dc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180013dce  cmp     rcx, rdi
0x180013dd1  jz      short loc_180013E14
0x180013dd3  test    byte ptr [rcx+1Ch], 1
0x180013dd7  jz      short loc_180013E14
0x180013dd9  call    cs:__imp_GetLastError
0x180013de0  nop     dword ptr [rax+rax+00h]
0x180013de5  mov     rcx, cs:WPP_GLOBAL_Control
0x180013dec  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013df3  mov     edx, 18h
0x180013df8  mov     r9d, eax
0x180013dfb  mov     rcx, [rcx+10h]
0x180013dff  call    WPP_SF_d
0x180013e04  jmp     short loc_180013E0D
0x180013e06  lea     rdi, WPP_GLOBAL_Control
0x180013e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e14  test    ebx, ebx
0x180013e16  jnz     short loc_180013E8C
0x180013e18  cmp     rcx, rdi
0x180013e1b  jz      short loc_180013E36
0x180013e1d  test    byte ptr [rcx+1Ch], 4
0x180013e21  jz      short loc_180013E36
0x180013e23  mov     rcx, [rcx+10h]
0x180013e27  lea     edx, [rbx+19h]
0x180013e2a  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013e31  call    WPP_SF_
0x180013e36  mov     rdx, [rsp+0B8h+arg_8]
0x180013e3e  mov     rcx, [rsp+0B8h+arg_30]
0x180013e46  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180013e4b  mov     rcx, [rsp+0B8h+arg_8]
0x180013e53  mov     rax, r14
0x180013e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e5b  mov     r8, [rsp+0B8h+var_48]
0x180013e60  test    r8, r8
0x180013e63  jz      short loc_180013E8C
0x180013e65  mov     ecx, [rsp+0B8h+arg_0]
0x180013e6c  test    ecx, ecx
0x180013e6e  jz      short loc_180013E8C
0x180013e70  mov     edx, ecx
0x180013e72  mov     rcx, [rsp+0B8h+arg_28]
0x180013e7a  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180013e7f  mov     rcx, [rsp+0B8h+var_48]
0x180013e84  mov     rax, r14
0x180013e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e8c  mov     eax, ebx
0x180013e8e  mov     rbx, [rsp+0B8h+arg_10]
0x180013e96  add     rsp, 80h
0x180013e9d  pop     r15
0x180013e9f  pop     r14
0x180013ea1  pop     r13
0x180013ea3  pop     r12
0x180013ea5  pop     rdi
0x180013ea6  pop     rsi
0x180013ea7  pop     rbp
0x180013ea8  retn
0x180013eaa  call    cs:__imp_GetLastError
0x180013eb1  nop     dword ptr [rax+rax+00h]
0x180013eb6  mov     r8d, eax; int
0x180013eb9  lea     rdx, aImpersonatelog; "ImpersonateLoggedOnUser()"
0x180013ec0  lea     rcx, aLegacyeapmetho; "LegacyEapMethodRuntime::GetIdentity()"
0x180013ec7  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
