# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180008eac`
- end: `0x180009279`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800083f8`

## callees

- `0x180007f18`
- `0x180008308`
- `0x180008eac`
- `0x18000986c`
- `0x18000a56c`
- `0x18000b1e8`
- `0x18000cd10`
- `0x18000cda0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008fa2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008fa2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008f8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008f8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009235`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009235`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000920d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009243`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000920d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009243`

## string_xrefs

- `0x180008f84`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v4; // r12
  unsigned __int64 v5; // r15
  wil::details_abi *v7; // r14
  unsigned int v8; // edx
  char v9; // cl
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // rax
  int v17; // ebx
  __int64 v18; // r9
  char v19; // bl
  int updated; // eax
  __int64 v21; // r9
  void *v22; // rsi
  HANDLE ProcessHeap; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  __int64 *v26; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v29[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v30; // [rsp+64h] [rbp-9Ch]
  __int16 v31; // [rsp+66h] [rbp-9Ah]
  char v32; // [rsp+68h] [rbp-98h]
  __int64 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+78h] [rbp-88h]
  __int128 v35; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v37; // [rsp+98h] [rbp-68h]
  char v38; // [rsp+9Ah] [rbp-66h]
  __int64 v39; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v41; // [rsp+B0h] [rbp-50h] BYREF
  char v42; // [rsp+B2h] [rbp-4Eh]
  unsigned int v43; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v44; // [rsp+B8h] [rbp-48h]
  __int128 v45; // [rsp+C0h] [rbp-40h]
  __int16 v46; // [rsp+D0h] [rbp-30h] BYREF
  char v47; // [rsp+D2h] [rbp-2Eh]
  int v48; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v49; // [rsp+D8h] [rbp-28h]
  __int128 v50; // [rsp+E0h] [rbp-20h]
  __int64 v51; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v52; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v53; // [rsp+100h] [rbp+0h] BYREF
  __int64 v54; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v55[13]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *v56; // [rsp+180h] [rbp+80h]
  _BYTE v57[4096]; // [rsp+190h] [rbp+90h] BYREF

  v4 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v5 = 0;
  v40 = 0;
  v7 = this;
  while ( 1 )
  {
    v8 = *(unsigned __int16 *)(a3 + 6);
    v9 = *(_BYTE *)(a3 + 8);
    v29[0] = *(_WORD *)a3;
    v29[1] = *(_WORD *)(a3 + 2);
    v30 = *(_BYTE *)(a3 + 4);
    v31 = v8;
    v32 = v9;
    if ( (_WORD)v8 )
    {
      v10 = v8;
      if ( v9 == 1 )
      {
        v10 = v8 + 2LL;
      }
      else if ( v9 == 2 )
      {
        v10 = v8 + 4LL;
      }
      v33 = v10;
    }
    else
    {
      v33 = 0;
    }
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    v34 = 0;
    v35 = 0;
    lpMem = 0;
    v37 = 0;
    v38 = 0;
    v28[0] = 0;
    LODWORD(v27) = 4096;
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
      v26 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v7, 0, 0, v28);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      v28[0] = 0;
      LODWORD(v27) = 0;
    }
    else
    {
      v15 = (unsigned int)v27;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v29, v57, v15, 0x1000u);
    if ( HIBYTE(v37) )
      break;
    v39 = 0;
    v55[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v43 = 0;
    v55[1] = &v39;
    v55[2] = &v40;
    v55[3] = v29;
    v56 = (wil::details::in1diag3 *)v55;
    v16 = *(_QWORD *)(a3 + 24);
    v44 = 0;
    v27 = (unsigned __int8 *)(v16 + 10);
    v41 = *(_WORD *)(a3 + 2);
    v42 = *(_BYTE *)(a3 + 4);
    v46 = *(_WORD *)(a3 + 6);
    v47 = *(_BYTE *)(a3 + 8);
    v45 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
LABEL_25:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v41,
              &v27,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v17 = 0;
      if ( v43 )
      {
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v46,
                  &v27,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v28[2] = v48;
          v51 = v49;
          v52 = *((_QWORD *)&v50 + 1);
          v53 = v44;
          v54 = *((_QWORD *)&v45 + 1);
          if ( !v56 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v26 = &v51;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v56 + 32LL))(
                  v56,
                  &v54,
                  &v53,
                  &v52) )
          {
            if ( v56 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
            v19 = 0;
            goto LABEL_29;
          }
          if ( ++v17 >= v43 )
            goto LABEL_25;
        }
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
    v19 = 1;
