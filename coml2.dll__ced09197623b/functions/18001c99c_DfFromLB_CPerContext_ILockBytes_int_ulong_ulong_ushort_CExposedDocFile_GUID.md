# DfFromLB(CPerContext *,ILockBytes *,int,ulong,ulong,ushort * *,CExposedDocFile * *,_GUID *)

- ea: `0x18001c99c`
- end: `0x18001cd7e`
- name: `?DfFromLB@@YAJPEAVCPerContext@@PEAUILockBytes@@HKKPEAPEAGPEAPEAVCExposedDocFile@@PEAU_GUID@@@Z`
- size: `994`
- prototype: `__int64 __fastcall(struct CPerContext *this, struct ILockBytes *, int, unsigned int, unsigned int, unsigned __int16 **, struct CExposedDocFile **)`
- caller_count: `4`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c2ac`
- `0x18001eaa0`
- `0x180036c90`
- `0x18003d950`

## callees

- `0x18000cdd8`
- `0x180015f30`
- `0x180016810`
- `0x18001ad54`
- `0x18001b89c`
- `0x18001c99c`
- `0x18001cd84`
- `0x18001d820`
- `0x18001e218`
- `0x18002e5d8`
- `0x18002f2e0`
- `0x1800325d4`
- `0x1800331cc`
- `0x18003ab9c`
- `0x180042800`
- `0x180043100`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ca67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ca67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001caff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001caff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc4d`

## pseudocode

