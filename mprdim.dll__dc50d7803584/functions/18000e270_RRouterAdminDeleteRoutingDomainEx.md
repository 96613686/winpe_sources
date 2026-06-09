# RRouterAdminDeleteRoutingDomainEx

- ea: `0x18000e270`
- end: `0x18000e46a`
- name: `RRouterAdminDeleteRoutingDomainEx`
- size: `506`
- prototype: `__int64 __fastcall(__int64, struct _GUID *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000da10`
- `0x18000df70`
- `0x18000e270`
- `0x180012be0`
- `0x180014fcc`
- `0x180019eb0`
- `0x1800288a8`
- `0x1800353e0`
- `0x180045ca0`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e331`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e331`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e428`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e428`

## string_xrefs

- `0x18000e359`: `RRouterAdminDeleteRoutingDomainEx: IsRoutingDomainAvailable failed: %d.`
- `0x18000e3cf`: `RRouterAdminDeleteRoutingDomainEx: DimStopRoutingDomain failed: %d.`
- `0x18000e3fd`: `RRouterAdminDeleteRoutingDomainEx: DisableRoutingDomainOnRRAS failed: %d.`

## pseudocode

```c
__int64 __fastcall RRouterAdminDeleteRoutingDomainEx(__int64 a1, struct _GUID *a2)
{
  int v3; // esi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  CDimInterfaceTable *v7; // rcx
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  GUID ActivityId; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v10; // [rsp+48h] [rbp-B8h]
  int v11; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v12; // [rsp+5Ch] [rbp-A4h]
  __int128 v13; // [rsp+6Ch] [rbp-94h]
  int v14; // [rsp+7Ch] [rbp-84h]
  int v15; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v16[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v8 = 0;
  v15 = 0;
  ActivityId = 0;
  v10 = 0;
  memset_0(v16, 0, sizeof(v16));
  v11 = 0;
  v14 = 0;
  v12 = 0;
  v13 = 0;
  v3 = SetActivityId(a2);
  if ( !IsLRPC() )
  {
    if ( v3 )
      ReSetActivityId(&ActivityId);
    return 5;
  }
  if ( !a2 )
  {
    if ( v3 )
      ReSetActivityId(&ActivityId);
    return 87;
  }
  EnterCriticalSection(&CriticalSection);
  v5 = IsRoutingDomainAvailable(a2, &v8);
  v6 = v5;
  if ( !v5 )
  {
    v6 = DimStopRoutingDomain(a2, 1);
    if ( v6 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_22;
      LOWORD(v15) = 0;
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v15, L"RRouterAdminDeleteRoutingDomainEx: DimStopRoutingDomain failed: %d.", v6);
    }
    else
    {
      v6 = DisableRoutingDomainOnRRAS(a2);
      if ( !v6 )
      {
        if ( !v8 )
          UpdateGlobalPhoneBookContext();
        goto LABEL_22;
      }
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_22;
      LOWORD(v15) = 0;
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v15, L"RRouterAdminDeleteRoutingDomainEx: DisableRoutingDomainOnRRAS failed: %d.", v6);
    }
LABEL_12:
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceError,
        (unsigned int)&v15,
        (_DWORD)a2,
        0,
        (__int64)&v11);
    goto LABEL_22;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
  {
    LOWORD(v15) = 0;
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v15, L"RRouterAdminDeleteRoutingDomainEx: IsRoutingDomainAvailable failed: %d.", v5);
    goto LABEL_12;
  }
LABEL_22:
  LeaveCriticalSection(&CriticalSection);
  if ( !v6 )
    CDimInterfaceTable::UpdateTelemetry(v7);
  if ( v3 )
    ReSetActivityId(&ActivityId);
  EtwEndRRASActivity(a2);
  return v6;
}

```

## disassembly

