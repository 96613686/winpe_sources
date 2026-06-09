# CFveApiBase::GetUnlockAccessPolicy(_FVE_DATUM_KEY const *,_FVE_AUTH_INFORMATION const *,int *)

- ea: `0x180058334`
- end: `0x180058a3a`
- name: `?GetUnlockAccessPolicy@CFveApiBase@@QEAAJPEBU_FVE_DATUM_KEY@@PEBU_FVE_AUTH_INFORMATION@@PEAH@Z`
- size: `1798`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this, const struct _FVE_DATUM_KEY *, const struct _FVE_AUTH_INFORMATION *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180079538`

## callees

- `0x18000ba30`
- `0x18003d000`
- `0x180046e6c`
- `0x180058334`
- `0x18008488c`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005845f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058565`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800585e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058686`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005876e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800587f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005845f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058565`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800585e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058686`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005876e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800587f7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800589ad`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800589ad`

## pseudocode

```c
__int64 __fastcall CFveApiBase::GetUnlockAccessPolicy(
        CFveApiBase *this,
        const struct _FVE_DATUM_KEY *a2,
        const struct _FVE_AUTH_INFORMATION *a3,
        int *a4)
{
  char *v6; // r13
  PCNZWCH *v7; // r12
  signed int IdentificationField; // ebx
  LSTATUS ValueW; // eax
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  __int64 v14; // rsi
  LSTATUS v15; // eax
  __int64 v16; // rcx
  unsigned __int64 v17; // r14
  __int64 v18; // rdx
  __int64 v19; // rax
  LSTATUS v20; // eax
  LSTATUS v21; // eax
  PCNZWCH *v22; // rax
  unsigned int v23; // r9d
  unsigned int i; // ecx
  __int64 v25; // r9
  __int64 j; // rdx
  __int64 v27; // r8
  unsigned int k; // r10d
  unsigned int v29; // r13d
  unsigned __int64 v30; // r9
  int v31; // r10d
  const WCHAR *lpString1; // [rsp+48h] [rbp-B0h]
  unsigned int v34; // [rsp+50h] [rbp-A8h]
  int cchCount1; // [rsp+58h] [rbp-A0h] BYREF
  char *v36; // [rsp+60h] [rbp-98h]
  int v37; // [rsp+68h] [rbp-90h]
  int cchCount2[2]; // [rsp+70h] [rbp-88h] BYREF
  unsigned __int64 v39; // [rsp+78h] [rbp-80h] BYREF
  unsigned int v40; // [rsp+80h] [rbp-78h]
  int v41; // [rsp+84h] [rbp-74h]
  PCNZWCH *v42; // [rsp+88h] [rbp-70h]
  DWORD v43[2]; // [rsp+90h] [rbp-68h] BYREF
  DWORD v44[2]; // [rsp+98h] [rbp-60h] BYREF
  char v45[4]; // [rsp+A0h] [rbp-58h] BYREF
  int pvData; // [rsp+A4h] [rbp-54h] BYREF
  int v47; // [rsp+A8h] [rbp-50h] BYREF
  DWORD pcbData; // [rsp+ACh] [rbp-4Ch] BYREF
  DWORD v49; // [rsp+B0h] [rbp-48h] BYREF

  *(_QWORD *)cchCount2 = a2;
  pvData = 2;
  pcbData = 4;
  lpString1 = 0;
  v39 = 0;
  v6 = 0;
  v36 = 0;
  *(_QWORD *)v43 = 0;
  *(_QWORD *)v44 = 0;
  v7 = 0;
  v42 = 0;
  v34 = 0;
  cchCount1 = 0;
  v47 = 2;
  v49 = 4;
  v45[0] = 0;
  if ( !a2 || !a4 )
  {
    IdentificationField = -2147024809;
    goto LABEL_79;
  }
  if ( (*((_DWORD *)a3 + 2) & 0x800000) != 0
    && (*(int (__fastcall **)(CFveApiBase *, char *))(*(_QWORD *)this + 136LL))(this, v45) >= 0
    && v45[0] )
  {
    goto LABEL_6;
  }
  if ( (*((_BYTE *)this + 108) & 0x10) == 0 )
    goto LABEL_9;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\FVE",
             L"RDVDenyCrossOrg",
             0x18u,
             0,
             &pvData,
             &pcbData);
  IdentificationField = ValueW;
  if ( ValueW > 0 )
    IdentificationField = (unsigned __int16)ValueW | 0x80070000;
  if ( IdentificationField == -2147024894 )
    goto LABEL_9;
  if ( IdentificationField < 0 )
    goto LABEL_79;
  if ( pvData != 1 )
    goto LABEL_15;
  if ( CFveApiBase::GetIdentificationField(this, 0, 0, *(const struct _FVE_DATUM_KEY **)cchCount2, &v39) != -2147024774 )
  {
LABEL_6:
    *a4 = 1;
LABEL_7:
    IdentificationField = 0;
    goto LABEL_79;
  }
  v10 = v39;
  v11 = (unsigned __int16 *)CFveApiBase::ZeroAlloc(2 * v39);
  lpString1 = v11;
  if ( !v11 )
  {
    IdentificationField = -2147024882;
    goto LABEL_80;
  }
  IdentificationField = CFveApiBase::GetIdentificationField(
                          this,
                          v11,
                          v10,
                          *(const struct _FVE_DATUM_KEY **)cchCount2,
                          &v39);
  if ( IdentificationField >= 0 )
  {
    v12 = RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\FVE",
            L"IdentificationField",
            0x18u,
            0,
            &v47,
            &v49);
    IdentificationField = v12;
    if ( v12 > 0 )
      IdentificationField = (unsigned __int16)v12 | 0x80070000;
    if ( IdentificationField != -2147024894 )
    {
      if ( IdentificationField < 0 )
        goto LABEL_79;
      if ( v47 == 1 )
      {
        *(_QWORD *)v43 = 0;
        v13 = RegGetValueW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Policies\\Microsoft\\FVE",
                L"IdentificationFieldString",
                2u,
                0,
                0,
                v43);
        IdentificationField = v13;
        if ( v13 > 0 )
          IdentificationField = (unsigned __int16)v13 | 0x80070000;
        if ( IdentificationField == -2147024894 || *(_QWORD *)v43 <= 2u )
        {
          *(_QWORD *)v43 = 0;
          v14 = 0;
        }
        else
        {
          if ( IdentificationField < 0 )
            goto LABEL_79;
          v14 = *(_QWORD *)v43 >> 1;
          v34 = 1;
          v37 = 1;
        }
        *(_QWORD *)v44 = 0;
        v15 = RegGetValueW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Policies\\Microsoft\\FVE",
                L"SecondaryIdentificationField",
                2u,
                0,
                0,
                v44);
        IdentificationField = v15;
        if ( v15 > 0 )
          IdentificationField = (unsigned __int16)v15 | 0x80070000;
        if ( IdentificationField == -2147024894 || (v16 = *(_QWORD *)v44, *(_QWORD *)v44 <= 2u) )
        {
          v16 = 0;
          *(_QWORD *)v44 = 0;
          v17 = 0;
          IdentificationField = 0;
          v18 = *(_QWORD *)v43;
        }
        else
        {
          if ( IdentificationField < 0 )
            goto LABEL_79;
          v17 = *(_QWORD *)v44 >> 1;
          v18 = *(_QWORD *)v43;
          v14 = *(_QWORD *)v43 >> 1;
          v37 = ++v34;
        }
        if ( v17 + v14 )
        {
          v6 = (char *)CFveApiBase::ZeroAlloc(v18 + v16);
          v36 = v6;
          if ( !v6 )
            goto LABEL_41;
          v19 = *(_QWORD *)v43;
          if ( *(_QWORD *)v43 )
          {
            v20 = RegGetValueW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Policies\\Microsoft\\FVE",
                    L"IdentificationFieldString",
                    2u,
                    0,
                    v6,
                    v43);
            IdentificationField = v20;
            if ( v20 > 0 )
              IdentificationField = (unsigned __int16)v20 | 0x80070000;
            if ( IdentificationField >= 0 )
            {
              v19 = *(_QWORD *)v43;
              v14 = *(_QWORD *)v43 >> 1;
            }
            else
            {
              v19 = 0;
              *(_QWORD *)v43 = 0;
              v14 = 0;
              IdentificationField = 0;
            }
          }
          if ( *(_QWORD *)v44 )
          {
            v21 = RegGetValueW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Policies\\Microsoft\\FVE",
                    L"SecondaryIdentificationField",
                    2u,
                    0,
                    &v6[v19],
                    v44);
            IdentificationField = v21;
            if ( v21 > 0 )
              IdentificationField = (unsigned __int16)v21 | 0x80070000;
            if ( IdentificationField >= 0 )
            {
              v17 = *(_QWORD *)v44 >> 1;
              for ( i = 0; ; ++i )
              {
                v40 = i;
                if ( i >= v17 )
                  break;
                if ( *(_WORD *)&v6[2 * v14 + 2 * i] == 44 )
                  v37 = ++v34;
              }
            }
            else
            {
              *(_QWORD *)v44 = 0;
              v17 = 0;
              IdentificationField = 0;
            }
          }
          v22 = (PCNZWCH *)CFveApiBase::ZeroAlloc(8LL * v34);
          v7 = v22;
          v42 = v22;
          if ( v22 )
          {
            if ( v14 )
            {
              *v22 = (PCNZWCH)v6;
              v23 = 1;
            }
            else
            {
              v23 = cchCount1;
            }
            if ( v17 )
            {
              v22[v23] = (PCNZWCH)&v6[2 * v14];
              v25 = v23 + 1;
              for ( j = 0; ; j = (unsigned int)(j + 1) )
              {
                v41 = j;
                if ( (unsigned int)j >= v17 )
                  break;
                v27 = j + v14;
                if ( *(_WORD *)&v6[2 * j + 2 * v14] == 44 )
                {
                  *(_WORD *)&v6[2 * v27] = 0;
                  if ( (unsigned int)j < v17 - 1 )
                  {
                    v22[v25] = (PCNZWCH)&v6[2 * v27 + 2];
                    v25 = (unsigned int)(v25 + 1);
                  }
                }
              }
            }
            for ( k = 0; k < v34; k = v29 )
            {
              v29 = k + 1;
              cchCount1 = 0;
              cchCount2[0] = 0;
              IdentificationField = UIntPtrToInt(v39, &cchCount1);
              if ( IdentificationField )
                goto LABEL_78;
              IdentificationField = UIntPtrToInt(v30, cchCount2);
              if ( IdentificationField )
                goto LABEL_78;
              if ( CompareStringW(0x7Fu, 1u, lpString1, cchCount1, v7[v31], cchCount2[0]) == 2 )
              {
                *a4 = 0;
                goto LABEL_78;
              }
            }
            *a4 = 1;
LABEL_78:
            v6 = v36;
          }
          else
          {
LABEL_41:
            IdentificationField = -2147024882;
          }
          goto LABEL_79;
        }
        goto LABEL_6;
      }
