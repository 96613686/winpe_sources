# LCIEFindOrCreateProcessManagerAtIL(bool,_IsoIntegrity,ulong *,bool,unsigned __int64 *,ulong)

- ea: `0x180082fb0`
- end: `0x1800832a4`
- name: `?LCIEFindOrCreateProcessManagerAtIL@@YAJ_NW4_IsoIntegrity@@PEAK0PEA_KK@Z`
- size: `756`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e550`
- `0x1801ce444`
- `0x1803b7564`
- `0x1803d9c0c`
- `0x1803fbb8c`
- `0x18041a46c`

## callees

- `0x180082fb0`
- `0x180084d74`
- `0x180094d9c`
- `0x18009ccb8`
- `0x1801d075c`
- `0x180591ef6`
- `0x180591f80`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800831a0`
- `KERNEL32!GetCurrentThreadId` at `0x1800831a0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180082ffe`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800831c9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180082ffe`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800831c9`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800831d9`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800831d9`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18008326b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18008326b`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x1800831ee`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x1800831ee`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x180083118`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18008312b`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x180083118`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18008312b`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1800830bb`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1800830bb`
- `msIso!__imp_?IsoCreateProcess@@YAJKPEAU_IsoCreationProcessData@@KPEBGPEAKPEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x18008323f`
- `msIso!__imp_?IsoCreateProcess@@YAJKPEAU_IsoCreationProcessData@@KPEBGPEAKPEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x18008323f`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x180083031`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x180083031`
- `msIso!__imp_?IsoGetProcessManager@@YAJKPEAK@Z` at `0x180083258`
- `msIso!__imp_?IsoGetProcessManager@@YAJKPEAK@Z` at `0x180083258`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x180083153`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x180083153`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180083020`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180083020`

## pseudocode

```c
__int64 __fastcall LCIEFindOrCreateProcessManagerAtIL(
        __int64 a1,
        unsigned int a2,
        unsigned int *a3,
        char a4,
        __int64 a5,
        int a6)
{
  __int16 v8; // bx
  int v9; // r15d
  HRESULT NextArtifact; // ebx
  __int64 v11; // rdx
  unsigned int v12; // ebx
  unsigned int v13; // esi
  DWORD CurrentThreadId; // eax
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR AppID; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[32]; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+80h] [rbp-80h]
  _BYTE v21[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v22; // [rsp+B2h] [rbp-4Eh]
  int v23; // [rsp+C8h] [rbp-38h]
  __int16 v24; // [rsp+D0h] [rbp-30h]
  unsigned int v25; // [rsp+D3h] [rbp-2Dh] BYREF
  unsigned int v26[82]; // [rsp+D7h] [rbp-29h] BYREF
  _BYTE v27[32]; // [rsp+220h] [rbp+120h] BYREF

  v8 = a2;
  v9 = LCIEGetPICFromIntegrityFlags(a2);
  if ( (unsigned __int8)IEConfiguration_GetBool(268435483)
    || LCIEUnifiedFrame() && v9 != (unsigned int)IsoGetIntegrity(1) )
  {
    memset_0(v19, 0, 0x48u);
    v16 = 0;
    v20 = v9 | v8 & 0x400;
    LCIEGetURLPolicyWithTabflags(&Default, (struct tagTABWINDOWDATA *)v19, 0, &v16, 0);
    v12 = 5;
    v18 = 0;
    v13 = v16;
    while ( 1 )
    {
      LOBYTE(v11) = 20;
      NextArtifact = IsoGetNextArtifact(v12, v11, v27, a3, &v18, 0);
      if ( NextArtifact )
        break;
      if ( *(_WORD *)(v18 + 2) == 3
        && (*(_DWORD *)(v18 + 20) & 0x6050000) == 0x4000000
        && ((v13 ^ *(_DWORD *)(v18 + 20)) & 0x8000000) == 0
        && *(_DWORD *)(v18 + 72) == a6
        && (*(_BYTE *)(v18 + 20) & 0x7F) == v9
        && (*(_DWORD *)(v18 + 64) & 1) == 0 )
      {
        IsoUnlockArtifact(*a3);
        if ( a5 )
          IsoAddDependency(*a3, *a3, 1, 49, a5);
        return (unsigned int)NextArtifact;
      }
      v12 = 6;
      IsoUnlockArtifact(*a3);
    }
    if ( a4 )
    {
      return (unsigned int)-2147467263;
    }
    else
    {
      v16 = 0;
      memset_0(v21, 0, 0x164u);
      v22 = 356;
      v24 = 0;
      v21[0] = 6;
      CurrentThreadId = GetCurrentThreadId();
      GetIESessionFromFrameThread(CurrentThreadId, v26, &v25);
      v23 = a6;
      AppID = 0;
      if ( (unsigned __int8)IEConfiguration_GetBool(268435465) || IsDualEngineProcess() )
        NextArtifact = GetCurrentProcessExplicitAppUserModelID(&AppID);
      if ( NextArtifact >= 0 )
      {
        NextArtifact = IsoCreateProcess(v9 | v13 | 0x5000, v21, 105, AppID, &v16, 0, a5 & -(__int64)(a5 != 0), 0);
        if ( NextArtifact >= 0 )
          NextArtifact = IsoGetProcessManager(v16, a3);
      }
      CoTaskMemFree(AppID);
    }
  }
  else
  {
    *a3 = IsoGetAuthorityManager();
    return 1;
  }
  return (unsigned int)NextArtifact;
}

