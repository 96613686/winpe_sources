# CPersistErrorCache::AddError(long,ulong,IErrorInfo *)

- ea: `0x180015988`
- end: `0x180015e8b`
- name: `?AddError@CPersistErrorCache@@AEAAXJKPEAUIErrorInfo@@@Z`
- size: `1283`
- prototype: `void(CPersistErrorCache *__hidden this, int, unsigned int, struct IErrorInfo *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015e94`
- `0x180016128`

## callees

- `0x180001dd4`
- `0x180002770`
- `0x1800028b8`
- `0x18001588c`
- `0x180015988`
- `0x180017170`
- `0x18001b008`
- `0x18002dca4`
- `0x18002f0e0`
- `0x180031010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180015a2c`
- `ole32!CoCreateInstance` at `0x180015b67`
- `ole32!CoCreateInstance` at `0x180015a2c`
- `ole32!CoCreateInstance` at `0x180015b67`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CPersistErrorCache::AddError(
        CPersistErrorCache *this,
        unsigned int a2,
        unsigned int a3,
        struct IErrorInfo *a4)
{
  _QWORD *v7; // r14
  void (__fastcall ***v8)(_QWORD, GUID *, LPVOID *); // rcx
  HRESULT v9; // eax
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  HRESULT v13; // eax
  int v14; // ebx
  int v15; // eax
  int v16; // ebx
  unsigned int i; // r14d
  int v18; // ebx
  int v19; // ebx
  CPersistErrorInfo *v20; // rbx
  unsigned int v21; // edx
  CPersistErrorInfo *v22; // rax
  CPersistErrorInfo *v23; // rsi
  __int64 v24; // rcx
  int v25; // ebx
  LPVOID v26; // [rsp+40h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-41h] BYREF
  unsigned int v28; // [rsp+50h] [rbp-39h] BYREF
  CPersistErrorInfo *v29; // [rsp+58h] [rbp-31h] BYREF
  CPersistErrorInfo *v30; // [rsp+60h] [rbp-29h] BYREF
  __int64 v31; // [rsp+68h] [rbp-21h] BYREF
  _OWORD v32[3]; // [rsp+70h] [rbp-19h] BYREF

