# CUrlHistory::_NotifyWS(IHistoryData *,ulong)

- ea: `0x180014cc0`
- end: `0x1800150e5`
- name: `?_NotifyWS@CUrlHistory@@EEAAXPEAUIHistoryData@@K@Z`
- size: `1061`
- prototype: `void __fastcall(CUrlHistory *__hidden this, struct IHistoryData *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180146f00`

## callees

- `0x18000c530`
- `0x180011230`
- `0x18001132c`
- `0x180012338`
- `0x1800125bc`
- `0x1800134e4`
- `0x180014a0c`
- `0x180014cc0`
- `0x180018694`
- `0x1800906d4`
- `0x1804f9c3c`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180014ff1`
- `KERNEL32!GetCurrentProcess` at `0x180014ff1`
- `KERNEL32!LocalFree` at `0x180015068`
- `KERNEL32!LocalFree` at `0x180015068`
- `KERNEL32!GetProcessHeap` at `0x180015019`
- `KERNEL32!GetProcessHeap` at `0x180015077`
- `KERNEL32!GetProcessHeap` at `0x180015019`
- `KERNEL32!GetProcessHeap` at `0x180015077`
- `KERNEL32!CloseHandle` at `0x18001508f`
- `KERNEL32!CloseHandle` at `0x18001508f`
- `KERNEL32!LeaveCriticalSection` at `0x180014fd6`
- `KERNEL32!LeaveCriticalSection` at `0x180014fd6`
- `KERNEL32!EnterCriticalSection` at `0x180014fbe`
- `KERNEL32!EnterCriticalSection` at `0x180014fbe`
- `KERNEL32!HeapFree` at `0x180015085`
- `KERNEL32!HeapFree` at `0x180015085`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenProcessToken` at `0x180015003`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenProcessToken` at `0x180015003`
- `SHELL32!SHBindToObject` at `0x180014dce`
- `SHELL32!SHBindToObject` at `0x180014dce`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180014d90`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180014d90`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180014d42`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180014d42`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180014f56`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180014f56`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180014edd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180014f14`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180014f1e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800150c6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180014edd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180014f14`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180014f1e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800150c6`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180014e75`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180014e75`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertSidToStringSidW` at `0x180015043`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertSidToStringSidW` at `0x180015043`

## pseudocode

