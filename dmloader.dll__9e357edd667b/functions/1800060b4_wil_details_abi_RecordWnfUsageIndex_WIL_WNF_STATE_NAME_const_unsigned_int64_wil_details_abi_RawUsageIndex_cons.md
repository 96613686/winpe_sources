# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800060b4`
- end: `0x180006484`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `976`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800057a0`

## callees

- `0x1800015d0`
- `0x1800052d8`
- `0x1800056a0`
- `0x1800060b4`
- `0x180006af8`
- `0x18000782c`
- `0x180007e78`
- `0x18000f930`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006194`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006194`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800061ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800061ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006418`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000644e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006418`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000644e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000640a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006440`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000640a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006440`

## string_xrefs

- `0x18000618d`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v4; // r13
  unsigned __int64 v5; // r12
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
  unsigned int v17; // esi
  int v18; // ebx
  __int64 v19; // r15
  __int64 v20; // r9
  char v21; // bl
  int updated; // eax
  __int64 v23; // r9
  void *v24; // rsi
  HANDLE ProcessHeap; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  __int64 *v28; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v32; // [rsp+64h] [rbp-9Ch]
  __int16 v33; // [rsp+66h] [rbp-9Ah]
  char v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+78h] [rbp-88h]
  __int128 v37; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v39; // [rsp+98h] [rbp-68h]
  char v40; // [rsp+9Ah] [rbp-66h]
  __int64 v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v43; // [rsp+B0h] [rbp-50h] BYREF
  char v44; // [rsp+B2h] [rbp-4Eh]
  unsigned int v45; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v46; // [rsp+B8h] [rbp-48h]
  __int128 v47; // [rsp+C0h] [rbp-40h]
  __int16 v48; // [rsp+D0h] [rbp-30h] BYREF
  char v49; // [rsp+D2h] [rbp-2Eh]
  int v50; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v51; // [rsp+D8h] [rbp-28h]
  __int128 v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v54; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v55; // [rsp+100h] [rbp+0h] BYREF
  __int64 v56; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v57[13]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *v58; // [rsp+180h] [rbp+80h]
  _BYTE v59[4096]; // [rsp+190h] [rbp+90h] BYREF

  v4 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v5 = 0;
  v42 = 0;
  v7 = this;
  while ( 1 )
  {
    v8 = *(unsigned __int16 *)(a3 + 6);
    v9 = *(_BYTE *)(a3 + 8);
    v31[0] = *(_WORD *)a3;
    v31[1] = *(_WORD *)(a3 + 2);
    v32 = *(_BYTE *)(a3 + 4);
    v33 = v8;
    v34 = v9;
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
      v35 = v10;
    }
    else
    {
      v35 = 0;
    }
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    v36 = 0;
    v37 = 0;
    lpMem = 0;
    v39 = 0;
    v40 = 0;
    v30[0] = 0;
    LODWORD(v29) = 4096;
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
      v28 = (__int64 *)v59;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v7, 0, 0, v30);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      v30[0] = 0;
      LODWORD(v29) = 0;
    }
    else
    {
      v15 = (unsigned int)v29;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v31, v59, v15, 0x1000u);
    if ( HIBYTE(v39) )
      break;
    v41 = 0;
    v57[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v45 = 0;
    v57[1] = &v41;
    v57[2] = &v42;
    v57[3] = v31;
    v58 = (wil::details::in1diag3 *)v57;
    v16 = *(_QWORD *)(a3 + 24);
    v46 = 0;
    v29 = (unsigned __int8 *)(v16 + 10);
    v43 = *(_WORD *)(a3 + 2);
    v44 = *(_BYTE *)(a3 + 4);
    v48 = *(_WORD *)(a3 + 6);
    v49 = *(_BYTE *)(a3 + 8);
    v47 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
LABEL_26:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v43,
              &v29,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v17 = v45;
      v18 = 0;
      if ( v45 )
      {
        v19 = *((_QWORD *)&v47 + 1);
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v48,
                  &v29,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v30[2] = v50;
          v53 = v51;
          v54 = *((_QWORD *)&v52 + 1);
          v55 = v46;
          v56 = v19;
          if ( !v58 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v28 = &v53;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v58 + 32LL))(
                  v58,
                  &v56,
                  &v55,
                  &v54) )
          {
            if ( v58 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
            v21 = 0;
            goto LABEL_30;
          }
          if ( ++v18 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v58 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
    v21 = 1;
LABEL_30:
    if ( !(_BYTE)v39 )
      goto LABEL_38;
    updated = wil_details_NtUpdateWnfStateData((__int64)v7, v36, (int)v37 - (int)v36, v20, (int)v28, v30[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v7, v36, v37 - v36, v23, (int)v28, 0, 0);
LABEL_38:
      v7 = (wil::details_abi *)((char *)v7 + 8);
      v42 = v41;
      goto LABEL_39;
    }
    ++v5;
    v21 = 0;
LABEL_39:
    v24 = lpMem;
    lpMem = 0;
    if ( v24 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v24);
    }
    if ( v21 || v7 >= v4 || v5 >= 0x32 )
      return;
  }
  v26 = lpMem;
  lpMem = 0;
  if ( v26 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26);
  }
}

```

