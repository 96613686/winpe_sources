# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x140007f4c`
- end: `0x140008324`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14000742c`

## callees

- `0x140001ba0`
- `0x140006d68`
- `0x14000732c`
- `0x140007f4c`
- `0x140008c04`
- `0x14000a11c`
- `0x14000ad60`
- `0x1400a7290`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000802c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000802c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008043`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008043`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400082aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400082e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400082aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400082e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400082b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400082ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400082b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400082ee`

## string_xrefs

- `0x140008025`: `ntdll.dll`

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
0x140007f4c  mov     [rsp-8+arg_8], rbx
0x140007f51  push    rbp
0x140007f52  push    rsi
0x140007f53  push    rdi
0x140007f54  push    r12
0x140007f56  push    r13
0x140007f58  push    r14
0x140007f5a  push    r15
0x140007f5c  lea     rbp, [rsp-10A0h]
0x140007f64  mov     eax, 11A0h
0x140007f69  call    _alloca_probe
0x140007f6e  sub     rsp, rax
0x140007f71  mov     rax, cs:__security_cookie
0x140007f78  xor     rax, rsp
0x140007f7b  mov     [rbp+10D0h+var_40], rax
0x140007f82  mov     rdi, r8
0x140007f85  mov     r14, rcx
0x140007f88  lea     r13, [rcx+rdx*8]
0x140007f8c  xor     r15d, r15d
0x140007f8f  mov     r12d, r15d
0x140007f92  mov     [rbp+10D0h+var_1128], r15
0x140007f96  mov     cl, [rdi+8]
0x140007f99  movzx   edx, word ptr [rdi+6]
0x140007f9d  movzx   eax, word ptr [rdi]
0x140007fa0  mov     [rsp+11D0h+var_1170], ax
0x140007fa5  movzx   eax, word ptr [rdi+2]
0x140007fa9  mov     [rsp+11D0h+var_116E], ax
0x140007fae  mov     al, [rdi+4]
0x140007fb1  mov     [rsp+11D0h+var_116C], al
0x140007fb5  mov     [rsp+11D0h+var_116A], dx
0x140007fba  mov     [rsp+11D0h+var_1168], cl
0x140007fbe  test    dx, dx
0x140007fc1  jz      short loc_140007FE0
0x140007fc3  mov     eax, edx
0x140007fc5  cmp     cl, 1
0x140007fc8  jnz     short loc_140007FD0
0x140007fca  add     rax, 2
0x140007fce  jmp     short loc_140007FD9
0x140007fd0  cmp     cl, 2
0x140007fd3  jnz     short loc_140007FD9
0x140007fd5  add     rax, 4
0x140007fd9  mov     [rsp+11D0h+var_1160], rax
0x140007fde  jmp     short loc_140007FE5
0x140007fe0  mov     [rsp+11D0h+var_1160], r15
0x140007fe5  mov     [rsp+11D0h+var_1158], r15
0x140007fea  xorps   xmm0, xmm0
0x140007fed  movdqa  [rbp+10D0h+var_1150], xmm0
0x140007ff2  mov     [rbp+10D0h+lpMem], r15
0x140007ff6  mov     [rbp+10D0h+var_1138], 0
0x140007ffc  mov     [rbp+10D0h+var_1136], r15b
0x140008000  mov     [rsp+11D0h+var_1188], r15d
0x140008005  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x14000800d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140008014  test    rax, rax
0x140008017  jnz     short loc_14000805C
0x140008019  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008020  test    rax, rax
0x140008023  jnz     short loc_140008039
0x140008025  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000802c  call    cs:__imp_GetModuleHandleW
0x140008032  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008039  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140008040  mov     rcx, rax; hModule
0x140008043  call    cs:__imp_GetProcAddress
0x140008049  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140008050  test    rax, rax
0x140008053  jnz     short loc_14000805C
0x140008055  mov     ebx, 0C0000139h
0x14000805a  jmp     short loc_140008086
0x14000805c  lea     rcx, [rsp+11D0h+var_1190]
0x140008061  mov     [rsp+11D0h+var_11A8], rcx
0x140008066  lea     rcx, [rbp+10D0h+var_1040]
0x14000806d  mov     [rsp+11D0h+var_11B0], rcx
0x140008072  lea     r9, [rsp+11D0h+var_1188]
0x140008077  xor     r8d, r8d
0x14000807a  xor     edx, edx
0x14000807c  mov     rcx, r14
0x14000807f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008084  mov     ebx, eax
0x140008086  mov     ecx, ebx; this
0x140008088  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000808d  test    ebx, ebx
0x14000808f  jz      short loc_14000809F
0x140008091  mov     eax, r15d
0x140008094  mov     dword ptr [rsp+11D0h+var_1190], eax
0x140008098  mov     [rsp+11D0h+var_1188], r15d
0x14000809d  jmp     short loc_1400080A3
0x14000809f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x1400080a3  mov     r8d, eax; unsigned __int64
0x1400080a6  mov     r9d, 1000h; unsigned __int64
0x1400080ac  lea     rdx, [rbp+10D0h+var_1040]; void *
0x1400080b3  lea     rcx, [rsp+11D0h+var_1170]; this
0x1400080b8  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1400080bd  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x1400080c1  jnz     loc_1400082D3
0x1400080c7  mov     [rbp+10D0h+var_1130], r15
0x1400080cb  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1400080d2  mov     [rbp+10D0h+var_10B0], rax
0x1400080d6  lea     rax, [rbp+10D0h+var_1130]
0x1400080da  mov     [rbp+10D0h+var_10A8], rax
0x1400080de  lea     rax, [rbp+10D0h+var_1128]
0x1400080e2  mov     [rbp+10D0h+var_10A0], rax
0x1400080e6  lea     rax, [rsp+11D0h+var_1170]
0x1400080eb  mov     [rbp+10D0h+var_1098], rax
0x1400080ef  lea     rax, [rbp+10D0h+var_10B0]
0x1400080f3  mov     [rbp+10D0h+var_1048], rax
0x1400080fa  lea     rax, [rbp+10D0h+var_10B8]
0x1400080fe  mov     [rbp+10D0h+var_10C0], rax
0x140008102  mov     rax, [rdi+18h]
0x140008106  add     rax, 0Ah
0x14000810a  mov     [rsp+11D0h+var_1190], rax
0x14000810f  movzx   eax, word ptr [rdi+2]
0x140008113  mov     [rbp+10D0h+var_1120], ax
0x140008117  mov     al, [rdi+4]
0x14000811a  mov     [rbp+10D0h+var_111E], al
0x14000811d  mov     [rbp+10D0h+var_111C], r15d
0x140008121  mov     [rbp+10D0h+var_1118], r15w
0x140008126  xorps   xmm0, xmm0
0x140008129  movdqu  [rbp+10D0h+var_1110], xmm0
0x14000812e  movzx   eax, word ptr [rdi+6]
0x140008132  mov     [rbp+10D0h+var_1100], ax
0x140008136  mov     al, [rdi+8]
0x140008139  mov     [rbp+10D0h+var_10FE], al
0x14000813c  mov     [rbp+10D0h+var_10FC], r15d
0x140008140  mov     [rbp+10D0h+var_10F8], r15w
0x140008145  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14000814a  jmp     loc_1400081E2
0x14000814f  mov     ebx, r15d
0x140008152  mov     esi, [rbp+10D0h+var_111C]
0x140008155  test    esi, esi
0x140008157  jz      loc_1400081E2
0x14000815d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x140008161  mov     r8, [rdi+20h]; unsigned __int8 *
0x140008165  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000816a  lea     rcx, [rbp+10D0h+var_1100]; this
0x14000816e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140008173  test    al, al
0x140008175  jz      short loc_1400081DF
0x140008177  mov     eax, [rbp+10D0h+var_10FC]
0x14000817a  mov     [rsp+11D0h+var_1180], eax
0x14000817e  movzx   eax, [rbp+10D0h+var_10F8]
0x140008182  mov     [rbp+10D0h+var_10E0], rax
0x140008186  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14000818a  mov     [rbp+10D0h+var_10D8], rax
0x14000818e  movzx   eax, [rbp+10D0h+var_1118]
0x140008192  mov     [rbp+10D0h+var_10D0], rax
0x140008196  mov     [rbp+10D0h+var_10C8], r15
0x14000819a  mov     rcx, [rbp+10D0h+var_1048]; this
0x1400081a1  test    rcx, rcx
0x1400081a4  jz      loc_14000831E
0x1400081aa  mov     rax, [rcx]
0x1400081ad  lea     rdx, [rsp+11D0h+var_1180]
0x1400081b2  mov     [rsp+11D0h+var_11A8], rdx
0x1400081b7  lea     rdx, [rbp+10D0h+var_10E0]
0x1400081bb  mov     [rsp+11D0h+var_11B0], rdx
0x1400081c0  lea     r9, [rbp+10D0h+var_10D8]
0x1400081c4  lea     r8, [rbp+10D0h+var_10D0]
0x1400081c8  lea     rdx, [rbp+10D0h+var_10C8]
0x1400081cc  mov     rax, [rax+20h]
0x1400081d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400081d5  test    al, al
0x1400081d7  jz      short loc_14000824F
0x1400081d9  inc     ebx
0x1400081db  cmp     ebx, esi
0x1400081dd  jb      short loc_140008161
0x1400081df  xor     r15d, r15d
0x1400081e2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400081e6  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1400081eb  lea     rcx, [rbp+10D0h+var_1120]; this
0x1400081ef  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400081f4  test    al, al
0x1400081f6  jnz     loc_14000814F
0x1400081fc  mov     rcx, [rbp+10D0h+var_1048]
0x140008203  test    rcx, rcx
0x140008206  jz      short loc_140008214
0x140008208  mov     rax, [rcx]
0x14000820b  mov     rax, [rax+18h]
0x14000820f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008214  mov     bl, 1
0x140008216  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x14000821a  jz      short loc_140008291
0x14000821c  mov     eax, [rsp+11D0h+var_1188]
0x140008220  mov     rdx, [rsp+11D0h+var_1158]
0x140008225  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x140008229  sub     r8d, edx
0x14000822c  mov     [rsp+11D0h+var_11A0], 1
0x140008234  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x140008238  mov     rcx, r14
0x14000823b  call    wil_details_NtUpdateWnfStateData
0x140008240  cmp     eax, 0C0000001h
0x140008245  jnz     short loc_14000826F
0x140008247  inc     r12
0x14000824a  mov     bl, r15b
0x14000824d  jmp     short loc_14000829D
0x14000824f  mov     rcx, [rbp+10D0h+var_1048]
0x140008256  xor     r15d, r15d
0x140008259  test    rcx, rcx
0x14000825c  jz      short loc_14000826A
0x14000825e  mov     rax, [rcx]
0x140008261  mov     rax, [rax+18h]
0x140008265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000826a  mov     bl, r15b
0x14000826d  jmp     short loc_140008216
0x14000826f  test    eax, eax
0x140008271  jz      short loc_140008291
0x140008273  mov     rdx, [rsp+11D0h+var_1158]
0x140008278  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000827c  sub     r8d, edx
0x14000827f  mov     [rsp+11D0h+var_11A0], r15d
0x140008284  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x140008289  mov     rcx, r14
0x14000828c  call    wil_details_NtUpdateWnfStateData
0x140008291  add     r14, 8
0x140008295  mov     rax, [rbp+10D0h+var_1130]
0x140008299  mov     [rbp+10D0h+var_1128], rax
0x14000829d  mov     rsi, [rbp+10D0h+lpMem]
0x1400082a1  mov     [rbp+10D0h+lpMem], r15
0x1400082a5  test    rsi, rsi
0x1400082a8  jz      short loc_1400082BE
0x1400082aa  call    cs:__imp_GetProcessHeap
0x1400082b0  mov     rcx, rax; hHeap
0x1400082b3  mov     r8, rsi; lpMem
0x1400082b6  xor     edx, edx; dwFlags
0x1400082b8  call    cs:__imp_HeapFree
0x1400082be  test    bl, bl
0x1400082c0  jnz     short loc_1400082F4
0x1400082c2  cmp     r14, r13
0x1400082c5  jnb     short loc_1400082F4
0x1400082c7  cmp     r12, 32h ; '2'
0x1400082cb  jb      loc_140007F96
0x1400082d1  jmp     short loc_1400082F4
0x1400082d3  mov     rbx, [rbp+10D0h+lpMem]
0x1400082d7  mov     [rbp+10D0h+lpMem], r15
0x1400082db  test    rbx, rbx
0x1400082de  jz      short loc_1400082F4
0x1400082e0  call    cs:__imp_GetProcessHeap
0x1400082e6  mov     rcx, rax; hHeap
0x1400082e9  mov     r8, rbx; lpMem
0x1400082ec  xor     edx, edx; dwFlags
0x1400082ee  call    cs:__imp_HeapFree
0x1400082f4  mov     rcx, [rbp+10D0h+var_40]
0x1400082fb  xor     rcx, rsp; StackCookie
0x1400082fe  call    __security_check_cookie
0x140008303  mov     rbx, [rsp+11D0h+arg_8]
0x14000830b  add     rsp, 11A0h
0x140008312  pop     r15
0x140008314  pop     r14
0x140008316  pop     r13
0x140008318  pop     r12
0x14000831a  pop     rdi
0x14000831b  pop     rsi
0x14000831c  pop     rbp
0x14000831d  retn
0x14000831e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
