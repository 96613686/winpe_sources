# ProvisioningPackage::GetDataSourceId(ushort const *,_LARGE_INTEGER *)

- ea: `0x18000741c`
- end: `0x1800076fe`
- name: `?GetDataSourceId@ProvisioningPackage@@QEAAJPEBGPEAT_LARGE_INTEGER@@@Z`
- size: `738`
- prototype: `__int64 __fastcall(char *UserData, const unsigned __int16 *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, installer_update`

## callers

- `0x180016710`

## callees

- `0x180006014`
- `0x18000741c`
- `0x18000ef58`
- `0x18000f040`
- `0x1800100a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800075b2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800075b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007667`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007654`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800074fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800074fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000765f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000768a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000765f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000768a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076e5`
- `WOFUTIL!WofWimAddEntry` at `0x1800075fd`
- `WOFUTIL!WofWimAddEntry` at `0x1800075fd`
- `WOFUTIL!WofEnumEntries` at `0x1800075d9`
- `WOFUTIL!WofEnumEntries` at `0x1800075d9`

## string_xrefs

- `0x1800076ce`: `    Failed to allocate link path string`
- `0x18000758c`: `    Failed to get path root`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::GetDataSourceId(
        char *UserData,
        const unsigned __int16 *a2,
        union _LARGE_INTEGER *a3)
{
  unsigned __int16 *v6; // rbx
  int v7; // edi
  unsigned __int16 *v8; // rsi
  unsigned __int64 v9; // rcx
  enum PATHCCH_OPTIONS v10; // edi
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  unsigned __int64 v13; // rsi
  unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  HRESULT v16; // eax
  bool v17; // zf
  void **v18; // rsi
  HRESULT v19; // eax
  void *v20; // rbp
  DWORD LastError; // edi
  unsigned __int16 *v22; // rcx
  PLARGE_INTEGER DataSourceId; // [rsp+20h] [rbp-68h]
  unsigned __int16 *v25; // [rsp+30h] [rbp-58h] BYREF
  enum PATHCCH_OPTIONS v26; // [rsp+A8h] [rbp+20h] BYREF

  v26 = PATHCCH_ALLOW_LONG_PATHS;
  v6 = 0;
  v25 = 0;
  if ( !AreOptionsValidAndOptInLongPathAwareProcess(&v26) )
  {
    v7 = -2147024809;
    v8 = 0;
LABEL_46:
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetDataSourceId",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      105,
      v7,
      v25);
    ProvPackageLog(3, L"    Failed to allocate link path string");
    v17 = v8 == 0;
    goto LABEL_47;
  }
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  if ( v9 >= 0x8000 )
  {
    v7 = -2147024690;
    v8 = 0;
LABEL_45:
    v25 = 0;
    goto LABEL_46;
  }
  v10 = v26;
  if ( v9 )
  {
    if ( (v26 & 0x20) != 0 && a2[v9 - 1] != 92 )
      ++v9;
    v11 = v9 + 1;
  }
  else
  {
    v11 = 2;
  }
  if ( (v26 & 0x10) != 0 || v11 > 0x104 && (v26 & 5) == 5 )
    v12 = 6;
  else
    v12 = 0;
  v13 = v12 + v11;
  if ( v12 + v11 > (unsigned __int64)((v26 & 0x11) != 0 ? 0x7EFC : 0) + 260 )
    v13 = (v26 & 0x11) != 0 ? 0x8000LL : 260LL;
  v14 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v13);
  v6 = v14;
  if ( !v14 )
  {
    v8 = 0;
    v7 = -2147024882;
    goto LABEL_45;
  }
  v7 = PathCchCanonicalizeEx(v14, v13, a2, v10);
  if ( v7 < 0 )
  {
    LocalFree(v6);
    v6 = 0;
  }
  v25 = v6;
  if ( v7 < 0 )
  {
    v8 = v6;
    goto LABEL_46;
  }
  v15 = -1;
  do
    ++v15;
  while ( v6[v15] );
  v16 = PathCchStripToRoot(v6, v15 + 1);
  v7 = v16;
  if ( v16 < 0 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::GetDataSourceId",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      109,
      v16,
      v25);
    ProvPackageLog(3, L"    Failed to get path root");
