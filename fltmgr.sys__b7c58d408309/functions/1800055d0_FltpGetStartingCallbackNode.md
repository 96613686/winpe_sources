# FltpGetStartingCallbackNode

- ea: `0x1800055d0`
- end: `0x180005a3f`
- name: `FltpGetStartingCallbackNode`
- size: `1135`
- prototype: `void __fastcall(struct _FILE_OBJECT *, _QWORD *, char)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180005460`
- `0x18001b800`

## callees

- `0x1800055d0`
- `0x180009f20`
- `0x180024c00`
- `0x18005cfe0`
- `0x180065d30`
- `0x18006ba60`

## import_xrefs

- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180005719`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180005719`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180005776`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180005776`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180005753`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180005753`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800057dd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800057dd`
- `ntoskrnl!ExReleaseFastResource` at `0x1800057d1`
- `ntoskrnl!ExReleaseFastResource` at `0x1800057d1`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x180005742`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x180005742`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180005731`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180005731`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180005892`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18000599b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180005892`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18000599b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800057fc`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800057fc`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1800057f0`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1800057f0`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x18000591c`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x18000591c`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x1800058cc`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x1800058cc`
- `ntoskrnl!FsRtlIsEcpFromUserMode` at `0x18000594f`
- `ntoskrnl!FsRtlIsEcpFromUserMode` at `0x18000594f`
- `ntoskrnl!FsRtlLookupPerFileObjectContext` at `0x180005621`
- `ntoskrnl!FsRtlLookupPerFileObjectContext` at `0x180005621`

## pseudocode

```c
void __fastcall FltpGetStartingCallbackNode(struct _FILE_OBJECT *a1, _QWORD *a2, char a3)
{
  int v3; // eax
  __int64 v4; // r15
  PFSRTL_PER_FILEOBJECT_CONTEXT v8; // rax
  __int64 v9; // rdx
  _BYTE *v10; // r13
  __int64 v11; // rsi
  __int64 v12; // r12
  __int64 v13; // rax
  unsigned int v14; // ecx
  bool v15; // zf
  __int16 v16; // ax
  unsigned __int8 v17; // al
  __int64 v18; // rdi
  struct _ECP_LIST *v19; // rsi
  __int64 v20; // rdi
  __int64 v21; // r8
  _LIST_ENTRY *v22; // rdi
  _LIST_ENTRY *p_EcpList; // r12
  unsigned __int8 v24; // si
  __int64 v25; // rax
  unsigned int EcpListFromIrp; // eax
  unsigned int ExtraCreateParameter; // eax
  __int64 v28; // rax
  PECP_LIST EcpList; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+28h] [rbp-A0h]
  __int64 v31; // [rsp+30h] [rbp-98h]
  _BYTE v32[80]; // [rsp+40h] [rbp-88h] BYREF
  __int64 EcpContextSize; // [rsp+D8h] [rbp+10h] BYREF
  PVOID EcpContext; // [rsp+E8h] [rbp+20h] BYREF

  v3 = *((_DWORD *)a2 + 10);
  v4 = 0;
  EcpContext = 0;
  if ( (v3 & 0x400) != 0 )
  {
    *((_DWORD *)a2 + 10) = v3 & 0xFFFFFBFF;
    return;
  }
  if ( a3 == -14 || a3 == -7 )
  {
    v25 = a2[2];
    EcpList = 0;
    LODWORD(EcpContextSize) = 0;
    EcpListFromIrp = FsRtlGetEcpListFromIrp(*(PIRP *)(*(_QWORD *)(v25 + 248) + 24LL), &EcpList);
    if ( (int)FltpDbgStatus(EcpListFromIrp, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 933, 0) < 0 )
      return;
    if ( !EcpList )
      return;
    ExtraCreateParameter = FsRtlFindExtraCreateParameter(
                             EcpList,
                             &FLTMGR_TIOCTRL_ECP_GUID,
                             &EcpContext,
                             (ULONG *)&EcpContextSize);
    if ( (int)FltpDbgStatus(ExtraCreateParameter, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 949, 0) < 0
      || FsRtlIsEcpFromUserMode(EcpContext) )
    {
      return;
    }
  }
  else
  {
    if ( !a1 )
      return;
    v8 = FsRtlLookupPerFileObjectContext(a1, DriverObject, 0);
    if ( !v8 )
      return;
    EcpContext = &v8[-1];
  }
  v9 = *a2;
  v10 = EcpContext;
  v11 = *(_QWORD *)(*a2 + 104LL);
  v31 = v11;
  switch ( *((_WORD *)EcpContext + 2) )
  {
    case 0:
      v12 = *((_QWORD *)EcpContext + 9);
      if ( !v12 )
        break;
      if ( *(_QWORD *)(*(_QWORD *)(v12 + 64) + 88LL) != *(_QWORD *)(v9 + 88) )
      {
        if ( (*((_BYTE *)EcpContext + 6) & 2) != 0 )
          *((_DWORD *)a2 + 10) |= 0x10u;
        break;
      }
      v13 = *((_QWORD *)EcpContext + 1);
      v14 = *(_DWORD *)(v11 + 24);
      v15 = v14 == *(_DWORD *)(v13 + 24);
      if ( v14 <= *(_DWORD *)(v13 + 24) )
      {
        v16 = *((_WORD *)EcpContext + 3);
        if ( v15 )
        {
          v15 = (v16 & 0x20) == 0;
          v17 = a3 + 22;
          if ( v15 )
          {
            LOBYTE(EcpContextSize) = a3 + 22;
          }
          else
          {
            EcpContextSize = v17;
            v18 = *(_QWORD *)(v12 + 8LL * v17 + 304);
            if ( !v18
              || (*(_DWORD *)(v12 + 80) & 6) != 0
              || !ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v12 + 56), 1u) )
            {
              v18 = 0;
            }
            a2[3] = v18;
          }
          if ( (v10[6] & 0x20) == 0 || !a2[3] )
          {
            memset(v32, 0, 0x48u);
            ExInitializeFastOwnerEntry(v32);
            v19 = *(struct _ECP_LIST **)(v12 + 64);
            v20 = qword_18003E9A0;
            KeEnterGuardedRegion();
            v30 = ExAcquireCacheAwarePushLockSharedEx(v20, 0);
            KeEnterCriticalRegion();
            LOBYTE(v21) = 1;
            EcpList = v19 + 8;
            ExAcquireFastResourceShared(&v19[8], v32, v21);
            v22 = *(_LIST_ENTRY **)(v12 + 16);
            p_EcpList = &v19[12].EcpList;
            if ( v22 != &v19[12].EcpList )
            {
              v24 = EcpContextSize;
              do
              {
                if ( ((__int64)v22[4].Flink & 6) == 0 )
                {
                  v4 = *((_QWORD *)&v22[18].Flink + v24);
                  if ( v4 )
                  {
                    if ( ExAcquireRundownProtectionCacheAwareEx((PEX_RUNDOWN_REF_CACHE_AWARE)v22[2].Blink, 1u) )
                      break;
                  }
                }
                v22 = v22->Flink;
                v4 = 0;
              }
              while ( v22 != p_EcpList );
            }
            ExReleaseFastResource(EcpList, v32);
            KeLeaveCriticalRegion();
            ExReleaseCacheAwarePushLockSharedEx(v30, 0);
            KeLeaveGuardedRegion();
            v11 = v31;
            a2[3] = v4;
          }
          if ( (v10[6] & 2) == 0 )
            break;
        }
        else if ( (v16 & 2) == 0 )
        {
          break;
        }
        goto LABEL_53;
      }
