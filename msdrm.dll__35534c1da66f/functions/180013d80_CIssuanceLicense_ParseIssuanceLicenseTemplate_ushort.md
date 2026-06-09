# CIssuanceLicense::ParseIssuanceLicenseTemplate(ushort *)

- ea: `0x180013d80`
- end: `0x180014158`
- name: `?ParseIssuanceLicenseTemplate@CIssuanceLicense@@QEAAJPEAG@Z`
- size: `984`
- prototype: `__int64 __fastcall(CIssuanceLicense *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config`

## callers

- `0x180004970`

## callees

- `0x180001244`
- `0x180001284`
- `0x180001290`
- `0x180012908`
- `0x1800129e8`
- `0x180013630`
- `0x180013a08`
- `0x180013d80`
- `0x180014160`
- `0x180014310`
- `0x180014490`
- `0x180014b20`
- `0x18003bb68`
- `0x18003db94`
- `0x18003dcb4`
- `0x180040220`
- `0x180040380`
- `0x180040648`
- `0x180040940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014138`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014138`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013daf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013daf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIssuanceLicense::ParseIssuanceLicenseTemplate(CIssuanceLicense *this, unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  unsigned int *v5; // r12
  __int64 *v6; // rax
  __int64 *v7; // rdi
  int LicenseObject; // esi
  __int64 *v9; // r14
  __int64 v10; // r13
  unsigned int v11; // r15d
  unsigned int v12; // r12d
  unsigned int v13; // r13d
  unsigned __int8 *v14; // rax
  int v16; // [rsp+20h] [rbp-68h]
  int v17; // [rsp+24h] [rbp-64h]
  __int64 v18; // [rsp+28h] [rbp-60h]
  __int64 v19; // [rsp+30h] [rbp-58h]
  __int64 v20; // [rsp+38h] [rbp-50h]
  unsigned int v21; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v22; // [rsp+A0h] [rbp+18h] BYREF
  __int64 *v23; // [rsp+A8h] [rbp+20h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v21 = 0;
  v22 = 0;
  operator delete(*((void **)this + 95));
  *((_QWORD *)this + 95) = 0;
  v5 = (unsigned int *)((char *)this + 768);
  *((_DWORD *)this + 192) = 0;
  *((_DWORD *)this + 193) = 0;
  v6 = (__int64 *)operator new(0x28u);
  v7 = v6;
  v23 = v6;
  if ( !v6 )
  {
    LicenseObject = -2147024882;
    goto LABEL_38;
  }
  v6[1] = 0;
  *((_DWORD *)v6 + 4) = 0;
  v6[3] = 0;
  *((_DWORD *)v6 + 1) = 1;
  LicenseObject = CDRMLicense::ParseLicense((CDRMLicense *)v6, a2);
  if ( LicenseObject >= 0 )
  {
    if ( *((_DWORD *)this + 146)
      || (LicenseObject = CIssuanceLicense::ParseInitialData(this, (struct CDRMLicense *)v7), LicenseObject >= 0) )
    {
      v9 = v7 + 4;
      v10 = v7[4];
      v20 = v10;
      v17 = *(_DWORD *)v7;
      LicenseObject = CDRMLicense::GetLicenseObject((CDRMLicense *)v7, L"work", 0);
      if ( LicenseObject >= 0 )
      {
        if ( *((_DWORD *)this + 146)
          || (LicenseObject = CIssuanceLicense::ParseMetaData(this, (struct CDRMLicense *)v7), LicenseObject >= 0)
          && (LicenseObject = CIssuanceLicense::ParseOwner(this, (struct CDRMLicense *)v7), LicenseObject >= 0)
          && (LicenseObject = CIssuanceLicense::ParseConditionList(this, (struct CDRMLicense *)v7), LicenseObject >= 0) )
        {
          LicenseObject = CDRMLicense::GetLicenseObjectCount((CDRMLicense *)v7, L"rights-group", &v21);
          if ( LicenseObject >= 0 )
          {
            v19 = *v9;
            v16 = *(_DWORD *)v7;
            v11 = 0;
            if ( v21 )
            {
              while ( 1 )
              {
                LicenseObject = CDRMLicense::GetLicenseObject((CDRMLicense *)v7, L"rights-group", v11);
                if ( LicenseObject < 0 )
                  goto LABEL_35;
                LicenseObject = CDRMLicense::GetLicenseObjectCount((CDRMLicense *)v7, L"right", &v22);
                if ( LicenseObject < 0 )
                  goto LABEL_35;
                v18 = *v9;
                LODWORD(v23) = *(_DWORD *)v7;
                v12 = 0;
                v13 = v22;
                if ( v22 )
                {
                  do
                  {
                    LicenseObject = CDRMLicense::GetLicenseObject((CDRMLicense *)v7, L"right", v12);
                    if ( LicenseObject < 0 )
                      goto LABEL_35;
                    LicenseObject = CIssuanceLicense::ParseRight(this, (CRight **)v7);
                    if ( LicenseObject < 0 )
                      goto LABEL_35;
                    *v9 = v18;
                    *(_DWORD *)v7 = (_DWORD)v23;
                  }
                  while ( ++v12 < v13 );
                }
                *v9 = v19;
                *(_DWORD *)v7 = v16;
                if ( ++v11 >= v21 )
                {
                  v5 = (unsigned int *)((char *)this + 768);
                  v10 = v20;
                  break;
                }
              }
            }
            *v9 = v10;
            *(_DWORD *)v7 = v17;
            if ( !*((_DWORD *)this + 146) )
            {
              LicenseObject = CIssuanceLicense::ParsePolicyList(this, (struct CDRMLicense *)v7);
              if ( LicenseObject < 0 )
                goto LABEL_35;
              LicenseObject = CIssuanceLicense::ParseAuthenticatedData(this, (struct CDRMLicense *)v7);
              if ( LicenseObject < 0 )
                goto LABEL_35;
              LicenseObject = CIssuanceLicense::ParseDescriptor(this, (struct CDRMLicense *)v7);
              if ( LicenseObject < 0 )
                goto LABEL_35;
              *v9 = v10;
              *(_DWORD *)v7 = v17;
            }
            if ( (unsigned int)CDRMLicense::GetLicenseObject((CDRMLicense *)v7, L"issuer", 0) == -2147168490 )
            {
LABEL_34:
              LicenseObject = 0;
              goto LABEL_35;
            }
            LicenseObject = CDRMLicense::ExtractPublicKey((CDRMLicense *)v7, (unsigned int *)this + 193, v5, 0);
            if ( LicenseObject < 0 )
              goto LABEL_35;
            v14 = (unsigned __int8 *)operator new[](*v5);
            *((_QWORD *)this + 95) = v14;
            if ( !v14 )
            {
              LicenseObject = -2147024882;
              goto LABEL_35;
            }
            LicenseObject = CDRMLicense::ExtractPublicKey((CDRMLicense *)v7, (unsigned int *)this + 193, v5, v14);
            if ( LicenseObject >= 0 )
            {
              *v9 = v10;
              *(_DWORD *)v7 = v17;
              if ( (int)CDRMLicense::VerifySignature((CDRMLicense *)v7, 0) < 0
                || (int)CDRMLicense::VerifyAlgorithms(
                          (CDRMLicense *)v7,
                          (const struct _DRM_CRYPTO_VERSION_PARAMETERS *)qword_180061048,
                          0,
                          1) < 0 )
              {
                LicenseObject = -2147168428;
                goto LABEL_35;
              }
              *((_DWORD *)this + 189) = 1;
              goto LABEL_34;
            }
          }
        }
      }
    }
  }
LABEL_35:
  CDRMXML::~CDRMXML((CDRMXML *)(v7 + 1));
  operator delete(v7);
  if ( LicenseObject == -2147168490 )
    LicenseObject = -2147168428;
LABEL_38:
  *((_DWORD *)this + 146) = 0;
  LeaveCriticalSection(v4);
  return (unsigned int)LicenseObject;
}

```

