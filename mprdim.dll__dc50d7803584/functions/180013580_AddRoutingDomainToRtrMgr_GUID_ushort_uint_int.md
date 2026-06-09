# AddRoutingDomainToRtrMgr(_GUID *,ushort *,uint,int)

- ea: `0x180013580`
- end: `0x180013805`
- name: `?AddRoutingDomainToRtrMgr@@YAKPEAU_GUID@@PEAGIH@Z`
- size: `645`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014244`

## callees

- `0x18000df70`
- `0x180013580`
- `0x18002e15c`
- `0x180035d10`
- `0x1800442f0`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001370f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001370f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001375a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001375a`

## string_xrefs

- `0x180013648`: `AddRoutingDomainToRtrMgr: transport is not configured for routing domain.`

## pseudocode

```c
__int64 __fastcall AddRoutingDomainToRtrMgr(struct _GUID *a1, unsigned __int16 *a2, unsigned int a3)
{
  unsigned int RoutingDomainConfiguration; // eax
  unsigned int v6; // ebx
  __int128 *v7; // r9
  __int128 *v8; // r9
  RTL_SRWLOCK *v9; // rdi
  unsigned int v10; // r15d
  __int64 v11; // r12
  unsigned int v12; // ebx
  struct CDimRouterManager::_ROUTER *Router; // rax
  __int64 (__fastcall *v14)(struct _GUID *, unsigned __int16 *, _QWORD, __int64, unsigned int); // rax
  __int128 *v15; // r9
  unsigned int v18[4]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+5Ch] [rbp-A4h]
  __int128 v22; // [rsp+6Ch] [rbp-94h]
  int v23; // [rsp+7Ch] [rbp-84h]
  int v24; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v24 = 0;
  *(_OWORD *)v18 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v23 = 0;
  v21 = 0;
  v22 = 0;
  v19 = 0;
  RoutingDomainConfiguration = GetRoutingDomainConfiguration(a1, (__int64)v18);
  v6 = RoutingDomainConfiguration;
  if ( RoutingDomainConfiguration )
  {
    if ( RoutingDomainConfiguration == 2 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        v7 = &v19;
        LOWORD(v20) = 0;
        if ( a1 )
          LODWORD(v7) = (_DWORD)a1;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceError,
          (unsigned int)L"AddRoutingDomainToRtrMgr: transport is not configured for routing domain.",
          (_DWORD)v7,
          0,
          (__int64)&v20);
      }
      return 0;
    }
    else if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v24) = 0;
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v24, L"AddRoutingDomainToRtrMgr: Failed to retrieve: %d.", RoutingDomainConfiguration);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        v8 = &v19;
        if ( a1 )
          LODWORD(v8) = (_DWORD)a1;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceError,
          (unsigned int)&v24,
          (_DWORD)v8,
          0,
          (__int64)&v20);
      }
    }
  }
  else
  {
    v9 = (RTL_SRWLOCK *)g_pCDimRouterManager;
    v10 = v18[1];
    v11 = *(_QWORD *)&v18[2];
    v12 = v18[0];
    AcquireSRWLockShared((PSRWLOCK)g_pCDimRouterManager + 1);
    Router = CDimRouterManager::GetRouter((CDimRouterManager *)v9, v12);
    if ( Router )
    {
      v14 = (__int64 (__fastcall *)(struct _GUID *, unsigned __int16 *, _QWORD, __int64, unsigned int))*((_QWORD *)Router + 40);
      if ( v14 )
        v6 = v14(a1, a2, a3, v11, v10);
      else
        v6 = 50;
    }
    else
    {
      v6 = 902;
    }
    ReleaseSRWLockShared(v9 + 1);
    if ( v6 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v24) = 0;
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v24, L"AddRoutingDomainToRtrMgr: AddRoutingDomain failed : %d.", v6);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v15 = &v19;
          if ( a1 )
            LODWORD(v15) = (_DWORD)a1;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v24,
            (_DWORD)v15,
            0,
            (__int64)&v20);
        }
      }
    }
    FreeRoutingDomainConfiguration(32, v18);
  }
  return v6;
}

```

## disassembly