  memset(v32, 0, 44);
  v28 = 1;
  v26 = 0;
  ppv = 0;
  if ( a4 )
  {
    v7 = (_QWORD *)((char *)this + 8);
    v8 = (void (__fastcall ***)(_QWORD, GUID *, LPVOID *))*((_QWORD *)this + 1);
    if ( v8 )
    {
      (**v8)(v8, &IID_IErrorRecords, &ppv);
    }
    else
    {
      if ( ((__int64 (__fastcall *)(struct IErrorInfo *, GUID *, LPVOID *))a4->lpVtbl->QueryInterface)(
             a4,
             &IID_IErrorRecords,
             &ppv) >= 0 )
      {
        *v7 = a4;
        ((void (__fastcall *)(struct IErrorInfo *))a4->lpVtbl->AddRef)(a4);
        goto LABEL_15;
      }
      v9 = CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorRecords, &ppv);
      v10 = v9;
      if ( v9 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_180049A50[0] )
            bidTraceW(off_1800491E8[0], 455680, off_180049A50[0], (unsigned int)v9, 445);
        }
        ThrowHR(v10);
      }
      v11 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, _QWORD *))ppv)(ppv, &IID_IErrorInfo, v7);
      v12 = v11;
      if ( v11 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A48[0] )
          bidTraceW(off_1800491E8[0], 459776, off_180049A48[0], (unsigned int)v11, 449);
        ThrowHR(v12);
      }
    }
    if ( ((__int64 (__fastcall *)(struct IErrorInfo *, GUID *, LPVOID *))a4->lpVtbl->QueryInterface)(
           a4,
           &IID_IErrorRecords,
           &v26) < 0 )
    {
      v13 = CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorRecords, &v26);
      v14 = v13;
      if ( v13 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A40[0] )
          bidTraceW(off_1800491E8[0], 484352, off_180049A40[0], (unsigned int)v13, 473);
        ThrowHR(v14);
      }
      *(GUID *)((char *)v32 + 8) = CLSID_MSPersist;
      *(_QWORD *)&v32[0] = __PAIR64__(a3, a2);
      memset((char *)&v32[1] + 8, 0, 20);
      v15 = (*(__int64 (__fastcall **)(LPVOID, _OWORD *, _QWORD, _QWORD, struct IErrorInfo *, _DWORD))(*(_QWORD *)v26 + 24LL))(
              v26,
              v32,
              0,
              0,
              a4,
              0);
      v16 = v15;
      if ( v15 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A38[0] )
          bidTraceW(off_1800491E8[0], 495616, off_180049A38[0], (unsigned int)v15, 484);
        ThrowHR(v16);
      }
    }
    (*(void (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)v26 + 64LL))(v26, &v28);
    for ( i = 0; i < v28; ++i )
    {
      v31 = 0;
      v29 = 0;
      v30 = 0;
      v18 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _OWORD *))(*(_QWORD *)v26 + 32LL))(v26, i, v32);
      if ( v18 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A30[0] )
          bidTraceW(off_1800491E8[0], 507904, off_180049A30[0], (unsigned int)v18, 496);
        ThrowHR(v18);
      }
      v19 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, CPersistErrorInfo **))(*(_QWORD *)v26 + 40LL))(
              v26,
              i,
              &IID_IUnknown,
              &v29);
      if ( v19 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A28[0] )
          bidTraceW(off_1800491E8[0], 509952, off_180049A28[0], (unsigned int)v19, 498);
        ThrowHR(v19);
      }
      v20 = v29;
      if ( v29 )
      {
        if ( (**(int (__fastcall ***)(CPersistErrorInfo *, GUID *, __int64 *))v29)(v29, &IID_IErrorInfo, &v31) >= 0 )
        {
          v20 = v29;
        }
        else
        {
          v22 = (CPersistErrorInfo *)MMMAlloc(0x48u, v21);
          v30 = v22;
          if ( v22 )
            v20 = CPersistErrorInfo::CPersistErrorInfo(v22);
          else
            v20 = 0;
          v30 = v20;
          OnNullThrowOOM(v20);
          CPersistErrorInfo::SetErrorInfo(v20, a4);
          v23 = v29;
          v24 = *((_QWORD *)v20 + 2);
          if ( v24 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          *((_QWORD *)v20 + 2) = v23;
          if ( v23 )
            (*(void (__fastcall **)(CPersistErrorInfo *))(*(_QWORD *)v23 + 8LL))(v23);
        }
      }
      v25 = (*(__int64 (__fastcall **)(LPVOID, _OWORD *, _QWORD, _QWORD, CPersistErrorInfo *, _DWORD))(*(_QWORD *)ppv + 24LL))(
              ppv,
              v32,
              v20 == 0 ? 0x10000000 : 0,
              0,
              v20,
              0);
      if ( v25 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A20[0] )
          bidTraceW(off_1800491E8[0], 525312, off_180049A20[0], (unsigned int)v25, 513);
        ThrowHR(v25);
      }
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v30);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v29);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v31);
    }
  }
LABEL_15:
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&ppv);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v26);
}

