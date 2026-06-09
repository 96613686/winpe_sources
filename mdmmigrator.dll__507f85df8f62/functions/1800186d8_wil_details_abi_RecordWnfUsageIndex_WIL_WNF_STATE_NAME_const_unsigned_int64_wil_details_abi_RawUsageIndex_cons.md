# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800186d8`
- end: `0x180018aa8`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `976`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180017e34`

## callees

- `0x1800022e0`
- `0x18000714c`
- `0x180017a74`
- `0x180017d34`
- `0x1800186d8`
- `0x18001ba0c`
- `0x18001d34c`
- `0x18001ea10`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800187b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800187b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800187cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800187cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018a2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018a64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018a2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018a64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018a3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018a72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018a3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018a72`

## string_xrefs

- `0x1800187b1`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v4; // r13
  unsigned __int64 v5; // r12
  wil::details_abi *v7; // r14
  unsigned int v8; // edx
  char v9; // cl
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // rax
  unsigned int v17; // esi
  int v18; // ebx
  __int64 v19; // r15
  int v20; // r9d
  char v21; // bl
  int updated; // eax
  int v23; // r9d
  void *v24; // rsi
  HANDLE ProcessHeap; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  __int64 *v28; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v29; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v30[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v32; // [rsp+64h] [rbp-9Ch]
  __int16 v33; // [rsp+66h] [rbp-9Ah]
  char v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+78h] [rbp-88h]
  __int128 v37; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v39; // [rsp+98h] [rbp-68h]
  char v40; // [rsp+9Ah] [rbp-66h]
  __int64 v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v43; // [rsp+B0h] [rbp-50h] BYREF
  char v44; // [rsp+B2h] [rbp-4Eh]
  unsigned int v45; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v46; // [rsp+B8h] [rbp-48h]
  __int128 v47; // [rsp+C0h] [rbp-40h]
  __int16 v48; // [rsp+D0h] [rbp-30h] BYREF
  char v49; // [rsp+D2h] [rbp-2Eh]
  int v50; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v51; // [rsp+D8h] [rbp-28h]
  __int128 v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v54; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v55; // [rsp+100h] [rbp+0h] BYREF
  __int64 v56; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v57[13]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *v58; // [rsp+180h] [rbp+80h]
  _BYTE v59[4096]; // [rsp+190h] [rbp+90h] BYREF

  v4 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v5 = 0;
  v42 = 0;
  v7 = this;
  while ( 1 )
  {
    v8 = *(unsigned __int16 *)(a3 + 6);
    v9 = *(_BYTE *)(a3 + 8);
    v31[0] = *(_WORD *)a3;
    v31[1] = *(_WORD *)(a3 + 2);
    v32 = *(_BYTE *)(a3 + 4);
    v33 = v8;
    v34 = v9;
    if ( (_WORD)v8 )
    {
      v10 = v8;
      if ( v9 == 1 )
      {
        v10 = v8 + 2LL;
      }
      else if ( v9 == 2 )
      {
        v10 = v8 + 4LL;
      }
      v35 = v10;
    }
    else
    {
      v35 = 0;
    }
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    v36 = 0;
    v37 = 0;
    lpMem = 0;
    v39 = 0;
    v40 = 0;
    v30[0] = 0;
    LODWORD(v29) = 4096;
    if ( g_wil_details_pfnNtQueryWnfStateData )
      goto LABEL_14;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
    g_wil_details_pfnNtQueryWnfStateData = (__int64)ProcAddress;
    if ( ProcAddress )
    {
LABEL_14:
      v28 = (__int64 *)v59;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v7, 0, 0, v30);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      v30[0] = 0;
      LODWORD(v29) = 0;
    }
    else
    {
      v15 = (unsigned int)v29;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v31, v59, v15, 0x1000u);
    if ( HIBYTE(v39) )
      break;
    v41 = 0;
    v57[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v45 = 0;
    v57[1] = &v41;
    v57[2] = &v42;
    v57[3] = v31;
    v58 = (wil::details::in1diag3 *)v57;
    v16 = *(_QWORD *)(a3 + 24);
    v46 = 0;
    v29 = (unsigned __int8 *)(v16 + 10);
    v43 = *(_WORD *)(a3 + 2);
    v44 = *(_BYTE *)(a3 + 4);
    v48 = *(_WORD *)(a3 + 6);
    v49 = *(_BYTE *)(a3 + 8);
    v47 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
LABEL_26:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v43,
              &v29,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v17 = v45;
      v18 = 0;
      if ( v45 )
      {
        v19 = *((_QWORD *)&v47 + 1);
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v48,
                  &v29,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v30[2] = v50;
          v53 = v51;
          v54 = *((_QWORD *)&v52 + 1);
          v55 = v46;
          v56 = v19;
          if ( !v58 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v28 = &v53;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v58 + 32LL))(
                  v58,
                  &v56,
                  &v55,
                  &v54) )
          {
            if ( v58 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
            v21 = 0;
            goto LABEL_30;
          }
          if ( ++v18 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v58 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
    v21 = 1;
LABEL_30:
    if ( !(_BYTE)v39 )
      goto LABEL_38;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v7, v36, (int)v37 - (int)v36, v20, (_DWORD)v28, v30[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v7, v36, v37 - v36, v23, (_DWORD)v28, 0, 0);
LABEL_38:
      v7 = (wil::details_abi *)((char *)v7 + 8);
      v42 = v41;
      goto LABEL_39;
    }
    ++v5;
    v21 = 0;
LABEL_39:
    v24 = lpMem;
    lpMem = 0;
    if ( v24 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v24);
    }
    if ( v21 || v7 >= v4 || v5 >= 0x32 )
      return;
  }
  v26 = lpMem;
  lpMem = 0;
  if ( v26 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26);
  }
}

