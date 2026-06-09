# CONFIG_ELEMENT::SetMetadata(ushort *,tagVARIANT)

- ea: `0x180034410`
- end: `0x18003490a`
- name: `?SetMetadata@CONFIG_ELEMENT@@UEAAJPEAGUtagVARIANT@@@Z`
- size: `1274`
- prototype: `__int64 __fastcall(CONFIG_ELEMENT *__hidden this, wchar_t *String1, VARIANTARG *pvarSrc)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001a18c`
- `0x18001c250`
- `0x18001e678`
- `0x18001fda0`
- `0x18002dbd0`
- `0x18002fbf4`
- `0x180033de0`
- `0x18003424c`
- `0x180034410`
- `0x180034910`
- `0x180034f88`
- `0x180035ff0`
- `0x180059bf6`
- `0x18005b010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800344e4`
- `OLEAUT32!__imp_VariantInit` at `0x1800344e4`
- `OLEAUT32!__imp_VariantClear` at `0x180034570`
- `OLEAUT32!__imp_VariantClear` at `0x180034570`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800344fa`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800344fa`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180034581`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180034581`

## string_xrefs

- `0x1800346f6`: `configSource`
- `0x18003454c`: `CONFIG_ELEMENT::SetMetadata`

## pseudocode

```c
__int64 __fastcall CONFIG_ELEMENT::SetMetadata(CONFIG_ELEMENT *this, wchar_t *String1, VARIANTARG *pvarSrc)
{
  IErrorInfo *v6; // r14
  int FieldMemory; // ebx
  int v8; // r12d
  const WCHAR *v9; // r13
  __int64 v10; // rdx
  __int64 v11; // rax
  const WCHAR *v12; // rcx
  const WCHAR *v13; // r9
  __int64 v14; // rax
  CONFIG_EXCEPTION *v16; // rax
  CONFIG_EXCEPTION *v17; // rax
  const unsigned __int16 *v18; // r8
  int v19; // eax
  int v20; // r8d
  const unsigned __int16 *v21; // rdx
  int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  _DWORD *v25; // rcx
  METADATA_LIST *v26; // rcx
  IRecordInfo *pRecInfo; // xmm1_8
  const unsigned __int16 *bstrVal; // r8
  int v29; // eax
  char *v30[2]; // [rsp+50h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-29h] BYREF
  struct tagVARIANT v32; // [rsp+80h] [rbp-9h] BYREF
  struct CONFIG_EXCEPTION *v33; // [rsp+F8h] [rbp+6Fh] BYREF

  v33 = 0;
  v6 = 0;
  *(_OWORD *)v30 = 0;
  if ( !String1 )
    return (unsigned int)-2147024809;
  v8 = *((_DWORD *)this + 34);
  if ( (v8 & 0xF0000) != 0 )
    return (unsigned int)-2147024846;
  v9 = &szDomain;
  if ( !wcscmp_0(String1, L"overrideMode") )
  {
    if ( pvarSrc->vt == 8 )
    {
      if ( !wcscmp_0(pvarSrc->bstrVal, L"Allow") )
      {
        v10 = 1;
      }
      else if ( !wcscmp_0(pvarSrc->bstrVal, L"Deny") )
      {
        v10 = 2;
      }
      else
      {
        if ( wcscmp_0(pvarSrc->bstrVal, L"Inherit") )
        {
          v30[0] = (char *)L"overrideMode";
          v30[1] = (char *)L"Allow, Deny, Inherit";
          v16 = (CONFIG_EXCEPTION *)operator new(0x178u);
          if ( v16 )
          {
            v17 = CONFIG_EXCEPTION::CONFIG_EXCEPTION(v16);
            v6 = (IErrorInfo *)v17;
            if ( v17 )
              CONFIG_EXCEPTION::CreateFromErrorId(v17, 0xC0000A91, (const char **)v30);
          }
          FieldMemory = -2147024883;
          goto LABEL_11;
        }
        v10 = 3;
      }
      FieldMemory = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this + 2) + 200LL))((char *)this + 16, v10);
    }
    else
    {
      FieldMemory = -2147024846;
    }
LABEL_11:
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    if ( VariantChangeType(&pvarg, pvarSrc, 2u, 8u) >= 0 && (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x10) != 0 )
    {
      v11 = *((_QWORD *)this + 10);
      v12 = &szDomain;
      v13 = &szDomain;
      if ( *(_QWORD *)(v11 + 24) )
        v12 = *(const WCHAR **)(v11 + 24);
      v14 = *((_QWORD *)this + 19);
      if ( v14 )
      {
        if ( *(_QWORD *)(v14 + 8) )
          v13 = *(const WCHAR **)(v14 + 8);
        if ( *(_QWORD *)(v14 + 16) )
          v9 = *(const WCHAR **)(v14 + 16);
      }
      McTemplateU0zzzpzzz_EtwEventWriteTransfer(
        (_DWORD)v12,
        0,
        (_DWORD)v9,
        (_DWORD)v13,
        (__int64)L"CONFIG_ELEMENT::SetMetadata",
        (char)this,
        (__int64)v12,
        (__int64)String1,
        pvarg.llVal);
    }
    VariantClear(&pvarg);
    goto LABEL_22;
  }
  if ( wcscmp_0(String1, L"lockItem") )
  {
    FieldMemory = 0;
    if ( !wcscmp_0(String1, L"lockAllElementsExcept")
      || !wcscmp_0(String1, L"lockElements")
      || !wcscmp_0(String1, L"lockAllAttributesExcept")
      || !wcscmp_0(String1, L"lockAttributes") )
    {
      if ( pvarSrc->vt == 8 )
      {
        bstrVal = pvarSrc->bstrVal;
      }
      else
      {
        if ( pvarSrc->vt >= 2u )
          return (unsigned int)-2147024883;
        bstrVal = 0;
      }
      v29 = CONFIG_ELEMENT::SetLockAttribute(this, String1, bstrVal, &v33);
      v6 = (IErrorInfo *)v33;
      FieldMemory = v29;
      if ( v29 < 0 )
        goto LABEL_22;
      goto LABEL_11;
    }
    if ( !wcscmp_0(String1, L"configSource") )
    {
      if ( pvarSrc->vt == 8 )
      {
        v20 = 0;
LABEL_50:
        v21 = pvarSrc->bstrVal;
LABEL_54:
        v22 = CONFIG_ELEMENT::SetConfigSource(this, v21, v20, 1);
LABEL_79:
        FieldMemory = v22;
        goto LABEL_11;
      }
      if ( !pvarSrc->vt )
      {
        v20 = 0;
LABEL_53:
        v21 = &szDomain;
        goto LABEL_54;
      }
    }
    else
    {
      if ( wcscmp_0(String1, L"childSource") )
      {
        if ( !wcscmp_0(String1, L"inheritInChildApplications") )
        {
          if ( pvarSrc->vt == 11 )
          {
            v23 = 256;
            if ( pvarSrc->iVal != -1 )
              v23 = 512;
            *((_DWORD *)this + 34) = v8 & 0xFFFFF0FF | v23;
            CONFIG_ELEMENT::ModifyElementRecursively(this, 1);
            goto LABEL_11;
          }
        }
        else
        {
          if ( wcscmp_0(String1, L"isEmptyElementVisible") )
          {
            FieldMemory = CONFIG_ELEMENT::AllocateFieldMemory((RTL_SRWLOCK *)this, 3);
            if ( FieldMemory < 0 )
              return (unsigned int)FieldMemory;
            v24 = *((_QWORD *)this + 16);
            if ( !*(_QWORD *)(v24 + 8) )
            {
              v25 = operator new(0x28u);
              if ( v25 )
              {
                *(_QWORD *)v25 = &DICTIONARY_LIST::`vftable';
                v25[2] = 8;
                *((_QWORD *)v25 + 2) = 0;
                *((_QWORD *)v25 + 3) = 0;
                *((_QWORD *)v25 + 4) = 0;
              }
              else
              {
                v25 = 0;
              }
              *(_QWORD *)(*((_QWORD *)this + 16) + 8LL) = v25;
              v24 = *((_QWORD *)this + 16);
              if ( !*(_QWORD *)(v24 + 8) )
                return (unsigned int)-2147024888;
            }
            v26 = *(METADATA_LIST **)(v24 + 8);
            pRecInfo = pvarSrc->pRecInfo;
            *(_OWORD *)&v32.vt = *(_OWORD *)&pvarSrc->vt;
            v32.pRecInfo = pRecInfo;
            v22 = METADATA_LIST::SetMetadata(v26, String1, &v32);
            goto LABEL_79;
          }
          if ( pvarSrc->vt == 11 )
          {
            if ( !CONFIG_ELEMENT::TrySetEmptyElementIsVisible(this, 0, pvarSrc->iVal == -1) )
              return (unsigned int)-2147024846;
            goto LABEL_11;
          }
        }
        FieldMemory = -2147024846;
        goto LABEL_11;
      }
      if ( pvarSrc->vt == 8 )
      {
        v20 = 1;
        goto LABEL_50;
      }
      if ( !pvarSrc->vt )
      {
        v20 = 1;
        goto LABEL_53;
      }
    }
    FieldMemory = -2147024846;
    goto LABEL_11;
  }
  if ( pvarSrc->vt == 11 )
  {
    v18 = L"true";
    if ( pvarSrc->iVal != -1 )
      v18 = L"false";
  }
  else
  {
    if ( pvarSrc->vt )
    {
      FieldMemory = -2147024883;
      goto LABEL_22;
    }
    v18 = 0;
  }
  v19 = CONFIG_ELEMENT::SetLockAttribute(this, (wchar_t *)L"lockItem", v18, &v33);
  v6 = (IErrorInfo *)v33;
  FieldMemory = v19;
  if ( v19 >= 0 )
    goto LABEL_11;
