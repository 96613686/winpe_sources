# XMLHttp2::Initialize(void)

- ea: `0x18013d4b0`
- end: `0x18013d626`
- name: `?Initialize@XMLHttp2@@AEAAJXZ`
- size: `374`
- prototype: `HRESULT __fastcall(XMLHttp2 *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008be70`

## callees

- `0x18013cb14`
- `0x18013d4b0`
- `0x180189008`
- `0x1801890e0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013d5e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013d5e9`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18013d503`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18013d503`

## pseudocode

```c
__int64 __fastcall XMLHttp2::Initialize(XMLHttp2 *this)
{
  HRESULT ApartmentType; // ebx
  int v3; // ebx
  XMLHttp *v4; // rcx
  _APTTYPE AptType; // [rsp+48h] [rbp+28h] BYREF
  _APTTYPEQUALIFIER AptQualifier; // [rsp+50h] [rbp+30h] BYREF
  XMLHttp *pXMLHttp; // [rsp+58h] [rbp+38h] BYREF

  pXMLHttp = 0;
  AptType = APTTYPE_CURRENT;
  AptQualifier = APTTYPEQUALIFIER_NONE;
  if ( (xmmword_1801FAD20 & 2) != 0 )
    WPP_SF_q(0x401u, 0x83u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, (unsigned __int64)this);
  ApartmentType = CoGetApartmentType(&AptType, &AptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_9;
  v3 = 0;
  if ( AptType == APTTYPE_STA )
  {
LABEL_22:
    this->m_dwStaThreadId = GetCurrentThreadId();
    goto LABEL_23;
  }
  if ( AptType == APTTYPE_MTA )
    goto LABEL_21;
  if ( AptType != APTTYPE_NA )
  {
    if ( AptType != APTTYPE_MAINSTA )
    {
LABEL_8:
      ApartmentType = -2147417842;
LABEL_9:
      v4 = pXMLHttp;
      goto $CleanUp_442;
    }
    goto LABEL_22;
  }
  switch ( AptQualifier )
  {
    case APTTYPEQUALIFIER_IMPLICIT_MTA:
    case APTTYPEQUALIFIER_NA_ON_MTA:
      goto LABEL_21;
    case APTTYPEQUALIFIER_NA_ON_STA:
      goto LABEL_23;
    case APTTYPEQUALIFIER_NA_ON_IMPLICIT_MTA:
LABEL_21:
      v3 = 1;
      goto LABEL_23;
  }
  if ( (unsigned int)(AptQualifier - 5) >= 2 )
    goto LABEL_8;
LABEL_23:
  ApartmentType = XMLHttp::CreateInstance(v3, 1, 0, &pXMLHttp);
  if ( ApartmentType < 0 )
    goto LABEL_9;
  v4 = 0;
  this->m_pXMLHttp = pXMLHttp;
  pXMLHttp = 0;
$CleanUp_442:
  if ( v4 )
  {
    v4->Release(v4);
    pXMLHttp = 0;
  }
  if ( (g_rgFastWppLevelEnabledFlags[2 * (ApartmentType >> 31) + 4].rgbFlags[0] & 2) != 0 )
    WPP_SF_d(
      (((unsigned __int16)(ApartmentType >> 31) + 2) << 9) | 1,
      0x84u,
      WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids,
      ApartmentType);
  return (unsigned int)ApartmentType;
}

```

## disassembly

