# NetrLogonComputeClientDigest

- ea: `0x18005ee10`
- end: `0x18005f170`
- name: `NetrLogonComputeClientDigest`
- size: `864`
- prototype: `__int64 __fastcall(unsigned __int16 *, PCWSTR SourceString, unsigned __int8 *, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003890`
- `0x180006a94`
- `0x180007518`
- `0x180007e90`
- `0x18000c440`
- `0x18000e0e0`
- `0x18000e910`
- `0x1800267ec`
- `0x1800271d4`
- `0x180040f18`
- `0x180041944`
- `0x180041e68`
- `0x18005a070`
- `0x18005ac58`
- `0x18005ee10`
- `0x180069a30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f110`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f141`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f110`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f141`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005eee7`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005eee7`

## string_xrefs

- `0x18005ee6c`: `NetrLogonComputeClientDigest: %ws: Message: `
- `0x18005eefc`: `NetrLogonComputeClientDigest: RtlInitUnicodeStringEx on DomainName failed: 0x%08x\n`
- `0x18005ef39`: `NetrLogonComputeClientDigest: %ws: No such trusted domain\n`
- `0x18005ef7d`: `NetrLogonComputeClientDigest: cannot NlGetOutgoingPassword 0x%lx\n`
- `0x18005efdf`: `NetrLogonComputeClientDigest: cannot NlComputeMd5Digest (1) 0x%lx\n`
- `0x18005f000`: `NetrLogonComputeClientDigest: %ws: New Password: `
- `0x18005f022`: `NetrLogonComputeClientDigest: %ws: New Digest: `
- `0x18005f05a`: `NetrLogonComputeClientDigest: cannot NlComputeMd5Digest (2) 0x%lx\n`
- `0x18005f069`: `NetrLogonComputeClientDigest: %ws: Old Password: `
- `0x18005f08d`: `NetrLogonComputeClientDigest: %ws: Old Digest: `

## pseudocode

```c
__int64 __fastcall NetrLogonComputeClientDigest(
        unsigned __int16 *a1,
        PCWSTR SourceString,
        unsigned __int8 *a3,
        unsigned int a4,
        char *a5,
        char *a6)
{
  struct _DOMAIN_INFO *v6; // rdi
  const WCHAR *v8; // r14
  struct _CLIENT_SESSION *v11; // rsi
  __int64 v12; // r15
  __int64 v13; // r8
  unsigned int v14; // ebx
  struct _DOMAIN_INFO *DomainByServerName; // rax
  NTSTATUS inited; // eax
  NTSTATUS v17; // ebx
  struct _CLIENT_SESSION *NamedClientSession; // rax
  int OutgoingPassword; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  __int64 v22; // rcx
  struct _LM_OWF_PASSWORD *v23; // rax
  struct _LM_OWF_PASSWORD *v24; // rax
  HLOCAL v25; // rcx
  __int64 v26; // rdx
  _BYTE *v27; // rax
  HLOCAL v28; // rcx
  __int64 v29; // rdx
  _BYTE *v30; // rax
  HLOCAL hMem; // [rsp+30h] [rbp-59h] BYREF
  HLOCAL v33; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v34; // [rsp+40h] [rbp-49h] BYREF
  char *v35; // [rsp+48h] [rbp-41h]
  char *v36; // [rsp+50h] [rbp-39h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-31h] BYREF
  struct _LM_OWF_PASSWORD v38; // [rsp+68h] [rbp-21h] BYREF
  struct _LM_OWF_PASSWORD v39; // [rsp+78h] [rbp-11h] BYREF

  v6 = 0;
  v35 = a5;
  v8 = SourceString;
  v36 = a6;
  hMem = 0;
  v33 = 0;
  v34 = 0;
  v11 = 0;
  DestinationString = 0;
  v39 = 0;
  v38 = 0;
  NlPrintRoutine(0x400000u, L"NetrLogonComputeClientDigest: %ws: Message: ", SourceString);
  NlpDumpBuffer(0x400000u, a3, a4);
  v12 = 16;
  if ( NetpAccessCheck2(NlGlobalNetlogonSecurityDescriptor, 0x10u, v13, 1) )
  {
    v14 = 5;
    goto LABEL_23;
  }
  DomainByServerName = NlFindDomainByServerName(a1);
  v6 = DomainByServerName;
  if ( !DomainByServerName )
  {
    v14 = 1210;
    goto LABEL_23;
  }
  if ( !v8 )
    v8 = (const WCHAR *)((char *)DomainByServerName + 72);
  inited = RtlInitUnicodeStringEx(&DestinationString, v8);
  v17 = inited;
  if ( inited < 0 )
  {
    NlPrintRoutine(
      0x100u,
      L"NetrLogonComputeClientDigest: RtlInitUnicodeStringEx on DomainName failed: 0x%08x\n",
      (unsigned int)inited);
LABEL_9:
    v14 = NetpNtStatusToApiStatus(v17);
    goto LABEL_23;
  }
  NamedClientSession = NlFindNamedClientSession(v6, &DestinationString, 5u, 0);
  v11 = NamedClientSession;
  if ( !NamedClientSession )
  {
    NlPrintDomRoutine(0x100u, v6, L"NetrLogonComputeClientDigest: %ws: No such trusted domain\n", v8);
    v14 = 1355;
    goto LABEL_23;
  }
  OutgoingPassword = NlGetOutgoingPassword(
                       NamedClientSession,
                       (struct _UNICODE_STRING **)&hMem,
                       (struct _UNICODE_STRING **)&v33,
                       &v34,
                       0);
  v17 = OutgoingPassword;
  if ( OutgoingPassword < 0 )
  {
    NlPrintCsRoutine(
      0x100u,
      v11,
      L"NetrLogonComputeClientDigest: cannot NlGetOutgoingPassword 0x%lx\n",
      (unsigned int)OutgoingPassword);
    if ( !NlpIsNtStatusResourceError(v17) )
      v17 = -1073741430;
    goto LABEL_9;
  }
  v14 = NetpComputeNtOwfPasswords((struct _UNICODE_STRING *)hMem, &v39, (struct _UNICODE_STRING *)v33, &v38);
  if ( !v14 )
  {
    v20 = NlComputeMd5Digest(a3, a4, &v39, v35);
    v14 = v20;
    if ( v20 )
    {
      NlPrintCsRoutine(0x100u, v11, L"NetrLogonComputeClientDigest: cannot NlComputeMd5Digest (1) 0x%lx\n", v20);
    }
    else
    {
      NlPrintRoutine(0x400000u, L"NetrLogonComputeClientDigest: %ws: New Password: ", v8);
      NlpDumpBuffer(0x400000u, &v39, 0x10u);
      NlPrintRoutine(0x400000u, L"NetrLogonComputeClientDigest: %ws: New Digest: ", v8);
      NlpDumpBuffer(0x400000u, v35, 8u);
      v21 = NlComputeMd5Digest(a3, a4, &v38, v36);
      v14 = v21;
      if ( v21 )
      {
        NlPrintCsRoutine(0x100u, v11, L"NetrLogonComputeClientDigest: cannot NlComputeMd5Digest (2) 0x%lx\n", v21);
      }
      else
      {
        NlPrintRoutine(0x400000u, L"NetrLogonComputeClientDigest: %ws: Old Password: ", v8);
        NlpDumpBuffer(0x400000u, &v38, 0x10u);
        NlPrintRoutine(0x400000u, L"NetrLogonComputeClientDigest: %ws: Old Digest: ", v8);
        NlpDumpBuffer(0x400000u, v36, 8u);
      }
    }
  }
LABEL_23:
  v22 = 16;
  v23 = &v38;
  do
  {
    v23->data[0].data[0] = 0;
    v23 = (struct _LM_OWF_PASSWORD *)((char *)v23 + 1);
    --v22;
  }
  while ( v22 );
  v24 = &v39;
  do
  {
    v24->data[0].data[0] = 0;
    v24 = (struct _LM_OWF_PASSWORD *)((char *)v24 + 1);
    --v12;
  }
  while ( v12 );
  if ( v11 )
    NlUnrefClientSession(v11);
  if ( v6 )
    NlDereferenceDomain(v6);
  v25 = hMem;
  if ( hMem )
  {
    v26 = *(unsigned __int16 *)hMem;
    v27 = (_BYTE *)*((_QWORD *)hMem + 1);
    if ( *(_WORD *)hMem )
    {
      do
      {
        *v27++ = 0;
        --v26;
      }
      while ( v26 );
      v25 = hMem;
    }
    LocalFree(v25);
  }
  v28 = v33;
  if ( v33 )
  {
    v29 = *(unsigned __int16 *)v33;
    v30 = (_BYTE *)*((_QWORD *)v33 + 1);
    if ( *(_WORD *)v33 )
    {
      do
      {
        *v30++ = 0;
        --v29;
      }
      while ( v29 );
      v28 = v33;
    }
    LocalFree(v28);
  }
  return v14;
}

