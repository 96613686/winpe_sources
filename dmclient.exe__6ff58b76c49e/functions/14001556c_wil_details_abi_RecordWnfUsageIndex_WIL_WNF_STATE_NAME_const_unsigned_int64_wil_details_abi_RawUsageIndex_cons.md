# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x14001556c`
- end: `0x140015943`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140014d0c`

## callees

- `0x14000bc1c`
- `0x14001496c`
- `0x140014c1c`
- `0x14001556c`
- `0x14001612c`
- `0x140016ed8`
- `0x1400187e0`
- `0x1400188a0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140015662`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140015662`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001564b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001564b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400158c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400158ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400158c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400158ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400158d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001590d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400158d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001590d`

## string_xrefs

- `0x140015644`: `ntdll.dll`

## pseudocode

```c
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
  int v17; // r9d
  char v18; // di
  int updated; // eax
  int v20; // r9d
  void *v21; // rsi
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  __int64 *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v26; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v27[6]; // [rsp+48h] [rbp-B8h] BYREF
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
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v5, 0, 0, v27);
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
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v5, v33, (int)v34 - (int)v33, v17, (_DWORD)v25, v27[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v5, v33, v34 - v33, v20, (_DWORD)v25, 0, 0);
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
0x14001556c  mov     [rsp-8+arg_8], rbx
0x140015571  push    rbp
0x140015572  push    rsi
0x140015573  push    rdi
0x140015574  push    r12
0x140015576  push    r13
0x140015578  push    r14
0x14001557a  push    r15
0x14001557c  lea     rbp, [rsp-10A0h]
0x140015584  mov     eax, 11A0h
0x140015589  call    _alloca_probe
0x14001558e  sub     rsp, rax
0x140015591  mov     rax, cs:__security_cookie
0x140015598  xor     rax, rsp
0x14001559b  mov     [rbp+10D0h+var_40], rax
0x1400155a2  mov     rbx, r8
0x1400155a5  mov     r14, rcx
0x1400155a8  lea     r12, [rcx+rdx*8]
0x1400155ac  xor     r13d, r13d
0x1400155af  mov     r15d, r13d
0x1400155b2  mov     [rbp+10D0h+var_1128], r13
0x1400155b6  mov     cl, [rbx+8]
0x1400155b9  movzx   edx, word ptr [rbx+6]
0x1400155bd  movzx   eax, word ptr [rbx]
0x1400155c0  mov     [rsp+11D0h+var_1170], ax
0x1400155c5  movzx   eax, word ptr [rbx+2]
0x1400155c9  mov     [rsp+11D0h+var_116E], ax
0x1400155ce  mov     al, [rbx+4]
0x1400155d1  mov     [rsp+11D0h+var_116C], al
0x1400155d5  mov     [rsp+11D0h+var_116A], dx
0x1400155da  mov     [rsp+11D0h+var_1168], cl
0x1400155de  test    dx, dx
0x1400155e1  jz      short loc_140015600
0x1400155e3  mov     eax, edx
0x1400155e5  cmp     cl, 1
0x1400155e8  jnz     short loc_1400155F0
0x1400155ea  add     rax, 2
0x1400155ee  jmp     short loc_1400155F9
0x1400155f0  cmp     cl, 2
0x1400155f3  jnz     short loc_1400155F9
0x1400155f5  add     rax, 4
0x1400155f9  mov     [rsp+11D0h+var_1160], rax
0x1400155fe  jmp     short loc_140015605
0x140015600  mov     [rsp+11D0h+var_1160], r13
0x140015605  mov     [rsp+11D0h+var_1158], r13
0x14001560a  xorps   xmm0, xmm0
0x14001560d  movdqa  [rbp+10D0h+var_1150], xmm0
0x140015612  mov     [rbp+10D0h+lpMem], r13
0x140015616  mov     [rbp+10D0h+var_1138], r13w
0x14001561b  mov     [rbp+10D0h+var_1136], r13b
0x14001561f  mov     [rsp+11D0h+var_1188], r13d
0x140015624  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x14001562c  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140015633  test    rax, rax
0x140015636  jnz     short loc_14001567B
0x140015638  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001563f  test    rax, rax
0x140015642  jnz     short loc_140015658
0x140015644  lea     rcx, ModuleName; "ntdll.dll"
0x14001564b  call    cs:__imp_GetModuleHandleW
0x140015651  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140015658  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14001565f  mov     rcx, rax; hModule
0x140015662  call    cs:__imp_GetProcAddress
0x140015668  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14001566f  test    rax, rax
0x140015672  jnz     short loc_14001567B
0x140015674  mov     edi, 0C0000139h
0x140015679  jmp     short loc_1400156A5
0x14001567b  lea     rcx, [rsp+11D0h+var_1190]
0x140015680  mov     [rsp+11D0h+var_11A8], rcx
0x140015685  lea     rcx, [rbp+10D0h+var_1040]
0x14001568c  mov     [rsp+11D0h+var_11B0], rcx
0x140015691  lea     r9, [rsp+11D0h+var_1188]
0x140015696  xor     r8d, r8d
0x140015699  xor     edx, edx
0x14001569b  mov     rcx, r14
0x14001569e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400156a3  mov     edi, eax
0x1400156a5  mov     ecx, edi; this
0x1400156a7  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1400156ac  test    edi, edi
0x1400156ae  jz      short loc_1400156BE
0x1400156b0  mov     eax, r13d
0x1400156b3  mov     dword ptr [rsp+11D0h+var_1190], eax
0x1400156b7  mov     [rsp+11D0h+var_1188], r13d
0x1400156bc  jmp     short loc_1400156C2
0x1400156be  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x1400156c2  mov     r8d, eax; unsigned __int64
0x1400156c5  mov     r9d, 1000h; unsigned __int64
0x1400156cb  lea     rdx, [rbp+10D0h+var_1040]; void *
0x1400156d2  lea     rcx, [rsp+11D0h+var_1170]; this
0x1400156d7  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1400156dc  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x1400156e0  jnz     loc_1400158F2
0x1400156e6  mov     [rbp+10D0h+var_1130], r13
0x1400156ea  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1400156f1  mov     [rbp+10D0h+var_10B0], rax
0x1400156f5  lea     rax, [rbp+10D0h+var_1130]
0x1400156f9  mov     [rbp+10D0h+var_10A8], rax
0x1400156fd  lea     rax, [rbp+10D0h+var_1128]
0x140015701  mov     [rbp+10D0h+var_10A0], rax
0x140015705  lea     rax, [rsp+11D0h+var_1170]
0x14001570a  mov     [rbp+10D0h+var_1098], rax
0x14001570e  lea     rax, [rbp+10D0h+var_10B0]
0x140015712  mov     [rbp+10D0h+var_1048], rax
0x140015719  lea     rax, [rbp+10D0h+var_10B8]
0x14001571d  mov     [rbp+10D0h+var_10C0], rax
0x140015721  mov     rax, [rbx+18h]
0x140015725  add     rax, 0Ah
0x140015729  mov     [rsp+11D0h+var_1190], rax
0x14001572e  movzx   eax, word ptr [rbx+2]
0x140015732  mov     [rbp+10D0h+var_1120], ax
0x140015736  mov     al, [rbx+4]
0x140015739  mov     [rbp+10D0h+var_111E], al
0x14001573c  mov     [rbp+10D0h+var_111C], r13d
0x140015740  mov     [rbp+10D0h+var_1118], r13w
0x140015745  xorps   xmm0, xmm0
0x140015748  movdqu  [rbp+10D0h+var_1110], xmm0
0x14001574d  movzx   eax, word ptr [rbx+6]
0x140015751  mov     [rbp+10D0h+var_1100], ax
0x140015755  mov     al, [rbx+8]
0x140015758  mov     [rbp+10D0h+var_10FE], al
0x14001575b  mov     [rbp+10D0h+var_10FC], r13d
0x14001575f  mov     [rbp+10D0h+var_10F8], r13w
0x140015764  movdqu  [rbp+10D0h+var_10F0], xmm0
0x140015769  jmp     loc_140015802
0x14001576e  mov     edi, r13d
0x140015771  cmp     [rbp+10D0h+var_111C], r13d
0x140015775  jbe     loc_140015802
0x14001577b  mov     r8, [rbx+20h]; unsigned __int8 *
0x14001577f  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x140015784  lea     rcx, [rbp+10D0h+var_1100]; this
0x140015788  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14001578d  test    al, al
0x14001578f  jz      short loc_140015802
0x140015791  mov     eax, [rbp+10D0h+var_10FC]
0x140015794  mov     [rsp+11D0h+var_1180], eax
0x140015798  movzx   eax, [rbp+10D0h+var_10F8]
0x14001579c  mov     [rbp+10D0h+var_10E0], rax
0x1400157a0  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1400157a4  mov     [rbp+10D0h+var_10D8], rax
0x1400157a8  movzx   eax, [rbp+10D0h+var_1118]
0x1400157ac  mov     [rbp+10D0h+var_10D0], rax
0x1400157b0  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x1400157b4  mov     [rbp+10D0h+var_10C8], rax
0x1400157b8  mov     rcx, [rbp+10D0h+var_1048]; this
0x1400157bf  test    rcx, rcx
0x1400157c2  jz      loc_14001593D
0x1400157c8  mov     rax, [rcx]
0x1400157cb  lea     rdx, [rsp+11D0h+var_1180]
0x1400157d0  mov     [rsp+11D0h+var_11A8], rdx
0x1400157d5  lea     rdx, [rbp+10D0h+var_10E0]
0x1400157d9  mov     [rsp+11D0h+var_11B0], rdx
0x1400157de  lea     r9, [rbp+10D0h+var_10D8]
0x1400157e2  lea     r8, [rbp+10D0h+var_10D0]
0x1400157e6  lea     rdx, [rbp+10D0h+var_10C8]
0x1400157ea  mov     rax, [rax+20h]
0x1400157ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400157f3  test    al, al
0x1400157f5  jz      short loc_140015870
0x1400157f7  inc     edi
0x1400157f9  cmp     edi, [rbp+10D0h+var_111C]
0x1400157fc  jb      loc_14001577B
0x140015802  mov     r8, [rbx+20h]; unsigned __int8 *
0x140015806  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14001580b  lea     rcx, [rbp+10D0h+var_1120]; this
0x14001580f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140015814  test    al, al
0x140015816  jnz     loc_14001576E
0x14001581c  mov     rcx, [rbp+10D0h+var_1048]
0x140015823  test    rcx, rcx
0x140015826  jz      short loc_140015834
0x140015828  mov     rax, [rcx]
0x14001582b  mov     rax, [rax+18h]
0x14001582f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015834  mov     dil, 1
0x140015837  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x14001583b  jz      short loc_1400158AF
0x14001583d  mov     eax, [rsp+11D0h+var_1188]
0x140015841  mov     rdx, [rsp+11D0h+var_1158]
0x140015846  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14001584a  sub     r8d, edx
0x14001584d  mov     [rsp+11D0h+var_11A0], 1
0x140015855  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x140015859  mov     rcx, r14
0x14001585c  call    wil_details_NtUpdateWnfStateData
0x140015861  cmp     eax, 0C0000001h
0x140015866  jnz     short loc_14001588D
0x140015868  inc     r15
0x14001586b  mov     dil, r13b
0x14001586e  jmp     short loc_1400158BB
0x140015870  mov     rcx, [rbp+10D0h+var_1048]
0x140015877  test    rcx, rcx
0x14001587a  jz      short loc_140015888
0x14001587c  mov     rax, [rcx]
0x14001587f  mov     rax, [rax+18h]
0x140015883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015888  mov     dil, r13b
0x14001588b  jmp     short loc_140015837
0x14001588d  test    eax, eax
0x14001588f  jz      short loc_1400158AF
0x140015891  mov     rdx, [rsp+11D0h+var_1158]
0x140015896  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14001589a  sub     r8d, edx
0x14001589d  mov     [rsp+11D0h+var_11A0], r13d
0x1400158a2  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x1400158a7  mov     rcx, r14
0x1400158aa  call    wil_details_NtUpdateWnfStateData
0x1400158af  add     r14, 8
0x1400158b3  mov     rax, [rbp+10D0h+var_1130]
0x1400158b7  mov     [rbp+10D0h+var_1128], rax
0x1400158bb  mov     rsi, [rbp+10D0h+lpMem]
0x1400158bf  mov     [rbp+10D0h+lpMem], r13
0x1400158c3  test    rsi, rsi
0x1400158c6  jz      short loc_1400158DC
0x1400158c8  call    cs:__imp_GetProcessHeap
0x1400158ce  mov     rcx, rax; hHeap
0x1400158d1  mov     r8, rsi; lpMem
0x1400158d4  xor     edx, edx; dwFlags
0x1400158d6  call    cs:__imp_HeapFree
0x1400158dc  test    dil, dil
0x1400158df  jnz     short loc_140015913
0x1400158e1  cmp     r14, r12
0x1400158e4  jnb     short loc_140015913
0x1400158e6  cmp     r15, 32h ; '2'
0x1400158ea  jb      loc_1400155B6
0x1400158f0  jmp     short loc_140015913
0x1400158f2  mov     rbx, [rbp+10D0h+lpMem]
0x1400158f6  mov     [rbp+10D0h+lpMem], r13
0x1400158fa  test    rbx, rbx
0x1400158fd  jz      short loc_140015913
0x1400158ff  call    cs:__imp_GetProcessHeap
0x140015905  mov     rcx, rax; hHeap
0x140015908  mov     r8, rbx; lpMem
0x14001590b  xor     edx, edx; dwFlags
0x14001590d  call    cs:__imp_HeapFree
0x140015913  mov     rcx, [rbp+10D0h+var_40]
0x14001591a  xor     rcx, rsp; StackCookie
0x14001591d  call    __security_check_cookie
0x140015922  mov     rbx, [rsp+11D0h+arg_8]
0x14001592a  add     rsp, 11A0h
0x140015931  pop     r15
0x140015933  pop     r14
0x140015935  pop     r13
0x140015937  pop     r12
0x140015939  pop     rdi
0x14001593a  pop     rsi
0x14001593b  pop     rbp
0x14001593c  retn
0x14001593d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
