# LoadClusterResourceLibraries(CLUSTER_API *)

- ea: `0x180153310`
- end: `0x18015366f`
- name: `?LoadClusterResourceLibraries@@YAKPEAUCLUSTER_API@@@Z`
- size: `863`
- prototype: `unsigned int __fastcall(struct CLUSTER_API *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180156f90`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180153310`
- `0x180157620`
- `0x18015a6f0`
- `0x18015a880`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180153584`
- `KERNEL32!FreeLibrary` at `0x180153596`
- `KERNEL32!FreeLibrary` at `0x1801535a8`
- `KERNEL32!FreeLibrary` at `0x180153584`
- `KERNEL32!FreeLibrary` at `0x180153596`
- `KERNEL32!FreeLibrary` at `0x1801535a8`
- `KERNEL32!GetLastError` at `0x180153572`
- `KERNEL32!GetLastError` at `0x180153572`
- `KERNEL32!GetProcAddress` at `0x180153393`
- `KERNEL32!GetProcAddress` at `0x1801533b0`
- `KERNEL32!GetProcAddress` at `0x1801533cd`
- `KERNEL32!GetProcAddress` at `0x1801533ea`
- `KERNEL32!GetProcAddress` at `0x180153407`
- `KERNEL32!GetProcAddress` at `0x180153424`
- `KERNEL32!GetProcAddress` at `0x180153441`
- `KERNEL32!GetProcAddress` at `0x18015345e`
- `KERNEL32!GetProcAddress` at `0x18015347b`
- `KERNEL32!GetProcAddress` at `0x180153498`
- `KERNEL32!GetProcAddress` at `0x1801534b5`
- `KERNEL32!GetProcAddress` at `0x1801534d2`
- `KERNEL32!GetProcAddress` at `0x180153506`
- `KERNEL32!GetProcAddress` at `0x18015351f`
- `KERNEL32!GetProcAddress` at `0x180153393`
- `KERNEL32!GetProcAddress` at `0x1801533b0`
- `KERNEL32!GetProcAddress` at `0x1801533cd`
- `KERNEL32!GetProcAddress` at `0x1801533ea`
- `KERNEL32!GetProcAddress` at `0x180153407`
- `KERNEL32!GetProcAddress` at `0x180153424`
- `KERNEL32!GetProcAddress` at `0x180153441`
- `KERNEL32!GetProcAddress` at `0x18015345e`
- `KERNEL32!GetProcAddress` at `0x18015347b`
- `KERNEL32!GetProcAddress` at `0x180153498`
- `KERNEL32!GetProcAddress` at `0x1801534b5`
- `KERNEL32!GetProcAddress` at `0x1801534d2`
- `KERNEL32!GetProcAddress` at `0x180153506`
- `KERNEL32!GetProcAddress` at `0x18015351f`

## string_xrefs

