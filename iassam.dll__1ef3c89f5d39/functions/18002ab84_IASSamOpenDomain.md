# IASSamOpenDomain

- ea: `0x18002ab84`
- end: `0x18002add3`
- name: `IASSamOpenDomain`
- size: `591`
- prototype: `__int64 __usercall@<rax>(wchar_t *Source@<rcx>, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002addc`

## callees

- `0x18000c4a4`
- `0x18000e754`
- `0x1800254a0`
- `0x1800281a0`
- `0x18002a898`
- `0x18002aad4`
- `0x18002ab84`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002abc2`
- `msvcrt!_wcsicmp` at `0x18002abc2`
- `ntdll!RtlInitUnicodeString` at `0x18002ad1e`
- `ntdll!RtlInitUnicodeString` at `0x18002ad56`
- `ntdll!RtlInitUnicodeString` at `0x18002ad1e`
- `ntdll!RtlInitUnicodeString` at `0x18002ad56`
- `ntdll!RtlNtStatusToDosError` at `0x18002adc0`
- `ntdll!RtlNtStatusToDosError` at `0x18002adc0`
- `netutils!NetApiBufferFree` at `0x18002ad45`
- `netutils!NetApiBufferFree` at `0x18002ad45`
- `SAMLIB!SamOpenDomain` at `0x18002ad82`
- `SAMLIB!SamOpenDomain` at `0x18002ad82`
- `SAMLIB!SamConnect` at `0x18002ad39`
- `SAMLIB!SamConnect` at `0x18002ad39`
- `SAMLIB!SamLookupDomainInSamServer` at `0x18002ad67`
- `SAMLIB!SamLookupDomainInSamServer` at `0x18002ad67`
- `SAMLIB!SamFreeMemory` at `0x18002ada7`
- `SAMLIB!SamFreeMemory` at `0x18002ada7`
- `SAMLIB!SamCloseHandle` at `0x18002adb8`
- `SAMLIB!SamCloseHandle` at `0x18002adb8`

## string_xrefs

- `0x18002ac13`: `Using cached SAM connection to local account domain.`
- `0x18002ac65`: `Using cached SAM connection.`

## pseudocode

```c
ULONG __fastcall IASSamOpenDomain(wchar_t *Source, __int64 a2, int a3, int a4, int a5, _QWORD *a6, _QWORD *a7)
{
  __int64 v10; // rdx
  __int64 v11; // rdx
  ULONG result; // eax
  int v13; // r9d
  NTSTATUS v14; // edi
  LPVOID Buffer; // [rsp+30h] [rbp-38h] BYREF
  __int64 v16; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING v18; // [rsp+50h] [rbp-18h] BYREF

  Buffer = 0;
  v16 = 0;
  DestinationString = 0;
  v18 = 0;
  if ( !_wcsicmp(Source, &theAccountDomain) )
  {
    *a6 = theAccountDomainSid;
    *a7 = theAccountDomainHandle;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      return 0;
    }
    WppDbgPrint("Using cached SAM connection to local account domain.");
    v11 = 10;
LABEL_12:
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_e0ba6dc947893981c01e383b05472641_Traceguids, "NPSSVC");
    return 0;
  }
  if ( !a5 && (unsigned int)IASSamOpenCachedDomain(Source, v10, a6, a7) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      return 0;
    }
    WppDbgPrint("Using cached SAM connection.");
    v11 = 11;
    goto LABEL_12;
  }
  result = IASGetDcName(Source, a3 | (unsigned int)(a4 != 0), (PDOMAIN_CONTROLLER_INFOW *)&Buffer);
  if ( !result )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Connecting to SAM server on %S.");
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_e0ba6dc947893981c01e383b05472641_Traceguids,
        v13,
        *(_QWORD *)Buffer);
    }
    RtlInitUnicodeString(&DestinationString, *(PCWSTR *)Buffer);
    v14 = SamConnect(&DestinationString, &v16, 32, &theObjectAttributes);
    NetApiBufferFree(Buffer);
    if ( v14 >= 0 )
    {
      RtlInitUnicodeString(&v18, Source);
      v14 = SamLookupDomainInSamServer(v16, &v18, a6);
      if ( v14 >= 0 )
      {
        v14 = SamOpenDomain(v16, 512, *a6, a7);
        if ( v14 < 0 )
        {
          SamFreeMemory(*a6);
          *a6 = 0;
        }
        else if ( !a5 )
        {
          IASSamAddCachedDomain(Source);
        }
      }
      SamCloseHandle(v16);
    }
    return RtlNtStatusToDosError(v14);
  }
  return result;
}

