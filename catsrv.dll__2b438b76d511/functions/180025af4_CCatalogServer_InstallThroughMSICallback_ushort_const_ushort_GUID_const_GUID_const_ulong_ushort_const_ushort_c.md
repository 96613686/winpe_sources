# CCatalogServer::InstallThroughMSICallback(ushort const *,ushort *,_GUID const &,_GUID const &,ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x180025af4`
- end: `0x180025e1a`
- name: `?InstallThroughMSICallback@CCatalogServer@@AEAAJPEBGPEAGAEBU_GUID@@2K000@Z`
- size: `806`
- prototype: `int(CCatalogServer *__hidden this, const unsigned __int16 *, unsigned __int16 *, const struct _GUID *, const struct _GUID *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180025390`

## callees

- `0x18000ae48`
- `0x18000ae78`
- `0x180025af4`
- `0x180025e20`
- `0x18002673c`
- `0x18002ffc0`
- `0x180032c98`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180025db7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180025db7`
- `catsrvut!CGMIsAdministrator` at `0x180025ba1`
- `catsrvut!CGMIsAdministrator` at `0x180025ba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025dc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025dc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025dd0`

## pseudocode

```c
__int64 __fastcall CCatalogServer::InstallThroughMSICallback(
        CCatalogServer *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct _GUID *a4,
        struct _GUID *a5,
        unsigned int a6,
        unsigned __int16 *a7,
        const unsigned __int16 *a8,
        const unsigned __int16 *a9)
{
  int v9; // ebx
  GUID *v10; // rdi
  WCHAR *v12; // rsi
  __int64 v13; // rax
  BOOL v14; // r14d
  int v15; // r13d
  BOOL v16; // r15d
  struct _GUID v17; // xmm1
  int updated; // eax
  unsigned __int16 *v19; // rcx
  bool v20; // zf
  __int64 v21; // rax
  CCatalogServer *v22; // r15
  GUID *v23; // r14
  const struct _GUID *v24; // rbx
  CCatalogServer *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  int v29; // [rsp+40h] [rbp-A1h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-99h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-91h] BYREF
  int v32; // [rsp+58h] [rbp-89h] BYREF
  GUID *v33; // [rsp+60h] [rbp-81h]
  CCatalogServer *v34; // [rsp+68h] [rbp-79h]
  unsigned __int16 *v35; // [rsp+70h] [rbp-71h]
  const unsigned __int16 *v36; // [rsp+78h] [rbp-69h]
  const unsigned __int16 *v37; // [rsp+80h] [rbp-61h]
  void *ppInterface; // [rsp+88h] [rbp-59h] BYREF
  int v39; // [rsp+90h] [rbp-51h]
  __int64 v40; // [rsp+98h] [rbp-49h]
  GUID v41; // [rsp+A0h] [rbp-41h] BYREF
  struct _GUID Buf1; // [rsp+B0h] [rbp-31h] BYREF
  GUID rguid; // [rsp+C0h] [rbp-21h] BYREF

  v9 = 0;
  v10 = a5;
  v35 = a7;
  v12 = 0;
  v37 = a8;
  v34 = this;
  v36 = a9;
  v33 = a4;
  pv = a3;
  ppInterface = 0;
  v39 = 0;
  v40 = 0;
  lpFileName = 0;
  v29 = CImpersonate::ImpersonateClient(&ppInterface);
  if ( v29 >= 0 )
  {
    v13 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v13 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_NULL.Data4;
    v32 = 0;
    v14 = v13 != 0;
    v29 = CGMIsAdministrator(&v32);
    if ( v29 >= 0 )
    {
      v15 = 0;
      v16 = v32 == 0;
      if ( memcmp_0(&stru_180072AA0, &GUID_NULL, 0x10u) && memcmp_0(&stru_180072AA0, &GUID_DefaultAppPartition, 0x10u) )
        v9 = 1;
      if ( v14 || v16 || v9 )
      {
        v17 = *a5;
        v41 = stru_180072AA0;
        Buf1 = v17;
        rguid = *v33;
        updated = UpdateMSIFile(a2, &rguid, &Buf1, &v41, v16, v14, v9, (unsigned __int16 **)&lpFileName);
        v12 = (WCHAR *)lpFileName;
        v29 = updated;
        if ( updated < 0 )
          goto LABEL_29;
        a2 = lpFileName;
      }
      v19 = (unsigned __int16 *)pv;
      if ( pv && *(_WORD *)pv )
      {
        v23 = v33;
        v22 = v34;
      }
      else
      {
        v21 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_NULL.Data1;
        v20 = *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_NULL.Data1;
        lpFileName = 0;
        if ( v20 )
          v21 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_NULL.Data4;
        v22 = v34;
        v23 = v33;
        pv = 0;
        v24 = v33;
        if ( v21 )
          v24 = a5;
        v29 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, LPCWSTR *))v34 + 32))(
                *((_QWORD *)v34 + 32),
                &IID_IAppImport2,
                &lpFileName);
        if ( v29 < 0 )
          goto LABEL_29;
        v29 = (*(__int64 (__fastcall **)(LPCWSTR, const struct _GUID *, const unsigned __int16 *, LPVOID *))(*(_QWORD *)lpFileName + 40LL))(
                lpFileName,
                v24,
                a2,
                &pv);
        (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)lpFileName + 16LL))(lpFileName);
        if ( v29 < 0 )
          goto LABEL_29;
        v19 = (unsigned __int16 *)pv;
        v15 = 1;
      }
      RegScanUtil::StoreFileRefCounts(v19);
      v29 = CCatalogServer::InvokeMSI(v25, a2, (const unsigned __int16 *)pv, v35, a6);
      if ( v29 >= 0 )
      {
        v26 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_NULL.Data1;
        if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
          v26 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_NULL.Data4;
        v27 = *((_QWORD *)v22 + 32);
        if ( !v26 )
          v10 = v23;
        rguid = *v10;
        v29 = (*(__int64 (__fastcall **)(__int64, GUID *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v27 + 48LL))(
                v27,
                &rguid,
                v37,
                v36);
      }
LABEL_29:
      if ( v12 )
      {
        DeleteFileW(v12);
        CoTaskMemFree(v12);
      }
      if ( v15 )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
    }
  }
  CImpersonate::Cleanup((CImpersonate *)&ppInterface, &v29);
  CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x180025af4  push    rbp
