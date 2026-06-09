# HTTP_PROTOCOL::CreateCtrlRequestQueue(ushort const *,void *,void *,void * *)

- ea: `0x18001d6cc`
- end: `0x18001db0d`
- name: `?CreateCtrlRequestQueue@HTTP_PROTOCOL@@QEAAJPEBGPEAX1PEAPEAX@Z`
- size: `1089`
- prototype: `int(HTTP_PROTOCOL *__hidden this, const unsigned __int16 *, void *, void *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f810`
- `0x18005b460`

## callees

- `0x18001d6cc`
- `0x18001f2d4`
- `0x18005f870`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d975`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001da63`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001da63`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001d91d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001d91d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001d96b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001d96b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001daa8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001daa8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001d7c5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001d7c5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d864`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d879`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d864`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d879`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dabd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dabd`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001d8de`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001d8de`
- `iisutil!PuDbgPrintError` at `0x18001d81c`
- `iisutil!PuDbgPrintError` at `0x18001da41`
- `iisutil!PuDbgPrintError` at `0x18001d81c`
- `iisutil!PuDbgPrintError` at `0x18001da41`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001dae1`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001dae1`
- `HTTPAPI!HttpCloseRequestQueue` at `0x18001dad2`
- `HTTPAPI!HttpCloseRequestQueue` at `0x18001dad2`

## string_xrefs

- `0x18001d815`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol.cxx`
- `0x18001da30`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol.cxx`
- `0x18001d902`: `Setting ACE's into ACL failed.\n`
- `0x18001d7f1`: `Creating Local System SID failed\n`
- `0x18001d80e`: `HTTP_PROTOCOL::CreateCtrlRequestQueue`
- `0x18001da24`: `HTTP_PROTOCOL::CreateCtrlRequestQueue`
- `0x18001d895`: `Request Queue Delegator Identity SID can't be the same to the Apppool ID Sid\n`
- `0x18001d949`: `Initializing the security descriptor failed\n`
- `0x18001d997`: `Setting the DACL on the security descriptor failed\n`
- `0x18001da19`: `Couldn't create app pool handle, Retry count is %d\n`

## pseudocode