```c
void __fastcall CUrlHistory::_NotifyWS(CUrlHistory *this, struct IHistoryData *a2, int a3)
{
  __int64 v3; // rax
  __int64 v7; // rax
  int v8; // ebx
  _QWORD *v9; // r15
  _QWORD *v10; // r12
  __int64 v11; // r13
  LPWSTR v12; // rcx
  LPCITEMIDLIST *v13; // rbx
  HRESULT v14; // eax
  __int64 v15; // r8
  _WORD *v16; // r14
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rsi
  __int64 v20; // rax
  unsigned __int64 v21; // rax
  signed int v22; // ebx
  unsigned __int16 *v23; // rax
  unsigned __int16 *v24; // rdi
  int v25; // eax
  HANDLE CurrentProcess; // rax
  void *v27; // rbx
  HANDLE ProcessHeap; // rax
  int TokenInformation_Heap; // ebx
  void *v30; // rdi
  HANDLE v31; // rax
  LPWSTR StringSid; // [rsp+40h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-21h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-19h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v36; // [rsp+68h] [rbp-1h]
  void **v37; // [rsp+70h] [rbp+7h]
  LPVOID pv[9]; // [rsp+78h] [rbp+Fh] BYREF
  LPWSTR ppwsz; // [rsp+D8h] [rbp+6Fh] BYREF
  LPVOID v40; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = *(_QWORD *)a2;
  v40 = 0;
  if ( (*(int (__fastcall **)(struct IHistoryData *, LPVOID *))(v3 + 80))(a2, &v40) >= 0 )
  {
    v36 = 0;
    v7 = *(_QWORD *)a2;
    *(_OWORD *)pvar = 0;
    if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(v7 + 24))(a2, 9, pvar) < 0 )
      goto LABEL_30;
    if ( !LOWORD(pvar[0]) )
      goto LABEL_30;
    v8 = (int)pvar[1];
    PropVariantClear(pvar);
    if ( (v8 & 0x10000000) == 0 )
      goto LABEL_30;
    v9 = (_QWORD *)(*(__int64 (__fastcall **)(struct IHistoryData *, LPVOID *))(*(_QWORD *)a2 + 96LL))(a2, &lpMem);
    v10 = (_QWORD *)(*(__int64 (__fastcall **)(struct IHistoryData *, void **))(*(_QWORD *)a2 + 112LL))(
                      a2,
                      &TokenHandle);
    v11 = (*(__int64 (__fastcall **)(struct IHistoryData *))(*(_QWORD *)a2 + 72LL))(a2);
    if ( IsProtectedModeProcess() )
    {
      v12 = 0;
      v13 = (LPCITEMIDLIST *)((char *)this + 24);
      ppwsz = 0;
      if ( !*((_QWORD *)this + 3) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
        if ( !*v13 )
          SHGetHistoryPIDL((char *)this + 24);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
        v12 = ppwsz;
      }
      if ( *v13 )
      {
        v14 = SHBindToObject(0, *v13, 0, &GUID_f646011b_e24e_4ed8_85ba_eed288bd6a94, (void **)&ppwsz);
        v12 = ppwsz;
        if ( v14 >= 0 )
        {
          (*(void (__fastcall **)(LPWSTR, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppwsz + 40LL))(
            ppwsz,
            v11,
            *v10,
            *v9,
            0);
          v12 = ppwsz;
        }
      }
      if ( v12 )
        (*(void (__fastcall **)(LPWSTR))(*(_QWORD *)v12 + 16LL))(v12);
    }
    if ( !(unsigned int)IsWSEnabled(0) || (GetEnabledWSProviders(0) & 1) == 0 )
      goto LABEL_30;
    if ( !a3 )
    {
      WSChangeNotifyHistoryItem(1, v40, v15, 0);
      goto LABEL_30;
    }
    v16 = v40;
    *(_OWORD *)pv = 0;
    v37 = &CHistoryProtocolUrl::`vftable';
    ppwsz = 0;
    if ( !word_1806667F0 )
    {
      TokenHandle = 0;
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        v27 = TokenHandle;
        lpMem = 0;
        ProcessHeap = GetProcessHeap();
        TokenInformation_Heap = GetTokenInformation_HeapFree<_TOKEN_USER>(ProcessHeap, v27);
        if ( TokenInformation_Heap >= 0 )
        {
          v30 = lpMem;
          StringSid = 0;
          if ( ConvertSidToStringSidW(*(PSID *)lpMem, &StringSid) )
          {
            TokenInformation_Heap = StringCchCopyW(&word_1806667F0, 0x64u, StringSid);
            LocalFree(StringSid);
          }
          else
          {
            TokenInformation_Heap = HRESULTFromLastErrorError();
          }
          v31 = GetProcessHeap();
          HeapFree(v31, 0, v30);
        }
        CloseHandle(TokenHandle);
      }
      else
      {
        TokenInformation_Heap = HRESULTFromLastErrorError();
      }
      if ( TokenInformation_Heap < 0 )
        goto LABEL_29;
    }
    if ( SHStrDupW(&word_1806667F0, &ppwsz) < 0 )
    {
LABEL_29:
      CoTaskMemFree(pv[0]);
LABEL_30:
      CoTaskMemFree(v40);
      return;
    }
    v17 = -1;
    do
      ++v17;
    while ( ppwsz[v17] );
    v18 = v17 + 16;
    if ( v18 < 0x10 )
      goto LABEL_32;
    v19 = v18;
    if ( v16 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v16[v20] );
      v21 = v18 + v20;
      v19 = -1;
      if ( v21 >= v18 )
        v19 = v21;
      v22 = v21 < v18 ? 0x80070216 : 0;
      if ( v21 < v18 )
        goto LABEL_26;
    }
    if ( is_mul_ok(v19, 2u) )
    {
      v23 = (unsigned __int16 *)CoTaskMemAlloc(2 * v19);
      v24 = v23;
      if ( v23 )
      {
        if ( v16 )
          v25 = StringCchPrintfW(v23, v19, L"%s{%s}/%s", L"iehistory://", ppwsz, v16);
        else
          v25 = StringCchPrintfW(v23, v19, L"%s{%s}/", L"iehistory://", ppwsz);
        v22 = v25;
        if ( v25 < 0 )
        {
          CoTaskMemFree(v24);
        }
        else
        {
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(pv);
          pv[0] = v24;
        }
      }
      else
      {
        v22 = -2147024882;
      }
    }
    else
    {
LABEL_32:
      v22 = -2147024362;
    }
