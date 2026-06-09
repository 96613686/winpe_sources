# CAppImport::QueryApplication2(ushort const *,tagImportPartInfo *)

- ea: `0x1800434f0`
- end: `0x1800438f2`
- name: `?QueryApplication2@CAppImport@@UEAAJPEBGPEAUtagImportPartInfo@@@Z`
- size: `1026`
- prototype: `int(CAppImport *__hidden this, const unsigned __int16 *, struct tagImportPartInfo *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000ae48`
- `0x18000ae78`
- `0x180032c98`
- `0x18003a57c`
- `0x180042ef8`
- `0x180042f68`
- `0x1800434f0`
- `0x180043b4c`
- `0x180044b28`
- `0x18004859c`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004374a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043753`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004376a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043788`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043798`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800437d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800437e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004383e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004385e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004386b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800438a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004374a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043753`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004376a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043788`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043798`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800437d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800437e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004383e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004385e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004386b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800438a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800435dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043733`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800435dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043733`

## pseudocode

```c
__int64 __fastcall CAppImport::QueryApplication2(CAppImport *this, unsigned __int16 *a2, struct tagImportPartInfo *a3)
{
  CAppImport *v7; // rcx
  unsigned int v8; // ebx
  void *v9; // r14
  void *v10; // rsi
  signed int AplCountFromMsi; // eax
  __int64 v12; // r15
  void *v13; // rax
  __int64 i; // rbx
  unsigned int *v15; // r10
  unsigned __int16 **p_pv; // r8
  unsigned __int16 ***v17; // rdx
  signed int ApplicationFromAPL; // eax
  __int128 v19; // xmm0
  LPVOID v20; // rax
  _OWORD *v21; // rax
  void *v22; // rbx
  unsigned __int16 **v23; // rbx
  unsigned int v24; // r12d
  unsigned int v25; // ebx
  unsigned __int16 **j; // r15
  void *v27; // rcx
  unsigned __int16 **v28; // rcx
  void *v29; // rcx
  unsigned int k; // esi
  unsigned int v31; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v32; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v34[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 **v35; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 **v36[2]; // [rsp+60h] [rbp-A0h] BYREF
  void *ppInterface; // [rsp+70h] [rbp-90h] BYREF
  int v38; // [rsp+78h] [rbp-88h]
  __int64 v39; // [rsp+80h] [rbp-80h]
  _BYTE v40[320]; // [rsp+90h] [rbp-70h] BYREF

  if ( !a3 )
    return 2147500035LL;
  *(_OWORD *)a3 = 0;
  *((_OWORD *)a3 + 1) = 0;
  *((_OWORD *)a3 + 2) = 0;
  if ( !a2 )
    return 2147942487LL;
  ppInterface = 0;
  v38 = 0;
  v39 = 0;
  v8 = CImpersonate::ImpersonateClient(&ppInterface);
  if ( !v8 )
  {
    v32 = 0;
    pv = 0;
    *(GUID *)v36 = GUID_NULL;
    v9 = 0;
    *(_QWORD *)v34 = 0;
    v10 = 0;
    AplCountFromMsi = CAppImport::GetAplCountFromMsi(v7, a2, &v32);
    v31 = AplCountFromMsi;
    if ( AplCountFromMsi >= 0 )
    {
      v12 = v32;
      *((_DWORD *)a3 + 8) = v32;
      if ( (unsigned __int64)(40 * v12) > 0xFFFFFFFF )
      {
        v31 = -2147024362;
      }
      else
      {
        v31 = 0;
        v13 = CoTaskMemAlloc((unsigned int)(40 * v12));
        *((_QWORD *)a3 + 5) = v13;
        if ( v13 )
        {
          memset_0(v13, 0, 40 * v12);
          for ( i = 0; (unsigned int)i < (unsigned int)v12; i = (unsigned int)(i + 1) )
          {
            v15 = v34;
            p_pv = (unsigned __int16 **)&pv;
            if ( v10 )
              p_pv = 0;
            v17 = v36;
            if ( v10 )
            {
              v17 = 0;
              v15 = 0;
            }
            ApplicationFromAPL = CAppImport::QueryApplicationFromAPL(
                                   (CAppImport *)((char *)this - 8),
                                   a2,
                                   i,
                                   (struct tagImportAppInfo *)(*((_QWORD *)a3 + 5) + 40 * i),
                                   (unsigned __int16 **)v15,
                                   p_pv,
                                   (struct _GUID *)v17);
            v10 = *(void **)v34;
            v31 = ApplicationFromAPL;
            if ( ApplicationFromAPL < 0 )
            {
              v9 = pv;
              goto LABEL_31;
            }
          }
          v19 = *(_OWORD *)v36;
          v20 = pv;
          *(_QWORD *)a3 = v10;
          v10 = 0;
          *((_OWORD *)a3 + 1) = v19;
          *((_QWORD *)a3 + 1) = v20;
        }
        else
        {
          v31 = -2147024882;
        }
      }
      goto LABEL_31;
    }
    if ( AplCountFromMsi == -2146368504 || AplCountFromMsi == -2147024786 )
    {
      CPackageDefinitionFile::CPackageDefinitionFile(
        (CPackageDefinitionFile *)v40,
        (const struct _GUID *)((char *)this + 88));
      v31 = 0;
      pv = 0;
      v35 = 0;
      v34[0] = 0;
      v32 = 0;
      v36[0] = 0;
      v31 = CPackageDefinitionFile::QueryPackageFromFile(
              (CPackageDefinitionFile *)v40,
              a2,
              &v31,
              (unsigned __int16 ***)&pv,
              &v35,
              v34,
              &v32,
              v36);
      if ( (v31 & 0x80000000) == 0 )
      {
        *((_DWORD *)a3 + 8) = 1;
        v21 = CoTaskMemAlloc(0x28u);
        *((_QWORD *)a3 + 5) = v21;
        if ( !v21 )
        {
          v22 = pv;
          CoTaskMemFree(*(LPVOID *)pv);
          CoTaskMemFree(v22);
          v23 = v35;
          CoTaskMemFree(*v35);
          CoTaskMemFree(v23);
          v24 = v32;
          v25 = 0;
          for ( j = v36[0]; v25 < v24; ++v25 )
            CoTaskMemFree(j[v25]);
          CoTaskMemFree(j);
          v31 = -2147024882;
          CPackageDefinitionFile::~CPackageDefinitionFile((CPackageDefinitionFile *)v40);
          goto LABEL_31;
        }
        *v21 = 0;
        v21[1] = 0;
        *((_QWORD *)v21 + 4) = 0;
        v27 = pv;
        **((_QWORD **)a3 + 5) = *(_QWORD *)pv;
        CoTaskMemFree(v27);
        v28 = v35;
        *(_QWORD *)(*((_QWORD *)a3 + 5) + 8LL) = *v35;
        CoTaskMemFree(v28);
        *(_QWORD *)(*((_QWORD *)a3 + 5) + 16LL) = v34[0] != 0;
        *(_DWORD *)(*((_QWORD *)a3 + 5) + 24LL) = 0;
        *(_DWORD *)(*((_QWORD *)a3 + 5) + 28LL) = v32;
        *(unsigned __int16 ***)(*((_QWORD *)a3 + 5) + 32LL) = v36[0];
      }
      CPackageDefinitionFile::~CPackageDefinitionFile((CPackageDefinitionFile *)v40);
    }
LABEL_31:
    CoTaskMemFree(v10);
    CoTaskMemFree(v9);
    CImpersonate::Cleanup((CImpersonate *)&ppInterface, (int *)&v31);
    v8 = v31;
    if ( (v31 & 0x80000000) != 0 )
    {
      CoTaskMemFree(*(LPVOID *)a3);
      v29 = (void *)*((_QWORD *)a3 + 1);
      *(_QWORD *)a3 = 0;
      CoTaskMemFree(v29);
      *((_QWORD *)a3 + 1) = 0;
      if ( *((_QWORD *)a3 + 5) )
      {
        for ( k = 0; k < *((_DWORD *)a3 + 8); ++k )
          CAppImport::ClearImportAppInfo((LPVOID *)(*((_QWORD *)a3 + 5) + 40LL * k));
        CoTaskMemFree(*((LPVOID *)a3 + 5));
        *((_QWORD *)a3 + 5) = 0;
      }
      *((_DWORD *)a3 + 8) = 0;
      *((GUID *)a3 + 1) = GUID_NULL;
    }
  }
  CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
  return v8;
}

```