```asm
0x18000e270  push    rbp
0x18000e272  push    rbx
0x18000e273  push    rsi
0x18000e274  push    rdi
0x18000e275  lea     rbp, [rsp-798h]
0x18000e27d  sub     rsp, 898h
0x18000e284  mov     rax, cs:__security_cookie
0x18000e28b  xor     rax, rsp
0x18000e28e  mov     [rbp+7B0h+var_30], rax
0x18000e295  mov     rdi, rdx
0x18000e298  mov     [rsp+8B0h+var_880], 0
0x18000e2a0  xorps   xmm0, xmm0
0x18000e2a3  lea     rcx, [rbp+7B0h+var_82C]; void *
0x18000e2a7  xorps   xmm1, xmm1
0x18000e2aa  xor     eax, eax
0x18000e2ac  xor     edx, edx; Val
0x18000e2ae  mov     [rbp+7B0h+var_830], eax
0x18000e2b1  mov     r8d, 7FCh; Size
0x18000e2b7  movups  xmmword ptr [rsp+8B0h+ActivityId.Data1], xmm0
0x18000e2bc  movups  [rsp+8B0h+var_868], xmm1
0x18000e2c1  call    memset_0
0x18000e2c6  xor     eax, eax
0x18000e2c8  lea     rdx, [rsp+8B0h+ActivityId]
0x18000e2cd  xorps   xmm0, xmm0
0x18000e2d0  mov     [rsp+8B0h+var_858], eax
0x18000e2d4  mov     rcx, rdi; ActivityId
0x18000e2d7  mov     [rsp+8B0h+var_834], eax
0x18000e2db  movups  [rsp+8B0h+var_854], xmm0
0x18000e2e0  movups  [rsp+8B0h+var_844], xmm0
0x18000e2e5  call    SetActivityId
0x18000e2ea  mov     esi, eax
0x18000e2ec  call    ?IsLRPC@@YAHXZ; IsLRPC(void)
0x18000e2f1  test    eax, eax
0x18000e2f3  jnz     short loc_18000E30D
0x18000e2f5  test    esi, esi
0x18000e2f7  jz      short loc_18000E303
0x18000e2f9  lea     rcx, [rsp+8B0h+ActivityId]; ActivityId
0x18000e2fe  call    ReSetActivityId
0x18000e303  mov     eax, 5
0x18000e308  jmp     loc_18000E44F
0x18000e30d  test    rdi, rdi
0x18000e310  jnz     short loc_18000E32A
0x18000e312  test    esi, esi
0x18000e314  jz      short loc_18000E320
0x18000e316  lea     rcx, [rsp+8B0h+ActivityId]; ActivityId
0x18000e31b  call    ReSetActivityId
0x18000e320  mov     eax, 57h ; 'W'
0x18000e325  jmp     loc_18000E44F
0x18000e32a  lea     rcx, CriticalSection; lpCriticalSection
0x18000e331  call    cs:__imp_EnterCriticalSection
0x18000e337  lea     rdx, [rsp+8B0h+var_880]; int *
0x18000e33c  mov     rcx, rdi; struct _GUID *
0x18000e33f  call    ?IsRoutingDomainAvailable@@YAKPEAU_GUID@@PEAH@Z; IsRoutingDomainAvailable(_GUID *,int *)
0x18000e344  mov     ebx, eax
0x18000e346  test    eax, eax
0x18000e348  jz      short loc_18000E3B1
0x18000e34a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000e351  jz      loc_18000E421
0x18000e357  xor     ecx, ecx
0x18000e359  lea     rdx, aRrouteradminde_1; "RRouterAdminDeleteRoutingDomainEx: IsRo"...
0x18000e360  mov     word ptr [rbp+7B0h+var_830], cx
0x18000e364  mov     r8d, eax
0x18000e367  mov     word ptr [rsp+8B0h+var_858], cx
0x18000e36c  lea     rcx, [rbp+7B0h+var_830]
0x18000e370  call    FormatRRASErrorString
0x18000e375  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000e37c  jz      loc_18000E421
0x18000e382  lea     rax, [rsp+8B0h+var_858]
0x18000e387  mov     r9, rdi
0x18000e38a  mov     [rsp+8B0h+var_888], rax
0x18000e38f  lea     r8, [rbp+7B0h+var_830]
0x18000e393  lea     rdx, RasDimParamTraceError
0x18000e39a  mov     [rsp+8B0h+var_890], 0
0x18000e3a3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e3aa  call    McTemplateU0zjzz_EventWriteTransfer
0x18000e3af  jmp     short loc_18000E421
0x18000e3b1  mov     edx, 1; int
0x18000e3b6  mov     rcx, rdi; struct _GUID *
0x18000e3b9  call    ?DimStopRoutingDomain@@YAKPEAU_GUID@@H@Z; DimStopRoutingDomain(_GUID *,int)
0x18000e3be  mov     ebx, eax
0x18000e3c0  test    eax, eax
0x18000e3c2  jz      short loc_18000E3E4
0x18000e3c4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000e3cb  jz      short loc_18000E421
0x18000e3cd  xor     eax, eax
0x18000e3cf  lea     rdx, aRrouteradminde_0; "RRouterAdminDeleteRoutingDomainEx: DimS"...
0x18000e3d6  mov     word ptr [rbp+7B0h+var_830], ax
0x18000e3da  mov     r8d, ebx
0x18000e3dd  mov     word ptr [rsp+8B0h+var_858], ax
0x18000e3e2  jmp     short loc_18000E36C
0x18000e3e4  mov     rcx, rdi; struct _GUID *
0x18000e3e7  call    DisableRoutingDomainOnRRAS
0x18000e3ec  mov     ebx, eax
0x18000e3ee  test    eax, eax
0x18000e3f0  jz      short loc_18000E415
0x18000e3f2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000e3f9  jz      short loc_18000E421
0x18000e3fb  xor     eax, eax
0x18000e3fd  lea     rdx, aRrouteradminde; "RRouterAdminDeleteRoutingDomainEx: Disa"...
0x18000e404  mov     word ptr [rbp+7B0h+var_830], ax
0x18000e408  mov     r8d, ebx
0x18000e40b  mov     word ptr [rsp+8B0h+var_858], ax
0x18000e410  jmp     loc_18000E36C
0x18000e415  cmp     [rsp+8B0h+var_880], 0
0x18000e41a  jnz     short loc_18000E421
0x18000e41c  call    ?UpdateGlobalPhoneBookContext@@YAXXZ; UpdateGlobalPhoneBookContext(void)
0x18000e421  lea     rcx, CriticalSection; lpCriticalSection
0x18000e428  call    cs:__imp_LeaveCriticalSection
0x18000e42e  test    ebx, ebx
0x18000e430  jnz     short loc_18000E437
0x18000e432  call    ?UpdateTelemetry@CDimInterfaceTable@@QEAAXXZ; CDimInterfaceTable::UpdateTelemetry(void)
0x18000e437  test    esi, esi
0x18000e439  jz      short loc_18000E445
0x18000e43b  lea     rcx, [rsp+8B0h+ActivityId]; ActivityId
0x18000e440  call    ReSetActivityId
0x18000e445  mov     rcx, rdi; struct _GUID *
0x18000e448  call    EtwEndRRASActivity
0x18000e44d  mov     eax, ebx
0x18000e44f  mov     rcx, [rbp+7B0h+var_30]
0x18000e456  xor     rcx, rsp; StackCookie
0x18000e459  call    __security_check_cookie
0x18000e45e  add     rsp, 898h
0x18000e465  pop     rdi
0x18000e466  pop     rsi
0x18000e467  pop     rbx
0x18000e468  pop     rbp
0x18000e469  retn
```
