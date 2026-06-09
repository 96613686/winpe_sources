# AcceptSecurityContext

- ea: `0x180055a50`
- end: `0x180056145`
- name: `AcceptSecurityContext`
- size: `1781`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, PSecBufferDesc pInput, unsigned int fContextReq, unsigned int TargetDataRep, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800037f0`
- `0x180007518`
- `0x18000d444`
- `0x18000d854`
- `0x18000d8d4`
- `0x18000dd00`
- `0x18000e910`
- `0x18000f3e4`
- `0x1800267ec`
- `0x180026fdc`
- `0x180027350`
- `0x180054e28`
- `0x180055a50`
- `0x180057174`
- `0x18007d518`
- `0x180088fe8`
- `0x18008a070`
- `0x18008b8a0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180055ef4`
- `ntdll!RtlLeaveCriticalSection` at `0x180055f2f`
- `ntdll!RtlLeaveCriticalSection` at `0x180055f8b`
- `ntdll!RtlLeaveCriticalSection` at `0x180055ef4`
- `ntdll!RtlLeaveCriticalSection` at `0x180055f2f`
- `ntdll!RtlLeaveCriticalSection` at `0x180055f8b`
- `ntdll!RtlEnterCriticalSection` at `0x180055ed2`
- `ntdll!RtlEnterCriticalSection` at `0x180055ed2`
- `netutils!NetApiBufferFree` at `0x1800560c1`
- `netutils!NetApiBufferFree` at `0x1800560d9`
- `netutils!NetApiBufferFree` at `0x1800560c1`
- `netutils!NetApiBufferFree` at `0x1800560d9`

## string_xrefs

- `0x180056042`: `onecore\ds\netapi\svcdlls\logonsrv\server\secpkg.cxx`
- `0x180055a8a`: `AcceptSecurityContext: called\n`
- `0x180055bc8`: `AcceptSecurityContext: %Ix.%Ix: cannot get netbios domain name\n`
- `0x180055c18`: `AcceptSecurityContext: %Ix.%Ix: Cannot parse computer name\n`
- `0x180055c3f`: `AcceptSecurityContext: %Ix.%Ix: DNS domain bad.\n`
- `0x180055c67`: `AcceptSecurityContext: %Ix.%Ix: DNS hostname bad.\n`
- `0x180055c83`: `AcceptSecurityContext: %Ix.%Ix: both DNS '%hs' and Netbios '%hs' client name specified\n`
- `0x180055cca`: `AcceptSecurityContext: %Ix.%Ix: UTF8 computer name bad.\n`
- `0x180055d1f`: `AcceptSecurityContext: %Ix.%Ix: Cannot find domain %hs\n`
- `0x180055d42`: `AcceptSecurityContext: %Ix.%Ix: Neither DNS or netbios domain name specified (fatal)\n`
- `0x180055d6a`: `AcceptSecurityContext: %Ix.%Ix: Cannot alloc domain name %hs\n`
- `0x180055da6`: `AcceptSecurityContext: %Ix.%Ix: Cannot find domain %ws (fatal)\n`
- `0x180055df6`: `AcceptSecurityContext: %Ix.%Ix: Cannot alloc DNS computer name %hs\n`
- `0x180055e59`: `AcceptSecurityContext: %Ix.%Ix: Cannot alloc utf8 computer name %hs\n`
- `0x180055ea3`: `AcceptSecurityContext: %Ix.%Ix: Cannot alloc oem computer name %hs\n`
- `0x18005600b`: `AcceptSecurityContext: %Ix.%Ix: Don't know client computer name.\n`
- `0x180055eb7`: `AcceptSecurityContext: %Ix.%Ix: from %ws\n`
- `0x180055f00`: `AcceptSecurityContext: %Ix.%Ix: Can't NlFindNamedServerSession for %ws\n`
- `0x180055f3b`: `AcceptSecurityContext: %Ix.%Ix: Secure channel doesn't exist for %ws\n`
- `0x180055f5c`: `AcceptSecurityContext: %Ix.%Ix: Secure channel has been established with Kerberos for %ws\n`
- `0x180056055`: `AcceptSecurityContext: Second accept called.\n`
- `0x180056100`: `AcceptSecurityContext: %Ix.%Ix: returns 0x%lx\n`

## pseudocode