LABEL_49:
      a2[3] = 0;
      break;
    case 1:
      goto LABEL_49;
    case 2:
      v28 = *((_QWORD *)EcpContext + 8);
      if ( v28 && v28 != *(_QWORD *)(v9 + 88) )
      {
        if ( (*((_BYTE *)EcpContext + 6) & 2) == 0 )
          break;
        goto LABEL_53;
      }
      if ( *(_DWORD *)(v11 + 24) > *(_DWORD *)(*((_QWORD *)EcpContext + 1) + 24LL) )
        goto LABEL_49;
      if ( (*((_BYTE *)EcpContext + 6) & 2) != 0 )
LABEL_53:
        *((_DWORD *)a2 + 10) |= 0x10u;
      break;
  }
  if ( (a2[5] & 0x200) != 0 )
  {
    if ( a3 == 18 )
    {
      FltpCleanupFileObjectContextForCleanup(v11, EcpContext);
    }
    else if ( a3 == 2 )
    {
      FltpCleanupFileObjectContextForClose(v11, EcpContext);
      if ( !a2[3] )
        FltpCleanupStreamListCtrlForFileObjectClose(*a2, a1);
    }
  }
}

```

## disassembly

```asm
0x1800055d0  push    rbx
0x1800055d2  push    rbp
0x1800055d3  push    r14
0x1800055d5  push    r15
0x1800055d7  sub     rsp, 0A8h
0x1800055de  mov     eax, [rdx+28h]
0x1800055e1  xor     r15d, r15d
0x1800055e4  mov     [rsp+0C8h+EcpContext], r15
0x1800055ec  movzx   ebx, r8b
0x1800055f0  mov     r14, rdx
0x1800055f3  mov     rbp, rcx
0x1800055f6  bt      eax, 0Ah
0x1800055fa  jb      loc_1800059B4
0x180005600  cmp     bl, 0F2h
0x180005603  jz      loc_1800058AB
0x180005609  cmp     bl, 0F9h
0x18000560c  jz      loc_1800058AB
0x180005612  test    rcx, rcx
0x180005615  jz      short loc_180005632
0x180005617  mov     rdx, cs:DriverObject; OwnerId
0x18000561e  xor     r8d, r8d; InstanceId
0x180005621  call    cs:__imp_FsRtlLookupPerFileObjectContext
0x180005628  nop     dword ptr [rax+rax+00h]
0x18000562d  test    rax, rax
0x180005630  jnz     short loc_180005641
0x180005632  add     rsp, 0A8h
0x180005639  pop     r15
0x18000563b  pop     r14
0x18000563d  pop     rbp
0x18000563e  pop     rbx
0x18000563f  retn
0x180005641  add     rax, 0FFFFFFFFFFFFFFE0h
0x180005645  mov     [rsp+0C8h+EcpContext], rax
0x18000564d  mov     rdx, [r14]
0x180005650  mov     [rsp+0C8h+arg_0], rsi
0x180005658  mov     [rsp+0C8h+var_30], r12
0x180005660  mov     [rsp+0C8h+var_38], r13
0x180005668  mov     r13, [rsp+0C8h+EcpContext]
0x180005670  mov     rsi, [rdx+68h]
0x180005674  mov     [rsp+0C8h+var_98], rsi
0x180005679  movzx   ecx, word ptr [r13+4]
0x18000567e  test    ecx, ecx
0x180005680  jnz     loc_1800059D6
0x180005686  mov     r12, [r13+48h]
0x18000568a  test    r12, r12
0x18000568d  jz      loc_180005824
0x180005693  mov     rcx, [r12+40h]
0x180005698  mov     rax, [rdx+58h]
0x18000569c  cmp     [rcx+58h], rax
0x1800056a0  jnz     loc_1800059E4
0x1800056a6  mov     rax, [r13+8]
0x1800056aa  mov     ecx, [rsi+18h]
0x1800056ad  cmp     ecx, [rax+18h]
0x1800056b0  ja      loc_1800059DB
0x1800056b6  movzx   eax, word ptr [r13+6]
0x1800056bb  jnz     loc_180005968
0x1800056c1  test    al, 20h
0x1800056c3  mov     [rsp+0C8h+var_28], rdi
0x1800056cb  lea     eax, [rbx+16h]
0x1800056ce  jz      loc_1800059CA
0x1800056d4  movzx   edi, al
0x1800056d7  mov     [rsp+0C8h+EcpContextSize], rdi
0x1800056df  mov     rdi, [r12+rdi*8+130h]
0x1800056e7  test    rdi, rdi
0x1800056ea  jnz     loc_180005984
0x1800056f0  mov     rdi, r15
0x1800056f3  mov     [r14+18h], rdi
0x1800056f7  test    byte ptr [r13+6], 20h
0x1800056fc  jnz     loc_180005975
0x180005702  xor     edx, edx; Val
0x180005704  lea     rcx, [rsp+0C8h+var_88]; void *
0x180005709  mov     r8d, 48h ; 'H'; Size
0x18000570f  call    memset
0x180005714  lea     rcx, [rsp+0C8h+var_88]
0x180005719  call    cs:__imp_ExInitializeFastOwnerEntry
0x180005720  nop     dword ptr [rax+rax+00h]
0x180005725  mov     rsi, [r12+40h]
0x18000572a  mov     rdi, cs:qword_18003E9A0
0x180005731  call    cs:__imp_KeEnterGuardedRegion
0x180005738  nop     dword ptr [rax+rax+00h]
0x18000573d  xor     edx, edx
0x18000573f  mov     rcx, rdi
0x180005742  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x180005749  nop     dword ptr [rax+rax+00h]
0x18000574e  mov     [rsp+0C8h+var_A0], rax
0x180005753  call    cs:__imp_KeEnterCriticalRegion
0x18000575a  nop     dword ptr [rax+rax+00h]
0x18000575f  lea     rax, [rsi+0C0h]
0x180005766  mov     r8b, 1
0x180005769  mov     rcx, rax
0x18000576c  mov     [rsp+0C8h+EcpList], rax
0x180005771  lea     rdx, [rsp+0C8h+var_88]
0x180005776  call    cs:__imp_ExAcquireFastResourceShared
0x18000577d  nop     dword ptr [rax+rax+00h]
0x180005782  mov     rdi, [r12+10h]
0x180005787  lea     r12, [rsi+128h]
0x18000578e  cmp     rdi, r12
0x180005791  jz      short loc_1800057C7
0x180005793  mov     rsi, [rsp+0C8h+EcpContextSize]
0x18000579b  nop     dword ptr [rax+rax+00h]
0x1800057a0  mov     eax, [rdi+40h]
0x1800057a3  test    al, 6
0x1800057a5  jnz     short loc_1800057BC
0x1800057a7  movzx   eax, sil
0x1800057ab  mov     r15, [rdi+rax*8+120h]
0x1800057b3  test    r15, r15
0x1800057b6  jnz     loc_180005889
0x1800057bc  mov     rdi, [rdi]
0x1800057bf  xor     r15d, r15d
0x1800057c2  cmp     rdi, r12
0x1800057c5  jnz     short loc_1800057A0
0x1800057c7  mov     rcx, [rsp+0C8h+EcpList]
0x1800057cc  lea     rdx, [rsp+0C8h+var_88]
0x1800057d1  call    cs:__imp_ExReleaseFastResource
0x1800057d8  nop     dword ptr [rax+rax+00h]
0x1800057dd  call    cs:__imp_KeLeaveCriticalRegion
0x1800057e4  nop     dword ptr [rax+rax+00h]
0x1800057e9  mov     rcx, [rsp+0C8h+var_A0]
0x1800057ee  xor     edx, edx
0x1800057f0  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1800057f7  nop     dword ptr [rax+rax+00h]
0x1800057fc  call    cs:__imp_KeLeaveGuardedRegion
0x180005803  nop     dword ptr [rax+rax+00h]
0x180005808  mov     rsi, [rsp+0C8h+var_98]
0x18000580d  mov     [r14+18h], r15
0x180005811  test    byte ptr [r13+6], 2
0x180005816  mov     rdi, [rsp+0C8h+var_28]
0x18000581e  jnz     loc_180005A04
0x180005824  test    dword ptr [r14+28h], 200h
0x18000582c  mov     r13, [rsp+0C8h+var_38]
0x180005834  mov     r12, [rsp+0C8h+var_30]
0x18000583c  jz      short loc_18000587C
0x18000583e  cmp     bl, 12h
0x180005841  jz      short loc_18000586C
0x180005843  cmp     bl, 2
0x180005846  jnz     short loc_18000587C
0x180005848  mov     rdx, [rsp+0C8h+EcpContext]
0x180005850  mov     rcx, rsi
0x180005853  call    FltpCleanupFileObjectContextForClose
0x180005858  cmp     qword ptr [r14+18h], 0
0x18000585d  jnz     short loc_18000587C
0x18000585f  mov     rcx, [r14]
0x180005862  mov     rdx, rbp
0x180005865  call    FltpCleanupStreamListCtrlForFileObjectClose
0x18000586a  jmp     short loc_18000587C
0x18000586c  mov     rdx, [rsp+0C8h+EcpContext]
0x180005874  mov     rcx, rsi
0x180005877  call    FltpCleanupFileObjectContextForCleanup
0x18000587c  mov     rsi, [rsp+0C8h+arg_0]
0x180005884  jmp     loc_180005632
0x180005889  mov     rcx, [rdi+28h]; RunRefCacheAware
0x18000588d  mov     edx, 1; Count
0x180005892  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x180005899  nop     dword ptr [rax+rax+00h]
0x18000589e  test    al, al
0x1800058a0  jz      loc_1800057BC
0x1800058a6  jmp     loc_1800057C7
0x1800058ab  mov     rax, [rdx+10h]
0x1800058af  lea     rdx, [rsp+0C8h+EcpList]; EcpList
0x1800058b4  mov     [rsp+0C8h+EcpList], r15
0x1800058b9  mov     dword ptr [rsp+0C8h+EcpContextSize], r15d
0x1800058c1  mov     rcx, [rax+0F8h]
0x1800058c8  mov     rcx, [rcx+18h]; Irp
0x1800058cc  call    cs:__imp_FsRtlGetEcpListFromIrp
0x1800058d3  nop     dword ptr [rax+rax+00h]
0x1800058d8  mov     r8d, 3A5h
0x1800058de  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x1800058e5  mov     ecx, eax
0x1800058e7  xor     r9d, r9d
0x1800058ea  call    FltpDbgStatus
0x1800058ef  test    eax, eax
0x1800058f1  js      loc_180005632
0x1800058f7  mov     rcx, [rsp+0C8h+EcpList]; EcpList
0x1800058fc  test    rcx, rcx
0x1800058ff  jz      loc_180005632
0x180005905  lea     r9, [rsp+0C8h+EcpContextSize]; EcpContextSize
0x18000590d  lea     r8, [rsp+0C8h+EcpContext]; EcpContext
0x180005915  lea     rdx, FLTMGR_TIOCTRL_ECP_GUID; EcpType
0x18000591c  call    cs:__imp_FsRtlFindExtraCreateParameter
0x180005923  nop     dword ptr [rax+rax+00h]
0x180005928  mov     r8d, 3B5h
0x18000592e  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x180005935  mov     ecx, eax
0x180005937  xor     r9d, r9d
0x18000593a  call    FltpDbgStatus
0x18000593f  test    eax, eax
0x180005941  js      loc_180005632
0x180005947  mov     rcx, [rsp+0C8h+EcpContext]; EcpContext
0x18000594f  call    cs:__imp_FsRtlIsEcpFromUserMode
0x180005956  nop     dword ptr [rax+rax+00h]
0x18000595b  test    al, al
0x18000595d  jnz     loc_180005632
0x180005963  jmp     loc_18000564D
0x180005968  test    al, 2
0x18000596a  jz      loc_180005824
0x180005970  jmp     loc_180005A04
0x180005975  cmp     [r14+18h], r15
0x180005979  jnz     loc_180005811
0x18000597f  jmp     loc_180005702
0x180005984  mov     eax, [r12+50h]
0x180005989  test    al, 6
0x18000598b  jnz     loc_1800056F0
0x180005991  mov     rcx, [r12+38h]; RunRefCacheAware
0x180005996  mov     edx, 1; Count
0x18000599b  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1800059a2  nop     dword ptr [rax+rax+00h]
0x1800059a7  test    al, al
0x1800059a9  jnz     loc_1800056F3
0x1800059af  jmp     loc_1800056F0
0x1800059b4  btr     eax, 0Ah
0x1800059b8  mov     [rdx+28h], eax
0x1800059bb  add     rsp, 0A8h
0x1800059c2  pop     r15
0x1800059c4  pop     r14
0x1800059c6  pop     rbp
0x1800059c7  pop     rbx
0x1800059c8  retn
0x1800059ca  mov     byte ptr [rsp+0C8h+EcpContextSize], al
0x1800059d1  jmp     loc_1800056F7
0x1800059d6  sub     ecx, 1
0x1800059d9  jnz     short loc_180005A0E
0x1800059db  mov     [r14+18h], r15
0x1800059df  jmp     loc_180005824
0x1800059e4  test    byte ptr [r13+6], 2
0x1800059e9  jz      loc_180005824
0x1800059ef  or      dword ptr [r14+28h], 10h
0x1800059f4  jmp     loc_180005824
0x1800059f9  test    byte ptr [r13+6], 2
0x1800059fe  jz      loc_180005824
0x180005a04  or      dword ptr [r14+28h], 10h
0x180005a09  jmp     loc_180005824
0x180005a0e  cmp     ecx, 1
0x180005a11  jnz     loc_180005824
0x180005a17  mov     rax, [r13+40h]
0x180005a1b  test    rax, rax
0x180005a1e  jz      short loc_180005A26
0x180005a20  cmp     rax, [rdx+58h]
0x180005a24  jnz     short loc_1800059F9
0x180005a26  mov     rax, [r13+8]
0x180005a2a  mov     ecx, [rax+18h]
0x180005a2d  cmp     [rsi+18h], ecx
0x180005a30  ja      short loc_1800059DB
0x180005a32  test    byte ptr [r13+6], 2
0x180005a37  jz      loc_180005824
0x180005a3d  jmp     short loc_180005A04
```
