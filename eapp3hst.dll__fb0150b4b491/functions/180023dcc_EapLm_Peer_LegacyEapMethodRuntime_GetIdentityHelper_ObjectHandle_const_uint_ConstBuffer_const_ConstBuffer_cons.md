# EapLm::Peer::LegacyEapMethodRuntime::GetIdentityHelper(ObjectHandle const &,uint,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &)

- ea: `0x180023dcc`
- end: `0x180024082`
- name: `?GetIdentityHelper@LegacyEapMethodRuntime@Peer@EapLm@@AEAAKAEBVObjectHandle@@IAEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(__int64, __int64, int, _QWORD *, __int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023b40`

## callees

- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x1800126f8`
- `0x180013d10`
- `0x180015534`
- `0x180023dcc`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023fb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023fb8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023f9c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023f9c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180023e98`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180023e98`

## string_xrefs

- `0x180023eab`: `ImpersonateLoggedOnUser()`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  DWORD LastError; // eax
  __int64 *v16; // rbx
  int v17; // edi
  __int64 v18; // rbx
  int v19; // eax
  unsigned int v20; // ebx
  _QWORD *v21; // rcx
  DWORD v22; // eax
  _QWORD v24[9]; // [rsp+70h] [rbp-48h] BYREF
  unsigned int v25; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v26; // [rsp+C8h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 304), 0);
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
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
    if ( !ImpersonateLoggedOnUser(*(HANDLE *)(a2 + 8)) )
    {
      LastError = GetLastError();
      EapHost::EapException::Throw(L"LegacyEapMethodRuntime::GetIdentity()", L"ImpersonateLoggedOnUser()", LastError);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
  v16 = a5;
  v17 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a5[1]);
  v18 = *v16;
  v19 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a4[1]);
  v20 = v13(*(unsigned __int8 *)(a1 + 16), 0, a3 | 2u, 0, 0, *a4, v19, v18, v17, v24, &v25, &v26);
  if ( !v12 )
    goto LABEL_22;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
  if ( RevertToSelf() )
    goto LABEL_22;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v22 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids, v22);
LABEL_22:
    v21 = WPP_GLOBAL_Control;
  }
  if ( !v20 )
  {
    if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 )
      WPP_SF_(v21[2], 25, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
    BasicSimpleString<wchar_t>::Assign(a7, v26);
    v14(v26);
    if ( v24[0] && v25 )
    {
      TempBuffer<0>::Assign(a6, v25);
      v14(v24[0]);
    }
  }
  return v20;
}

```

## disassembly

