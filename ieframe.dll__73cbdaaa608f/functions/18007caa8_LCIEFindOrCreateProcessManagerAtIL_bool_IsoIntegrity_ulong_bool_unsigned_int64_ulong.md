# LCIEFindOrCreateProcessManagerAtIL(bool,_IsoIntegrity,ulong *,bool,unsigned __int64 *,ulong)

- ea: `0x18007caa8`
- end: `0x18007cd40`
- name: `?LCIEFindOrCreateProcessManagerAtIL@@YAJ_NW4_IsoIntegrity@@PEAK0PEA_KK@Z`
- size: `664`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800072f0`
- `0x1801b8650`
- `0x1803867f8`
- `0x1803a794c`
- `0x1803c86a8`
- `0x1803e5488`

## callees

- `0x18007caa8`
- `0x18007f160`
- `0x18008e390`
- `0x1800959cc`
- `0x1801ba5a0`
- `0x18054e286`
- `0x18054e310`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007cc67`
- `KERNEL32!GetCurrentThreadId` at `0x18007cc67`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007caf6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007cc8a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007caf6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007cc8a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18007cc94`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18007cc94`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18007cd0e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18007cd0e`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x18007cca3`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x18007cca3`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18007cbf4`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18007cbfe`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18007cbf4`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18007cbfe`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x18007cba1`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x18007cba1`
- `msIso!__imp_?IsoCreateProcess@@YAJKPEAU_IsoCreationProcessData@@KPEBGPEAKPEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x18007ccee`
- `msIso!__imp_?IsoCreateProcess@@YAJKPEAU_IsoCreationProcessData@@KPEBGPEAKPEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x18007ccee`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x18007cb1d`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x18007cb1d`
- `msIso!__imp_?IsoGetProcessManager@@YAJKPEAK@Z` at `0x18007cd01`
- `msIso!__imp_?IsoGetProcessManager@@YAJKPEAK@Z` at `0x18007cd01`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x18007cc20`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x18007cc20`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18007cb12`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18007cb12`

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
    LCIEGetURLPolicyWithTabflags(&SrcStr, (struct tagTABWINDOWDATA *)v19, 0, &v16, 0);
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
0x18007caa8  mov     [rsp-8+arg_0], rbx
0x18007caad  push    rbp
0x18007caae  push    rsi
0x18007caaf  push    rdi
0x18007cab0  push    r12
0x18007cab2  push    r13
0x18007cab4  push    r14
0x18007cab6  push    r15
0x18007cab8  lea     rbp, [rsp-150h]
0x18007cac0  sub     rsp, 250h
0x18007cac7  mov     rax, cs:__security_cookie
0x18007cace  xor     rax, rsp
0x18007cad1  mov     [rbp+180h+var_40], rax
0x18007cad8  mov     r14, [rbp+180h+arg_20]
0x18007cadf  mov     ecx, edx
0x18007cae1  mov     r13b, r9b
0x18007cae4  mov     rdi, r8
0x18007cae7  mov     ebx, edx
0x18007cae9  call    ?LCIEGetPICFromIntegrityFlags@@YA?AW4_IsoIntegrity@@W41@@Z; LCIEGetPICFromIntegrityFlags(_IsoIntegrity)
0x18007caee  mov     ecx, 1000001Bh
0x18007caf3  mov     r15d, eax
0x18007caf6  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18007cafc  xor     esi, esi
0x18007cafe  lea     r12d, [rsi+1]
0x18007cb02  test    al, al
0x18007cb04  jnz     short loc_18007CB2D
0x18007cb06  call    ?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x18007cb0b  test    al, al
0x18007cb0d  jz      short loc_18007CB1D
0x18007cb0f  mov     ecx, r12d
0x18007cb12  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18007cb18  cmp     r15d, eax
0x18007cb1b  jnz     short loc_18007CB2D
0x18007cb1d  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x18007cb23  mov     [rdi], eax
0x18007cb25  mov     ebx, r12d
0x18007cb28  jmp     loc_18007CD14
0x18007cb2d  xor     edx, edx; Val
0x18007cb2f  lea     rcx, [rsp+280h+var_220]; void *
0x18007cb34  lea     r8d, [rdx+48h]; Size
0x18007cb38  call    memset_0
0x18007cb3d  and     ebx, 400h
0x18007cb43  mov     [rsp+280h+var_240], esi
0x18007cb47  or      ebx, r15d
0x18007cb4a  mov     [rsp+280h+var_260], rsi; unsigned int *
0x18007cb4f  lea     r9, [rsp+280h+var_240]; unsigned int *
0x18007cb54  mov     [rbp+180h+var_200], ebx
0x18007cb57  xor     r8d, r8d; unsigned int *
0x18007cb5a  lea     rdx, [rsp+280h+var_220]; struct tagTABWINDOWDATA *
0x18007cb5f  lea     rcx, SrcStr; unsigned __int16 *
0x18007cb66  call    ?LCIEGetURLPolicyWithTabflags@@YAJPEBGPEAUtagTABWINDOWDATA@@PEAK22@Z; LCIEGetURLPolicyWithTabflags(ushort const *,tagTABWINDOWDATA *,ulong *,ulong *,ulong *)
0x18007cb6b  mov     r12d, [rbp+180h+arg_28]
0x18007cb72  mov     ebx, 5
0x18007cb77  mov     [rsp+280h+var_230], rsi
0x18007cb7c  mov     esi, [rsp+280h+var_240]
0x18007cb80  lea     rax, [rsp+280h+var_230]
0x18007cb85  mov     [rsp+280h+var_258], 0
0x18007cb8e  mov     r9, rdi
0x18007cb91  mov     [rsp+280h+var_260], rax
0x18007cb96  lea     r8, [rbp+180h+var_60]
0x18007cb9d  mov     dl, 14h
0x18007cb9f  mov     ecx, ebx
0x18007cba1  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x18007cba7  mov     ebx, eax
0x18007cba9  test    eax, eax
0x18007cbab  jnz     short loc_18007CC2B
0x18007cbad  mov     rdx, [rsp+280h+var_230]
0x18007cbb2  cmp     word ptr [rdx+2], 3
0x18007cbb7  jnz     short loc_18007CBED
0x18007cbb9  mov     eax, [rdx+14h]
0x18007cbbc  mov     ecx, eax
0x18007cbbe  and     ecx, 6050000h
0x18007cbc4  cmp     ecx, 4000000h
0x18007cbca  jnz     short loc_18007CBED
0x18007cbcc  xor     eax, esi
0x18007cbce  bt      eax, 1Bh
0x18007cbd2  jb      short loc_18007CBED
0x18007cbd4  cmp     [rdx+48h], r12d
0x18007cbd8  jnz     short loc_18007CBED
0x18007cbda  movzx   eax, byte ptr [rdx+14h]
0x18007cbde  and     eax, 7Fh
0x18007cbe1  cmp     eax, r15d
0x18007cbe4  jnz     short loc_18007CBED
0x18007cbe6  mov     eax, [rdx+40h]
0x18007cbe9  test    al, 1
0x18007cbeb  jz      short loc_18007CBFC
0x18007cbed  mov     ecx, [rdi]
0x18007cbef  mov     ebx, 6
0x18007cbf4  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x18007cbfa  jmp     short loc_18007CB80
0x18007cbfc  mov     ecx, [rdi]
0x18007cbfe  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x18007cc04  test    r14, r14
0x18007cc07  jz      loc_18007CD14
0x18007cc0d  mov     edx, [rdi]
0x18007cc0f  mov     r9d, 31h ; '1'
0x18007cc15  mov     ecx, edx
0x18007cc17  mov     [rsp+280h+var_260], r14
0x18007cc1c  lea     r8d, [r9-30h]
0x18007cc20  call    cs:__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z; IsoAddDependency(ulong,ulong,_IsoComponentDependencyFlags,_BlockSuspendReason,unsigned __int64 *)
0x18007cc26  jmp     loc_18007CD14
0x18007cc2b  test    r13b, r13b
0x18007cc2e  jz      short loc_18007CC3A
0x18007cc30  mov     ebx, 80004001h
0x18007cc35  jmp     loc_18007CD14
0x18007cc3a  mov     r13d, 164h
0x18007cc40  mov     [rsp+280h+var_240], 0
0x18007cc48  mov     r8d, r13d; Size
0x18007cc4b  lea     rcx, [rbp+180h+var_1D0]; void *
0x18007cc4f  xor     edx, edx; Val
0x18007cc51  call    memset_0
0x18007cc56  mov     [rbp+180h+var_1CE], r13w
0x18007cc5b  xor     r13d, r13d
0x18007cc5e  mov     [rbp+180h+var_1B0], r13w
0x18007cc63  mov     [rbp+180h+var_1D0], 6
0x18007cc67  call    cs:__imp_GetCurrentThreadId
0x18007cc6d  mov     ecx, eax; unsigned int
0x18007cc6f  lea     r8, [rbp+180h+var_1AD]; unsigned int *
0x18007cc73  lea     rdx, [rbp+180h+var_1A9]; unsigned int *
0x18007cc77  call    ?GetIESessionFromFrameThread@@YAJKPEAK0@Z; GetIESessionFromFrameThread(ulong,ulong *,ulong *)
0x18007cc7c  mov     ecx, 10000009h
0x18007cc81  mov     [rbp+180h+var_1B8], r12d
0x18007cc85  mov     [rsp+280h+AppID], r13
0x18007cc8a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18007cc90  test    al, al
0x18007cc92  jnz     short loc_18007CC9E
0x18007cc94  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18007cc9a  test    al, al
0x18007cc9c  jz      short loc_18007CCAB
0x18007cc9e  lea     rcx, [rsp+280h+AppID]; AppID
0x18007cca3  call    cs:__imp_GetCurrentProcessExplicitAppUserModelID
0x18007cca9  mov     ebx, eax
0x18007ccab  test    ebx, ebx
0x18007ccad  js      short loc_18007CD09
0x18007ccaf  mov     r9, [rsp+280h+AppID]
0x18007ccb4  lea     rdx, [rbp+180h+var_1D0]
0x18007ccb8  mov     [rsp+280h+var_248], r13d
0x18007ccbd  mov     rax, r14
0x18007ccc0  neg     rax
0x18007ccc3  lea     rax, [rsp+280h+var_240]
0x18007ccc8  sbb     r8, r8
0x18007cccb  or      esi, r15d
0x18007ccce  and     r8, r14
0x18007ccd1  or      esi, 5000h
0x18007ccd7  mov     [rsp+280h+var_250], r8
0x18007ccdc  mov     ecx, esi
0x18007ccde  mov     [rsp+280h+var_258], r13
0x18007cce3  mov     r8d, 69h ; 'i'
0x18007cce9  mov     [rsp+280h+var_260], rax
0x18007ccee  call    cs:__imp_?IsoCreateProcess@@YAJKPEAU_IsoCreationProcessData@@KPEBGPEAKPEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z; IsoCreateProcess(ulong,_IsoCreationProcessData *,ulong,ushort const *,ulong *,_IsoWindowsContainer *,unsigned __int64 *,IsoCreationFailureTreatment)
0x18007ccf4  mov     ebx, eax
0x18007ccf6  test    eax, eax
0x18007ccf8  js      short loc_18007CD09
0x18007ccfa  mov     ecx, [rsp+280h+var_240]
0x18007ccfe  mov     rdx, rdi
0x18007cd01  call    cs:__imp_?IsoGetProcessManager@@YAJKPEAK@Z; IsoGetProcessManager(ulong,ulong *)
0x18007cd07  mov     ebx, eax
0x18007cd09  mov     rcx, [rsp+280h+AppID]; pv
0x18007cd0e  call    cs:__imp_CoTaskMemFree
0x18007cd14  mov     eax, ebx
0x18007cd16  mov     rcx, [rbp+180h+var_40]
0x18007cd1d  xor     rcx, rsp; StackCookie
0x18007cd20  call    __security_check_cookie
0x18007cd25  mov     rbx, [rsp+280h+arg_0]
0x18007cd2d  add     rsp, 250h
0x18007cd34  pop     r15
0x18007cd36  pop     r14
0x18007cd38  pop     r13
0x18007cd3a  pop     r12
0x18007cd3c  pop     rdi
0x18007cd3d  pop     rsi
0x18007cd3e  pop     rbp
0x18007cd3f  retn
```