```c
__int64 __fastcall DfFromLB(
        struct CPerContext *this,
        struct ILockBytes *a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int16 **a6,
        struct CExposedDocFile **a7)
{
  struct IMalloc *v9; // r13
  struct IMalloc *v12; // rdx
  int inited; // ebx
  CMSFHeader *v14; // rsi
  struct ILockBytesVtbl *lpVtbl; // rax
  HRESULT (__stdcall *ReadAt)(ILockBytes *, ULARGE_INTEGER, void *, ULONG, ULONG *); // rax
  int v17; // eax
  CRootPubDocFile *v18; // rax
  CRootPubDocFile *v19; // rax
  CPubDocFile *v20; // rsi
  int (__fastcall ***v21)(_QWORD, GUID *, _QWORD *); // r9
  struct IMalloc *v22; // rdx
  __int64 v23; // rcx
  unsigned int v24; // eax
  __int64 v25; // rax
  CExposedDocFile *v26; // rax
  struct CExposedDocFile *v27; // rax
  unsigned int v29; // r8d
  unsigned int v30; // [rsp+40h] [rbp-A9h] BYREF
  struct CDFBasis *v31; // [rsp+48h] [rbp-A1h] BYREF
  _QWORD v32[2]; // [rsp+50h] [rbp-99h] BYREF
  unsigned __int16 **v33; // [rsp+60h] [rbp-89h]
  int v34; // [rsp+68h] [rbp-81h] BYREF
  struct CPerContext *v35; // [rsp+70h] [rbp-79h]
  __int128 v36; // [rsp+78h] [rbp-71h]
  _BYTE v37[16]; // [rsp+90h] [rbp-59h] BYREF
  unsigned __int64 v38; // [rsp+A0h] [rbp-49h]

  v9 = (struct IMalloc *)*((_QWORD *)this + 8);
  v33 = a6;
  v31 = 0;
  v30 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 14);
  v35 = this;
  v34 = -2147286784;
  v36 = 0;
  inited = CSafeSem::Take((CSafeSem *)&v34);
  if ( inited < 0 )
    goto LABEL_22;
  if ( !a3 && (a5 & 4) == 0 )
  {
    memset_0(v37, 0, 0x50u);
    if ( ((int (__fastcall *)(struct ILockBytes *, _BYTE *, __int64))a2->lpVtbl->Stat)(a2, v37, 1) >= 0 )
    {
      v14 = (CMSFHeader *)CoTaskMemAlloc(0x200u);
      if ( !v14 )
      {
LABEL_25:
        inited = -2147287032;
        goto LABEL_22;
      }
      lpVtbl = a2->lpVtbl;
      v32[1] = 0;
      ReadAt = lpVtbl->ReadAt;
      LODWORD(v32[0]) = 0;
      inited = ((__int64 (__fastcall *)(struct ILockBytes *, _QWORD, CMSFHeader *, __int64, _QWORD *))ReadAt)(
                 a2,
                 0,
                 v14,
                 512,
                 v32);
      if ( inited >= 0 )
      {
        if ( LODWORD(v32[0]) < 0x200 || (v17 = CMSFHeader::Validate(v14), inited = v17, v17 == -2147286789) )
        {
          inited = -2147286960;
        }
        else if ( v17 >= 0 )
        {
          inited = CMSFHeader::CheckSectorsAgainstFileSize(v14, v38, a2);
          if ( inited >= 0 )
          {
            CoTaskMemFree(v14);
            goto LABEL_12;
          }
        }
      }
      CoTaskMemFree(v14);
LABEL_22:
      CPerContext::Release(this);
      goto LABEL_19;
    }
  }
LABEL_12:
  v18 = (CRootPubDocFile *)CMallocBased::operator new(0xC0u, v12);
  if ( !v18 )
    goto LABEL_25;
  v19 = CRootPubDocFile::CRootPubDocFile(v18, v9);
  v20 = v19;
  if ( !v19 )
    goto LABEL_25;
  inited = CRootPubDocFile::InitRoot(v19, a2, a5, a4, v33, &v31, &v30, *((struct CGlobalContext **)this + 6));
  if ( inited < 0 )
  {
LABEL_26:
    v29 = *((_DWORD *)v20 + 42);
    if ( v29 )
    {
      StgpReleaseAccessLocks(a2, 0x40u, v29);
      *((_DWORD *)v20 + 42) = 0;
    }
    CPubDocFile::vRelease(v20);
    goto LABEL_22;
  }
  v21 = (int (__fastcall ***)(_QWORD, GUID *, _QWORD *))*((_QWORD *)v31 + 4);
  v22 = (struct IMalloc *)*((_QWORD *)v31 + 6);
  v23 = *((_QWORD *)v31 + 5);
  v24 = v30;
  *((_QWORD *)this + 2) = v21;
  *((_QWORD *)this + 3) = v23;
  *((_QWORD *)this + 4) = v22;
  *((_DWORD *)this + 10) = v24;
  *((_QWORD *)this + 9) = 0;
  if ( v21 )
  {
    v32[0] = 0;
    if ( (**v21)(v21, &GUID_de2eacd0_9c9d_11cf_882a_00aa00b569f5, v32) >= 0 )
    {
      if ( (int)CPerContext::InitNotificationEvent(this, *((struct ILockBytes **)this + 2)) >= 0 )
        *((_QWORD *)this + 9) = v32[0];
      else
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v32[0] + 16LL))(v32[0]);
    }
  }
  v25 = *((_QWORD *)this + 6);
  *(_DWORD *)(v25 + 32) = v30 != 0;
  *(_DWORD *)(v25 + 36) = a4;
  v26 = (CExposedDocFile *)CMallocBased::operator new(0x100u, v22);
  if ( !v26 )
  {
    *a7 = 0;
LABEL_30:
    inited = -2147287032;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 6) + 8LL))(*((_QWORD *)v31 + 6));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 4) + 8LL))(*((_QWORD *)v31 + 4));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 5) + 8LL))(*((_QWORD *)v31 + 5));
    if ( v30 && !*((_QWORD *)this + 6) )
      StgpReleaseOpenLocks(*((struct ILockBytes **)v31 + 6), a4, v30);
    v30 = 0;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 5) + 16LL))(*((_QWORD *)v31 + 5));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 4) + 16LL))(*((_QWORD *)v31 + 4));
    *((_QWORD *)v31 + 5) = 0;
    *((_QWORD *)v31 + 4) = 0;
    goto LABEL_26;
  }
  v27 = CExposedDocFile::CExposedDocFile(v26, v20, v31, this);
  *a7 = v27;
  if ( !v27 )
    goto LABEL_30;
LABEL_19:
  CSafeSem::Release((CSafeSem *)&v34);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001c99c  mov     [rsp-8+arg_10], rbx
0x18001c9a1  push    rbp
0x18001c9a2  push    rsi
0x18001c9a3  push    rdi
0x18001c9a4  push    r12
0x18001c9a6  push    r13
0x18001c9a8  push    r14
0x18001c9aa  push    r15
0x18001c9ac  lea     rbp, [rsp-7]
0x18001c9b1  sub     rsp, 0F0h
0x18001c9b8  mov     rax, cs:__security_cookie
0x18001c9bf  xor     rax, rsp
0x18001c9c2  mov     [rbp+37h+var_40], rax
0x18001c9c6  mov     rax, [rbp+37h+arg_28]
0x18001c9ca  mov     r15d, r9d
0x18001c9cd  mov     r12, [rbp+37h+arg_30]
0x18001c9d1  mov     esi, r8d
0x18001c9d4  mov     r13, [rcx+40h]
0x18001c9d8  mov     r14, rdx
0x18001c9db  mov     [rsp+120h+var_C0], rax
0x18001c9e0  mov     rdi, rcx
0x18001c9e3  mov     [rsp+120h+var_D8], 0
0x18001c9ec  mov     [rsp+120h+var_E0], 0
0x18001c9f4  lock inc dword ptr [rcx+38h]
0x18001c9f8  mov     [rbp+37h+var_B0], rcx
0x18001c9fc  xorps   xmm0, xmm0
0x18001c9ff  lea     rcx, [rsp+120h+var_B8]; this
0x18001ca04  mov     [rsp+120h+var_B8], 80030100h
0x18001ca0c  movdqu  [rbp+37h+var_A8], xmm0
0x18001ca11  call    ?Take@CSafeSem@@QEAAJXZ; CSafeSem::Take(void)
0x18001ca16  mov     ebx, eax
0x18001ca18  test    eax, eax
0x18001ca1a  js      loc_18001CC53
0x18001ca20  test    esi, esi
0x18001ca22  jnz     loc_18001CB05
0x18001ca28  test    byte ptr [rbp+37h+arg_20], 4
0x18001ca2c  jnz     loc_18001CB05
0x18001ca32  xor     edx, edx; Val
0x18001ca34  lea     r8d, [rsi+50h]; Size
0x18001ca38  lea     rcx, [rbp+37h+var_90]; void *
0x18001ca3c  call    memset_0
0x18001ca41  mov     rax, [r14]
0x18001ca44  lea     r8d, [rsi+1]
0x18001ca48  lea     rdx, [rbp+37h+var_90]
0x18001ca4c  mov     rcx, r14
0x18001ca4f  mov     rax, [rax+48h]
0x18001ca53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca58  test    eax, eax
0x18001ca5a  js      loc_18001CB05
0x18001ca60  mov     ebx, 200h
0x18001ca65  mov     ecx, ebx; cb
0x18001ca67  call    cs:__imp_CoTaskMemAlloc
0x18001ca6d  mov     rsi, rax
0x18001ca70  test    rax, rax
0x18001ca73  jz      loc_18001CC87
0x18001ca79  mov     rax, [r14]
0x18001ca7c  lea     rcx, [rsp+120h+var_D0]
0x18001ca81  mov     [rsp+120h+var_100], rcx
0x18001ca86  mov     r9d, ebx
0x18001ca89  mov     [rsp+120h+var_C8], 0
0x18001ca92  mov     r8, rsi
0x18001ca95  mov     rdx, [rsp+120h+var_C8]
0x18001ca9a  mov     rcx, r14
0x18001ca9d  mov     rax, [rax+18h]
0x18001caa1  mov     dword ptr [rsp+120h+var_D0], 0
0x18001caa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caae  mov     ebx, eax
0x18001cab0  test    eax, eax
0x18001cab2  js      loc_18001CC4A
0x18001cab8  cmp     dword ptr [rsp+120h+var_D0], 200h
0x18001cac0  jb      loc_18001CC45
0x18001cac6  mov     rcx, rsi; this
0x18001cac9  call    ?Validate@CMSFHeader@@QEBAJXZ; CMSFHeader::Validate(void)
0x18001cace  mov     ebx, eax
0x18001cad0  cmp     eax, 800300FBh
0x18001cad5  jz      loc_18001CC45
0x18001cadb  test    eax, eax
0x18001cadd  js      loc_18001CC4A
0x18001cae3  mov     rdx, [rbp+37h+var_80]; unsigned __int64
0x18001cae7  mov     r8, r14; struct ILockBytes *
0x18001caea  mov     rcx, rsi; this
0x18001caed  call    ?CheckSectorsAgainstFileSize@CMSFHeader@@QEBAJ_KPEAUILockBytes@@@Z; CMSFHeader::CheckSectorsAgainstFileSize(unsigned __int64,ILockBytes *)
0x18001caf2  mov     ebx, eax
0x18001caf4  test    eax, eax
0x18001caf6  js      loc_18001CC4A
0x18001cafc  mov     rcx, rsi; pv
0x18001caff  call    cs:__imp_CoTaskMemFree
0x18001cb05  mov     ecx, 0C0h; unsigned __int64
0x18001cb0a  call    ??2CMallocBased@@SAPEAX_KQEAUIMalloc@@@Z; CMallocBased::operator new(unsigned __int64,IMalloc * const)
0x18001cb0f  test    rax, rax
0x18001cb12  jz      loc_18001CC87
0x18001cb18  mov     rdx, r13; struct IMalloc *
0x18001cb1b  mov     rcx, rax; this
0x18001cb1e  call    ??0CRootPubDocFile@@QEAA@QEAUIMalloc@@@Z; CRootPubDocFile::CRootPubDocFile(IMalloc * const)
0x18001cb23  xor     r13d, r13d
0x18001cb26  mov     rsi, rax
0x18001cb29  test    rax, rax
0x18001cb2c  jz      loc_18001CC87
0x18001cb32  mov     rcx, [rdi+30h]
0x18001cb36  lea     rax, [rsp+120h+var_E0]
0x18001cb3b  mov     r8d, [rbp+37h+arg_20]; unsigned int
0x18001cb3f  mov     r9d, r15d; unsigned int
0x18001cb42  mov     [rsp+120h+var_E8], rcx; struct CGlobalContext *
0x18001cb47  mov     rdx, r14; struct ILockBytes *
0x18001cb4a  mov     [rsp+120h+var_F0], rax; unsigned int *
0x18001cb4f  mov     rcx, rsi; this
0x18001cb52  lea     rax, [rsp+120h+var_D8]
0x18001cb57  mov     [rsp+120h+var_F8], rax; struct CDFBasis **
0x18001cb5c  mov     rax, [rsp+120h+var_C0]
0x18001cb61  mov     [rsp+120h+var_100], rax; unsigned __int16 **
0x18001cb66  call    ?InitRoot@CRootPubDocFile@@QEAAJPEAUILockBytes@@KKPEAPEAGPEAPEAVCDFBasis@@PEAKPEAVCGlobalContext@@@Z; CRootPubDocFile::InitRoot(ILockBytes *,ulong,ulong,ushort * *,CDFBasis * *,ulong *,CGlobalContext *)
0x18001cb6b  mov     ebx, eax
0x18001cb6d  test    eax, eax
0x18001cb6f  js      loc_18001CC8E
0x18001cb75  mov     rax, [rsp+120h+var_D8]
0x18001cb7a  mov     r9, [rax+20h]
0x18001cb7e  mov     rdx, [rax+30h]
0x18001cb82  mov     rcx, [rax+28h]
0x18001cb86  mov     eax, [rsp+120h+var_E0]
0x18001cb8a  mov     [rdi+10h], r9
0x18001cb8e  mov     [rdi+18h], rcx
0x18001cb92  mov     [rdi+20h], rdx
0x18001cb96  mov     [rdi+28h], eax
0x18001cb99  mov     [rdi+48h], r13
0x18001cb9d  test    r9, r9
0x18001cba0  jz      short loc_18001CBC9
0x18001cba2  mov     [rsp+120h+var_D0], r13
0x18001cba7  lea     r8, [rsp+120h+var_D0]
0x18001cbac  mov     rax, [r9]
0x18001cbaf  lea     rdx, _GUID_de2eacd0_9c9d_11cf_882a_00aa00b569f5
0x18001cbb6  mov     rcx, r9
0x18001cbb9  mov     rax, [rax]
0x18001cbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbc1  test    eax, eax
0x18001cbc3  jns     loc_18001CC5D
0x18001cbc9  cmp     [rsp+120h+var_E0], r13d
0x18001cbce  mov     ecx, r13d
0x18001cbd1  mov     rax, [rdi+30h]
0x18001cbd5  setnz   cl
0x18001cbd8  mov     [rax+20h], ecx
0x18001cbdb  mov     ecx, 100h; unsigned __int64
0x18001cbe0  mov     [rax+24h], r15d
0x18001cbe4  call    ??2CMallocBased@@SAPEAX_KQEAUIMalloc@@@Z; CMallocBased::operator new(unsigned __int64,IMalloc * const)
0x18001cbe9  test    rax, rax
0x18001cbec  jz      loc_18001CCA8
0x18001cbf2  mov     r8, [rsp+120h+var_D8]; struct CDFBasis *
0x18001cbf7  mov     r9, rdi; struct CPerContext *
0x18001cbfa  mov     rdx, rsi; struct CPubDocFile *
0x18001cbfd  mov     rcx, rax; this
0x18001cc00  call    ??0CExposedDocFile@@QEAA@PEAVCPubDocFile@@PEAVCDFBasis@@PEAVCPerContext@@@Z; CExposedDocFile::CExposedDocFile(CPubDocFile *,CDFBasis *,CPerContext *)
0x18001cc05  mov     [r12], rax
0x18001cc09  test    rax, rax
0x18001cc0c  jz      loc_18001CCAC
0x18001cc12  lea     rcx, [rsp+120h+var_B8]; this
0x18001cc17  call    ?Release@CSafeSem@@QEAAXXZ; CSafeSem::Release(void)
0x18001cc1c  mov     eax, ebx
0x18001cc1e  mov     rcx, [rbp+37h+var_40]
0x18001cc22  xor     rcx, rsp; StackCookie
0x18001cc25  call    __security_check_cookie
0x18001cc2a  mov     rbx, [rsp+120h+arg_10]
0x18001cc32  add     rsp, 0F0h
0x18001cc39  pop     r15
0x18001cc3b  pop     r14
0x18001cc3d  pop     r13
0x18001cc3f  pop     r12
0x18001cc41  pop     rdi
0x18001cc42  pop     rsi
0x18001cc43  pop     rbp
0x18001cc44  retn
0x18001cc45  mov     ebx, 80030050h
0x18001cc4a  mov     rcx, rsi; pv
0x18001cc4d  call    cs:__imp_CoTaskMemFree
0x18001cc53  mov     rcx, rdi; this
0x18001cc56  call    ?Release@CPerContext@@QEAAJXZ; CPerContext::Release(void)
0x18001cc5b  jmp     short loc_18001CC12
0x18001cc5d  mov     rdx, [rdi+10h]; struct ILockBytes *
0x18001cc61  mov     rcx, rdi; this
0x18001cc64  call    ?InitNotificationEvent@CPerContext@@QEAAJPEAUILockBytes@@@Z; CPerContext::InitNotificationEvent(ILockBytes *)
0x18001cc69  test    eax, eax
0x18001cc6b  jns     loc_18001CD57
0x18001cc71  mov     rcx, [rsp+120h+var_D0]
0x18001cc76  mov     rax, [rcx]
0x18001cc79  mov     rax, [rax+10h]
0x18001cc7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc82  jmp     loc_18001CBC9
0x18001cc87  mov     ebx, 80030008h
0x18001cc8c  jmp     short loc_18001CC53
0x18001cc8e  mov     r8d, [rsi+0A8h]; unsigned int
0x18001cc95  test    r8d, r8d
0x18001cc98  jnz     loc_18001CD65
0x18001cc9e  mov     rcx, rsi; this
0x18001cca1  call    ?vRelease@CPubDocFile@@QEAAJXZ; CPubDocFile::vRelease(void)
0x18001cca6  jmp     short loc_18001CC53
0x18001cca8  mov     [r12], r13
0x18001ccac  mov     ebx, 80030008h
0x18001ccb1  mov     rax, [rsp+120h+var_D8]
0x18001ccb6  mov     rcx, [rax+30h]
0x18001ccba  mov     rax, [rcx]
0x18001ccbd  mov     rax, [rax+8]
0x18001ccc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccc6  mov     rax, [rsp+120h+var_D8]
0x18001cccb  mov     rcx, [rax+20h]
0x18001cccf  mov     rax, [rcx]
0x18001ccd2  mov     rax, [rax+8]
0x18001ccd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccdb  mov     rax, [rsp+120h+var_D8]
0x18001cce0  mov     rcx, [rax+28h]
0x18001cce4  mov     rax, [rcx]
0x18001cce7  mov     rax, [rax+8]
0x18001cceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccf0  mov     r8d, [rsp+120h+var_E0]; unsigned int
0x18001ccf5  test    r8d, r8d
0x18001ccf8  jz      short loc_18001CD11
0x18001ccfa  cmp     [rdi+30h], r13
0x18001ccfe  jnz     short loc_18001CD11
0x18001cd00  mov     rcx, [rsp+120h+var_D8]
0x18001cd05  mov     edx, r15d; unsigned int
0x18001cd08  mov     rcx, [rcx+30h]; struct ILockBytes *
0x18001cd0c  call    ?StgpReleaseOpenLocks@@YAXPEAUILockBytes@@KK@Z; StgpReleaseOpenLocks(ILockBytes *,ulong,ulong)
0x18001cd11  mov     rax, [rsp+120h+var_D8]
0x18001cd16  mov     [rsp+120h+var_E0], r13d
0x18001cd1b  mov     rcx, [rax+28h]
0x18001cd1f  mov     rax, [rcx]
0x18001cd22  mov     rax, [rax+10h]
0x18001cd26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd2b  mov     rax, [rsp+120h+var_D8]
0x18001cd30  mov     rcx, [rax+20h]
0x18001cd34  mov     rax, [rcx]
0x18001cd37  mov     rax, [rax+10h]
0x18001cd3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd40  mov     rax, [rsp+120h+var_D8]
0x18001cd45  mov     [rax+28h], r13
0x18001cd49  mov     rax, [rsp+120h+var_D8]
0x18001cd4e  mov     [rax+20h], r13
0x18001cd52  jmp     loc_18001CC8E
0x18001cd57  mov     rax, [rsp+120h+var_D0]
0x18001cd5c  mov     [rdi+48h], rax
0x18001cd60  jmp     loc_18001CBC9
0x18001cd65  mov     edx, 40h ; '@'; unsigned int
0x18001cd6a  mov     rcx, r14; struct ILockBytes *
0x18001cd6d  call    ?StgpReleaseAccessLocks@@YAXPEAUILockBytes@@KK@Z; StgpReleaseAccessLocks(ILockBytes *,ulong,ulong)
0x18001cd72  mov     [rsi+0A8h], r13d
0x18001cd79  jmp     loc_18001CC9E
```
