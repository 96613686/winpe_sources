# SymFunctionTableAccess64AccessRoutines

- ea: `0x18000bd00`
- end: `0x18000c006`
- name: `SymFunctionTableAccess64AccessRoutines`
- size: `774`
- prototype: `PVOID __stdcall(HANDLE hProcess, DWORD64 AddrBase, PREAD_PROCESS_MEMORY_ROUTINE64 ReadMemoryRoutine, PGET_MODULE_BASE_ROUTINE64 GetModuleBaseRoutine)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18000d0b0`

## callees

- `0x18000a820`
- `0x18000aeec`
- `0x18000af48`
- `0x18000bd00`
- `0x18000c444`
- `0x18000c76c`
- `0x18000c828`
- `0x18000ca14`
- `0x18000ca80`
- `0x180169420`
- `0x180205010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000bed7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000bf58`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000bed7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000bf58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bfda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bffc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bfda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bffc`

## string_xrefs

- `0x18000bed0`: `ntdll`
- `0x18000bf51`: `ntdll`

## pseudocode

```c
PVOID __stdcall SymFunctionTableAccess64AccessRoutines(
        HANDLE hProcess,
        DWORD64 AddrBase,
        PREAD_PROCESS_MEMORY_ROUTINE64 ReadMemoryRoutine,
        PGET_MODULE_BASE_ROUTINE64 GetModuleBaseRoutine)
{
  int (*v4)(void *, unsigned __int64, void *, unsigned int, unsigned int *); // r14
  char *v7; // rsi
  struct _PROCESS_ENTRY *ProcessEntry; // rax
  struct _PROCESS_ENTRY *v9; // rdi
  struct _MODULE_ENTRY *ModuleForPC; // rax
  __int64 v11; // rbx
  unsigned __int16 v12; // cx
  bool v13; // zf
  unsigned int v14; // edi
  unsigned int *FeCache; // r15
  struct FeCacheEntry *Direct; // rdx
  struct FeCacheEntry *v17; // rax
  struct FeCacheEntry *v18; // r14
  __int64 *v20; // rdi
  __int64 *v21; // rbx
  __int64 *v22; // r14
  int v23; // eax
  _BOOL8 v24; // rdx
  __int64 *v25; // rax
  void *(*v26)(void *, unsigned __int64); // [rsp+28h] [rbp-80h]

  v4 = ReadMemoryRoutine;
  v7 = 0;
  if ( dwTlsIndex == -1 || (ProcessEntry = FindProcessEntry(hProcess), (v9 = ProcessEntry) == 0) )
  {
    SetLastError(6u);
    return 0;
  }
  ModuleForPC = GetModuleForPC(ProcessEntry, AddrBase, 0, 1, 1, 1);
  v11 = (__int64)ModuleForPC;
  if ( ModuleForPC
    && AddrBase >= *((_QWORD *)ModuleForPC + 3)
    && AddrBase < *((_QWORD *)ModuleForPC + 3) + (unsigned __int64)*((unsigned int *)ModuleForPC + 8) )
  {
    LoadSymbols(hProcess, ModuleForPC, 0);
LABEL_7:
    v12 = *(_WORD *)(v11 + 44);
    v13 = *(_DWORD *)(v11 + 24192) == 0;
    goto LABEL_8;
  }
  v20 = (__int64 *)((char *)v9 + 16);
  v21 = (__int64 *)*v20;
  if ( *v20 )
  {
    while ( v21 != v20 )
    {
      v22 = v21;
      v21 = (__int64 *)*v21;
      v23 = _o__wcsicmp((char *)v22 + 46, L"ntdll");
      v24 = v23 == 0;
      if ( v23 && *((_WORD *)v22 + 87) )
        v24 = (unsigned int)_o__wcsicmp((char *)v22 + 174, L"ntdll") == 0;
      if ( v24 )
      {
        v11 = (unsigned __int64)v22
            & -(__int64)((unsigned int)LoadSymbols(hProcess, (struct _MODULE_ENTRY *)v22, 0) != 0);
        v4 = ReadMemoryRoutine;
        goto LABEL_32;
      }
    }
    v4 = ReadMemoryRoutine;
  }
  v11 = 0;
LABEL_32:
  if ( v11 )
    goto LABEL_7;
  v25 = (__int64 *)*v20;
  if ( !*v20 || v25 == v20 )
  {
    v14 = 0;
    goto LABEL_10;
  }
  v11 = *v20;
  v12 = *((_WORD *)v25 + 22);
  v13 = *((_DWORD *)v25 + 6048) == 0;
LABEL_8:
  if ( !v13 && v12 == 332 )
    v12 = 14948;
  v14 = v12;
LABEL_10:
  if ( !v14 )
    v14 = 34404;
  if ( v14 == 332 )
  {
LABEL_24:
    v7 = (char *)LookupFunctionEntryX86(hProcess, (struct _MODULE_ENTRY *)v11, AddrBase);
    goto LABEL_21;
  }
  FeCache = (unsigned int *)GetFeCache(v14, 1);
  if ( !FeCache )
    goto LABEL_21;
  if ( v4 && GetModuleBaseRoutine )
  {
    v17 = FunctionEntryCache::Find((FunctionEntryCache *)FeCache, hProcess, AddrBase, v4, GetModuleBaseRoutine, v26);
    goto LABEL_18;
  }
  if ( dwTlsIndex != -1 )
  {
    Direct = FunctionEntryCache::FindDirect(
               (FunctionEntryCache *)FeCache,
               hProcess,
               AddrBase,
               (int (*)(void *, unsigned __int64, void *, unsigned int, unsigned int *))ReadInProcMemory,
               SymGetModuleBase64,
               v26);
    if ( Direct )
    {
      v17 = (struct FeCacheEntry *)(*(__int64 (__fastcall **)(unsigned int *, struct FeCacheEntry *, HANDLE, __int64 (__fastcall *)(void *, char *, char *, unsigned int, unsigned int *), DWORD64 (__stdcall *)(HANDLE, DWORD64), _QWORD))(*(_QWORD *)FeCache + 32LL))(
                                     FeCache,
                                     Direct,
                                     hProcess,
                                     ReadInProcMemory,
                                     SymGetModuleBase64,
                                     0);
LABEL_18:
      v18 = v17;
      goto LABEL_19;
    }
  }
  v18 = 0;
LABEL_19:
  if ( v18 )
  {
    v7 = (char *)GetTlsPtr() + 96;
    memcpy_0(v7, v18, FeCache[4]);
    goto LABEL_21;
  }
  if ( v14 == 14948 )
    goto LABEL_24;
LABEL_21:
  if ( v7 )
    return v7;
  SetLastError(0x1E7u);
  return 0;
}