```

## disassembly

```asm
0x1800186d8  mov     [rsp-8+arg_8], rbx
0x1800186dd  push    rbp
0x1800186de  push    rsi
0x1800186df  push    rdi
0x1800186e0  push    r12
0x1800186e2  push    r13
0x1800186e4  push    r14
0x1800186e6  push    r15
0x1800186e8  lea     rbp, [rsp-10A0h]
0x1800186f0  mov     eax, 11A0h
0x1800186f5  call    _alloca_probe
0x1800186fa  sub     rsp, rax
0x1800186fd  mov     rax, cs:__security_cookie
0x180018704  xor     rax, rsp
0x180018707  mov     [rbp+10D0h+var_40], rax
0x18001870e  xor     r15d, r15d
0x180018711  lea     r13, [rcx+rdx*8]
0x180018715  mov     r12d, r15d
0x180018718  mov     [rbp+10D0h+var_1128], r15
0x18001871c  mov     rdi, r8
0x18001871f  mov     r14, rcx
0x180018722  movzx   eax, word ptr [rdi]
0x180018725  movzx   edx, word ptr [rdi+6]
0x180018729  mov     cl, [rdi+8]
0x18001872c  mov     [rsp+11D0h+var_1170], ax
0x180018731  movzx   eax, word ptr [rdi+2]
0x180018735  mov     [rsp+11D0h+var_116E], ax
0x18001873a  mov     al, [rdi+4]
0x18001873d  mov     [rsp+11D0h+var_116C], al
0x180018741  mov     [rsp+11D0h+var_116A], dx
0x180018746  mov     [rsp+11D0h+var_1168], cl
0x18001874a  test    dx, dx
0x18001874d  jz      short loc_18001876C
0x18001874f  mov     eax, edx
0x180018751  cmp     cl, 1
0x180018754  jnz     short loc_18001875C
0x180018756  add     rax, 2
0x18001875a  jmp     short loc_180018765
0x18001875c  cmp     cl, 2
0x18001875f  jnz     short loc_180018765
0x180018761  add     rax, 4
0x180018765  mov     [rsp+11D0h+var_1160], rax
0x18001876a  jmp     short loc_180018771
0x18001876c  mov     [rsp+11D0h+var_1160], r15
0x180018771  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180018778  xorps   xmm0, xmm0
0x18001877b  mov     [rsp+11D0h+var_1158], r15
0x180018780  movdqa  [rbp+10D0h+var_1150], xmm0
0x180018785  mov     [rbp+10D0h+lpMem], r15
0x180018789  mov     [rbp+10D0h+var_1138], 0
0x18001878f  mov     [rbp+10D0h+var_1136], r15b
0x180018793  mov     [rsp+11D0h+var_1188], r15d
0x180018798  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1800187a0  test    rax, rax
0x1800187a3  jnz     short loc_1800187E8
0x1800187a5  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800187ac  test    rax, rax
0x1800187af  jnz     short loc_1800187C5
0x1800187b1  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800187b8  call    cs:__imp_GetModuleHandleW
0x1800187be  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800187c5  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800187cc  mov     rcx, rax; hModule
0x1800187cf  call    cs:__imp_GetProcAddress
0x1800187d5  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800187dc  test    rax, rax
0x1800187df  jnz     short loc_1800187E8
0x1800187e1  mov     ebx, 0C0000139h
0x1800187e6  jmp     short loc_180018812
0x1800187e8  lea     rcx, [rsp+11D0h+var_1190]
0x1800187ed  xor     r8d, r8d
0x1800187f0  mov     [rsp+11D0h+var_11A8], rcx
0x1800187f5  lea     r9, [rsp+11D0h+var_1188]
0x1800187fa  lea     rcx, [rbp+10D0h+var_1040]
0x180018801  xor     edx, edx
0x180018803  mov     [rsp+11D0h+var_11B0], rcx
0x180018808  mov     rcx, r14
0x18001880b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018810  mov     ebx, eax
0x180018812  mov     ecx, ebx; this
0x180018814  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180018819  test    ebx, ebx
0x18001881b  jz      short loc_18001882B
0x18001881d  mov     eax, r15d
0x180018820  mov     [rsp+11D0h+var_1188], r15d
0x180018825  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180018829  jmp     short loc_18001882F
0x18001882b  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18001882f  mov     r8d, eax; unsigned __int64
0x180018832  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180018839  mov     r9d, 1000h; unsigned __int64
0x18001883f  lea     rcx, [rsp+11D0h+var_1170]; this
0x180018844  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180018849  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18001884d  jnz     loc_180018A57
0x180018853  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18001885a  mov     [rbp+10D0h+var_1130], r15
0x18001885e  mov     [rbp+10D0h+var_10B8], rax
0x180018862  xorps   xmm0, xmm0
0x180018865  lea     rax, [rbp+10D0h+var_1130]
0x180018869  mov     [rbp+10D0h+var_111C], r15d
0x18001886d  mov     [rbp+10D0h+var_10B0], rax
0x180018871  lea     rax, [rbp+10D0h+var_1128]
0x180018875  mov     [rbp+10D0h+var_10A8], rax
0x180018879  lea     rax, [rsp+11D0h+var_1170]
0x18001887e  mov     [rbp+10D0h+var_10A0], rax
0x180018882  lea     rax, [rbp+10D0h+var_10B8]
0x180018886  mov     [rbp+10D0h+var_1050], rax
0x18001888d  mov     rax, [rdi+18h]
0x180018891  add     rax, 0Ah
0x180018895  mov     [rbp+10D0h+var_1118], r15w
0x18001889a  mov     [rsp+11D0h+var_1190], rax
0x18001889f  movzx   eax, word ptr [rdi+2]
0x1800188a3  mov     [rbp+10D0h+var_1120], ax
0x1800188a7  mov     al, [rdi+4]
0x1800188aa  mov     [rbp+10D0h+var_111E], al
0x1800188ad  movzx   eax, word ptr [rdi+6]
0x1800188b1  mov     [rbp+10D0h+var_1100], ax
0x1800188b5  mov     al, [rdi+8]
0x1800188b8  mov     [rbp+10D0h+var_10FE], al
0x1800188bb  movdqu  [rbp+10D0h+var_1110], xmm0
0x1800188c0  mov     [rbp+10D0h+var_10FC], r15d
0x1800188c4  mov     [rbp+10D0h+var_10F8], r15w
0x1800188c9  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800188ce  jmp     loc_180018966
0x1800188d3  mov     esi, [rbp+10D0h+var_111C]
0x1800188d6  mov     ebx, r15d
0x1800188d9  test    esi, esi
0x1800188db  jz      loc_180018966
0x1800188e1  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x1800188e5  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800188e9  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800188ee  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800188f2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800188f7  test    al, al
0x1800188f9  jz      short loc_180018963
0x1800188fb  mov     eax, [rbp+10D0h+var_10FC]
0x1800188fe  mov     rcx, [rbp+10D0h+var_1050]; this
0x180018905  mov     [rsp+11D0h+var_1180], eax
0x180018909  movzx   eax, [rbp+10D0h+var_10F8]
0x18001890d  mov     [rbp+10D0h+var_10E0], rax
0x180018911  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180018915  mov     [rbp+10D0h+var_10D8], rax
0x180018919  movzx   eax, [rbp+10D0h+var_1118]
0x18001891d  mov     [rbp+10D0h+var_10D0], rax
0x180018921  mov     [rbp+10D0h+var_10C8], r15
0x180018925  test    rcx, rcx
0x180018928  jz      loc_180018AA2
0x18001892e  mov     rax, [rcx]
0x180018931  lea     rdx, [rsp+11D0h+var_1180]
0x180018936  mov     [rsp+11D0h+var_11A8], rdx
0x18001893b  lea     r9, [rbp+10D0h+var_10D8]
0x18001893f  lea     rdx, [rbp+10D0h+var_10E0]
0x180018943  mov     [rsp+11D0h+var_11B0], rdx
0x180018948  lea     r8, [rbp+10D0h+var_10D0]
0x18001894c  mov     rax, [rax+20h]
0x180018950  lea     rdx, [rbp+10D0h+var_10C8]
0x180018954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018959  test    al, al
0x18001895b  jz      short loc_1800189D3
0x18001895d  inc     ebx
0x18001895f  cmp     ebx, esi
0x180018961  jb      short loc_1800188E5
0x180018963  xor     r15d, r15d
0x180018966  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001896a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18001896f  lea     rcx, [rbp+10D0h+var_1120]; this
0x180018973  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180018978  test    al, al
0x18001897a  jnz     loc_1800188D3
0x180018980  mov     rcx, [rbp+10D0h+var_1050]
0x180018987  test    rcx, rcx
0x18001898a  jz      short loc_180018998
0x18001898c  mov     rax, [rcx]
0x18001898f  mov     rax, [rax+18h]
0x180018993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018998  mov     bl, 1
0x18001899a  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18001899e  jz      short loc_180018A15
0x1800189a0  mov     rdx, [rsp+11D0h+var_1158]
0x1800189a5  mov     rcx, r14
0x1800189a8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800189ac  mov     eax, [rsp+11D0h+var_1188]
0x1800189b0  sub     r8d, edx
0x1800189b3  mov     [rsp+11D0h+var_11A0], 1
0x1800189bb  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800189bf  call    wil_details_NtUpdateWnfStateData
0x1800189c4  cmp     eax, 0C0000001h
0x1800189c9  jnz     short loc_1800189F3
0x1800189cb  inc     r12
0x1800189ce  mov     bl, r15b
0x1800189d1  jmp     short loc_180018A21
0x1800189d3  mov     rcx, [rbp+10D0h+var_1050]
0x1800189da  xor     r15d, r15d
0x1800189dd  test    rcx, rcx
0x1800189e0  jz      short loc_1800189EE
0x1800189e2  mov     rax, [rcx]
0x1800189e5  mov     rax, [rax+18h]
0x1800189e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189ee  mov     bl, r15b
0x1800189f1  jmp     short loc_18001899A
0x1800189f3  test    eax, eax
0x1800189f5  jz      short loc_180018A15
0x1800189f7  mov     rdx, [rsp+11D0h+var_1158]
0x1800189fc  mov     rcx, r14
0x1800189ff  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180018a03  sub     r8d, edx
0x180018a06  mov     [rsp+11D0h+var_11A0], r15d
0x180018a0b  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180018a10  call    wil_details_NtUpdateWnfStateData
0x180018a15  mov     rax, [rbp+10D0h+var_1130]
0x180018a19  add     r14, 8
0x180018a1d  mov     [rbp+10D0h+var_1128], rax
0x180018a21  mov     rsi, [rbp+10D0h+lpMem]
0x180018a25  mov     [rbp+10D0h+lpMem], r15
0x180018a29  test    rsi, rsi
0x180018a2c  jz      short loc_180018A42
0x180018a2e  call    cs:__imp_GetProcessHeap
0x180018a34  mov     r8, rsi; lpMem
0x180018a37  xor     edx, edx; dwFlags
0x180018a39  mov     rcx, rax; hHeap
0x180018a3c  call    cs:__imp_HeapFree
0x180018a42  test    bl, bl
0x180018a44  jnz     short loc_180018A78
0x180018a46  cmp     r14, r13
0x180018a49  jnb     short loc_180018A78
0x180018a4b  cmp     r12, 32h ; '2'
0x180018a4f  jb      loc_180018722
0x180018a55  jmp     short loc_180018A78
0x180018a57  mov     rbx, [rbp+10D0h+lpMem]
0x180018a5b  mov     [rbp+10D0h+lpMem], r15
0x180018a5f  test    rbx, rbx
0x180018a62  jz      short loc_180018A78
0x180018a64  call    cs:__imp_GetProcessHeap
0x180018a6a  mov     r8, rbx; lpMem
0x180018a6d  xor     edx, edx; dwFlags
0x180018a6f  mov     rcx, rax; hHeap
0x180018a72  call    cs:__imp_HeapFree
0x180018a78  mov     rcx, [rbp+10D0h+var_40]
0x180018a7f  xor     rcx, rsp; StackCookie
0x180018a82  call    __security_check_cookie
0x180018a87  mov     rbx, [rsp+11D0h+arg_8]
0x180018a8f  add     rsp, 11A0h
0x180018a96  pop     r15
0x180018a98  pop     r14
0x180018a9a  pop     r13
0x180018a9c  pop     r12
0x180018a9e  pop     rdi
0x180018a9f  pop     rsi
0x180018aa0  pop     rbp
0x180018aa1  retn
0x180018aa2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
