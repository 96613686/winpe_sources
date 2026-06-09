# CAppImport::ImportApplicationFromPDF(ushort *,ushort *,ushort *,ushort *,ushort *,ulong,CArray<FileInfo *,FileInfo * const &> * *,CArray<CompInfo *,CompInfo * const &> * *)

- ea: `0x18003d4bc`
- end: `0x18003d715`
- name: `?ImportApplicationFromPDF@CAppImport@@AEAAJPEAG0000KPEAPEAV?$CArray@PEAUFileInfo@@AEBQEAU1@@@PEAPEAV?$CArray@PEAUCompInfo@@AEBQEAU1@@@@Z`
- size: `601`
- prototype: `__int64 __fastcall(__int64, wchar_t *String1, wchar_t *String2, unsigned __int16 *, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c380`

## callees

- `0x180029550`
- `0x18003a57c`
- `0x18003d4bc`
- `0x180044b28`
- `0x1800474b0`
- `0x18004859c`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d661`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d674`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d68d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d6af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d6c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d661`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d674`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d68d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d6af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d6c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d589`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAppImport::ImportApplicationFromPDF(
        const struct _GUID *a1,
        wchar_t *String1,
        wchar_t *String2,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        char a7,
        __int64 *a8,
        __int64 *a9)
{
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  unsigned int v15; // r12d
  unsigned int v16; // edi
  _QWORD *v17; // rbx
  unsigned int v18; // r14d
  unsigned __int16 **v19; // r15
  void *v20; // rcx
  unsigned __int16 *v21; // rcx
  unsigned int v22; // edi
  unsigned __int16 **v23; // rbx
  unsigned int i; // esi
  unsigned __int16 *v25; // rcx
  int v27; // [rsp+30h] [rbp-D0h]
  unsigned int v28; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v29; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v30; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 **v32; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 **v33; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v34; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v35; // [rsp+80h] [rbp-80h]
  _QWORD *v36; // [rsp+88h] [rbp-78h]
  _BYTE v37[320]; // [rsp+90h] [rbp-70h] BYREF

  v35 = a5;
  v34 = a6;
  UploadSQMData<enum CatalogServerSQMFlags>(1);
  CPackageDefinitionFile::CPackageDefinitionFile((CPackageDefinitionFile *)v37, a1 + 6);
  v28 = 0;
  pv = 0;
  v32 = 0;
  v30 = 0;
  v29 = 0;
  v33 = 0;
  v13 = CoTaskMemAlloc(0x20u);
  v36 = v13;
  if ( !v13 )
  {
    *a8 = 0;
    goto LABEL_23;
  }
  *v13 = &CArray<DllInfo *,DllInfo * const &>::`vftable';
  v13[1] = 0;
  *(_QWORD *)((char *)v13 + 20) = 0;
  *((_DWORD *)v13 + 4) = 0;
  *a8 = (__int64)v13;
  v14 = CoTaskMemAlloc(0x20u);
  v36 = v14;
  if ( !v14 )
  {
    *a9 = 0;
LABEL_23:
    CPackageDefinitionFile::~CPackageDefinitionFile((CPackageDefinitionFile *)v37);
    return 2147942414LL;
  }
  *v14 = &CArray<CompInfo *,CompInfo * const &>::`vftable';
  v14[1] = 0;
  *(_QWORD *)((char *)v14 + 20) = 0;
  *((_DWORD *)v14 + 4) = 0;
  *a9 = (__int64)v14;
  v15 = CPackageDefinitionFile::QueryPackageFromFile(
          (CPackageDefinitionFile *)v37,
          a4,
          &v28,
          (LPVOID **)&pv,
          &v32,
          &v30,
          &v29,
          &v33);
  if ( !v15 )
    v15 = CPackageDefinitionFile::InstallPackage(
            (CPDFPackage *)v37,
            String1,
            String2,
            v35,
            v34,
            (__int64)a1,
            v27,
            a7 & 1,
            *a8,
            *a9);
  v16 = 0;
  v17 = pv;
  v18 = v28;
  if ( v28 )
  {
    v19 = v32;
    do
    {
      v20 = (void *)v17[v16];
      if ( v20 )
      {
        CoTaskMemFree(v20);
        v17[v16] = 0;
      }
      v21 = v19[v16];
      if ( v21 )
      {
        CoTaskMemFree(v21);
        v19[v16] = 0;
      }
      ++v16;
    }
    while ( v16 < v18 );
  }
  if ( v17 )
    CoTaskMemFree(v17);
  v22 = 0;
  v23 = v33;
  for ( i = v29; v22 < i; ++v22 )
  {
    v25 = v23[v22];
    if ( v25 )
    {
      CoTaskMemFree(v25);
      v23[v22] = 0;
    }
  }
  if ( v23 )
    CoTaskMemFree(v23);
  CPackageDefinitionFile::~CPackageDefinitionFile((CPackageDefinitionFile *)v37);
  return v15;
}

```

