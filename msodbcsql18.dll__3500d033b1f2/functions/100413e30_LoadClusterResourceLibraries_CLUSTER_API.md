# LoadClusterResourceLibraries(CLUSTER_API *)

- ea: `0x100413e30`
- end: `0x100414167`
- name: `?LoadClusterResourceLibraries@@YAKPEAUCLUSTER_API@@@Z`
- size: `823`
- prototype: `unsigned int __fastcall(struct CLUSTER_API *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x100414170`

## callees

- `0x100413e30`
- `0x100417768`
- `0x10043a7c4`
- `0x10043a930`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100414087`
- `KERNEL32!GetLastError` at `0x100414087`
- `KERNEL32!GetProcAddress` at `0x100413ea8`
- `KERNEL32!GetProcAddress` at `0x100413ec5`
- `KERNEL32!GetProcAddress` at `0x100413ee2`
- `KERNEL32!GetProcAddress` at `0x100413eff`
- `KERNEL32!GetProcAddress` at `0x100413f1c`
- `KERNEL32!GetProcAddress` at `0x100413f39`
- `KERNEL32!GetProcAddress` at `0x100413f56`
- `KERNEL32!GetProcAddress` at `0x100413f73`
- `KERNEL32!GetProcAddress` at `0x100413f90`
- `KERNEL32!GetProcAddress` at `0x100413fad`
- `KERNEL32!GetProcAddress` at `0x100413fca`
- `KERNEL32!GetProcAddress` at `0x100413fe7`
- `KERNEL32!GetProcAddress` at `0x10041401b`
- `KERNEL32!GetProcAddress` at `0x100414034`
- `KERNEL32!GetProcAddress` at `0x100413ea8`
- `KERNEL32!GetProcAddress` at `0x100413ec5`
- `KERNEL32!GetProcAddress` at `0x100413ee2`
- `KERNEL32!GetProcAddress` at `0x100413eff`
- `KERNEL32!GetProcAddress` at `0x100413f1c`
- `KERNEL32!GetProcAddress` at `0x100413f39`
- `KERNEL32!GetProcAddress` at `0x100413f56`
- `KERNEL32!GetProcAddress` at `0x100413f73`
- `KERNEL32!GetProcAddress` at `0x100413f90`
- `KERNEL32!GetProcAddress` at `0x100413fad`
- `KERNEL32!GetProcAddress` at `0x100413fca`
- `KERNEL32!GetProcAddress` at `0x100413fe7`
- `KERNEL32!GetProcAddress` at `0x10041401b`
- `KERNEL32!GetProcAddress` at `0x100414034`
- `KERNEL32!FreeLibrary` at `0x100414097`
- `KERNEL32!FreeLibrary` at `0x1004140a9`
- `KERNEL32!FreeLibrary` at `0x1004140bb`
- `KERNEL32!FreeLibrary` at `0x100414097`
- `KERNEL32!FreeLibrary` at `0x1004140a9`
- `KERNEL32!FreeLibrary` at `0x1004140bb`

## string_xrefs

- `0x100413e86`: `CLUSAPI.DLL`
- `0x100413e9e`: `OpenCluster`
- `0x100413ed8`: `OpenClusterResource`
- `0x100413f12`: `ClusterOpenEnum`
- `0x100413f69`: `ClusterResourceOpenEnum`
- `0x100413ffd`: `RESUTILS.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LoadClusterResourceLibraries(struct CLUSTER_API *a1)
{
  DWORD v2; // ebx
  HMODULE v3; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  HMODULE v17; // rax
  FARPROC v18; // rax
  FARPROC v19; // rax
  DWORD LastError; // ebp
  HMODULE v21; // rcx
  __int64 v23; // [rsp+58h] [rbp+10h] BYREF

  v23 = -1;
  v2 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7710[0] )
    bidScopeEnterW(&v23, off_1005E7710[0], a1);
  v3 = (HMODULE)SNILoadSystemLibA("CLUSAPI.DLL");
  v4 = v3;
  if ( !v3 )
    goto LABEL_23;
  ProcAddress = GetProcAddress(v3, "OpenCluster");
  *((_QWORD *)a1 + 1) = ProcAddress;
  if ( !ProcAddress )
    goto LABEL_23;
  v6 = GetProcAddress(v4, "CloseCluster");
  *((_QWORD *)a1 + 2) = v6;
  if ( !v6 )
    goto LABEL_23;
  v7 = GetProcAddress(v4, "OpenClusterResource");
  *((_QWORD *)a1 + 3) = v7;
  if ( !v7 )
    goto LABEL_23;
  v8 = GetProcAddress(v4, "CloseClusterResource");
  *((_QWORD *)a1 + 4) = v8;
  if ( !v8 )
    goto LABEL_23;
  v9 = GetProcAddress(v4, "ClusterOpenEnum");
  *((_QWORD *)a1 + 5) = v9;
  if ( !v9 )
    goto LABEL_23;
  v10 = GetProcAddress(v4, "ClusterEnum");
  *((_QWORD *)a1 + 6) = v10;
  if ( !v10 )
    goto LABEL_23;
  v11 = GetProcAddress(v4, "ClusterCloseEnum");
  *((_QWORD *)a1 + 7) = v11;
  if ( !v11 )
    goto LABEL_23;
  v12 = GetProcAddress(v4, "ClusterResourceOpenEnum");
  *((_QWORD *)a1 + 8) = v12;
  if ( !v12 )
    goto LABEL_23;
  v13 = GetProcAddress(v4, "ClusterResourceEnum");
  *((_QWORD *)a1 + 9) = v13;
  if ( !v13 )
    goto LABEL_23;
  v14 = GetProcAddress(v4, "ClusterResourceCloseEnum");
  *((_QWORD *)a1 + 10) = v14;
  if ( !v14 )
    goto LABEL_23;
  v15 = GetProcAddress(v4, "ClusterResourceControl");
  *((_QWORD *)a1 + 11) = v15;
  if ( !v15 )
    goto LABEL_23;
  v16 = GetProcAddress(v4, "GetClusterResourceState");
  *((_QWORD *)a1 + 12) = v16;
  if ( !v16 )
    goto LABEL_23;
  *(_QWORD *)a1 = v4;
  v17 = (HMODULE)SNILoadSystemLibA("RESUTILS.DLL");
  v4 = v17;
  if ( v17
    && (v18 = GetProcAddress(v17, "ResUtilFindSzProperty"), (*((_QWORD *)a1 + 14) = v18) != 0)
    && (v19 = GetProcAddress(v4, "ResUtilResourceTypesEqual"), (*((_QWORD *)a1 + 15) = v19) != 0) )
  {
    *((_QWORD *)a1 + 13) = v4;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E44C8[0] )
      bidTraceW(0, 251904, off_1005E44C8[0], 0);
  }
  else
  {
LABEL_23:
    LastError = GetLastError();
    if ( *(_QWORD *)a1 )
    {
      FreeLibrary(*(HMODULE *)a1);
      *(_QWORD *)a1 = 0;
    }
    v21 = (HMODULE)*((_QWORD *)a1 + 13);
    if ( v21 )
    {
      FreeLibrary(v21);
      *((_QWORD *)a1 + 13) = 0;
    }
    if ( v4 )
      FreeLibrary(v4);
    if ( (bidGblFlags & 2) != 0 && off_1005E44D0[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 277504, off_1005E44D0[0], 7);
    }
    SNISetLastError(7, LastError, 50100);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E44D8[0] )
      bidTraceW(0, 279552, off_1005E44D8[0], LastError);
    v2 = LastError;
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v23);
  return v2;
}

