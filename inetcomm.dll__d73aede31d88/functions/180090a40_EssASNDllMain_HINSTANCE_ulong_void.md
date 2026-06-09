# EssASNDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x180090a40`
- end: `0x180090ae9`
- name: `?EssASNDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `169`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800212e0`

## callees

- `0x180090a40`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180090ad9`
- `KERNEL32!DeleteCriticalSection` at `0x180090ad9`
- `KERNEL32!FreeLibrary` at `0x180090aad`
- `KERNEL32!FreeLibrary` at `0x180090abf`
- `KERNEL32!FreeLibrary` at `0x180090aad`
- `KERNEL32!FreeLibrary` at `0x180090abf`
- `KERNEL32!InitializeCriticalSection` at `0x180090a58`
- `KERNEL32!InitializeCriticalSection` at `0x180090a58`
- `KERNEL32!LeaveCriticalSection` at `0x180090acc`
- `KERNEL32!LeaveCriticalSection` at `0x180090acc`
- `KERNEL32!EnterCriticalSection` at `0x180090a9b`
- `KERNEL32!EnterCriticalSection` at `0x180090a9b`

## pseudocode

```c
__int64 __fastcall EssASNDllMain(HINSTANCE a1, __int64 a2, void *a3)
{
  if ( (_DWORD)a2 )
  {
    if ( (_DWORD)a2 == 1 )
      InitializeCriticalSection(&stru_1800F33B8);
  }
  else
  {
    if ( ICM_hAsn1Module )
    {
      ((void (__fastcall *)(_QWORD, __int64, void *))VAR_I_CryptUninstallAsn1Module)(ICM_hAsn1Module, a2, a3);
      ((void (__fastcall *)(__int64))VAR_ASN1_CloseModule)(ESS_Module);
      ESS_Module = 0;
    }
    EnterCriticalSection(&stru_1800F33B8);
    if ( hModule )
      FreeLibrary(hModule);
    if ( qword_1800F33A0 )
      FreeLibrary(qword_1800F33A0);
    LeaveCriticalSection(&stru_1800F33B8);
    DeleteCriticalSection(&stru_1800F33B8);
  }
  return 1;
}

```

## disassembly

```asm
0x180090a40  sub     rsp, 28h
0x180090a44  test    edx, edx
0x180090a46  jz      short loc_180090A60
0x180090a48  cmp     edx, 1
0x180090a4b  jnz     loc_180090ADF
0x180090a51  lea     rcx, stru_1800F33B8; lpCriticalSection
0x180090a58  call    cs:__imp_InitializeCriticalSection
0x180090a5e  jmp     short loc_180090ADF
0x180090a60  mov     ecx, cs:?ICM_hAsn1Module@@3KA; ulong ICM_hAsn1Module
0x180090a66  test    ecx, ecx
0x180090a68  jz      short loc_180090A94
0x180090a6a  mov     rax, cs:?VAR_I_CryptUninstallAsn1Module@@3P6AHK@ZEA; int (*VAR_I_CryptUninstallAsn1Module)(ulong)
0x180090a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090a76  mov     rcx, cs:ESS_Module
0x180090a7d  mov     rax, cs:?VAR_ASN1_CloseModule@@3P6AXPEAUtagASN1module_t@@@ZEA; void (*VAR_ASN1_CloseModule)(tagASN1module_t *)
0x180090a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090a89  mov     cs:ESS_Module, 0
0x180090a94  lea     rcx, stru_1800F33B8; lpCriticalSection
0x180090a9b  call    cs:__imp_EnterCriticalSection
0x180090aa1  mov     rcx, cs:hModule; hLibModule
0x180090aa8  test    rcx, rcx
0x180090aab  jz      short loc_180090AB3
0x180090aad  call    cs:__imp_FreeLibrary
0x180090ab3  mov     rcx, cs:qword_1800F33A0; hLibModule
0x180090aba  test    rcx, rcx
0x180090abd  jz      short loc_180090AC5
0x180090abf  call    cs:__imp_FreeLibrary
0x180090ac5  lea     rcx, stru_1800F33B8; lpCriticalSection
0x180090acc  call    cs:__imp_LeaveCriticalSection
0x180090ad2  lea     rcx, stru_1800F33B8; lpCriticalSection
0x180090ad9  call    cs:__imp_DeleteCriticalSection
0x180090adf  mov     eax, 1
0x180090ae4  add     rsp, 28h
0x180090ae8  retn
```
