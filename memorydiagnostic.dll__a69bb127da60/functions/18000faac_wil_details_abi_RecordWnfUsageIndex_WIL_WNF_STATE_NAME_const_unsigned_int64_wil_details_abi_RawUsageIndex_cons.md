# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000faac`
- end: `0x18000fe84`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ef90`

## callees

- `0x180002e50`
- `0x18000e544`
- `0x18000ee48`
- `0x18000faac`
- `0x180010e6c`
- `0x1800155f4`
- `0x180019c48`
- `0x180020830`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000fb8c`
- `KERNEL32!GetModuleHandleW` at `0x18000fb8c`
- `KERNEL32!GetProcessHeap` at `0x18000fe0a`
- `KERNEL32!GetProcessHeap` at `0x18000fe40`
- `KERNEL32!GetProcessHeap` at `0x18000fe0a`
- `KERNEL32!GetProcessHeap` at `0x18000fe40`
- `KERNEL32!GetProcAddress` at `0x18000fba3`
- `KERNEL32!GetProcAddress` at `0x18000fba3`
- `KERNEL32!HeapFree` at `0x18000fe18`
- `KERNEL32!HeapFree` at `0x18000fe4e`
- `KERNEL32!HeapFree` at `0x18000fe18`
- `KERNEL32!HeapFree` at `0x18000fe4e`

## string_xrefs

