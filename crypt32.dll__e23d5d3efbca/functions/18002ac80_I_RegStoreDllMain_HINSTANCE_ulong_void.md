# I_RegStoreDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x18002ac80`
- end: `0x18002adef`
- name: `?I_RegStoreDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `367`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800a3b20`

## callees

- `0x180028d60`
- `0x18002967c`
- `0x18002ac80`
- `0x18002b3a0`
- `0x18002b480`
- `0x1800449d4`
- `0x180045014`
- `0x18008a070`
- `0x180091f9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ad56`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ad68`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ad75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ad8e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ad9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002adc0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ade4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ad56`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ad68`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ad75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ad8e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ad9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002adc0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ade4`

## pseudocode

```c
__int64 __fastcall I_RegStoreDllMain(HINSTANCE a1, __int64 a2, void *a3)
{
  unsigned int v3; // esi
  __int64 v4; // rdx
  void *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 i; // rdi
  void *inited; // rax
  __int64 v11; // rcx
  __int64 v12; // r8

  v3 = 1;
  if ( !(_DWORD)a2 )
  {
    FreePredefinedSids(a1, a2, a3);
    DeleteCriticalSection(&stru_18015CD60);
    DeleteCriticalSection(&Crypt32EventLogCriticalSection);
    FreeGptStoreChangeInfo(&qword_180158328);
    FreeGptStoreChangeInfo(&qword_180158330);
    DeleteCriticalSection(&stru_1801582C8);
    I_CryptFreeTls((unsigned int)dword_1801582C4, PkiDefaultCryptFree, v12);
    return v3;
  }
  if ( (_DWORD)a2 != 1 )
  {
    v4 = (unsigned int)(a2 - 1);
    if ( (_DWORD)v4 )
    {
      if ( (_DWORD)v4 == 2 )
      {
        v6 = (void *)I_CryptDetachTls((unsigned int)dword_1801582C4, v4, a3);
        PkiDefaultCryptFree(v6);
      }
      return v3;
    }
LABEL_10:
    for ( i = 0; (unsigned int)i < 7; i = (unsigned int)(i + 1) )
    {
      inited = I_CryptInitDllMainOIDFunctionSet(dword_18013E690[i]);
      *(&qword_1801582F0 + i) = inited;
      if ( !inited )
        goto LABEL_17;
    }
    if ( (unsigned int)Pki_InitializeCriticalSection(&stru_1801582C8, v4, a3) )
    {
      dword_1801582C4 = I_CryptAllocTlsEx(0);
      if ( dword_1801582C4 )
        return v3;
      DeleteCriticalSection(&stru_1801582C8);
    }
LABEL_17:
    FreePredefinedSids(v11, v4, a3);
    DeleteCriticalSection(&stru_18015CD60);
    DeleteCriticalSection(&Crypt32EventLogCriticalSection);
    return 0;
  }
  hModule = a1;
  if ( (unsigned int)Pki_InitializeCriticalSection(&stru_18015CD60, a2, a3) )
  {
    if ( (unsigned int)Pki_InitializeCriticalSection(&Crypt32EventLogCriticalSection, v7, v8) )
      goto LABEL_10;
    DeleteCriticalSection(&stru_18015CD60);
  }
  return 0;
}

```

## disassembly

