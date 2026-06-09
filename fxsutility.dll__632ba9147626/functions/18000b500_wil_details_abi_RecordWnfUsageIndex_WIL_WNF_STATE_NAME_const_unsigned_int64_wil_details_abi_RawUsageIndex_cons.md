# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000b500`
- end: `0x18000b8d7`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ac2c`

## callees

- `0x18000a7e8`
- `0x18000ab3c`
- `0x18000b500`
- `0x18000bcc4`
- `0x18000cedc`
- `0x18000d734`
- `0x180015cf0`
- `0x180015db0`
- `0x180017010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000b86a`
- `KERNEL32!HeapFree` at `0x18000b8a1`
- `KERNEL32!HeapFree` at `0x18000b86a`
- `KERNEL32!HeapFree` at `0x18000b8a1`
- `KERNEL32!GetProcessHeap` at `0x18000b85c`
- `KERNEL32!GetProcessHeap` at `0x18000b893`
- `KERNEL32!GetProcessHeap` at `0x18000b85c`
- `KERNEL32!GetProcessHeap` at `0x18000b893`
- `KERNEL32!GetModuleHandleW` at `0x18000b5df`
- `KERNEL32!GetModuleHandleW` at `0x18000b5df`
- `KERNEL32!GetProcAddress` at `0x18000b5f6`
- `KERNEL32!GetProcAddress` at `0x18000b5f6`

## string_xrefs

- `0x18000b5d8`: `ntdll.dll`

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
  wil::details_abi *v6; // r12
  unsigned __int64 v7; // r15
  char v8; // cl
  unsigned int v9; // edx
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // edi
  unsigned int v15; // eax
  int v16; // edi
  __int64 v17; // r9
  char v18; // di
  int updated; // eax
  __int64 v20; // r9
  void *v21; // rsi
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  __int64 *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v29; // [rsp+64h] [rbp-9Ch]
  __int16 v30; // [rsp+66h] [rbp-9Ah]
  char v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  __int128 v34; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v36; // [rsp+98h] [rbp-68h]
  char v37; // [rsp+9Ah] [rbp-66h]
  __int64 v38; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v40; // [rsp+B0h] [rbp-50h] BYREF
  char v41; // [rsp+B2h] [rbp-4Eh]
  unsigned int v42; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v43; // [rsp+B8h] [rbp-48h]
  __int128 v44; // [rsp+C0h] [rbp-40h]
  __int16 v45; // [rsp+D0h] [rbp-30h] BYREF
  char v46; // [rsp+D2h] [rbp-2Eh]
  int v47; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v48; // [rsp+D8h] [rbp-28h]
  __int128 v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v52; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v53[2]; // [rsp+108h] [rbp+8h] BYREF
  char v54; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v55[13]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *v56; // [rsp+188h] [rbp+88h]
  _BYTE v57[4096]; // [rsp+190h] [rbp+90h] BYREF

  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v39 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v28[0] = *(_WORD *)a3;
    v28[1] = *(_WORD *)(a3 + 2);
    v29 = *(_BYTE *)(a3 + 4);
    v30 = v9;
    v31 = v8;
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
      v32 = v10;
    }
    else
    {
      v32 = 0;
    }
    v33 = 0;
    v34 = 0;
    lpMem = 0;
    v36 = 0;
    v37 = 0;
    v27[0] = 0;
    LODWORD(v26) = 4096;
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
      v25 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v27);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v26) = 0;
      v27[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v26;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v28, v57, v15, 0x1000u);
    if ( HIBYTE(v36) )
      break;
    v38 = 0;
    v55[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v55[1] = &v38;
    v55[2] = &v39;
    v55[3] = v28;
    v56 = (wil::details::in1diag3 *)v55;
    v53[1] = &v54;
    v26 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
    v40 = *(_WORD *)(a3 + 2);
    v41 = *(_BYTE *)(a3 + 4);
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = *(_WORD *)(a3 + 6);
    v46 = *(_BYTE *)(a3 + 8);
    v47 = 0;
    v48 = 0;
    v49 = 0;
LABEL_25:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v40,
              &v26,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      if ( v42 )
      {
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v45,
                  &v26,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v27[2] = v47;
          v50 = v48;
          v51 = *((_QWORD *)&v49 + 1);
          v52 = v43;
          v53[0] = *((_QWORD *)&v44 + 1);
          if ( !v56 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v25 = &v50;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, _QWORD *, __int64 *, __int64 *))(*(_QWORD *)v56 + 32LL))(
                  v56,
                  v53,
                  &v52,
                  &v51) )
          {
            if ( v56 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
            v18 = 0;
            goto LABEL_29;
          }
          if ( ++v16 >= v42 )
            goto LABEL_25;
        }
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
    v18 = 1;
LABEL_29:
    if ( !(_BYTE)v36 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v33, (int)v34 - (int)v33, v17, (int)v25, v27[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v33, v34 - v33, v20, (int)v25, 0, 0);
LABEL_37:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v39 = v38;
      goto LABEL_38;
    }
    ++v7;
    v18 = 0;
LABEL_38:
    v21 = lpMem;
    lpMem = 0;
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
    if ( v18 || v5 >= v6 || v7 >= 0x32 )
      return;
  }
  v23 = lpMem;
  lpMem = 0;
  if ( v23 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v23);
  }
}

```

