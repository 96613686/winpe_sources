# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000778c`
- end: `0x180007b64`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180006c6c`

## callees

- `0x180001f60`
- `0x1800066e4`
- `0x180006b24`
- `0x18000778c`
- `0x180008584`
- `0x180009a4c`
- `0x18000a270`
- `0x180014e20`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007883`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007883`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000786c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000786c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007af8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007af8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007aea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007aea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b20`

## string_xrefs

- `0x180007865`: `ntdll.dll`

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
0x18000778c  mov     [rsp-8+arg_8], rbx
0x180007791  push    rbp
0x180007792  push    rsi
0x180007793  push    rdi
0x180007794  push    r12
0x180007796  push    r13
0x180007798  push    r14
0x18000779a  push    r15
0x18000779c  lea     rbp, [rsp-10A0h]
0x1800077a4  mov     eax, 11A0h
0x1800077a9  call    _alloca_probe
0x1800077ae  sub     rsp, rax
0x1800077b1  mov     rax, cs:__security_cookie
0x1800077b8  xor     rax, rsp
0x1800077bb  mov     [rbp+10D0h+var_40], rax
0x1800077c2  mov     rdi, r8
0x1800077c5  mov     r14, rcx
0x1800077c8  lea     r13, [rcx+rdx*8]
0x1800077cc  xor     r15d, r15d
0x1800077cf  mov     r12d, r15d
0x1800077d2  mov     [rbp+10D0h+var_1128], r15
0x1800077d6  mov     cl, [rdi+8]
0x1800077d9  movzx   edx, word ptr [rdi+6]
0x1800077dd  movzx   eax, word ptr [rdi]
0x1800077e0  mov     [rsp+11D0h+var_1170], ax
0x1800077e5  movzx   eax, word ptr [rdi+2]
0x1800077e9  mov     [rsp+11D0h+var_116E], ax
0x1800077ee  mov     al, [rdi+4]
0x1800077f1  mov     [rsp+11D0h+var_116C], al
0x1800077f5  mov     [rsp+11D0h+var_116A], dx
0x1800077fa  mov     [rsp+11D0h+var_1168], cl
0x1800077fe  test    dx, dx
0x180007801  jz      short loc_180007820
0x180007803  mov     eax, edx
0x180007805  cmp     cl, 1
0x180007808  jnz     short loc_180007810
0x18000780a  add     rax, 2
0x18000780e  jmp     short loc_180007819
0x180007810  cmp     cl, 2
0x180007813  jnz     short loc_180007819
0x180007815  add     rax, 4
0x180007819  mov     [rsp+11D0h+var_1160], rax
0x18000781e  jmp     short loc_180007825
0x180007820  mov     [rsp+11D0h+var_1160], r15
0x180007825  mov     [rsp+11D0h+var_1158], r15
0x18000782a  xorps   xmm0, xmm0
0x18000782d  movdqa  [rbp+10D0h+var_1150], xmm0
0x180007832  mov     [rbp+10D0h+lpMem], r15
0x180007836  mov     [rbp+10D0h+var_1138], 0
0x18000783c  mov     [rbp+10D0h+var_1136], r15b
0x180007840  mov     [rsp+11D0h+var_1188], r15d
0x180007845  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000784d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180007854  test    rax, rax
0x180007857  jnz     short loc_18000789C
0x180007859  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007860  test    rax, rax
0x180007863  jnz     short loc_180007879
0x180007865  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000786c  call    cs:__imp_GetModuleHandleW
0x180007872  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007879  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180007880  mov     rcx, rax; hModule
0x180007883  call    cs:__imp_GetProcAddress
0x180007889  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180007890  test    rax, rax
0x180007893  jnz     short loc_18000789C
0x180007895  mov     ebx, 0C0000139h
0x18000789a  jmp     short loc_1800078C6
0x18000789c  lea     rcx, [rsp+11D0h+var_1190]
0x1800078a1  mov     [rsp+11D0h+var_11A8], rcx
0x1800078a6  lea     rcx, [rbp+10D0h+var_1040]
0x1800078ad  mov     [rsp+11D0h+var_11B0], rcx
0x1800078b2  lea     r9, [rsp+11D0h+var_1188]
0x1800078b7  xor     r8d, r8d
0x1800078ba  xor     edx, edx
0x1800078bc  mov     rcx, r14
0x1800078bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c4  mov     ebx, eax
0x1800078c6  mov     ecx, ebx; this
0x1800078c8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800078cd  test    ebx, ebx
0x1800078cf  jz      short loc_1800078DF
0x1800078d1  mov     eax, r15d
0x1800078d4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x1800078d8  mov     [rsp+11D0h+var_1188], r15d
0x1800078dd  jmp     short loc_1800078E3
0x1800078df  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x1800078e3  mov     r8d, eax; unsigned __int64
0x1800078e6  mov     r9d, 1000h; unsigned __int64
0x1800078ec  lea     rdx, [rbp+10D0h+var_1040]; void *
0x1800078f3  lea     rcx, [rsp+11D0h+var_1170]; this
0x1800078f8  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1800078fd  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180007901  jnz     loc_180007B13
0x180007907  mov     [rbp+10D0h+var_1130], r15
0x18000790b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180007912  mov     [rbp+10D0h+var_10B0], rax
0x180007916  lea     rax, [rbp+10D0h+var_1130]
0x18000791a  mov     [rbp+10D0h+var_10A8], rax
0x18000791e  lea     rax, [rbp+10D0h+var_1128]
0x180007922  mov     [rbp+10D0h+var_10A0], rax
0x180007926  lea     rax, [rsp+11D0h+var_1170]
0x18000792b  mov     [rbp+10D0h+var_1098], rax
0x18000792f  lea     rax, [rbp+10D0h+var_10B0]
0x180007933  mov     [rbp+10D0h+var_1048], rax
0x18000793a  lea     rax, [rbp+10D0h+var_10B8]
0x18000793e  mov     [rbp+10D0h+var_10C0], rax
0x180007942  mov     rax, [rdi+18h]
0x180007946  add     rax, 0Ah
0x18000794a  mov     [rsp+11D0h+var_1190], rax
0x18000794f  movzx   eax, word ptr [rdi+2]
0x180007953  mov     [rbp+10D0h+var_1120], ax
0x180007957  mov     al, [rdi+4]
0x18000795a  mov     [rbp+10D0h+var_111E], al
0x18000795d  mov     [rbp+10D0h+var_111C], r15d
0x180007961  mov     [rbp+10D0h+var_1118], r15w
0x180007966  xorps   xmm0, xmm0
0x180007969  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000796e  movzx   eax, word ptr [rdi+6]
0x180007972  mov     [rbp+10D0h+var_1100], ax
0x180007976  mov     al, [rdi+8]
0x180007979  mov     [rbp+10D0h+var_10FE], al
0x18000797c  mov     [rbp+10D0h+var_10FC], r15d
0x180007980  mov     [rbp+10D0h+var_10F8], r15w
0x180007985  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000798a  jmp     loc_180007A22
0x18000798f  mov     ebx, r15d
0x180007992  mov     esi, [rbp+10D0h+var_111C]
0x180007995  test    esi, esi
0x180007997  jz      loc_180007A22
0x18000799d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x1800079a1  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800079a5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800079aa  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800079ae  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800079b3  test    al, al
0x1800079b5  jz      short loc_180007A1F
0x1800079b7  mov     eax, [rbp+10D0h+var_10FC]
0x1800079ba  mov     [rsp+11D0h+var_1180], eax
0x1800079be  movzx   eax, [rbp+10D0h+var_10F8]
0x1800079c2  mov     [rbp+10D0h+var_10E0], rax
0x1800079c6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1800079ca  mov     [rbp+10D0h+var_10D8], rax
0x1800079ce  movzx   eax, [rbp+10D0h+var_1118]
0x1800079d2  mov     [rbp+10D0h+var_10D0], rax
0x1800079d6  mov     [rbp+10D0h+var_10C8], r15
0x1800079da  mov     rcx, [rbp+10D0h+var_1048]; this
0x1800079e1  test    rcx, rcx
0x1800079e4  jz      loc_180007B5E
0x1800079ea  mov     rax, [rcx]
0x1800079ed  lea     rdx, [rsp+11D0h+var_1180]
0x1800079f2  mov     [rsp+11D0h+var_11A8], rdx
0x1800079f7  lea     rdx, [rbp+10D0h+var_10E0]
0x1800079fb  mov     [rsp+11D0h+var_11B0], rdx
0x180007a00  lea     r9, [rbp+10D0h+var_10D8]
0x180007a04  lea     r8, [rbp+10D0h+var_10D0]
0x180007a08  lea     rdx, [rbp+10D0h+var_10C8]
0x180007a0c  mov     rax, [rax+20h]
0x180007a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a15  test    al, al
0x180007a17  jz      short loc_180007A8F
0x180007a19  inc     ebx
0x180007a1b  cmp     ebx, esi
0x180007a1d  jb      short loc_1800079A1
0x180007a1f  xor     r15d, r15d
0x180007a22  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007a26  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180007a2b  lea     rcx, [rbp+10D0h+var_1120]; this
0x180007a2f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007a34  test    al, al
0x180007a36  jnz     loc_18000798F
0x180007a3c  mov     rcx, [rbp+10D0h+var_1048]
0x180007a43  test    rcx, rcx
0x180007a46  jz      short loc_180007A54
0x180007a48  mov     rax, [rcx]
0x180007a4b  mov     rax, [rax+18h]
0x180007a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a54  mov     bl, 1
0x180007a56  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x180007a5a  jz      short loc_180007AD1
0x180007a5c  mov     eax, [rsp+11D0h+var_1188]
0x180007a60  mov     rdx, [rsp+11D0h+var_1158]
0x180007a65  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180007a69  sub     r8d, edx
0x180007a6c  mov     [rsp+11D0h+var_11A0], 1
0x180007a74  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180007a78  mov     rcx, r14
0x180007a7b  call    wil_details_NtUpdateWnfStateData
0x180007a80  cmp     eax, 0C0000001h
0x180007a85  jnz     short loc_180007AAF
0x180007a87  inc     r12
0x180007a8a  mov     bl, r15b
0x180007a8d  jmp     short loc_180007ADD
0x180007a8f  mov     rcx, [rbp+10D0h+var_1048]
0x180007a96  xor     r15d, r15d
0x180007a99  test    rcx, rcx
0x180007a9c  jz      short loc_180007AAA
0x180007a9e  mov     rax, [rcx]
0x180007aa1  mov     rax, [rax+18h]
0x180007aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aaa  mov     bl, r15b
0x180007aad  jmp     short loc_180007A56
0x180007aaf  test    eax, eax
0x180007ab1  jz      short loc_180007AD1
0x180007ab3  mov     rdx, [rsp+11D0h+var_1158]
0x180007ab8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180007abc  sub     r8d, edx
0x180007abf  mov     [rsp+11D0h+var_11A0], r15d
0x180007ac4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180007ac9  mov     rcx, r14
0x180007acc  call    wil_details_NtUpdateWnfStateData
0x180007ad1  add     r14, 8
0x180007ad5  mov     rax, [rbp+10D0h+var_1130]
0x180007ad9  mov     [rbp+10D0h+var_1128], rax
0x180007add  mov     rsi, [rbp+10D0h+lpMem]
0x180007ae1  mov     [rbp+10D0h+lpMem], r15
0x180007ae5  test    rsi, rsi
0x180007ae8  jz      short loc_180007AFE
0x180007aea  call    cs:__imp_GetProcessHeap
0x180007af0  mov     rcx, rax; hHeap
0x180007af3  mov     r8, rsi; lpMem
0x180007af6  xor     edx, edx; dwFlags
0x180007af8  call    cs:__imp_HeapFree
0x180007afe  test    bl, bl
0x180007b00  jnz     short loc_180007B34
0x180007b02  cmp     r14, r13
0x180007b05  jnb     short loc_180007B34
0x180007b07  cmp     r12, 32h ; '2'
0x180007b0b  jb      loc_1800077D6
0x180007b11  jmp     short loc_180007B34
0x180007b13  mov     rbx, [rbp+10D0h+lpMem]
0x180007b17  mov     [rbp+10D0h+lpMem], r15
0x180007b1b  test    rbx, rbx
0x180007b1e  jz      short loc_180007B34
0x180007b20  call    cs:__imp_GetProcessHeap
0x180007b26  mov     rcx, rax; hHeap
0x180007b29  mov     r8, rbx; lpMem
0x180007b2c  xor     edx, edx; dwFlags
0x180007b2e  call    cs:__imp_HeapFree
0x180007b34  mov     rcx, [rbp+10D0h+var_40]
0x180007b3b  xor     rcx, rsp; StackCookie
0x180007b3e  call    __security_check_cookie
0x180007b43  mov     rbx, [rsp+11D0h+arg_8]
0x180007b4b  add     rsp, 11A0h
0x180007b52  pop     r15
0x180007b54  pop     r14
0x180007b56  pop     r13
0x180007b58  pop     r12
0x180007b5a  pop     rdi
0x180007b5b  pop     rsi
0x180007b5c  pop     rbp
0x180007b5d  retn
0x180007b5e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
