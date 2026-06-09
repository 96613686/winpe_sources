# CPackageDefinitionFile::InstallPackage(ushort *,ushort *,ushort *,ushort *,CAppImport *,int,int,CArray<FileInfo *,FileInfo * const &> *,CArray<CompInfo *,CompInfo * const &> *)

- ea: `0x1800474b0`
- end: `0x18004777f`
- name: `?InstallPackage@CPackageDefinitionFile@@QEAAJPEAG000PEAVCAppImport@@HHPEAV?$CArray@PEAUFileInfo@@AEBQEAU1@@@PEAV?$CArray@PEAUCompInfo@@AEBQEAU1@@@@Z`
- size: `719`
- prototype: `__int64 __fastcall(CPDFPackage *this, wchar_t *String1, wchar_t *String2, unsigned __int16 *, unsigned __int16 *, __int64, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003d4bc`

## callees

- `0x18003a604`
- `0x18003a77c`
- `0x18003c0f0`
- `0x18003d92c`
- `0x18003e5e4`
- `0x180042bb8`
- `0x180044bf0`
- `0x18004557c`
- `0x180045954`
- `0x180045c70`
- `0x1800474b0`
- `0x180055550`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004753e`
- `msvcrt!_wcsicmp` at `0x18004753e`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18004766e`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18004766e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800475c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800475c4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800476d4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800476d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047610`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall CPackageDefinitionFile::InstallPackage(
        CPDFPackage *this,
        wchar_t *String1,
        wchar_t *String2,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v12; // r15
  int result; // eax
  CAppImport *v14; // rcx
  _QWORD *v15; // rdi
  _QWORD *v16; // r15
  _QWORD *v17; // r12
  struct CString *v18; // rdx
  int NameAndCopy; // eax
  unsigned int v20; // edx
  int v21; // ebx
  FileInfo *v22; // rax
  FileInfo *v23; // rbx
  __int64 v24; // r15
  unsigned int v25; // edx
  unsigned int v26; // edx
  unsigned int v27; // edi
  int v28; // eax
  int v29; // edi
  int v30; // [rsp+40h] [rbp-B8h]
  unsigned int v31[3]; // [rsp+44h] [rbp-B4h] BYREF
  GUID v32; // [rsp+50h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-98h] BYREF
  unsigned __int16 *v34; // [rsp+68h] [rbp-90h]
  DllInfo *v35; // [rsp+70h] [rbp-88h]
  __int64 v36; // [rsp+78h] [rbp-80h]
  unsigned __int16 *v37; // [rsp+80h] [rbp-78h]
  __int64 v38; // [rsp+88h] [rbp-70h]
  FileInfo *v39; // [rsp+90h] [rbp-68h]
  GUID pclsid; // [rsp+A0h] [rbp-58h] BYREF

  v37 = String2;
  v34 = String1;
  v38 = a6;
  v12 = a10;
  v36 = a10;
  pv = 0;
  v31[0] = 0;
  pclsid = GUID_NULL;
  v30 = _wcsicmp(String1, String2);
  result = CPDFPackage::ImportPackageToProvider(this, (CPDFPackage *)((char *)this + 224), a4, a5);
  if ( !result )
  {
    if ( *((_DWORD *)this + 68) )
    {
      v15 = (_QWORD *)*((_QWORD *)this + 32);
      while ( v15 )
      {
        v16 = (_QWORD *)*v15;
        v17 = v15 + 2;
        v32.Data1 = 1;
        *(_QWORD *)v32.Data4 = 0;
        v18 = (struct CString *)(v15 + 2);
        if ( v30 )
          NameAndCopy = CAppImport::GetNameAndCopy(v14, v18, v34, v37, a8);
        else
          NameAndCopy = CAppImport::VerifyFileExists(v14, v18, v34);
        v21 = NameAndCopy;
        if ( NameAndCopy )
          goto LABEL_8;
        v15 = v16;
        v22 = (FileInfo *)CoTaskMemAlloc(0x10u);
        v39 = v22;
        if ( v22 )
          v23 = FileInfo::FileInfo(v22);
        else
          v23 = 0;
        v35 = v23;
        *(_QWORD *)v32.Data4 = v23;
        if ( !v23 )
        {
          v21 = -2147024882;
LABEL_8:
          CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v32, v20);
          goto LABEL_9;
        }
        v24 = *(int *)(a9 + 16);
        if ( (int)v24 >= 0 )
        {
          try
          {
            CArray<DllInfo *,DllInfo * const &>::SetSize(a9, v24 + 1);
            *(_QWORD *)(*(_QWORD *)(a9 + 8) + 8 * v24) = v23;
          }
          catch ( ... )
          {
            DllInfo::`scalar deleting destructor'(v35);
            CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v32, v26);
            v21 = -2147024882;
