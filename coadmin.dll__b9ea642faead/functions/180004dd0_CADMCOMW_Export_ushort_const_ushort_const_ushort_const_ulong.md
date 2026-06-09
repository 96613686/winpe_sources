# CADMCOMW::Export(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180004dd0`
- end: `0x180005041`
- name: `?Export@CADMCOMW@@UEAAJPEBG00K@Z`
- size: `625`
- prototype: `__int64 __fastcall(CADMCOMW *this, const unsigned __int16 *, const unsigned __int16 *, wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001cec`
- `0x180004dd0`
- `0x180007068`
- `0x180007394`
- `0x180007f40`
- `0x18000be20`
- `0x18000fb50`
- `0x180010010`

## import_xrefs

- `ole32!CoImpersonateClient` at `0x180004e3f`
- `ole32!CoImpersonateClient` at `0x180004e3f`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180005019`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180005019`
- `IisRTL!PuDbgPrint` at `0x180004ec4`
- `IisRTL!PuDbgPrint` at `0x180004f9d`
- `IisRTL!PuDbgPrint` at `0x180004ec4`
- `IisRTL!PuDbgPrint` at `0x180004f9d`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x180004e1d`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x180004e1d`

## string_xrefs

- `0x180004eab`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180004f84`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180004eb2`: `AccessCheck failed hr = 0x%08x\n`
- `0x180004f8b`: `AccessCheck failed hr = 0x%08x\n`
- `0x180004ea0`: `CADMCOMW::Export`
- `0x180004f79`: `CADMCOMW::Export`

## pseudocode

