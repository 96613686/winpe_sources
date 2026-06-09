# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800063d0`
- end: `0x1800067a7`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180005afc`

## callees

- `0x1800056b8`
- `0x180005a0c`
- `0x1800063d0`
- `0x180006b94`
- `0x180007edc`
- `0x180008460`
- `0x18001ca70`
- `0x18001cb00`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800064c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800064c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800064af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800064af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000673a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006771`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000673a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006771`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000672c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006763`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000672c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006763`

## string_xrefs

- `0x1800064a8`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v5; // r14
  wil::details_abi *v6; // r12
  unsigned __int64 v7; // r15
  char v8; // cl
  unsigned int v9; // edx
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // edi
  unsigned int v15; // eax
  int v16; // edi
  int v17; // r9d
  char v18; // di
  int updated; // eax
  int v20; // r9d
  void *v21; // rsi
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  __int64 *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v26; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v27[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v29; // [rsp+64h] [rbp-9Ch]
  __int16 v30; // [rsp+66h] [rbp-9Ah]
  char v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  __int128 v34; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v36; // [rsp+98h] [rbp-68h]
  char v37; // [rsp+9Ah] [rbp-66h]
  __int64 v38; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v40; // [rsp+B0h] [rbp-50h] BYREF
  char v41; // [rsp+B2h] [rbp-4Eh]
  unsigned int v42; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v43; // [rsp+B8h] [rbp-48h]
  __int128 v44; // [rsp+C0h] [rbp-40h]
  __int16 v45; // [rsp+D0h] [rbp-30h] BYREF
  char v46; // [rsp+D2h] [rbp-2Eh]
  int v47; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v48; // [rsp+D8h] [rbp-28h]
  __int128 v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v52; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v53[2]; // [rsp+108h] [rbp+8h] BYREF
  char v54; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v55[13]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *v56; // [rsp+188h] [rbp+88h]
  _BYTE v57[4096]; // [rsp+190h] [rbp+90h] BYREF

  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v39 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v28[0] = *(_WORD *)a3;
    v28[1] = *(_WORD *)(a3 + 2);
    v29 = *(_BYTE *)(a3 + 4);
    v30 = v9;
    v31 = v8;
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
      v32 = v10;
    }
    else
    {
      v32 = 0;
    }
    v33 = 0;
    v34 = 0;
    lpMem = 0;
    v36 = 0;
    v37 = 0;
    v27[0] = 0;
    LODWORD(v26) = 4096;
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
      v25 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v5, 0, 0, v27);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v26) = 0;
      v27[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v26;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v28, v57, v15, 0x1000u);
    if ( HIBYTE(v36) )
      break;
    v38 = 0;
    v55[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v55[1] = &v38;
    v55[2] = &v39;
    v55[3] = v28;
    v56 = (wil::details::in1diag3 *)v55;
    v53[1] = &v54;
    v26 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
    v40 = *(_WORD *)(a3 + 2);
    v41 = *(_BYTE *)(a3 + 4);
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = *(_WORD *)(a3 + 6);
    v46 = *(_BYTE *)(a3 + 8);
    v47 = 0;
    v48 = 0;
    v49 = 0;
LABEL_25:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v40,
              &v26,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      if ( v42 )
      {
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v45,
                  &v26,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v27[2] = v47;
          v50 = v48;
          v51 = *((_QWORD *)&v49 + 1);
          v52 = v43;
          v53[0] = *((_QWORD *)&v44 + 1);
          if ( !v56 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v25 = &v50;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, _QWORD *, __int64 *, __int64 *))(*(_QWORD *)v56 + 32LL))(
                  v56,
                  v53,
                  &v52,
                  &v51) )
          {
            if ( v56 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
            v18 = 0;
            goto LABEL_29;
          }
          if ( ++v16 >= v42 )
            goto LABEL_25;
        }
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
    v18 = 1;
LABEL_29:
    if ( !(_BYTE)v36 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v5, v33, (int)v34 - (int)v33, v17, (_DWORD)v25, v27[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v5, v33, v34 - v33, v20, (_DWORD)v25, 0, 0);
LABEL_37:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v39 = v38;
      goto LABEL_38;
    }
    ++v7;
    v18 = 0;
LABEL_38:
    v21 = lpMem;
    lpMem = 0;
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
    if ( v18 || v5 >= v6 || v7 >= 0x32 )
      return;
  }
  v23 = lpMem;
  lpMem = 0;
  if ( v23 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v23);
  }
}

```

