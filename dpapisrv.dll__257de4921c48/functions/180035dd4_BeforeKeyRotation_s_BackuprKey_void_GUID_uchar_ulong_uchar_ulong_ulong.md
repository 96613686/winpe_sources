# BeforeKeyRotation::s_BackuprKey(void *,_GUID *,uchar *,ulong,uchar * *,ulong *,ulong)

- ea: `0x180035dd4`
- end: `0x1800362b0`
- name: `?s_BackuprKey@BeforeKeyRotation@@YAKPEAXPEAU_GUID@@PEAEKPEAPEAEPEAKK@Z`
- size: `1244`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, _QWORD *, struct _GUID *, unsigned __int8 *, _QWORD *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800362c0`

## callees

- `0x180007f10`
- `0x18000b680`
- `0x18002ffac`
- `0x180033b04`
- `0x1800349e4`
- `0x1800354c8`
- `0x180035c00`
- `0x180035dd4`
- `0x180036778`
- `0x18003c62c`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180035e75`
- `RPCRT4!RpcImpersonateClient` at `0x180035e75`
- `RPCRT4!RpcRevertToSelf` at `0x180035f1c`
- `RPCRT4!RpcRevertToSelf` at `0x180035f1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036224`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035ec6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035ec6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035eab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035eab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800361a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800361a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036291`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036291`

## string_xrefs

