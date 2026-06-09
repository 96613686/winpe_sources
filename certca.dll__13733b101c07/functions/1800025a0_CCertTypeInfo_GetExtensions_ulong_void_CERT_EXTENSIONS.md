# CCertTypeInfo::GetExtensions(ulong,void *,_CERT_EXTENSIONS * *)

- ea: `0x1800025a0`
- end: `0x180002ee8`
- name: `?GetExtensions@CCertTypeInfo@@QEAAJKPEAXPEAPEAU_CERT_EXTENSIONS@@@Z`
- size: `2376`
- prototype: `__int64 __fastcall(CCertTypeInfo *this, int, void *, struct _CERT_EXTENSIONS **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180011210`

## callees

- `0x180001334`
- `0x180001bf0`
- `0x180002280`
- `0x1800025a0`
- `0x180002ef0`
- `0x180005944`
- `0x180008610`
- `0x18001052c`
- `0x180011038`
- `0x180012a7c`
- `0x180013a86`
- `0x180038286`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000299a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000299a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ecc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ecc`

## string_xrefs

- `0x180002605`: `pKICriticalExtensions`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::GetExtensions(CCertTypeInfo *this, int a2, void *a3, struct _CERT_EXTENSIONS **a4)
{
  unsigned __int16 *v5; // r12
  unsigned __int16 *v6; // r13
  unsigned __int16 *v7; // rsi
  unsigned __int16 *v8; // r15
  int Property; // eax
  int v11; // edx
  unsigned int v12; // r14d
  int BasicConstraintsValue; // eax
  int EKUValue; // eax
  unsigned __int16 *v15; // rdi
  int KUValue; // eax
  int TypeExtensionValue; // eax
  CCertTypeInfo *v18; // rax
  _DWORD *v19; // rsi
  int PoliciesValue; // eax
  unsigned int v21; // edx
  _DWORD *v22; // rdi
  int v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  int v26; // ecx
  unsigned int v27; // eax
  __int64 v28; // rbx
  struct _CERT_EXTENSIONS *v29; // rax
  struct _CERT_EXTENSIONS *v30; // r11
  struct _CERT_EXTENSIONS *v31; // rbx
  const unsigned __int16 *v32; // rdx
  unsigned int IsCritical; // eax
  _QWORD **v34; // rdx
  __int64 v35; // r11
  const CHAR *v36; // rcx
  unsigned __int16 *v37; // r9
  __int64 v38; // rbx
  const unsigned __int16 *v39; // rdx
  __int64 v40; // rbx
  unsigned int v41; // eax
  unsigned __int16 *v42; // r9
  __int64 v43; // r11
  const wchar_t **v44; // rax
  int v45; // ecx
  __int64 v46; // rbx
  unsigned __int16 *v47; // rdx
  const wchar_t **v48; // rax
  int v49; // ecx
  __int64 v50; // rbx
  const wchar_t **v51; // rax
  int v52; // ecx
  __int64 v53; // rbx
  const wchar_t **v54; // rax
  int v55; // ecx
  const wchar_t **v56; // rax
  __int64 v57; // rdx
  unsigned __int16 *v58; // [rsp+20h] [rbp-48h] BYREF
  void *Src; // [rsp+28h] [rbp-40h] BYREF
  unsigned int *p_cExtension; // [rsp+30h] [rbp-38h]
  unsigned __int16 *v61; // [rsp+38h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 *v63; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int16 *v64; // [rsp+50h] [rbp-18h] BYREF
  unsigned __int16 *v65; // [rsp+58h] [rbp-10h] BYREF

  v65 = 0;
  v5 = 0;
  v64 = 0;
  v6 = 0;
  v63 = 0;
  v7 = 0;
  Src = 0;
  v8 = 0;
  v58 = 0;
  v61 = 0;
  hMem = 0;
  if ( !a4 )
    return 2147500035LL;
  Property = CCertTypeInfo::GetProperty(this, L"pKICriticalExtensions", (unsigned __int16 ***)&hMem);
  v12 = Property;
  if ( !Property )
  {
    if ( !a2 || (a2 & 8) != 0 )
    {
      BasicConstraintsValue = CCertTypeInfo::_GetBasicConstraintsValue(this, &v65);
      v12 = BasicConstraintsValue;
      if ( BasicConstraintsValue )
      {
        CSPrintErrorLineFileData2(0, 0x15200328u, BasicConstraintsValue, 0);
LABEL_146:
        if ( v65 )
          CertFreeString(v65);
        if ( v7 )
          CertFreeString(v7);
        if ( v8 )
          CertFreeString(v8);
        goto LABEL_152;
      }
      if ( (a2 & 8) != 0 && !v65 )
      {
        v12 = -2146885628;
        CSPrintErrorLineFileData2(0, 0x15250328u, -2146885628, 0);
        goto LABEL_152;
      }
    }
    if ( !a2 || (a2 & 4) != 0 )
    {
      EKUValue = CCertTypeInfo::_GetEKUValue(this, &v64);
      v12 = EKUValue;
      if ( EKUValue )
      {
        CSPrintErrorLineFileData2(0, 0x152C0328u, EKUValue, 0);
        v5 = v64;
        v15 = (unsigned __int16 *)Src;
LABEL_142:
        if ( v5 )
          CertFreeString(v5);
        if ( v15 )
          CertFreeString(v15);
        goto LABEL_146;
      }
      v5 = v64;
      if ( (a2 & 4) != 0 && !v64 )
      {
        v12 = -2146885628;
        CSPrintErrorLineFileData2(0, 0x15310328u, -2146885628, 0);
        goto LABEL_146;
      }
    }
    if ( !a2 || (a2 & 2) != 0 )
    {
      KUValue = CCertTypeInfo::_GetKUValue(this, (unsigned __int16 **)&Src);
      v12 = KUValue;
      if ( KUValue )
      {
        CSPrintErrorLineFileData2(0, 0x15380328u, KUValue, 0);
        v15 = (unsigned __int16 *)Src;
        goto LABEL_142;
      }
      if ( (a2 & 2) != 0 )
      {
        v15 = (unsigned __int16 *)Src;
        if ( !Src )
        {
          v12 = -2146885628;
          CSPrintErrorLineFileData2(0, 0x153D0328u, -2146885628, 0);
          goto LABEL_142;
        }
      }
    }
    if ( !a2 || (a2 & 1) != 0 )
    {
      TypeExtensionValue = CCertTypeInfo::_GetTypeExtensionValue(this, v11, &v63);
      v12 = TypeExtensionValue;
      if ( TypeExtensionValue )
      {
        CSPrintErrorLineFileData2(0, 0x15450328u, TypeExtensionValue, 0);
        v6 = v63;
        v15 = (unsigned __int16 *)Src;
        goto LABEL_140;
      }
      v6 = v63;
      if ( (a2 & 1) != 0 && !v63 )
      {
        v12 = -2146885628;
        CSPrintErrorLineFileData2(0, 0x154A0328u, -2146885628, 0);
        v15 = (unsigned __int16 *)Src;
        goto LABEL_142;
      }
    }
    v18 = this;
    if ( *((_DWORD *)this + 22) )
    {
      if ( !a2 )
      {
        v19 = (_DWORD *)((char *)this + 88);
        goto LABEL_38;
      }
      if ( (a2 & 0x20) != 0 )
      {
        v19 = (_DWORD *)((char *)this + 88);
LABEL_38:
        PoliciesValue = CCertTypeInfo::_GetPoliciesValue(this, L"msPKI-Certificate-Policy", a3, &v58);
        v12 = PoliciesValue;
        if ( PoliciesValue )
        {
          CSPrintErrorLineFileData2(0, 0x15540328u, PoliciesValue, 0);
          v7 = v58;
          v15 = (unsigned __int16 *)Src;
          goto LABEL_140;
        }
        v18 = this;
LABEL_42:
        if ( (a2 & 0x20) != 0 )
        {
          if ( !v58 )
          {
            v21 = 358286120;
LABEL_45:
            v12 = -2146885628;
            CSPrintErrorLineFileData2(0, v21, -2146885628, 0);
            v7 = v58;
            v15 = (unsigned __int16 *)Src;
            goto LABEL_140;
          }
        }
        else
        {
          v19 = (_DWORD *)((char *)this + 88);
        }
        if ( *v19 )
        {
          if ( !a2 )
          {
            v22 = v19;
            goto LABEL_52;
          }
          if ( (a2 & 0x10) != 0 )
          {
            v22 = (_DWORD *)((char *)v18 + 88);
LABEL_52:
            v23 = CCertTypeInfo::_GetPoliciesValue(v18, L"msPKI-Certificate-Application-Policy", a3, &v61);
            v12 = v23;
            if ( v23 )
            {
              CSPrintErrorLineFileData2(0, 0x15630328u, v23, 0);
              v8 = v61;
              v7 = v58;
              v15 = (unsigned __int16 *)Src;
LABEL_140:
              if ( v6 )
                CertFreeString(v6);
              goto LABEL_142;
            }
            v8 = v61;
            v18 = this;
LABEL_56:
            if ( (a2 & 0x10) != 0 )
            {
              if ( !v8 )
              {
                v21 = 359269160;
                goto LABEL_45;
              }
            }
            else
            {
              v22 = v19;
            }
            v24 = 0;
            v25 = 1;
            LODWORD(v64) = 0;
            LODWORD(v63) = 1;
            if ( *v22 && (!a2 || (a2 & 0x40) != 0) )
            {
              if ( (*((_DWORD *)v18 + 17) & 0x1000) != 0 )
                v24 = 1;
              LODWORD(v64) = v24;
            }
            if ( v6 )
            {
              v26 = *((_DWORD *)v6 - 1) + 48;
            }
            else
            {
              v26 = 16;
              v25 = 0;
            }
            if ( v5 )
            {
              v26 += *((_DWORD *)v5 - 1) + 32;
              ++v25;
            }
            v15 = (unsigned __int16 *)Src;
            if ( Src )
            {
              v26 += *((_DWORD *)Src - 1) + 32;
              ++v25;
            }
            if ( v65 )
            {
              v26 += *((_DWORD *)v65 - 1) + 32;
              ++v25;
            }
            v7 = v58;
            if ( v58 )
            {
              v26 += *((_DWORD *)v58 - 1) + 32;
              ++v25;
            }
            if ( v8 )
            {
              v26 += *((_DWORD *)v8 - 1) + 32;
              ++v25;
            }
            v27 = v26 + 34;
            v28 = v25 + 1;
            if ( !v24 )
            {
              v27 = v26;
              v28 = v25;
            }
            v29 = (struct _CERT_EXTENSIONS *)LocalAlloc(0, v27);
            Src = v29;
            v30 = v29;
            if ( v29 )
            {
              v29->cExtension = v28;
              p_cExtension = &v29[1].cExtension;
              v31 = &v29[2 * v28 + 1];
              v29->rgExtension = (PCERT_EXTENSION)&v29[1];
              if ( v6 )
              {
                v32 = L"1.3.6.1.4.1.311.20.2";
                if ( *((_DWORD *)this + 22) >= 2u )
                  v32 = L"1.3.6.1.4.1.311.21.7";
                IsCritical = CCertTypeInfo::_IsCritical((CCertTypeInfo *)&v29[1], v32, (const unsigned __int16 **)hMem);
                v34 = (_QWORD **)Src;
                p_cExtension[2] = IsCritical;
                v36 = "1.3.6.1.4.1.311.20.2";
                if ( *(_DWORD *)(v35 + 88) >= 2u )
                  v36 = "1.3.6.1.4.1.311.21.7";
                *v34[1] = v36;
                v34[1][3] = v31;
                *((_DWORD *)v34[1] + 4) = *((_DWORD *)v6 - 1);
                memcpy_0(v31, v6, *((unsigned int *)v6 - 1));
                v30 = (struct _CERT_EXTENSIONS *)Src;
                p_cExtension = (unsigned int *)*((_QWORD *)Src + 1);
                v37 = (unsigned __int16 *)((char *)v31 + p_cExtension[4]);
                v38 = 1;
                v58 = v37;
              }
              else
              {
                v37 = (unsigned __int16 *)v31;
                v58 = (unsigned __int16 *)v31;
                v38 = 0;
              }
              LODWORD(v61) = v38;
              if ( v5 )
              {
                v39 = L"2.5.29.37";
                v40 = 32 * v38;
                if ( *((_DWORD *)this + 22) >= 2u )
                  v39 = L"1.3.6.1.4.1.311.21.10";
                v41 = CCertTypeInfo::_IsCritical(
                        (CCertTypeInfo *)L"1.3.6.1.4.1.311.21.10",
                        v39,
                        (const unsigned __int16 **)hMem);
                v42 = v58;
                p_cExtension[(unsigned __int64)v40 / 4 + 2] = v41;
                *(_QWORD *)(v40 + *(_QWORD *)(v43 + 8)) = "2.5.29.37";
                *(_QWORD *)(*(_QWORD *)(v43 + 8) + v40 + 24) = v42;
                *(_DWORD *)(*(_QWORD *)(v43 + 8) + v40 + 16) = *((_DWORD *)v5 - 1);
                memcpy_0(v42, v5, *((unsigned int *)v5 - 1));
                v30 = (struct _CERT_EXTENSIONS *)Src;
                v37 = (unsigned __int16 *)((char *)v58 + *(unsigned int *)(*((_QWORD *)Src + 1) + v40 + 16));
                v38 = (unsigned int)((_DWORD)v61 + 1);
                v58 = v37;
                LODWORD(v61) = (_DWORD)v61 + 1;
              }
              if ( v15 )
              {
                v44 = (const wchar_t **)hMem;
                p_cExtension = (unsigned int *)hMem;
                if ( hMem )
                {
                  while ( *v44 )
                  {
                    if ( !wcscmp_0(*v44, L"2.5.29.15") )
                    {
                      v30 = (struct _CERT_EXTENSIONS *)Src;
                      v45 = 1;
                      v37 = v58;
                      goto LABEL_102;
                    }
                    v44 = (const wchar_t **)(p_cExtension + 2);
                    p_cExtension += 2;
                  }
                  v30 = (struct _CERT_EXTENSIONS *)Src;
                  v37 = v58;
                }
                v45 = 0;
LABEL_102:
                v46 = v38;
                v30->rgExtension[v46].fCritical = v45;
                v30->rgExtension[v46].pszObjId = (LPSTR)"2.5.29.15";
                v30->rgExtension[v46].Value.pbData = (BYTE *)v37;
                v30->rgExtension[v46].Value.cbData = *((_DWORD *)v15 - 1);
                memcpy_0(v37, v15, *((unsigned int *)v15 - 1));
                v30 = (struct _CERT_EXTENSIONS *)Src;
                v37 = (unsigned __int16 *)((char *)v58 + *(unsigned int *)(v46 * 32 + *((_QWORD *)Src + 1) + 16));
                v38 = (unsigned int)((_DWORD)v61 + 1);
                v58 = v37;
                LODWORD(v61) = (_DWORD)v61 + 1;
              }
              v47 = v65;
              if ( v65 )
              {
                v48 = (const wchar_t **)hMem;
                p_cExtension = (unsigned int *)hMem;
                if ( hMem )
                {
                  while ( *v48 )
                  {
                    if ( !wcscmp_0(*v48, L"2.5.29.19") )
                    {
                      v47 = v65;
                      v49 = 1;
                      v30 = (struct _CERT_EXTENSIONS *)Src;
                      v37 = v58;
                      goto LABEL_111;
                    }
                    v48 = (const wchar_t **)(p_cExtension + 2);
                    p_cExtension += 2;
                  }
                  v47 = v65;
                  v30 = (struct _CERT_EXTENSIONS *)Src;
                  v37 = v58;
                }
                v49 = 0;
LABEL_111:
                v50 = v38;
                v30->rgExtension[v50].fCritical = v49;
                v30->rgExtension[v50].pszObjId = "2.5.29.19";
                v30->rgExtension[v50].Value.pbData = (BYTE *)v37;
                v30->rgExtension[v50].Value.cbData = *((_DWORD *)v47 - 1);
                memcpy_0(v37, v47, *((unsigned int *)v47 - 1));
                v30 = (struct _CERT_EXTENSIONS *)Src;
                v37 = (unsigned __int16 *)((char *)v58 + *(unsigned int *)(v50 * 32 + *((_QWORD *)Src + 1) + 16));
                v38 = (unsigned int)((_DWORD)v61 + 1);
                v58 = v37;
                LODWORD(v61) = (_DWORD)v61 + 1;
              }
              if ( v7 )
              {
                v51 = (const wchar_t **)hMem;
                p_cExtension = (unsigned int *)hMem;
                if ( hMem )
                {
                  while ( *v51 )
                  {
                    if ( !wcscmp_0(*v51, L"2.5.29.32") )
                    {
                      v30 = (struct _CERT_EXTENSIONS *)Src;
                      v52 = 1;
                      v37 = v58;
                      goto LABEL_120;
                    }
                    v51 = (const wchar_t **)(p_cExtension + 2);
                    p_cExtension += 2;
                  }
                  v30 = (struct _CERT_EXTENSIONS *)Src;
                  v37 = v58;
                }
                v52 = 0;
LABEL_120:
                v53 = v38;
                v30->rgExtension[v53].fCritical = v52;
                v30->rgExtension[v53].pszObjId = (LPSTR)"2.5.29.32";
                v30->rgExtension[v53].Value.pbData = (BYTE *)v37;
                v30->rgExtension[v53].Value.cbData = *((_DWORD *)v7 - 1);
                memcpy_0(v37, v7, *((unsigned int *)v7 - 1));
                v30 = (struct _CERT_EXTENSIONS *)Src;
                v37 = (unsigned __int16 *)((char *)v58 + *(unsigned int *)(v53 * 32 + *((_QWORD *)Src + 1) + 16));
                v38 = (unsigned int)((_DWORD)v61 + 1);
                v58 = v37;
                LODWORD(v61) = (_DWORD)v61 + 1;
              }
              if ( v8 )
              {
                v54 = (const wchar_t **)hMem;
                p_cExtension = (unsigned int *)hMem;
                if ( hMem )
                {
                  while ( *v54 )
                  {
                    if ( !wcscmp_0(*v54, L"1.3.6.1.4.1.311.21.10") )
                    {
                      v30 = (struct _CERT_EXTENSIONS *)Src;
                      v55 = 1;
                      v37 = v58;
                      goto LABEL_129;
                    }
                    v54 = (const wchar_t **)(p_cExtension + 2);
                    p_cExtension += 2;
                  }
                  v30 = (struct _CERT_EXTENSIONS *)Src;
                  v37 = v58;
                }
                v55 = 0;
LABEL_129:
                v38 *= 32;
                *(BOOL *)((char *)&v30->rgExtension->fCritical + v38) = v55;
                *(LPSTR *)((char *)&v30->rgExtension->pszObjId + v38) = "1.3.6.1.4.1.311.21.10";
                *(BYTE **)((char *)&v30->rgExtension->Value.pbData + v38) = (BYTE *)v37;
                *(DWORD *)((char *)&v30->rgExtension->Value.cbData + v38) = *((_DWORD *)v8 - 1);
                memcpy_0(v37, v8, *((unsigned int *)v8 - 1));
                v30 = (struct _CERT_EXTENSIONS *)Src;
                v37 = (unsigned __int16 *)((char *)v58 + *(unsigned int *)(v38 + *((_QWORD *)Src + 1) + 16));
                v58 = v37;
                LODWORD(v38) = (_DWORD)v61 + 1;
              }
              if ( (_DWORD)v64 )
              {
                v56 = (const wchar_t **)hMem;
                p_cExtension = (unsigned int *)hMem;
                if ( hMem )
                {
                  while ( *v56 )
                  {
                    if ( !wcscmp_0(*v56, L"1.3.6.1.5.5.7.48.1.5") )
                    {
                      v30 = (struct _CERT_EXTENSIONS *)Src;
                      v37 = v58;
                      goto LABEL_138;
                    }
                    v56 = (const wchar_t **)(p_cExtension + 2);
                    p_cExtension += 2;
                  }
                  v30 = (struct _CERT_EXTENSIONS *)Src;
                  v37 = v58;
                }
                LODWORD(v63) = 0;
LABEL_138:
                v57 = (unsigned int)v38;
                v30->rgExtension[v57].fCritical = (int)v63;
                v30->rgExtension[v57].pszObjId = "1.3.6.1.5.5.7.48.1.5";
                v30->rgExtension[v57].Value.pbData = (BYTE *)v37;
                v30->rgExtension[v57].Value.cbData = 2;
                *v37 = 5;
              }
              *a4 = v30;
            }
            else
            {
              v12 = -2147024882;
            }
            goto LABEL_140;
          }
        }
        v22 = v19;
        goto LABEL_56;
      }
    }
    v19 = (_DWORD *)((char *)this + 88);
    goto LABEL_42;
  }
  CSPrintErrorLineFileData2(0, 0x15160328u, Property, 0);
LABEL_152:
  if ( hMem )
    LocalFree(hMem);
  return v12;
}

```

