# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x14000badc`
- end: `0x14000beb4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14000b1bc`

## callees

- `0x1400022a0`
- `0x14000a7b4`
- `0x14000acf0`
- `0x14000badc`
- `0x14000cc24`
- `0x1400100dc`
- `0x140011008`
- `0x1400113b0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bbd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bbd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bbbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bbbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000be3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000be70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000be3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000be70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000be48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000be7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000be48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000be7e`

## string_xrefs

- `0x14000bbb5`: `ntdll.dll`

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
0x14000badc  mov     [rsp-8+arg_8], rbx
0x14000bae1  push    rbp
0x14000bae2  push    rsi
0x14000bae3  push    rdi
0x14000bae4  push    r12
0x14000bae6  push    r13
0x14000bae8  push    r14
0x14000baea  push    r15
0x14000baec  lea     rbp, [rsp-10A0h]
0x14000baf4  mov     eax, 11A0h
0x14000baf9  call    _alloca_probe
0x14000bafe  sub     rsp, rax
0x14000bb01  mov     rax, cs:__security_cookie
0x14000bb08  xor     rax, rsp
0x14000bb0b  mov     [rbp+10D0h+var_40], rax
0x14000bb12  mov     rdi, r8
0x14000bb15  mov     r14, rcx
0x14000bb18  lea     r13, [rcx+rdx*8]
0x14000bb1c  xor     r15d, r15d
0x14000bb1f  mov     r12d, r15d
0x14000bb22  mov     [rbp+10D0h+var_1128], r15
0x14000bb26  mov     cl, [rdi+8]
0x14000bb29  movzx   edx, word ptr [rdi+6]
0x14000bb2d  movzx   eax, word ptr [rdi]
0x14000bb30  mov     [rsp+11D0h+var_1170], ax
0x14000bb35  movzx   eax, word ptr [rdi+2]
0x14000bb39  mov     [rsp+11D0h+var_116E], ax
0x14000bb3e  mov     al, [rdi+4]
0x14000bb41  mov     [rsp+11D0h+var_116C], al
0x14000bb45  mov     [rsp+11D0h+var_116A], dx
0x14000bb4a  mov     [rsp+11D0h+var_1168], cl
0x14000bb4e  test    dx, dx
0x14000bb51  jz      short loc_14000BB70
0x14000bb53  mov     eax, edx
0x14000bb55  cmp     cl, 1
0x14000bb58  jnz     short loc_14000BB60
0x14000bb5a  add     rax, 2
0x14000bb5e  jmp     short loc_14000BB69
0x14000bb60  cmp     cl, 2
0x14000bb63  jnz     short loc_14000BB69
0x14000bb65  add     rax, 4
0x14000bb69  mov     [rsp+11D0h+var_1160], rax
0x14000bb6e  jmp     short loc_14000BB75
0x14000bb70  mov     [rsp+11D0h+var_1160], r15
0x14000bb75  mov     [rsp+11D0h+var_1158], r15
0x14000bb7a  xorps   xmm0, xmm0
0x14000bb7d  movdqa  [rbp+10D0h+var_1150], xmm0
0x14000bb82  mov     [rbp+10D0h+lpMem], r15
0x14000bb86  mov     [rbp+10D0h+var_1138], 0
0x14000bb8c  mov     [rbp+10D0h+var_1136], r15b
0x14000bb90  mov     [rsp+11D0h+var_1188], r15d
0x14000bb95  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x14000bb9d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000bba4  test    rax, rax
0x14000bba7  jnz     short loc_14000BBEC
0x14000bba9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bbb0  test    rax, rax
0x14000bbb3  jnz     short loc_14000BBC9
0x14000bbb5  lea     rcx, ModuleName; "ntdll.dll"
0x14000bbbc  call    cs:__imp_GetModuleHandleW
0x14000bbc2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bbc9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000bbd0  mov     rcx, rax; hModule
0x14000bbd3  call    cs:__imp_GetProcAddress
0x14000bbd9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000bbe0  test    rax, rax
0x14000bbe3  jnz     short loc_14000BBEC
0x14000bbe5  mov     ebx, 0C0000139h
0x14000bbea  jmp     short loc_14000BC16
0x14000bbec  lea     rcx, [rsp+11D0h+var_1190]
0x14000bbf1  mov     [rsp+11D0h+var_11A8], rcx
0x14000bbf6  lea     rcx, [rbp+10D0h+var_1040]
0x14000bbfd  mov     [rsp+11D0h+var_11B0], rcx
0x14000bc02  lea     r9, [rsp+11D0h+var_1188]
0x14000bc07  xor     r8d, r8d
0x14000bc0a  xor     edx, edx
0x14000bc0c  mov     rcx, r14
0x14000bc0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bc14  mov     ebx, eax
0x14000bc16  mov     ecx, ebx; this
0x14000bc18  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000bc1d  test    ebx, ebx
0x14000bc1f  jz      short loc_14000BC2F
0x14000bc21  mov     eax, r15d
0x14000bc24  mov     dword ptr [rsp+11D0h+var_1190], eax
0x14000bc28  mov     [rsp+11D0h+var_1188], r15d
0x14000bc2d  jmp     short loc_14000BC33
0x14000bc2f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x14000bc33  mov     r8d, eax; unsigned __int64
0x14000bc36  mov     r9d, 1000h; unsigned __int64
0x14000bc3c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x14000bc43  lea     rcx, [rsp+11D0h+var_1170]; this
0x14000bc48  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x14000bc4d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x14000bc51  jnz     loc_14000BE63
0x14000bc57  mov     [rbp+10D0h+var_1130], r15
0x14000bc5b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x14000bc62  mov     [rbp+10D0h+var_10B0], rax
0x14000bc66  lea     rax, [rbp+10D0h+var_1130]
0x14000bc6a  mov     [rbp+10D0h+var_10A8], rax
0x14000bc6e  lea     rax, [rbp+10D0h+var_1128]
0x14000bc72  mov     [rbp+10D0h+var_10A0], rax
0x14000bc76  lea     rax, [rsp+11D0h+var_1170]
0x14000bc7b  mov     [rbp+10D0h+var_1098], rax
0x14000bc7f  lea     rax, [rbp+10D0h+var_10B0]
0x14000bc83  mov     [rbp+10D0h+var_1048], rax
0x14000bc8a  lea     rax, [rbp+10D0h+var_10B8]
0x14000bc8e  mov     [rbp+10D0h+var_10C0], rax
0x14000bc92  mov     rax, [rdi+18h]
0x14000bc96  add     rax, 0Ah
0x14000bc9a  mov     [rsp+11D0h+var_1190], rax
0x14000bc9f  movzx   eax, word ptr [rdi+2]
0x14000bca3  mov     [rbp+10D0h+var_1120], ax
0x14000bca7  mov     al, [rdi+4]
0x14000bcaa  mov     [rbp+10D0h+var_111E], al
0x14000bcad  mov     [rbp+10D0h+var_111C], r15d
0x14000bcb1  mov     [rbp+10D0h+var_1118], r15w
0x14000bcb6  xorps   xmm0, xmm0
0x14000bcb9  movdqu  [rbp+10D0h+var_1110], xmm0
0x14000bcbe  movzx   eax, word ptr [rdi+6]
0x14000bcc2  mov     [rbp+10D0h+var_1100], ax
0x14000bcc6  mov     al, [rdi+8]
0x14000bcc9  mov     [rbp+10D0h+var_10FE], al
0x14000bccc  mov     [rbp+10D0h+var_10FC], r15d
0x14000bcd0  mov     [rbp+10D0h+var_10F8], r15w
0x14000bcd5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14000bcda  jmp     loc_14000BD72
0x14000bcdf  mov     ebx, r15d
0x14000bce2  mov     esi, [rbp+10D0h+var_111C]
0x14000bce5  test    esi, esi
0x14000bce7  jz      loc_14000BD72
0x14000bced  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x14000bcf1  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000bcf5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000bcfa  lea     rcx, [rbp+10D0h+var_1100]; this
0x14000bcfe  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000bd03  test    al, al
0x14000bd05  jz      short loc_14000BD6F
0x14000bd07  mov     eax, [rbp+10D0h+var_10FC]
0x14000bd0a  mov     [rsp+11D0h+var_1180], eax
0x14000bd0e  movzx   eax, [rbp+10D0h+var_10F8]
0x14000bd12  mov     [rbp+10D0h+var_10E0], rax
0x14000bd16  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14000bd1a  mov     [rbp+10D0h+var_10D8], rax
0x14000bd1e  movzx   eax, [rbp+10D0h+var_1118]
0x14000bd22  mov     [rbp+10D0h+var_10D0], rax
0x14000bd26  mov     [rbp+10D0h+var_10C8], r15
0x14000bd2a  mov     rcx, [rbp+10D0h+var_1048]; this
0x14000bd31  test    rcx, rcx
0x14000bd34  jz      loc_14000BEAE
0x14000bd3a  mov     rax, [rcx]
0x14000bd3d  lea     rdx, [rsp+11D0h+var_1180]
0x14000bd42  mov     [rsp+11D0h+var_11A8], rdx
0x14000bd47  lea     rdx, [rbp+10D0h+var_10E0]
0x14000bd4b  mov     [rsp+11D0h+var_11B0], rdx
0x14000bd50  lea     r9, [rbp+10D0h+var_10D8]
0x14000bd54  lea     r8, [rbp+10D0h+var_10D0]
0x14000bd58  lea     rdx, [rbp+10D0h+var_10C8]
0x14000bd5c  mov     rax, [rax+20h]
0x14000bd60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd65  test    al, al
0x14000bd67  jz      short loc_14000BDDF
0x14000bd69  inc     ebx
0x14000bd6b  cmp     ebx, esi
0x14000bd6d  jb      short loc_14000BCF1
0x14000bd6f  xor     r15d, r15d
0x14000bd72  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000bd76  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000bd7b  lea     rcx, [rbp+10D0h+var_1120]; this
0x14000bd7f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000bd84  test    al, al
0x14000bd86  jnz     loc_14000BCDF
0x14000bd8c  mov     rcx, [rbp+10D0h+var_1048]
0x14000bd93  test    rcx, rcx
0x14000bd96  jz      short loc_14000BDA4
0x14000bd98  mov     rax, [rcx]
0x14000bd9b  mov     rax, [rax+18h]
0x14000bd9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bda4  mov     bl, 1
0x14000bda6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x14000bdaa  jz      short loc_14000BE21
0x14000bdac  mov     eax, [rsp+11D0h+var_1188]
0x14000bdb0  mov     rdx, [rsp+11D0h+var_1158]
0x14000bdb5  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000bdb9  sub     r8d, edx
0x14000bdbc  mov     [rsp+11D0h+var_11A0], 1
0x14000bdc4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x14000bdc8  mov     rcx, r14
0x14000bdcb  call    wil_details_NtUpdateWnfStateData
0x14000bdd0  cmp     eax, 0C0000001h
0x14000bdd5  jnz     short loc_14000BDFF
0x14000bdd7  inc     r12
0x14000bdda  mov     bl, r15b
0x14000bddd  jmp     short loc_14000BE2D
0x14000bddf  mov     rcx, [rbp+10D0h+var_1048]
0x14000bde6  xor     r15d, r15d
0x14000bde9  test    rcx, rcx
0x14000bdec  jz      short loc_14000BDFA
0x14000bdee  mov     rax, [rcx]
0x14000bdf1  mov     rax, [rax+18h]
0x14000bdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bdfa  mov     bl, r15b
0x14000bdfd  jmp     short loc_14000BDA6
0x14000bdff  test    eax, eax
0x14000be01  jz      short loc_14000BE21
0x14000be03  mov     rdx, [rsp+11D0h+var_1158]
0x14000be08  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000be0c  sub     r8d, edx
0x14000be0f  mov     [rsp+11D0h+var_11A0], r15d
0x14000be14  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x14000be19  mov     rcx, r14
0x14000be1c  call    wil_details_NtUpdateWnfStateData
0x14000be21  add     r14, 8
0x14000be25  mov     rax, [rbp+10D0h+var_1130]
0x14000be29  mov     [rbp+10D0h+var_1128], rax
0x14000be2d  mov     rsi, [rbp+10D0h+lpMem]
0x14000be31  mov     [rbp+10D0h+lpMem], r15
0x14000be35  test    rsi, rsi
0x14000be38  jz      short loc_14000BE4E
0x14000be3a  call    cs:__imp_GetProcessHeap
0x14000be40  mov     rcx, rax; hHeap
0x14000be43  mov     r8, rsi; lpMem
0x14000be46  xor     edx, edx; dwFlags
0x14000be48  call    cs:__imp_HeapFree
0x14000be4e  test    bl, bl
0x14000be50  jnz     short loc_14000BE84
0x14000be52  cmp     r14, r13
0x14000be55  jnb     short loc_14000BE84
0x14000be57  cmp     r12, 32h ; '2'
0x14000be5b  jb      loc_14000BB26
0x14000be61  jmp     short loc_14000BE84
0x14000be63  mov     rbx, [rbp+10D0h+lpMem]
0x14000be67  mov     [rbp+10D0h+lpMem], r15
0x14000be6b  test    rbx, rbx
0x14000be6e  jz      short loc_14000BE84
0x14000be70  call    cs:__imp_GetProcessHeap
0x14000be76  mov     rcx, rax; hHeap
0x14000be79  mov     r8, rbx; lpMem
0x14000be7c  xor     edx, edx; dwFlags
0x14000be7e  call    cs:__imp_HeapFree
0x14000be84  mov     rcx, [rbp+10D0h+var_40]
0x14000be8b  xor     rcx, rsp; StackCookie
0x14000be8e  call    __security_check_cookie
0x14000be93  mov     rbx, [rsp+11D0h+arg_8]
0x14000be9b  add     rsp, 11A0h
0x14000bea2  pop     r15
0x14000bea4  pop     r14
0x14000bea6  pop     r13
0x14000bea8  pop     r12
0x14000beaa  pop     rdi
0x14000beab  pop     rsi
0x14000beac  pop     rbp
0x14000bead  retn
0x14000beae  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