```c
__int64 __fastcall HTTP_PROTOCOL::CreateCtrlRequestQueue(
        HTTP_PROTOCOL *this,
        const unsigned __int16 *a2,
        void *a3,
        void *a4,
        void **a5)
{
  int v5; // esi
  HANDLE v7; // rdx
  unsigned int v11; // ebx
  signed int v12; // eax
  const char *v13; // rax
  __int64 v14; // r8
  ULONG v15; // edi
  _EXPLICIT_ACCESS_W *p_pListOfExplicitEntries; // rax
  __int64 v17; // rcx
  signed int v18; // eax
  signed int LastError; // eax
  signed int v20; // eax
  struct _SECURITY_ATTRIBUTES *v21; // r9
  int v22; // eax
  int v23; // edi
  HANDLE RequestQueueHandle; // [rsp+60h] [rbp-A0h] BYREF
  PSID pSid2; // [rsp+68h] [rbp-98h] BYREF
  PACL NewAcl; // [rsp+70h] [rbp-90h] BYREF
  __int128 v28; // [rsp+78h] [rbp-88h] BYREF
  __int64 v29; // [rsp+88h] [rbp-78h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+90h] [rbp-70h] BYREF
  __int128 v31; // [rsp+C0h] [rbp-40h]
  _OWORD v32[2]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v34; // [rsp+110h] [rbp+10h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v36[5]; // [rsp+120h] [rbp+20h] BYREF
  int v37; // [rsp+148h] [rbp+48h]
  __int16 v38; // [rsp+14Ch] [rbp+4Ch]

  v5 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v34 = 0;
  v29 = 0;
  v7 = 0;
  v36[4] = v36;
  RequestQueueHandle = 0;
  pSid2 = 0;
  NewAcl = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  v36[0] = 0;
  v37 = 32;
  v38 = 256;
  v31 = 0;
  memset(v32, 0, sizeof(v32));
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v28 = 0;
  if ( !*((_QWORD *)this + 44) )
  {
    v11 = -2147024846;
    goto LABEL_59;
  }
  if ( *((_DWORD *)g_pWebAdminService + 412) )
    goto LABEL_36;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid2) )
  {
    v15 = 1;
    p_pListOfExplicitEntries = &pListOfExplicitEntries;
    v17 = 96;
    do
    {
      LOBYTE(p_pListOfExplicitEntries->grfAccessPermissions) = 0;
      p_pListOfExplicitEntries = (_EXPLICIT_ACCESS_W *)((char *)p_pListOfExplicitEntries + 1);
      --v17;
    }
    while ( v17 );
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid2;
    pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
    if ( a4 && !EqualSid(a4, pSid2) )
    {
      if ( a3 && EqualSid(a4, a3) )
      {
        v11 = -2147024846;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
            4137,
            "HTTP_PROTOCOL::CreateCtrlRequestQueue",
            -2147024846,
            "Request Queue Delegator Identity SID can't be the same to the Apppool ID Sid\n");
        goto LABEL_53;
      }
      v15 = 2;
      LODWORD(v31) = -1073741824;
      *(_QWORD *)((char *)&v31 + 4) = 1;
      *(_QWORD *)((char *)v32 + 12) = 0;
      *((_QWORD *)&v32[1] + 1) = a4;
    }
    v18 = SetEntriesInAclW(v15, &pListOfExplicitEntries, 0, &NewAcl);
    v11 = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        v11 = (unsigned __int16)v18 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_53;
      v13 = "Setting ACE's into ACL failed.\n";
      v14 = 4176;
      goto LABEL_9;
    }
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_53;
      v13 = "Initializing the security descriptor failed\n";
      v14 = 4188;
      goto LABEL_9;
    }
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
    {
      v20 = GetLastError();
      v11 = v20;
      if ( v20 > 0 )
        v11 = (unsigned __int16)v20 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_53;
      v13 = "Setting the DACL on the security descriptor failed\n";
      v14 = 4203;
      goto LABEL_9;
    }
    v7 = RequestQueueHandle;
LABEL_36:
    LODWORD(v28) = 24;
    *((_QWORD *)&v28 + 1) = pSecurityDescriptor;
    LODWORD(v29) = 0;
    while ( !v7 )
    {
      v21 = (struct _SECURITY_ATTRIBUTES *)&v28;
      if ( *((_DWORD *)g_pWebAdminService + 412) )
        v21 = 0;
      v22 = HTTP_WRAPPER::CreateRequestQueue(*((HTTP_WRAPPER **)this + 44), &RequestQueueHandle, a2, v21);
      v23 = v22;
      if ( v22 )
      {
        if ( v22 > 0 )
          v11 = (unsigned __int16)v22 | 0x80070000;
        else
          v11 = v22;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
            4235,
            "HTTP_PROTOCOL::CreateCtrlRequestQueue",
            v11,
            "Couldn't create app pool handle, Retry count is %d\n",
            v5);
        if ( (unsigned int)++v5 > 0x32 || v23 != 183 )
          goto LABEL_53;
        Sleep(5u);
      }
      v7 = RequestQueueHandle;
    }
    if ( a3 )
    {
      HTTP_PROTOCOL::ResetRequestQueueAccess(this, (enum _ACCESS_MODE)v7, a3, v7, a2);
      v7 = RequestQueueHandle;
    }
    *a5 = v7;
    v11 = 0;
    RequestQueueHandle = 0;
    goto LABEL_53;
  }
  v12 = GetLastError();
  v11 = v12;
  if ( v12 > 0 )
    v11 = (unsigned __int16)v12 | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) == 0 )
    goto LABEL_53;
  v13 = "Creating Local System SID failed\n";
  v14 = 4109;
LABEL_9:
  PuDbgPrintError(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
    v14,
    "HTTP_PROTOCOL::CreateCtrlRequestQueue",
    v11,
    v13);
LABEL_53:
  if ( pSid2 )
  {
    FreeSid(pSid2);
    pSid2 = 0;
  }
  if ( NewAcl )
  {
    LocalFree(NewAcl);
    NewAcl = 0;
  }
  if ( RequestQueueHandle )
  {
    HttpCloseRequestQueue(RequestQueueHandle);
    RequestQueueHandle = 0;
  }
LABEL_59:
  BUFFER::~BUFFER((BUFFER *)v36);
  return v11;
}

```