```

## disassembly

```asm
0x18005ee10  push    rbp
0x18005ee12  push    rbx
0x18005ee13  push    rsi
0x18005ee14  push    rdi
0x18005ee15  push    r12
0x18005ee17  push    r13
0x18005ee19  push    r14
0x18005ee1b  push    r15
0x18005ee1d  lea     rbp, [rsp-0Fh]
0x18005ee22  sub     rsp, 98h
0x18005ee29  mov     rax, cs:__security_cookie
0x18005ee30  xor     rax, rsp
0x18005ee33  mov     [rbp+47h+var_48], rax
0x18005ee37  mov     rax, [rbp+47h+arg_20]
0x18005ee3b  xor     edi, edi
0x18005ee3d  xorps   xmm0, xmm0
0x18005ee40  mov     [rbp+47h+var_88], rax
0x18005ee44  mov     rax, [rbp+47h+arg_28]
0x18005ee48  mov     r12, r8
0x18005ee4b  mov     r14, rdx
0x18005ee4e  mov     [rbp+47h+var_80], rax
0x18005ee52  mov     rbx, rcx
0x18005ee55  mov     [rbp+47h+hMem], rdi
0x18005ee59  xorps   xmm1, xmm1
0x18005ee5c  mov     [rbp+47h+var_98], rdi
0x18005ee60  mov     r8, rdx
0x18005ee63  mov     [rbp+47h+var_90], edi
0x18005ee66  mov     r15d, 400000h
0x18005ee6c  lea     rdx, aNetrlogoncompu_31; "NetrLogonComputeClientDigest: %ws: Mess"...
0x18005ee73  mov     ecx, r15d; unsigned int
0x18005ee76  mov     r13d, r9d
0x18005ee79  mov     esi, edi
0x18005ee7b  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x18005ee7f  movups  xmmword ptr [rbp+47h+var_58.data.data], xmm0
0x18005ee83  movups  xmmword ptr [rbp+47h+var_68.data.data], xmm1
0x18005ee87  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005ee8c  mov     r8d, r13d; unsigned int
0x18005ee8f  mov     rdx, r12; void *
0x18005ee92  mov     ecx, r15d; unsigned int
0x18005ee95  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005ee9a  mov     rcx, cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA; pSecurityDescriptor
0x18005eea1  lea     r15d, [rdi+10h]
0x18005eea5  mov     edx, r15d; DesiredAccess
0x18005eea8  lea     r9d, [rdi+1]
0x18005eeac  call    NetpAccessCheck2
0x18005eeb1  test    eax, eax
0x18005eeb3  jz      short loc_18005EEBD
0x18005eeb5  lea     ebx, [rdi+5]
0x18005eeb8  jmp     loc_18005F0AE
0x18005eebd  mov     rcx, rbx; unsigned __int16 *
0x18005eec0  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x18005eec5  mov     rdi, rax
0x18005eec8  test    rax, rax
0x18005eecb  jnz     short loc_18005EED7
0x18005eecd  mov     ebx, 4BAh
0x18005eed2  jmp     loc_18005F0AE
0x18005eed7  test    r14, r14
0x18005eeda  jnz     short loc_18005EEE0
0x18005eedc  lea     r14, [rax+48h]
0x18005eee0  mov     rdx, r14; SourceString
0x18005eee3  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x18005eee7  call    cs:__imp_RtlInitUnicodeStringEx
0x18005eeee  nop     dword ptr [rax+rax+00h]
0x18005eef3  mov     ebx, eax
0x18005eef5  test    eax, eax
0x18005eef7  jns     short loc_18005EF1B
0x18005eef9  mov     r8d, eax
0x18005eefc  lea     rdx, aNetrlogoncompu_2; "NetrLogonComputeClientDigest: RtlInitUn"...
0x18005ef03  mov     ecx, 100h; unsigned int
0x18005ef08  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005ef0d  mov     ecx, ebx; Status
0x18005ef0f  call    NetpNtStatusToApiStatus
0x18005ef14  mov     ebx, eax
0x18005ef16  jmp     loc_18005F0AE
0x18005ef1b  xor     r9d, r9d; unsigned __int8 *
0x18005ef1e  lea     rdx, [rbp+47h+DestinationString]; struct _UNICODE_STRING *
0x18005ef22  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18005ef25  lea     r8d, [r9+5]; unsigned int
0x18005ef29  call    ?NlFindNamedClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@KPEAE@Z; NlFindNamedClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,ulong,uchar *)
0x18005ef2e  mov     rsi, rax
0x18005ef31  test    rax, rax
0x18005ef34  jnz     short loc_18005EF57
0x18005ef36  mov     r9, r14
0x18005ef39  lea     r8, aNetrlogoncompu_5; "NetrLogonComputeClientDigest: %ws: No s"...
0x18005ef40  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005ef43  mov     ecx, 100h; unsigned int
0x18005ef48  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005ef4d  mov     ebx, 54Bh
0x18005ef52  jmp     loc_18005F0AE
0x18005ef57  lea     r9, [rbp+47h+var_90]; unsigned int *
0x18005ef5b  mov     [rsp+0D0h+var_B0], 0; union _LARGE_INTEGER *
0x18005ef64  lea     r8, [rbp+47h+var_98]; struct _UNICODE_STRING **
0x18005ef68  mov     rcx, rsi; struct _CLIENT_SESSION *
0x18005ef6b  lea     rdx, [rbp+47h+hMem]; struct _UNICODE_STRING **
0x18005ef6f  call    ?NlGetOutgoingPassword@@YAJPEAU_CLIENT_SESSION@@PEAPEAU_UNICODE_STRING@@1PEAKPEAT_LARGE_INTEGER@@@Z; NlGetOutgoingPassword(_CLIENT_SESSION *,_UNICODE_STRING * *,_UNICODE_STRING * *,ulong *,_LARGE_INTEGER *)
0x18005ef74  mov     ebx, eax
0x18005ef76  test    eax, eax
0x18005ef78  jns     short loc_18005EFA7
0x18005ef7a  mov     r9d, eax
0x18005ef7d  lea     r8, aNetrlogoncompu_20; "NetrLogonComputeClientDigest: cannot Nl"...
0x18005ef84  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18005ef87  mov     ecx, 100h; unsigned int
0x18005ef8c  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18005ef91  mov     ecx, ebx; int
0x18005ef93  call    ?NlpIsNtStatusResourceError@@YAEJ@Z; NlpIsNtStatusResourceError(long)
0x18005ef98  test    al, al
0x18005ef9a  mov     ecx, 0C000018Ah
0x18005ef9f  cmovz   ebx, ecx
0x18005efa2  jmp     loc_18005EF0D
0x18005efa7  mov     r8, [rbp+47h+var_98]; struct _UNICODE_STRING *
0x18005efab  lea     r9, [rbp+47h+var_68]; struct _LM_OWF_PASSWORD *
0x18005efaf  mov     rcx, [rbp+47h+hMem]; struct _UNICODE_STRING *
0x18005efb3  lea     rdx, [rbp+47h+var_58]; struct _LM_OWF_PASSWORD *
0x18005efb7  call    ?NetpComputeNtOwfPasswords@@YAKPEAU_UNICODE_STRING@@PEAU_LM_OWF_PASSWORD@@01@Z; NetpComputeNtOwfPasswords(_UNICODE_STRING *,_LM_OWF_PASSWORD *,_UNICODE_STRING *,_LM_OWF_PASSWORD *)
0x18005efbc  mov     ebx, eax
0x18005efbe  test    eax, eax
0x18005efc0  jnz     loc_18005F0AE
0x18005efc6  mov     r9, [rbp+47h+var_88]; char *
0x18005efca  lea     r8, [rbp+47h+var_58]; struct _LM_OWF_PASSWORD *
0x18005efce  mov     edx, r13d; unsigned int
0x18005efd1  mov     rcx, r12; unsigned __int8 *
0x18005efd4  call    ?NlComputeMd5Digest@@YAKPEAEKPEAU_LM_OWF_PASSWORD@@QEAD@Z; NlComputeMd5Digest(uchar *,ulong,_LM_OWF_PASSWORD *,char * const)
0x18005efd9  mov     ebx, eax
0x18005efdb  test    eax, eax
0x18005efdd  jz      short loc_18005EFFB
0x18005efdf  lea     r8, aNetrlogoncompu_9; "NetrLogonComputeClientDigest: cannot Nl"...
0x18005efe6  mov     r9d, eax
0x18005efe9  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18005efec  mov     ecx, 100h; unsigned int
0x18005eff1  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18005eff6  jmp     loc_18005F0AE
0x18005effb  mov     ebx, 400000h
0x18005f000  lea     rdx, aNetrlogoncompu_15; "NetrLogonComputeClientDigest: %ws: New "...
0x18005f007  mov     ecx, ebx; unsigned int
0x18005f009  mov     r8, r14
0x18005f00c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005f011  mov     r8d, r15d; unsigned int
0x18005f014  lea     rdx, [rbp+47h+var_58]; void *
0x18005f018  mov     ecx, ebx; unsigned int
0x18005f01a  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005f01f  mov     r8, r14
0x18005f022  lea     rdx, aNetrlogoncompu_27; "NetrLogonComputeClientDigest: %ws: New "...
0x18005f029  mov     ecx, ebx; unsigned int
0x18005f02b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005f030  mov     rdx, [rbp+47h+var_88]; void *
0x18005f034  mov     r8d, 8; unsigned int
0x18005f03a  mov     ecx, ebx; unsigned int
0x18005f03c  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005f041  mov     r9, [rbp+47h+var_80]; char *
0x18005f045  lea     r8, [rbp+47h+var_68]; struct _LM_OWF_PASSWORD *
0x18005f049  mov     edx, r13d; unsigned int
0x18005f04c  mov     rcx, r12; unsigned __int8 *
0x18005f04f  call    ?NlComputeMd5Digest@@YAKPEAEKPEAU_LM_OWF_PASSWORD@@QEAD@Z; NlComputeMd5Digest(uchar *,ulong,_LM_OWF_PASSWORD *,char * const)
0x18005f054  mov     ebx, eax
0x18005f056  test    eax, eax
0x18005f058  jz      short loc_18005F063
0x18005f05a  lea     r8, aNetrlogoncompu_32; "NetrLogonComputeClientDigest: cannot Nl"...
0x18005f061  jmp     short loc_18005EFE6
0x18005f063  mov     r12d, 400000h
0x18005f069  lea     rdx, aNetrlogoncompu_29; "NetrLogonComputeClientDigest: %ws: Old "...
0x18005f070  mov     ecx, r12d; unsigned int
0x18005f073  mov     r8, r14
0x18005f076  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005f07b  mov     r8d, r15d; unsigned int
0x18005f07e  lea     rdx, [rbp+47h+var_68]; void *
0x18005f082  mov     ecx, r12d; unsigned int
0x18005f085  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005f08a  mov     r8, r14
0x18005f08d  lea     rdx, aNetrlogoncompu_17; "NetrLogonComputeClientDigest: %ws: Old "...
0x18005f094  mov     ecx, r12d; unsigned int
0x18005f097  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005f09c  mov     rdx, [rbp+47h+var_80]; void *
0x18005f0a0  mov     r8d, 8; unsigned int
0x18005f0a6  mov     ecx, r12d; unsigned int
0x18005f0a9  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005f0ae  mov     rcx, r15
0x18005f0b1  lea     rax, [rbp+47h+var_68]
0x18005f0b5  mov     byte ptr [rax], 0
0x18005f0b8  inc     rax
0x18005f0bb  sub     rcx, 1
0x18005f0bf  jnz     short loc_18005F0B5
0x18005f0c1  lea     rax, [rbp+47h+var_58]
0x18005f0c5  mov     byte ptr [rax], 0
0x18005f0c8  inc     rax
0x18005f0cb  sub     r15, 1
0x18005f0cf  jnz     short loc_18005F0C5
0x18005f0d1  test    rsi, rsi
0x18005f0d4  jz      short loc_18005F0DE
0x18005f0d6  mov     rcx, rsi; hMem
0x18005f0d9  call    ?NlUnrefClientSession@@YAXPEAU_CLIENT_SESSION@@@Z; NlUnrefClientSession(_CLIENT_SESSION *)
0x18005f0de  test    rdi, rdi
0x18005f0e1  jz      short loc_18005F0EB
0x18005f0e3  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18005f0e6  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x18005f0eb  mov     rcx, [rbp+47h+hMem]
0x18005f0ef  test    rcx, rcx
0x18005f0f2  jz      short loc_18005F11C
0x18005f0f4  movzx   edx, word ptr [rcx]
0x18005f0f7  mov     rax, [rcx+8]
0x18005f0fb  test    rdx, rdx
0x18005f0fe  jz      short loc_18005F110
0x18005f100  mov     byte ptr [rax], 0
0x18005f103  inc     rax
0x18005f106  sub     rdx, 1
0x18005f10a  jnz     short loc_18005F100
0x18005f10c  mov     rcx, [rbp+47h+hMem]; hMem
0x18005f110  call    cs:__imp_LocalFree
0x18005f117  nop     dword ptr [rax+rax+00h]
0x18005f11c  mov     rcx, [rbp+47h+var_98]
0x18005f120  test    rcx, rcx
0x18005f123  jz      short loc_18005F14D
0x18005f125  movzx   edx, word ptr [rcx]
0x18005f128  mov     rax, [rcx+8]
0x18005f12c  test    rdx, rdx
0x18005f12f  jz      short loc_18005F141
0x18005f131  mov     byte ptr [rax], 0
0x18005f134  inc     rax
0x18005f137  sub     rdx, 1
0x18005f13b  jnz     short loc_18005F131
0x18005f13d  mov     rcx, [rbp+47h+var_98]; hMem
0x18005f141  call    cs:__imp_LocalFree
0x18005f148  nop     dword ptr [rax+rax+00h]
0x18005f14d  mov     eax, ebx
0x18005f14f  mov     rcx, [rbp+47h+var_48]
0x18005f153  xor     rcx, rsp; StackCookie
0x18005f156  call    __security_check_cookie
0x18005f15b  add     rsp, 98h
0x18005f162  pop     r15
0x18005f164  pop     r14
0x18005f166  pop     r13
0x18005f168  pop     r12
0x18005f16a  pop     rdi
0x18005f16b  pop     rsi
0x18005f16c  pop     rbx
0x18005f16d  pop     rbp
0x18005f16e  retn
```