```

## disassembly

```asm
0x100413e30  mov     r11, rsp
0x100413e33  push    rdi
0x100413e34  sub     rsp, 40h
0x100413e38  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x100413e40  mov     [r11+8], rbx
0x100413e44  mov     [r11+18h], rbp
0x100413e48  mov     [r11+20h], rsi
0x100413e4c  mov     rsi, rcx
0x100413e4f  or      qword ptr [r11+10h], 0FFFFFFFFFFFFFFFFh
0x100413e54  mov     eax, cs:_bidGblFlags
0x100413e5a  mov     ecx, 20004h
0x100413e5f  and     eax, ecx
0x100413e61  xor     ebx, ebx
0x100413e63  cmp     eax, ecx
0x100413e65  jnz     short loc_100413E86
0x100413e67  mov     rax, cs:off_1005E7710; "<LoadClusterResourceLibraries|API|SNI> "...
0x100413e6e  test    rax, rax
0x100413e71  jz      short loc_100413E86
0x100413e73  mov     r8, rsi
0x100413e76  mov     rdx, cs:off_1005E7710; "<LoadClusterResourceLibraries|API|SNI> "...
0x100413e7d  lea     rcx, [r11+10h]
0x100413e81  call    _bidScopeEnterW
0x100413e86  lea     rcx, aClusapiDll; "CLUSAPI.DLL"
0x100413e8d  call    SNILoadSystemLibA
0x100413e92  mov     rdi, rax
0x100413e95  test    rax, rax
0x100413e98  jz      loc_100414087
0x100413e9e  lea     rdx, aOpencluster; "OpenCluster"
0x100413ea5  mov     rcx, rax; hModule
0x100413ea8  call    cs:__imp_GetProcAddress
0x100413eae  mov     [rsi+8], rax
0x100413eb2  test    rax, rax
0x100413eb5  jz      loc_100414087
0x100413ebb  lea     rdx, aClosecluster; "CloseCluster"
0x100413ec2  mov     rcx, rdi; hModule
0x100413ec5  call    cs:__imp_GetProcAddress
0x100413ecb  mov     [rsi+10h], rax
0x100413ecf  test    rax, rax
0x100413ed2  jz      loc_100414087
0x100413ed8  lea     rdx, aOpenclusterres; "OpenClusterResource"
0x100413edf  mov     rcx, rdi; hModule
0x100413ee2  call    cs:__imp_GetProcAddress
0x100413ee8  mov     [rsi+18h], rax
0x100413eec  test    rax, rax
0x100413eef  jz      loc_100414087
0x100413ef5  lea     rdx, aCloseclusterre; "CloseClusterResource"
0x100413efc  mov     rcx, rdi; hModule
0x100413eff  call    cs:__imp_GetProcAddress
0x100413f05  mov     [rsi+20h], rax
0x100413f09  test    rax, rax
0x100413f0c  jz      loc_100414087
0x100413f12  lea     rdx, aClusteropenenu; "ClusterOpenEnum"
0x100413f19  mov     rcx, rdi; hModule
0x100413f1c  call    cs:__imp_GetProcAddress
0x100413f22  mov     [rsi+28h], rax
0x100413f26  test    rax, rax
0x100413f29  jz      loc_100414087
0x100413f2f  lea     rdx, aClusterenum; "ClusterEnum"
0x100413f36  mov     rcx, rdi; hModule
0x100413f39  call    cs:__imp_GetProcAddress
0x100413f3f  mov     [rsi+30h], rax
0x100413f43  test    rax, rax
0x100413f46  jz      loc_100414087
0x100413f4c  lea     rdx, aClustercloseen; "ClusterCloseEnum"
0x100413f53  mov     rcx, rdi; hModule
0x100413f56  call    cs:__imp_GetProcAddress
0x100413f5c  mov     [rsi+38h], rax
0x100413f60  test    rax, rax
0x100413f63  jz      loc_100414087
0x100413f69  lea     rdx, aClusterresourc_1; "ClusterResourceOpenEnum"
0x100413f70  mov     rcx, rdi; hModule
0x100413f73  call    cs:__imp_GetProcAddress
0x100413f79  mov     [rsi+40h], rax
0x100413f7d  test    rax, rax
0x100413f80  jz      loc_100414087
0x100413f86  lea     rdx, aClusterresourc; "ClusterResourceEnum"
0x100413f8d  mov     rcx, rdi; hModule
0x100413f90  call    cs:__imp_GetProcAddress
0x100413f96  mov     [rsi+48h], rax
0x100413f9a  test    rax, rax
0x100413f9d  jz      loc_100414087
0x100413fa3  lea     rdx, aClusterresourc_0; "ClusterResourceCloseEnum"
0x100413faa  mov     rcx, rdi; hModule
0x100413fad  call    cs:__imp_GetProcAddress
0x100413fb3  mov     [rsi+50h], rax
0x100413fb7  test    rax, rax
0x100413fba  jz      loc_100414087
0x100413fc0  lea     rdx, aClusterresourc_2; "ClusterResourceControl"
0x100413fc7  mov     rcx, rdi; hModule
0x100413fca  call    cs:__imp_GetProcAddress
0x100413fd0  mov     [rsi+58h], rax
0x100413fd4  test    rax, rax
0x100413fd7  jz      loc_100414087
0x100413fdd  lea     rdx, aGetclusterreso; "GetClusterResourceState"
0x100413fe4  mov     rcx, rdi; hModule
0x100413fe7  call    cs:__imp_GetProcAddress
0x100413fed  mov     [rsi+60h], rax
0x100413ff1  test    rax, rax
0x100413ff4  jz      loc_100414087
0x100413ffa  mov     [rsi], rdi
0x100413ffd  lea     rcx, aResutilsDll; "RESUTILS.DLL"
0x100414004  call    SNILoadSystemLibA
0x100414009  mov     rdi, rax
0x10041400c  test    rax, rax
0x10041400f  jz      short loc_100414087
0x100414011  lea     rdx, aResutilfindszp; "ResUtilFindSzProperty"
0x100414018  mov     rcx, rax; hModule
0x10041401b  call    cs:__imp_GetProcAddress
0x100414021  mov     [rsi+70h], rax
0x100414025  test    rax, rax
0x100414028  jz      short loc_100414087
0x10041402a  lea     rdx, aResutilresourc; "ResUtilResourceTypesEqual"
0x100414031  mov     rcx, rdi; hModule
0x100414034  call    cs:__imp_GetProcAddress
0x10041403a  mov     [rsi+78h], rax
0x10041403e  test    rax, rax
0x100414041  jz      short loc_100414087
0x100414043  mov     [rsi+68h], rdi
0x100414047  mov     eax, cs:_bidGblFlags
0x10041404d  mov     ecx, 20002h
0x100414052  and     eax, ecx
0x100414054  cmp     eax, ecx
0x100414056  jnz     loc_100414146
0x10041405c  mov     rax, cs:off_1005E44C8; "<LoadClusterResourceLibraries|RET|SNI> "...
0x100414063  test    rax, rax
0x100414066  jz      loc_100414146
0x10041406c  xor     r9d, r9d
0x10041406f  mov     r8, cs:off_1005E44C8; "<LoadClusterResourceLibraries|RET|SNI> "...
0x100414076  mov     edx, 3D800h
0x10041407b  xor     ecx, ecx
0x10041407d  call    _bidTraceW
0x100414082  jmp     loc_100414146
0x100414087  call    cs:__imp_GetLastError
0x10041408d  mov     ebp, eax
0x10041408f  cmp     [rsi], rbx
0x100414092  jz      short loc_1004140A0
0x100414094  mov     rcx, [rsi]; hLibModule
0x100414097  call    cs:__imp_FreeLibrary
0x10041409d  mov     [rsi], rbx
0x1004140a0  mov     rcx, [rsi+68h]; hLibModule
0x1004140a4  test    rcx, rcx
0x1004140a7  jz      short loc_1004140B3
0x1004140a9  call    cs:__imp_FreeLibrary
0x1004140af  mov     [rsi+68h], rbx
0x1004140b3  test    rdi, rdi
0x1004140b6  jz      short loc_1004140C1
0x1004140b8  mov     rcx, rdi; hLibModule
0x1004140bb  call    cs:__imp_FreeLibrary
0x1004140c1  mov     edi, 0C3B4h
0x1004140c6  mov     esi, 7
0x1004140cb  test    byte ptr cs:_bidGblFlags, 2
0x1004140d2  jz      short loc_100414105
0x1004140d4  mov     rax, cs:off_1005E44D0; "<LoadClusterResourceLibraries|ERR|SNI> "...
0x1004140db  test    rax, rax
0x1004140de  jz      short loc_100414105
0x1004140e0  mov     ecx, edi; unsigned int
0x1004140e2  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004140e7  mov     [rsp+48h+var_20], ebp
0x1004140eb  mov     [rsp+48h+var_28], eax
0x1004140ef  mov     r9d, esi
0x1004140f2  mov     r8, cs:off_1005E44D0; "<LoadClusterResourceLibraries|ERR|SNI> "...
0x1004140f9  mov     edx, 43C00h
0x1004140fe  xor     ecx, ecx
0x100414100  call    _bidTraceW
0x100414105  mov     r8d, edi
0x100414108  mov     edx, ebp
0x10041410a  mov     ecx, esi
0x10041410c  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100414111  mov     eax, cs:_bidGblFlags
0x100414117  mov     ecx, 20002h
0x10041411c  and     eax, ecx
0x10041411e  cmp     eax, ecx
0x100414120  jnz     short loc_100414144
0x100414122  mov     rax, cs:off_1005E44D8; "<LoadClusterResourceLibraries|RET|SNI> "...
0x100414129  test    rax, rax
0x10041412c  jz      short loc_100414144
0x10041412e  mov     r9d, ebp
0x100414131  mov     r8, cs:off_1005E44D8; "<LoadClusterResourceLibraries|RET|SNI> "...
0x100414138  mov     edx, 44400h
0x10041413d  xor     ecx, ecx
0x10041413f  call    _bidTraceW
0x100414144  mov     ebx, ebp
0x100414146  lea     rcx, [rsp+48h+arg_8]; this
0x10041414b  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100414150  mov     eax, ebx
0x100414152  mov     rbx, [rsp+48h+arg_0]
0x100414157  mov     rbp, [rsp+48h+arg_10]
0x10041415c  mov     rsi, [rsp+48h+arg_18]
0x100414161  add     rsp, 40h
0x100414165  pop     rdi
0x100414166  retn
```
