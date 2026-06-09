# MQSec_CalculateServiceSid(void * *)

- ea: `0x1800216f0`
- end: `0x180021856`
- name: `?MQSec_CalculateServiceSid@@YAJPEAPEAX@Z`
- size: `358`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180029610`
- `0x180029b50`
- `0x18002ba00`

## callees

- `0x180004074`
- `0x18000d940`
- `0x18001722c`
- `0x180017430`
- `0x1800216f0`
- `0x18002f0e0`

## import_xrefs

- `msvcrt!free` at `0x180021822`
- `msvcrt!free` at `0x180021832`
- `msvcrt!free` at `0x180021822`
- `msvcrt!free` at `0x180021832`
- `ntdll!RtlInitUnicodeString` at `0x1800217c7`
- `ntdll!RtlInitUnicodeString` at `0x1800217c7`
- `ntdll!RtlCreateServiceSid` at `0x1800217e1`
- `ntdll!RtlCreateServiceSid` at `0x180021813`
- `ntdll!RtlCreateServiceSid` at `0x1800217e1`
- `ntdll!RtlCreateServiceSid` at `0x180021813`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MQSec_CalculateServiceSid(void **a1)
{
  int FalconServiceName; // ebx
  unsigned int v3; // eax
  void *v5; // rbx
  NTSTATUS v6; // edi
  __int16 v7; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ServiceSidLength; // [rsp+68h] [rbp-98h] BYREF
  void *v9; // [rsp+70h] [rbp-90h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SourceString[304]; // [rsp+90h] [rbp-70h] BYREF

  FalconServiceName = GetFalconServiceName(SourceString, 0x12Cu);
  if ( FalconServiceName >= 0 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
    ServiceSidLength = 0;
    if ( RtlCreateServiceSid(&DestinationString, 0, &ServiceSidLength) == -1073741789 )
    {
      v5 = MmAllocate(ServiceSidLength);
      v9 = v5;
      v6 = RtlCreateServiceSid(&DestinationString, v5, &ServiceSidLength);
      if ( v6 >= 0 )
      {
        *a1 = v5;
        free(0);
        return 0;
      }
      else
      {
        free(v5);
        return (unsigned int)v6;
      }
    }
    else
    {
      return 2147549183LL;
    }
  }
  else
  {
    v7 = 200;
    LODWORD(v9) = FalconServiceName;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v3 = mqwcslen(L"acssctrl/acssinit");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v3 + 1),
        L"acssctrl/acssinit",
        2,
        &v7,
        4,
        &v9,
        0,
        0);
    }
    return (unsigned int)FalconServiceName;
  }
}

```

## disassembly

```asm
0x1800216f0  push    rbp
0x1800216f2  push    rbx
0x1800216f3  push    rsi
0x1800216f4  push    rdi
0x1800216f5  lea     rbp, [rsp-208h]
0x1800216fd  sub     rsp, 308h
0x180021704  mov     rax, cs:__security_cookie
0x18002170b  xor     rax, rsp
0x18002170e  mov     [rbp+220h+var_30], rax
0x180021715  mov     rsi, rcx
0x180021718  mov     edx, 12Ch; unsigned int
0x18002171d  lea     rcx, [rbp+220h+SourceString]; wchar_t *
0x180021721  call    ?GetFalconServiceName@@YAJPEA_WK@Z; GetFalconServiceName(wchar_t *,ulong)
0x180021726  mov     ebx, eax
0x180021728  test    eax, eax
0x18002172a  jns     loc_1800217B6
0x180021730  mov     eax, 0C8h
0x180021735  mov     [rsp+320h+var_2C0], ax
0x18002173a  mov     dword ptr [rsp+320h+var_2B0], ebx
0x18002173e  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180021746  jz      short loc_1800217AF
0x180021748  lea     rdi, aAcssctrlAcssin; "acssctrl/acssinit"
0x18002174f  mov     rcx, rdi; wchar_t *
0x180021752  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180021757  mov     edx, 1
0x18002175c  lea     r9d, [rdx+rax]
0x180021760  add     r9, r9
0x180021763  mov     [rsp+320h+var_2D0], 0
0x18002176c  mov     [rsp+320h+var_2D8], 0
0x180021775  lea     rax, [rsp+320h+var_2B0]
0x18002177a  mov     [rsp+320h+var_2E0], rax
0x18002177f  mov     [rsp+320h+var_2E8], 4
0x180021788  lea     rax, [rsp+320h+var_2C0]
0x18002178d  mov     [rsp+320h+var_2F0], rax
0x180021792  mov     [rsp+320h+var_2F8], 2
0x18002179b  mov     [rsp+320h+var_300], rdi
0x1800217a0  mov     r8d, edx
0x1800217a3  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800217aa  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800217af  mov     eax, ebx
0x1800217b1  jmp     loc_18002183B
0x1800217b6  xorps   xmm0, xmm0
0x1800217b9  movups  xmmword ptr [rsp+320h+DestinationString.Length], xmm0
0x1800217be  lea     rdx, [rbp+220h+SourceString]; SourceString
0x1800217c2  lea     rcx, [rsp+320h+DestinationString]; DestinationString
0x1800217c7  call    cs:__imp_RtlInitUnicodeString
0x1800217cd  mov     [rsp+320h+ServiceSidLength], 0
0x1800217d5  lea     r8, [rsp+320h+ServiceSidLength]; ServiceSidLength
0x1800217da  xor     edx, edx; ServiceSid
0x1800217dc  lea     rcx, [rsp+320h+DestinationString]; ServiceName
0x1800217e1  call    cs:__imp_RtlCreateServiceSid
0x1800217e7  cmp     eax, 0C0000023h
0x1800217ec  jz      short loc_1800217F5
0x1800217ee  mov     eax, 8000FFFFh
0x1800217f3  jmp     short loc_18002183B
0x1800217f5  mov     ecx, [rsp+320h+ServiceSidLength]; unsigned __int64
0x1800217f9  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800217fe  mov     rbx, rax
0x180021801  mov     [rsp+320h+var_2B0], rax
0x180021806  lea     r8, [rsp+320h+ServiceSidLength]; ServiceSidLength
0x18002180b  mov     rdx, rax; ServiceSid
0x18002180e  lea     rcx, [rsp+320h+DestinationString]; ServiceName
0x180021813  call    cs:__imp_RtlCreateServiceSid
0x180021819  mov     edi, eax
0x18002181b  test    eax, eax
0x18002181d  jns     short loc_18002182D
0x18002181f  mov     rcx, rbx; Block
0x180021822  call    cs:__imp_free
0x180021828  nop
0x180021829  mov     eax, edi
0x18002182b  jmp     short loc_18002183B
0x18002182d  mov     [rsi], rbx
0x180021830  xor     ecx, ecx; Block
0x180021832  call    cs:__imp_free
0x180021838  nop
0x180021839  xor     eax, eax
0x18002183b  mov     rcx, [rbp+220h+var_30]
0x180021842  xor     rcx, rsp; StackCookie
0x180021845  call    __security_check_cookie
0x18002184a  add     rsp, 308h
0x180021851  pop     rdi
0x180021852  pop     rsi
0x180021853  pop     rbx
0x180021854  pop     rbp
0x180021855  retn
```