LABEL_29:
    v17 = v6 == 0;
LABEL_47:
    if ( !v17 )
      LocalFree(v6);
    return (unsigned int)v7;
  }
  v18 = (void **)(UserData + 80);
  if ( !*((_QWORD *)UserData + 10) || (unsigned int)_o__wcsicmp(v6) )
  {
    *((_QWORD *)UserData + 9) = -1;
    if ( WofEnumEntries(v6, 1u, ProvisioningPackage::DataSourceEnum, UserData) < 0 || *((_QWORD *)UserData + 9) == -1 )
    {
      v19 = WofWimAddEntry(v6, *((PCWSTR *)UserData + 3), 0, 1u, (PLARGE_INTEGER)UserData + 9);
      v7 = v19;
      if ( v19 < 0 )
      {
        LODWORD(DataSourceId) = 125;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "ProvisioningPackage::GetDataSourceId",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
          DataSourceId,
          v19,
          v25);
        ProvPackageLog(3, L"    Failed to add wof entry");
        goto LABEL_29;
      }
    }
  }
  if ( v18 == (void **)&v25 )
  {
    v22 = v6;
  }
  else
  {
    v20 = *v18;
    if ( *v18 )
    {
      LastError = GetLastError();
      LocalFree(v20);
      SetLastError(LastError);
    }
    *v18 = v6;
    v6 = 0;
    v22 = 0;
  }
  *a3 = *(union _LARGE_INTEGER *)(UserData + 72);
  if ( v22 )
    LocalFree(v6);
  return 0;
}

