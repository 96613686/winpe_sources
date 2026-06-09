# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x140016078`
- end: `0x140016445`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1400157ac`

## callees

- `0x140015368`
- `0x1400156bc`
- `0x140016078`
- `0x140016a3c`
- `0x1400176cc`
- `0x140017a60`
- `0x140018350`
- `0x1400183e0`
- `0x140019010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400163d9`
- `KERNEL32!HeapFree` at `0x14001640f`
- `KERNEL32!HeapFree` at `0x1400163d9`
- `KERNEL32!HeapFree` at `0x14001640f`
- `KERNEL32!GetProcessHeap` at `0x1400163cb`
- `KERNEL32!GetProcessHeap` at `0x140016401`
- `KERNEL32!GetProcessHeap` at `0x1400163cb`
- `KERNEL32!GetProcessHeap` at `0x140016401`
- `KERNEL32!GetProcAddress` at `0x14001616e`
- `KERNEL32!GetProcAddress` at `0x14001616e`
- `KERNEL32!GetModuleHandleW` at `0x140016157`
- `KERNEL32!GetModuleHandleW` at `0x140016157`

## string_xrefs

- `0x140016150`: `ntdll.dll`

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
0x140016078  mov     [rsp-8+arg_8], rbx
0x14001607d  push    rbp
0x14001607e  push    rsi
0x14001607f  push    rdi
0x140016080  push    r12
0x140016082  push    r13
0x140016084  push    r14
0x140016086  push    r15
0x140016088  lea     rbp, [rsp-10A0h]
0x140016090  mov     eax, 11A0h
0x140016095  call    _alloca_probe
0x14001609a  sub     rsp, rax
0x14001609d  mov     rax, cs:__security_cookie
0x1400160a4  xor     rax, rsp
0x1400160a7  mov     [rbp+10D0h+var_40], rax
0x1400160ae  xor     r13d, r13d
0x1400160b1  lea     r12, [rcx+rdx*8]
0x1400160b5  mov     r15d, r13d
0x1400160b8  mov     [rbp+10D0h+var_1128], r13
0x1400160bc  mov     rdi, r8
0x1400160bf  mov     r14, rcx
0x1400160c2  movzx   eax, word ptr [rdi]
0x1400160c5  movzx   edx, word ptr [rdi+6]
0x1400160c9  mov     cl, [rdi+8]
0x1400160cc  mov     [rsp+11D0h+var_1170], ax
0x1400160d1  movzx   eax, word ptr [rdi+2]
0x1400160d5  mov     [rsp+11D0h+var_116E], ax
0x1400160da  mov     al, [rdi+4]
0x1400160dd  mov     [rsp+11D0h+var_116C], al
0x1400160e1  mov     [rsp+11D0h+var_116A], dx
0x1400160e6  mov     [rsp+11D0h+var_1168], cl
0x1400160ea  test    dx, dx
0x1400160ed  jz      short loc_14001610C
0x1400160ef  mov     eax, edx
0x1400160f1  cmp     cl, 1
0x1400160f4  jnz     short loc_1400160FC
0x1400160f6  add     rax, 2
0x1400160fa  jmp     short loc_140016105
0x1400160fc  cmp     cl, 2
0x1400160ff  jnz     short loc_140016105
0x140016101  add     rax, 4
0x140016105  mov     [rsp+11D0h+var_1160], rax
0x14001610a  jmp     short loc_140016111
0x14001610c  mov     [rsp+11D0h+var_1160], r13
0x140016111  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140016118  xorps   xmm0, xmm0
0x14001611b  mov     [rsp+11D0h+var_1158], r13
0x140016120  movdqa  [rbp+10D0h+var_1150], xmm0
0x140016125  mov     [rbp+10D0h+lpMem], r13
0x140016129  mov     [rbp+10D0h+var_1138], r13w
0x14001612e  mov     [rbp+10D0h+var_1136], r13b
0x140016132  mov     [rsp+11D0h+var_1188], r13d
0x140016137  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x14001613f  test    rax, rax
0x140016142  jnz     short loc_140016187
0x140016144  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001614b  test    rax, rax
0x14001614e  jnz     short loc_140016164
0x140016150  lea     rcx, ModuleName; "ntdll.dll"
0x140016157  call    cs:__imp_GetModuleHandleW
0x14001615d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016164  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14001616b  mov     rcx, rax; hModule
0x14001616e  call    cs:__imp_GetProcAddress
0x140016174  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14001617b  test    rax, rax
0x14001617e  jnz     short loc_140016187
0x140016180  mov     ebx, 0C0000139h
0x140016185  jmp     short loc_1400161B1
0x140016187  lea     rcx, [rsp+11D0h+var_1190]
0x14001618c  xor     r8d, r8d
0x14001618f  mov     [rsp+11D0h+var_11A8], rcx
0x140016194  lea     r9, [rsp+11D0h+var_1188]
0x140016199  lea     rcx, [rbp+10D0h+var_1040]
0x1400161a0  xor     edx, edx
0x1400161a2  mov     [rsp+11D0h+var_11B0], rcx
0x1400161a7  mov     rcx, r14
0x1400161aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400161af  mov     ebx, eax
0x1400161b1  mov     ecx, ebx; this
0x1400161b3  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1400161b8  test    ebx, ebx
0x1400161ba  jz      short loc_1400161CA
0x1400161bc  mov     eax, r13d
0x1400161bf  mov     [rsp+11D0h+var_1188], r13d
0x1400161c4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x1400161c8  jmp     short loc_1400161CE
0x1400161ca  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x1400161ce  mov     r8d, eax; unsigned __int64
0x1400161d1  lea     rdx, [rbp+10D0h+var_1040]; void *
0x1400161d8  mov     r9d, 1000h; unsigned __int64
0x1400161de  lea     rcx, [rsp+11D0h+var_1170]; this
0x1400161e3  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1400161e8  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x1400161ec  jnz     loc_1400163F4
0x1400161f2  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1400161f9  mov     [rbp+10D0h+var_1130], r13
0x1400161fd  mov     [rbp+10D0h+var_10B8], rax
0x140016201  xorps   xmm0, xmm0
0x140016204  lea     rax, [rbp+10D0h+var_1130]
0x140016208  mov     [rbp+10D0h+var_111C], r13d
0x14001620c  mov     [rbp+10D0h+var_10B0], rax
0x140016210  lea     rax, [rbp+10D0h+var_1128]
0x140016214  mov     [rbp+10D0h+var_10A8], rax
0x140016218  lea     rax, [rsp+11D0h+var_1170]
0x14001621d  mov     [rbp+10D0h+var_10A0], rax
0x140016221  lea     rax, [rbp+10D0h+var_10B8]
0x140016225  mov     [rbp+10D0h+var_1050], rax
0x14001622c  mov     rax, [rdi+18h]
0x140016230  add     rax, 0Ah
0x140016234  mov     [rbp+10D0h+var_1118], r13w
0x140016239  mov     [rsp+11D0h+var_1190], rax
0x14001623e  movzx   eax, word ptr [rdi+2]
0x140016242  mov     [rbp+10D0h+var_1120], ax
0x140016246  mov     al, [rdi+4]
0x140016249  mov     [rbp+10D0h+var_111E], al
0x14001624c  movzx   eax, word ptr [rdi+6]
0x140016250  mov     [rbp+10D0h+var_1100], ax
0x140016254  mov     al, [rdi+8]
0x140016257  mov     [rbp+10D0h+var_10FE], al
0x14001625a  movdqu  [rbp+10D0h+var_1110], xmm0
0x14001625f  mov     [rbp+10D0h+var_10FC], r13d
0x140016263  mov     [rbp+10D0h+var_10F8], r13w
0x140016268  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14001626d  jmp     loc_140016306
0x140016272  mov     ebx, r13d
0x140016275  cmp     [rbp+10D0h+var_111C], r13d
0x140016279  jbe     loc_140016306
0x14001627f  mov     r8, [rdi+20h]; unsigned __int8 *
0x140016283  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x140016288  lea     rcx, [rbp+10D0h+var_1100]; this
0x14001628c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140016291  test    al, al
0x140016293  jz      short loc_140016306
0x140016295  mov     eax, [rbp+10D0h+var_10FC]
0x140016298  mov     rcx, [rbp+10D0h+var_1050]; this
0x14001629f  mov     [rsp+11D0h+var_1180], eax
0x1400162a3  movzx   eax, [rbp+10D0h+var_10F8]
0x1400162a7  mov     [rbp+10D0h+var_10E0], rax
0x1400162ab  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1400162af  mov     [rbp+10D0h+var_10D8], rax
0x1400162b3  movzx   eax, [rbp+10D0h+var_1118]
0x1400162b7  mov     [rbp+10D0h+var_10D0], rax
0x1400162bb  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x1400162bf  mov     [rbp+10D0h+var_10C8], rax
0x1400162c3  test    rcx, rcx
0x1400162c6  jz      loc_14001643F
0x1400162cc  mov     rax, [rcx]
0x1400162cf  lea     rdx, [rsp+11D0h+var_1180]
0x1400162d4  mov     [rsp+11D0h+var_11A8], rdx
0x1400162d9  lea     r9, [rbp+10D0h+var_10D8]
0x1400162dd  lea     rdx, [rbp+10D0h+var_10E0]
0x1400162e1  mov     [rsp+11D0h+var_11B0], rdx
0x1400162e6  lea     r8, [rbp+10D0h+var_10D0]
0x1400162ea  mov     rax, [rax+20h]
0x1400162ee  lea     rdx, [rbp+10D0h+var_10C8]
0x1400162f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400162f7  test    al, al
0x1400162f9  jz      short loc_140016373
0x1400162fb  inc     ebx
0x1400162fd  cmp     ebx, [rbp+10D0h+var_111C]
0x140016300  jb      loc_14001627F
0x140016306  mov     r8, [rdi+20h]; unsigned __int8 *
0x14001630a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14001630f  lea     rcx, [rbp+10D0h+var_1120]; this
0x140016313  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140016318  test    al, al
0x14001631a  jnz     loc_140016272
0x140016320  mov     rcx, [rbp+10D0h+var_1050]
0x140016327  test    rcx, rcx
0x14001632a  jz      short loc_140016338
0x14001632c  mov     rax, [rcx]
0x14001632f  mov     rax, [rax+18h]
0x140016333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016338  mov     bl, 1
0x14001633a  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x14001633e  jz      short loc_1400163B2
0x140016340  mov     rdx, [rsp+11D0h+var_1158]
0x140016345  mov     rcx, r14
0x140016348  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14001634c  mov     eax, [rsp+11D0h+var_1188]
0x140016350  sub     r8d, edx
0x140016353  mov     [rsp+11D0h+var_11A0], 1
0x14001635b  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x14001635f  call    wil_details_NtUpdateWnfStateData
0x140016364  cmp     eax, 0C0000001h
0x140016369  jnz     short loc_140016390
0x14001636b  inc     r15
0x14001636e  mov     bl, r13b
0x140016371  jmp     short loc_1400163BE
0x140016373  mov     rcx, [rbp+10D0h+var_1050]
0x14001637a  test    rcx, rcx
0x14001637d  jz      short loc_14001638B
0x14001637f  mov     rax, [rcx]
0x140016382  mov     rax, [rax+18h]
0x140016386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001638b  mov     bl, r13b
0x14001638e  jmp     short loc_14001633A
0x140016390  test    eax, eax
0x140016392  jz      short loc_1400163B2
0x140016394  mov     rdx, [rsp+11D0h+var_1158]
0x140016399  mov     rcx, r14
0x14001639c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1400163a0  sub     r8d, edx
0x1400163a3  mov     [rsp+11D0h+var_11A0], r13d
0x1400163a8  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x1400163ad  call    wil_details_NtUpdateWnfStateData
0x1400163b2  mov     rax, [rbp+10D0h+var_1130]
0x1400163b6  add     r14, 8
0x1400163ba  mov     [rbp+10D0h+var_1128], rax
0x1400163be  mov     rsi, [rbp+10D0h+lpMem]
0x1400163c2  mov     [rbp+10D0h+lpMem], r13
0x1400163c6  test    rsi, rsi
0x1400163c9  jz      short loc_1400163DF
0x1400163cb  call    cs:__imp_GetProcessHeap
0x1400163d1  mov     r8, rsi; lpMem
0x1400163d4  xor     edx, edx; dwFlags
0x1400163d6  mov     rcx, rax; hHeap
0x1400163d9  call    cs:__imp_HeapFree
0x1400163df  test    bl, bl
0x1400163e1  jnz     short loc_140016415
0x1400163e3  cmp     r14, r12
0x1400163e6  jnb     short loc_140016415
0x1400163e8  cmp     r15, 32h ; '2'
0x1400163ec  jb      loc_1400160C2
0x1400163f2  jmp     short loc_140016415
0x1400163f4  mov     rbx, [rbp+10D0h+lpMem]
0x1400163f8  mov     [rbp+10D0h+lpMem], r13
0x1400163fc  test    rbx, rbx
0x1400163ff  jz      short loc_140016415
0x140016401  call    cs:__imp_GetProcessHeap
0x140016407  mov     r8, rbx; lpMem
0x14001640a  xor     edx, edx; dwFlags
0x14001640c  mov     rcx, rax; hHeap
0x14001640f  call    cs:__imp_HeapFree
0x140016415  mov     rcx, [rbp+10D0h+var_40]
0x14001641c  xor     rcx, rsp; StackCookie
0x14001641f  call    __security_check_cookie
0x140016424  mov     rbx, [rsp+11D0h+arg_8]
0x14001642c  add     rsp, 11A0h
0x140016433  pop     r15
0x140016435  pop     r14
0x140016437  pop     r13
0x140016439  pop     r12
0x14001643b  pop     rdi
0x14001643c  pop     rsi
0x14001643d  pop     rbp
0x14001643e  retn
0x14001643f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