```asm
0x18002ac80  push    rbx
0x18002ac82  push    rsi
0x18002ac83  push    rdi
0x18002ac84  push    r14
0x18002ac86  sub     rsp, 28h
0x18002ac8a  mov     eax, edx
0x18002ac8c  mov     esi, 1
0x18002ac91  test    edx, edx
0x18002ac93  jz      loc_18002AD82
0x18002ac99  cmp     eax, esi
0x18002ac9b  jz      short loc_18002ACCF
0x18002ac9d  test    edx, edx
0x18002ac9f  jz      loc_18002ADA1
0x18002aca5  sub     edx, esi
0x18002aca7  jz      short loc_18002ACFE
0x18002aca9  cmp     edx, 2
0x18002acac  jz      short loc_18002ACBA
0x18002acae  mov     eax, esi
0x18002acb0  add     rsp, 28h
0x18002acb4  pop     r14
0x18002acb6  pop     rdi
0x18002acb7  pop     rsi
0x18002acb8  pop     rbx
0x18002acb9  retn
0x18002acba  mov     ecx, cs:dword_1801582C4
0x18002acc0  call    I_CryptDetachTls
0x18002acc5  mov     rcx, rax; hMem
0x18002acc8  call    PkiDefaultCryptFree
0x18002accd  jmp     short loc_18002ACAE
0x18002accf  mov     cs:hModule, rcx
0x18002acd6  lea     rcx, stru_18015CD60
0x18002acdd  call    Pki_InitializeCriticalSection
0x18002ace2  test    eax, eax
0x18002ace4  jnz     short loc_18002ACEA
0x18002ace6  xor     eax, eax
0x18002ace8  jmp     short loc_18002ACB0
0x18002acea  lea     rcx, ?Crypt32EventLogCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION Crypt32EventLogCriticalSection
0x18002acf1  call    Pki_InitializeCriticalSection
0x18002acf6  test    eax, eax
0x18002acf8  jz      loc_18002ADDD
0x18002acfe  xor     edi, edi
0x18002ad00  lea     r14, __ImageBase
0x18002ad07  cmp     edi, 7
0x18002ad0a  jnb     short loc_18002AD2A
0x18002ad0c  mov     ecx, ds:rva dword_18013E690[r14+rdi*4]; unsigned int
0x18002ad14  call    ?I_CryptInitDllMainOIDFunctionSet@@YAPEAXK@Z; I_CryptInitDllMainOIDFunctionSet(ulong)
0x18002ad19  mov     rva qword_1801582F0[r14+rdi*8], rax
0x18002ad21  test    rax, rax
0x18002ad24  jz      short loc_18002AD5C
0x18002ad26  add     edi, esi
0x18002ad28  jmp     short loc_18002AD07
0x18002ad2a  lea     rcx, stru_1801582C8
0x18002ad31  call    Pki_InitializeCriticalSection
0x18002ad36  test    eax, eax
0x18002ad38  jz      short loc_18002AD5C
0x18002ad3a  xor     ecx, ecx
0x18002ad3c  call    I_CryptAllocTlsEx
0x18002ad41  mov     cs:dword_1801582C4, eax
0x18002ad47  test    eax, eax
0x18002ad49  jnz     loc_18002ACAE
0x18002ad4f  lea     rcx, stru_1801582C8; lpCriticalSection
0x18002ad56  call    cs:__imp_DeleteCriticalSection
0x18002ad5c  call    FreePredefinedSids
0x18002ad61  lea     rcx, stru_18015CD60; lpCriticalSection
0x18002ad68  call    cs:__imp_DeleteCriticalSection
0x18002ad6e  lea     rcx, ?Crypt32EventLogCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002ad75  call    cs:__imp_DeleteCriticalSection
0x18002ad7b  xor     esi, esi
0x18002ad7d  jmp     loc_18002ACAE
0x18002ad82  call    FreePredefinedSids
0x18002ad87  lea     rcx, stru_18015CD60; lpCriticalSection
0x18002ad8e  call    cs:__imp_DeleteCriticalSection
0x18002ad94  lea     rcx, ?Crypt32EventLogCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002ad9b  call    cs:__imp_DeleteCriticalSection
0x18002ada1  lea     rcx, qword_180158328; struct _GPT_STORE_CHANGE_INFO **
0x18002ada8  call    ?FreeGptStoreChangeInfo@@YAXPEAPEAU_GPT_STORE_CHANGE_INFO@@@Z; FreeGptStoreChangeInfo(_GPT_STORE_CHANGE_INFO * *)
0x18002adad  lea     rcx, qword_180158330; struct _GPT_STORE_CHANGE_INFO **
0x18002adb4  call    ?FreeGptStoreChangeInfo@@YAXPEAPEAU_GPT_STORE_CHANGE_INFO@@@Z; FreeGptStoreChangeInfo(_GPT_STORE_CHANGE_INFO * *)
0x18002adb9  lea     rcx, stru_1801582C8; lpCriticalSection
0x18002adc0  call    cs:__imp_DeleteCriticalSection
0x18002adc6  mov     ecx, cs:dword_1801582C4
0x18002adcc  lea     rdx, PkiDefaultCryptFree
0x18002add3  call    I_CryptFreeTls
0x18002add8  jmp     loc_18002ACAE
0x18002addd  lea     rcx, stru_18015CD60; lpCriticalSection
0x18002ade4  call    cs:__imp_DeleteCriticalSection
0x18002adea  jmp     loc_18002ACE6
```