```c
SECURITY_STATUS __stdcall AcceptSecurityContext(
        PCredHandle phCredential,
        PCtxtHandle phContext,
        PSecBufferDesc pInput,
        unsigned int fContextReq,
        unsigned int TargetDataRep,
        PCtxtHandle phNewContext,
        PSecBufferDesc pOutput,
        unsigned int *pfContextAttr,
        PTimeStamp ptsExpiry)
{
  LPCCH v12; // r12
  unsigned __int16 *v13; // r13
  unsigned __int16 *v15; // r14
  __int64 v16; // r9
  SECURITY_STATUS v17; // ebx
  ULONG_PTR dwLower; // r15
  ULONG_PTR dwUpper; // rdi
  unsigned int v20; // r11d
  struct _SecBuffer *v21; // r12
  unsigned int v22; // r11d
  _BYTE *pvBuffer; // rsi
  bool v24; // zf
  const char *v25; // r15
  char *v26; // rsi
  struct _DOMAIN_INFO *v27; // r13
  void *v28; // rax
  void *v29; // rsi
  LPCCH v30; // rsi
  struct _SERVER_SESSION *NamedServerSession; // rax
  struct _UNICODE_STRING *v32; // rsi
  int v33; // r12d
  __int128 v34; // xmm6
  struct _UNICODE_STRING *v35; // rdx
  unsigned int v36; // esi
  struct _NL_AUTH_CONTEXT *Context; // rbx
  struct _SecBuffer *v38; // rdi
  _BYTE *v39; // rax
  union _LARGE_INTEGER *v40; // rcx
  PCtxtHandle v41; // rax
  struct _SecHandle v42; // xmm0
  char *v43; // rax
  unsigned __int16 **v44; // [rsp+28h] [rbp-B9h]
  LPCCH v45; // [rsp+40h] [rbp-A1h] BYREF
  LPCCH lpMultiByteStr; // [rsp+48h] [rbp-99h] BYREF
  ULONG_PTR v47; // [rsp+50h] [rbp-91h]
  PCSZ SourceString; // [rsp+58h] [rbp-89h] BYREF
  unsigned int v49; // [rsp+60h] [rbp-81h]
  char *v50; // [rsp+68h] [rbp-79h] BYREF
  unsigned __int16 *v51; // [rsp+70h] [rbp-71h] BYREF
  char *v52; // [rsp+78h] [rbp-69h] BYREF
  struct _DOMAIN_INFO *DnsDomain; // [rsp+80h] [rbp-61h]
  LPVOID Buffer; // [rsp+88h] [rbp-59h]
  struct _SecBuffer *v55; // [rsp+90h] [rbp-51h]
  PCtxtHandle v56; // [rsp+98h] [rbp-49h]
  unsigned int *v57; // [rsp+A0h] [rbp-41h]
  PTimeStamp v58; // [rsp+A8h] [rbp-39h]
  char v59; // [rsp+B0h] [rbp-31h] BYREF

  v56 = phNewContext;
  v57 = pfContextAttr;
  v58 = ptsExpiry;
  v52 = 0;
  v12 = 0;
  lpMultiByteStr = 0;
  v13 = 0;
  v45 = 0;
  v51 = 0;
  SourceString = 0;
  v49 = fContextReq;
  NlPrintRoutine(0x80000u, L"AcceptSecurityContext: called\n");
  if ( !(unsigned int)NlStartNetlogonCall() )
    return -2146893051;
  v15 = 0;
  Buffer = 0;
  DnsDomain = 0;
  v16 = 16;
  if ( (v49 & 0x100) == 0 )
  {
    v21 = LocateBuffer(pInput, 0xCu);
    if ( v21 )
    {
      v55 = LocateBuffer(pOutput, v20);
      if ( v55 )
      {
        if ( !phContext )
        {
          if ( !phCredential || (dwUpper = phCredential->dwUpper, dwUpper != 4278124286) || phCredential->dwLower )
          {
            v17 = -2146893043;
            dwLower = 0;
            dwUpper = 0;
            goto LABEL_72;
          }
          dwLower = 0;
          v47 = 0;
          if ( v21->cbBuffer < v22 )
            goto LABEL_71;
          pvBuffer = v21->pvBuffer;
          if ( *(_DWORD *)pvBuffer )
            goto LABEL_71;
          v24 = (pvBuffer[4] & 1) == 0;
          v50 = pvBuffer + 8;
          if ( !v24 )
          {
            if ( !(unsigned int)NetpLogonGetOemString(
                                  (_DWORD)pvBuffer,
                                  v21->cbBuffer,
                                  (unsigned int)&v50,
                                  v16,
                                  (__int64)&v51) )
            {
              NlPrintRoutine(
                0x100u,
                L"AcceptSecurityContext: %Ix.%Ix: cannot get netbios domain name\n",
                4278124286LL,
                0);
LABEL_16:
              v16 = 16;
LABEL_71:
              v17 = -2146893048;
              goto LABEL_72;
            }
            v13 = v51;
            LODWORD(v16) = 16;
          }
          if ( (pvBuffer[4] & 2) != 0
            && !(unsigned int)NetpLogonGetOemString(
                                (_DWORD)pvBuffer,
                                v21->cbBuffer,
                                (unsigned int)&v50,
                                v16,
                                (__int64)&SourceString) )
          {
            NlPrintRoutine(0x100u, L"AcceptSecurityContext: %Ix.%Ix: Cannot parse computer name\n", 4278124286LL, 0);
            goto LABEL_16;
          }
          if ( (pvBuffer[4] & 4) != 0 && !(unsigned int)NetpLogonGetCutf8String(pvBuffer, v21->cbBuffer, &v50, &v52) )
          {
            NlPrintRoutine(0x100u, L"AcceptSecurityContext: %Ix.%Ix: DNS domain bad.\n", 4278124286LL, 0);
            goto LABEL_16;
          }
          if ( (pvBuffer[4] & 8) != 0 )
          {
            if ( !(unsigned int)NetpLogonGetCutf8String(pvBuffer, v21->cbBuffer, &v50, (char **)&lpMultiByteStr) )
            {
              NlPrintRoutine(0x100u, L"AcceptSecurityContext: %Ix.%Ix: DNS hostname bad.\n", 4278124286LL, 0);
              goto LABEL_16;
            }
            v25 = SourceString;
            if ( (pvBuffer[4] & 2) != 0 )
              NlPrintRoutine(
                0x100u,
                L"AcceptSecurityContext: %Ix.%Ix: both DNS '%hs' and Netbios '%hs' client name specified\n",
                4278124286LL,
                0,
                lpMultiByteStr,
                SourceString);
          }
          else
          {
            v25 = SourceString;
          }
          if ( (pvBuffer[4] & 0x10) != 0
            && !(unsigned int)NetpLogonGetCutf8String(pvBuffer, v21->cbBuffer, &v50, (char **)&v45) )
          {
            NlPrintRoutine(0x100u, L"AcceptSecurityContext: %Ix.%Ix: UTF8 computer name bad.\n", 4278124286LL, 0);
LABEL_33:
            dwLower = v47;
            v16 = 16;
            goto LABEL_71;
          }
          v26 = v52;
          if ( v52 )
          {
            DnsDomain = NlFindDnsDomain(v52, 0, 0, 1u, 0);
            v27 = DnsDomain;
            if ( !DnsDomain )
            {
              NlPrintRoutine(0x100u, L"AcceptSecurityContext: %Ix.%Ix: Cannot find domain %hs\n", 4278124286LL, 0, v26);
              goto LABEL_33;
            }
          }
          else
          {
            if ( !v13 )
            {
              NlPrintRoutine(
                0x100u,
                L"AcceptSecurityContext: %Ix.%Ix: Neither DNS or netbios domain name specified (fatal)\n",
                4278124286LL,
                0);
              goto LABEL_33;
            }
            v28 = (void *)NetpAllocWStrFromStr((PCSZ)v13);
            Buffer = v28;
            v29 = v28;
            if ( !v28 )
            {
              NlPrintRoutine(
                0x100u,
                L"AcceptSecurityContext: %Ix.%Ix: Cannot alloc domain name %hs\n",
                4278124286LL,
                0,
                v13);
              goto LABEL_42;
            }
            DnsDomain = NlFindNetbiosDomain((PCWSTR)v28, 0);
            v27 = DnsDomain;
            if ( !DnsDomain )
            {
              NlPrintRoutine(
                0x100u,
                L"AcceptSecurityContext: %Ix.%Ix: Cannot find domain %ws (fatal)\n",
                4278124286LL,
                0,
                v29);
              goto LABEL_33;
            }
          }
          v12 = lpMultiByteStr;
          if ( lpMultiByteStr )
          {
            v51 = 0;
            if ( NetpAllocWStrFromUtf8StrAsRequired(lpMultiByteStr, 0xFFFFFFFF, 0, 0, &v51) || (v15 = v51) == 0 )
            {
              NlPrintRoutine(
                0x100u,
                L"AcceptSecurityContext: %Ix.%Ix: Cannot alloc DNS computer name %hs\n",
                4278124286LL,
                0,
                v12);
              v17 = -2146893056;
LABEL_49:
              dwLower = v47;
              v16 = 16;
              goto LABEL_73;
            }
LABEL_58:
            NlPrintRoutine(0x80000u, L"AcceptSecurityContext: %Ix.%Ix: from %ws\n", 4278124286LL, 0, v15);
            RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v27 + 504));
            NamedServerSession = NlFindNamedServerSession(v27, v15);
            v32 = (struct _UNICODE_STRING *)NamedServerSession;
            if ( !NamedServerSession )
            {
              RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v27 + 504));
              NlPrintRoutine(
                0x100u,
                L"AcceptSecurityContext: %Ix.%Ix: Can't NlFindNamedServerSession for %ws\n",
                4278124286LL,
                0,
                v15);
LABEL_60:
              v17 = -2146893048;
              goto LABEL_49;
            }
            if ( !*((_DWORD *)NamedServerSession + 8) )
            {
              RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v27 + 504));
              NlPrintRoutine(
                0x100u,
                L"AcceptSecurityContext: %Ix.%Ix: Secure channel doesn't exist for %ws\n",
                4278124286LL,
                0,
                v15);
              goto LABEL_60;
            }
            v33 = *((_DWORD *)NamedServerSession + 18);
            v34 = *((_OWORD *)NamedServerSession + 6);
            if ( v33 < 0 )
              NlPrintRoutine(
                0x100u,
                L"AcceptSecurityContext: %Ix.%Ix: Secure channel has been established with Kerberos for %ws\n",
                4278124286LL,
                0,
                v15);
            v35 = v32 + 10;
            v32[4].Length = 0;
            v36 = v49;
            Context = AllocateContext(v49, v35);
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v27 + 504));
            if ( Context )
            {
              v38 = v55;
              *(_OWORD *)((char *)Context + 36) = v34;
              *((_DWORD *)Context + 14) = 2;
              *((_BYTE *)Context + 60) = 1;
              *((_DWORD *)Context + 13) = v33;
              memset_0(v38->pvBuffer, 0, v38->cbBuffer);
              v39 = v38->pvBuffer;
              v40 = v58;
              *(_QWORD *)v39 = 1;
              v39[8] = 0;
              v41 = v56;
              v38->cbBuffer = 12;
              v42 = *(struct _SecHandle *)Context;
              v17 = 0;
              *v41 = v42;
              dwLower = v41->dwLower;
              dwUpper = v41->dwUpper;
              v16 = 16;
              *v57 = v36;
              *v40 = Forever;
              goto LABEL_72;
            }
LABEL_42:
            dwLower = v47;
            v17 = -2146893056;
            v16 = 16;
LABEL_72:
            v12 = lpMultiByteStr;
            goto LABEL_73;
          }
          v30 = v45;
          if ( v45 )
          {
            SourceString = 0;
            if ( !NetpAllocWStrFromUtf8StrAsRequired(v45, 0xFFFFFFFF, 0, 0, (unsigned __int16 **)&SourceString) )
            {
              v15 = (unsigned __int16 *)SourceString;
              if ( SourceString )
                goto LABEL_58;
            }
            NlPrintRoutine(
              0x100u,
              L"AcceptSecurityContext: %Ix.%Ix: Cannot alloc utf8 computer name %hs\n",
              4278124286LL,
              0,
              v30);
          }
          else
          {
            if ( !v25 )
            {
              dwLower = 0;
              NlPrintRoutine(
                0x100u,
                L"AcceptSecurityContext: %Ix.%Ix: Don't know client computer name.\n",
                4278124286LL,
                0);
              v16 = 16;
              v17 = -2146893048;
              goto LABEL_74;
            }
            v15 = (unsigned __int16 *)NetpAllocWStrFromStr(v25);
            if ( v15 )
              goto LABEL_58;
            NlPrintRoutine(
              0x100u,
              L"AcceptSecurityContext: %Ix.%Ix: Cannot alloc oem computer name %hs\n",
              4278124286LL,
              0,
              v25);
          }
          dwLower = v47;
          v16 = 16;
          v17 = -2146893056;
          goto LABEL_74;
        }
        NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\secpkg.cxx", 0x8C6u, (char *)v16);
        NlPrintRoutine(0x100u, L"AcceptSecurityContext: Second accept called.\n");
        v16 = 16;
      }
    }
    dwLower = 0;
    dwUpper = 0;
    goto LABEL_71;
  }
  v17 = -2146893056;
  dwLower = 0;
  dwUpper = 0;
LABEL_73:
  v30 = v45;
LABEL_74:
  v43 = &v59;
  do
  {
    *v43++ = 0;
    --v16;
  }
  while ( v16 );
  if ( v52 )
    NetpMemoryFree(v52);
  if ( v12 )
    NetpMemoryFree(v12);
  if ( v30 )
    NetpMemoryFree(v30);
  if ( v15 )
    NetApiBufferFree(v15);
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( DnsDomain )
    NlDereferenceDomain(DnsDomain);
  LODWORD(v44) = v17;
  NlPrintRoutine(0x80000u, L"AcceptSecurityContext: %Ix.%Ix: returns 0x%lx\n", dwUpper, dwLower, v44);
  NlEndNetlogonCall();
  return v17;
}

```

