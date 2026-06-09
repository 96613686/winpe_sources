# KspProcessOpaqueBlob

- ea: `0x1800362fc`
- end: `0x18003674c`
- name: `KspProcessOpaqueBlob`
- size: `1104`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002b460`

## callees

- `0x1800060e0`
- `0x180006744`
- `0x180008840`
- `0x1800090c0`
- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180010530`
- `0x18001e4cc`
- `0x1800362fc`
- `0x1800398b0`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003663e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003663e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800366b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036709`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800366b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036709`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003662e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003662e`

## string_xrefs

- `0x180036374`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x1800364f6`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x180036547`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x1800365ef`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x180036650`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x1800366e3`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`

## pseudocode

```c
__int64 __fastcall KspProcessOpaqueBlob(__int64 a1, __int64 a2, _DWORD *a3, unsigned int a4)
{
  __int64 v4; // r14
  __int64 v7; // rdi
  __int64 v8; // r9
  __int64 LastError; // rbx
  __int64 v10; // rcx
  unsigned int v11; // edx
  unsigned int v12; // r8d
  unsigned int v13; // r10d
  unsigned int v14; // r11d
  unsigned int i; // ecx
  unsigned __int64 v16; // rax
  unsigned int v17; // ecx
  unsigned int v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // eax
  unsigned int v21; // ecx
  unsigned int j; // edx
  int v23; // r8d
  unsigned int v24; // eax
  __int64 v25; // rcx
  void *v26; // rax
  __int64 v27; // r13
  unsigned int UserDirectory; // eax
  _WORD *v29; // rcx
  __int64 v30; // rax
  unsigned int NestedDirectories; // eax
  __int64 v32; // r9
  __int64 v33; // r14
  char *v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v41[224]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = -1;
  v39 = 0;
  hFile[0] = (HANDLE)-1LL;
  NumberOfBytesWritten = 0;
  v7 = 0;
  if ( a4 - 68 > 0xFFFFBC )
  {
    LODWORD(LastError) = -2146893819;
    DebugTraceError(2148073477LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 883);
LABEL_55:
    if ( v4 != -1 )
      CloseHandle((HANDLE)v4);
    goto LABEL_57;
  }
  if ( *a3 != 826427725 )
  {
    v8 = 892;
LABEL_4:
    LODWORD(LastError) = -2146893819;
    v10 = 2148073477LL;
LABEL_5:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", v8);
    return (unsigned int)LastError;
  }
  if ( a3[1] > a4
    || (v11 = a3[2], v11 > a4)
    || (v12 = a3[3], v12 > a4)
    || (v13 = a3[4], v13 > a4)
    || (v14 = a3[5], v14 > a4) )
  {
    v8 = 903;
    goto LABEL_4;
  }
  for ( i = 0; i < 8; ++i )
  {
    if ( a3[i + 6] > a4 )
    {
      v8 = 912;
      goto LABEL_4;
    }
  }
  v16 = 2LL * (unsigned int)a3[1];
  if ( v16 > 0xFFFFFFFF
    || (v17 = v16 + 68, (int)v16 + 68 < (unsigned int)v16)
    || (v18 = v17 + v11, v17 + v11 < v17)
    || (v19 = v18 + v12, v18 + v12 < v18)
    || (v20 = v19 + v13, v19 + v13 < v19)
    || (v21 = v20 + v14, v20 + v14 < v20) )
  {
    v8 = 926;
    goto LABEL_4;
  }
  for ( j = 0; j < 8; ++j )
  {
    v23 = a3[j + 6];
    if ( v23 )
    {
      v24 = v21 + 16;
      if ( v21 + 16 < v21 || (v21 = v23 + v24, v23 + v24 < v24) )
      {
        v8 = 939;
        goto LABEL_4;
      }
    }
  }
  if ( a4 != v21 )
  {
    v8 = 948;
    goto LABEL_4;
  }
  v25 = *(_QWORD *)(a2 + 8);
  if ( v25 )
    MSCryptFree(v25);
  v26 = (void *)SafeAllocaAllocateFromHeap(2LL * (unsigned int)(a3[1] + 1));
  *(_QWORD *)(a2 + 8) = v26;
  if ( !v26 )
  {
    LODWORD(LastError) = -2146893810;
    v8 = 968;
    v10 = 2148073486LL;
    goto LABEL_5;
  }
  memcpy_0(v26, a3 + 17, 2LL * (unsigned int)a3[1]);
  *(_WORD *)(*(_QWORD *)(a2 + 8) + 2LL * (unsigned int)a3[1]) = 0;
  v27 = (unsigned int)a3[1];
  UserDirectory = GetUserDirectory(*(unsigned int *)(a2 + 32), *(_QWORD *)(a2 + 80) != 0, *(_QWORD *)(a2 + 72), &v39);
  LODWORD(LastError) = UserDirectory;
  if ( UserDirectory )
  {
    DebugTraceError(UserDirectory, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 989);
    v7 = v39;
    goto LABEL_57;
  }
  v29 = *(_WORD **)(a2 + 72);
  v30 = -1;
  do
    ++v30;
  while ( v29[v30] );
  v7 = v39;
  NestedDirectories = CreateNestedDirectories(v29, (void *)(v39 + 2 * (v30 + 1)));
  LODWORD(LastError) = NestedDirectories;
  if ( NestedDirectories )
  {
    v32 = 1004;
LABEL_41:
    DebugTraceError(NestedDirectories, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", v32);
    goto LABEL_57;
  }
  NestedDirectories = AddMachineGuidAndAppContainerSidHashToContainerNameW(*(STRSAFE_PCNZWCH *)(a2 + 8));
  LODWORD(LastError) = NestedDirectories;
  if ( NestedDirectories )
  {
    v32 = 1016;
    goto LABEL_41;
  }
  v33 = (unsigned int)a3[2];
  LODWORD(LastError) = OpenFileInStorageArea(*(_DWORD *)(a2 + 32), 0x40000000, v7, (unsigned int)v41, (__int64)hFile);
  if ( (_DWORD)LastError )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_ddedfd0907163dc02d23f0e3561c76af_Traceguids,
        v7,
        (__int64)v41);
    DebugTraceError(
      (unsigned int)LastError,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c",
      1032);
    v4 = (__int64)hFile[0];
    goto LABEL_55;
  }
  v34 = (char *)a3 + 2 * v27 + v33 + 68;
  v4 = (__int64)hFile[0];
  if ( !WriteFile(hFile[0], v34, a3[3], &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 1039);
    KspCryptAuditKeyFileOperation(0, v36, a2, v7, v41, 2459, LastError);
    goto LABEL_55;
  }
  KspCryptAuditKeyFileOperation(1, v35, a2, v7, v41, 2459, 0);
  CloseHandle((HANDLE)v4);
  LODWORD(LastError) = 0;