LABEL_9:
            if ( pv )
              CoTaskMemFree(pv);
            return v21;
          }
        }
        CString::operator=(v23, v17);
        *((_DWORD *)v23 + 3) = 0;
        v32.Data1 = 0;
        CPtr<FileInfo>::~CPtr<FileInfo>((__int64)&v32, v25);
      }
      v21 = CPDFPackage::AddCLSIDsToList(this, &pv, v31);
      if ( v21 )
        goto LABEL_9;
      v27 = v31[0];
      if ( v31[0] )
      {
        v21 = CLSIDFromString(*(LPCOLESTR *)this, &pclsid);
        if ( v21 )
          goto LABEL_9;
        v32 = pclsid;
        v12 = v36;
        v21 = CAppImport::RegisterImportedModules(v38, (__int128 *)&v32, 64, (__int64)pv, v27, a9, v36, 3);
        if ( v21 )
          goto LABEL_9;
      }
      else
      {
        v12 = v36;
      }
    }
    v28 = CPDFPackage::ImportComponentsAndRolesToProvider(this, v12);
    v21 = v28;
    if ( v28 < 0 )
      goto LABEL_9;
    v29 = v28;
    if ( *((float *)this + 76) >= 2.0 )
    {
      v21 = CPDFPackage::ImportFinalProperties(this);
      if ( v21 )
        goto LABEL_9;
    }
    return v29;
  }
  return result;
}