## disassembly

```asm
0x180055a50  mov     rax, rsp
0x180055a53  mov     [rax+10h], rbx
0x180055a57  push    rbp
0x180055a58  push    rsi
0x180055a59  push    rdi
0x180055a5a  push    r12
0x180055a5c  push    r13
0x180055a5e  push    r14
0x180055a60  push    r15
0x180055a62  lea     rbp, [rax-3Fh]
0x180055a66  sub     rsp, 0E0h
0x180055a6d  movaps  xmmword ptr [rax-48h], xmm6
0x180055a71  mov     rax, cs:__security_cookie
0x180055a78  xor     rax, rsp
0x180055a7b  mov     [rbp+37h+var_50], rax
0x180055a7f  mov     rax, [rbp+37h+phNewContext]
0x180055a83  mov     rsi, rdx
0x180055a86  mov     r15, [rbp+37h+pOutput]
0x180055a8a  lea     rdx, aAcceptsecurity_10; "AcceptSecurityContext: called\n"
0x180055a91  mov     [rbp+37h+var_80], rax
0x180055a95  mov     rbx, rcx
0x180055a98  mov     rax, [rbp+37h+pfContextAttr]
0x180055a9c  mov     ecx, 80000h; unsigned int
0x180055aa1  mov     [rbp+37h+var_78], rax
0x180055aa5  mov     rdi, r8
0x180055aa8  mov     rax, [rbp+37h+ptsExpiry]
0x180055aaf  mov     [rbp+37h+var_70], rax
0x180055ab3  xor     eax, eax
0x180055ab5  mov     [rbp+37h+var_A0], rax
0x180055ab9  mov     r12d, eax
0x180055abc  mov     [rsp+110h+lpMultiByteStr], rax
0x180055ac1  mov     r13d, eax
0x180055ac4  mov     [rsp+110h+var_D8], rax
0x180055ac9  mov     [rbp+37h+var_A8], rax
0x180055acd  mov     [rsp+110h+SourceString], rax
0x180055ad2  mov     [rsp+110h+var_B8], r9d
0x180055ad7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180055adc  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x180055ae1  test    eax, eax
0x180055ae3  jnz     short loc_180055AEF
0x180055ae5  mov     eax, 80090305h
0x180055aea  jmp     loc_180056118
0x180055aef  xor     r14d, r14d
0x180055af2  mov     [rbp+37h+Buffer], r12
0x180055af6  test    [rsp+110h+var_B8], 100h
0x180055afe  mov     [rbp+37h+var_98], r12
0x180055b02  lea     r9d, [r14+10h]
0x180055b06  jz      short loc_180055B18
0x180055b08  mov     ebx, 80090300h
0x180055b0d  mov     r15, r12
0x180055b10  mov     rdi, r12
0x180055b13  jmp     loc_18005607C
0x180055b18  mov     r11d, 0Ch
0x180055b1e  mov     rcx, rdi; struct _SecBufferDesc *
0x180055b21  mov     edx, r11d; unsigned int
0x180055b24  call    ?LocateBuffer@@YAPEAU_SecBuffer@@PEAU_SecBufferDesc@@K@Z; LocateBuffer(_SecBufferDesc *,ulong)
0x180055b29  mov     r12, rax
0x180055b2c  test    rax, rax
0x180055b2f  jz      loc_18005606C
0x180055b35  mov     edx, r11d; unsigned int
0x180055b38  mov     rcx, r15; struct _SecBufferDesc *
0x180055b3b  call    ?LocateBuffer@@YAPEAU_SecBuffer@@PEAU_SecBufferDesc@@K@Z; LocateBuffer(_SecBufferDesc *,ulong)
0x180055b40  mov     [rbp+37h+var_88], rax
0x180055b44  test    rax, rax
0x180055b47  jz      loc_18005606C
0x180055b4d  test    rsi, rsi
0x180055b50  jnz     loc_18005603C
0x180055b56  test    rbx, rbx
0x180055b59  jz      loc_18005602F
0x180055b5f  mov     rdi, [rbx+8]
0x180055b63  mov     eax, 0FEFEFEFEh
0x180055b68  cmp     rdi, rax
0x180055b6b  jnz     loc_18005602F
0x180055b71  mov     rbx, [rbx]
0x180055b74  test    rbx, rbx
0x180055b77  jnz     loc_18005602F
0x180055b7d  mov     r15, rbx
0x180055b80  mov     [rsp+110h+var_C8], rbx
0x180055b85  cmp     [r12], r11d
0x180055b89  jb      loc_180056072
0x180055b8f  mov     rsi, [r12+8]
0x180055b94  cmp     [rsi], r13d
0x180055b97  jnz     loc_180056072
0x180055b9d  test    byte ptr [rsi+4], 1
0x180055ba1  lea     rax, [rsi+8]
0x180055ba5  mov     [rbp+37h+var_B0], rax
0x180055ba9  jz      short loc_180055BF4
0x180055bab  mov     edx, [r12]
0x180055baf  lea     rax, [rbp+37h+var_A8]
0x180055bb3  lea     r8, [rbp+37h+var_B0]
0x180055bb7  mov     [rsp+110h+var_F0], rax
0x180055bbc  mov     rcx, rsi
0x180055bbf  call    NetpLogonGetOemString
0x180055bc4  test    eax, eax
0x180055bc6  jnz     short loc_180055BEA
0x180055bc8  lea     rdx, aAcceptsecurity_1; "AcceptSecurityContext: %Ix.%Ix: cannot "...
0x180055bcf  mov     r8, rdi
0x180055bd2  mov     r9, rbx
0x180055bd5  mov     ecx, 100h; unsigned int
0x180055bda  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180055bdf  mov     r9d, 10h
0x180055be5  jmp     loc_180056072
0x180055bea  mov     r13, [rbp+37h+var_A8]
0x180055bee  mov     r9d, 10h
0x180055bf4  test    byte ptr [rsi+4], 2
0x180055bf8  jz      short loc_180055C21
0x180055bfa  mov     edx, [r12]
0x180055bfe  lea     rax, [rsp+110h+SourceString]
0x180055c03  lea     r8, [rbp+37h+var_B0]
0x180055c07  mov     [rsp+110h+var_F0], rax
0x180055c0c  mov     rcx, rsi
0x180055c0f  call    NetpLogonGetOemString
0x180055c14  test    eax, eax
0x180055c16  jnz     short loc_180055C21
0x180055c18  lea     rdx, aAcceptsecurity_18; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x180055c1f  jmp     short loc_180055BCF
0x180055c21  test    byte ptr [rsi+4], 4
0x180055c25  jz      short loc_180055C48
0x180055c27  mov     edx, [r12]; unsigned int
0x180055c2b  lea     r9, [rbp+37h+var_A0]; char **
0x180055c2f  lea     r8, [rbp+37h+var_B0]; char **
0x180055c33  mov     rcx, rsi; void *
0x180055c36  call    ?NetpLogonGetCutf8String@@YAHPEAXKPEAPEAD1@Z; NetpLogonGetCutf8String(void *,ulong,char * *,char * *)
0x180055c3b  test    eax, eax
0x180055c3d  jnz     short loc_180055C48
0x180055c3f  lea     rdx, aAcceptsecurity_19; "AcceptSecurityContext: %Ix.%Ix: DNS dom"...
0x180055c46  jmp     short loc_180055BCF
0x180055c48  test    byte ptr [rsi+4], 8
0x180055c4c  jz      short loc_180055CA6
0x180055c4e  mov     edx, [r12]; unsigned int
0x180055c52  lea     r9, [rsp+110h+lpMultiByteStr]; char **
0x180055c57  lea     r8, [rbp+37h+var_B0]; char **
0x180055c5b  mov     rcx, rsi; void *
0x180055c5e  call    ?NetpLogonGetCutf8String@@YAHPEAXKPEAPEAD1@Z; NetpLogonGetCutf8String(void *,ulong,char * *,char * *)
0x180055c63  test    eax, eax
0x180055c65  jnz     short loc_180055C73
0x180055c67  lea     rdx, aAcceptsecurity_3; "AcceptSecurityContext: %Ix.%Ix: DNS hos"...
0x180055c6e  jmp     loc_180055BCF
0x180055c73  test    byte ptr [rsi+4], 2
0x180055c77  mov     r15, [rsp+110h+SourceString]
0x180055c7c  jz      short loc_180055CAB
0x180055c7e  mov     rax, [rsp+110h+lpMultiByteStr]
0x180055c83  lea     rdx, aAcceptsecurity_2; "AcceptSecurityContext: %Ix.%Ix: both DN"...
0x180055c8a  mov     [rsp+110h+var_E8], r15
0x180055c8f  mov     r9, rbx
0x180055c92  mov     r8, rdi
0x180055c95  mov     [rsp+110h+var_F0], rax
0x180055c9a  mov     ecx, 100h; unsigned int
0x180055c9f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180055ca4  jmp     short loc_180055CAB
0x180055ca6  mov     r15, [rsp+110h+SourceString]
0x180055cab  test    byte ptr [rsi+4], 10h
0x180055caf  jz      short loc_180055CF1
0x180055cb1  mov     edx, [r12]; unsigned int
0x180055cb5  lea     r9, [rsp+110h+var_D8]; char **
0x180055cba  lea     r8, [rbp+37h+var_B0]; char **
0x180055cbe  mov     rcx, rsi; void *
0x180055cc1  call    ?NetpLogonGetCutf8String@@YAHPEAXKPEAPEAD1@Z; NetpLogonGetCutf8String(void *,ulong,char * *,char * *)
0x180055cc6  test    eax, eax
0x180055cc8  jnz     short loc_180055CF1
0x180055cca  lea     rdx, aAcceptsecurity_15; "AcceptSecurityContext: %Ix.%Ix: UTF8 co"...
0x180055cd1  mov     r8, rdi
0x180055cd4  mov     r9, rbx
0x180055cd7  mov     ecx, 100h; unsigned int
0x180055cdc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180055ce1  mov     r15, [rsp+110h+var_C8]
0x180055ce6  mov     r9d, 10h
0x180055cec  jmp     loc_180056072
0x180055cf1  mov     rsi, [rbp+37h+var_A0]
0x180055cf5  test    rsi, rsi
0x180055cf8  jz      short loc_180055D3D
0x180055cfa  mov     r9b, 1; unsigned __int8
0x180055cfd  mov     [rsp+110h+var_F0], r14; unsigned __int8 *
0x180055d02  xor     r8d, r8d; unsigned __int8
0x180055d05  xor     edx, edx; Buf1
0x180055d07  mov     rcx, rsi; char *
0x180055d0a  call    ?NlFindDnsDomain@@YAPEAU_DOMAIN_INFO@@PEBDPEAU_GUID@@EEPEAE@Z; NlFindDnsDomain(char const *,_GUID *,uchar,uchar,uchar *)
0x180055d0f  mov     [rbp+37h+var_98], rax
0x180055d13  mov     r13, rax
0x180055d16  test    rax, rax
0x180055d19  jnz     loc_180055DB2
0x180055d1f  lea     rdx, aAcceptsecurity_4; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x180055d26  mov     r8, rdi
0x180055d29  mov     [rsp+110h+var_F0], rsi
0x180055d2e  mov     r9, rbx
0x180055d31  mov     ecx, 100h; unsigned int
0x180055d36  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180055d3b  jmp     short loc_180055CE1
0x180055d3d  test    r13, r13
0x180055d40  jnz     short loc_180055D4B
0x180055d42  lea     rdx, aAcceptsecurity_16; "AcceptSecurityContext: %Ix.%Ix: Neither"...
0x180055d49  jmp     short loc_180055CD1
0x180055d4b  mov     rcx, r13; SourceString
0x180055d4e  call    NetpAllocWStrFromStr
0x180055d53  mov     [rbp+37h+Buffer], rax
0x180055d57  mov     rsi, rax
0x180055d5a  test    rax, rax
0x180055d5d  jnz     short loc_180055D90
0x180055d5f  mov     r9, rbx
0x180055d62  mov     [rsp+110h+var_F0], r13
0x180055d67  mov     r8, rdi
0x180055d6a  lea     rdx, aAcceptsecurity_14; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x180055d71  mov     ecx, 100h; unsigned int
0x180055d76  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180055d7b  mov     r15, [rsp+110h+var_C8]
0x180055d80  mov     ebx, 80090300h
0x180055d85  mov     r9d, 10h
0x180055d8b  jmp     loc_180056077
0x180055d90  xor     edx, edx; unsigned __int8
0x180055d92  mov     rcx, rsi; SourceString
0x180055d95  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x180055d9a  mov     [rbp+37h+var_98], rax
0x180055d9e  mov     r13, rax
0x180055da1  test    rax, rax
0x180055da4  jnz     short loc_180055DB2
0x180055da6  lea     rdx, aAcceptsecurity_8; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x180055dad  jmp     loc_180055D26
0x180055db2  mov     r12, [rsp+110h+lpMultiByteStr]
0x180055db7  test    r12, r12
0x180055dba  jz      short loc_180055E1C
0x180055dbc  lea     rax, [rbp+37h+var_A8]
0x180055dc0  mov     [rbp+37h+var_A8], r14
0x180055dc4  xor     r9d, r9d; unsigned __int16 *
0x180055dc7  mov     [rsp+110h+var_F0], rax; unsigned __int16 **
0x180055dcc  xor     r8d, r8d; unsigned int
0x180055dcf  or      edx, 0FFFFFFFFh; cbMultiByte
0x180055dd2  mov     rcx, r12; lpMultiByteStr
0x180055dd5  call    ?NetpAllocWStrFromUtf8StrAsRequired@@YAKPEADKKPEAGPEAPEAG@Z; NetpAllocWStrFromUtf8StrAsRequired(char *,ulong,ulong,ushort *,ushort * *)
0x180055dda  test    eax, eax
0x180055ddc  jnz     short loc_180055DEB
0x180055dde  mov     r14, [rbp+37h+var_A8]
0x180055de2  test    r14, r14
0x180055de5  jnz     loc_180055EAC
0x180055deb  mov     r9, rbx
0x180055dee  mov     [rsp+110h+var_F0], r12
0x180055df3  mov     r8, rdi
0x180055df6  lea     rdx, aAcceptsecurity; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x180055dfd  mov     ecx, 100h; unsigned int
0x180055e02  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180055e07  mov     ebx, 80090300h
0x180055e0c  mov     r15, [rsp+110h+var_C8]
0x180055e11  mov     r9d, 10h
0x180055e17  jmp     loc_18005607C
0x180055e1c  mov     rsi, [rsp+110h+var_D8]
0x180055e21  test    rsi, rsi
0x180055e24  jz      short loc_180055E85
0x180055e26  lea     rax, [rsp+110h+SourceString]
0x180055e2b  mov     [rsp+110h+SourceString], r14
0x180055e30  xor     r9d, r9d; unsigned __int16 *
0x180055e33  mov     [rsp+110h+var_F0], rax; unsigned __int16 **
0x180055e38  xor     r8d, r8d; unsigned int
0x180055e3b  or      edx, 0FFFFFFFFh; cbMultiByte
0x180055e3e  mov     rcx, rsi; lpMultiByteStr
0x180055e41  call    ?NetpAllocWStrFromUtf8StrAsRequired@@YAKPEADKKPEAGPEAPEAG@Z; NetpAllocWStrFromUtf8StrAsRequired(char *,ulong,ulong,ushort *,ushort * *)
0x180055e46  test    eax, eax
0x180055e48  jnz     short loc_180055E54
0x180055e4a  mov     r14, [rsp+110h+SourceString]
0x180055e4f  test    r14, r14
0x180055e52  jnz     short loc_180055EAC
0x180055e54  mov     [rsp+110h+var_F0], rsi
0x180055e59  lea     rdx, aAcceptsecurity_0; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x180055e60  mov     r8, rdi
0x180055e63  mov     r9, rbx
0x180055e66  mov     ecx, 100h; unsigned int
0x180055e6b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180055e70  mov     r15, [rsp+110h+var_C8]
0x180055e75  mov     r9d, 10h
0x180055e7b  mov     ebx, 80090300h
0x180055e80  jmp     loc_180056081
0x180055e85  test    r15, r15
0x180055e88  jz      loc_180056008
0x180055e8e  mov     rcx, r15; SourceString
0x180055e91  call    NetpAllocWStrFromStr
0x180055e96  mov     r14, rax
0x180055e99  test    rax, rax
0x180055e9c  jnz     short loc_180055EAC
0x180055e9e  mov     [rsp+110h+var_F0], r15
0x180055ea3  lea     rdx, aAcceptsecurity_7; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x180055eaa  jmp     short loc_180055E60
0x180055eac  mov     r9, rbx
0x180055eaf  mov     [rsp+110h+var_F0], r14
0x180055eb4  mov     r8, rdi
0x180055eb7  lea     rdx, aAcceptsecurity_6; "AcceptSecurityContext: %Ix.%Ix: from %w"...
0x180055ebe  mov     ecx, 80000h; unsigned int
0x180055ec3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180055ec8  lea     r15, [r13+1F8h]
0x180055ecf  mov     rcx, r15; CriticalSection
0x180055ed2  call    cs:__imp_RtlEnterCriticalSection
0x180055ed9  nop     dword ptr [rax+rax+00h]
0x180055ede  mov     rdx, r14; unsigned __int16 *
0x180055ee1  mov     rcx, r13; struct _DOMAIN_INFO *
0x180055ee4  call    ?NlFindNamedServerSession@@YAPEAU_SERVER_SESSION@@PEAU_DOMAIN_INFO@@PEAG@Z; NlFindNamedServerSession(_DOMAIN_INFO *,ushort *)
0x180055ee9  mov     rsi, rax
0x180055eec  test    rax, rax
0x180055eef  jnz     short loc_180055F26
0x180055ef1  mov     rcx, r15; CriticalSection
0x180055ef4  call    cs:__imp_RtlLeaveCriticalSection
0x180055efb  nop     dword ptr [rax+rax+00h]
0x180055f00  lea     rdx, aAcceptsecurity_9; "AcceptSecurityContext: %Ix.%Ix: Can't N"...
0x180055f07  mov     r8, rdi
  ... truncated ...
```