## disassembly

```asm
0x1800434f0  mov     [rsp-8+arg_18], rbx
0x1800434f5  push    rbp
0x1800434f6  push    rsi
0x1800434f7  push    rdi
0x1800434f8  push    r12
0x1800434fa  push    r13
0x1800434fc  push    r14
0x1800434fe  push    r15
0x180043500  lea     rbp, [rsp-0E0h]
0x180043508  sub     rsp, 1E0h
0x18004350f  mov     rax, cs:__security_cookie
0x180043516  xor     rax, rsp
0x180043519  mov     [rbp+110h+var_40], rax
0x180043520  xor     r15d, r15d
0x180043523  mov     rdi, r8
0x180043526  mov     r12, rdx
0x180043529  mov     r13, rcx
0x18004352c  test    r8, r8
0x18004352f  jnz     short loc_18004353B
0x180043531  mov     eax, 80004003h
0x180043536  jmp     loc_1800438C8
0x18004353b  xorps   xmm0, xmm0
0x18004353e  movups  xmmword ptr [r8], xmm0
0x180043542  movups  xmmword ptr [r8+10h], xmm0
0x180043547  movups  xmmword ptr [r8+20h], xmm0
0x18004354c  test    r12, r12
0x18004354f  jnz     short loc_18004355B
0x180043551  mov     eax, 80070057h
0x180043556  jmp     loc_1800438C8
0x18004355b  lea     rcx, [rsp+210h+ppInterface]; ppInterface
0x180043560  mov     [rsp+210h+ppInterface], r15
0x180043565  mov     [rsp+210h+var_198], r15d
0x18004356a  mov     [rbp+110h+var_190], r15
0x18004356e  call    ?ImpersonateClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateClient(void)
0x180043573  mov     ebx, eax
0x180043575  test    eax, eax
0x180043577  jnz     loc_1800438BC
0x18004357d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180043584  lea     r8, [rsp+210h+var_1CC]; unsigned int *
0x180043589  mov     [rsp+210h+var_1CC], r15d
0x18004358e  mov     rdx, r12; unsigned __int16 *
0x180043591  mov     [rsp+210h+pv], r15
0x180043596  movdqu  xmmword ptr [rsp+210h+var_1B0], xmm0
0x18004359c  mov     r14, r15
0x18004359f  mov     qword ptr [rsp+210h+var_1C0], r15
0x1800435a4  mov     rsi, r15
0x1800435a7  call    ?GetAplCountFromMsi@CAppImport@@AEAAJPEBGPEAK@Z; CAppImport::GetAplCountFromMsi(ushort const *,ulong *)
0x1800435ac  mov     [rsp+210h+var_1D0], eax
0x1800435b0  test    eax, eax
0x1800435b2  js      loc_1800436A0
0x1800435b8  mov     r15d, [rsp+210h+var_1CC]
0x1800435bd  mov     eax, 0FFFFFFFFh
0x1800435c2  mov     [rdi+20h], r15d
0x1800435c6  lea     rbx, [r15+r15*4]
0x1800435ca  shl     rbx, 3
0x1800435ce  cmp     rbx, rax
0x1800435d1  ja      loc_180043693
0x1800435d7  mov     ecx, ebx; cb
0x1800435d9  mov     [rsp+210h+var_1D0], esi
0x1800435dd  call    cs:__imp_CoTaskMemAlloc
0x1800435e3  mov     [rdi+28h], rax
0x1800435e7  test    rax, rax
0x1800435ea  jnz     short loc_1800435FC
0x1800435ec  mov     [rsp+210h+var_1D0], 8007000Eh
0x1800435f4  xor     r15d, r15d
0x1800435f7  jmp     loc_180043832
0x1800435fc  mov     r8, rbx; Size
0x1800435ff  xor     edx, edx; Val
0x180043601  mov     rcx, rax; void *
0x180043604  call    memset_0
0x180043609  xor     ebx, ebx
0x18004360b  cmp     ebx, r15d
0x18004360e  jnb     short loc_180043672
0x180043610  xor     eax, eax
0x180043612  lea     rcx, [rbx+rbx*4]
0x180043616  test    rsi, rsi
0x180043619  lea     r10, [rsp+210h+var_1C0]
0x18004361e  lea     r8, [rsp+210h+pv]
0x180043623  cmovnz  r8, rax
0x180043627  lea     rdx, [rsp+210h+var_1B0]
0x18004362c  cmovnz  rdx, rax
0x180043630  cmovnz  r10, rax
0x180043634  mov     rax, [rdi+28h]
0x180043638  mov     [rsp+210h+var_1E0], rdx; struct _GUID *
0x18004363d  mov     rdx, r12; unsigned __int16 *
0x180043640  mov     [rsp+210h+var_1E8], r8; unsigned __int16 **
0x180043645  mov     r8d, ebx; unsigned int
0x180043648  mov     [rsp+210h+var_1F0], r10; unsigned __int16 **
0x18004364d  lea     r9, [rax+rcx*8]; struct tagImportAppInfo *
0x180043651  lea     rcx, [r13-8]; this
0x180043655  call    ?QueryApplicationFromAPL@CAppImport@@AEAAJPEBGKPEAUtagImportAppInfo@@PEAPEAG2PEAU_GUID@@@Z; CAppImport::QueryApplicationFromAPL(ushort const *,ulong,tagImportAppInfo *,ushort * *,ushort * *,_GUID *)
0x18004365a  mov     rsi, qword ptr [rsp+210h+var_1C0]
0x18004365f  mov     [rsp+210h+var_1D0], eax
0x180043663  test    eax, eax
0x180043665  js      short loc_18004366B
0x180043667  inc     ebx
0x180043669  jmp     short loc_18004360B
0x18004366b  mov     r14, [rsp+210h+pv]
0x180043670  jmp     short loc_1800435F4
0x180043672  movups  xmm0, xmmword ptr [rsp+210h+var_1B0]
0x180043677  mov     rax, [rsp+210h+pv]
0x18004367c  xor     r15d, r15d
0x18004367f  mov     [rdi], rsi
0x180043682  mov     esi, r15d
0x180043685  movdqu  xmmword ptr [rdi+10h], xmm0
0x18004368a  mov     [rdi+8], rax
0x18004368e  jmp     loc_180043832
0x180043693  mov     [rsp+210h+var_1D0], 80070216h
0x18004369b  jmp     loc_1800435F4
0x1800436a0  cmp     eax, 80110408h
0x1800436a5  jz      short loc_1800436B2
0x1800436a7  cmp     eax, 8007006Eh
0x1800436ac  jnz     loc_180043832
0x1800436b2  lea     rdx, [r13+58h]; struct _GUID *
0x1800436b6  lea     rcx, [rbp+110h+var_180]; this
0x1800436ba  call    ??0CPackageDefinitionFile@@QEAA@AEBU_GUID@@@Z; CPackageDefinitionFile::CPackageDefinitionFile(_GUID const &)
0x1800436bf  lea     rax, [rsp+210h+var_1B0]
0x1800436c4  mov     [rsp+210h+var_1D0], r15d
0x1800436c9  mov     [rsp+210h+var_1D8], rax; unsigned __int16 ***
0x1800436ce  lea     r9, [rsp+210h+pv]; unsigned __int16 ***
0x1800436d3  lea     rax, [rsp+210h+var_1CC]
0x1800436d8  mov     [rsp+210h+pv], r15
0x1800436dd  mov     [rsp+210h+var_1E0], rax; unsigned int *
0x1800436e2  lea     r8, [rsp+210h+var_1D0]; unsigned int *
0x1800436e7  lea     rax, [rsp+210h+var_1C0]
0x1800436ec  mov     [rsp+210h+var_1B8], r15
0x1800436f1  mov     [rsp+210h+var_1E8], rax; unsigned int *
0x1800436f6  lea     rcx, [rbp+110h+var_180]; this
0x1800436fa  lea     rax, [rsp+210h+var_1B8]
0x1800436ff  mov     [rsp+210h+var_1C0], r15d
0x180043704  mov     rdx, r12; unsigned __int16 *
0x180043707  mov     [rsp+210h+var_1F0], rax; unsigned __int16 ***
0x18004370c  mov     [rsp+210h+var_1CC], r15d
0x180043711  mov     [rsp+210h+var_1B0], r15
0x180043716  call    ?QueryPackageFromFile@CPackageDefinitionFile@@QEAAJPEAGPEAKPEAPEAPEAG2112@Z; CPackageDefinitionFile::QueryPackageFromFile(ushort *,ulong *,ushort * * *,ushort * * *,ulong *,ulong *,ushort * * *)
0x18004371b  mov     [rsp+210h+var_1D0], eax
0x18004371f  test    eax, eax
0x180043721  js      loc_180043829
0x180043727  mov     ecx, 28h ; '('; cb
0x18004372c  mov     dword ptr [rdi+20h], 1
0x180043733  call    cs:__imp_CoTaskMemAlloc
0x180043739  mov     [rdi+28h], rax
0x18004373d  test    rax, rax
0x180043740  jnz     short loc_1800437B4
0x180043742  mov     rbx, [rsp+210h+pv]
0x180043747  mov     rcx, [rbx]; pv
0x18004374a  call    cs:__imp_CoTaskMemFree
0x180043750  mov     rcx, rbx; pv
0x180043753  call    cs:__imp_CoTaskMemFree
0x180043759  mov     rbx, [rsp+210h+var_1B8]
0x18004375e  mov     rcx, [rbx]; pv
0x180043761  call    cs:__imp_CoTaskMemFree
0x180043767  mov     rcx, rbx; pv
0x18004376a  call    cs:__imp_CoTaskMemFree
0x180043770  mov     r12d, [rsp+210h+var_1CC]
0x180043775  mov     ebx, r15d
0x180043778  mov     r15, [rsp+210h+var_1B0]
0x18004377d  test    r12d, r12d
0x180043780  jz      short loc_180043795
0x180043782  mov     ecx, ebx
0x180043784  mov     rcx, [r15+rcx*8]; pv
0x180043788  call    cs:__imp_CoTaskMemFree
0x18004378e  inc     ebx
0x180043790  cmp     ebx, r12d
0x180043793  jb      short loc_180043782
0x180043795  mov     rcx, r15; pv
0x180043798  call    cs:__imp_CoTaskMemFree
0x18004379e  lea     rcx, [rbp+110h+var_180]; this
0x1800437a2  mov     [rsp+210h+var_1D0], 8007000Eh
0x1800437aa  call    ??1CPackageDefinitionFile@@QEAA@XZ; CPackageDefinitionFile::~CPackageDefinitionFile(void)
0x1800437af  jmp     loc_1800435F4
0x1800437b4  xorps   xmm0, xmm0
0x1800437b7  xor     ecx, ecx
0x1800437b9  movups  xmmword ptr [rax], xmm0
0x1800437bc  movups  xmmword ptr [rax+10h], xmm0
0x1800437c0  mov     [rax+20h], rcx
0x1800437c4  mov     rcx, [rsp+210h+pv]; pv
0x1800437c9  mov     rdx, [rdi+28h]
0x1800437cd  mov     rax, [rcx]
0x1800437d0  mov     [rdx], rax
0x1800437d3  call    cs:__imp_CoTaskMemFree
0x1800437d9  mov     rcx, [rsp+210h+var_1B8]; pv
0x1800437de  mov     rdx, [rdi+28h]
0x1800437e2  mov     rax, [rcx]
0x1800437e5  mov     [rdx+8], rax
0x1800437e9  call    cs:__imp_CoTaskMemFree
0x1800437ef  mov     rax, [rdi+28h]
0x1800437f3  mov     ecx, r15d
0x1800437f6  cmp     [rsp+210h+var_1C0], r15d
0x1800437fb  setnz   cl
0x1800437fe  mov     [rax+10h], ecx
0x180043801  mov     rax, [rdi+28h]
0x180043805  mov     [rax+14h], r15d
0x180043809  mov     rax, [rdi+28h]
0x18004380d  mov     [rax+18h], r15d
0x180043811  mov     rdx, [rdi+28h]
0x180043815  mov     eax, [rsp+210h+var_1CC]
0x180043819  mov     [rdx+1Ch], eax
0x18004381c  mov     rdx, [rdi+28h]
0x180043820  mov     rax, [rsp+210h+var_1B0]
0x180043825  mov     [rdx+20h], rax
0x180043829  lea     rcx, [rbp+110h+var_180]; this
0x18004382d  call    ??1CPackageDefinitionFile@@QEAA@XZ; CPackageDefinitionFile::~CPackageDefinitionFile(void)
0x180043832  mov     rcx, rsi; pv
0x180043835  call    cs:__imp_CoTaskMemFree
0x18004383b  mov     rcx, r14; pv
0x18004383e  call    cs:__imp_CoTaskMemFree
0x180043844  lea     rdx, [rsp+210h+var_1D0]; int *
0x180043849  lea     rcx, [rsp+210h+ppInterface]; this
0x18004384e  call    ?Cleanup@CImpersonate@@QEAAXPEAJ@Z; CImpersonate::Cleanup(long *)
0x180043853  mov     ebx, [rsp+210h+var_1D0]
0x180043857  test    ebx, ebx
0x180043859  jns     short loc_1800438BC
0x18004385b  mov     rcx, [rdi]; pv
0x18004385e  call    cs:__imp_CoTaskMemFree
0x180043864  mov     rcx, [rdi+8]; pv
0x180043868  mov     [rdi], r15
0x18004386b  call    cs:__imp_CoTaskMemFree
0x180043871  mov     [rdi+8], r15
0x180043875  cmp     [rdi+28h], r15
0x180043879  jz      short loc_1800438AC
0x18004387b  mov     esi, r15d
0x18004387e  cmp     [rdi+20h], r15d
0x180043882  jbe     short loc_18004389E
0x180043884  mov     eax, esi
0x180043886  lea     rcx, [rax+rax*4]
0x18004388a  mov     rax, [rdi+28h]
0x18004388e  lea     rcx, [rax+rcx*8]; struct tagImportAppInfo *
0x180043892  call    ?ClearImportAppInfo@CAppImport@@CAXPEAUtagImportAppInfo@@@Z; CAppImport::ClearImportAppInfo(tagImportAppInfo *)
0x180043897  inc     esi
0x180043899  cmp     esi, [rdi+20h]
0x18004389c  jb      short loc_180043884
0x18004389e  mov     rcx, [rdi+28h]; pv
0x1800438a2  call    cs:__imp_CoTaskMemFree
0x1800438a8  mov     [rdi+28h], r15
0x1800438ac  mov     [rdi+20h], r15d
0x1800438b0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800438b7  movdqu  xmmword ptr [rdi+10h], xmm0
0x1800438bc  lea     rcx, [rsp+210h+ppInterface]; this
0x1800438c1  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1800438c6  mov     eax, ebx
0x1800438c8  mov     rcx, [rbp+110h+var_40]
0x1800438cf  xor     rcx, rsp; StackCookie
0x1800438d2  call    __security_check_cookie
0x1800438d7  mov     rbx, [rsp+210h+arg_18]
0x1800438df  add     rsp, 1E0h
0x1800438e6  pop     r15
0x1800438e8  pop     r14
0x1800438ea  pop     r13
0x1800438ec  pop     r12
0x1800438ee  pop     rdi
0x1800438ef  pop     rsi
0x1800438f0  pop     rbp
0x1800438f1  retn
```
