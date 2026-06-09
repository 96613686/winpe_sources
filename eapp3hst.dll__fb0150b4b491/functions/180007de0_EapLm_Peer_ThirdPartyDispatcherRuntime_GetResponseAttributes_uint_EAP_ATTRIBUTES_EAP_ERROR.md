# EapLm::Peer::ThirdPartyDispatcherRuntime::GetResponseAttributes(uint,_EAP_ATTRIBUTES *,_EAP_ERROR * *)

- ea: `0x180007de0`
- end: `0x180007fd1`
- name: `?GetResponseAttributes@ThirdPartyDispatcherRuntime@Peer@EapLm@@UEAAJIPEAU_EAP_ATTRIBUTES@@PEAPEAU_EAP_ERROR@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherRuntime *__hidden this, unsigned int, struct _EAP_ATTRIBUTES *, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800058cc`
- `0x180005d30`
- `0x180007de0`
- `0x18000bf94`
- `0x180012c10`
- `0x180015534`
- `0x180015b00`
- `0x18001677c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f91`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherRuntime::GetResponseAttributes(
        EapLm::Peer::ThirdPartyDispatcherRuntime *this,
        unsigned int a2,
        struct _EAP_ATTRIBUTES *a3,
        struct _EAP_ERROR **a4)
{
  unsigned int v6; // edi
  ReferenceCounted *v7; // rdx
  volatile signed __int32 *v8; // rbx
  __int64 v9; // rdx
  bool v10; // r8
  int *v11; // r9
  struct _EAP_ATTRIBUTES *v12; // rsi
  unsigned __int64 i; // r14
  const ATL::CAtlException *v15; // [rsp+28h] [rbp-70h] BYREF
  const EapHost::EapException *v16; // [rsp+30h] [rbp-68h] BYREF
  const Exception *v17; // [rsp+38h] [rbp-60h] BYREF
  ReferenceCounted *v18[2]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v19; // [rsp+50h] [rbp-48h] BYREF
  __int64 v20; // [rsp+60h] [rbp-38h]
  _OWORD v21[3]; // [rsp+68h] [rbp-30h] BYREF
  struct _EAP_ERROR *v22; // [rsp+A8h] [rbp+10h] BYREF
  struct _EAP_ATTRIBUTES *v23; // [rsp+B0h] [rbp+18h]
  const struct Exception *v24; // [rsp+B8h] [rbp+20h]