## disassembly

```asm
0x18003d4bc  push    rbp
0x18003d4be  push    rbx
0x18003d4bf  push    rsi
0x18003d4c0  push    rdi
0x18003d4c1  push    r12
0x18003d4c3  push    r13
0x18003d4c5  push    r14
0x18003d4c7  push    r15
0x18003d4c9  lea     rbp, [rsp-0E8h]
0x18003d4d1  sub     rsp, 1E8h
0x18003d4d8  mov     rax, cs:__security_cookie
0x18003d4df  xor     rax, rsp
0x18003d4e2  mov     [rbp+120h+var_50], rax
0x18003d4e9  mov     r14, r9
0x18003d4ec  mov     r13, r8
0x18003d4ef  mov     r15, rdx
0x18003d4f2  mov     rsi, rcx
0x18003d4f5  mov     rax, [rbp+120h+arg_20]
0x18003d4fc  mov     [rbp+120h+var_1A0], rax
0x18003d500  mov     rax, [rbp+120h+arg_28]
0x18003d507  mov     [rsp+220h+var_1A8], rax
0x18003d50c  mov     rdi, [rbp+120h+arg_38]
0x18003d513  mov     rbx, [rbp+120h+arg_40]
0x18003d51a  mov     ecx, 1
0x18003d51f  call    ??$UploadSQMData@W4CatalogServerSQMFlags@@@@YAXW4CatalogServerSQMFlags@@@Z; UploadSQMData<CatalogServerSQMFlags>(CatalogServerSQMFlags)
0x18003d524  lea     rdx, [rsi+60h]; struct _GUID *
0x18003d528  lea     rcx, [rbp+120h+var_190]; this
0x18003d52c  call    ??0CPackageDefinitionFile@@QEAA@AEBU_GUID@@@Z; CPackageDefinitionFile::CPackageDefinitionFile(_GUID const &)
0x18003d531  nop
0x18003d532  xor     r12d, r12d
0x18003d535  mov     [rsp+220h+var_1D0], r12d
0x18003d53a  mov     [rsp+220h+pv], r12
0x18003d53f  mov     [rsp+220h+var_1B8], r12
0x18003d544  mov     [rsp+220h+var_1C8], r12d
0x18003d549  mov     [rsp+220h+var_1CC], r12d
0x18003d54e  mov     [rsp+220h+var_1B0], r12
0x18003d553  lea     ecx, [r12+20h]; cb
0x18003d558  call    cs:__imp_CoTaskMemAlloc
0x18003d55e  mov     [rbp+120h+var_198], rax
0x18003d562  test    rax, rax
0x18003d565  jz      loc_18003D6E1
0x18003d56b  lea     rdx, ??_7?$CArray@PEAUDllInfo@@AEBQEAU1@@@6B@; const CArray<DllInfo *,DllInfo * const &>::`vftable'
0x18003d572  mov     [rax], rdx
0x18003d575  mov     [rax+8], r12
0x18003d579  mov     [rax+14h], r12
0x18003d57d  mov     [rax+10h], r12d
0x18003d581  mov     [rdi], rax
0x18003d584  lea     ecx, [r12+20h]; cb
0x18003d589  call    cs:__imp_CoTaskMemAlloc
0x18003d58f  mov     [rbp+120h+var_198], rax
0x18003d593  test    rax, rax
0x18003d596  jz      loc_18003D6DC
0x18003d59c  lea     rcx, ??_7?$CArray@PEAUCompInfo@@AEBQEAU1@@@6B@; const CArray<CompInfo *,CompInfo * const &>::`vftable'
0x18003d5a3  mov     [rax], rcx
0x18003d5a6  mov     [rax+8], r12
0x18003d5aa  mov     [rax+14h], r12
0x18003d5ae  mov     [rax+10h], r12d
0x18003d5b2  mov     [rbx], rax
0x18003d5b5  lea     rax, [rsp+220h+var_1B0]
0x18003d5ba  mov     [rsp+220h+var_1E8], rax; unsigned __int16 ***
0x18003d5bf  lea     rax, [rsp+220h+var_1CC]
0x18003d5c4  mov     [rsp+220h+var_1F0], rax; int
0x18003d5c9  lea     rax, [rsp+220h+var_1C8]
0x18003d5ce  mov     [rsp+220h+var_1F8], rax; unsigned int *
0x18003d5d3  lea     rax, [rsp+220h+var_1B8]
0x18003d5d8  mov     [rsp+220h+var_200], rax; unsigned __int16 ***
0x18003d5dd  lea     r9, [rsp+220h+pv]; unsigned __int16 ***
0x18003d5e2  lea     r8, [rsp+220h+var_1D0]; unsigned int *
0x18003d5e7  mov     rdx, r14; unsigned __int16 *
0x18003d5ea  lea     rcx, [rbp+120h+var_190]; this
0x18003d5ee  call    ?QueryPackageFromFile@CPackageDefinitionFile@@QEAAJPEAGPEAKPEAPEAPEAG2112@Z; CPackageDefinitionFile::QueryPackageFromFile(ushort *,ulong *,ushort * * *,ushort * * *,ulong *,ulong *,ushort * * *)
0x18003d5f3  mov     r12d, eax
0x18003d5f6  test    eax, eax
0x18003d5f8  jnz     short loc_18003D63C
0x18003d5fa  mov     ecx, dword ptr [rbp+120h+arg_30]
0x18003d600  and     ecx, 1
0x18003d603  mov     rax, [rbx]
0x18003d606  mov     [rsp+220h+var_1D8], rax; __int64
0x18003d60b  mov     rax, [rdi]
0x18003d60e  mov     [rsp+220h+var_1E0], rax; __int64
0x18003d613  mov     dword ptr [rsp+220h+var_1E8], ecx; int
0x18003d617  mov     [rsp+220h+var_1F8], rsi; __int64
0x18003d61c  mov     rax, [rsp+220h+var_1A8]
0x18003d621  mov     [rsp+220h+var_200], rax; unsigned __int16 *
0x18003d626  mov     r9, [rbp+120h+var_1A0]; unsigned __int16 *
0x18003d62a  mov     r8, r13; String2
0x18003d62d  mov     rdx, r15; String1
0x18003d630  lea     rcx, [rbp+120h+var_190]; this
0x18003d634  call    ?InstallPackage@CPackageDefinitionFile@@QEAAJPEAG000PEAVCAppImport@@HHPEAV?$CArray@PEAUFileInfo@@AEBQEAU1@@@PEAV?$CArray@PEAUCompInfo@@AEBQEAU1@@@@Z; CPackageDefinitionFile::InstallPackage(ushort *,ushort *,ushort *,ushort *,CAppImport *,int,int,CArray<FileInfo *,FileInfo * const &> *,CArray<CompInfo *,CompInfo * const &> *)
0x18003d639  mov     r12d, eax
0x18003d63c  xor     r13d, r13d
0x18003d63f  mov     edi, r13d
0x18003d642  mov     rbx, [rsp+220h+pv]
0x18003d647  mov     r14d, [rsp+220h+var_1D0]
0x18003d64c  test    r14d, r14d
0x18003d64f  jz      short loc_18003D685
0x18003d651  mov     r15, [rsp+220h+var_1B8]
0x18003d656  mov     esi, edi
0x18003d658  mov     rcx, [rbx+rsi*8]; pv
0x18003d65c  test    rcx, rcx
0x18003d65f  jz      short loc_18003D66B
0x18003d661  call    cs:__imp_CoTaskMemFree
0x18003d667  mov     [rbx+rsi*8], r13
0x18003d66b  mov     rcx, [r15+rsi*8]; pv
0x18003d66f  test    rcx, rcx
0x18003d672  jz      short loc_18003D67E
0x18003d674  call    cs:__imp_CoTaskMemFree
0x18003d67a  mov     [r15+rsi*8], r13
0x18003d67e  inc     edi
0x18003d680  cmp     edi, r14d
0x18003d683  jb      short loc_18003D656
0x18003d685  test    rbx, rbx
0x18003d688  jz      short loc_18003D693
0x18003d68a  mov     rcx, rbx; pv
0x18003d68d  call    cs:__imp_CoTaskMemFree
0x18003d693  mov     edi, r13d
0x18003d696  mov     rbx, [rsp+220h+var_1B0]
0x18003d69b  mov     esi, [rsp+220h+var_1CC]
0x18003d69f  test    esi, esi
0x18003d6a1  jz      short loc_18003D6BF
0x18003d6a3  mov     r14d, edi
0x18003d6a6  mov     rcx, [rbx+r14*8]; pv
0x18003d6aa  test    rcx, rcx
0x18003d6ad  jz      short loc_18003D6B9
0x18003d6af  call    cs:__imp_CoTaskMemFree
0x18003d6b5  mov     [rbx+r14*8], r13
0x18003d6b9  inc     edi
0x18003d6bb  cmp     edi, esi
0x18003d6bd  jb      short loc_18003D6A3
0x18003d6bf  test    rbx, rbx
0x18003d6c2  jz      short loc_18003D6CE
0x18003d6c4  mov     rcx, rbx; pv
0x18003d6c7  call    cs:__imp_CoTaskMemFree
0x18003d6cd  nop
0x18003d6ce  lea     rcx, [rbp+120h+var_190]; this
0x18003d6d2  call    ??1CPackageDefinitionFile@@QEAA@XZ; CPackageDefinitionFile::~CPackageDefinitionFile(void)
0x18003d6d7  mov     eax, r12d
0x18003d6da  jmp     short loc_18003D6F2
0x18003d6dc  mov     [rbx], r12
0x18003d6df  jmp     short loc_18003D6E4
0x18003d6e1  mov     [rdi], r12
0x18003d6e4  lea     rcx, [rbp+120h+var_190]; this
0x18003d6e8  call    ??1CPackageDefinitionFile@@QEAA@XZ; CPackageDefinitionFile::~CPackageDefinitionFile(void)
0x18003d6ed  mov     eax, 8007000Eh
0x18003d6f2  mov     rcx, [rbp+120h+var_50]
0x18003d6f9  xor     rcx, rsp; StackCookie
0x18003d6fc  call    __security_check_cookie
0x18003d701  add     rsp, 1E8h
0x18003d708  pop     r15
0x18003d70a  pop     r14
0x18003d70c  pop     r13
0x18003d70e  pop     r12
0x18003d710  pop     rdi
0x18003d711  pop     rsi
0x18003d712  pop     rbx
0x18003d713  pop     rbp
0x18003d714  retn
```
