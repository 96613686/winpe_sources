# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18001598c`
- end: `0x180015d63`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180014f28`

## callees

- `0x18000863c`
- `0x180013d7c`
- `0x180014e38`
- `0x18001598c`
- `0x180017c7c`
- `0x180022cd0`
- `0x180033ed0`
- `0x180033f90`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015a6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015a6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015a82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015a82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015cf6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015d2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015cf6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015d2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015ce8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015d1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015ce8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015d1f`

## string_xrefs

- `0x180015a64`: `ntdll.dll`

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
0x18001598c  mov     [rsp-8+arg_8], rbx
0x180015991  push    rbp
0x180015992  push    rsi
0x180015993  push    rdi
0x180015994  push    r12
0x180015996  push    r13
0x180015998  push    r14
0x18001599a  push    r15
0x18001599c  lea     rbp, [rsp-10A0h]
0x1800159a4  mov     eax, 11A0h
0x1800159a9  call    _alloca_probe
0x1800159ae  sub     rsp, rax
0x1800159b1  mov     rax, cs:__security_cookie
0x1800159b8  xor     rax, rsp
0x1800159bb  mov     [rbp+10D0h+var_40], rax
0x1800159c2  mov     rbx, r8
0x1800159c5  mov     r14, rcx
0x1800159c8  lea     r12, [rcx+rdx*8]
0x1800159cc  xor     r13d, r13d
0x1800159cf  mov     r15d, r13d
0x1800159d2  mov     [rbp+10D0h+var_1128], r13
0x1800159d6  mov     cl, [rbx+8]
0x1800159d9  movzx   edx, word ptr [rbx+6]
0x1800159dd  movzx   eax, word ptr [rbx]
0x1800159e0  mov     [rsp+11D0h+var_1170], ax
0x1800159e5  movzx   eax, word ptr [rbx+2]
0x1800159e9  mov     [rsp+11D0h+var_116E], ax
0x1800159ee  mov     al, [rbx+4]
0x1800159f1  mov     [rsp+11D0h+var_116C], al
0x1800159f5  mov     [rsp+11D0h+var_116A], dx
0x1800159fa  mov     [rsp+11D0h+var_1168], cl
0x1800159fe  test    dx, dx
0x180015a01  jz      short loc_180015A20
0x180015a03  mov     eax, edx
0x180015a05  cmp     cl, 1
0x180015a08  jnz     short loc_180015A10
0x180015a0a  add     rax, 2
0x180015a0e  jmp     short loc_180015A19
0x180015a10  cmp     cl, 2
0x180015a13  jnz     short loc_180015A19
0x180015a15  add     rax, 4
0x180015a19  mov     [rsp+11D0h+var_1160], rax
0x180015a1e  jmp     short loc_180015A25
0x180015a20  mov     [rsp+11D0h+var_1160], r13
0x180015a25  mov     [rsp+11D0h+var_1158], r13
0x180015a2a  xorps   xmm0, xmm0
0x180015a2d  movdqa  [rbp+10D0h+var_1150], xmm0
0x180015a32  mov     [rbp+10D0h+lpMem], r13
0x180015a36  mov     [rbp+10D0h+var_1138], r13w
0x180015a3b  mov     [rbp+10D0h+var_1136], r13b
0x180015a3f  mov     [rsp+11D0h+var_1188], r13d
0x180015a44  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180015a4c  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180015a53  test    rax, rax
0x180015a56  jnz     short loc_180015A9B
0x180015a58  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015a5f  test    rax, rax
0x180015a62  jnz     short loc_180015A78
0x180015a64  lea     rcx, ModuleName; "ntdll.dll"
0x180015a6b  call    cs:__imp_GetModuleHandleW
0x180015a71  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015a78  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180015a7f  mov     rcx, rax; hModule
0x180015a82  call    cs:__imp_GetProcAddress
0x180015a88  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180015a8f  test    rax, rax
0x180015a92  jnz     short loc_180015A9B
0x180015a94  mov     edi, 0C0000139h
0x180015a99  jmp     short loc_180015AC5
0x180015a9b  lea     rcx, [rsp+11D0h+var_1190]
0x180015aa0  mov     [rsp+11D0h+var_11A8], rcx
0x180015aa5  lea     rcx, [rbp+10D0h+var_1040]
0x180015aac  mov     [rsp+11D0h+var_11B0], rcx
0x180015ab1  lea     r9, [rsp+11D0h+var_1188]
0x180015ab6  xor     r8d, r8d
0x180015ab9  xor     edx, edx
0x180015abb  mov     rcx, r14
0x180015abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ac3  mov     edi, eax
0x180015ac5  mov     ecx, edi; this
0x180015ac7  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180015acc  test    edi, edi
0x180015ace  jz      short loc_180015ADE
0x180015ad0  mov     eax, r13d
0x180015ad3  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180015ad7  mov     [rsp+11D0h+var_1188], r13d
0x180015adc  jmp     short loc_180015AE2
0x180015ade  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180015ae2  mov     r8d, eax; unsigned __int64
0x180015ae5  mov     r9d, 1000h; unsigned __int64
0x180015aeb  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180015af2  lea     rcx, [rsp+11D0h+var_1170]; this
0x180015af7  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180015afc  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x180015b00  jnz     loc_180015D12
0x180015b06  mov     [rbp+10D0h+var_1130], r13
0x180015b0a  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180015b11  mov     [rbp+10D0h+var_10B0], rax
0x180015b15  lea     rax, [rbp+10D0h+var_1130]
0x180015b19  mov     [rbp+10D0h+var_10A8], rax
0x180015b1d  lea     rax, [rbp+10D0h+var_1128]
0x180015b21  mov     [rbp+10D0h+var_10A0], rax
0x180015b25  lea     rax, [rsp+11D0h+var_1170]
0x180015b2a  mov     [rbp+10D0h+var_1098], rax
0x180015b2e  lea     rax, [rbp+10D0h+var_10B0]
0x180015b32  mov     [rbp+10D0h+var_1048], rax
0x180015b39  lea     rax, [rbp+10D0h+var_10B8]
0x180015b3d  mov     [rbp+10D0h+var_10C0], rax
0x180015b41  mov     rax, [rbx+18h]
0x180015b45  add     rax, 0Ah
0x180015b49  mov     [rsp+11D0h+var_1190], rax
0x180015b4e  movzx   eax, word ptr [rbx+2]
0x180015b52  mov     [rbp+10D0h+var_1120], ax
0x180015b56  mov     al, [rbx+4]
0x180015b59  mov     [rbp+10D0h+var_111E], al
0x180015b5c  mov     [rbp+10D0h+var_111C], r13d
0x180015b60  mov     [rbp+10D0h+var_1118], r13w
0x180015b65  xorps   xmm0, xmm0
0x180015b68  movdqu  [rbp+10D0h+var_1110], xmm0
0x180015b6d  movzx   eax, word ptr [rbx+6]
0x180015b71  mov     [rbp+10D0h+var_1100], ax
0x180015b75  mov     al, [rbx+8]
0x180015b78  mov     [rbp+10D0h+var_10FE], al
0x180015b7b  mov     [rbp+10D0h+var_10FC], r13d
0x180015b7f  mov     [rbp+10D0h+var_10F8], r13w
0x180015b84  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180015b89  jmp     loc_180015C22
0x180015b8e  mov     edi, r13d
0x180015b91  cmp     [rbp+10D0h+var_111C], r13d
0x180015b95  jbe     loc_180015C22
0x180015b9b  mov     r8, [rbx+20h]; unsigned __int8 *
0x180015b9f  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180015ba4  lea     rcx, [rbp+10D0h+var_1100]; this
0x180015ba8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180015bad  test    al, al
0x180015baf  jz      short loc_180015C22
0x180015bb1  mov     eax, [rbp+10D0h+var_10FC]
0x180015bb4  mov     [rsp+11D0h+var_1180], eax
0x180015bb8  movzx   eax, [rbp+10D0h+var_10F8]
0x180015bbc  mov     [rbp+10D0h+var_10E0], rax
0x180015bc0  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180015bc4  mov     [rbp+10D0h+var_10D8], rax
0x180015bc8  movzx   eax, [rbp+10D0h+var_1118]
0x180015bcc  mov     [rbp+10D0h+var_10D0], rax
0x180015bd0  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x180015bd4  mov     [rbp+10D0h+var_10C8], rax
0x180015bd8  mov     rcx, [rbp+10D0h+var_1048]; this
0x180015bdf  test    rcx, rcx
0x180015be2  jz      loc_180015D5D
0x180015be8  mov     rax, [rcx]
0x180015beb  lea     rdx, [rsp+11D0h+var_1180]
0x180015bf0  mov     [rsp+11D0h+var_11A8], rdx
0x180015bf5  lea     rdx, [rbp+10D0h+var_10E0]
0x180015bf9  mov     [rsp+11D0h+var_11B0], rdx
0x180015bfe  lea     r9, [rbp+10D0h+var_10D8]
0x180015c02  lea     r8, [rbp+10D0h+var_10D0]
0x180015c06  lea     rdx, [rbp+10D0h+var_10C8]
0x180015c0a  mov     rax, [rax+20h]
0x180015c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c13  test    al, al
0x180015c15  jz      short loc_180015C90
0x180015c17  inc     edi
0x180015c19  cmp     edi, [rbp+10D0h+var_111C]
0x180015c1c  jb      loc_180015B9B
0x180015c22  mov     r8, [rbx+20h]; unsigned __int8 *
0x180015c26  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180015c2b  lea     rcx, [rbp+10D0h+var_1120]; this
0x180015c2f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180015c34  test    al, al
0x180015c36  jnz     loc_180015B8E
0x180015c3c  mov     rcx, [rbp+10D0h+var_1048]
0x180015c43  test    rcx, rcx
0x180015c46  jz      short loc_180015C54
0x180015c48  mov     rax, [rcx]
0x180015c4b  mov     rax, [rax+18h]
0x180015c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c54  mov     dil, 1
0x180015c57  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x180015c5b  jz      short loc_180015CCF
0x180015c5d  mov     eax, [rsp+11D0h+var_1188]
0x180015c61  mov     rdx, [rsp+11D0h+var_1158]
0x180015c66  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180015c6a  sub     r8d, edx
0x180015c6d  mov     [rsp+11D0h+var_11A0], 1
0x180015c75  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180015c79  mov     rcx, r14
0x180015c7c  call    wil_details_NtUpdateWnfStateData
0x180015c81  cmp     eax, 0C0000001h
0x180015c86  jnz     short loc_180015CAD
0x180015c88  inc     r15
0x180015c8b  mov     dil, r13b
0x180015c8e  jmp     short loc_180015CDB
0x180015c90  mov     rcx, [rbp+10D0h+var_1048]
0x180015c97  test    rcx, rcx
0x180015c9a  jz      short loc_180015CA8
0x180015c9c  mov     rax, [rcx]
0x180015c9f  mov     rax, [rax+18h]
0x180015ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ca8  mov     dil, r13b
0x180015cab  jmp     short loc_180015C57
0x180015cad  test    eax, eax
0x180015caf  jz      short loc_180015CCF
0x180015cb1  mov     rdx, [rsp+11D0h+var_1158]
0x180015cb6  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180015cba  sub     r8d, edx
0x180015cbd  mov     [rsp+11D0h+var_11A0], r13d
0x180015cc2  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x180015cc7  mov     rcx, r14
0x180015cca  call    wil_details_NtUpdateWnfStateData
0x180015ccf  add     r14, 8
0x180015cd3  mov     rax, [rbp+10D0h+var_1130]
0x180015cd7  mov     [rbp+10D0h+var_1128], rax
0x180015cdb  mov     rsi, [rbp+10D0h+lpMem]
0x180015cdf  mov     [rbp+10D0h+lpMem], r13
0x180015ce3  test    rsi, rsi
0x180015ce6  jz      short loc_180015CFC
0x180015ce8  call    cs:__imp_GetProcessHeap
0x180015cee  mov     rcx, rax; hHeap
0x180015cf1  mov     r8, rsi; lpMem
0x180015cf4  xor     edx, edx; dwFlags
0x180015cf6  call    cs:__imp_HeapFree
0x180015cfc  test    dil, dil
0x180015cff  jnz     short loc_180015D33
0x180015d01  cmp     r14, r12
0x180015d04  jnb     short loc_180015D33
0x180015d06  cmp     r15, 32h ; '2'
0x180015d0a  jb      loc_1800159D6
0x180015d10  jmp     short loc_180015D33
0x180015d12  mov     rbx, [rbp+10D0h+lpMem]
0x180015d16  mov     [rbp+10D0h+lpMem], r13
0x180015d1a  test    rbx, rbx
0x180015d1d  jz      short loc_180015D33
0x180015d1f  call    cs:__imp_GetProcessHeap
0x180015d25  mov     rcx, rax; hHeap
0x180015d28  mov     r8, rbx; lpMem
0x180015d2b  xor     edx, edx; dwFlags
0x180015d2d  call    cs:__imp_HeapFree
0x180015d33  mov     rcx, [rbp+10D0h+var_40]
0x180015d3a  xor     rcx, rsp; StackCookie
0x180015d3d  call    __security_check_cookie
0x180015d42  mov     rbx, [rsp+11D0h+arg_8]
0x180015d4a  add     rsp, 11A0h
0x180015d51  pop     r15
0x180015d53  pop     r14
0x180015d55  pop     r13
0x180015d57  pop     r12
0x180015d59  pop     rdi
0x180015d5a  pop     rsi
0x180015d5b  pop     rbp
0x180015d5c  retn
0x180015d5d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