- `0x180035e2a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180035e53`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180035e91`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180035ef1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180035f0e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall BeforeKeyRotation::s_BackuprKey(
        RPC_BINDING_HANDLE BindingHandle,
        _QWORD *a2,
        struct _GUID *a3,
        unsigned __int8 *a4,
        _QWORD *a5,
        unsigned __int8 **a6)
{
  unsigned int v6; // r15d
  unsigned int valid; // eax
  BeforeKeyRotation *v12; // rcx
  DWORD LastError; // ebx
  unsigned int v14; // eax
  HANDLE CurrentThread; // rax
  BOOL v16; // r13d
  unsigned int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  int v20; // ecx
  int v21; // ecx
  unsigned int v22; // r8d
  HLOCAL v23; // r9
  unsigned int *v24; // [rsp+28h] [rbp-60h]
  unsigned int *v25; // [rsp+30h] [rbp-58h]
  unsigned int v26[2]; // [rsp+38h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-48h] BYREF

  v6 = (unsigned int)a4;
  TokenHandle = 0;
  *(_QWORD *)v26 = 0;
  if ( !g_fBackupKeyServerStarted )
    return 87;
  valid = VerifyRpcValidSecurityLevel(BindingHandle);
  LastError = valid;
  if ( valid )
  {
    DebugTraceError(valid, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6398);
    goto LABEL_57;
  }
  if ( !BeforeKeyRotation::SetupPreferredBackupKeys(v12) )
  {
    DebugTraceError(
      87,
      "ERROR_INVALID_PARAMETER",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
      6408);
    return 87;
  }
  v14 = RpcImpersonateClient(BindingHandle);
  LastError = v14;
  LODWORD(v25) = v14;
  if ( v14 )
  {
    DebugTraceError(v14, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6421);
    goto LABEL_57;
  }
  CurrentThread = GetCurrentThread();
  v16 = OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle);
  if ( !v16 )
  {
    LastError = GetLastError();
    LODWORD(v25) = LastError;
    DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6435);
  }
  v17 = RpcRevertToSelf();
  if ( v17 )
  {
    if ( v16 )
    {
      LastError = v17;
      DebugTraceError(v17, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6441);
    }
    goto LABEL_57;
  }
  if ( v16 )
  {
    if ( *a2 == 0x499B2FC747270C64LL && a2[1] == 0x9A89CECD370E5BACuLL )
    {
      if ( v6 < 4 )
      {
        LastError = 87;
        goto LABEL_57;
      }
      if ( a3->Data1 == 1 )
        goto LABEL_21;
      if ( a3->Data1 - 2 > 1 )
      {
        LastError = 87;
        DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6488);
        goto LABEL_57;
      }
      v19 = 0;
    }
    else
    {
      if ( *a2 == 0x11D1178E7F752B10LL && a2[1] == 0x40DB145F80008FABLL )
      {
        v18 = BeforeKeyRotation::BackupToRecoverableBlobW2K(
                (BeforeKeyRotation *)TokenHandle,
                a3,
                (unsigned __int8 *)v6,
                (unsigned int)v26,
                a6,
                v24);
        goto LABEL_37;
      }
      if ( *a2 != 0x11D1178E7FE94D50LL || a2[1] != 0x40DB145F80008FABLL )
      {
        if ( *a2 != 0x40C6EABA018FF48ALL || a2[1] != 0x67E9400237726D8FLL )
        {
          LastError = 87;
          DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6606);
          goto LABEL_57;
        }
        if ( (unsigned int)FIsLegacyCompliant() )
        {
          LastError = 50;
          DebugTraceError(50, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6566);
          goto LABEL_57;
        }
        UpdateGlobals(v21);
        if ( !dword_18004CCAC )
        {
          LastError = 50;
          DebugTraceError(50, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6573);
          goto LABEL_57;
        }
        if ( (unsigned int)BeforeKeyRotation::g_cbPreferredKey < 0xC
          || *(_DWORD *)BeforeKeyRotation::g_pbPreferredKey != 2
          || (v22 = *((_DWORD *)BeforeKeyRotation::g_pbPreferredKey + 2),
              v22 + *((_DWORD *)BeforeKeyRotation::g_pbPreferredKey + 1) + 12LL != (unsigned int)BeforeKeyRotation::g_cbPreferredKey) )
        {
          LastError = 87;
          DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6584);
          goto LABEL_57;
        }
        v23 = LocalAlloc(0, v22);
        *(_QWORD *)v26 = v23;
        if ( !v23 )
        {
          LastError = 8;
          DebugTraceError(8, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6591);
          goto LABEL_57;
        }
        memcpy_0(
          v23,
          (char *)BeforeKeyRotation::g_pbPreferredKey + *((unsigned int *)BeforeKeyRotation::g_pbPreferredKey + 1) + 12,
          *((unsigned int *)BeforeKeyRotation::g_pbPreferredKey + 2));
        *(_DWORD *)a6 = *((_DWORD *)BeforeKeyRotation::g_pbPreferredKey + 2);
        v20 = 1;
LABEL_50:
        if ( v20 )
        {
          *a5 = *(_QWORD *)v26;
        }
        else
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 2;
        }
        goto LABEL_57;
      }
      if ( v6 < 4 )
      {
        LastError = 87;
        DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6518);
        goto LABEL_57;
      }
      if ( a3->Data1 == 1 )
      {
LABEL_21:
        v18 = BeforeKeyRotation::RestoreFromRecoverableBlobW2K(
                (BeforeKeyRotation *)TokenHandle,
                a3,
                (unsigned __int8 *)v6,
                (unsigned int)v26,
                a6,
                v24);
LABEL_37:
        v20 = v18;
        goto LABEL_50;
      }
      if ( a3->Data1 - 2 > 1 )
      {
        LastError = 87;
        DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 6552);
        goto LABEL_57;
      }
      v19 = 1;
    }
    v18 = BeforeKeyRotation::RestoreFromRecoverableBlob(
            (BeforeKeyRotation *)TokenHandle,
            (void *)v19,
            (int)a3,
            (unsigned __int8 *)v6,
            (unsigned int)v26,
            a6,
            v25);
    goto LABEL_37;
  }
LABEL_57:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180035dd4  push    rbx
0x180035dd6  push    rsi
0x180035dd7  push    rdi
0x180035dd8  push    r12
0x180035dda  push    r13
0x180035ddc  push    r14
0x180035dde  push    r15
0x180035de0  sub     rsp, 50h
0x180035de4  mov     r15d, r9d
0x180035de7  mov     r12, r8
0x180035dea  mov     rdi, rdx
0x180035ded  mov     rsi, rcx
0x180035df0  mov     [rsp+88h+TokenHandle], 0
0x180035df9  mov     qword ptr [rsp+88h+var_50], 0
0x180035e02  cmp     cs:?g_fBackupKeyServerStarted@@3HA, 0; int g_fBackupKeyServerStarted
0x180035e09  jnz     short loc_180035E15
0x180035e0b  mov     eax, 57h ; 'W'
0x180035e10  jmp     loc_18003629F
0x180035e15  call    ?VerifyRpcValidSecurityLevel@@YAKPEAX@Z; VerifyRpcValidSecurityLevel(void *)
0x180035e1a  mov     ebx, eax
0x180035e1c  mov     dword ptr [rsp+88h+var_58], eax
0x180035e20  test    eax, eax
0x180035e22  jz      short loc_180035E44
0x180035e24  mov     r9d, 18FEh
0x180035e2a  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180035e31  lea     rdx, aDwlasterror; "dwLastError"
0x180035e38  mov     ecx, eax
0x180035e3a  call    DebugTraceError
0x180035e3f  jmp     loc_180036287
0x180035e44  call    ?SetupPreferredBackupKeys@BeforeKeyRotation@@YAHXZ; BeforeKeyRotation::SetupPreferredBackupKeys(void)
0x180035e49  test    eax, eax
0x180035e4b  jnz     short loc_180035E72
0x180035e4d  mov     r9d, 1908h
0x180035e53  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180035e5a  lea     rdx, aErrorInvalidPa; "ERROR_INVALID_PARAMETER"
0x180035e61  lea     edi, [rax+57h]
0x180035e64  mov     ecx, edi
0x180035e66  call    DebugTraceError
0x180035e6b  mov     eax, edi
0x180035e6d  jmp     loc_18003629F
0x180035e72  mov     rcx, rsi; BindingHandle
0x180035e75  call    cs:__imp_RpcImpersonateClient
0x180035e7c  nop     dword ptr [rax+rax+00h]
0x180035e81  mov     ebx, eax
0x180035e83  mov     dword ptr [rsp+88h+var_58], eax; unsigned int *
0x180035e87  test    eax, eax
0x180035e89  jz      short loc_180035EAB
0x180035e8b  mov     r9d, 1915h
0x180035e91  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180035e98  lea     rdx, aDwlasterror; "dwLastError"
0x180035e9f  mov     ecx, eax
0x180035ea1  call    DebugTraceError
0x180035ea6  jmp     loc_180036287
0x180035eab  call    cs:__imp_GetCurrentThread
0x180035eb2  nop     dword ptr [rax+rax+00h]
0x180035eb7  mov     rcx, rax; ThreadHandle
0x180035eba  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x180035ebf  xor     r8d, r8d; OpenAsSelf
0x180035ec2  lea     edx, [r8+8]; DesiredAccess
0x180035ec6  call    cs:__imp_OpenThreadToken
0x180035ecd  nop     dword ptr [rax+rax+00h]
0x180035ed2  mov     r13d, eax
0x180035ed5  test    eax, eax
0x180035ed7  jnz     short loc_180035F0E
0x180035ed9  call    cs:__imp_GetLastError
0x180035ee0  nop     dword ptr [rax+rax+00h]
0x180035ee5  mov     ebx, eax
0x180035ee7  mov     dword ptr [rsp+88h+var_58], eax
0x180035eeb  mov     r9d, 1923h
0x180035ef1  lea     rsi, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180035ef8  mov     r8, rsi
0x180035efb  lea     r14, aDwlasterror; "dwLastError"
0x180035f02  mov     rdx, r14
0x180035f05  mov     ecx, eax
0x180035f07  call    DebugTraceError
0x180035f0c  jmp     short loc_180035F1C
0x180035f0e  lea     rsi, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180035f15  lea     r14, aDwlasterror; "dwLastError"
0x180035f1c  call    cs:__imp_RpcRevertToSelf
0x180035f23  nop     dword ptr [rax+rax+00h]
0x180035f28  test    eax, eax
0x180035f2a  jz      short loc_180035F4F
0x180035f2c  test    r13d, r13d
0x180035f2f  jz      short loc_180035F54
0x180035f31  mov     ebx, eax
0x180035f33  mov     dword ptr [rsp+88h+var_58], eax
0x180035f37  mov     r9d, 1929h
0x180035f3d  mov     r8, rsi
0x180035f40  mov     rdx, r14
0x180035f43  mov     ecx, eax
0x180035f45  call    DebugTraceError
0x180035f4a  jmp     loc_180036287
0x180035f4f  test    r13d, r13d
0x180035f52  jnz     short loc_180035F59
0x180035f54  jmp     loc_180036287
0x180035f59  mov     rax, [rdi]
0x180035f5c  cmp     rax, cs:qword_180043858
0x180035f63  jnz     loc_180035FEF
0x180035f69  mov     rax, [rdi+8]
0x180035f6d  cmp     rax, cs:qword_180043860
0x180035f74  jnz     short loc_180035FEF
0x180035f76  cmp     r15d, 4
0x180035f7a  jnb     short loc_180035F8A
0x180035f7c  mov     ebx, 57h ; 'W'
0x180035f81  mov     dword ptr [rsp+88h+var_58], ebx
0x180035f85  jmp     loc_180036287
0x180035f8a  mov     eax, [r12]
0x180035f8e  mov     ecx, 1
0x180035f93  cmp     eax, ecx
0x180035f95  jnz     short loc_180035FBE
0x180035f97  mov     rax, [rsp+88h+arg_28]
0x180035f9f  mov     [rsp+88h+var_68], rax; unsigned __int8 **
0x180035fa4  lea     r9, [rsp+88h+var_50]; unsigned int
0x180035fa9  mov     r8d, r15d; unsigned __int8 *
0x180035fac  mov     rdx, r12; void *
0x180035faf  mov     rcx, [rsp+88h+TokenHandle]; this
0x180035fb4  call    ?RestoreFromRecoverableBlobW2K@BeforeKeyRotation@@YAHPEAXPEAEKPEAPEAEPEAK@Z; BeforeKeyRotation::RestoreFromRecoverableBlobW2K(void *,uchar *,ulong,uchar * *,ulong *)
0x180035fb9  jmp     loc_1800360DB
0x180035fbe  add     eax, 0FFFFFFFEh
0x180035fc1  cmp     eax, ecx
0x180035fc3  jbe     short loc_180035FE8
0x180035fc5  mov     edi, 57h ; 'W'
0x180035fca  mov     ebx, edi
0x180035fcc  mov     dword ptr [rsp+88h+var_58], ebx
0x180035fd0  mov     r9d, 1958h
0x180035fd6  mov     r8, rsi
0x180035fd9  mov     rdx, r14
0x180035fdc  mov     ecx, edi
0x180035fde  call    DebugTraceError
0x180035fe3  jmp     loc_180036287
0x180035fe8  xor     edx, edx
0x180035fea  jmp     loc_1800360B4
0x180035fef  mov     rax, [rdi]
0x180035ff2  cmp     rax, cs:qword_180043828
0x180035ff9  jnz     short loc_18003602F
0x180035ffb  mov     rax, [rdi+8]
0x180035fff  cmp     rax, cs:qword_180043830
0x180036006  jnz     short loc_18003602F
0x180036008  mov     rax, [rsp+88h+arg_28]
0x180036010  mov     [rsp+88h+var_68], rax; unsigned __int8 **
0x180036015  lea     r9, [rsp+88h+var_50]; unsigned int
0x18003601a  mov     r8d, r15d; unsigned __int8 *
0x18003601d  mov     rdx, r12; void *
0x180036020  mov     rcx, [rsp+88h+TokenHandle]; this
0x180036025  call    ?BackupToRecoverableBlobW2K@BeforeKeyRotation@@YAHPEAXPEAEKPEAPEAEPEAK@Z; BeforeKeyRotation::BackupToRecoverableBlobW2K(void *,uchar *,ulong,uchar * *,ulong *)
0x18003602a  jmp     loc_1800360DB
0x18003602f  mov     rax, [rdi]
0x180036032  cmp     rax, cs:qword_180043878
0x180036039  jnz     loc_1800360E7
0x18003603f  mov     rax, [rdi+8]
0x180036043  cmp     rax, cs:qword_180043880
0x18003604a  jnz     loc_1800360E7
0x180036050  cmp     r15d, 4
0x180036054  jnb     short loc_180036079
0x180036056  mov     edi, 57h ; 'W'
0x18003605b  mov     ebx, edi
0x18003605d  mov     dword ptr [rsp+88h+var_58], ebx
0x180036061  mov     r9d, 1976h
0x180036067  mov     r8, rsi
0x18003606a  mov     rdx, r14
0x18003606d  mov     ecx, edi
0x18003606f  call    DebugTraceError
0x180036074  jmp     loc_180036287
0x180036079  mov     eax, [r12]
0x18003607d  mov     ecx, 1
0x180036082  cmp     eax, ecx
0x180036084  jz      loc_180035F97
0x18003608a  add     eax, 0FFFFFFFEh
0x18003608d  cmp     eax, ecx
0x18003608f  jbe     short loc_1800360B2
0x180036091  lea     edi, [rcx+56h]
0x180036094  mov     ebx, edi
0x180036096  mov     dword ptr [rsp+88h+var_58], ebx
0x18003609a  mov     r9d, 1998h
0x1800360a0  mov     r8, rsi
0x1800360a3  mov     rdx, r14
0x1800360a6  mov     ecx, edi
0x1800360a8  call    DebugTraceError
0x1800360ad  jmp     loc_180036287
0x1800360b2  mov     edx, ecx; void *
0x1800360b4  mov     rax, [rsp+88h+arg_28]
0x1800360bc  mov     [rsp+88h+var_60], rax; unsigned __int8 **
0x1800360c1  lea     rax, [rsp+88h+var_50]
0x1800360c6  mov     r8, r12; int
0x1800360c9  mov     r9d, r15d; unsigned __int8 *
0x1800360cc  mov     [rsp+88h+var_68], rax; unsigned int
0x1800360d1  mov     rcx, [rsp+88h+TokenHandle]; this
0x1800360d6  call    ?RestoreFromRecoverableBlob@BeforeKeyRotation@@YAHPEAXHPEAEKPEAPEAEPEAK@Z; BeforeKeyRotation::RestoreFromRecoverableBlob(void *,int,uchar *,ulong,uchar * *,ulong *)
0x1800360db  mov     ecx, eax
0x1800360dd  mov     edi, 2
0x1800360e2  jmp     loc_18003620E
0x1800360e7  mov     rax, [rdi]
0x1800360ea  cmp     rax, cs:qword_180043818
0x1800360f1  jnz     loc_180036261
0x1800360f7  mov     rax, [rdi+8]
0x1800360fb  cmp     rax, cs:qword_180043820
0x180036102  jnz     loc_180036261
0x180036108  call    ?FIsLegacyCompliant@@YAHXZ; FIsLegacyCompliant(void)
0x18003610d  test    eax, eax
0x18003610f  jz      short loc_180036132
0x180036111  mov     ecx, 32h ; '2'
0x180036116  mov     ebx, ecx
0x180036118  mov     dword ptr [rsp+88h+var_58], ecx
0x18003611c  mov     r9d, 19A6h
0x180036122  mov     r8, rsi
0x180036125  mov     rdx, r14
0x180036128  call    DebugTraceError
0x18003612d  jmp     loc_180036287
0x180036132  call    ?UpdateGlobals@@YAKH@Z; UpdateGlobals(int)
0x180036137  cmp     cs:dword_18004CCAC, 0
0x18003613e  jnz     short loc_180036161
0x180036140  mov     ecx, 32h ; '2'
0x180036145  mov     ebx, ecx
0x180036147  mov     dword ptr [rsp+88h+var_58], ecx
0x18003614b  mov     r9d, 19ADh
0x180036151  mov     r8, rsi
0x180036154  mov     rdx, r14
0x180036157  call    DebugTraceError
0x18003615c  jmp     loc_180036287
0x180036161  mov     edx, cs:?g_cbPreferredKey@BeforeKeyRotation@@3KA; ulong BeforeKeyRotation::g_cbPreferredKey
0x180036167  cmp     edx, 0Ch
0x18003616a  jb      loc_180036241
0x180036170  mov     edi, 2
0x180036175  mov     rax, cs:?g_pbPreferredKey@BeforeKeyRotation@@3PEAEEA; uchar * BeforeKeyRotation::g_pbPreferredKey
0x18003617c  cmp     [rax], edi
0x18003617e  jnz     loc_180036241
0x180036184  mov     r8d, [rax+8]
0x180036188  mov     ecx, [rax+4]
0x18003618b  add     ecx, r8d
0x18003618e  add     rcx, 0Ch
0x180036192  cmp     rcx, rdx
0x180036195  jnz     loc_180036241
0x18003619b  mov     edx, r8d; uBytes
0x18003619e  xor     ecx, ecx; uFlags
0x1800361a0  call    cs:__imp_LocalAlloc
0x1800361a7  nop     dword ptr [rax+rax+00h]
0x1800361ac  mov     r9, rax
0x1800361af  mov     qword ptr [rsp+88h+var_50], rax
0x1800361b4  test    rax, rax
0x1800361b7  jnz     short loc_1800361D8
0x1800361b9  lea     ecx, [rdi+6]
0x1800361bc  mov     ebx, ecx
0x1800361be  mov     dword ptr [rsp+88h+var_58], ecx
0x1800361c2  mov     r9d, 19BFh
0x1800361c8  mov     r8, rsi
0x1800361cb  mov     rdx, r14
0x1800361ce  call    DebugTraceError
0x1800361d3  jmp     loc_180036287
0x1800361d8  mov     rcx, cs:?g_pbPreferredKey@BeforeKeyRotation@@3PEAEEA; uchar * BeforeKeyRotation::g_pbPreferredKey
0x1800361df  mov     r8d, [rcx+8]; Size
0x1800361e3  mov     eax, [rcx+4]
0x1800361e6  lea     rdx, [rcx+0Ch]
0x1800361ea  add     rdx, rax; Src
0x1800361ed  mov     rcx, r9; void *
0x1800361f0  call    memcpy_0
0x1800361f5  mov     rax, cs:?g_pbPreferredKey@BeforeKeyRotation@@3PEAEEA; uchar * BeforeKeyRotation::g_pbPreferredKey
0x1800361fc  mov     ecx, [rax+8]
0x1800361ff  mov     rax, [rsp+88h+arg_28]
0x180036207  mov     [rax], ecx
0x180036209  mov     ecx, 1
0x18003620e  test    ecx, ecx
0x180036210  jz      short loc_180036224
0x180036212  mov     rcx, qword ptr [rsp+88h+var_50]
0x180036217  mov     rax, [rsp+88h+arg_20]
0x18003621f  mov     [rax], rcx
0x180036222  jmp     short loc_18003623F
0x180036224  call    cs:__imp_GetLastError
0x18003622b  nop     dword ptr [rax+rax+00h]
0x180036230  mov     ebx, eax
0x180036232  mov     dword ptr [rsp+88h+var_58], eax
0x180036236  test    eax, eax
0x180036238  cmovz   ebx, edi
0x18003623b  mov     dword ptr [rsp+88h+var_58], ebx
0x18003623f  jmp     short loc_180036287
0x180036241  mov     edi, 57h ; 'W'
0x180036246  mov     ebx, edi
0x180036248  mov     dword ptr [rsp+88h+var_58], ebx
0x18003624c  mov     r9d, 19B8h
0x180036252  mov     r8, rsi
0x180036255  mov     rdx, r14
0x180036258  mov     ecx, edi
0x18003625a  call    DebugTraceError
0x18003625f  jmp     short loc_180036287
0x180036261  mov     edi, 57h ; 'W'
0x180036266  mov     ebx, edi
0x180036268  mov     dword ptr [rsp+88h+var_58], ebx
0x18003626c  mov     r9d, 19CEh
0x180036272  mov     r8, rsi
0x180036275  mov     rdx, r14
0x180036278  mov     ecx, edi
0x18003627a  call    DebugTraceError
0x18003627f  jmp     short loc_180036287
0x180036281  mov     ebx, eax
0x180036283  mov     dword ptr [rsp+88h+var_58], eax
0x180036287  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x18003628c  test    rcx, rcx
0x18003628f  jz      short loc_18003629D
0x180036291  call    cs:__imp_CloseHandle
0x180036298  nop     dword ptr [rax+rax+00h]
0x18003629d  mov     eax, ebx
  ... truncated ...
```
