# NetpQueryDelegatedManagedServiceAccount(ushort const *,_MSA_INFO_LEVEL,_MSA_INFO_BUFFER *)

- ea: `0x1800746dc`
- end: `0x18007491f`
- name: `?NetpQueryDelegatedManagedServiceAccount@@YAJPEBGW4_MSA_INFO_LEVEL@@PEAT_MSA_INFO_BUFFER@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(PCWSTR SourceString, enum _MSA_INFO_LEVEL, union _MSA_INFO_BUFFER *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a838`

## callees

- `0x180004420`
- `0x180007278`
- `0x180008818`
- `0x180008b50`
- `0x18000d100`
- `0x1800746dc`
- `0x180083180`

## import_xrefs

- `ntdll!RtlEqualDomainName` at `0x1800747c5`
- `ntdll!RtlEqualDomainName` at `0x1800747c5`
- `ntdll!RtlInitUnicodeString` at `0x18007475f`
- `ntdll!RtlInitUnicodeString` at `0x1800747b0`
- `ntdll!RtlInitUnicodeString` at `0x180074845`
- `ntdll!RtlInitUnicodeString` at `0x180074853`
- `ntdll!RtlInitUnicodeString` at `0x18007475f`
- `ntdll!RtlInitUnicodeString` at `0x1800747b0`
- `ntdll!RtlInitUnicodeString` at `0x180074845`
- `ntdll!RtlInitUnicodeString` at `0x180074853`
- `netutils!NetApiBufferFree` at `0x1800748be`
- `netutils!NetApiBufferFree` at `0x1800748be`
- `SAMLIB!SamiAccountIsDelegateManagedServiceAccount` at `0x180074869`
- `SAMLIB!SamiAccountIsDelegateManagedServiceAccount` at `0x180074869`

## string_xrefs

- `0x180074742`: `Entering NetpQueryDelegatedManagedServiceAccount for account %s, Level %u\n`
- `0x180074829`: `NetpQueryDelegatedManagedServiceAccount: Failed to find usable DC\n`
- `0x180074875`: `NetpQueryDelegatedManagedServiceAccount: Failed to call SAM to check if account is a dMSA\n`
- `0x1800748f5`: `Exiting NetpQueryDelegatedManagedServiceAccount for account %s, Status 0x%08X\n`

## pseudocode

