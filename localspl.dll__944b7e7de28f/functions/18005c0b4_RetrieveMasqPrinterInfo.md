# RetrieveMasqPrinterInfo

- ea: `0x18005c0b4`
- end: `0x18005c2c7`
- name: `RetrieveMasqPrinterInfo`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005ab8c`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x180040830`
- `0x180042ad0`
- `0x1800436b8`
- `0x1800436fc`
- `0x18005c0b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c1df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c1df`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005c222`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005c23d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005c222`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005c23d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005c20d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005c22c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005c20d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005c22c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005c277`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005c277`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c1a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c1b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c1a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c1b7`
- `SPOOLSS!DllFreeSplMem` at `0x18005c1c0`
- `SPOOLSS!DllFreeSplMem` at `0x18005c1ee`
- `SPOOLSS!DllFreeSplMem` at `0x18005c1c0`
- `SPOOLSS!DllFreeSplMem` at `0x18005c1ee`
- `SPOOLSS!DllAllocSplMem` at `0x18005c15d`
- `SPOOLSS!DllAllocSplMem` at `0x18005c298`
- `SPOOLSS!DllAllocSplMem` at `0x18005c15d`
- `SPOOLSS!DllAllocSplMem` at `0x18005c298`

## pseudocode

```c
__int64 __fastcall RetrieveMasqPrinterInfo(__int64 a1, __int64 *a2, int *a3)
{
  unsigned int PrinterInfoFromRouter; // eax
  unsigned int v6; // esi
  unsigned int *v7; // rdi
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rbx
  unsigned int *v11; // rcx
  DWORD v12; // ecx
  __int64 v13; // rcx
  HANDLE CurrentThread; // rax
  HANDLE v16; // rax
  HANDLE v17; // rbp
  __int64 v18; // rax
  HANDLE v19[9]; // [rsp+30h] [rbp-48h] BYREF
  DWORD ThreadId; // [rsp+80h] [rbp+8h] BYREF

  NSecurityLibrary::Low2MediumIntegrity::Low2MediumIntegrity(
    (NSecurityLibrary::Low2MediumIntegrity *)v19,
    (__int64)a2,
    a3);
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 168) + 316LL) & 4) != 0 )
  {
    v7 = *(unsigned int **)(a1 + 64);
    v8 = 0;
    EnterSplSem(0);
    if ( v7[104] || (v7[104] = 1, v8 = 1, !v7) || SafeIncrementReference(v7 + 4) <= v7[62] )
    {
      LeaveSplSem(v9);
      if ( !v8 )
        goto LABEL_19;
    }
    else
    {
      v7[62] = v7[4];
      LeaveSplSem(v9);
    }
    ThreadId = 0;
    v10 = DllAllocSplMem(16);
    if ( v10 )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xCu, 0, (PHANDLE)v10) )
      {
        v16 = GetCurrentThread();
        v6 = OpenThreadToken(v16, 0xCu, 1, (PHANDLE)v10);
        if ( !v6 )
          goto LABEL_10;
      }
      *(_QWORD *)(v10 + 8) = v7;
      v17 = CreateThread(0, 0, AsyncPopulateMasqPrinterCache, (LPVOID)v10, 0, &ThreadId);
      if ( v17 )
      {
        v6 = 1;
        v10 = 0;
        CloseHandle(v17);
        goto LABEL_14;
      }
    }
    v6 = 0;
LABEL_10:
    EnterSplSem(0);
    v7[104] = 0;
    if ( v7 )
    {
      v11 = v7 + 4;
      if ( v7[4] )
        SafeDecrementReference(v11);
    }
    LeaveSplSem(v11);
LABEL_14:
    if ( v10 )
    {
      if ( *(_QWORD *)v10 )
        CloseHandle(*(HANDLE *)v10);
      DllFreeSplMem(v10);
    }
    if ( !v6 )
      goto LABEL_23;
LABEL_19:
    EnterSplSem(0);
    v12 = v7[103];
    if ( v12 )
    {
      SetLastError(v12);
    }
    else
    {
      v18 = DllAllocSplMem(136);
      if ( v18 )
      {
        v6 = 1;
        *(_DWORD *)(v18 + 124) = v7[101];
        v13 = v7[102];
        *(_DWORD *)(v18 + 128) = v13;
        *a2 = v18;
        goto LABEL_22;
      }
    }
    v6 = 0;