- `0x180153371`: `CLUSAPI.DLL`
- `0x180153389`: `OpenCluster`
- `0x1801533c3`: `OpenClusterResource`
- `0x1801533fd`: `ClusterOpenEnum`
- `0x180153454`: `ClusterResourceOpenEnum`
- `0x1801534e8`: `RESUTILS.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LoadClusterResourceLibraries(struct CLUSTER_API *a1, __int64 a2, __int64 a3, __int64 a4)
{
  HMODULE v5; // rax
  HMODULE v6; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  FARPROC v17; // rax
  FARPROC v18; // rax
  HMODULE v19; // rax
  FARPROC v20; // rax
  FARPROC v21; // rax
  DWORD v22; // esi
  DWORD LastError; // ebp
  HMODULE v24; // rcx
  __int64 v26; // [rsp+30h] [rbp-18h] BYREF

  v26 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266708[0] )
    bidScopeEnterW(&v26, off_180266708[0], a1, a4);
  v5 = (HMODULE)SNILoadSystemLibA("CLUSAPI.DLL");
  v6 = v5;
  if ( !v5 )
    goto LABEL_24;
  ProcAddress = GetProcAddress(v5, "OpenCluster");
  *((_QWORD *)a1 + 1) = ProcAddress;
  if ( !ProcAddress )
    goto LABEL_24;
  v8 = GetProcAddress(v6, "CloseCluster");
  *((_QWORD *)a1 + 2) = v8;
  if ( !v8 )
    goto LABEL_24;
  v9 = GetProcAddress(v6, "OpenClusterResource");
  *((_QWORD *)a1 + 3) = v9;
  if ( !v9 )
    goto LABEL_24;
  v10 = GetProcAddress(v6, "CloseClusterResource");
  *((_QWORD *)a1 + 4) = v10;
  if ( !v10 )
    goto LABEL_24;
  v11 = GetProcAddress(v6, "ClusterOpenEnum");
  *((_QWORD *)a1 + 5) = v11;
  if ( !v11 )
    goto LABEL_24;
  v12 = GetProcAddress(v6, "ClusterEnum");
  *((_QWORD *)a1 + 6) = v12;
  if ( !v12 )
    goto LABEL_24;
  v13 = GetProcAddress(v6, "ClusterCloseEnum");
  *((_QWORD *)a1 + 7) = v13;
  if ( !v13 )
    goto LABEL_24;
  v14 = GetProcAddress(v6, "ClusterResourceOpenEnum");
  *((_QWORD *)a1 + 8) = v14;
  if ( !v14 )
    goto LABEL_24;
  v15 = GetProcAddress(v6, "ClusterResourceEnum");
  *((_QWORD *)a1 + 9) = v15;
  if ( !v15 )
    goto LABEL_24;
  v16 = GetProcAddress(v6, "ClusterResourceCloseEnum");
  *((_QWORD *)a1 + 10) = v16;
  if ( !v16 )
    goto LABEL_24;
  v17 = GetProcAddress(v6, "ClusterResourceControl");
  *((_QWORD *)a1 + 11) = v17;
  if ( !v17 )
    goto LABEL_24;
  v18 = GetProcAddress(v6, "GetClusterResourceState");
  *((_QWORD *)a1 + 12) = v18;
  if ( !v18 )
    goto LABEL_24;
  *(_QWORD *)a1 = v6;
  v19 = (HMODULE)SNILoadSystemLibA("RESUTILS.DLL");
  v6 = v19;
  if ( v19
    && (v20 = GetProcAddress(v19, "ResUtilFindSzProperty"), (*((_QWORD *)a1 + 14) = v20) != 0)
    && (v21 = GetProcAddress(v6, "ResUtilResourceTypesEqual"), (*((_QWORD *)a1 + 15) = v21) != 0) )
  {
    *((_QWORD *)a1 + 13) = v6;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180263BF0[0] )
      bidTraceW(off_1802608A8[0], 236544, off_180263BF0[0], 0);
    v22 = 0;
  }
  else
  {
LABEL_24:
    LastError = GetLastError();
    if ( *(_QWORD *)a1 )
    {
      FreeLibrary(*(HMODULE *)a1);
      *(_QWORD *)a1 = 0;
    }
    v24 = (HMODULE)*((_QWORD *)a1 + 13);
    if ( v24 )
    {
      FreeLibrary(v24);
      *((_QWORD *)a1 + 13) = 0;
    }
    if ( v6 )
      FreeLibrary(v6);
    if ( (bidGblFlags & 2) != 0 && off_180263BF8[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(off_1802608B0[0], 0x40000, off_180263BF8[0], 6);
    }
    SNISetLastError(6, LastError, 50100);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180263C00[0] )
      bidTraceW(off_1802608B8[0], 264192, off_180263C00[0], LastError);
    v22 = LastError;
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v26);
  return v22;
}

```

## disassembly

