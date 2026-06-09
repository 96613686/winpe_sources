# XMLHttp2::Initialize(void)

- ea: `0x18013a3d0`
- end: `0x18013a539`
- name: `?Initialize@XMLHttp2@@AEAAJXZ`
- size: `361`
- prototype: `HRESULT __fastcall(XMLHttp2 *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008becc`

## callees

- `0x180139a44`
- `0x18013a3d0`
- `0x180185008`
- `0x1801850e0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013a502`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013a502`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18013a423`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18013a423`

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
  if ( (xmmword_1801F6C20 & 2) != 0 )
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
0x18013a3d0  mov     [rsp-18h+arg_0], rbx
0x18013a3d5  push    rbp
0x18013a3d6  push    rdi
0x18013a3d7  push    r14
0x18013a3d9  mov     rbp, rsp
0x18013a3dc  sub     rsp, 20h
0x18013a3e0  mov     rdi, this
0x18013a3e3  mov     [rbp+pXMLHttp], 0
0x18013a3eb  mov     [rbp+AptType], 0FFFFFFFFh
0x18013a3f2  mov     [rbp+AptQualifier], 0
0x18013a3f9  test    byte ptr cs:xmmword_1801F6C20, 2; __annotation("TMF:",
0x18013a400  jz      short loc_18013A41B
0x18013a402  mov     edx, 83h; id
0x18013a407  lea     r8, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x18013a40e  mov     ecx, 401h; LevelKeyword
0x18013a413  mov     r9, rdi; _a1
0x18013a416  call    WPP_SF_q
0x18013a41b  lea     rdx, [rbp+AptQualifier]; pAptQualifier
0x18013a41f  lea     this, [rbp+AptType]; pAptType
0x18013a423  call    cs:__imp_CoGetApartmentType
0x18013a429  mov     ebx, eax
0x18013a42b  mov     r14d, 1
0x18013a431  test    eax, eax
0x18013a433  js      short loc_18013A462
0x18013a435  mov     ecx, [rbp+AptType]
0x18013a438  xor     ebx, ebx
0x18013a43a  test    ecx, ecx
0x18013a43c  jz      loc_18013A502
0x18013a442  sub     ecx, r14d
0x18013a445  jz      loc_18013A4FD
0x18013a44b  sub     ecx, r14d
0x18013a44e  jz      loc_18013A4D7
0x18013a454  cmp     ecx, r14d
0x18013a457  jz      loc_18013A502
0x18013a45d  mov     ebx, 8001010Eh
0x18013a462  mov     this, [rbp+pXMLHttp]
0x18013a466  test    this, this
0x18013a469  jz      short loc_18013A47F
0x18013a46b  mov     rax, [this]
0x18013a46e  mov     rax, [rax+10h]
0x18013a472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013a477  mov     [rbp+pXMLHttp], 0
0x18013a47f  mov     r9d, ebx; __annotation("TMF:",
0x18013a482  sar     r9d, 1Fh
0x18013a486  lea     eax, ds:4[r9*2]
0x18013a48e  movsxd  this, eax
0x18013a491  lea     rax, g_rgFastWppLevelEnabledFlags
0x18013a498  test    byte ptr [rax+this*8], 2
0x18013a49c  jz      short loc_18013A4C7
0x18013a49e  add     r9w, 2
0x18013a4a3  lea     r8, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x18013a4aa  movzx   ecx, r9w
0x18013a4ae  mov     eax, 200h
0x18013a4b3  imul    ecx, eax
0x18013a4b6  mov     edx, 84h; id
0x18013a4bb  mov     r9d, ebx; _a1
0x18013a4be  or      cx, r14w; LevelKeyword
0x18013a4c2  call    WPP_SF_d
0x18013a4c7  mov     eax, ebx
0x18013a4c9  mov     rbx, [rsp+20h+arg_0]
0x18013a4ce  add     rsp, 20h
0x18013a4d2  pop     r14
0x18013a4d4  pop     rdi
0x18013a4d5  pop     rbp
0x18013a4d6  retn
0x18013a4d7  mov     ecx, [rbp+AptQualifier]
0x18013a4da  sub     ecx, r14d
0x18013a4dd  jz      short loc_18013A4FD
0x18013a4df  sub     ecx, r14d
0x18013a4e2  jz      short loc_18013A4FD
0x18013a4e4  sub     ecx, r14d
0x18013a4e7  jz      short loc_18013A50B
0x18013a4e9  sub     ecx, r14d
0x18013a4ec  jz      short loc_18013A4FD
0x18013a4ee  sub     ecx, r14d
0x18013a4f1  jz      short loc_18013A50B
0x18013a4f3  cmp     ecx, r14d
0x18013a4f6  jz      short loc_18013A50B
0x18013a4f8  jmp     loc_18013A45D
0x18013a4fd  mov     ebx, r14d
0x18013a500  jmp     short loc_18013A50B
0x18013a502  call    cs:__imp_GetCurrentThreadId
0x18013a508  mov     [rdi+30h], eax
0x18013a50b  lea     r9, [rbp+pXMLHttp]; ppXmlHttp
0x18013a50f  xor     r8d, r8d; fServer
0x18013a512  mov     edx, r14d; fDisableLegacyFeatures
0x18013a515  mov     ecx, ebx; fMta
0x18013a517  call    ?CreateInstance@XMLHttp@@SAJHHHPEAPEAV1@@Z; XMLHttp::CreateInstance(int,int,int,XMLHttp * *)
0x18013a51c  mov     ebx, eax
0x18013a51e  test    eax, eax
0x18013a520  js      loc_18013A462
0x18013a526  mov     rax, [rbp+pXMLHttp]
0x18013a52a  xor     ecx, ecx
0x18013a52c  mov     [rdi+28h], rax
0x18013a530  mov     [rbp+pXMLHttp], this
0x18013a534  jmp     $CleanUp_442
```
