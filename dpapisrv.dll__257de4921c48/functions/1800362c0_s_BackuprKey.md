# s_BackuprKey

- ea: `0x1800362c0`
- end: `0x180036770`
- name: `s_BackuprKey`
- size: `1200`
- prototype: `unsigned int __fastcall(RPC_BINDING_HANDLE BindingHandle, _QWORD *, struct _GUID *, unsigned __int8 *, unsigned __int8 **, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000145c`
- `0x180007f10`
- `0x18000b680`
- `0x18001467c`
- `0x180023d84`
- `0x18002fab8`
- `0x180030df0`
- `0x18003325c`
- `0x18003442c`
- `0x180035460`
- `0x180035c00`
- `0x180035dd4`
- `0x1800362c0`
- `0x180036778`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800363a4`
- `RPCRT4!RpcImpersonateClient` at `0x1800363a4`
- `RPCRT4!RpcRevertToSelf` at `0x180036441`
- `RPCRT4!RpcRevertToSelf` at `0x180036441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800366bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800366bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800363f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800363f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800363da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800363da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036753`

## string_xrefs

- `0x180036357`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180036380`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800363c0`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180036420`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180036462`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800364fa`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x18003658e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800365c9`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x18003664b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x18003667e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800366f0`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
unsigned int __fastcall s_BackuprKey(
        RPC_BINDING_HANDLE BindingHandle,
        _QWORD *a2,
        struct _GUID *a3,
        unsigned __int8 *a4,
        unsigned __int8 **a5,
        unsigned __int8 **a6)
{
  unsigned int v6; // edi
  unsigned int valid; // eax
  DWORD LastError; // ebx
  unsigned int v13; // eax
  HANDLE CurrentThread; // rax
  BOOL v15; // r12d
  unsigned int v16; // eax
  int v17; // eax
  int v18; // edx
  int v19; // ecx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  unsigned int *v23; // [rsp+30h] [rbp-68h]
  unsigned int v24; // [rsp+38h] [rbp-60h]
  unsigned __int8 *v25; // [rsp+48h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-48h] BYREF
  _QWORD *v27; // [rsp+58h] [rbp-40h] BYREF

  v6 = (unsigned int)a4;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
    return BeforeKeyRotation::s_BackuprKey(BindingHandle, a2, a3, (unsigned __int8 *)v6, (unsigned int)a5, a6, v23, v24);
  TokenHandle = 0;
  v25 = 0;
  if ( !g_fBackupKeyServerStarted )
    return 87;
  valid = VerifyRpcValidSecurityLevel(BindingHandle);
  LastError = valid;
  if ( valid )
  {
    DebugTraceError(valid, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 442);
    goto LABEL_54;
  }
  if ( !CPreferredKeys::Setup() )
  {
    DebugTraceError(
      87,
      "ERROR_INVALID_PARAMETER",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
      452);
    return 87;
  }
  v13 = RpcImpersonateClient(BindingHandle);
  LastError = v13;
  if ( v13 )
  {
    DebugTraceError(v13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 465);
    goto LABEL_54;
  }
  CurrentThread = GetCurrentThread();
  v15 = OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle);
  if ( !v15 )
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 479);
  }
  v16 = RpcRevertToSelf();
  if ( v16 )
  {
    if ( v15 )
    {
      LastError = v16;
      DebugTraceError(v16, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 485);
    }
    goto LABEL_54;
  }
  if ( v15 )
  {
    if ( *a2 == 0x499B2FC747270C64LL && a2[1] == 0x9A89CECD370E5BACuLL )
    {
      if ( v6 < 4 )
      {
        LastError = 87;
        goto LABEL_54;
      }
      if ( a3->Data1 == 1 )
        goto LABEL_23;
      if ( a3->Data1 - 2 > 1 )
      {
        LastError = 87;
        DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 532);
        goto LABEL_54;
      }
      v18 = 0;
    }
    else
    {
      if ( *a2 == 0x11D1178E7F752B10LL && a2[1] == 0x40DB145F80008FABLL )
      {
        v17 = BackupToRecoverableBlobW2K(TokenHandle, (unsigned __int8 *)a3, v6, &v25, (unsigned int *)a6);
        goto LABEL_46;
      }
      if ( *a2 != 0x11D1178E7FE94D50LL || a2[1] != 0x40DB145F80008FABLL )
      {
        if ( *a2 != 0x40C6EABA018FF48ALL || a2[1] != 0x67E9400237726D8FLL )
        {
          LastError = 87;
          DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 626);
          if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
          {
            v27 = a2;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
              v20,
              (unsigned int)byte_180045193,
              v21,
              v22,
              (__int64)&v27);
          }
          goto LABEL_54;
        }
        if ( (unsigned int)FIsLegacyCompliant() )
        {
          LastError = 50;
          DebugTraceError(50, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 610);
          goto LABEL_54;
        }
        UpdateGlobals(v19);
        if ( !dword_18004CCAC )
        {
          LastError = 50;
          DebugTraceError(50, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 617);
          goto LABEL_54;
        }
        v17 = CPreferredKeys::CopyPublicKey(&v25, (unsigned int *)a6);
