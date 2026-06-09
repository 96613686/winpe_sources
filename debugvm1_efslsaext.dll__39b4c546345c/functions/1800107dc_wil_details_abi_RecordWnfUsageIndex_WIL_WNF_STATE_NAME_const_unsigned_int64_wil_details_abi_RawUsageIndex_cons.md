# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800107dc`
- end: `0x180010ba9`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ff84`

## callees

- `0x1800062ec`
- `0x18000fbe4`
- `0x18000fe94`
- `0x1800107dc`
- `0x180010d50`
- `0x180011b60`
- `0x180012040`
- `0x1800120d0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800108bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800108bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010b3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010b73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010b3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010b73`

## string_xrefs

- `0x1800108b4`: `ntdll.dll`

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
  __int64 v18; // r9
  char v19; // bl
  int updated; // eax
  __int64 v21; // r9
  void *v22; // rsi
  HANDLE ProcessHeap; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  __int64 *v26; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v7, 0, 0, v28);
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
    updated = wil_details_NtUpdateWnfStateData((__int64)v7, v34, (int)v35 - (int)v34, v18, (int)v26, v28[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v7, v34, v35 - v34, v21, (int)v26, 0, 0);
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
0x1800107dc  mov     [rsp-8+arg_8], rbx
0x1800107e1  push    rbp
0x1800107e2  push    rsi
0x1800107e3  push    rdi
0x1800107e4  push    r12
0x1800107e6  push    r13
0x1800107e8  push    r14
0x1800107ea  push    r15
0x1800107ec  lea     rbp, [rsp-10A0h]
0x1800107f4  mov     eax, 11A0h
0x1800107f9  call    _alloca_probe
0x1800107fe  sub     rsp, rax
0x180010801  mov     rax, cs:__security_cookie
0x180010808  xor     rax, rsp
0x18001080b  mov     [rbp+10D0h+var_40], rax
0x180010812  xor     r13d, r13d
0x180010815  lea     r12, [rcx+rdx*8]
0x180010819  mov     r15d, r13d
0x18001081c  mov     [rbp+10D0h+var_1128], r13
0x180010820  mov     rdi, r8
0x180010823  mov     r14, rcx
0x180010826  movzx   eax, word ptr [rdi]
0x180010829  movzx   edx, word ptr [rdi+6]
0x18001082d  mov     cl, [rdi+8]
0x180010830  mov     [rsp+11D0h+var_1170], ax
0x180010835  movzx   eax, word ptr [rdi+2]
0x180010839  mov     [rsp+11D0h+var_116E], ax
0x18001083e  mov     al, [rdi+4]
0x180010841  mov     [rsp+11D0h+var_116C], al
0x180010845  mov     [rsp+11D0h+var_116A], dx
0x18001084a  mov     [rsp+11D0h+var_1168], cl
0x18001084e  test    dx, dx
0x180010851  jz      short loc_180010870
0x180010853  mov     eax, edx
0x180010855  cmp     cl, 1
0x180010858  jnz     short loc_180010860
0x18001085a  add     rax, 2
0x18001085e  jmp     short loc_180010869
0x180010860  cmp     cl, 2
0x180010863  jnz     short loc_180010869
0x180010865  add     rax, 4
0x180010869  mov     [rsp+11D0h+var_1160], rax
0x18001086e  jmp     short loc_180010875
0x180010870  mov     [rsp+11D0h+var_1160], r13
0x180010875  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18001087c  xorps   xmm0, xmm0
0x18001087f  mov     [rsp+11D0h+var_1158], r13
0x180010884  movdqa  [rbp+10D0h+var_1150], xmm0
0x180010889  mov     [rbp+10D0h+lpMem], r13
0x18001088d  mov     [rbp+10D0h+var_1138], r13w
0x180010892  mov     [rbp+10D0h+var_1136], r13b
0x180010896  mov     [rsp+11D0h+var_1188], r13d
0x18001089b  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1800108a3  test    rax, rax
0x1800108a6  jnz     short loc_1800108EB
0x1800108a8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800108af  test    rax, rax
0x1800108b2  jnz     short loc_1800108C8
0x1800108b4  lea     rcx, ModuleName; "ntdll.dll"
0x1800108bb  call    cs:__imp_GetModuleHandleW
0x1800108c1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800108c8  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800108cf  mov     rcx, rax; hModule
0x1800108d2  call    cs:__imp_GetProcAddress
0x1800108d8  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800108df  test    rax, rax
0x1800108e2  jnz     short loc_1800108EB
0x1800108e4  mov     ebx, 0C0000139h
0x1800108e9  jmp     short loc_180010915
0x1800108eb  lea     rcx, [rsp+11D0h+var_1190]
0x1800108f0  xor     r8d, r8d
0x1800108f3  mov     [rsp+11D0h+var_11A8], rcx
0x1800108f8  lea     r9, [rsp+11D0h+var_1188]
0x1800108fd  lea     rcx, [rbp+10D0h+var_1040]
0x180010904  xor     edx, edx
0x180010906  mov     [rsp+11D0h+var_11B0], rcx
0x18001090b  mov     rcx, r14
0x18001090e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010913  mov     ebx, eax
0x180010915  mov     ecx, ebx; this
0x180010917  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18001091c  test    ebx, ebx
0x18001091e  jz      short loc_18001092E
0x180010920  mov     eax, r13d
0x180010923  mov     [rsp+11D0h+var_1188], r13d
0x180010928  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18001092c  jmp     short loc_180010932
0x18001092e  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180010932  mov     r8d, eax; unsigned __int64
0x180010935  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18001093c  mov     r9d, 1000h; unsigned __int64
0x180010942  lea     rcx, [rsp+11D0h+var_1170]; this
0x180010947  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18001094c  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x180010950  jnz     loc_180010B58
0x180010956  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18001095d  mov     [rbp+10D0h+var_1130], r13
0x180010961  mov     [rbp+10D0h+var_10B8], rax
0x180010965  xorps   xmm0, xmm0
0x180010968  lea     rax, [rbp+10D0h+var_1130]
0x18001096c  mov     [rbp+10D0h+var_111C], r13d
0x180010970  mov     [rbp+10D0h+var_10B0], rax
0x180010974  lea     rax, [rbp+10D0h+var_1128]
0x180010978  mov     [rbp+10D0h+var_10A8], rax
0x18001097c  lea     rax, [rsp+11D0h+var_1170]
0x180010981  mov     [rbp+10D0h+var_10A0], rax
0x180010985  lea     rax, [rbp+10D0h+var_10B8]
0x180010989  mov     [rbp+10D0h+var_1050], rax
0x180010990  mov     rax, [rdi+18h]
0x180010994  add     rax, 0Ah
0x180010998  mov     [rbp+10D0h+var_1118], r13w
0x18001099d  mov     [rsp+11D0h+var_1190], rax
0x1800109a2  movzx   eax, word ptr [rdi+2]
0x1800109a6  mov     [rbp+10D0h+var_1120], ax
0x1800109aa  mov     al, [rdi+4]
0x1800109ad  mov     [rbp+10D0h+var_111E], al
0x1800109b0  movzx   eax, word ptr [rdi+6]
0x1800109b4  mov     [rbp+10D0h+var_1100], ax
0x1800109b8  mov     al, [rdi+8]
0x1800109bb  mov     [rbp+10D0h+var_10FE], al
0x1800109be  movdqu  [rbp+10D0h+var_1110], xmm0
0x1800109c3  mov     [rbp+10D0h+var_10FC], r13d
0x1800109c7  mov     [rbp+10D0h+var_10F8], r13w
0x1800109cc  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800109d1  jmp     loc_180010A6A
0x1800109d6  mov     ebx, r13d
0x1800109d9  cmp     [rbp+10D0h+var_111C], r13d
0x1800109dd  jbe     loc_180010A6A
0x1800109e3  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800109e7  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800109ec  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800109f0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800109f5  test    al, al
0x1800109f7  jz      short loc_180010A6A
0x1800109f9  mov     eax, [rbp+10D0h+var_10FC]
0x1800109fc  mov     rcx, [rbp+10D0h+var_1050]; this
0x180010a03  mov     [rsp+11D0h+var_1180], eax
0x180010a07  movzx   eax, [rbp+10D0h+var_10F8]
0x180010a0b  mov     [rbp+10D0h+var_10E0], rax
0x180010a0f  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180010a13  mov     [rbp+10D0h+var_10D8], rax
0x180010a17  movzx   eax, [rbp+10D0h+var_1118]
0x180010a1b  mov     [rbp+10D0h+var_10D0], rax
0x180010a1f  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x180010a23  mov     [rbp+10D0h+var_10C8], rax
0x180010a27  test    rcx, rcx
0x180010a2a  jz      loc_180010BA3
0x180010a30  mov     rax, [rcx]
0x180010a33  lea     rdx, [rsp+11D0h+var_1180]
0x180010a38  mov     [rsp+11D0h+var_11A8], rdx
0x180010a3d  lea     r9, [rbp+10D0h+var_10D8]
0x180010a41  lea     rdx, [rbp+10D0h+var_10E0]
0x180010a45  mov     [rsp+11D0h+var_11B0], rdx
0x180010a4a  lea     r8, [rbp+10D0h+var_10D0]
0x180010a4e  mov     rax, [rax+20h]
0x180010a52  lea     rdx, [rbp+10D0h+var_10C8]
0x180010a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a5b  test    al, al
0x180010a5d  jz      short loc_180010AD7
0x180010a5f  inc     ebx
0x180010a61  cmp     ebx, [rbp+10D0h+var_111C]
0x180010a64  jb      loc_1800109E3
0x180010a6a  mov     r8, [rdi+20h]; unsigned __int8 *
0x180010a6e  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180010a73  lea     rcx, [rbp+10D0h+var_1120]; this
0x180010a77  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180010a7c  test    al, al
0x180010a7e  jnz     loc_1800109D6
0x180010a84  mov     rcx, [rbp+10D0h+var_1050]
0x180010a8b  test    rcx, rcx
0x180010a8e  jz      short loc_180010A9C
0x180010a90  mov     rax, [rcx]
0x180010a93  mov     rax, [rax+18h]
0x180010a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a9c  mov     bl, 1
0x180010a9e  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x180010aa2  jz      short loc_180010B16
0x180010aa4  mov     rdx, [rsp+11D0h+var_1158]
0x180010aa9  mov     rcx, r14
0x180010aac  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180010ab0  mov     eax, [rsp+11D0h+var_1188]
0x180010ab4  sub     r8d, edx
0x180010ab7  mov     [rsp+11D0h+var_11A0], 1
0x180010abf  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180010ac3  call    wil_details_NtUpdateWnfStateData
0x180010ac8  cmp     eax, 0C0000001h
0x180010acd  jnz     short loc_180010AF4
0x180010acf  inc     r15
0x180010ad2  mov     bl, r13b
0x180010ad5  jmp     short loc_180010B22
0x180010ad7  mov     rcx, [rbp+10D0h+var_1050]
0x180010ade  test    rcx, rcx
0x180010ae1  jz      short loc_180010AEF
0x180010ae3  mov     rax, [rcx]
0x180010ae6  mov     rax, [rax+18h]
0x180010aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aef  mov     bl, r13b
0x180010af2  jmp     short loc_180010A9E
0x180010af4  test    eax, eax
0x180010af6  jz      short loc_180010B16
0x180010af8  mov     rdx, [rsp+11D0h+var_1158]
0x180010afd  mov     rcx, r14
0x180010b00  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180010b04  sub     r8d, edx
0x180010b07  mov     [rsp+11D0h+var_11A0], r13d
0x180010b0c  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x180010b11  call    wil_details_NtUpdateWnfStateData
0x180010b16  mov     rax, [rbp+10D0h+var_1130]
0x180010b1a  add     r14, 8
0x180010b1e  mov     [rbp+10D0h+var_1128], rax
0x180010b22  mov     rsi, [rbp+10D0h+lpMem]
0x180010b26  mov     [rbp+10D0h+lpMem], r13
0x180010b2a  test    rsi, rsi
0x180010b2d  jz      short loc_180010B43
0x180010b2f  call    cs:__imp_GetProcessHeap
0x180010b35  mov     r8, rsi; lpMem
0x180010b38  xor     edx, edx; dwFlags
0x180010b3a  mov     rcx, rax; hHeap
0x180010b3d  call    cs:__imp_HeapFree
0x180010b43  test    bl, bl
0x180010b45  jnz     short loc_180010B79
0x180010b47  cmp     r14, r12
0x180010b4a  jnb     short loc_180010B79
0x180010b4c  cmp     r15, 32h ; '2'
0x180010b50  jb      loc_180010826
0x180010b56  jmp     short loc_180010B79
0x180010b58  mov     rbx, [rbp+10D0h+lpMem]
0x180010b5c  mov     [rbp+10D0h+lpMem], r13
0x180010b60  test    rbx, rbx
0x180010b63  jz      short loc_180010B79
0x180010b65  call    cs:__imp_GetProcessHeap
0x180010b6b  mov     r8, rbx; lpMem
0x180010b6e  xor     edx, edx; dwFlags
0x180010b70  mov     rcx, rax; hHeap
0x180010b73  call    cs:__imp_HeapFree
0x180010b79  mov     rcx, [rbp+10D0h+var_40]
0x180010b80  xor     rcx, rsp; StackCookie
0x180010b83  call    __security_check_cookie
0x180010b88  mov     rbx, [rsp+11D0h+arg_8]
0x180010b90  add     rsp, 11A0h
0x180010b97  pop     r15
0x180010b99  pop     r14
0x180010b9b  pop     r13
0x180010b9d  pop     r12
0x180010b9f  pop     rdi
0x180010ba0  pop     rsi
0x180010ba1  pop     rbp
0x180010ba2  retn
0x180010ba3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