LABEL_57:
  if ( v7 )
    MSCryptFree(v7);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800362fc  mov     [rsp-8+arg_0], rbx
0x180036301  push    rbp
0x180036302  push    rsi
0x180036303  push    rdi
0x180036304  push    r12
0x180036306  push    r13
0x180036308  push    r14
0x18003630a  push    r15
0x18003630c  lea     rbp, [rsp-50h]
0x180036311  sub     rsp, 150h
0x180036318  mov     rax, cs:__security_cookie
0x18003631f  xor     rax, rsp
0x180036322  mov     [rbp+80h+var_40], rax
0x180036326  xor     r13d, r13d
0x180036329  lea     eax, [r9-44h]
0x18003632d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180036331  mov     [rsp+180h+var_138], r13
0x180036336  mov     [rsp+180h+hFile], r14
0x18003633b  mov     rsi, r8
0x18003633e  mov     [rsp+180h+NumberOfBytesWritten], r13d
0x180036343  mov     r15, rdx
0x180036346  mov     edi, r13d
0x180036349  cmp     eax, 0FFFFBCh
0x18003634e  ja      loc_1800366DD
0x180036354  cmp     dword ptr [r8], 3142494Dh
0x18003635b  jz      short loc_180036385
0x18003635d  mov     r9d, 37Ch
0x180036363  mov     ebx, 80090005h
0x180036368  mov     ecx, 80090005h
0x18003636d  lea     rdx, aStatus; "Status"
0x180036374  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003637b  call    DebugTraceError
0x180036380  jmp     loc_180036722
0x180036385  cmp     [r8+4], r9d
0x180036389  ja      loc_1800366D2
0x18003638f  mov     edx, [r8+8]
0x180036393  cmp     edx, r9d
0x180036396  ja      loc_1800366D2
0x18003639c  mov     r8d, [r8+0Ch]
0x1800363a0  cmp     r8d, r9d
0x1800363a3  ja      loc_1800366D2
0x1800363a9  mov     r10d, [rsi+10h]
0x1800363ad  cmp     r10d, r9d
0x1800363b0  ja      loc_1800366D2
0x1800363b6  mov     r11d, [rsi+14h]
0x1800363ba  cmp     r11d, r9d
0x1800363bd  ja      loc_1800366D2
0x1800363c3  mov     ecx, r13d
0x1800363c6  cmp     ecx, 8
0x1800363c9  jnb     short loc_1800363E0
0x1800363cb  mov     eax, ecx
0x1800363cd  cmp     [rsi+rax*4+18h], r9d
0x1800363d2  ja      short loc_1800363D8
0x1800363d4  inc     ecx
0x1800363d6  jmp     short loc_1800363C6
0x1800363d8  mov     r9d, 390h
0x1800363de  jmp     short loc_180036363
0x1800363e0  mov     eax, [rsi+4]
0x1800363e3  mov     ecx, 0FFFFFFFFh
0x1800363e8  add     rax, rax
0x1800363eb  cmp     rax, rcx
0x1800363ee  ja      loc_1800366C7
0x1800363f4  lea     ecx, [rax+44h]
0x1800363f7  cmp     ecx, eax
0x1800363f9  jb      loc_1800366C7
0x1800363ff  lea     eax, [rcx+rdx]
0x180036402  cmp     eax, ecx
0x180036404  jb      loc_1800366C7
0x18003640a  lea     ecx, [rax+r8]
0x18003640e  cmp     ecx, eax
0x180036410  jb      loc_1800366C7
0x180036416  lea     eax, [rcx+r10]
0x18003641a  cmp     eax, ecx
0x18003641c  jb      loc_1800366C7
0x180036422  lea     ecx, [rax+r11]
0x180036426  cmp     ecx, eax
0x180036428  jb      loc_1800366C7
0x18003642e  mov     edx, r13d
0x180036431  cmp     edx, 8
0x180036434  jnb     short loc_180036460
0x180036436  mov     eax, edx
0x180036438  mov     r8d, [rsi+rax*4+18h]
0x18003643d  test    r8d, r8d
0x180036440  jz      short loc_180036451
0x180036442  lea     eax, [rcx+10h]
0x180036445  cmp     eax, ecx
0x180036447  jb      short loc_180036455
0x180036449  lea     ecx, [r8+rax]
0x18003644d  cmp     ecx, eax
0x18003644f  jb      short loc_180036455
0x180036451  inc     edx
0x180036453  jmp     short loc_180036431
0x180036455  mov     r9d, 3ABh
0x18003645b  jmp     loc_180036363
0x180036460  cmp     r9d, ecx
0x180036463  jz      short loc_180036470
0x180036465  mov     r9d, 3B4h
0x18003646b  jmp     loc_180036363
0x180036470  mov     rcx, [r15+8]
0x180036474  test    rcx, rcx
0x180036477  jz      short loc_18003647E
0x180036479  call    MSCryptFree
0x18003647e  mov     ecx, [rsi+4]
0x180036481  inc     ecx
0x180036483  add     rcx, rcx
0x180036486  call    SafeAllocaAllocateFromHeap
0x18003648b  mov     [r15+8], rax
0x18003648f  test    rax, rax
0x180036492  jnz     short loc_1800364A9
0x180036494  mov     ebx, 8009000Eh
0x180036499  mov     r9d, 3C8h
0x18003649f  mov     ecx, 8009000Eh
0x1800364a4  jmp     loc_18003636D
0x1800364a9  mov     r8d, [rsi+4]
0x1800364ad  lea     r12, [rsi+44h]
0x1800364b1  add     r8, r8; Size
0x1800364b4  mov     rdx, r12; Src
0x1800364b7  mov     rcx, rax; void *
0x1800364ba  call    memcpy_0
0x1800364bf  mov     edx, [rsi+4]
0x1800364c2  lea     r9, [rsp+180h+var_138]
0x1800364c7  mov     rcx, [r15+8]
0x1800364cb  mov     [rcx+rdx*2], r13w
0x1800364d0  mov     edx, edi
0x1800364d2  cmp     [r15+50h], rdi
0x1800364d6  mov     r8, [r15+48h]
0x1800364da  mov     ecx, [r15+20h]
0x1800364de  setnz   dl
0x1800364e1  mov     r13d, [rsi+4]
0x1800364e5  call    GetUserDirectory
0x1800364ea  mov     ebx, eax
0x1800364ec  test    eax, eax
0x1800364ee  jz      short loc_180036515
0x1800364f0  mov     r9d, 3DDh
0x1800364f6  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800364fd  lea     rdx, aStatus; "Status"
0x180036504  mov     ecx, eax
0x180036506  call    DebugTraceError
0x18003650b  mov     rdi, [rsp+180h+var_138]
0x180036510  jmp     loc_180036715
0x180036515  mov     rcx, [r15+48h]; Src
0x180036519  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003651d  inc     rax
0x180036520  cmp     [rcx+rax*2], di
0x180036524  jnz     short loc_18003651D
0x180036526  mov     rdi, [rsp+180h+var_138]
0x18003652b  inc     rax
0x18003652e  mov     r8d, [r15+20h]
0x180036532  lea     rdx, [rdi+rax*2]; void *
0x180036536  call    CreateNestedDirectories
0x18003653b  mov     ebx, eax
0x18003653d  test    eax, eax
0x18003653f  jz      short loc_180036561
0x180036541  mov     r9d, 3ECh
0x180036547  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003654e  mov     ecx, eax
0x180036550  lea     rdx, aStatus; "Status"
0x180036557  call    DebugTraceError
0x18003655c  jmp     loc_180036715
0x180036561  mov     edx, [r15+210h]
0x180036568  lea     r8, [rsp+180h+var_120]
0x18003656d  mov     rcx, [r15+8]; pszSrc
0x180036571  call    AddMachineGuidAndAppContainerSidHashToContainerNameW
0x180036576  mov     ebx, eax
0x180036578  test    eax, eax
0x18003657a  jz      short loc_180036584
0x18003657c  mov     r9d, 3F8h
0x180036582  jmp     short loc_180036547
0x180036584  mov     ecx, [r15+20h]
0x180036588  lea     rax, [rsp+180h+hFile]
0x18003658d  mov     r14d, [rsi+8]
0x180036591  lea     r9, [rsp+180h+var_120]
0x180036596  mov     r8, rdi
0x180036599  mov     [rsp+180h+lpOverlapped], rax
0x18003659e  mov     edx, 40000000h
0x1800365a3  call    OpenFileInStorageArea
0x1800365a8  mov     ebx, eax
0x1800365aa  test    eax, eax
0x1800365ac  jz      short loc_18003660E
0x1800365ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365b5  lea     rax, WPP_GLOBAL_Control
0x1800365bc  cmp     rcx, rax
0x1800365bf  jz      short loc_1800365E9
0x1800365c1  test    byte ptr [rcx+1Ch], 1
0x1800365c5  jz      short loc_1800365E9
0x1800365c7  mov     rcx, [rcx+10h]
0x1800365cb  lea     rax, [rsp+180h+var_120]
0x1800365d0  mov     edx, 0Ah
0x1800365d5  mov     [rsp+180h+lpOverlapped], rax
0x1800365da  mov     r9, rdi
0x1800365dd  lea     r8, WPP_ddedfd0907163dc02d23f0e3561c76af_Traceguids
0x1800365e4  call    WPP_SF_SS
0x1800365e9  mov     r9d, 408h
0x1800365ef  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800365f6  lea     rdx, aStatus; "Status"
0x1800365fd  mov     ecx, ebx
0x1800365ff  call    DebugTraceError
0x180036604  mov     r14, [rsp+180h+hFile]
0x180036609  jmp     loc_180036700
0x18003660e  mov     r8d, [rsi+0Ch]; nNumberOfBytesToWrite
0x180036612  lea     r9, [rsp+180h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180036617  add     r14, r12
0x18003661a  lea     rdx, [r14+r13*2]; lpBuffer
0x18003661e  mov     r14, [rsp+180h+hFile]
0x180036623  xor     r13d, r13d
0x180036626  mov     rcx, r14; hFile
0x180036629  mov     [rsp+180h+lpOverlapped], r13; lpOverlapped
0x18003662e  call    cs:__imp_WriteFile
0x180036635  nop     dword ptr [rax+rax+00h]
0x18003663a  test    eax, eax
0x18003663c  jnz     short loc_18003668C
0x18003663e  call    cs:__imp_GetLastError
0x180036645  nop     dword ptr [rax+rax+00h]
0x18003664a  mov     r9d, 40Fh
0x180036650  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180036657  mov     ecx, eax
0x180036659  lea     rdx, aStatus; "Status"
0x180036660  mov     ebx, eax
0x180036662  call    DebugTraceError
0x180036667  lea     rax, [rsp+180h+var_120]
0x18003666c  mov     [rsp+180h+var_150], ebx
0x180036670  mov     [rsp+180h+var_158], 99Bh
0x180036678  mov     r9, rdi
0x18003667b  mov     r8, r15
0x18003667e  mov     [rsp+180h+lpOverlapped], rax
0x180036683  xor     ecx, ecx
0x180036685  call    KspCryptAuditKeyFileOperation
0x18003668a  jmp     short loc_180036700
0x18003668c  mov     [rsp+180h+var_150], r13d
0x180036691  lea     rax, [rsp+180h+var_120]
0x180036696  mov     [rsp+180h+var_158], 99Bh
0x18003669e  mov     r9, rdi
0x1800366a1  mov     r8, r15
0x1800366a4  mov     [rsp+180h+lpOverlapped], rax
0x1800366a9  mov     ecx, 1
0x1800366ae  call    KspCryptAuditKeyFileOperation
0x1800366b3  mov     rcx, r14; hObject
0x1800366b6  call    cs:__imp_CloseHandle
0x1800366bd  nop     dword ptr [rax+rax+00h]
0x1800366c2  mov     ebx, r13d
0x1800366c5  jmp     short loc_180036715
0x1800366c7  mov     r9d, 39Eh
0x1800366cd  jmp     loc_180036363
0x1800366d2  mov     r9d, 387h
0x1800366d8  jmp     loc_180036363
0x1800366dd  mov     r9d, 373h
0x1800366e3  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800366ea  lea     rdx, aStatus; "Status"
0x1800366f1  mov     ecx, 80090005h
0x1800366f6  mov     ebx, 80090005h
0x1800366fb  call    DebugTraceError
0x180036700  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180036704  jz      short loc_180036715
0x180036706  mov     rcx, r14; hObject
0x180036709  call    cs:__imp_CloseHandle
0x180036710  nop     dword ptr [rax+rax+00h]
0x180036715  test    rdi, rdi
0x180036718  jz      short loc_180036722
0x18003671a  mov     rcx, rdi
0x18003671d  call    MSCryptFree
0x180036722  mov     eax, ebx
0x180036724  mov     rcx, [rbp+80h+var_40]
0x180036728  xor     rcx, rsp; StackCookie
0x18003672b  call    __security_check_cookie
0x180036730  mov     rbx, [rsp+180h+arg_0]
0x180036738  add     rsp, 150h
0x18003673f  pop     r15
0x180036741  pop     r14
0x180036743  pop     r13
0x180036745  pop     r12
0x180036747  pop     rdi
0x180036748  pop     rsi
0x180036749  pop     rbp
0x18003674a  retn
```
