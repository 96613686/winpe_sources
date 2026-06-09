# EapLm::Peer::LegacyEapMethodRuntime::GetIdentityHelper(ObjectHandle const &,uint,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &)

- ea: `0x180013430`
- end: `0x1800136e8`
- name: `?GetIdentityHelper@LegacyEapMethodRuntime@Peer@EapLm@@AEAAKAEBVObjectHandle@@IAEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@@Z`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800131c0`

## callees

- `0x1800052c0`
- `0x180009dc4`
- `0x180009dec`
- `0x1800121ec`
- `0x180013430`
- `0x18001cf70`
- `0x18001dcbc`
- `0x18002fd44`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136cb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800134fa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800134fa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800135e5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800135e5`

## string_xrefs

- `0x1800136d4`: `ImpersonateLoggedOnUser()`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::LegacyEapMethodRuntime::GetIdentityHelper(
        __int64 a1,
        __int64 a2,
        int a3,
        _QWORD *a4,
        __int64 *a5,
        __int64 a6,
        void **a7)
{
  __int64 v11; // rax
  char v12; // r15
  __int64 (__fastcall *v13)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int, __int64, int, const void **, unsigned int *, __int64 *); // r13
  void (__fastcall *v14)(__int64); // r14
  __int64 *v15; // rbx
  int v16; // edi
  __int64 v17; // rbx
  int v18; // eax
  unsigned int v19; // ebx
  EapHost::Peer::Host *v20; // rcx
  DWORD v21; // eax
  DWORD LastError; // eax
  const void *v24; // [rsp+70h] [rbp-48h] BYREF
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
  v13 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int, __int64, int, const void **, unsigned int *, __int64 *))(v11 + 216);
  v14 = *(void (__fastcall **)(__int64))(v11 + 232);
  v25 = 0;
  v24 = 0;
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
  v19 = v13(*(unsigned __int8 *)(a1 + 16), 0, a3 | 2u, 0, 0, *a4, v18, v17, v16, &v24, &v25, &v26);
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
    if ( v24 && v25 )
    {
      TempBuffer<0>::Assign(a6, v25, v24);
      v14((__int64)v24);
    }
  }
  return v19;
}

