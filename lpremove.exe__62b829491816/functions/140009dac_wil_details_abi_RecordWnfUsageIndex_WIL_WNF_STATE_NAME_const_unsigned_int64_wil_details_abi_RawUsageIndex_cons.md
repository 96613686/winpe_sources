# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x140009dac`
- end: `0x14000a184`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140009494`

## callees

- `0x140002190`
- `0x140008f24`
- `0x1400092c8`
- `0x140009dac`
- `0x14000ac24`
- `0x14000cdec`
- `0x14000d808`
- `0x14000fe00`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140009e8c`
- `KERNEL32!GetModuleHandleW` at `0x140009e8c`
- `KERNEL32!GetProcAddress` at `0x140009ea3`
- `KERNEL32!GetProcAddress` at `0x140009ea3`
- `KERNEL32!GetProcessHeap` at `0x14000a10a`
- `KERNEL32!GetProcessHeap` at `0x14000a140`
- `KERNEL32!GetProcessHeap` at `0x14000a10a`
- `KERNEL32!GetProcessHeap` at `0x14000a140`
- `KERNEL32!HeapFree` at `0x14000a118`
- `KERNEL32!HeapFree` at `0x14000a14e`
- `KERNEL32!HeapFree` at `0x14000a118`
- `KERNEL32!HeapFree` at `0x14000a14e`

## string_xrefs

