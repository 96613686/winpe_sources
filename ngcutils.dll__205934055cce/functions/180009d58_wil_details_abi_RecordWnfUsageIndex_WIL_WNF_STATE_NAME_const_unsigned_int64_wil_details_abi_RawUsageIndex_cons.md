# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180009d58`
- end: `0x18000a130`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180009230`

## callees

- `0x180003080`
- `0x180008c58`
- `0x1800090e8`
- `0x180009d58`
- `0x18000a8c4`
- `0x18000be1c`
- `0x18000c620`
- `0x180057f50`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009e4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009e4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a0c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a0fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a0c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a0fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a0b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a0ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a0b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a0ec`

## string_xrefs

- `0x180009e31`: `ntdll.dll`

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
0x180009d58  mov     [rsp-8+arg_8], rbx
0x180009d5d  push    rbp
0x180009d5e  push    rsi
0x180009d5f  push    rdi
0x180009d60  push    r12
0x180009d62  push    r13
0x180009d64  push    r14
0x180009d66  push    r15
0x180009d68  lea     rbp, [rsp-10A0h]
0x180009d70  mov     eax, 11A0h
0x180009d75  call    _alloca_probe
0x180009d7a  sub     rsp, rax
0x180009d7d  mov     rax, cs:__security_cookie
0x180009d84  xor     rax, rsp
0x180009d87  mov     [rbp+10D0h+var_40], rax
0x180009d8e  mov     rdi, r8
0x180009d91  mov     r14, rcx
0x180009d94  lea     r13, [rcx+rdx*8]
0x180009d98  xor     r15d, r15d
0x180009d9b  mov     r12d, r15d
0x180009d9e  mov     [rbp+10D0h+var_1128], r15
0x180009da2  mov     cl, [rdi+8]
0x180009da5  movzx   edx, word ptr [rdi+6]
0x180009da9  movzx   eax, word ptr [rdi]
0x180009dac  mov     [rsp+11D0h+var_1170], ax
0x180009db1  movzx   eax, word ptr [rdi+2]
0x180009db5  mov     [rsp+11D0h+var_116E], ax
0x180009dba  mov     al, [rdi+4]
0x180009dbd  mov     [rsp+11D0h+var_116C], al
0x180009dc1  mov     [rsp+11D0h+var_116A], dx
0x180009dc6  mov     [rsp+11D0h+var_1168], cl
0x180009dca  test    dx, dx
0x180009dcd  jz      short loc_180009DEC
0x180009dcf  mov     eax, edx
0x180009dd1  cmp     cl, 1
0x180009dd4  jnz     short loc_180009DDC
0x180009dd6  add     rax, 2
0x180009dda  jmp     short loc_180009DE5
0x180009ddc  cmp     cl, 2
0x180009ddf  jnz     short loc_180009DE5
0x180009de1  add     rax, 4
0x180009de5  mov     [rsp+11D0h+var_1160], rax
0x180009dea  jmp     short loc_180009DF1
0x180009dec  mov     [rsp+11D0h+var_1160], r15
0x180009df1  mov     [rsp+11D0h+var_1158], r15
0x180009df6  xorps   xmm0, xmm0
0x180009df9  movdqa  [rbp+10D0h+var_1150], xmm0
0x180009dfe  mov     [rbp+10D0h+lpMem], r15
0x180009e02  mov     [rbp+10D0h+var_1138], 0
0x180009e08  mov     [rbp+10D0h+var_1136], r15b
0x180009e0c  mov     [rsp+11D0h+var_1188], r15d
0x180009e11  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180009e19  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180009e20  test    rax, rax
0x180009e23  jnz     short loc_180009E68
0x180009e25  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009e2c  test    rax, rax
0x180009e2f  jnz     short loc_180009E45
0x180009e31  lea     rcx, ModuleName; "ntdll.dll"
0x180009e38  call    cs:__imp_GetModuleHandleW
0x180009e3e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009e45  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180009e4c  mov     rcx, rax; hModule
0x180009e4f  call    cs:__imp_GetProcAddress
0x180009e55  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180009e5c  test    rax, rax
0x180009e5f  jnz     short loc_180009E68
0x180009e61  mov     ebx, 0C0000139h
0x180009e66  jmp     short loc_180009E92
0x180009e68  lea     rcx, [rsp+11D0h+var_1190]
0x180009e6d  mov     [rsp+11D0h+var_11A8], rcx
0x180009e72  lea     rcx, [rbp+10D0h+var_1040]
0x180009e79  mov     [rsp+11D0h+var_11B0], rcx
0x180009e7e  lea     r9, [rsp+11D0h+var_1188]
0x180009e83  xor     r8d, r8d
0x180009e86  xor     edx, edx
0x180009e88  mov     rcx, r14
0x180009e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e90  mov     ebx, eax
0x180009e92  mov     ecx, ebx; this
0x180009e94  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180009e99  test    ebx, ebx
0x180009e9b  jz      short loc_180009EAB
0x180009e9d  mov     eax, r15d
0x180009ea0  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180009ea4  mov     [rsp+11D0h+var_1188], r15d
0x180009ea9  jmp     short loc_180009EAF
0x180009eab  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180009eaf  mov     r8d, eax; unsigned __int64
0x180009eb2  mov     r9d, 1000h; unsigned __int64
0x180009eb8  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180009ebf  lea     rcx, [rsp+11D0h+var_1170]; this
0x180009ec4  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180009ec9  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180009ecd  jnz     loc_18000A0DF
0x180009ed3  mov     [rbp+10D0h+var_1130], r15
0x180009ed7  lea     rax, ??_7?$__func@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@$$A6A_NPEAX131I@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180009ede  mov     [rbp+10D0h+var_10B0], rax
0x180009ee2  lea     rax, [rbp+10D0h+var_1130]
0x180009ee6  mov     [rbp+10D0h+var_10A8], rax
0x180009eea  lea     rax, [rbp+10D0h+var_1128]
0x180009eee  mov     [rbp+10D0h+var_10A0], rax
0x180009ef2  lea     rax, [rsp+11D0h+var_1170]
0x180009ef7  mov     [rbp+10D0h+var_1098], rax
0x180009efb  lea     rax, [rbp+10D0h+var_10B0]
0x180009eff  mov     [rbp+10D0h+var_1048], rax
0x180009f06  lea     rax, [rbp+10D0h+var_10B8]
0x180009f0a  mov     [rbp+10D0h+var_10C0], rax
0x180009f0e  mov     rax, [rdi+18h]
0x180009f12  add     rax, 0Ah
0x180009f16  mov     [rsp+11D0h+var_1190], rax
0x180009f1b  movzx   eax, word ptr [rdi+2]
0x180009f1f  mov     [rbp+10D0h+var_1120], ax
0x180009f23  mov     al, [rdi+4]
0x180009f26  mov     [rbp+10D0h+var_111E], al
0x180009f29  mov     [rbp+10D0h+var_111C], r15d
0x180009f2d  mov     [rbp+10D0h+var_1118], r15w
0x180009f32  xorps   xmm0, xmm0
0x180009f35  movdqu  [rbp+10D0h+var_1110], xmm0
0x180009f3a  movzx   eax, word ptr [rdi+6]
0x180009f3e  mov     [rbp+10D0h+var_1100], ax
0x180009f42  mov     al, [rdi+8]
0x180009f45  mov     [rbp+10D0h+var_10FE], al
0x180009f48  mov     [rbp+10D0h+var_10FC], r15d
0x180009f4c  mov     [rbp+10D0h+var_10F8], r15w
0x180009f51  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180009f56  jmp     loc_180009FEE
0x180009f5b  mov     ebx, r15d
0x180009f5e  mov     esi, [rbp+10D0h+var_111C]
0x180009f61  test    esi, esi
0x180009f63  jz      loc_180009FEE
0x180009f69  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180009f6d  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009f71  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180009f76  lea     rcx, [rbp+10D0h+var_1100]; this
0x180009f7a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009f7f  test    al, al
0x180009f81  jz      short loc_180009FEB
0x180009f83  mov     eax, [rbp+10D0h+var_10FC]
0x180009f86  mov     [rsp+11D0h+var_1180], eax
0x180009f8a  movzx   eax, [rbp+10D0h+var_10F8]
0x180009f8e  mov     [rbp+10D0h+var_10E0], rax
0x180009f92  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180009f96  mov     [rbp+10D0h+var_10D8], rax
0x180009f9a  movzx   eax, [rbp+10D0h+var_1118]
0x180009f9e  mov     [rbp+10D0h+var_10D0], rax
0x180009fa2  mov     [rbp+10D0h+var_10C8], r15
0x180009fa6  mov     rcx, [rbp+10D0h+var_1048]; this
0x180009fad  test    rcx, rcx
0x180009fb0  jz      loc_18000A12A
0x180009fb6  mov     rax, [rcx]
0x180009fb9  lea     rdx, [rsp+11D0h+var_1180]
0x180009fbe  mov     [rsp+11D0h+var_11A8], rdx
0x180009fc3  lea     rdx, [rbp+10D0h+var_10E0]
0x180009fc7  mov     [rsp+11D0h+var_11B0], rdx
0x180009fcc  lea     r9, [rbp+10D0h+var_10D8]
0x180009fd0  lea     r8, [rbp+10D0h+var_10D0]
0x180009fd4  lea     rdx, [rbp+10D0h+var_10C8]
0x180009fd8  mov     rax, [rax+20h]
0x180009fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fe1  test    al, al
0x180009fe3  jz      short loc_18000A05B
0x180009fe5  inc     ebx
0x180009fe7  cmp     ebx, esi
0x180009fe9  jb      short loc_180009F6D
0x180009feb  xor     r15d, r15d
0x180009fee  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009ff2  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180009ff7  lea     rcx, [rbp+10D0h+var_1120]; this
0x180009ffb  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000a000  test    al, al
0x18000a002  jnz     loc_180009F5B
0x18000a008  mov     rcx, [rbp+10D0h+var_1048]
0x18000a00f  test    rcx, rcx
0x18000a012  jz      short loc_18000A020
0x18000a014  mov     rax, [rcx]
0x18000a017  mov     rax, [rax+18h]
0x18000a01b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a020  mov     bl, 1
0x18000a022  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000a026  jz      short loc_18000A09D
0x18000a028  mov     eax, [rsp+11D0h+var_1188]
0x18000a02c  mov     rdx, [rsp+11D0h+var_1158]
0x18000a031  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000a035  sub     r8d, edx
0x18000a038  mov     [rsp+11D0h+var_11A0], 1
0x18000a040  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000a044  mov     rcx, r14
0x18000a047  call    wil_details_NtUpdateWnfStateData
0x18000a04c  cmp     eax, 0C0000001h
0x18000a051  jnz     short loc_18000A07B
0x18000a053  inc     r12
0x18000a056  mov     bl, r15b
0x18000a059  jmp     short loc_18000A0A9
0x18000a05b  mov     rcx, [rbp+10D0h+var_1048]
0x18000a062  xor     r15d, r15d
0x18000a065  test    rcx, rcx
0x18000a068  jz      short loc_18000A076
0x18000a06a  mov     rax, [rcx]
0x18000a06d  mov     rax, [rax+18h]
0x18000a071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a076  mov     bl, r15b
0x18000a079  jmp     short loc_18000A022
0x18000a07b  test    eax, eax
0x18000a07d  jz      short loc_18000A09D
0x18000a07f  mov     rdx, [rsp+11D0h+var_1158]
0x18000a084  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000a088  sub     r8d, edx
0x18000a08b  mov     [rsp+11D0h+var_11A0], r15d
0x18000a090  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000a095  mov     rcx, r14
0x18000a098  call    wil_details_NtUpdateWnfStateData
0x18000a09d  add     r14, 8
0x18000a0a1  mov     rax, [rbp+10D0h+var_1130]
0x18000a0a5  mov     [rbp+10D0h+var_1128], rax
0x18000a0a9  mov     rsi, [rbp+10D0h+lpMem]
0x18000a0ad  mov     [rbp+10D0h+lpMem], r15
0x18000a0b1  test    rsi, rsi
0x18000a0b4  jz      short loc_18000A0CA
0x18000a0b6  call    cs:__imp_GetProcessHeap
0x18000a0bc  mov     rcx, rax; hHeap
0x18000a0bf  mov     r8, rsi; lpMem
0x18000a0c2  xor     edx, edx; dwFlags
0x18000a0c4  call    cs:__imp_HeapFree
0x18000a0ca  test    bl, bl
0x18000a0cc  jnz     short loc_18000A100
0x18000a0ce  cmp     r14, r13
0x18000a0d1  jnb     short loc_18000A100
0x18000a0d3  cmp     r12, 32h ; '2'
0x18000a0d7  jb      loc_180009DA2
0x18000a0dd  jmp     short loc_18000A100
0x18000a0df  mov     rbx, [rbp+10D0h+lpMem]
0x18000a0e3  mov     [rbp+10D0h+lpMem], r15
0x18000a0e7  test    rbx, rbx
0x18000a0ea  jz      short loc_18000A100
0x18000a0ec  call    cs:__imp_GetProcessHeap
0x18000a0f2  mov     rcx, rax; hHeap
0x18000a0f5  mov     r8, rbx; lpMem
0x18000a0f8  xor     edx, edx; dwFlags
0x18000a0fa  call    cs:__imp_HeapFree
0x18000a100  mov     rcx, [rbp+10D0h+var_40]
0x18000a107  xor     rcx, rsp; StackCookie
0x18000a10a  call    __security_check_cookie
0x18000a10f  mov     rbx, [rsp+11D0h+arg_8]
0x18000a117  add     rsp, 11A0h
0x18000a11e  pop     r15
0x18000a120  pop     r14
0x18000a122  pop     r13
0x18000a124  pop     r12
0x18000a126  pop     rdi
0x18000a127  pop     rsi
0x18000a128  pop     rbp
0x18000a129  retn
0x18000a12a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