  v24 = (const struct Exception *)a4;
  v23 = a3;
  v6 = 0;
  LODWORD(v22) = 0;
  if ( !a2 || !a3 || !a4 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    EapHost::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>(
      v18,
      (EapLm::Peer::ThirdPartyDispatcherRuntime *)((char *)this - 88),
      a2);
    v7 = v18[0];
    if ( !v18[0] )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_bb903cf33960336db7d560c47724160a_Traceguids, a2);
      EapHost::EapException::Throw(L"Session missing in the session table", L"GetRespnseAttributes", -2147024809);
    }
    if ( !*((_QWORD *)v18[0] + 8) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_bb903cf33960336db7d560c47724160a_Traceguids, a2);
      EapHost::EapException::Throw(L"Session(%d)'s innersession is missing", L"GetRespnseAttributes", -2147024809);
    }
    v8 = (volatile signed __int32 *)*((_QWORD *)v18[0] + 9);
    if ( v8 )
      _InterlockedIncrement(v8 + 2);
    v19 = 0;
    v20 = 0;
    v21[0] = 0u;
    (*(void (__fastcall **)(volatile signed __int32 *, _QWORD, __int128 *))(*(_QWORD *)v8 + 88LL))(
      v8,
      *((_QWORD *)v7 + 8),
      &v19);
    ComCopy((const struct EapHost::Attributes *)v21, a3);
    EapHost::AutoAttributes::~AutoAttributes((EapHost::AutoAttributes *)&v19);
    ReferenceCounted::Release((ReferenceCounted *)v8);
    EapHost::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>::~SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>(
      v18,
      v9,
      v10);
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v22) = -2147024882;
    *(_QWORD *)v24 = 0;
    v6 = (unsigned int)v22;
    goto LABEL_19;
  }
  catch ( const ATL::CAtlException *v15 )
  {
    LODWORD(v22) = *(_DWORD *)v15;
    *(_QWORD *)v24 = 0;
    goto LABEL_18;
  }
  catch ( const EapHost::EapException *v16 )
  {
    EapHost::EapException2EapErrorOle(v16, v24, &v22, v11);
    goto LABEL_18;
  }
  catch ( const Exception *v17 )
  {
    EapHost::Exception2EapErrorOle(v17, v24, &v22, v11);
LABEL_18:
    v6 = (unsigned int)v22;
    if ( (int)v22 < 0 )
    {
LABEL_19:
      v12 = v23;
      for ( i = 0; i < v12->dwNumberOfAttributes; v12->pAttribs[i++].pValue = 0 )
        CoTaskMemFree(v12->pAttribs[i].pValue);
      *v12 = 0;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180007de0  mov     rax, rsp
0x180007de3  mov     [rax+8], rbx
0x180007de7  mov     [rax+20h], r9
0x180007deb  mov     [rax+18h], r8
0x180007def  push    rsi
0x180007df0  push    rdi
0x180007df1  push    r14
0x180007df3  sub     rsp, 80h
0x180007dfa  mov     rsi, r8
0x180007dfd  mov     ebx, edx
0x180007dff  xor     edi, edi
0x180007e01  mov     [rax+10h], edi
0x180007e04  test    edx, edx
0x180007e06  jz      loc_180007FB8
0x180007e0c  test    r8, r8
0x180007e0f  jz      loc_180007FB8
0x180007e15  test    r9, r9
0x180007e18  jz      loc_180007FB8
0x180007e1e  xorps   xmm0, xmm0
0x180007e21  movups  xmmword ptr [r8], xmm0
0x180007e25  lea     rdx, [rcx-58h]
0x180007e29  mov     r8d, ebx
0x180007e2c  lea     rcx, [rax-58h]
0x180007e30  call    ??0?$SessionAccessor@VThirdPartyDispatcherSession@Peer@EapLm@@@EapHost@@QEAA@AEAV?$Cache@V?$SessionTableOperation@VThirdPartyDispatcherSession@Peer@EapLm@@@EapHost@@@@I_N@Z; EapHost::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>(Cache<EapHost::SessionTableOperation<EapLm::Peer::ThirdPartyDispatcherSession>> &,uint,bool)
0x180007e35  nop
0x180007e36  mov     rdx, [rsp+98h+var_58]
0x180007e3b  test    rdx, rdx
0x180007e3e  jnz     short loc_180007E88
0x180007e40  lea     rax, WPP_GLOBAL_Control
0x180007e47  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e4e  cmp     rcx, rax
0x180007e51  jz      short loc_180007E6F
0x180007e53  test    byte ptr [rcx+1Ch], 1
0x180007e57  jz      short loc_180007E6F
0x180007e59  lea     edx, [rdi+14h]
0x180007e5c  mov     r9d, ebx
0x180007e5f  lea     r8, WPP_bb903cf33960336db7d560c47724160a_Traceguids
0x180007e66  mov     rcx, [rcx+10h]
0x180007e6a  call    WPP_SF_d
0x180007e6f  mov     r8d, 80070057h; int
0x180007e75  lea     rdx, aGetrespnseattr; "GetRespnseAttributes"
0x180007e7c  lea     rcx, aSessionMissing; "Session missing in the session table"
0x180007e83  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180007e88  cmp     qword ptr [rdx+40h], 0
0x180007e8d  jnz     short loc_180007ED9
0x180007e8f  lea     rax, WPP_GLOBAL_Control
0x180007e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e9d  cmp     rcx, rax
0x180007ea0  jz      short loc_180007EC0
0x180007ea2  test    byte ptr [rcx+1Ch], 1
0x180007ea6  jz      short loc_180007EC0
0x180007ea8  mov     edx, 15h
0x180007ead  mov     r9d, ebx
0x180007eb0  lea     r8, WPP_bb903cf33960336db7d560c47724160a_Traceguids
0x180007eb7  mov     rcx, [rcx+10h]
0x180007ebb  call    WPP_SF_d
0x180007ec0  mov     r8d, 80070057h; int
0x180007ec6  lea     rdx, aGetrespnseattr; "GetRespnseAttributes"
0x180007ecd  lea     rcx, aSessionDSInner; "Session(%d)'s innersession is missing"
0x180007ed4  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180007ed9  mov     rbx, [rdx+48h]
0x180007edd  mov     [rsp+98h+var_78], rbx
0x180007ee2  test    rbx, rbx
0x180007ee5  jz      short loc_180007EEB
0x180007ee7  lock inc dword ptr [rbx+8]
0x180007eeb  xorps   xmm0, xmm0
0x180007eee  movdqu  [rsp+98h+var_48], xmm0
0x180007ef4  mov     [rsp+98h+var_38], 0
0x180007efd  movups  [rsp+98h+var_30], xmm0
0x180007f02  mov     dword ptr [rsp+98h+var_30], 0
0x180007f0a  mov     qword ptr [rsp+98h+var_30+8], 0
0x180007f13  mov     rax, [rbx]
0x180007f16  lea     r8, [rsp+98h+var_48]
0x180007f1b  mov     rdx, [rdx+40h]
0x180007f1f  mov     rcx, rbx
0x180007f22  mov     rax, [rax+58h]
0x180007f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f2b  mov     rdx, rsi; struct _EAP_ATTRIBUTES *
0x180007f2e  lea     rcx, [rsp+98h+var_30]; struct EapHost::Attributes *
0x180007f33  call    ?ComCopy@@YAXAEBVAttributes@EapHost@@AEAU_EAP_ATTRIBUTES@@@Z; ComCopy(EapHost::Attributes const &,_EAP_ATTRIBUTES &)
0x180007f38  nop
0x180007f39  lea     rcx, [rsp+98h+var_48]; this
0x180007f3e  call    ??1AutoAttributes@EapHost@@QEAA@XZ; EapHost::AutoAttributes::~AutoAttributes(void)
0x180007f43  nop
0x180007f44  mov     rcx, rbx; this
0x180007f47  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x180007f4c  nop
0x180007f4d  lea     rcx, [rsp+98h+var_58]
0x180007f52  call    ??1?$SessionAccessor@VThirdPartyDispatcherSession@Peer@EapLm@@@EapHost@@QEAA@XZ; EapHost::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>::~SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>(void)
0x180007f57  nop
0x180007f58  jmp     short loc_180007FB4
0x180007f5a  mov     edi, dword ptr [rsp+98h+arg_8]
0x180007f61  jmp     short loc_180007F72
0x180007f63  jmp     short loc_180007F67
0x180007f65  jmp     short $+2
0x180007f67  mov     edi, dword ptr [rsp+98h+arg_8]
0x180007f6e  test    edi, edi
0x180007f70  jns     short loc_180007FB4
0x180007f72  mov     rsi, [rsp+98h+arg_10]
0x180007f7a  xor     r14d, r14d
0x180007f7d  cmp     [rsi], r14d
0x180007f80  jbe     short loc_180007FAE
0x180007f82  mov     rbx, r14
0x180007f85  add     rbx, rbx
0x180007f88  mov     rcx, [rsi+8]
0x180007f8c  mov     rcx, [rcx+rbx*8+8]; pv
0x180007f91  call    cs:__imp_CoTaskMemFree
0x180007f97  mov     rcx, [rsi+8]
0x180007f9b  mov     qword ptr [rcx+rbx*8+8], 0
0x180007fa4  inc     r14
0x180007fa7  mov     ecx, [rsi]
0x180007fa9  cmp     r14, rcx
0x180007fac  jb      short loc_180007F82
0x180007fae  xorps   xmm0, xmm0
0x180007fb1  movups  xmmword ptr [rsi], xmm0
0x180007fb4  mov     eax, edi
0x180007fb6  jmp     short loc_180007FBD
0x180007fb8  mov     eax, 80004003h
0x180007fbd  mov     rbx, [rsp+98h+arg_0]
0x180007fc5  add     rsp, 80h
0x180007fcc  pop     r14
0x180007fce  pop     rdi
0x180007fcf  pop     rsi
0x180007fd0  retn
```
