# NetrLogonComputeClientDigest

- ea: `0x18005abe0`
- end: `0x18005af2d`
- name: `NetrLogonComputeClientDigest`
- size: `845`
- prototype: `__int64 __fastcall(unsigned __int16 *, PCWSTR SourceString, unsigned __int8 *, unsigned int, char *, char *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003700`
- `0x180006860`
- `0x180007278`
- `0x180007b50`
- `0x18000bd98`
- `0x18000da94`
- `0x18000e270`
- `0x180025708`
- `0x18002601c`
- `0x18003e71c`
- `0x18003f054`
- `0x18003f540`
- `0x1800562f4`
- `0x180056e3c`
- `0x18005abe0`
- `0x180064f64`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005aeda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005af05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005aeda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005af05`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005acb7`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005acb7`

## string_xrefs

- `0x18005ac3c`: `NetrLogonComputeClientDigest: %ws: Message: `
- `0x18005acc6`: `NetrLogonComputeClientDigest: RtlInitUnicodeStringEx on DomainName failed: 0x%08x\n`
- `0x18005ad03`: `NetrLogonComputeClientDigest: %ws: No such trusted domain\n`
- `0x18005ad47`: `NetrLogonComputeClientDigest: cannot NlGetOutgoingPassword 0x%lx\n`
- `0x18005ada9`: `NetrLogonComputeClientDigest: cannot NlComputeMd5Digest (1) 0x%lx\n`
- `0x18005adca`: `NetrLogonComputeClientDigest: %ws: New Password: `
- `0x18005adec`: `NetrLogonComputeClientDigest: %ws: New Digest: `
- `0x18005ae24`: `NetrLogonComputeClientDigest: cannot NlComputeMd5Digest (2) 0x%lx\n`
- `0x18005ae33`: `NetrLogonComputeClientDigest: %ws: Old Password: `
- `0x18005ae57`: `NetrLogonComputeClientDigest: %ws: Old Digest: `

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
0x18005abe0  push    rbp
0x18005abe2  push    rbx
0x18005abe3  push    rsi
0x18005abe4  push    rdi
0x18005abe5  push    r12
0x18005abe7  push    r13
0x18005abe9  push    r14
0x18005abeb  push    r15
0x18005abed  lea     rbp, [rsp-0Fh]
0x18005abf2  sub     rsp, 98h
0x18005abf9  mov     rax, cs:__security_cookie
0x18005ac00  xor     rax, rsp
0x18005ac03  mov     [rbp+47h+var_48], rax
0x18005ac07  mov     rax, [rbp+47h+arg_20]
0x18005ac0b  xor     edi, edi
0x18005ac0d  xorps   xmm0, xmm0
0x18005ac10  mov     [rbp+47h+var_88], rax
0x18005ac14  mov     rax, [rbp+47h+arg_28]
0x18005ac18  mov     r12, r8
0x18005ac1b  mov     r14, rdx
0x18005ac1e  mov     [rbp+47h+var_80], rax
0x18005ac22  mov     rbx, rcx
0x18005ac25  mov     [rbp+47h+hMem], rdi
0x18005ac29  xorps   xmm1, xmm1
0x18005ac2c  mov     [rbp+47h+var_98], rdi
0x18005ac30  mov     r8, rdx
0x18005ac33  mov     [rbp+47h+var_90], edi
0x18005ac36  mov     r15d, 400000h
0x18005ac3c  lea     rdx, aNetrlogoncompu_31; "NetrLogonComputeClientDigest: %ws: Mess"...
0x18005ac43  mov     ecx, r15d; unsigned int
0x18005ac46  mov     r13d, r9d
0x18005ac49  mov     esi, edi
0x18005ac4b  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x18005ac4f  movups  xmmword ptr [rbp+47h+var_58.data.data], xmm0
0x18005ac53  movups  xmmword ptr [rbp+47h+var_68.data.data], xmm1
0x18005ac57  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005ac5c  mov     r8d, r13d; unsigned int
0x18005ac5f  mov     rdx, r12; void *
0x18005ac62  mov     ecx, r15d; unsigned int
0x18005ac65  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005ac6a  mov     rcx, cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA; pSecurityDescriptor
0x18005ac71  lea     r15d, [rdi+10h]
0x18005ac75  mov     edx, r15d; DesiredAccess
0x18005ac78  lea     r9d, [rdi+1]
0x18005ac7c  call    NetpAccessCheck2
0x18005ac81  test    eax, eax
0x18005ac83  jz      short loc_18005AC8D
0x18005ac85  lea     ebx, [rdi+5]
0x18005ac88  jmp     loc_18005AE78
0x18005ac8d  mov     rcx, rbx; unsigned __int16 *
0x18005ac90  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x18005ac95  mov     rdi, rax
0x18005ac98  test    rax, rax
0x18005ac9b  jnz     short loc_18005ACA7
0x18005ac9d  mov     ebx, 4BAh
0x18005aca2  jmp     loc_18005AE78
0x18005aca7  test    r14, r14
0x18005acaa  jnz     short loc_18005ACB0
0x18005acac  lea     r14, [rax+48h]
0x18005acb0  mov     rdx, r14; SourceString
0x18005acb3  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x18005acb7  call    cs:__imp_RtlInitUnicodeStringEx
0x18005acbd  mov     ebx, eax
0x18005acbf  test    eax, eax
0x18005acc1  jns     short loc_18005ACE5
0x18005acc3  mov     r8d, eax
0x18005acc6  lea     rdx, aNetrlogoncompu_2; "NetrLogonComputeClientDigest: RtlInitUn"...
0x18005accd  mov     ecx, 100h; unsigned int
0x18005acd2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005acd7  mov     ecx, ebx; Status
0x18005acd9  call    NetpNtStatusToApiStatus
0x18005acde  mov     ebx, eax
0x18005ace0  jmp     loc_18005AE78
0x18005ace5  xor     r9d, r9d; unsigned __int8 *
0x18005ace8  lea     rdx, [rbp+47h+DestinationString]; struct _UNICODE_STRING *
0x18005acec  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18005acef  lea     r8d, [r9+5]; unsigned int
0x18005acf3  call    ?NlFindNamedClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@KPEAE@Z; NlFindNamedClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,ulong,uchar *)
0x18005acf8  mov     rsi, rax
0x18005acfb  test    rax, rax
0x18005acfe  jnz     short loc_18005AD21
0x18005ad00  mov     r9, r14
0x18005ad03  lea     r8, aNetrlogoncompu_5; "NetrLogonComputeClientDigest: %ws: No s"...
0x18005ad0a  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005ad0d  mov     ecx, 100h; unsigned int
0x18005ad12  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005ad17  mov     ebx, 54Bh
0x18005ad1c  jmp     loc_18005AE78
0x18005ad21  lea     r9, [rbp+47h+var_90]; unsigned int *
0x18005ad25  mov     [rsp+0D0h+var_B0], 0; union _LARGE_INTEGER *
0x18005ad2e  lea     r8, [rbp+47h+var_98]; struct _UNICODE_STRING **
0x18005ad32  mov     rcx, rsi; struct _CLIENT_SESSION *
0x18005ad35  lea     rdx, [rbp+47h+hMem]; struct _UNICODE_STRING **
0x18005ad39  call    ?NlGetOutgoingPassword@@YAJPEAU_CLIENT_SESSION@@PEAPEAU_UNICODE_STRING@@1PEAKPEAT_LARGE_INTEGER@@@Z; NlGetOutgoingPassword(_CLIENT_SESSION *,_UNICODE_STRING * *,_UNICODE_STRING * *,ulong *,_LARGE_INTEGER *)
0x18005ad3e  mov     ebx, eax
0x18005ad40  test    eax, eax
0x18005ad42  jns     short loc_18005AD71
0x18005ad44  mov     r9d, eax
0x18005ad47  lea     r8, aNetrlogoncompu_20; "NetrLogonComputeClientDigest: cannot Nl"...
0x18005ad4e  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18005ad51  mov     ecx, 100h; unsigned int
0x18005ad56  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18005ad5b  mov     ecx, ebx; int
0x18005ad5d  call    ?NlpIsNtStatusResourceError@@YAEJ@Z; NlpIsNtStatusResourceError(long)
0x18005ad62  test    al, al
0x18005ad64  mov     ecx, 0C000018Ah
0x18005ad69  cmovz   ebx, ecx
0x18005ad6c  jmp     loc_18005ACD7
0x18005ad71  mov     r8, [rbp+47h+var_98]; struct _UNICODE_STRING *
0x18005ad75  lea     r9, [rbp+47h+var_68]; struct _LM_OWF_PASSWORD *
0x18005ad79  mov     rcx, [rbp+47h+hMem]; struct _UNICODE_STRING *
0x18005ad7d  lea     rdx, [rbp+47h+var_58]; struct _LM_OWF_PASSWORD *
0x18005ad81  call    ?NetpComputeNtOwfPasswords@@YAKPEAU_UNICODE_STRING@@PEAU_LM_OWF_PASSWORD@@01@Z; NetpComputeNtOwfPasswords(_UNICODE_STRING *,_LM_OWF_PASSWORD *,_UNICODE_STRING *,_LM_OWF_PASSWORD *)
0x18005ad86  mov     ebx, eax
0x18005ad88  test    eax, eax
0x18005ad8a  jnz     loc_18005AE78
0x18005ad90  mov     r9, [rbp+47h+var_88]; char *
0x18005ad94  lea     r8, [rbp+47h+var_58]; struct _LM_OWF_PASSWORD *
0x18005ad98  mov     edx, r13d; unsigned int
0x18005ad9b  mov     rcx, r12; unsigned __int8 *
0x18005ad9e  call    ?NlComputeMd5Digest@@YAKPEAEKPEAU_LM_OWF_PASSWORD@@QEAD@Z; NlComputeMd5Digest(uchar *,ulong,_LM_OWF_PASSWORD *,char * const)
0x18005ada3  mov     ebx, eax
0x18005ada5  test    eax, eax
0x18005ada7  jz      short loc_18005ADC5
0x18005ada9  lea     r8, aNetrlogoncompu_9; "NetrLogonComputeClientDigest: cannot Nl"...
0x18005adb0  mov     r9d, eax
0x18005adb3  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18005adb6  mov     ecx, 100h; unsigned int
0x18005adbb  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18005adc0  jmp     loc_18005AE78
0x18005adc5  mov     ebx, 400000h
0x18005adca  lea     rdx, aNetrlogoncompu_15; "NetrLogonComputeClientDigest: %ws: New "...
0x18005add1  mov     ecx, ebx; unsigned int
0x18005add3  mov     r8, r14
0x18005add6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005addb  mov     r8d, r15d; unsigned int
0x18005adde  lea     rdx, [rbp+47h+var_58]; void *
0x18005ade2  mov     ecx, ebx; unsigned int
0x18005ade4  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005ade9  mov     r8, r14
0x18005adec  lea     rdx, aNetrlogoncompu_27; "NetrLogonComputeClientDigest: %ws: New "...
0x18005adf3  mov     ecx, ebx; unsigned int
0x18005adf5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005adfa  mov     rdx, [rbp+47h+var_88]; void *
0x18005adfe  mov     r8d, 8; unsigned int
0x18005ae04  mov     ecx, ebx; unsigned int
0x18005ae06  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005ae0b  mov     r9, [rbp+47h+var_80]; char *
0x18005ae0f  lea     r8, [rbp+47h+var_68]; struct _LM_OWF_PASSWORD *
0x18005ae13  mov     edx, r13d; unsigned int
0x18005ae16  mov     rcx, r12; unsigned __int8 *
0x18005ae19  call    ?NlComputeMd5Digest@@YAKPEAEKPEAU_LM_OWF_PASSWORD@@QEAD@Z; NlComputeMd5Digest(uchar *,ulong,_LM_OWF_PASSWORD *,char * const)
0x18005ae1e  mov     ebx, eax
0x18005ae20  test    eax, eax
0x18005ae22  jz      short loc_18005AE2D
0x18005ae24  lea     r8, aNetrlogoncompu_32; "NetrLogonComputeClientDigest: cannot Nl"...
0x18005ae2b  jmp     short loc_18005ADB0
0x18005ae2d  mov     r12d, 400000h
0x18005ae33  lea     rdx, aNetrlogoncompu_29; "NetrLogonComputeClientDigest: %ws: Old "...
0x18005ae3a  mov     ecx, r12d; unsigned int
0x18005ae3d  mov     r8, r14
0x18005ae40  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005ae45  mov     r8d, r15d; unsigned int
0x18005ae48  lea     rdx, [rbp+47h+var_68]; void *
0x18005ae4c  mov     ecx, r12d; unsigned int
0x18005ae4f  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005ae54  mov     r8, r14
0x18005ae57  lea     rdx, aNetrlogoncompu_17; "NetrLogonComputeClientDigest: %ws: Old "...
0x18005ae5e  mov     ecx, r12d; unsigned int
0x18005ae61  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005ae66  mov     rdx, [rbp+47h+var_80]; void *
0x18005ae6a  mov     r8d, 8; unsigned int
0x18005ae70  mov     ecx, r12d; unsigned int
0x18005ae73  call    ?NlpDumpBuffer@@YAXKPEAXK@Z; NlpDumpBuffer(ulong,void *,ulong)
0x18005ae78  mov     rcx, r15
0x18005ae7b  lea     rax, [rbp+47h+var_68]
0x18005ae7f  mov     byte ptr [rax], 0
0x18005ae82  inc     rax
0x18005ae85  sub     rcx, 1
0x18005ae89  jnz     short loc_18005AE7F
0x18005ae8b  lea     rax, [rbp+47h+var_58]
0x18005ae8f  mov     byte ptr [rax], 0
0x18005ae92  inc     rax
0x18005ae95  sub     r15, 1
0x18005ae99  jnz     short loc_18005AE8F
0x18005ae9b  test    rsi, rsi
0x18005ae9e  jz      short loc_18005AEA8
0x18005aea0  mov     rcx, rsi; hMem
0x18005aea3  call    ?NlUnrefClientSession@@YAXPEAU_CLIENT_SESSION@@@Z; NlUnrefClientSession(_CLIENT_SESSION *)
0x18005aea8  test    rdi, rdi
0x18005aeab  jz      short loc_18005AEB5
0x18005aead  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18005aeb0  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x18005aeb5  mov     rcx, [rbp+47h+hMem]
0x18005aeb9  test    rcx, rcx
0x18005aebc  jz      short loc_18005AEE0
0x18005aebe  movzx   edx, word ptr [rcx]
0x18005aec1  mov     rax, [rcx+8]
0x18005aec5  test    rdx, rdx
0x18005aec8  jz      short loc_18005AEDA
0x18005aeca  mov     byte ptr [rax], 0
0x18005aecd  inc     rax
0x18005aed0  sub     rdx, 1
0x18005aed4  jnz     short loc_18005AECA
0x18005aed6  mov     rcx, [rbp+47h+hMem]; hMem
0x18005aeda  call    cs:__imp_LocalFree
0x18005aee0  mov     rcx, [rbp+47h+var_98]
0x18005aee4  test    rcx, rcx
0x18005aee7  jz      short loc_18005AF0B
0x18005aee9  movzx   edx, word ptr [rcx]
0x18005aeec  mov     rax, [rcx+8]
0x18005aef0  test    rdx, rdx
0x18005aef3  jz      short loc_18005AF05
0x18005aef5  mov     byte ptr [rax], 0
0x18005aef8  inc     rax
0x18005aefb  sub     rdx, 1
0x18005aeff  jnz     short loc_18005AEF5
0x18005af01  mov     rcx, [rbp+47h+var_98]; hMem
0x18005af05  call    cs:__imp_LocalFree
0x18005af0b  mov     eax, ebx
0x18005af0d  mov     rcx, [rbp+47h+var_48]
0x18005af11  xor     rcx, rsp; StackCookie
0x18005af14  call    __security_check_cookie
0x18005af19  add     rsp, 98h
0x18005af20  pop     r15
0x18005af22  pop     r14
0x18005af24  pop     r13
0x18005af26  pop     r12
0x18005af28  pop     rdi
0x18005af29  pop     rsi
0x18005af2a  pop     rbx
0x18005af2b  pop     rbp
0x18005af2c  retn
```
