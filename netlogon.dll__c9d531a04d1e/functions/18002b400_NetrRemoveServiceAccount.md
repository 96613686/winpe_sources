# NetrRemoveServiceAccount

- ea: `0x18002b400`
- end: `0x18002b5a9`
- name: `NetrRemoveServiceAccount`
- size: `425`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003700`
- `0x180007278`
- `0x18000d100`
- `0x18002af98`
- `0x18002b400`
- `0x180062ee0`

## import_xrefs

- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x18002b47f`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x18002b47f`
- `LSASRV!LsaIIsContainerized` at `0x18002b513`
- `LSASRV!LsaIIsContainerized` at `0x18002b513`
- `ntdll!RtlInitUnicodeString` at `0x18002b4a7`
- `ntdll!RtlInitUnicodeString` at `0x18002b4a7`
- `gmsaclient!GMSACheckIfExistsInAD` at `0x18002b4e9`
- `gmsaclient!GMSACheckIfExistsInAD` at `0x18002b4e9`
- `gmsaclient!GMSADelete` at `0x18002b4b7`
- `gmsaclient!GMSADelete` at `0x18002b4b7`

## string_xrefs

- `0x18002b45f`: `NetpAccessCheck failed 0x%08X\n`
- `0x18002b427`: `Entering NetrRemoveServiceAccount for account %ws, flags 0x%08X\n`
- `0x18002b48b`: `Ignoring managed service account removal request - in EDJ mode\n`
- `0x18002b4c6`: `NetpDeleteGMSA failed 0x%08X\n`
- `0x18002b520`: `NetrRemoveServiceAccount (%ws) was invoked for a standalone MSA when containerized; failing.`
- `0x18002b549`: `NetpRemoveServiceAccount failed 0x%08X\n`
- `0x18002b58b`: `Exiting NetrRemoveServiceAccount for account %ws, Status 0x%08X\n`

## pseudocode

```c
__int64 __fastcall NetrRemoveServiceAccount(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  unsigned int v5; // eax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  int v14; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  NlPrintRoutine(0x40u, L"Entering NetrRemoveServiceAccount for account %ws, flags 0x%08X\n", a2, a3, 0, 0);
  v5 = NetpAccessCheck2(NlGlobalNetlogonSecurityDescriptor, 4u);
  v6 = NetpApiStatusToNtStatus(v5);
  v7 = v6;
  if ( v6 < 0 )
  {
    NlPrintRoutine(0x40u, L"NetpAccessCheck failed 0x%08X\n", (unsigned int)v6);
    goto LABEL_20;
  }
  if ( a2 && *a2 )
  {
    if ( (unsigned __int8)LsaIIsInEmulatedDomainJoinMode() )
    {
      v7 = 0;
      NlPrintRoutine(0x40u, L"Ignoring managed service account removal request - in EDJ mode\n");
      goto LABEL_22;
    }
    RtlInitUnicodeString(&DestinationString, a2);
    v9 = GMSADelete(&DestinationString, &v14);
    v7 = v9;
    if ( v9 < 0 )
    {
      NlPrintRoutine(0x40u, L"NetpDeleteGMSA failed 0x%08X\n", (unsigned int)v9);
      goto LABEL_20;
    }
    if ( v14 )
      goto LABEL_18;
    if ( (a3 & 2) == 0 )
    {
      v10 = GMSACheckIfExistsInAD(&DestinationString, &v14);
      v7 = v10;
      if ( v10 < 0 )
      {
        NlPrintRoutine(0x40u, L"GMSACheckGMSAExistsInAD for account %ws failed 0x%08X\n", a2, (unsigned int)v10);
        goto LABEL_20;
      }
      if ( v14 )
        goto LABEL_18;
    }
    if ( (unsigned __int8)LsaIIsContainerized() )
    {
      NlPrintRoutine(
        0x40u,
        L"NetrRemoveServiceAccount (%ws) was invoked for a standalone MSA when containerized; failing.",
        a2);
      v7 = -1073741637;
      goto LABEL_20;
    }
    v11 = NetpRemoveServiceAccount(a2, a3);
    v7 = v11;
    if ( v11 >= 0 )
    {
LABEL_18:
      v7 = 0;
      goto LABEL_22;
    }
    NlPrintRoutine(0x40u, L"NetpRemoveServiceAccount failed 0x%08X\n", (unsigned int)v11);
  }
  else
  {
    v7 = -1073741811;
    NlPrintRoutine(0x40u, L"Parameter Validation failed 0x%08X\n", 3221225485LL);
  }
LABEL_20:
  if ( (Microsoft_Windows_Security_NetlogonEnableBits & 4) != 0 )
    McTemplateU0zq_EtwEventWriteTransfer(v8, MSA_NETREMOVESERVICEACCOUNT_FAILURE, a2, v7);
LABEL_22:
  NlPrintRoutine(0x40u, L"Exiting NetrRemoveServiceAccount for account %ws, Status 0x%08X\n", a2, v7);
  return v7;
}