0x180025af6  push    rbx
0x180025af7  push    rsi
0x180025af8  push    rdi
0x180025af9  push    r12
0x180025afb  push    r13
0x180025afd  push    r14
0x180025aff  push    r15
0x180025b01  lea     rbp, [rsp-7]
0x180025b06  sub     rsp, 0E8h
0x180025b0d  mov     rax, cs:__security_cookie
0x180025b14  xor     rax, rsp
0x180025b17  mov     [rbp+3Fh+var_50], rax
0x180025b1b  mov     rax, [rbp+3Fh+arg_30]
0x180025b1f  xor     ebx, ebx
0x180025b21  mov     rdi, [rbp+3Fh+arg_20]
0x180025b25  mov     r12, rdx
0x180025b28  mov     [rbp+3Fh+var_B0], rax
0x180025b2c  mov     esi, ebx
0x180025b2e  mov     rax, [rbp+3Fh+arg_38]
0x180025b35  mov     [rbp+3Fh+var_A0], rax
0x180025b39  mov     rax, [rbp+3Fh+arg_40]
0x180025b40  mov     [rbp+3Fh+var_B8], rcx
0x180025b44  lea     rcx, [rbp+3Fh+ppInterface]; ppInterface
0x180025b48  mov     [rbp+3Fh+var_A8], rax
0x180025b4c  mov     [rsp+120h+var_C0], r9
0x180025b51  mov     [rsp+120h+pv], r8
0x180025b56  mov     [rbp+3Fh+ppInterface], rbx
0x180025b5a  mov     [rbp+3Fh+var_90], ebx
0x180025b5d  mov     [rbp+3Fh+var_88], rbx
0x180025b61  mov     [rsp+120h+lpFileName], rbx
0x180025b66  call    ?ImpersonateClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateClient(void)
0x180025b6b  mov     [rsp+120h+var_E0], eax
0x180025b6f  test    eax, eax
0x180025b71  js      loc_180025DDF
0x180025b77  mov     rax, [rdi]
0x180025b7a  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180025b81  jnz     short loc_180025B8E
0x180025b83  mov     rax, [rdi+8]
0x180025b87  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180025b8e  test    rax, rax
0x180025b91  mov     [rsp+120h+var_C8], ebx
0x180025b95  mov     r14d, ebx
0x180025b98  lea     rcx, [rsp+120h+var_C8]
0x180025b9d  setnz   r14b
0x180025ba1  call    cs:__imp_CGMIsAdministrator
0x180025ba7  mov     [rsp+120h+var_E0], eax
0x180025bab  test    eax, eax
0x180025bad  js      loc_180025DDF
0x180025bb3  cmp     [rsp+120h+var_C8], ebx
0x180025bb7  lea     rdx, GUID_NULL; Buf2
0x180025bbe  mov     eax, 1
0x180025bc3  lea     rcx, stru_180072AA0; Buf1
0x180025bca  mov     r15d, ebx
0x180025bcd  mov     r13d, ebx
0x180025bd0  cmovz   r15d, eax
0x180025bd4  lea     r8d, [rax+0Fh]; Size
0x180025bd8  call    memcmp_0
0x180025bdd  test    eax, eax
0x180025bdf  jz      short loc_180025C04
0x180025be1  mov     r8d, 10h; Size
0x180025be7  lea     rdx, GUID_DefaultAppPartition; Buf2
0x180025bee  lea     rcx, stru_180072AA0; Buf1
0x180025bf5  call    memcmp_0
0x180025bfa  test    eax, eax
0x180025bfc  mov     eax, 1
0x180025c01  cmovnz  ebx, eax
0x180025c04  test    r14d, r14d
0x180025c07  jnz     short loc_180025C12
0x180025c09  test    r15d, r15d
0x180025c0c  jnz     short loc_180025C12
0x180025c0e  test    ebx, ebx
0x180025c10  jz      short loc_180025C73
0x180025c12  movaps  xmm0, xmmword ptr cs:stru_180072AA0.Data1
0x180025c19  lea     r9, [rbp+3Fh+var_80]; GUID *
0x180025c1d  mov     rax, [rsp+120h+var_C0]
0x180025c22  lea     r8, [rbp+3Fh+Buf1]; Buf1
0x180025c26  movaps  xmm1, xmmword ptr [rdi]
0x180025c29  lea     rdx, [rbp+3Fh+rguid]; rguid
0x180025c2d  movdqu  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x180025c32  mov     rcx, r12; lpExistingFileName
0x180025c35  movdqa  xmmword ptr [rbp+3Fh+Buf1.Data1], xmm1
0x180025c3a  movups  xmm0, xmmword ptr [rax]
0x180025c3d  lea     rax, [rsp+120h+lpFileName]
0x180025c42  mov     [rsp+120h+var_E8], rax; unsigned __int16 **
0x180025c47  mov     [rsp+120h+var_F0], ebx; int
0x180025c4b  mov     [rsp+120h+var_F8], r14d; int
0x180025c50  mov     [rsp+120h+var_100], r15d; int
0x180025c55  movdqu  xmmword ptr [rbp+3Fh+rguid.Data1], xmm0
0x180025c5a  call    ?UpdateMSIFile@@YAJPEBGU_GUID@@11HHHPEAPEAG@Z; UpdateMSIFile(ushort const *,_GUID,_GUID,_GUID,int,int,int,ushort * *)
0x180025c5f  mov     rsi, [rsp+120h+lpFileName]
0x180025c64  mov     [rsp+120h+var_E0], eax
0x180025c68  test    eax, eax
0x180025c6a  js      loc_180025DAF
0x180025c70  mov     r12, rsi
0x180025c73  mov     rcx, [rsp+120h+pv]; unsigned __int16 *
0x180025c78  test    rcx, rcx
0x180025c7b  jz      short loc_180025C88
0x180025c7d  xor     eax, eax
0x180025c7f  cmp     ax, [rcx]
0x180025c82  jnz     loc_180025D33
0x180025c88  mov     rax, [rdi]
0x180025c8b  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180025c92  mov     [rsp+120h+lpFileName], r13
0x180025c97  jnz     short loc_180025CA4
0x180025c99  mov     rax, [rdi+8]
0x180025c9d  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180025ca4  mov     r15, [rbp+3Fh+var_B8]
0x180025ca8  lea     r8, [rsp+120h+lpFileName]
0x180025cad  mov     r14, [rsp+120h+var_C0]
0x180025cb2  lea     rdx, IID_IAppImport2
0x180025cb9  test    rax, rax
0x180025cbc  mov     [rsp+120h+pv], r13
0x180025cc1  mov     rbx, r14
0x180025cc4  mov     rcx, [r15+100h]
0x180025ccb  setz    al
0x180025cce  test    al, al
0x180025cd0  cmovz   rbx, rdi
0x180025cd4  mov     rax, [rcx]
0x180025cd7  mov     rax, [rax]
0x180025cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cdf  mov     [rsp+120h+var_E0], eax
0x180025ce3  test    eax, eax
0x180025ce5  js      loc_180025DAF
0x180025ceb  mov     rcx, [rsp+120h+lpFileName]
0x180025cf0  lea     r9, [rsp+120h+pv]
0x180025cf5  mov     r8, r12
0x180025cf8  mov     rdx, rbx
0x180025cfb  mov     rax, [rcx]
0x180025cfe  mov     rax, [rax+28h]
0x180025d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d07  mov     rcx, [rsp+120h+lpFileName]
0x180025d0c  mov     ebx, eax
0x180025d0e  mov     [rsp+120h+var_E0], eax
0x180025d12  mov     rdx, [rcx]
0x180025d15  mov     rax, [rdx+10h]
0x180025d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d1e  test    ebx, ebx
0x180025d20  js      loc_180025DAF
0x180025d26  mov     rcx, [rsp+120h+pv]
0x180025d2b  mov     r13d, 1
0x180025d31  jmp     short loc_180025D3C
0x180025d33  mov     r14, [rsp+120h+var_C0]
0x180025d38  mov     r15, [rbp+3Fh+var_B8]
0x180025d3c  call    ?StoreFileRefCounts@RegScanUtil@@SAXPEAG@Z; RegScanUtil::StoreFileRefCounts(ushort *)
0x180025d41  mov     eax, [rbp+3Fh+arg_28]
0x180025d44  mov     rdx, r12; unsigned __int16 *
0x180025d47  mov     r9, [rbp+3Fh+var_B0]; unsigned __int16 *
0x180025d4b  mov     r8, [rsp+120h+pv]; unsigned __int16 *
0x180025d50  mov     [rsp+120h+var_100], eax; unsigned int
0x180025d54  call    ?InvokeMSI@CCatalogServer@@AEAAJPEBG00K@Z; CCatalogServer::InvokeMSI(ushort const *,ushort const *,ushort const *,ulong)
0x180025d59  mov     [rsp+120h+var_E0], eax
0x180025d5d  test    eax, eax
0x180025d5f  js      short loc_180025DAF
0x180025d61  mov     rax, [rdi]
0x180025d64  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180025d6b  jnz     short loc_180025D78
0x180025d6d  mov     rax, [rdi+8]
0x180025d71  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180025d78  mov     rcx, [r15+100h]
0x180025d7f  lea     rdx, [rbp+3Fh+rguid]
0x180025d83  mov     r9, [rbp+3Fh+var_A8]
0x180025d87  test    rax, rax
0x180025d8a  mov     r8, [rbp+3Fh+var_A0]
0x180025d8e  setnz   al
0x180025d91  test    al, al
0x180025d93  cmovz   rdi, r14
0x180025d97  movups  xmm0, xmmword ptr [rdi]
0x180025d9a  movdqu  xmmword ptr [rbp+3Fh+rguid.Data1], xmm0
0x180025d9f  mov     rax, [rcx]
0x180025da2  mov     rax, [rax+30h]
0x180025da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dab  mov     [rsp+120h+var_E0], eax
0x180025daf  test    rsi, rsi
0x180025db2  jz      short loc_180025DC6
0x180025db4  mov     rcx, rsi; lpFileName
0x180025db7  call    cs:__imp_DeleteFileW
0x180025dbd  mov     rcx, rsi; pv
0x180025dc0  call    cs:__imp_CoTaskMemFree
0x180025dc6  test    r13d, r13d
0x180025dc9  jz      short loc_180025DDF
0x180025dcb  mov     rcx, [rsp+120h+pv]; pv
0x180025dd0  call    cs:__imp_CoTaskMemFree
0x180025dd6  mov     [rsp+120h+pv], 0
0x180025ddf  lea     rdx, [rsp+120h+var_E0]; int *
0x180025de4  lea     rcx, [rbp+3Fh+ppInterface]; this
0x180025de8  call    ?Cleanup@CImpersonate@@QEAAXPEAJ@Z; CImpersonate::Cleanup(long *)
0x180025ded  lea     rcx, [rbp+3Fh+ppInterface]; this
0x180025df1  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x180025df6  mov     eax, [rsp+120h+var_E0]
0x180025dfa  mov     rcx, [rbp+3Fh+var_50]
0x180025dfe  xor     rcx, rsp; StackCookie
0x180025e01  call    __security_check_cookie
0x180025e06  add     rsp, 0E8h
0x180025e0d  pop     r15
0x180025e0f  pop     r14
0x180025e11  pop     r13
0x180025e13  pop     r12
0x180025e15  pop     rdi
0x180025e16  pop     rsi
0x180025e17  pop     rbx
0x180025e18  pop     rbp
0x180025e19  retn
```
