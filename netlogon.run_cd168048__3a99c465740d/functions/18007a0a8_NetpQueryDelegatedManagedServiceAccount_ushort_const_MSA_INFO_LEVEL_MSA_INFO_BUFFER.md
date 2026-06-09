# NetpQueryDelegatedManagedServiceAccount(ushort const *,_MSA_INFO_LEVEL,_MSA_INFO_BUFFER *)

- ea: `0x18007a0a8`
- end: `0x18007a319`
- name: `?NetpQueryDelegatedManagedServiceAccount@@YAJPEBGW4_MSA_INFO_LEVEL@@PEAT_MSA_INFO_BUFFER@@@Z`
- size: `625`
- prototype: `__int64 __fastcall(PCWSTR SourceString, enum _MSA_INFO_LEVEL, union _MSA_INFO_BUFFER *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002c0b8`

## callees

- `0x1800046b0`
- `0x180007518`
- `0x180008bb0`
- `0x180008f08`
- `0x18000d7a0`
- `0x18007a0a8`
- `0x180089328`

## import_xrefs

- `ntdll!RtlEqualDomainName` at `0x18007a19d`
- `ntdll!RtlEqualDomainName` at `0x18007a19d`
- `ntdll!RtlInitUnicodeString` at `0x18007a12b`
- `ntdll!RtlInitUnicodeString` at `0x18007a182`
- `ntdll!RtlInitUnicodeString` at `0x18007a226`
- `ntdll!RtlInitUnicodeString` at `0x18007a23a`
- `ntdll!RtlInitUnicodeString` at `0x18007a12b`
- `ntdll!RtlInitUnicodeString` at `0x18007a182`
- `ntdll!RtlInitUnicodeString` at `0x18007a226`
- `ntdll!RtlInitUnicodeString` at `0x18007a23a`
- `netutils!NetApiBufferFree` at `0x18007a2b1`
- `netutils!NetApiBufferFree` at `0x18007a2b1`
- `SAMLIB!SamiAccountIsDelegateManagedServiceAccount` at `0x18007a256`
- `SAMLIB!SamiAccountIsDelegateManagedServiceAccount` at `0x18007a256`

## string_xrefs

