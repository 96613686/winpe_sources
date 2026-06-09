# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000b298`
- end: `0x18000b670`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a770`

## callees

- `0x1800039f0`
- `0x18000a198`
- `0x18000a628`
- `0x18000b298`
- `0x18000bdc4`
- `0x18000d438`
- `0x18000e520`
- `0x1800388e0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b604`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b63a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b604`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b63a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b62c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b62c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b378`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b378`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b38f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b38f`

## string_xrefs

- `0x18000b371`: `ntdll.dll`

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
0x18000b298  mov     [rsp-8+arg_8], rbx
0x18000b29d  push    rbp
0x18000b29e  push    rsi
0x18000b29f  push    rdi
0x18000b2a0  push    r12
0x18000b2a2  push    r13
0x18000b2a4  push    r14
0x18000b2a6  push    r15
0x18000b2a8  lea     rbp, [rsp-10A0h]
0x18000b2b0  mov     eax, 11A0h
0x18000b2b5  call    _alloca_probe
0x18000b2ba  sub     rsp, rax
0x18000b2bd  mov     rax, cs:__security_cookie
0x18000b2c4  xor     rax, rsp
0x18000b2c7  mov     [rbp+10D0h+var_40], rax
0x18000b2ce  mov     rdi, r8
0x18000b2d1  mov     r14, rcx
0x18000b2d4  lea     r13, [rcx+rdx*8]
0x18000b2d8  xor     r15d, r15d
0x18000b2db  mov     r12d, r15d
0x18000b2de  mov     [rbp+10D0h+var_1128], r15
0x18000b2e2  mov     cl, [rdi+8]
0x18000b2e5  movzx   edx, word ptr [rdi+6]
0x18000b2e9  movzx   eax, word ptr [rdi]
0x18000b2ec  mov     [rsp+11D0h+var_1170], ax
0x18000b2f1  movzx   eax, word ptr [rdi+2]
0x18000b2f5  mov     [rsp+11D0h+var_116E], ax
0x18000b2fa  mov     al, [rdi+4]
0x18000b2fd  mov     [rsp+11D0h+var_116C], al
0x18000b301  mov     [rsp+11D0h+var_116A], dx
0x18000b306  mov     [rsp+11D0h+var_1168], cl
0x18000b30a  test    dx, dx
0x18000b30d  jz      short loc_18000B32C
0x18000b30f  mov     eax, edx
0x18000b311  cmp     cl, 1
0x18000b314  jnz     short loc_18000B31C
0x18000b316  add     rax, 2
0x18000b31a  jmp     short loc_18000B325
0x18000b31c  cmp     cl, 2
0x18000b31f  jnz     short loc_18000B325
0x18000b321  add     rax, 4
0x18000b325  mov     [rsp+11D0h+var_1160], rax
0x18000b32a  jmp     short loc_18000B331
0x18000b32c  mov     [rsp+11D0h+var_1160], r15
0x18000b331  mov     [rsp+11D0h+var_1158], r15
0x18000b336  xorps   xmm0, xmm0
0x18000b339  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000b33e  mov     [rbp+10D0h+lpMem], r15
0x18000b342  mov     [rbp+10D0h+var_1138], 0
0x18000b348  mov     [rbp+10D0h+var_1136], r15b
0x18000b34c  mov     [rsp+11D0h+var_1188], r15d
0x18000b351  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000b359  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b360  test    rax, rax
0x18000b363  jnz     short loc_18000B3A8
0x18000b365  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b36c  test    rax, rax
0x18000b36f  jnz     short loc_18000B385
0x18000b371  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000b378  call    cs:__imp_GetModuleHandleW
0x18000b37e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b385  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b38c  mov     rcx, rax; hModule
0x18000b38f  call    cs:__imp_GetProcAddress
0x18000b395  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b39c  test    rax, rax
0x18000b39f  jnz     short loc_18000B3A8
0x18000b3a1  mov     ebx, 0C0000139h
0x18000b3a6  jmp     short loc_18000B3D2
0x18000b3a8  lea     rcx, [rsp+11D0h+var_1190]
0x18000b3ad  mov     [rsp+11D0h+var_11A8], rcx
0x18000b3b2  lea     rcx, [rbp+10D0h+var_1040]
0x18000b3b9  mov     [rsp+11D0h+var_11B0], rcx
0x18000b3be  lea     r9, [rsp+11D0h+var_1188]
0x18000b3c3  xor     r8d, r8d
0x18000b3c6  xor     edx, edx
0x18000b3c8  mov     rcx, r14
0x18000b3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3d0  mov     ebx, eax
0x18000b3d2  mov     ecx, ebx; this
0x18000b3d4  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000b3d9  test    ebx, ebx
0x18000b3db  jz      short loc_18000B3EB
0x18000b3dd  mov     eax, r15d
0x18000b3e0  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000b3e4  mov     [rsp+11D0h+var_1188], r15d
0x18000b3e9  jmp     short loc_18000B3EF
0x18000b3eb  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000b3ef  mov     r8d, eax; unsigned __int64
0x18000b3f2  mov     r9d, 1000h; unsigned __int64
0x18000b3f8  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000b3ff  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000b404  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000b409  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000b40d  jnz     loc_18000B61F
0x18000b413  mov     [rbp+10D0h+var_1130], r15
0x18000b417  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000b41e  mov     [rbp+10D0h+var_10B0], rax
0x18000b422  lea     rax, [rbp+10D0h+var_1130]
0x18000b426  mov     [rbp+10D0h+var_10A8], rax
0x18000b42a  lea     rax, [rbp+10D0h+var_1128]
0x18000b42e  mov     [rbp+10D0h+var_10A0], rax
0x18000b432  lea     rax, [rsp+11D0h+var_1170]
0x18000b437  mov     [rbp+10D0h+var_1098], rax
0x18000b43b  lea     rax, [rbp+10D0h+var_10B0]
0x18000b43f  mov     [rbp+10D0h+var_1048], rax
0x18000b446  lea     rax, [rbp+10D0h+var_10B8]
0x18000b44a  mov     [rbp+10D0h+var_10C0], rax
0x18000b44e  mov     rax, [rdi+18h]
0x18000b452  add     rax, 0Ah
0x18000b456  mov     [rsp+11D0h+var_1190], rax
0x18000b45b  movzx   eax, word ptr [rdi+2]
0x18000b45f  mov     [rbp+10D0h+var_1120], ax
0x18000b463  mov     al, [rdi+4]
0x18000b466  mov     [rbp+10D0h+var_111E], al
0x18000b469  mov     [rbp+10D0h+var_111C], r15d
0x18000b46d  mov     [rbp+10D0h+var_1118], r15w
0x18000b472  xorps   xmm0, xmm0
0x18000b475  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000b47a  movzx   eax, word ptr [rdi+6]
0x18000b47e  mov     [rbp+10D0h+var_1100], ax
0x18000b482  mov     al, [rdi+8]
0x18000b485  mov     [rbp+10D0h+var_10FE], al
0x18000b488  mov     [rbp+10D0h+var_10FC], r15d
0x18000b48c  mov     [rbp+10D0h+var_10F8], r15w
0x18000b491  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000b496  jmp     loc_18000B52E
0x18000b49b  mov     ebx, r15d
0x18000b49e  mov     esi, [rbp+10D0h+var_111C]
0x18000b4a1  test    esi, esi
0x18000b4a3  jz      loc_18000B52E
0x18000b4a9  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18000b4ad  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b4b1  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b4b6  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000b4ba  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b4bf  test    al, al
0x18000b4c1  jz      short loc_18000B52B
0x18000b4c3  mov     eax, [rbp+10D0h+var_10FC]
0x18000b4c6  mov     [rsp+11D0h+var_1180], eax
0x18000b4ca  movzx   eax, [rbp+10D0h+var_10F8]
0x18000b4ce  mov     [rbp+10D0h+var_10E0], rax
0x18000b4d2  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000b4d6  mov     [rbp+10D0h+var_10D8], rax
0x18000b4da  movzx   eax, [rbp+10D0h+var_1118]
0x18000b4de  mov     [rbp+10D0h+var_10D0], rax
0x18000b4e2  mov     [rbp+10D0h+var_10C8], r15
0x18000b4e6  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000b4ed  test    rcx, rcx
0x18000b4f0  jz      loc_18000B66A
0x18000b4f6  mov     rax, [rcx]
0x18000b4f9  lea     rdx, [rsp+11D0h+var_1180]
0x18000b4fe  mov     [rsp+11D0h+var_11A8], rdx
0x18000b503  lea     rdx, [rbp+10D0h+var_10E0]
0x18000b507  mov     [rsp+11D0h+var_11B0], rdx
0x18000b50c  lea     r9, [rbp+10D0h+var_10D8]
0x18000b510  lea     r8, [rbp+10D0h+var_10D0]
0x18000b514  lea     rdx, [rbp+10D0h+var_10C8]
0x18000b518  mov     rax, [rax+20h]
0x18000b51c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b521  test    al, al
0x18000b523  jz      short loc_18000B59B
0x18000b525  inc     ebx
0x18000b527  cmp     ebx, esi
0x18000b529  jb      short loc_18000B4AD
0x18000b52b  xor     r15d, r15d
0x18000b52e  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b532  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b537  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000b53b  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b540  test    al, al
0x18000b542  jnz     loc_18000B49B
0x18000b548  mov     rcx, [rbp+10D0h+var_1048]
0x18000b54f  test    rcx, rcx
0x18000b552  jz      short loc_18000B560
0x18000b554  mov     rax, [rcx]
0x18000b557  mov     rax, [rax+18h]
0x18000b55b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b560  mov     bl, 1
0x18000b562  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000b566  jz      short loc_18000B5DD
0x18000b568  mov     eax, [rsp+11D0h+var_1188]
0x18000b56c  mov     rdx, [rsp+11D0h+var_1158]
0x18000b571  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b575  sub     r8d, edx
0x18000b578  mov     [rsp+11D0h+var_11A0], 1
0x18000b580  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000b584  mov     rcx, r14
0x18000b587  call    wil_details_NtUpdateWnfStateData
0x18000b58c  cmp     eax, 0C0000001h
0x18000b591  jnz     short loc_18000B5BB
0x18000b593  inc     r12
0x18000b596  mov     bl, r15b
0x18000b599  jmp     short loc_18000B5E9
0x18000b59b  mov     rcx, [rbp+10D0h+var_1048]
0x18000b5a2  xor     r15d, r15d
0x18000b5a5  test    rcx, rcx
0x18000b5a8  jz      short loc_18000B5B6
0x18000b5aa  mov     rax, [rcx]
0x18000b5ad  mov     rax, [rax+18h]
0x18000b5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5b6  mov     bl, r15b
0x18000b5b9  jmp     short loc_18000B562
0x18000b5bb  test    eax, eax
0x18000b5bd  jz      short loc_18000B5DD
0x18000b5bf  mov     rdx, [rsp+11D0h+var_1158]
0x18000b5c4  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b5c8  sub     r8d, edx
0x18000b5cb  mov     [rsp+11D0h+var_11A0], r15d
0x18000b5d0  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000b5d5  mov     rcx, r14
0x18000b5d8  call    wil_details_NtUpdateWnfStateData
0x18000b5dd  add     r14, 8
0x18000b5e1  mov     rax, [rbp+10D0h+var_1130]
0x18000b5e5  mov     [rbp+10D0h+var_1128], rax
0x18000b5e9  mov     rsi, [rbp+10D0h+lpMem]
0x18000b5ed  mov     [rbp+10D0h+lpMem], r15
0x18000b5f1  test    rsi, rsi
0x18000b5f4  jz      short loc_18000B60A
0x18000b5f6  call    cs:__imp_GetProcessHeap
0x18000b5fc  mov     rcx, rax; hHeap
0x18000b5ff  mov     r8, rsi; lpMem
0x18000b602  xor     edx, edx; dwFlags
0x18000b604  call    cs:__imp_HeapFree
0x18000b60a  test    bl, bl
0x18000b60c  jnz     short loc_18000B640
0x18000b60e  cmp     r14, r13
0x18000b611  jnb     short loc_18000B640
0x18000b613  cmp     r12, 32h ; '2'
0x18000b617  jb      loc_18000B2E2
0x18000b61d  jmp     short loc_18000B640
0x18000b61f  mov     rbx, [rbp+10D0h+lpMem]
0x18000b623  mov     [rbp+10D0h+lpMem], r15
0x18000b627  test    rbx, rbx
0x18000b62a  jz      short loc_18000B640
0x18000b62c  call    cs:__imp_GetProcessHeap
0x18000b632  mov     rcx, rax; hHeap
0x18000b635  mov     r8, rbx; lpMem
0x18000b638  xor     edx, edx; dwFlags
0x18000b63a  call    cs:__imp_HeapFree
0x18000b640  mov     rcx, [rbp+10D0h+var_40]
0x18000b647  xor     rcx, rsp; StackCookie
0x18000b64a  call    __security_check_cookie
0x18000b64f  mov     rbx, [rsp+11D0h+arg_8]
0x18000b657  add     rsp, 11A0h
0x18000b65e  pop     r15
0x18000b660  pop     r14
0x18000b662  pop     r13
0x18000b664  pop     r12
0x18000b666  pop     rdi
0x18000b667  pop     rsi
0x18000b668  pop     rbp
0x18000b669  retn
0x18000b66a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
