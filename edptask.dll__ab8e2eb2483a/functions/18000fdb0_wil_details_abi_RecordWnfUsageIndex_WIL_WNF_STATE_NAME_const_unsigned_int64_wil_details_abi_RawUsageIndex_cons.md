# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000fdb0`
- end: `0x180010187`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f358`

## callees

- `0x180006790`
- `0x18000ed68`
- `0x18000f268`
- `0x18000fdb0`
- `0x180010610`
- `0x180012ca0`
- `0x180013410`
- `0x1800134d0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fe8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fe8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fea6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fea6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001011a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010151`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001011a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010151`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001010c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010143`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001010c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010143`

## string_xrefs

- `0x18000fe88`: `ntdll.dll`

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
0x18000fdb0  mov     [rsp-8+arg_8], rbx
0x18000fdb5  push    rbp
0x18000fdb6  push    rsi
0x18000fdb7  push    rdi
0x18000fdb8  push    r12
0x18000fdba  push    r13
0x18000fdbc  push    r14
0x18000fdbe  push    r15
0x18000fdc0  lea     rbp, [rsp-10A0h]
0x18000fdc8  mov     eax, 11A0h
0x18000fdcd  call    _alloca_probe
0x18000fdd2  sub     rsp, rax
0x18000fdd5  mov     rax, cs:__security_cookie
0x18000fddc  xor     rax, rsp
0x18000fddf  mov     [rbp+10D0h+var_40], rax
0x18000fde6  mov     rbx, r8
0x18000fde9  mov     r14, rcx
0x18000fdec  lea     r12, [rcx+rdx*8]
0x18000fdf0  xor     r13d, r13d
0x18000fdf3  mov     r15d, r13d
0x18000fdf6  mov     [rbp+10D0h+var_1128], r13
0x18000fdfa  mov     cl, [rbx+8]
0x18000fdfd  movzx   edx, word ptr [rbx+6]
0x18000fe01  movzx   eax, word ptr [rbx]
0x18000fe04  mov     [rsp+11D0h+var_1170], ax
0x18000fe09  movzx   eax, word ptr [rbx+2]
0x18000fe0d  mov     [rsp+11D0h+var_116E], ax
0x18000fe12  mov     al, [rbx+4]
0x18000fe15  mov     [rsp+11D0h+var_116C], al
0x18000fe19  mov     [rsp+11D0h+var_116A], dx
0x18000fe1e  mov     [rsp+11D0h+var_1168], cl
0x18000fe22  test    dx, dx
0x18000fe25  jz      short loc_18000FE44
0x18000fe27  mov     eax, edx
0x18000fe29  cmp     cl, 1
0x18000fe2c  jnz     short loc_18000FE34
0x18000fe2e  add     rax, 2
0x18000fe32  jmp     short loc_18000FE3D
0x18000fe34  cmp     cl, 2
0x18000fe37  jnz     short loc_18000FE3D
0x18000fe39  add     rax, 4
0x18000fe3d  mov     [rsp+11D0h+var_1160], rax
0x18000fe42  jmp     short loc_18000FE49
0x18000fe44  mov     [rsp+11D0h+var_1160], r13
0x18000fe49  mov     [rsp+11D0h+var_1158], r13
0x18000fe4e  xorps   xmm0, xmm0
0x18000fe51  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000fe56  mov     [rbp+10D0h+lpMem], r13
0x18000fe5a  mov     [rbp+10D0h+var_1138], r13w
0x18000fe5f  mov     [rbp+10D0h+var_1136], r13b
0x18000fe63  mov     [rsp+11D0h+var_1188], r13d
0x18000fe68  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000fe70  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000fe77  test    rax, rax
0x18000fe7a  jnz     short loc_18000FEBF
0x18000fe7c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fe83  test    rax, rax
0x18000fe86  jnz     short loc_18000FE9C
0x18000fe88  lea     rcx, ModuleName; "ntdll.dll"
0x18000fe8f  call    cs:__imp_GetModuleHandleW
0x18000fe95  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fe9c  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000fea3  mov     rcx, rax; hModule
0x18000fea6  call    cs:__imp_GetProcAddress
0x18000feac  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000feb3  test    rax, rax
0x18000feb6  jnz     short loc_18000FEBF
0x18000feb8  mov     edi, 0C0000139h
0x18000febd  jmp     short loc_18000FEE9
0x18000febf  lea     rcx, [rsp+11D0h+var_1190]
0x18000fec4  mov     [rsp+11D0h+var_11A8], rcx
0x18000fec9  lea     rcx, [rbp+10D0h+var_1040]
0x18000fed0  mov     [rsp+11D0h+var_11B0], rcx
0x18000fed5  lea     r9, [rsp+11D0h+var_1188]
0x18000feda  xor     r8d, r8d
0x18000fedd  xor     edx, edx
0x18000fedf  mov     rcx, r14
0x18000fee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fee7  mov     edi, eax
0x18000fee9  mov     ecx, edi; this
0x18000feeb  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000fef0  test    edi, edi
0x18000fef2  jz      short loc_18000FF02
0x18000fef4  mov     eax, r13d
0x18000fef7  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000fefb  mov     [rsp+11D0h+var_1188], r13d
0x18000ff00  jmp     short loc_18000FF06
0x18000ff02  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000ff06  mov     r8d, eax; unsigned __int64
0x18000ff09  mov     r9d, 1000h; unsigned __int64
0x18000ff0f  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000ff16  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000ff1b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000ff20  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18000ff24  jnz     loc_180010136
0x18000ff2a  mov     [rbp+10D0h+var_1130], r13
0x18000ff2e  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000ff35  mov     [rbp+10D0h+var_10B0], rax
0x18000ff39  lea     rax, [rbp+10D0h+var_1130]
0x18000ff3d  mov     [rbp+10D0h+var_10A8], rax
0x18000ff41  lea     rax, [rbp+10D0h+var_1128]
0x18000ff45  mov     [rbp+10D0h+var_10A0], rax
0x18000ff49  lea     rax, [rsp+11D0h+var_1170]
0x18000ff4e  mov     [rbp+10D0h+var_1098], rax
0x18000ff52  lea     rax, [rbp+10D0h+var_10B0]
0x18000ff56  mov     [rbp+10D0h+var_1048], rax
0x18000ff5d  lea     rax, [rbp+10D0h+var_10B8]
0x18000ff61  mov     [rbp+10D0h+var_10C0], rax
0x18000ff65  mov     rax, [rbx+18h]
0x18000ff69  add     rax, 0Ah
0x18000ff6d  mov     [rsp+11D0h+var_1190], rax
0x18000ff72  movzx   eax, word ptr [rbx+2]
0x18000ff76  mov     [rbp+10D0h+var_1120], ax
0x18000ff7a  mov     al, [rbx+4]
0x18000ff7d  mov     [rbp+10D0h+var_111E], al
0x18000ff80  mov     [rbp+10D0h+var_111C], r13d
0x18000ff84  mov     [rbp+10D0h+var_1118], r13w
0x18000ff89  xorps   xmm0, xmm0
0x18000ff8c  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000ff91  movzx   eax, word ptr [rbx+6]
0x18000ff95  mov     [rbp+10D0h+var_1100], ax
0x18000ff99  mov     al, [rbx+8]
0x18000ff9c  mov     [rbp+10D0h+var_10FE], al
0x18000ff9f  mov     [rbp+10D0h+var_10FC], r13d
0x18000ffa3  mov     [rbp+10D0h+var_10F8], r13w
0x18000ffa8  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000ffad  jmp     loc_180010046
0x18000ffb2  mov     edi, r13d
0x18000ffb5  cmp     [rbp+10D0h+var_111C], r13d
0x18000ffb9  jbe     loc_180010046
0x18000ffbf  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000ffc3  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000ffc8  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000ffcc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000ffd1  test    al, al
0x18000ffd3  jz      short loc_180010046
0x18000ffd5  mov     eax, [rbp+10D0h+var_10FC]
0x18000ffd8  mov     [rsp+11D0h+var_1180], eax
0x18000ffdc  movzx   eax, [rbp+10D0h+var_10F8]
0x18000ffe0  mov     [rbp+10D0h+var_10E0], rax
0x18000ffe4  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000ffe8  mov     [rbp+10D0h+var_10D8], rax
0x18000ffec  movzx   eax, [rbp+10D0h+var_1118]
0x18000fff0  mov     [rbp+10D0h+var_10D0], rax
0x18000fff4  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18000fff8  mov     [rbp+10D0h+var_10C8], rax
0x18000fffc  mov     rcx, [rbp+10D0h+var_1048]; this
0x180010003  test    rcx, rcx
0x180010006  jz      loc_180010181
0x18001000c  mov     rax, [rcx]
0x18001000f  lea     rdx, [rsp+11D0h+var_1180]
0x180010014  mov     [rsp+11D0h+var_11A8], rdx
0x180010019  lea     rdx, [rbp+10D0h+var_10E0]
0x18001001d  mov     [rsp+11D0h+var_11B0], rdx
0x180010022  lea     r9, [rbp+10D0h+var_10D8]
0x180010026  lea     r8, [rbp+10D0h+var_10D0]
0x18001002a  lea     rdx, [rbp+10D0h+var_10C8]
0x18001002e  mov     rax, [rax+20h]
0x180010032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010037  test    al, al
0x180010039  jz      short loc_1800100B4
0x18001003b  inc     edi
0x18001003d  cmp     edi, [rbp+10D0h+var_111C]
0x180010040  jb      loc_18000FFBF
0x180010046  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001004a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18001004f  lea     rcx, [rbp+10D0h+var_1120]; this
0x180010053  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180010058  test    al, al
0x18001005a  jnz     loc_18000FFB2
0x180010060  mov     rcx, [rbp+10D0h+var_1048]
0x180010067  test    rcx, rcx
0x18001006a  jz      short loc_180010078
0x18001006c  mov     rax, [rcx]
0x18001006f  mov     rax, [rax+18h]
0x180010073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010078  mov     dil, 1
0x18001007b  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18001007f  jz      short loc_1800100F3
0x180010081  mov     eax, [rsp+11D0h+var_1188]
0x180010085  mov     rdx, [rsp+11D0h+var_1158]
0x18001008a  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18001008e  sub     r8d, edx
0x180010091  mov     [rsp+11D0h+var_11A0], 1
0x180010099  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18001009d  mov     rcx, r14
0x1800100a0  call    wil_details_NtUpdateWnfStateData
0x1800100a5  cmp     eax, 0C0000001h
0x1800100aa  jnz     short loc_1800100D1
0x1800100ac  inc     r15
0x1800100af  mov     dil, r13b
0x1800100b2  jmp     short loc_1800100FF
0x1800100b4  mov     rcx, [rbp+10D0h+var_1048]
0x1800100bb  test    rcx, rcx
0x1800100be  jz      short loc_1800100CC
0x1800100c0  mov     rax, [rcx]
0x1800100c3  mov     rax, [rax+18h]
0x1800100c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100cc  mov     dil, r13b
0x1800100cf  jmp     short loc_18001007B
0x1800100d1  test    eax, eax
0x1800100d3  jz      short loc_1800100F3
0x1800100d5  mov     rdx, [rsp+11D0h+var_1158]
0x1800100da  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800100de  sub     r8d, edx
0x1800100e1  mov     [rsp+11D0h+var_11A0], r13d
0x1800100e6  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x1800100eb  mov     rcx, r14
0x1800100ee  call    wil_details_NtUpdateWnfStateData
0x1800100f3  add     r14, 8
0x1800100f7  mov     rax, [rbp+10D0h+var_1130]
0x1800100fb  mov     [rbp+10D0h+var_1128], rax
0x1800100ff  mov     rsi, [rbp+10D0h+lpMem]
0x180010103  mov     [rbp+10D0h+lpMem], r13
0x180010107  test    rsi, rsi
0x18001010a  jz      short loc_180010120
0x18001010c  call    cs:__imp_GetProcessHeap
0x180010112  mov     rcx, rax; hHeap
0x180010115  mov     r8, rsi; lpMem
0x180010118  xor     edx, edx; dwFlags
0x18001011a  call    cs:__imp_HeapFree
0x180010120  test    dil, dil
0x180010123  jnz     short loc_180010157
0x180010125  cmp     r14, r12
0x180010128  jnb     short loc_180010157
0x18001012a  cmp     r15, 32h ; '2'
0x18001012e  jb      loc_18000FDFA
0x180010134  jmp     short loc_180010157
0x180010136  mov     rbx, [rbp+10D0h+lpMem]
0x18001013a  mov     [rbp+10D0h+lpMem], r13
0x18001013e  test    rbx, rbx
0x180010141  jz      short loc_180010157
0x180010143  call    cs:__imp_GetProcessHeap
0x180010149  mov     rcx, rax; hHeap
0x18001014c  mov     r8, rbx; lpMem
0x18001014f  xor     edx, edx; dwFlags
0x180010151  call    cs:__imp_HeapFree
0x180010157  mov     rcx, [rbp+10D0h+var_40]
0x18001015e  xor     rcx, rsp; StackCookie
0x180010161  call    __security_check_cookie
0x180010166  mov     rbx, [rsp+11D0h+arg_8]
0x18001016e  add     rsp, 11A0h
0x180010175  pop     r15
0x180010177  pop     r14
0x180010179  pop     r13
0x18001017b  pop     r12
0x18001017d  pop     rdi
0x18001017e  pop     rsi
0x18001017f  pop     rbp
0x180010180  retn
0x180010181  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
