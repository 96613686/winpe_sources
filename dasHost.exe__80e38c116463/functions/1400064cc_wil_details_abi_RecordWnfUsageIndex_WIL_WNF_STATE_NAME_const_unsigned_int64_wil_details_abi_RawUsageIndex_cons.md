# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1400064cc`
- end: `0x1400068a4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140005bc8`

## callees

- `0x140001570`
- `0x140005718`
- `0x140005a80`
- `0x1400064cc`
- `0x140006ff4`
- `0x1400083ac`
- `0x1400089d8`
- `0x14001a7d0`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400065ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400065ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400065c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400065c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006838`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000686e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006838`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000686e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000682a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006860`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000682a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006860`

## string_xrefs

- `0x1400065a5`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v5; // r14
  wil::details_abi *v6; // r13
  unsigned __int64 v7; // r12
  char v8; // cl
  unsigned int v9; // edx
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // ebx
  unsigned int v15; // eax
  int v16; // ebx
  unsigned int v17; // esi
  __int64 v18; // r15
  int v19; // r9d
  char v20; // bl
  int updated; // eax
  int v22; // r9d
  void *v23; // rsi
  HANDLE ProcessHeap; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  __int64 *v27; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v28; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v29[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v31; // [rsp+64h] [rbp-9Ch]
  __int16 v32; // [rsp+66h] [rbp-9Ah]
  char v33; // [rsp+68h] [rbp-98h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  __int128 v36; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v38; // [rsp+98h] [rbp-68h]
  char v39; // [rsp+9Ah] [rbp-66h]
  __int64 v40; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v42; // [rsp+B0h] [rbp-50h] BYREF
  char v43; // [rsp+B2h] [rbp-4Eh]
  unsigned int v44; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v45; // [rsp+B8h] [rbp-48h]
  __int128 v46; // [rsp+C0h] [rbp-40h]
  __int16 v47; // [rsp+D0h] [rbp-30h] BYREF
  char v48; // [rsp+D2h] [rbp-2Eh]
  int v49; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v50; // [rsp+D8h] [rbp-28h]
  __int128 v51; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v53; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v54; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v55[2]; // [rsp+108h] [rbp+8h] BYREF
  char v56; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v57[13]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *v58; // [rsp+188h] [rbp+88h]
  _BYTE v59[4096]; // [rsp+190h] [rbp+90h] BYREF

  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v41 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v30[0] = *(_WORD *)a3;
    v30[1] = *(_WORD *)(a3 + 2);
    v31 = *(_BYTE *)(a3 + 4);
    v32 = v9;
    v33 = v8;
    if ( (_WORD)v9 )
    {
      v10 = v9;
      if ( v8 == 1 )
      {
        v10 = v9 + 2LL;
      }
      else if ( v8 == 2 )
      {
        v10 = v9 + 4LL;
      }
      v34 = v10;
    }
    else
    {
      v34 = 0;
    }
    v35 = 0;
    v36 = 0;
    lpMem = 0;
    v38 = 0;
    v39 = 0;
    v29[0] = 0;
    LODWORD(v28) = 4096;
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    if ( g_wil_details_pfnNtQueryWnfStateData )
      goto LABEL_14;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
      v27 = (__int64 *)v59;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v5, 0, 0, v29);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v28) = 0;
      v29[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v28;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v30, v59, v15, 0x1000u);
    if ( HIBYTE(v38) )
      break;
    v40 = 0;
    v57[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v57[1] = &v40;
    v57[2] = &v41;
    v57[3] = v30;
    v58 = (wil::details::in1diag3 *)v57;
    v55[1] = &v56;
    v28 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
    v42 = *(_WORD *)(a3 + 2);
    v43 = *(_BYTE *)(a3 + 4);
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = *(_WORD *)(a3 + 6);
    v48 = *(_BYTE *)(a3 + 8);
    v49 = 0;
    v50 = 0;
    v51 = 0;
LABEL_26:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v42,
              &v28,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      v17 = v44;
      if ( v44 )
      {
        v18 = *((_QWORD *)&v46 + 1);
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v47,
                  &v28,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v29[2] = v49;
          v52 = v50;
          v53 = *((_QWORD *)&v51 + 1);
          v54 = v45;
          v55[0] = v18;
          if ( !v58 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v27 = &v52;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, _QWORD *, __int64 *, __int64 *))(*(_QWORD *)v58 + 32LL))(
                  v58,
                  v55,
                  &v54,
                  &v53) )
          {
            if ( v58 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
            v20 = 0;
            goto LABEL_30;
          }
          if ( ++v16 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v58 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
    v20 = 1;
LABEL_30:
    if ( !(_BYTE)v38 )
      goto LABEL_38;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v5, v35, (int)v36 - (int)v35, v19, (_DWORD)v27, v29[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v5, v35, v36 - v35, v22, (_DWORD)v27, 0, 0);
LABEL_38:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v41 = v40;
      goto LABEL_39;
    }
    ++v7;
    v20 = 0;
LABEL_39:
    v23 = lpMem;
    lpMem = 0;
    if ( v23 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v23);
    }
    if ( v20 || v5 >= v6 || v7 >= 0x32 )
      return;
  }
  v25 = lpMem;
  lpMem = 0;
  if ( v25 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v25);
  }
}