```

## disassembly

```asm
0x180082fb0  mov     [rsp-8+arg_0], rbx
0x180082fb5  push    rbp
0x180082fb6  push    rsi
0x180082fb7  push    rdi
0x180082fb8  push    r12
0x180082fba  push    r13
0x180082fbc  push    r14
0x180082fbe  push    r15
0x180082fc0  lea     rbp, [rsp-150h]
0x180082fc8  sub     rsp, 250h
0x180082fcf  mov     rax, cs:__security_cookie
0x180082fd6  xor     rax, rsp
0x180082fd9  mov     [rbp+180h+var_40], rax
0x180082fe0  mov     r14, [rbp+180h+arg_20]
0x180082fe7  mov     ecx, edx
0x180082fe9  mov     r13b, r9b
0x180082fec  mov     rdi, r8
0x180082fef  mov     ebx, edx
0x180082ff1  call    ?LCIEGetPICFromIntegrityFlags@@YA?AW4_IsoIntegrity@@W41@@Z; LCIEGetPICFromIntegrityFlags(_IsoIntegrity)
0x180082ff6  mov     ecx, 1000001Bh
0x180082ffb  mov     r15d, eax
0x180082ffe  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180083005  nop     dword ptr [rax+rax+00h]
0x18008300a  xor     esi, esi
0x18008300c  lea     r12d, [rsi+1]
0x180083010  test    al, al
0x180083012  jnz     short loc_180083047
0x180083014  call    ?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x180083019  test    al, al
0x18008301b  jz      short loc_180083031
0x18008301d  mov     ecx, r12d
0x180083020  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180083027  nop     dword ptr [rax+rax+00h]
0x18008302c  cmp     r15d, eax
0x18008302f  jnz     short loc_180083047
0x180083031  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x180083038  nop     dword ptr [rax+rax+00h]
0x18008303d  mov     [rdi], eax
0x18008303f  mov     ebx, r12d
0x180083042  jmp     loc_180083277
0x180083047  xor     edx, edx; Val
0x180083049  lea     rcx, [rsp+280h+var_220]; void *
0x18008304e  lea     r8d, [rdx+48h]; Size
0x180083052  call    memset_0
0x180083057  and     ebx, 400h
0x18008305d  mov     [rsp+280h+var_240], esi
0x180083061  or      ebx, r15d
0x180083064  mov     [rsp+280h+var_260], rsi; unsigned int *
0x180083069  lea     r9, [rsp+280h+var_240]; unsigned int *
0x18008306e  mov     [rbp+180h+var_200], ebx
0x180083071  xor     r8d, r8d; unsigned int *
0x180083074  lea     rdx, [rsp+280h+var_220]; struct tagTABWINDOWDATA *
0x180083079  lea     rcx, Default; unsigned __int16 *
0x180083080  call    ?LCIEGetURLPolicyWithTabflags@@YAJPEBGPEAUtagTABWINDOWDATA@@PEAK22@Z; LCIEGetURLPolicyWithTabflags(ushort const *,tagTABWINDOWDATA *,ulong *,ulong *,ulong *)
0x180083085  mov     r12d, [rbp+180h+arg_28]
0x18008308c  mov     ebx, 5
0x180083091  mov     [rsp+280h+var_230], rsi
0x180083096  mov     esi, [rsp+280h+var_240]
0x18008309a  lea     rax, [rsp+280h+var_230]
0x18008309f  mov     [rsp+280h+var_258], 0
0x1800830a8  mov     r9, rdi
0x1800830ab  mov     [rsp+280h+var_260], rax
0x1800830b0  lea     r8, [rbp+180h+var_60]
0x1800830b7  mov     dl, 14h
0x1800830b9  mov     ecx, ebx
0x1800830bb  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x1800830c2  nop     dword ptr [rax+rax+00h]
0x1800830c7  mov     ebx, eax
0x1800830c9  test    eax, eax
0x1800830cb  jnz     loc_180083164
0x1800830d1  mov     rdx, [rsp+280h+var_230]
0x1800830d6  cmp     word ptr [rdx+2], 3
0x1800830db  jnz     short loc_180083111
0x1800830dd  mov     eax, [rdx+14h]
0x1800830e0  mov     ecx, eax
0x1800830e2  and     ecx, 6050000h
0x1800830e8  cmp     ecx, 4000000h
0x1800830ee  jnz     short loc_180083111
0x1800830f0  xor     eax, esi
0x1800830f2  bt      eax, 1Bh
0x1800830f6  jb      short loc_180083111
0x1800830f8  cmp     [rdx+48h], r12d
0x1800830fc  jnz     short loc_180083111
0x1800830fe  movzx   eax, byte ptr [rdx+14h]
0x180083102  and     eax, 7Fh
0x180083105  cmp     eax, r15d
0x180083108  jnz     short loc_180083111
0x18008310a  mov     eax, [rdx+40h]
0x18008310d  test    al, 1
0x18008310f  jz      short loc_180083129
0x180083111  mov     ecx, [rdi]
0x180083113  mov     ebx, 6
0x180083118  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x18008311f  nop     dword ptr [rax+rax+00h]
0x180083124  jmp     loc_18008309A
0x180083129  mov     ecx, [rdi]
0x18008312b  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x180083132  nop     dword ptr [rax+rax+00h]
0x180083137  test    r14, r14
0x18008313a  jz      loc_180083277
0x180083140  mov     edx, [rdi]
0x180083142  mov     r9d, 31h ; '1'
0x180083148  mov     ecx, edx
0x18008314a  mov     [rsp+280h+var_260], r14
0x18008314f  lea     r8d, [r9-30h]
0x180083153  call    cs:__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z; IsoAddDependency(ulong,ulong,_IsoComponentDependencyFlags,_BlockSuspendReason,unsigned __int64 *)
0x18008315a  nop     dword ptr [rax+rax+00h]
0x18008315f  jmp     loc_180083277
0x180083164  test    r13b, r13b
0x180083167  jz      short loc_180083173
0x180083169  mov     ebx, 80004001h
0x18008316e  jmp     loc_180083277
0x180083173  mov     r13d, 164h
0x180083179  mov     [rsp+280h+var_240], 0
0x180083181  mov     r8d, r13d; Size
0x180083184  lea     rcx, [rbp+180h+var_1D0]; void *
0x180083188  xor     edx, edx; Val
0x18008318a  call    memset_0
0x18008318f  mov     [rbp+180h+var_1CE], r13w
0x180083194  xor     r13d, r13d
0x180083197  mov     [rbp+180h+var_1B0], r13w
0x18008319c  mov     [rbp+180h+var_1D0], 6
0x1800831a0  call    cs:__imp_GetCurrentThreadId
0x1800831a7  nop     dword ptr [rax+rax+00h]
0x1800831ac  mov     ecx, eax; unsigned int
0x1800831ae  lea     r8, [rbp+180h+var_1AD]; unsigned int *
0x1800831b2  lea     rdx, [rbp+180h+var_1A9]; unsigned int *
0x1800831b6  call    ?GetIESessionFromFrameThread@@YAJKPEAK0@Z; GetIESessionFromFrameThread(ulong,ulong *,ulong *)
0x1800831bb  mov     ecx, 10000009h
0x1800831c0  mov     [rbp+180h+var_1B8], r12d
0x1800831c4  mov     [rsp+280h+AppID], r13
0x1800831c9  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800831d0  nop     dword ptr [rax+rax+00h]
0x1800831d5  test    al, al
0x1800831d7  jnz     short loc_1800831E9
0x1800831d9  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1800831e0  nop     dword ptr [rax+rax+00h]
0x1800831e5  test    al, al
0x1800831e7  jz      short loc_1800831FC
0x1800831e9  lea     rcx, [rsp+280h+AppID]; AppID
0x1800831ee  call    cs:__imp_GetCurrentProcessExplicitAppUserModelID
0x1800831f5  nop     dword ptr [rax+rax+00h]
0x1800831fa  mov     ebx, eax
0x1800831fc  test    ebx, ebx
0x1800831fe  js      short loc_180083266
0x180083200  mov     r9, [rsp+280h+AppID]
0x180083205  lea     rdx, [rbp+180h+var_1D0]
0x180083209  mov     [rsp+280h+var_248], r13d
0x18008320e  mov     rax, r14
0x180083211  neg     rax
0x180083214  lea     rax, [rsp+280h+var_240]
0x180083219  sbb     r8, r8
0x18008321c  or      esi, r15d
0x18008321f  and     r8, r14
0x180083222  or      esi, 5000h
0x180083228  mov     [rsp+280h+var_250], r8
0x18008322d  mov     ecx, esi
0x18008322f  mov     [rsp+280h+var_258], r13
0x180083234  mov     r8d, 69h ; 'i'
0x18008323a  mov     [rsp+280h+var_260], rax
0x18008323f  call    cs:__imp_?IsoCreateProcess@@YAJKPEAU_IsoCreationProcessData@@KPEBGPEAKPEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z; IsoCreateProcess(ulong,_IsoCreationProcessData *,ulong,ushort const *,ulong *,_IsoWindowsContainer *,unsigned __int64 *,IsoCreationFailureTreatment)
0x180083246  nop     dword ptr [rax+rax+00h]
0x18008324b  mov     ebx, eax
0x18008324d  test    eax, eax
0x18008324f  js      short loc_180083266
0x180083251  mov     ecx, [rsp+280h+var_240]
0x180083255  mov     rdx, rdi
0x180083258  call    cs:__imp_?IsoGetProcessManager@@YAJKPEAK@Z; IsoGetProcessManager(ulong,ulong *)
0x18008325f  nop     dword ptr [rax+rax+00h]
0x180083264  mov     ebx, eax
0x180083266  mov     rcx, [rsp+280h+AppID]; pv
0x18008326b  call    cs:__imp_CoTaskMemFree
0x180083272  nop     dword ptr [rax+rax+00h]
0x180083277  mov     eax, ebx
0x180083279  mov     rcx, [rbp+180h+var_40]
0x180083280  xor     rcx, rsp; StackCookie
0x180083283  call    __security_check_cookie
0x180083288  mov     rbx, [rsp+280h+arg_0]
0x180083290  add     rsp, 250h
0x180083297  pop     r15
0x180083299  pop     r14
0x18008329b  pop     r13
0x18008329d  pop     r12
0x18008329f  pop     rdi
0x1800832a0  pop     rsi
0x1800832a1  pop     rbp
0x1800832a2  retn
```
