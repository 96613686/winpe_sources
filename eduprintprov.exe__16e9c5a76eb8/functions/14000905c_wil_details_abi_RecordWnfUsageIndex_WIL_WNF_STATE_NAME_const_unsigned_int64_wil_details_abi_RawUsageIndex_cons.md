# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x14000905c`
- end: `0x140009434`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140008740`

## callees

- `0x140002600`
- `0x140008228`
- `0x140008640`
- `0x14000905c`
- `0x140009a74`
- `0x14000af58`
- `0x14000c1f0`
- `0x1400130e0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000913c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000913c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009153`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009153`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400093ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400093f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400093ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400093f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400093c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400093fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400093c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400093fe`

## string_xrefs

- `0x140009135`: `ntdll.dll`

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
0x14000905c  mov     [rsp-8+arg_8], rbx
0x140009061  push    rbp
0x140009062  push    rsi
0x140009063  push    rdi
0x140009064  push    r12
0x140009066  push    r13
0x140009068  push    r14
0x14000906a  push    r15
0x14000906c  lea     rbp, [rsp-10A0h]
0x140009074  mov     eax, 11A0h
0x140009079  call    _alloca_probe
0x14000907e  sub     rsp, rax
0x140009081  mov     rax, cs:__security_cookie
0x140009088  xor     rax, rsp
0x14000908b  mov     [rbp+10D0h+var_40], rax
0x140009092  mov     rdi, r8
0x140009095  mov     r14, rcx
0x140009098  lea     r13, [rcx+rdx*8]
0x14000909c  xor     r15d, r15d
0x14000909f  mov     r12d, r15d
0x1400090a2  mov     [rbp+10D0h+var_1128], r15
0x1400090a6  mov     cl, [rdi+8]
0x1400090a9  movzx   edx, word ptr [rdi+6]
0x1400090ad  movzx   eax, word ptr [rdi]
0x1400090b0  mov     [rsp+11D0h+var_1170], ax
0x1400090b5  movzx   eax, word ptr [rdi+2]
0x1400090b9  mov     [rsp+11D0h+var_116E], ax
0x1400090be  mov     al, [rdi+4]
0x1400090c1  mov     [rsp+11D0h+var_116C], al
0x1400090c5  mov     [rsp+11D0h+var_116A], dx
0x1400090ca  mov     [rsp+11D0h+var_1168], cl
0x1400090ce  test    dx, dx
0x1400090d1  jz      short loc_1400090F0
0x1400090d3  mov     eax, edx
0x1400090d5  cmp     cl, 1
0x1400090d8  jnz     short loc_1400090E0
0x1400090da  add     rax, 2
0x1400090de  jmp     short loc_1400090E9
0x1400090e0  cmp     cl, 2
0x1400090e3  jnz     short loc_1400090E9
0x1400090e5  add     rax, 4
0x1400090e9  mov     [rsp+11D0h+var_1160], rax
0x1400090ee  jmp     short loc_1400090F5
0x1400090f0  mov     [rsp+11D0h+var_1160], r15
0x1400090f5  mov     [rsp+11D0h+var_1158], r15
0x1400090fa  xorps   xmm0, xmm0
0x1400090fd  movdqa  [rbp+10D0h+var_1150], xmm0
0x140009102  mov     [rbp+10D0h+lpMem], r15
0x140009106  mov     [rbp+10D0h+var_1138], 0
0x14000910c  mov     [rbp+10D0h+var_1136], r15b
0x140009110  mov     [rsp+11D0h+var_1188], r15d
0x140009115  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x14000911d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140009124  test    rax, rax
0x140009127  jnz     short loc_14000916C
0x140009129  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009130  test    rax, rax
0x140009133  jnz     short loc_140009149
0x140009135  lea     rcx, ModuleName; "ntdll.dll"
0x14000913c  call    cs:__imp_GetModuleHandleW
0x140009142  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009149  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140009150  mov     rcx, rax; hModule
0x140009153  call    cs:__imp_GetProcAddress
0x140009159  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140009160  test    rax, rax
0x140009163  jnz     short loc_14000916C
0x140009165  mov     ebx, 0C0000139h
0x14000916a  jmp     short loc_140009196
0x14000916c  lea     rcx, [rsp+11D0h+var_1190]
0x140009171  mov     [rsp+11D0h+var_11A8], rcx
0x140009176  lea     rcx, [rbp+10D0h+var_1040]
0x14000917d  mov     [rsp+11D0h+var_11B0], rcx
0x140009182  lea     r9, [rsp+11D0h+var_1188]
0x140009187  xor     r8d, r8d
0x14000918a  xor     edx, edx
0x14000918c  mov     rcx, r14
0x14000918f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009194  mov     ebx, eax
0x140009196  mov     ecx, ebx; this
0x140009198  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000919d  test    ebx, ebx
0x14000919f  jz      short loc_1400091AF
0x1400091a1  mov     eax, r15d
0x1400091a4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x1400091a8  mov     [rsp+11D0h+var_1188], r15d
0x1400091ad  jmp     short loc_1400091B3
0x1400091af  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x1400091b3  mov     r8d, eax; unsigned __int64
0x1400091b6  mov     r9d, 1000h; unsigned __int64
0x1400091bc  lea     rdx, [rbp+10D0h+var_1040]; void *
0x1400091c3  lea     rcx, [rsp+11D0h+var_1170]; this
0x1400091c8  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1400091cd  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x1400091d1  jnz     loc_1400093E3
0x1400091d7  mov     [rbp+10D0h+var_1130], r15
0x1400091db  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1400091e2  mov     [rbp+10D0h+var_10B0], rax
0x1400091e6  lea     rax, [rbp+10D0h+var_1130]
0x1400091ea  mov     [rbp+10D0h+var_10A8], rax
0x1400091ee  lea     rax, [rbp+10D0h+var_1128]
0x1400091f2  mov     [rbp+10D0h+var_10A0], rax
0x1400091f6  lea     rax, [rsp+11D0h+var_1170]
0x1400091fb  mov     [rbp+10D0h+var_1098], rax
0x1400091ff  lea     rax, [rbp+10D0h+var_10B0]
0x140009203  mov     [rbp+10D0h+var_1048], rax
0x14000920a  lea     rax, [rbp+10D0h+var_10B8]
0x14000920e  mov     [rbp+10D0h+var_10C0], rax
0x140009212  mov     rax, [rdi+18h]
0x140009216  add     rax, 0Ah
0x14000921a  mov     [rsp+11D0h+var_1190], rax
0x14000921f  movzx   eax, word ptr [rdi+2]
0x140009223  mov     [rbp+10D0h+var_1120], ax
0x140009227  mov     al, [rdi+4]
0x14000922a  mov     [rbp+10D0h+var_111E], al
0x14000922d  mov     [rbp+10D0h+var_111C], r15d
0x140009231  mov     [rbp+10D0h+var_1118], r15w
0x140009236  xorps   xmm0, xmm0
0x140009239  movdqu  [rbp+10D0h+var_1110], xmm0
0x14000923e  movzx   eax, word ptr [rdi+6]
0x140009242  mov     [rbp+10D0h+var_1100], ax
0x140009246  mov     al, [rdi+8]
0x140009249  mov     [rbp+10D0h+var_10FE], al
0x14000924c  mov     [rbp+10D0h+var_10FC], r15d
0x140009250  mov     [rbp+10D0h+var_10F8], r15w
0x140009255  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14000925a  jmp     loc_1400092F2
0x14000925f  mov     ebx, r15d
0x140009262  mov     esi, [rbp+10D0h+var_111C]
0x140009265  test    esi, esi
0x140009267  jz      loc_1400092F2
0x14000926d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x140009271  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009275  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000927a  lea     rcx, [rbp+10D0h+var_1100]; this
0x14000927e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009283  test    al, al
0x140009285  jz      short loc_1400092EF
0x140009287  mov     eax, [rbp+10D0h+var_10FC]
0x14000928a  mov     [rsp+11D0h+var_1180], eax
0x14000928e  movzx   eax, [rbp+10D0h+var_10F8]
0x140009292  mov     [rbp+10D0h+var_10E0], rax
0x140009296  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14000929a  mov     [rbp+10D0h+var_10D8], rax
0x14000929e  movzx   eax, [rbp+10D0h+var_1118]
0x1400092a2  mov     [rbp+10D0h+var_10D0], rax
0x1400092a6  mov     [rbp+10D0h+var_10C8], r15
0x1400092aa  mov     rcx, [rbp+10D0h+var_1048]; this
0x1400092b1  test    rcx, rcx
0x1400092b4  jz      loc_14000942E
0x1400092ba  mov     rax, [rcx]
0x1400092bd  lea     rdx, [rsp+11D0h+var_1180]
0x1400092c2  mov     [rsp+11D0h+var_11A8], rdx
0x1400092c7  lea     rdx, [rbp+10D0h+var_10E0]
0x1400092cb  mov     [rsp+11D0h+var_11B0], rdx
0x1400092d0  lea     r9, [rbp+10D0h+var_10D8]
0x1400092d4  lea     r8, [rbp+10D0h+var_10D0]
0x1400092d8  lea     rdx, [rbp+10D0h+var_10C8]
0x1400092dc  mov     rax, [rax+20h]
0x1400092e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092e5  test    al, al
0x1400092e7  jz      short loc_14000935F
0x1400092e9  inc     ebx
0x1400092eb  cmp     ebx, esi
0x1400092ed  jb      short loc_140009271
0x1400092ef  xor     r15d, r15d
0x1400092f2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400092f6  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1400092fb  lea     rcx, [rbp+10D0h+var_1120]; this
0x1400092ff  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009304  test    al, al
0x140009306  jnz     loc_14000925F
0x14000930c  mov     rcx, [rbp+10D0h+var_1048]
0x140009313  test    rcx, rcx
0x140009316  jz      short loc_140009324
0x140009318  mov     rax, [rcx]
0x14000931b  mov     rax, [rax+18h]
0x14000931f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009324  mov     bl, 1
0x140009326  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x14000932a  jz      short loc_1400093A1
0x14000932c  mov     eax, [rsp+11D0h+var_1188]
0x140009330  mov     rdx, [rsp+11D0h+var_1158]
0x140009335  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x140009339  sub     r8d, edx
0x14000933c  mov     [rsp+11D0h+var_11A0], 1
0x140009344  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x140009348  mov     rcx, r14
0x14000934b  call    wil_details_NtUpdateWnfStateData
0x140009350  cmp     eax, 0C0000001h
0x140009355  jnz     short loc_14000937F
0x140009357  inc     r12
0x14000935a  mov     bl, r15b
0x14000935d  jmp     short loc_1400093AD
0x14000935f  mov     rcx, [rbp+10D0h+var_1048]
0x140009366  xor     r15d, r15d
0x140009369  test    rcx, rcx
0x14000936c  jz      short loc_14000937A
0x14000936e  mov     rax, [rcx]
0x140009371  mov     rax, [rax+18h]
0x140009375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000937a  mov     bl, r15b
0x14000937d  jmp     short loc_140009326
0x14000937f  test    eax, eax
0x140009381  jz      short loc_1400093A1
0x140009383  mov     rdx, [rsp+11D0h+var_1158]
0x140009388  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000938c  sub     r8d, edx
0x14000938f  mov     [rsp+11D0h+var_11A0], r15d
0x140009394  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x140009399  mov     rcx, r14
0x14000939c  call    wil_details_NtUpdateWnfStateData
0x1400093a1  add     r14, 8
0x1400093a5  mov     rax, [rbp+10D0h+var_1130]
0x1400093a9  mov     [rbp+10D0h+var_1128], rax
0x1400093ad  mov     rsi, [rbp+10D0h+lpMem]
0x1400093b1  mov     [rbp+10D0h+lpMem], r15
0x1400093b5  test    rsi, rsi
0x1400093b8  jz      short loc_1400093CE
0x1400093ba  call    cs:__imp_GetProcessHeap
0x1400093c0  mov     rcx, rax; hHeap
0x1400093c3  mov     r8, rsi; lpMem
0x1400093c6  xor     edx, edx; dwFlags
0x1400093c8  call    cs:__imp_HeapFree
0x1400093ce  test    bl, bl
0x1400093d0  jnz     short loc_140009404
0x1400093d2  cmp     r14, r13
0x1400093d5  jnb     short loc_140009404
0x1400093d7  cmp     r12, 32h ; '2'
0x1400093db  jb      loc_1400090A6
0x1400093e1  jmp     short loc_140009404
0x1400093e3  mov     rbx, [rbp+10D0h+lpMem]
0x1400093e7  mov     [rbp+10D0h+lpMem], r15
0x1400093eb  test    rbx, rbx
0x1400093ee  jz      short loc_140009404
0x1400093f0  call    cs:__imp_GetProcessHeap
0x1400093f6  mov     rcx, rax; hHeap
0x1400093f9  mov     r8, rbx; lpMem
0x1400093fc  xor     edx, edx; dwFlags
0x1400093fe  call    cs:__imp_HeapFree
0x140009404  mov     rcx, [rbp+10D0h+var_40]
0x14000940b  xor     rcx, rsp; StackCookie
0x14000940e  call    __security_check_cookie
0x140009413  mov     rbx, [rsp+11D0h+arg_8]
0x14000941b  add     rsp, 11A0h
0x140009422  pop     r15
0x140009424  pop     r14
0x140009426  pop     r13
0x140009428  pop     r12
0x14000942a  pop     rdi
0x14000942b  pop     rsi
0x14000942c  pop     rbp
0x14000942d  retn
0x14000942e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
