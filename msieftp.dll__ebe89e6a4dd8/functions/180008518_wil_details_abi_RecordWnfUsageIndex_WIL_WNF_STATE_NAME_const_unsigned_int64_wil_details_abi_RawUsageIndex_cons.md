# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180008518`
- end: `0x1800088e8`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `976`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180007a10`

## callees

- `0x180002240`
- `0x180007314`
- `0x180007910`
- `0x180008518`
- `0x180009488`
- `0x18000a3bc`
- `0x18000adf0`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800085f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800085f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000860f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000860f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000887c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000887c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000886e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000886e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088a4`

## string_xrefs

- `0x1800085f1`: `ntdll.dll`

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
0x180008518  mov     [rsp-8+arg_8], rbx
0x18000851d  push    rbp
0x18000851e  push    rsi
0x18000851f  push    rdi
0x180008520  push    r12
0x180008522  push    r13
0x180008524  push    r14
0x180008526  push    r15
0x180008528  lea     rbp, [rsp-10A0h]
0x180008530  mov     eax, 11A0h
0x180008535  call    _alloca_probe
0x18000853a  sub     rsp, rax
0x18000853d  mov     rax, cs:__security_cookie
0x180008544  xor     rax, rsp
0x180008547  mov     [rbp+10D0h+var_40], rax
0x18000854e  xor     r15d, r15d
0x180008551  lea     r13, [rcx+rdx*8]
0x180008555  mov     r12d, r15d
0x180008558  mov     [rbp+10D0h+var_1128], r15
0x18000855c  mov     rdi, r8
0x18000855f  mov     r14, rcx
0x180008562  movzx   eax, word ptr [rdi]
0x180008565  movzx   edx, word ptr [rdi+6]
0x180008569  mov     cl, [rdi+8]
0x18000856c  mov     [rsp+11D0h+var_1170], ax
0x180008571  movzx   eax, word ptr [rdi+2]
0x180008575  mov     [rsp+11D0h+var_116E], ax
0x18000857a  mov     al, [rdi+4]
0x18000857d  mov     [rsp+11D0h+var_116C], al
0x180008581  mov     [rsp+11D0h+var_116A], dx
0x180008586  mov     [rsp+11D0h+var_1168], cl
0x18000858a  test    dx, dx
0x18000858d  jz      short loc_1800085AC
0x18000858f  mov     eax, edx
0x180008591  cmp     cl, 1
0x180008594  jnz     short loc_18000859C
0x180008596  add     rax, 2
0x18000859a  jmp     short loc_1800085A5
0x18000859c  cmp     cl, 2
0x18000859f  jnz     short loc_1800085A5
0x1800085a1  add     rax, 4
0x1800085a5  mov     [rsp+11D0h+var_1160], rax
0x1800085aa  jmp     short loc_1800085B1
0x1800085ac  mov     [rsp+11D0h+var_1160], r15
0x1800085b1  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800085b8  xorps   xmm0, xmm0
0x1800085bb  mov     [rsp+11D0h+var_1158], r15
0x1800085c0  movdqa  [rbp+10D0h+var_1150], xmm0
0x1800085c5  mov     [rbp+10D0h+lpMem], r15
0x1800085c9  mov     [rbp+10D0h+var_1138], 0
0x1800085cf  mov     [rbp+10D0h+var_1136], r15b
0x1800085d3  mov     [rsp+11D0h+var_1188], r15d
0x1800085d8  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1800085e0  test    rax, rax
0x1800085e3  jnz     short loc_180008628
0x1800085e5  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800085ec  test    rax, rax
0x1800085ef  jnz     short loc_180008605
0x1800085f1  lea     rcx, ModuleName; "ntdll.dll"
0x1800085f8  call    cs:__imp_GetModuleHandleW
0x1800085fe  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008605  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000860c  mov     rcx, rax; hModule
0x18000860f  call    cs:__imp_GetProcAddress
0x180008615  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000861c  test    rax, rax
0x18000861f  jnz     short loc_180008628
0x180008621  mov     ebx, 0C0000139h
0x180008626  jmp     short loc_180008652
0x180008628  lea     rcx, [rsp+11D0h+var_1190]
0x18000862d  xor     r8d, r8d
0x180008630  mov     [rsp+11D0h+var_11A8], rcx
0x180008635  lea     r9, [rsp+11D0h+var_1188]
0x18000863a  lea     rcx, [rbp+10D0h+var_1040]
0x180008641  xor     edx, edx
0x180008643  mov     [rsp+11D0h+var_11B0], rcx
0x180008648  mov     rcx, r14
0x18000864b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008650  mov     ebx, eax
0x180008652  mov     ecx, ebx; this
0x180008654  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180008659  test    ebx, ebx
0x18000865b  jz      short loc_18000866B
0x18000865d  mov     eax, r15d
0x180008660  mov     [rsp+11D0h+var_1188], r15d
0x180008665  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180008669  jmp     short loc_18000866F
0x18000866b  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000866f  mov     r8d, eax; unsigned __int64
0x180008672  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180008679  mov     r9d, 1000h; unsigned __int64
0x18000867f  lea     rcx, [rsp+11D0h+var_1170]; this
0x180008684  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180008689  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000868d  jnz     loc_180008897
0x180008693  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000869a  mov     [rbp+10D0h+var_1130], r15
0x18000869e  mov     [rbp+10D0h+var_10B8], rax
0x1800086a2  xorps   xmm0, xmm0
0x1800086a5  lea     rax, [rbp+10D0h+var_1130]
0x1800086a9  mov     [rbp+10D0h+var_111C], r15d
0x1800086ad  mov     [rbp+10D0h+var_10B0], rax
0x1800086b1  lea     rax, [rbp+10D0h+var_1128]
0x1800086b5  mov     [rbp+10D0h+var_10A8], rax
0x1800086b9  lea     rax, [rsp+11D0h+var_1170]
0x1800086be  mov     [rbp+10D0h+var_10A0], rax
0x1800086c2  lea     rax, [rbp+10D0h+var_10B8]
0x1800086c6  mov     [rbp+10D0h+var_1050], rax
0x1800086cd  mov     rax, [rdi+18h]
0x1800086d1  add     rax, 0Ah
0x1800086d5  mov     [rbp+10D0h+var_1118], r15w
0x1800086da  mov     [rsp+11D0h+var_1190], rax
0x1800086df  movzx   eax, word ptr [rdi+2]
0x1800086e3  mov     [rbp+10D0h+var_1120], ax
0x1800086e7  mov     al, [rdi+4]
0x1800086ea  mov     [rbp+10D0h+var_111E], al
0x1800086ed  movzx   eax, word ptr [rdi+6]
0x1800086f1  mov     [rbp+10D0h+var_1100], ax
0x1800086f5  mov     al, [rdi+8]
0x1800086f8  mov     [rbp+10D0h+var_10FE], al
0x1800086fb  movdqu  [rbp+10D0h+var_1110], xmm0
0x180008700  mov     [rbp+10D0h+var_10FC], r15d
0x180008704  mov     [rbp+10D0h+var_10F8], r15w
0x180008709  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000870e  jmp     loc_1800087A6
0x180008713  mov     esi, [rbp+10D0h+var_111C]
0x180008716  mov     ebx, r15d
0x180008719  test    esi, esi
0x18000871b  jz      loc_1800087A6
0x180008721  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180008725  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008729  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000872e  lea     rcx, [rbp+10D0h+var_1100]; this
0x180008732  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008737  test    al, al
0x180008739  jz      short loc_1800087A3
0x18000873b  mov     eax, [rbp+10D0h+var_10FC]
0x18000873e  mov     rcx, [rbp+10D0h+var_1050]; this
0x180008745  mov     [rsp+11D0h+var_1180], eax
0x180008749  movzx   eax, [rbp+10D0h+var_10F8]
0x18000874d  mov     [rbp+10D0h+var_10E0], rax
0x180008751  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180008755  mov     [rbp+10D0h+var_10D8], rax
0x180008759  movzx   eax, [rbp+10D0h+var_1118]
0x18000875d  mov     [rbp+10D0h+var_10D0], rax
0x180008761  mov     [rbp+10D0h+var_10C8], r15
0x180008765  test    rcx, rcx
0x180008768  jz      loc_1800088E2
0x18000876e  mov     rax, [rcx]
0x180008771  lea     rdx, [rsp+11D0h+var_1180]
0x180008776  mov     [rsp+11D0h+var_11A8], rdx
0x18000877b  lea     r9, [rbp+10D0h+var_10D8]
0x18000877f  lea     rdx, [rbp+10D0h+var_10E0]
0x180008783  mov     [rsp+11D0h+var_11B0], rdx
0x180008788  lea     r8, [rbp+10D0h+var_10D0]
0x18000878c  mov     rax, [rax+20h]
0x180008790  lea     rdx, [rbp+10D0h+var_10C8]
0x180008794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008799  test    al, al
0x18000879b  jz      short loc_180008813
0x18000879d  inc     ebx
0x18000879f  cmp     ebx, esi
0x1800087a1  jb      short loc_180008725
0x1800087a3  xor     r15d, r15d
0x1800087a6  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800087aa  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800087af  lea     rcx, [rbp+10D0h+var_1120]; this
0x1800087b3  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800087b8  test    al, al
0x1800087ba  jnz     loc_180008713
0x1800087c0  mov     rcx, [rbp+10D0h+var_1050]
0x1800087c7  test    rcx, rcx
0x1800087ca  jz      short loc_1800087D8
0x1800087cc  mov     rax, [rcx]
0x1800087cf  mov     rax, [rax+18h]
0x1800087d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087d8  mov     bl, 1
0x1800087da  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x1800087de  jz      short loc_180008855
0x1800087e0  mov     rdx, [rsp+11D0h+var_1158]
0x1800087e5  mov     rcx, r14
0x1800087e8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800087ec  mov     eax, [rsp+11D0h+var_1188]
0x1800087f0  sub     r8d, edx
0x1800087f3  mov     [rsp+11D0h+var_11A0], 1
0x1800087fb  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800087ff  call    wil_details_NtUpdateWnfStateData
0x180008804  cmp     eax, 0C0000001h
0x180008809  jnz     short loc_180008833
0x18000880b  inc     r12
0x18000880e  mov     bl, r15b
0x180008811  jmp     short loc_180008861
0x180008813  mov     rcx, [rbp+10D0h+var_1050]
0x18000881a  xor     r15d, r15d
0x18000881d  test    rcx, rcx
0x180008820  jz      short loc_18000882E
0x180008822  mov     rax, [rcx]
0x180008825  mov     rax, [rax+18h]
0x180008829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000882e  mov     bl, r15b
0x180008831  jmp     short loc_1800087DA
0x180008833  test    eax, eax
0x180008835  jz      short loc_180008855
0x180008837  mov     rdx, [rsp+11D0h+var_1158]
0x18000883c  mov     rcx, r14
0x18000883f  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180008843  sub     r8d, edx
0x180008846  mov     [rsp+11D0h+var_11A0], r15d
0x18000884b  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180008850  call    wil_details_NtUpdateWnfStateData
0x180008855  mov     rax, [rbp+10D0h+var_1130]
0x180008859  add     r14, 8
0x18000885d  mov     [rbp+10D0h+var_1128], rax
0x180008861  mov     rsi, [rbp+10D0h+lpMem]
0x180008865  mov     [rbp+10D0h+lpMem], r15
0x180008869  test    rsi, rsi
0x18000886c  jz      short loc_180008882
0x18000886e  call    cs:__imp_GetProcessHeap
0x180008874  mov     r8, rsi; lpMem
0x180008877  xor     edx, edx; dwFlags
0x180008879  mov     rcx, rax; hHeap
0x18000887c  call    cs:__imp_HeapFree
0x180008882  test    bl, bl
0x180008884  jnz     short loc_1800088B8
0x180008886  cmp     r14, r13
0x180008889  jnb     short loc_1800088B8
0x18000888b  cmp     r12, 32h ; '2'
0x18000888f  jb      loc_180008562
0x180008895  jmp     short loc_1800088B8
0x180008897  mov     rbx, [rbp+10D0h+lpMem]
0x18000889b  mov     [rbp+10D0h+lpMem], r15
0x18000889f  test    rbx, rbx
0x1800088a2  jz      short loc_1800088B8
0x1800088a4  call    cs:__imp_GetProcessHeap
0x1800088aa  mov     r8, rbx; lpMem
0x1800088ad  xor     edx, edx; dwFlags
0x1800088af  mov     rcx, rax; hHeap
0x1800088b2  call    cs:__imp_HeapFree
0x1800088b8  mov     rcx, [rbp+10D0h+var_40]
0x1800088bf  xor     rcx, rsp; StackCookie
0x1800088c2  call    __security_check_cookie
0x1800088c7  mov     rbx, [rsp+11D0h+arg_8]
0x1800088cf  add     rsp, 11A0h
0x1800088d6  pop     r15
0x1800088d8  pop     r14
0x1800088da  pop     r13
0x1800088dc  pop     r12
0x1800088de  pop     rdi
0x1800088df  pop     rsi
0x1800088e0  pop     rbp
0x1800088e1  retn
0x1800088e2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