```

## disassembly

```asm
0x180015988  push    rbp
0x18001598a  push    rbx
0x18001598b  push    rsi
0x18001598c  push    rdi
0x18001598d  push    r12
0x18001598f  push    r14
0x180015991  push    r15
0x180015993  lea     rbp, [rsp-27h]
0x180015998  sub     rsp, 0B0h
0x18001599f  mov     rax, cs:__security_cookie
0x1800159a6  xor     rax, rsp
0x1800159a9  mov     [rbp+57h+var_40], rax
0x1800159ad  mov     rdi, r9
0x1800159b0  mov     r12d, r8d
0x1800159b3  mov     r15d, edx
0x1800159b6  xorps   xmm0, xmm0
0x1800159b9  xor     eax, eax
0x1800159bb  movups  [rbp+57h+var_70], xmm0
0x1800159bf  movups  [rbp+57h+var_60], xmm0
0x1800159c3  movups  [rbp+57h+var_60+0Ch], xmm0
0x1800159c7  mov     [rbp+57h+var_90], 1
0x1800159ce  mov     [rbp+57h+var_A0], rax
0x1800159d2  mov     [rbp+57h+var_98], rax
0x1800159d6  test    r9, r9
0x1800159d9  jz      loc_180015AF4
0x1800159df  lea     r14, [rcx+8]
0x1800159e3  mov     rcx, [r14]
0x1800159e6  lea     r8, [rbp+57h+var_98]
0x1800159ea  lea     rsi, IID_IErrorRecords
0x1800159f1  mov     rdx, rsi
0x1800159f4  test    rcx, rcx
0x1800159f7  jnz     loc_180015B26
0x1800159fd  mov     rax, [r9]
0x180015a00  mov     rcx, r9
0x180015a03  mov     rax, [rax]
0x180015a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a0b  test    eax, eax
0x180015a0d  jns     loc_180015AE1
0x180015a13  lea     rax, [rbp+57h+var_98]
0x180015a17  mov     [rsp+0E0h+ppv], rax; ppv
0x180015a1c  mov     r9, rsi; riid
0x180015a1f  xor     edx, edx; pUnkOuter
0x180015a21  lea     r8d, [rdx+1]; dwClsContext
0x180015a25  lea     rcx, CLSID_EXTENDEDERRORINFO; rclsid
0x180015a2c  call    cs:__imp_CoCreateInstance
0x180015a33  nop     dword ptr [rax+rax+00h]
0x180015a38  mov     ebx, eax
0x180015a3a  test    eax, eax
0x180015a3c  jns     short loc_180015A7E
0x180015a3e  test    byte ptr cs:_bidGblFlags, 2
0x180015a45  jz      short loc_180015A76
0x180015a47  mov     rcx, cs:off_180049A50; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015a4e  test    rcx, rcx
0x180015a51  jz      short loc_180015A76
0x180015a53  mov     dword ptr [rsp+0E0h+ppv], 1BDh
0x180015a5b  mov     r9d, eax
0x180015a5e  mov     r8, cs:off_180049A50; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015a65  mov     edx, 6F400h
0x180015a6a  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015a71  call    _bidTraceW
0x180015a76  mov     ecx, ebx; int
0x180015a78  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015a7e  mov     rcx, [rbp+57h+var_98]
0x180015a82  mov     rax, [rcx]
0x180015a85  mov     r8, r14
0x180015a88  lea     rdx, IID_IErrorInfo
0x180015a8f  mov     rax, [rax]
0x180015a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a97  mov     ebx, eax
0x180015a99  test    eax, eax
0x180015a9b  jns     loc_180015B31
0x180015aa1  test    byte ptr cs:_bidGblFlags, 2
0x180015aa8  jz      short loc_180015AD9
0x180015aaa  mov     rcx, cs:off_180049A48; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015ab1  test    rcx, rcx
0x180015ab4  jz      short loc_180015AD9
0x180015ab6  mov     dword ptr [rsp+0E0h+ppv], 1C1h
0x180015abe  mov     r9d, eax
0x180015ac1  mov     r8, cs:off_180049A48; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015ac8  mov     edx, 70400h
0x180015acd  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015ad4  call    _bidTraceW
0x180015ad9  mov     ecx, ebx; int
0x180015adb  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015ae1  mov     [r14], rdi
0x180015ae4  mov     rax, [rdi]
0x180015ae7  mov     rcx, rdi
0x180015aea  mov     rax, [rax+8]
0x180015aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015af3  nop
0x180015af4  lea     rcx, [rbp+57h+var_98]
0x180015af8  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015afd  nop
0x180015afe  lea     rcx, [rbp+57h+var_A0]
0x180015b02  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015b07  mov     rcx, [rbp+57h+var_40]
0x180015b0b  xor     rcx, rsp; StackCookie
0x180015b0e  call    __security_check_cookie
0x180015b13  add     rsp, 0B0h
0x180015b1a  pop     r15
0x180015b1c  pop     r14
0x180015b1e  pop     r12
0x180015b20  pop     rdi
0x180015b21  pop     rsi
0x180015b22  pop     rbx
0x180015b23  pop     rbp
0x180015b24  retn
0x180015b26  mov     rax, [rcx]
0x180015b29  mov     rax, [rax]
0x180015b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b31  mov     rax, [rdi]
0x180015b34  lea     r8, [rbp+57h+var_A0]
0x180015b38  mov     rdx, rsi
0x180015b3b  mov     rcx, rdi
0x180015b3e  mov     rax, [rax]
0x180015b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b46  test    eax, eax
0x180015b48  jns     loc_180015C4D
0x180015b4e  lea     rax, [rbp+57h+var_A0]
0x180015b52  mov     [rsp+0E0h+ppv], rax; ppv
0x180015b57  mov     r9, rsi; riid
0x180015b5a  xor     edx, edx; pUnkOuter
0x180015b5c  lea     r8d, [rdx+1]; dwClsContext
0x180015b60  lea     rcx, CLSID_EXTENDEDERRORINFO; rclsid
0x180015b67  call    cs:__imp_CoCreateInstance
0x180015b6e  nop     dword ptr [rax+rax+00h]
0x180015b73  mov     ebx, eax
0x180015b75  test    eax, eax
0x180015b77  jns     short loc_180015BB9
0x180015b79  test    byte ptr cs:_bidGblFlags, 2
0x180015b80  jz      short loc_180015BB1
0x180015b82  mov     rcx, cs:off_180049A40; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015b89  test    rcx, rcx
0x180015b8c  jz      short loc_180015BB1
0x180015b8e  mov     dword ptr [rsp+0E0h+ppv], 1D9h
0x180015b96  mov     r9d, eax
0x180015b99  mov     r8, cs:off_180049A40; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015ba0  mov     edx, 76400h
0x180015ba5  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015bac  call    _bidTraceW
0x180015bb1  mov     ecx, ebx; int
0x180015bb3  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015bb9  movups  xmm0, xmmword ptr cs:?CLSID_MSPersist@@3U_GUID@@B.Data1; _GUID const CLSID_MSPersist ...
0x180015bc0  movdqu  [rbp+57h+var_70+8], xmm0
0x180015bc5  mov     [rbp+57h+var_48], 0
0x180015bcc  mov     dword ptr [rbp+57h+var_70+4], r12d
0x180015bd0  mov     dword ptr [rbp+57h+var_70], r15d
0x180015bd4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180015bdb  movdqu  [rbp+57h+var_60+8], xmm0
0x180015be0  mov     rcx, [rbp+57h+var_A0]
0x180015be4  mov     rax, [rcx]
0x180015be7  mov     [rsp+0E0h+var_B8], 0
0x180015bef  mov     [rsp+0E0h+ppv], rdi
0x180015bf4  xor     r9d, r9d
0x180015bf7  xor     r8d, r8d
0x180015bfa  lea     rdx, [rbp+57h+var_70]
0x180015bfe  mov     rax, [rax+18h]
0x180015c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c07  mov     ebx, eax
0x180015c09  test    eax, eax
0x180015c0b  jns     short loc_180015C4D
0x180015c0d  test    byte ptr cs:_bidGblFlags, 2
0x180015c14  jz      short loc_180015C45
0x180015c16  mov     rcx, cs:off_180049A38; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015c1d  test    rcx, rcx
0x180015c20  jz      short loc_180015C45
0x180015c22  mov     dword ptr [rsp+0E0h+ppv], 1E4h
0x180015c2a  mov     r9d, eax
0x180015c2d  mov     r8, cs:off_180049A38; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015c34  mov     edx, 79000h
0x180015c39  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015c40  call    _bidTraceW
0x180015c45  mov     ecx, ebx; int
0x180015c47  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015c4d  mov     rcx, [rbp+57h+var_A0]
0x180015c51  mov     rax, [rcx]
0x180015c54  lea     rdx, [rbp+57h+var_90]
0x180015c58  mov     rax, [rax+40h]
0x180015c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c61  xor     r14d, r14d
0x180015c64  cmp     r14d, [rbp+57h+var_90]
0x180015c68  jnb     loc_180015AF4
0x180015c6e  mov     [rbp+57h+var_78], 0
0x180015c76  mov     [rbp+57h+var_88], 0
0x180015c7e  mov     [rbp+57h+var_80], 0
0x180015c86  mov     rcx, [rbp+57h+var_A0]
0x180015c8a  mov     rax, [rcx]
0x180015c8d  lea     r8, [rbp+57h+var_70]
0x180015c91  mov     edx, r14d
0x180015c94  mov     rax, [rax+20h]
0x180015c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c9d  mov     ebx, eax
0x180015c9f  test    eax, eax
0x180015ca1  js      loc_180015E4B
0x180015ca7  mov     rcx, [rbp+57h+var_A0]
0x180015cab  mov     rax, [rcx]
0x180015cae  lea     r9, [rbp+57h+var_88]
0x180015cb2  lea     r8, IID_IUnknown
0x180015cb9  mov     edx, r14d
0x180015cbc  mov     rax, [rax+28h]
0x180015cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cc5  mov     ebx, eax
0x180015cc7  test    eax, eax
0x180015cc9  js      loc_180015E0B
0x180015ccf  mov     rbx, [rbp+57h+var_88]
0x180015cd3  test    rbx, rbx
0x180015cd6  jz      loc_180015D69
0x180015cdc  mov     rax, [rbx]
0x180015cdf  lea     r8, [rbp+57h+var_78]
0x180015ce3  lea     rdx, IID_IErrorInfo
0x180015cea  mov     rcx, rbx
0x180015ced  mov     rax, [rax]
0x180015cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cf5  test    eax, eax
0x180015cf7  jns     short loc_180015D65
0x180015cf9  mov     ecx, 48h ; 'H'; unsigned int
0x180015cfe  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180015d03  mov     [rbp+57h+var_80], rax
0x180015d07  test    rax, rax
0x180015d0a  jz      short loc_180015D19
0x180015d0c  mov     rcx, rax; this
0x180015d0f  call    ??0CPersistErrorInfo@@QEAA@XZ; CPersistErrorInfo::CPersistErrorInfo(void)
0x180015d14  mov     rbx, rax
0x180015d17  jmp     short loc_180015D1B
0x180015d19  xor     ebx, ebx
0x180015d1b  mov     [rbp+57h+var_80], rbx
0x180015d1f  mov     rcx, rbx; void *
0x180015d22  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180015d27  mov     rdx, rdi; struct IErrorInfo *
0x180015d2a  mov     rcx, rbx; this
0x180015d2d  call    ?SetErrorInfo@CPersistErrorInfo@@QEAAXPEAUIErrorInfo@@@Z; CPersistErrorInfo::SetErrorInfo(IErrorInfo *)
0x180015d32  mov     rsi, [rbp+57h+var_88]
0x180015d36  mov     rcx, [rbx+10h]
0x180015d3a  test    rcx, rcx
0x180015d3d  jz      short loc_180015D4B
0x180015d3f  mov     rax, [rcx]
0x180015d42  mov     rax, [rax+10h]
0x180015d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d4b  mov     [rbx+10h], rsi
0x180015d4f  test    rsi, rsi
0x180015d52  jz      short loc_180015D69
0x180015d54  mov     rax, [rsi]
0x180015d57  mov     rcx, rsi
0x180015d5a  mov     rax, [rax+8]
0x180015d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d63  jmp     short loc_180015D69
0x180015d65  mov     rbx, [rbp+57h+var_88]
0x180015d69  mov     rcx, [rbp+57h+var_98]
0x180015d6d  mov     rdx, [rcx]
0x180015d70  mov     rax, rbx
0x180015d73  neg     rax
0x180015d76  sbb     r8d, r8d
0x180015d79  not     r8d
0x180015d7c  and     r8d, 10000000h
0x180015d83  mov     rax, [rdx+18h]
0x180015d87  mov     [rsp+0E0h+var_B8], 0
0x180015d8f  mov     [rsp+0E0h+ppv], rbx
0x180015d94  xor     r9d, r9d
0x180015d97  lea     rdx, [rbp+57h+var_70]
0x180015d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015da0  mov     ebx, eax
0x180015da2  test    eax, eax
0x180015da4  js      short loc_180015DCB
0x180015da6  lea     rcx, [rbp+57h+var_80]
0x180015daa  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015daf  nop
0x180015db0  lea     rcx, [rbp+57h+var_88]
0x180015db4  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015db9  nop
0x180015dba  lea     rcx, [rbp+57h+var_78]
0x180015dbe  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015dc3  inc     r14d
0x180015dc6  jmp     loc_180015C64
0x180015dcb  test    byte ptr cs:_bidGblFlags, 2
0x180015dd2  jz      short loc_180015E03
0x180015dd4  mov     rax, cs:off_180049A20; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015ddb  test    rax, rax
0x180015dde  jz      short loc_180015E03
0x180015de0  mov     dword ptr [rsp+0E0h+ppv], 201h
0x180015de8  mov     r9d, ebx
0x180015deb  mov     r8, cs:off_180049A20; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015df2  mov     edx, 80400h
0x180015df7  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015dfe  call    _bidTraceW
0x180015e03  mov     ecx, ebx; int
0x180015e05  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015e0b  test    byte ptr cs:_bidGblFlags, 2
0x180015e12  jz      short loc_180015E43
0x180015e14  mov     rax, cs:off_180049A28; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015e1b  test    rax, rax
0x180015e1e  jz      short loc_180015E43
0x180015e20  mov     dword ptr [rsp+0E0h+ppv], 1F2h
0x180015e28  mov     r9d, ebx
0x180015e2b  mov     r8, cs:off_180049A28; "<CPersistErrorCache::AddError|ADO|ERR> "...
0x180015e32  mov     edx, 7C800h
0x180015e37  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015e3e  call    _bidTraceW
0x180015e43  mov     ecx, ebx; int
0x180015e45  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015e4b  test    byte ptr cs:_bidGblFlags, 2
  ... truncated ...
```