```asm
0x180023dcc  mov     [rsp+arg_10], rbx
0x180023dd1  push    rbp
0x180023dd2  push    rsi
0x180023dd3  push    rdi
0x180023dd4  push    r12
0x180023dd6  push    r13
0x180023dd8  push    r14
0x180023dda  push    r15
0x180023ddc  sub     rsp, 80h
0x180023de3  mov     r12, r9
0x180023de6  mov     ebp, r8d
0x180023de9  mov     rbx, rdx
0x180023dec  mov     rsi, rcx
0x180023def  mov     rcx, cs:WPP_GLOBAL_Control
0x180023df6  lea     rax, WPP_GLOBAL_Control
0x180023dfd  cmp     rcx, rax
0x180023e00  jz      short loc_180023E1D
0x180023e02  test    byte ptr [rcx+1Ch], 4
0x180023e06  jz      short loc_180023E1D
0x180023e08  mov     rcx, [rcx+10h]
0x180023e0c  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180023e13  mov     edx, 14h
0x180023e18  call    WPP_SF_
0x180023e1d  mov     rcx, [rsi+130h]; this
0x180023e24  xor     edx, edx; bool
0x180023e26  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x180023e2b  mov     rax, [rsi+130h]
0x180023e32  xor     edi, edi
0x180023e34  mov     r15b, dil
0x180023e37  mov     r13, [rax+0D8h]
0x180023e3e  mov     r14, [rax+0E8h]
0x180023e45  mov     [rsp+0B8h+arg_0], edi
0x180023e4c  mov     [rsp+0B8h+var_48], rdi
0x180023e51  mov     [rsp+0B8h+arg_8], rdi
0x180023e59  cmp     [rbx+8], rdi
0x180023e5d  jz      short loc_180023EBF
0x180023e5f  test    bpl, 21h
0x180023e63  jnz     short loc_180023EBF
0x180023e65  mov     r15b, 1
0x180023e68  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e6f  lea     rax, WPP_GLOBAL_Control
0x180023e76  cmp     rcx, rax
0x180023e79  jz      short loc_180023E94
0x180023e7b  test    byte ptr [rcx+1Ch], 4
0x180023e7f  jz      short loc_180023E94
0x180023e81  mov     rcx, [rcx+10h]
0x180023e85  lea     edx, [rdi+15h]
0x180023e88  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180023e8f  call    WPP_SF_
0x180023e94  mov     rcx, [rbx+8]; hToken
0x180023e98  call    cs:__imp_ImpersonateLoggedOnUser
0x180023e9e  test    eax, eax
0x180023ea0  jnz     short loc_180023EBF
0x180023ea2  call    cs:__imp_GetLastError
0x180023ea8  mov     r8d, eax; int
0x180023eab  lea     rdx, aImpersonatelog; "ImpersonateLoggedOnUser()"
0x180023eb2  lea     rcx, aLegacyeapmetho_0; "LegacyEapMethodRuntime::GetIdentity()"
0x180023eb9  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180023ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ec6  lea     rax, WPP_GLOBAL_Control
0x180023ecd  cmp     rcx, rax
0x180023ed0  jz      short loc_180023EED
0x180023ed2  test    byte ptr [rcx+1Ch], 4
0x180023ed6  jz      short loc_180023EED
0x180023ed8  mov     rcx, [rcx+10h]
0x180023edc  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180023ee3  mov     edx, 16h
0x180023ee8  call    WPP_SF_
0x180023eed  mov     rbx, [rsp+0B8h+arg_20]
0x180023ef5  mov     rcx, [rbx+8]
0x180023ef9  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180023efe  mov     rcx, [r12+8]
0x180023f03  mov     edi, eax
0x180023f05  mov     rbx, [rbx]
0x180023f08  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180023f0d  movzx   ecx, byte ptr [rsi+10h]
0x180023f11  lea     rdx, [rsp+0B8h+arg_8]
0x180023f19  mov     [rsp+0B8h+var_60], rdx
0x180023f1e  or      ebp, 2
0x180023f21  lea     rdx, [rsp+0B8h+arg_0]
0x180023f29  xor     r9d, r9d
0x180023f2c  mov     [rsp+0B8h+var_68], rdx
0x180023f31  mov     r8d, ebp
0x180023f34  lea     rdx, [rsp+0B8h+var_48]
0x180023f39  mov     [rsp+0B8h+var_70], rdx
0x180023f3e  mov     rdx, [r12]
0x180023f42  mov     [rsp+0B8h+var_78], edi
0x180023f46  mov     [rsp+0B8h+var_80], rbx
0x180023f4b  mov     [rsp+0B8h+var_88], eax
0x180023f4f  mov     rax, r13
0x180023f52  mov     [rsp+0B8h+var_90], rdx
0x180023f57  xor     edx, edx
0x180023f59  mov     [rsp+0B8h+var_98], 0
0x180023f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f67  mov     ebx, eax
0x180023f69  test    r15b, r15b
0x180023f6c  jz      short loc_180023FDF
0x180023f6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f75  lea     rdi, WPP_GLOBAL_Control
0x180023f7c  cmp     rcx, rdi
0x180023f7f  jz      short loc_180023F9C
0x180023f81  test    byte ptr [rcx+1Ch], 4
0x180023f85  jz      short loc_180023F9C
0x180023f87  mov     rcx, [rcx+10h]
0x180023f8b  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180023f92  mov     edx, 17h
0x180023f97  call    WPP_SF_
0x180023f9c  call    cs:__imp_RevertToSelf
0x180023fa2  test    eax, eax
0x180023fa4  jnz     short loc_180023FE6
0x180023fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fad  cmp     rcx, rdi
0x180023fb0  jz      short loc_180023FED
0x180023fb2  test    byte ptr [rcx+1Ch], 1
0x180023fb6  jz      short loc_180023FED
0x180023fb8  call    cs:__imp_GetLastError
0x180023fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fc5  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180023fcc  mov     edx, 18h
0x180023fd1  mov     r9d, eax
0x180023fd4  mov     rcx, [rcx+10h]
0x180023fd8  call    WPP_SF_d
0x180023fdd  jmp     short loc_180023FE6
0x180023fdf  lea     rdi, WPP_GLOBAL_Control
0x180023fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fed  test    ebx, ebx
0x180023fef  jnz     short loc_180024065
0x180023ff1  cmp     rcx, rdi
0x180023ff4  jz      short loc_18002400F
0x180023ff6  test    byte ptr [rcx+1Ch], 4
0x180023ffa  jz      short loc_18002400F
0x180023ffc  mov     rcx, [rcx+10h]
0x180024000  lea     edx, [rbx+19h]
0x180024003  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x18002400a  call    WPP_SF_
0x18002400f  mov     rdx, [rsp+0B8h+arg_8]
0x180024017  mov     rcx, [rsp+0B8h+arg_30]
0x18002401f  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180024024  mov     rcx, [rsp+0B8h+arg_8]
0x18002402c  mov     rax, r14
0x18002402f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024034  mov     r8, [rsp+0B8h+var_48]
0x180024039  test    r8, r8
0x18002403c  jz      short loc_180024065
0x18002403e  mov     ecx, [rsp+0B8h+arg_0]
0x180024045  test    ecx, ecx
0x180024047  jz      short loc_180024065
0x180024049  mov     edx, ecx
0x18002404b  mov     rcx, [rsp+0B8h+arg_28]
0x180024053  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180024058  mov     rcx, [rsp+0B8h+var_48]
0x18002405d  mov     rax, r14
0x180024060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024065  mov     eax, ebx
0x180024067  mov     rbx, [rsp+0B8h+arg_10]
0x18002406f  add     rsp, 80h
0x180024076  pop     r15
0x180024078  pop     r14
0x18002407a  pop     r13
0x18002407c  pop     r12
0x18002407e  pop     rdi
0x18002407f  pop     rsi
0x180024080  pop     rbp
0x180024081  retn
```