```asm
0x18013d4b0  mov     [rsp-18h+arg_0], rbx
0x18013d4b5  push    rbp
0x18013d4b6  push    rdi
0x18013d4b7  push    r14
0x18013d4b9  mov     rbp, rsp
0x18013d4bc  sub     rsp, 20h
0x18013d4c0  mov     rdi, this
0x18013d4c3  mov     [rbp+pXMLHttp], 0
0x18013d4cb  mov     [rbp+AptType], 0FFFFFFFFh
0x18013d4d2  mov     [rbp+AptQualifier], 0
0x18013d4d9  test    byte ptr cs:xmmword_1801FAD20, 2; __annotation("TMF:",
0x18013d4e0  jz      short loc_18013D4FB
0x18013d4e2  mov     edx, 83h; id
0x18013d4e7  lea     r8, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x18013d4ee  mov     ecx, 401h; LevelKeyword
0x18013d4f3  mov     r9, rdi; _a1
0x18013d4f6  call    WPP_SF_q
0x18013d4fb  lea     rdx, [rbp+AptQualifier]; pAptQualifier
0x18013d4ff  lea     this, [rbp+AptType]; pAptType
0x18013d503  call    cs:__imp_CoGetApartmentType
0x18013d50a  nop     dword ptr [rax+rax+00h]
0x18013d50f  mov     ebx, eax
0x18013d511  mov     r14d, 1
0x18013d517  test    eax, eax
0x18013d519  js      short loc_18013D548
0x18013d51b  mov     ecx, [rbp+AptType]
0x18013d51e  xor     ebx, ebx
0x18013d520  test    ecx, ecx
0x18013d522  jz      loc_18013D5E9
0x18013d528  sub     ecx, r14d
0x18013d52b  jz      loc_18013D5E4
0x18013d531  sub     ecx, r14d
0x18013d534  jz      loc_18013D5BE
0x18013d53a  cmp     ecx, r14d
0x18013d53d  jz      loc_18013D5E9
0x18013d543  mov     ebx, 8001010Eh
0x18013d548  mov     this, [rbp+pXMLHttp]
0x18013d54c  test    this, this
0x18013d54f  jz      short loc_18013D565
0x18013d551  mov     rax, [this]
0x18013d554  mov     rax, [rax+10h]
0x18013d558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d55d  mov     [rbp+pXMLHttp], 0
0x18013d565  mov     r9d, ebx; __annotation("TMF:",
0x18013d568  sar     r9d, 1Fh
0x18013d56c  lea     eax, ds:4[r9*2]
0x18013d574  movsxd  this, eax
0x18013d577  lea     rax, g_rgFastWppLevelEnabledFlags
0x18013d57e  test    byte ptr [rax+this*8], 2
0x18013d582  jz      short loc_18013D5AD
0x18013d584  add     r9w, 2
0x18013d589  lea     r8, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x18013d590  movzx   ecx, r9w
0x18013d594  mov     eax, 200h
0x18013d599  imul    ecx, eax
0x18013d59c  mov     edx, 84h; id
0x18013d5a1  mov     r9d, ebx; _a1
0x18013d5a4  or      cx, r14w; LevelKeyword
0x18013d5a8  call    WPP_SF_d
0x18013d5ad  mov     eax, ebx
0x18013d5af  mov     rbx, [rsp+20h+arg_0]
0x18013d5b4  add     rsp, 20h
0x18013d5b8  pop     r14
0x18013d5ba  pop     rdi
0x18013d5bb  pop     rbp
0x18013d5bc  retn
0x18013d5be  mov     ecx, [rbp+AptQualifier]
0x18013d5c1  sub     ecx, r14d
0x18013d5c4  jz      short loc_18013D5E4
0x18013d5c6  sub     ecx, r14d
0x18013d5c9  jz      short loc_18013D5E4
0x18013d5cb  sub     ecx, r14d
0x18013d5ce  jz      short loc_18013D5F8
0x18013d5d0  sub     ecx, r14d
0x18013d5d3  jz      short loc_18013D5E4
0x18013d5d5  sub     ecx, r14d
0x18013d5d8  jz      short loc_18013D5F8
0x18013d5da  cmp     ecx, r14d
0x18013d5dd  jz      short loc_18013D5F8
0x18013d5df  jmp     loc_18013D543
0x18013d5e4  mov     ebx, r14d
0x18013d5e7  jmp     short loc_18013D5F8
0x18013d5e9  call    cs:__imp_GetCurrentThreadId
0x18013d5f0  nop     dword ptr [rax+rax+00h]
0x18013d5f5  mov     [rdi+30h], eax
0x18013d5f8  lea     r9, [rbp+pXMLHttp]; ppXmlHttp
0x18013d5fc  xor     r8d, r8d; fServer
0x18013d5ff  mov     edx, r14d; fDisableLegacyFeatures
0x18013d602  mov     ecx, ebx; fMta
0x18013d604  call    ?CreateInstance@XMLHttp@@SAJHHHPEAPEAV1@@Z; XMLHttp::CreateInstance(int,int,int,XMLHttp * *)
0x18013d609  mov     ebx, eax
0x18013d60b  test    eax, eax
0x18013d60d  js      loc_18013D548
0x18013d613  mov     rax, [rbp+pXMLHttp]
0x18013d617  xor     ecx, ecx
0x18013d619  mov     [rdi+28h], rax
0x18013d61d  mov     [rbp+pXMLHttp], this
0x18013d621  jmp     $CleanUp_442
```
