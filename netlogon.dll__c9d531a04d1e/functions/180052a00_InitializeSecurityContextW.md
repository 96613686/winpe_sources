# InitializeSecurityContextW

- ea: `0x180052a00`
- end: `0x180052e90`
- name: `InitializeSecurityContextW`
- size: `1168`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, SEC_WCHAR *pszTargetName, unsigned int fContextReq, unsigned int Reserved1, unsigned int TargetDataRep, PSecBufferDesc pInput, unsigned int Reserved2, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007278`
- `0x18000b8e4`
- `0x18000ccf0`
- `0x18000d094`
- `0x18000d1a0`
- `0x18000d710`
- `0x18000e270`
- `0x18000ed34`
- `0x180051574`
- `0x180052a00`
- `0x1800836f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180052bd0`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180052bfe`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180052bd0`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180052bfe`
- `ntdll!RtlLeaveCriticalSection` at `0x180052b61`
- `ntdll!RtlLeaveCriticalSection` at `0x180052b61`
- `ntdll!RtlEnterCriticalSection` at `0x180052b2d`
- `ntdll!RtlEnterCriticalSection` at `0x180052b2d`

## string_xrefs

- `0x180052b8b`: `onecore\ds\netapi\svcdlls\logonsrv\server\secpkg.cxx`
- `0x180052a6f`: `InitializeSecurityContext: %ws: called\n`
- `0x180052af0`: `InitializeSecurityContext: %Ix.%Ix: %ws: called with cred handle\n`
- `0x180052d86`: `Cannot pack UTF-8 netbios computer name into message %ld\n`
- `0x180052d5a`: `InitializeSecurityContext: Cannot allocate context\n`
- `0x180052dc6`: `InitializeSecurityContext: %Ix.%Ix: %ws: called with context handle\n`
- `0x180052e58`: `InitializeSecurityContext: returns 0x%lx\n`

## pseudocode

