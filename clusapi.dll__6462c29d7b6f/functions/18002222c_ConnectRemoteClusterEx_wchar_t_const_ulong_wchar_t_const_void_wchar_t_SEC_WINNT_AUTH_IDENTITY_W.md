# ConnectRemoteClusterEx(wchar_t const *,ulong,wchar_t const *,void * *,wchar_t * *,_SEC_WINNT_AUTH_IDENTITY_W *)

- ea: `0x18002222c`
- end: `0x180022501`
- name: `?ConnectRemoteClusterEx@@YAJPEB_WK0PEAPEAXPEAPEA_WPEAU_SEC_WINNT_AUTH_IDENTITY_W@@@Z`
- size: `725`
- prototype: `__int64 __usercall@<rax>(PCWSTR AddressString@<rcx>, unsigned int@<edx>, const wchar_t *@<r8>, void **@<r9>, wchar_t **, struct _SEC_WINNT_AUTH_IDENTITY_W *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180021ef0`

## callees

- `0x180002f50`
- `0x18001236c`
- `0x18002222c`
- `0x180024efc`
- `0x180028f30`
- `0x180029578`
- `0x18006f910`
- `0x18009e5ac`
- `0x18009e6e4`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180022330`
- `RPCRT4!RpcStringFreeW` at `0x1800224c6`
- `RPCRT4!RpcStringFreeW` at `0x180022330`
- `RPCRT4!RpcStringFreeW` at `0x1800224c6`
- `RPCRT4!RpcMgmtSetComTimeout` at `0x1800223e0`
- `RPCRT4!RpcMgmtSetComTimeout` at `0x1800223e0`
- `RPCRT4!RpcEpResolveBinding` at `0x18002231d`
- `RPCRT4!RpcEpResolveBinding` at `0x18002231d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180022303`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180022303`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800222ec`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800222ec`
- `RPCRT4!RpcBindingFree` at `0x180022339`
- `RPCRT4!RpcBindingFree` at `0x1800224d9`
- `RPCRT4!RpcBindingFree` at `0x180022339`
- `RPCRT4!RpcBindingFree` at `0x1800224d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800224b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800224b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022480`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022480`

## string_xrefs

- `0x1800223f2`: `RpcMgmtSetComTimeout failed - %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConnectRemoteClusterEx(
        unsigned __int16 *AddressString,
        unsigned int a2,
        const wchar_t *a3,
        void **a4,
        wchar_t **a5,
        struct _SEC_WINNT_AUTH_IDENTITY_W *a6)
{
  HLOCAL v8; // r15
  const WCHAR *v9; // rdi
  unsigned __int16 *User; // rax
  int i; // ebx
  __int64 v12; // rcx
  unsigned int v13; // esi
  unsigned int KerberosSPN; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  RPC_STATUS v17; // eax
  wchar_t **v18; // r12
  unsigned __int32 v19; // edi
  wchar_t *v20; // rbx
  const wchar_t *v21; // rax
  RPC_WSTR *StringBinding; // [rsp+28h] [rbp-61h]
  RPC_WSTR *StringBindinga; // [rsp+28h] [rbp-61h]
  __int64 v25; // [rsp+30h] [rbp-59h]
  RPC_WSTR String; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-41h]
  HLOCAL hMem; // [rsp+50h] [rbp-39h]
  wchar_t **v29; // [rsp+58h] [rbp-31h]
  __int128 v30; // [rsp+60h] [rbp-29h] BYREF
  __m128i si128; // [rsp+70h] [rbp-19h]

  v27 = a2;
  v29 = a5;
  String = 0;
  v8 = 0;
  hMem = 0;
  v9 = a3;
  if ( !a3 )
    v9 = AddressString;
  if ( a6 )
    User = a6->User;
  else
    User = (unsigned __int16 *)&base;
  TraceMsg(
    4,
    0,
    L"ConnectRemoteClusterEx",
    1218,
    L"Connecting to to ClusterName '%ws' (kerb name '%ws'), username '%ws'",
    a3,
    v9,
    User);
  for ( i = 0; i < 2; ++i )
  {
    *a4 = 0;
    v13 = RpcStringBindingComposeW(
            (RPC_WSTR)L"b97db8b2-4c63-11cf-bff6-08002be23f2f",
            (RPC_WSTR)L"ncacn_ip_tcp",
            AddressString,
            0,
            0,
            &String);
    if ( v13 )
      goto LABEL_19;
    v13 = RpcBindingFromStringBindingW(String, a4);
    if ( v13 )
      goto LABEL_19;
    v13 = RpcEpResolveBinding(*a4, qword_1800BB3B0);
    if ( v13 != 1726 )
      break;
    RpcStringFreeW(&String);
    RpcBindingFree(a4);
  }
  if ( v13 )
  {
    LODWORD(v25) = v13;
    TraceMsg(
      2,
      0,
      L"ConnectRemoteClusterEx",
      1269,
      L"Couldn't resolve RPC binding to cluster '%ws', Status = %u",
      AddressString,
      v25);
LABEL_19:
    v30 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v30) = 0;
    LogExtendedErrorInformationInternal(v12, &v30);
    v18 = v29;
    if ( v29 )
    {
      v19 = 2 * si128.m128i_i32[0] + 2;
      v20 = (wchar_t *)LocalAlloc(0x40u, v19);
      *v18 = v20;
      v21 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v30);
      StringCchCopyW(v20, v19, v21);
    }
    std::wstring::_Tidy_deallocate(&v30);
    goto LABEL_22;
  }
  KerberosSPN = ClRtlMakeKerberosSPN(v9);
  v13 = KerberosSPN;
  if ( KerberosSPN )
  {
    LODWORD(StringBinding) = KerberosSPN;
    TraceMsg(2, 0, L"ConnectRemoteClusterEx", 1286, L"ClRtlMakeKerberosSPN failed - %d", StringBinding);
    v8 = hMem;
    goto LABEL_19;
  }
  HIDWORD(StringBindinga) = HIDWORD(a6);
  v8 = hMem;
  v16 = ClRtlSecureClusterRPCHandle(*a4, v15, v27, hMem);
  v13 = v16;
  if ( v16 )
  {
    LODWORD(StringBindinga) = v16;
    TraceMsg(
      2,
      0,
      L"ConnectRemoteClusterEx",
      1308,
      L"Failed to apply authentication parameters to the RPC binding handle. Error: %d.",
      StringBindinga);
    goto LABEL_19;
  }
  v17 = RpcMgmtSetComTimeout(*a4, 0);
  if ( v17 )
  {
    LODWORD(StringBindinga) = v17;
    TraceMsg(v13 + 2, 0, L"ConnectRemoteClusterEx", 1304, L"RpcMgmtSetComTimeout failed - %d", StringBindinga);
  }