```c
__int64 __fastcall CADMCOMW::Export(
        CADMCOMW *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        wchar_t *a4,
        unsigned int a5)
{
  struct COpenHandle *v6; // rdi
  int PathCanonicalizationProof; // ebx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  unsigned int v15; // [rsp+50h] [rbp-51h] BYREF
  unsigned int v16; // [rsp+54h] [rbp-4Dh] BYREF
  unsigned int v17; // [rsp+58h] [rbp-49h] BYREF
  struct COpenHandle *v18; // [rsp+60h] [rbp-41h] BYREF
  _BYTE v19[32]; // [rsp+68h] [rbp-39h] BYREF
  __int64 v20; // [rsp+88h] [rbp-19h]

  v15 = 0;
  v16 = 0;
  v6 = 0;
  v17 = 0;
  v18 = 0;
  STRU::STRU((STRU *)v19);
  if ( a3 && *a3 && a4 )
  {
    PathCanonicalizationProof = CoImpersonateClient();
    if ( PathCanonicalizationProof < 0 )
      goto LABEL_20;
    v11 = CADMCOMW::AccessCheck(
            (__int64)this,
            0,
            &byte_1800127D8,
            2u,
            2u,
            0,
            (struct COpenHandle *)&g_ohMasterRootHandle,
            0,
            0);
    PathCanonicalizationProof = v11;
    if ( v11 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
          3858,
          "CADMCOMW::Export",
          "AccessCheck failed hr = 0x%08x\n",
          v11);
      goto LABEL_20;
    }
    PathCanonicalizationProof = CADMCOMW::OpenKeyHelper(this, 0, a4, 1u, 0x1388u, &v15);
    if ( PathCanonicalizationProof < 0 )
      goto LABEL_20;
    v12 = CADMCOMW::Lookup(this, v15, &v16, &v17, &v18);
    v6 = v18;
    PathCanonicalizationProof = v12;
    if ( v12 >= 0 )
    {
      COpenHandle::Release(v18, this);
      v13 = CADMCOMW::AccessCheck((__int64)this, v15, &byte_1800127D8, 2u, 2u, 0, v6, 0, 0);
      PathCanonicalizationProof = v13;
      if ( v13 >= 0 )
      {
        PathCanonicalizationProof = MakePathCanonicalizationProof(a3, 0, (struct STRU *)v19);
        if ( PathCanonicalizationProof >= 0 )
          PathCanonicalizationProof = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, __int64, wchar_t *, unsigned int))(**((_QWORD **)this + 4) + 472LL))(
                                        *((_QWORD *)this + 4),
                                        v16,
                                        a2,
                                        v20,
                                        a4,
                                        a5);
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
          3894,
          "CADMCOMW::Export",
          "AccessCheck failed hr = 0x%08x\n",
          v13);
      }
    }
  }
  else
  {
    PathCanonicalizationProof = -2147024809;
  }
  if ( v6 )
  {
    if ( v16 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 288LL))(*((_QWORD *)this + 4));
    COpenHandle::Release(v6, this);
  }
LABEL_20:
  STRU::~STRU((STRU *)v19);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x180004dd0  push    rbp
0x180004dd2  push    rbx
0x180004dd3  push    rsi
0x180004dd4  push    rdi
0x180004dd5  push    r12
0x180004dd7  push    r13
0x180004dd9  push    r14
0x180004ddb  push    r15
0x180004ddd  lea     rbp, [rsp-17h]
0x180004de2  sub     rsp, 0B8h
0x180004de9  mov     rax, cs:__security_cookie
0x180004df0  xor     rax, rsp
0x180004df3  mov     [rbp+4Fh+var_50], rax
0x180004df7  xor     r13d, r13d
0x180004dfa  mov     rsi, rcx
0x180004dfd  lea     rcx, [rbp+4Fh+var_88]
0x180004e01  mov     [rbp+4Fh+var_A0], r13d
0x180004e05  mov     [rbp+4Fh+var_9C], r13d
0x180004e09  mov     edi, r13d
0x180004e0c  mov     [rbp+4Fh+var_98], r13d
0x180004e10  mov     r15, r9
0x180004e13  mov     [rbp+4Fh+var_90], r13
0x180004e17  mov     r14, r8
0x180004e1a  mov     r12, rdx
0x180004e1d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004e23  test    r14, r14
0x180004e26  jz      loc_180004FE6
0x180004e2c  cmp     [r14], r13w
0x180004e30  jz      loc_180004FE6
0x180004e36  test    r15, r15
0x180004e39  jz      loc_180004FE6
0x180004e3f  call    cs:__imp_CoImpersonateClient
0x180004e45  mov     ebx, eax
0x180004e47  test    eax, eax
0x180004e49  js      loc_180005015
0x180004e4f  mov     [rsp+0F0h+var_B0], r13
0x180004e54  lea     rax, ?g_ohMasterRootHandle@@3VCOpenHandle@@A; COpenHandle g_ohMasterRootHandle
0x180004e5b  mov     [rsp+0F0h+var_B8], r13
0x180004e60  lea     r8, byte_1800127D8
0x180004e67  mov     [rsp+0F0h+var_C0], rax
0x180004e6c  xor     edx, edx
0x180004e6e  lea     eax, [r13+2]
0x180004e72  mov     [rsp+0F0h+var_C8], r13
0x180004e77  mov     r9d, eax
0x180004e7a  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180004e7e  mov     rcx, rsi
0x180004e81  call    ?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z; CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)
0x180004e86  mov     ebx, eax
0x180004e88  test    eax, eax
0x180004e8a  jns     short loc_180004ECF
0x180004e8c  test    byte ptr cs:g_dwDebugFlags, 3
0x180004e93  jz      loc_180005015
0x180004e99  mov     rcx, cs:g_pDebug
0x180004ea0  lea     r9, aCadmcomwExport; "CADMCOMW::Export"
0x180004ea7  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180004eab  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180004eb2  lea     rax, aAccesscheckFai; "AccessCheck failed hr = 0x%08x\n"
0x180004eb9  mov     r8d, 0F12h
0x180004ebf  mov     [rsp+0F0h+var_D0], rax
0x180004ec4  call    cs:__imp_PuDbgPrint
0x180004eca  jmp     loc_180005015
0x180004ecf  lea     rax, [rbp+4Fh+var_A0]
0x180004ed3  mov     r9d, 1; unsigned int
0x180004ed9  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x180004ede  mov     r8, r15; Str
0x180004ee1  xor     edx, edx; unsigned int
0x180004ee3  mov     dword ptr [rsp+0F0h+var_D0], 1388h; unsigned int
0x180004eeb  mov     rcx, rsi; this
0x180004eee  call    ?OpenKeyHelper@CADMCOMW@@QEAAJKPEBGKKPEAK@Z; CADMCOMW::OpenKeyHelper(ulong,ushort const *,ulong,ulong,ulong *)
0x180004ef3  mov     ebx, eax
0x180004ef5  test    eax, eax
0x180004ef7  js      loc_180005015
0x180004efd  mov     edx, [rbp+4Fh+var_A0]; unsigned int
0x180004f00  lea     rax, [rbp+4Fh+var_90]
0x180004f04  lea     r9, [rbp+4Fh+var_98]; unsigned int *
0x180004f08  mov     [rsp+0F0h+var_D0], rax; struct COpenHandle **
0x180004f0d  lea     r8, [rbp+4Fh+var_9C]; unsigned int *
0x180004f11  mov     rcx, rsi; this
0x180004f14  call    ?Lookup@CADMCOMW@@QEAAJKPEAK0PEAPEAVCOpenHandle@@@Z; CADMCOMW::Lookup(ulong,ulong *,ulong *,COpenHandle * *)
0x180004f19  mov     rdi, [rbp+4Fh+var_90]
0x180004f1d  mov     ebx, eax
0x180004f1f  test    eax, eax
0x180004f21  js      loc_180004FEB
0x180004f27  mov     rdx, rsi; void *
0x180004f2a  mov     rcx, rdi; this
0x180004f2d  call    ?Release@COpenHandle@@QEAAXPEAX@Z; COpenHandle::Release(void *)
0x180004f32  mov     edx, [rbp+4Fh+var_A0]
0x180004f35  lea     r8, byte_1800127D8
0x180004f3c  mov     [rsp+0F0h+var_B0], r13
0x180004f41  mov     r9d, 2
0x180004f47  mov     [rsp+0F0h+var_B8], r13
0x180004f4c  mov     rcx, rsi
0x180004f4f  mov     [rsp+0F0h+var_C0], rdi
0x180004f54  mov     [rsp+0F0h+var_C8], r13
0x180004f59  mov     dword ptr [rsp+0F0h+var_D0], r9d
0x180004f5e  call    ?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z; CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)
0x180004f63  mov     ebx, eax
0x180004f65  test    eax, eax
0x180004f67  jns     short loc_180004FA5
0x180004f69  test    byte ptr cs:g_dwDebugFlags, 3
0x180004f70  jz      short loc_180004FEB
0x180004f72  mov     rcx, cs:g_pDebug
0x180004f79  lea     r9, aCadmcomwExport; "CADMCOMW::Export"
0x180004f80  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180004f84  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180004f8b  lea     rax, aAccesscheckFai; "AccessCheck failed hr = 0x%08x\n"
0x180004f92  mov     r8d, 0F36h
0x180004f98  mov     [rsp+0F0h+var_D0], rax
0x180004f9d  call    cs:__imp_PuDbgPrint
0x180004fa3  jmp     short loc_180004FEB
0x180004fa5  lea     r8, [rbp+4Fh+var_88]; struct STRU *
0x180004fa9  xor     edx, edx; int
0x180004fab  mov     rcx, r14; unsigned __int16 *
0x180004fae  call    ?MakePathCanonicalizationProof@@YAJPEBGHPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,int,STRU *)
0x180004fb3  mov     ebx, eax
0x180004fb5  test    eax, eax
0x180004fb7  js      short loc_180004FEB
0x180004fb9  mov     edx, [rbp+4Fh+arg_20]
0x180004fbc  mov     r8, r12
0x180004fbf  mov     rcx, [rsi+20h]
0x180004fc3  mov     r9, [rbp+4Fh+var_68]
0x180004fc7  mov     dword ptr [rsp+0F0h+var_C8], edx
0x180004fcb  mov     edx, [rbp+4Fh+var_9C]
0x180004fce  mov     rax, [rcx]
0x180004fd1  mov     [rsp+0F0h+var_D0], r15
0x180004fd6  mov     rax, [rax+1D8h]
0x180004fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe2  mov     ebx, eax
0x180004fe4  jmp     short loc_180004FEB
0x180004fe6  mov     ebx, 80070057h
0x180004feb  test    rdi, rdi
0x180004fee  jz      short loc_180005015
0x180004ff0  mov     edx, [rbp+4Fh+var_9C]
0x180004ff3  test    edx, edx
0x180004ff5  jz      short loc_18000500A
0x180004ff7  mov     rcx, [rsi+20h]
0x180004ffb  mov     rax, [rcx]
0x180004ffe  mov     rax, [rax+120h]
0x180005005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000500a  mov     rdx, rsi; void *
0x18000500d  mov     rcx, rdi; this
0x180005010  call    ?Release@COpenHandle@@QEAAXPEAX@Z; COpenHandle::Release(void *)
0x180005015  lea     rcx, [rbp+4Fh+var_88]
0x180005019  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000501f  mov     eax, ebx
0x180005021  mov     rcx, [rbp+4Fh+var_50]
0x180005025  xor     rcx, rsp; StackCookie
0x180005028  call    __security_check_cookie
0x18000502d  add     rsp, 0B8h
0x180005034  pop     r15
0x180005036  pop     r14
0x180005038  pop     r13
0x18000503a  pop     r12
0x18000503c  pop     rdi
0x18000503d  pop     rsi
0x18000503e  pop     rbx
0x18000503f  pop     rbp
0x180005040  retn
```
