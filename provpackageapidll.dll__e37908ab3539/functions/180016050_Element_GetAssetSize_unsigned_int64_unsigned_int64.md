# Element::GetAssetSize(unsigned __int64 *,unsigned __int64 *)

- ea: `0x180016050`
- end: `0x180016556`
- name: `?GetAssetSize@Element@@EEAAJPEA_K0@Z`
- size: `1286`
- prototype: `__int64 __fastcall(Element *__hidden this, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x180001510`
- `0x180001e66`
- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x18000fc8c`
- `0x180016050`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001628f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001628f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162e0`
- `WIMGAPI!WIMFindFirstImageFileEx` at `0x180016235`
- `WIMGAPI!WIMFindFirstImageFileEx` at `0x180016235`
- `WIMGAPI!WIMCloseHandle` at `0x180016272`
- `WIMGAPI!WIMCloseHandle` at `0x180016272`

## string_xrefs

- `0x180016487`: `    Failed to allocate spPayloadPath.get()`
- `0x180016420`: `    Failed to get next payload path`
- `0x1800163c1`: `    Failed to allocate spFullPayloadPath.get()`
- `0x180016350`: `    Failed to assemble full payload path`
- `0x1800162d2`: `    Failed to find first payload path`

## pseudocode

```c
__int64 __fastcall Element::GetAssetSize(Element *this, unsigned __int64 *a2, unsigned __int64 *a3)
{
  int v6; // eax
  unsigned int v7; // edi
  int v8; // eax
  unsigned __int64 v9; // rax
  void *v10; // rdi
  int v11; // eax
  unsigned int v12; // esi
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // r14
  unsigned __int64 v16; // rax
  WCHAR *v17; // rax
  WCHAR *v18; // rsi
  HRESULT v19; // eax
  unsigned int v20; // r14d
  __int64 ImageFile; // rax
  const struct std::nothrow_t *v22; // rdx
  const struct std::nothrow_t *v23; // rdx
  signed int LastError; // eax
  signed int v25; // eax
  const struct std::nothrow_t *v26; // rdx
  unsigned int v27; // ebx
  const struct std::nothrow_t *v28; // rdx
  const struct std::nothrow_t *v30; // rdx
  const struct std::nothrow_t *v31; // rdx
  const struct std::nothrow_t *v32; // rdx
  void (*v33)(void); // rax
  const struct std::nothrow_t *v34; // rdx
  __int64 v35; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v37[6]; // [rsp+38h] [rbp-C8h] BYREF
  char v38; // [rsp+68h] [rbp-98h]
  _BYTE v39[28]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v40; // [rsp+8Ch] [rbp-74h]
  unsigned int v41; // [rsp+90h] [rbp-70h]
  __int64 v42; // [rsp+2F8h] [rbp+1F8h]

  *a2 = 0;
  *a3 = 0;
  v36 = 0;
  v37[5] = (unsigned __int64)&v36;
  v38 = 1;
  v6 = (*(__int64 (__fastcall **)(Element *, __int64 *))(*(_QWORD *)this + 64LL))(this, &v36);
  v7 = v6;
  if ( v6 < 0 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::GetAssetSize",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      161,
      v6);
    ProvPackageLog(3, L"    Failed to enumerate payload");
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    return v7;
  }
  v37[0] = 0;
  while ( 1 )
  {
    v8 = (**(__int64 (__fastcall ***)(__int64, unsigned __int64 *))v36)(v36, v37);
    v7 = v8;
    if ( v8 < 0 )
      break;
    ++v37[0];
    v9 = 2 * v37[0];
    if ( !is_mul_ok(v37[0], 2u) )
      v9 = -1;
    v10 = operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
    v37[2] = (unsigned __int64)v10;
    if ( !v10 )
    {
      LODWORD(v35) = 169;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::GetAssetSize",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v35,
        -2147024882);
      ProvPackageLog(3, L"    Failed to allocate spPayloadPath.get()");
      if ( v36 )
      {
        v33 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
LABEL_40:
        v33();
      }
      return 2147942414LL;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, void *, unsigned __int64))(*(_QWORD *)v36 + 8LL))(v36, v10, v37[0]);
    v12 = v11;
    if ( v11 < 0 )
    {
      LODWORD(v35) = 172;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::GetAssetSize",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v35,
        v11);
      ProvPackageLog(3, L"    Failed to get next payload path");
      operator delete(v10, v34);
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      return v12;
    }
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v10 + v13) );
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(*((_QWORD *)this + 2) + 2 * v14) );
    v15 = v14 + v13 + 6;
    v16 = 2 * v15;
    if ( !is_mul_ok(v15, 2u) )
      v16 = -1;
    v17 = (WCHAR *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v17;
    v37[3] = (unsigned __int64)v17;
    if ( !v17 )
    {
      LODWORD(v35) = 178;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::GetAssetSize",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v35,
        -2147024882);
      ProvPackageLog(3, L"    Failed to allocate spFullPayloadPath.get()");
      operator delete(v10, v32);
      if ( v36 )
      {
        v33 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
        goto LABEL_40;
      }
      return 2147942414LL;
    }
    v19 = PathCchCombineEx(v17, v15, *((PCWSTR *)this + 2), (PCWSTR)v10, v35);
    v20 = v19;
    if ( v19 < 0 )
    {
      LODWORD(v35) = 182;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::GetAssetSize",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v35,
        v19);
      ProvPackageLog(3, L"    Failed to assemble full payload path");
      operator delete(v18, v30);
      operator delete(v10, v31);
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      return v20;
    }
    memset_0(v39, 0, 0x2A0u);
    ImageFile = WIMFindFirstImageFileEx(*(_QWORD *)(*((_QWORD *)this + 1) + 16LL), v18, 672, v39);
    v37[4] = ImageFile;
    if ( !ImageFile )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v35) = 187;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::GetAssetSize",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v35,
        LastError);
      ProvPackageLog(3, L"    Failed to find first payload path");
      v25 = GetLastError();
      v27 = v25;
      if ( v25 > 0 )
        v27 = (unsigned __int16)v25 | 0x80070000;
      operator delete(v18, v26);
      operator delete(v10, v28);
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      return v27;
    }
    *a2 += v42;
    v37[1] = __PAIR64__(v40, v41);
    *a3 += __PAIR64__(v40, v41);
    if ( ImageFile != -1 )
      WIMCloseHandle(ImageFile);
    operator delete(v18, v22);
    operator delete(v10, v23);
  }
  if ( v8 != -2147024637 )
  {
    LODWORD(v35) = 200;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::GetAssetSize",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v35,
      v8);
    ProvPackageLog(3, L"    Failed to get next payload length");
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    return v7;
  }
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  return 0;
}

```