## disassembly

```asm
0x180013d80  mov     rax, rsp
0x180013d83  push    rbp
0x180013d84  push    rsi
0x180013d85  push    rdi
0x180013d86  push    r12
0x180013d88  push    r13
0x180013d8a  push    r14
0x180013d8c  push    r15
0x180013d8e  sub     rsp, 50h
0x180013d92  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180013d9a  mov     [rax+10h], rbx
0x180013d9e  mov     rsi, rdx
0x180013da1  mov     rbp, rcx
0x180013da4  lea     rbx, [rcx+58h]
0x180013da8  mov     [rax-40h], rbx
0x180013dac  mov     rcx, rbx; lpCriticalSection
0x180013daf  call    cs:__imp_EnterCriticalSection
0x180013db5  nop
0x180013db6  mov     [rsp+88h+arg_0], 0
0x180013dc1  mov     [rsp+88h+arg_10], 0
0x180013dcc  mov     rcx, [rbp+2F8h]; Block
0x180013dd3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013dd8  mov     qword ptr [rbp+2F8h], 0
0x180013de3  lea     r12, [rbp+300h]
0x180013dea  mov     dword ptr [r12], 0
0x180013df2  mov     dword ptr [rbp+304h], 0
0x180013dfc  mov     ecx, 28h ; '('; Size
0x180013e01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013e06  mov     rdi, rax
0x180013e09  mov     [rsp+88h+arg_18], rax
0x180013e11  test    rax, rax
0x180013e14  jz      loc_180014126
0x180013e1a  mov     qword ptr [rax+8], 0
0x180013e22  mov     dword ptr [rax+10h], 0
0x180013e29  mov     qword ptr [rax+18h], 0
0x180013e31  mov     dword ptr [rax+4], 1
0x180013e38  test    rax, rax
0x180013e3b  jz      loc_180014126
0x180013e41  mov     rdx, rsi; unsigned __int16 *
0x180013e44  mov     rcx, rax; this
0x180013e47  call    ?ParseLicense@CDRMLicense@@QEAAJPEBG@Z; CDRMLicense::ParseLicense(ushort const *)
0x180013e4c  mov     esi, eax
0x180013e4e  test    eax, eax
0x180013e50  js      loc_180014106
0x180013e56  cmp     dword ptr [rbp+248h], 0
0x180013e5d  jnz     short loc_180013E74
0x180013e5f  mov     rdx, rdi; struct CDRMLicense *
0x180013e62  mov     rcx, rbp; this
0x180013e65  call    ?ParseInitialData@CIssuanceLicense@@AEAAJPEAVCDRMLicense@@@Z; CIssuanceLicense::ParseInitialData(CDRMLicense *)
0x180013e6a  mov     esi, eax
0x180013e6c  test    eax, eax
0x180013e6e  js      loc_180014106
0x180013e74  lea     r14, [rdi+20h]
0x180013e78  mov     r13, [r14]
0x180013e7b  mov     [rsp+88h+var_50], r13
0x180013e80  mov     eax, [rdi]
0x180013e82  mov     [rsp+88h+var_64], eax
0x180013e86  xor     r8d, r8d; unsigned int
0x180013e89  lea     rdx, aWork; "work"
0x180013e90  mov     rcx, rdi; this
0x180013e93  call    ?GetLicenseObject@CDRMLicense@@QEAAJPEBGI@Z; CDRMLicense::GetLicenseObject(ushort const *,uint)
0x180013e98  mov     esi, eax
0x180013e9a  test    eax, eax
0x180013e9c  js      loc_180014106
0x180013ea2  cmp     dword ptr [rbp+248h], 0
0x180013ea9  jnz     short loc_180013EEA
0x180013eab  mov     rdx, rdi; struct CDRMLicense *
0x180013eae  mov     rcx, rbp; this
0x180013eb1  call    ?ParseMetaData@CIssuanceLicense@@AEAAJPEAVCDRMLicense@@@Z; CIssuanceLicense::ParseMetaData(CDRMLicense *)
0x180013eb6  mov     esi, eax
0x180013eb8  test    eax, eax
0x180013eba  js      loc_180014106
0x180013ec0  mov     rdx, rdi; struct CDRMLicense *
0x180013ec3  mov     rcx, rbp; this
0x180013ec6  call    ?ParseOwner@CIssuanceLicense@@AEAAJPEAVCDRMLicense@@@Z; CIssuanceLicense::ParseOwner(CDRMLicense *)
0x180013ecb  mov     esi, eax
0x180013ecd  test    eax, eax
0x180013ecf  js      loc_180014106
0x180013ed5  mov     rdx, rdi; struct CDRMLicense *
0x180013ed8  mov     rcx, rbp; this
0x180013edb  call    ?ParseConditionList@CIssuanceLicense@@AEAAJPEAVCDRMLicense@@@Z; CIssuanceLicense::ParseConditionList(CDRMLicense *)
0x180013ee0  mov     esi, eax
0x180013ee2  test    eax, eax
0x180013ee4  js      loc_180014106
0x180013eea  lea     r8, [rsp+88h+arg_0]; unsigned int *
0x180013ef2  lea     rdx, aRightsGroup; "rights-group"
0x180013ef9  mov     rcx, rdi; this
0x180013efc  call    ?GetLicenseObjectCount@CDRMLicense@@QEAAJPEBGPEAI@Z; CDRMLicense::GetLicenseObjectCount(ushort const *,uint *)
0x180013f01  mov     esi, eax
0x180013f03  test    eax, eax
0x180013f05  js      loc_180014106
0x180013f0b  mov     rax, [r14]
0x180013f0e  mov     [rsp+88h+var_58], rax
0x180013f13  mov     eax, [rdi]
0x180013f15  mov     [rsp+88h+var_68], eax
0x180013f19  xor     r15d, r15d
0x180013f1c  cmp     [rsp+88h+arg_0], r15d
0x180013f24  jbe     loc_180013FFD
0x180013f2a  mov     r8d, r15d; unsigned int
0x180013f2d  lea     rdx, aRightsGroup; "rights-group"
0x180013f34  mov     rcx, rdi; this
0x180013f37  call    ?GetLicenseObject@CDRMLicense@@QEAAJPEBGI@Z; CDRMLicense::GetLicenseObject(ushort const *,uint)
0x180013f3c  mov     esi, eax
0x180013f3e  test    eax, eax
0x180013f40  js      loc_180014106
0x180013f46  lea     r8, [rsp+88h+arg_10]; unsigned int *
0x180013f4e  lea     rdx, aRight; "right"
0x180013f55  mov     rcx, rdi; this
0x180013f58  call    ?GetLicenseObjectCount@CDRMLicense@@QEAAJPEBGPEAI@Z; CDRMLicense::GetLicenseObjectCount(ushort const *,uint *)
0x180013f5d  mov     esi, eax
0x180013f5f  test    eax, eax
0x180013f61  js      loc_180014106
0x180013f67  mov     rax, [r14]
0x180013f6a  mov     [rsp+88h+var_60], rax
0x180013f6f  mov     eax, [rdi]
0x180013f71  mov     dword ptr [rsp+88h+arg_18], eax
0x180013f78  xor     r12d, r12d
0x180013f7b  mov     r13d, [rsp+88h+arg_10]
0x180013f83  test    r13d, r13d
0x180013f86  jz      short loc_180013FD2
0x180013f88  mov     r8d, r12d; unsigned int
0x180013f8b  lea     rdx, aRight; "right"
0x180013f92  mov     rcx, rdi; this
0x180013f95  call    ?GetLicenseObject@CDRMLicense@@QEAAJPEBGI@Z; CDRMLicense::GetLicenseObject(ushort const *,uint)
0x180013f9a  mov     esi, eax
0x180013f9c  test    eax, eax
0x180013f9e  js      loc_180014106
0x180013fa4  mov     rdx, rdi; struct CDRMLicense *
0x180013fa7  mov     rcx, rbp; this
0x180013faa  call    ?ParseRight@CIssuanceLicense@@AEAAJPEAVCDRMLicense@@@Z; CIssuanceLicense::ParseRight(CDRMLicense *)
0x180013faf  mov     esi, eax
0x180013fb1  test    eax, eax
0x180013fb3  js      loc_180014106
0x180013fb9  mov     rax, [rsp+88h+var_60]
0x180013fbe  mov     [r14], rax
0x180013fc1  mov     eax, dword ptr [rsp+88h+arg_18]
0x180013fc8  mov     [rdi], eax
0x180013fca  inc     r12d
0x180013fcd  cmp     r12d, r13d
0x180013fd0  jb      short loc_180013F88
0x180013fd2  mov     rax, [rsp+88h+var_58]
0x180013fd7  mov     [r14], rax
0x180013fda  mov     eax, [rsp+88h+var_68]
0x180013fde  mov     [rdi], eax
0x180013fe0  inc     r15d
0x180013fe3  cmp     r15d, [rsp+88h+arg_0]
0x180013feb  jb      loc_180013F2A
0x180013ff1  lea     r12, [rbp+300h]
0x180013ff8  mov     r13, [rsp+88h+var_50]
0x180013ffd  mov     [r14], r13
0x180014000  mov     r15d, [rsp+88h+var_64]
0x180014005  mov     [rdi], r15d
0x180014008  cmp     dword ptr [rbp+248h], 0
0x18001400f  jnz     short loc_180014056
0x180014011  mov     rdx, rdi; struct CDRMLicense *
0x180014014  mov     rcx, rbp; this
0x180014017  call    ?ParsePolicyList@CIssuanceLicense@@AEAAJPEAVCDRMLicense@@@Z; CIssuanceLicense::ParsePolicyList(CDRMLicense *)
0x18001401c  mov     esi, eax
0x18001401e  test    eax, eax
0x180014020  js      loc_180014106
0x180014026  mov     rdx, rdi; struct CDRMLicense *
0x180014029  mov     rcx, rbp; this
0x18001402c  call    ?ParseAuthenticatedData@CIssuanceLicense@@AEAAJPEAVCDRMLicense@@@Z; CIssuanceLicense::ParseAuthenticatedData(CDRMLicense *)
0x180014031  mov     esi, eax
0x180014033  test    eax, eax
0x180014035  js      loc_180014106
0x18001403b  mov     rdx, rdi; struct CDRMLicense *
0x18001403e  mov     rcx, rbp; this
0x180014041  call    ?ParseDescriptor@CIssuanceLicense@@AEAAJPEAVCDRMLicense@@@Z; CIssuanceLicense::ParseDescriptor(CDRMLicense *)
0x180014046  mov     esi, eax
0x180014048  test    eax, eax
0x18001404a  js      loc_180014106
0x180014050  mov     [r14], r13
0x180014053  mov     [rdi], r15d
0x180014056  xor     r8d, r8d; unsigned int
0x180014059  lea     rdx, aIssuer; "issuer"
0x180014060  mov     rcx, rdi; this
0x180014063  call    ?GetLicenseObject@CDRMLicense@@QEAAJPEBGI@Z; CDRMLicense::GetLicenseObject(ushort const *,uint)
0x180014068  cmp     eax, 8004CF16h
0x18001406d  jz      loc_180014104
0x180014073  xor     r9d, r9d; unsigned __int8 *
0x180014076  mov     r8, r12; unsigned int *
0x180014079  lea     rdx, [rbp+304h]; unsigned int *
0x180014080  mov     rcx, rdi; this
0x180014083  call    ?ExtractPublicKey@CDRMLicense@@QEAAJPEAI0PEAE@Z; CDRMLicense::ExtractPublicKey(uint *,uint *,uchar *)
0x180014088  mov     esi, eax
0x18001408a  test    eax, eax
0x18001408c  js      short loc_180014106
0x18001408e  mov     ecx, [r12]; unsigned __int64
0x180014092  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014097  mov     [rbp+2F8h], rax
0x18001409e  test    rax, rax
0x1800140a1  jnz     short loc_1800140AA
0x1800140a3  mov     esi, 8007000Eh
0x1800140a8  jmp     short loc_180014106
0x1800140aa  mov     r9, rax; unsigned __int8 *
0x1800140ad  mov     r8, r12; unsigned int *
0x1800140b0  lea     rdx, [rbp+304h]; unsigned int *
0x1800140b7  mov     rcx, rdi; this
0x1800140ba  call    ?ExtractPublicKey@CDRMLicense@@QEAAJPEAI0PEAE@Z; CDRMLicense::ExtractPublicKey(uint *,uint *,uchar *)
0x1800140bf  mov     esi, eax
0x1800140c1  test    eax, eax
0x1800140c3  js      short loc_180014106
0x1800140c5  mov     [r14], r13
0x1800140c8  mov     [rdi], r15d
0x1800140cb  xor     edx, edx; unsigned int *
0x1800140cd  mov     rcx, rdi; this
0x1800140d0  call    ?VerifySignature@CDRMLicense@@QEAAJPEAK@Z; CDRMLicense::VerifySignature(ulong *)
0x1800140d5  test    eax, eax
0x1800140d7  jns     short loc_1800140E0
0x1800140d9  mov     esi, 8004CF54h
0x1800140de  jmp     short loc_180014106
0x1800140e0  mov     esi, 1
0x1800140e5  mov     r9d, esi; int
0x1800140e8  xor     r8d, r8d; struct _DRM_CRYPTO_VERSION_PARAMETERS *
0x1800140eb  lea     rdx, qword_180061048; struct _DRM_CRYPTO_VERSION_PARAMETERS *
0x1800140f2  mov     rcx, rdi; this
0x1800140f5  call    ?VerifyAlgorithms@CDRMLicense@@QEAAJPEBU_DRM_CRYPTO_VERSION_PARAMETERS@@0H@Z; CDRMLicense::VerifyAlgorithms(_DRM_CRYPTO_VERSION_PARAMETERS const *,_DRM_CRYPTO_VERSION_PARAMETERS const *,int)
0x1800140fa  test    eax, eax
0x1800140fc  js      short loc_1800140D9
0x1800140fe  mov     [rbp+2F4h], esi
0x180014104  xor     esi, esi
0x180014106  lea     rcx, [rdi+8]; this
0x18001410a  call    ??1CDRMXML@@QEAA@XZ; CDRMXML::~CDRMXML(void)
0x18001410f  mov     rcx, rdi; Block
0x180014112  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014117  cmp     esi, 8004CF16h
0x18001411d  jnz     short loc_18001412B
0x18001411f  mov     esi, 8004CF54h
0x180014124  jmp     short loc_18001412B
0x180014126  mov     esi, 8007000Eh
0x18001412b  mov     dword ptr [rbp+248h], 0
0x180014135  mov     rcx, rbx; lpCriticalSection
0x180014138  call    cs:__imp_LeaveCriticalSection
0x18001413e  mov     eax, esi
0x180014140  mov     rbx, [rsp+88h+arg_8]
0x180014148  add     rsp, 50h
0x18001414c  pop     r15
0x18001414e  pop     r14
0x180014150  pop     r13
0x180014152  pop     r12
0x180014154  pop     rdi
0x180014155  pop     rsi
0x180014156  pop     rbp
0x180014157  retn
```
