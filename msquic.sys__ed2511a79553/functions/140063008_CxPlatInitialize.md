# CxPlatInitialize

- ea: `0x140063008`
- end: `0x1400631b2`
- name: `CxPlatInitialize`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140023f20`

## callees

- `0x1400340c8`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003e928`
- `0x14003ead8`
- `0x140063008`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140063176`
- `ntoskrnl!_snprintf_s` at `0x140063176`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400630cc`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400630cc`
- `ntoskrnl!RtlGetVersion` at `0x140063069`
- `ntoskrnl!RtlGetVersion` at `0x140063069`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140063038`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140063038`
- `cng!BCryptOpenAlgorithmProvider` at `0x14006309a`
- `cng!BCryptOpenAlgorithmProvider` at `0x14006309a`
- `cng!BCryptCloseAlgorithmProvider` at `0x140063121`
- `cng!BCryptCloseAlgorithmProvider` at `0x140063121`

## string_xrefs

- `0x1400630b5`: `BCryptOpenAlgorithmProvider (RNG)`

## pseudocode

```c
__int64 CxPlatInitialize()
{
  int v0; // eax
  __int64 v1; // rdx
  __int64 v2; // rcx
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // rcx
  _DWORD SystemInformation[16]; // [rsp+30h] [rbp-1F8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-1B8h] BYREF
  char DstBuf[128]; // [rsp+190h] [rbp-98h] BYREF

  memset(SystemInformation, 0, sizeof(SystemInformation));
  CxPlatProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
  memset(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( RtlGetVersion(&VersionInformation) >= 0 )
    dword_14005DA50 = VersionInformation.dwBuildNumber;
  v0 = BCryptOpenAlgorithmProvider(&CxPlatform, L"RNG", 0, 1u);
  v3 = v0;
  if ( v0 < 0 )
  {
    if ( (Microsoft_QuicEnableBits & 4) == 0 )
      goto LABEL_13;
    v4 = "BCryptOpenAlgorithmProvider (RNG)";
    goto LABEL_12;
  }
  v0 = ZwQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
  v3 = v0;
  if ( v0 < 0 )
  {
    if ( (Microsoft_QuicEnableBits & 4) == 0 )
      goto LABEL_13;
    v4 = "ZwQuerySystemInformation(SystemBasicInformation)";
    goto LABEL_12;
  }
  v0 = CxPlatCryptInitialize();
  v3 = v0;
  if ( v0 < 0 )
  {
    if ( (Microsoft_QuicEnableBits & 4) == 0 )
      goto LABEL_13;
    v4 = "CxPlatCryptInitialize";
LABEL_12:
    McTemplateU0qs_EtwWriteTransfer(v2, v1, (unsigned int)v0, v4);
LABEL_13:
    if ( CxPlatform )
    {
      BCryptCloseAlgorithmProvider(CxPlatform, 0);
      CxPlatform = 0;
    }
    return v3;
  }
  CxPlatTotalMemory = SystemInformation[3] * (unsigned __int64)SystemInformation[2];
  if ( (byte_14005C48E & 0x40) != 0 )
  {
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "[ sys] Initialized (PageSize = %u bytes; AvailMem = %llu bytes)",
      SystemInformation[2],
      SystemInformation[3] * (unsigned __int64)SystemInformation[2]);
    McTemplateU0s_EtwWriteTransfer(v5, QuicLogInfo, DstBuf);
  }
  return v3;
}

