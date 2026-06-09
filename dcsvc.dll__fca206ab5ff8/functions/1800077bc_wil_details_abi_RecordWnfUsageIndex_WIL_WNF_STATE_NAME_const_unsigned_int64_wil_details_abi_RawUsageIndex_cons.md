# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800077bc`
- end: `0x180007b94`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180006c9c`

## callees

- `0x180001cf0`
- `0x180006798`
- `0x180006b9c`
- `0x1800077bc`
- `0x1800087f0`
- `0x18000a12c`
- `0x18000ab30`
- `0x180011c00`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000789c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000789c`

## string_xrefs

- `0x180007895`: `ntdll.dll`

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
0x1800077bc  mov     [rsp-8+arg_8], rbx
0x1800077c1  push    rbp
0x1800077c2  push    rsi
0x1800077c3  push    rdi
0x1800077c4  push    r12
0x1800077c6  push    r13
0x1800077c8  push    r14
0x1800077ca  push    r15
0x1800077cc  lea     rbp, [rsp-10A0h]
0x1800077d4  mov     eax, 11A0h
0x1800077d9  call    _alloca_probe
0x1800077de  sub     rsp, rax
0x1800077e1  mov     rax, cs:__security_cookie
0x1800077e8  xor     rax, rsp
0x1800077eb  mov     [rbp+10D0h+var_40], rax
0x1800077f2  mov     rdi, r8
0x1800077f5  mov     r14, rcx
0x1800077f8  lea     r13, [rcx+rdx*8]
0x1800077fc  xor     r15d, r15d
0x1800077ff  mov     r12d, r15d
0x180007802  mov     [rbp+10D0h+var_1128], r15
0x180007806  mov     cl, [rdi+8]
0x180007809  movzx   edx, word ptr [rdi+6]
0x18000780d  movzx   eax, word ptr [rdi]
0x180007810  mov     [rsp+11D0h+var_1170], ax
0x180007815  movzx   eax, word ptr [rdi+2]
0x180007819  mov     [rsp+11D0h+var_116E], ax
0x18000781e  mov     al, [rdi+4]
0x180007821  mov     [rsp+11D0h+var_116C], al
0x180007825  mov     [rsp+11D0h+var_116A], dx
0x18000782a  mov     [rsp+11D0h+var_1168], cl
0x18000782e  test    dx, dx
0x180007831  jz      short loc_180007850
0x180007833  mov     eax, edx
0x180007835  cmp     cl, 1
0x180007838  jnz     short loc_180007840
0x18000783a  add     rax, 2
0x18000783e  jmp     short loc_180007849
0x180007840  cmp     cl, 2
0x180007843  jnz     short loc_180007849
0x180007845  add     rax, 4
0x180007849  mov     [rsp+11D0h+var_1160], rax
0x18000784e  jmp     short loc_180007855
0x180007850  mov     [rsp+11D0h+var_1160], r15
0x180007855  mov     [rsp+11D0h+var_1158], r15
0x18000785a  xorps   xmm0, xmm0
0x18000785d  movdqa  [rbp+10D0h+var_1150], xmm0
0x180007862  mov     [rbp+10D0h+lpMem], r15
0x180007866  mov     [rbp+10D0h+var_1138], 0
0x18000786c  mov     [rbp+10D0h+var_1136], r15b
0x180007870  mov     [rsp+11D0h+var_1188], r15d
0x180007875  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000787d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180007884  test    rax, rax
0x180007887  jnz     short loc_1800078CC
0x180007889  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007890  test    rax, rax
0x180007893  jnz     short loc_1800078A9
0x180007895  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000789c  call    cs:__imp_GetModuleHandleW
0x1800078a2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800078a9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800078b0  mov     rcx, rax; hModule
0x1800078b3  call    cs:__imp_GetProcAddress
0x1800078b9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800078c0  test    rax, rax
0x1800078c3  jnz     short loc_1800078CC
0x1800078c5  mov     ebx, 0C0000139h
0x1800078ca  jmp     short loc_1800078F6
0x1800078cc  lea     rcx, [rsp+11D0h+var_1190]
0x1800078d1  mov     [rsp+11D0h+var_11A8], rcx
0x1800078d6  lea     rcx, [rbp+10D0h+var_1040]
0x1800078dd  mov     [rsp+11D0h+var_11B0], rcx
0x1800078e2  lea     r9, [rsp+11D0h+var_1188]
0x1800078e7  xor     r8d, r8d
0x1800078ea  xor     edx, edx
0x1800078ec  mov     rcx, r14
0x1800078ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078f4  mov     ebx, eax
0x1800078f6  mov     ecx, ebx; this
0x1800078f8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800078fd  test    ebx, ebx
0x1800078ff  jz      short loc_18000790F
0x180007901  mov     eax, r15d
0x180007904  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180007908  mov     [rsp+11D0h+var_1188], r15d
0x18000790d  jmp     short loc_180007913
0x18000790f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180007913  mov     r8d, eax; unsigned __int64
0x180007916  mov     r9d, 1000h; unsigned __int64
0x18000791c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180007923  lea     rcx, [rsp+11D0h+var_1170]; this
0x180007928  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000792d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180007931  jnz     loc_180007B43
0x180007937  mov     [rbp+10D0h+var_1130], r15
0x18000793b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180007942  mov     [rbp+10D0h+var_10B0], rax
0x180007946  lea     rax, [rbp+10D0h+var_1130]
0x18000794a  mov     [rbp+10D0h+var_10A8], rax
0x18000794e  lea     rax, [rbp+10D0h+var_1128]
0x180007952  mov     [rbp+10D0h+var_10A0], rax
0x180007956  lea     rax, [rsp+11D0h+var_1170]
0x18000795b  mov     [rbp+10D0h+var_1098], rax
0x18000795f  lea     rax, [rbp+10D0h+var_10B0]
0x180007963  mov     [rbp+10D0h+var_1048], rax
0x18000796a  lea     rax, [rbp+10D0h+var_10B8]
0x18000796e  mov     [rbp+10D0h+var_10C0], rax
0x180007972  mov     rax, [rdi+18h]
0x180007976  add     rax, 0Ah
0x18000797a  mov     [rsp+11D0h+var_1190], rax
0x18000797f  movzx   eax, word ptr [rdi+2]
0x180007983  mov     [rbp+10D0h+var_1120], ax
0x180007987  mov     al, [rdi+4]
0x18000798a  mov     [rbp+10D0h+var_111E], al
0x18000798d  mov     [rbp+10D0h+var_111C], r15d
0x180007991  mov     [rbp+10D0h+var_1118], r15w
0x180007996  xorps   xmm0, xmm0
0x180007999  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000799e  movzx   eax, word ptr [rdi+6]
0x1800079a2  mov     [rbp+10D0h+var_1100], ax
0x1800079a6  mov     al, [rdi+8]
0x1800079a9  mov     [rbp+10D0h+var_10FE], al
0x1800079ac  mov     [rbp+10D0h+var_10FC], r15d
0x1800079b0  mov     [rbp+10D0h+var_10F8], r15w
0x1800079b5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800079ba  jmp     loc_180007A52
0x1800079bf  mov     ebx, r15d
0x1800079c2  mov     esi, [rbp+10D0h+var_111C]
0x1800079c5  test    esi, esi
0x1800079c7  jz      loc_180007A52
0x1800079cd  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x1800079d1  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800079d5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800079da  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800079de  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800079e3  test    al, al
0x1800079e5  jz      short loc_180007A4F
0x1800079e7  mov     eax, [rbp+10D0h+var_10FC]
0x1800079ea  mov     [rsp+11D0h+var_1180], eax
0x1800079ee  movzx   eax, [rbp+10D0h+var_10F8]
0x1800079f2  mov     [rbp+10D0h+var_10E0], rax
0x1800079f6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1800079fa  mov     [rbp+10D0h+var_10D8], rax
0x1800079fe  movzx   eax, [rbp+10D0h+var_1118]
0x180007a02  mov     [rbp+10D0h+var_10D0], rax
0x180007a06  mov     [rbp+10D0h+var_10C8], r15
0x180007a0a  mov     rcx, [rbp+10D0h+var_1048]; this
0x180007a11  test    rcx, rcx
0x180007a14  jz      loc_180007B8E
0x180007a1a  mov     rax, [rcx]
0x180007a1d  lea     rdx, [rsp+11D0h+var_1180]
0x180007a22  mov     [rsp+11D0h+var_11A8], rdx
0x180007a27  lea     rdx, [rbp+10D0h+var_10E0]
0x180007a2b  mov     [rsp+11D0h+var_11B0], rdx
0x180007a30  lea     r9, [rbp+10D0h+var_10D8]
0x180007a34  lea     r8, [rbp+10D0h+var_10D0]
0x180007a38  lea     rdx, [rbp+10D0h+var_10C8]
0x180007a3c  mov     rax, [rax+20h]
0x180007a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a45  test    al, al
0x180007a47  jz      short loc_180007ABF
0x180007a49  inc     ebx
0x180007a4b  cmp     ebx, esi
0x180007a4d  jb      short loc_1800079D1
0x180007a4f  xor     r15d, r15d
0x180007a52  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007a56  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180007a5b  lea     rcx, [rbp+10D0h+var_1120]; this
0x180007a5f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007a64  test    al, al
0x180007a66  jnz     loc_1800079BF
0x180007a6c  mov     rcx, [rbp+10D0h+var_1048]
0x180007a73  test    rcx, rcx
0x180007a76  jz      short loc_180007A84
0x180007a78  mov     rax, [rcx]
0x180007a7b  mov     rax, [rax+18h]
0x180007a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a84  mov     bl, 1
0x180007a86  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x180007a8a  jz      short loc_180007B01
0x180007a8c  mov     eax, [rsp+11D0h+var_1188]
0x180007a90  mov     rdx, [rsp+11D0h+var_1158]
0x180007a95  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180007a99  sub     r8d, edx
0x180007a9c  mov     [rsp+11D0h+var_11A0], 1
0x180007aa4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180007aa8  mov     rcx, r14
0x180007aab  call    wil_details_NtUpdateWnfStateData
0x180007ab0  cmp     eax, 0C0000001h
0x180007ab5  jnz     short loc_180007ADF
0x180007ab7  inc     r12
0x180007aba  mov     bl, r15b
0x180007abd  jmp     short loc_180007B0D
0x180007abf  mov     rcx, [rbp+10D0h+var_1048]
0x180007ac6  xor     r15d, r15d
0x180007ac9  test    rcx, rcx
0x180007acc  jz      short loc_180007ADA
0x180007ace  mov     rax, [rcx]
0x180007ad1  mov     rax, [rax+18h]
0x180007ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ada  mov     bl, r15b
0x180007add  jmp     short loc_180007A86
0x180007adf  test    eax, eax
0x180007ae1  jz      short loc_180007B01
0x180007ae3  mov     rdx, [rsp+11D0h+var_1158]
0x180007ae8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180007aec  sub     r8d, edx
0x180007aef  mov     [rsp+11D0h+var_11A0], r15d
0x180007af4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180007af9  mov     rcx, r14
0x180007afc  call    wil_details_NtUpdateWnfStateData
0x180007b01  add     r14, 8
0x180007b05  mov     rax, [rbp+10D0h+var_1130]
0x180007b09  mov     [rbp+10D0h+var_1128], rax
0x180007b0d  mov     rsi, [rbp+10D0h+lpMem]
0x180007b11  mov     [rbp+10D0h+lpMem], r15
0x180007b15  test    rsi, rsi
0x180007b18  jz      short loc_180007B2E
0x180007b1a  call    cs:__imp_GetProcessHeap
0x180007b20  mov     rcx, rax; hHeap
0x180007b23  mov     r8, rsi; lpMem
0x180007b26  xor     edx, edx; dwFlags
0x180007b28  call    cs:__imp_HeapFree
0x180007b2e  test    bl, bl
0x180007b30  jnz     short loc_180007B64
0x180007b32  cmp     r14, r13
0x180007b35  jnb     short loc_180007B64
0x180007b37  cmp     r12, 32h ; '2'
0x180007b3b  jb      loc_180007806
0x180007b41  jmp     short loc_180007B64
0x180007b43  mov     rbx, [rbp+10D0h+lpMem]
0x180007b47  mov     [rbp+10D0h+lpMem], r15
0x180007b4b  test    rbx, rbx
0x180007b4e  jz      short loc_180007B64
0x180007b50  call    cs:__imp_GetProcessHeap
0x180007b56  mov     rcx, rax; hHeap
0x180007b59  mov     r8, rbx; lpMem
0x180007b5c  xor     edx, edx; dwFlags
0x180007b5e  call    cs:__imp_HeapFree
0x180007b64  mov     rcx, [rbp+10D0h+var_40]
0x180007b6b  xor     rcx, rsp; StackCookie
0x180007b6e  call    __security_check_cookie
0x180007b73  mov     rbx, [rsp+11D0h+arg_8]
0x180007b7b  add     rsp, 11A0h
0x180007b82  pop     r15
0x180007b84  pop     r14
0x180007b86  pop     r13
0x180007b88  pop     r12
0x180007b8a  pop     rdi
0x180007b8b  pop     rsi
0x180007b8c  pop     rbp
0x180007b8d  retn
0x180007b8e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
