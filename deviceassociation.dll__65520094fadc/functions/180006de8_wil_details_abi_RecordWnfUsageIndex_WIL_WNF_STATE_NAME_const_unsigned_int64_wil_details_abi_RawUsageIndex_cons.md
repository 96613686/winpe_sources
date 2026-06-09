# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180006de8`
- end: `0x1800071b5`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000651c`

## callees

- `0x1800060d8`
- `0x18000642c`
- `0x180006de8`
- `0x1800077ac`
- `0x18000843c`
- `0x1800097dc`
- `0x18000bbf0`
- `0x18000bc80`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000713b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007171`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000713b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007171`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007149`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000717f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007149`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000717f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006ede`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006ede`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006ec7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006ec7`

## string_xrefs

- `0x180006ec0`: `ntdll.dll`

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
0x180006de8  mov     [rsp-8+arg_8], rbx
0x180006ded  push    rbp
0x180006dee  push    rsi
0x180006def  push    rdi
0x180006df0  push    r12
0x180006df2  push    r13
0x180006df4  push    r14
0x180006df6  push    r15
0x180006df8  lea     rbp, [rsp-10A0h]
0x180006e00  mov     eax, 11A0h
0x180006e05  call    _alloca_probe
0x180006e0a  sub     rsp, rax
0x180006e0d  mov     rax, cs:__security_cookie
0x180006e14  xor     rax, rsp
0x180006e17  mov     [rbp+10D0h+var_40], rax
0x180006e1e  xor     r13d, r13d
0x180006e21  lea     r12, [rcx+rdx*8]
0x180006e25  mov     r15d, r13d
0x180006e28  mov     [rbp+10D0h+var_1128], r13
0x180006e2c  mov     rdi, r8
0x180006e2f  mov     r14, rcx
0x180006e32  movzx   eax, word ptr [rdi]
0x180006e35  movzx   edx, word ptr [rdi+6]
0x180006e39  mov     cl, [rdi+8]
0x180006e3c  mov     [rsp+11D0h+var_1170], ax
0x180006e41  movzx   eax, word ptr [rdi+2]
0x180006e45  mov     [rsp+11D0h+var_116E], ax
0x180006e4a  mov     al, [rdi+4]
0x180006e4d  mov     [rsp+11D0h+var_116C], al
0x180006e51  mov     [rsp+11D0h+var_116A], dx
0x180006e56  mov     [rsp+11D0h+var_1168], cl
0x180006e5a  test    dx, dx
0x180006e5d  jz      short loc_180006E7C
0x180006e5f  mov     eax, edx
0x180006e61  cmp     cl, 1
0x180006e64  jnz     short loc_180006E6C
0x180006e66  add     rax, 2
0x180006e6a  jmp     short loc_180006E75
0x180006e6c  cmp     cl, 2
0x180006e6f  jnz     short loc_180006E75
0x180006e71  add     rax, 4
0x180006e75  mov     [rsp+11D0h+var_1160], rax
0x180006e7a  jmp     short loc_180006E81
0x180006e7c  mov     [rsp+11D0h+var_1160], r13
0x180006e81  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180006e88  xorps   xmm0, xmm0
0x180006e8b  mov     [rsp+11D0h+var_1158], r13
0x180006e90  movdqa  [rbp+10D0h+var_1150], xmm0
0x180006e95  mov     [rbp+10D0h+lpMem], r13
0x180006e99  mov     [rbp+10D0h+var_1138], r13w
0x180006e9e  mov     [rbp+10D0h+var_1136], r13b
0x180006ea2  mov     [rsp+11D0h+var_1188], r13d
0x180006ea7  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180006eaf  test    rax, rax
0x180006eb2  jnz     short loc_180006EF7
0x180006eb4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006ebb  test    rax, rax
0x180006ebe  jnz     short loc_180006ED4
0x180006ec0  lea     rcx, ModuleName; "ntdll.dll"
0x180006ec7  call    cs:__imp_GetModuleHandleW
0x180006ecd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006ed4  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180006edb  mov     rcx, rax; hModule
0x180006ede  call    cs:__imp_GetProcAddress
0x180006ee4  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180006eeb  test    rax, rax
0x180006eee  jnz     short loc_180006EF7
0x180006ef0  mov     ebx, 0C0000139h
0x180006ef5  jmp     short loc_180006F21
0x180006ef7  lea     rcx, [rsp+11D0h+var_1190]
0x180006efc  xor     r8d, r8d
0x180006eff  mov     [rsp+11D0h+var_11A8], rcx
0x180006f04  lea     r9, [rsp+11D0h+var_1188]
0x180006f09  lea     rcx, [rbp+10D0h+var_1040]
0x180006f10  xor     edx, edx
0x180006f12  mov     [rsp+11D0h+var_11B0], rcx
0x180006f17  mov     rcx, r14
0x180006f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f1f  mov     ebx, eax
0x180006f21  mov     ecx, ebx; this
0x180006f23  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180006f28  test    ebx, ebx
0x180006f2a  jz      short loc_180006F3A
0x180006f2c  mov     eax, r13d
0x180006f2f  mov     [rsp+11D0h+var_1188], r13d
0x180006f34  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180006f38  jmp     short loc_180006F3E
0x180006f3a  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180006f3e  mov     r8d, eax; unsigned __int64
0x180006f41  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180006f48  mov     r9d, 1000h; unsigned __int64
0x180006f4e  lea     rcx, [rsp+11D0h+var_1170]; this
0x180006f53  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180006f58  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x180006f5c  jnz     loc_180007164
0x180006f62  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180006f69  mov     [rbp+10D0h+var_1130], r13
0x180006f6d  mov     [rbp+10D0h+var_10B8], rax
0x180006f71  xorps   xmm0, xmm0
0x180006f74  lea     rax, [rbp+10D0h+var_1130]
0x180006f78  mov     [rbp+10D0h+var_111C], r13d
0x180006f7c  mov     [rbp+10D0h+var_10B0], rax
0x180006f80  lea     rax, [rbp+10D0h+var_1128]
0x180006f84  mov     [rbp+10D0h+var_10A8], rax
0x180006f88  lea     rax, [rsp+11D0h+var_1170]
0x180006f8d  mov     [rbp+10D0h+var_10A0], rax
0x180006f91  lea     rax, [rbp+10D0h+var_10B8]
0x180006f95  mov     [rbp+10D0h+var_1050], rax
0x180006f9c  mov     rax, [rdi+18h]
0x180006fa0  add     rax, 0Ah
0x180006fa4  mov     [rbp+10D0h+var_1118], r13w
0x180006fa9  mov     [rsp+11D0h+var_1190], rax
0x180006fae  movzx   eax, word ptr [rdi+2]
0x180006fb2  mov     [rbp+10D0h+var_1120], ax
0x180006fb6  mov     al, [rdi+4]
0x180006fb9  mov     [rbp+10D0h+var_111E], al
0x180006fbc  movzx   eax, word ptr [rdi+6]
0x180006fc0  mov     [rbp+10D0h+var_1100], ax
0x180006fc4  mov     al, [rdi+8]
0x180006fc7  mov     [rbp+10D0h+var_10FE], al
0x180006fca  movdqu  [rbp+10D0h+var_1110], xmm0
0x180006fcf  mov     [rbp+10D0h+var_10FC], r13d
0x180006fd3  mov     [rbp+10D0h+var_10F8], r13w
0x180006fd8  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180006fdd  jmp     loc_180007076
0x180006fe2  mov     ebx, r13d
0x180006fe5  cmp     [rbp+10D0h+var_111C], r13d
0x180006fe9  jbe     loc_180007076
0x180006fef  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006ff3  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180006ff8  lea     rcx, [rbp+10D0h+var_1100]; this
0x180006ffc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007001  test    al, al
0x180007003  jz      short loc_180007076
0x180007005  mov     eax, [rbp+10D0h+var_10FC]
0x180007008  mov     rcx, [rbp+10D0h+var_1050]; this
0x18000700f  mov     [rsp+11D0h+var_1180], eax
0x180007013  movzx   eax, [rbp+10D0h+var_10F8]
0x180007017  mov     [rbp+10D0h+var_10E0], rax
0x18000701b  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000701f  mov     [rbp+10D0h+var_10D8], rax
0x180007023  movzx   eax, [rbp+10D0h+var_1118]
0x180007027  mov     [rbp+10D0h+var_10D0], rax
0x18000702b  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18000702f  mov     [rbp+10D0h+var_10C8], rax
0x180007033  test    rcx, rcx
0x180007036  jz      loc_1800071AF
0x18000703c  mov     rax, [rcx]
0x18000703f  lea     rdx, [rsp+11D0h+var_1180]
0x180007044  mov     [rsp+11D0h+var_11A8], rdx
0x180007049  lea     r9, [rbp+10D0h+var_10D8]
0x18000704d  lea     rdx, [rbp+10D0h+var_10E0]
0x180007051  mov     [rsp+11D0h+var_11B0], rdx
0x180007056  lea     r8, [rbp+10D0h+var_10D0]
0x18000705a  mov     rax, [rax+20h]
0x18000705e  lea     rdx, [rbp+10D0h+var_10C8]
0x180007062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007067  test    al, al
0x180007069  jz      short loc_1800070E3
0x18000706b  inc     ebx
0x18000706d  cmp     ebx, [rbp+10D0h+var_111C]
0x180007070  jb      loc_180006FEF
0x180007076  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000707a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000707f  lea     rcx, [rbp+10D0h+var_1120]; this
0x180007083  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007088  test    al, al
0x18000708a  jnz     loc_180006FE2
0x180007090  mov     rcx, [rbp+10D0h+var_1050]
0x180007097  test    rcx, rcx
0x18000709a  jz      short loc_1800070A8
0x18000709c  mov     rax, [rcx]
0x18000709f  mov     rax, [rax+18h]
0x1800070a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070a8  mov     bl, 1
0x1800070aa  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x1800070ae  jz      short loc_180007122
0x1800070b0  mov     rdx, [rsp+11D0h+var_1158]
0x1800070b5  mov     rcx, r14
0x1800070b8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800070bc  mov     eax, [rsp+11D0h+var_1188]
0x1800070c0  sub     r8d, edx
0x1800070c3  mov     [rsp+11D0h+var_11A0], 1
0x1800070cb  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800070cf  call    wil_details_NtUpdateWnfStateData
0x1800070d4  cmp     eax, 0C0000001h
0x1800070d9  jnz     short loc_180007100
0x1800070db  inc     r15
0x1800070de  mov     bl, r13b
0x1800070e1  jmp     short loc_18000712E
0x1800070e3  mov     rcx, [rbp+10D0h+var_1050]
0x1800070ea  test    rcx, rcx
0x1800070ed  jz      short loc_1800070FB
0x1800070ef  mov     rax, [rcx]
0x1800070f2  mov     rax, [rax+18h]
0x1800070f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070fb  mov     bl, r13b
0x1800070fe  jmp     short loc_1800070AA
0x180007100  test    eax, eax
0x180007102  jz      short loc_180007122
0x180007104  mov     rdx, [rsp+11D0h+var_1158]
0x180007109  mov     rcx, r14
0x18000710c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180007110  sub     r8d, edx
0x180007113  mov     [rsp+11D0h+var_11A0], r13d
0x180007118  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18000711d  call    wil_details_NtUpdateWnfStateData
0x180007122  mov     rax, [rbp+10D0h+var_1130]
0x180007126  add     r14, 8
0x18000712a  mov     [rbp+10D0h+var_1128], rax
0x18000712e  mov     rsi, [rbp+10D0h+lpMem]
0x180007132  mov     [rbp+10D0h+lpMem], r13
0x180007136  test    rsi, rsi
0x180007139  jz      short loc_18000714F
0x18000713b  call    cs:__imp_GetProcessHeap
0x180007141  mov     r8, rsi; lpMem
0x180007144  xor     edx, edx; dwFlags
0x180007146  mov     rcx, rax; hHeap
0x180007149  call    cs:__imp_HeapFree
0x18000714f  test    bl, bl
0x180007151  jnz     short loc_180007185
0x180007153  cmp     r14, r12
0x180007156  jnb     short loc_180007185
0x180007158  cmp     r15, 32h ; '2'
0x18000715c  jb      loc_180006E32
0x180007162  jmp     short loc_180007185
0x180007164  mov     rbx, [rbp+10D0h+lpMem]
0x180007168  mov     [rbp+10D0h+lpMem], r13
0x18000716c  test    rbx, rbx
0x18000716f  jz      short loc_180007185
0x180007171  call    cs:__imp_GetProcessHeap
0x180007177  mov     r8, rbx; lpMem
0x18000717a  xor     edx, edx; dwFlags
0x18000717c  mov     rcx, rax; hHeap
0x18000717f  call    cs:__imp_HeapFree
0x180007185  mov     rcx, [rbp+10D0h+var_40]
0x18000718c  xor     rcx, rsp; StackCookie
0x18000718f  call    __security_check_cookie
0x180007194  mov     rbx, [rsp+11D0h+arg_8]
0x18000719c  add     rsp, 11A0h
0x1800071a3  pop     r15
0x1800071a5  pop     r14
0x1800071a7  pop     r13
0x1800071a9  pop     r12
0x1800071ab  pop     rdi
0x1800071ac  pop     rsi
0x1800071ad  pop     rbp
0x1800071ae  retn
0x1800071af  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