```c
__int64 __fastcall NetpQueryDelegatedManagedServiceAccount(
        PCWSTR SourceString,
        enum _MSA_INFO_LEVEL a2,
        union _MSA_INFO_BUFFER *a3)
{
  const struct _UNICODE_STRING *v5; // rdx
  int v6; // eax
  int IsDelegateManagedServiceAccount; // ebx
  unsigned int v8; // ebx
  unsigned int DcNameEx2; // eax
  int v10; // eax
  PCWSTR v12; // [rsp+40h] [rbp-19h] BYREF
  LPVOID Buffer; // [rsp+48h] [rbp-11h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-1h] BYREF
  struct _UNICODE_STRING DomainName1; // [rsp+68h] [rbp+Fh] BYREF
  struct _UNICODE_STRING v17; // [rsp+78h] [rbp+1Fh] BYREF
  enum _MSA_INFO_LEVEL v18; // [rsp+C8h] [rbp+6Fh] BYREF
  char v19; // [rsp+D0h] [rbp+77h] BYREF
  PCWSTR SourceStringa; // [rsp+D8h] [rbp+7Fh] BYREF

  v18 = a2;
  Buffer = 0;
  LOBYTE(v18) = 0;
  v19 = 0;
  hMem = 0;
  v12 = 0;
  SourceStringa = 0;
  v17 = 0;
  DestinationString = 0;
  DomainName1 = 0;
  if ( !a3 )
    return 3221225485LL;
  NlPrintRoutine(0x40u, L"Entering NetpQueryDelegatedManagedServiceAccount for account %s, Level %u\n", SourceString);
  RtlInitUnicodeString(&DestinationString, SourceString);
  v6 = DmsapParseAccountNames(
         &DestinationString,
         v5,
         (unsigned __int16 **)&hMem,
         (unsigned __int16 **)&v12,
         (unsigned __int16 **)&SourceStringa);
  IsDelegateManagedServiceAccount = v6;
  if ( v6 >= 0 )
  {
    v8 = 1107296256;
    if ( SourceStringa )
    {
      RtlInitUnicodeString(&DomainName1, SourceStringa);
      if ( !RtlEqualDomainName(&DomainName1, (PUNICODE_STRING)((char *)NlGlobalDomainInfo + 56))
        && !(unsigned int)NlEqualDnsNameU(&DomainName1, (struct _UNICODE_STRING *)((char *)NlGlobalDomainInfo + 56)) )
      {
        v8 = 1107300352;
      }
    }
    DcNameEx2 = DsrGetDcNameEx2(
                  0,
                  0,
                  0,
                  (unsigned __int16 *)SourceStringa,
                  0,
                  0,
                  v8,
                  (struct _DOMAIN_CONTROLLER_INFOW **)&Buffer);
    IsDelegateManagedServiceAccount = NetpApiStatusToNtStatus(DcNameEx2);
    if ( IsDelegateManagedServiceAccount >= 0 )
    {
      RtlInitUnicodeString(&v17, *(PCWSTR *)Buffer);
      RtlInitUnicodeString(&DestinationString, v12);
      IsDelegateManagedServiceAccount = SamiAccountIsDelegateManagedServiceAccount(&v17, &DestinationString, &v18, &v19);
      if ( IsDelegateManagedServiceAccount >= 0 )
      {
        if ( *(_QWORD *)a3 )
        {
          if ( !(_BYTE)v18 || (v10 = 5, !v19) )
            v10 = 2;
          **(_DWORD **)a3 = v10;
          *(_DWORD *)(*(_QWORD *)a3 + 4LL) = (_BYTE)v18 != MsaInfoLevel0 ? 3 : 0;
        }
        else
        {
          IsDelegateManagedServiceAccount = -1073741811;
        }
      }
      else
      {
        NlPrintRoutine(
          0x40u,
          L"NetpQueryDelegatedManagedServiceAccount: Failed to call SAM to check if account is a dMSA\n");
      }
    }
    else
    {
      NlPrintRoutine(0x40u, L"NetpQueryDelegatedManagedServiceAccount: Failed to find usable DC\n");
    }
  }
  else
  {
    NlPrintRoutine(0x40u, L"GmsapParseAccountNamesLocally failed %#x\n", (unsigned int)v6);
  }
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( hMem )
    DmsapFreeStringRoutine(hMem);
  if ( v12 )
    DmsapFreeStringRoutine((HLOCAL)v12);
  if ( SourceStringa )
    DmsapFreeStringRoutine((HLOCAL)SourceStringa);
  NlPrintRoutine(
    0x40u,
    L"Exiting NetpQueryDelegatedManagedServiceAccount for account %s, Status 0x%08X\n",
    SourceString,
    (unsigned int)IsDelegateManagedServiceAccount);
  return (unsigned int)IsDelegateManagedServiceAccount;
}

```

## disassembly