LABEL_46:
        if ( v17 )
        {
          *a5 = v25;
        }
        else
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 2;
        }
        goto LABEL_54;
      }
      if ( v6 < 4 )
      {
        LastError = 87;
        DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 562);
        goto LABEL_54;
      }
      if ( a3->Data1 == 1 )
      {
LABEL_23:
        v17 = RestoreFromRecoverableBlobW2K(TokenHandle, (unsigned __int8 *)a3, v6, &v25, (unsigned int *)a6);
        goto LABEL_46;
      }
      if ( a3->Data1 - 2 > 1 )
      {
        LastError = 87;
        DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 596);
        goto LABEL_54;
      }
      v18 = 1;
    }
    v17 = RestoreFromRecoverableBlob(TokenHandle, v18, (unsigned __int8 *)a3, v6, &v25, (unsigned int *)a6);
    goto LABEL_46;
  }
LABEL_54:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800362c0  push    rbx
0x1800362c2  push    rsi
0x1800362c3  push    rdi
0x1800362c4  push    r12
0x1800362c6  push    r14
0x1800362c8  push    r15
0x1800362ca  sub     rsp, 68h
0x1800362ce  mov     edi, r9d
0x1800362d1  mov     r15, r8
0x1800362d4  mov     r14, rdx
0x1800362d7  mov     rsi, rcx
0x1800362da  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation> `wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl(void)'::`2'::impl
0x1800362e1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled(void)
0x1800362e6  test    al, al
0x1800362e8  jnz     short loc_18003631A
0x1800362ea  mov     rax, [rsp+98h+arg_28]
0x1800362f2  mov     [rsp+98h+var_70], rax; unsigned __int8 **
0x1800362f7  mov     rax, [rsp+98h+arg_20]
0x1800362ff  mov     [rsp+98h+var_78], rax; unsigned int
0x180036304  mov     r9d, edi; unsigned __int8 *
0x180036307  mov     r8, r15; struct _GUID *
0x18003630a  mov     rdx, r14; void *
0x18003630d  mov     rcx, rsi; BindingHandle
0x180036310  call    ?s_BackuprKey@BeforeKeyRotation@@YAKPEAXPEAU_GUID@@PEAEKPEAPEAEPEAKK@Z; BeforeKeyRotation::s_BackuprKey(void *,_GUID *,uchar *,ulong,uchar * *,ulong *,ulong)
0x180036315  jmp     loc_180036761
0x18003631a  mov     [rsp+98h+TokenHandle], 0
0x180036323  mov     [rsp+98h+var_50], 0
0x18003632c  cmp     cs:?g_fBackupKeyServerStarted@@3HA, 0; int g_fBackupKeyServerStarted
0x180036333  jnz     short loc_18003633F
0x180036335  mov     eax, 57h ; 'W'
0x18003633a  jmp     loc_180036761
0x18003633f  mov     rcx, rsi; void *
0x180036342  call    ?VerifyRpcValidSecurityLevel@@YAKPEAX@Z; VerifyRpcValidSecurityLevel(void *)
0x180036347  mov     ebx, eax
0x180036349  mov     [rsp+98h+var_58], eax
0x18003634d  test    eax, eax
0x18003634f  jz      short loc_180036371
0x180036351  mov     r9d, 1BAh
0x180036357  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18003635e  lea     rdx, aDwlasterror; "dwLastError"
0x180036365  mov     ecx, eax
0x180036367  call    DebugTraceError
0x18003636c  jmp     loc_180036749
0x180036371  call    ?Setup@CPreferredKeys@@SA_NXZ; CPreferredKeys::Setup(void)
0x180036376  test    al, al
0x180036378  jnz     short loc_1800363A1
0x18003637a  mov     r9d, 1C4h
0x180036380  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180036387  lea     rdx, aErrorInvalidPa; "ERROR_INVALID_PARAMETER"
0x18003638e  mov     edi, 57h ; 'W'
0x180036393  mov     ecx, edi
0x180036395  call    DebugTraceError
0x18003639a  mov     eax, edi
0x18003639c  jmp     loc_180036761
0x1800363a1  mov     rcx, rsi; BindingHandle
0x1800363a4  call    cs:__imp_RpcImpersonateClient
0x1800363ab  nop     dword ptr [rax+rax+00h]
0x1800363b0  mov     ebx, eax
0x1800363b2  mov     [rsp+98h+var_58], eax
0x1800363b6  test    eax, eax
0x1800363b8  jz      short loc_1800363DA
0x1800363ba  mov     r9d, 1D1h
0x1800363c0  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800363c7  lea     rdx, aDwlasterror; "dwLastError"
0x1800363ce  mov     ecx, eax
0x1800363d0  call    DebugTraceError
0x1800363d5  jmp     loc_180036749
0x1800363da  call    cs:__imp_GetCurrentThread
0x1800363e1  nop     dword ptr [rax+rax+00h]
0x1800363e6  mov     rcx, rax; ThreadHandle
0x1800363e9  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x1800363ee  xor     r8d, r8d; OpenAsSelf
0x1800363f1  lea     edx, [r8+8]; DesiredAccess
0x1800363f5  call    cs:__imp_OpenThreadToken
0x1800363fc  nop     dword ptr [rax+rax+00h]
0x180036401  mov     r12d, eax
0x180036404  test    eax, eax
0x180036406  jnz     short loc_18003643A
0x180036408  call    cs:__imp_GetLastError
0x18003640f  nop     dword ptr [rax+rax+00h]
0x180036414  mov     ebx, eax
0x180036416  mov     [rsp+98h+var_58], eax
0x18003641a  mov     r9d, 1DFh
0x180036420  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180036427  lea     rsi, aDwlasterror; "dwLastError"
0x18003642e  mov     rdx, rsi
0x180036431  mov     ecx, eax
0x180036433  call    DebugTraceError
0x180036438  jmp     short loc_180036441
0x18003643a  lea     rsi, aDwlasterror; "dwLastError"
0x180036441  call    cs:__imp_RpcRevertToSelf
0x180036448  nop     dword ptr [rax+rax+00h]
0x18003644d  test    eax, eax
0x18003644f  jz      short loc_180036478
0x180036451  test    r12d, r12d
0x180036454  jz      short loc_18003647D
0x180036456  mov     ebx, eax
0x180036458  mov     [rsp+98h+var_58], eax
0x18003645c  mov     r9d, 1E5h
0x180036462  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180036469  mov     rdx, rsi
0x18003646c  mov     ecx, eax
0x18003646e  call    DebugTraceError
0x180036473  jmp     loc_180036749
0x180036478  test    r12d, r12d
0x18003647b  jnz     short loc_180036482
0x18003647d  jmp     loc_180036749
0x180036482  mov     rax, [r14]
0x180036485  cmp     rax, cs:qword_180043898
0x18003648c  jnz     loc_180036517
0x180036492  mov     rax, [r14+8]
0x180036496  cmp     rax, cs:qword_1800438A0
0x18003649d  jnz     short loc_180036517
0x18003649f  cmp     edi, 4
0x1800364a2  jnb     short loc_1800364B2
0x1800364a4  mov     ebx, 57h ; 'W'
0x1800364a9  mov     [rsp+98h+var_58], ebx
0x1800364ad  jmp     loc_180036749
0x1800364b2  mov     eax, [r15]
0x1800364b5  cmp     eax, 1
0x1800364b8  jnz     short loc_1800364E1
0x1800364ba  mov     rax, [rsp+98h+arg_28]
0x1800364c2  mov     [rsp+98h+var_78], rax; unsigned int *
0x1800364c7  lea     r9, [rsp+98h+var_50]; unsigned __int8 **
0x1800364cc  mov     r8d, edi; unsigned int
0x1800364cf  mov     rdx, r15; unsigned __int8 *
0x1800364d2  mov     rcx, [rsp+98h+TokenHandle]; void *
0x1800364d7  call    ?RestoreFromRecoverableBlobW2K@@YAHPEAXPEAEKPEAPEAEPEAK@Z; RestoreFromRecoverableBlobW2K(void *,uchar *,ulong,uchar * *,ulong *)
0x1800364dc  jmp     loc_1800366A7
0x1800364e1  add     eax, 0FFFFFFFEh
0x1800364e4  cmp     eax, 1
0x1800364e7  jbe     short loc_180036510
0x1800364e9  mov     edi, 57h ; 'W'
0x1800364ee  mov     ebx, edi
0x1800364f0  mov     [rsp+98h+var_58], ebx
0x1800364f4  mov     r9d, 214h
0x1800364fa  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180036501  mov     rdx, rsi
0x180036504  mov     ecx, edi
0x180036506  call    DebugTraceError
0x18003650b  jmp     loc_180036749
0x180036510  xor     edx, edx
0x180036512  jmp     loc_1800365E4
0x180036517  mov     rax, [r14]
0x18003651a  cmp     rax, cs:qword_180043868
0x180036521  jnz     short loc_180036557
0x180036523  mov     rax, [r14+8]
0x180036527  cmp     rax, cs:qword_180043870
0x18003652e  jnz     short loc_180036557
0x180036530  mov     rax, [rsp+98h+arg_28]
0x180036538  mov     [rsp+98h+var_78], rax; unsigned int *
0x18003653d  lea     r9, [rsp+98h+var_50]; unsigned __int8 **
0x180036542  mov     r8d, edi; unsigned int
0x180036545  mov     rdx, r15; unsigned __int8 *
0x180036548  mov     rcx, [rsp+98h+TokenHandle]; void *
0x18003654d  call    ?BackupToRecoverableBlobW2K@@YAHPEAXPEAEKPEAPEAEPEAK@Z; BackupToRecoverableBlobW2K(void *,uchar *,ulong,uchar * *,ulong *)
0x180036552  jmp     loc_1800366A7
0x180036557  mov     rax, [r14]
0x18003655a  cmp     rax, cs:qword_180043888
0x180036561  jnz     loc_180036610
0x180036567  mov     rax, [r14+8]
0x18003656b  cmp     rax, cs:qword_180043890
0x180036572  jnz     loc_180036610
0x180036578  cmp     edi, 4
0x18003657b  jnb     short loc_1800365A4
0x18003657d  mov     edi, 57h ; 'W'
0x180036582  mov     ebx, edi
0x180036584  mov     [rsp+98h+var_58], ebx
0x180036588  mov     r9d, 232h
0x18003658e  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180036595  mov     rdx, rsi
0x180036598  mov     ecx, edi
0x18003659a  call    DebugTraceError
0x18003659f  jmp     loc_180036749
0x1800365a4  mov     eax, [r15]
0x1800365a7  cmp     eax, 1
0x1800365aa  jz      loc_1800364BA
0x1800365b0  add     eax, 0FFFFFFFEh
0x1800365b3  cmp     eax, 1
0x1800365b6  jbe     short loc_1800365DF
0x1800365b8  mov     edi, 57h ; 'W'
0x1800365bd  mov     ebx, edi
0x1800365bf  mov     [rsp+98h+var_58], ebx
0x1800365c3  mov     r9d, 254h
0x1800365c9  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800365d0  mov     rdx, rsi
0x1800365d3  mov     ecx, edi
0x1800365d5  call    DebugTraceError
0x1800365da  jmp     loc_180036749
0x1800365df  mov     edx, 1; int
0x1800365e4  mov     rax, [rsp+98h+arg_28]
0x1800365ec  mov     [rsp+98h+var_70], rax; unsigned int *
0x1800365f1  lea     rax, [rsp+98h+var_50]
0x1800365f6  mov     r8, r15; unsigned __int8 *
0x1800365f9  mov     r9d, edi; unsigned int
0x1800365fc  mov     [rsp+98h+var_78], rax; unsigned __int8 **
0x180036601  mov     rcx, [rsp+98h+TokenHandle]; void *
0x180036606  call    ?RestoreFromRecoverableBlob@@YAHPEAXHPEAEKPEAPEAEPEAK@Z; RestoreFromRecoverableBlob(void *,int,uchar *,ulong,uchar * *,ulong *)
0x18003660b  jmp     loc_1800366A7
0x180036610  mov     rax, [r14]
0x180036613  cmp     rax, cs:qword_180043848
0x18003661a  jnz     loc_1800366DF
0x180036620  mov     rax, [r14+8]
0x180036624  cmp     rax, cs:qword_180043850
0x18003662b  jnz     loc_1800366DF
0x180036631  call    ?FIsLegacyCompliant@@YAHXZ; FIsLegacyCompliant(void)
0x180036636  test    eax, eax
0x180036638  jz      short loc_18003665F
0x18003663a  mov     ecx, 32h ; '2'
0x18003663f  mov     ebx, ecx
0x180036641  mov     [rsp+98h+var_58], ecx
0x180036645  mov     r9d, 262h
0x18003664b  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180036652  mov     rdx, rsi
0x180036655  call    DebugTraceError
0x18003665a  jmp     loc_180036749
0x18003665f  call    ?UpdateGlobals@@YAKH@Z; UpdateGlobals(int)
0x180036664  cmp     cs:dword_18004CCAC, 0
0x18003666b  jnz     short loc_180036692
0x18003666d  mov     ecx, 32h ; '2'
0x180036672  mov     ebx, ecx
0x180036674  mov     [rsp+98h+var_58], ecx
0x180036678  mov     r9d, 269h
0x18003667e  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180036685  mov     rdx, rsi
0x180036688  call    DebugTraceError
0x18003668d  jmp     loc_180036749
0x180036692  mov     rdx, [rsp+98h+arg_28]; unsigned int *
0x18003669a  lea     rcx, [rsp+98h+var_50]; unsigned __int8 **
0x18003669f  call    ?CopyPublicKey@CPreferredKeys@@SA_NPEAPEAEPEAK@Z; CPreferredKeys::CopyPublicKey(uchar * *,ulong *)
0x1800366a4  movzx   eax, al
0x1800366a7  test    eax, eax
0x1800366a9  jz      short loc_1800366BD
0x1800366ab  mov     rcx, [rsp+98h+var_50]
0x1800366b0  mov     rax, [rsp+98h+arg_20]
0x1800366b8  mov     [rax], rcx
0x1800366bb  jmp     short loc_1800366DD
0x1800366bd  call    cs:__imp_GetLastError
0x1800366c4  nop     dword ptr [rax+rax+00h]
0x1800366c9  mov     ebx, eax
0x1800366cb  mov     [rsp+98h+var_58], eax
0x1800366cf  mov     eax, 2
0x1800366d4  test    ebx, ebx
0x1800366d6  cmovz   ebx, eax
0x1800366d9  mov     [rsp+98h+var_58], ebx
0x1800366dd  jmp     short loc_180036749
0x1800366df  mov     edi, 57h ; 'W'
0x1800366e4  mov     ebx, edi
0x1800366e6  mov     [rsp+98h+var_58], ebx
0x1800366ea  mov     r9d, 272h
0x1800366f0  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800366f7  mov     rdx, rsi
0x1800366fa  mov     ecx, edi
0x1800366fc  call    DebugTraceError
0x180036701  mov     eax, cs:dword_18004C260
0x180036707  cmp     eax, 5
0x18003670a  jbe     short loc_180036741
0x18003670c  mov     rdx, 400000000000h
0x180036716  lea     rcx, dword_18004C260
0x18003671d  call    _tlgKeywordOn
0x180036722  test    al, al
0x180036724  jz      short loc_180036741
0x180036726  mov     [rsp+98h+var_40], r14
0x18003672b  lea     rax, [rsp+98h+var_40]
0x180036730  mov     [rsp+98h+var_78], rax
0x180036735  lea     rdx, byte_180045193
0x18003673c  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x180036741  jmp     short loc_180036749
0x180036743  mov     ebx, eax
0x180036745  mov     [rsp+98h+var_58], eax
0x180036749  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x18003674e  test    rcx, rcx
0x180036751  jz      short loc_18003675F
0x180036753  call    cs:__imp_CloseHandle
0x18003675a  nop     dword ptr [rax+rax+00h]
0x18003675f  mov     eax, ebx
0x180036761  add     rsp, 68h
0x180036765  pop     r15
0x180036767  pop     r14
0x180036769  pop     r12
0x18003676b  pop     rdi
0x18003676c  pop     rsi
0x18003676d  pop     rbx
0x18003676e  retn
```