## disassembly

```asm
0x18001d6cc  push    rbp
0x18001d6ce  push    rbx
0x18001d6cf  push    rsi
0x18001d6d0  push    rdi
0x18001d6d1  push    r12
0x18001d6d3  push    r13
0x18001d6d5  push    r14
0x18001d6d7  push    r15
0x18001d6d9  lea     rbp, [rsp-68h]
0x18001d6de  sub     rsp, 168h
0x18001d6e5  mov     rax, cs:__security_cookie
0x18001d6ec  xor     rax, rsp
0x18001d6ef  mov     [rbp+0A0h+var_50], rax
0x18001d6f3  mov     r12, [rbp+0A0h+arg_20]
0x18001d6fa  xor     esi, esi
0x18001d6fc  xorps   xmm0, xmm0
0x18001d6ff  mov     dword ptr [rbp+0A0h+pIdentifierAuthority.Value], esi
0x18001d702  xor     eax, eax
0x18001d704  mov     word ptr [rbp+0A0h+pIdentifierAuthority.Value+4], 500h
0x18001d70a  xorps   xmm1, xmm1
0x18001d70d  mov     [rbp+0A0h+var_90], rax
0x18001d711  mov     r15, rdx
0x18001d714  mov     [rbp+0A0h+var_118], rax
0x18001d718  lea     rax, [rbp+0A0h+var_80]
0x18001d71c  mov     edx, esi
0x18001d71e  mov     rbx, r9
0x18001d721  mov     [rbp+0A0h+var_60], rax
0x18001d725  mov     r14, r8
0x18001d728  mov     r13, rcx
0x18001d72b  mov     [rsp+1A0h+RequestQueueHandle], rdx
0x18001d730  mov     [rsp+1A0h+pSid2], rsi
0x18001d735  mov     [rsp+1A0h+NewAcl], rsi
0x18001d73a  movups  xmmword ptr [rbp+0A0h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18001d73e  mov     [rbp+0A0h+var_80], rsi
0x18001d742  movups  xmmword ptr [rbp+0A0h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18001d746  mov     [rbp+0A0h+var_58], 20h ; ' '
0x18001d74d  movups  xmmword ptr [rbp+0A0h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18001d751  mov     [rbp+0A0h+var_54], 100h
0x18001d757  movups  [rbp+0A0h+var_E0], xmm1
0x18001d75b  movups  [rbp+0A0h+var_D0], xmm1
0x18001d75f  movups  [rbp+0A0h+var_C0], xmm1
0x18001d763  movups  [rbp+0A0h+pSecurityDescriptor], xmm0
0x18001d767  movups  [rbp+0A0h+var_A0], xmm0
0x18001d76b  movups  [rsp+1A0h+var_128], xmm0
0x18001d770  cmp     [rcx+160h], rsi
0x18001d777  jnz     short loc_18001D783
0x18001d779  mov     ebx, 80070032h
0x18001d77e  jmp     loc_18001DADD
0x18001d783  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18001d78a  cmp     [rax+670h], esi
0x18001d790  jnz     loc_18001D9AE
0x18001d796  lea     rax, [rsp+1A0h+pSid2]
0x18001d79b  xor     r9d, r9d; nSubAuthority1
0x18001d79e  mov     [rsp+1A0h+pSid], rax; pSid
0x18001d7a3  lea     rcx, [rbp+0A0h+pIdentifierAuthority]; pIdentifierAuthority
0x18001d7a7  mov     [rsp+1A0h+nSubAuthority7], esi; nSubAuthority7
0x18001d7ab  mov     dl, 1; nSubAuthorityCount
0x18001d7ad  mov     [rsp+1A0h+nSubAuthority6], esi; nSubAuthority6
0x18001d7b1  mov     [rsp+1A0h+nSubAuthority5], esi; nSubAuthority5
0x18001d7b5  lea     r8d, [r9+12h]; nSubAuthority0
0x18001d7b9  mov     [rsp+1A0h+nSubAuthority4], esi; nSubAuthority4
0x18001d7bd  mov     [rsp+1A0h+nSubAuthority3], esi; nSubAuthority3
0x18001d7c1  mov     [rsp+1A0h+nSubAuthority2], esi; nSubAuthority2
0x18001d7c5  call    cs:__imp_AllocateAndInitializeSid
0x18001d7cb  test    eax, eax
0x18001d7cd  jnz     short loc_18001D827
0x18001d7cf  call    cs:__imp_GetLastError
0x18001d7d5  mov     ebx, eax
0x18001d7d7  test    eax, eax
0x18001d7d9  jle     short loc_18001D7E4
0x18001d7db  movzx   ebx, ax
0x18001d7de  or      ebx, 80070000h
0x18001d7e4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001d7eb  jz      loc_18001DA9E
0x18001d7f1  lea     rax, aCreatingLocalS; "Creating Local System SID failed\n"
0x18001d7f8  mov     r8d, 100Dh
0x18001d7fe  mov     qword ptr [rsp+1A0h+nSubAuthority3], rax
0x18001d803  mov     [rsp+1A0h+nSubAuthority2], ebx
0x18001d807  mov     rcx, cs:g_pDebug
0x18001d80e  lea     r9, aHttpProtocolCr; "HTTP_PROTOCOL::CreateCtrlRequestQueue"
0x18001d815  lea     rdx, aServercommonIn_29; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001d81c  call    cs:__imp_PuDbgPrintError
0x18001d822  jmp     loc_18001DA9E
0x18001d827  mov     edi, 1
0x18001d82c  lea     rax, [rbp+0A0h+pListOfExplicitEntries]
0x18001d830  lea     ecx, [rdi+5Fh]
0x18001d833  mov     [rax], sil
0x18001d836  inc     rax
0x18001d839  sub     rcx, rdi
0x18001d83c  jnz     short loc_18001D833
0x18001d83e  mov     rdx, [rsp+1A0h+pSid2]; pSid2
0x18001d843  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.ptstrName], rdx
0x18001d847  mov     [rbp+0A0h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x18001d84e  mov     qword ptr [rbp+0A0h+pListOfExplicitEntries.grfAccessMode], rdi
0x18001d852  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x18001d855  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x18001d85c  test    rbx, rbx
0x18001d85f  jz      short loc_18001D8D0
0x18001d861  mov     rcx, rbx; pSid1
0x18001d864  call    cs:__imp_EqualSid
0x18001d86a  test    eax, eax
0x18001d86c  jnz     short loc_18001D8D0
0x18001d86e  test    r14, r14
0x18001d871  jz      short loc_18001D8B4
0x18001d873  mov     rdx, r14; pSid2
0x18001d876  mov     rcx, rbx; pSid1
0x18001d879  call    cs:__imp_EqualSid
0x18001d87f  test    eax, eax
0x18001d881  jz      short loc_18001D8B4
0x18001d883  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001d88a  mov     ebx, 80070032h
0x18001d88f  jz      loc_18001DA9E
0x18001d895  lea     rax, aRequestQueueDe; "Request Queue Delegator Identity SID ca"...
0x18001d89c  mov     r8d, 1029h
0x18001d8a2  mov     qword ptr [rsp+1A0h+nSubAuthority3], rax
0x18001d8a7  mov     [rsp+1A0h+nSubAuthority2], 80070032h
0x18001d8af  jmp     loc_18001D807
0x18001d8b4  mov     edi, 2
0x18001d8b9  mov     dword ptr [rbp+0A0h+var_E0], 0C0000000h
0x18001d8c0  mov     qword ptr [rbp+0A0h+var_E0+4], 1
0x18001d8c8  mov     qword ptr [rbp+0A0h+var_D0+0Ch], rsi
0x18001d8cc  mov     qword ptr [rbp+0A0h+var_C0+8], rbx
0x18001d8d0  lea     r9, [rsp+1A0h+NewAcl]; NewAcl
0x18001d8d5  xor     r8d, r8d; OldAcl
0x18001d8d8  lea     rdx, [rbp+0A0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18001d8dc  mov     ecx, edi; cCountOfExplicitEntries
0x18001d8de  call    cs:__imp_SetEntriesInAclW
0x18001d8e4  mov     ebx, eax
0x18001d8e6  test    eax, eax
0x18001d8e8  jz      short loc_18001D914
0x18001d8ea  jle     short loc_18001D8F5
0x18001d8ec  movzx   ebx, ax
0x18001d8ef  or      ebx, 80070000h
0x18001d8f5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001d8fc  jz      loc_18001DA9E
0x18001d902  lea     rax, aSettingAceSInt; "Setting ACE's into ACL failed.\n"
0x18001d909  mov     r8d, 1050h
0x18001d90f  jmp     loc_18001D7FE
0x18001d914  mov     edx, 1; dwRevision
0x18001d919  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18001d91d  call    cs:__imp_InitializeSecurityDescriptor
0x18001d923  test    eax, eax
0x18001d925  jnz     short loc_18001D95B
0x18001d927  call    cs:__imp_GetLastError
0x18001d92d  mov     ebx, eax
0x18001d92f  test    eax, eax
0x18001d931  jle     short loc_18001D93C
0x18001d933  movzx   ebx, ax
0x18001d936  or      ebx, 80070000h
0x18001d93c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001d943  jz      loc_18001DA9E
0x18001d949  lea     rax, aInitializingTh_0; "Initializing the security descriptor fa"...
0x18001d950  mov     r8d, 105Ch
0x18001d956  jmp     loc_18001D7FE
0x18001d95b  mov     r8, [rsp+1A0h+NewAcl]; pDacl
0x18001d960  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18001d964  xor     r9d, r9d; bDaclDefaulted
0x18001d967  lea     edx, [r9+1]; bDaclPresent
0x18001d96b  call    cs:__imp_SetSecurityDescriptorDacl
0x18001d971  test    eax, eax
0x18001d973  jnz     short loc_18001D9A9
0x18001d975  call    cs:__imp_GetLastError
0x18001d97b  mov     ebx, eax
0x18001d97d  test    eax, eax
0x18001d97f  jle     short loc_18001D98A
0x18001d981  movzx   ebx, ax
0x18001d984  or      ebx, 80070000h
0x18001d98a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001d991  jz      loc_18001DA9E
0x18001d997  lea     rax, aSettingTheDacl; "Setting the DACL on the security descri"...
0x18001d99e  mov     r8d, 106Bh
0x18001d9a4  jmp     loc_18001D7FE
0x18001d9a9  mov     rdx, [rsp+1A0h+RequestQueueHandle]
0x18001d9ae  lea     rax, [rbp+0A0h+pSecurityDescriptor]
0x18001d9b2  mov     dword ptr [rsp+1A0h+var_128], 18h
0x18001d9ba  mov     qword ptr [rbp+0A0h+var_128+8], rax
0x18001d9be  mov     dword ptr [rbp+0A0h+var_118], esi
0x18001d9c1  jmp     loc_18001DA6E
0x18001d9c6  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18001d9cd  lea     r9, [rsp+1A0h+var_128]
0x18001d9d2  xor     ecx, ecx
0x18001d9d4  lea     rdx, [rsp+1A0h+RequestQueueHandle]; void **
0x18001d9d9  mov     r8, r15; unsigned __int16 *
0x18001d9dc  cmp     [rax+670h], ecx
0x18001d9e2  cmovnz  r9, rcx; struct _SECURITY_ATTRIBUTES *
0x18001d9e6  mov     rcx, [r13+160h]; this
0x18001d9ed  call    ?CreateRequestQueue@HTTP_WRAPPER@@QEAAKPEAPEAXPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; HTTP_WRAPPER::CreateRequestQueue(void * *,ushort const *,_SECURITY_ATTRIBUTES *)
0x18001d9f2  mov     edi, eax
0x18001d9f4  test    eax, eax
0x18001d9f6  jz      short loc_18001DA69
0x18001d9f8  test    eax, eax
0x18001d9fa  jg      short loc_18001DA00
0x18001d9fc  mov     ebx, eax
0x18001d9fe  jmp     short loc_18001DA09
0x18001da00  movzx   ebx, di
0x18001da03  or      ebx, 80070000h
0x18001da09  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001da10  jz      short loc_18001DA47
0x18001da12  mov     rcx, cs:g_pDebug
0x18001da19  lea     rax, aCouldnTCreateA; "Couldn't create app pool handle, Retry "...
0x18001da20  mov     [rsp+1A0h+nSubAuthority4], esi
0x18001da24  lea     r9, aHttpProtocolCr; "HTTP_PROTOCOL::CreateCtrlRequestQueue"
0x18001da2b  mov     qword ptr [rsp+1A0h+nSubAuthority3], rax
0x18001da30  lea     rdx, aServercommonIn_29; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001da37  mov     r8d, 108Bh
0x18001da3d  mov     [rsp+1A0h+nSubAuthority2], ebx
0x18001da41  call    cs:__imp_PuDbgPrintError
0x18001da47  inc     esi
0x18001da49  cmp     esi, 32h ; '2'
0x18001da4c  ja      loc_18001DB09
0x18001da52  cmp     edi, 0B7h
0x18001da58  jnz     loc_18001DB09
0x18001da5e  mov     ecx, 5; dwMilliseconds
0x18001da63  call    cs:__imp_Sleep
0x18001da69  mov     rdx, [rsp+1A0h+RequestQueueHandle]; enum _ACCESS_MODE
0x18001da6e  test    rdx, rdx
0x18001da71  jz      loc_18001D9C6
0x18001da77  xor     esi, esi
0x18001da79  test    r14, r14
0x18001da7c  jz      short loc_18001DA93
0x18001da7e  mov     r9, rdx; void *
0x18001da81  mov     qword ptr [rsp+1A0h+nSubAuthority2], r15; unsigned __int16 *
0x18001da86  mov     r8, r14; void *
0x18001da89  call    ?ResetRequestQueueAccess@HTTP_PROTOCOL@@AEAAXW4_ACCESS_MODE@@PEAX1PEBG@Z; HTTP_PROTOCOL::ResetRequestQueueAccess(_ACCESS_MODE,void *,void *,ushort const *)
0x18001da8e  mov     rdx, [rsp+1A0h+RequestQueueHandle]
0x18001da93  mov     [r12], rdx
0x18001da97  mov     ebx, esi
0x18001da99  mov     [rsp+1A0h+RequestQueueHandle], rsi
0x18001da9e  mov     rcx, [rsp+1A0h+pSid2]; pSid
0x18001daa3  test    rcx, rcx
0x18001daa6  jz      short loc_18001DAB3
0x18001daa8  call    cs:__imp_FreeSid
0x18001daae  mov     [rsp+1A0h+pSid2], rsi
0x18001dab3  mov     rcx, [rsp+1A0h+NewAcl]; hMem
0x18001dab8  test    rcx, rcx
0x18001dabb  jz      short loc_18001DAC8
0x18001dabd  call    cs:__imp_LocalFree
0x18001dac3  mov     [rsp+1A0h+NewAcl], rsi
0x18001dac8  mov     rcx, [rsp+1A0h+RequestQueueHandle]; RequestQueueHandle
0x18001dacd  test    rcx, rcx
0x18001dad0  jz      short loc_18001DADD
0x18001dad2  call    cs:__imp_HttpCloseRequestQueue
0x18001dad8  mov     [rsp+1A0h+RequestQueueHandle], rsi
0x18001dadd  lea     rcx, [rbp+0A0h+var_80]
0x18001dae1  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001dae7  mov     eax, ebx
0x18001dae9  mov     rcx, [rbp+0A0h+var_50]
0x18001daed  xor     rcx, rsp; StackCookie
0x18001daf0  call    __security_check_cookie
0x18001daf5  add     rsp, 168h
0x18001dafc  pop     r15
0x18001dafe  pop     r14
0x18001db00  pop     r13
0x18001db02  pop     r12
0x18001db04  pop     rdi
0x18001db05  pop     rsi
0x18001db06  pop     rbx
0x18001db07  pop     rbp
0x18001db08  retn
0x18001db09  xor     esi, esi
0x18001db0b  jmp     short loc_18001DA9E
```