```asm
0x1800746dc  mov     [rsp-8+arg_8], edx
0x1800746e0  push    rbp
0x1800746e1  push    rbx
0x1800746e2  push    rsi
0x1800746e3  push    r13
0x1800746e5  push    r15
0x1800746e7  lea     rbp, [rsp-37h]
0x1800746ec  sub     rsp, 90h
0x1800746f3  mov     [rbp+57h+Buffer], 0
0x1800746fb  xorps   xmm0, xmm0
0x1800746fe  mov     byte ptr [rbp+57h+arg_8], 0
0x180074702  xorps   xmm1, xmm1
0x180074705  mov     [rbp+57h+arg_10], 0
0x180074709  mov     rsi, r8
0x18007470c  mov     [rbp+57h+hMem], 0
0x180074714  mov     r15, rcx
0x180074717  mov     [rbp+57h+var_70], 0
0x18007471f  mov     [rbp+57h+SourceString], 0
0x180074727  movups  xmmword ptr [rbp+57h+var_38.Length], xmm0
0x18007472b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18007472f  movups  xmmword ptr [rbp+57h+DomainName1.Length], xmm0
0x180074733  test    r8, r8
0x180074736  jz      loc_18007490B
0x18007473c  mov     r9d, 1
0x180074742  lea     rdx, aEnteringNetpqu_1; "Entering NetpQueryDelegatedManagedServi"...
0x180074749  mov     r8, rcx
0x18007474c  lea     r13d, [r9+3Fh]
0x180074750  mov     ecx, r13d; unsigned int
0x180074753  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180074758  mov     rdx, r15; SourceString
0x18007475b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18007475f  call    cs:__imp_RtlInitUnicodeString
0x180074765  lea     rax, [rbp+57h+SourceString]
0x180074769  lea     r9, [rbp+57h+var_70]; unsigned __int16 **
0x18007476d  mov     [rsp+0B0h+var_90], rax; unsigned __int16 **
0x180074772  lea     r8, [rbp+57h+hMem]; unsigned __int16 **
0x180074776  lea     rcx, [rbp+57h+DestinationString]; SourceString
0x18007477a  call    ?DmsapParseAccountNames@@YAJPEBU_UNICODE_STRING@@0PEAPEAG11@Z; DmsapParseAccountNames(_UNICODE_STRING const *,_UNICODE_STRING const *,ushort * *,ushort * *,ushort * *)
0x18007477f  mov     ebx, eax
0x180074781  test    eax, eax
0x180074783  jns     short loc_18007479C
0x180074785  mov     r8d, eax
0x180074788  lea     rdx, aGmsapparseacco; "GmsapParseAccountNamesLocally failed %#"...
0x18007478f  mov     ecx, r13d; unsigned int
0x180074792  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180074797  jmp     loc_1800748B5
0x18007479c  cmp     [rbp+57h+SourceString], 0
0x1800747a1  mov     ebx, 42000000h
0x1800747a6  jz      short loc_1800747ED
0x1800747a8  mov     rdx, [rbp+57h+SourceString]; SourceString
0x1800747ac  lea     rcx, [rbp+57h+DomainName1]; DestinationString
0x1800747b0  call    cs:__imp_RtlInitUnicodeString
0x1800747b6  mov     rdx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x1800747bd  lea     rcx, [rbp+57h+DomainName1]; DomainName1
0x1800747c1  add     rdx, 38h ; '8'; DomainName2
0x1800747c5  call    cs:__imp_RtlEqualDomainName
0x1800747cb  test    al, al
0x1800747cd  jnz     short loc_1800747ED
0x1800747cf  mov     rdx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x1800747d6  lea     rcx, [rbp+57h+DomainName1]; struct _UNICODE_STRING *
0x1800747da  add     rdx, 38h ; '8'; struct _UNICODE_STRING *
0x1800747de  call    ?NlEqualDnsNameU@@YAHPEAU_UNICODE_STRING@@0@Z; NlEqualDnsNameU(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800747e3  test    eax, eax
0x1800747e5  mov     ecx, 42001000h
0x1800747ea  cmovz   ebx, ecx
0x1800747ed  mov     r9, [rbp+57h+SourceString]
0x1800747f1  lea     rax, [rbp+57h+Buffer]
0x1800747f5  mov     [rsp+0B0h+var_78], rax
0x1800747fa  xor     r8d, r8d
0x1800747fd  mov     [rsp+0B0h+var_80], ebx
0x180074801  xor     edx, edx
0x180074803  mov     [rsp+0B0h+var_88], 0
0x18007480c  xor     ecx, ecx
0x18007480e  mov     [rsp+0B0h+var_90], 0
0x180074817  call    DsrGetDcNameEx2
0x18007481c  mov     ecx, eax
0x18007481e  call    NetpApiStatusToNtStatus
0x180074823  mov     ebx, eax
0x180074825  test    eax, eax
0x180074827  jns     short loc_18007483A
0x180074829  lea     rdx, aNetpquerydeleg_0; "NetpQueryDelegatedManagedServiceAccount"...
0x180074830  mov     ecx, r13d; unsigned int
0x180074833  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180074838  jmp     short loc_1800748B5
0x18007483a  mov     rdx, [rbp+57h+Buffer]
0x18007483e  lea     rcx, [rbp+57h+var_38]; DestinationString
0x180074842  mov     rdx, [rdx]; SourceString
0x180074845  call    cs:__imp_RtlInitUnicodeString
0x18007484b  mov     rdx, [rbp+57h+var_70]; SourceString
0x18007484f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180074853  call    cs:__imp_RtlInitUnicodeString
0x180074859  lea     r9, [rbp+57h+arg_10]
0x18007485d  lea     r8, [rbp+57h+arg_8]
0x180074861  lea     rdx, [rbp+57h+DestinationString]
0x180074865  lea     rcx, [rbp+57h+var_38]
0x180074869  call    cs:__imp_SamiAccountIsDelegateManagedServiceAccount
0x18007486f  mov     ebx, eax
0x180074871  test    eax, eax
0x180074873  jns     short loc_18007487E
0x180074875  lea     rdx, aNetpquerydeleg_1; "NetpQueryDelegatedManagedServiceAccount"...
0x18007487c  jmp     short loc_180074830
0x18007487e  mov     rcx, [rsi]
0x180074881  test    rcx, rcx
0x180074884  jnz     short loc_18007488D
0x180074886  mov     ebx, 0C000000Dh
0x18007488b  jmp     short loc_1800748B5
0x18007488d  cmp     byte ptr [rbp+57h+arg_8], 0
0x180074891  jz      short loc_18007489E
0x180074893  cmp     [rbp+57h+arg_10], 0
0x180074897  mov     eax, 5
0x18007489c  jnz     short loc_1800748A3
0x18007489e  mov     eax, 2
0x1800748a3  mov     [rcx], eax
0x1800748a5  mov     al, byte ptr [rbp+57h+arg_8]
0x1800748a8  neg     al
0x1800748aa  mov     rax, [rsi]
0x1800748ad  sbb     ecx, ecx
0x1800748af  and     ecx, 3
0x1800748b2  mov     [rax+4], ecx
0x1800748b5  mov     rcx, [rbp+57h+Buffer]; Buffer
0x1800748b9  test    rcx, rcx
0x1800748bc  jz      short loc_1800748C4
0x1800748be  call    cs:__imp_NetApiBufferFree
0x1800748c4  mov     rcx, [rbp+57h+hMem]; hMem
0x1800748c8  test    rcx, rcx
0x1800748cb  jz      short loc_1800748D2
0x1800748cd  call    DmsapFreeStringRoutine
0x1800748d2  cmp     [rbp+57h+var_70], 0
0x1800748d7  jz      short loc_1800748E2
0x1800748d9  mov     rcx, [rbp+57h+var_70]; hMem
0x1800748dd  call    DmsapFreeStringRoutine
0x1800748e2  cmp     [rbp+57h+SourceString], 0
0x1800748e7  jz      short loc_1800748F2
0x1800748e9  mov     rcx, [rbp+57h+SourceString]; hMem
0x1800748ed  call    DmsapFreeStringRoutine
0x1800748f2  mov     r9d, ebx
0x1800748f5  lea     rdx, aExitingNetpque_1; "Exiting NetpQueryDelegatedManagedServic"...
0x1800748fc  mov     r8, r15
0x1800748ff  mov     ecx, r13d; unsigned int
0x180074902  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180074907  mov     eax, ebx
0x180074909  jmp     short loc_180074910
0x18007490b  mov     eax, 0C000000Dh
0x180074910  add     rsp, 90h
0x180074917  pop     r15
0x180074919  pop     r13
0x18007491b  pop     rsi
0x18007491c  pop     rbx
0x18007491d  pop     rbp
0x18007491e  retn
```
