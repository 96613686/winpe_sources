# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x140011d3c`
- end: `0x140012114`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140011224`

## callees

- `0x140002f60`
- `0x140010cd8`
- `0x1400110dc`
- `0x140011d3c`
- `0x140012864`
- `0x140013d7c`
- `0x140014650`
- `0x14003bcc0`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011e33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011e33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011e1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011e1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400120a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400120de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400120a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400120de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001209a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400120d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001209a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400120d0`

## string_xrefs

- `0x140011e15`: `ntdll.dll`

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
  __int64 v19; // r9
  char v20; // bl
  int updated; // eax
  __int64 v22; // r9
  void *v23; // rsi
  HANDLE ProcessHeap; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  __int64 *v27; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v29);
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
    v57[0] = wistd::__function::Z::$$A6A_NPEAX131I::Z::__func<`wil::details_abi::RecordWnfUsageIndex'::`4'::_lambda_1_,AXPEBU__WIL__WNF_STATE_NAME,unsigned __int64,wil::details_abi::RawUsageIndex const &>::`vftable';
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
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v35, (int)v36 - (int)v35, v19, (int)v27, v29[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v35, v36 - v35, v22, (int)v27, 0, 0);
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
0x140011d3c  mov     [rsp-8+arg_8], rbx
0x140011d41  push    rbp
0x140011d42  push    rsi
0x140011d43  push    rdi
0x140011d44  push    r12
0x140011d46  push    r13
0x140011d48  push    r14
0x140011d4a  push    r15
0x140011d4c  lea     rbp, [rsp-10A0h]
0x140011d54  mov     eax, 11A0h
0x140011d59  call    _alloca_probe
0x140011d5e  sub     rsp, rax
0x140011d61  mov     rax, cs:__security_cookie
0x140011d68  xor     rax, rsp
0x140011d6b  mov     [rbp+10D0h+var_40], rax
0x140011d72  mov     rdi, r8
0x140011d75  mov     r14, rcx
0x140011d78  lea     r13, [rcx+rdx*8]
0x140011d7c  xor     r15d, r15d
0x140011d7f  mov     r12d, r15d
0x140011d82  mov     [rbp+10D0h+var_1128], r15
0x140011d86  mov     cl, [rdi+8]
0x140011d89  movzx   edx, word ptr [rdi+6]
0x140011d8d  movzx   eax, word ptr [rdi]
0x140011d90  mov     [rsp+11D0h+var_1170], ax
0x140011d95  movzx   eax, word ptr [rdi+2]
0x140011d99  mov     [rsp+11D0h+var_116E], ax
0x140011d9e  mov     al, [rdi+4]
0x140011da1  mov     [rsp+11D0h+var_116C], al
0x140011da5  mov     [rsp+11D0h+var_116A], dx
0x140011daa  mov     [rsp+11D0h+var_1168], cl
0x140011dae  test    dx, dx
0x140011db1  jz      short loc_140011DD0
0x140011db3  mov     eax, edx
0x140011db5  cmp     cl, 1
0x140011db8  jnz     short loc_140011DC0
0x140011dba  add     rax, 2
0x140011dbe  jmp     short loc_140011DC9
0x140011dc0  cmp     cl, 2
0x140011dc3  jnz     short loc_140011DC9
0x140011dc5  add     rax, 4
0x140011dc9  mov     [rsp+11D0h+var_1160], rax
0x140011dce  jmp     short loc_140011DD5
0x140011dd0  mov     [rsp+11D0h+var_1160], r15
0x140011dd5  mov     [rsp+11D0h+var_1158], r15
0x140011dda  xorps   xmm0, xmm0
0x140011ddd  movdqa  [rbp+10D0h+var_1150], xmm0
0x140011de2  mov     [rbp+10D0h+lpMem], r15
0x140011de6  mov     [rbp+10D0h+var_1138], 0
0x140011dec  mov     [rbp+10D0h+var_1136], r15b
0x140011df0  mov     [rsp+11D0h+var_1188], r15d
0x140011df5  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x140011dfd  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140011e04  test    rax, rax
0x140011e07  jnz     short loc_140011E4C
0x140011e09  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140011e10  test    rax, rax
0x140011e13  jnz     short loc_140011E29
0x140011e15  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140011e1c  call    cs:__imp_GetModuleHandleW
0x140011e22  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140011e29  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140011e30  mov     rcx, rax; hModule
0x140011e33  call    cs:__imp_GetProcAddress
0x140011e39  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140011e40  test    rax, rax
0x140011e43  jnz     short loc_140011E4C
0x140011e45  mov     ebx, 0C0000139h
0x140011e4a  jmp     short loc_140011E76
0x140011e4c  lea     rcx, [rsp+11D0h+var_1190]
0x140011e51  mov     [rsp+11D0h+var_11A8], rcx
0x140011e56  lea     rcx, [rbp+10D0h+var_1040]
0x140011e5d  mov     [rsp+11D0h+var_11B0], rcx
0x140011e62  lea     r9, [rsp+11D0h+var_1188]
0x140011e67  xor     r8d, r8d
0x140011e6a  xor     edx, edx
0x140011e6c  mov     rcx, r14
0x140011e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e74  mov     ebx, eax
0x140011e76  mov     ecx, ebx; this
0x140011e78  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x140011e7d  test    ebx, ebx
0x140011e7f  jz      short loc_140011E8F
0x140011e81  mov     eax, r15d
0x140011e84  mov     dword ptr [rsp+11D0h+var_1190], eax
0x140011e88  mov     [rsp+11D0h+var_1188], r15d
0x140011e8d  jmp     short loc_140011E93
0x140011e8f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x140011e93  mov     r8d, eax; unsigned __int64
0x140011e96  mov     r9d, 1000h; unsigned __int64
0x140011e9c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x140011ea3  lea     rcx, [rsp+11D0h+var_1170]; this
0x140011ea8  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140011ead  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x140011eb1  jnz     loc_1400120C3
0x140011eb7  mov     [rbp+10D0h+var_1130], r15
0x140011ebb  lea     rax, ??_7?$__func@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@$$A6A_NPEAX131I@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x140011ec2  mov     [rbp+10D0h+var_10B0], rax
0x140011ec6  lea     rax, [rbp+10D0h+var_1130]
0x140011eca  mov     [rbp+10D0h+var_10A8], rax
0x140011ece  lea     rax, [rbp+10D0h+var_1128]
0x140011ed2  mov     [rbp+10D0h+var_10A0], rax
0x140011ed6  lea     rax, [rsp+11D0h+var_1170]
0x140011edb  mov     [rbp+10D0h+var_1098], rax
0x140011edf  lea     rax, [rbp+10D0h+var_10B0]
0x140011ee3  mov     [rbp+10D0h+var_1048], rax
0x140011eea  lea     rax, [rbp+10D0h+var_10B8]
0x140011eee  mov     [rbp+10D0h+var_10C0], rax
0x140011ef2  mov     rax, [rdi+18h]
0x140011ef6  add     rax, 0Ah
0x140011efa  mov     [rsp+11D0h+var_1190], rax
0x140011eff  movzx   eax, word ptr [rdi+2]
0x140011f03  mov     [rbp+10D0h+var_1120], ax
0x140011f07  mov     al, [rdi+4]
0x140011f0a  mov     [rbp+10D0h+var_111E], al
0x140011f0d  mov     [rbp+10D0h+var_111C], r15d
0x140011f11  mov     [rbp+10D0h+var_1118], r15w
0x140011f16  xorps   xmm0, xmm0
0x140011f19  movdqu  [rbp+10D0h+var_1110], xmm0
0x140011f1e  movzx   eax, word ptr [rdi+6]
0x140011f22  mov     [rbp+10D0h+var_1100], ax
0x140011f26  mov     al, [rdi+8]
0x140011f29  mov     [rbp+10D0h+var_10FE], al
0x140011f2c  mov     [rbp+10D0h+var_10FC], r15d
0x140011f30  mov     [rbp+10D0h+var_10F8], r15w
0x140011f35  movdqu  [rbp+10D0h+var_10F0], xmm0
0x140011f3a  jmp     loc_140011FD2
0x140011f3f  mov     ebx, r15d
0x140011f42  mov     esi, [rbp+10D0h+var_111C]
0x140011f45  test    esi, esi
0x140011f47  jz      loc_140011FD2
0x140011f4d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x140011f51  mov     r8, [rdi+20h]; unsigned __int8 *
0x140011f55  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x140011f5a  lea     rcx, [rbp+10D0h+var_1100]; this
0x140011f5e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140011f63  test    al, al
0x140011f65  jz      short loc_140011FCF
0x140011f67  mov     eax, [rbp+10D0h+var_10FC]
0x140011f6a  mov     [rsp+11D0h+var_1180], eax
0x140011f6e  movzx   eax, [rbp+10D0h+var_10F8]
0x140011f72  mov     [rbp+10D0h+var_10E0], rax
0x140011f76  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x140011f7a  mov     [rbp+10D0h+var_10D8], rax
0x140011f7e  movzx   eax, [rbp+10D0h+var_1118]
0x140011f82  mov     [rbp+10D0h+var_10D0], rax
0x140011f86  mov     [rbp+10D0h+var_10C8], r15
0x140011f8a  mov     rcx, [rbp+10D0h+var_1048]; this
0x140011f91  test    rcx, rcx
0x140011f94  jz      loc_14001210E
0x140011f9a  mov     rax, [rcx]
0x140011f9d  lea     rdx, [rsp+11D0h+var_1180]
0x140011fa2  mov     [rsp+11D0h+var_11A8], rdx
0x140011fa7  lea     rdx, [rbp+10D0h+var_10E0]
0x140011fab  mov     [rsp+11D0h+var_11B0], rdx
0x140011fb0  lea     r9, [rbp+10D0h+var_10D8]
0x140011fb4  lea     r8, [rbp+10D0h+var_10D0]
0x140011fb8  lea     rdx, [rbp+10D0h+var_10C8]
0x140011fbc  mov     rax, [rax+20h]
0x140011fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011fc5  test    al, al
0x140011fc7  jz      short loc_14001203F
0x140011fc9  inc     ebx
0x140011fcb  cmp     ebx, esi
0x140011fcd  jb      short loc_140011F51
0x140011fcf  xor     r15d, r15d
0x140011fd2  mov     r8, [rdi+20h]; unsigned __int8 *
0x140011fd6  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x140011fdb  lea     rcx, [rbp+10D0h+var_1120]; this
0x140011fdf  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140011fe4  test    al, al
0x140011fe6  jnz     loc_140011F3F
0x140011fec  mov     rcx, [rbp+10D0h+var_1048]
0x140011ff3  test    rcx, rcx
0x140011ff6  jz      short loc_140012004
0x140011ff8  mov     rax, [rcx]
0x140011ffb  mov     rax, [rax+18h]
0x140011fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012004  mov     bl, 1
0x140012006  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x14001200a  jz      short loc_140012081
0x14001200c  mov     eax, [rsp+11D0h+var_1188]
0x140012010  mov     rdx, [rsp+11D0h+var_1158]
0x140012015  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x140012019  sub     r8d, edx
0x14001201c  mov     [rsp+11D0h+var_11A0], 1
0x140012024  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x140012028  mov     rcx, r14
0x14001202b  call    wil_details_NtUpdateWnfStateData
0x140012030  cmp     eax, 0C0000001h
0x140012035  jnz     short loc_14001205F
0x140012037  inc     r12
0x14001203a  mov     bl, r15b
0x14001203d  jmp     short loc_14001208D
0x14001203f  mov     rcx, [rbp+10D0h+var_1048]
0x140012046  xor     r15d, r15d
0x140012049  test    rcx, rcx
0x14001204c  jz      short loc_14001205A
0x14001204e  mov     rax, [rcx]
0x140012051  mov     rax, [rax+18h]
0x140012055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001205a  mov     bl, r15b
0x14001205d  jmp     short loc_140012006
0x14001205f  test    eax, eax
0x140012061  jz      short loc_140012081
0x140012063  mov     rdx, [rsp+11D0h+var_1158]
0x140012068  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14001206c  sub     r8d, edx
0x14001206f  mov     [rsp+11D0h+var_11A0], r15d
0x140012074  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x140012079  mov     rcx, r14
0x14001207c  call    wil_details_NtUpdateWnfStateData
0x140012081  add     r14, 8
0x140012085  mov     rax, [rbp+10D0h+var_1130]
0x140012089  mov     [rbp+10D0h+var_1128], rax
0x14001208d  mov     rsi, [rbp+10D0h+lpMem]
0x140012091  mov     [rbp+10D0h+lpMem], r15
0x140012095  test    rsi, rsi
0x140012098  jz      short loc_1400120AE
0x14001209a  call    cs:__imp_GetProcessHeap
0x1400120a0  mov     rcx, rax; hHeap
0x1400120a3  mov     r8, rsi; lpMem
0x1400120a6  xor     edx, edx; dwFlags
0x1400120a8  call    cs:__imp_HeapFree
0x1400120ae  test    bl, bl
0x1400120b0  jnz     short loc_1400120E4
0x1400120b2  cmp     r14, r13
0x1400120b5  jnb     short loc_1400120E4
0x1400120b7  cmp     r12, 32h ; '2'
0x1400120bb  jb      loc_140011D86
0x1400120c1  jmp     short loc_1400120E4
0x1400120c3  mov     rbx, [rbp+10D0h+lpMem]
0x1400120c7  mov     [rbp+10D0h+lpMem], r15
0x1400120cb  test    rbx, rbx
0x1400120ce  jz      short loc_1400120E4
0x1400120d0  call    cs:__imp_GetProcessHeap
0x1400120d6  mov     rcx, rax; hHeap
0x1400120d9  mov     r8, rbx; lpMem
0x1400120dc  xor     edx, edx; dwFlags
0x1400120de  call    cs:__imp_HeapFree
0x1400120e4  mov     rcx, [rbp+10D0h+var_40]
0x1400120eb  xor     rcx, rsp; StackCookie
0x1400120ee  call    __security_check_cookie
0x1400120f3  mov     rbx, [rsp+11D0h+arg_8]
0x1400120fb  add     rsp, 11A0h
0x140012102  pop     r15
0x140012104  pop     r14
0x140012106  pop     r13
0x140012108  pop     r12
0x14001210a  pop     rdi
0x14001210b  pop     rsi
0x14001210c  pop     rbp
0x14001210d  retn
0x14001210e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
