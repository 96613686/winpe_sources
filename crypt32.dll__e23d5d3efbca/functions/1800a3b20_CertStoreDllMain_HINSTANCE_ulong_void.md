# CertStoreDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x1800a3b20`
- end: `0x1800a3b88`
- name: `?CertStoreDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `104`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800944a0`

## callees

- `0x180029624`
- `0x18002ac80`
- `0x1800449d4`
- `0x180045014`
- `0x18008a070`
- `0x180091f9c`
- `0x18009e6a8`
- `0x1800a3b20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a3b60`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a3b6d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18011d141`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18011d14e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18011d160`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18011d16d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18011d192`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a3b60`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a3b6d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18011d141`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18011d14e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18011d160`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18011d16d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18011d192`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800a3b75`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800a3b75`

## pseudocode

```c
__int64 __fastcall CertStoreDllMain(HINSTANCE a1, unsigned int a2, void *a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r8

  if ( (unsigned int)I_RegStoreDllMain(a1, a2, a3) )
  {
    if ( !a2 )
    {
      if ( qword_18015D650 )
      {
        RtlUnsubscribeWnfNotificationWaitForCompletion();
        qword_18015D650 = 0;
      }
      DeleteCriticalSection(&stru_180158280);
      DeleteCriticalSection(&ShareStoreCriticalSection);
      return 1;
    }
    if ( a2 != 1 )
      return 1;
    qword_1801582A8 = (struct _FUNC_SET *)qword_180158BA0;
    if ( (unsigned int)I_CryptInstallDllMainOIDFunctionAddress(0, 0x19u, 0x18u, &stru_1801269A0)
      && (unsigned int)Pki_InitializeCriticalSection(&stru_180158280, v5, v6) )
    {
      if ( (unsigned int)Pki_InitializeCriticalSection(&ShareStoreCriticalSection, v7, v8) )
      {
        if ( (unsigned int)InitNullCertStore() )
          return 1;
        DeleteCriticalSection(&ShareStoreCriticalSection);
      }
      DeleteCriticalSection(&stru_180158280);
    }
    FreePredefinedSids();
    DeleteCriticalSection(&stru_18015CD60);
    DeleteCriticalSection(&Crypt32EventLogCriticalSection);
    FreeGptStoreChangeInfo(&qword_180158328);
    FreeGptStoreChangeInfo(&qword_180158330);
    DeleteCriticalSection(&stru_1801582C8);
    I_CryptFreeTls((unsigned int)dword_1801582C4, PkiDefaultCryptFree, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a3b20  push    rbx
0x1800a3b22  sub     rsp, 20h
0x1800a3b26  mov     ebx, edx
0x1800a3b28  call    ?I_RegStoreDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z; I_RegStoreDllMain(HINSTANCE__ *,ulong,void *)
0x1800a3b2d  test    eax, eax
0x1800a3b2f  jz      short loc_1800A3B45
0x1800a3b31  test    ebx, ebx
0x1800a3b33  jz      short loc_1800A3B4D
0x1800a3b35  cmp     ebx, 1
0x1800a3b38  jz      loc_18011D0E4
0x1800a3b3e  mov     eax, 1
0x1800a3b43  jmp     short loc_1800A3B47
0x1800a3b45  xor     eax, eax
0x1800a3b47  add     rsp, 20h
0x1800a3b4b  pop     rbx
0x1800a3b4c  retn
0x1800a3b4d  mov     rcx, cs:qword_18015D650
0x1800a3b54  test    rcx, rcx
0x1800a3b57  jnz     short loc_1800A3B75
0x1800a3b59  lea     rcx, stru_180158280; lpCriticalSection
0x1800a3b60  call    cs:__imp_DeleteCriticalSection
0x1800a3b66  lea     rcx, ?ShareStoreCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a3b6d  call    cs:__imp_DeleteCriticalSection
0x1800a3b73  jmp     short loc_1800A3B3E
0x1800a3b75  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800a3b7b  mov     cs:qword_18015D650, 0
0x1800a3b86  jmp     short loc_1800A3B59
0x18011d0e4  lea     rax, qword_180158BA0
0x18011d0eb  mov     cs:qword_1801582A8, rax
0x18011d0f2  mov     edx, 19h; unsigned int
0x18011d0f7  lea     r9, stru_1801269A0; struct _CRYPT_OID_FUNC_ENTRY *
0x18011d0fe  xor     ecx, ecx; unsigned int
0x18011d100  lea     r8d, [rdx-1]; unsigned int
0x18011d104  call    ?I_CryptInstallDllMainOIDFunctionAddress@@YAHKKKQEBU_CRYPT_OID_FUNC_ENTRY@@@Z; I_CryptInstallDllMainOIDFunctionAddress(ulong,ulong,ulong,_CRYPT_OID_FUNC_ENTRY const * const)
0x18011d109  test    eax, eax
0x18011d10b  jz      short loc_18011D154
0x18011d10d  lea     rcx, stru_180158280
0x18011d114  call    Pki_InitializeCriticalSection
0x18011d119  test    eax, eax
0x18011d11b  jz      short loc_18011D154
0x18011d11d  lea     rcx, ?ShareStoreCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION ShareStoreCriticalSection
0x18011d124  call    Pki_InitializeCriticalSection
0x18011d129  test    eax, eax
0x18011d12b  jz      short loc_18011D147
0x18011d12d  call    ?InitNullCertStore@@YAHXZ; InitNullCertStore(void)
0x18011d132  test    eax, eax
0x18011d134  jnz     loc_1800A3B3E
0x18011d13a  lea     rcx, ?ShareStoreCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18011d141  call    cs:__imp_DeleteCriticalSection
0x18011d147  lea     rcx, stru_180158280; lpCriticalSection
0x18011d14e  call    cs:__imp_DeleteCriticalSection
0x18011d154  call    FreePredefinedSids
0x18011d159  lea     rcx, stru_18015CD60; lpCriticalSection
0x18011d160  call    cs:__imp_DeleteCriticalSection
0x18011d166  lea     rcx, ?Crypt32EventLogCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18011d16d  call    cs:__imp_DeleteCriticalSection
0x18011d173  lea     rcx, qword_180158328; struct _GPT_STORE_CHANGE_INFO **
0x18011d17a  call    ?FreeGptStoreChangeInfo@@YAXPEAPEAU_GPT_STORE_CHANGE_INFO@@@Z; FreeGptStoreChangeInfo(_GPT_STORE_CHANGE_INFO * *)
0x18011d17f  lea     rcx, qword_180158330; struct _GPT_STORE_CHANGE_INFO **
0x18011d186  call    ?FreeGptStoreChangeInfo@@YAXPEAPEAU_GPT_STORE_CHANGE_INFO@@@Z; FreeGptStoreChangeInfo(_GPT_STORE_CHANGE_INFO * *)
0x18011d18b  lea     rcx, stru_1801582C8; lpCriticalSection
0x18011d192  call    cs:__imp_DeleteCriticalSection
0x18011d198  mov     ecx, cs:dword_1801582C4
0x18011d19e  lea     rdx, PkiDefaultCryptFree
0x18011d1a5  call    I_CryptFreeTls
0x18011d1aa  nop
0x18011d1ab  jmp     loc_1800A3B45
```
