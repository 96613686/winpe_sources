# NetrRemoveServiceAccount

- ea: `0x18002cd20`
- end: `0x18002ceec`
- name: `NetrRemoveServiceAccount`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003890`
- `0x180007518`
- `0x18000d7a0`
- `0x18002c89c`
- `0x18002cd20`
- `0x180067760`

## import_xrefs

- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x18002cd9f`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x18002cd9f`
- `LSASRV!LsaIIsContainerized` at `0x18002ce4f`
- `LSASRV!LsaIIsContainerized` at `0x18002ce4f`
- `ntdll!RtlInitUnicodeString` at `0x18002cdcd`
- `ntdll!RtlInitUnicodeString` at `0x18002cdcd`
- `gmsaclient!GMSACheckIfExistsInAD` at `0x18002ce1f`
- `gmsaclient!GMSACheckIfExistsInAD` at `0x18002ce1f`
- `gmsaclient!GMSADelete` at `0x18002cde3`
- `gmsaclient!GMSADelete` at `0x18002cde3`

## string_xrefs

- `0x18002cd7f`: `NetpAccessCheck failed 0x%08X\n`
- `0x18002cd47`: `Entering NetrRemoveServiceAccount for account %ws, flags 0x%08X\n`
- `0x18002cdb1`: `Ignoring managed service account removal request - in EDJ mode\n`
- `0x18002cdf8`: `NetpDeleteGMSA failed 0x%08X\n`
- `0x18002ce62`: `NetrRemoveServiceAccount (%ws) was invoked for a standalone MSA when containerized; failing.`
- `0x18002ce8b`: `NetpRemoveServiceAccount failed 0x%08X\n`
- `0x18002cecd`: `Exiting NetrRemoveServiceAccount for account %ws, Status 0x%08X\n`

## pseudocode

```c
__int64 __fastcall NetrRemoveServiceAccount(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  __int64 v5; // r8
  unsigned int v6; // eax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  int v15; // [rsp+78h] [rbp+20h] BYREF

  v15 = 0;
  NlPrintRoutine(0x40u, L"Entering NetrRemoveServiceAccount for account %ws, flags 0x%08X\n", a2, a3, 0, 0);
  v6 = NetpAccessCheck2(NlGlobalNetlogonSecurityDescriptor, 4u, v5, 1);
  v7 = NetpApiStatusToNtStatus(v6);
  v8 = v7;
  if ( v7 < 0 )
  {
    NlPrintRoutine(0x40u, L"NetpAccessCheck failed 0x%08X\n", (unsigned int)v7);
    goto LABEL_20;
  }
  if ( a2 && *a2 )
  {
    if ( (unsigned __int8)LsaIIsInEmulatedDomainJoinMode() )
    {
      v8 = 0;
      NlPrintRoutine(0x40u, L"Ignoring managed service account removal request - in EDJ mode\n");
      goto LABEL_22;
    }
    RtlInitUnicodeString(&DestinationString, a2);
    v10 = GMSADelete(&DestinationString, &v15);
    v8 = v10;
    if ( v10 < 0 )
    {
      NlPrintRoutine(0x40u, L"NetpDeleteGMSA failed 0x%08X\n", (unsigned int)v10);
      goto LABEL_20;
    }
    if ( v15 )
      goto LABEL_18;
    if ( (a3 & 2) == 0 )
    {
      v11 = GMSACheckIfExistsInAD(&DestinationString, &v15);
      v8 = v11;
      if ( v11 < 0 )
      {
        NlPrintRoutine(0x40u, L"GMSACheckGMSAExistsInAD for account %ws failed 0x%08X\n", a2, (unsigned int)v11);
        goto LABEL_20;
      }
      if ( v15 )
        goto LABEL_18;
    }
    if ( (unsigned __int8)LsaIIsContainerized() )
    {
      NlPrintRoutine(
        0x40u,
        L"NetrRemoveServiceAccount (%ws) was invoked for a standalone MSA when containerized; failing.",
        a2);
      v8 = -1073741637;
      goto LABEL_20;
    }
    v12 = NetpRemoveServiceAccount(a2, a3);
    v8 = v12;
    if ( v12 >= 0 )
    {
LABEL_18:
      v8 = 0;
      goto LABEL_22;
    }
    NlPrintRoutine(0x40u, L"NetpRemoveServiceAccount failed 0x%08X\n", (unsigned int)v12);
  }
  else
  {
    v8 = -1073741811;
    NlPrintRoutine(0x40u, L"Parameter Validation failed 0x%08X\n", 3221225485LL);
  }
LABEL_20:
  if ( (Microsoft_Windows_Security_NetlogonEnableBits & 4) != 0 )
    McTemplateU0zq_EtwEventWriteTransfer(v9, MSA_NETREMOVESERVICEACCOUNT_FAILURE, a2, v8);
LABEL_22:
  NlPrintRoutine(0x40u, L"Exiting NetrRemoveServiceAccount for account %ws, Status 0x%08X\n", a2, v8);
  return v8;
}