```

## disassembly

```asm
0x140063008  push    rbx
0x14006300a  sub     rsp, 220h
0x140063011  mov     rax, cs:__security_cookie
0x140063018  xor     rax, rsp
0x14006301b  mov     [rsp+228h+var_18], rax
0x140063023  xor     edx, edx; Val
0x140063025  lea     rcx, [rsp+228h+SystemInformation]; void *
0x14006302a  lea     r8d, [rdx+40h]; Size
0x14006302e  call    memset
0x140063033  mov     ecx, 0FFFFh; GroupNumber
0x140063038  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14006303f  nop     dword ptr [rax+rax+00h]
0x140063044  xor     edx, edx; Val
0x140063046  lea     rcx, [rsp+228h+VersionInformation.dwMajorVersion]; void *
0x14006304b  mov     r8d, 110h; Size
0x140063051  mov     cs:CxPlatProcessorCount, eax
0x140063057  call    memset
0x14006305c  lea     rcx, [rsp+228h+VersionInformation]; lpVersionInformation
0x140063061  mov     [rsp+228h+VersionInformation.dwOSVersionInfoSize], 114h
0x140063069  call    cs:__imp_RtlGetVersion
0x140063070  nop     dword ptr [rax+rax+00h]
0x140063075  test    eax, eax
0x140063077  js      short loc_140063083
0x140063079  mov     eax, [rsp+228h+VersionInformation.dwBuildNumber]
0x14006307d  mov     cs:dword_14005DA50, eax
0x140063083  mov     r9d, 1; dwFlags
0x140063089  lea     rdx, aRng; "RNG"
0x140063090  xor     r8d, r8d; pszImplementation
0x140063093  lea     rcx, CxPlatform; phAlgorithm
0x14006309a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400630a1  nop     dword ptr [rax+rax+00h]
0x1400630a6  mov     ebx, eax
0x1400630a8  test    eax, eax
0x1400630aa  jns     short loc_1400630BE
0x1400630ac  test    cs:Microsoft_QuicEnableBits, 4
0x1400630b3  jz      short loc_140063113
0x1400630b5  lea     r9, aBcryptopenalgo; "BCryptOpenAlgorithmProvider (RNG)"
0x1400630bc  jmp     short loc_14006310B
0x1400630be  xor     r9d, r9d; ReturnLength
0x1400630c1  lea     rdx, [rsp+228h+SystemInformation]; SystemInformation
0x1400630c6  xor     ecx, ecx; SystemInformationClass
0x1400630c8  lea     r8d, [r9+40h]; SystemInformationLength
0x1400630cc  call    cs:__imp_ZwQuerySystemInformation
0x1400630d3  nop     dword ptr [rax+rax+00h]
0x1400630d8  mov     ebx, eax
0x1400630da  test    eax, eax
0x1400630dc  jns     short loc_1400630F0
0x1400630de  test    cs:Microsoft_QuicEnableBits, 4
0x1400630e5  jz      short loc_140063113
0x1400630e7  lea     r9, aZwquerysystemi; "ZwQuerySystemInformation(SystemBasicInf"...
0x1400630ee  jmp     short loc_14006310B
0x1400630f0  call    CxPlatCryptInitialize
0x1400630f5  mov     ebx, eax
0x1400630f7  test    eax, eax
0x1400630f9  jns     short loc_140063137
0x1400630fb  test    cs:Microsoft_QuicEnableBits, 4
0x140063102  jz      short loc_140063113
0x140063104  lea     r9, aCxplatcryptini; "CxPlatCryptInitialize"
0x14006310b  mov     r8d, eax
0x14006310e  call    McTemplateU0qs_EtwWriteTransfer
0x140063113  mov     rcx, cs:CxPlatform; hAlgorithm
0x14006311a  test    rcx, rcx
0x14006311d  jz      short loc_140063196
0x14006311f  xor     edx, edx; dwFlags
0x140063121  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140063128  nop     dword ptr [rax+rax+00h]
0x14006312d  and     cs:CxPlatform, 0
0x140063135  jmp     short loc_140063196
0x140063137  mov     edx, [rsp+228h+var_1F0]
0x14006313b  mov     eax, [rsp+228h+var_1EC]
0x14006313f  mov     ecx, edx
0x140063141  imul    rcx, rax
0x140063145  test    cs:byte_14005C48E, 40h
0x14006314c  mov     cs:CxPlatTotalMemory, rcx
0x140063153  jz      short loc_140063196
0x140063155  mov     [rsp+228h+var_200], rcx
0x14006315a  lea     r9, aSysInitialized; "[ sys] Initialized (PageSize = %u bytes"...
0x140063161  mov     [rsp+228h+var_208], edx
0x140063165  lea     rcx, [rsp+228h+DstBuf]; DstBuf
0x14006316d  mov     edx, 80h; SizeInBytes
0x140063172  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140063176  call    cs:__imp__snprintf_s
0x14006317d  nop     dword ptr [rax+rax+00h]
0x140063182  lea     r8, [rsp+228h+DstBuf]
0x14006318a  lea     rdx, QuicLogInfo
0x140063191  call    McTemplateU0s_EtwWriteTransfer
0x140063196  mov     eax, ebx
0x140063198  mov     rcx, [rsp+228h+var_18]
0x1400631a0  xor     rcx, rsp; StackCookie
0x1400631a3  call    __security_check_cookie
0x1400631a8  add     rsp, 220h
0x1400631af  pop     rbx
0x1400631b0  retn
```