LABEL_29:
    if ( !(_BYTE)v37 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((__int64)v7, v34, (int)v35 - (int)v34, v18, (int)v26, v28[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v7, v34, v35 - v34, v21, (int)v26, 0, 0);
LABEL_37:
      v7 = (wil::details_abi *)((char *)v7 + 8);
      v40 = v39;
      goto LABEL_38;
    }
    ++v5;
    v19 = 0;
LABEL_38:
    v22 = lpMem;
    lpMem = 0;
    if ( v22 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v22);
    }
    if ( v19 || v7 >= v4 || v5 >= 0x32 )
      return;
  }
  v24 = lpMem;
  lpMem = 0;
  if ( v24 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
  }
}

```

## disassembly

```asm
0x180008eac  mov     [rsp-8+arg_8], rbx
0x180008eb1  push    rbp
0x180008eb2  push    rsi
0x180008eb3  push    rdi
0x180008eb4  push    r12
0x180008eb6  push    r13
0x180008eb8  push    r14
0x180008eba  push    r15
0x180008ebc  lea     rbp, [rsp-10A0h]
0x180008ec4  mov     eax, 11A0h
0x180008ec9  call    _alloca_probe
0x180008ece  sub     rsp, rax
0x180008ed1  mov     rax, cs:__security_cookie
0x180008ed8  xor     rax, rsp
0x180008edb  mov     [rbp+10D0h+var_40], rax
0x180008ee2  xor     r13d, r13d
0x180008ee5  lea     r12, [rcx+rdx*8]
0x180008ee9  mov     r15d, r13d
0x180008eec  mov     [rbp+10D0h+var_1128], r13
0x180008ef0  mov     rdi, r8
0x180008ef3  mov     r14, rcx
0x180008ef6  movzx   eax, word ptr [rdi]
0x180008ef9  movzx   edx, word ptr [rdi+6]
0x180008efd  mov     cl, [rdi+8]
0x180008f00  mov     [rsp+11D0h+var_1170], ax
0x180008f05  movzx   eax, word ptr [rdi+2]
0x180008f09  mov     [rsp+11D0h+var_116E], ax
0x180008f0e  mov     al, [rdi+4]
0x180008f11  mov     [rsp+11D0h+var_116C], al
0x180008f15  mov     [rsp+11D0h+var_116A], dx
0x180008f1a  mov     [rsp+11D0h+var_1168], cl
0x180008f1e  test    dx, dx
0x180008f21  jz      short loc_180008F40
0x180008f23  mov     eax, edx
0x180008f25  cmp     cl, 1
0x180008f28  jnz     short loc_180008F30
0x180008f2a  add     rax, 2
0x180008f2e  jmp     short loc_180008F39
0x180008f30  cmp     cl, 2
0x180008f33  jnz     short loc_180008F39
0x180008f35  add     rax, 4
0x180008f39  mov     [rsp+11D0h+var_1160], rax
0x180008f3e  jmp     short loc_180008F45
0x180008f40  mov     [rsp+11D0h+var_1160], r13
0x180008f45  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008f4c  xorps   xmm0, xmm0
0x180008f4f  mov     [rsp+11D0h+var_1158], r13
0x180008f54  movdqa  [rbp+10D0h+var_1150], xmm0
0x180008f59  mov     [rbp+10D0h+lpMem], r13
0x180008f5d  mov     [rbp+10D0h+var_1138], r13w
0x180008f62  mov     [rbp+10D0h+var_1136], r13b
0x180008f66  mov     [rsp+11D0h+var_1188], r13d
0x180008f6b  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180008f73  test    rax, rax
0x180008f76  jnz     short loc_180008FBB
0x180008f78  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008f7f  test    rax, rax
0x180008f82  jnz     short loc_180008F98
0x180008f84  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008f8b  call    cs:__imp_GetModuleHandleW
0x180008f91  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008f98  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008f9f  mov     rcx, rax; hModule
0x180008fa2  call    cs:__imp_GetProcAddress
0x180008fa8  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008faf  test    rax, rax
0x180008fb2  jnz     short loc_180008FBB
0x180008fb4  mov     ebx, 0C0000139h
0x180008fb9  jmp     short loc_180008FE5
0x180008fbb  lea     rcx, [rsp+11D0h+var_1190]
0x180008fc0  xor     r8d, r8d
0x180008fc3  mov     [rsp+11D0h+var_11A8], rcx
0x180008fc8  lea     r9, [rsp+11D0h+var_1188]
0x180008fcd  lea     rcx, [rbp+10D0h+var_1040]
0x180008fd4  xor     edx, edx
0x180008fd6  mov     [rsp+11D0h+var_11B0], rcx
0x180008fdb  mov     rcx, r14
0x180008fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fe3  mov     ebx, eax
0x180008fe5  mov     ecx, ebx; this
0x180008fe7  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180008fec  test    ebx, ebx
0x180008fee  jz      short loc_180008FFE
0x180008ff0  mov     eax, r13d
0x180008ff3  mov     [rsp+11D0h+var_1188], r13d
0x180008ff8  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180008ffc  jmp     short loc_180009002
0x180008ffe  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180009002  mov     r8d, eax; unsigned __int64
0x180009005  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000900c  mov     r9d, 1000h; unsigned __int64
0x180009012  lea     rcx, [rsp+11D0h+var_1170]; this
0x180009017  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000901c  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x180009020  jnz     loc_180009228
0x180009026  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000902d  mov     [rbp+10D0h+var_1130], r13
0x180009031  mov     [rbp+10D0h+var_10B8], rax
0x180009035  xorps   xmm0, xmm0
0x180009038  lea     rax, [rbp+10D0h+var_1130]
0x18000903c  mov     [rbp+10D0h+var_111C], r13d
0x180009040  mov     [rbp+10D0h+var_10B0], rax
0x180009044  lea     rax, [rbp+10D0h+var_1128]
0x180009048  mov     [rbp+10D0h+var_10A8], rax
0x18000904c  lea     rax, [rsp+11D0h+var_1170]
0x180009051  mov     [rbp+10D0h+var_10A0], rax
0x180009055  lea     rax, [rbp+10D0h+var_10B8]
0x180009059  mov     [rbp+10D0h+var_1050], rax
0x180009060  mov     rax, [rdi+18h]
0x180009064  add     rax, 0Ah
0x180009068  mov     [rbp+10D0h+var_1118], r13w
0x18000906d  mov     [rsp+11D0h+var_1190], rax
0x180009072  movzx   eax, word ptr [rdi+2]
0x180009076  mov     [rbp+10D0h+var_1120], ax
0x18000907a  mov     al, [rdi+4]
0x18000907d  mov     [rbp+10D0h+var_111E], al
0x180009080  movzx   eax, word ptr [rdi+6]
0x180009084  mov     [rbp+10D0h+var_1100], ax
0x180009088  mov     al, [rdi+8]
0x18000908b  mov     [rbp+10D0h+var_10FE], al
0x18000908e  movdqu  [rbp+10D0h+var_1110], xmm0
0x180009093  mov     [rbp+10D0h+var_10FC], r13d
0x180009097  mov     [rbp+10D0h+var_10F8], r13w
0x18000909c  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800090a1  jmp     loc_18000913A
0x1800090a6  mov     ebx, r13d
0x1800090a9  cmp     [rbp+10D0h+var_111C], r13d
0x1800090ad  jbe     loc_18000913A
0x1800090b3  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800090b7  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800090bc  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800090c0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800090c5  test    al, al
0x1800090c7  jz      short loc_18000913A
0x1800090c9  mov     eax, [rbp+10D0h+var_10FC]
0x1800090cc  mov     rcx, [rbp+10D0h+var_1050]; this
0x1800090d3  mov     [rsp+11D0h+var_1180], eax
0x1800090d7  movzx   eax, [rbp+10D0h+var_10F8]
0x1800090db  mov     [rbp+10D0h+var_10E0], rax
0x1800090df  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1800090e3  mov     [rbp+10D0h+var_10D8], rax
0x1800090e7  movzx   eax, [rbp+10D0h+var_1118]
0x1800090eb  mov     [rbp+10D0h+var_10D0], rax
0x1800090ef  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x1800090f3  mov     [rbp+10D0h+var_10C8], rax
0x1800090f7  test    rcx, rcx
0x1800090fa  jz      loc_180009273
0x180009100  mov     rax, [rcx]
0x180009103  lea     rdx, [rsp+11D0h+var_1180]
0x180009108  mov     [rsp+11D0h+var_11A8], rdx
0x18000910d  lea     r9, [rbp+10D0h+var_10D8]
0x180009111  lea     rdx, [rbp+10D0h+var_10E0]
0x180009115  mov     [rsp+11D0h+var_11B0], rdx
0x18000911a  lea     r8, [rbp+10D0h+var_10D0]
0x18000911e  mov     rax, [rax+20h]
0x180009122  lea     rdx, [rbp+10D0h+var_10C8]
0x180009126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000912b  test    al, al
0x18000912d  jz      short loc_1800091A7
0x18000912f  inc     ebx
0x180009131  cmp     ebx, [rbp+10D0h+var_111C]
0x180009134  jb      loc_1800090B3
0x18000913a  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000913e  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180009143  lea     rcx, [rbp+10D0h+var_1120]; this
0x180009147  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000914c  test    al, al
0x18000914e  jnz     loc_1800090A6
0x180009154  mov     rcx, [rbp+10D0h+var_1050]
0x18000915b  test    rcx, rcx
0x18000915e  jz      short loc_18000916C
0x180009160  mov     rax, [rcx]
0x180009163  mov     rax, [rax+18h]
0x180009167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000916c  mov     bl, 1
0x18000916e  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x180009172  jz      short loc_1800091E6
0x180009174  mov     rdx, [rsp+11D0h+var_1158]
0x180009179  mov     rcx, r14
0x18000917c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180009180  mov     eax, [rsp+11D0h+var_1188]
0x180009184  sub     r8d, edx
0x180009187  mov     [rsp+11D0h+var_11A0], 1
0x18000918f  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180009193  call    wil_details_NtUpdateWnfStateData
0x180009198  cmp     eax, 0C0000001h
0x18000919d  jnz     short loc_1800091C4
0x18000919f  inc     r15
0x1800091a2  mov     bl, r13b
0x1800091a5  jmp     short loc_1800091F2
0x1800091a7  mov     rcx, [rbp+10D0h+var_1050]
0x1800091ae  test    rcx, rcx
0x1800091b1  jz      short loc_1800091BF
0x1800091b3  mov     rax, [rcx]
0x1800091b6  mov     rax, [rax+18h]
0x1800091ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091bf  mov     bl, r13b
0x1800091c2  jmp     short loc_18000916E
0x1800091c4  test    eax, eax
0x1800091c6  jz      short loc_1800091E6
0x1800091c8  mov     rdx, [rsp+11D0h+var_1158]
0x1800091cd  mov     rcx, r14
0x1800091d0  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800091d4  sub     r8d, edx
0x1800091d7  mov     [rsp+11D0h+var_11A0], r13d
0x1800091dc  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x1800091e1  call    wil_details_NtUpdateWnfStateData
0x1800091e6  mov     rax, [rbp+10D0h+var_1130]
0x1800091ea  add     r14, 8
0x1800091ee  mov     [rbp+10D0h+var_1128], rax
0x1800091f2  mov     rsi, [rbp+10D0h+lpMem]
0x1800091f6  mov     [rbp+10D0h+lpMem], r13
0x1800091fa  test    rsi, rsi
0x1800091fd  jz      short loc_180009213
0x1800091ff  call    cs:__imp_GetProcessHeap
0x180009205  mov     r8, rsi; lpMem
0x180009208  xor     edx, edx; dwFlags
0x18000920a  mov     rcx, rax; hHeap
0x18000920d  call    cs:__imp_HeapFree
0x180009213  test    bl, bl
0x180009215  jnz     short loc_180009249
0x180009217  cmp     r14, r12
0x18000921a  jnb     short loc_180009249
0x18000921c  cmp     r15, 32h ; '2'
0x180009220  jb      loc_180008EF6
0x180009226  jmp     short loc_180009249
0x180009228  mov     rbx, [rbp+10D0h+lpMem]
0x18000922c  mov     [rbp+10D0h+lpMem], r13
0x180009230  test    rbx, rbx
0x180009233  jz      short loc_180009249
0x180009235  call    cs:__imp_GetProcessHeap
0x18000923b  mov     r8, rbx; lpMem
0x18000923e  xor     edx, edx; dwFlags
0x180009240  mov     rcx, rax; hHeap
0x180009243  call    cs:__imp_HeapFree
0x180009249  mov     rcx, [rbp+10D0h+var_40]
0x180009250  xor     rcx, rsp; StackCookie
0x180009253  call    __security_check_cookie
0x180009258  mov     rbx, [rsp+11D0h+arg_8]
0x180009260  add     rsp, 11A0h
0x180009267  pop     r15
0x180009269  pop     r14
0x18000926b  pop     r13
0x18000926d  pop     r12
0x18000926f  pop     rdi
0x180009270  pop     rsi
0x180009271  pop     rbp
0x180009272  retn
0x180009273  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