- `0x18000fb85`: `ntdll.dll`

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
0x18000faac  mov     [rsp-8+arg_8], rbx
0x18000fab1  push    rbp
0x18000fab2  push    rsi
0x18000fab3  push    rdi
0x18000fab4  push    r12
0x18000fab6  push    r13
0x18000fab8  push    r14
0x18000faba  push    r15
0x18000fabc  lea     rbp, [rsp-10A0h]
0x18000fac4  mov     eax, 11A0h
0x18000fac9  call    _alloca_probe
0x18000face  sub     rsp, rax
0x18000fad1  mov     rax, cs:__security_cookie
0x18000fad8  xor     rax, rsp
0x18000fadb  mov     [rbp+10D0h+var_40], rax
0x18000fae2  mov     rdi, r8
0x18000fae5  mov     r14, rcx
0x18000fae8  lea     r13, [rcx+rdx*8]
0x18000faec  xor     r15d, r15d
0x18000faef  mov     r12d, r15d
0x18000faf2  mov     [rbp+10D0h+var_1128], r15
0x18000faf6  mov     cl, [rdi+8]
0x18000faf9  movzx   edx, word ptr [rdi+6]
0x18000fafd  movzx   eax, word ptr [rdi]
0x18000fb00  mov     [rsp+11D0h+var_1170], ax
0x18000fb05  movzx   eax, word ptr [rdi+2]
0x18000fb09  mov     [rsp+11D0h+var_116E], ax
0x18000fb0e  mov     al, [rdi+4]
0x18000fb11  mov     [rsp+11D0h+var_116C], al
0x18000fb15  mov     [rsp+11D0h+var_116A], dx
0x18000fb1a  mov     [rsp+11D0h+var_1168], cl
0x18000fb1e  test    dx, dx
0x18000fb21  jz      short loc_18000FB40
0x18000fb23  mov     eax, edx
0x18000fb25  cmp     cl, 1
0x18000fb28  jnz     short loc_18000FB30
0x18000fb2a  add     rax, 2
0x18000fb2e  jmp     short loc_18000FB39
0x18000fb30  cmp     cl, 2
0x18000fb33  jnz     short loc_18000FB39
0x18000fb35  add     rax, 4
0x18000fb39  mov     [rsp+11D0h+var_1160], rax
0x18000fb3e  jmp     short loc_18000FB45
0x18000fb40  mov     [rsp+11D0h+var_1160], r15
0x18000fb45  mov     [rsp+11D0h+var_1158], r15
0x18000fb4a  xorps   xmm0, xmm0
0x18000fb4d  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000fb52  mov     [rbp+10D0h+lpMem], r15
0x18000fb56  mov     [rbp+10D0h+var_1138], 0
0x18000fb5c  mov     [rbp+10D0h+var_1136], r15b
0x18000fb60  mov     [rsp+11D0h+var_1188], r15d
0x18000fb65  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000fb6d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000fb74  test    rax, rax
0x18000fb77  jnz     short loc_18000FBBC
0x18000fb79  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fb80  test    rax, rax
0x18000fb83  jnz     short loc_18000FB99
0x18000fb85  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000fb8c  call    cs:__imp_GetModuleHandleW
0x18000fb92  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fb99  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000fba0  mov     rcx, rax; hModule
0x18000fba3  call    cs:__imp_GetProcAddress
0x18000fba9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000fbb0  test    rax, rax
0x18000fbb3  jnz     short loc_18000FBBC
0x18000fbb5  mov     ebx, 0C0000139h
0x18000fbba  jmp     short loc_18000FBE6
0x18000fbbc  lea     rcx, [rsp+11D0h+var_1190]
0x18000fbc1  mov     [rsp+11D0h+var_11A8], rcx
0x18000fbc6  lea     rcx, [rbp+10D0h+var_1040]
0x18000fbcd  mov     [rsp+11D0h+var_11B0], rcx
0x18000fbd2  lea     r9, [rsp+11D0h+var_1188]
0x18000fbd7  xor     r8d, r8d
0x18000fbda  xor     edx, edx
0x18000fbdc  mov     rcx, r14
0x18000fbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbe4  mov     ebx, eax
0x18000fbe6  mov     ecx, ebx; this
0x18000fbe8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000fbed  test    ebx, ebx
0x18000fbef  jz      short loc_18000FBFF
0x18000fbf1  mov     eax, r15d
0x18000fbf4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000fbf8  mov     [rsp+11D0h+var_1188], r15d
0x18000fbfd  jmp     short loc_18000FC03
0x18000fbff  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000fc03  mov     r8d, eax; unsigned __int64
0x18000fc06  mov     r9d, 1000h; unsigned __int64
0x18000fc0c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000fc13  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000fc18  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000fc1d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000fc21  jnz     loc_18000FE33
0x18000fc27  mov     [rbp+10D0h+var_1130], r15
0x18000fc2b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000fc32  mov     [rbp+10D0h+var_10B0], rax
0x18000fc36  lea     rax, [rbp+10D0h+var_1130]
0x18000fc3a  mov     [rbp+10D0h+var_10A8], rax
0x18000fc3e  lea     rax, [rbp+10D0h+var_1128]
0x18000fc42  mov     [rbp+10D0h+var_10A0], rax
0x18000fc46  lea     rax, [rsp+11D0h+var_1170]
0x18000fc4b  mov     [rbp+10D0h+var_1098], rax
0x18000fc4f  lea     rax, [rbp+10D0h+var_10B0]
0x18000fc53  mov     [rbp+10D0h+var_1048], rax
0x18000fc5a  lea     rax, [rbp+10D0h+var_10B8]
0x18000fc5e  mov     [rbp+10D0h+var_10C0], rax
0x18000fc62  mov     rax, [rdi+18h]
0x18000fc66  add     rax, 0Ah
0x18000fc6a  mov     [rsp+11D0h+var_1190], rax
0x18000fc6f  movzx   eax, word ptr [rdi+2]
0x18000fc73  mov     [rbp+10D0h+var_1120], ax
0x18000fc77  mov     al, [rdi+4]
0x18000fc7a  mov     [rbp+10D0h+var_111E], al
0x18000fc7d  mov     [rbp+10D0h+var_111C], r15d
0x18000fc81  mov     [rbp+10D0h+var_1118], r15w
0x18000fc86  xorps   xmm0, xmm0
0x18000fc89  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000fc8e  movzx   eax, word ptr [rdi+6]
0x18000fc92  mov     [rbp+10D0h+var_1100], ax
0x18000fc96  mov     al, [rdi+8]
0x18000fc99  mov     [rbp+10D0h+var_10FE], al
0x18000fc9c  mov     [rbp+10D0h+var_10FC], r15d
0x18000fca0  mov     [rbp+10D0h+var_10F8], r15w
0x18000fca5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000fcaa  jmp     loc_18000FD42
0x18000fcaf  mov     ebx, r15d
0x18000fcb2  mov     esi, [rbp+10D0h+var_111C]
0x18000fcb5  test    esi, esi
0x18000fcb7  jz      loc_18000FD42
0x18000fcbd  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18000fcc1  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000fcc5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000fcca  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000fcce  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000fcd3  test    al, al
0x18000fcd5  jz      short loc_18000FD3F
0x18000fcd7  mov     eax, [rbp+10D0h+var_10FC]
0x18000fcda  mov     [rsp+11D0h+var_1180], eax
0x18000fcde  movzx   eax, [rbp+10D0h+var_10F8]
0x18000fce2  mov     [rbp+10D0h+var_10E0], rax
0x18000fce6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000fcea  mov     [rbp+10D0h+var_10D8], rax
0x18000fcee  movzx   eax, [rbp+10D0h+var_1118]
0x18000fcf2  mov     [rbp+10D0h+var_10D0], rax
0x18000fcf6  mov     [rbp+10D0h+var_10C8], r15
0x18000fcfa  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000fd01  test    rcx, rcx
0x18000fd04  jz      loc_18000FE7E
0x18000fd0a  mov     rax, [rcx]
0x18000fd0d  lea     rdx, [rsp+11D0h+var_1180]
0x18000fd12  mov     [rsp+11D0h+var_11A8], rdx
0x18000fd17  lea     rdx, [rbp+10D0h+var_10E0]
0x18000fd1b  mov     [rsp+11D0h+var_11B0], rdx
0x18000fd20  lea     r9, [rbp+10D0h+var_10D8]
0x18000fd24  lea     r8, [rbp+10D0h+var_10D0]
0x18000fd28  lea     rdx, [rbp+10D0h+var_10C8]
0x18000fd2c  mov     rax, [rax+20h]
0x18000fd30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd35  test    al, al
0x18000fd37  jz      short loc_18000FDAF
0x18000fd39  inc     ebx
0x18000fd3b  cmp     ebx, esi
0x18000fd3d  jb      short loc_18000FCC1
0x18000fd3f  xor     r15d, r15d
0x18000fd42  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000fd46  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000fd4b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000fd4f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000fd54  test    al, al
0x18000fd56  jnz     loc_18000FCAF
0x18000fd5c  mov     rcx, [rbp+10D0h+var_1048]
0x18000fd63  test    rcx, rcx
0x18000fd66  jz      short loc_18000FD74
0x18000fd68  mov     rax, [rcx]
0x18000fd6b  mov     rax, [rax+18h]
0x18000fd6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd74  mov     bl, 1
0x18000fd76  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000fd7a  jz      short loc_18000FDF1
0x18000fd7c  mov     eax, [rsp+11D0h+var_1188]
0x18000fd80  mov     rdx, [rsp+11D0h+var_1158]
0x18000fd85  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000fd89  sub     r8d, edx
0x18000fd8c  mov     [rsp+11D0h+var_11A0], 1
0x18000fd94  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000fd98  mov     rcx, r14
0x18000fd9b  call    wil_details_NtUpdateWnfStateData
0x18000fda0  cmp     eax, 0C0000001h
0x18000fda5  jnz     short loc_18000FDCF
0x18000fda7  inc     r12
0x18000fdaa  mov     bl, r15b
0x18000fdad  jmp     short loc_18000FDFD
0x18000fdaf  mov     rcx, [rbp+10D0h+var_1048]
0x18000fdb6  xor     r15d, r15d
0x18000fdb9  test    rcx, rcx
0x18000fdbc  jz      short loc_18000FDCA
0x18000fdbe  mov     rax, [rcx]
0x18000fdc1  mov     rax, [rax+18h]
0x18000fdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdca  mov     bl, r15b
0x18000fdcd  jmp     short loc_18000FD76
0x18000fdcf  test    eax, eax
0x18000fdd1  jz      short loc_18000FDF1
0x18000fdd3  mov     rdx, [rsp+11D0h+var_1158]
0x18000fdd8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000fddc  sub     r8d, edx
0x18000fddf  mov     [rsp+11D0h+var_11A0], r15d
0x18000fde4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000fde9  mov     rcx, r14
0x18000fdec  call    wil_details_NtUpdateWnfStateData
0x18000fdf1  add     r14, 8
0x18000fdf5  mov     rax, [rbp+10D0h+var_1130]
0x18000fdf9  mov     [rbp+10D0h+var_1128], rax
0x18000fdfd  mov     rsi, [rbp+10D0h+lpMem]
0x18000fe01  mov     [rbp+10D0h+lpMem], r15
0x18000fe05  test    rsi, rsi
0x18000fe08  jz      short loc_18000FE1E
0x18000fe0a  call    cs:__imp_GetProcessHeap
0x18000fe10  mov     rcx, rax; hHeap
0x18000fe13  mov     r8, rsi; lpMem
0x18000fe16  xor     edx, edx; dwFlags
0x18000fe18  call    cs:__imp_HeapFree
0x18000fe1e  test    bl, bl
0x18000fe20  jnz     short loc_18000FE54
0x18000fe22  cmp     r14, r13
0x18000fe25  jnb     short loc_18000FE54
0x18000fe27  cmp     r12, 32h ; '2'
0x18000fe2b  jb      loc_18000FAF6
0x18000fe31  jmp     short loc_18000FE54
0x18000fe33  mov     rbx, [rbp+10D0h+lpMem]
0x18000fe37  mov     [rbp+10D0h+lpMem], r15
0x18000fe3b  test    rbx, rbx
0x18000fe3e  jz      short loc_18000FE54
0x18000fe40  call    cs:__imp_GetProcessHeap
0x18000fe46  mov     rcx, rax; hHeap
0x18000fe49  mov     r8, rbx; lpMem
0x18000fe4c  xor     edx, edx; dwFlags
0x18000fe4e  call    cs:__imp_HeapFree
0x18000fe54  mov     rcx, [rbp+10D0h+var_40]
0x18000fe5b  xor     rcx, rsp; StackCookie
0x18000fe5e  call    __security_check_cookie
0x18000fe63  mov     rbx, [rsp+11D0h+arg_8]
0x18000fe6b  add     rsp, 11A0h
0x18000fe72  pop     r15
0x18000fe74  pop     r14
0x18000fe76  pop     r13
0x18000fe78  pop     r12
0x18000fe7a  pop     rdi
0x18000fe7b  pop     rsi
0x18000fe7c  pop     rbp
0x18000fe7d  retn
0x18000fe7e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