```asm
0x180153310  mov     [rsp+arg_8], rbx
0x180153315  mov     [rsp+arg_10], rbp
0x18015331a  mov     [rsp+arg_18], rsi
0x18015331f  push    rdi
0x180153320  sub     rsp, 40h
0x180153324  mov     rax, cs:__security_cookie
0x18015332b  xor     rax, rsp
0x18015332e  mov     [rsp+48h+var_10], rax
0x180153333  mov     rdi, rcx
0x180153336  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFFh
0x18015333f  mov     eax, cs:_bidGblFlags
0x180153345  and     eax, 20004h
0x18015334a  cmp     eax, 20004h
0x18015334f  jnz     short loc_180153371
0x180153351  mov     rax, cs:off_180266708; "<LoadClusterResourceLibraries|API|SNI> "...
0x180153358  test    rax, rax
0x18015335b  jz      short loc_180153371
0x18015335d  mov     r8, rcx
0x180153360  mov     rdx, cs:off_180266708; "<LoadClusterResourceLibraries|API|SNI> "...
0x180153367  lea     rcx, [rsp+48h+var_18]
0x18015336c  call    _bidScopeEnterW
0x180153371  lea     rcx, aClusapiDll; "CLUSAPI.DLL"
0x180153378  call    SNILoadSystemLibA
0x18015337d  mov     rbx, rax
0x180153380  test    rax, rax
0x180153383  jz      loc_180153572
0x180153389  lea     rdx, aOpencluster; "OpenCluster"
0x180153390  mov     rcx, rax; hModule
0x180153393  call    cs:__imp_GetProcAddress
0x180153399  mov     [rdi+8], rax
0x18015339d  test    rax, rax
0x1801533a0  jz      loc_180153572
0x1801533a6  lea     rdx, aClosecluster; "CloseCluster"
0x1801533ad  mov     rcx, rbx; hModule
0x1801533b0  call    cs:__imp_GetProcAddress
0x1801533b6  mov     [rdi+10h], rax
0x1801533ba  test    rax, rax
0x1801533bd  jz      loc_180153572
0x1801533c3  lea     rdx, aOpenclusterres; "OpenClusterResource"
0x1801533ca  mov     rcx, rbx; hModule
0x1801533cd  call    cs:__imp_GetProcAddress
0x1801533d3  mov     [rdi+18h], rax
0x1801533d7  test    rax, rax
0x1801533da  jz      loc_180153572
0x1801533e0  lea     rdx, aCloseclusterre; "CloseClusterResource"
0x1801533e7  mov     rcx, rbx; hModule
0x1801533ea  call    cs:__imp_GetProcAddress
0x1801533f0  mov     [rdi+20h], rax
0x1801533f4  test    rax, rax
0x1801533f7  jz      loc_180153572
0x1801533fd  lea     rdx, aClusteropenenu; "ClusterOpenEnum"
0x180153404  mov     rcx, rbx; hModule
0x180153407  call    cs:__imp_GetProcAddress
0x18015340d  mov     [rdi+28h], rax
0x180153411  test    rax, rax
0x180153414  jz      loc_180153572
0x18015341a  lea     rdx, aClusterenum; "ClusterEnum"
0x180153421  mov     rcx, rbx; hModule
0x180153424  call    cs:__imp_GetProcAddress
0x18015342a  mov     [rdi+30h], rax
0x18015342e  test    rax, rax
0x180153431  jz      loc_180153572
0x180153437  lea     rdx, aClustercloseen; "ClusterCloseEnum"
0x18015343e  mov     rcx, rbx; hModule
0x180153441  call    cs:__imp_GetProcAddress
0x180153447  mov     [rdi+38h], rax
0x18015344b  test    rax, rax
0x18015344e  jz      loc_180153572
0x180153454  lea     rdx, aClusterresourc_1; "ClusterResourceOpenEnum"
0x18015345b  mov     rcx, rbx; hModule
0x18015345e  call    cs:__imp_GetProcAddress
0x180153464  mov     [rdi+40h], rax
0x180153468  test    rax, rax
0x18015346b  jz      loc_180153572
0x180153471  lea     rdx, aClusterresourc; "ClusterResourceEnum"
0x180153478  mov     rcx, rbx; hModule
0x18015347b  call    cs:__imp_GetProcAddress
0x180153481  mov     [rdi+48h], rax
0x180153485  test    rax, rax
0x180153488  jz      loc_180153572
0x18015348e  lea     rdx, aClusterresourc_0; "ClusterResourceCloseEnum"
0x180153495  mov     rcx, rbx; hModule
0x180153498  call    cs:__imp_GetProcAddress
0x18015349e  mov     [rdi+50h], rax
0x1801534a2  test    rax, rax
0x1801534a5  jz      loc_180153572
0x1801534ab  lea     rdx, aClusterresourc_2; "ClusterResourceControl"
0x1801534b2  mov     rcx, rbx; hModule
0x1801534b5  call    cs:__imp_GetProcAddress
0x1801534bb  mov     [rdi+58h], rax
0x1801534bf  test    rax, rax
0x1801534c2  jz      loc_180153572
0x1801534c8  lea     rdx, aGetclusterreso; "GetClusterResourceState"
0x1801534cf  mov     rcx, rbx; hModule
0x1801534d2  call    cs:__imp_GetProcAddress
0x1801534d8  mov     [rdi+60h], rax
0x1801534dc  test    rax, rax
0x1801534df  jz      loc_180153572
0x1801534e5  mov     [rdi], rbx
0x1801534e8  lea     rcx, aResutilsDll; "RESUTILS.DLL"
0x1801534ef  call    SNILoadSystemLibA
0x1801534f4  mov     rbx, rax
0x1801534f7  test    rax, rax
0x1801534fa  jz      short loc_180153572
0x1801534fc  lea     rdx, aResutilfindszp; "ResUtilFindSzProperty"
0x180153503  mov     rcx, rax; hModule
0x180153506  call    cs:__imp_GetProcAddress
0x18015350c  mov     [rdi+70h], rax
0x180153510  test    rax, rax
0x180153513  jz      short loc_180153572
0x180153515  lea     rdx, aResutilresourc; "ResUtilResourceTypesEqual"
0x18015351c  mov     rcx, rbx; hModule
0x18015351f  call    cs:__imp_GetProcAddress
0x180153525  mov     [rdi+78h], rax
0x180153529  test    rax, rax
0x18015352c  jz      short loc_180153572
0x18015352e  mov     [rdi+68h], rbx
0x180153532  mov     eax, cs:_bidGblFlags
0x180153538  and     eax, 20002h
0x18015353d  cmp     eax, 20002h
0x180153542  jnz     short loc_18015356B
0x180153544  mov     rax, cs:off_180263BF0; "<LoadClusterResourceLibraries|RET|SNI> "...
0x18015354b  test    rax, rax
0x18015354e  jz      short loc_18015356B
0x180153550  xor     r9d, r9d
0x180153553  mov     r8, cs:off_180263BF0; "<LoadClusterResourceLibraries|RET|SNI> "...
0x18015355a  mov     edx, 39C00h
0x18015355f  mov     rcx, cs:off_1802608A8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180153566  call    _bidTraceW
0x18015356b  xor     esi, esi
0x18015356d  jmp     loc_180153640
0x180153572  call    cs:__imp_GetLastError
0x180153578  mov     ebp, eax
0x18015357a  mov     rcx, [rdi]; hLibModule
0x18015357d  xor     esi, esi
0x18015357f  test    rcx, rcx
0x180153582  jz      short loc_18015358D
0x180153584  call    cs:__imp_FreeLibrary
0x18015358a  mov     [rdi], rsi
0x18015358d  mov     rcx, [rdi+68h]; hLibModule
0x180153591  test    rcx, rcx
0x180153594  jz      short loc_1801535A0
0x180153596  call    cs:__imp_FreeLibrary
0x18015359c  mov     [rdi+68h], rsi
0x1801535a0  test    rbx, rbx
0x1801535a3  jz      short loc_1801535AE
0x1801535a5  mov     rcx, rbx; hLibModule
0x1801535a8  call    cs:__imp_FreeLibrary
0x1801535ae  test    byte ptr cs:_bidGblFlags, 2
0x1801535b5  jz      short loc_1801535F3
0x1801535b7  mov     rax, cs:off_180263BF8; "<LoadClusterResourceLibraries|ERR|SNI> "...
0x1801535be  test    rax, rax
0x1801535c1  jz      short loc_1801535F3
0x1801535c3  mov     ecx, 0C3B4h; unsigned int
0x1801535c8  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1801535cd  mov     [rsp+48h+var_20], ebp
0x1801535d1  mov     [rsp+48h+var_28], eax
0x1801535d5  mov     r9d, 6
0x1801535db  mov     r8, cs:off_180263BF8; "<LoadClusterResourceLibraries|ERR|SNI> "...
0x1801535e2  mov     edx, 40000h
0x1801535e7  mov     rcx, cs:off_1802608B0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801535ee  call    _bidTraceW
0x1801535f3  mov     r8d, 0C3B4h
0x1801535f9  mov     edx, ebp
0x1801535fb  mov     ecx, 6
0x180153600  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x180153605  mov     eax, cs:_bidGblFlags
0x18015360b  and     eax, 20002h
0x180153610  cmp     eax, 20002h
0x180153615  jnz     short loc_18015363E
0x180153617  mov     rax, cs:off_180263C00; "<LoadClusterResourceLibraries|RET|SNI> "...
0x18015361e  test    rax, rax
0x180153621  jz      short loc_18015363E
0x180153623  mov     r9d, ebp
0x180153626  mov     r8, cs:off_180263C00; "<LoadClusterResourceLibraries|RET|SNI> "...
0x18015362d  mov     edx, 40800h
0x180153632  mov     rcx, cs:off_1802608B8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180153639  call    _bidTraceW
0x18015363e  mov     esi, ebp
0x180153640  lea     rcx, [rsp+48h+var_18]; this
0x180153645  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18015364a  nop
0x18015364b  mov     eax, esi
0x18015364d  mov     rcx, [rsp+48h+var_10]
0x180153652  xor     rcx, rsp; StackCookie
0x180153655  call    __security_check_cookie
0x18015365a  mov     rbx, [rsp+48h+arg_8]
0x18015365f  mov     rbp, [rsp+48h+arg_10]
0x180153664  mov     rsi, [rsp+48h+arg_18]
0x180153669  add     rsp, 40h
0x18015366d  pop     rdi
0x18015366e  retn
```
