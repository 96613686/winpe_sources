# CAppImport::QueryApplication(ushort *,ulong *,ushort * * *,ushort * * *,ulong *,ulong *,ulong *,ushort * * *)

- ea: `0x180043900`
- end: `0x180043b46`
- name: `?QueryApplication@CAppImport@@UEAAJPEAGPEAKPEAPEAPEAG21112@Z`
- size: `582`
- prototype: `__int64 __usercall@<rax>(CAppImport *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned int *@<r8>, unsigned __int16 ***@<r9>, unsigned __int16 ***, unsigned int *, unsigned int *, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000ae48`
- `0x18000ae78`
- `0x180032c98`
- `0x18003a57c`
- `0x180042ef8`
- `0x180043900`
- `0x180043b4c`
- `0x180044b28`
- `0x18004859c`
- `0x180055550`

## import_xrefs

- `MfcSubs!??1CString@@QEAA@XZ` at `0x180043b12`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x180043b12`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x1800439b0`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x1800439b0`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18004397a`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18004397a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043a6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043a75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043a6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043a75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800439ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800439fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800439ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800439fa`

## pseudocode

```c
__int64 __fastcall CAppImport::QueryApplication(
        struct _GUID *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        LPVOID **a4,
        unsigned __int16 ***a5,
        unsigned int *a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned __int16 ***a9)
{
  unsigned int v12; // esi
  int ApplicationFromAPL; // eax
  unsigned __int16 **v14; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 **v16; // rcx
  unsigned __int16 *v17; // rax
  unsigned int *v18; // rcx
  int v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v21; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 ***v22; // [rsp+50h] [rbp-B0h]
  unsigned int *v23; // [rsp+58h] [rbp-A8h]
  __int128 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v25; // [rsp+70h] [rbp-90h]
  unsigned __int16 **v26; // [rsp+80h] [rbp-80h]
  void *ppInterface; // [rsp+88h] [rbp-78h] BYREF
  int v28; // [rsp+90h] [rbp-70h]
  __int64 v29; // [rsp+98h] [rbp-68h]
  _BYTE v30[320]; // [rsp+A0h] [rbp-60h] BYREF

  v23 = a8;
  v22 = a9;
  ppInterface = 0;
  v28 = 0;
  v29 = 0;
  *(_QWORD *)v20 = a2;
  CString::CString((CString *)&v21);
  v24 = 0;
  v26 = 0;
  v25 = 0;
  v12 = CImpersonate::ImpersonateClient(&ppInterface);
  if ( !v12 )
  {
    CString::operator=(&v21, *(_QWORD *)v20);
    ApplicationFromAPL = CAppImport::QueryApplicationFromAPL(
                           (CAppImport *)this,
                           v21,
                           0,
                           (struct tagImportAppInfo *)&v24,
                           0,
                           0,
                           0);
    v20[0] = ApplicationFromAPL;
    if ( ApplicationFromAPL < 0 )
    {
      if ( ApplicationFromAPL == -2146368504 || ApplicationFromAPL == -2147024786 )
      {
        CPackageDefinitionFile::CPackageDefinitionFile((CPackageDefinitionFile *)v30, this + 6);
        v20[0] = CPackageDefinitionFile::QueryPackageFromFile(
                   (CPackageDefinitionFile *)v30,
                   v21,
                   a3,
                   a4,
                   a5,
                   a6,
                   v23,
                   v22);
        *a7 = 0;
        CPackageDefinitionFile::~CPackageDefinitionFile((CPackageDefinitionFile *)v30);
      }
    }
    else
    {
      *a4 = (LPVOID *)CoTaskMemAlloc(8u);
      v14 = (unsigned __int16 **)CoTaskMemAlloc(8u);
      *a5 = v14;
      if ( *a4 && v14 )
      {
        v15 = (unsigned __int16 *)v24;
        *a3 = 1;
        **a4 = v15;
        v16 = *a5;
        v17 = (unsigned __int16 *)*((_QWORD *)&v24 + 1);
        v24 = 0;
        *v16 = v17;
        v18 = v23;
        *a6 = v25;
        *a7 = DWORD1(v25);
        *v18 = HIDWORD(v25);
        v25 = 0;
        *v22 = v26;
        v26 = 0;
      }
      else
      {
        CoTaskMemFree(*a4);
        CoTaskMemFree(*a5);
        *a5 = 0;
        *a4 = 0;
        v20[0] = -2147024882;
      }
    }
    CAppImport::ClearImportAppInfo((LPVOID *)&v24);
    CImpersonate::Cleanup((CImpersonate *)&ppInterface, v20);
    v12 = v20[0];
  }
  CString::~CString((CString *)&v21);
  CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
  return v12;
}

