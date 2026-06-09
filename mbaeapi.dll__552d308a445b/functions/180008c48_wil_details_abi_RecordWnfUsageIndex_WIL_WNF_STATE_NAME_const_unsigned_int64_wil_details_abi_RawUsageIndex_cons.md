# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180008c48`
- end: `0x180009020`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180008124`

## callees

- `0x1800024e0`
- `0x180007bd8`
- `0x180007fdc`
- `0x180008c48`
- `0x180009784`
- `0x18000ad4c`
- `0x18000b570`
- `0x1800588d0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d28`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fdc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fdc`

## string_xrefs

- `0x180008d21`: `ntdll.dll`

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
0x180008c48  mov     [rsp-8+arg_8], rbx
0x180008c4d  push    rbp
0x180008c4e  push    rsi
0x180008c4f  push    rdi
0x180008c50  push    r12
0x180008c52  push    r13
0x180008c54  push    r14
0x180008c56  push    r15
0x180008c58  lea     rbp, [rsp-10A0h]
0x180008c60  mov     eax, 11A0h
0x180008c65  call    _alloca_probe
0x180008c6a  sub     rsp, rax
0x180008c6d  mov     rax, cs:__security_cookie
0x180008c74  xor     rax, rsp
0x180008c77  mov     [rbp+10D0h+var_40], rax
0x180008c7e  mov     rdi, r8
0x180008c81  mov     r14, rcx
0x180008c84  lea     r13, [rcx+rdx*8]
0x180008c88  xor     r15d, r15d
0x180008c8b  mov     r12d, r15d
0x180008c8e  mov     [rbp+10D0h+var_1128], r15
0x180008c92  mov     cl, [rdi+8]
0x180008c95  movzx   edx, word ptr [rdi+6]
0x180008c99  movzx   eax, word ptr [rdi]
0x180008c9c  mov     [rsp+11D0h+var_1170], ax
0x180008ca1  movzx   eax, word ptr [rdi+2]
0x180008ca5  mov     [rsp+11D0h+var_116E], ax
0x180008caa  mov     al, [rdi+4]
0x180008cad  mov     [rsp+11D0h+var_116C], al
0x180008cb1  mov     [rsp+11D0h+var_116A], dx
0x180008cb6  mov     [rsp+11D0h+var_1168], cl
0x180008cba  test    dx, dx
0x180008cbd  jz      short loc_180008CDC
0x180008cbf  mov     eax, edx
0x180008cc1  cmp     cl, 1
0x180008cc4  jnz     short loc_180008CCC
0x180008cc6  add     rax, 2
0x180008cca  jmp     short loc_180008CD5
0x180008ccc  cmp     cl, 2
0x180008ccf  jnz     short loc_180008CD5
0x180008cd1  add     rax, 4
0x180008cd5  mov     [rsp+11D0h+var_1160], rax
0x180008cda  jmp     short loc_180008CE1
0x180008cdc  mov     [rsp+11D0h+var_1160], r15
0x180008ce1  mov     [rsp+11D0h+var_1158], r15
0x180008ce6  xorps   xmm0, xmm0
0x180008ce9  movdqa  [rbp+10D0h+var_1150], xmm0
0x180008cee  mov     [rbp+10D0h+lpMem], r15
0x180008cf2  mov     [rbp+10D0h+var_1138], 0
0x180008cf8  mov     [rbp+10D0h+var_1136], r15b
0x180008cfc  mov     [rsp+11D0h+var_1188], r15d
0x180008d01  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180008d09  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008d10  test    rax, rax
0x180008d13  jnz     short loc_180008D58
0x180008d15  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d1c  test    rax, rax
0x180008d1f  jnz     short loc_180008D35
0x180008d21  lea     rcx, ModuleName; "ntdll.dll"
0x180008d28  call    cs:__imp_GetModuleHandleW
0x180008d2e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d35  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008d3c  mov     rcx, rax; hModule
0x180008d3f  call    cs:__imp_GetProcAddress
0x180008d45  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008d4c  test    rax, rax
0x180008d4f  jnz     short loc_180008D58
0x180008d51  mov     ebx, 0C0000139h
0x180008d56  jmp     short loc_180008D82
0x180008d58  lea     rcx, [rsp+11D0h+var_1190]
0x180008d5d  mov     [rsp+11D0h+var_11A8], rcx
0x180008d62  lea     rcx, [rbp+10D0h+var_1040]
0x180008d69  mov     [rsp+11D0h+var_11B0], rcx
0x180008d6e  lea     r9, [rsp+11D0h+var_1188]
0x180008d73  xor     r8d, r8d
0x180008d76  xor     edx, edx
0x180008d78  mov     rcx, r14
0x180008d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d80  mov     ebx, eax
0x180008d82  mov     ecx, ebx; this
0x180008d84  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180008d89  test    ebx, ebx
0x180008d8b  jz      short loc_180008D9B
0x180008d8d  mov     eax, r15d
0x180008d90  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180008d94  mov     [rsp+11D0h+var_1188], r15d
0x180008d99  jmp     short loc_180008D9F
0x180008d9b  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180008d9f  mov     r8d, eax; unsigned __int64
0x180008da2  mov     r9d, 1000h; unsigned __int64
0x180008da8  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180008daf  lea     rcx, [rsp+11D0h+var_1170]; this
0x180008db4  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180008db9  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180008dbd  jnz     loc_180008FCF
0x180008dc3  mov     [rbp+10D0h+var_1130], r15
0x180008dc7  lea     rax, ??_7?$__func@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@$$A6A_NPEAX131I@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180008dce  mov     [rbp+10D0h+var_10B0], rax
0x180008dd2  lea     rax, [rbp+10D0h+var_1130]
0x180008dd6  mov     [rbp+10D0h+var_10A8], rax
0x180008dda  lea     rax, [rbp+10D0h+var_1128]
0x180008dde  mov     [rbp+10D0h+var_10A0], rax
0x180008de2  lea     rax, [rsp+11D0h+var_1170]
0x180008de7  mov     [rbp+10D0h+var_1098], rax
0x180008deb  lea     rax, [rbp+10D0h+var_10B0]
0x180008def  mov     [rbp+10D0h+var_1048], rax
0x180008df6  lea     rax, [rbp+10D0h+var_10B8]
0x180008dfa  mov     [rbp+10D0h+var_10C0], rax
0x180008dfe  mov     rax, [rdi+18h]
0x180008e02  add     rax, 0Ah
0x180008e06  mov     [rsp+11D0h+var_1190], rax
0x180008e0b  movzx   eax, word ptr [rdi+2]
0x180008e0f  mov     [rbp+10D0h+var_1120], ax
0x180008e13  mov     al, [rdi+4]
0x180008e16  mov     [rbp+10D0h+var_111E], al
0x180008e19  mov     [rbp+10D0h+var_111C], r15d
0x180008e1d  mov     [rbp+10D0h+var_1118], r15w
0x180008e22  xorps   xmm0, xmm0
0x180008e25  movdqu  [rbp+10D0h+var_1110], xmm0
0x180008e2a  movzx   eax, word ptr [rdi+6]
0x180008e2e  mov     [rbp+10D0h+var_1100], ax
0x180008e32  mov     al, [rdi+8]
0x180008e35  mov     [rbp+10D0h+var_10FE], al
0x180008e38  mov     [rbp+10D0h+var_10FC], r15d
0x180008e3c  mov     [rbp+10D0h+var_10F8], r15w
0x180008e41  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180008e46  jmp     loc_180008EDE
0x180008e4b  mov     ebx, r15d
0x180008e4e  mov     esi, [rbp+10D0h+var_111C]
0x180008e51  test    esi, esi
0x180008e53  jz      loc_180008EDE
0x180008e59  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180008e5d  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008e61  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180008e66  lea     rcx, [rbp+10D0h+var_1100]; this
0x180008e6a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008e6f  test    al, al
0x180008e71  jz      short loc_180008EDB
0x180008e73  mov     eax, [rbp+10D0h+var_10FC]
0x180008e76  mov     [rsp+11D0h+var_1180], eax
0x180008e7a  movzx   eax, [rbp+10D0h+var_10F8]
0x180008e7e  mov     [rbp+10D0h+var_10E0], rax
0x180008e82  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180008e86  mov     [rbp+10D0h+var_10D8], rax
0x180008e8a  movzx   eax, [rbp+10D0h+var_1118]
0x180008e8e  mov     [rbp+10D0h+var_10D0], rax
0x180008e92  mov     [rbp+10D0h+var_10C8], r15
0x180008e96  mov     rcx, [rbp+10D0h+var_1048]; this
0x180008e9d  test    rcx, rcx
0x180008ea0  jz      loc_18000901A
0x180008ea6  mov     rax, [rcx]
0x180008ea9  lea     rdx, [rsp+11D0h+var_1180]
0x180008eae  mov     [rsp+11D0h+var_11A8], rdx
0x180008eb3  lea     rdx, [rbp+10D0h+var_10E0]
0x180008eb7  mov     [rsp+11D0h+var_11B0], rdx
0x180008ebc  lea     r9, [rbp+10D0h+var_10D8]
0x180008ec0  lea     r8, [rbp+10D0h+var_10D0]
0x180008ec4  lea     rdx, [rbp+10D0h+var_10C8]
0x180008ec8  mov     rax, [rax+20h]
0x180008ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ed1  test    al, al
0x180008ed3  jz      short loc_180008F4B
0x180008ed5  inc     ebx
0x180008ed7  cmp     ebx, esi
0x180008ed9  jb      short loc_180008E5D
0x180008edb  xor     r15d, r15d
0x180008ede  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008ee2  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180008ee7  lea     rcx, [rbp+10D0h+var_1120]; this
0x180008eeb  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008ef0  test    al, al
0x180008ef2  jnz     loc_180008E4B
0x180008ef8  mov     rcx, [rbp+10D0h+var_1048]
0x180008eff  test    rcx, rcx
0x180008f02  jz      short loc_180008F10
0x180008f04  mov     rax, [rcx]
0x180008f07  mov     rax, [rax+18h]
0x180008f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f10  mov     bl, 1
0x180008f12  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x180008f16  jz      short loc_180008F8D
0x180008f18  mov     eax, [rsp+11D0h+var_1188]
0x180008f1c  mov     rdx, [rsp+11D0h+var_1158]
0x180008f21  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180008f25  sub     r8d, edx
0x180008f28  mov     [rsp+11D0h+var_11A0], 1
0x180008f30  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180008f34  mov     rcx, r14
0x180008f37  call    wil_details_NtUpdateWnfStateData
0x180008f3c  cmp     eax, 0C0000001h
0x180008f41  jnz     short loc_180008F6B
0x180008f43  inc     r12
0x180008f46  mov     bl, r15b
0x180008f49  jmp     short loc_180008F99
0x180008f4b  mov     rcx, [rbp+10D0h+var_1048]
0x180008f52  xor     r15d, r15d
0x180008f55  test    rcx, rcx
0x180008f58  jz      short loc_180008F66
0x180008f5a  mov     rax, [rcx]
0x180008f5d  mov     rax, [rax+18h]
0x180008f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f66  mov     bl, r15b
0x180008f69  jmp     short loc_180008F12
0x180008f6b  test    eax, eax
0x180008f6d  jz      short loc_180008F8D
0x180008f6f  mov     rdx, [rsp+11D0h+var_1158]
0x180008f74  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180008f78  sub     r8d, edx
0x180008f7b  mov     [rsp+11D0h+var_11A0], r15d
0x180008f80  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180008f85  mov     rcx, r14
0x180008f88  call    wil_details_NtUpdateWnfStateData
0x180008f8d  add     r14, 8
0x180008f91  mov     rax, [rbp+10D0h+var_1130]
0x180008f95  mov     [rbp+10D0h+var_1128], rax
0x180008f99  mov     rsi, [rbp+10D0h+lpMem]
0x180008f9d  mov     [rbp+10D0h+lpMem], r15
0x180008fa1  test    rsi, rsi
0x180008fa4  jz      short loc_180008FBA
0x180008fa6  call    cs:__imp_GetProcessHeap
0x180008fac  mov     rcx, rax; hHeap
0x180008faf  mov     r8, rsi; lpMem
0x180008fb2  xor     edx, edx; dwFlags
0x180008fb4  call    cs:__imp_HeapFree
0x180008fba  test    bl, bl
0x180008fbc  jnz     short loc_180008FF0
0x180008fbe  cmp     r14, r13
0x180008fc1  jnb     short loc_180008FF0
0x180008fc3  cmp     r12, 32h ; '2'
0x180008fc7  jb      loc_180008C92
0x180008fcd  jmp     short loc_180008FF0
0x180008fcf  mov     rbx, [rbp+10D0h+lpMem]
0x180008fd3  mov     [rbp+10D0h+lpMem], r15
0x180008fd7  test    rbx, rbx
0x180008fda  jz      short loc_180008FF0
0x180008fdc  call    cs:__imp_GetProcessHeap
0x180008fe2  mov     rcx, rax; hHeap
0x180008fe5  mov     r8, rbx; lpMem
0x180008fe8  xor     edx, edx; dwFlags
0x180008fea  call    cs:__imp_HeapFree
0x180008ff0  mov     rcx, [rbp+10D0h+var_40]
0x180008ff7  xor     rcx, rsp; StackCookie
0x180008ffa  call    __security_check_cookie
0x180008fff  mov     rbx, [rsp+11D0h+arg_8]
0x180009007  add     rsp, 11A0h
0x18000900e  pop     r15
0x180009010  pop     r14
0x180009012  pop     r13
0x180009014  pop     r12
0x180009016  pop     rdi
0x180009017  pop     rsi
0x180009018  pop     rbp
0x180009019  retn
0x18000901a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
