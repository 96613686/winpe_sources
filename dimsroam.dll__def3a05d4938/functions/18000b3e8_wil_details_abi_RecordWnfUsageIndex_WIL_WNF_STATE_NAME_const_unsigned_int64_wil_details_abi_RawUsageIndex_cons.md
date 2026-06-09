# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000b3e8`
- end: `0x18000b7b5`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ab1c`

## callees

- `0x18000a6d8`
- `0x18000aa2c`
- `0x18000b3e8`
- `0x18000bdac`
- `0x18000ca3c`
- `0x18000d700`
- `0x18000d8d0`
- `0x18000d960`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b4c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b4c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b4de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b4de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b749`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b77f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b749`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b77f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b73b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b771`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b73b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b771`

## string_xrefs

- `0x18000b4c0`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v4; // r12
  unsigned __int64 v5; // r15
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
  int v17; // ebx
  int v18; // r9d
  char v19; // bl
  int updated; // eax
  int v21; // r9d
  void *v22; // rsi
  HANDLE ProcessHeap; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  __int64 *v26; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v27; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v28[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v29[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v30; // [rsp+64h] [rbp-9Ch]
  __int16 v31; // [rsp+66h] [rbp-9Ah]
  char v32; // [rsp+68h] [rbp-98h]
  __int64 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+78h] [rbp-88h]
  __int128 v35; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v37; // [rsp+98h] [rbp-68h]
  char v38; // [rsp+9Ah] [rbp-66h]
  __int64 v39; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v41; // [rsp+B0h] [rbp-50h] BYREF
  char v42; // [rsp+B2h] [rbp-4Eh]
  unsigned int v43; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v44; // [rsp+B8h] [rbp-48h]
  __int128 v45; // [rsp+C0h] [rbp-40h]
  __int16 v46; // [rsp+D0h] [rbp-30h] BYREF
  char v47; // [rsp+D2h] [rbp-2Eh]
  int v48; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v49; // [rsp+D8h] [rbp-28h]
  __int128 v50; // [rsp+E0h] [rbp-20h]
  __int64 v51; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v52; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v53; // [rsp+100h] [rbp+0h] BYREF
  __int64 v54; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v55[13]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *v56; // [rsp+180h] [rbp+80h]
  _BYTE v57[4096]; // [rsp+190h] [rbp+90h] BYREF

  v4 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v5 = 0;
  v40 = 0;
  v7 = this;
  while ( 1 )
  {
    v8 = *(unsigned __int16 *)(a3 + 6);
    v9 = *(_BYTE *)(a3 + 8);
    v29[0] = *(_WORD *)a3;
    v29[1] = *(_WORD *)(a3 + 2);
    v30 = *(_BYTE *)(a3 + 4);
    v31 = v8;
    v32 = v9;
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
      v33 = v10;
    }
    else
    {
      v33 = 0;
    }
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    v34 = 0;
    v35 = 0;
    lpMem = 0;
    v37 = 0;
    v38 = 0;
    v28[0] = 0;
    LODWORD(v27) = 4096;
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
      v26 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v7, 0, 0, v28);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      v28[0] = 0;
      LODWORD(v27) = 0;
    }
    else
    {
      v15 = (unsigned int)v27;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v29, v57, v15, 0x1000u);
    if ( HIBYTE(v37) )
      break;
    v39 = 0;
    v55[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v43 = 0;
    v55[1] = &v39;
    v55[2] = &v40;
    v55[3] = v29;
    v56 = (wil::details::in1diag3 *)v55;
    v16 = *(_QWORD *)(a3 + 24);
    v44 = 0;
    v27 = (unsigned __int8 *)(v16 + 10);
    v41 = *(_WORD *)(a3 + 2);
    v42 = *(_BYTE *)(a3 + 4);
    v46 = *(_WORD *)(a3 + 6);
    v47 = *(_BYTE *)(a3 + 8);
    v45 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
LABEL_25:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v41,
              &v27,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v17 = 0;
      if ( v43 )
      {
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v46,
                  &v27,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v28[2] = v48;
          v51 = v49;
          v52 = *((_QWORD *)&v50 + 1);
          v53 = v44;
          v54 = *((_QWORD *)&v45 + 1);
          if ( !v56 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v26 = &v51;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v56 + 32LL))(
                  v56,
                  &v54,
                  &v53,
                  &v52) )
          {
            if ( v56 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
            v19 = 0;
            goto LABEL_29;
          }
          if ( ++v17 >= v43 )
            goto LABEL_25;
        }
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
    v19 = 1;
LABEL_29:
    if ( !(_BYTE)v37 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v7, v34, (int)v35 - (int)v34, v18, (_DWORD)v26, v28[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v7, v34, v35 - v34, v21, (_DWORD)v26, 0, 0);
LABEL_37:
      v7 = (wil::details_abi *)((char *)v7 + 8);
      v40 = v39;
      goto LABEL_38;
    }
    ++v5;
    v19 = 0;
LABEL_38:
    v22 = lpMem;
    lpMem = 0;
    if ( v22 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v22);
    }
    if ( v19 || v7 >= v4 || v5 >= 0x32 )
      return;
  }
  v24 = lpMem;
  lpMem = 0;
  if ( v24 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
  }
}

```