## disassembly

```asm
0x18000b500  mov     [rsp-8+arg_8], rbx
0x18000b505  push    rbp
0x18000b506  push    rsi
0x18000b507  push    rdi
0x18000b508  push    r12
0x18000b50a  push    r13
0x18000b50c  push    r14
0x18000b50e  push    r15
0x18000b510  lea     rbp, [rsp-10A0h]
0x18000b518  mov     eax, 11A0h
0x18000b51d  call    _alloca_probe
0x18000b522  sub     rsp, rax
0x18000b525  mov     rax, cs:__security_cookie
0x18000b52c  xor     rax, rsp
0x18000b52f  mov     [rbp+10D0h+var_40], rax
0x18000b536  mov     rbx, r8
0x18000b539  mov     r14, rcx
0x18000b53c  lea     r12, [rcx+rdx*8]
0x18000b540  xor     r13d, r13d
0x18000b543  mov     r15d, r13d
0x18000b546  mov     [rbp+10D0h+var_1128], r13
0x18000b54a  mov     cl, [rbx+8]
0x18000b54d  movzx   edx, word ptr [rbx+6]
0x18000b551  movzx   eax, word ptr [rbx]
0x18000b554  mov     [rsp+11D0h+var_1170], ax
0x18000b559  movzx   eax, word ptr [rbx+2]
0x18000b55d  mov     [rsp+11D0h+var_116E], ax
0x18000b562  mov     al, [rbx+4]
0x18000b565  mov     [rsp+11D0h+var_116C], al
0x18000b569  mov     [rsp+11D0h+var_116A], dx
0x18000b56e  mov     [rsp+11D0h+var_1168], cl
0x18000b572  test    dx, dx
0x18000b575  jz      short loc_18000B594
0x18000b577  mov     eax, edx
0x18000b579  cmp     cl, 1
0x18000b57c  jnz     short loc_18000B584
0x18000b57e  add     rax, 2
0x18000b582  jmp     short loc_18000B58D
0x18000b584  cmp     cl, 2
0x18000b587  jnz     short loc_18000B58D
0x18000b589  add     rax, 4
0x18000b58d  mov     [rsp+11D0h+var_1160], rax
0x18000b592  jmp     short loc_18000B599
0x18000b594  mov     [rsp+11D0h+var_1160], r13
0x18000b599  mov     [rsp+11D0h+var_1158], r13
0x18000b59e  xorps   xmm0, xmm0
0x18000b5a1  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000b5a6  mov     [rbp+10D0h+lpMem], r13
0x18000b5aa  mov     [rbp+10D0h+var_1138], r13w
0x18000b5af  mov     [rbp+10D0h+var_1136], r13b
0x18000b5b3  mov     [rsp+11D0h+var_1188], r13d
0x18000b5b8  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000b5c0  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b5c7  test    rax, rax
0x18000b5ca  jnz     short loc_18000B60F
0x18000b5cc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b5d3  test    rax, rax
0x18000b5d6  jnz     short loc_18000B5EC
0x18000b5d8  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000b5df  call    cs:__imp_GetModuleHandleW
0x18000b5e5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b5ec  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b5f3  mov     rcx, rax; hModule
0x18000b5f6  call    cs:__imp_GetProcAddress
0x18000b5fc  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b603  test    rax, rax
0x18000b606  jnz     short loc_18000B60F
0x18000b608  mov     edi, 0C0000139h
0x18000b60d  jmp     short loc_18000B639
0x18000b60f  lea     rcx, [rsp+11D0h+var_1190]
0x18000b614  mov     [rsp+11D0h+var_11A8], rcx
0x18000b619  lea     rcx, [rbp+10D0h+var_1040]
0x18000b620  mov     [rsp+11D0h+var_11B0], rcx
0x18000b625  lea     r9, [rsp+11D0h+var_1188]
0x18000b62a  xor     r8d, r8d
0x18000b62d  xor     edx, edx
0x18000b62f  mov     rcx, r14
0x18000b632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b637  mov     edi, eax
0x18000b639  mov     ecx, edi; this
0x18000b63b  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000b640  test    edi, edi
0x18000b642  jz      short loc_18000B652
0x18000b644  mov     eax, r13d
0x18000b647  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000b64b  mov     [rsp+11D0h+var_1188], r13d
0x18000b650  jmp     short loc_18000B656
0x18000b652  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000b656  mov     r8d, eax; unsigned __int64
0x18000b659  mov     r9d, 1000h; unsigned __int64
0x18000b65f  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000b666  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000b66b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000b670  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18000b674  jnz     loc_18000B886
0x18000b67a  mov     [rbp+10D0h+var_1130], r13
0x18000b67e  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000b685  mov     [rbp+10D0h+var_10B0], rax
0x18000b689  lea     rax, [rbp+10D0h+var_1130]
0x18000b68d  mov     [rbp+10D0h+var_10A8], rax
0x18000b691  lea     rax, [rbp+10D0h+var_1128]
0x18000b695  mov     [rbp+10D0h+var_10A0], rax
0x18000b699  lea     rax, [rsp+11D0h+var_1170]
0x18000b69e  mov     [rbp+10D0h+var_1098], rax
0x18000b6a2  lea     rax, [rbp+10D0h+var_10B0]
0x18000b6a6  mov     [rbp+10D0h+var_1048], rax
0x18000b6ad  lea     rax, [rbp+10D0h+var_10B8]
0x18000b6b1  mov     [rbp+10D0h+var_10C0], rax
0x18000b6b5  mov     rax, [rbx+18h]
0x18000b6b9  add     rax, 0Ah
0x18000b6bd  mov     [rsp+11D0h+var_1190], rax
0x18000b6c2  movzx   eax, word ptr [rbx+2]
0x18000b6c6  mov     [rbp+10D0h+var_1120], ax
0x18000b6ca  mov     al, [rbx+4]
0x18000b6cd  mov     [rbp+10D0h+var_111E], al
0x18000b6d0  mov     [rbp+10D0h+var_111C], r13d
0x18000b6d4  mov     [rbp+10D0h+var_1118], r13w
0x18000b6d9  xorps   xmm0, xmm0
0x18000b6dc  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000b6e1  movzx   eax, word ptr [rbx+6]
0x18000b6e5  mov     [rbp+10D0h+var_1100], ax
0x18000b6e9  mov     al, [rbx+8]
0x18000b6ec  mov     [rbp+10D0h+var_10FE], al
0x18000b6ef  mov     [rbp+10D0h+var_10FC], r13d
0x18000b6f3  mov     [rbp+10D0h+var_10F8], r13w
0x18000b6f8  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000b6fd  jmp     loc_18000B796
0x18000b702  mov     edi, r13d
0x18000b705  cmp     [rbp+10D0h+var_111C], r13d
0x18000b709  jbe     loc_18000B796
0x18000b70f  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000b713  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b718  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000b71c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b721  test    al, al
0x18000b723  jz      short loc_18000B796
0x18000b725  mov     eax, [rbp+10D0h+var_10FC]
0x18000b728  mov     [rsp+11D0h+var_1180], eax
0x18000b72c  movzx   eax, [rbp+10D0h+var_10F8]
0x18000b730  mov     [rbp+10D0h+var_10E0], rax
0x18000b734  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000b738  mov     [rbp+10D0h+var_10D8], rax
0x18000b73c  movzx   eax, [rbp+10D0h+var_1118]
0x18000b740  mov     [rbp+10D0h+var_10D0], rax
0x18000b744  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18000b748  mov     [rbp+10D0h+var_10C8], rax
0x18000b74c  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000b753  test    rcx, rcx
0x18000b756  jz      loc_18000B8D1
0x18000b75c  mov     rax, [rcx]
0x18000b75f  lea     rdx, [rsp+11D0h+var_1180]
0x18000b764  mov     [rsp+11D0h+var_11A8], rdx
0x18000b769  lea     rdx, [rbp+10D0h+var_10E0]
0x18000b76d  mov     [rsp+11D0h+var_11B0], rdx
0x18000b772  lea     r9, [rbp+10D0h+var_10D8]
0x18000b776  lea     r8, [rbp+10D0h+var_10D0]
0x18000b77a  lea     rdx, [rbp+10D0h+var_10C8]
0x18000b77e  mov     rax, [rax+20h]
0x18000b782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b787  test    al, al
0x18000b789  jz      short loc_18000B804
0x18000b78b  inc     edi
0x18000b78d  cmp     edi, [rbp+10D0h+var_111C]
0x18000b790  jb      loc_18000B70F
0x18000b796  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000b79a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b79f  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000b7a3  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b7a8  test    al, al
0x18000b7aa  jnz     loc_18000B702
0x18000b7b0  mov     rcx, [rbp+10D0h+var_1048]
0x18000b7b7  test    rcx, rcx
0x18000b7ba  jz      short loc_18000B7C8
0x18000b7bc  mov     rax, [rcx]
0x18000b7bf  mov     rax, [rax+18h]
0x18000b7c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7c8  mov     dil, 1
0x18000b7cb  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18000b7cf  jz      short loc_18000B843
0x18000b7d1  mov     eax, [rsp+11D0h+var_1188]
0x18000b7d5  mov     rdx, [rsp+11D0h+var_1158]
0x18000b7da  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b7de  sub     r8d, edx
0x18000b7e1  mov     [rsp+11D0h+var_11A0], 1
0x18000b7e9  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000b7ed  mov     rcx, r14
0x18000b7f0  call    wil_details_NtUpdateWnfStateData
0x18000b7f5  cmp     eax, 0C0000001h
0x18000b7fa  jnz     short loc_18000B821
0x18000b7fc  inc     r15
0x18000b7ff  mov     dil, r13b
0x18000b802  jmp     short loc_18000B84F
0x18000b804  mov     rcx, [rbp+10D0h+var_1048]
0x18000b80b  test    rcx, rcx
0x18000b80e  jz      short loc_18000B81C
0x18000b810  mov     rax, [rcx]
0x18000b813  mov     rax, [rax+18h]
0x18000b817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b81c  mov     dil, r13b
0x18000b81f  jmp     short loc_18000B7CB
0x18000b821  test    eax, eax
0x18000b823  jz      short loc_18000B843
0x18000b825  mov     rdx, [rsp+11D0h+var_1158]
0x18000b82a  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b82e  sub     r8d, edx
0x18000b831  mov     [rsp+11D0h+var_11A0], r13d
0x18000b836  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18000b83b  mov     rcx, r14
0x18000b83e  call    wil_details_NtUpdateWnfStateData
0x18000b843  add     r14, 8
0x18000b847  mov     rax, [rbp+10D0h+var_1130]
0x18000b84b  mov     [rbp+10D0h+var_1128], rax
0x18000b84f  mov     rsi, [rbp+10D0h+lpMem]
0x18000b853  mov     [rbp+10D0h+lpMem], r13
0x18000b857  test    rsi, rsi
0x18000b85a  jz      short loc_18000B870
0x18000b85c  call    cs:__imp_GetProcessHeap
0x18000b862  mov     rcx, rax; hHeap
0x18000b865  mov     r8, rsi; lpMem
0x18000b868  xor     edx, edx; dwFlags
0x18000b86a  call    cs:__imp_HeapFree
0x18000b870  test    dil, dil
0x18000b873  jnz     short loc_18000B8A7
0x18000b875  cmp     r14, r12
0x18000b878  jnb     short loc_18000B8A7
0x18000b87a  cmp     r15, 32h ; '2'
0x18000b87e  jb      loc_18000B54A
0x18000b884  jmp     short loc_18000B8A7
0x18000b886  mov     rbx, [rbp+10D0h+lpMem]
0x18000b88a  mov     [rbp+10D0h+lpMem], r13
0x18000b88e  test    rbx, rbx
0x18000b891  jz      short loc_18000B8A7
0x18000b893  call    cs:__imp_GetProcessHeap
0x18000b899  mov     rcx, rax; hHeap
0x18000b89c  mov     r8, rbx; lpMem
0x18000b89f  xor     edx, edx; dwFlags
0x18000b8a1  call    cs:__imp_HeapFree
0x18000b8a7  mov     rcx, [rbp+10D0h+var_40]
0x18000b8ae  xor     rcx, rsp; StackCookie
0x18000b8b1  call    __security_check_cookie
0x18000b8b6  mov     rbx, [rsp+11D0h+arg_8]
0x18000b8be  add     rsp, 11A0h
0x18000b8c5  pop     r15
0x18000b8c7  pop     r14
0x18000b8c9  pop     r13
0x18000b8cb  pop     r12
0x18000b8cd  pop     rdi
0x18000b8ce  pop     rsi
0x18000b8cf  pop     rbp
0x18000b8d0  retn
0x18000b8d1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
