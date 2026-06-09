# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180007418`
- end: `0x1800077e8`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `976`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180006918`

## callees

- `0x180001670`
- `0x180006418`
- `0x180006818`
- `0x180007418`
- `0x180007dd8`
- `0x180008c7c`
- `0x180009490`
- `0x18003acd0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000777c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000777c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000776e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000776e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000750f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000750f`

## string_xrefs

- `0x1800074f1`: `ntdll.dll`

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
  __int64 v20; // r9
  char v21; // bl
  int updated; // eax
  __int64 v23; // r9
  void *v24; // rsi
  HANDLE ProcessHeap; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  __int64 *v28; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v28 = (__int64 *)v59;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v7, 0, 0, v30);
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
    updated = wil_details_NtUpdateWnfStateData((__int64)v7, v36, (int)v37 - (int)v36, v20, (int)v28, v30[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v7, v36, v37 - v36, v23, (int)v28, 0, 0);
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
0x180007418  mov     [rsp-8+arg_8], rbx
0x18000741d  push    rbp
0x18000741e  push    rsi
0x18000741f  push    rdi
0x180007420  push    r12
0x180007422  push    r13
0x180007424  push    r14
0x180007426  push    r15
0x180007428  lea     rbp, [rsp-10A0h]
0x180007430  mov     eax, 11A0h
0x180007435  call    _alloca_probe
0x18000743a  sub     rsp, rax
0x18000743d  mov     rax, cs:__security_cookie
0x180007444  xor     rax, rsp
0x180007447  mov     [rbp+10D0h+var_40], rax
0x18000744e  xor     r15d, r15d
0x180007451  lea     r13, [rcx+rdx*8]
0x180007455  mov     r12d, r15d
0x180007458  mov     [rbp+10D0h+var_1128], r15
0x18000745c  mov     rdi, r8
0x18000745f  mov     r14, rcx
0x180007462  movzx   eax, word ptr [rdi]
0x180007465  movzx   edx, word ptr [rdi+6]
0x180007469  mov     cl, [rdi+8]
0x18000746c  mov     [rsp+11D0h+var_1170], ax
0x180007471  movzx   eax, word ptr [rdi+2]
0x180007475  mov     [rsp+11D0h+var_116E], ax
0x18000747a  mov     al, [rdi+4]
0x18000747d  mov     [rsp+11D0h+var_116C], al
0x180007481  mov     [rsp+11D0h+var_116A], dx
0x180007486  mov     [rsp+11D0h+var_1168], cl
0x18000748a  test    dx, dx
0x18000748d  jz      short loc_1800074AC
0x18000748f  mov     eax, edx
0x180007491  cmp     cl, 1
0x180007494  jnz     short loc_18000749C
0x180007496  add     rax, 2
0x18000749a  jmp     short loc_1800074A5
0x18000749c  cmp     cl, 2
0x18000749f  jnz     short loc_1800074A5
0x1800074a1  add     rax, 4
0x1800074a5  mov     [rsp+11D0h+var_1160], rax
0x1800074aa  jmp     short loc_1800074B1
0x1800074ac  mov     [rsp+11D0h+var_1160], r15
0x1800074b1  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800074b8  xorps   xmm0, xmm0
0x1800074bb  mov     [rsp+11D0h+var_1158], r15
0x1800074c0  movdqa  [rbp+10D0h+var_1150], xmm0
0x1800074c5  mov     [rbp+10D0h+lpMem], r15
0x1800074c9  mov     [rbp+10D0h+var_1138], 0
0x1800074cf  mov     [rbp+10D0h+var_1136], r15b
0x1800074d3  mov     [rsp+11D0h+var_1188], r15d
0x1800074d8  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1800074e0  test    rax, rax
0x1800074e3  jnz     short loc_180007528
0x1800074e5  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800074ec  test    rax, rax
0x1800074ef  jnz     short loc_180007505
0x1800074f1  lea     rcx, ModuleName; "ntdll.dll"
0x1800074f8  call    cs:__imp_GetModuleHandleW
0x1800074fe  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007505  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000750c  mov     rcx, rax; hModule
0x18000750f  call    cs:__imp_GetProcAddress
0x180007515  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000751c  test    rax, rax
0x18000751f  jnz     short loc_180007528
0x180007521  mov     ebx, 0C0000139h
0x180007526  jmp     short loc_180007552
0x180007528  lea     rcx, [rsp+11D0h+var_1190]
0x18000752d  xor     r8d, r8d
0x180007530  mov     [rsp+11D0h+var_11A8], rcx
0x180007535  lea     r9, [rsp+11D0h+var_1188]
0x18000753a  lea     rcx, [rbp+10D0h+var_1040]
0x180007541  xor     edx, edx
0x180007543  mov     [rsp+11D0h+var_11B0], rcx
0x180007548  mov     rcx, r14
0x18000754b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007550  mov     ebx, eax
0x180007552  mov     ecx, ebx; this
0x180007554  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180007559  test    ebx, ebx
0x18000755b  jz      short loc_18000756B
0x18000755d  mov     eax, r15d
0x180007560  mov     [rsp+11D0h+var_1188], r15d
0x180007565  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180007569  jmp     short loc_18000756F
0x18000756b  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000756f  mov     r8d, eax; unsigned __int64
0x180007572  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180007579  mov     r9d, 1000h; unsigned __int64
0x18000757f  lea     rcx, [rsp+11D0h+var_1170]; this
0x180007584  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180007589  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000758d  jnz     loc_180007797
0x180007593  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000759a  mov     [rbp+10D0h+var_1130], r15
0x18000759e  mov     [rbp+10D0h+var_10B8], rax
0x1800075a2  xorps   xmm0, xmm0
0x1800075a5  lea     rax, [rbp+10D0h+var_1130]
0x1800075a9  mov     [rbp+10D0h+var_111C], r15d
0x1800075ad  mov     [rbp+10D0h+var_10B0], rax
0x1800075b1  lea     rax, [rbp+10D0h+var_1128]
0x1800075b5  mov     [rbp+10D0h+var_10A8], rax
0x1800075b9  lea     rax, [rsp+11D0h+var_1170]
0x1800075be  mov     [rbp+10D0h+var_10A0], rax
0x1800075c2  lea     rax, [rbp+10D0h+var_10B8]
0x1800075c6  mov     [rbp+10D0h+var_1050], rax
0x1800075cd  mov     rax, [rdi+18h]
0x1800075d1  add     rax, 0Ah
0x1800075d5  mov     [rbp+10D0h+var_1118], r15w
0x1800075da  mov     [rsp+11D0h+var_1190], rax
0x1800075df  movzx   eax, word ptr [rdi+2]
0x1800075e3  mov     [rbp+10D0h+var_1120], ax
0x1800075e7  mov     al, [rdi+4]
0x1800075ea  mov     [rbp+10D0h+var_111E], al
0x1800075ed  movzx   eax, word ptr [rdi+6]
0x1800075f1  mov     [rbp+10D0h+var_1100], ax
0x1800075f5  mov     al, [rdi+8]
0x1800075f8  mov     [rbp+10D0h+var_10FE], al
0x1800075fb  movdqu  [rbp+10D0h+var_1110], xmm0
0x180007600  mov     [rbp+10D0h+var_10FC], r15d
0x180007604  mov     [rbp+10D0h+var_10F8], r15w
0x180007609  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000760e  jmp     loc_1800076A6
0x180007613  mov     esi, [rbp+10D0h+var_111C]
0x180007616  mov     ebx, r15d
0x180007619  test    esi, esi
0x18000761b  jz      loc_1800076A6
0x180007621  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180007625  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007629  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000762e  lea     rcx, [rbp+10D0h+var_1100]; this
0x180007632  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007637  test    al, al
0x180007639  jz      short loc_1800076A3
0x18000763b  mov     eax, [rbp+10D0h+var_10FC]
0x18000763e  mov     rcx, [rbp+10D0h+var_1050]; this
0x180007645  mov     [rsp+11D0h+var_1180], eax
0x180007649  movzx   eax, [rbp+10D0h+var_10F8]
0x18000764d  mov     [rbp+10D0h+var_10E0], rax
0x180007651  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180007655  mov     [rbp+10D0h+var_10D8], rax
0x180007659  movzx   eax, [rbp+10D0h+var_1118]
0x18000765d  mov     [rbp+10D0h+var_10D0], rax
0x180007661  mov     [rbp+10D0h+var_10C8], r15
0x180007665  test    rcx, rcx
0x180007668  jz      loc_1800077E2
0x18000766e  mov     rax, [rcx]
0x180007671  lea     rdx, [rsp+11D0h+var_1180]
0x180007676  mov     [rsp+11D0h+var_11A8], rdx
0x18000767b  lea     r9, [rbp+10D0h+var_10D8]
0x18000767f  lea     rdx, [rbp+10D0h+var_10E0]
0x180007683  mov     [rsp+11D0h+var_11B0], rdx
0x180007688  lea     r8, [rbp+10D0h+var_10D0]
0x18000768c  mov     rax, [rax+20h]
0x180007690  lea     rdx, [rbp+10D0h+var_10C8]
0x180007694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007699  test    al, al
0x18000769b  jz      short loc_180007713
0x18000769d  inc     ebx
0x18000769f  cmp     ebx, esi
0x1800076a1  jb      short loc_180007625
0x1800076a3  xor     r15d, r15d
0x1800076a6  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800076aa  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800076af  lea     rcx, [rbp+10D0h+var_1120]; this
0x1800076b3  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800076b8  test    al, al
0x1800076ba  jnz     loc_180007613
0x1800076c0  mov     rcx, [rbp+10D0h+var_1050]
0x1800076c7  test    rcx, rcx
0x1800076ca  jz      short loc_1800076D8
0x1800076cc  mov     rax, [rcx]
0x1800076cf  mov     rax, [rax+18h]
0x1800076d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076d8  mov     bl, 1
0x1800076da  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x1800076de  jz      short loc_180007755
0x1800076e0  mov     rdx, [rsp+11D0h+var_1158]
0x1800076e5  mov     rcx, r14
0x1800076e8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800076ec  mov     eax, [rsp+11D0h+var_1188]
0x1800076f0  sub     r8d, edx
0x1800076f3  mov     [rsp+11D0h+var_11A0], 1
0x1800076fb  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800076ff  call    wil_details_NtUpdateWnfStateData
0x180007704  cmp     eax, 0C0000001h
0x180007709  jnz     short loc_180007733
0x18000770b  inc     r12
0x18000770e  mov     bl, r15b
0x180007711  jmp     short loc_180007761
0x180007713  mov     rcx, [rbp+10D0h+var_1050]
0x18000771a  xor     r15d, r15d
0x18000771d  test    rcx, rcx
0x180007720  jz      short loc_18000772E
0x180007722  mov     rax, [rcx]
0x180007725  mov     rax, [rax+18h]
0x180007729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000772e  mov     bl, r15b
0x180007731  jmp     short loc_1800076DA
0x180007733  test    eax, eax
0x180007735  jz      short loc_180007755
0x180007737  mov     rdx, [rsp+11D0h+var_1158]
0x18000773c  mov     rcx, r14
0x18000773f  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180007743  sub     r8d, edx
0x180007746  mov     [rsp+11D0h+var_11A0], r15d
0x18000774b  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180007750  call    wil_details_NtUpdateWnfStateData
0x180007755  mov     rax, [rbp+10D0h+var_1130]
0x180007759  add     r14, 8
0x18000775d  mov     [rbp+10D0h+var_1128], rax
0x180007761  mov     rsi, [rbp+10D0h+lpMem]
0x180007765  mov     [rbp+10D0h+lpMem], r15
0x180007769  test    rsi, rsi
0x18000776c  jz      short loc_180007782
0x18000776e  call    cs:__imp_GetProcessHeap
0x180007774  mov     r8, rsi; lpMem
0x180007777  xor     edx, edx; dwFlags
0x180007779  mov     rcx, rax; hHeap
0x18000777c  call    cs:__imp_HeapFree
0x180007782  test    bl, bl
0x180007784  jnz     short loc_1800077B8
0x180007786  cmp     r14, r13
0x180007789  jnb     short loc_1800077B8
0x18000778b  cmp     r12, 32h ; '2'
0x18000778f  jb      loc_180007462
0x180007795  jmp     short loc_1800077B8
0x180007797  mov     rbx, [rbp+10D0h+lpMem]
0x18000779b  mov     [rbp+10D0h+lpMem], r15
0x18000779f  test    rbx, rbx
0x1800077a2  jz      short loc_1800077B8
0x1800077a4  call    cs:__imp_GetProcessHeap
0x1800077aa  mov     r8, rbx; lpMem
0x1800077ad  xor     edx, edx; dwFlags
0x1800077af  mov     rcx, rax; hHeap
0x1800077b2  call    cs:__imp_HeapFree
0x1800077b8  mov     rcx, [rbp+10D0h+var_40]
0x1800077bf  xor     rcx, rsp; StackCookie
0x1800077c2  call    __security_check_cookie
0x1800077c7  mov     rbx, [rsp+11D0h+arg_8]
0x1800077cf  add     rsp, 11A0h
0x1800077d6  pop     r15
0x1800077d8  pop     r14
0x1800077da  pop     r13
0x1800077dc  pop     r12
0x1800077de  pop     rdi
0x1800077df  pop     rsi
0x1800077e0  pop     rbp
0x1800077e1  retn
0x1800077e2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