- `0x18007a10e`: `Entering NetpQueryDelegatedManagedServiceAccount for account %s, Level %u\n`
- `0x18007a207`: `NetpQueryDelegatedManagedServiceAccount: Failed to find usable DC\n`
- `0x18007a268`: `NetpQueryDelegatedManagedServiceAccount: Failed to call SAM to check if account is a dMSA\n`
- `0x18007a2ee`: `Exiting NetpQueryDelegatedManagedServiceAccount for account %s, Status 0x%08X\n`

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
    DcNameEx2 = DsrGetDcNameEx2(0, 0, 0, v8, (__int64)&Buffer);
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
0x18007a0a8  mov     [rsp-8+arg_8], edx
0x18007a0ac  push    rbp
0x18007a0ad  push    rbx
0x18007a0ae  push    rsi
0x18007a0af  push    r13
0x18007a0b1  push    r15
0x18007a0b3  lea     rbp, [rsp-37h]
0x18007a0b8  sub     rsp, 90h
0x18007a0bf  mov     [rbp+57h+Buffer], 0
0x18007a0c7  xorps   xmm0, xmm0
0x18007a0ca  mov     byte ptr [rbp+57h+arg_8], 0
0x18007a0ce  xorps   xmm1, xmm1
0x18007a0d1  mov     [rbp+57h+arg_10], 0
0x18007a0d5  mov     rsi, r8
0x18007a0d8  mov     [rbp+57h+hMem], 0
0x18007a0e0  mov     r15, rcx
0x18007a0e3  mov     [rbp+57h+var_70], 0
0x18007a0eb  mov     [rbp+57h+SourceString], 0
0x18007a0f3  movups  xmmword ptr [rbp+57h+var_38.Length], xmm0
0x18007a0f7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18007a0fb  movups  xmmword ptr [rbp+57h+DomainName1.Length], xmm0
0x18007a0ff  test    r8, r8
0x18007a102  jz      loc_18007A304
0x18007a108  mov     r9d, 1
0x18007a10e  lea     rdx, aEnteringNetpqu_1; "Entering NetpQueryDelegatedManagedServi"...
0x18007a115  mov     r8, rcx
0x18007a118  lea     r13d, [r9+3Fh]
0x18007a11c  mov     ecx, r13d; unsigned int
0x18007a11f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007a124  mov     rdx, r15; SourceString
0x18007a127  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18007a12b  call    cs:__imp_RtlInitUnicodeString
0x18007a132  nop     dword ptr [rax+rax+00h]
0x18007a137  lea     rax, [rbp+57h+SourceString]
0x18007a13b  lea     r9, [rbp+57h+var_70]; unsigned __int16 **
0x18007a13f  mov     [rsp+0B0h+var_90], rax; unsigned __int16 **
0x18007a144  lea     r8, [rbp+57h+hMem]; unsigned __int16 **
0x18007a148  lea     rcx, [rbp+57h+DestinationString]; SourceString
0x18007a14c  call    ?DmsapParseAccountNames@@YAJPEBU_UNICODE_STRING@@0PEAPEAG11@Z; DmsapParseAccountNames(_UNICODE_STRING const *,_UNICODE_STRING const *,ushort * *,ushort * *,ushort * *)
0x18007a151  mov     ebx, eax
0x18007a153  test    eax, eax
0x18007a155  jns     short loc_18007A16E
0x18007a157  mov     r8d, eax
0x18007a15a  lea     rdx, aGmsapparseacco; "GmsapParseAccountNamesLocally failed %#"...
0x18007a161  mov     ecx, r13d; unsigned int
0x18007a164  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007a169  jmp     loc_18007A2A8
0x18007a16e  cmp     [rbp+57h+SourceString], 0
0x18007a173  mov     ebx, 42000000h
0x18007a178  jz      short loc_18007A1CB
0x18007a17a  mov     rdx, [rbp+57h+SourceString]; SourceString
0x18007a17e  lea     rcx, [rbp+57h+DomainName1]; DestinationString
0x18007a182  call    cs:__imp_RtlInitUnicodeString
0x18007a189  nop     dword ptr [rax+rax+00h]
0x18007a18e  mov     rdx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x18007a195  lea     rcx, [rbp+57h+DomainName1]; DomainName1
0x18007a199  add     rdx, 38h ; '8'; DomainName2
0x18007a19d  call    cs:__imp_RtlEqualDomainName
0x18007a1a4  nop     dword ptr [rax+rax+00h]
0x18007a1a9  test    al, al
0x18007a1ab  jnz     short loc_18007A1CB
0x18007a1ad  mov     rdx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x18007a1b4  lea     rcx, [rbp+57h+DomainName1]; struct _UNICODE_STRING *
0x18007a1b8  add     rdx, 38h ; '8'; struct _UNICODE_STRING *
0x18007a1bc  call    ?NlEqualDnsNameU@@YAHPEAU_UNICODE_STRING@@0@Z; NlEqualDnsNameU(_UNICODE_STRING *,_UNICODE_STRING *)
0x18007a1c1  test    eax, eax
0x18007a1c3  mov     ecx, 42001000h
0x18007a1c8  cmovz   ebx, ecx
0x18007a1cb  mov     r9, [rbp+57h+SourceString]
0x18007a1cf  lea     rax, [rbp+57h+Buffer]
0x18007a1d3  mov     [rsp+0B0h+var_78], rax
0x18007a1d8  xor     r8d, r8d
0x18007a1db  mov     [rsp+0B0h+var_80], ebx
0x18007a1df  xor     edx, edx
0x18007a1e1  mov     [rsp+0B0h+var_88], 0
0x18007a1ea  xor     ecx, ecx
0x18007a1ec  mov     [rsp+0B0h+var_90], 0
0x18007a1f5  call    DsrGetDcNameEx2
0x18007a1fa  mov     ecx, eax
0x18007a1fc  call    NetpApiStatusToNtStatus
0x18007a201  mov     ebx, eax
0x18007a203  test    eax, eax
0x18007a205  jns     short loc_18007A21B
0x18007a207  lea     rdx, aNetpquerydeleg_0; "NetpQueryDelegatedManagedServiceAccount"...
0x18007a20e  mov     ecx, r13d; unsigned int
0x18007a211  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007a216  jmp     loc_18007A2A8
0x18007a21b  mov     rdx, [rbp+57h+Buffer]
0x18007a21f  lea     rcx, [rbp+57h+var_38]; DestinationString
0x18007a223  mov     rdx, [rdx]; SourceString
0x18007a226  call    cs:__imp_RtlInitUnicodeString
0x18007a22d  nop     dword ptr [rax+rax+00h]
0x18007a232  mov     rdx, [rbp+57h+var_70]; SourceString
0x18007a236  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18007a23a  call    cs:__imp_RtlInitUnicodeString
0x18007a241  nop     dword ptr [rax+rax+00h]
0x18007a246  lea     r9, [rbp+57h+arg_10]
0x18007a24a  lea     r8, [rbp+57h+arg_8]
0x18007a24e  lea     rdx, [rbp+57h+DestinationString]
0x18007a252  lea     rcx, [rbp+57h+var_38]
0x18007a256  call    cs:__imp_SamiAccountIsDelegateManagedServiceAccount
0x18007a25d  nop     dword ptr [rax+rax+00h]
0x18007a262  mov     ebx, eax
0x18007a264  test    eax, eax
0x18007a266  jns     short loc_18007A271
0x18007a268  lea     rdx, aNetpquerydeleg_1; "NetpQueryDelegatedManagedServiceAccount"...
0x18007a26f  jmp     short loc_18007A20E
0x18007a271  mov     rcx, [rsi]
0x18007a274  test    rcx, rcx
0x18007a277  jnz     short loc_18007A280
0x18007a279  mov     ebx, 0C000000Dh
0x18007a27e  jmp     short loc_18007A2A8
0x18007a280  cmp     byte ptr [rbp+57h+arg_8], 0
0x18007a284  jz      short loc_18007A291
0x18007a286  cmp     [rbp+57h+arg_10], 0
0x18007a28a  mov     eax, 5
0x18007a28f  jnz     short loc_18007A296
0x18007a291  mov     eax, 2
0x18007a296  mov     [rcx], eax
0x18007a298  mov     al, byte ptr [rbp+57h+arg_8]
0x18007a29b  neg     al
0x18007a29d  mov     rax, [rsi]
0x18007a2a0  sbb     ecx, ecx
0x18007a2a2  and     ecx, 3
0x18007a2a5  mov     [rax+4], ecx
0x18007a2a8  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18007a2ac  test    rcx, rcx
0x18007a2af  jz      short loc_18007A2BD
0x18007a2b1  call    cs:__imp_NetApiBufferFree
0x18007a2b8  nop     dword ptr [rax+rax+00h]
0x18007a2bd  mov     rcx, [rbp+57h+hMem]; hMem
0x18007a2c1  test    rcx, rcx
0x18007a2c4  jz      short loc_18007A2CB
0x18007a2c6  call    DmsapFreeStringRoutine
0x18007a2cb  cmp     [rbp+57h+var_70], 0
0x18007a2d0  jz      short loc_18007A2DB
0x18007a2d2  mov     rcx, [rbp+57h+var_70]; hMem
0x18007a2d6  call    DmsapFreeStringRoutine
0x18007a2db  cmp     [rbp+57h+SourceString], 0
0x18007a2e0  jz      short loc_18007A2EB
0x18007a2e2  mov     rcx, [rbp+57h+SourceString]; hMem
0x18007a2e6  call    DmsapFreeStringRoutine
0x18007a2eb  mov     r9d, ebx
0x18007a2ee  lea     rdx, aExitingNetpque_1; "Exiting NetpQueryDelegatedManagedServic"...
0x18007a2f5  mov     r8, r15
0x18007a2f8  mov     ecx, r13d; unsigned int
0x18007a2fb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007a300  mov     eax, ebx
0x18007a302  jmp     short loc_18007A309
0x18007a304  mov     eax, 0C000000Dh
0x18007a309  add     rsp, 90h
0x18007a310  pop     r15
0x18007a312  pop     r13
0x18007a314  pop     rsi
0x18007a315  pop     rbx
0x18007a316  pop     rbp
0x18007a317  retn
```