## disassembly

```asm
0x1800025a0  mov     [rsp-30h+arg_18], r9
0x1800025a5  mov     [rsp-30h+arg_10], r8
0x1800025aa  mov     [rsp-30h+arg_0], rcx
0x1800025af  push    rbp
0x1800025b0  push    rbx
0x1800025b1  push    rsi
0x1800025b2  push    r12
0x1800025b4  push    r13
0x1800025b6  push    r15
0x1800025b8  mov     rbp, rsp
0x1800025bb  sub     rsp, 68h
0x1800025bf  mov     rax, rcx
0x1800025c2  mov     ebx, edx
0x1800025c4  xor     ecx, ecx
0x1800025c6  mov     [rbp+var_10], rcx
0x1800025ca  mov     r12d, ecx
0x1800025cd  mov     [rbp+var_18], rcx
0x1800025d1  mov     r13d, ecx
0x1800025d4  mov     [rbp+var_20], rcx
0x1800025d8  mov     esi, ecx
0x1800025da  mov     [rbp+Src], rcx
0x1800025de  mov     r15d, ecx
0x1800025e1  mov     [rbp+var_48], rcx
0x1800025e5  mov     [rbp+var_30], rcx
0x1800025e9  mov     [rbp+hMem], rcx
0x1800025ed  test    r9, r9
0x1800025f0  jnz     short loc_1800025FC
0x1800025f2  mov     eax, 80004003h
0x1800025f7  jmp     loc_180002EDA
0x1800025fc  lea     r8, [rbp+hMem]; unsigned __int16 ***
0x180002600  mov     [rsp+68h+var_8], r14
0x180002605  lea     rdx, aPkicriticalext; "pKICriticalExtensions"
0x18000260c  mov     rcx, rax; this
0x18000260f  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180002614  mov     r14d, eax
0x180002617  test    eax, eax
0x180002619  jz      short loc_180002632
0x18000261b  xor     r9d, r9d; int
0x18000261e  mov     r8d, eax; int
0x180002621  mov     edx, 15160328h; unsigned int
0x180002626  xor     ecx, ecx; unsigned __int16 *
0x180002628  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000262d  jmp     loc_180002EC3
0x180002632  mov     [rsp+68h+arg_8], rdi
0x18000263a  mov     edi, ebx
0x18000263c  and     edi, 8
0x18000263f  test    ebx, ebx
0x180002641  jz      short loc_180002647
0x180002643  test    edi, edi
0x180002645  jz      short loc_180002699
0x180002647  mov     rcx, [rbp+arg_0]; this
0x18000264b  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x18000264f  call    ?_GetBasicConstraintsValue@CCertTypeInfo@@IEAAJPEAPEAG@Z; CCertTypeInfo::_GetBasicConstraintsValue(ushort * *)
0x180002654  mov     r14d, eax
0x180002657  test    eax, eax
0x180002659  jz      short loc_180002672
0x18000265b  xor     r9d, r9d; int
0x18000265e  mov     r8d, eax; int
0x180002661  mov     edx, 15200328h; unsigned int
0x180002666  xor     ecx, ecx; unsigned __int16 *
0x180002668  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000266d  jmp     loc_180002E90
0x180002672  test    edi, edi
0x180002674  jz      short loc_180002699
0x180002676  cmp     [rbp+var_10], rsi
0x18000267a  jnz     short loc_180002699
0x18000267c  mov     r14d, 80092004h
0x180002682  xor     r9d, r9d; int
0x180002685  mov     r8d, r14d; int
0x180002688  mov     edx, 15250328h; unsigned int
0x18000268d  xor     ecx, ecx; unsigned __int16 *
0x18000268f  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180002694  jmp     loc_180002EBB
0x180002699  mov     edi, ebx
0x18000269b  and     edi, 4
0x18000269e  test    ebx, ebx
0x1800026a0  jz      short loc_1800026A6
0x1800026a2  test    edi, edi
0x1800026a4  jz      short loc_180002703
0x1800026a6  mov     rcx, [rbp+arg_0]; this
0x1800026aa  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x1800026ae  call    ?_GetEKUValue@CCertTypeInfo@@IEAAJPEAPEAG@Z; CCertTypeInfo::_GetEKUValue(ushort * *)
0x1800026b3  mov     r14d, eax
0x1800026b6  test    eax, eax
0x1800026b8  jz      short loc_1800026D9
0x1800026ba  xor     r9d, r9d; int
0x1800026bd  mov     r8d, eax; int
0x1800026c0  mov     edx, 152C0328h; unsigned int
0x1800026c5  xor     ecx, ecx; unsigned __int16 *
0x1800026c7  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800026cc  mov     r12, [rbp+var_18]
0x1800026d0  mov     rdi, [rbp+Src]
0x1800026d4  jmp     loc_180002E76
0x1800026d9  mov     r12, [rbp+var_18]
0x1800026dd  test    edi, edi
0x1800026df  jz      short loc_180002703
0x1800026e1  test    r12, r12
0x1800026e4  jnz     short loc_180002703
0x1800026e6  mov     r14d, 80092004h
0x1800026ec  xor     r9d, r9d; int
0x1800026ef  mov     r8d, r14d; int
0x1800026f2  mov     edx, 15310328h; unsigned int
0x1800026f7  xor     ecx, ecx; unsigned __int16 *
0x1800026f9  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800026fe  jmp     loc_180002E90
0x180002703  mov     edi, ebx
0x180002705  and     edi, 2
0x180002708  test    ebx, ebx
0x18000270a  jz      short loc_180002710
0x18000270c  test    edi, edi
0x18000270e  jz      short loc_180002769
0x180002710  mov     rcx, [rbp+arg_0]; this
0x180002714  lea     rdx, [rbp+Src]; unsigned __int16 **
0x180002718  call    ?_GetKUValue@CCertTypeInfo@@IEAAJPEAPEAG@Z; CCertTypeInfo::_GetKUValue(ushort * *)
0x18000271d  mov     r14d, eax
0x180002720  test    eax, eax
0x180002722  jz      short loc_18000273F
0x180002724  xor     r9d, r9d; int
0x180002727  mov     r8d, eax; int
0x18000272a  mov     edx, 15380328h; unsigned int
0x18000272f  xor     ecx, ecx; unsigned __int16 *
0x180002731  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180002736  mov     rdi, [rbp+Src]
0x18000273a  jmp     loc_180002E76
0x18000273f  test    edi, edi
0x180002741  jz      short loc_180002769
0x180002743  mov     rdi, [rbp+Src]
0x180002747  test    rdi, rdi
0x18000274a  jnz     short loc_180002769
0x18000274c  mov     r14d, 80092004h
0x180002752  xor     r9d, r9d; int
0x180002755  mov     r8d, r14d; int
0x180002758  mov     edx, 153D0328h; unsigned int
0x18000275d  xor     ecx, ecx; unsigned __int16 *
0x18000275f  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180002764  jmp     loc_180002E76
0x180002769  mov     edi, ebx
0x18000276b  and     edi, 1
0x18000276e  test    ebx, ebx
0x180002770  jz      short loc_180002776
0x180002772  test    edi, edi
0x180002774  jz      short loc_1800027D7
0x180002776  mov     rcx, [rbp+arg_0]; this
0x18000277a  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18000277e  call    ?_GetTypeExtensionValue@CCertTypeInfo@@IEAAJHPEAPEAG@Z; CCertTypeInfo::_GetTypeExtensionValue(int,ushort * *)
0x180002783  mov     r14d, eax
0x180002786  test    eax, eax
0x180002788  jz      short loc_1800027A9
0x18000278a  xor     r9d, r9d; int
0x18000278d  mov     r8d, eax; int
0x180002790  mov     edx, 15450328h; unsigned int
0x180002795  xor     ecx, ecx; unsigned __int16 *
0x180002797  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000279c  mov     r13, [rbp+var_20]
0x1800027a0  mov     rdi, [rbp+Src]
0x1800027a4  jmp     loc_180002E69
0x1800027a9  mov     r13, [rbp+var_20]
0x1800027ad  test    edi, edi
0x1800027af  jz      short loc_1800027D7
0x1800027b1  test    r13, r13
0x1800027b4  jnz     short loc_1800027D7
0x1800027b6  mov     r14d, 80092004h
0x1800027bc  xor     r9d, r9d; int
0x1800027bf  mov     r8d, r14d; int
0x1800027c2  mov     edx, 154A0328h; unsigned int
0x1800027c7  xor     ecx, ecx; unsigned __int16 *
0x1800027c9  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800027ce  mov     rdi, [rbp+Src]
0x1800027d2  jmp     loc_180002E76
0x1800027d7  mov     rax, [rbp+arg_0]
0x1800027db  cmp     [rax+58h], esi
0x1800027de  lea     rdi, [rax+58h]
0x1800027e2  jz      short loc_180002839
0x1800027e4  test    ebx, ebx
0x1800027e6  jz      short loc_1800027F3
0x1800027e8  test    bl, 20h
0x1800027eb  jz      short loc_180002839
0x1800027ed  lea     rsi, [rax+58h]
0x1800027f1  jmp     short loc_1800027F6
0x1800027f3  mov     rsi, rdi
0x1800027f6  mov     r8, [rbp+arg_10]; void *
0x1800027fa  lea     r9, [rbp+var_48]; unsigned __int16 **
0x1800027fe  lea     rdx, aMspkiCertifica; "msPKI-Certificate-Policy"
0x180002805  mov     rcx, rax; this
0x180002808  call    ?_GetPoliciesValue@CCertTypeInfo@@IEAAJPEBGPEAXPEAPEAG@Z; CCertTypeInfo::_GetPoliciesValue(ushort const *,void *,ushort * *)
0x18000280d  mov     r14d, eax
0x180002810  test    eax, eax
0x180002812  jz      short loc_180002833
0x180002814  xor     r9d, r9d; int
0x180002817  mov     r8d, eax; int
0x18000281a  mov     edx, 15540328h; unsigned int
0x18000281f  xor     ecx, ecx; unsigned __int16 *
0x180002821  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180002826  mov     rsi, [rbp+var_48]
0x18000282a  mov     rdi, [rbp+Src]
0x18000282e  jmp     loc_180002E69
0x180002833  mov     rax, [rbp+arg_0]
0x180002837  jmp     short loc_18000283C
0x180002839  mov     rsi, rdi
0x18000283c  test    bl, 20h
0x18000283f  jz      short loc_18000286C
0x180002841  cmp     [rbp+var_48], r15
0x180002845  jnz     short loc_18000286F
0x180002847  mov     edx, 155B0328h; unsigned int
0x18000284c  mov     r14d, 80092004h
0x180002852  xor     r9d, r9d; int
0x180002855  mov     r8d, r14d; int
0x180002858  xor     ecx, ecx; unsigned __int16 *
0x18000285a  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000285f  mov     rsi, [rbp+var_48]
0x180002863  mov     rdi, [rbp+Src]
0x180002867  jmp     loc_180002E69
0x18000286c  mov     rsi, rdi
0x18000286f  cmp     [rsi], r15d
0x180002872  jz      short loc_1800028D1
0x180002874  test    ebx, ebx
0x180002876  jz      short loc_180002883
0x180002878  test    bl, 10h
0x18000287b  jz      short loc_1800028D1
0x18000287d  lea     rdi, [rax+58h]
0x180002881  jmp     short loc_180002886
0x180002883  mov     rdi, rsi
0x180002886  mov     r8, [rbp+arg_10]; void *
0x18000288a  lea     r9, [rbp+var_30]; unsigned __int16 **
0x18000288e  lea     rdx, aMspkiCertifica_0; "msPKI-Certificate-Application-Policy"
0x180002895  mov     rcx, rax; this
0x180002898  call    ?_GetPoliciesValue@CCertTypeInfo@@IEAAJPEBGPEAXPEAPEAG@Z; CCertTypeInfo::_GetPoliciesValue(ushort const *,void *,ushort * *)
0x18000289d  mov     r14d, eax
0x1800028a0  test    eax, eax
0x1800028a2  jz      short loc_1800028C7
0x1800028a4  xor     r9d, r9d; int
0x1800028a7  mov     r8d, eax; int
0x1800028aa  mov     edx, 15630328h; unsigned int
0x1800028af  xor     ecx, ecx; unsigned __int16 *
0x1800028b1  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800028b6  mov     r15, [rbp+var_30]
0x1800028ba  mov     rsi, [rbp+var_48]
0x1800028be  mov     rdi, [rbp+Src]
0x1800028c2  jmp     loc_180002E69
0x1800028c7  mov     r15, [rbp+var_30]
0x1800028cb  mov     rax, [rbp+arg_0]
0x1800028cf  jmp     short loc_1800028D4
0x1800028d1  mov     rdi, rsi
0x1800028d4  test    bl, 10h
0x1800028d7  jz      short loc_1800028E8
0x1800028d9  test    r15, r15
0x1800028dc  jnz     short loc_1800028EB
0x1800028de  mov     edx, 156A0328h
0x1800028e3  jmp     loc_18000284C
0x1800028e8  mov     rdi, rsi
0x1800028eb  xor     edx, edx
0x1800028ed  mov     r8d, 1
0x1800028f3  mov     dword ptr [rbp+var_18], edx
0x1800028f6  mov     dword ptr [rbp+var_20], r8d
0x1800028fa  cmp     [rdi], edx
0x1800028fc  jz      short loc_180002915
0x1800028fe  test    ebx, ebx
0x180002900  jz      short loc_180002907
0x180002902  test    bl, 40h
0x180002905  jz      short loc_180002915
0x180002907  test    dword ptr [rax+44h], 1000h
0x18000290e  cmovnz  edx, r8d
0x180002912  mov     dword ptr [rbp+var_18], edx
0x180002915  test    r13, r13
0x180002918  jz      short loc_180002923
0x18000291a  mov     ecx, [r13-4]
0x18000291e  add     ecx, 30h ; '0'
0x180002921  jmp     short loc_18000292B
0x180002923  mov     ecx, 10h
0x180002928  xor     r8d, r8d
0x18000292b  test    r12, r12
0x18000292e  jz      short loc_18000293B
0x180002930  add     ecx, 20h ; ' '
0x180002933  add     ecx, [r12-4]
0x180002938  inc     r8d
0x18000293b  mov     rdi, [rbp+Src]
0x18000293f  test    rdi, rdi
0x180002942  jz      short loc_18000294F
0x180002944  mov     eax, [rdi-4]
0x180002947  add     eax, 20h ; ' '
0x18000294a  add     ecx, eax
0x18000294c  inc     r8d
0x18000294f  mov     rax, [rbp+var_10]
0x180002953  test    rax, rax
0x180002956  jz      short loc_180002963
0x180002958  mov     eax, [rax-4]
0x18000295b  add     eax, 20h ; ' '
0x18000295e  add     ecx, eax
0x180002960  inc     r8d
0x180002963  mov     rsi, [rbp+var_48]
0x180002967  test    rsi, rsi
0x18000296a  jz      short loc_180002977
0x18000296c  mov     eax, [rsi-4]
0x18000296f  add     eax, 20h ; ' '
0x180002972  add     ecx, eax
0x180002974  inc     r8d
0x180002977  test    r15, r15
0x18000297a  jz      short loc_180002986
0x18000297c  add     ecx, 20h ; ' '
0x18000297f  add     ecx, [r15-4]
  ... truncated ...
```
