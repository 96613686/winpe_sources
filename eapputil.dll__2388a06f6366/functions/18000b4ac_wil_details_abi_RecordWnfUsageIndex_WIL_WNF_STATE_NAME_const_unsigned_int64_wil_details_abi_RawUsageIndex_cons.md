# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000b4ac`
- end: `0x18000b884`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000aa00`

## callees

- `0x1800021d0`
- `0x180007a2c`
- `0x18000a45c`
- `0x18000a900`
- `0x18000b4ac`
- `0x18000baac`
- `0x18000cd00`
- `0x180030510`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b58c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b58c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b5a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b5a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b80a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b840`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b80a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b840`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b818`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b84e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b818`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b84e`

## string_xrefs

- `0x18000b585`: `ntdll.dll`

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
0x18000b4ac  mov     [rsp-8+arg_8], rbx
0x18000b4b1  push    rbp
0x18000b4b2  push    rsi
0x18000b4b3  push    rdi
0x18000b4b4  push    r12
0x18000b4b6  push    r13
0x18000b4b8  push    r14
0x18000b4ba  push    r15
0x18000b4bc  lea     rbp, [rsp-10A0h]
0x18000b4c4  mov     eax, 11A0h
0x18000b4c9  call    _alloca_probe
0x18000b4ce  sub     rsp, rax
0x18000b4d1  mov     rax, cs:__security_cookie
0x18000b4d8  xor     rax, rsp
0x18000b4db  mov     [rbp+10D0h+var_40], rax
0x18000b4e2  mov     rdi, r8
0x18000b4e5  mov     r14, rcx
0x18000b4e8  lea     r13, [rcx+rdx*8]
0x18000b4ec  xor     r15d, r15d
0x18000b4ef  mov     r12d, r15d
0x18000b4f2  mov     [rbp+10D0h+var_1128], r15
0x18000b4f6  mov     cl, [rdi+8]
0x18000b4f9  movzx   edx, word ptr [rdi+6]
0x18000b4fd  movzx   eax, word ptr [rdi]
0x18000b500  mov     [rsp+11D0h+var_1170], ax
0x18000b505  movzx   eax, word ptr [rdi+2]
0x18000b509  mov     [rsp+11D0h+var_116E], ax
0x18000b50e  mov     al, [rdi+4]
0x18000b511  mov     [rsp+11D0h+var_116C], al
0x18000b515  mov     [rsp+11D0h+var_116A], dx
0x18000b51a  mov     [rsp+11D0h+var_1168], cl
0x18000b51e  test    dx, dx
0x18000b521  jz      short loc_18000B540
0x18000b523  mov     eax, edx
0x18000b525  cmp     cl, 1
0x18000b528  jnz     short loc_18000B530
0x18000b52a  add     rax, 2
0x18000b52e  jmp     short loc_18000B539
0x18000b530  cmp     cl, 2
0x18000b533  jnz     short loc_18000B539
0x18000b535  add     rax, 4
0x18000b539  mov     [rsp+11D0h+var_1160], rax
0x18000b53e  jmp     short loc_18000B545
0x18000b540  mov     [rsp+11D0h+var_1160], r15
0x18000b545  mov     [rsp+11D0h+var_1158], r15
0x18000b54a  xorps   xmm0, xmm0
0x18000b54d  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000b552  mov     [rbp+10D0h+lpMem], r15
0x18000b556  mov     [rbp+10D0h+var_1138], 0
0x18000b55c  mov     [rbp+10D0h+var_1136], r15b
0x18000b560  mov     [rsp+11D0h+var_1188], r15d
0x18000b565  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000b56d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b574  test    rax, rax
0x18000b577  jnz     short loc_18000B5BC
0x18000b579  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b580  test    rax, rax
0x18000b583  jnz     short loc_18000B599
0x18000b585  lea     rcx, ModuleName; "ntdll.dll"
0x18000b58c  call    cs:__imp_GetModuleHandleW
0x18000b592  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b599  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b5a0  mov     rcx, rax; hModule
0x18000b5a3  call    cs:__imp_GetProcAddress
0x18000b5a9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b5b0  test    rax, rax
0x18000b5b3  jnz     short loc_18000B5BC
0x18000b5b5  mov     ebx, 0C0000139h
0x18000b5ba  jmp     short loc_18000B5E6
0x18000b5bc  lea     rcx, [rsp+11D0h+var_1190]
0x18000b5c1  mov     [rsp+11D0h+var_11A8], rcx
0x18000b5c6  lea     rcx, [rbp+10D0h+var_1040]
0x18000b5cd  mov     [rsp+11D0h+var_11B0], rcx
0x18000b5d2  lea     r9, [rsp+11D0h+var_1188]
0x18000b5d7  xor     r8d, r8d
0x18000b5da  xor     edx, edx
0x18000b5dc  mov     rcx, r14
0x18000b5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5e4  mov     ebx, eax
0x18000b5e6  mov     ecx, ebx; this
0x18000b5e8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000b5ed  test    ebx, ebx
0x18000b5ef  jz      short loc_18000B5FF
0x18000b5f1  mov     eax, r15d
0x18000b5f4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000b5f8  mov     [rsp+11D0h+var_1188], r15d
0x18000b5fd  jmp     short loc_18000B603
0x18000b5ff  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000b603  mov     r8d, eax; unsigned __int64
0x18000b606  mov     r9d, 1000h; unsigned __int64
0x18000b60c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000b613  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000b618  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000b61d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000b621  jnz     loc_18000B833
0x18000b627  mov     [rbp+10D0h+var_1130], r15
0x18000b62b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000b632  mov     [rbp+10D0h+var_10B0], rax
0x18000b636  lea     rax, [rbp+10D0h+var_1130]
0x18000b63a  mov     [rbp+10D0h+var_10A8], rax
0x18000b63e  lea     rax, [rbp+10D0h+var_1128]
0x18000b642  mov     [rbp+10D0h+var_10A0], rax
0x18000b646  lea     rax, [rsp+11D0h+var_1170]
0x18000b64b  mov     [rbp+10D0h+var_1098], rax
0x18000b64f  lea     rax, [rbp+10D0h+var_10B0]
0x18000b653  mov     [rbp+10D0h+var_1048], rax
0x18000b65a  lea     rax, [rbp+10D0h+var_10B8]
0x18000b65e  mov     [rbp+10D0h+var_10C0], rax
0x18000b662  mov     rax, [rdi+18h]
0x18000b666  add     rax, 0Ah
0x18000b66a  mov     [rsp+11D0h+var_1190], rax
0x18000b66f  movzx   eax, word ptr [rdi+2]
0x18000b673  mov     [rbp+10D0h+var_1120], ax
0x18000b677  mov     al, [rdi+4]
0x18000b67a  mov     [rbp+10D0h+var_111E], al
0x18000b67d  mov     [rbp+10D0h+var_111C], r15d
0x18000b681  mov     [rbp+10D0h+var_1118], r15w
0x18000b686  xorps   xmm0, xmm0
0x18000b689  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000b68e  movzx   eax, word ptr [rdi+6]
0x18000b692  mov     [rbp+10D0h+var_1100], ax
0x18000b696  mov     al, [rdi+8]
0x18000b699  mov     [rbp+10D0h+var_10FE], al
0x18000b69c  mov     [rbp+10D0h+var_10FC], r15d
0x18000b6a0  mov     [rbp+10D0h+var_10F8], r15w
0x18000b6a5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000b6aa  jmp     loc_18000B742
0x18000b6af  mov     ebx, r15d
0x18000b6b2  mov     esi, [rbp+10D0h+var_111C]
0x18000b6b5  test    esi, esi
0x18000b6b7  jz      loc_18000B742
0x18000b6bd  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18000b6c1  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b6c5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b6ca  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000b6ce  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b6d3  test    al, al
0x18000b6d5  jz      short loc_18000B73F
0x18000b6d7  mov     eax, [rbp+10D0h+var_10FC]
0x18000b6da  mov     [rsp+11D0h+var_1180], eax
0x18000b6de  movzx   eax, [rbp+10D0h+var_10F8]
0x18000b6e2  mov     [rbp+10D0h+var_10E0], rax
0x18000b6e6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000b6ea  mov     [rbp+10D0h+var_10D8], rax
0x18000b6ee  movzx   eax, [rbp+10D0h+var_1118]
0x18000b6f2  mov     [rbp+10D0h+var_10D0], rax
0x18000b6f6  mov     [rbp+10D0h+var_10C8], r15
0x18000b6fa  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000b701  test    rcx, rcx
0x18000b704  jz      loc_18000B87E
0x18000b70a  mov     rax, [rcx]
0x18000b70d  lea     rdx, [rsp+11D0h+var_1180]
0x18000b712  mov     [rsp+11D0h+var_11A8], rdx
0x18000b717  lea     rdx, [rbp+10D0h+var_10E0]
0x18000b71b  mov     [rsp+11D0h+var_11B0], rdx
0x18000b720  lea     r9, [rbp+10D0h+var_10D8]
0x18000b724  lea     r8, [rbp+10D0h+var_10D0]
0x18000b728  lea     rdx, [rbp+10D0h+var_10C8]
0x18000b72c  mov     rax, [rax+20h]
0x18000b730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b735  test    al, al
0x18000b737  jz      short loc_18000B7AF
0x18000b739  inc     ebx
0x18000b73b  cmp     ebx, esi
0x18000b73d  jb      short loc_18000B6C1
0x18000b73f  xor     r15d, r15d
0x18000b742  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b746  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b74b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000b74f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b754  test    al, al
0x18000b756  jnz     loc_18000B6AF
0x18000b75c  mov     rcx, [rbp+10D0h+var_1048]
0x18000b763  test    rcx, rcx
0x18000b766  jz      short loc_18000B774
0x18000b768  mov     rax, [rcx]
0x18000b76b  mov     rax, [rax+18h]
0x18000b76f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b774  mov     bl, 1
0x18000b776  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000b77a  jz      short loc_18000B7F1
0x18000b77c  mov     eax, [rsp+11D0h+var_1188]
0x18000b780  mov     rdx, [rsp+11D0h+var_1158]
0x18000b785  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b789  sub     r8d, edx
0x18000b78c  mov     [rsp+11D0h+var_11A0], 1
0x18000b794  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000b798  mov     rcx, r14
0x18000b79b  call    wil_details_NtUpdateWnfStateData
0x18000b7a0  cmp     eax, 0C0000001h
0x18000b7a5  jnz     short loc_18000B7CF
0x18000b7a7  inc     r12
0x18000b7aa  mov     bl, r15b
0x18000b7ad  jmp     short loc_18000B7FD
0x18000b7af  mov     rcx, [rbp+10D0h+var_1048]
0x18000b7b6  xor     r15d, r15d
0x18000b7b9  test    rcx, rcx
0x18000b7bc  jz      short loc_18000B7CA
0x18000b7be  mov     rax, [rcx]
0x18000b7c1  mov     rax, [rax+18h]
0x18000b7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7ca  mov     bl, r15b
0x18000b7cd  jmp     short loc_18000B776
0x18000b7cf  test    eax, eax
0x18000b7d1  jz      short loc_18000B7F1
0x18000b7d3  mov     rdx, [rsp+11D0h+var_1158]
0x18000b7d8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b7dc  sub     r8d, edx
0x18000b7df  mov     [rsp+11D0h+var_11A0], r15d
0x18000b7e4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000b7e9  mov     rcx, r14
0x18000b7ec  call    wil_details_NtUpdateWnfStateData
0x18000b7f1  add     r14, 8
0x18000b7f5  mov     rax, [rbp+10D0h+var_1130]
0x18000b7f9  mov     [rbp+10D0h+var_1128], rax
0x18000b7fd  mov     rsi, [rbp+10D0h+lpMem]
0x18000b801  mov     [rbp+10D0h+lpMem], r15
0x18000b805  test    rsi, rsi
0x18000b808  jz      short loc_18000B81E
0x18000b80a  call    cs:__imp_GetProcessHeap
0x18000b810  mov     rcx, rax; hHeap
0x18000b813  mov     r8, rsi; lpMem
0x18000b816  xor     edx, edx; dwFlags
0x18000b818  call    cs:__imp_HeapFree
0x18000b81e  test    bl, bl
0x18000b820  jnz     short loc_18000B854
0x18000b822  cmp     r14, r13
0x18000b825  jnb     short loc_18000B854
0x18000b827  cmp     r12, 32h ; '2'
0x18000b82b  jb      loc_18000B4F6
0x18000b831  jmp     short loc_18000B854
0x18000b833  mov     rbx, [rbp+10D0h+lpMem]
0x18000b837  mov     [rbp+10D0h+lpMem], r15
0x18000b83b  test    rbx, rbx
0x18000b83e  jz      short loc_18000B854
0x18000b840  call    cs:__imp_GetProcessHeap
0x18000b846  mov     rcx, rax; hHeap
0x18000b849  mov     r8, rbx; lpMem
0x18000b84c  xor     edx, edx; dwFlags
0x18000b84e  call    cs:__imp_HeapFree
0x18000b854  mov     rcx, [rbp+10D0h+var_40]
0x18000b85b  xor     rcx, rsp; StackCookie
0x18000b85e  call    __security_check_cookie
0x18000b863  mov     rbx, [rsp+11D0h+arg_8]
0x18000b86b  add     rsp, 11A0h
0x18000b872  pop     r15
0x18000b874  pop     r14
0x18000b876  pop     r13
0x18000b878  pop     r12
0x18000b87a  pop     rdi
0x18000b87b  pop     rsi
0x18000b87c  pop     rbp
0x18000b87d  retn
0x18000b87e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