```

## disassembly

```asm
0x180043900  push    rbp
0x180043902  push    rbx
0x180043903  push    rsi
0x180043904  push    rdi
0x180043905  push    r12
0x180043907  push    r13
0x180043909  push    r14
0x18004390b  push    r15
0x18004390d  lea     rbp, [rsp-0F8h]
0x180043915  sub     rsp, 1F8h
0x18004391c  mov     rax, cs:__security_cookie
0x180043923  xor     rax, rsp
0x180043926  mov     [rbp+130h+var_50], rax
0x18004392d  mov     rax, [rbp+130h+arg_38]
0x180043934  mov     r14, rcx
0x180043937  mov     rbx, [rbp+130h+arg_20]
0x18004393e  lea     rcx, [rsp+230h+var_1E8]
0x180043943  mov     r12, [rbp+130h+arg_28]
0x18004394a  mov     rdi, r9
0x18004394d  mov     r13, [rbp+130h+arg_30]
0x180043954  mov     r15, r8
0x180043957  mov     [rsp+230h+var_1D8], rax
0x18004395c  mov     rax, [rbp+130h+arg_40]
0x180043963  mov     [rsp+230h+var_1E0], rax
0x180043968  xor     eax, eax
0x18004396a  mov     [rbp+130h+ppInterface], rax
0x18004396e  mov     [rbp+130h+var_1A0], eax
0x180043971  mov     [rbp+130h+var_198], rax
0x180043975  mov     qword ptr [rsp+230h+var_1F0], rdx
0x18004397a  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x180043980  xorps   xmm0, xmm0
0x180043983  lea     rcx, [rbp+130h+ppInterface]; ppInterface
0x180043987  xor     eax, eax
0x180043989  movups  [rsp+230h+var_1D0], xmm0
0x18004398e  mov     [rbp+130h+var_1B0], rax
0x180043992  movups  [rsp+230h+var_1C0], xmm0
0x180043997  call    ?ImpersonateClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateClient(void)
0x18004399c  mov     esi, eax
0x18004399e  test    eax, eax
0x1800439a0  jnz     loc_180043B0D
0x1800439a6  mov     rdx, qword ptr [rsp+230h+var_1F0]
0x1800439ab  lea     rcx, [rsp+230h+var_1E8]
0x1800439b0  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1800439b6  mov     rdx, [rsp+230h+var_1E8]; unsigned __int16 *
0x1800439bb  lea     r9, [rsp+230h+var_1D0]; struct tagImportAppInfo *
0x1800439c0  xor     esi, esi
0x1800439c2  xor     r8d, r8d; unsigned int
0x1800439c5  mov     [rsp+230h+var_200], rsi; struct _GUID *
0x1800439ca  mov     rcx, r14; this
0x1800439cd  mov     [rsp+230h+var_208], rsi; unsigned __int16 **
0x1800439d2  mov     [rsp+230h+var_210], rsi; unsigned __int16 **
0x1800439d7  call    ?QueryApplicationFromAPL@CAppImport@@AEAAJPEBGKPEAUtagImportAppInfo@@PEAPEAG2PEAU_GUID@@@Z; CAppImport::QueryApplicationFromAPL(ushort const *,ulong,tagImportAppInfo *,ushort * *,ushort * *,_GUID *)
0x1800439dc  mov     [rsp+230h+var_1F0], eax
0x1800439e0  test    eax, eax
0x1800439e2  js      loc_180043A93
0x1800439e8  mov     esi, 8
0x1800439ed  mov     ecx, esi; cb
0x1800439ef  call    cs:__imp_CoTaskMemAlloc
0x1800439f5  mov     ecx, esi; cb
0x1800439f7  mov     [rdi], rax
0x1800439fa  call    cs:__imp_CoTaskMemAlloc
0x180043a00  mov     [rbx], rax
0x180043a03  mov     rcx, [rdi]; pv
0x180043a06  test    rcx, rcx
0x180043a09  jz      short loc_180043A6C
0x180043a0b  test    rax, rax
0x180043a0e  jz      short loc_180043A6C
0x180043a10  mov     rax, qword ptr [rsp+230h+var_1D0]
0x180043a15  xorps   xmm0, xmm0
0x180043a18  mov     dword ptr [r15], 1
0x180043a1f  mov     rcx, [rdi]
0x180043a22  mov     [rcx], rax
0x180043a25  mov     rcx, [rbx]
0x180043a28  mov     rax, qword ptr [rsp+230h+var_1D0+8]
0x180043a2d  movups  [rsp+230h+var_1D0], xmm0
0x180043a32  mov     [rcx], rax
0x180043a35  mov     eax, dword ptr [rsp+230h+var_1C0]
0x180043a39  mov     rcx, [rsp+230h+var_1D8]
0x180043a3e  mov     [r12], eax
0x180043a42  mov     eax, dword ptr [rsp+230h+var_1C0+4]
0x180043a46  mov     [r13+0], eax
0x180043a4a  mov     eax, dword ptr [rsp+230h+var_1C0+0Ch]
0x180043a4e  mov     [rcx], eax
0x180043a50  mov     rax, [rbp+130h+var_1B0]
0x180043a54  mov     rcx, [rsp+230h+var_1E0]
0x180043a59  movups  [rsp+230h+var_1C0], xmm0
0x180043a5e  mov     [rcx], rax
0x180043a61  xor     eax, eax
0x180043a63  mov     [rbp+130h+var_1B0], rax
0x180043a67  jmp     loc_180043AF1
0x180043a6c  call    cs:__imp_CoTaskMemFree
0x180043a72  mov     rcx, [rbx]; pv
0x180043a75  call    cs:__imp_CoTaskMemFree
0x180043a7b  mov     qword ptr [rbx], 0
0x180043a82  mov     qword ptr [rdi], 0
0x180043a89  mov     [rsp+230h+var_1F0], 8007000Eh
0x180043a91  jmp     short loc_180043AF1
0x180043a93  cmp     eax, 80110408h
0x180043a98  jz      short loc_180043AA1
0x180043a9a  cmp     eax, 8007006Eh
0x180043a9f  jnz     short loc_180043AF1
0x180043aa1  lea     rdx, [r14+60h]; struct _GUID *
0x180043aa5  lea     rcx, [rbp+130h+var_190]; this
0x180043aa9  call    ??0CPackageDefinitionFile@@QEAA@AEBU_GUID@@@Z; CPackageDefinitionFile::CPackageDefinitionFile(_GUID const &)
0x180043aae  mov     rcx, [rsp+230h+var_1E0]
0x180043ab3  mov     r9, rdi; unsigned __int16 ***
0x180043ab6  mov     rdx, [rsp+230h+var_1E8]; unsigned __int16 *
0x180043abb  mov     r8, r15; unsigned int *
0x180043abe  mov     [rsp+230h+var_1F8], rcx; unsigned __int16 ***
0x180043ac3  mov     rcx, [rsp+230h+var_1D8]
0x180043ac8  mov     [rsp+230h+var_200], rcx; unsigned int *
0x180043acd  lea     rcx, [rbp+130h+var_190]; this
0x180043ad1  mov     [rsp+230h+var_208], r12; unsigned int *
0x180043ad6  mov     [rsp+230h+var_210], rbx; unsigned __int16 ***
0x180043adb  call    ?QueryPackageFromFile@CPackageDefinitionFile@@QEAAJPEAGPEAKPEAPEAPEAG2112@Z; CPackageDefinitionFile::QueryPackageFromFile(ushort *,ulong *,ushort * * *,ushort * * *,ulong *,ulong *,ushort * * *)
0x180043ae0  lea     rcx, [rbp+130h+var_190]; this
0x180043ae4  mov     [rsp+230h+var_1F0], eax
0x180043ae8  mov     [r13+0], esi
0x180043aec  call    ??1CPackageDefinitionFile@@QEAA@XZ; CPackageDefinitionFile::~CPackageDefinitionFile(void)
0x180043af1  lea     rcx, [rsp+230h+var_1D0]; struct tagImportAppInfo *
0x180043af6  call    ?ClearImportAppInfo@CAppImport@@CAXPEAUtagImportAppInfo@@@Z; CAppImport::ClearImportAppInfo(tagImportAppInfo *)
0x180043afb  lea     rdx, [rsp+230h+var_1F0]; int *
0x180043b00  lea     rcx, [rbp+130h+ppInterface]; this
0x180043b04  call    ?Cleanup@CImpersonate@@QEAAXPEAJ@Z; CImpersonate::Cleanup(long *)
0x180043b09  mov     esi, [rsp+230h+var_1F0]
0x180043b0d  lea     rcx, [rsp+230h+var_1E8]
0x180043b12  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x180043b18  lea     rcx, [rbp+130h+ppInterface]; this
0x180043b1c  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x180043b21  mov     eax, esi
0x180043b23  mov     rcx, [rbp+130h+var_50]
0x180043b2a  xor     rcx, rsp; StackCookie
0x180043b2d  call    __security_check_cookie
0x180043b32  add     rsp, 1F8h
0x180043b39  pop     r15
0x180043b3b  pop     r14
0x180043b3d  pop     r13
0x180043b3f  pop     r12
0x180043b41  pop     rdi
0x180043b42  pop     rsi
0x180043b43  pop     rbx
0x180043b44  pop     rbp
0x180043b45  retn
```