```

## disassembly

```asm
0x1800474b0  push    rbx
0x1800474b2  push    rdi
0x1800474b3  push    r12
0x1800474b5  push    r13
0x1800474b7  push    r14
0x1800474b9  push    r15
0x1800474bb  sub     rsp, 0C8h
0x1800474c2  mov     rax, cs:__security_cookie
0x1800474c9  xor     rax, rsp
0x1800474cc  mov     [rsp+0F8h+var_48], rax
0x1800474d4  mov     rdi, r9
0x1800474d7  mov     [rsp+0F8h+var_78], r8
0x1800474df  mov     rax, rdx
0x1800474e2  mov     [rsp+0F8h+var_90], rdx
0x1800474e7  mov     r14, rcx
0x1800474ea  mov     rbx, [rsp+0F8h+arg_20]
0x1800474f2  mov     r12, [rsp+0F8h+arg_28]
0x1800474fa  mov     [rsp+0F8h+var_70], r12
0x180047502  mov     r13, [rsp+0F8h+arg_40]
0x18004750a  mov     r15, [rsp+0F8h+arg_48]
0x180047512  mov     [rsp+0F8h+var_80], r15
0x180047517  mov     [rsp+0F8h+pv], 0
0x180047520  mov     [rsp+0F8h+var_B4], 0
0x180047528  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004752f  movdqu  xmmword ptr [rsp+0F8h+pclsid.Data1], xmm0
0x180047538  mov     rdx, r8; String2
0x18004753b  mov     rcx, rax; String1
0x18004753e  call    cs:__imp__wcsicmp
0x180047544  mov     [rsp+0F8h+var_B8], eax
0x180047548  lea     rdx, [r14+0E0h]; struct CString *
0x18004754f  mov     r9, rbx; unsigned __int16 *
0x180047552  mov     r8, rdi; unsigned __int16 *
0x180047555  mov     rcx, r14; this
0x180047558  call    ?ImportPackageToProvider@CPDFPackage@@QEAAJAEAVCString@@PEAG1@Z; CPDFPackage::ImportPackageToProvider(CString &,ushort *,ushort *)
0x18004755d  test    eax, eax
0x18004755f  jnz     short loc_1800475CC
0x180047561  cmp     [r14+110h], eax
0x180047568  jz      loc_180047739
0x18004756e  mov     rdi, [r14+100h]
0x180047575  test    rdi, rdi
0x180047578  jz      loc_1800476A5
0x18004757e  mov     r15, [rdi]
0x180047581  lea     r12, [rdi+10h]
0x180047585  mov     dword ptr [rsp+0F8h+var_A8], 1
0x18004758d  mov     qword ptr [rsp+0F8h+var_A8+8], 0
0x180047596  mov     r8, [rsp+0F8h+var_90]; unsigned __int16 *
0x18004759b  mov     rdx, r12; struct CString *
0x18004759e  cmp     [rsp+0F8h+var_B8], 0
0x1800475a3  jnz     short loc_1800475EE
0x1800475a5  call    ?VerifyFileExists@CAppImport@@QEAAJAEAVCString@@PEAG@Z; CAppImport::VerifyFileExists(CString &,ushort *)
0x1800475aa  mov     ebx, eax
0x1800475ac  test    eax, eax
0x1800475ae  jz      short loc_180047608
0x1800475b0  lea     rcx, [rsp+0F8h+var_A8]
0x1800475b5  call    ??1?$CPtr@UFileInfo@@@@QEAA@XZ; CPtr<FileInfo>::~CPtr<FileInfo>(void)
0x1800475ba  mov     rcx, [rsp+0F8h+pv]; pv
0x1800475bf  test    rcx, rcx
0x1800475c2  jz      short loc_1800475CA
0x1800475c4  call    cs:__imp_CoTaskMemFree
0x1800475ca  mov     eax, ebx
0x1800475cc  mov     rcx, [rsp+0F8h+var_48]
0x1800475d4  xor     rcx, rsp; StackCookie
0x1800475d7  call    __security_check_cookie
0x1800475dc  add     rsp, 0C8h
0x1800475e3  pop     r15
0x1800475e5  pop     r14
0x1800475e7  pop     r13
0x1800475e9  pop     r12
0x1800475eb  pop     rdi
0x1800475ec  pop     rbx
0x1800475ed  retn
0x1800475ee  mov     eax, [rsp+0F8h+arg_38]
0x1800475f5  mov     [rsp+0F8h+var_D8], eax; int
0x1800475f9  mov     r9, [rsp+0F8h+var_78]; unsigned __int16 *
0x180047601  call    ?GetNameAndCopy@CAppImport@@QEAAJAEAVCString@@PEAG1H@Z; CAppImport::GetNameAndCopy(CString &,ushort *,ushort *,int)
0x180047606  jmp     short loc_1800475AA
0x180047608  mov     rdi, r15
0x18004760b  mov     ecx, 10h; cb
0x180047610  call    cs:__imp_CoTaskMemAlloc
0x180047616  mov     [rsp+0F8h+var_68], rax
0x18004761e  test    rax, rax
0x180047621  jz      short loc_180047630
0x180047623  mov     rcx, rax; this
0x180047626  call    ??0FileInfo@@QEAA@XZ; FileInfo::FileInfo(void)
0x18004762b  mov     rbx, rax
0x18004762e  jmp     short loc_180047632
0x180047630  xor     ebx, ebx
0x180047632  mov     [rsp+0F8h+var_88], rbx
0x180047637  mov     qword ptr [rsp+0F8h+var_A8+8], rbx
0x18004763c  test    rbx, rbx
0x18004763f  jnz     short loc_18004764B
0x180047641  mov     ebx, 8007000Eh
0x180047646  jmp     loc_1800475B0
0x18004764b  movsxd  r15, dword ptr [r13+10h]
0x18004764f  test    r15d, r15d
0x180047652  js      short loc_180047668
0x180047654  lea     edx, [r15+1]
0x180047658  mov     rcx, r13
0x18004765b  call    ?SetSize@?$CArray@PEAUDllInfo@@AEBQEAU1@@@QEAAXHH@Z; CArray<DllInfo *,DllInfo * const &>::SetSize(int,int)
0x180047660  mov     rax, [r13+8]
0x180047664  mov     [rax+r15*8], rbx
0x180047668  mov     rdx, r12
0x18004766b  mov     rcx, rbx
0x18004766e  call    cs:__imp_??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x180047674  mov     dword ptr [rbx+0Ch], 0
0x18004767b  mov     dword ptr [rsp+0F8h+var_A8], 0
0x180047683  lea     rcx, [rsp+0F8h+var_A8]
0x180047688  call    ??1?$CPtr@UFileInfo@@@@QEAA@XZ; CPtr<FileInfo>::~CPtr<FileInfo>(void)
0x18004768d  jmp     loc_180047575
0x180047692  lea     rcx, [rsp+0F8h+var_A8]
0x180047697  call    ??1?$CPtr@UFileInfo@@@@QEAA@XZ; CPtr<FileInfo>::~CPtr<FileInfo>(void)
0x18004769c  mov     ebx, [rsp+0F8h+var_B8]
0x1800476a0  jmp     loc_1800475BA
0x1800476a5  lea     r8, [rsp+0F8h+var_B4]; unsigned int *
0x1800476aa  lea     rdx, [rsp+0F8h+pv]; struct _GUID **
0x1800476af  mov     rcx, r14; this
0x1800476b2  call    ?AddCLSIDsToList@CPDFPackage@@QEAAJPEAPEAU_GUID@@PEAK@Z; CPDFPackage::AddCLSIDsToList(_GUID * *,ulong *)
0x1800476b7  mov     ebx, eax
0x1800476b9  test    eax, eax
0x1800476bb  jnz     loc_1800475BA
0x1800476c1  mov     edi, [rsp+0F8h+var_B4]
0x1800476c5  test    edi, edi
0x1800476c7  jz      short loc_180047734
0x1800476c9  lea     rdx, [rsp+0F8h+pclsid]; pclsid
0x1800476d1  mov     rcx, [r14]; lpsz
0x1800476d4  call    cs:__imp_CLSIDFromString
0x1800476da  mov     ebx, eax
0x1800476dc  test    eax, eax
0x1800476de  jnz     loc_1800475BA
0x1800476e4  movaps  xmm0, xmmword ptr [rsp+0F8h+pclsid.Data1]
0x1800476ec  movdqa  [rsp+0F8h+var_A8], xmm0
0x1800476f2  mov     [rsp+0F8h+var_C0], 3
0x1800476fa  mov     r15, [rsp+0F8h+var_80]
0x1800476ff  mov     [rsp+0F8h+var_C8], r15
0x180047704  mov     [rsp+0F8h+var_D0], r13
0x180047709  mov     [rsp+0F8h+var_D8], edi
0x18004770d  mov     r9, [rsp+0F8h+pv]
0x180047712  lea     r8d, [rax+40h]
0x180047716  lea     rdx, [rsp+0F8h+var_A8]
0x18004771b  mov     rcx, [rsp+0F8h+var_70]
0x180047723  call    ?RegisterImportedModules@CAppImport@@QEAAJU_GUID@@KPEAU2@KPEAV?$CArray@PEAUFileInfo@@AEBQEAU1@@@PEAV?$CArray@PEAUCompInfo@@AEBQEAU1@@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z; CAppImport::RegisterImportedModules(_GUID,ulong,_GUID *,ulong,CArray<FileInfo *,FileInfo * const &> *,CArray<CompInfo *,CompInfo * const &> *,__MIDL___MIDL_itf_registrar_0000_0000_0001)
0x180047728  mov     ebx, eax
0x18004772a  test    eax, eax
0x18004772c  jnz     loc_1800475BA
0x180047732  jmp     short loc_180047739
0x180047734  mov     r15, [rsp+0F8h+var_80]
0x180047739  mov     rdx, r15
0x18004773c  mov     rcx, r14
0x18004773f  call    ?ImportComponentsAndRolesToProvider@CPDFPackage@@QEAAJPEAV?$CArray@PEAUCompInfo@@AEBQEAU1@@@H@Z; CPDFPackage::ImportComponentsAndRolesToProvider(CArray<CompInfo *,CompInfo * const &> *,int)
0x180047744  mov     ebx, eax
0x180047746  test    eax, eax
0x180047748  js      loc_1800475BA
0x18004774e  mov     edi, eax
0x180047750  movss   xmm0, dword ptr [r14+130h]
0x180047759  cvtps2pd xmm0, xmm0
0x18004775c  comisd  xmm0, cs:__real@4000000000000000
0x180047764  jb      short loc_180047778
0x180047766  mov     rcx, r14; this
0x180047769  call    ?ImportFinalProperties@CPDFPackage@@QEAAJXZ; CPDFPackage::ImportFinalProperties(void)
0x18004776e  mov     ebx, eax
0x180047770  test    eax, eax
0x180047772  jnz     loc_1800475BA
0x180047778  mov     eax, edi
0x18004777a  jmp     loc_1800475CC
```