## disassembly

```asm
0x18000b3e8  mov     [rsp-8+arg_8], rbx
0x18000b3ed  push    rbp
0x18000b3ee  push    rsi
0x18000b3ef  push    rdi
0x18000b3f0  push    r12
0x18000b3f2  push    r13
0x18000b3f4  push    r14
0x18000b3f6  push    r15
0x18000b3f8  lea     rbp, [rsp-10A0h]
0x18000b400  mov     eax, 11A0h
0x18000b405  call    _alloca_probe
0x18000b40a  sub     rsp, rax
0x18000b40d  mov     rax, cs:__security_cookie
0x18000b414  xor     rax, rsp
0x18000b417  mov     [rbp+10D0h+var_40], rax
0x18000b41e  xor     r13d, r13d
0x18000b421  lea     r12, [rcx+rdx*8]
0x18000b425  mov     r15d, r13d
0x18000b428  mov     [rbp+10D0h+var_1128], r13
0x18000b42c  mov     rdi, r8
0x18000b42f  mov     r14, rcx
0x18000b432  movzx   eax, word ptr [rdi]
0x18000b435  movzx   edx, word ptr [rdi+6]
0x18000b439  mov     cl, [rdi+8]
0x18000b43c  mov     [rsp+11D0h+var_1170], ax
0x18000b441  movzx   eax, word ptr [rdi+2]
0x18000b445  mov     [rsp+11D0h+var_116E], ax
0x18000b44a  mov     al, [rdi+4]
0x18000b44d  mov     [rsp+11D0h+var_116C], al
0x18000b451  mov     [rsp+11D0h+var_116A], dx
0x18000b456  mov     [rsp+11D0h+var_1168], cl
0x18000b45a  test    dx, dx
0x18000b45d  jz      short loc_18000B47C
0x18000b45f  mov     eax, edx
0x18000b461  cmp     cl, 1
0x18000b464  jnz     short loc_18000B46C
0x18000b466  add     rax, 2
0x18000b46a  jmp     short loc_18000B475
0x18000b46c  cmp     cl, 2
0x18000b46f  jnz     short loc_18000B475
0x18000b471  add     rax, 4
0x18000b475  mov     [rsp+11D0h+var_1160], rax
0x18000b47a  jmp     short loc_18000B481
0x18000b47c  mov     [rsp+11D0h+var_1160], r13
0x18000b481  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b488  xorps   xmm0, xmm0
0x18000b48b  mov     [rsp+11D0h+var_1158], r13
0x18000b490  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000b495  mov     [rbp+10D0h+lpMem], r13
0x18000b499  mov     [rbp+10D0h+var_1138], r13w
0x18000b49e  mov     [rbp+10D0h+var_1136], r13b
0x18000b4a2  mov     [rsp+11D0h+var_1188], r13d
0x18000b4a7  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000b4af  test    rax, rax
0x18000b4b2  jnz     short loc_18000B4F7
0x18000b4b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b4bb  test    rax, rax
0x18000b4be  jnz     short loc_18000B4D4
0x18000b4c0  lea     rcx, ModuleName; "ntdll.dll"
0x18000b4c7  call    cs:__imp_GetModuleHandleW
0x18000b4cd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b4d4  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b4db  mov     rcx, rax; hModule
0x18000b4de  call    cs:__imp_GetProcAddress
0x18000b4e4  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b4eb  test    rax, rax
0x18000b4ee  jnz     short loc_18000B4F7
0x18000b4f0  mov     ebx, 0C0000139h
0x18000b4f5  jmp     short loc_18000B521
0x18000b4f7  lea     rcx, [rsp+11D0h+var_1190]
0x18000b4fc  xor     r8d, r8d
0x18000b4ff  mov     [rsp+11D0h+var_11A8], rcx
0x18000b504  lea     r9, [rsp+11D0h+var_1188]
0x18000b509  lea     rcx, [rbp+10D0h+var_1040]
0x18000b510  xor     edx, edx
0x18000b512  mov     [rsp+11D0h+var_11B0], rcx
0x18000b517  mov     rcx, r14
0x18000b51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b51f  mov     ebx, eax
0x18000b521  mov     ecx, ebx; this
0x18000b523  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000b528  test    ebx, ebx
0x18000b52a  jz      short loc_18000B53A
0x18000b52c  mov     eax, r13d
0x18000b52f  mov     [rsp+11D0h+var_1188], r13d
0x18000b534  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000b538  jmp     short loc_18000B53E
0x18000b53a  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000b53e  mov     r8d, eax; unsigned __int64
0x18000b541  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000b548  mov     r9d, 1000h; unsigned __int64
0x18000b54e  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000b553  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000b558  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18000b55c  jnz     loc_18000B764
0x18000b562  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000b569  mov     [rbp+10D0h+var_1130], r13
0x18000b56d  mov     [rbp+10D0h+var_10B8], rax
0x18000b571  xorps   xmm0, xmm0
0x18000b574  lea     rax, [rbp+10D0h+var_1130]
0x18000b578  mov     [rbp+10D0h+var_111C], r13d
0x18000b57c  mov     [rbp+10D0h+var_10B0], rax
0x18000b580  lea     rax, [rbp+10D0h+var_1128]
0x18000b584  mov     [rbp+10D0h+var_10A8], rax
0x18000b588  lea     rax, [rsp+11D0h+var_1170]
0x18000b58d  mov     [rbp+10D0h+var_10A0], rax
0x18000b591  lea     rax, [rbp+10D0h+var_10B8]
0x18000b595  mov     [rbp+10D0h+var_1050], rax
0x18000b59c  mov     rax, [rdi+18h]
0x18000b5a0  add     rax, 0Ah
0x18000b5a4  mov     [rbp+10D0h+var_1118], r13w
0x18000b5a9  mov     [rsp+11D0h+var_1190], rax
0x18000b5ae  movzx   eax, word ptr [rdi+2]
0x18000b5b2  mov     [rbp+10D0h+var_1120], ax
0x18000b5b6  mov     al, [rdi+4]
0x18000b5b9  mov     [rbp+10D0h+var_111E], al
0x18000b5bc  movzx   eax, word ptr [rdi+6]
0x18000b5c0  mov     [rbp+10D0h+var_1100], ax
0x18000b5c4  mov     al, [rdi+8]
0x18000b5c7  mov     [rbp+10D0h+var_10FE], al
0x18000b5ca  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000b5cf  mov     [rbp+10D0h+var_10FC], r13d
0x18000b5d3  mov     [rbp+10D0h+var_10F8], r13w
0x18000b5d8  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000b5dd  jmp     loc_18000B676
0x18000b5e2  mov     ebx, r13d
0x18000b5e5  cmp     [rbp+10D0h+var_111C], r13d
0x18000b5e9  jbe     loc_18000B676
0x18000b5ef  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b5f3  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b5f8  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000b5fc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b601  test    al, al
0x18000b603  jz      short loc_18000B676
0x18000b605  mov     eax, [rbp+10D0h+var_10FC]
0x18000b608  mov     rcx, [rbp+10D0h+var_1050]; this
0x18000b60f  mov     [rsp+11D0h+var_1180], eax
0x18000b613  movzx   eax, [rbp+10D0h+var_10F8]
0x18000b617  mov     [rbp+10D0h+var_10E0], rax
0x18000b61b  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000b61f  mov     [rbp+10D0h+var_10D8], rax
0x18000b623  movzx   eax, [rbp+10D0h+var_1118]
0x18000b627  mov     [rbp+10D0h+var_10D0], rax
0x18000b62b  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18000b62f  mov     [rbp+10D0h+var_10C8], rax
0x18000b633  test    rcx, rcx
0x18000b636  jz      loc_18000B7AF
0x18000b63c  mov     rax, [rcx]
0x18000b63f  lea     rdx, [rsp+11D0h+var_1180]
0x18000b644  mov     [rsp+11D0h+var_11A8], rdx
0x18000b649  lea     r9, [rbp+10D0h+var_10D8]
0x18000b64d  lea     rdx, [rbp+10D0h+var_10E0]
0x18000b651  mov     [rsp+11D0h+var_11B0], rdx
0x18000b656  lea     r8, [rbp+10D0h+var_10D0]
0x18000b65a  mov     rax, [rax+20h]
0x18000b65e  lea     rdx, [rbp+10D0h+var_10C8]
0x18000b662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b667  test    al, al
0x18000b669  jz      short loc_18000B6E3
0x18000b66b  inc     ebx
0x18000b66d  cmp     ebx, [rbp+10D0h+var_111C]
0x18000b670  jb      loc_18000B5EF
0x18000b676  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b67a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b67f  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000b683  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b688  test    al, al
0x18000b68a  jnz     loc_18000B5E2
0x18000b690  mov     rcx, [rbp+10D0h+var_1050]
0x18000b697  test    rcx, rcx
0x18000b69a  jz      short loc_18000B6A8
0x18000b69c  mov     rax, [rcx]
0x18000b69f  mov     rax, [rax+18h]
0x18000b6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6a8  mov     bl, 1
0x18000b6aa  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18000b6ae  jz      short loc_18000B722
0x18000b6b0  mov     rdx, [rsp+11D0h+var_1158]
0x18000b6b5  mov     rcx, r14
0x18000b6b8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b6bc  mov     eax, [rsp+11D0h+var_1188]
0x18000b6c0  sub     r8d, edx
0x18000b6c3  mov     [rsp+11D0h+var_11A0], 1
0x18000b6cb  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000b6cf  call    wil_details_NtUpdateWnfStateData
0x18000b6d4  cmp     eax, 0C0000001h
0x18000b6d9  jnz     short loc_18000B700
0x18000b6db  inc     r15
0x18000b6de  mov     bl, r13b
0x18000b6e1  jmp     short loc_18000B72E
0x18000b6e3  mov     rcx, [rbp+10D0h+var_1050]
0x18000b6ea  test    rcx, rcx
0x18000b6ed  jz      short loc_18000B6FB
0x18000b6ef  mov     rax, [rcx]
0x18000b6f2  mov     rax, [rax+18h]
0x18000b6f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6fb  mov     bl, r13b
0x18000b6fe  jmp     short loc_18000B6AA
0x18000b700  test    eax, eax
0x18000b702  jz      short loc_18000B722
0x18000b704  mov     rdx, [rsp+11D0h+var_1158]
0x18000b709  mov     rcx, r14
0x18000b70c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b710  sub     r8d, edx
0x18000b713  mov     [rsp+11D0h+var_11A0], r13d
0x18000b718  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18000b71d  call    wil_details_NtUpdateWnfStateData
0x18000b722  mov     rax, [rbp+10D0h+var_1130]
0x18000b726  add     r14, 8
0x18000b72a  mov     [rbp+10D0h+var_1128], rax
0x18000b72e  mov     rsi, [rbp+10D0h+lpMem]
0x18000b732  mov     [rbp+10D0h+lpMem], r13
0x18000b736  test    rsi, rsi
0x18000b739  jz      short loc_18000B74F
0x18000b73b  call    cs:__imp_GetProcessHeap
0x18000b741  mov     r8, rsi; lpMem
0x18000b744  xor     edx, edx; dwFlags
0x18000b746  mov     rcx, rax; hHeap
0x18000b749  call    cs:__imp_HeapFree
0x18000b74f  test    bl, bl
0x18000b751  jnz     short loc_18000B785
0x18000b753  cmp     r14, r12
0x18000b756  jnb     short loc_18000B785
0x18000b758  cmp     r15, 32h ; '2'
0x18000b75c  jb      loc_18000B432
0x18000b762  jmp     short loc_18000B785
0x18000b764  mov     rbx, [rbp+10D0h+lpMem]
0x18000b768  mov     [rbp+10D0h+lpMem], r13
0x18000b76c  test    rbx, rbx
0x18000b76f  jz      short loc_18000B785
0x18000b771  call    cs:__imp_GetProcessHeap
0x18000b777  mov     r8, rbx; lpMem
0x18000b77a  xor     edx, edx; dwFlags
0x18000b77c  mov     rcx, rax; hHeap
0x18000b77f  call    cs:__imp_HeapFree
0x18000b785  mov     rcx, [rbp+10D0h+var_40]
0x18000b78c  xor     rcx, rsp; StackCookie
0x18000b78f  call    __security_check_cookie
0x18000b794  mov     rbx, [rsp+11D0h+arg_8]
0x18000b79c  add     rsp, 11A0h
0x18000b7a3  pop     r15
0x18000b7a5  pop     r14
0x18000b7a7  pop     r13
0x18000b7a9  pop     r12
0x18000b7ab  pop     rdi
0x18000b7ac  pop     rsi
0x18000b7ad  pop     rbp
0x18000b7ae  retn
0x18000b7af  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
