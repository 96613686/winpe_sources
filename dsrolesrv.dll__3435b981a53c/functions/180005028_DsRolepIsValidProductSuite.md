# DsRolepIsValidProductSuite

- ea: `0x180005028`
- end: `0x18000510a`
- name: `DsRolepIsValidProductSuite`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800058a0`
- `0x180005e40`

## callees

- `0x180005028`
- `0x180006fd0`
- `0x180007268`
- `0x180020dbc`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x1800050c2`
- `DNSAPI!DnsNameCompare_W` at `0x1800050c2`
- `DNSAPI!DnsNameCompareEx_W` at `0x1800050d1`
- `DNSAPI!DnsNameCompareEx_W` at `0x1800050d1`
- `logoncli!DsGetDcNameW` at `0x180005088`
- `logoncli!DsGetDcNameW` at `0x180005088`
- `netutils!NetApiBufferFree` at `0x1800050f9`
- `netutils!NetApiBufferFree` at `0x1800050f9`

## pseudocode

```c
__int64 __fastcall DsRolepIsValidProductSuite(int a1, int a2, const WCHAR *a3)
{
  unsigned int v6; // ebx
  DWORD DcNameW; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  const WCHAR *DnsForestName; // rdx
  int v10; // eax
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+78h] [rbp+20h] BYREF

  DomainControllerInfo = 0;
  if ( (unsigned int)IsProductSuiteConfigured(1024) )
    goto LABEL_2;
  v6 = 0;
  if ( (unsigned int)IsProductSuiteConfigured(32) )
  {
    if ( a2 )
    {
      DcNameW = DsGetDcNameW(0, a3, 0, 0, 0, &DomainControllerInfo);
      v6 = DcNameW;
      if ( DcNameW )
      {
        DsRolepLogPrintRoutine(1, "Request to find a DC for %ws failed (%d)\n", a3, DcNameW);
        goto LABEL_15;
      }
      IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_IsEnabledDeviceUsageNoInline();
      DnsForestName = DomainControllerInfo->DnsForestName;
      if ( IsEnabledDeviceUsageNoInline )
      {
        if ( !DnsNameCompare_W(a3, DnsForestName) )
LABEL_2:
          v6 = 50;
      }
      else if ( (unsigned int)DnsNameCompareEx_W(a3, DnsForestName, 0) != 1 )
      {
        goto LABEL_2;
      }
    }
    else
    {
      v10 = 0;
      if ( !a1 )
        v10 = 50;
      v6 = v10;
    }
  }
LABEL_15:
  if ( DomainControllerInfo )
    NetApiBufferFree(DomainControllerInfo);
  return v6;
}

```

## disassembly

```asm
0x180005028  push    rbx
0x18000502a  push    rbp
0x18000502b  push    rsi
0x18000502c  push    rdi
0x18000502d  sub     rsp, 38h
0x180005031  mov     ebp, ecx
0x180005033  mov     [rsp+58h+arg_18], 0
0x18000503c  mov     ecx, 400h
0x180005041  mov     rdi, r8
0x180005044  mov     esi, edx
0x180005046  call    IsProductSuiteConfigured
0x18000504b  test    eax, eax
0x18000504d  jz      short loc_180005059
0x18000504f  mov     ebx, 32h ; '2'
0x180005054  jmp     loc_1800050EF
0x180005059  xor     ebx, ebx
0x18000505b  lea     ecx, [rbx+20h]
0x18000505e  call    IsProductSuiteConfigured
0x180005063  test    eax, eax
0x180005065  jz      loc_1800050EF
0x18000506b  test    esi, esi
0x18000506d  jz      short loc_1800050E1
0x18000506f  lea     rax, [rsp+58h+arg_18]
0x180005074  xor     r9d, r9d; SiteName
0x180005077  mov     [rsp+58h+DomainControllerInfo], rax; DomainControllerInfo
0x18000507c  xor     r8d, r8d; DomainGuid
0x18000507f  mov     rdx, rdi; DomainName
0x180005082  mov     [rsp+58h+Flags], ebx; Flags
0x180005086  xor     ecx, ecx; ComputerName
0x180005088  call    cs:__imp_DsGetDcNameW
0x18000508e  mov     ebx, eax
0x180005090  test    eax, eax
0x180005092  jz      short loc_1800050AD
0x180005094  mov     r9d, eax
0x180005097  lea     rdx, aRequestToFindA; "Request to find a DC for %ws failed (%d"...
0x18000509e  mov     r8, rdi
0x1800050a1  mov     ecx, 1
0x1800050a6  call    DsRolepLogPrintRoutine
0x1800050ab  jmp     short loc_1800050EF
0x1800050ad  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x1800050b2  mov     rdx, [rsp+58h+arg_18]
0x1800050b7  mov     rcx, rdi; pName1
0x1800050ba  mov     rdx, [rdx+30h]; pName2
0x1800050be  test    eax, eax
0x1800050c0  jz      short loc_1800050CE
0x1800050c2  call    cs:__imp_DnsNameCompare_W
0x1800050c8  test    eax, eax
0x1800050ca  jnz     short loc_1800050EF
0x1800050cc  jmp     short loc_18000504F
0x1800050ce  xor     r8d, r8d
0x1800050d1  call    cs:__imp_DnsNameCompareEx_W
0x1800050d7  cmp     eax, 1
0x1800050da  jz      short loc_1800050EF
0x1800050dc  jmp     loc_18000504F
0x1800050e1  mov     eax, ebx
0x1800050e3  test    ebp, ebp
0x1800050e5  mov     ebx, 32h ; '2'
0x1800050ea  cmovz   eax, ebx
0x1800050ed  mov     ebx, eax
0x1800050ef  mov     rcx, [rsp+58h+arg_18]; Buffer
0x1800050f4  test    rcx, rcx
0x1800050f7  jz      short loc_1800050FF
0x1800050f9  call    cs:__imp_NetApiBufferFree
0x1800050ff  mov     eax, ebx
0x180005101  add     rsp, 38h
0x180005105  pop     rdi
0x180005106  pop     rsi
0x180005107  pop     rbp
0x180005108  pop     rbx
0x180005109  retn
```
