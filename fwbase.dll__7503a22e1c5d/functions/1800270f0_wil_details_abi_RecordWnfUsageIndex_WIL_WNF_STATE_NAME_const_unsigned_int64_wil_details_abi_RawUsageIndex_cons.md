# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800270f0`
- end: `0x1800273a0`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `688`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x1800262a0`

## callees

- `0x18001e1d0`
- `0x180025130`
- `0x180025b50`
- `0x1800270f0`
- `0x180027d50`
- `0x18002a560`
- `0x18002f5f0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800271ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800271ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800271d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800271d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027332`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027370`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027332`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027370`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027324`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027362`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027324`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027362`

## string_xrefs

- `0x1800271d1`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v5; // rsi
  wil::details_abi *v6; // r12
  unsigned __int64 v7; // r15
  char v8; // cl
  unsigned int v9; // edx
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // eax
  wil::details *v15; // rbx
  int v16; // edx
  char v17; // di
  __int64 v18; // r9
  int updated; // eax
  __int64 v20; // r9
  void *v21; // rbx
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  _BYTE *v25; // [rsp+20h] [rbp-E0h]
  _BYTE v26[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v27[14]; // [rsp+48h] [rbp-B8h] BYREF
  int v28; // [rsp+B8h] [rbp-48h] BYREF
  int v29; // [rsp+C0h] [rbp-40h]
  _WORD v30[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v31; // [rsp+D4h] [rbp-2Ch]
  __int16 v32; // [rsp+D6h] [rbp-2Ah]
  char v33; // [rsp+D8h] [rbp-28h]
  __int64 v34; // [rsp+E0h] [rbp-20h]
  __int64 v35; // [rsp+E8h] [rbp-18h]
  __int128 v36; // [rsp+F0h] [rbp-10h]
  LPVOID lpMem; // [rsp+100h] [rbp+0h]
  __int16 v38; // [rsp+108h] [rbp+8h]
  char v39; // [rsp+10Ah] [rbp+Ah]
  __int64 v40; // [rsp+110h] [rbp+10h] BYREF
  __int64 v41; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v42[4096]; // [rsp+120h] [rbp+20h] BYREF

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
        v34 = v9 + 2LL;
      }
      else
      {
        if ( v8 == 2 )
          v10 = v9 + 4LL;
        v34 = v10;
      }
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
    v28 = 0;
    v29 = 4096;
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
      v25 = v42;
      v15 = (wil::details *)((unsigned int (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(
                              v5,
                              0,
                              0,
                              &v28);
      wil::details::NtStatusToHr(v15, v16);
      if ( (_DWORD)v15 )
      {
        v14 = 0;
        v29 = 0;
        v28 = 0;
      }
      else
      {
        v14 = v29;
      }
    }
    else
    {
      wil::details::NtStatusToHr((wil::details *)0xC0000139LL, v13);
      v14 = 0;
      v29 = 0;
      v28 = 0;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v30, v42, v14, 0x1000u);
    if ( HIBYTE(v38) )
      break;
    v40 = 0;
    v27[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v27[1] = &v40;
    v27[2] = &v41;
    v27[3] = v30;
    v27[13] = v27;
    v17 = wil::details_abi::RawUsageIndex::Iterate(a3, v26);
    if ( !(_BYTE)v38 )
      goto LABEL_23;
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v35, (int)v36 - (int)v35, v18, (int)v25, v28, 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v35, v36 - v35, v20, (int)v25, 0, 0);
LABEL_23:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v41 = v40;
      goto LABEL_24;
    }
    ++v7;
    v17 = 0;
LABEL_24:
    v21 = lpMem;
    lpMem = 0;
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
    if ( v17 || v5 >= v6 || v7 >= 0x32 )
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
0x1800270f0  mov     [rsp-8+arg_8], rbx
0x1800270f5  push    rbp
0x1800270f6  push    rsi
0x1800270f7  push    rdi
0x1800270f8  push    r12
0x1800270fa  push    r13
0x1800270fc  push    r14
0x1800270fe  push    r15
0x180027100  lea     rbp, [rsp-1030h]
0x180027108  mov     eax, 1130h
0x18002710d  call    _alloca_probe
0x180027112  sub     rsp, rax
0x180027115  mov     rax, cs:__security_cookie
0x18002711c  xor     rax, rsp
0x18002711f  mov     [rbp+1060h+var_40], rax
0x180027126  mov     r14, r8
0x180027129  mov     rsi, rcx
0x18002712c  lea     r12, [rcx+rdx*8]
0x180027130  xor     r13d, r13d
0x180027133  mov     r15d, r13d
0x180027136  mov     [rbp+1060h+var_1048], r13
0x18002713a  lea     rdi, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180027141  movzx   ecx, byte ptr [r14+8]
0x180027146  movzx   edx, word ptr [r14+6]
0x18002714b  movzx   eax, word ptr [r14]
0x18002714f  mov     [rbp+1060h+var_1090], ax
0x180027153  movzx   eax, word ptr [r14+2]
0x180027158  mov     [rbp+1060h+var_108E], ax
0x18002715c  movzx   eax, byte ptr [r14+4]
0x180027161  mov     [rbp+1060h+var_108C], al
0x180027164  mov     [rbp+1060h+var_108A], dx
0x180027168  mov     [rbp+1060h+var_1088], cl
0x18002716b  test    dx, dx
0x18002716e  jz      short loc_180027190
0x180027170  mov     eax, edx
0x180027172  cmp     cl, 1
0x180027175  jnz     short loc_180027181
0x180027177  add     rax, 2
0x18002717b  mov     [rbp+1060h+var_1080], rax
0x18002717f  jmp     short loc_180027194
0x180027181  cmp     cl, 2
0x180027184  jnz     short loc_18002718A
0x180027186  add     rax, 4
0x18002718a  mov     [rbp+1060h+var_1080], rax
0x18002718e  jmp     short loc_180027194
0x180027190  mov     [rbp+1060h+var_1080], r13
0x180027194  mov     [rbp+1060h+var_1078], r13
0x180027198  xorps   xmm0, xmm0
0x18002719b  movdqa  [rbp+1060h+var_1070], xmm0
0x1800271a0  mov     [rbp+1060h+lpMem], r13
0x1800271a4  mov     [rbp+1060h+var_1058], 0
0x1800271aa  mov     [rbp+1060h+var_1056], 0
0x1800271ae  mov     [rbp+1060h+var_10A8], r13d
0x1800271b2  mov     [rbp+1060h+var_10A0], 1000h
0x1800271b9  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800271c0  test    rax, rax
0x1800271c3  jnz     short loc_180027217
0x1800271c5  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800271cc  test    rax, rax
0x1800271cf  jnz     short loc_1800271E5
0x1800271d1  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800271d8  call    cs:__imp_GetModuleHandleW
0x1800271de  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800271e5  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800271ec  mov     rcx, rax; hModule
0x1800271ef  call    cs:__imp_GetProcAddress
0x1800271f5  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800271fc  test    rax, rax
0x1800271ff  jnz     short loc_180027217
0x180027201  mov     ecx, 0C0000139h; this
0x180027206  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18002720b  mov     eax, r13d
0x18002720e  mov     [rbp+1060h+var_10A0], eax
0x180027211  mov     [rbp+1060h+var_10A8], r13d
0x180027215  jmp     short loc_180027256
0x180027217  lea     rcx, [rbp+1060h+var_10A0]
0x18002721b  mov     [rsp+1160h+var_1138], rcx
0x180027220  lea     rcx, [rbp+1060h+var_1040]
0x180027224  mov     [rsp+1160h+var_1140], rcx
0x180027229  lea     r9, [rbp+1060h+var_10A8]
0x18002722d  xor     r8d, r8d
0x180027230  xor     edx, edx
0x180027232  mov     rcx, rsi
0x180027235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002723a  mov     ebx, eax
0x18002723c  mov     ecx, eax; this
0x18002723e  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180027243  test    ebx, ebx
0x180027245  jz      short loc_180027253
0x180027247  mov     eax, r13d
0x18002724a  mov     [rbp+1060h+var_10A0], eax
0x18002724d  mov     [rbp+1060h+var_10A8], r13d
0x180027251  jmp     short loc_180027256
0x180027253  mov     eax, [rbp+1060h+var_10A0]
0x180027256  mov     r8d, eax; unsigned __int64
0x180027259  mov     r9d, 1000h; unsigned __int64
0x18002725f  lea     rdx, [rbp+1060h+var_1040]; void *
0x180027263  lea     rcx, [rbp+1060h+var_1090]; this
0x180027267  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18002726c  cmp     byte ptr [rbp+1060h+var_1058+1], 0
0x180027270  jnz     loc_180027355
0x180027276  mov     [rbp+1060h+var_1050], r13
0x18002727a  mov     [rsp+1160h+var_1118], rdi
0x18002727f  lea     rax, [rbp+1060h+var_1050]
0x180027283  mov     [rsp+1160h+var_1110], rax
0x180027288  lea     rax, [rbp+1060h+var_1048]
0x18002728c  mov     [rsp+1160h+var_1108], rax
0x180027291  lea     rax, [rbp+1060h+var_1090]
0x180027295  mov     [rsp+1160h+var_1100], rax
0x18002729a  lea     rax, [rsp+1160h+var_1118]
0x18002729f  mov     [rbp+1060h+var_10B0], rax
0x1800272a3  lea     rdx, [rsp+1160h+var_1120]
0x1800272a8  mov     rcx, r14
0x1800272ab  call    ?Iterate@RawUsageIndex@details_abi@wil@@QEBA_NV?$function@$$A6A_NPEAX_K01I@Z@wistd@@@Z; wil::details_abi::RawUsageIndex::Iterate(wistd::function<bool (void *,unsigned __int64,void *,unsigned __int64,uint)>)
0x1800272b0  movzx   edi, al
0x1800272b3  cmp     byte ptr [rbp+1060h+var_1058], 0
0x1800272b7  jz      short loc_18002730B
0x1800272b9  mov     ecx, [rbp+1060h+var_10A8]
0x1800272bc  mov     rdx, [rbp+1060h+var_1078]
0x1800272c0  mov     r8d, dword ptr [rbp+1060h+var_1070]
0x1800272c4  sub     r8d, edx
0x1800272c7  mov     [rsp+1160h+var_1130], 1
0x1800272cf  mov     dword ptr [rsp+1160h+var_1138], ecx
0x1800272d3  mov     rcx, rsi
0x1800272d6  call    wil_details_NtUpdateWnfStateData
0x1800272db  cmp     eax, 0C0000001h
0x1800272e0  jnz     short loc_1800272EA
0x1800272e2  inc     r15
0x1800272e5  xor     dil, dil
0x1800272e8  jmp     short loc_180027317
0x1800272ea  test    eax, eax
0x1800272ec  jz      short loc_18002730B
0x1800272ee  mov     rdx, [rbp+1060h+var_1078]
0x1800272f2  mov     r8d, dword ptr [rbp+1060h+var_1070]
0x1800272f6  sub     r8d, edx
0x1800272f9  mov     [rsp+1160h+var_1130], r13d
0x1800272fe  mov     dword ptr [rsp+1160h+var_1138], r13d
0x180027303  mov     rcx, rsi
0x180027306  call    wil_details_NtUpdateWnfStateData
0x18002730b  add     rsi, 8
0x18002730f  mov     rax, [rbp+1060h+var_1050]
0x180027313  mov     [rbp+1060h+var_1048], rax
0x180027317  mov     rbx, [rbp+1060h+lpMem]
0x18002731b  mov     [rbp+1060h+lpMem], r13
0x18002731f  test    rbx, rbx
0x180027322  jz      short loc_180027338
0x180027324  call    cs:__imp_GetProcessHeap
0x18002732a  mov     rcx, rax; hHeap
0x18002732d  mov     r8, rbx; lpMem
0x180027330  xor     edx, edx; dwFlags
0x180027332  call    cs:__imp_HeapFree
0x180027338  test    dil, dil
0x18002733b  jnz     short loc_180027376
0x18002733d  cmp     rsi, r12
0x180027340  jnb     short loc_180027376
0x180027342  cmp     r15, 32h ; '2'
0x180027346  lea     rdi, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18002734d  jb      loc_180027141
0x180027353  jmp     short loc_180027376
0x180027355  mov     rbx, [rbp+1060h+lpMem]
0x180027359  mov     [rbp+1060h+lpMem], r13
0x18002735d  test    rbx, rbx
0x180027360  jz      short loc_180027376
0x180027362  call    cs:__imp_GetProcessHeap
0x180027368  mov     rcx, rax; hHeap
0x18002736b  mov     r8, rbx; lpMem
0x18002736e  xor     edx, edx; dwFlags
0x180027370  call    cs:__imp_HeapFree
0x180027376  mov     rcx, [rbp+1060h+var_40]
0x18002737d  xor     rcx, rsp; StackCookie
0x180027380  call    __security_check_cookie
0x180027385  mov     rbx, [rsp+1160h+arg_8]
0x18002738d  add     rsp, 1130h
0x180027394  pop     r15
0x180027396  pop     r14
0x180027398  pop     r13
0x18002739a  pop     r12
0x18002739c  pop     rdi
0x18002739d  pop     rsi
0x18002739e  pop     rbp
0x18002739f  retn
```
