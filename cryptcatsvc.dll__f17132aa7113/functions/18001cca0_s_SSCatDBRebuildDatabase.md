# s_SSCatDBRebuildDatabase

- ea: `0x18001cca0`
- end: `0x18001ce88`
- name: `s_SSCatDBRebuildDatabase`
- size: `488`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x1800015b0`
- `0x180003d48`
- `0x180007fb0`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000a710`
- `0x180013584`
- `0x180019a7c`
- `0x18001c03c`
- `0x18001c6b4`
- `0x18001cca0`
- `0x18001cf60`
- `0x18001d62c`
- `0x18001f748`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cd0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cd0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ce5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ce5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ccf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cdd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ce19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ccf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cdd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ce19`

## string_xrefs

- `0x18001ce40`: `RebuildDatabase(%s):: ERROR_ACCESS_DENIED`

## pseudocode

```c
__int64 __fastcall s_SSCatDBRebuildDatabase(RPC_BINDING_HANDLE BindingHandle, unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rdi
  int v5; // ebp
  DWORD v6; // eax
  DWORD Error; // ebx
  unsigned int v8; // edx
  unsigned __int16 *v9; // rcx
  unsigned int v10; // r8d
  const unsigned __int16 *v11; // rax
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  int v15; // [rsp+28h] [rbp-30h]
  int v16; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  v16 = 0;
  v5 = 0;
  I_CatDBEventSubsystemTemplate(a2, CAPI2_CATDB_REBUILD_DATABASE_START_EVENT);
  if ( !BindingHandle || !(unsigned int)_CatDBDVerifyGUIDString(a2) )
  {
    SetLastError(0xA0u);
    v10 = 3692;
    goto LABEL_22;
  }
  v6 = _CatDBCanWriteToPathWithImpersonation(BindingHandle, g_pwszCatalogFileBaseDirectory);
  Error = v6;
  if ( !v6 )
  {
    EnterCriticalSection(&g_CatDBAddDeleteCS);
    v5 = 1;
    v11 = _CATDBConstructWSTRPath(g_pwszCatalogFileBaseDirectory, a2);
    v4 = (unsigned __int16 *)v11;
    if ( !v11 )
    {
      ErrLog_LogError(v13, v12, 0xE83u, 0, 0, v15);
      goto LABEL_23;
    }
    if ( !_CatDBSyncDB(0, v11, a2, 0, 1, &v16) )
    {
      if ( GetLastError() != 303 )
      {
        v10 = 3725;
        goto LABEL_22;
      }
      if ( !(unsigned int)CatDBFreezeJet(0) )
      {
        v10 = 3731;
        goto LABEL_22;
      }
      Error = 0;
      if ( !(unsigned int)_CatDBDeleteJetFiles(0) )
        Error = _CatDBGetNonzeroLastError();
      if ( !(unsigned int)CatDBThawJet(0) )
      {
        if ( Error )
        {
LABEL_18:
          SetLastError(Error);
          v10 = 3748;
          goto LABEL_22;
        }
        Error = _CatDBGetNonzeroLastError();
      }
      if ( Error )
        goto LABEL_18;
      if ( !_CatDBSyncDB(0, v4, a2, 0, 1, &v16) )
      {
        v10 = 3756;
        goto LABEL_22;
      }
    }
LABEL_26:
    LeaveCriticalSection(&g_CatDBAddDeleteCS);
    goto LABEL_27;
  }
  SetLastError(v6);
  v10 = 3699;
LABEL_22:
  ErrLog_LogError(v9, v8, v10, 0, 0, v15);
LABEL_23:
  Error = _CatDBGetNonzeroLastError();
  if ( Error == 5 )
    ErrLog_LogPrintfW(0, 1, L"RebuildDatabase(%s):: ERROR_ACCESS_DENIED", a2);
  if ( v5 )
    goto LABEL_26;
LABEL_27:
  if ( v4 )
    _CatDBFree(v4);
  I_CatDBEventStatusTemplate(Error, CAPI2_CATDB_REBUILD_DATABASE_STOP_EVENT);
  return Error;
}

