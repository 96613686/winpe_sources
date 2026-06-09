# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800098a8`
- end: `0x180009c8c`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `996`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180008f7c`

## callees

- `0x180001710`
- `0x1800033d0`
- `0x180008a64`
- `0x180008e80`
- `0x1800098a8`
- `0x18000a708`
- `0x18000f33c`
- `0x18001064c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800099ab`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800099ab`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180009994`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180009994`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c56`

## string_xrefs

- `0x18000998d`: `ntdll.dll`

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
  _QWORD v55[3]; // [rsp+108h] [rbp+8h] BYREF
  char v56; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v57[13]; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *v58; // [rsp+190h] [rbp+90h]
  _BYTE v59[4096]; // [rsp+1A0h] [rbp+A0h] BYREF

  v55[1] = -2;
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
    v57[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v57[1] = &v40;
    v57[2] = &v41;
    v57[3] = v30;
    v58 = (wil::details::in1diag3 *)v57;
    v55[2] = &v56;
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
0x1800098a8  push    rbp
0x1800098aa  push    rsi
0x1800098ab  push    rdi
0x1800098ac  push    r12
0x1800098ae  push    r13
0x1800098b0  push    r14
0x1800098b2  push    r15
0x1800098b4  lea     rbp, [rsp-10B0h]
0x1800098bc  mov     eax, 11B0h
0x1800098c1  call    _alloca_probe
0x1800098c6  sub     rsp, rax
0x1800098c9  mov     [rbp+10E0h+var_10D0], 0FFFFFFFFFFFFFFFEh
0x1800098d1  mov     [rsp+11E0h+arg_8], rbx
0x1800098d9  mov     rax, cs:__security_cookie
0x1800098e0  xor     rax, rsp
0x1800098e3  mov     [rbp+10E0h+var_40], rax
0x1800098ea  mov     rdi, r8
0x1800098ed  mov     r14, rcx
0x1800098f0  lea     r13, [rcx+rdx*8]
0x1800098f4  xor     r15d, r15d
0x1800098f7  mov     r12d, r15d
0x1800098fa  mov     [rbp+10E0h+var_1138], r15
0x1800098fe  mov     cl, [rdi+8]
0x180009901  movzx   edx, word ptr [rdi+6]
0x180009905  movzx   eax, word ptr [rdi]
0x180009908  mov     [rsp+11E0h+var_1180], ax
0x18000990d  movzx   eax, word ptr [rdi+2]
0x180009911  mov     [rsp+11E0h+var_117E], ax
0x180009916  mov     al, [rdi+4]
0x180009919  mov     [rsp+11E0h+var_117C], al
0x18000991d  mov     [rsp+11E0h+var_117A], dx
0x180009922  mov     [rsp+11E0h+var_1178], cl
0x180009926  test    dx, dx
0x180009929  jz      short loc_180009948
0x18000992b  mov     eax, edx
0x18000992d  cmp     cl, 1
0x180009930  jnz     short loc_180009938
0x180009932  add     rax, 2
0x180009936  jmp     short loc_180009941
0x180009938  cmp     cl, 2
0x18000993b  jnz     short loc_180009941
0x18000993d  add     rax, 4
0x180009941  mov     [rsp+11E0h+var_1170], rax
0x180009946  jmp     short loc_18000994D
0x180009948  mov     [rsp+11E0h+var_1170], r15
0x18000994d  mov     [rsp+11E0h+var_1168], r15
0x180009952  xorps   xmm0, xmm0
0x180009955  movdqa  [rbp+10E0h+var_1160], xmm0
0x18000995a  mov     [rbp+10E0h+lpMem], r15
0x18000995e  mov     [rbp+10E0h+var_1148], 0
0x180009964  mov     [rbp+10E0h+var_1146], r15b
0x180009968  mov     [rsp+11E0h+var_1198], r15d
0x18000996d  mov     dword ptr [rsp+11E0h+var_11A0], 1000h
0x180009975  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000997c  test    rax, rax
0x18000997f  jnz     short loc_1800099C4
0x180009981  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009988  test    rax, rax
0x18000998b  jnz     short loc_1800099A1
0x18000998d  lea     rcx, ModuleName; "ntdll.dll"
0x180009994  call    cs:__imp_GetModuleHandleW
0x18000999a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800099a1  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800099a8  mov     rcx, rax; hModule
0x1800099ab  call    cs:__imp_GetProcAddress
0x1800099b1  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800099b8  test    rax, rax
0x1800099bb  jnz     short loc_1800099C4
0x1800099bd  mov     ebx, 0C0000139h
0x1800099c2  jmp     short loc_1800099EE
0x1800099c4  lea     rcx, [rsp+11E0h+var_11A0]
0x1800099c9  mov     [rsp+11E0h+var_11B8], rcx
0x1800099ce  lea     rcx, [rbp+10E0h+var_1040]
0x1800099d5  mov     [rsp+11E0h+var_11C0], rcx
0x1800099da  lea     r9, [rsp+11E0h+var_1198]
0x1800099df  xor     r8d, r8d
0x1800099e2  xor     edx, edx
0x1800099e4  mov     rcx, r14
0x1800099e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ec  mov     ebx, eax
0x1800099ee  mov     ecx, ebx; this
0x1800099f0  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800099f5  test    ebx, ebx
0x1800099f7  jz      short loc_180009A07
0x1800099f9  mov     eax, r15d
0x1800099fc  mov     dword ptr [rsp+11E0h+var_11A0], eax
0x180009a00  mov     [rsp+11E0h+var_1198], r15d
0x180009a05  jmp     short loc_180009A0B
0x180009a07  mov     eax, dword ptr [rsp+11E0h+var_11A0]
0x180009a0b  mov     r8d, eax; unsigned __int64
0x180009a0e  mov     r9d, 1000h; unsigned __int64
0x180009a14  lea     rdx, [rbp+10E0h+var_1040]; void *
0x180009a1b  lea     rcx, [rsp+11E0h+var_1180]; this
0x180009a20  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180009a25  cmp     byte ptr [rbp+10E0h+var_1148+1], r15b
0x180009a29  jnz     loc_180009C3B
0x180009a2f  mov     [rbp+10E0h+var_1140], r15
0x180009a33  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180009a3a  mov     [rbp+10E0h+var_10B8], rax
0x180009a3e  lea     rax, [rbp+10E0h+var_1140]
0x180009a42  mov     [rbp+10E0h+var_10B0], rax
0x180009a46  lea     rax, [rbp+10E0h+var_1138]
0x180009a4a  mov     [rbp+10E0h+var_10A8], rax
0x180009a4e  lea     rax, [rsp+11E0h+var_1180]
0x180009a53  mov     [rbp+10E0h+var_10A0], rax
0x180009a57  lea     rax, [rbp+10E0h+var_10B8]
0x180009a5b  mov     [rbp+10E0h+var_1050], rax
0x180009a62  lea     rax, [rbp+10E0h+var_10C0]
0x180009a66  mov     [rbp+10E0h+var_10C8], rax
0x180009a6a  mov     rax, [rdi+18h]
0x180009a6e  add     rax, 0Ah
0x180009a72  mov     [rsp+11E0h+var_11A0], rax
0x180009a77  movzx   eax, word ptr [rdi+2]
0x180009a7b  mov     [rbp+10E0h+var_1130], ax
0x180009a7f  mov     al, [rdi+4]
0x180009a82  mov     [rbp+10E0h+var_112E], al
0x180009a85  mov     [rbp+10E0h+var_112C], r15d
0x180009a89  mov     [rbp+10E0h+var_1128], r15w
0x180009a8e  xorps   xmm0, xmm0
0x180009a91  movdqu  [rbp+10E0h+var_1120], xmm0
0x180009a96  movzx   eax, word ptr [rdi+6]
0x180009a9a  mov     [rbp+10E0h+var_1110], ax
0x180009a9e  mov     al, [rdi+8]
0x180009aa1  mov     [rbp+10E0h+var_110E], al
0x180009aa4  mov     [rbp+10E0h+var_110C], r15d
0x180009aa8  mov     [rbp+10E0h+var_1108], r15w
0x180009aad  movdqu  [rbp+10E0h+var_1100], xmm0
0x180009ab2  jmp     loc_180009B4A
0x180009ab7  mov     ebx, r15d
0x180009aba  mov     esi, [rbp+10E0h+var_112C]
0x180009abd  test    esi, esi
0x180009abf  jz      loc_180009B4A
0x180009ac5  mov     r15, qword ptr [rbp+10E0h+var_1120+8]
0x180009ac9  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009acd  lea     rdx, [rsp+11E0h+var_11A0]; unsigned __int8 **
0x180009ad2  lea     rcx, [rbp+10E0h+var_1110]; this
0x180009ad6  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009adb  test    al, al
0x180009add  jz      short loc_180009B47
0x180009adf  mov     eax, [rbp+10E0h+var_110C]
0x180009ae2  mov     [rsp+11E0h+var_1190], eax
0x180009ae6  movzx   eax, [rbp+10E0h+var_1108]
0x180009aea  mov     [rbp+10E0h+var_10F0], rax
0x180009aee  mov     rax, qword ptr [rbp+10E0h+var_1100+8]
0x180009af2  mov     [rbp+10E0h+var_10E8], rax
0x180009af6  movzx   eax, [rbp+10E0h+var_1128]
0x180009afa  mov     [rbp+10E0h+var_10E0], rax
0x180009afe  mov     [rbp+10E0h+var_10D8], r15
0x180009b02  mov     rcx, [rbp+10E0h+var_1050]; this
0x180009b09  test    rcx, rcx
0x180009b0c  jz      loc_180009C86
0x180009b12  mov     rax, [rcx]
0x180009b15  lea     rdx, [rsp+11E0h+var_1190]
0x180009b1a  mov     [rsp+11E0h+var_11B8], rdx
0x180009b1f  lea     rdx, [rbp+10E0h+var_10F0]
0x180009b23  mov     [rsp+11E0h+var_11C0], rdx
0x180009b28  lea     r9, [rbp+10E0h+var_10E8]
0x180009b2c  lea     r8, [rbp+10E0h+var_10E0]
0x180009b30  lea     rdx, [rbp+10E0h+var_10D8]
0x180009b34  mov     rax, [rax+20h]
0x180009b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b3d  test    al, al
0x180009b3f  jz      short loc_180009BB7
0x180009b41  inc     ebx
0x180009b43  cmp     ebx, esi
0x180009b45  jb      short loc_180009AC9
0x180009b47  xor     r15d, r15d
0x180009b4a  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009b4e  lea     rdx, [rsp+11E0h+var_11A0]; unsigned __int8 **
0x180009b53  lea     rcx, [rbp+10E0h+var_1130]; this
0x180009b57  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009b5c  test    al, al
0x180009b5e  jnz     loc_180009AB7
0x180009b64  mov     rcx, [rbp+10E0h+var_1050]
0x180009b6b  test    rcx, rcx
0x180009b6e  jz      short loc_180009B7C
0x180009b70  mov     rax, [rcx]
0x180009b73  mov     rax, [rax+18h]
0x180009b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b7c  mov     bl, 1
0x180009b7e  cmp     byte ptr [rbp+10E0h+var_1148], r15b
0x180009b82  jz      short loc_180009BF9
0x180009b84  mov     eax, [rsp+11E0h+var_1198]
0x180009b88  mov     rdx, [rsp+11E0h+var_1168]
0x180009b8d  mov     r8d, dword ptr [rbp+10E0h+var_1160]
0x180009b91  sub     r8d, edx
0x180009b94  mov     [rsp+11E0h+var_11B0], 1
0x180009b9c  mov     dword ptr [rsp+11E0h+var_11B8], eax
0x180009ba0  mov     rcx, r14
0x180009ba3  call    wil_details_NtUpdateWnfStateData
0x180009ba8  cmp     eax, 0C0000001h
0x180009bad  jnz     short loc_180009BD7
0x180009baf  inc     r12
0x180009bb2  mov     bl, r15b
0x180009bb5  jmp     short loc_180009C05
0x180009bb7  mov     rcx, [rbp+10E0h+var_1050]
0x180009bbe  xor     r15d, r15d
0x180009bc1  test    rcx, rcx
0x180009bc4  jz      short loc_180009BD2
0x180009bc6  mov     rax, [rcx]
0x180009bc9  mov     rax, [rax+18h]
0x180009bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bd2  mov     bl, r15b
0x180009bd5  jmp     short loc_180009B7E
0x180009bd7  test    eax, eax
0x180009bd9  jz      short loc_180009BF9
0x180009bdb  mov     rdx, [rsp+11E0h+var_1168]
0x180009be0  mov     r8d, dword ptr [rbp+10E0h+var_1160]
0x180009be4  sub     r8d, edx
0x180009be7  mov     [rsp+11E0h+var_11B0], r15d
0x180009bec  mov     dword ptr [rsp+11E0h+var_11B8], r15d
0x180009bf1  mov     rcx, r14
0x180009bf4  call    wil_details_NtUpdateWnfStateData
0x180009bf9  add     r14, 8
0x180009bfd  mov     rax, [rbp+10E0h+var_1140]
0x180009c01  mov     [rbp+10E0h+var_1138], rax
0x180009c05  mov     rsi, [rbp+10E0h+lpMem]
0x180009c09  mov     [rbp+10E0h+lpMem], r15
0x180009c0d  test    rsi, rsi
0x180009c10  jz      short loc_180009C26
0x180009c12  call    cs:__imp_GetProcessHeap
0x180009c18  mov     rcx, rax; hHeap
0x180009c1b  mov     r8, rsi; lpMem
0x180009c1e  xor     edx, edx; dwFlags
0x180009c20  call    cs:__imp_HeapFree
0x180009c26  test    bl, bl
0x180009c28  jnz     short loc_180009C5C
0x180009c2a  cmp     r14, r13
0x180009c2d  jnb     short loc_180009C5C
0x180009c2f  cmp     r12, 32h ; '2'
0x180009c33  jb      loc_1800098FE
0x180009c39  jmp     short loc_180009C5C
0x180009c3b  mov     rbx, [rbp+10E0h+lpMem]
0x180009c3f  mov     [rbp+10E0h+lpMem], r15
0x180009c43  test    rbx, rbx
0x180009c46  jz      short loc_180009C5C
0x180009c48  call    cs:__imp_GetProcessHeap
0x180009c4e  mov     rcx, rax; hHeap
0x180009c51  mov     r8, rbx; lpMem
0x180009c54  xor     edx, edx; dwFlags
0x180009c56  call    cs:__imp_HeapFree
0x180009c5c  mov     rcx, [rbp+10E0h+var_40]
0x180009c63  xor     rcx, rsp; StackCookie
0x180009c66  call    __security_check_cookie
0x180009c6b  mov     rbx, [rsp+11E0h+arg_8]
0x180009c73  add     rsp, 11B0h
0x180009c7a  pop     r15
0x180009c7c  pop     r14
0x180009c7e  pop     r13
0x180009c80  pop     r12
0x180009c82  pop     rdi
0x180009c83  pop     rsi
0x180009c84  pop     rbp
0x180009c85  retn
0x180009c86  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
