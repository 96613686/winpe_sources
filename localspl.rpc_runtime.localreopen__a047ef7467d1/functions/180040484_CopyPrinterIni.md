# CopyPrinterIni

- ea: `0x180040484`
- end: `0x18004066c`
- name: `CopyPrinterIni`
- size: `488`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180038d84`
- `0x1800590d0`

## callees

- `0x180004cfc`
- `0x180005cc0`
- `0x180008520`
- `0x180008560`
- `0x1800085ac`
- `0x1800086e0`
- `0x180008730`
- `0x180012dc0`
- `0x180025938`
- `0x18002595c`
- `0x180040484`
- `0x18009fd60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004052e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004052e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800405f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800405f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800405df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800405df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800405a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800405a9`
- `SPOOLSS!DllFreeSplStr` at `0x180040639`
- `SPOOLSS!DllFreeSplStr` at `0x180040642`
- `SPOOLSS!DllFreeSplStr` at `0x180040639`
- `SPOOLSS!DllFreeSplStr` at `0x180040642`
- `SPOOLSS!DllFreeSplMem` at `0x1800405fe`
- `SPOOLSS!DllFreeSplMem` at `0x1800405fe`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800404b7`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800404b7`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18004064b`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18004064b`

## pseudocode

```c
HANDLE __fastcall CopyPrinterIni(__int64 a1, __int64 a2)
{
  unsigned int *v2; // rbx
  HANDLE result; // rax
  void *v6; // r13
  __int64 v7; // r15
  __int64 v8; // rsi
  unsigned int *v9; // r14
  __int64 v10; // rcx
  unsigned int v11; // [rsp+70h] [rbp+8h]

  v2 = *(unsigned int **)(a1 + 280);
  result = RevertToPrinterSelf();
  v6 = result;
  if ( result )
  {
    v7 = SubChar(*(_QWORD *)(a1 + 24));
    if ( v7 )
    {
      v8 = SubChar(a2);
      if ( v8 )
      {
        if ( v2 )
          SafeIncrementReference(v2 + 4);
        v9 = (unsigned int *)(a1 + 16);
        if ( SafeIncrementReference((unsigned int *)(a1 + 16)) > *(_DWORD *)(a1 + 248) )
          *(_DWORD *)(a1 + 248) = *v9;
        v11 = LeaveSplSemAndResetCount();
        EnterCriticalSection(&RegistryLock);
        EnterSplSem(0);
        CloneIniSpooler(v2);
        LeaveSplSem(v10);
        LeaveCriticalSection(&RegistryLock);
        DllFreeSplMem(0);
        EnterSplSemAndRestoreCount(v11);
        if ( *v9 )
          SafeDecrementReference(v9);
        if ( v2 )
        {
          if ( v2[4] )
            SafeDecrementReference(v2 + 4);
          DeleteSpoolerCheck(v2);
        }
      }
    }
    else
    {
      v8 = 0;
    }
    DllFreeSplStr(v7);
    DllFreeSplStr(v8);
    ImpersonatePrinterClient(v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180040484  mov     rax, rsp
0x180040487  mov     [rax+10h], rbx
0x18004048b  push    rbp
0x18004048c  push    rsi
0x18004048d  push    rdi
0x18004048e  push    r12
0x180040490  push    r13
0x180040492  push    r14
0x180040494  push    r15
0x180040496  sub     rsp, 30h
0x18004049a  mov     rbx, [rcx+118h]
0x1800404a1  mov     r12, rdx
0x1800404a4  mov     rdi, rcx
0x1800404a7  mov     qword ptr [rax+20h], 0
0x1800404af  mov     qword ptr [rax+18h], 0
0x1800404b7  call    cs:__imp_RevertToPrinterSelf
0x1800404bd  mov     r13, rax
0x1800404c0  test    rax, rax
0x1800404c3  jz      loc_180040657
0x1800404c9  mov     rcx, [rdi+18h]
0x1800404cd  call    SubChar
0x1800404d2  mov     r15, rax
0x1800404d5  test    rax, rax
0x1800404d8  jnz     short loc_1800404E3
0x1800404da  xor     esi, esi
0x1800404dc  xor     edi, edi
0x1800404de  jmp     loc_180040636
0x1800404e3  mov     rcx, r12
0x1800404e6  call    SubChar
0x1800404eb  mov     rsi, rax
0x1800404ee  test    rax, rax
0x1800404f1  jz      short loc_1800404DC
0x1800404f3  test    rbx, rbx
0x1800404f6  jz      short loc_180040501
0x1800404f8  lea     rcx, [rbx+10h]; unsigned int *
0x1800404fc  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180040501  lea     r14, [rdi+10h]
0x180040505  mov     rcx, r14; unsigned int *
0x180040508  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x18004050d  cmp     eax, [rdi+0F8h]
0x180040513  jbe     short loc_18004051E
0x180040515  mov     eax, [r14]
0x180040518  mov     [rdi+0F8h], eax
0x18004051e  call    LeaveSplSemAndResetCount
0x180040523  lea     rcx, RegistryLock; lpCriticalSection
0x18004052a  mov     [rsp+68h+arg_0], eax
0x18004052e  call    cs:__imp_EnterCriticalSection
0x180040534  xor     ecx, ecx
0x180040536  call    EnterSplSem
0x18004053b  lea     rdx, [rsp+68h+arg_10]
0x180040543  mov     rcx, rbx; Src
0x180040546  call    CloneIniSpooler
0x18004054b  mov     rbp, [rsp+68h+arg_10]
0x180040553  test    eax, eax
0x180040555  jz      loc_1800405E7
0x18004055b  test    rbp, rbp
0x18004055e  jz      loc_1800405E7
0x180040564  call    LeaveSplSem
0x180040569  mov     rcx, [rbp+0F0h]; int
0x180040570  mov     r9, rsi; int
0x180040573  mov     r8, rcx; int
0x180040576  mov     [rsp+68h+phkResult], rbp; struct _INISPOOLER *
0x18004057b  mov     rdx, r15; int
0x18004057e  call    CopyRegistryKeys
0x180040583  mov     edi, eax
0x180040585  test    eax, eax
0x180040587  jz      short loc_1800405EE
0x180040589  mov     rcx, [rbp+0F0h]; hKey
0x180040590  lea     rax, [rsp+68h+hKey]
0x180040598  mov     r9d, 20006h; samDesired
0x18004059e  mov     [rsp+68h+phkResult], rax; phkResult
0x1800405a3  xor     r8d, r8d; ulOptions
0x1800405a6  mov     rdx, rsi; lpSubKey
0x1800405a9  call    cs:__imp_RegOpenKeyExW
0x1800405af  test    eax, eax
0x1800405b1  jnz     short loc_1800405EE
0x1800405b3  mov     rcx, [rsp+68h+hKey]; void *
0x1800405bb  lea     r9, [rsp+68h+arg_10]
0x1800405c3  mov     r8, r12
0x1800405c6  mov     [rsp+68h+phkResult], rbp; struct _INISPOOLER *
0x1800405cb  lea     rdx, szName
0x1800405d2  call    RegSetString
0x1800405d7  mov     rcx, [rsp+68h+hKey]; hKey
0x1800405df  call    cs:__imp_RegCloseKey
0x1800405e5  jmp     short loc_1800405EE
0x1800405e7  xor     edi, edi
0x1800405e9  call    LeaveSplSem
0x1800405ee  lea     rcx, RegistryLock; lpCriticalSection
0x1800405f5  call    cs:__imp_LeaveCriticalSection
0x1800405fb  mov     rcx, rbp
0x1800405fe  call    cs:__imp_DllFreeSplMem
0x180040604  mov     ecx, [rsp+68h+arg_0]
0x180040608  call    EnterSplSemAndRestoreCount
0x18004060d  cmp     dword ptr [r14], 0
0x180040611  jz      short loc_18004061B
0x180040613  mov     rcx, r14; unsigned int *
0x180040616  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x18004061b  test    rbx, rbx
0x18004061e  jz      short loc_180040636
0x180040620  lea     rcx, [rbx+10h]; unsigned int *
0x180040624  cmp     dword ptr [rcx], 0
0x180040627  jz      short loc_18004062E
0x180040629  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x18004062e  mov     rcx, rbx
0x180040631  call    DeleteSpoolerCheck
0x180040636  mov     rcx, r15
0x180040639  call    cs:__imp_DllFreeSplStr
0x18004063f  mov     rcx, rsi
0x180040642  call    cs:__imp_DllFreeSplStr
0x180040648  mov     rcx, r13; hToken
0x18004064b  call    cs:__imp_ImpersonatePrinterClient
0x180040651  neg     eax
0x180040653  sbb     eax, eax
0x180040655  and     eax, edi
0x180040657  mov     rbx, [rsp+68h+arg_8]
0x18004065c  add     rsp, 30h
0x180040660  pop     r15
0x180040662  pop     r14
0x180040664  pop     r13
0x180040666  pop     r12
0x180040668  pop     rdi
0x180040669  pop     rsi
0x18004066a  pop     rbp
0x18004066b  retn
```
