# AcceptSecurityContext

- ea: `0x1800520e0`
- end: `0x1800527b0`
- name: `AcceptSecurityContext`
- size: `1744`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, PCtxtHandle phContext, PSecBufferDesc pInput, unsigned int fContextReq, unsigned int TargetDataRep, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003670`
- `0x180007278`
- `0x18000ccf0`
- `0x18000d094`
- `0x18000d1a0`
- `0x18000d710`
- `0x18000e270`
- `0x18000ed34`
- `0x180025708`
- `0x180025e34`
- `0x180026180`
- `0x180051574`
- `0x1800520e0`
- `0x18005378c`
- `0x180077a74`
- `0x180082e88`
- `0x180083f24`
- `0x180085594`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18005257e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800525b3`
- `ntdll!RtlLeaveCriticalSection` at `0x180052609`
- `ntdll!RtlLeaveCriticalSection` at `0x18005257e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800525b3`
- `ntdll!RtlLeaveCriticalSection` at `0x180052609`
- `ntdll!RtlEnterCriticalSection` at `0x180052562`
- `ntdll!RtlEnterCriticalSection` at `0x180052562`
- `netutils!NetApiBufferFree` at `0x180052739`
- `netutils!NetApiBufferFree` at `0x18005274b`
- `netutils!NetApiBufferFree` at `0x180052739`
- `netutils!NetApiBufferFree` at `0x18005274b`

## string_xrefs