```

## disassembly

```asm
0x18000bd00  push    rbx
0x18000bd02  push    rsi
0x18000bd03  push    rdi
0x18000bd04  push    r12
0x18000bd06  push    r13
0x18000bd08  push    r14
0x18000bd0a  push    r15
0x18000bd0c  sub     rsp, 70h
0x18000bd10  mov     [rsp+0A8h+var_48], r9
0x18000bd15  mov     r14, r8
0x18000bd18  mov     [rsp+0A8h+var_60], r8
0x18000bd1d  mov     r13, rdx
0x18000bd20  mov     r12, rcx
0x18000bd23  xor     r15d, r15d
0x18000bd26  mov     esi, r15d
0x18000bd29  cmp     cs:dwTlsIndex, 0FFFFFFFFh
0x18000bd30  jz      loc_18000BFF7
0x18000bd36  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x18000bd3b  mov     rdi, rax
0x18000bd3e  test    rax, rax
0x18000bd41  jz      loc_18000BF6C
0x18000bd47  mov     byte ptr [rsp+0A8h+var_80], 1; void *(*)(void *, unsigned __int64)
0x18000bd4c  mov     byte ptr [rsp+0A8h+var_88], 1; bool
0x18000bd51  mov     r9b, 1; bool
0x18000bd54  xor     r8d, r8d; bool
0x18000bd57  mov     rdx, r13; unsigned __int64
0x18000bd5a  mov     rcx, rax; struct _PROCESS_ENTRY *
0x18000bd5d  call    ?GetModuleForPC@@YAPEAU_MODULE_ENTRY@@PEAU_PROCESS_ENTRY@@_K_N222@Z; GetModuleForPC(_PROCESS_ENTRY *,unsigned __int64,bool,bool,bool,bool)
0x18000bd62  mov     rbx, rax
0x18000bd65  mov     [rsp+0A8h+var_58], rax
0x18000bd6a  test    rax, rax
0x18000bd6d  jz      loc_18000BEA8
0x18000bd73  cmp     r13, [rax+18h]
0x18000bd77  jb      loc_18000BEA8
0x18000bd7d  mov     eax, [rax+20h]
0x18000bd80  add     rax, [rbx+18h]
0x18000bd84  cmp     r13, rax
0x18000bd87  jnb     loc_18000BEA8
0x18000bd8d  xor     r8d, r8d; unsigned int
0x18000bd90  mov     rdx, rbx; struct _MODULE_ENTRY *
0x18000bd93  mov     rcx, r12; void *
0x18000bd96  call    ?LoadSymbols@@YAHPEAXPEAU_MODULE_ENTRY@@K@Z; LoadSymbols(void *,_MODULE_ENTRY *,ulong)
0x18000bd9b  movzx   ecx, word ptr [rbx+2Ch]
0x18000bd9f  cmp     [rbx+5E80h], r15d
0x18000bda6  mov     eax, 14Ch
0x18000bdab  jnz     loc_18000BF85
0x18000bdb1  movzx   edi, cx
0x18000bdb4  mov     ecx, 8664h
0x18000bdb9  test    edi, edi
0x18000bdbb  cmovz   edi, ecx
0x18000bdbe  cmp     edi, eax
0x18000bdc0  jz      loc_18000BE90
0x18000bdc6  mov     edx, 1; int
0x18000bdcb  mov     ecx, edi; unsigned int
0x18000bdcd  call    ?GetFeCache@@YAPEAVFunctionEntryCache@@KH@Z; GetFeCache(ulong,int)
0x18000bdd2  mov     r15, rax
0x18000bdd5  test    rax, rax
0x18000bdd8  jz      loc_18000BE6D
0x18000bdde  test    r14, r14
0x18000bde1  jnz     loc_18000BFA5
0x18000bde7  cmp     cs:dwTlsIndex, 0FFFFFFFFh
0x18000bdee  jz      loc_18000BFCE
0x18000bdf4  lea     r14, SymGetModuleBase64
0x18000bdfb  mov     [rsp+0A8h+var_88], r14; unsigned __int64 (*)(void *, unsigned __int64)
0x18000be00  lea     r9, ?ReadInProcMemory@@YAHPEAX_K0KPEAK@Z; int (*)(void *, unsigned __int64, void *, unsigned int, unsigned int *)
0x18000be07  mov     r8, r13; unsigned __int64
0x18000be0a  mov     rdx, r12; void *
0x18000be0d  mov     rcx, r15; this
0x18000be10  call    ?FindDirect@FunctionEntryCache@@QEAAPEAUFeCacheEntry@@PEAX_KP6AH010KPEAK@ZP6A_K01@ZP6APEAX01@Z@Z; FunctionEntryCache::FindDirect(void *,unsigned __int64,int (*)(void *,unsigned __int64,void *,ulong,ulong *),unsigned __int64 (*)(void *,unsigned __int64),void * (*)(void *,unsigned __int64))
0x18000be15  mov     rdx, rax
0x18000be18  test    rax, rax
0x18000be1b  jz      loc_18000BFCE
0x18000be21  mov     rax, [r15]
0x18000be24  mov     [rsp+0A8h+var_80], 0
0x18000be2d  mov     [rsp+0A8h+var_88], r14
0x18000be32  lea     r9, ?ReadInProcMemory@@YAHPEAX_K0KPEAK@Z; ReadInProcMemory(void *,unsigned __int64,void *,ulong,ulong *)
0x18000be39  mov     r8, r12
0x18000be3c  mov     rcx, r15
0x18000be3f  mov     rax, [rax+20h]
0x18000be43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be48  mov     r14, rax
0x18000be4b  test    r14, r14
0x18000be4e  jz      short loc_18000BE88
0x18000be50  call    ?GetTlsPtr@@YAPEAUTLS@@XZ; GetTlsPtr(void)
0x18000be55  lea     rsi, [rax+60h]
0x18000be59  mov     [rsp+0A8h+var_50], rsi
0x18000be5e  mov     r8d, [r15+10h]; Size
0x18000be62  mov     rdx, r14; Src
0x18000be65  mov     rcx, rsi; void *
0x18000be68  call    memcpy_0
0x18000be6d  test    rsi, rsi
0x18000be70  jnz     loc_18000BFD6
0x18000be76  mov     ecx, 1E7h; dwErrCode
0x18000be7b  call    cs:__imp_SetLastError
0x18000be81  xor     eax, eax
0x18000be83  jmp     loc_18000BFE2
0x18000be88  cmp     edi, 3A64h
0x18000be8e  jnz     short loc_18000BE6D
0x18000be90  mov     r8, r13; unsigned __int64
0x18000be93  mov     rdx, rbx; struct _MODULE_ENTRY *
0x18000be96  mov     rcx, r12; void *
0x18000be99  call    ?LookupFunctionEntryX86@@YAPEAXPEAXPEAU_MODULE_ENTRY@@_K@Z; LookupFunctionEntryX86(void *,_MODULE_ENTRY *,unsigned __int64)
0x18000be9e  mov     [rsp+0A8h+var_50], rax
0x18000bea3  mov     rsi, rax
0x18000bea6  jmp     short loc_18000BE6D
0x18000bea8  mov     [rsp+0A8h+var_68], r15d
0x18000bead  add     rdi, 10h
0x18000beb1  mov     rbx, [rdi]
0x18000beb4  test    rbx, rbx
0x18000beb7  jz      loc_18000BF80
0x18000bebd  cmp     rbx, rdi
0x18000bec0  jz      loc_18000BF7B
0x18000bec6  mov     r14, rbx
0x18000bec9  mov     rbx, [rbx]
0x18000becc  lea     rcx, [r14+2Eh]
0x18000bed0  lea     rdx, aNtdll; "ntdll"
0x18000bed7  call    cs:__imp__o__wcsicmp
0x18000bedd  mov     edx, r15d
0x18000bee0  test    eax, eax
0x18000bee2  setz    dl
0x18000bee5  mov     [rsp+0A8h+var_68], edx
0x18000bee9  test    eax, eax
0x18000beeb  jz      short loc_18000BEFA
0x18000beed  lea     rcx, [r14+0AEh]
0x18000bef4  cmp     [rcx], r15w
0x18000bef8  jnz     short loc_18000BF51
0x18000befa  test    edx, edx
0x18000befc  jz      short loc_18000BF4C
0x18000befe  xor     r8d, r8d; unsigned int
0x18000bf01  mov     rdx, r14; struct _MODULE_ENTRY *
0x18000bf04  mov     rcx, r12; void *
0x18000bf07  call    ?LoadSymbols@@YAHPEAXPEAU_MODULE_ENTRY@@K@Z; LoadSymbols(void *,_MODULE_ENTRY *,ulong)
0x18000bf0c  neg     eax
0x18000bf0e  sbb     rbx, rbx
0x18000bf11  and     rbx, r14
0x18000bf14  mov     r14, [rsp+0A8h+var_60]
0x18000bf19  mov     [rsp+0A8h+var_58], rbx
0x18000bf1e  test    rbx, rbx
0x18000bf21  jnz     loc_18000BD9B
0x18000bf27  mov     rax, [rdi]
0x18000bf2a  test    rax, rax
0x18000bf2d  jz      short loc_18000BF98
0x18000bf2f  cmp     rax, rdi
0x18000bf32  jz      short loc_18000BF98
0x18000bf34  mov     rbx, rax
0x18000bf37  mov     [rsp+0A8h+var_58], rax
0x18000bf3c  movzx   ecx, word ptr [rax+2Ch]
0x18000bf40  cmp     [rax+5E80h], r15d
0x18000bf47  jmp     loc_18000BDA6
0x18000bf4c  jmp     loc_18000BEBD
0x18000bf51  lea     rdx, aNtdll; "ntdll"
0x18000bf58  call    cs:__imp__o__wcsicmp
0x18000bf5e  mov     edx, r15d
0x18000bf61  test    eax, eax
0x18000bf63  setz    dl
0x18000bf66  mov     [rsp+0A8h+var_68], edx
0x18000bf6a  jmp     short loc_18000BEFA
0x18000bf6c  mov     ecx, 6; dwErrCode
0x18000bf71  call    cs:__imp_SetLastError
0x18000bf77  xor     eax, eax
0x18000bf79  jmp     short loc_18000BFE2
0x18000bf7b  mov     r14, [rsp+0A8h+var_60]
0x18000bf80  mov     rbx, r15
0x18000bf83  jmp     short loc_18000BF19
0x18000bf85  cmp     cx, ax
0x18000bf88  jnz     loc_18000BDB1
0x18000bf8e  mov     ecx, 3A64h
0x18000bf93  jmp     loc_18000BDB1
0x18000bf98  mov     edi, r15d
0x18000bf9b  mov     eax, 14Ch
0x18000bfa0  jmp     loc_18000BDB4
0x18000bfa5  mov     rax, [rsp+0A8h+var_48]
0x18000bfaa  test    rax, rax
0x18000bfad  jz      loc_18000BDE7
0x18000bfb3  mov     [rsp+0A8h+var_88], rax; unsigned __int64 (*)(void *, unsigned __int64)
0x18000bfb8  mov     r9, r14; int (*)(void *, unsigned __int64, void *, unsigned int, unsigned int *)
0x18000bfbb  mov     r8, r13; unsigned __int64
0x18000bfbe  mov     rdx, r12; void *
0x18000bfc1  mov     rcx, r15; this
0x18000bfc4  call    ?Find@FunctionEntryCache@@QEAAPEAUFeCacheEntry@@PEAX_KP6AH010KPEAK@ZP6A_K01@ZP6APEAX01@Z@Z; FunctionEntryCache::Find(void *,unsigned __int64,int (*)(void *,unsigned __int64,void *,ulong,ulong *),unsigned __int64 (*)(void *,unsigned __int64),void * (*)(void *,unsigned __int64))
0x18000bfc9  jmp     loc_18000BE48
0x18000bfce  xor     r14d, r14d
0x18000bfd1  jmp     loc_18000BE4B
0x18000bfd6  jmp     short loc_18000BFF2
0x18000bfd8  mov     ecx, eax; dwErrCode
0x18000bfda  call    cs:__imp_SetLastError
0x18000bfe0  xor     eax, eax
0x18000bfe2  add     rsp, 70h
0x18000bfe6  pop     r15
0x18000bfe8  pop     r14
0x18000bfea  pop     r13
0x18000bfec  pop     r12
0x18000bfee  pop     rdi
0x18000bfef  pop     rsi
0x18000bff0  pop     rbx
0x18000bff1  retn
0x18000bff2  mov     rax, rsi
0x18000bff5  jmp     short loc_18000BFE2
0x18000bff7  mov     ecx, 6; dwErrCode
0x18000bffc  call    cs:__imp_SetLastError
0x18000c002  xor     eax, eax
0x18000c004  jmp     short loc_18000BFE2
```