```

## disassembly

```asm
0x1400064cc  mov     [rsp-8+arg_8], rbx
0x1400064d1  push    rbp
0x1400064d2  push    rsi
0x1400064d3  push    rdi
0x1400064d4  push    r12
0x1400064d6  push    r13
0x1400064d8  push    r14
0x1400064da  push    r15
0x1400064dc  lea     rbp, [rsp-10A0h]
0x1400064e4  mov     eax, 11A0h
0x1400064e9  call    _alloca_probe
0x1400064ee  sub     rsp, rax
0x1400064f1  mov     rax, cs:__security_cookie
0x1400064f8  xor     rax, rsp
0x1400064fb  mov     [rbp+10D0h+var_40], rax
0x140006502  mov     rdi, r8
0x140006505  mov     r14, rcx
0x140006508  lea     r13, [rcx+rdx*8]
0x14000650c  xor     r15d, r15d
0x14000650f  mov     r12d, r15d
0x140006512  mov     [rbp+10D0h+var_1128], r15
0x140006516  mov     cl, [rdi+8]
0x140006519  movzx   edx, word ptr [rdi+6]
0x14000651d  movzx   eax, word ptr [rdi]
0x140006520  mov     [rsp+11D0h+var_1170], ax
0x140006525  movzx   eax, word ptr [rdi+2]
0x140006529  mov     [rsp+11D0h+var_116E], ax
0x14000652e  mov     al, [rdi+4]
0x140006531  mov     [rsp+11D0h+var_116C], al
0x140006535  mov     [rsp+11D0h+var_116A], dx
0x14000653a  mov     [rsp+11D0h+var_1168], cl
0x14000653e  test    dx, dx
0x140006541  jz      short loc_140006560
0x140006543  mov     eax, edx
0x140006545  cmp     cl, 1
0x140006548  jnz     short loc_140006550
0x14000654a  add     rax, 2
0x14000654e  jmp     short loc_140006559
0x140006550  cmp     cl, 2
0x140006553  jnz     short loc_140006559
0x140006555  add     rax, 4
0x140006559  mov     [rsp+11D0h+var_1160], rax
0x14000655e  jmp     short loc_140006565
0x140006560  mov     [rsp+11D0h+var_1160], r15
0x140006565  mov     [rsp+11D0h+var_1158], r15
0x14000656a  xorps   xmm0, xmm0
0x14000656d  movdqa  [rbp+10D0h+var_1150], xmm0
0x140006572  mov     [rbp+10D0h+lpMem], r15
0x140006576  mov     [rbp+10D0h+var_1138], 0
0x14000657c  mov     [rbp+10D0h+var_1136], r15b
0x140006580  mov     [rsp+11D0h+var_1188], r15d
0x140006585  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x14000658d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140006594  test    rax, rax
0x140006597  jnz     short loc_1400065DC
0x140006599  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400065a0  test    rax, rax
0x1400065a3  jnz     short loc_1400065B9
0x1400065a5  lea     rcx, ModuleName; "ntdll.dll"
0x1400065ac  call    cs:__imp_GetModuleHandleW
0x1400065b2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400065b9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1400065c0  mov     rcx, rax; hModule
0x1400065c3  call    cs:__imp_GetProcAddress
0x1400065c9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1400065d0  test    rax, rax
0x1400065d3  jnz     short loc_1400065DC
0x1400065d5  mov     ebx, 0C0000139h
0x1400065da  jmp     short loc_140006606
0x1400065dc  lea     rcx, [rsp+11D0h+var_1190]
0x1400065e1  mov     [rsp+11D0h+var_11A8], rcx
0x1400065e6  lea     rcx, [rbp+10D0h+var_1040]
0x1400065ed  mov     [rsp+11D0h+var_11B0], rcx
0x1400065f2  lea     r9, [rsp+11D0h+var_1188]
0x1400065f7  xor     r8d, r8d
0x1400065fa  xor     edx, edx
0x1400065fc  mov     rcx, r14
0x1400065ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006604  mov     ebx, eax
0x140006606  mov     ecx, ebx; this
0x140006608  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000660d  test    ebx, ebx
0x14000660f  jz      short loc_14000661F
0x140006611  mov     eax, r15d
0x140006614  mov     dword ptr [rsp+11D0h+var_1190], eax
0x140006618  mov     [rsp+11D0h+var_1188], r15d
0x14000661d  jmp     short loc_140006623
0x14000661f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x140006623  mov     r8d, eax; unsigned __int64
0x140006626  mov     r9d, 1000h; unsigned __int64
0x14000662c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x140006633  lea     rcx, [rsp+11D0h+var_1170]; this
0x140006638  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x14000663d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x140006641  jnz     loc_140006853
0x140006647  mov     [rbp+10D0h+var_1130], r15
0x14000664b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x140006652  mov     [rbp+10D0h+var_10B0], rax
0x140006656  lea     rax, [rbp+10D0h+var_1130]
0x14000665a  mov     [rbp+10D0h+var_10A8], rax
0x14000665e  lea     rax, [rbp+10D0h+var_1128]
0x140006662  mov     [rbp+10D0h+var_10A0], rax
0x140006666  lea     rax, [rsp+11D0h+var_1170]
0x14000666b  mov     [rbp+10D0h+var_1098], rax
0x14000666f  lea     rax, [rbp+10D0h+var_10B0]
0x140006673  mov     [rbp+10D0h+var_1048], rax
0x14000667a  lea     rax, [rbp+10D0h+var_10B8]
0x14000667e  mov     [rbp+10D0h+var_10C0], rax
0x140006682  mov     rax, [rdi+18h]
0x140006686  add     rax, 0Ah
0x14000668a  mov     [rsp+11D0h+var_1190], rax
0x14000668f  movzx   eax, word ptr [rdi+2]
0x140006693  mov     [rbp+10D0h+var_1120], ax
0x140006697  mov     al, [rdi+4]
0x14000669a  mov     [rbp+10D0h+var_111E], al
0x14000669d  mov     [rbp+10D0h+var_111C], r15d
0x1400066a1  mov     [rbp+10D0h+var_1118], r15w
0x1400066a6  xorps   xmm0, xmm0
0x1400066a9  movdqu  [rbp+10D0h+var_1110], xmm0
0x1400066ae  movzx   eax, word ptr [rdi+6]
0x1400066b2  mov     [rbp+10D0h+var_1100], ax
0x1400066b6  mov     al, [rdi+8]
0x1400066b9  mov     [rbp+10D0h+var_10FE], al
0x1400066bc  mov     [rbp+10D0h+var_10FC], r15d
0x1400066c0  mov     [rbp+10D0h+var_10F8], r15w
0x1400066c5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1400066ca  jmp     loc_140006762
0x1400066cf  mov     ebx, r15d
0x1400066d2  mov     esi, [rbp+10D0h+var_111C]
0x1400066d5  test    esi, esi
0x1400066d7  jz      loc_140006762
0x1400066dd  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x1400066e1  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400066e5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1400066ea  lea     rcx, [rbp+10D0h+var_1100]; this
0x1400066ee  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400066f3  test    al, al
0x1400066f5  jz      short loc_14000675F
0x1400066f7  mov     eax, [rbp+10D0h+var_10FC]
0x1400066fa  mov     [rsp+11D0h+var_1180], eax
0x1400066fe  movzx   eax, [rbp+10D0h+var_10F8]
0x140006702  mov     [rbp+10D0h+var_10E0], rax
0x140006706  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14000670a  mov     [rbp+10D0h+var_10D8], rax
0x14000670e  movzx   eax, [rbp+10D0h+var_1118]
0x140006712  mov     [rbp+10D0h+var_10D0], rax
0x140006716  mov     [rbp+10D0h+var_10C8], r15
0x14000671a  mov     rcx, [rbp+10D0h+var_1048]; this
0x140006721  test    rcx, rcx
0x140006724  jz      loc_14000689E
0x14000672a  mov     rax, [rcx]
0x14000672d  lea     rdx, [rsp+11D0h+var_1180]
0x140006732  mov     [rsp+11D0h+var_11A8], rdx
0x140006737  lea     rdx, [rbp+10D0h+var_10E0]
0x14000673b  mov     [rsp+11D0h+var_11B0], rdx
0x140006740  lea     r9, [rbp+10D0h+var_10D8]
0x140006744  lea     r8, [rbp+10D0h+var_10D0]
0x140006748  lea     rdx, [rbp+10D0h+var_10C8]
0x14000674c  mov     rax, [rax+20h]
0x140006750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006755  test    al, al
0x140006757  jz      short loc_1400067CF
0x140006759  inc     ebx
0x14000675b  cmp     ebx, esi
0x14000675d  jb      short loc_1400066E1
0x14000675f  xor     r15d, r15d
0x140006762  mov     r8, [rdi+20h]; unsigned __int8 *
0x140006766  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000676b  lea     rcx, [rbp+10D0h+var_1120]; this
0x14000676f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140006774  test    al, al
0x140006776  jnz     loc_1400066CF
0x14000677c  mov     rcx, [rbp+10D0h+var_1048]
0x140006783  test    rcx, rcx
0x140006786  jz      short loc_140006794
0x140006788  mov     rax, [rcx]
0x14000678b  mov     rax, [rax+18h]
0x14000678f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006794  mov     bl, 1
0x140006796  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x14000679a  jz      short loc_140006811
0x14000679c  mov     eax, [rsp+11D0h+var_1188]
0x1400067a0  mov     rdx, [rsp+11D0h+var_1158]
0x1400067a5  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1400067a9  sub     r8d, edx
0x1400067ac  mov     [rsp+11D0h+var_11A0], 1
0x1400067b4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1400067b8  mov     rcx, r14
0x1400067bb  call    wil_details_NtUpdateWnfStateData
0x1400067c0  cmp     eax, 0C0000001h
0x1400067c5  jnz     short loc_1400067EF
0x1400067c7  inc     r12
0x1400067ca  mov     bl, r15b
0x1400067cd  jmp     short loc_14000681D
0x1400067cf  mov     rcx, [rbp+10D0h+var_1048]
0x1400067d6  xor     r15d, r15d
0x1400067d9  test    rcx, rcx
0x1400067dc  jz      short loc_1400067EA
0x1400067de  mov     rax, [rcx]
0x1400067e1  mov     rax, [rax+18h]
0x1400067e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067ea  mov     bl, r15b
0x1400067ed  jmp     short loc_140006796
0x1400067ef  test    eax, eax
0x1400067f1  jz      short loc_140006811
0x1400067f3  mov     rdx, [rsp+11D0h+var_1158]
0x1400067f8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1400067fc  sub     r8d, edx
0x1400067ff  mov     [rsp+11D0h+var_11A0], r15d
0x140006804  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x140006809  mov     rcx, r14
0x14000680c  call    wil_details_NtUpdateWnfStateData
0x140006811  add     r14, 8
0x140006815  mov     rax, [rbp+10D0h+var_1130]
0x140006819  mov     [rbp+10D0h+var_1128], rax
0x14000681d  mov     rsi, [rbp+10D0h+lpMem]
0x140006821  mov     [rbp+10D0h+lpMem], r15
0x140006825  test    rsi, rsi
0x140006828  jz      short loc_14000683E
0x14000682a  call    cs:__imp_GetProcessHeap
0x140006830  mov     rcx, rax; hHeap
0x140006833  mov     r8, rsi; lpMem
0x140006836  xor     edx, edx; dwFlags
0x140006838  call    cs:__imp_HeapFree
0x14000683e  test    bl, bl
0x140006840  jnz     short loc_140006874
0x140006842  cmp     r14, r13
0x140006845  jnb     short loc_140006874
0x140006847  cmp     r12, 32h ; '2'
0x14000684b  jb      loc_140006516
0x140006851  jmp     short loc_140006874
0x140006853  mov     rbx, [rbp+10D0h+lpMem]
0x140006857  mov     [rbp+10D0h+lpMem], r15
0x14000685b  test    rbx, rbx
0x14000685e  jz      short loc_140006874
0x140006860  call    cs:__imp_GetProcessHeap
0x140006866  mov     rcx, rax; hHeap
0x140006869  mov     r8, rbx; lpMem
0x14000686c  xor     edx, edx; dwFlags
0x14000686e  call    cs:__imp_HeapFree
0x140006874  mov     rcx, [rbp+10D0h+var_40]
0x14000687b  xor     rcx, rsp; StackCookie
0x14000687e  call    __security_check_cookie
0x140006883  mov     rbx, [rsp+11D0h+arg_8]
0x14000688b  add     rsp, 11A0h
0x140006892  pop     r15
0x140006894  pop     r14
0x140006896  pop     r13
0x140006898  pop     r12
0x14000689a  pop     rdi
0x14000689b  pop     rsi
0x14000689c  pop     rbp
0x14000689d  retn
0x14000689e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