LABEL_22:
  if ( v6 )
  {
    SetErrorInfo(0, v6 + 1);
    CONFIG_EXCEPTION::DereferenceSectionException((CONFIG_EXCEPTION *)v6);
  }
  return (unsigned int)FieldMemory;
}

```

## disassembly

```asm
0x180034410  push    rbp
0x180034412  push    rbx
0x180034413  push    rsi
0x180034414  push    rdi
0x180034415  push    r12
0x180034417  push    r13
0x180034419  push    r14
0x18003441b  push    r15
0x18003441d  lea     rbp, [rsp-1Fh]
0x180034422  sub     rsp, 0A8h
0x180034429  xor     ebx, ebx
0x18003442b  xorps   xmm0, xmm0
0x18003442e  mov     [rbp+57h+arg_8], rbx
0x180034432  mov     rsi, r8
0x180034435  mov     r15, rdx
0x180034438  mov     rdi, rcx
0x18003443b  mov     r14d, ebx
0x18003443e  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180034442  test    rdx, rdx
0x180034445  jnz     short loc_180034451
0x180034447  mov     ebx, 80070057h
0x18003444c  jmp     loc_18003458F
0x180034451  mov     r12d, [rcx+88h]
0x180034458  test    r12d, 0F0000h
0x18003445f  jz      short loc_18003446B
0x180034461  mov     ebx, 80070032h
0x180034466  jmp     loc_18003458F
0x18003446b  lea     rdx, aOverridemode; "overrideMode"
0x180034472  mov     rcx, r15; String1
0x180034475  call    wcscmp_0
0x18003447a  lea     r13, szDomain
0x180034481  mov     ecx, 8
0x180034486  test    eax, eax
0x180034488  jnz     loc_18003462D
0x18003448e  cmp     [rsi], cx
0x180034491  jz      short loc_18003449D
0x180034493  mov     ebx, 80070032h
0x180034498  mov     r12d, ecx
0x18003449b  jmp     short loc_1800344D3
0x18003449d  mov     rcx, [rsi+8]; String1
0x1800344a1  lea     rdx, aAllow; "Allow"
0x1800344a8  call    wcscmp_0
0x1800344ad  test    eax, eax
0x1800344af  jnz     loc_1800345A5
0x1800344b5  lea     edx, [rax+1]
0x1800344b8  lea     rcx, [rdi+10h]
0x1800344bc  mov     rax, [rcx]
0x1800344bf  mov     rax, [rax+0C8h]
0x1800344c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344cb  mov     ebx, eax
0x1800344cd  mov     r12d, 8
0x1800344d3  xorps   xmm0, xmm0
0x1800344d6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800344da  xor     eax, eax
0x1800344dc  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800344e0  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800344e4  call    cs:__imp_VariantInit
0x1800344ea  mov     r9d, r12d; vt
0x1800344ed  lea     rcx, [rbp+57h+pvarg]; pvargDest
0x1800344f1  mov     r8d, 2; wFlags
0x1800344f7  mov     rdx, rsi; pvarSrc
0x1800344fa  call    cs:__imp_VariantChangeType
0x180034500  xor     edx, edx
0x180034502  test    eax, eax
0x180034504  js      short loc_18003456C
0x180034506  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 10h
0x18003450d  jz      short loc_18003456C
0x18003450f  mov     rax, [rdi+50h]
0x180034513  mov     rcx, r13
0x180034516  mov     r9, r13
0x180034519  cmp     [rax+18h], rdx
0x18003451d  cmovnz  rcx, [rax+18h]
0x180034522  mov     rax, [rdi+98h]
0x180034529  test    rax, rax
0x18003452c  jz      short loc_180034540
0x18003452e  cmp     [rax+8], rdx
0x180034532  cmovnz  r9, [rax+8]
0x180034537  cmp     [rax+10h], rdx
0x18003453b  cmovnz  r13, [rax+10h]
0x180034540  mov     rax, qword ptr [rbp+57h+pvarg+8]
0x180034544  mov     r8, r13
0x180034547  mov     [rsp+0E0h+var_A0], rax
0x18003454c  lea     rax, aConfigElementS; "CONFIG_ELEMENT::SetMetadata"
0x180034553  mov     [rsp+0E0h+var_A8], r15
0x180034558  mov     [rsp+0E0h+var_B0], rcx
0x18003455d  mov     [rsp+0E0h+var_B8], rdi
0x180034562  mov     [rsp+0E0h+var_C0], rax
0x180034567  call    McTemplateU0zzzpzzz_EtwEventWriteTransfer
0x18003456c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180034570  call    cs:__imp_VariantClear
0x180034576  test    r14, r14
0x180034579  jz      short loc_18003458F
0x18003457b  lea     rdx, [r14+8]; perrinfo
0x18003457f  xor     ecx, ecx; dwReserved
0x180034581  call    cs:__imp_SetErrorInfo
0x180034587  mov     rcx, r14; this
0x18003458a  call    ?DereferenceSectionException@CONFIG_EXCEPTION@@QEAAXXZ; CONFIG_EXCEPTION::DereferenceSectionException(void)
0x18003458f  mov     eax, ebx
0x180034591  add     rsp, 0A8h
0x180034598  pop     r15
0x18003459a  pop     r14
0x18003459c  pop     r13
0x18003459e  pop     r12
0x1800345a0  pop     rdi
0x1800345a1  pop     rsi
0x1800345a2  pop     rbx
0x1800345a3  pop     rbp
0x1800345a4  retn
0x1800345a5  mov     rcx, [rsi+8]; String1
0x1800345a9  lea     rdx, aDeny; "Deny"
0x1800345b0  call    wcscmp_0
0x1800345b5  test    eax, eax
0x1800345b7  jnz     short loc_1800345C1
0x1800345b9  lea     edx, [rax+2]
0x1800345bc  jmp     loc_1800344B8
0x1800345c1  mov     rcx, [rsi+8]; String1
0x1800345c5  lea     rdx, aInherit; "Inherit"
0x1800345cc  call    wcscmp_0
0x1800345d1  test    eax, eax
0x1800345d3  jnz     short loc_1800345DD
0x1800345d5  lea     edx, [rax+3]
0x1800345d8  jmp     loc_1800344B8
0x1800345dd  lea     rax, aOverridemode; "overrideMode"
0x1800345e4  mov     ecx, 178h; Size
0x1800345e9  mov     [rbp+57h+var_90], rax
0x1800345ed  lea     rax, aAllowDenyInher; "Allow, Deny, Inherit"
0x1800345f4  mov     [rbp+57h+var_90+8], rax
0x1800345f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800345fd  test    rax, rax
0x180034600  jz      short loc_180034623
0x180034602  mov     rcx, rax; this
0x180034605  call    ??0CONFIG_EXCEPTION@@QEAA@XZ; CONFIG_EXCEPTION::CONFIG_EXCEPTION(void)
0x18003460a  mov     r14, rax
0x18003460d  test    rax, rax
0x180034610  jz      short loc_180034623
0x180034612  lea     r8, [rbp+57h+var_90]; char **
0x180034616  mov     edx, 0C0000A91h; unsigned int
0x18003461b  mov     rcx, rax; this
0x18003461e  call    ?CreateFromErrorId@CONFIG_EXCEPTION@@QEAAJKPEAPEBD@Z; CONFIG_EXCEPTION::CreateFromErrorId(ulong,char const * *)
0x180034623  mov     ebx, 8007000Dh
0x180034628  jmp     loc_1800344CD
0x18003462d  lea     rbx, aLockitem; "lockItem"
0x180034634  mov     rcx, r15; String1
0x180034637  mov     rdx, rbx; String2
0x18003463a  call    wcscmp_0
0x18003463f  xor     edx, edx
0x180034641  test    eax, eax
0x180034643  jnz     short loc_180034698
0x180034645  cmp     word ptr [rsi], 0Bh
0x180034649  jnz     short loc_180034664
0x18003464b  cmp     word ptr [rsi+8], 0FFFFh
0x180034650  lea     rax, aFalse; "false"
0x180034657  lea     r8, aTrue; "true"
0x18003465e  cmovnz  r8, rax
0x180034662  jmp     short loc_18003466C
0x180034664  cmp     [rsi], dx
0x180034667  jnz     short loc_18003468E
0x180034669  mov     r8, rdx; unsigned __int16 *
0x18003466c  lea     r9, [rbp+57h+arg_8]; struct CONFIG_EXCEPTION **
0x180034670  mov     rcx, rdi; this
0x180034673  mov     rdx, rbx; String1
0x180034676  call    ?SetLockAttribute@CONFIG_ELEMENT@@QEAAJPEBG0PEAPEAVCONFIG_EXCEPTION@@@Z; CONFIG_ELEMENT::SetLockAttribute(ushort const *,ushort const *,CONFIG_EXCEPTION * *)
0x18003467b  mov     r14, [rbp+57h+arg_8]
0x18003467f  mov     ebx, eax
0x180034681  test    eax, eax
0x180034683  jns     loc_1800344CD
0x180034689  jmp     loc_180034576
0x18003468e  mov     ebx, 8007000Dh
0x180034693  jmp     loc_180034576
0x180034698  lea     rdx, aLockallelement; "lockAllElementsExcept"
0x18003469f  mov     rcx, r15; String1
0x1800346a2  call    wcscmp_0
0x1800346a7  xor     ebx, ebx
0x1800346a9  test    eax, eax
0x1800346ab  jz      loc_1800348BF
0x1800346b1  lea     rdx, aLockelements; "lockElements"
0x1800346b8  mov     rcx, r15; String1
0x1800346bb  call    wcscmp_0
0x1800346c0  test    eax, eax
0x1800346c2  jz      loc_1800348BF
0x1800346c8  lea     rdx, aLockallattribu; "lockAllAttributesExcept"
0x1800346cf  mov     rcx, r15; String1
0x1800346d2  call    wcscmp_0
0x1800346d7  test    eax, eax
0x1800346d9  jz      loc_1800348BF
0x1800346df  lea     rdx, aLockattributes; "lockAttributes"
0x1800346e6  mov     rcx, r15; String1
0x1800346e9  call    wcscmp_0
0x1800346ee  test    eax, eax
0x1800346f0  jz      loc_1800348BF
0x1800346f6  lea     rdx, aConfigsource; "configSource"
0x1800346fd  mov     rcx, r15; String1
0x180034700  call    wcscmp_0
0x180034705  test    eax, eax
0x180034707  jnz     short loc_18003473E
0x180034709  lea     r12d, [rbx+8]
0x18003470d  cmp     [rsi], r12w
0x180034711  jnz     short loc_180034720
0x180034713  lea     r9d, [rbx+1]
0x180034717  xor     r8d, r8d
0x18003471a  mov     rdx, [rsi+8]
0x18003471e  jmp     short loc_180034731
0x180034720  cmp     [rsi], bx
0x180034723  jnz     short loc_180034774
0x180034725  mov     r9d, 1; int
0x18003472b  xor     r8d, r8d; int
0x18003472e  mov     rdx, r13; unsigned __int16 *
0x180034731  mov     rcx, rdi; this
0x180034734  call    ?SetConfigSource@CONFIG_ELEMENT@@QEAAJPEBGHH@Z; CONFIG_ELEMENT::SetConfigSource(ushort const *,int,int)
0x180034739  jmp     loc_1800348B8
0x18003473e  lea     rdx, aChildsource; "childSource"
0x180034745  mov     rcx, r15; String1
0x180034748  call    wcscmp_0
0x18003474d  test    eax, eax
0x18003474f  jnz     short loc_18003477E
0x180034751  lea     r12d, [rax+8]
0x180034755  cmp     [rsi], r12w
0x180034759  jnz     short loc_180034764
0x18003475b  lea     r9d, [rax+1]
0x18003475f  mov     r8d, r9d
0x180034762  jmp     short loc_18003471A
0x180034764  cmp     [rsi], bx
0x180034767  jnz     short loc_180034774
0x180034769  mov     r9d, 1
0x18003476f  mov     r8d, r9d
0x180034772  jmp     short loc_18003472E
0x180034774  mov     ebx, 80070032h
0x180034779  jmp     loc_1800344D3
0x18003477e  lea     rdx, aInheritinchild; "inheritInChildApplications"
0x180034785  mov     rcx, r15; String1
0x180034788  call    wcscmp_0
0x18003478d  test    eax, eax
0x18003478f  jnz     short loc_1800347D7
0x180034791  cmp     word ptr [rsi], 0Bh
0x180034795  jz      short loc_1800347A1
0x180034797  mov     ebx, 80070032h
0x18003479c  jmp     loc_1800344CD
0x1800347a1  cmp     word ptr [rsi+8], 0FFFFh
0x1800347a6  mov     eax, 100h
0x1800347ab  mov     ecx, 200h
0x1800347b0  cmovnz  eax, ecx
0x1800347b3  xor     r8d, r8d
0x1800347b6  and     r12d, 0FFFFF0FFh
0x1800347bd  mov     rcx, rdi
0x1800347c0  or      eax, r12d
0x1800347c3  mov     [rdi+88h], eax
0x1800347c9  lea     edx, [r8+1]
0x1800347cd  call    ?ModifyElementRecursively@CONFIG_ELEMENT@@QEAAXW4CONFIG_EDIT_TYPE@@H@Z; CONFIG_ELEMENT::ModifyElementRecursively(CONFIG_EDIT_TYPE,int)
0x1800347d2  jmp     loc_1800344CD
0x1800347d7  lea     rdx, aIsemptyelement; "isEmptyElementVisible"
0x1800347de  mov     rcx, r15; String1
0x1800347e1  call    wcscmp_0
0x1800347e6  test    eax, eax
0x1800347e8  jnz     short loc_180034816
0x1800347ea  cmp     word ptr [rsi], 0Bh
0x1800347ee  jnz     short loc_180034797
0x1800347f0  xor     r12d, r12d
0x1800347f3  mov     rcx, rdi; this
0x1800347f6  cmp     word ptr [rsi+8], 0FFFFh
0x1800347fb  mov     r8d, r12d
0x1800347fe  setz    r8b; int
0x180034802  xor     edx, edx; int
0x180034804  call    ?TrySetEmptyElementIsVisible@CONFIG_ELEMENT@@QEAAHHH@Z; CONFIG_ELEMENT::TrySetEmptyElementIsVisible(int,int)
0x180034809  test    eax, eax
0x18003480b  jnz     loc_1800344CD
0x180034811  jmp     loc_180034461
0x180034816  mov     edx, 3
0x18003481b  mov     rcx, rdi
0x18003481e  call    ?AllocateFieldMemory@CONFIG_ELEMENT@@QEAAJW4ALLOCATION_TYPE@@@Z; CONFIG_ELEMENT::AllocateFieldMemory(ALLOCATION_TYPE)
0x180034823  mov     ebx, eax
0x180034825  test    eax, eax
0x180034827  js      loc_18003458F
0x18003482d  mov     rcx, [rdi+80h]
0x180034834  xor     ebx, ebx
0x180034836  cmp     [rcx+8], rbx
0x18003483a  jnz     short loc_180034891
0x18003483c  lea     ecx, [rbx+28h]; Size
0x18003483f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034844  lea     r12d, [rbx+8]
0x180034848  mov     rcx, rax
0x18003484b  test    rax, rax
0x18003484e  jz      short loc_18003486C
0x180034850  lea     rax, ??_7DICTIONARY_LIST@@6B@; const DICTIONARY_LIST::`vftable'
0x180034857  mov     [rcx], rax
0x18003485a  mov     [rcx+8], r12d
0x18003485e  mov     [rcx+10h], rbx
0x180034862  mov     [rcx+18h], rbx
0x180034866  mov     [rcx+20h], rbx
0x18003486a  jmp     short loc_18003486F
0x18003486c  mov     rcx, rbx
0x18003486f  mov     rax, [rdi+80h]
0x180034876  mov     [rax+8], rcx
0x18003487a  mov     rcx, [rdi+80h]
0x180034881  cmp     [rcx+8], rbx
0x180034885  jnz     short loc_180034897
0x180034887  mov     ebx, 80070008h
0x18003488c  jmp     loc_18003458F
0x180034891  mov     r12d, 8
0x180034897  movups  xmm0, xmmword ptr [rsi]
0x18003489a  lea     r8, [rbp+57h+var_60]; struct tagVARIANT
  ... truncated ...
```