## disassembly

```asm
0x1800060b4  mov     [rsp-8+arg_8], rbx
0x1800060b9  push    rbp
0x1800060ba  push    rsi
0x1800060bb  push    rdi
0x1800060bc  push    r12
0x1800060be  push    r13
0x1800060c0  push    r14
0x1800060c2  push    r15
0x1800060c4  lea     rbp, [rsp-10A0h]
0x1800060cc  mov     eax, 11A0h
0x1800060d1  call    _alloca_probe
0x1800060d6  sub     rsp, rax
0x1800060d9  mov     rax, cs:__security_cookie
0x1800060e0  xor     rax, rsp
0x1800060e3  mov     [rbp+10D0h+var_40], rax
0x1800060ea  xor     r15d, r15d
0x1800060ed  lea     r13, [rcx+rdx*8]
0x1800060f1  mov     r12d, r15d
0x1800060f4  mov     [rbp+10D0h+var_1128], r15
0x1800060f8  mov     rdi, r8
0x1800060fb  mov     r14, rcx
0x1800060fe  movzx   eax, word ptr [rdi]
0x180006101  movzx   edx, word ptr [rdi+6]
0x180006105  mov     cl, [rdi+8]
0x180006108  mov     [rsp+11D0h+var_1170], ax
0x18000610d  movzx   eax, word ptr [rdi+2]
0x180006111  mov     [rsp+11D0h+var_116E], ax
0x180006116  mov     al, [rdi+4]
0x180006119  mov     [rsp+11D0h+var_116C], al
0x18000611d  mov     [rsp+11D0h+var_116A], dx
0x180006122  mov     [rsp+11D0h+var_1168], cl
0x180006126  test    dx, dx
0x180006129  jz      short loc_180006148
0x18000612b  mov     eax, edx
0x18000612d  cmp     cl, 1
0x180006130  jnz     short loc_180006138
0x180006132  add     rax, 2
0x180006136  jmp     short loc_180006141
0x180006138  cmp     cl, 2
0x18000613b  jnz     short loc_180006141
0x18000613d  add     rax, 4
0x180006141  mov     [rsp+11D0h+var_1160], rax
0x180006146  jmp     short loc_18000614D
0x180006148  mov     [rsp+11D0h+var_1160], r15
0x18000614d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180006154  xorps   xmm0, xmm0
0x180006157  mov     [rsp+11D0h+var_1158], r15
0x18000615c  movdqa  [rbp+10D0h+var_1150], xmm0
0x180006161  mov     [rbp+10D0h+lpMem], r15
0x180006165  mov     [rbp+10D0h+var_1138], 0
0x18000616b  mov     [rbp+10D0h+var_1136], r15b
0x18000616f  mov     [rsp+11D0h+var_1188], r15d
0x180006174  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000617c  test    rax, rax
0x18000617f  jnz     short loc_1800061C4
0x180006181  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006188  test    rax, rax
0x18000618b  jnz     short loc_1800061A1
0x18000618d  lea     rcx, ModuleName; "ntdll.dll"
0x180006194  call    cs:__imp_GetModuleHandleW
0x18000619a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800061a1  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800061a8  mov     rcx, rax; hModule
0x1800061ab  call    cs:__imp_GetProcAddress
0x1800061b1  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800061b8  test    rax, rax
0x1800061bb  jnz     short loc_1800061C4
0x1800061bd  mov     ebx, 0C0000139h
0x1800061c2  jmp     short loc_1800061EE
0x1800061c4  lea     rcx, [rsp+11D0h+var_1190]
0x1800061c9  xor     r8d, r8d
0x1800061cc  mov     [rsp+11D0h+var_11A8], rcx
0x1800061d1  lea     r9, [rsp+11D0h+var_1188]
0x1800061d6  lea     rcx, [rbp+10D0h+var_1040]
0x1800061dd  xor     edx, edx
0x1800061df  mov     [rsp+11D0h+var_11B0], rcx
0x1800061e4  mov     rcx, r14
0x1800061e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ec  mov     ebx, eax
0x1800061ee  mov     ecx, ebx; this
0x1800061f0  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800061f5  test    ebx, ebx
0x1800061f7  jz      short loc_180006207
0x1800061f9  mov     eax, r15d
0x1800061fc  mov     [rsp+11D0h+var_1188], r15d
0x180006201  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180006205  jmp     short loc_18000620B
0x180006207  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000620b  mov     r8d, eax; unsigned __int64
0x18000620e  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180006215  mov     r9d, 1000h; unsigned __int64
0x18000621b  lea     rcx, [rsp+11D0h+var_1170]; this
0x180006220  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180006225  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180006229  jnz     loc_180006433
0x18000622f  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180006236  mov     [rbp+10D0h+var_1130], r15
0x18000623a  mov     [rbp+10D0h+var_10B8], rax
0x18000623e  xorps   xmm0, xmm0
0x180006241  lea     rax, [rbp+10D0h+var_1130]
0x180006245  mov     [rbp+10D0h+var_111C], r15d
0x180006249  mov     [rbp+10D0h+var_10B0], rax
0x18000624d  lea     rax, [rbp+10D0h+var_1128]
0x180006251  mov     [rbp+10D0h+var_10A8], rax
0x180006255  lea     rax, [rsp+11D0h+var_1170]
0x18000625a  mov     [rbp+10D0h+var_10A0], rax
0x18000625e  lea     rax, [rbp+10D0h+var_10B8]
0x180006262  mov     [rbp+10D0h+var_1050], rax
0x180006269  mov     rax, [rdi+18h]
0x18000626d  add     rax, 0Ah
0x180006271  mov     [rbp+10D0h+var_1118], r15w
0x180006276  mov     [rsp+11D0h+var_1190], rax
0x18000627b  movzx   eax, word ptr [rdi+2]
0x18000627f  mov     [rbp+10D0h+var_1120], ax
0x180006283  mov     al, [rdi+4]
0x180006286  mov     [rbp+10D0h+var_111E], al
0x180006289  movzx   eax, word ptr [rdi+6]
0x18000628d  mov     [rbp+10D0h+var_1100], ax
0x180006291  mov     al, [rdi+8]
0x180006294  mov     [rbp+10D0h+var_10FE], al
0x180006297  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000629c  mov     [rbp+10D0h+var_10FC], r15d
0x1800062a0  mov     [rbp+10D0h+var_10F8], r15w
0x1800062a5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800062aa  jmp     loc_180006342
0x1800062af  mov     esi, [rbp+10D0h+var_111C]
0x1800062b2  mov     ebx, r15d
0x1800062b5  test    esi, esi
0x1800062b7  jz      loc_180006342
0x1800062bd  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x1800062c1  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800062c5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800062ca  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800062ce  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800062d3  test    al, al
0x1800062d5  jz      short loc_18000633F
0x1800062d7  mov     eax, [rbp+10D0h+var_10FC]
0x1800062da  mov     rcx, [rbp+10D0h+var_1050]; this
0x1800062e1  mov     [rsp+11D0h+var_1180], eax
0x1800062e5  movzx   eax, [rbp+10D0h+var_10F8]
0x1800062e9  mov     [rbp+10D0h+var_10E0], rax
0x1800062ed  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1800062f1  mov     [rbp+10D0h+var_10D8], rax
0x1800062f5  movzx   eax, [rbp+10D0h+var_1118]
0x1800062f9  mov     [rbp+10D0h+var_10D0], rax
0x1800062fd  mov     [rbp+10D0h+var_10C8], r15
0x180006301  test    rcx, rcx
0x180006304  jz      loc_18000647E
0x18000630a  mov     rax, [rcx]
0x18000630d  lea     rdx, [rsp+11D0h+var_1180]
0x180006312  mov     [rsp+11D0h+var_11A8], rdx
0x180006317  lea     r9, [rbp+10D0h+var_10D8]
0x18000631b  lea     rdx, [rbp+10D0h+var_10E0]
0x18000631f  mov     [rsp+11D0h+var_11B0], rdx
0x180006324  lea     r8, [rbp+10D0h+var_10D0]
0x180006328  mov     rax, [rax+20h]
0x18000632c  lea     rdx, [rbp+10D0h+var_10C8]
0x180006330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006335  test    al, al
0x180006337  jz      short loc_1800063AF
0x180006339  inc     ebx
0x18000633b  cmp     ebx, esi
0x18000633d  jb      short loc_1800062C1
0x18000633f  xor     r15d, r15d
0x180006342  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006346  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000634b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000634f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006354  test    al, al
0x180006356  jnz     loc_1800062AF
0x18000635c  mov     rcx, [rbp+10D0h+var_1050]
0x180006363  test    rcx, rcx
0x180006366  jz      short loc_180006374
0x180006368  mov     rax, [rcx]
0x18000636b  mov     rax, [rax+18h]
0x18000636f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006374  mov     bl, 1
0x180006376  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000637a  jz      short loc_1800063F1
0x18000637c  mov     rdx, [rsp+11D0h+var_1158]
0x180006381  mov     rcx, r14
0x180006384  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006388  mov     eax, [rsp+11D0h+var_1188]
0x18000638c  sub     r8d, edx
0x18000638f  mov     [rsp+11D0h+var_11A0], 1
0x180006397  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000639b  call    wil_details_NtUpdateWnfStateData
0x1800063a0  cmp     eax, 0C0000001h
0x1800063a5  jnz     short loc_1800063CF
0x1800063a7  inc     r12
0x1800063aa  mov     bl, r15b
0x1800063ad  jmp     short loc_1800063FD
0x1800063af  mov     rcx, [rbp+10D0h+var_1050]
0x1800063b6  xor     r15d, r15d
0x1800063b9  test    rcx, rcx
0x1800063bc  jz      short loc_1800063CA
0x1800063be  mov     rax, [rcx]
0x1800063c1  mov     rax, [rax+18h]
0x1800063c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ca  mov     bl, r15b
0x1800063cd  jmp     short loc_180006376
0x1800063cf  test    eax, eax
0x1800063d1  jz      short loc_1800063F1
0x1800063d3  mov     rdx, [rsp+11D0h+var_1158]
0x1800063d8  mov     rcx, r14
0x1800063db  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800063df  sub     r8d, edx
0x1800063e2  mov     [rsp+11D0h+var_11A0], r15d
0x1800063e7  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x1800063ec  call    wil_details_NtUpdateWnfStateData
0x1800063f1  mov     rax, [rbp+10D0h+var_1130]
0x1800063f5  add     r14, 8
0x1800063f9  mov     [rbp+10D0h+var_1128], rax
0x1800063fd  mov     rsi, [rbp+10D0h+lpMem]
0x180006401  mov     [rbp+10D0h+lpMem], r15
0x180006405  test    rsi, rsi
0x180006408  jz      short loc_18000641E
0x18000640a  call    cs:__imp_GetProcessHeap
0x180006410  mov     r8, rsi; lpMem
0x180006413  xor     edx, edx; dwFlags
0x180006415  mov     rcx, rax; hHeap
0x180006418  call    cs:__imp_HeapFree
0x18000641e  test    bl, bl
0x180006420  jnz     short loc_180006454
0x180006422  cmp     r14, r13
0x180006425  jnb     short loc_180006454
0x180006427  cmp     r12, 32h ; '2'
0x18000642b  jb      loc_1800060FE
0x180006431  jmp     short loc_180006454
0x180006433  mov     rbx, [rbp+10D0h+lpMem]
0x180006437  mov     [rbp+10D0h+lpMem], r15
0x18000643b  test    rbx, rbx
0x18000643e  jz      short loc_180006454
0x180006440  call    cs:__imp_GetProcessHeap
0x180006446  mov     r8, rbx; lpMem
0x180006449  xor     edx, edx; dwFlags
0x18000644b  mov     rcx, rax; hHeap
0x18000644e  call    cs:__imp_HeapFree
0x180006454  mov     rcx, [rbp+10D0h+var_40]
0x18000645b  xor     rcx, rsp; StackCookie
0x18000645e  call    __security_check_cookie
0x180006463  mov     rbx, [rsp+11D0h+arg_8]
0x18000646b  add     rsp, 11A0h
0x180006472  pop     r15
0x180006474  pop     r14
0x180006476  pop     r13
0x180006478  pop     r12
0x18000647a  pop     rdi
0x18000647b  pop     rsi
0x18000647c  pop     rbp
0x18000647d  retn
0x18000647e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