```

## disassembly

```asm
0x18000741c  mov     rax, rsp
0x18000741f  push    rbx
0x180007420  push    rbp
0x180007421  push    rsi
0x180007422  push    rdi
0x180007423  push    r12
0x180007425  push    r13
0x180007427  push    r14
0x180007429  push    r15
0x18000742b  sub     rsp, 48h
0x18000742f  mov     r15, r8
0x180007432  mov     rbp, rdx
0x180007435  mov     r14, rcx
0x180007438  mov     dword ptr [rax+20h], 1
0x18000743f  xor     r12d, r12d
0x180007442  mov     ebx, r12d
0x180007445  mov     [rax-58h], rbx
0x180007449  lea     rcx, [rax+20h]; enum PATHCCH_OPTIONS *
0x18000744d  call    ?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z; AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)
0x180007452  test    al, al
0x180007454  jnz     short loc_180007463
0x180007456  mov     edi, 80070057h
0x18000745b  mov     esi, r12d
0x18000745e  jmp     loc_1800076A1
0x180007463  or      r13, 0FFFFFFFFFFFFFFFFh
0x180007467  mov     rcx, r13
0x18000746a  inc     rcx
0x18000746d  cmp     [rbp+rcx*2+0], r12w
0x180007473  jnz     short loc_18000746A
0x180007475  cmp     rcx, 8000h
0x18000747c  jb      short loc_18000748B
0x18000747e  mov     edi, 800700CEh
0x180007483  mov     rsi, r12
0x180007486  jmp     loc_18000769C
0x18000748b  mov     edi, [rsp+88h+arg_18]
0x180007492  test    rcx, rcx
0x180007495  jz      short loc_1800074AD
0x180007497  test    dil, 20h
0x18000749b  jz      short loc_1800074A8
0x18000749d  cmp     word ptr [rbp+rcx*2-2], 5Ch ; '\'
0x1800074a3  jz      short loc_1800074A8
0x1800074a5  inc     rcx
0x1800074a8  inc     rcx
0x1800074ab  jmp     short loc_1800074B2
0x1800074ad  mov     ecx, 2
0x1800074b2  mov     eax, edi
0x1800074b4  and     al, 11h
0x1800074b6  neg     al
0x1800074b8  sbb     rdx, rdx
0x1800074bb  and     edx, 7EFCh
0x1800074c1  mov     eax, 104h
0x1800074c6  add     rdx, rax
0x1800074c9  test    dil, 10h
0x1800074cd  jnz     short loc_1800074E2
0x1800074cf  cmp     rcx, rax
0x1800074d2  jbe     short loc_1800074DD
0x1800074d4  mov     eax, edi
0x1800074d6  and     eax, 5
0x1800074d9  cmp     al, 5
0x1800074db  jz      short loc_1800074E2
0x1800074dd  mov     rax, r12
0x1800074e0  jmp     short loc_1800074E7
0x1800074e2  mov     eax, 6
0x1800074e7  lea     rsi, [rax+rcx]
0x1800074eb  cmp     rsi, rdx
0x1800074ee  cmova   rsi, rdx
0x1800074f2  lea     rdx, [rsi+rsi]; uBytes
0x1800074f6  mov     ecx, 40h ; '@'; uFlags
0x1800074fb  call    cs:__imp_LocalAlloc
0x180007501  mov     rbx, rax
0x180007504  test    rax, rax
0x180007507  jz      loc_180007694
0x18000750d  mov     r9d, edi; enum PATHCCH_OPTIONS
0x180007510  mov     r8, rbp; unsigned __int16 *
0x180007513  mov     rdx, rsi; unsigned __int64
0x180007516  mov     rcx, rax; unsigned __int16 *
0x180007519  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x18000751e  mov     edi, eax
0x180007520  test    eax, eax
0x180007522  jns     short loc_180007530
0x180007524  mov     rcx, rbx; hMem
0x180007527  call    cs:__imp_LocalFree
0x18000752d  mov     rbx, r12
0x180007530  mov     [rsp+88h+var_58], rbx
0x180007535  test    edi, edi
0x180007537  jns     short loc_180007541
0x180007539  mov     rsi, rbx
0x18000753c  jmp     loc_1800076A1
0x180007541  mov     rdx, r13
0x180007544  inc     rdx
0x180007547  cmp     [rbx+rdx*2], r12w
0x18000754c  jnz     short loc_180007544
0x18000754e  inc     rdx; cchPath
0x180007551  mov     rcx, rbx; pszPath
0x180007554  call    PathCchStripToRoot
0x180007559  mov     edi, eax
0x18000755b  test    eax, eax
0x18000755d  jns     short loc_1800075A3
0x18000755f  mov     [rsp+88h+var_60], eax
0x180007563  mov     dword ptr [rsp+88h+DataSourceId], 6Dh ; 'm'
0x18000756b  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180007572  lea     r8, aProvisioningpa_19; "ProvisioningPackage::GetDataSourceId"
0x180007579  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007580  mov     ebp, 3
0x180007585  mov     ecx, ebp
0x180007587  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000758c  lea     rdx, aFailedToGetPat; "    Failed to get path root"
0x180007593  mov     ecx, ebp
0x180007595  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000759a  nop
0x18000759b  test    rbx, rbx
0x18000759e  jmp     loc_1800076E0
0x1800075a3  lea     rsi, [r14+50h]
0x1800075a7  mov     rdx, [rsi]
0x1800075aa  test    rdx, rdx
0x1800075ad  jz      short loc_1800075C0
0x1800075af  mov     rcx, rbx
0x1800075b2  call    cs:__imp__o__wcsicmp
0x1800075b8  test    eax, eax
0x1800075ba  jz      loc_180007642
0x1800075c0  lea     rdi, [r14+48h]
0x1800075c4  mov     [rdi], r13
0x1800075c7  mov     r9, r14; UserData
0x1800075ca  lea     r8, ?DataSourceEnum@ProvisioningPackage@@CAHQEAXPEAX@Z; EnumProc
0x1800075d1  mov     edx, 1; Provider
0x1800075d6  mov     rcx, rbx; VolumeName
0x1800075d9  call    cs:__imp_WofEnumEntries
0x1800075df  test    eax, eax
0x1800075e1  js      short loc_1800075E8
0x1800075e3  cmp     [rdi], r13
0x1800075e6  jnz     short loc_180007642
0x1800075e8  mov     [rsp+88h+DataSourceId], rdi; DataSourceId
0x1800075ed  mov     r9d, 1; WimIndex
0x1800075f3  xor     r8d, r8d; WimType
0x1800075f6  mov     rdx, [r14+18h]; WimPath
0x1800075fa  mov     rcx, rbx; VolumeName
0x1800075fd  call    cs:__imp_WofWimAddEntry
0x180007603  mov     edi, eax
0x180007605  test    eax, eax
0x180007607  jns     short loc_180007642
0x180007609  mov     [rsp+88h+var_60], eax
0x18000760d  mov     dword ptr [rsp+88h+DataSourceId], 7Dh ; '}'
0x180007615  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000761c  lea     r8, aProvisioningpa_19; "ProvisioningPackage::GetDataSourceId"
0x180007623  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000762a  mov     ebp, 3
0x18000762f  mov     ecx, ebp
0x180007631  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180007636  lea     rdx, aFailedToAddWof; "    Failed to add wof entry"
0x18000763d  jmp     loc_180007593
0x180007642  lea     rax, [rsp+88h+var_58]
0x180007647  cmp     rsi, rax
0x18000764a  jz      short loc_180007678
0x18000764c  mov     rbp, [rsi]
0x18000764f  test    rbp, rbp
0x180007652  jz      short loc_18000766D
0x180007654  call    cs:__imp_GetLastError
0x18000765a  mov     edi, eax
0x18000765c  mov     rcx, rbp; hMem
0x18000765f  call    cs:__imp_LocalFree
0x180007665  mov     ecx, edi; dwErrCode
0x180007667  call    cs:__imp_SetLastError
0x18000766d  mov     [rsi], rbx
0x180007670  mov     rbx, r12
0x180007673  mov     rcx, r12
0x180007676  jmp     short loc_18000767B
0x180007678  mov     rcx, rbx
0x18000767b  mov     rax, [r14+48h]
0x18000767f  mov     [r15], rax
0x180007682  test    rcx, rcx
0x180007685  jz      short loc_180007690
0x180007687  mov     rcx, rbx; hMem
0x18000768a  call    cs:__imp_LocalFree
0x180007690  xor     eax, eax
0x180007692  jmp     short loc_1800076ED
0x180007694  mov     rsi, rbx
0x180007697  mov     edi, 8007000Eh
0x18000769c  mov     [rsp+88h+var_58], rbx
0x1800076a1  mov     [rsp+88h+var_60], edi
0x1800076a5  mov     dword ptr [rsp+88h+DataSourceId], 69h ; 'i'
0x1800076ad  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800076b4  lea     r8, aProvisioningpa_19; "ProvisioningPackage::GetDataSourceId"
0x1800076bb  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800076c2  mov     ebp, 3
0x1800076c7  mov     ecx, ebp
0x1800076c9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800076ce  lea     rdx, aFailedToAlloca_38; "    Failed to allocate link path string"
0x1800076d5  mov     ecx, ebp
0x1800076d7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800076dc  nop
0x1800076dd  test    rsi, rsi
0x1800076e0  jz      short loc_1800076EB
0x1800076e2  mov     rcx, rbx; hMem
0x1800076e5  call    cs:__imp_LocalFree
0x1800076eb  mov     eax, edi
0x1800076ed  add     rsp, 48h
0x1800076f1  pop     r15
0x1800076f3  pop     r14
0x1800076f5  pop     r13
0x1800076f7  pop     r12
0x1800076f9  pop     rdi
0x1800076fa  pop     rsi
0x1800076fb  pop     rbp
0x1800076fc  pop     rbx
0x1800076fd  retn
```