LABEL_22:
  if ( v8 )
    LocalFree(v8);
  if ( String )
    RpcStringFreeW(&String);
  if ( v13 && *a4 )
    RpcBindingFree(a4);
  return v13;
}

```

## disassembly

```asm
0x18002222c  push    rbp
0x18002222e  push    rbx
0x18002222f  push    rsi
0x180022230  push    rdi
0x180022231  push    r12
0x180022233  push    r13
0x180022235  push    r14
0x180022237  push    r15
0x180022239  lea     rbp, [rsp-0Fh]
0x18002223e  sub     rsp, 98h
0x180022245  mov     rax, cs:__security_cookie
0x18002224c  xor     rax, rsp
0x18002224f  mov     [rbp+47h+var_50], rax
0x180022253  mov     r14, r9
0x180022256  mov     [rbp+47h+var_88], edx
0x180022259  mov     r13, rcx
0x18002225c  mov     r12, [rbp+47h+arg_28]
0x180022260  mov     rax, [rbp+47h+arg_20]
0x180022264  mov     [rbp+47h+var_78], rax
0x180022268  mov     [rbp+47h+String], 0
0x180022270  xor     r15d, r15d
0x180022273  mov     [rbp+47h+hMem], r15
0x180022277  mov     rdi, r8
0x18002227a  test    r8, r8
0x18002227d  cmovz   rdi, rcx
0x180022281  test    r12, r12
0x180022284  jz      short loc_18002228C
0x180022286  mov     rax, [r12]
0x18002228a  jmp     short loc_180022293
0x18002228c  lea     rax, base
0x180022293  mov     [rsp+0D0h+var_98], rax
0x180022298  mov     [rsp+0D0h+var_A0], rdi
0x18002229d  mov     [rsp+0D0h+StringBinding], r8
0x1800222a2  lea     rax, aConnectingToTo; "Connecting to to ClusterName '%ws' (ker"...
0x1800222a9  mov     [rsp+0D0h+Options], rax
0x1800222ae  mov     r9d, 4C2h
0x1800222b4  lea     r8, aConnectremotec; "ConnectRemoteClusterEx"
0x1800222bb  xor     edx, edx
0x1800222bd  lea     ecx, [rdx+4]
0x1800222c0  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800222c5  xor     ebx, ebx
0x1800222c7  mov     [r14], r15
0x1800222ca  lea     rax, [rbp+47h+String]
0x1800222ce  mov     [rsp+0D0h+StringBinding], rax; StringBinding
0x1800222d3  mov     [rsp+0D0h+Options], r15; Options
0x1800222d8  xor     r9d, r9d; Endpoint
0x1800222db  mov     r8, r13; NetworkAddr
0x1800222de  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x1800222e5  lea     rcx, ObjUuid; "b97db8b2-4c63-11cf-bff6-08002be23f2f"
0x1800222ec  call    cs:__imp_RpcStringBindingComposeW
0x1800222f2  mov     esi, eax
0x1800222f4  test    eax, eax
0x1800222f6  jnz     loc_180022441
0x1800222fc  mov     rdx, r14; Binding
0x1800222ff  mov     rcx, [rbp+47h+String]; StringBinding
0x180022303  call    cs:__imp_RpcBindingFromStringBindingW
0x180022309  mov     esi, eax
0x18002230b  test    eax, eax
0x18002230d  jnz     loc_180022441
0x180022313  lea     rdx, qword_1800BB3B0; IfSpec
0x18002231a  mov     rcx, [r14]; Binding
0x18002231d  call    cs:__imp_RpcEpResolveBinding
0x180022323  mov     esi, eax
0x180022325  cmp     eax, 6BEh
0x18002232a  jnz     short loc_180022346
0x18002232c  lea     rcx, [rbp+47h+String]; String
0x180022330  call    cs:__imp_RpcStringFreeW
0x180022336  mov     rcx, r14; Binding
0x180022339  call    cs:__imp_RpcBindingFree
0x18002233f  inc     ebx
0x180022341  cmp     ebx, 2
0x180022344  jl      short loc_1800222C7
0x180022346  test    esi, esi
0x180022348  jz      short loc_18002237B
0x18002234a  mov     dword ptr [rsp+0D0h+var_A0], esi
0x18002234e  mov     [rsp+0D0h+StringBinding], r13
0x180022353  lea     rax, aCouldnTResolve; "Couldn't resolve RPC binding to cluster"...
0x18002235a  mov     [rsp+0D0h+Options], rax
0x18002235f  mov     r9d, 4F5h
0x180022365  lea     r8, aConnectremotec; "ConnectRemoteClusterEx"
0x18002236c  xor     edx, edx
0x18002236e  lea     ecx, [rdx+2]
0x180022371  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180022376  jmp     loc_180022441
0x18002237b  lea     rdx, [rbp+47h+hMem]
0x18002237f  mov     rcx, rdi; AddressString
0x180022382  call    ClRtlMakeKerberosSPN
0x180022387  mov     esi, eax
0x180022389  test    eax, eax
0x18002238b  jz      short loc_1800223BD
0x18002238d  mov     dword ptr [rsp+0D0h+StringBinding], eax
0x180022391  lea     rax, aClrtlmakekerbe; "ClRtlMakeKerberosSPN failed - %d"
0x180022398  mov     [rsp+0D0h+Options], rax
0x18002239d  mov     r9d, 506h
0x1800223a3  lea     r8, aConnectremotec; "ConnectRemoteClusterEx"
0x1800223aa  xor     edx, edx
0x1800223ac  lea     ecx, [rdx+2]
0x1800223af  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800223b4  mov     r15, [rbp+47h+hMem]
0x1800223b8  jmp     loc_180022441
0x1800223bd  mov     [rsp+0D0h+StringBinding], r12
0x1800223c2  mov     r15, [rbp+47h+hMem]
0x1800223c6  mov     r9, r15
0x1800223c9  mov     r8d, [rbp+47h+var_88]
0x1800223cd  mov     rcx, [r14]
0x1800223d0  call    ClRtlSecureClusterRPCHandle
0x1800223d5  mov     esi, eax
0x1800223d7  test    eax, eax
0x1800223d9  jnz     short loc_18002241A
0x1800223db  xor     edx, edx; Timeout
0x1800223dd  mov     rcx, [r14]; Binding
0x1800223e0  call    cs:__imp_RpcMgmtSetComTimeout
0x1800223e6  test    eax, eax
0x1800223e8  jz      loc_1800224AD
0x1800223ee  mov     dword ptr [rsp+0D0h+StringBinding], eax
0x1800223f2  lea     rax, aRpcmgmtsetcomt; "RpcMgmtSetComTimeout failed - %d"
0x1800223f9  mov     [rsp+0D0h+Options], rax
0x1800223fe  mov     r9d, 518h
0x180022404  lea     r8, aConnectremotec; "ConnectRemoteClusterEx"
0x18002240b  xor     edx, edx
0x18002240d  lea     ecx, [rsi+2]
0x180022410  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180022415  jmp     loc_1800224AD
0x18002241a  mov     dword ptr [rsp+0D0h+StringBinding], eax
0x18002241e  lea     rax, aFailedToApplyA; "Failed to apply authentication paramete"...
0x180022425  mov     [rsp+0D0h+Options], rax
0x18002242a  mov     r9d, 51Ch
0x180022430  lea     r8, aConnectremotec; "ConnectRemoteClusterEx"
0x180022437  xor     edx, edx
0x180022439  lea     ecx, [rdx+2]
0x18002243c  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180022441  xorps   xmm0, xmm0
0x180022444  movups  [rbp+47h+var_70], xmm0
0x180022448  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180022450  movdqu  [rbp+47h+var_60], xmm1
0x180022455  xor     eax, eax
0x180022457  mov     word ptr [rbp+47h+var_70], ax
0x18002245b  lea     rdx, [rbp+47h+var_70]
0x18002245f  call    ?LogExtendedErrorInformationInternal@@YAX_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogExtendedErrorInformationInternal(bool,std::wstring &)
0x180022464  mov     r12, [rbp+47h+var_78]
0x180022468  test    r12, r12
0x18002246b  jz      short loc_1800224A4
0x18002246d  mov     eax, dword ptr [rbp+47h+var_60]
0x180022470  lea     eax, ds:2[rax*2]
0x180022477  mov     edi, eax
0x180022479  mov     edx, eax; uBytes
0x18002247b  mov     ecx, 40h ; '@'; uFlags
0x180022480  call    cs:__imp_LocalAlloc
0x180022486  mov     rbx, rax
0x180022489  mov     [r12], rax
0x18002248d  lea     rcx, [rbp+47h+var_70]
0x180022491  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180022496  mov     r8, rax; wchar_t *
0x180022499  mov     edx, edi; unsigned __int64
0x18002249b  mov     rcx, rbx; wchar_t *
0x18002249e  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800224a3  nop
0x1800224a4  lea     rcx, [rbp+47h+var_70]
0x1800224a8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800224ad  test    r15, r15
0x1800224b0  jz      short loc_1800224BB
0x1800224b2  mov     rcx, r15; hMem
0x1800224b5  call    cs:__imp_LocalFree
0x1800224bb  cmp     [rbp+47h+String], 0
0x1800224c0  jz      short loc_1800224CC
0x1800224c2  lea     rcx, [rbp+47h+String]; String
0x1800224c6  call    cs:__imp_RpcStringFreeW
0x1800224cc  test    esi, esi
0x1800224ce  jz      short loc_1800224DF
0x1800224d0  cmp     qword ptr [r14], 0
0x1800224d4  jz      short loc_1800224DF
0x1800224d6  mov     rcx, r14; Binding
0x1800224d9  call    cs:__imp_RpcBindingFree
0x1800224df  mov     eax, esi
0x1800224e1  mov     rcx, [rbp+47h+var_50]
0x1800224e5  xor     rcx, rsp; StackCookie
0x1800224e8  call    __security_check_cookie
0x1800224ed  add     rsp, 98h
0x1800224f4  pop     r15
0x1800224f6  pop     r14
0x1800224f8  pop     r13
0x1800224fa  pop     r12
0x1800224fc  pop     rdi
0x1800224fd  pop     rsi
0x1800224fe  pop     rbx
0x1800224ff  pop     rbp
0x180022500  retn
```