```c
SECURITY_STATUS __stdcall InitializeSecurityContextW(
        PCredHandle phCredential,
        PCtxtHandle phContext,
        SEC_WCHAR *pszTargetName,
        unsigned int fContextReq,
        unsigned int Reserved1,
        unsigned int TargetDataRep,
        PSecBufferDesc pInput,
        unsigned int Reserved2,
        PCtxtHandle phNewContext,
        PSecBufferDesc pOutput,
        unsigned int *pfContextAttr,
        PTimeStamp ptsExpiry)
{
  unsigned int v17; // ebx
  struct _SecBuffer *Buffer; // rax
  struct _SecBuffer *v19; // r14
  __int64 v20; // rbx
  struct _RTL_CRITICAL_SECTION *v21; // rsi
  struct _NL_AUTH_CREDENTIAL * near *i; // rbx
  char *v23; // r9
  struct _NL_AUTH_CREDENTIAL *v24; // rbx
  char *pvBuffer; // rdi
  char *v26; // rsi
  int v27; // eax
  unsigned __int8 *v28; // rcx
  int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  struct _NL_AUTH_CONTEXT *v34; // rax
  struct _NL_AUTH_CONTEXT *v35; // rcx
  int v36; // eax
  _OWORD *p_dwLower; // rax
  struct _NL_AUTH_CONTEXT *Context; // rax
  struct _SecBuffer *v39; // rax
  __int64 v40; // r9
  union _LARGE_INTEGER *v41; // rcx
  unsigned int v42; // [rsp+40h] [rbp-A1h] BYREF
  unsigned __int8 *v43; // [rsp+48h] [rbp-99h] BYREF
  unsigned int v44; // [rsp+50h] [rbp-91h] BYREF
  PTimeStamp v45; // [rsp+58h] [rbp-89h]
  PCtxtHandle v46; // [rsp+60h] [rbp-81h]
  char *v47[10]; // [rsp+70h] [rbp-71h] BYREF
  unsigned __int16 v48[12]; // [rsp+C0h] [rbp-21h] BYREF

  v46 = phNewContext;
  v45 = ptsExpiry;
  memset_0(v47, 0, sizeof(v47));
  NlPrintRoutine(0x80000u, L"InitializeSecurityContext: %ws: called\n", pszTargetName);
  if ( !(unsigned int)NlStartNetlogonCall() )
    return -2146893051;
  if ( (fContextReq & 0x100) != 0 )
    goto LABEL_4;
  Buffer = LocateBuffer(pOutput, 0xCu);
  v19 = Buffer;
  if ( !Buffer )
  {
LABEL_6:
    v17 = -2146893048;
    goto LABEL_51;
  }
  if ( Buffer->cbBuffer < 0x22C )
  {
    v17 = -2146893023;
    goto LABEL_51;
  }
  if ( phContext )
  {
    NlPrintRoutine(
      0x80000u,
      L"InitializeSecurityContext: %Ix.%Ix: %ws: called with context handle\n",
      phContext->dwUpper,
      phContext->dwLower,
      pszTargetName);
    Context = LocateContext(phContext);
    if ( !Context || *((_DWORD *)Context + 14) != 1 )
    {
      v17 = -2146893055;
      goto LABEL_51;
    }
    v39 = LocateBuffer(pInput, 0xCu);
    if ( !v39 || v39->cbBuffer < 0xC || *(_DWORD *)v39->pvBuffer != 1 )
      goto LABEL_6;
    *(_DWORD *)(v40 + 56) = 3;
    v17 = 0;
    *(_QWORD *)(v40 + 24) = 0;
    v19->cbBuffer = 0;
LABEL_50:
    v41 = v45;
    *pfContextAttr = fContextReq;
    *v41 = Forever;
    goto LABEL_51;
  }
  if ( !phCredential )
    goto LABEL_11;
  NlPrintRoutine(
    0x80000u,
    L"InitializeSecurityContext: %Ix.%Ix: %ws: called with cred handle\n",
    phCredential->dwUpper,
    phCredential->dwLower,
    pszTargetName);
  v20 = phCredential->dwLower & 0xF;
  v21 = (struct _RTL_CRITICAL_SECTION *)(&NlGlobalSecPkgCritSect + 6 * v20);
  RtlEnterCriticalSection(v21);
  for ( i = (&CredentialList)[v20]; i; i = (struct _NL_AUTH_CREDENTIAL * near *)i[2] )
  {
    if ( i[1] == (struct _NL_AUTH_CREDENTIAL *)phCredential->dwUpper
      && *i == (struct _NL_AUTH_CREDENTIAL *)phCredential->dwLower )
    {
      break;
    }
  }
  RtlLeaveCriticalSection(v21);
  if ( !i )
  {
LABEL_11:
    v17 = -2146893043;
    goto LABEL_51;
  }
  v24 = i[4];
  if ( !v24 )
    goto LABEL_6;
  if ( *(_DWORD *)v24 != 689046055 )
    NlAssertFailed(
      "ClientAuthData->Signature == NL_AUTH_DATA_SIGNATURE",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\secpkg.cxx",
      1462,
      v23);
  memset_0(v19->pvBuffer, 0, v19->cbBuffer);
  pvBuffer = (char *)v19->pvBuffer;
  *(_QWORD *)pvBuffer = 0;
  v26 = pvBuffer + 8;
  v27 = *((_DWORD *)v24 + 8);
  v43 = (unsigned __int8 *)(pvBuffer + 8);
  if ( v27 )
  {
    strcpy_s(pvBuffer + 8, (unsigned int)(v27 + 1), (const char *)v24 + *((unsigned int *)v24 + 7));
    v28 = (unsigned __int8 *)&v26[*((_DWORD *)v24 + 8) + 1];
    *((_DWORD *)pvBuffer + 1) |= 1u;
    v26 = (char *)v28;
    v43 = v28;
  }
  v29 = *((_DWORD *)v24 + 11);
  if ( v29 )
  {
    strcpy_s(v26, (unsigned int)(v29 + 1), (const char *)v24 + *((unsigned int *)v24 + 10));
    v26 += (unsigned int)(*((_DWORD *)v24 + 11) + 1);
    *((_DWORD *)pvBuffer + 1) |= 2u;
    v43 = (unsigned __int8 *)v26;
  }
  v30 = 0;
  v44 = 512;
  v42 = 0;
  if ( *((_DWORD *)v24 + 9) )
  {
    v31 = NlpUtf8ToCutf8(
            (unsigned __int8 *)pvBuffer,
            (const char *)v24 + *((unsigned int *)v24 + 9),
            0,
            &v43,
            &v44,
            &v42,
            v48,
            v47);
    if ( v31 )
    {
      NlPrintRoutine(0x100u, L"Cannot pack DomainName into message %ld\n", v31);
      goto LABEL_6;
    }
    *((_DWORD *)pvBuffer + 1) |= 4u;
    v30 = v42;
    LODWORD(v26) = (_DWORD)v43;
  }
  if ( *((_DWORD *)v24 + 14) )
  {
    if ( v30 >= 0xA )
    {
      v32 = 122;
    }
    else
    {
      v32 = NlpUtf8ToCutf8(
              (unsigned __int8 *)pvBuffer,
              (const char *)v24 + *((unsigned int *)v24 + 14),
              0,
              &v43,
              &v44,
              &v42,
              v48,
              v47);
      if ( !v32 )
      {
        *((_DWORD *)pvBuffer + 1) |= 8u;
        v30 = v42;
        LODWORD(v26) = (_DWORD)v43;
        goto LABEL_32;
      }
    }
    NlPrintRoutine(0x100u, L"Cannot pack dns host name into message %ld\n", v32);
    goto LABEL_6;
  }
LABEL_32:
  if ( !*((_DWORD *)v24 + 13) )
    goto LABEL_36;
  if ( v30 >= 0xA )
  {
    v33 = 122;
    goto LABEL_41;
  }
  v33 = NlpUtf8ToCutf8(
          (unsigned __int8 *)pvBuffer,
          (const char *)v24 + *((unsigned int *)v24 + 12),
          1u,
          &v43,
          &v44,
          &v42,
          v48,
          v47);
  if ( v33 )
  {
LABEL_41:
    NlPrintRoutine(0x100u, L"Cannot pack UTF-8 netbios computer name into message %ld\n", v33);
    goto LABEL_6;
  }
  *((_DWORD *)pvBuffer + 1) |= 0x10u;
  LODWORD(v26) = (_DWORD)v43;
LABEL_36:
  v34 = AllocateContext(fContextReq, 0);
  v35 = v34;
  if ( v34 )
  {
    *((_DWORD *)v34 + 14) = 1;
    *((_BYTE *)v34 + 60) = 0;
    *(_OWORD *)((char *)v34 + 36) = *(_OWORD *)((char *)v24 + 8);
    v36 = *((_DWORD *)v24 + 6);
    v17 = 590610;
    *((_DWORD *)v35 + 13) = v36;
    p_dwLower = &v46->dwLower;
    v19->cbBuffer = (_DWORD)v26 - (_DWORD)pvBuffer;
    *p_dwLower = *(_OWORD *)v35;
    goto LABEL_50;
  }
  NlPrintRoutine(0x100u, L"InitializeSecurityContext: Cannot allocate context\n");
LABEL_4:
  v17 = -2146893056;
LABEL_51:
  NlPrintRoutine(0x80000u, L"InitializeSecurityContext: returns 0x%lx\n", v17);
  NlEndNetlogonCall();
  return v17;
}

```