## disassembly

```asm
0x180016050  mov     [rsp-8+arg_18], rbx
0x180016055  push    rbp
0x180016056  push    rsi
0x180016057  push    rdi
0x180016058  push    r12
0x18001605a  push    r13
0x18001605c  push    r14
0x18001605e  push    r15
0x180016060  lea     rbp, [rsp-220h]
0x180016068  sub     rsp, 320h
0x18001606f  mov     rax, cs:__security_cookie
0x180016076  xor     rax, rsp
0x180016079  mov     [rbp+250h+var_40], rax
0x180016080  mov     r12, r8
0x180016083  mov     r15, rdx
0x180016086  mov     rbx, rcx
0x180016089  xor     r13d, r13d
0x18001608c  mov     [rdx], r13
0x18001608f  mov     [r8], r13
0x180016092  mov     [rsp+350h+var_320], r13
0x180016097  lea     rax, [rsp+350h+var_320]
0x18001609c  mov     [rsp+350h+var_2F0], rax
0x1800160a1  mov     [rsp+350h+var_2E8], 1
0x1800160a6  mov     rax, [rcx]
0x1800160a9  lea     rdx, [rsp+350h+var_320]
0x1800160ae  mov     rax, [rax+40h]
0x1800160b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160b7  mov     edi, eax
0x1800160b9  test    eax, eax
0x1800160bb  jns     short loc_180016114
0x1800160bd  mov     [rsp+350h+var_328], eax
0x1800160c1  mov     dword ptr [rsp+350h+var_330], 0A1h
0x1800160c9  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800160d0  lea     r8, aElementGetasse; "Element::GetAssetSize"
0x1800160d7  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800160de  lea     ebx, [r13+3]
0x1800160e2  mov     ecx, ebx
0x1800160e4  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800160e9  lea     rdx, aFailedToEnumer_1; "    Failed to enumerate payload"
0x1800160f0  mov     ecx, ebx
0x1800160f2  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800160f7  nop
0x1800160f8  mov     rcx, [rsp+350h+var_320]
0x1800160fd  test    rcx, rcx
0x180016100  jz      short loc_18001610F
0x180016102  mov     rax, [rcx]
0x180016105  mov     rax, [rax+10h]
0x180016109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001610e  nop
0x18001610f  jmp     loc_18001652A
0x180016114  mov     [rsp+350h+var_318], r13
0x180016119  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001611d  mov     rcx, [rsp+350h+var_320]
0x180016122  mov     rax, [rcx]
0x180016125  lea     rdx, [rsp+350h+var_318]
0x18001612a  mov     rax, [rax]
0x18001612d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016132  mov     edi, eax
0x180016134  test    eax, eax
0x180016136  js      loc_1800164B4
0x18001613c  mov     rcx, [rsp+350h+var_318]
0x180016141  inc     rcx
0x180016144  mov     [rsp+350h+var_318], rcx
0x180016149  mov     eax, 2
0x18001614e  mul     rcx
0x180016151  cmovb   rax, r14
0x180016155  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001615c  mov     rcx, rax; unsigned __int64
0x18001615f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016164  mov     rdi, rax
0x180016167  mov     [rsp+350h+var_308], rax
0x18001616c  test    rax, rax
0x18001616f  jz      loc_180016456
0x180016175  mov     rcx, [rsp+350h+var_320]
0x18001617a  mov     rdx, [rcx]
0x18001617d  mov     rax, [rdx+8]
0x180016181  mov     r8, [rsp+350h+var_318]
0x180016186  mov     rdx, rdi
0x180016189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001618e  mov     esi, eax
0x180016190  test    eax, eax
0x180016192  js      loc_1800163F3
0x180016198  mov     rax, r14
0x18001619b  inc     rax
0x18001619e  cmp     [rdi+rax*2], r13w
0x1800161a3  jnz     short loc_18001619B
0x1800161a5  mov     rdx, [rbx+10h]
0x1800161a9  mov     rcx, r14
0x1800161ac  inc     rcx
0x1800161af  cmp     [rdx+rcx*2], r13w
0x1800161b4  jnz     short loc_1800161AC
0x1800161b6  lea     r14, [rax+6]
0x1800161ba  add     r14, rcx
0x1800161bd  mov     eax, 2
0x1800161c2  mul     r14
0x1800161c5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800161cc  cmovb   rax, rcx
0x1800161d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800161d7  mov     rcx, rax; unsigned __int64
0x1800161da  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800161df  mov     rsi, rax
0x1800161e2  mov     [rsp+350h+var_300], rax
0x1800161e7  test    rax, rax
0x1800161ea  jz      loc_180016390
0x1800161f0  mov     r9, rdi; pszMore
0x1800161f3  mov     r8, [rbx+10h]; pszPathIn
0x1800161f7  mov     rdx, r14; cchPathOut
0x1800161fa  mov     rcx, rax; pszPathOut
0x1800161fd  call    PathCchCombineEx
0x180016202  mov     r14d, eax
0x180016205  test    eax, eax
0x180016207  js      loc_180016322
0x18001620d  mov     r14d, 2A0h
0x180016213  mov     r8d, r14d; Size
0x180016216  xor     edx, edx; Val
0x180016218  lea     rcx, [rsp+350h+var_2E0]; void *
0x18001621d  call    memset_0
0x180016222  mov     rcx, [rbx+8]
0x180016226  lea     r9, [rsp+350h+var_2E0]
0x18001622b  mov     r8d, r14d
0x18001622e  mov     rdx, rsi
0x180016231  mov     rcx, [rcx+10h]
0x180016235  call    cs:__imp_WIMFindFirstImageFileEx
0x18001623b  mov     [rsp+350h+var_2F8], rax
0x180016240  test    rax, rax
0x180016243  jz      short loc_18001628F
0x180016245  mov     rcx, [rbp+250h+var_58]
0x18001624c  add     [r15], rcx
0x18001624f  mov     ecx, [rbp+250h+var_2C0]
0x180016252  mov     dword ptr [rsp+350h+var_310], ecx
0x180016256  mov     ecx, [rbp+250h+var_2C4]
0x180016259  mov     dword ptr [rsp+350h+var_310+4], ecx
0x18001625d  mov     rcx, [rsp+350h+var_310]
0x180016262  add     [r12], rcx
0x180016266  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001626a  cmp     rax, r14
0x18001626d  jz      short loc_180016279
0x18001626f  mov     rcx, rax
0x180016272  call    cs:__imp_WIMCloseHandle
0x180016278  nop
0x180016279  mov     rcx, rsi; void *
0x18001627c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016281  nop
0x180016282  mov     rcx, rdi; void *
0x180016285  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001628a  jmp     loc_18001611D
0x18001628f  call    cs:__imp_GetLastError
0x180016295  mov     r14d, 80070000h
0x18001629b  test    eax, eax
0x18001629d  jle     short loc_1800162A5
0x18001629f  movzx   eax, ax
0x1800162a2  or      eax, r14d
0x1800162a5  mov     [rsp+350h+var_328], eax
0x1800162a9  mov     dword ptr [rsp+350h+var_330], 0BBh
0x1800162b1  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800162b8  lea     r8, aElementGetasse; "Element::GetAssetSize"
0x1800162bf  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800162c6  mov     ebx, 3
0x1800162cb  mov     ecx, ebx
0x1800162cd  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800162d2  lea     rdx, aFailedToFindFi_0; "    Failed to find first payload path"
0x1800162d9  mov     ecx, ebx
0x1800162db  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800162e0  call    cs:__imp_GetLastError
0x1800162e6  mov     ebx, eax
0x1800162e8  test    eax, eax
0x1800162ea  jle     short loc_1800162F2
0x1800162ec  movzx   ebx, ax
0x1800162ef  or      ebx, r14d
0x1800162f2  mov     rcx, rsi; void *
0x1800162f5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800162fa  nop
0x1800162fb  mov     rcx, rdi; void *
0x1800162fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016303  nop
0x180016304  mov     rcx, [rsp+350h+var_320]
0x180016309  test    rcx, rcx
0x18001630c  jz      short loc_18001631B
0x18001630e  mov     rdx, [rcx]
0x180016311  mov     rax, [rdx+10h]
0x180016315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001631a  nop
0x18001631b  mov     eax, ebx
0x18001631d  jmp     loc_18001652C
0x180016322  mov     [rsp+350h+var_328], r14d
0x180016327  mov     dword ptr [rsp+350h+var_330], 0B6h
0x18001632f  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016336  lea     r8, aElementGetasse; "Element::GetAssetSize"
0x18001633d  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016344  mov     ebx, 3
0x180016349  mov     ecx, ebx
0x18001634b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016350  lea     rdx, aFailedToAssemb_9; "    Failed to assemble full payload pat"...
0x180016357  mov     ecx, ebx
0x180016359  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001635e  nop
0x18001635f  mov     rcx, rsi; void *
0x180016362  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016367  nop
0x180016368  mov     rcx, rdi; void *
0x18001636b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016370  nop
0x180016371  mov     rcx, [rsp+350h+var_320]
0x180016376  test    rcx, rcx
0x180016379  jz      short loc_180016388
0x18001637b  mov     rax, [rcx]
0x18001637e  mov     rax, [rax+10h]
0x180016382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016387  nop
0x180016388  mov     eax, r14d
0x18001638b  jmp     loc_18001652C
0x180016390  mov     [rsp+350h+var_328], 8007000Eh
0x180016398  mov     dword ptr [rsp+350h+var_330], 0B2h
0x1800163a0  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800163a7  lea     r8, aElementGetasse; "Element::GetAssetSize"
0x1800163ae  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800163b5  mov     ebx, 3
0x1800163ba  mov     ecx, ebx
0x1800163bc  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800163c1  lea     rdx, aFailedToAlloca_18; "    Failed to allocate spFullPayloadPat"...
0x1800163c8  mov     ecx, ebx
0x1800163ca  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800163cf  nop
0x1800163d0  mov     rcx, rdi; void *
0x1800163d3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800163d8  nop
0x1800163d9  mov     rcx, [rsp+350h+var_320]
0x1800163de  test    rcx, rcx
0x1800163e1  jz      loc_1800164AD
0x1800163e7  mov     rax, [rcx]
0x1800163ea  mov     rax, [rax+10h]
0x1800163ee  jmp     loc_1800164A7
0x1800163f3  mov     [rsp+350h+var_328], esi
0x1800163f7  mov     dword ptr [rsp+350h+var_330], 0ACh
0x1800163ff  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180016406  lea     r8, aElementGetasse; "Element::GetAssetSize"
0x18001640d  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180016414  mov     ebx, 3
0x180016419  mov     ecx, ebx
0x18001641b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016420  lea     rdx, aFailedToGetNex_0; "    Failed to get next payload path"
0x180016427  mov     ecx, ebx
0x180016429  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001642e  nop
0x18001642f  mov     rcx, rdi; void *
0x180016432  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016437  nop
0x180016438  mov     rcx, [rsp+350h+var_320]
0x18001643d  test    rcx, rcx
0x180016440  jz      short loc_18001644F
0x180016442  mov     rax, [rcx]
0x180016445  mov     rax, [rax+10h]
0x180016449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001644e  nop
0x18001644f  mov     eax, esi
0x180016451  jmp     loc_18001652C
0x180016456  mov     [rsp+350h+var_328], 8007000Eh
0x18001645e  mov     dword ptr [rsp+350h+var_330], 0A9h
0x180016466  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001646d  lea     r8, aElementGetasse; "Element::GetAssetSize"
0x180016474  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001647b  mov     ebx, 3
0x180016480  mov     ecx, ebx
0x180016482  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016487  lea     rdx, aFailedToAlloca_27; "    Failed to allocate spPayloadPath.ge"...
0x18001648e  mov     ecx, ebx
0x180016490  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016495  nop
0x180016496  mov     rcx, [rsp+350h+var_320]
0x18001649b  test    rcx, rcx
0x18001649e  jz      short loc_1800164AD
0x1800164a0  mov     rdx, [rcx]
0x1800164a3  mov     rax, [rdx+10h]
0x1800164a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164ac  nop
0x1800164ad  mov     eax, 8007000Eh
0x1800164b2  jmp     short loc_18001652C
0x1800164b4  cmp     edi, 80070103h
0x1800164ba  jnz     short loc_1800164D7
0x1800164bc  mov     rcx, [rsp+350h+var_320]
0x1800164c1  test    rcx, rcx
0x1800164c4  jz      short loc_1800164D3
0x1800164c6  mov     rax, [rcx]
0x1800164c9  mov     rax, [rax+10h]
0x1800164cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164d2  nop
0x1800164d3  xor     eax, eax
0x1800164d5  jmp     short loc_18001652C
0x1800164d7  mov     [rsp+350h+var_328], edi
0x1800164db  mov     dword ptr [rsp+350h+var_330], 0C8h
0x1800164e3  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800164ea  lea     r8, aElementGetasse; "Element::GetAssetSize"
0x1800164f1  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800164f8  mov     ebx, 3
0x1800164fd  mov     ecx, ebx
0x1800164ff  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016504  lea     rdx, aFailedToGetNex_3; "    Failed to get next payload length"
0x18001650b  mov     ecx, ebx
0x18001650d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180016512  nop
  ... truncated ...
```
