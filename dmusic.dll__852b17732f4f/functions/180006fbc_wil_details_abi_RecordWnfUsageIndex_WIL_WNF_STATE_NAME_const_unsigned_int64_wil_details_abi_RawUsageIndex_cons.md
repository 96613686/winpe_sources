# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180006fbc`
- end: `0x180007394`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800064a8`

## callees

- `0x1800016d0`
- `0x180005f1c`
- `0x1800063a8`
- `0x180006fbc`
- `0x180007994`
- `0x180008ebc`
- `0x1800096e0`
- `0x180021750`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000709c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000709c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800070b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800070b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007328`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000735e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007328`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000735e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000731a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007350`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000731a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007350`

## string_xrefs

- `0x180007095`: `ntdll.dll`

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
0x180006fbc  mov     [rsp-8+arg_8], rbx
0x180006fc1  push    rbp
0x180006fc2  push    rsi
0x180006fc3  push    rdi
0x180006fc4  push    r12
0x180006fc6  push    r13
0x180006fc8  push    r14
0x180006fca  push    r15
0x180006fcc  lea     rbp, [rsp-10A0h]
0x180006fd4  mov     eax, 11A0h
0x180006fd9  call    _alloca_probe
0x180006fde  sub     rsp, rax
0x180006fe1  mov     rax, cs:__security_cookie
0x180006fe8  xor     rax, rsp
0x180006feb  mov     [rbp+10D0h+var_40], rax
0x180006ff2  mov     rdi, r8
0x180006ff5  mov     r14, rcx
0x180006ff8  lea     r13, [rcx+rdx*8]
0x180006ffc  xor     r15d, r15d
0x180006fff  mov     r12d, r15d
0x180007002  mov     [rbp+10D0h+var_1128], r15
0x180007006  mov     cl, [rdi+8]
0x180007009  movzx   edx, word ptr [rdi+6]
0x18000700d  movzx   eax, word ptr [rdi]
0x180007010  mov     [rsp+11D0h+var_1170], ax
0x180007015  movzx   eax, word ptr [rdi+2]
0x180007019  mov     [rsp+11D0h+var_116E], ax
0x18000701e  mov     al, [rdi+4]
0x180007021  mov     [rsp+11D0h+var_116C], al
0x180007025  mov     [rsp+11D0h+var_116A], dx
0x18000702a  mov     [rsp+11D0h+var_1168], cl
0x18000702e  test    dx, dx
0x180007031  jz      short loc_180007050
0x180007033  mov     eax, edx
0x180007035  cmp     cl, 1
0x180007038  jnz     short loc_180007040
0x18000703a  add     rax, 2
0x18000703e  jmp     short loc_180007049
0x180007040  cmp     cl, 2
0x180007043  jnz     short loc_180007049
0x180007045  add     rax, 4
0x180007049  mov     [rsp+11D0h+var_1160], rax
0x18000704e  jmp     short loc_180007055
0x180007050  mov     [rsp+11D0h+var_1160], r15
0x180007055  mov     [rsp+11D0h+var_1158], r15
0x18000705a  xorps   xmm0, xmm0
0x18000705d  movdqa  [rbp+10D0h+var_1150], xmm0
0x180007062  mov     [rbp+10D0h+lpMem], r15
0x180007066  mov     [rbp+10D0h+var_1138], 0
0x18000706c  mov     [rbp+10D0h+var_1136], r15b
0x180007070  mov     [rsp+11D0h+var_1188], r15d
0x180007075  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000707d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180007084  test    rax, rax
0x180007087  jnz     short loc_1800070CC
0x180007089  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007090  test    rax, rax
0x180007093  jnz     short loc_1800070A9
0x180007095  lea     rcx, ModuleName; "ntdll.dll"
0x18000709c  call    cs:__imp_GetModuleHandleW
0x1800070a2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800070a9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800070b0  mov     rcx, rax; hModule
0x1800070b3  call    cs:__imp_GetProcAddress
0x1800070b9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800070c0  test    rax, rax
0x1800070c3  jnz     short loc_1800070CC
0x1800070c5  mov     ebx, 0C0000139h
0x1800070ca  jmp     short loc_1800070F6
0x1800070cc  lea     rcx, [rsp+11D0h+var_1190]
0x1800070d1  mov     [rsp+11D0h+var_11A8], rcx
0x1800070d6  lea     rcx, [rbp+10D0h+var_1040]
0x1800070dd  mov     [rsp+11D0h+var_11B0], rcx
0x1800070e2  lea     r9, [rsp+11D0h+var_1188]
0x1800070e7  xor     r8d, r8d
0x1800070ea  xor     edx, edx
0x1800070ec  mov     rcx, r14
0x1800070ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070f4  mov     ebx, eax
0x1800070f6  mov     ecx, ebx; this
0x1800070f8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800070fd  test    ebx, ebx
0x1800070ff  jz      short loc_18000710F
0x180007101  mov     eax, r15d
0x180007104  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180007108  mov     [rsp+11D0h+var_1188], r15d
0x18000710d  jmp     short loc_180007113
0x18000710f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180007113  mov     r8d, eax; unsigned __int64
0x180007116  mov     r9d, 1000h; unsigned __int64
0x18000711c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180007123  lea     rcx, [rsp+11D0h+var_1170]; this
0x180007128  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000712d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180007131  jnz     loc_180007343
0x180007137  mov     [rbp+10D0h+var_1130], r15
0x18000713b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180007142  mov     [rbp+10D0h+var_10B0], rax
0x180007146  lea     rax, [rbp+10D0h+var_1130]
0x18000714a  mov     [rbp+10D0h+var_10A8], rax
0x18000714e  lea     rax, [rbp+10D0h+var_1128]
0x180007152  mov     [rbp+10D0h+var_10A0], rax
0x180007156  lea     rax, [rsp+11D0h+var_1170]
0x18000715b  mov     [rbp+10D0h+var_1098], rax
0x18000715f  lea     rax, [rbp+10D0h+var_10B0]
0x180007163  mov     [rbp+10D0h+var_1048], rax
0x18000716a  lea     rax, [rbp+10D0h+var_10B8]
0x18000716e  mov     [rbp+10D0h+var_10C0], rax
0x180007172  mov     rax, [rdi+18h]
0x180007176  add     rax, 0Ah
0x18000717a  mov     [rsp+11D0h+var_1190], rax
0x18000717f  movzx   eax, word ptr [rdi+2]
0x180007183  mov     [rbp+10D0h+var_1120], ax
0x180007187  mov     al, [rdi+4]
0x18000718a  mov     [rbp+10D0h+var_111E], al
0x18000718d  mov     [rbp+10D0h+var_111C], r15d
0x180007191  mov     [rbp+10D0h+var_1118], r15w
0x180007196  xorps   xmm0, xmm0
0x180007199  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000719e  movzx   eax, word ptr [rdi+6]
0x1800071a2  mov     [rbp+10D0h+var_1100], ax
0x1800071a6  mov     al, [rdi+8]
0x1800071a9  mov     [rbp+10D0h+var_10FE], al
0x1800071ac  mov     [rbp+10D0h+var_10FC], r15d
0x1800071b0  mov     [rbp+10D0h+var_10F8], r15w
0x1800071b5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800071ba  jmp     loc_180007252
0x1800071bf  mov     ebx, r15d
0x1800071c2  mov     esi, [rbp+10D0h+var_111C]
0x1800071c5  test    esi, esi
0x1800071c7  jz      loc_180007252
0x1800071cd  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x1800071d1  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800071d5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800071da  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800071de  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800071e3  test    al, al
0x1800071e5  jz      short loc_18000724F
0x1800071e7  mov     eax, [rbp+10D0h+var_10FC]
0x1800071ea  mov     [rsp+11D0h+var_1180], eax
0x1800071ee  movzx   eax, [rbp+10D0h+var_10F8]
0x1800071f2  mov     [rbp+10D0h+var_10E0], rax
0x1800071f6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1800071fa  mov     [rbp+10D0h+var_10D8], rax
0x1800071fe  movzx   eax, [rbp+10D0h+var_1118]
0x180007202  mov     [rbp+10D0h+var_10D0], rax
0x180007206  mov     [rbp+10D0h+var_10C8], r15
0x18000720a  mov     rcx, [rbp+10D0h+var_1048]; this
0x180007211  test    rcx, rcx
0x180007214  jz      loc_18000738E
0x18000721a  mov     rax, [rcx]
0x18000721d  lea     rdx, [rsp+11D0h+var_1180]
0x180007222  mov     [rsp+11D0h+var_11A8], rdx
0x180007227  lea     rdx, [rbp+10D0h+var_10E0]
0x18000722b  mov     [rsp+11D0h+var_11B0], rdx
0x180007230  lea     r9, [rbp+10D0h+var_10D8]
0x180007234  lea     r8, [rbp+10D0h+var_10D0]
0x180007238  lea     rdx, [rbp+10D0h+var_10C8]
0x18000723c  mov     rax, [rax+20h]
0x180007240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007245  test    al, al
0x180007247  jz      short loc_1800072BF
0x180007249  inc     ebx
0x18000724b  cmp     ebx, esi
0x18000724d  jb      short loc_1800071D1
0x18000724f  xor     r15d, r15d
0x180007252  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007256  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000725b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000725f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007264  test    al, al
0x180007266  jnz     loc_1800071BF
0x18000726c  mov     rcx, [rbp+10D0h+var_1048]
0x180007273  test    rcx, rcx
0x180007276  jz      short loc_180007284
0x180007278  mov     rax, [rcx]
0x18000727b  mov     rax, [rax+18h]
0x18000727f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007284  mov     bl, 1
0x180007286  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000728a  jz      short loc_180007301
0x18000728c  mov     eax, [rsp+11D0h+var_1188]
0x180007290  mov     rdx, [rsp+11D0h+var_1158]
0x180007295  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180007299  sub     r8d, edx
0x18000729c  mov     [rsp+11D0h+var_11A0], 1
0x1800072a4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800072a8  mov     rcx, r14
0x1800072ab  call    wil_details_NtUpdateWnfStateData
0x1800072b0  cmp     eax, 0C0000001h
0x1800072b5  jnz     short loc_1800072DF
0x1800072b7  inc     r12
0x1800072ba  mov     bl, r15b
0x1800072bd  jmp     short loc_18000730D
0x1800072bf  mov     rcx, [rbp+10D0h+var_1048]
0x1800072c6  xor     r15d, r15d
0x1800072c9  test    rcx, rcx
0x1800072cc  jz      short loc_1800072DA
0x1800072ce  mov     rax, [rcx]
0x1800072d1  mov     rax, [rax+18h]
0x1800072d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072da  mov     bl, r15b
0x1800072dd  jmp     short loc_180007286
0x1800072df  test    eax, eax
0x1800072e1  jz      short loc_180007301
0x1800072e3  mov     rdx, [rsp+11D0h+var_1158]
0x1800072e8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800072ec  sub     r8d, edx
0x1800072ef  mov     [rsp+11D0h+var_11A0], r15d
0x1800072f4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x1800072f9  mov     rcx, r14
0x1800072fc  call    wil_details_NtUpdateWnfStateData
0x180007301  add     r14, 8
0x180007305  mov     rax, [rbp+10D0h+var_1130]
0x180007309  mov     [rbp+10D0h+var_1128], rax
0x18000730d  mov     rsi, [rbp+10D0h+lpMem]
0x180007311  mov     [rbp+10D0h+lpMem], r15
0x180007315  test    rsi, rsi
0x180007318  jz      short loc_18000732E
0x18000731a  call    cs:__imp_GetProcessHeap
0x180007320  mov     rcx, rax; hHeap
0x180007323  mov     r8, rsi; lpMem
0x180007326  xor     edx, edx; dwFlags
0x180007328  call    cs:__imp_HeapFree
0x18000732e  test    bl, bl
0x180007330  jnz     short loc_180007364
0x180007332  cmp     r14, r13
0x180007335  jnb     short loc_180007364
0x180007337  cmp     r12, 32h ; '2'
0x18000733b  jb      loc_180007006
0x180007341  jmp     short loc_180007364
0x180007343  mov     rbx, [rbp+10D0h+lpMem]
0x180007347  mov     [rbp+10D0h+lpMem], r15
0x18000734b  test    rbx, rbx
0x18000734e  jz      short loc_180007364
0x180007350  call    cs:__imp_GetProcessHeap
0x180007356  mov     rcx, rax; hHeap
0x180007359  mov     r8, rbx; lpMem
0x18000735c  xor     edx, edx; dwFlags
0x18000735e  call    cs:__imp_HeapFree
0x180007364  mov     rcx, [rbp+10D0h+var_40]
0x18000736b  xor     rcx, rsp; StackCookie
0x18000736e  call    __security_check_cookie
0x180007373  mov     rbx, [rsp+11D0h+arg_8]
0x18000737b  add     rsp, 11A0h
0x180007382  pop     r15
0x180007384  pop     r14
0x180007386  pop     r13
0x180007388  pop     r12
0x18000738a  pop     rdi
0x18000738b  pop     rsi
0x18000738c  pop     rbp
0x18000738d  retn
0x18000738e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
