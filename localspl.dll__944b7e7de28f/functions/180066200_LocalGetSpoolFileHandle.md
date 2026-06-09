# LocalGetSpoolFileHandle

- ea: `0x180066200`
- end: `0x1800664f5`
- name: `LocalGetSpoolFileHandle`
- size: `757`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x180006830`
- `0x180008520`
- `0x180008560`
- `0x18000b9ec`
- `0x18000d0d8`
- `0x180011f00`
- `0x180013c90`
- `0x1800237b0`
- `0x180042ad0`
- `0x180044484`
- `0x180066200`
- `0x1800cd7b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066394`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066394`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800663a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800663a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066270`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006645b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066270`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006645b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18006632c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18006632c`
- `SPOOLSS!DllFreeSplMem` at `0x18006640f`
- `SPOOLSS!DllFreeSplMem` at `0x180066418`
- `SPOOLSS!DllFreeSplMem` at `0x1800664d2`
- `SPOOLSS!DllFreeSplMem` at `0x1800664e0`
- `SPOOLSS!DllFreeSplMem` at `0x18006640f`
- `SPOOLSS!DllFreeSplMem` at `0x180066418`
- `SPOOLSS!DllFreeSplMem` at `0x1800664d2`
- `SPOOLSS!DllFreeSplMem` at `0x1800664e0`
- `SPOOLSS!DllAllocSplMem` at `0x1800662d2`
- `SPOOLSS!DllAllocSplMem` at `0x1800662e9`
- `SPOOLSS!DllAllocSplMem` at `0x1800662d2`
- `SPOOLSS!DllAllocSplMem` at `0x1800662e9`
- `SPOOLSS!AllocSplStr` at `0x18006647c`
- `SPOOLSS!AllocSplStr` at `0x18006647c`

## pseudocode

```c
__int64 __fastcall LocalGetSpoolFileHandle(__int64 a1, __int64 *a2, HANDLE *a3, void *a4, HANDLE hTargetProcessHandle)
{
  unsigned __int16 *v9; // rbp
  DWORD v10; // ebx
  __int64 v12; // rax
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rsi
  __int64 v16; // rcx
  const unsigned __int16 *v17; // r8
  unsigned int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // ebx
  __int64 v21; // r14
  __int64 v22; // rcx
  __int64 *i; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rdx
  unsigned int v27; // eax
  __int64 bInheritHandle; // [rsp+28h] [rbp-50h]
  __int64 dwOptions; // [rsp+30h] [rbp-48h]
  __int64 v30; // [rsp+38h] [rbp-40h]
  __int64 v31; // [rsp+40h] [rbp-38h]

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = (HANDLE)-1LL;
  if ( a1 )
  {
    if ( a3 )
      goto LABEL_7;
LABEL_11:
    SetLastError(0x57u);
    return 0;
  }
  if ( !a2 )
    goto LABEL_11;
LABEL_7:
  v9 = 0;
  EnterSplSem(0);
  if ( !a1 )
  {
    v15 = 0;
    v19 = *((_QWORD *)pLocalIniSpooler + 12);
    if ( v19 )
    {
      v25 = AllocSplStr(v19);
      *a2 = v25;
      v20 = v25 != 0;
    }
    else
    {
      v26 = *((_QWORD *)pLocalIniSpooler + 4);
      v20 = 1;
      if ( v26 )
      {
        v27 = StrCatAlloc(a2, v26, L"\\", L"PRINTERS");
        v20 = BoolFromStatus(v27);
      }
    }
    goto LABEL_44;
  }
  if ( (unsigned int)ValidateSpoolHandle(a1, 16) )
  {
    if ( (*(_DWORD *)(a1 + 112) & 0x11) != 1 )
    {
      v10 = 3003;
      goto LABEL_39;
    }
    v12 = *(_QWORD *)(a1 + 80);
    if ( v12 )
    {
      if ( *(_QWORD *)(v12 + 184) != -1 && (*(_BYTE *)(a1 + 88) & 0xC) == 0 )
      {
        if ( (*(_BYTE *)(a1 + 112) & 4) != 0 && (*(_BYTE *)(v12 + 32) & 0x20) != 0 )
        {
          v10 = 63;
          v13 = LocalSpoolerTelemetry::Provider();
          SplTraceErrorPrintCancelled(v13, L"LocalGetSpoolFileHandle");
          goto LABEL_39;
        }
        v15 = DllAllocSplMem(24);
        if ( !v15
          || (v9 = (unsigned __int16 *)DllAllocSplMem(520)) == 0
          || !DuplicateHandle(a4, *(HANDLE *)(*(_QWORD *)(a1 + 80) + 184LL), hTargetProcessHandle, a3, 0, 1, 2u) )
        {
          v20 = 0;
          LeaveSplSem(v14);
          goto LABEL_45;
        }
        INIJOB::SetJobStatusFlags(*(INIJOB **)(a1 + 80), 0x8000000u);
        v16 = *(_QWORD *)(a1 + 80);
        if ( *(_QWORD *)(v16 + 392) == -1 || (v17 = *(const unsigned __int16 **)(v16 + 384)) == 0 )
        {
          v20 = 1;
          LODWORD(bInheritHandle) = 0;
          GetFullNameFromId(
            *(_QWORD *)(v16 + 88),
            *(_DWORD *)(v16 + 40),
            1,
            (__int64)v9,
            260,
            bInheritHandle,
            dwOptions,
            v30,
            v31);
        }
        else
        {
          v18 = StringCchCopyW(v9, 0x104u, v17);
          v20 = BoolFromHResult(v18);
          if ( !v20 )
            goto LABEL_44;
          v21 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 392LL);
          if ( v21 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(v21 + 24));
            *(_DWORD *)(v21 + 64) |= 0x40u;
            LeaveCriticalSection((LPCRITICAL_SECTION)(v21 + 24));
            v22 = 0;
          }
          else
          {
            v22 = 2147942487LL;
          }
          v20 = BoolFromHResult(v22);
          if ( !v20 )
            goto LABEL_44;
        }
        for ( i = *(__int64 **)(a1 + 272); i; i = (__int64 *)*i )
        {
          if ( *((_DWORD *)i + 4) == *(_DWORD *)(*(_QWORD *)(a1 + 80) + 40LL) )
          {
            *((_DWORD *)i + 5) |= 1u;
            DllFreeSplMem(v9);
            DllFreeSplMem(v15);
            goto LABEL_44;
          }
        }
        *(_QWORD *)(v15 + 8) = v9;
        v19 = *(unsigned int *)(*(_QWORD *)(a1 + 80) + 40LL);
        *(_DWORD *)(v15 + 16) = v19;
        *(_DWORD *)(v15 + 20) = 1;
        *(_QWORD *)v15 = *(_QWORD *)(a1 + 272);
        *(_QWORD *)(a1 + 272) = v15;
LABEL_44:
        LeaveSplSem(v19);
        if ( v20 )
          return v20;
LABEL_45:
        if ( v15 )
          DllFreeSplMem(v15);
        if ( v9 )
          DllFreeSplMem(v9);
        return v20;
      }
    }
  }
  v10 = 6;