```

## disassembly

```asm
0x18002ab84  push    rbp
0x18002ab86  push    rbx
0x18002ab87  push    rsi
0x18002ab88  push    rdi
0x18002ab89  push    r12
0x18002ab8b  push    r14
0x18002ab8d  mov     rbp, rsp
0x18002ab90  sub     rsp, 68h
0x18002ab94  xorps   xmm0, xmm0
0x18002ab97  mov     [rbp+Buffer], 0
0x18002ab9f  xorps   xmm1, xmm1
0x18002aba2  mov     [rbp+var_30], 0
0x18002abaa  lea     rdx, theAccountDomain; String2
0x18002abb1  mov     edi, r9d
0x18002abb4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002abb8  mov     r12d, r8d
0x18002abbb  mov     rsi, rcx
0x18002abbe  movups  xmmword ptr [rbp+var_18.Length], xmm1
0x18002abc2  call    cs:__imp__wcsicmp
0x18002abc8  test    eax, eax
0x18002abca  jnz     short loc_18002AC26
0x18002abcc  mov     rcx, [rbp+arg_28]
0x18002abd0  mov     rax, cs:theAccountDomainSid
0x18002abd7  mov     [rcx], rax
0x18002abda  mov     rcx, [rbp+arg_30]
0x18002abde  mov     rax, cs:theAccountDomainHandle
0x18002abe5  mov     [rcx], rax
0x18002abe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abef  lea     rax, WPP_GLOBAL_Control
0x18002abf6  cmp     rcx, rax
0x18002abf9  jz      loc_18002AC94
0x18002abff  cmp     byte ptr [rcx+19h], 4
0x18002ac03  jb      loc_18002AC94
0x18002ac09  test    byte ptr [rcx+1Ch], 4
0x18002ac0d  jz      loc_18002AC94
0x18002ac13  lea     rcx, aUsingCachedSam; "Using cached SAM connection to local ac"...
0x18002ac1a  call    WppDbgPrint
0x18002ac1f  mov     edx, 0Ah
0x18002ac24  jmp     short loc_18002AC76
0x18002ac26  cmp     [rbp+arg_20], 0
0x18002ac2a  mov     r14, [rbp+arg_30]
0x18002ac2e  mov     rbx, [rbp+arg_28]
0x18002ac32  jnz     short loc_18002AC9B
0x18002ac34  mov     r9, r14
0x18002ac37  mov     r8, rbx
0x18002ac3a  mov     rcx, rsi
0x18002ac3d  call    IASSamOpenCachedDomain
0x18002ac42  test    eax, eax
0x18002ac44  jz      short loc_18002AC9B
0x18002ac46  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac4d  lea     rax, WPP_GLOBAL_Control
0x18002ac54  cmp     rcx, rax
0x18002ac57  jz      short loc_18002AC94
0x18002ac59  cmp     byte ptr [rcx+19h], 4
0x18002ac5d  jb      short loc_18002AC94
0x18002ac5f  test    byte ptr [rcx+1Ch], 4
0x18002ac63  jz      short loc_18002AC94
0x18002ac65  lea     rcx, aUsingCachedSam_0; "Using cached SAM connection."
0x18002ac6c  call    WppDbgPrint
0x18002ac71  mov     edx, 0Bh
0x18002ac76  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac7d  lea     r9, aNpssvc; "NPSSVC"
0x18002ac84  lea     r8, WPP_e0ba6dc947893981c01e383b05472641_Traceguids
0x18002ac8b  mov     rcx, [rcx+10h]
0x18002ac8f  call    WPP_SF_s
0x18002ac94  xor     eax, eax
0x18002ac96  jmp     loc_18002ADC6
0x18002ac9b  xor     edx, edx
0x18002ac9d  lea     r8, [rbp+Buffer]; DomainControllerInfo
0x18002aca1  test    edi, edi
0x18002aca3  mov     rcx, rsi; DomainName
0x18002aca6  setnz   dl
0x18002aca9  or      edx, r12d; Flags
0x18002acac  call    IASGetDcName
0x18002acb1  test    eax, eax
0x18002acb3  jnz     loc_18002ADC6
0x18002acb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002acc0  lea     rax, WPP_GLOBAL_Control
0x18002acc7  cmp     rcx, rax
0x18002acca  jz      short loc_18002AD13
0x18002accc  cmp     byte ptr [rcx+19h], 4
0x18002acd0  jb      short loc_18002AD13
0x18002acd2  test    byte ptr [rcx+1Ch], 4
0x18002acd6  jz      short loc_18002AD13
0x18002acd8  mov     rdx, [rbp+Buffer]
0x18002acdc  lea     rcx, aConnectingToSa; "Connecting to SAM server on %S."
0x18002ace3  mov     rdx, [rdx]
0x18002ace6  call    WppDbgPrint
0x18002aceb  mov     rax, [rbp+Buffer]
0x18002acef  lea     r8, WPP_e0ba6dc947893981c01e383b05472641_Traceguids
0x18002acf6  mov     edx, 0Ch
0x18002acfb  mov     rcx, [rax]
0x18002acfe  mov     [rsp+68h+var_48], rcx
0x18002ad03  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad0a  mov     rcx, [rcx+10h]
0x18002ad0e  call    WPP_SF_sS
0x18002ad13  mov     rdx, [rbp+Buffer]
0x18002ad17  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002ad1b  mov     rdx, [rdx]; SourceString
0x18002ad1e  call    cs:__imp_RtlInitUnicodeString
0x18002ad24  lea     r9, theObjectAttributes
0x18002ad2b  mov     r8d, 20h ; ' '
0x18002ad31  lea     rdx, [rbp+var_30]
0x18002ad35  lea     rcx, [rbp+DestinationString]
0x18002ad39  call    cs:__imp_SamConnect
0x18002ad3f  mov     rcx, [rbp+Buffer]; Buffer
0x18002ad43  mov     edi, eax
0x18002ad45  call    cs:__imp_NetApiBufferFree
0x18002ad4b  test    edi, edi
0x18002ad4d  js      short loc_18002ADBE
0x18002ad4f  mov     rdx, rsi; SourceString
0x18002ad52  lea     rcx, [rbp+var_18]; DestinationString
0x18002ad56  call    cs:__imp_RtlInitUnicodeString
0x18002ad5c  mov     rcx, [rbp+var_30]
0x18002ad60  lea     rdx, [rbp+var_18]
0x18002ad64  mov     r8, rbx
0x18002ad67  call    cs:__imp_SamLookupDomainInSamServer
0x18002ad6d  mov     edi, eax
0x18002ad6f  test    eax, eax
0x18002ad71  js      short loc_18002ADB4
0x18002ad73  mov     r8, [rbx]
0x18002ad76  mov     r9, r14
0x18002ad79  mov     rcx, [rbp+var_30]
0x18002ad7d  mov     edx, 200h
0x18002ad82  call    cs:__imp_SamOpenDomain
0x18002ad88  mov     edi, eax
0x18002ad8a  test    eax, eax
0x18002ad8c  js      short loc_18002ADA4
0x18002ad8e  cmp     [rbp+arg_20], 0
0x18002ad92  jnz     short loc_18002ADB4
0x18002ad94  mov     r9, [r14]
0x18002ad97  mov     rcx, rsi; Source
0x18002ad9a  mov     r8, [rbx]
0x18002ad9d  call    IASSamAddCachedDomain
0x18002ada2  jmp     short loc_18002ADB4
0x18002ada4  mov     rcx, [rbx]
0x18002ada7  call    cs:__imp_SamFreeMemory
0x18002adad  mov     qword ptr [rbx], 0
0x18002adb4  mov     rcx, [rbp+var_30]
0x18002adb8  call    cs:__imp_SamCloseHandle
0x18002adbe  mov     ecx, edi; Status
0x18002adc0  call    cs:__imp_RtlNtStatusToDosError
0x18002adc6  add     rsp, 68h
0x18002adca  pop     r14
0x18002adcc  pop     r12
0x18002adce  pop     rdi
0x18002adcf  pop     rsi
0x18002add0  pop     rbx
0x18002add1  pop     rbp
0x18002add2  retn
```