LABEL_15:
      *a4 = 0;
      goto LABEL_79;
    }
LABEL_9:
    *a4 = 0;
    goto LABEL_7;
  }
LABEL_79:
  v11 = (unsigned __int16 *)lpString1;
LABEL_80:
  if ( v11 )
    CFveApiBase::FastFree(v11);
  if ( v7 )
    CFveApiBase::FastFree(v7);
  if ( v6 )
    CFveApiBase::FastFree(v6);
  return (unsigned int)IdentificationField;
}

```

## disassembly

```asm
0x180058334  mov     r11, rsp
0x180058337  push    rbx
0x180058338  push    rsi
0x180058339  push    rdi
0x18005833a  push    r12
0x18005833c  push    r13
0x18005833e  push    r14
0x180058340  push    r15
0x180058342  sub     rsp, 0C0h
0x180058349  mov     rax, cs:__security_cookie
0x180058350  xor     rax, rsp
0x180058353  mov     [rsp+0F8h+var_40], rax
0x18005835b  mov     r15, r9
0x18005835e  mov     rax, rdx
0x180058361  mov     qword ptr [rsp+0F8h+cchCount2], rdx
0x180058366  mov     rsi, rcx
0x180058369  mov     dword ptr [r11-54h], 2
0x180058371  mov     ecx, 4
0x180058376  mov     [r11-4Ch], ecx
0x18005837a  mov     [rsp+0F8h+lpString1], 0
0x180058383  mov     qword ptr [r11-80h], 0
0x18005838b  xor     r13d, r13d
0x18005838e  mov     [rsp+0F8h+var_98], r13
0x180058393  mov     [r11-68h], r13
0x180058397  mov     [r11-60h], r13
0x18005839b  xor     r12d, r12d
0x18005839e  mov     [r11-70h], r12
0x1800583a2  mov     [rsp+0F8h+var_A8], r12d
0x1800583a7  mov     [rsp+0F8h+cchCount1], r12d
0x1800583ac  mov     dword ptr [r11-50h], 2
0x1800583b4  mov     [r11-48h], ecx
0x1800583b8  mov     [r11-58h], r12b
0x1800583bc  test    rax, rax
0x1800583bf  jz      loc_1800589D9
0x1800583c5  test    r9, r9
0x1800583c8  jz      loc_1800589D9
0x1800583ce  test    dword ptr [r8+8], 800000h
0x1800583d6  jz      short loc_180058412
0x1800583d8  mov     rax, [rsi]
0x1800583db  lea     rdx, [r11-58h]
0x1800583df  mov     rcx, rsi
0x1800583e2  mov     rax, [rax+88h]
0x1800583e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583ee  mov     [rsp+0F8h+var_B8], eax
0x1800583f2  test    eax, eax
0x1800583f4  js      short loc_180058412
0x1800583f6  cmp     [rsp+0F8h+var_58], r12b
0x1800583fe  jz      short loc_180058412
0x180058400  lea     edi, [r13+1]
0x180058404  mov     [r15], edi
0x180058407  xor     ebx, ebx
0x180058409  mov     [rsp+0F8h+var_B8], ebx
0x18005840d  jmp     loc_1800589E8
0x180058412  test    byte ptr [rsi+6Ch], 10h
0x180058416  jnz     short loc_180058421
0x180058418  mov     dword ptr [r15], 0
0x18005841f  jmp     short loc_180058407
0x180058421  lea     rax, [rsp+0F8h+var_4C]
0x180058429  mov     [rsp+0F8h+pcbData], rax; pcbData
0x18005842e  lea     rax, [rsp+0F8h+var_54]
0x180058436  mov     [rsp+0F8h+pvData], rax; pvData
0x18005843b  mov     [rsp+0F8h+pdwType], 0; pdwType
0x180058444  mov     r9d, 18h; dwFlags
0x18005844a  lea     r8, aRdvdenycrossor; "RDVDenyCrossOrg"
0x180058451  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\FVE"
0x180058458  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18005845f  call    cs:__imp_RegGetValueW
0x180058466  nop     dword ptr [rax+rax+00h]
0x18005846b  mov     ebx, eax
0x18005846d  mov     r14d, 80070000h
0x180058473  test    eax, eax
0x180058475  jle     short loc_18005847D
0x180058477  movzx   ebx, ax
0x18005847a  or      ebx, r14d
0x18005847d  mov     [rsp+0F8h+var_B8], ebx
0x180058481  cmp     ebx, 80070002h
0x180058487  jz      short loc_180058418
0x180058489  test    ebx, ebx
0x18005848b  js      loc_1800589E8
0x180058491  mov     edi, 1
0x180058496  cmp     [rsp+0F8h+var_54], edi
0x18005849d  jz      short loc_1800584AB
0x18005849f  mov     dword ptr [r15], 0
0x1800584a6  jmp     loc_1800589E8
0x1800584ab  lea     rax, [rsp+0F8h+var_80]
0x1800584b0  mov     [rsp+0F8h+pdwType], rax; unsigned __int64 *
0x1800584b5  mov     r9, qword ptr [rsp+0F8h+cchCount2]; struct _FVE_DATUM_KEY *
0x1800584ba  xor     r8d, r8d; unsigned __int64
0x1800584bd  xor     edx, edx; unsigned __int16 *
0x1800584bf  mov     rcx, rsi; this
0x1800584c2  call    ?GetIdentificationField@CFveApiBase@@QEAAJPEAG_KPEBU_FVE_DATUM_KEY@@PEA_K@Z; CFveApiBase::GetIdentificationField(ushort *,unsigned __int64,_FVE_DATUM_KEY const *,unsigned __int64 *)
0x1800584c7  mov     [rsp+0F8h+var_B8], eax
0x1800584cb  cmp     eax, 8007007Ah
0x1800584d0  jnz     loc_180058404
0x1800584d6  mov     rbx, [rsp+0F8h+var_80]
0x1800584db  lea     rcx, [rbx+rbx]; unsigned __int64
0x1800584df  call    ?ZeroAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::ZeroAlloc(unsigned __int64)
0x1800584e4  mov     [rsp+0F8h+lpString1], rax
0x1800584e9  test    rax, rax
0x1800584ec  jnz     short loc_1800584FC
0x1800584ee  mov     ebx, 8007000Eh
0x1800584f3  mov     [rsp+0F8h+var_B8], ebx
0x1800584f7  jmp     loc_1800589ED
0x1800584fc  lea     rcx, [rsp+0F8h+var_80]
0x180058501  mov     [rsp+0F8h+pdwType], rcx; unsigned __int64 *
0x180058506  mov     r9, qword ptr [rsp+0F8h+cchCount2]; struct _FVE_DATUM_KEY *
0x18005850b  mov     r8, rbx; unsigned __int64
0x18005850e  mov     rdx, rax; unsigned __int16 *
0x180058511  mov     rcx, rsi; this
0x180058514  call    ?GetIdentificationField@CFveApiBase@@QEAAJPEAG_KPEBU_FVE_DATUM_KEY@@PEA_K@Z; CFveApiBase::GetIdentificationField(ushort *,unsigned __int64,_FVE_DATUM_KEY const *,unsigned __int64 *)
0x180058519  mov     ebx, eax
0x18005851b  mov     [rsp+0F8h+var_B8], eax
0x18005851f  test    eax, eax
0x180058521  js      loc_1800589E8
0x180058527  lea     rax, [rsp+0F8h+var_48]
0x18005852f  mov     [rsp+0F8h+pcbData], rax; pcbData
0x180058534  lea     rax, [rsp+0F8h+var_50]
0x18005853c  mov     [rsp+0F8h+pvData], rax; pvData
0x180058541  mov     [rsp+0F8h+pdwType], 0; pdwType
0x18005854a  mov     r9d, 18h; dwFlags
0x180058550  lea     r8, aIdentification_0; "IdentificationField"
0x180058557  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\FVE"
0x18005855e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180058565  call    cs:__imp_RegGetValueW
0x18005856c  nop     dword ptr [rax+rax+00h]
0x180058571  mov     ebx, eax
0x180058573  test    eax, eax
0x180058575  jle     short loc_18005857D
0x180058577  movzx   ebx, ax
0x18005857a  or      ebx, r14d
0x18005857d  mov     [rsp+0F8h+var_B8], ebx
0x180058581  mov     esi, 80070002h
0x180058586  cmp     ebx, esi
0x180058588  jz      loc_180058418
0x18005858e  test    ebx, ebx
0x180058590  js      loc_1800589E8
0x180058596  cmp     [rsp+0F8h+var_50], edi
0x18005859d  jnz     loc_18005849F
0x1800585a3  mov     qword ptr [rsp+0F8h+var_68], 0
0x1800585af  lea     rax, [rsp+0F8h+var_68]
0x1800585b7  mov     [rsp+0F8h+pcbData], rax; pcbData
0x1800585bc  mov     [rsp+0F8h+pvData], 0; pvData
0x1800585c5  mov     [rsp+0F8h+pdwType], 0; pdwType
0x1800585ce  mov     r9d, 2; dwFlags
0x1800585d4  lea     r8, aIdentification; "IdentificationFieldString"
0x1800585db  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\FVE"
0x1800585e2  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800585e9  call    cs:__imp_RegGetValueW
0x1800585f0  nop     dword ptr [rax+rax+00h]
0x1800585f5  mov     ebx, eax
0x1800585f7  test    eax, eax
0x1800585f9  jle     short loc_180058601
0x1800585fb  movzx   ebx, ax
0x1800585fe  or      ebx, r14d
0x180058601  mov     [rsp+0F8h+var_B8], ebx
0x180058605  cmp     ebx, esi
0x180058607  jz      short loc_18005862E
0x180058609  mov     rsi, qword ptr [rsp+0F8h+var_68]
0x180058611  cmp     rsi, 2
0x180058615  jbe     short loc_18005862E
0x180058617  test    ebx, ebx
0x180058619  js      loc_1800589E8
0x18005861f  shr     rsi, 1
0x180058622  mov     eax, edi
0x180058624  mov     [rsp+0F8h+var_A8], eax
0x180058628  mov     [rsp+0F8h+var_90], eax
0x18005862c  jmp     short loc_180058640
0x18005862e  mov     qword ptr [rsp+0F8h+var_68], 0
0x18005863a  xor     esi, esi
0x18005863c  mov     [rsp+0F8h+var_B8], esi
0x180058640  mov     qword ptr [rsp+0F8h+var_60], 0
0x18005864c  lea     rax, [rsp+0F8h+var_60]
0x180058654  mov     [rsp+0F8h+pcbData], rax; pcbData
0x180058659  mov     [rsp+0F8h+pvData], 0; pvData
0x180058662  mov     [rsp+0F8h+pdwType], 0; pdwType
0x18005866b  mov     r9d, 2; dwFlags
0x180058671  lea     r8, aSecondaryident; "SecondaryIdentificationField"
0x180058678  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\FVE"
0x18005867f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180058686  call    cs:__imp_RegGetValueW
0x18005868d  nop     dword ptr [rax+rax+00h]
0x180058692  mov     ebx, eax
0x180058694  test    eax, eax
0x180058696  jle     short loc_18005869E
0x180058698  movzx   ebx, ax
0x18005869b  or      ebx, r14d
0x18005869e  mov     [rsp+0F8h+var_B8], ebx
0x1800586a2  cmp     ebx, 80070002h
0x1800586a8  jz      short loc_1800586E4
0x1800586aa  mov     rcx, qword ptr [rsp+0F8h+var_60]
0x1800586b2  cmp     rcx, 2
0x1800586b6  jbe     short loc_1800586E4
0x1800586b8  test    ebx, ebx
0x1800586ba  js      loc_1800589E8
0x1800586c0  mov     r14, rcx
0x1800586c3  shr     r14, 1
0x1800586c6  mov     rdx, qword ptr [rsp+0F8h+var_68]
0x1800586ce  mov     rsi, rdx
0x1800586d1  shr     rsi, 1
0x1800586d4  mov     eax, [rsp+0F8h+var_A8]
0x1800586d8  add     eax, edi
0x1800586da  mov     [rsp+0F8h+var_A8], eax
0x1800586de  mov     [rsp+0F8h+var_90], eax
0x1800586e2  jmp     short loc_1800586FF
0x1800586e4  xor     ecx, ecx
0x1800586e6  mov     qword ptr [rsp+0F8h+var_60], rcx
0x1800586ee  xor     r14d, r14d
0x1800586f1  xor     ebx, ebx
0x1800586f3  mov     [rsp+0F8h+var_B8], ebx
0x1800586f7  mov     rdx, qword ptr [rsp+0F8h+var_68]
0x1800586ff  lea     rax, [r14+rsi]
0x180058703  test    rax, rax
0x180058706  jz      loc_180058404
0x18005870c  add     rcx, rdx; unsigned __int64
0x18005870f  call    ?ZeroAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::ZeroAlloc(unsigned __int64)
0x180058714  mov     r13, rax
0x180058717  mov     [rsp+0F8h+var_98], rax
0x18005871c  test    rax, rax
0x18005871f  jnz     short loc_18005872B
0x180058721  mov     ebx, 8007000Eh
0x180058726  jmp     loc_180058409
0x18005872b  mov     rax, qword ptr [rsp+0F8h+var_68]
0x180058733  test    rax, rax
0x180058736  jz      short loc_1800587B3
0x180058738  lea     rax, [rsp+0F8h+var_68]
0x180058740  mov     [rsp+0F8h+pcbData], rax; pcbData
0x180058745  mov     [rsp+0F8h+pvData], r13; pvData
0x18005874a  mov     [rsp+0F8h+pdwType], 0; pdwType
0x180058753  mov     r9d, 2; dwFlags
0x180058759  lea     r8, aIdentification; "IdentificationFieldString"
0x180058760  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\FVE"
0x180058767  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18005876e  call    cs:__imp_RegGetValueW
0x180058775  nop     dword ptr [rax+rax+00h]
0x18005877a  mov     ebx, eax
0x18005877c  test    eax, eax
0x18005877e  jle     short loc_180058789
0x180058780  movzx   ebx, ax
0x180058783  or      ebx, 80070000h
0x180058789  mov     [rsp+0F8h+var_B8], ebx
0x18005878d  test    ebx, ebx
0x18005878f  jns     short loc_1800587A5
0x180058791  xor     eax, eax
0x180058793  mov     qword ptr [rsp+0F8h+var_68], rax
0x18005879b  xor     esi, esi
0x18005879d  xor     ebx, ebx
0x18005879f  mov     [rsp+0F8h+var_B8], ebx
0x1800587a3  jmp     short loc_1800587B3
0x1800587a5  mov     rax, qword ptr [rsp+0F8h+var_68]
0x1800587ad  mov     rsi, rax
0x1800587b0  shr     rsi, 1
0x1800587b3  cmp     qword ptr [rsp+0F8h+var_60], 0
0x1800587bc  jz      short loc_18005882F
0x1800587be  add     rax, r13
0x1800587c1  lea     r9, [rsp+0F8h+var_60]
0x1800587c9  mov     [rsp+0F8h+pcbData], r9; pcbData
0x1800587ce  mov     [rsp+0F8h+pvData], rax; pvData
0x1800587d3  mov     [rsp+0F8h+pdwType], 0; pdwType
0x1800587dc  mov     r9d, 2; dwFlags
0x1800587e2  lea     r8, aSecondaryident; "SecondaryIdentificationField"
0x1800587e9  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\FVE"
0x1800587f0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800587f7  call    cs:__imp_RegGetValueW
0x1800587fe  nop     dword ptr [rax+rax+00h]
0x180058803  mov     ebx, eax
0x180058805  test    eax, eax
0x180058807  jle     short loc_180058812
0x180058809  movzx   ebx, ax
0x18005880c  or      ebx, 80070000h
0x180058812  mov     [rsp+0F8h+var_B8], ebx
0x180058816  test    ebx, ebx
0x180058818  jns     short loc_180058861
0x18005881a  mov     qword ptr [rsp+0F8h+var_60], 0
0x180058826  xor     r14d, r14d
0x180058829  xor     ebx, ebx
0x18005882b  mov     [rsp+0F8h+var_B8], ebx
0x18005882f  mov     ecx, [rsp+0F8h+var_A8]
0x180058833  shl     rcx, 3; unsigned __int64
0x180058837  call    ?ZeroAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::ZeroAlloc(unsigned __int64)
0x18005883c  mov     r12, rax
0x18005883f  mov     [rsp+0F8h+var_70], rax
0x180058847  test    rax, rax
0x18005884a  jz      loc_180058721
0x180058850  test    rsi, rsi
0x180058853  jz      short loc_18005889A
0x180058855  mov     [rax], r13
0x180058858  mov     r9d, edi
0x18005885b  mov     [rsp+0F8h+var_A4], edi
0x18005885f  jmp     short loc_18005889F
0x180058861  mov     r14, qword ptr [rsp+0F8h+var_60]
0x180058869  shr     r14, 1
0x18005886c  xor     ecx, ecx
0x18005886e  mov     [rsp+0F8h+var_78], ecx
0x180058875  mov     eax, ecx
0x180058877  cmp     rax, r14
0x18005887a  jnb     short loc_18005882F
0x18005887c  add     rax, rsi
0x18005887f  cmp     word ptr [r13+rax*2+0], 2Ch ; ','
0x180058886  jnz     short loc_180058896
0x180058888  mov     eax, [rsp+0F8h+var_A8]
  ... truncated ...
```