```asm
0x180013580  mov     [rsp-8+arg_18], rbx
0x180013585  push    rbp
0x180013586  push    rsi
0x180013587  push    rdi
0x180013588  push    r12
0x18001358a  push    r13
0x18001358c  push    r14
0x18001358e  push    r15
0x180013590  lea     rbp, [rsp-790h]
0x180013598  sub     rsp, 890h
0x18001359f  mov     rax, cs:__security_cookie
0x1800135a6  xor     rax, rsp
0x1800135a9  mov     [rbp+7C0h+var_40], rax
0x1800135b0  mov     [rsp+8C0h+var_890], r8d
0x1800135b5  mov     r13, rdx
0x1800135b8  mov     rsi, rcx
0x1800135bb  xorps   xmm0, xmm0
0x1800135be  xor     eax, eax
0x1800135c0  lea     rcx, [rbp+7C0h+var_83C]; void *
0x1800135c4  xor     edx, edx; Val
0x1800135c6  mov     [rbp+7C0h+var_840], eax
0x1800135c9  mov     r8d, 7FCh; Size
0x1800135cf  mov     ebx, r9d
0x1800135d2  movups  xmmword ptr [rsp+8C0h+var_888], xmm0
0x1800135d7  call    memset_0
0x1800135dc  xor     eax, eax
0x1800135de  mov     [rsp+8C0h+var_88C], 10h
0x1800135e6  xorps   xmm0, xmm0
0x1800135e9  mov     [rsp+8C0h+var_868], eax
0x1800135ed  mov     [rsp+8C0h+var_844], eax
0x1800135f1  lea     r9, [rsp+8C0h+var_88C]
0x1800135f6  lea     rax, [rsp+8C0h+var_888]
0x1800135fb  neg     ebx
0x1800135fd  mov     rcx, rsi; struct _GUID *
0x180013600  mov     [rsp+8C0h+var_8A0], rax; __int64
0x180013605  sbb     edx, edx
0x180013607  xor     r8d, r8d
0x18001360a  and     edx, 0FFFFFFA0h
0x18001360d  sub     edx, 0FFFFFF80h
0x180013610  movups  [rsp+8C0h+var_864], xmm0
0x180013615  movups  [rsp+8C0h+var_854], xmm0
0x18001361a  movups  [rsp+8C0h+var_878], xmm0
0x18001361f  call    GetRoutingDomainConfiguration
0x180013624  mov     ebx, eax
0x180013626  test    eax, eax
0x180013628  jz      loc_1800136F6
0x18001362e  cmp     eax, 2
0x180013631  jnz     short loc_180013683
0x180013633  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18001363a  jz      short loc_18001367C
0x18001363c  xor     eax, eax
0x18001363e  lea     r9, [rsp+8C0h+var_878]
0x180013643  mov     word ptr [rsp+8C0h+var_868], ax
0x180013648  lea     r8, aAddroutingdoma_1; "AddRoutingDomainToRtrMgr: transport is "...
0x18001364f  test    rsi, rsi
0x180013652  lea     rax, [rsp+8C0h+var_868]
0x180013657  mov     [rsp+8C0h+var_898], rax
0x18001365c  lea     rdx, RasDimParamTraceError
0x180013663  cmovnz  r9, rsi
0x180013667  mov     [rsp+8C0h+var_8A0], 0
0x180013670  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013677  call    McTemplateU0zjzz_EventWriteTransfer
0x18001367c  xor     ebx, ebx
0x18001367e  jmp     loc_1800137D9
0x180013683  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18001368a  jz      loc_1800137D9
0x180013690  xor     eax, eax
0x180013692  lea     rdx, aAddroutingdoma_0; "AddRoutingDomainToRtrMgr: Failed to ret"...
0x180013699  mov     r8d, ebx
0x18001369c  mov     word ptr [rbp+7C0h+var_840], ax
0x1800136a0  lea     rcx, [rbp+7C0h+var_840]
0x1800136a4  mov     word ptr [rsp+8C0h+var_868], ax
0x1800136a9  call    FormatRRASErrorString
0x1800136ae  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800136b5  jz      loc_1800137D9
0x1800136bb  test    rsi, rsi
0x1800136be  lea     rax, [rsp+8C0h+var_868]
0x1800136c3  mov     [rsp+8C0h+var_898], rax
0x1800136c8  lea     r9, [rsp+8C0h+var_878]
0x1800136cd  cmovnz  r9, rsi
0x1800136d1  mov     [rsp+8C0h+var_8A0], 0
0x1800136da  lea     r8, [rbp+7C0h+var_840]
0x1800136de  lea     rdx, RasDimParamTraceError
0x1800136e5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800136ec  call    McTemplateU0zjzz_EventWriteTransfer
0x1800136f1  jmp     loc_1800137D9
0x1800136f6  mov     rdi, cs:?g_pCDimRouterManager@@3PEAVCDimRouterManager@@EA; CDimRouterManager * g_pCDimRouterManager
0x1800136fd  mov     r15d, [rsp+8C0h+var_888+4]
0x180013702  mov     r12, qword ptr [rsp+8C0h+var_888+8]
0x180013707  mov     ebx, [rsp+8C0h+var_888]
0x18001370b  lea     rcx, [rdi+8]; SRWLock
0x18001370f  call    cs:__imp_AcquireSRWLockShared
0x180013715  mov     edx, ebx; unsigned int
0x180013717  mov     rcx, rdi; this
0x18001371a  call    ?GetRouter@CDimRouterManager@@AEAAPEAU_ROUTER@1@K@Z; CDimRouterManager::GetRouter(ulong)
0x18001371f  test    rax, rax
0x180013722  jnz     short loc_18001372B
0x180013724  mov     ebx, 386h
0x180013729  jmp     short loc_180013756
0x18001372b  mov     rax, [rax+140h]
0x180013732  test    rax, rax
0x180013735  jnz     short loc_18001373C
0x180013737  lea     ebx, [rax+32h]
0x18001373a  jmp     short loc_180013756
0x18001373c  mov     r8d, [rsp+8C0h+var_890]
0x180013741  mov     r9, r12
0x180013744  mov     rdx, r13
0x180013747  mov     dword ptr [rsp+8C0h+var_8A0], r15d
0x18001374c  mov     rcx, rsi
0x18001374f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013754  mov     ebx, eax
0x180013756  lea     rcx, [rdi+8]; SRWLock
0x18001375a  call    cs:__imp_ReleaseSRWLockShared
0x180013760  test    ebx, ebx
0x180013762  jz      short loc_1800137CA
0x180013764  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18001376b  jz      short loc_1800137CA
0x18001376d  xor     eax, eax
0x18001376f  lea     rdx, aAddroutingdoma; "AddRoutingDomainToRtrMgr: AddRoutingDom"...
0x180013776  mov     r8d, ebx
0x180013779  mov     word ptr [rbp+7C0h+var_840], ax
0x18001377d  lea     rcx, [rbp+7C0h+var_840]
0x180013781  mov     word ptr [rsp+8C0h+var_868], ax
0x180013786  call    FormatRRASErrorString
0x18001378b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180013792  jz      short loc_1800137CA
0x180013794  test    rsi, rsi
0x180013797  lea     rax, [rsp+8C0h+var_868]
0x18001379c  mov     [rsp+8C0h+var_898], rax
0x1800137a1  lea     r9, [rsp+8C0h+var_878]
0x1800137a6  cmovnz  r9, rsi
0x1800137aa  mov     [rsp+8C0h+var_8A0], 0
0x1800137b3  lea     r8, [rbp+7C0h+var_840]
0x1800137b7  lea     rdx, RasDimParamTraceError
0x1800137be  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800137c5  call    McTemplateU0zjzz_EventWriteTransfer
0x1800137ca  lea     rdx, [rsp+8C0h+var_888]
0x1800137cf  mov     ecx, 20h ; ' '
0x1800137d4  call    FreeRoutingDomainConfiguration
0x1800137d9  mov     eax, ebx
0x1800137db  mov     rcx, [rbp+7C0h+var_40]
0x1800137e2  xor     rcx, rsp; StackCookie
0x1800137e5  call    __security_check_cookie
0x1800137ea  mov     rbx, [rsp+8C0h+arg_18]
0x1800137f2  add     rsp, 890h
0x1800137f9  pop     r15
0x1800137fb  pop     r14
0x1800137fd  pop     r13
0x1800137ff  pop     r12
0x180013801  pop     rdi
0x180013802  pop     rsi
0x180013803  pop     rbp
0x180013804  retn
```
