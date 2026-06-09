# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18001c1f8`
- end: `0x18001c5cf`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18001b998`

## callees

- `0x18000ad08`
- `0x180017e78`
- `0x18001b608`
- `0x18001c1f8`
- `0x18001f624`
- `0x180022f34`
- `0x180043750`
- `0x180043810`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c2ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c2ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c2d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c2d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c554`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c58b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c554`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c58b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c562`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c599`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c562`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c599`

## string_xrefs

- `0x18001c2d0`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  __int64 v17; // r9
  char v18; // di
  int updated; // eax
  __int64 v20; // r9
  void *v21; // rsi
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  __int64 *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v25 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v27);
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
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v33, (int)v34 - (int)v33, v17, (int)v25, v27[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v33, v34 - v33, v20, (int)v25, 0, 0);
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
0x18001c1f8  mov     [rsp-8+arg_8], rbx
0x18001c1fd  push    rbp
0x18001c1fe  push    rsi
0x18001c1ff  push    rdi
0x18001c200  push    r12
0x18001c202  push    r13
0x18001c204  push    r14
0x18001c206  push    r15
0x18001c208  lea     rbp, [rsp-10A0h]
0x18001c210  mov     eax, 11A0h
0x18001c215  call    _alloca_probe
0x18001c21a  sub     rsp, rax
0x18001c21d  mov     rax, cs:__security_cookie
0x18001c224  xor     rax, rsp
0x18001c227  mov     [rbp+10D0h+var_40], rax
0x18001c22e  mov     rbx, r8
0x18001c231  mov     r14, rcx
0x18001c234  lea     r12, [rcx+rdx*8]
0x18001c238  xor     r13d, r13d
0x18001c23b  mov     r15d, r13d
0x18001c23e  mov     [rbp+10D0h+var_1128], r13
0x18001c242  mov     cl, [rbx+8]
0x18001c245  movzx   edx, word ptr [rbx+6]
0x18001c249  movzx   eax, word ptr [rbx]
0x18001c24c  mov     [rsp+11D0h+var_1170], ax
0x18001c251  movzx   eax, word ptr [rbx+2]
0x18001c255  mov     [rsp+11D0h+var_116E], ax
0x18001c25a  mov     al, [rbx+4]
0x18001c25d  mov     [rsp+11D0h+var_116C], al
0x18001c261  mov     [rsp+11D0h+var_116A], dx
0x18001c266  mov     [rsp+11D0h+var_1168], cl
0x18001c26a  test    dx, dx
0x18001c26d  jz      short loc_18001C28C
0x18001c26f  mov     eax, edx
0x18001c271  cmp     cl, 1
0x18001c274  jnz     short loc_18001C27C
0x18001c276  add     rax, 2
0x18001c27a  jmp     short loc_18001C285
0x18001c27c  cmp     cl, 2
0x18001c27f  jnz     short loc_18001C285
0x18001c281  add     rax, 4
0x18001c285  mov     [rsp+11D0h+var_1160], rax
0x18001c28a  jmp     short loc_18001C291
0x18001c28c  mov     [rsp+11D0h+var_1160], r13
0x18001c291  mov     [rsp+11D0h+var_1158], r13
0x18001c296  xorps   xmm0, xmm0
0x18001c299  movdqa  [rbp+10D0h+var_1150], xmm0
0x18001c29e  mov     [rbp+10D0h+lpMem], r13
0x18001c2a2  mov     [rbp+10D0h+var_1138], r13w
0x18001c2a7  mov     [rbp+10D0h+var_1136], r13b
0x18001c2ab  mov     [rsp+11D0h+var_1188], r13d
0x18001c2b0  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18001c2b8  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18001c2bf  test    rax, rax
0x18001c2c2  jnz     short loc_18001C307
0x18001c2c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001c2cb  test    rax, rax
0x18001c2ce  jnz     short loc_18001C2E4
0x18001c2d0  lea     rcx, ModuleName; "ntdll.dll"
0x18001c2d7  call    cs:__imp_GetModuleHandleW
0x18001c2dd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001c2e4  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18001c2eb  mov     rcx, rax; hModule
0x18001c2ee  call    cs:__imp_GetProcAddress
0x18001c2f4  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18001c2fb  test    rax, rax
0x18001c2fe  jnz     short loc_18001C307
0x18001c300  mov     edi, 0C0000139h
0x18001c305  jmp     short loc_18001C331
0x18001c307  lea     rcx, [rsp+11D0h+var_1190]
0x18001c30c  mov     [rsp+11D0h+var_11A8], rcx
0x18001c311  lea     rcx, [rbp+10D0h+var_1040]
0x18001c318  mov     [rsp+11D0h+var_11B0], rcx
0x18001c31d  lea     r9, [rsp+11D0h+var_1188]
0x18001c322  xor     r8d, r8d
0x18001c325  xor     edx, edx
0x18001c327  mov     rcx, r14
0x18001c32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c32f  mov     edi, eax
0x18001c331  mov     ecx, edi; this
0x18001c333  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18001c338  test    edi, edi
0x18001c33a  jz      short loc_18001C34A
0x18001c33c  mov     eax, r13d
0x18001c33f  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18001c343  mov     [rsp+11D0h+var_1188], r13d
0x18001c348  jmp     short loc_18001C34E
0x18001c34a  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18001c34e  mov     r8d, eax; unsigned __int64
0x18001c351  mov     r9d, 1000h; unsigned __int64
0x18001c357  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18001c35e  lea     rcx, [rsp+11D0h+var_1170]; this
0x18001c363  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18001c368  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18001c36c  jnz     loc_18001C57E
0x18001c372  mov     [rbp+10D0h+var_1130], r13
0x18001c376  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18001c37d  mov     [rbp+10D0h+var_10B0], rax
0x18001c381  lea     rax, [rbp+10D0h+var_1130]
0x18001c385  mov     [rbp+10D0h+var_10A8], rax
0x18001c389  lea     rax, [rbp+10D0h+var_1128]
0x18001c38d  mov     [rbp+10D0h+var_10A0], rax
0x18001c391  lea     rax, [rsp+11D0h+var_1170]
0x18001c396  mov     [rbp+10D0h+var_1098], rax
0x18001c39a  lea     rax, [rbp+10D0h+var_10B0]
0x18001c39e  mov     [rbp+10D0h+var_1048], rax
0x18001c3a5  lea     rax, [rbp+10D0h+var_10B8]
0x18001c3a9  mov     [rbp+10D0h+var_10C0], rax
0x18001c3ad  mov     rax, [rbx+18h]
0x18001c3b1  add     rax, 0Ah
0x18001c3b5  mov     [rsp+11D0h+var_1190], rax
0x18001c3ba  movzx   eax, word ptr [rbx+2]
0x18001c3be  mov     [rbp+10D0h+var_1120], ax
0x18001c3c2  mov     al, [rbx+4]
0x18001c3c5  mov     [rbp+10D0h+var_111E], al
0x18001c3c8  mov     [rbp+10D0h+var_111C], r13d
0x18001c3cc  mov     [rbp+10D0h+var_1118], r13w
0x18001c3d1  xorps   xmm0, xmm0
0x18001c3d4  movdqu  [rbp+10D0h+var_1110], xmm0
0x18001c3d9  movzx   eax, word ptr [rbx+6]
0x18001c3dd  mov     [rbp+10D0h+var_1100], ax
0x18001c3e1  mov     al, [rbx+8]
0x18001c3e4  mov     [rbp+10D0h+var_10FE], al
0x18001c3e7  mov     [rbp+10D0h+var_10FC], r13d
0x18001c3eb  mov     [rbp+10D0h+var_10F8], r13w
0x18001c3f0  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18001c3f5  jmp     loc_18001C48E
0x18001c3fa  mov     edi, r13d
0x18001c3fd  cmp     [rbp+10D0h+var_111C], r13d
0x18001c401  jbe     loc_18001C48E
0x18001c407  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001c40b  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18001c410  lea     rcx, [rbp+10D0h+var_1100]; this
0x18001c414  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001c419  test    al, al
0x18001c41b  jz      short loc_18001C48E
0x18001c41d  mov     eax, [rbp+10D0h+var_10FC]
0x18001c420  mov     [rsp+11D0h+var_1180], eax
0x18001c424  movzx   eax, [rbp+10D0h+var_10F8]
0x18001c428  mov     [rbp+10D0h+var_10E0], rax
0x18001c42c  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18001c430  mov     [rbp+10D0h+var_10D8], rax
0x18001c434  movzx   eax, [rbp+10D0h+var_1118]
0x18001c438  mov     [rbp+10D0h+var_10D0], rax
0x18001c43c  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18001c440  mov     [rbp+10D0h+var_10C8], rax
0x18001c444  mov     rcx, [rbp+10D0h+var_1048]; this
0x18001c44b  test    rcx, rcx
0x18001c44e  jz      loc_18001C5C9
0x18001c454  mov     rax, [rcx]
0x18001c457  lea     rdx, [rsp+11D0h+var_1180]
0x18001c45c  mov     [rsp+11D0h+var_11A8], rdx
0x18001c461  lea     rdx, [rbp+10D0h+var_10E0]
0x18001c465  mov     [rsp+11D0h+var_11B0], rdx
0x18001c46a  lea     r9, [rbp+10D0h+var_10D8]
0x18001c46e  lea     r8, [rbp+10D0h+var_10D0]
0x18001c472  lea     rdx, [rbp+10D0h+var_10C8]
0x18001c476  mov     rax, [rax+20h]
0x18001c47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c47f  test    al, al
0x18001c481  jz      short loc_18001C4FC
0x18001c483  inc     edi
0x18001c485  cmp     edi, [rbp+10D0h+var_111C]
0x18001c488  jb      loc_18001C407
0x18001c48e  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001c492  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18001c497  lea     rcx, [rbp+10D0h+var_1120]; this
0x18001c49b  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001c4a0  test    al, al
0x18001c4a2  jnz     loc_18001C3FA
0x18001c4a8  mov     rcx, [rbp+10D0h+var_1048]
0x18001c4af  test    rcx, rcx
0x18001c4b2  jz      short loc_18001C4C0
0x18001c4b4  mov     rax, [rcx]
0x18001c4b7  mov     rax, [rax+18h]
0x18001c4bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4c0  mov     dil, 1
0x18001c4c3  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18001c4c7  jz      short loc_18001C53B
0x18001c4c9  mov     eax, [rsp+11D0h+var_1188]
0x18001c4cd  mov     rdx, [rsp+11D0h+var_1158]
0x18001c4d2  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18001c4d6  sub     r8d, edx
0x18001c4d9  mov     [rsp+11D0h+var_11A0], 1
0x18001c4e1  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18001c4e5  mov     rcx, r14
0x18001c4e8  call    wil_details_NtUpdateWnfStateData
0x18001c4ed  cmp     eax, 0C0000001h
0x18001c4f2  jnz     short loc_18001C519
0x18001c4f4  inc     r15
0x18001c4f7  mov     dil, r13b
0x18001c4fa  jmp     short loc_18001C547
0x18001c4fc  mov     rcx, [rbp+10D0h+var_1048]
0x18001c503  test    rcx, rcx
0x18001c506  jz      short loc_18001C514
0x18001c508  mov     rax, [rcx]
0x18001c50b  mov     rax, [rax+18h]
0x18001c50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c514  mov     dil, r13b
0x18001c517  jmp     short loc_18001C4C3
0x18001c519  test    eax, eax
0x18001c51b  jz      short loc_18001C53B
0x18001c51d  mov     rdx, [rsp+11D0h+var_1158]
0x18001c522  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18001c526  sub     r8d, edx
0x18001c529  mov     [rsp+11D0h+var_11A0], r13d
0x18001c52e  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18001c533  mov     rcx, r14
0x18001c536  call    wil_details_NtUpdateWnfStateData
0x18001c53b  add     r14, 8
0x18001c53f  mov     rax, [rbp+10D0h+var_1130]
0x18001c543  mov     [rbp+10D0h+var_1128], rax
0x18001c547  mov     rsi, [rbp+10D0h+lpMem]
0x18001c54b  mov     [rbp+10D0h+lpMem], r13
0x18001c54f  test    rsi, rsi
0x18001c552  jz      short loc_18001C568
0x18001c554  call    cs:__imp_GetProcessHeap
0x18001c55a  mov     rcx, rax; hHeap
0x18001c55d  mov     r8, rsi; lpMem
0x18001c560  xor     edx, edx; dwFlags
0x18001c562  call    cs:__imp_HeapFree
0x18001c568  test    dil, dil
0x18001c56b  jnz     short loc_18001C59F
0x18001c56d  cmp     r14, r12
0x18001c570  jnb     short loc_18001C59F
0x18001c572  cmp     r15, 32h ; '2'
0x18001c576  jb      loc_18001C242
0x18001c57c  jmp     short loc_18001C59F
0x18001c57e  mov     rbx, [rbp+10D0h+lpMem]
0x18001c582  mov     [rbp+10D0h+lpMem], r13
0x18001c586  test    rbx, rbx
0x18001c589  jz      short loc_18001C59F
0x18001c58b  call    cs:__imp_GetProcessHeap
0x18001c591  mov     rcx, rax; hHeap
0x18001c594  mov     r8, rbx; lpMem
0x18001c597  xor     edx, edx; dwFlags
0x18001c599  call    cs:__imp_HeapFree
0x18001c59f  mov     rcx, [rbp+10D0h+var_40]
0x18001c5a6  xor     rcx, rsp; StackCookie
0x18001c5a9  call    __security_check_cookie
0x18001c5ae  mov     rbx, [rsp+11D0h+arg_8]
0x18001c5b6  add     rsp, 11A0h
0x18001c5bd  pop     r15
0x18001c5bf  pop     r14
0x18001c5c1  pop     r13
0x18001c5c3  pop     r12
0x18001c5c5  pop     rdi
0x18001c5c6  pop     rsi
0x18001c5c7  pop     rbp
0x18001c5c8  retn
0x18001c5c9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
