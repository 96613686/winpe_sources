# CPackageDefinitionFile::QueryPackageFromFile(ushort *,ulong *,ushort * * *,ushort * * *,ulong *,ulong *,ushort * * *)

- ea: `0x18004859c`
- end: `0x180048956`
- name: `?QueryPackageFromFile@CPackageDefinitionFile@@QEAAJPEAGPEAKPEAPEAPEAG2112@Z`
- size: `954`
- prototype: `__int64 __usercall@<rax>(CPackageDefinitionFile *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned int *@<r8>, unsigned __int16 ***@<r9>, unsigned __int16 ***, unsigned int *, unsigned int *, unsigned __int16 ***)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d4bc`
- `0x1800434f0`
- `0x180043900`

## callees

- `0x180009ee0`
- `0x18000a01c`
- `0x18001a6c8`
- `0x180045344`
- `0x18004538c`
- `0x180047fd8`
- `0x18004859c`
- `0x180048e10`
- `0x180055550`

## import_xrefs

- `msvcrt!swscanf` at `0x180048660`
- `msvcrt!swscanf` at `0x1800486c6`
- `msvcrt!swscanf` at `0x180048660`
- `msvcrt!swscanf` at `0x1800486c6`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180048603`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180048775`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180048603`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180048775`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048838`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048841`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048855`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004885e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048892`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048838`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048841`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048855`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004885e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048892`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800487de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004880e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800488bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800488e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800487de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004880e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800488bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800488e7`

## pseudocode

```c
__int64 __fastcall CPackageDefinitionFile::QueryPackageFromFile(
        CPackageDefinitionFile *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        LPVOID **a4,
        unsigned __int16 ***a5,
        unsigned int *a6,
        unsigned int *a7,
        unsigned __int16 ***a8)
{
  const unsigned __int16 **v8; // rsi
  unsigned int *v11; // rax
  CPackageDefinitionFile *v12; // rcx
  unsigned int v13; // esi
  float v14; // xmm1_4
  float v15; // xmm2_4
  __int64 result; // rax
  int v17; // ebx
  unsigned __int16 **v18; // rax
  unsigned __int64 v19; // rbx
  unsigned __int16 *v20; // rcx
  unsigned int *v21; // r15
  unsigned int i; // edi
  unsigned __int16 **v23; // rax
  unsigned __int64 v24; // rbx
  unsigned __int16 *v25; // rcx
  bool v26; // zf
  unsigned __int16 *v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+28h] [rbp-D8h]
  float v29; // [rsp+30h] [rbp-D0h] BYREF
  float v30; // [rsp+34h] [rbp-CCh] BYREF
  int v31; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int *v32; // [rsp+40h] [rbp-C0h]
  unsigned int *v33; // [rsp+48h] [rbp-B8h]
  wchar_t Buffer[24]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v35[56]; // [rsp+80h] [rbp-80h] BYREF

  v8 = (const unsigned __int16 **)((char *)this + 232);
  v32 = a3;
  v33 = a7;
  v29 = 0.0;
  v30 = 0.0;
  CString::operator=((char *)this + 232, a2);
  v11 = v32;
  *a4 = 0;
  *a5 = 0;
  *a8 = 0;
  *a6 = 0;
  *v11 = 0;
  *a7 = 0;
  if ( ReadStringFromPDF(L"Packages", L"Version", Buffer, 0x14u, *v8) )
    return 2148598792LL;
  v13 = 1;
  if ( (unsigned int)(swscanf(Buffer, L"%f", &v29) + 1) <= 1 )
    return 2148598792LL;
  v14 = v29;
  if ( v29 < 2.0 )
  {
    v15 = FLOAT_1_0;
    v30 = FLOAT_1_0;
    goto LABEL_8;
  }
  if ( ReadStringFromPDF(L"Packages", L"ExtendedVersion", Buffer, 0x14u, *((const unsigned __int16 **)this + 29))
    || (unsigned int)(swscanf(Buffer, L"%f", &v30) + 1) <= 1 )
  {
    return 2148598792LL;
  }
  v14 = v29;
  v15 = v30;