```

## disassembly

```asm
0x18002b400  push    rbx
0x18002b402  push    rsi
0x18002b403  push    rdi
0x18002b404  push    r14
0x18002b406  sub     rsp, 38h
0x18002b40a  mov     esi, r8d
0x18002b40d  mov     [rsp+58h+arg_18], 0
0x18002b415  mov     r9d, r8d
0x18002b418  mov     rdi, rdx
0x18002b41b  mov     r8, rdx
0x18002b41e  xorps   xmm0, xmm0
0x18002b421  mov     r14d, 40h ; '@'
0x18002b427  lea     rdx, aEnteringNetrre; "Entering NetrRemoveServiceAccount for a"...
0x18002b42e  mov     ecx, r14d; unsigned int
0x18002b431  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18002b436  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b43b  mov     rcx, cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA; pSecurityDescriptor
0x18002b442  lea     edx, [r14-3Ch]; DesiredAccess
0x18002b446  lea     r9d, [r14-3Fh]
0x18002b44a  call    NetpAccessCheck2
0x18002b44f  mov     ecx, eax
0x18002b451  call    NetpApiStatusToNtStatus
0x18002b456  mov     ebx, eax
0x18002b458  test    eax, eax
0x18002b45a  jns     short loc_18002B46B
0x18002b45c  mov     r8d, eax
0x18002b45f  lea     rdx, aNetpaccesschec; "NetpAccessCheck failed 0x%08X\n"
0x18002b466  jmp     loc_18002B565
0x18002b46b  test    rdi, rdi
0x18002b46e  jz      loc_18002B556
0x18002b474  xor     eax, eax
0x18002b476  cmp     ax, [rdi]
0x18002b479  jz      loc_18002B556
0x18002b47f  call    cs:__imp_LsaIIsInEmulatedDomainJoinMode
0x18002b485  test    al, al
0x18002b487  jz      short loc_18002B49F
0x18002b489  xor     ebx, ebx
0x18002b48b  lea     rdx, aIgnoringManage; "Ignoring managed service account remova"...
0x18002b492  mov     ecx, r14d; unsigned int
0x18002b495  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b49a  jmp     loc_18002B588
0x18002b49f  mov     rdx, rdi; SourceString
0x18002b4a2  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18002b4a7  call    cs:__imp_RtlInitUnicodeString
0x18002b4ad  lea     rdx, [rsp+58h+arg_18]
0x18002b4b2  lea     rcx, [rsp+58h+DestinationString]
0x18002b4b7  call    cs:__imp_GMSADelete
0x18002b4bd  mov     ebx, eax
0x18002b4bf  test    eax, eax
0x18002b4c1  jns     short loc_18002B4D2
0x18002b4c3  mov     r8d, eax
0x18002b4c6  lea     rdx, aNetpdeletegmsa; "NetpDeleteGMSA failed 0x%08X\n"
0x18002b4cd  jmp     loc_18002B565
0x18002b4d2  cmp     [rsp+58h+arg_18], 0
0x18002b4d7  jnz     short loc_18002B552
0x18002b4d9  test    sil, 2
0x18002b4dd  jnz     short loc_18002B513
0x18002b4df  lea     rdx, [rsp+58h+arg_18]
0x18002b4e4  lea     rcx, [rsp+58h+DestinationString]
0x18002b4e9  call    cs:__imp_GMSACheckIfExistsInAD
0x18002b4ef  mov     ebx, eax
0x18002b4f1  test    eax, eax
0x18002b4f3  jns     short loc_18002B50C
0x18002b4f5  mov     r9d, eax
0x18002b4f8  lea     rdx, aGmsacheckgmsae; "GMSACheckGMSAExistsInAD for account %ws"...
0x18002b4ff  mov     r8, rdi
0x18002b502  mov     ecx, r14d; unsigned int
0x18002b505  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b50a  jmp     short loc_18002B56D
0x18002b50c  cmp     [rsp+58h+arg_18], 0
0x18002b511  jnz     short loc_18002B552
0x18002b513  call    cs:__imp_LsaIIsContainerized
0x18002b519  test    al, al
0x18002b51b  jz      short loc_18002B536
0x18002b51d  mov     r8, rdi
0x18002b520  lea     rdx, aNetrremoveserv; "NetrRemoveServiceAccount (%ws) was invo"...
0x18002b527  mov     ecx, r14d; unsigned int
0x18002b52a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b52f  mov     ebx, 0C00000BBh
0x18002b534  jmp     short loc_18002B56D
0x18002b536  mov     edx, esi; unsigned int
0x18002b538  mov     rcx, rdi; unsigned __int16 *
0x18002b53b  call    ?NetpRemoveServiceAccount@@YAJPEBGK@Z; NetpRemoveServiceAccount(ushort const *,ulong)
0x18002b540  mov     ebx, eax
0x18002b542  test    eax, eax
0x18002b544  jns     short loc_18002B552
0x18002b546  mov     r8d, eax
0x18002b549  lea     rdx, aNetpremoveserv_0; "NetpRemoveServiceAccount failed 0x%08X"...
0x18002b550  jmp     short loc_18002B565
0x18002b552  xor     ebx, ebx
0x18002b554  jmp     short loc_18002B588
0x18002b556  mov     ebx, 0C000000Dh
0x18002b55b  lea     rdx, aParameterValid; "Parameter Validation failed 0x%08X\n"
0x18002b562  mov     r8d, ebx
0x18002b565  mov     ecx, r14d; unsigned int
0x18002b568  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b56d  test    cs:Microsoft_Windows_Security_NetlogonEnableBits, 4
0x18002b574  jz      short loc_18002B588
0x18002b576  mov     r9d, ebx
0x18002b579  lea     rdx, MSA_NETREMOVESERVICEACCOUNT_FAILURE
0x18002b580  mov     r8, rdi
0x18002b583  call    McTemplateU0zq_EtwEventWriteTransfer
0x18002b588  mov     r9d, ebx
0x18002b58b  lea     rdx, aExitingNetrrem; "Exiting NetrRemoveServiceAccount for ac"...
0x18002b592  mov     r8, rdi
0x18002b595  mov     ecx, r14d; unsigned int
0x18002b598  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b59d  mov     eax, ebx
0x18002b59f  add     rsp, 38h
0x18002b5a3  pop     r14
0x18002b5a5  pop     rdi
0x18002b5a6  pop     rsi
0x18002b5a7  pop     rbx
0x18002b5a8  retn
```