- `0x140009e85`: `ntdll.dll`

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
0x140009dac  mov     [rsp-8+arg_8], rbx
0x140009db1  push    rbp
0x140009db2  push    rsi
0x140009db3  push    rdi
0x140009db4  push    r12
0x140009db6  push    r13
0x140009db8  push    r14
0x140009dba  push    r15
0x140009dbc  lea     rbp, [rsp-10A0h]
0x140009dc4  mov     eax, 11A0h
0x140009dc9  call    _alloca_probe
0x140009dce  sub     rsp, rax
0x140009dd1  mov     rax, cs:__security_cookie
0x140009dd8  xor     rax, rsp
0x140009ddb  mov     [rbp+10D0h+var_40], rax
0x140009de2  mov     rdi, r8
0x140009de5  mov     r14, rcx
0x140009de8  lea     r13, [rcx+rdx*8]
0x140009dec  xor     r15d, r15d
0x140009def  mov     r12d, r15d
0x140009df2  mov     [rbp+10D0h+var_1128], r15
0x140009df6  mov     cl, [rdi+8]
0x140009df9  movzx   edx, word ptr [rdi+6]
0x140009dfd  movzx   eax, word ptr [rdi]
0x140009e00  mov     [rsp+11D0h+var_1170], ax
0x140009e05  movzx   eax, word ptr [rdi+2]
0x140009e09  mov     [rsp+11D0h+var_116E], ax
0x140009e0e  mov     al, [rdi+4]
0x140009e11  mov     [rsp+11D0h+var_116C], al
0x140009e15  mov     [rsp+11D0h+var_116A], dx
0x140009e1a  mov     [rsp+11D0h+var_1168], cl
0x140009e1e  test    dx, dx
0x140009e21  jz      short loc_140009E40
0x140009e23  mov     eax, edx
0x140009e25  cmp     cl, 1
0x140009e28  jnz     short loc_140009E30
0x140009e2a  add     rax, 2
0x140009e2e  jmp     short loc_140009E39
0x140009e30  cmp     cl, 2
0x140009e33  jnz     short loc_140009E39
0x140009e35  add     rax, 4
0x140009e39  mov     [rsp+11D0h+var_1160], rax
0x140009e3e  jmp     short loc_140009E45
0x140009e40  mov     [rsp+11D0h+var_1160], r15
0x140009e45  mov     [rsp+11D0h+var_1158], r15
0x140009e4a  xorps   xmm0, xmm0
0x140009e4d  movdqa  [rbp+10D0h+var_1150], xmm0
0x140009e52  mov     [rbp+10D0h+lpMem], r15
0x140009e56  mov     [rbp+10D0h+var_1138], 0
0x140009e5c  mov     [rbp+10D0h+var_1136], r15b
0x140009e60  mov     [rsp+11D0h+var_1188], r15d
0x140009e65  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x140009e6d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140009e74  test    rax, rax
0x140009e77  jnz     short loc_140009EBC
0x140009e79  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009e80  test    rax, rax
0x140009e83  jnz     short loc_140009E99
0x140009e85  lea     rcx, ModuleName; "ntdll.dll"
0x140009e8c  call    cs:__imp_GetModuleHandleW
0x140009e92  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009e99  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140009ea0  mov     rcx, rax; hModule
0x140009ea3  call    cs:__imp_GetProcAddress
0x140009ea9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140009eb0  test    rax, rax
0x140009eb3  jnz     short loc_140009EBC
0x140009eb5  mov     ebx, 0C0000139h
0x140009eba  jmp     short loc_140009EE6
0x140009ebc  lea     rcx, [rsp+11D0h+var_1190]
0x140009ec1  mov     [rsp+11D0h+var_11A8], rcx
0x140009ec6  lea     rcx, [rbp+10D0h+var_1040]
0x140009ecd  mov     [rsp+11D0h+var_11B0], rcx
0x140009ed2  lea     r9, [rsp+11D0h+var_1188]
0x140009ed7  xor     r8d, r8d
0x140009eda  xor     edx, edx
0x140009edc  mov     rcx, r14
0x140009edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ee4  mov     ebx, eax
0x140009ee6  mov     ecx, ebx; this
0x140009ee8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x140009eed  test    ebx, ebx
0x140009eef  jz      short loc_140009EFF
0x140009ef1  mov     eax, r15d
0x140009ef4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x140009ef8  mov     [rsp+11D0h+var_1188], r15d
0x140009efd  jmp     short loc_140009F03
0x140009eff  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x140009f03  mov     r8d, eax; unsigned __int64
0x140009f06  mov     r9d, 1000h; unsigned __int64
0x140009f0c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x140009f13  lea     rcx, [rsp+11D0h+var_1170]; this
0x140009f18  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140009f1d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x140009f21  jnz     loc_14000A133
0x140009f27  mov     [rbp+10D0h+var_1130], r15
0x140009f2b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x140009f32  mov     [rbp+10D0h+var_10B0], rax
0x140009f36  lea     rax, [rbp+10D0h+var_1130]
0x140009f3a  mov     [rbp+10D0h+var_10A8], rax
0x140009f3e  lea     rax, [rbp+10D0h+var_1128]
0x140009f42  mov     [rbp+10D0h+var_10A0], rax
0x140009f46  lea     rax, [rsp+11D0h+var_1170]
0x140009f4b  mov     [rbp+10D0h+var_1098], rax
0x140009f4f  lea     rax, [rbp+10D0h+var_10B0]
0x140009f53  mov     [rbp+10D0h+var_1048], rax
0x140009f5a  lea     rax, [rbp+10D0h+var_10B8]
0x140009f5e  mov     [rbp+10D0h+var_10C0], rax
0x140009f62  mov     rax, [rdi+18h]
0x140009f66  add     rax, 0Ah
0x140009f6a  mov     [rsp+11D0h+var_1190], rax
0x140009f6f  movzx   eax, word ptr [rdi+2]
0x140009f73  mov     [rbp+10D0h+var_1120], ax
0x140009f77  mov     al, [rdi+4]
0x140009f7a  mov     [rbp+10D0h+var_111E], al
0x140009f7d  mov     [rbp+10D0h+var_111C], r15d
0x140009f81  mov     [rbp+10D0h+var_1118], r15w
0x140009f86  xorps   xmm0, xmm0
0x140009f89  movdqu  [rbp+10D0h+var_1110], xmm0
0x140009f8e  movzx   eax, word ptr [rdi+6]
0x140009f92  mov     [rbp+10D0h+var_1100], ax
0x140009f96  mov     al, [rdi+8]
0x140009f99  mov     [rbp+10D0h+var_10FE], al
0x140009f9c  mov     [rbp+10D0h+var_10FC], r15d
0x140009fa0  mov     [rbp+10D0h+var_10F8], r15w
0x140009fa5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x140009faa  jmp     loc_14000A042
0x140009faf  mov     ebx, r15d
0x140009fb2  mov     esi, [rbp+10D0h+var_111C]
0x140009fb5  test    esi, esi
0x140009fb7  jz      loc_14000A042
0x140009fbd  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x140009fc1  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009fc5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x140009fca  lea     rcx, [rbp+10D0h+var_1100]; this
0x140009fce  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009fd3  test    al, al
0x140009fd5  jz      short loc_14000A03F
0x140009fd7  mov     eax, [rbp+10D0h+var_10FC]
0x140009fda  mov     [rsp+11D0h+var_1180], eax
0x140009fde  movzx   eax, [rbp+10D0h+var_10F8]
0x140009fe2  mov     [rbp+10D0h+var_10E0], rax
0x140009fe6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x140009fea  mov     [rbp+10D0h+var_10D8], rax
0x140009fee  movzx   eax, [rbp+10D0h+var_1118]
0x140009ff2  mov     [rbp+10D0h+var_10D0], rax
0x140009ff6  mov     [rbp+10D0h+var_10C8], r15
0x140009ffa  mov     rcx, [rbp+10D0h+var_1048]; this
0x14000a001  test    rcx, rcx
0x14000a004  jz      loc_14000A17E
0x14000a00a  mov     rax, [rcx]
0x14000a00d  lea     rdx, [rsp+11D0h+var_1180]
0x14000a012  mov     [rsp+11D0h+var_11A8], rdx
0x14000a017  lea     rdx, [rbp+10D0h+var_10E0]
0x14000a01b  mov     [rsp+11D0h+var_11B0], rdx
0x14000a020  lea     r9, [rbp+10D0h+var_10D8]
0x14000a024  lea     r8, [rbp+10D0h+var_10D0]
0x14000a028  lea     rdx, [rbp+10D0h+var_10C8]
0x14000a02c  mov     rax, [rax+20h]
0x14000a030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a035  test    al, al
0x14000a037  jz      short loc_14000A0AF
0x14000a039  inc     ebx
0x14000a03b  cmp     ebx, esi
0x14000a03d  jb      short loc_140009FC1
0x14000a03f  xor     r15d, r15d
0x14000a042  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000a046  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000a04b  lea     rcx, [rbp+10D0h+var_1120]; this
0x14000a04f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000a054  test    al, al
0x14000a056  jnz     loc_140009FAF
0x14000a05c  mov     rcx, [rbp+10D0h+var_1048]
0x14000a063  test    rcx, rcx
0x14000a066  jz      short loc_14000A074
0x14000a068  mov     rax, [rcx]
0x14000a06b  mov     rax, [rax+18h]
0x14000a06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a074  mov     bl, 1
0x14000a076  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x14000a07a  jz      short loc_14000A0F1
0x14000a07c  mov     eax, [rsp+11D0h+var_1188]
0x14000a080  mov     rdx, [rsp+11D0h+var_1158]
0x14000a085  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000a089  sub     r8d, edx
0x14000a08c  mov     [rsp+11D0h+var_11A0], 1
0x14000a094  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x14000a098  mov     rcx, r14
0x14000a09b  call    wil_details_NtUpdateWnfStateData
0x14000a0a0  cmp     eax, 0C0000001h
0x14000a0a5  jnz     short loc_14000A0CF
0x14000a0a7  inc     r12
0x14000a0aa  mov     bl, r15b
0x14000a0ad  jmp     short loc_14000A0FD
0x14000a0af  mov     rcx, [rbp+10D0h+var_1048]
0x14000a0b6  xor     r15d, r15d
0x14000a0b9  test    rcx, rcx
0x14000a0bc  jz      short loc_14000A0CA
0x14000a0be  mov     rax, [rcx]
0x14000a0c1  mov     rax, [rax+18h]
0x14000a0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0ca  mov     bl, r15b
0x14000a0cd  jmp     short loc_14000A076
0x14000a0cf  test    eax, eax
0x14000a0d1  jz      short loc_14000A0F1
0x14000a0d3  mov     rdx, [rsp+11D0h+var_1158]
0x14000a0d8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000a0dc  sub     r8d, edx
0x14000a0df  mov     [rsp+11D0h+var_11A0], r15d
0x14000a0e4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x14000a0e9  mov     rcx, r14
0x14000a0ec  call    wil_details_NtUpdateWnfStateData
0x14000a0f1  add     r14, 8
0x14000a0f5  mov     rax, [rbp+10D0h+var_1130]
0x14000a0f9  mov     [rbp+10D0h+var_1128], rax
0x14000a0fd  mov     rsi, [rbp+10D0h+lpMem]
0x14000a101  mov     [rbp+10D0h+lpMem], r15
0x14000a105  test    rsi, rsi
0x14000a108  jz      short loc_14000A11E
0x14000a10a  call    cs:__imp_GetProcessHeap
0x14000a110  mov     rcx, rax; hHeap
0x14000a113  mov     r8, rsi; lpMem
0x14000a116  xor     edx, edx; dwFlags
0x14000a118  call    cs:__imp_HeapFree
0x14000a11e  test    bl, bl
0x14000a120  jnz     short loc_14000A154
0x14000a122  cmp     r14, r13
0x14000a125  jnb     short loc_14000A154
0x14000a127  cmp     r12, 32h ; '2'
0x14000a12b  jb      loc_140009DF6
0x14000a131  jmp     short loc_14000A154
0x14000a133  mov     rbx, [rbp+10D0h+lpMem]
0x14000a137  mov     [rbp+10D0h+lpMem], r15
0x14000a13b  test    rbx, rbx
0x14000a13e  jz      short loc_14000A154
0x14000a140  call    cs:__imp_GetProcessHeap
0x14000a146  mov     rcx, rax; hHeap
0x14000a149  mov     r8, rbx; lpMem
0x14000a14c  xor     edx, edx; dwFlags
0x14000a14e  call    cs:__imp_HeapFree
0x14000a154  mov     rcx, [rbp+10D0h+var_40]
0x14000a15b  xor     rcx, rsp; StackCookie
0x14000a15e  call    __security_check_cookie
0x14000a163  mov     rbx, [rsp+11D0h+arg_8]
0x14000a16b  add     rsp, 11A0h
0x14000a172  pop     r15
0x14000a174  pop     r14
0x14000a176  pop     r13
0x14000a178  pop     r12
0x14000a17a  pop     rdi
0x14000a17b  pop     rsi
0x14000a17c  pop     rbp
0x14000a17d  retn
0x14000a17e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