```

## disassembly

```asm
0x18002cd20  push    rbx
0x18002cd22  push    rsi
0x18002cd23  push    rdi
0x18002cd24  push    r14
0x18002cd26  sub     rsp, 38h
0x18002cd2a  mov     esi, r8d
0x18002cd2d  mov     [rsp+58h+arg_18], 0
0x18002cd35  mov     r9d, r8d
0x18002cd38  mov     rdi, rdx
0x18002cd3b  mov     r8, rdx
0x18002cd3e  xorps   xmm0, xmm0
0x18002cd41  mov     r14d, 40h ; '@'
0x18002cd47  lea     rdx, aEnteringNetrre; "Entering NetrRemoveServiceAccount for a"...
0x18002cd4e  mov     ecx, r14d; unsigned int
0x18002cd51  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18002cd56  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002cd5b  mov     rcx, cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA; pSecurityDescriptor
0x18002cd62  lea     edx, [r14-3Ch]; DesiredAccess
0x18002cd66  lea     r9d, [r14-3Fh]
0x18002cd6a  call    NetpAccessCheck2
0x18002cd6f  mov     ecx, eax
0x18002cd71  call    NetpApiStatusToNtStatus
0x18002cd76  mov     ebx, eax
0x18002cd78  test    eax, eax
0x18002cd7a  jns     short loc_18002CD8B
0x18002cd7c  mov     r8d, eax
0x18002cd7f  lea     rdx, aNetpaccesschec; "NetpAccessCheck failed 0x%08X\n"
0x18002cd86  jmp     loc_18002CEA7
0x18002cd8b  test    rdi, rdi
0x18002cd8e  jz      loc_18002CE98
0x18002cd94  xor     eax, eax
0x18002cd96  cmp     ax, [rdi]
0x18002cd99  jz      loc_18002CE98
0x18002cd9f  call    cs:__imp_LsaIIsInEmulatedDomainJoinMode
0x18002cda6  nop     dword ptr [rax+rax+00h]
0x18002cdab  test    al, al
0x18002cdad  jz      short loc_18002CDC5
0x18002cdaf  xor     ebx, ebx
0x18002cdb1  lea     rdx, aIgnoringManage; "Ignoring managed service account remova"...
0x18002cdb8  mov     ecx, r14d; unsigned int
0x18002cdbb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002cdc0  jmp     loc_18002CECA
0x18002cdc5  mov     rdx, rdi; SourceString
0x18002cdc8  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18002cdcd  call    cs:__imp_RtlInitUnicodeString
0x18002cdd4  nop     dword ptr [rax+rax+00h]
0x18002cdd9  lea     rdx, [rsp+58h+arg_18]
0x18002cdde  lea     rcx, [rsp+58h+DestinationString]
0x18002cde3  call    cs:__imp_GMSADelete
0x18002cdea  nop     dword ptr [rax+rax+00h]
0x18002cdef  mov     ebx, eax
0x18002cdf1  test    eax, eax
0x18002cdf3  jns     short loc_18002CE04
0x18002cdf5  mov     r8d, eax
0x18002cdf8  lea     rdx, aNetpdeletegmsa; "NetpDeleteGMSA failed 0x%08X\n"
0x18002cdff  jmp     loc_18002CEA7
0x18002ce04  cmp     [rsp+58h+arg_18], 0
0x18002ce09  jnz     loc_18002CE94
0x18002ce0f  test    sil, 2
0x18002ce13  jnz     short loc_18002CE4F
0x18002ce15  lea     rdx, [rsp+58h+arg_18]
0x18002ce1a  lea     rcx, [rsp+58h+DestinationString]
0x18002ce1f  call    cs:__imp_GMSACheckIfExistsInAD
0x18002ce26  nop     dword ptr [rax+rax+00h]
0x18002ce2b  mov     ebx, eax
0x18002ce2d  test    eax, eax
0x18002ce2f  jns     short loc_18002CE48
0x18002ce31  mov     r9d, eax
0x18002ce34  lea     rdx, aGmsacheckgmsae; "GMSACheckGMSAExistsInAD for account %ws"...
0x18002ce3b  mov     r8, rdi
0x18002ce3e  mov     ecx, r14d; unsigned int
0x18002ce41  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002ce46  jmp     short loc_18002CEAF
0x18002ce48  cmp     [rsp+58h+arg_18], 0
0x18002ce4d  jnz     short loc_18002CE94
0x18002ce4f  call    cs:__imp_LsaIIsContainerized
0x18002ce56  nop     dword ptr [rax+rax+00h]
0x18002ce5b  test    al, al
0x18002ce5d  jz      short loc_18002CE78
0x18002ce5f  mov     r8, rdi
0x18002ce62  lea     rdx, aNetrremoveserv; "NetrRemoveServiceAccount (%ws) was invo"...
0x18002ce69  mov     ecx, r14d; unsigned int
0x18002ce6c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002ce71  mov     ebx, 0C00000BBh
0x18002ce76  jmp     short loc_18002CEAF
0x18002ce78  mov     edx, esi; unsigned int
0x18002ce7a  mov     rcx, rdi; unsigned __int16 *
0x18002ce7d  call    ?NetpRemoveServiceAccount@@YAJPEBGK@Z; NetpRemoveServiceAccount(ushort const *,ulong)
0x18002ce82  mov     ebx, eax
0x18002ce84  test    eax, eax
0x18002ce86  jns     short loc_18002CE94
0x18002ce88  mov     r8d, eax
0x18002ce8b  lea     rdx, aNetpremoveserv_0; "NetpRemoveServiceAccount failed 0x%08X"...
0x18002ce92  jmp     short loc_18002CEA7
0x18002ce94  xor     ebx, ebx
0x18002ce96  jmp     short loc_18002CECA
0x18002ce98  mov     ebx, 0C000000Dh
0x18002ce9d  lea     rdx, aParameterValid; "Parameter Validation failed 0x%08X\n"
0x18002cea4  mov     r8d, ebx
0x18002cea7  mov     ecx, r14d; unsigned int
0x18002ceaa  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002ceaf  test    cs:Microsoft_Windows_Security_NetlogonEnableBits, 4
0x18002ceb6  jz      short loc_18002CECA
0x18002ceb8  mov     r9d, ebx
0x18002cebb  lea     rdx, MSA_NETREMOVESERVICEACCOUNT_FAILURE
0x18002cec2  mov     r8, rdi
0x18002cec5  call    McTemplateU0zq_EtwEventWriteTransfer
0x18002ceca  mov     r9d, ebx
0x18002cecd  lea     rdx, aExitingNetrrem; "Exiting NetrRemoveServiceAccount for ac"...
0x18002ced4  mov     r8, rdi
0x18002ced7  mov     ecx, r14d; unsigned int
0x18002ceda  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002cedf  mov     eax, ebx
0x18002cee1  add     rsp, 38h
0x18002cee5  pop     r14
0x18002cee7  pop     rdi
0x18002cee8  pop     rsi
0x18002cee9  pop     rbx
0x18002ceea  retn
```