## disassembly

```asm
0x1800063d0  mov     [rsp-8+arg_8], rbx
0x1800063d5  push    rbp
0x1800063d6  push    rsi
0x1800063d7  push    rdi
0x1800063d8  push    r12
0x1800063da  push    r13
0x1800063dc  push    r14
0x1800063de  push    r15
0x1800063e0  lea     rbp, [rsp-10A0h]
0x1800063e8  mov     eax, 11A0h
0x1800063ed  call    _alloca_probe
0x1800063f2  sub     rsp, rax
0x1800063f5  mov     rax, cs:__security_cookie
0x1800063fc  xor     rax, rsp
0x1800063ff  mov     [rbp+10D0h+var_40], rax
0x180006406  mov     rbx, r8
0x180006409  mov     r14, rcx
0x18000640c  lea     r12, [rcx+rdx*8]
0x180006410  xor     r13d, r13d
0x180006413  mov     r15d, r13d
0x180006416  mov     [rbp+10D0h+var_1128], r13
0x18000641a  mov     cl, [rbx+8]
0x18000641d  movzx   edx, word ptr [rbx+6]
0x180006421  movzx   eax, word ptr [rbx]
0x180006424  mov     [rsp+11D0h+var_1170], ax
0x180006429  movzx   eax, word ptr [rbx+2]
0x18000642d  mov     [rsp+11D0h+var_116E], ax
0x180006432  mov     al, [rbx+4]
0x180006435  mov     [rsp+11D0h+var_116C], al
0x180006439  mov     [rsp+11D0h+var_116A], dx
0x18000643e  mov     [rsp+11D0h+var_1168], cl
0x180006442  test    dx, dx
0x180006445  jz      short loc_180006464
0x180006447  mov     eax, edx
0x180006449  cmp     cl, 1
0x18000644c  jnz     short loc_180006454
0x18000644e  add     rax, 2
0x180006452  jmp     short loc_18000645D
0x180006454  cmp     cl, 2
0x180006457  jnz     short loc_18000645D
0x180006459  add     rax, 4
0x18000645d  mov     [rsp+11D0h+var_1160], rax
0x180006462  jmp     short loc_180006469
0x180006464  mov     [rsp+11D0h+var_1160], r13
0x180006469  mov     [rsp+11D0h+var_1158], r13
0x18000646e  xorps   xmm0, xmm0
0x180006471  movdqa  [rbp+10D0h+var_1150], xmm0
0x180006476  mov     [rbp+10D0h+lpMem], r13
0x18000647a  mov     [rbp+10D0h+var_1138], r13w
0x18000647f  mov     [rbp+10D0h+var_1136], r13b
0x180006483  mov     [rsp+11D0h+var_1188], r13d
0x180006488  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180006490  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180006497  test    rax, rax
0x18000649a  jnz     short loc_1800064DF
0x18000649c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800064a3  test    rax, rax
0x1800064a6  jnz     short loc_1800064BC
0x1800064a8  lea     rcx, ModuleName; "ntdll.dll"
0x1800064af  call    cs:__imp_GetModuleHandleW
0x1800064b5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800064bc  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800064c3  mov     rcx, rax; hModule
0x1800064c6  call    cs:__imp_GetProcAddress
0x1800064cc  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800064d3  test    rax, rax
0x1800064d6  jnz     short loc_1800064DF
0x1800064d8  mov     edi, 0C0000139h
0x1800064dd  jmp     short loc_180006509
0x1800064df  lea     rcx, [rsp+11D0h+var_1190]
0x1800064e4  mov     [rsp+11D0h+var_11A8], rcx
0x1800064e9  lea     rcx, [rbp+10D0h+var_1040]
0x1800064f0  mov     [rsp+11D0h+var_11B0], rcx
0x1800064f5  lea     r9, [rsp+11D0h+var_1188]
0x1800064fa  xor     r8d, r8d
0x1800064fd  xor     edx, edx
0x1800064ff  mov     rcx, r14
0x180006502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006507  mov     edi, eax
0x180006509  mov     ecx, edi; this
0x18000650b  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180006510  test    edi, edi
0x180006512  jz      short loc_180006522
0x180006514  mov     eax, r13d
0x180006517  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000651b  mov     [rsp+11D0h+var_1188], r13d
0x180006520  jmp     short loc_180006526
0x180006522  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180006526  mov     r8d, eax; unsigned __int64
0x180006529  mov     r9d, 1000h; unsigned __int64
0x18000652f  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180006536  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000653b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180006540  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x180006544  jnz     loc_180006756
0x18000654a  mov     [rbp+10D0h+var_1130], r13
0x18000654e  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180006555  mov     [rbp+10D0h+var_10B0], rax
0x180006559  lea     rax, [rbp+10D0h+var_1130]
0x18000655d  mov     [rbp+10D0h+var_10A8], rax
0x180006561  lea     rax, [rbp+10D0h+var_1128]
0x180006565  mov     [rbp+10D0h+var_10A0], rax
0x180006569  lea     rax, [rsp+11D0h+var_1170]
0x18000656e  mov     [rbp+10D0h+var_1098], rax
0x180006572  lea     rax, [rbp+10D0h+var_10B0]
0x180006576  mov     [rbp+10D0h+var_1048], rax
0x18000657d  lea     rax, [rbp+10D0h+var_10B8]
0x180006581  mov     [rbp+10D0h+var_10C0], rax
0x180006585  mov     rax, [rbx+18h]
0x180006589  add     rax, 0Ah
0x18000658d  mov     [rsp+11D0h+var_1190], rax
0x180006592  movzx   eax, word ptr [rbx+2]
0x180006596  mov     [rbp+10D0h+var_1120], ax
0x18000659a  mov     al, [rbx+4]
0x18000659d  mov     [rbp+10D0h+var_111E], al
0x1800065a0  mov     [rbp+10D0h+var_111C], r13d
0x1800065a4  mov     [rbp+10D0h+var_1118], r13w
0x1800065a9  xorps   xmm0, xmm0
0x1800065ac  movdqu  [rbp+10D0h+var_1110], xmm0
0x1800065b1  movzx   eax, word ptr [rbx+6]
0x1800065b5  mov     [rbp+10D0h+var_1100], ax
0x1800065b9  mov     al, [rbx+8]
0x1800065bc  mov     [rbp+10D0h+var_10FE], al
0x1800065bf  mov     [rbp+10D0h+var_10FC], r13d
0x1800065c3  mov     [rbp+10D0h+var_10F8], r13w
0x1800065c8  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800065cd  jmp     loc_180006666
0x1800065d2  mov     edi, r13d
0x1800065d5  cmp     [rbp+10D0h+var_111C], r13d
0x1800065d9  jbe     loc_180006666
0x1800065df  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800065e3  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800065e8  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800065ec  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800065f1  test    al, al
0x1800065f3  jz      short loc_180006666
0x1800065f5  mov     eax, [rbp+10D0h+var_10FC]
0x1800065f8  mov     [rsp+11D0h+var_1180], eax
0x1800065fc  movzx   eax, [rbp+10D0h+var_10F8]
0x180006600  mov     [rbp+10D0h+var_10E0], rax
0x180006604  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180006608  mov     [rbp+10D0h+var_10D8], rax
0x18000660c  movzx   eax, [rbp+10D0h+var_1118]
0x180006610  mov     [rbp+10D0h+var_10D0], rax
0x180006614  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x180006618  mov     [rbp+10D0h+var_10C8], rax
0x18000661c  mov     rcx, [rbp+10D0h+var_1048]; this
0x180006623  test    rcx, rcx
0x180006626  jz      loc_1800067A1
0x18000662c  mov     rax, [rcx]
0x18000662f  lea     rdx, [rsp+11D0h+var_1180]
0x180006634  mov     [rsp+11D0h+var_11A8], rdx
0x180006639  lea     rdx, [rbp+10D0h+var_10E0]
0x18000663d  mov     [rsp+11D0h+var_11B0], rdx
0x180006642  lea     r9, [rbp+10D0h+var_10D8]
0x180006646  lea     r8, [rbp+10D0h+var_10D0]
0x18000664a  lea     rdx, [rbp+10D0h+var_10C8]
0x18000664e  mov     rax, [rax+20h]
0x180006652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006657  test    al, al
0x180006659  jz      short loc_1800066D4
0x18000665b  inc     edi
0x18000665d  cmp     edi, [rbp+10D0h+var_111C]
0x180006660  jb      loc_1800065DF
0x180006666  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000666a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000666f  lea     rcx, [rbp+10D0h+var_1120]; this
0x180006673  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006678  test    al, al
0x18000667a  jnz     loc_1800065D2
0x180006680  mov     rcx, [rbp+10D0h+var_1048]
0x180006687  test    rcx, rcx
0x18000668a  jz      short loc_180006698
0x18000668c  mov     rax, [rcx]
0x18000668f  mov     rax, [rax+18h]
0x180006693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006698  mov     dil, 1
0x18000669b  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18000669f  jz      short loc_180006713
0x1800066a1  mov     eax, [rsp+11D0h+var_1188]
0x1800066a5  mov     rdx, [rsp+11D0h+var_1158]
0x1800066aa  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800066ae  sub     r8d, edx
0x1800066b1  mov     [rsp+11D0h+var_11A0], 1
0x1800066b9  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800066bd  mov     rcx, r14
0x1800066c0  call    wil_details_NtUpdateWnfStateData
0x1800066c5  cmp     eax, 0C0000001h
0x1800066ca  jnz     short loc_1800066F1
0x1800066cc  inc     r15
0x1800066cf  mov     dil, r13b
0x1800066d2  jmp     short loc_18000671F
0x1800066d4  mov     rcx, [rbp+10D0h+var_1048]
0x1800066db  test    rcx, rcx
0x1800066de  jz      short loc_1800066EC
0x1800066e0  mov     rax, [rcx]
0x1800066e3  mov     rax, [rax+18h]
0x1800066e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ec  mov     dil, r13b
0x1800066ef  jmp     short loc_18000669B
0x1800066f1  test    eax, eax
0x1800066f3  jz      short loc_180006713
0x1800066f5  mov     rdx, [rsp+11D0h+var_1158]
0x1800066fa  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800066fe  sub     r8d, edx
0x180006701  mov     [rsp+11D0h+var_11A0], r13d
0x180006706  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18000670b  mov     rcx, r14
0x18000670e  call    wil_details_NtUpdateWnfStateData
0x180006713  add     r14, 8
0x180006717  mov     rax, [rbp+10D0h+var_1130]
0x18000671b  mov     [rbp+10D0h+var_1128], rax
0x18000671f  mov     rsi, [rbp+10D0h+lpMem]
0x180006723  mov     [rbp+10D0h+lpMem], r13
0x180006727  test    rsi, rsi
0x18000672a  jz      short loc_180006740
0x18000672c  call    cs:__imp_GetProcessHeap
0x180006732  mov     rcx, rax; hHeap
0x180006735  mov     r8, rsi; lpMem
0x180006738  xor     edx, edx; dwFlags
0x18000673a  call    cs:__imp_HeapFree
0x180006740  test    dil, dil
0x180006743  jnz     short loc_180006777
0x180006745  cmp     r14, r12
0x180006748  jnb     short loc_180006777
0x18000674a  cmp     r15, 32h ; '2'
0x18000674e  jb      loc_18000641A
0x180006754  jmp     short loc_180006777
0x180006756  mov     rbx, [rbp+10D0h+lpMem]
0x18000675a  mov     [rbp+10D0h+lpMem], r13
0x18000675e  test    rbx, rbx
0x180006761  jz      short loc_180006777
0x180006763  call    cs:__imp_GetProcessHeap
0x180006769  mov     rcx, rax; hHeap
0x18000676c  mov     r8, rbx; lpMem
0x18000676f  xor     edx, edx; dwFlags
0x180006771  call    cs:__imp_HeapFree
0x180006777  mov     rcx, [rbp+10D0h+var_40]
0x18000677e  xor     rcx, rsp; StackCookie
0x180006781  call    __security_check_cookie
0x180006786  mov     rbx, [rsp+11D0h+arg_8]
0x18000678e  add     rsp, 11A0h
0x180006795  pop     r15
0x180006797  pop     r14
0x180006799  pop     r13
0x18000679b  pop     r12
0x18000679d  pop     rdi
0x18000679e  pop     rsi
0x18000679f  pop     rbp
0x1800067a0  retn
0x1800067a1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