LABEL_8:
  if ( v15 < v14 )
    return 2148598792LL;
  result = CPackageDefinitionFile::CheckPDFVersion(v12, v14, v15, (float *)this + 76);
  if ( (int)result < 0 )
    return result;
  LODWORD(v27) = 1;
  v17 = StringCchPrintfW(Buffer, 0x14u, L"%s%lu", L"Package", v27);
  if ( v17 < 0 )
    goto LABEL_18;
  if ( ReadStringFromPDF(L"Packages", Buffer, v35, 0x32u, *((const unsigned __int16 **)this + 29)) )
    return 2148598792LL;
  CString::operator=((char *)this + 224, v35);
  v28 = *((_DWORD *)this + 76);
  v31 = 0;
  result = CPDFPackage::LoadFromPDF(this, (CPackageDefinitionFile *)((char *)this + 232), &v31, v28);
  if ( !(_DWORD)result )
  {
    result = CreateArrayFromFileList((__int64)this + 248, (LPVOID *)a8, v33);
    if ( (int)result >= 0 )
    {
      v18 = (unsigned __int16 **)CoTaskMemAlloc(8u);
      *a5 = v18;
      if ( !v18 )
        return 2147942414LL;
      *v18 = 0;
      v19 = (int)(safe_lstrlenW(*((const unsigned __int16 **)this + 2)) + 2);
      **a5 = (unsigned __int16 *)CoTaskMemAlloc(2 * v19);
      v20 = **a5;
      if ( !v20 )
        goto LABEL_17;
      v17 = StringCchCopyW(v20, v19, *((const unsigned __int16 **)this + 2));
      if ( v17 < 0 )
        goto LABEL_18;
      v23 = (unsigned __int16 **)CoTaskMemAlloc(8u);
      *a4 = (LPVOID *)v23;
      if ( v23
        && (*v23 = 0,
            v24 = (int)(safe_lstrlenW(*((const unsigned __int16 **)this + 1)) + 2),
            **a4 = CoTaskMemAlloc(2 * v24),
            (v25 = (unsigned __int16 *)**a4) != 0) )
      {
        v17 = StringCchCopyW(v25, v24, *((const unsigned __int16 **)this + 1));
        if ( v17 >= 0 )
        {
          v26 = v31 == 0;
          *v32 = 1;
          if ( v26 )
            v13 = 0;
          *a6 = v13;
          return (unsigned int)v17;
        }
      }
      else
      {
LABEL_17:
        v17 = -2147024882;
      }
LABEL_18:
      if ( *a5 )
      {
        CoTaskMemFree(**a5);
        CoTaskMemFree(*a5);
        *a5 = 0;
      }
      if ( *a4 )
      {
        CoTaskMemFree(**a4);
        CoTaskMemFree(*a4);
        *a4 = 0;
      }
      if ( *a8 )
      {
        v21 = v33;
        for ( i = 0; i < *v21; ++i )
          CoTaskMemFree((*a8)[i]);
        CoTaskMemFree(*a8);
        *a8 = 0;
      }
      return (unsigned int)v17;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004859c  push    rbp
0x18004859e  push    rbx
0x18004859f  push    rsi
0x1800485a0  push    rdi
0x1800485a1  push    r12
0x1800485a3  push    r13
0x1800485a5  push    r14
0x1800485a7  push    r15
0x1800485a9  lea     rbp, [rsp-8]
0x1800485ae  sub     rsp, 108h
0x1800485b5  mov     rax, cs:__security_cookie
0x1800485bc  xor     rax, rsp
0x1800485bf  mov     [rbp+40h+var_50], rax
0x1800485c3  mov     rbx, [rbp+40h+arg_30]
0x1800485ca  lea     rsi, [rcx+0E8h]
0x1800485d1  mov     r15, [rbp+40h+arg_20]
0x1800485d5  mov     r13, rcx
0x1800485d8  mov     r12, [rbp+40h+arg_28]
0x1800485dc  mov     rcx, rsi
0x1800485df  mov     r14, [rbp+40h+arg_38]
0x1800485e6  mov     rdi, r9
0x1800485e9  mov     [rsp+140h+var_100], r8
0x1800485ee  mov     [rsp+140h+var_F8], rbx
0x1800485f3  mov     [rsp+140h+var_110], 0
0x1800485fb  mov     [rsp+140h+var_10C], 0
0x180048603  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180048609  mov     rax, [rsp+140h+var_100]
0x18004860e  lea     r8, [rsp+140h+Buffer]; unsigned __int16 *
0x180048613  xor     ecx, ecx
0x180048615  lea     rdx, aVersion; "Version"
0x18004861c  mov     [rdi], rcx
0x18004861f  mov     [r15], rcx
0x180048622  mov     [r14], rcx
0x180048625  mov     [r12], ecx
0x180048629  mov     [rax], ecx
0x18004862b  mov     [rbx], ecx
0x18004862d  lea     ebx, [rcx+14h]
0x180048630  mov     rax, [rsi]
0x180048633  lea     rcx, aPackages; "Packages"
0x18004863a  mov     r9d, ebx; unsigned int
0x18004863d  mov     [rsp+140h+var_120], rax; unsigned __int16 *
0x180048642  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180048647  test    eax, eax
0x180048649  jnz     loc_180048931
0x18004864f  lea     r8, [rsp+140h+var_110]
0x180048654  lea     rdx, asc_180067A94; "%f"
0x18004865b  lea     rcx, [rsp+140h+Buffer]; Buffer
0x180048660  call    cs:__imp_swscanf
0x180048666  inc     eax
0x180048668  lea     esi, [rbx-13h]
0x18004866b  cmp     eax, esi
0x18004866d  jbe     loc_180048931
0x180048673  movss   xmm1, [rsp+140h+var_110]; float
0x180048679  cvtps2pd xmm0, xmm1
0x18004867c  comisd  xmm0, cs:__real@4000000000000000
0x180048684  jb      short loc_1800486E4
0x180048686  mov     rax, [r13+0E8h]
0x18004868d  lea     r8, [rsp+140h+Buffer]; unsigned __int16 *
0x180048692  mov     r9d, ebx; unsigned int
0x180048695  mov     [rsp+140h+var_120], rax; unsigned __int16 *
0x18004869a  lea     rdx, aExtendedversio; "ExtendedVersion"
0x1800486a1  lea     rcx, aPackages; "Packages"
0x1800486a8  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x1800486ad  test    eax, eax
0x1800486af  jnz     loc_180048931
0x1800486b5  lea     r8, [rsp+140h+var_10C]
0x1800486ba  lea     rdx, asc_180067A94; "%f"
0x1800486c1  lea     rcx, [rsp+140h+Buffer]; Buffer
0x1800486c6  call    cs:__imp_swscanf
0x1800486cc  inc     eax
0x1800486ce  cmp     eax, esi
0x1800486d0  jbe     loc_180048931
0x1800486d6  movss   xmm1, [rsp+140h+var_110]
0x1800486dc  movss   xmm2, [rsp+140h+var_10C]
0x1800486e2  jmp     short loc_1800486F2
0x1800486e4  movss   xmm2, cs:__real@3f800000; float
0x1800486ec  movss   [rsp+140h+var_10C], xmm2
0x1800486f2  comiss  xmm2, xmm1
0x1800486f5  jb      loc_180048931
0x1800486fb  lea     r9, [r13+130h]; float *
0x180048702  call    ?CheckPDFVersion@CPackageDefinitionFile@@AEAAJMMPEAM@Z; CPackageDefinitionFile::CheckPDFVersion(float,float,float *)
0x180048707  test    eax, eax
0x180048709  js      loc_180048936
0x18004870f  lea     r9, aPackage; "Package"
0x180048716  mov     dword ptr [rsp+140h+var_120], esi
0x18004871a  lea     r8, aSLu; "%s%lu"
0x180048721  mov     rdx, rbx; unsigned __int64
0x180048724  lea     rcx, [rsp+140h+Buffer]; unsigned __int16 *
0x180048729  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004872e  mov     ebx, eax
0x180048730  test    eax, eax
0x180048732  js      loc_18004882A
0x180048738  mov     rax, [r13+0E8h]
0x18004873f  lea     r8, [rbp+40h+var_C0]; unsigned __int16 *
0x180048743  mov     r9d, 32h ; '2'; unsigned int
0x180048749  mov     [rsp+140h+var_120], rax; unsigned __int16 *
0x18004874e  lea     rdx, [rsp+140h+Buffer]; unsigned __int16 *
0x180048753  lea     rcx, aPackages; "Packages"
0x18004875a  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x18004875f  test    eax, eax
0x180048761  jnz     loc_180048931
0x180048767  lea     rbx, [r13+0E0h]
0x18004876e  mov     rcx, rbx
0x180048771  lea     rdx, [rbp+40h+var_C0]
0x180048775  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x18004877b  movss   xmm0, dword ptr [r13+130h]
0x180048784  lea     rcx, [rsp+140h+var_108]
0x180048789  movss   [rsp+140h+var_118], xmm0; int
0x18004878f  lea     r9, [r13+0F8h]
0x180048796  mov     [rsp+140h+var_120], rcx; int *
0x18004879b  lea     rdx, [r13+0E8h]; struct CString *
0x1800487a2  mov     rcx, r13; this
0x1800487a5  mov     [rsp+140h+var_108], 0
0x1800487ad  mov     r8, rbx
0x1800487b0  call    ?LoadFromPDF@CPDFPackage@@QEAAJAEAVCString@@0AEAV?$CList@VCString@@AEAV1@@@AEAHM@Z; CPDFPackage::LoadFromPDF(CString &,CString &,CList<CString,CString &> &,int &,float)
0x1800487b5  test    eax, eax
0x1800487b7  jnz     loc_180048936
0x1800487bd  mov     r8, [rsp+140h+var_F8]
0x1800487c2  lea     rcx, [r13+0F8h]
0x1800487c9  mov     rdx, r14
0x1800487cc  call    ?CreateArrayFromFileList@@YAJAEAV?$CList@VCString@@AEAV1@@@PEAPEAPEAGPEAK@Z; CreateArrayFromFileList(CList<CString,CString &> &,ushort * * *,ulong *)
0x1800487d1  test    eax, eax
0x1800487d3  js      loc_180048936
0x1800487d9  mov     ecx, 8; cb
0x1800487de  call    cs:__imp_CoTaskMemAlloc
0x1800487e4  mov     [r15], rax
0x1800487e7  test    rax, rax
0x1800487ea  jnz     short loc_1800487F6
0x1800487ec  mov     eax, 8007000Eh
0x1800487f1  jmp     loc_180048936
0x1800487f6  xor     ecx, ecx
0x1800487f8  mov     [rax], rcx
0x1800487fb  mov     rcx, [r13+10h]; unsigned __int16 *
0x1800487ff  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180048804  add     eax, 2
0x180048807  movsxd  rbx, eax
0x18004880a  lea     rcx, [rbx+rbx]; cb
0x18004880e  call    cs:__imp_CoTaskMemAlloc
0x180048814  mov     rcx, [r15]
0x180048817  mov     [rcx], rax
0x18004881a  mov     rax, [r15]
0x18004881d  mov     rcx, [rax]; unsigned __int16 *
0x180048820  test    rcx, rcx
0x180048823  jnz     short loc_1800488A2
0x180048825  mov     ebx, 8007000Eh
0x18004882a  mov     rcx, [r15]
0x18004882d  xor     r12d, r12d
0x180048830  test    rcx, rcx
0x180048833  jz      short loc_18004884A
0x180048835  mov     rcx, [rcx]; pv
0x180048838  call    cs:__imp_CoTaskMemFree
0x18004883e  mov     rcx, [r15]; pv
0x180048841  call    cs:__imp_CoTaskMemFree
0x180048847  mov     [r15], r12
0x18004884a  mov     rcx, [rdi]
0x18004884d  test    rcx, rcx
0x180048850  jz      short loc_180048867
0x180048852  mov     rcx, [rcx]; pv
0x180048855  call    cs:__imp_CoTaskMemFree
0x18004885b  mov     rcx, [rdi]; pv
0x18004885e  call    cs:__imp_CoTaskMemFree
0x180048864  mov     [rdi], r12
0x180048867  cmp     [r14], r12
0x18004886a  jz      short loc_18004889B
0x18004886c  mov     r15, [rsp+140h+var_F8]
0x180048871  mov     edi, r12d
0x180048874  cmp     [r15], r12d
0x180048877  jbe     short loc_18004888F
0x180048879  mov     rcx, [r14]
0x18004887c  mov     eax, edi
0x18004887e  mov     rcx, [rcx+rax*8]; pv
0x180048882  call    cs:__imp_CoTaskMemFree
0x180048888  add     edi, esi
0x18004888a  cmp     edi, [r15]
0x18004888d  jb      short loc_180048879
0x18004888f  mov     rcx, [r14]; pv
0x180048892  call    cs:__imp_CoTaskMemFree
0x180048898  mov     [r14], r12
0x18004889b  mov     eax, ebx
0x18004889d  jmp     loc_180048936
0x1800488a2  mov     r8, [r13+10h]; unsigned __int16 *
0x1800488a6  mov     rdx, rbx; unsigned __int64
0x1800488a9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800488ae  mov     ebx, eax
0x1800488b0  test    eax, eax
0x1800488b2  js      loc_18004882A
0x1800488b8  mov     ecx, 8; cb
0x1800488bd  call    cs:__imp_CoTaskMemAlloc
0x1800488c3  mov     [rdi], rax
0x1800488c6  test    rax, rax
0x1800488c9  jz      loc_180048825
0x1800488cf  xor     ecx, ecx
0x1800488d1  mov     [rax], rcx
0x1800488d4  mov     rcx, [r13+8]; unsigned __int16 *
0x1800488d8  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800488dd  add     eax, 2
0x1800488e0  movsxd  rbx, eax
0x1800488e3  lea     rcx, [rbx+rbx]; cb
0x1800488e7  call    cs:__imp_CoTaskMemAlloc
0x1800488ed  mov     rcx, [rdi]
0x1800488f0  mov     [rcx], rax
0x1800488f3  mov     rax, [rdi]
0x1800488f6  mov     rcx, [rax]; unsigned __int16 *
0x1800488f9  test    rcx, rcx
0x1800488fc  jz      loc_180048825
0x180048902  mov     r8, [r13+8]; unsigned __int16 *
0x180048906  mov     rdx, rbx; unsigned __int64
0x180048909  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004890e  mov     ebx, eax
0x180048910  test    eax, eax
0x180048912  js      loc_18004882A
0x180048918  cmp     [rsp+140h+var_108], 0
0x18004891d  mov     rax, [rsp+140h+var_100]
0x180048922  mov     [rax], esi
0x180048924  jnz     short loc_180048928
0x180048926  xor     esi, esi
0x180048928  mov     [r12], esi
0x18004892c  jmp     loc_18004889B
0x180048931  mov     eax, 80110408h
0x180048936  mov     rcx, [rbp+40h+var_50]
0x18004893a  xor     rcx, rsp; StackCookie
0x18004893d  call    __security_check_cookie
0x180048942  add     rsp, 108h
0x180048949  pop     r15
0x18004894b  pop     r14
0x18004894d  pop     r13
0x18004894f  pop     r12
0x180048951  pop     rdi
0x180048952  pop     rsi
0x180048953  pop     rbx
0x180048954  pop     rbp
0x180048955  retn
```