```

## disassembly

```asm
0x180013430  mov     [rsp+arg_10], rbx
0x180013435  push    rbp
0x180013436  push    rsi
0x180013437  push    rdi
0x180013438  push    r12
0x18001343a  push    r13
0x18001343c  push    r14
0x18001343e  push    r15
0x180013440  sub     rsp, 80h
0x180013447  mov     r12, r9
0x18001344a  mov     ebp, r8d
0x18001344d  mov     rbx, rdx
0x180013450  mov     rsi, rcx
0x180013453  mov     rcx, cs:WPP_GLOBAL_Control
0x18001345a  lea     rax, WPP_GLOBAL_Control
0x180013461  cmp     rcx, rax
0x180013464  jz      short loc_180013481
0x180013466  test    byte ptr [rcx+1Ch], 4
0x18001346a  jz      short loc_180013481
0x18001346c  mov     rcx, [rcx+10h]
0x180013470  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013477  mov     edx, 14h
0x18001347c  call    WPP_SF_
0x180013481  mov     rcx, [rsi+130h]; this
0x180013488  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001348d  mov     rax, [rsi+130h]
0x180013494  xor     edi, edi
0x180013496  mov     r15b, dil
0x180013499  mov     r13, [rax+0D8h]
0x1800134a0  mov     r14, [rax+0E8h]
0x1800134a7  mov     [rsp+0B8h+arg_0], edi
0x1800134ae  mov     [rsp+0B8h+var_48], rdi
0x1800134b3  mov     [rsp+0B8h+arg_8], rdi
0x1800134bb  cmp     [rbx+8], rdi
0x1800134bf  jz      short loc_180013508
0x1800134c1  test    bpl, 21h
0x1800134c5  jnz     short loc_180013508
0x1800134c7  mov     r15b, 1
0x1800134ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134d1  lea     rax, WPP_GLOBAL_Control
0x1800134d8  cmp     rcx, rax
0x1800134db  jz      short loc_1800134F6
0x1800134dd  test    byte ptr [rcx+1Ch], 4
0x1800134e1  jz      short loc_1800134F6
0x1800134e3  mov     rcx, [rcx+10h]
0x1800134e7  lea     edx, [rdi+15h]
0x1800134ea  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x1800134f1  call    WPP_SF_
0x1800134f6  mov     rcx, [rbx+8]; hToken
0x1800134fa  call    cs:__imp_ImpersonateLoggedOnUser
0x180013500  test    eax, eax
0x180013502  jz      loc_1800136CB
0x180013508  mov     rcx, cs:WPP_GLOBAL_Control
0x18001350f  lea     rax, WPP_GLOBAL_Control
0x180013516  cmp     rcx, rax
0x180013519  jz      short loc_180013536
0x18001351b  test    byte ptr [rcx+1Ch], 4
0x18001351f  jz      short loc_180013536
0x180013521  mov     rcx, [rcx+10h]
0x180013525  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x18001352c  mov     edx, 16h
0x180013531  call    WPP_SF_
0x180013536  mov     rbx, [rsp+0B8h+arg_20]
0x18001353e  mov     rcx, [rbx+8]
0x180013542  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180013547  mov     rcx, [r12+8]
0x18001354c  mov     edi, eax
0x18001354e  mov     rbx, [rbx]
0x180013551  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180013556  movzx   ecx, byte ptr [rsi+10h]
0x18001355a  lea     rdx, [rsp+0B8h+arg_8]
0x180013562  mov     [rsp+0B8h+var_60], rdx
0x180013567  or      ebp, 2
0x18001356a  lea     rdx, [rsp+0B8h+arg_0]
0x180013572  xor     r9d, r9d
0x180013575  mov     [rsp+0B8h+var_68], rdx
0x18001357a  mov     r8d, ebp
0x18001357d  lea     rdx, [rsp+0B8h+var_48]
0x180013582  mov     [rsp+0B8h+var_70], rdx
0x180013587  mov     rdx, [r12]
0x18001358b  mov     [rsp+0B8h+var_78], edi
0x18001358f  mov     [rsp+0B8h+var_80], rbx
0x180013594  mov     [rsp+0B8h+var_88], eax
0x180013598  mov     rax, r13
0x18001359b  mov     [rsp+0B8h+var_90], rdx
0x1800135a0  xor     edx, edx
0x1800135a2  mov     [rsp+0B8h+var_98], 0
0x1800135ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135b0  mov     ebx, eax
0x1800135b2  test    r15b, r15b
0x1800135b5  jz      short loc_180013628
0x1800135b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800135be  lea     rdi, WPP_GLOBAL_Control
0x1800135c5  cmp     rcx, rdi
0x1800135c8  jz      short loc_1800135E5
0x1800135ca  test    byte ptr [rcx+1Ch], 4
0x1800135ce  jz      short loc_1800135E5
0x1800135d0  mov     rcx, [rcx+10h]
0x1800135d4  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x1800135db  mov     edx, 17h
0x1800135e0  call    WPP_SF_
0x1800135e5  call    cs:__imp_RevertToSelf
0x1800135eb  test    eax, eax
0x1800135ed  jnz     short loc_18001362F
0x1800135ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800135f6  cmp     rcx, rdi
0x1800135f9  jz      short loc_180013636
0x1800135fb  test    byte ptr [rcx+1Ch], 1
0x1800135ff  jz      short loc_180013636
0x180013601  call    cs:__imp_GetLastError
0x180013607  mov     rcx, cs:WPP_GLOBAL_Control
0x18001360e  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013615  mov     edx, 18h
0x18001361a  mov     r9d, eax
0x18001361d  mov     rcx, [rcx+10h]
0x180013621  call    WPP_SF_d
0x180013626  jmp     short loc_18001362F
0x180013628  lea     rdi, WPP_GLOBAL_Control
0x18001362f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013636  test    ebx, ebx
0x180013638  jnz     short loc_1800136AE
0x18001363a  cmp     rcx, rdi
0x18001363d  jz      short loc_180013658
0x18001363f  test    byte ptr [rcx+1Ch], 4
0x180013643  jz      short loc_180013658
0x180013645  mov     rcx, [rcx+10h]
0x180013649  lea     edx, [rbx+19h]
0x18001364c  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013653  call    WPP_SF_
0x180013658  mov     rdx, [rsp+0B8h+arg_8]
0x180013660  mov     rcx, [rsp+0B8h+arg_30]
0x180013668  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18001366d  mov     rcx, [rsp+0B8h+arg_8]
0x180013675  mov     rax, r14
0x180013678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001367d  mov     r8, [rsp+0B8h+var_48]
0x180013682  test    r8, r8
0x180013685  jz      short loc_1800136AE
0x180013687  mov     ecx, [rsp+0B8h+arg_0]
0x18001368e  test    ecx, ecx
0x180013690  jz      short loc_1800136AE
0x180013692  mov     edx, ecx
0x180013694  mov     rcx, [rsp+0B8h+arg_28]
0x18001369c  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x1800136a1  mov     rcx, [rsp+0B8h+var_48]
0x1800136a6  mov     rax, r14
0x1800136a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136ae  mov     eax, ebx
0x1800136b0  mov     rbx, [rsp+0B8h+arg_10]
0x1800136b8  add     rsp, 80h
0x1800136bf  pop     r15
0x1800136c1  pop     r14
0x1800136c3  pop     r13
0x1800136c5  pop     r12
0x1800136c7  pop     rdi
0x1800136c8  pop     rsi
0x1800136c9  pop     rbp
0x1800136ca  retn
0x1800136cb  call    cs:__imp_GetLastError
0x1800136d1  mov     r8d, eax; int
0x1800136d4  lea     rdx, aImpersonatelog; "ImpersonateLoggedOnUser()"
0x1800136db  lea     rcx, aLegacyeapmetho; "LegacyEapMethodRuntime::GetIdentity()"
0x1800136e2  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