LABEL_39:
  SetLastError(v10);
  v20 = 0;
  LeaveSplSem(v24);
  return v20;
}

```

## disassembly

```asm
0x180066200  push    rbx
0x180066202  push    rbp
0x180066203  push    rsi
0x180066204  push    rdi
0x180066205  push    r12
0x180066207  push    r14
0x180066209  sub     rsp, 48h
0x18006620d  mov     r12, r9
0x180066210  mov     rbx, r8
0x180066213  mov     r14, rdx
0x180066216  mov     rdi, rcx
0x180066219  test    rdx, rdx
0x18006621c  jz      short loc_180066225
0x18006621e  mov     qword ptr [rdx], 0
0x180066225  test    rbx, rbx
0x180066228  jz      short loc_180066231
0x18006622a  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x180066231  test    rdi, rdi
0x180066234  jz      short loc_180066266
0x180066236  test    rbx, rbx
0x180066239  jz      short loc_18006626B
0x18006623b  xor     ecx, ecx
0x18006623d  xor     ebp, ebp
0x18006623f  call    EnterSplSem
0x180066244  test    rdi, rdi
0x180066247  jz      loc_18006646A
0x18006624d  lea     edx, [rbp+10h]
0x180066250  mov     rcx, rdi
0x180066253  call    ValidateSpoolHandle
0x180066258  test    eax, eax
0x18006625a  jnz     short loc_18006627D
0x18006625c  mov     ebx, 6
0x180066261  jmp     loc_180066459
0x180066266  test    r14, r14
0x180066269  jnz     short loc_18006623B
0x18006626b  mov     ecx, 57h ; 'W'; dwErrCode
0x180066270  call    cs:__imp_SetLastError
0x180066276  xor     eax, eax
0x180066278  jmp     loc_1800664E8
0x18006627d  mov     eax, [rdi+70h]
0x180066280  and     al, 11h
0x180066282  cmp     al, 1
0x180066284  jnz     loc_180066454
0x18006628a  mov     rax, [rdi+50h]
0x18006628e  test    rax, rax
0x180066291  jz      short loc_18006625C
0x180066293  cmp     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFFFh
0x18006629b  jz      short loc_18006625C
0x18006629d  test    byte ptr [rdi+58h], 0Ch
0x1800662a1  jnz     short loc_18006625C
0x1800662a3  test    byte ptr [rdi+70h], 4
0x1800662a7  jz      short loc_1800662CD
0x1800662a9  test    byte ptr [rax+20h], 20h
0x1800662ad  jz      short loc_1800662CD
0x1800662af  mov     ebx, 3Fh ; '?'
0x1800662b4  call    ?Provider@LocalSpoolerTelemetry@@SAPEBU_tlgProvider_t@@XZ; LocalSpoolerTelemetry::Provider(void)
0x1800662b9  mov     rcx, rax; struct _tlgProvider_t *
0x1800662bc  lea     rdx, aLocalgetspoolf; "LocalGetSpoolFileHandle"
0x1800662c3  call    ?SplTraceErrorPrintCancelled@@YAXPEBU_tlgProvider_t@@PEBG@Z; SplTraceErrorPrintCancelled(_tlgProvider_t const *,ushort const *)
0x1800662c8  jmp     loc_180066459
0x1800662cd  mov     ecx, 18h
0x1800662d2  call    cs:__imp_DllAllocSplMem
0x1800662d8  mov     rsi, rax
0x1800662db  test    rax, rax
0x1800662de  jz      loc_18006644B
0x1800662e4  mov     ecx, 208h
0x1800662e9  call    cs:__imp_DllAllocSplMem
0x1800662ef  mov     rbp, rax
0x1800662f2  test    rax, rax
0x1800662f5  jz      loc_18006644B
0x1800662fb  mov     rdx, [rdi+50h]
0x1800662ff  mov     r9, rbx; lpTargetHandle
0x180066302  mov     r8, [rsp+78h+hTargetProcessHandle]; hTargetProcessHandle
0x18006630a  mov     rcx, r12; hSourceProcessHandle
0x18006630d  mov     dword ptr [rsp+78h+dwOptions], 2; dwOptions
0x180066315  mov     dword ptr [rsp+78h+bInheritHandle], 1; bInheritHandle
0x18006631d  mov     rdx, [rdx+0B8h]; hSourceHandle
0x180066324  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x18006632c  call    cs:__imp_DuplicateHandle
0x180066332  test    eax, eax
0x180066334  jz      loc_18006644B
0x18006633a  mov     rcx, [rdi+50h]; this
0x18006633e  mov     edx, 8000000h; unsigned int
0x180066343  call    ?SetJobStatusFlags@INIJOB@@QEAAXK@Z; INIJOB::SetJobStatusFlags(ulong)
0x180066348  mov     rcx, [rdi+50h]
0x18006634c  cmp     qword ptr [rcx+188h], 0FFFFFFFFFFFFFFFFh
0x180066354  jz      short loc_1800663C3
0x180066356  mov     r8, [rcx+180h]; unsigned __int16 *
0x18006635d  test    r8, r8
0x180066360  jz      short loc_1800663C3
0x180066362  mov     edx, 104h; unsigned __int64
0x180066367  mov     rcx, rbp; unsigned __int16 *
0x18006636a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006636f  mov     ecx, eax
0x180066371  call    BoolFromHResult
0x180066376  mov     ebx, eax
0x180066378  test    eax, eax
0x18006637a  jz      loc_1800664C1
0x180066380  mov     rax, [rdi+50h]
0x180066384  mov     r14, [rax+188h]
0x18006638b  test    r14, r14
0x18006638e  jz      short loc_1800663AD
0x180066390  lea     rcx, [r14+18h]; lpCriticalSection
0x180066394  call    cs:__imp_EnterCriticalSection
0x18006639a  or      dword ptr [r14+40h], 40h
0x18006639f  lea     rcx, [r14+18h]; lpCriticalSection
0x1800663a3  call    cs:__imp_LeaveCriticalSection
0x1800663a9  xor     ecx, ecx
0x1800663ab  jmp     short loc_1800663B2
0x1800663ad  mov     ecx, 80070057h
0x1800663b2  call    BoolFromHResult
0x1800663b7  mov     ebx, eax
0x1800663b9  test    eax, eax
0x1800663bb  jz      loc_1800664C1
0x1800663c1  jmp     short loc_1800663EB
0x1800663c3  mov     edx, [rcx+28h]
0x1800663c6  mov     ebx, 1
0x1800663cb  mov     rcx, [rcx+58h]
0x1800663cf  mov     r8d, ebx
0x1800663d2  mov     dword ptr [rsp+78h+bInheritHandle], 0
0x1800663da  mov     r9, rbp
0x1800663dd  mov     qword ptr [rsp+78h+dwDesiredAccess], 104h
0x1800663e6  call    GetFullNameFromId
0x1800663eb  mov     rdx, [rdi+110h]
0x1800663f2  test    rdx, rdx
0x1800663f5  jz      short loc_180066423
0x1800663f7  mov     rax, [rdi+50h]
0x1800663fb  mov     ecx, [rax+28h]
0x1800663fe  cmp     [rdx+10h], ecx
0x180066401  jz      short loc_180066408
0x180066403  mov     rdx, [rdx]
0x180066406  jmp     short loc_1800663F2
0x180066408  or      dword ptr [rdx+14h], 1
0x18006640c  mov     rcx, rbp
0x18006640f  call    cs:__imp_DllFreeSplMem
0x180066415  mov     rcx, rsi
0x180066418  call    cs:__imp_DllFreeSplMem
0x18006641e  jmp     loc_1800664C1
0x180066423  mov     [rsi+8], rbp
0x180066427  mov     rax, [rdi+50h]
0x18006642b  mov     ecx, [rax+28h]
0x18006642e  mov     [rsi+10h], ecx
0x180066431  mov     dword ptr [rsi+14h], 1
0x180066438  mov     rax, [rdi+110h]
0x18006643f  mov     [rsi], rax
0x180066442  mov     [rdi+110h], rsi
0x180066449  jmp     short loc_1800664C1
0x18006644b  xor     ebx, ebx
0x18006644d  call    LeaveSplSem
0x180066452  jmp     short loc_1800664CA
0x180066454  mov     ebx, 0BBBh
0x180066459  mov     ecx, ebx; dwErrCode
0x18006645b  call    cs:__imp_SetLastError
0x180066461  xor     ebx, ebx
0x180066463  call    LeaveSplSem
0x180066468  jmp     short loc_1800664E6
0x18006646a  mov     rax, cs:pLocalIniSpooler
0x180066471  xor     esi, esi
0x180066473  mov     rcx, [rax+60h]
0x180066477  test    rcx, rcx
0x18006647a  jz      short loc_18006648F
0x18006647c  call    cs:__imp_AllocSplStr
0x180066482  xor     ebx, ebx
0x180066484  mov     [r14], rax
0x180066487  test    rax, rax
0x18006648a  setnz   bl
0x18006648d  jmp     short loc_1800664C1
0x18006648f  mov     rdx, [rax+20h]
0x180066493  mov     ebx, 1
0x180066498  test    rdx, rdx
0x18006649b  jz      short loc_1800664C1
0x18006649d  lea     r9, szPrinterDir; "PRINTERS"
0x1800664a4  mov     qword ptr [rsp+78h+dwDesiredAccess], rsi
0x1800664a9  lea     r8, SubBlock; "\\"
0x1800664b0  mov     rcx, r14
0x1800664b3  call    StrCatAlloc
0x1800664b8  mov     ecx, eax
0x1800664ba  call    BoolFromStatus
0x1800664bf  mov     ebx, eax
0x1800664c1  call    LeaveSplSem
0x1800664c6  test    ebx, ebx
0x1800664c8  jnz     short loc_1800664E6
0x1800664ca  test    rsi, rsi
0x1800664cd  jz      short loc_1800664D8
0x1800664cf  mov     rcx, rsi
0x1800664d2  call    cs:__imp_DllFreeSplMem
0x1800664d8  test    rbp, rbp
0x1800664db  jz      short loc_1800664E6
0x1800664dd  mov     rcx, rbp
0x1800664e0  call    cs:__imp_DllFreeSplMem
0x1800664e6  mov     eax, ebx
0x1800664e8  add     rsp, 48h
0x1800664ec  pop     r14
0x1800664ee  pop     r12
0x1800664f0  pop     rdi
0x1800664f1  pop     rsi
0x1800664f2  pop     rbp
0x1800664f3  pop     rbx
0x1800664f4  retn
```