LABEL_22:
    LeaveSplSem(v13);
LABEL_23:
    DllFreeSplMem(0);
    goto LABEL_24;
  }
  PrinterInfoFromRouter = GetPrinterInfoFromRouter(*(HANDLE *)(a1 + 104));
  v6 = BoolFromStatus(PrinterInfoFromRouter);
LABEL_24:
  NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity(v19);
  return v6;
}

```

## disassembly

```asm
0x18005c0b4  push    rbx
0x18005c0b6  push    rbp
0x18005c0b7  push    rsi
0x18005c0b8  push    rdi
0x18005c0b9  push    r12
0x18005c0bb  push    r14
0x18005c0bd  sub     rsp, 48h
0x18005c0c1  mov     rdi, rcx
0x18005c0c4  mov     r14, rdx
0x18005c0c7  lea     rcx, [rsp+78h+var_48]; this
0x18005c0cc  call    ??0Low2MediumIntegrity@NSecurityLibrary@@QEAA@XZ; NSecurityLibrary::Low2MediumIntegrity::Low2MediumIntegrity(void)
0x18005c0d1  mov     rax, [rdi+0A8h]
0x18005c0d8  test    byte ptr [rax+13Ch], 4
0x18005c0df  jnz     short loc_18005C0FB
0x18005c0e1  mov     rcx, [rdi+68h]; hPrinter
0x18005c0e5  mov     rdx, r14
0x18005c0e8  call    GetPrinterInfoFromRouter
0x18005c0ed  mov     ecx, eax
0x18005c0ef  call    BoolFromStatus
0x18005c0f4  mov     esi, eax
0x18005c0f6  jmp     loc_18005C1F4
0x18005c0fb  mov     rdi, [rdi+40h]
0x18005c0ff  xor     ecx, ecx
0x18005c101  xor     ebx, ebx
0x18005c103  call    EnterSplSem
0x18005c108  lea     r12d, [rbx+1]
0x18005c10c  cmp     [rdi+1A0h], ebx
0x18005c112  jnz     short loc_18005C144
0x18005c114  mov     [rdi+1A0h], r12d
0x18005c11b  mov     ebx, r12d
0x18005c11e  test    rdi, rdi
0x18005c121  jz      short loc_18005C144
0x18005c123  lea     rcx, [rdi+10h]; unsigned int *
0x18005c127  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x18005c12c  cmp     eax, [rdi+0F8h]
0x18005c132  jbe     short loc_18005C144
0x18005c134  mov     eax, [rdi+10h]
0x18005c137  mov     [rdi+0F8h], eax
0x18005c13d  call    LeaveSplSem
0x18005c142  jmp     short loc_18005C14D
0x18005c144  call    LeaveSplSem
0x18005c149  test    ebx, ebx
0x18005c14b  jz      short loc_18005C1CA
0x18005c14d  mov     ecx, 10h
0x18005c152  mov     [rsp+78h+ThreadId], 0
0x18005c15d  call    cs:__imp_DllAllocSplMem
0x18005c163  mov     rbx, rax
0x18005c166  test    rax, rax
0x18005c169  jnz     loc_18005C20D
0x18005c16f  xor     ebp, ebp
0x18005c171  xor     esi, esi
0x18005c173  xor     ecx, ecx
0x18005c175  call    EnterSplSem
0x18005c17a  mov     dword ptr [rdi+1A0h], 0
0x18005c184  test    rdi, rdi
0x18005c187  jz      short loc_18005C197
0x18005c189  lea     rcx, [rdi+10h]; unsigned int *
0x18005c18d  cmp     dword ptr [rcx], 0
0x18005c190  jz      short loc_18005C197
0x18005c192  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x18005c197  call    LeaveSplSem
0x18005c19c  test    rbp, rbp
0x18005c19f  jz      short loc_18005C1AA
0x18005c1a1  mov     rcx, rbp; hObject
0x18005c1a4  call    cs:__imp_CloseHandle
0x18005c1aa  test    rbx, rbx
0x18005c1ad  jz      short loc_18005C1C6
0x18005c1af  mov     rcx, [rbx]; hObject
0x18005c1b2  test    rcx, rcx
0x18005c1b5  jz      short loc_18005C1BD
0x18005c1b7  call    cs:__imp_CloseHandle
0x18005c1bd  mov     rcx, rbx
0x18005c1c0  call    cs:__imp_DllFreeSplMem
0x18005c1c6  test    esi, esi
0x18005c1c8  jz      short loc_18005C1EC
0x18005c1ca  xor     ecx, ecx
0x18005c1cc  call    EnterSplSem
0x18005c1d1  mov     ecx, [rdi+19Ch]; dwErrCode
0x18005c1d7  test    ecx, ecx
0x18005c1d9  jz      loc_18005C293
0x18005c1df  call    cs:__imp_SetLastError
0x18005c1e5  xor     esi, esi
0x18005c1e7  call    LeaveSplSem
0x18005c1ec  xor     ecx, ecx
0x18005c1ee  call    cs:__imp_DllFreeSplMem
0x18005c1f4  lea     rcx, [rsp+78h+var_48]; this
0x18005c1f9  call    ??1Low2MediumIntegrity@NSecurityLibrary@@QEAA@XZ; NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity(void)
0x18005c1fe  mov     eax, esi
0x18005c200  add     rsp, 48h
0x18005c204  pop     r14
0x18005c206  pop     r12
0x18005c208  pop     rdi
0x18005c209  pop     rsi
0x18005c20a  pop     rbp
0x18005c20b  pop     rbx
0x18005c20c  retn
0x18005c20d  call    cs:__imp_GetCurrentThread
0x18005c213  xor     r8d, r8d; OpenAsSelf
0x18005c216  mov     r9, rbx; TokenHandle
0x18005c219  mov     rcx, rax; ThreadHandle
0x18005c21c  lea     esi, [r8+0Ch]
0x18005c220  mov     edx, esi; DesiredAccess
0x18005c222  call    cs:__imp_OpenThreadToken
0x18005c228  test    eax, eax
0x18005c22a  jnz     short loc_18005C250
0x18005c22c  call    cs:__imp_GetCurrentThread
0x18005c232  mov     r9, rbx; TokenHandle
0x18005c235  mov     r8d, r12d; OpenAsSelf
0x18005c238  mov     rcx, rax; ThreadHandle
0x18005c23b  mov     edx, esi; DesiredAccess
0x18005c23d  call    cs:__imp_OpenThreadToken
0x18005c243  mov     esi, eax
0x18005c245  test    eax, eax
0x18005c247  jnz     short loc_18005C250
0x18005c249  xor     ebp, ebp
0x18005c24b  jmp     loc_18005C173
0x18005c250  lea     rax, [rsp+78h+ThreadId]
0x18005c258  mov     [rbx+8], rdi
0x18005c25c  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x18005c261  lea     r8, AsyncPopulateMasqPrinterCache; lpStartAddress
0x18005c268  mov     r9, rbx; lpParameter
0x18005c26b  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x18005c273  xor     edx, edx; dwStackSize
0x18005c275  xor     ecx, ecx; lpThreadAttributes
0x18005c277  call    cs:__imp_CreateThread
0x18005c27d  mov     rbp, rax
0x18005c280  test    rax, rax
0x18005c283  jz      loc_18005C171
0x18005c289  mov     esi, r12d
0x18005c28c  xor     ebx, ebx
0x18005c28e  jmp     loc_18005C1A1
0x18005c293  mov     ecx, 88h
0x18005c298  call    cs:__imp_DllAllocSplMem
0x18005c29e  test    rax, rax
0x18005c2a1  jz      loc_18005C1E5
0x18005c2a7  mov     ecx, [rdi+194h]
0x18005c2ad  mov     esi, r12d
0x18005c2b0  mov     [rax+7Ch], ecx
0x18005c2b3  mov     ecx, [rdi+198h]
0x18005c2b9  mov     [rax+80h], ecx
0x18005c2bf  mov     [r14], rax
0x18005c2c2  jmp     loc_18005C1E7
```
