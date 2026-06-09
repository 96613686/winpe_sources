# CertChainPolicyDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x18002b170`
- end: `0x18002b380`
- name: `?CertChainPolicyDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `528`
- prototype: `__int64 __fastcall(HINSTANCE, __int64, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800944a0`

## callees

- `0x18001fa60`
- `0x180027f90`
- `0x180028d60`
- `0x18002b170`
- `0x18002b388`
- `0x18002b3a0`
- `0x18002b410`
- `0x18002b480`
- `0x1800449d4`
- `0x180047f10`
- `0x18008a070`
- `0x18009aa70`
- `0x1800a3e98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b314`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b314`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b345`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b36a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b345`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b36a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b375`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b375`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002b33a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002b35f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002b33a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002b35f`

## pseudocode

```c
__int64 __fastcall CertChainPolicyDllMain(HINSTANCE a1, __int64 a2, void *a3)
{
  int v3; // ebx
  unsigned int v5; // ebp
  struct _CERT_DIAG_PIN_RULES_INFO *v6; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 i; // rdi
  __int64 v11; // rsi
  void *v12; // rcx
  HKEY v13; // rcx
  void *v14; // rcx
  __int64 v15; // r8
  struct _LIST_ENTRY *v16; // rcx

  v3 = a2;
  v5 = 1;
  switch ( (_DWORD)a2 )
  {
    case 0:
      for ( i = 0; i != 2; ++i )
      {
        v11 = 32 * i;
        v12 = *(&qword_18015D0E0 + 4 * i + 2);
        if ( v12 )
          UnregisterWaitEx(v12, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        v13 = *(HKEY *)((char *)&qword_18015D0E0 + v11);
        if ( v13 )
          RegCloseKey(v13);
        v14 = *(HKEY *)((char *)&qword_18015D0E0 + v11 + 8);
        if ( v14 )
          CloseHandle(v14);
      }
      ReleaseChainPinRulesContext(qword_18015D120);
      I_CryptFreeTls((unsigned int)dword_18015D12C, FreeCertDiagTls, v15);
      PkiDefaultCryptFree(qword_18015D138);
      IPS_FreeStringList(v16);
      if ( qword_18015D150 )
        I_CryptFreeLruCache(qword_18015D150);
LABEL_5:
      if ( WaitHandle )
        UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      if ( hKey )
        RegCloseKey(hKey);
      if ( hObject )
        CloseHandle(hObject);
      ReleaseHpkpRulesContext(qword_18015D178);
      PkiDefaultCryptFree(qword_18015D188);
      DeleteCriticalSection(&stru_180158368);
      if ( hCertStore )
        CertCloseStore(hCertStore, 0);
      return v5;
    case 1:
      dword_18015D12C = I_CryptAllocTlsEx(0);
      if ( !dword_18015D12C )
        return 0;
      break;
    case 3:
      v6 = (struct _CERT_DIAG_PIN_RULES_INFO *)I_CryptDetachTls((unsigned int)dword_18015D12C, a2, a3);
      FreeCertDiagPinRulesInfo(v6);
      return v5;
  }
  if ( !v3 )
    goto LABEL_5;
  if ( v3 == 1 )
  {
    qword_180158360 = a1;
    hChainPolicyFuncSet = (struct _FUNC_SET *)qword_1801588D0;
    if ( !(unsigned int)InstallOIDFunctionAddress(
                          0,
                          0,
                          (struct _FUNC_SET *)qword_1801588D0,
                          0xCu,
                          &stru_1801225E0,
                          0x80000000)
      || !(unsigned int)Pki_InitializeCriticalSection(&stru_180158368, v8, v9) )
    {
      return 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18002b170  push    rbx
0x18002b172  push    rbp
0x18002b173  push    rsi
0x18002b174  push    rdi
0x18002b175  push    r14
0x18002b177  push    r15
0x18002b179  sub     rsp, 38h
0x18002b17d  mov     ebx, edx
0x18002b17f  mov     r14, rcx
0x18002b182  mov     eax, edx
0x18002b184  mov     ebp, 1
0x18002b189  test    edx, edx
0x18002b18b  jz      loc_18002B27D
0x18002b191  sub     eax, ebp
0x18002b193  jz      loc_18002B21C
0x18002b199  cmp     eax, 2
0x18002b19c  jnz     short loc_18002B216
0x18002b19e  mov     ecx, cs:dword_18015D12C
0x18002b1a4  call    I_CryptDetachTls
0x18002b1a9  mov     rcx, rax; struct _CERT_DIAG_PIN_RULES_INFO *
0x18002b1ac  call    ?FreeCertDiagPinRulesInfo@@YAXPEAU_CERT_DIAG_PIN_RULES_INFO@@@Z; FreeCertDiagPinRulesInfo(_CERT_DIAG_PIN_RULES_INFO *)
0x18002b1b1  jmp     short loc_18002B207
0x18002b1b3  mov     rcx, cs:WaitHandle; WaitHandle
0x18002b1ba  test    rcx, rcx
0x18002b1bd  jnz     loc_18002B35B
0x18002b1c3  mov     rcx, cs:hKey; hKey
0x18002b1ca  test    rcx, rcx
0x18002b1cd  jnz     loc_18002B36A
0x18002b1d3  mov     rcx, cs:hObject; hObject
0x18002b1da  test    rcx, rcx
0x18002b1dd  jnz     loc_18002B375
0x18002b1e3  mov     rcx, cs:qword_18015D178; hMem
0x18002b1ea  call    _ReleaseHpkpRulesContext
0x18002b1ef  mov     rcx, cs:qword_18015D188; hMem
0x18002b1f6  call    PkiDefaultCryptFree
0x18002b1fb  test    ebx, ebx
0x18002b1fd  jz      loc_18002B30D
0x18002b203  cmp     ebx, ebp
0x18002b205  jz      short loc_18002B231
0x18002b207  mov     eax, ebp
0x18002b209  add     rsp, 38h
0x18002b20d  pop     r15
0x18002b20f  pop     r14
0x18002b211  pop     rdi
0x18002b212  pop     rsi
0x18002b213  pop     rbp
0x18002b214  pop     rbx
0x18002b215  retn
0x18002b216  test    ebx, ebx
0x18002b218  jz      short loc_18002B1B3
0x18002b21a  jmp     short loc_18002B203
0x18002b21c  xor     ecx, ecx
0x18002b21e  call    I_CryptAllocTlsEx
0x18002b223  mov     cs:dword_18015D12C, eax
0x18002b229  test    eax, eax
0x18002b22b  jnz     short loc_18002B216
0x18002b22d  xor     ebp, ebp
0x18002b22f  jmp     short loc_18002B207
0x18002b231  lea     r8, qword_1801588D0; struct _FUNC_SET *
0x18002b238  mov     cs:qword_180158360, r14
0x18002b23f  mov     cs:?hChainPolicyFuncSet@@3PEAXEA, r8; void * hChainPolicyFuncSet
0x18002b246  xor     edx, edx; unsigned int
0x18002b248  mov     [rsp+68h+var_40], 80000000h; unsigned int
0x18002b250  lea     rax, stru_1801225E0
0x18002b257  xor     ecx, ecx; hModule
0x18002b259  mov     [rsp+68h+var_48], rax; struct _CRYPT_OID_FUNC_ENTRY *
0x18002b25e  lea     r9d, [rdx+0Ch]; unsigned int
0x18002b262  call    ?InstallOIDFunctionAddress@@YAHPEAUHINSTANCE__@@KPEAU_FUNC_SET@@KQEBU_CRYPT_OID_FUNC_ENTRY@@K@Z; InstallOIDFunctionAddress(HINSTANCE__ *,ulong,_FUNC_SET *,ulong,_CRYPT_OID_FUNC_ENTRY const * const,ulong)
0x18002b267  test    eax, eax
0x18002b269  jz      short loc_18002B22D
0x18002b26b  lea     rcx, stru_180158368
0x18002b272  call    Pki_InitializeCriticalSection
0x18002b277  test    eax, eax
0x18002b279  jnz     short loc_18002B207
0x18002b27b  jmp     short loc_18002B22D
0x18002b27d  xor     edi, edi
0x18002b27f  lea     r15, qword_18015D0E0
0x18002b286  mov     rsi, rdi
0x18002b289  shl     rsi, 5
0x18002b28d  mov     rcx, [rsi+r15+10h]; WaitHandle
0x18002b292  test    rcx, rcx
0x18002b295  jnz     loc_18002B336
0x18002b29b  mov     rcx, [rsi+r15]; hKey
0x18002b29f  test    rcx, rcx
0x18002b2a2  jnz     loc_18002B345
0x18002b2a8  mov     rcx, [rsi+r15+8]; hObject
0x18002b2ad  test    rcx, rcx
0x18002b2b0  jnz     loc_18002B350
0x18002b2b6  add     rdi, rbp
0x18002b2b9  cmp     rdi, 2
0x18002b2bd  jnz     short loc_18002B286
0x18002b2bf  mov     rcx, cs:qword_18015D120; hMem
0x18002b2c6  call    _ReleaseChainPinRulesContext
0x18002b2cb  mov     ecx, cs:dword_18015D12C
0x18002b2d1  lea     rdx, _FreeCertDiagTls
0x18002b2d8  call    I_CryptFreeTls
0x18002b2dd  mov     rcx, cs:qword_18015D138; hMem
0x18002b2e4  call    PkiDefaultCryptFree
0x18002b2e9  call    ?IPS_FreeStringList@@YAXPEAU_LIST_ENTRY@@@Z; IPS_FreeStringList(_LIST_ENTRY *)
0x18002b2ee  mov     rcx, cs:qword_18015D150; this
0x18002b2f5  test    rcx, rcx
0x18002b2f8  jz      loc_18002B1B3
0x18002b2fe  xor     r8d, r8d
0x18002b301  xor     edx, edx
0x18002b303  call    I_CryptFreeLruCache
0x18002b308  jmp     loc_18002B1B3
0x18002b30d  lea     rcx, stru_180158368; lpCriticalSection
0x18002b314  call    cs:__imp_DeleteCriticalSection
0x18002b31a  mov     rcx, cs:hCertStore; hCertStore
0x18002b321  test    rcx, rcx
0x18002b324  jz      loc_18002B207
0x18002b32a  xor     edx, edx; dwFlags
0x18002b32c  call    CertCloseStore
0x18002b331  jmp     loc_18002B207
0x18002b336  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002b33a  call    cs:__imp_UnregisterWaitEx
0x18002b340  jmp     loc_18002B29B
0x18002b345  call    cs:__imp_RegCloseKey
0x18002b34b  jmp     loc_18002B2A8
0x18002b350  call    cs:__imp_CloseHandle
0x18002b356  jmp     loc_18002B2B6
0x18002b35b  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002b35f  call    cs:__imp_UnregisterWaitEx
0x18002b365  jmp     loc_18002B1C3
0x18002b36a  call    cs:__imp_RegCloseKey
0x18002b370  jmp     loc_18002B1D3
0x18002b375  call    cs:__imp_CloseHandle
0x18002b37b  jmp     loc_18002B1E3
```