```

## disassembly

```asm
0x18001cca0  push    rbx
0x18001cca2  push    rbp
0x18001cca3  push    rsi
0x18001cca4  push    rdi
0x18001cca5  sub     rsp, 38h
0x18001cca9  mov     rsi, rdx
0x18001ccac  mov     rbx, rcx
0x18001ccaf  xor     edi, edi
0x18001ccb1  lea     rdx, CAPI2_CATDB_REBUILD_DATABASE_START_EVENT
0x18001ccb8  mov     rcx, rsi
0x18001ccbb  mov     [rsp+58h+arg_0], edi
0x18001ccbf  xor     ebp, ebp
0x18001ccc1  call    I_CatDBEventSubsystemTemplate
0x18001ccc6  test    rbx, rbx
0x18001ccc9  jz      loc_18001CE14
0x18001cccf  mov     rcx, rsi; unsigned __int16 *
0x18001ccd2  call    ?_CatDBDVerifyGUIDString@@YAHPEBG@Z; _CatDBDVerifyGUIDString(ushort const *)
0x18001ccd7  test    eax, eax
0x18001ccd9  jz      loc_18001CE14
0x18001ccdf  mov     rdx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; lpFileName
0x18001cce6  mov     rcx, rbx; BindingHandle
0x18001cce9  call    ?_CatDBCanWriteToPathWithImpersonation@@YAKPEAXPEBG@Z; _CatDBCanWriteToPathWithImpersonation(void *,ushort const *)
0x18001ccee  mov     ebx, eax
0x18001ccf0  test    eax, eax
0x18001ccf2  jz      short loc_18001CD07
0x18001ccf4  mov     ecx, eax; dwErrCode
0x18001ccf6  call    cs:__imp_SetLastError
0x18001ccfc  mov     r8d, 0E73h
0x18001cd02  jmp     loc_18001CE25
0x18001cd07  lea     rcx, ?g_CatDBAddDeleteCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cd0e  call    cs:__imp_EnterCriticalSection
0x18001cd14  mov     rcx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; unsigned __int16 *
0x18001cd1b  mov     rdx, rsi; unsigned __int16 *
0x18001cd1e  mov     ebp, 1
0x18001cd23  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001cd28  xor     r9d, r9d; int
0x18001cd2b  mov     rdi, rax
0x18001cd2e  test    rax, rax
0x18001cd31  jnz     short loc_18001CD43
0x18001cd33  mov     [rsp+58h+var_38], r9d
0x18001cd38  mov     r8d, 0E83h
0x18001cd3e  jmp     loc_18001CE2C
0x18001cd43  lea     rax, [rsp+58h+arg_0]
0x18001cd48  mov     r8, rsi; unsigned __int16 *
0x18001cd4b  mov     qword ptr [rsp+58h+var_30], rax; int *
0x18001cd50  mov     rdx, rdi; unsigned __int16 *
0x18001cd53  xor     ecx, ecx; int
0x18001cd55  mov     [rsp+58h+var_38], ebp; int
0x18001cd59  call    ?_CatDBSyncDB@@YAHHPEBG0HHPEAH@Z; _CatDBSyncDB(int,ushort const *,ushort const *,int,int,int *)
0x18001cd5e  test    eax, eax
0x18001cd60  jnz     loc_18001CE55
0x18001cd66  call    cs:__imp_GetLastError
0x18001cd6c  cmp     eax, 12Fh
0x18001cd71  jz      short loc_18001CD86
0x18001cd73  mov     [rsp+58h+var_38], 0
0x18001cd7b  mov     r8d, 0E8Dh
0x18001cd81  jmp     loc_18001CE29
0x18001cd86  xor     ecx, ecx; int
0x18001cd88  call    _CatDBFreezeJet
0x18001cd8d  test    eax, eax
0x18001cd8f  jnz     short loc_18001CDA0
0x18001cd91  mov     [rsp+58h+var_38], eax
0x18001cd95  mov     r8d, 0E93h
0x18001cd9b  jmp     loc_18001CE29
0x18001cda0  xor     ecx, ecx; int
0x18001cda2  xor     ebx, ebx
0x18001cda4  call    ?_CatDBDeleteJetFiles@@YAHH@Z; _CatDBDeleteJetFiles(int)
0x18001cda9  test    eax, eax
0x18001cdab  jnz     short loc_18001CDB4
0x18001cdad  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001cdb2  mov     ebx, eax
0x18001cdb4  xor     ecx, ecx
0x18001cdb6  call    _CatDBThawJet
0x18001cdbb  test    eax, eax
0x18001cdbd  jnz     short loc_18001CDCA
0x18001cdbf  test    ebx, ebx
0x18001cdc1  jnz     short loc_18001CDCE
0x18001cdc3  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001cdc8  mov     ebx, eax
0x18001cdca  test    ebx, ebx
0x18001cdcc  jz      short loc_18001CDE6
0x18001cdce  mov     ecx, ebx; dwErrCode
0x18001cdd0  call    cs:__imp_SetLastError
0x18001cdd6  mov     r8d, 0EA4h
0x18001cddc  mov     [rsp+58h+var_38], 0
0x18001cde4  jmp     short loc_18001CE29
0x18001cde6  lea     rax, [rsp+58h+arg_0]
0x18001cdeb  xor     r9d, r9d; int
0x18001cdee  mov     qword ptr [rsp+58h+var_30], rax; int *
0x18001cdf3  mov     r8, rsi; unsigned __int16 *
0x18001cdf6  mov     rdx, rdi; unsigned __int16 *
0x18001cdf9  mov     [rsp+58h+var_38], ebp; int
0x18001cdfd  xor     ecx, ecx; int
0x18001cdff  call    ?_CatDBSyncDB@@YAHHPEBG0HHPEAH@Z; _CatDBSyncDB(int,ushort const *,ushort const *,int,int,int *)
0x18001ce04  test    eax, eax
0x18001ce06  jnz     short loc_18001CE55
0x18001ce08  mov     [rsp+58h+var_38], eax
0x18001ce0c  mov     r8d, 0EACh
0x18001ce12  jmp     short loc_18001CE29
0x18001ce14  mov     ecx, 0A0h; dwErrCode
0x18001ce19  call    cs:__imp_SetLastError
0x18001ce1f  mov     r8d, 0E6Ch; unsigned int
0x18001ce25  mov     [rsp+58h+var_38], edi; int
0x18001ce29  xor     r9d, r9d; unsigned int
0x18001ce2c  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001ce31  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001ce36  mov     ebx, eax
0x18001ce38  cmp     eax, 5
0x18001ce3b  jnz     short loc_18001CE51
0x18001ce3d  mov     r9, rsi
0x18001ce40  lea     r8, aRebuilddatabas; "RebuildDatabase(%s):: ERROR_ACCESS_DENI"...
0x18001ce47  lea     edx, [rax-4]; int
0x18001ce4a  xor     ecx, ecx; unsigned __int16 *
0x18001ce4c  call    ?ErrLog_LogPrintfW@@YAXPEAGHPEBGZZ; ErrLog_LogPrintfW(ushort *,int,ushort const *,...)
0x18001ce51  test    ebp, ebp
0x18001ce53  jz      short loc_18001CE62
0x18001ce55  lea     rcx, ?g_CatDBAddDeleteCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ce5c  call    cs:__imp_LeaveCriticalSection
0x18001ce62  test    rdi, rdi
0x18001ce65  jz      short loc_18001CE6F
0x18001ce67  mov     rcx, rdi; void *
0x18001ce6a  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001ce6f  lea     rdx, CAPI2_CATDB_REBUILD_DATABASE_STOP_EVENT
0x18001ce76  mov     ecx, ebx
0x18001ce78  call    I_CatDBEventStatusTemplate
0x18001ce7d  mov     eax, ebx
0x18001ce7f  add     rsp, 38h
0x18001ce83  pop     rdi
0x18001ce84  pop     rsi
0x18001ce85  pop     rbp
0x18001ce86  pop     rbx
0x18001ce87  retn
```