- `0x1800526ba`: `onecore\ds\netapi\svcdlls\logonsrv\server\secpkg.cxx`
- `0x18005211a`: `AcceptSecurityContext: called\n`
- `0x180052258`: `AcceptSecurityContext: %Ix.%Ix: cannot get netbios domain name\n`
- `0x1800522a8`: `AcceptSecurityContext: %Ix.%Ix: Cannot parse computer name\n`
- `0x1800522cf`: `AcceptSecurityContext: %Ix.%Ix: DNS domain bad.\n`
- `0x1800522f7`: `AcceptSecurityContext: %Ix.%Ix: DNS hostname bad.\n`
- `0x180052313`: `AcceptSecurityContext: %Ix.%Ix: both DNS '%hs' and Netbios '%hs' client name specified\n`
- `0x18005235a`: `AcceptSecurityContext: %Ix.%Ix: UTF8 computer name bad.\n`
- `0x1800523af`: `AcceptSecurityContext: %Ix.%Ix: Cannot find domain %hs\n`
- `0x1800523d2`: `AcceptSecurityContext: %Ix.%Ix: Neither DNS or netbios domain name specified (fatal)\n`
- `0x1800523fa`: `AcceptSecurityContext: %Ix.%Ix: Cannot alloc domain name %hs\n`
- `0x180052436`: `AcceptSecurityContext: %Ix.%Ix: Cannot find domain %ws (fatal)\n`
- `0x180052486`: `AcceptSecurityContext: %Ix.%Ix: Cannot alloc DNS computer name %hs\n`
- `0x1800524e9`: `AcceptSecurityContext: %Ix.%Ix: Cannot alloc utf8 computer name %hs\n`
- `0x180052533`: `AcceptSecurityContext: %Ix.%Ix: Cannot alloc oem computer name %hs\n`
- `0x180052683`: `AcceptSecurityContext: %Ix.%Ix: Don't know client computer name.\n`
- `0x180052547`: `AcceptSecurityContext: %Ix.%Ix: from %ws\n`
- `0x180052584`: `AcceptSecurityContext: %Ix.%Ix: Can't NlFindNamedServerSession for %ws\n`
- `0x1800525b9`: `AcceptSecurityContext: %Ix.%Ix: Secure channel doesn't exist for %ws\n`
- `0x1800525da`: `AcceptSecurityContext: %Ix.%Ix: Secure channel has been established with Kerberos for %ws\n`
- `0x1800526cd`: `AcceptSecurityContext: Second accept called.\n`
- `0x18005276c`: `AcceptSecurityContext: %Ix.%Ix: returns 0x%lx\n`

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
        NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\secpkg.cxx", 2246, (char *)v16);
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
0x1800520e0  mov     rax, rsp
0x1800520e3  mov     [rax+10h], rbx
0x1800520e7  push    rbp
0x1800520e8  push    rsi
0x1800520e9  push    rdi
0x1800520ea  push    r12
0x1800520ec  push    r13
0x1800520ee  push    r14
0x1800520f0  push    r15
0x1800520f2  lea     rbp, [rax-3Fh]
0x1800520f6  sub     rsp, 0E0h
0x1800520fd  movaps  xmmword ptr [rax-48h], xmm6
0x180052101  mov     rax, cs:__security_cookie
0x180052108  xor     rax, rsp
0x18005210b  mov     [rbp+37h+var_50], rax
0x18005210f  mov     rax, [rbp+37h+phNewContext]
0x180052113  mov     rsi, rdx
0x180052116  mov     r15, [rbp+37h+pOutput]
0x18005211a  lea     rdx, aAcceptsecurity_10; "AcceptSecurityContext: called\n"
0x180052121  mov     [rbp+37h+var_80], rax
0x180052125  mov     rbx, rcx
0x180052128  mov     rax, [rbp+37h+pfContextAttr]
0x18005212c  mov     ecx, 80000h; unsigned int
0x180052131  mov     [rbp+37h+var_78], rax
0x180052135  mov     rdi, r8
0x180052138  mov     rax, [rbp+37h+ptsExpiry]
0x18005213f  mov     [rbp+37h+var_70], rax
0x180052143  xor     eax, eax
0x180052145  mov     [rbp+37h+var_A0], rax
0x180052149  mov     r12d, eax
0x18005214c  mov     [rsp+110h+lpMultiByteStr], rax
0x180052151  mov     r13d, eax
0x180052154  mov     [rsp+110h+var_D8], rax
0x180052159  mov     [rbp+37h+var_A8], rax
0x18005215d  mov     [rsp+110h+SourceString], rax
0x180052162  mov     [rsp+110h+var_B8], r9d
0x180052167  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005216c  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x180052171  test    eax, eax
0x180052173  jnz     short loc_18005217F
0x180052175  mov     eax, 80090305h
0x18005217a  jmp     loc_180052784
0x18005217f  xor     r14d, r14d
0x180052182  mov     [rbp+37h+Buffer], r12
0x180052186  test    [rsp+110h+var_B8], 100h
0x18005218e  mov     [rbp+37h+var_98], r12
0x180052192  lea     r9d, [r14+10h]
0x180052196  jz      short loc_1800521A8
0x180052198  mov     ebx, 80090300h
0x18005219d  mov     r15, r12
0x1800521a0  mov     rdi, r12
0x1800521a3  jmp     loc_1800526F4
0x1800521a8  mov     r11d, 0Ch
0x1800521ae  mov     rcx, rdi; struct _SecBufferDesc *
0x1800521b1  mov     edx, r11d; unsigned int
0x1800521b4  call    ?LocateBuffer@@YAPEAU_SecBuffer@@PEAU_SecBufferDesc@@K@Z; LocateBuffer(_SecBufferDesc *,ulong)
0x1800521b9  mov     r12, rax
0x1800521bc  test    rax, rax
0x1800521bf  jz      loc_1800526E4
0x1800521c5  mov     edx, r11d; unsigned int
0x1800521c8  mov     rcx, r15; struct _SecBufferDesc *
0x1800521cb  call    ?LocateBuffer@@YAPEAU_SecBuffer@@PEAU_SecBufferDesc@@K@Z; LocateBuffer(_SecBufferDesc *,ulong)
0x1800521d0  mov     [rbp+37h+var_88], rax
0x1800521d4  test    rax, rax
0x1800521d7  jz      loc_1800526E4
0x1800521dd  test    rsi, rsi
0x1800521e0  jnz     loc_1800526B4
0x1800521e6  test    rbx, rbx
0x1800521e9  jz      loc_1800526A7
0x1800521ef  mov     rdi, [rbx+8]
0x1800521f3  mov     eax, 0FEFEFEFEh
0x1800521f8  cmp     rdi, rax
0x1800521fb  jnz     loc_1800526A7
0x180052201  mov     rbx, [rbx]
0x180052204  test    rbx, rbx
0x180052207  jnz     loc_1800526A7
0x18005220d  mov     r15, rbx
0x180052210  mov     [rsp+110h+var_C8], rbx
0x180052215  cmp     [r12], r11d
0x180052219  jb      loc_1800526EA
0x18005221f  mov     rsi, [r12+8]
0x180052224  cmp     [rsi], r13d
0x180052227  jnz     loc_1800526EA
0x18005222d  test    byte ptr [rsi+4], 1
0x180052231  lea     rax, [rsi+8]
0x180052235  mov     [rbp+37h+var_B0], rax
0x180052239  jz      short loc_180052284
0x18005223b  mov     edx, [r12]
0x18005223f  lea     rax, [rbp+37h+var_A8]
0x180052243  lea     r8, [rbp+37h+var_B0]
0x180052247  mov     [rsp+110h+var_F0], rax
0x18005224c  mov     rcx, rsi
0x18005224f  call    NetpLogonGetOemString
0x180052254  test    eax, eax
0x180052256  jnz     short loc_18005227A
0x180052258  lea     rdx, aAcceptsecurity_1; "AcceptSecurityContext: %Ix.%Ix: cannot "...
0x18005225f  mov     r8, rdi
0x180052262  mov     r9, rbx
0x180052265  mov     ecx, 100h; unsigned int
0x18005226a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005226f  mov     r9d, 10h
0x180052275  jmp     loc_1800526EA
0x18005227a  mov     r13, [rbp+37h+var_A8]
0x18005227e  mov     r9d, 10h
0x180052284  test    byte ptr [rsi+4], 2
0x180052288  jz      short loc_1800522B1
0x18005228a  mov     edx, [r12]
0x18005228e  lea     rax, [rsp+110h+SourceString]
0x180052293  lea     r8, [rbp+37h+var_B0]
0x180052297  mov     [rsp+110h+var_F0], rax
0x18005229c  mov     rcx, rsi
0x18005229f  call    NetpLogonGetOemString
0x1800522a4  test    eax, eax
0x1800522a6  jnz     short loc_1800522B1
0x1800522a8  lea     rdx, aAcceptsecurity_18; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x1800522af  jmp     short loc_18005225F
0x1800522b1  test    byte ptr [rsi+4], 4
0x1800522b5  jz      short loc_1800522D8
0x1800522b7  mov     edx, [r12]; unsigned int
0x1800522bb  lea     r9, [rbp+37h+var_A0]; char **
0x1800522bf  lea     r8, [rbp+37h+var_B0]; char **
0x1800522c3  mov     rcx, rsi; void *
0x1800522c6  call    ?NetpLogonGetCutf8String@@YAHPEAXKPEAPEAD1@Z; NetpLogonGetCutf8String(void *,ulong,char * *,char * *)
0x1800522cb  test    eax, eax
0x1800522cd  jnz     short loc_1800522D8
0x1800522cf  lea     rdx, aAcceptsecurity_19; "AcceptSecurityContext: %Ix.%Ix: DNS dom"...
0x1800522d6  jmp     short loc_18005225F
0x1800522d8  test    byte ptr [rsi+4], 8
0x1800522dc  jz      short loc_180052336
0x1800522de  mov     edx, [r12]; unsigned int
0x1800522e2  lea     r9, [rsp+110h+lpMultiByteStr]; char **
0x1800522e7  lea     r8, [rbp+37h+var_B0]; char **
0x1800522eb  mov     rcx, rsi; void *
0x1800522ee  call    ?NetpLogonGetCutf8String@@YAHPEAXKPEAPEAD1@Z; NetpLogonGetCutf8String(void *,ulong,char * *,char * *)
0x1800522f3  test    eax, eax
0x1800522f5  jnz     short loc_180052303
0x1800522f7  lea     rdx, aAcceptsecurity_3; "AcceptSecurityContext: %Ix.%Ix: DNS hos"...
0x1800522fe  jmp     loc_18005225F
0x180052303  test    byte ptr [rsi+4], 2
0x180052307  mov     r15, [rsp+110h+SourceString]
0x18005230c  jz      short loc_18005233B
0x18005230e  mov     rax, [rsp+110h+lpMultiByteStr]
0x180052313  lea     rdx, aAcceptsecurity_2; "AcceptSecurityContext: %Ix.%Ix: both DN"...
0x18005231a  mov     [rsp+110h+var_E8], r15
0x18005231f  mov     r9, rbx
0x180052322  mov     r8, rdi
0x180052325  mov     [rsp+110h+var_F0], rax
0x18005232a  mov     ecx, 100h; unsigned int
0x18005232f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052334  jmp     short loc_18005233B
0x180052336  mov     r15, [rsp+110h+SourceString]
0x18005233b  test    byte ptr [rsi+4], 10h
0x18005233f  jz      short loc_180052381
0x180052341  mov     edx, [r12]; unsigned int
0x180052345  lea     r9, [rsp+110h+var_D8]; char **
0x18005234a  lea     r8, [rbp+37h+var_B0]; char **
0x18005234e  mov     rcx, rsi; void *
0x180052351  call    ?NetpLogonGetCutf8String@@YAHPEAXKPEAPEAD1@Z; NetpLogonGetCutf8String(void *,ulong,char * *,char * *)
0x180052356  test    eax, eax
0x180052358  jnz     short loc_180052381
0x18005235a  lea     rdx, aAcceptsecurity_15; "AcceptSecurityContext: %Ix.%Ix: UTF8 co"...
0x180052361  mov     r8, rdi
0x180052364  mov     r9, rbx
0x180052367  mov     ecx, 100h; unsigned int
0x18005236c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052371  mov     r15, [rsp+110h+var_C8]
0x180052376  mov     r9d, 10h
0x18005237c  jmp     loc_1800526EA
0x180052381  mov     rsi, [rbp+37h+var_A0]
0x180052385  test    rsi, rsi
0x180052388  jz      short loc_1800523CD
0x18005238a  mov     r9b, 1; unsigned __int8
0x18005238d  mov     [rsp+110h+var_F0], r14; unsigned __int8 *
0x180052392  xor     r8d, r8d; unsigned __int8
0x180052395  xor     edx, edx; Buf1
0x180052397  mov     rcx, rsi; char *
0x18005239a  call    ?NlFindDnsDomain@@YAPEAU_DOMAIN_INFO@@PEBDPEAU_GUID@@EEPEAE@Z; NlFindDnsDomain(char const *,_GUID *,uchar,uchar,uchar *)
0x18005239f  mov     [rbp+37h+var_98], rax
0x1800523a3  mov     r13, rax
0x1800523a6  test    rax, rax
0x1800523a9  jnz     loc_180052442
0x1800523af  lea     rdx, aAcceptsecurity_4; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x1800523b6  mov     r8, rdi
0x1800523b9  mov     [rsp+110h+var_F0], rsi
0x1800523be  mov     r9, rbx
0x1800523c1  mov     ecx, 100h; unsigned int
0x1800523c6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800523cb  jmp     short loc_180052371
0x1800523cd  test    r13, r13
0x1800523d0  jnz     short loc_1800523DB
0x1800523d2  lea     rdx, aAcceptsecurity_16; "AcceptSecurityContext: %Ix.%Ix: Neither"...
0x1800523d9  jmp     short loc_180052361
0x1800523db  mov     rcx, r13; SourceString
0x1800523de  call    NetpAllocWStrFromStr
0x1800523e3  mov     [rbp+37h+Buffer], rax
0x1800523e7  mov     rsi, rax
0x1800523ea  test    rax, rax
0x1800523ed  jnz     short loc_180052420
0x1800523ef  mov     r9, rbx
0x1800523f2  mov     [rsp+110h+var_F0], r13
0x1800523f7  mov     r8, rdi
0x1800523fa  lea     rdx, aAcceptsecurity_14; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x180052401  mov     ecx, 100h; unsigned int
0x180052406  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005240b  mov     r15, [rsp+110h+var_C8]
0x180052410  mov     ebx, 80090300h
0x180052415  mov     r9d, 10h
0x18005241b  jmp     loc_1800526EF
0x180052420  xor     edx, edx; unsigned __int8
0x180052422  mov     rcx, rsi; SourceString
0x180052425  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x18005242a  mov     [rbp+37h+var_98], rax
0x18005242e  mov     r13, rax
0x180052431  test    rax, rax
0x180052434  jnz     short loc_180052442
0x180052436  lea     rdx, aAcceptsecurity_8; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x18005243d  jmp     loc_1800523B6
0x180052442  mov     r12, [rsp+110h+lpMultiByteStr]
0x180052447  test    r12, r12
0x18005244a  jz      short loc_1800524AC
0x18005244c  lea     rax, [rbp+37h+var_A8]
0x180052450  mov     [rbp+37h+var_A8], r14
0x180052454  xor     r9d, r9d; unsigned __int16 *
0x180052457  mov     [rsp+110h+var_F0], rax; unsigned __int16 **
0x18005245c  xor     r8d, r8d; unsigned int
0x18005245f  or      edx, 0FFFFFFFFh; cbMultiByte
0x180052462  mov     rcx, r12; lpMultiByteStr
0x180052465  call    ?NetpAllocWStrFromUtf8StrAsRequired@@YAKPEADKKPEAGPEAPEAG@Z; NetpAllocWStrFromUtf8StrAsRequired(char *,ulong,ulong,ushort *,ushort * *)
0x18005246a  test    eax, eax
0x18005246c  jnz     short loc_18005247B
0x18005246e  mov     r14, [rbp+37h+var_A8]
0x180052472  test    r14, r14
0x180052475  jnz     loc_18005253C
0x18005247b  mov     r9, rbx
0x18005247e  mov     [rsp+110h+var_F0], r12
0x180052483  mov     r8, rdi
0x180052486  lea     rdx, aAcceptsecurity; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x18005248d  mov     ecx, 100h; unsigned int
0x180052492  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052497  mov     ebx, 80090300h
0x18005249c  mov     r15, [rsp+110h+var_C8]
0x1800524a1  mov     r9d, 10h
0x1800524a7  jmp     loc_1800526F4
0x1800524ac  mov     rsi, [rsp+110h+var_D8]
0x1800524b1  test    rsi, rsi
0x1800524b4  jz      short loc_180052515
0x1800524b6  lea     rax, [rsp+110h+SourceString]
0x1800524bb  mov     [rsp+110h+SourceString], r14
0x1800524c0  xor     r9d, r9d; unsigned __int16 *
0x1800524c3  mov     [rsp+110h+var_F0], rax; unsigned __int16 **
0x1800524c8  xor     r8d, r8d; unsigned int
0x1800524cb  or      edx, 0FFFFFFFFh; cbMultiByte
0x1800524ce  mov     rcx, rsi; lpMultiByteStr
0x1800524d1  call    ?NetpAllocWStrFromUtf8StrAsRequired@@YAKPEADKKPEAGPEAPEAG@Z; NetpAllocWStrFromUtf8StrAsRequired(char *,ulong,ulong,ushort *,ushort * *)
0x1800524d6  test    eax, eax
0x1800524d8  jnz     short loc_1800524E4
0x1800524da  mov     r14, [rsp+110h+SourceString]
0x1800524df  test    r14, r14
0x1800524e2  jnz     short loc_18005253C
0x1800524e4  mov     [rsp+110h+var_F0], rsi
0x1800524e9  lea     rdx, aAcceptsecurity_0; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x1800524f0  mov     r8, rdi
0x1800524f3  mov     r9, rbx
0x1800524f6  mov     ecx, 100h; unsigned int
0x1800524fb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052500  mov     r15, [rsp+110h+var_C8]
0x180052505  mov     r9d, 10h
0x18005250b  mov     ebx, 80090300h
0x180052510  jmp     loc_1800526F9
0x180052515  test    r15, r15
0x180052518  jz      loc_180052680
0x18005251e  mov     rcx, r15; SourceString
0x180052521  call    NetpAllocWStrFromStr
0x180052526  mov     r14, rax
0x180052529  test    rax, rax
0x18005252c  jnz     short loc_18005253C
0x18005252e  mov     [rsp+110h+var_F0], r15
0x180052533  lea     rdx, aAcceptsecurity_7; "AcceptSecurityContext: %Ix.%Ix: Cannot "...
0x18005253a  jmp     short loc_1800524F0
0x18005253c  mov     r9, rbx
0x18005253f  mov     [rsp+110h+var_F0], r14
0x180052544  mov     r8, rdi
0x180052547  lea     rdx, aAcceptsecurity_6; "AcceptSecurityContext: %Ix.%Ix: from %w"...
0x18005254e  mov     ecx, 80000h; unsigned int
0x180052553  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180052558  lea     r15, [r13+1F8h]
0x18005255f  mov     rcx, r15; CriticalSection
0x180052562  call    cs:__imp_RtlEnterCriticalSection
0x180052568  mov     rdx, r14; unsigned __int16 *
0x18005256b  mov     rcx, r13; struct _DOMAIN_INFO *
0x18005256e  call    ?NlFindNamedServerSession@@YAPEAU_SERVER_SESSION@@PEAU_DOMAIN_INFO@@PEAG@Z; NlFindNamedServerSession(_DOMAIN_INFO *,ushort *)
0x180052573  mov     rsi, rax
0x180052576  test    rax, rax
0x180052579  jnz     short loc_1800525AA
0x18005257b  mov     rcx, r15; CriticalSection
0x18005257e  call    cs:__imp_RtlLeaveCriticalSection
0x180052584  lea     rdx, aAcceptsecurity_9; "AcceptSecurityContext: %Ix.%Ix: Can't N"...
0x18005258b  mov     r8, rdi
0x18005258e  mov     [rsp+110h+var_F0], r14
0x180052593  mov     r9, rbx
  ... truncated ...
```