LABEL_26:
    CoTaskMemFree(ppwsz);
    if ( v22 >= 0 )
      WSChangeNotifyMetaData(pv[0], 1, 1, 0, 5, 0);
    goto LABEL_29;
  }
}

```

## disassembly

```asm
0x180014cc0  mov     [rsp-8+arg_0], rbx
0x180014cc5  push    rbp
0x180014cc6  push    rsi
0x180014cc7  push    rdi
0x180014cc8  push    r12
0x180014cca  push    r13
0x180014ccc  push    r14
0x180014cce  push    r15
0x180014cd0  lea     rbp, [rsp-27h]
0x180014cd5  sub     rsp, 90h
0x180014cdc  mov     rax, [rdx]
0x180014cdf  mov     rdi, rdx
0x180014ce2  mov     rsi, rcx
0x180014ce5  lea     rdx, [rbp+57h+arg_18]
0x180014ce9  xor     ebx, ebx
0x180014ceb  mov     rcx, rdi
0x180014cee  mov     r14d, r8d
0x180014cf1  mov     [rbp+57h+arg_18], rbx
0x180014cf5  mov     rax, [rax+50h]
0x180014cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cfe  test    eax, eax
0x180014d00  js      loc_180014F24
0x180014d06  xor     eax, eax
0x180014d08  lea     r8, [rbp+57h+pvar]
0x180014d0c  mov     [rbp+57h+var_58], rax
0x180014d10  lea     edx, [rbx+9]
0x180014d13  mov     rax, [rdi]
0x180014d16  xorps   xmm0, xmm0
0x180014d19  mov     rcx, rdi
0x180014d1c  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180014d20  mov     rax, [rax+18h]
0x180014d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d29  test    eax, eax
0x180014d2b  js      loc_180014F1A
0x180014d31  cmp     word ptr [rbp+57h+pvar], bx
0x180014d35  jz      loc_180014F1A
0x180014d3b  mov     ebx, dword ptr [rbp+57h+pvar+8]
0x180014d3e  lea     rcx, [rbp+57h+pvar]; pvar
0x180014d42  call    cs:__imp_PropVariantClear
0x180014d48  bt      ebx, 1Ch
0x180014d4c  jnb     loc_180014F1A
0x180014d52  mov     rax, [rdi]
0x180014d55  lea     rdx, [rbp+57h+lpMem]
0x180014d59  mov     rcx, rdi
0x180014d5c  mov     rax, [rax+60h]
0x180014d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d65  mov     rcx, [rdi]
0x180014d68  lea     rdx, [rbp+57h+TokenHandle]
0x180014d6c  mov     r15, rax
0x180014d6f  mov     rax, [rcx+70h]
0x180014d73  mov     rcx, rdi
0x180014d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d7b  mov     rcx, [rdi]
0x180014d7e  mov     r12, rax
0x180014d81  mov     rax, [rcx+48h]
0x180014d85  mov     rcx, rdi
0x180014d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d8d  mov     r13, rax
0x180014d90  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x180014d96  test    eax, eax
0x180014d98  jz      loc_180014FE5
0x180014d9e  xor     ecx, ecx
0x180014da0  lea     rbx, [rsi+18h]
0x180014da4  mov     [rbp+57h+ppwsz], rcx
0x180014da8  cmp     [rbx], rcx
0x180014dab  jz      loc_180014FBA
0x180014db1  mov     rdx, [rbx]; pidl
0x180014db4  test    rdx, rdx
0x180014db7  jz      short loc_180014DFF
0x180014db9  lea     rax, [rbp+57h+ppwsz]
0x180014dbd  xor     r8d, r8d; pbc
0x180014dc0  lea     r9, _GUID_f646011b_e24e_4ed8_85ba_eed288bd6a94; riid
0x180014dc7  mov     [rsp+0C0h+ppv], rax; ppv
0x180014dcc  xor     ecx, ecx; psf
0x180014dce  call    cs:__imp_SHBindToObject
0x180014dd4  mov     rcx, [rbp+57h+ppwsz]
0x180014dd8  test    eax, eax
0x180014dda  js      short loc_180014DFF
0x180014ddc  mov     rax, [rcx]
0x180014ddf  mov     rdx, r13
0x180014de2  mov     r9, [r15]
0x180014de5  mov     r8, [r12]
0x180014de9  mov     [rsp+0C0h+ppv], 0
0x180014df2  mov     rax, [rax+28h]
0x180014df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dfb  mov     rcx, [rbp+57h+ppwsz]
0x180014dff  xor     r15d, r15d
0x180014e02  test    rcx, rcx
0x180014e05  jz      short loc_180014E13
0x180014e07  mov     rax, [rcx]
0x180014e0a  mov     rax, [rax+10h]
0x180014e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e13  xor     ecx, ecx; int
0x180014e15  call    ?IsWSEnabled@@YAHH@Z; IsWSEnabled(int)
0x180014e1a  test    eax, eax
0x180014e1c  jz      loc_180014F1A
0x180014e22  xor     ecx, ecx; int
0x180014e24  call    ?GetEnabledWSProviders@@YAKH@Z; GetEnabledWSProviders(int)
0x180014e29  mov     r12d, 1
0x180014e2f  test    r12b, al
0x180014e32  jz      loc_180014F1A
0x180014e38  test    r14d, r14d
0x180014e3b  jz      loc_1800150D1
0x180014e41  cmp     cs:word_1806667F0, r15w
0x180014e49  lea     rax, ??_7CHistoryProtocolUrl@@6B@; const CHistoryProtocolUrl::`vftable'
0x180014e50  mov     r14, [rbp+57h+arg_18]
0x180014e54  xorps   xmm0, xmm0
0x180014e57  movdqu  xmmword ptr [rbp+57h+pv], xmm0
0x180014e5c  mov     [rbp+57h+var_50], rax
0x180014e60  mov     [rbp+57h+ppwsz], r15
0x180014e64  jz      loc_180014FED
0x180014e6a  lea     rdx, [rbp+57h+ppwsz]; ppwsz
0x180014e6e  lea     rcx, word_1806667F0; psz
0x180014e75  call    cs:__imp_SHStrDupW
0x180014e7b  test    eax, eax
0x180014e7d  js      loc_180014F10
0x180014e83  mov     rax, [rbp+57h+ppwsz]
0x180014e87  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180014e8b  mov     rcx, rdx
0x180014e8e  inc     rcx
0x180014e91  cmp     [rax+rcx*2], r15w
0x180014e96  jnz     short loc_180014E8E
0x180014e98  add     rcx, 10h
0x180014e9c  cmp     rcx, 10h
0x180014ea0  jb      loc_180014F3F
0x180014ea6  mov     rsi, rcx
0x180014ea9  test    r14, r14
0x180014eac  jz      loc_180014F46
0x180014eb2  mov     rax, rdx
0x180014eb5  inc     rax
0x180014eb8  cmp     [r14+rax*2], r15w
0x180014ebd  jnz     short loc_180014EB5
0x180014ebf  add     rax, rcx
0x180014ec2  mov     rsi, rdx
0x180014ec5  cmp     rax, rcx
0x180014ec8  cmovnb  rsi, rax
0x180014ecc  sbb     ebx, ebx
0x180014ece  and     ebx, 80070216h
0x180014ed4  cmp     rax, rcx
0x180014ed7  jnb     short loc_180014F46
0x180014ed9  mov     rcx, [rbp+57h+ppwsz]; pv
0x180014edd  call    cs:__imp_CoTaskMemFree
0x180014ee3  test    ebx, ebx
0x180014ee5  js      short loc_180014F10
0x180014ee7  mov     rcx, [rbp+57h+pv]
0x180014eeb  xor     r9d, r9d
0x180014eee  mov     dword ptr [rsp+0C0h+var_98], r15d
0x180014ef3  mov     r8d, r12d
0x180014ef6  mov     edx, r12d
0x180014ef9  mov     dword ptr [rsp+0C0h+ppv], 5
0x180014f01  call    ?WSChangeNotifyMetaData@@YAJPEBGIW4tagWSMETADATAACTION@@I1HH@Z; WSChangeNotifyMetaData(ushort const *,uint,tagWSMETADATAACTION,uint,tagWSMETADATAACTION,int,int)
0x180014f06  jmp     short loc_180014F10
0x180014f08  test    ebx, ebx
0x180014f0a  jns     loc_180014E6A
0x180014f10  mov     rcx, [rbp+57h+pv]; pv
0x180014f14  call    cs:__imp_CoTaskMemFree
0x180014f1a  mov     rcx, [rbp+57h+arg_18]; pv
0x180014f1e  call    cs:__imp_CoTaskMemFree
0x180014f24  mov     rbx, [rsp+0C0h+arg_0]
0x180014f2c  add     rsp, 90h
0x180014f33  pop     r15
0x180014f35  pop     r14
0x180014f37  pop     r13
0x180014f39  pop     r12
0x180014f3b  pop     rdi
0x180014f3c  pop     rsi
0x180014f3d  pop     rbp
0x180014f3e  retn
0x180014f3f  mov     ebx, 80070216h
0x180014f44  jmp     short loc_180014ED9
0x180014f46  mov     eax, 2
0x180014f4b  mul     rsi
0x180014f4e  test    rdx, rdx
0x180014f51  jnz     short loc_180014F3F
0x180014f53  mov     rcx, rax; cb
0x180014f56  call    cs:__imp_CoTaskMemAlloc
0x180014f5c  mov     rdi, rax
0x180014f5f  test    rax, rax
0x180014f62  jz      short loc_180014FB0
0x180014f64  lea     r9, aIehistory_0; "iehistory://"
0x180014f6b  mov     rdx, rsi; unsigned __int64
0x180014f6e  test    r14, r14
0x180014f71  jz      loc_1800150A6
0x180014f77  mov     rcx, [rbp+57h+ppwsz]
0x180014f7b  lea     r8, aSSS_4; "%s{%s}/%s"
0x180014f82  mov     [rsp+0C0h+var_98], r14
0x180014f87  mov     [rsp+0C0h+ppv], rcx
0x180014f8c  mov     rcx, rax; unsigned __int16 *
0x180014f8f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014f94  mov     ebx, eax
0x180014f96  test    eax, eax
0x180014f98  js      loc_1800150C3
0x180014f9e  lea     rcx, [rbp+57h+pv]
0x180014fa2  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180014fa7  mov     [rbp+57h+pv], rdi
0x180014fab  jmp     loc_180014ED9
0x180014fb0  mov     ebx, 8007000Eh
0x180014fb5  jmp     loc_180014ED9
0x180014fba  lea     rcx, [rsi+20h]; lpCriticalSection
0x180014fbe  call    cs:__imp_EnterCriticalSection
0x180014fc4  cmp     qword ptr [rbx], 0
0x180014fc8  jnz     short loc_180014FD2
0x180014fca  mov     rcx, rbx
0x180014fcd  call    SHGetHistoryPIDL
0x180014fd2  lea     rcx, [rsi+20h]; lpCriticalSection
0x180014fd6  call    cs:__imp_LeaveCriticalSection
0x180014fdc  mov     rcx, [rbp+57h+ppwsz]
0x180014fe0  jmp     loc_180014DB1
0x180014fe5  xor     r15d, r15d
0x180014fe8  jmp     loc_180014E13
0x180014fed  mov     [rbp+57h+TokenHandle], r15
0x180014ff1  call    cs:__imp_GetCurrentProcess
0x180014ff7  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180014ffb  mov     edx, 8; DesiredAccess
0x180015000  mov     rcx, rax; ProcessHandle
0x180015003  call    cs:__imp_OpenProcessToken
0x180015009  test    eax, eax
0x18001500b  jz      loc_18001509A
0x180015011  mov     rbx, [rbp+57h+TokenHandle]
0x180015015  mov     [rbp+57h+lpMem], r15
0x180015019  call    cs:__imp_GetProcessHeap
0x18001501f  lea     r9, [rbp+57h+lpMem]
0x180015023  mov     rdx, rbx; TokenHandle
0x180015026  mov     rcx, rax; hHeap
0x180015029  call    ??$GetTokenInformation_HeapFree@U_TOKEN_USER@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_USER@@@Z; GetTokenInformation_HeapFree<_TOKEN_USER>(void *,void *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER * *)
0x18001502e  mov     ebx, eax
0x180015030  test    eax, eax
0x180015032  js      short loc_18001508B
0x180015034  mov     rdi, [rbp+57h+lpMem]
0x180015038  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18001503c  mov     [rbp+57h+StringSid], r15
0x180015040  mov     rcx, [rdi]; Sid
0x180015043  call    cs:__imp_ConvertSidToStringSidW
0x180015049  test    eax, eax
0x18001504b  jz      short loc_180015070
0x18001504d  mov     r8, [rbp+57h+StringSid]; unsigned __int16 *
0x180015051  lea     rcx, word_1806667F0; unsigned __int16 *
0x180015058  mov     edx, 64h ; 'd'; unsigned __int64
0x18001505d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015062  mov     rcx, [rbp+57h+StringSid]; hMem
0x180015066  mov     ebx, eax
0x180015068  call    cs:__imp_LocalFree
0x18001506e  jmp     short loc_180015077
0x180015070  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180015075  mov     ebx, eax
0x180015077  call    cs:__imp_GetProcessHeap
0x18001507d  mov     r8, rdi; lpMem
0x180015080  xor     edx, edx; dwFlags
0x180015082  mov     rcx, rax; hHeap
0x180015085  call    cs:__imp_HeapFree
0x18001508b  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001508f  call    cs:__imp_CloseHandle
0x180015095  jmp     loc_180014F08
0x18001509a  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18001509f  mov     ebx, eax
0x1800150a1  jmp     loc_180014F08
0x1800150a6  mov     rax, [rbp+57h+ppwsz]
0x1800150aa  lea     r8, aSS_20; "%s{%s}/"
0x1800150b1  mov     rcx, rdi; unsigned __int16 *
0x1800150b4  mov     [rsp+0C0h+ppv], rax
0x1800150b9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800150be  jmp     loc_180014F94
0x1800150c3  mov     rcx, rdi; pv
0x1800150c6  call    cs:__imp_CoTaskMemFree
0x1800150cc  jmp     loc_180014ED9
0x1800150d1  mov     rdx, [rbp+57h+arg_18]
0x1800150d5  xor     r9d, r9d
0x1800150d8  mov     ecx, r12d
0x1800150db  call    ?WSChangeNotifyHistoryItem@@YAJW4tagWSCHANGENOTIFYACTION@@PEBGHH@Z; WSChangeNotifyHistoryItem(tagWSCHANGENOTIFYACTION,ushort const *,int,int)
0x1800150e0  jmp     loc_180014F1A
```