## disassembly

```asm
0x180052a00  push    rbp
0x180052a02  push    rbx
0x180052a03  push    rsi
0x180052a04  push    rdi
0x180052a05  push    r12
0x180052a07  push    r13
0x180052a09  push    r14
0x180052a0b  push    r15
0x180052a0d  lea     rbp, [rsp-7]
0x180052a12  sub     rsp, 0E8h
0x180052a19  mov     rax, cs:__security_cookie
0x180052a20  xor     rax, rsp
0x180052a23  mov     [rbp+3Fh+var_48], rax
0x180052a27  mov     rax, [rbp+3Fh+phNewContext]
0x180052a2e  mov     rbx, rdx
0x180052a31  mov     r15, [rbp+3Fh+pInput]
0x180052a35  xor     edx, edx; Val
0x180052a37  mov     r14, [rbp+3Fh+pOutput]
0x180052a3e  mov     rsi, r8
0x180052a41  mov     r13, [rbp+3Fh+pfContextAttr]
0x180052a48  mov     rdi, rcx
0x180052a4b  mov     [rsp+120h+var_C0], rax
0x180052a50  lea     rcx, [rbp+3Fh+var_B0]; void *
0x180052a54  mov     rax, [rbp+3Fh+ptsExpiry]
0x180052a5b  lea     r8d, [rdx+50h]; Size
0x180052a5f  mov     r12d, r9d
0x180052a62  mov     [rsp+120h+var_C8], rax
0x180052a67  call    memset_0
0x180052a6c  mov     r8, rsi
0x180052a6f  lea     rdx, aInitializesecu_0; "InitializeSecurityContext: %ws: called"...
0x180052a76  mov     ecx, 80000h; unsigned int
0x180052a7b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052a80  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x180052a85  test    eax, eax
0x180052a87  jnz     short loc_180052A93
0x180052a89  mov     eax, 80090305h
0x180052a8e  jmp     loc_180052E70
0x180052a93  bt      r12d, 8
0x180052a98  jnb     short loc_180052AA4
0x180052a9a  mov     ebx, 80090300h
0x180052a9f  jmp     loc_180052E55
0x180052aa4  mov     edx, 0Ch; unsigned int
0x180052aa9  mov     rcx, r14; struct _SecBufferDesc *
0x180052aac  call    ?LocateBuffer@@YAPEAU_SecBuffer@@PEAU_SecBufferDesc@@K@Z; LocateBuffer(_SecBufferDesc *,ulong)
0x180052ab1  mov     r14, rax
0x180052ab4  test    rax, rax
0x180052ab7  jnz     short loc_180052AC3
0x180052ab9  mov     ebx, 80090308h
0x180052abe  jmp     loc_180052E55
0x180052ac3  cmp     dword ptr [rax], 22Ch
0x180052ac9  jnb     short loc_180052AD5
0x180052acb  mov     ebx, 80090321h
0x180052ad0  jmp     loc_180052E55
0x180052ad5  test    rbx, rbx
0x180052ad8  jnz     loc_180052DC3
0x180052ade  test    rdi, rdi
0x180052ae1  jnz     short loc_180052AED
0x180052ae3  mov     ebx, 8009030Dh
0x180052ae8  jmp     loc_180052E55
0x180052aed  mov     r9, [rdi]
0x180052af0  lea     rdx, aInitializesecu; "InitializeSecurityContext: %Ix.%Ix: %ws"...
0x180052af7  mov     r8, [rdi+8]
0x180052afb  mov     ecx, 80000h; unsigned int
0x180052b00  mov     [rsp+120h+var_100], rsi
0x180052b05  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052b0a  mov     eax, [rdi]
0x180052b0c  lea     r15, __ImageBase
0x180052b13  and     eax, 0Fh
0x180052b16  lea     rsi, rva ?NlGlobalSecPkgCritSect@@3PAU_SAFE_CRITICAL_SECTION@@A[r15]; _SAFE_CRITICAL_SECTION near * NlGlobalSecPkgCritSect ...
0x180052b1d  mov     ebx, eax
0x180052b1f  lea     rax, [rax+rax*2]
0x180052b23  shl     rax, 4
0x180052b27  add     rsi, rax
0x180052b2a  mov     rcx, rsi; CriticalSection
0x180052b2d  call    cs:__imp_RtlEnterCriticalSection
0x180052b33  mov     rbx, rva ?CredentialList@@3PAPEAU_NL_AUTH_CREDENTIAL@@A[r15+rbx*8]; _NL_AUTH_CREDENTIAL * near * CredentialList ...
0x180052b3b  xor     r15d, r15d
0x180052b3e  test    rbx, rbx
0x180052b41  jz      short loc_180052B5E
0x180052b43  mov     rdx, [rdi+8]
0x180052b47  cmp     [rbx+8], rdx
0x180052b4b  jnz     short loc_180052B55
0x180052b4d  mov     rax, [rdi]
0x180052b50  cmp     [rbx], rax
0x180052b53  jz      short loc_180052B5E
0x180052b55  mov     rbx, [rbx+10h]
0x180052b59  test    rbx, rbx
0x180052b5c  jnz     short loc_180052B47
0x180052b5e  mov     rcx, rsi; CriticalSection
0x180052b61  call    cs:__imp_RtlLeaveCriticalSection
0x180052b67  test    rbx, rbx
0x180052b6a  jz      loc_180052AE3
0x180052b70  mov     rbx, [rbx+20h]
0x180052b74  test    rbx, rbx
0x180052b77  jz      loc_180052AB9
0x180052b7d  cmp     dword ptr [rbx], 29120227h
0x180052b83  jz      short loc_180052B9E
0x180052b85  mov     r8d, 5B6h; unsigned int
0x180052b8b  lea     rdx, aOnecoreDsNetap_26; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180052b92  lea     rcx, aClientauthdata; "ClientAuthData->Signature == NL_AUTH_DA"...
0x180052b99  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180052b9e  mov     r8d, [r14]; Size
0x180052ba1  xor     edx, edx; Val
0x180052ba3  mov     rcx, [r14+8]; void *
0x180052ba7  call    memset_0
0x180052bac  mov     rdi, [r14+8]
0x180052bb0  mov     [rdi], r15
0x180052bb3  lea     rsi, [rdi+8]
0x180052bb7  mov     eax, [rbx+20h]
0x180052bba  mov     [rsp+120h+var_D8], rsi
0x180052bbf  test    eax, eax
0x180052bc1  jz      short loc_180052BEA
0x180052bc3  mov     r8d, [rbx+1Ch]
0x180052bc7  lea     edx, [rax+1]; SizeInBytes
0x180052bca  add     r8, rbx; Source
0x180052bcd  mov     rcx, rsi; Destination
0x180052bd0  call    cs:__imp_strcpy_s
0x180052bd6  mov     ecx, [rbx+20h]
0x180052bd9  inc     ecx
0x180052bdb  add     rcx, rsi
0x180052bde  or      dword ptr [rdi+4], 1
0x180052be2  mov     rsi, rcx
0x180052be5  mov     [rsp+120h+var_D8], rcx
0x180052bea  mov     eax, [rbx+2Ch]
0x180052bed  test    eax, eax
0x180052bef  jz      short loc_180052C15
0x180052bf1  mov     r8d, [rbx+28h]
0x180052bf5  lea     edx, [rax+1]; SizeInBytes
0x180052bf8  add     r8, rbx; Source
0x180052bfb  mov     rcx, rsi; Destination
0x180052bfe  call    cs:__imp_strcpy_s
0x180052c04  mov     eax, [rbx+2Ch]
0x180052c07  inc     eax
0x180052c09  add     rsi, rax
0x180052c0c  or      dword ptr [rdi+4], 2
0x180052c10  mov     [rsp+120h+var_D8], rsi
0x180052c15  mov     eax, r15d
0x180052c18  mov     [rsp+120h+var_D0], 200h
0x180052c20  mov     [rsp+120h+var_E0], eax
0x180052c24  cmp     [rbx+24h], r15d
0x180052c28  jz      short loc_180052C90
0x180052c2a  mov     edx, [rbx+24h]
0x180052c2d  lea     rax, [rbp+3Fh+var_B0]
0x180052c31  mov     [rsp+120h+var_E8], rax; char **
0x180052c36  lea     r9, [rsp+120h+var_D8]; unsigned __int8 **
0x180052c3b  lea     rax, [rbp+3Fh+var_60]
0x180052c3f  add     rdx, rbx; char *
0x180052c42  mov     [rsp+120h+var_F0], rax; unsigned __int16 *
0x180052c47  xor     r8d, r8d; unsigned __int8
0x180052c4a  lea     rax, [rsp+120h+var_E0]
0x180052c4f  mov     rcx, rdi; unsigned __int8 *
0x180052c52  mov     [rsp+120h+var_F8], rax; unsigned int *
0x180052c57  lea     rax, [rsp+120h+var_D0]
0x180052c5c  mov     [rsp+120h+var_100], rax; unsigned int *
0x180052c61  call    ?NlpUtf8ToCutf8@@YAKPEAEPEBDEPEAPEAEPEAK3PEAGPEAPEAD@Z; NlpUtf8ToCutf8(uchar *,char const *,uchar,uchar * *,ulong *,ulong *,ushort *,char * *)
0x180052c66  test    eax, eax
0x180052c68  jz      short loc_180052C83
0x180052c6a  lea     rdx, aCannotPackDoma; "Cannot pack DomainName into message %ld"...
0x180052c71  mov     r8d, eax
0x180052c74  mov     ecx, 100h; unsigned int
0x180052c79  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052c7e  jmp     loc_180052AB9
0x180052c83  or      dword ptr [rdi+4], 4
0x180052c87  mov     eax, [rsp+120h+var_E0]
0x180052c8b  mov     rsi, [rsp+120h+var_D8]
0x180052c90  cmp     [rbx+38h], r15d
0x180052c94  jz      short loc_180052CF0
0x180052c96  cmp     eax, 0Ah
0x180052c99  jnb     loc_180052D70
0x180052c9f  mov     edx, [rbx+38h]
0x180052ca2  lea     rax, [rbp+3Fh+var_B0]
0x180052ca6  mov     [rsp+120h+var_E8], rax; char **
0x180052cab  lea     r9, [rsp+120h+var_D8]; unsigned __int8 **
0x180052cb0  lea     rax, [rbp+3Fh+var_60]
0x180052cb4  add     rdx, rbx; char *
0x180052cb7  mov     [rsp+120h+var_F0], rax; unsigned __int16 *
0x180052cbc  xor     r8d, r8d; unsigned __int8
0x180052cbf  lea     rax, [rsp+120h+var_E0]
0x180052cc4  mov     rcx, rdi; unsigned __int8 *
0x180052cc7  mov     [rsp+120h+var_F8], rax; unsigned int *
0x180052ccc  lea     rax, [rsp+120h+var_D0]
0x180052cd1  mov     [rsp+120h+var_100], rax; unsigned int *
0x180052cd6  call    ?NlpUtf8ToCutf8@@YAKPEAEPEBDEPEAPEAEPEAK3PEAGPEAPEAD@Z; NlpUtf8ToCutf8(uchar *,char const *,uchar,uchar * *,ulong *,ulong *,ushort *,char * *)
0x180052cdb  test    eax, eax
0x180052cdd  jnz     loc_180052D75
0x180052ce3  or      dword ptr [rdi+4], 8
0x180052ce7  mov     eax, [rsp+120h+var_E0]
0x180052ceb  mov     rsi, [rsp+120h+var_D8]
0x180052cf0  cmp     [rbx+34h], r15d
0x180052cf4  jz      short loc_180052D48
0x180052cf6  cmp     eax, 0Ah
0x180052cf9  jnb     loc_180052D81
0x180052cff  mov     edx, [rbx+30h]
0x180052d02  lea     rax, [rbp+3Fh+var_B0]
0x180052d06  mov     [rsp+120h+var_E8], rax; char **
0x180052d0b  lea     r9, [rsp+120h+var_D8]; unsigned __int8 **
0x180052d10  lea     rax, [rbp+3Fh+var_60]
0x180052d14  add     rdx, rbx; char *
0x180052d17  mov     [rsp+120h+var_F0], rax; unsigned __int16 *
0x180052d1c  mov     r8b, 1; unsigned __int8
0x180052d1f  lea     rax, [rsp+120h+var_E0]
0x180052d24  mov     rcx, rdi; unsigned __int8 *
0x180052d27  mov     [rsp+120h+var_F8], rax; unsigned int *
0x180052d2c  lea     rax, [rsp+120h+var_D0]
0x180052d31  mov     [rsp+120h+var_100], rax; unsigned int *
0x180052d36  call    ?NlpUtf8ToCutf8@@YAKPEAEPEBDEPEAPEAEPEAK3PEAGPEAPEAD@Z; NlpUtf8ToCutf8(uchar *,char const *,uchar,uchar * *,ulong *,ulong *,ushort *,char * *)
0x180052d3b  test    eax, eax
0x180052d3d  jnz     short loc_180052D86
0x180052d3f  or      dword ptr [rdi+4], 10h
0x180052d43  mov     rsi, [rsp+120h+var_D8]
0x180052d48  xor     edx, edx; struct _UNICODE_STRING *
0x180052d4a  mov     ecx, r12d; unsigned int
0x180052d4d  call    ?AllocateContext@@YAPEAU_NL_AUTH_CONTEXT@@KPEAU_UNICODE_STRING@@@Z; AllocateContext(ulong,_UNICODE_STRING *)
0x180052d52  mov     rcx, rax
0x180052d55  test    rax, rax
0x180052d58  jnz     short loc_180052D92
0x180052d5a  lea     rdx, aInitializesecu_1; "InitializeSecurityContext: Cannot alloc"...
0x180052d61  mov     ecx, 100h; unsigned int
0x180052d66  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052d6b  jmp     loc_180052A9A
0x180052d70  mov     eax, 7Ah ; 'z'
0x180052d75  lea     rdx, aCannotPackDnsH; "Cannot pack dns host name into message "...
0x180052d7c  jmp     loc_180052C71
0x180052d81  mov     eax, 7Ah ; 'z'
0x180052d86  lea     rdx, aCannotPackUtf8; "Cannot pack UTF-8 netbios computer name"...
0x180052d8d  jmp     loc_180052C71
0x180052d92  mov     dword ptr [rax+38h], 1
0x180052d99  sub     esi, edi
0x180052d9b  mov     [rax+3Ch], r15b
0x180052d9f  movups  xmm0, xmmword ptr [rbx+8]
0x180052da3  movups  xmmword ptr [rax+24h], xmm0
0x180052da7  mov     eax, [rbx+18h]
0x180052daa  mov     ebx, 90312h
0x180052daf  mov     [rcx+34h], eax
0x180052db2  mov     rax, [rsp+120h+var_C0]
0x180052db7  mov     [r14], esi
0x180052dba  movups  xmm0, xmmword ptr [rcx]
0x180052dbd  movdqu  xmmword ptr [rax], xmm0
0x180052dc1  jmp     short loc_180052E42
0x180052dc3  mov     r9, [rbx]
0x180052dc6  lea     rdx, aInitializesecu_2; "InitializeSecurityContext: %Ix.%Ix: %ws"...
0x180052dcd  mov     r8, [rbx+8]
0x180052dd1  mov     ecx, 80000h; unsigned int
0x180052dd6  mov     [rsp+120h+var_100], rsi
0x180052ddb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052de0  mov     rcx, rbx; struct _SecHandle *
0x180052de3  call    ?LocateContext@@YAPEAU_NL_AUTH_CONTEXT@@PEAU_SecHandle@@@Z; LocateContext(_SecHandle *)
0x180052de8  mov     r9, rax
0x180052deb  test    rax, rax
0x180052dee  jnz     short loc_180052DF7
0x180052df0  mov     ebx, 80090301h
0x180052df5  jmp     short loc_180052E55
0x180052df7  cmp     dword ptr [rax+38h], 1
0x180052dfb  jnz     short loc_180052DF0
0x180052dfd  mov     edx, 0Ch; unsigned int
0x180052e02  mov     rcx, r15; struct _SecBufferDesc *
0x180052e05  call    ?LocateBuffer@@YAPEAU_SecBuffer@@PEAU_SecBufferDesc@@K@Z; LocateBuffer(_SecBufferDesc *,ulong)
0x180052e0a  test    rax, rax
0x180052e0d  jz      loc_180052AB9
0x180052e13  cmp     dword ptr [rax], 0Ch
0x180052e16  jb      loc_180052AB9
0x180052e1c  mov     rax, [rax+8]
0x180052e20  cmp     dword ptr [rax], 1
0x180052e23  jnz     loc_180052AB9
0x180052e29  mov     dword ptr [r9+38h], 3
0x180052e31  xor     ebx, ebx
0x180052e33  mov     qword ptr [r9+18h], 0
0x180052e3b  mov     dword ptr [r14], 0
0x180052e42  mov     rcx, [rsp+120h+var_C8]
0x180052e47  mov     rax, cs:?Forever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER Forever
0x180052e4e  mov     [r13+0], r12d
0x180052e52  mov     [rcx], rax
0x180052e55  mov     r8d, ebx
0x180052e58  lea     rdx, aInitializesecu_3; "InitializeSecurityContext: returns 0x%l"...
0x180052e5f  mov     ecx, 80000h; unsigned int
0x180052e64  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052e69  call    ?NlEndNetlogonCall@@YAXXZ; NlEndNetlogonCall(void)
0x180052e6e  mov     eax, ebx
0x180052e70  mov     rcx, [rbp+3Fh+var_48]
0x180052e74  xor     rcx, rsp; StackCookie
0x180052e77  call    __security_check_cookie
0x180052e7c  add     rsp, 0E8h
0x180052e83  pop     r15
0x180052e85  pop     r14
0x180052e87  pop     r13
0x180052e89  pop     r12
0x180052e8b  pop     rdi
0x180052e8c  pop     rsi
0x180052e8d  pop     rbx
0x180052e8e  pop     rbp
0x180052e8f  retn
```
