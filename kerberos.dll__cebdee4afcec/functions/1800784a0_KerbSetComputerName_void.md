# KerbSetComputerName(void)

- ea: `0x1800784a0`
- end: `0x18007865d`
- name: `?KerbSetComputerName@@YAJXZ`
- size: `445`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180077c00`
- `0x1800802c0`

## callees

- `0x1800068d0`
- `0x1800093f0`
- `0x18000e830`
- `0x1800784a0`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078539`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800784d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007852f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800784d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007852f`
- `ntdll!RtlEqualUnicodeString` at `0x1800785e4`
- `ntdll!RtlEqualUnicodeString` at `0x1800785e4`
- `ntdll!RtlReleaseResource` at `0x180078617`
- `ntdll!RtlReleaseResource` at `0x180078617`
- `ntdll!RtlAcquireResourceExclusive` at `0x180078594`
- `ntdll!RtlAcquireResourceExclusive` at `0x180078594`

## string_xrefs

- `0x1800784e0`: `Succeeded to get computer name when failure expected!`
- `0x1800784ed`: `KerbSetComputerName`
- `0x18007854c`: `KerbSetComputerName`
- `0x1800785fb`: `KerbSetComputerName`
- `0x18007853f`: `Failed to get computer name: %d`
- `0x1800785ee`: `Netbios computer name change detected.\n`

## pseudocode

```c
__int64 KerbSetComputerName(void)
{
  unsigned int v0; // ebx
  WCHAR *v1; // rax
  DWORD LastError; // eax
  unsigned __int64 v3; // rax
  UNICODE_STRING String2; // [rsp+30h] [rbp-40h] BYREF
  struct _STRING v6; // [rsp+40h] [rbp-30h] BYREF
  UNICODE_STRING String1; // [rsp+50h] [rbp-20h] BYREF
  struct _STRING v8; // [rsp+60h] [rbp-10h] BYREF
  DWORD nSize; // [rsp+80h] [rbp+10h] BYREF

  v0 = 0;
  *(_QWORD *)&String2.Length = 0;
  *(_QWORD *)&v6.Length = 0;
  String2.Buffer = 0;
  String1 = 0;
  v6.Buffer = 0;
  nSize = 0;
  if ( GetComputerNameExW(ComputerNameNetBIOS, 0, &nSize) )
  {
    KerbTracerT::Log(1, "KerbSetComputerName", 3247, "Succeeded to get computer name when failure expected!");
LABEL_3:
    v0 = -1073741823;
    goto LABEL_13;
  }
  v1 = (WCHAR *)MIDL_user_allocate(2LL * (nSize + 1));
  String2.Buffer = v1;
  if ( !v1 )
    goto LABEL_5;
  if ( !GetComputerNameExW(ComputerNameNetBIOS, v1, &nSize) )
  {
    LastError = GetLastError();
    KerbTracerT::Log(1, "KerbSetComputerName", 3267, "Failed to get computer name: %d", LastError);
    goto LABEL_3;
  }
  String2.Length = 2 * nSize;
  String2.MaximumLength = 2 * nSize + 2;
  if ( (unsigned int)KerbUnicodeStringToKerbString(&v6, &String2) )
  {
LABEL_5:
    v0 = -1073741670;
    goto LABEL_13;
  }
  RtlAcquireResourceExclusive(&KerberosGlobalResource, 1u);
  String1 = KerbGlobalMachineName;
  v3 = _mm_srli_si128((__m128i)KerbGlobalMachineName, 8).m128i_u64[0];
  KerbGlobalMachineName = String2;
  v8 = KerbGlobalKerbMachineName;
  KerbGlobalKerbMachineName = v6;
  if ( v3 && !RtlEqualUnicodeString(&String1, &String2, 0) )
  {
    KerbTracerT::Log(2, "KerbSetComputerName", 3310, "Netbios computer name change detected.\n");
    KerbGlobalMachineNameChanged = 1;
  }
  RtlReleaseResource(&KerberosGlobalResource);
  String2.Buffer = 0;
  v6.Buffer = 0;
  KerbFreeString((__int64)&String1);
  KerbFreeString((__int64)&v8);
LABEL_13:
  KerbFreeString((__int64)&String2);
  KerbFreeString((__int64)&v6);
  return v0;
}

```

## disassembly

```asm
0x1800784a0  mov     [rsp-8+arg_8], rbx
0x1800784a5  mov     [rsp-8+arg_10], rdi
0x1800784aa  push    rbp
0x1800784ab  mov     rbp, rsp
0x1800784ae  sub     rsp, 70h
0x1800784b2  xor     ebx, ebx
0x1800784b4  lea     r8, [rbp+nSize]; nSize
0x1800784b8  xorps   xmm0, xmm0
0x1800784bb  mov     qword ptr [rbp+String2.Length], rbx
0x1800784bf  xor     edx, edx; lpBuffer
0x1800784c1  mov     qword ptr [rbp+var_30.Length], rbx
0x1800784c5  xor     ecx, ecx; NameType
0x1800784c7  mov     [rbp+String2.Buffer], rbx
0x1800784cb  movups  xmmword ptr [rbp+String1.Length], xmm0
0x1800784cf  mov     [rbp+var_30.Buffer], rbx
0x1800784d3  mov     [rbp+nSize], ebx
0x1800784d6  call    cs:__imp_GetComputerNameExW
0x1800784dc  test    eax, eax
0x1800784de  jz      short loc_180078506
0x1800784e0  lea     r9, aSucceededToGet; "Succeeded to get computer name when fai"...
0x1800784e7  mov     r8d, 0CAFh
0x1800784ed  lea     rdx, aKerbsetcompute_0; "KerbSetComputerName"
0x1800784f4  lea     ecx, [rbx+1]
0x1800784f7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800784fc  mov     ebx, 0C0000001h
0x180078501  jmp     loc_180078637
0x180078506  mov     ecx, [rbp+nSize]
0x180078509  inc     ecx
0x18007850b  add     rcx, rcx; size
0x18007850e  call    MIDL_user_allocate
0x180078513  mov     [rbp+String2.Buffer], rax
0x180078517  test    rax, rax
0x18007851a  jnz     short loc_180078526
0x18007851c  mov     ebx, 0C000009Ah
0x180078521  jmp     loc_180078637
0x180078526  lea     r8, [rbp+nSize]; nSize
0x18007852a  mov     rdx, rax; lpBuffer
0x18007852d  xor     ecx, ecx; NameType
0x18007852f  call    cs:__imp_GetComputerNameExW
0x180078535  test    eax, eax
0x180078537  jnz     short loc_180078563
0x180078539  call    cs:__imp_GetLastError
0x18007853f  lea     r9, aFailedToGetCom; "Failed to get computer name: %d"
0x180078546  mov     r8d, 0CC3h
0x18007854c  lea     rdx, aKerbsetcompute_0; "KerbSetComputerName"
0x180078553  mov     [rsp+70h+var_50], eax
0x180078557  mov     ecx, 1
0x18007855c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180078561  jmp     short loc_1800784FC
0x180078563  movzx   eax, word ptr [rbp+nSize]
0x180078567  lea     rdx, [rbp+String2]; struct _UNICODE_STRING *
0x18007856b  add     ax, ax
0x18007856e  lea     rcx, [rbp+var_30]; struct _STRING *
0x180078572  mov     [rbp+String2.Length], ax
0x180078576  mov     edi, 2
0x18007857b  add     ax, di
0x18007857e  mov     [rbp+String2.MaximumLength], ax
0x180078582  call    ?KerbUnicodeStringToKerbString@@YAJPEAU_STRING@@PEAU_UNICODE_STRING@@@Z; KerbUnicodeStringToKerbString(_STRING *,_UNICODE_STRING *)
0x180078587  test    eax, eax
0x180078589  jnz     short loc_18007851C
0x18007858b  mov     dl, 1; Wait
0x18007858d  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x180078594  call    cs:__imp_RtlAcquireResourceExclusive
0x18007859a  movups  xmm0, xmmword ptr cs:?KerbGlobalMachineName@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING KerbGlobalMachineName ...
0x1800785a1  movups  xmm1, xmmword ptr [rbp+String2.Length]
0x1800785a5  movdqu  xmmword ptr [rbp+String1.Length], xmm0
0x1800785aa  psrldq  xmm0, 8
0x1800785af  movq    rax, xmm0
0x1800785b4  movups  xmm0, cs:?KerbGlobalKerbMachineName@@3U_STRING@@A; _STRING KerbGlobalKerbMachineName
0x1800785bb  movdqu  xmmword ptr cs:?KerbGlobalMachineName@@3U_UNICODE_STRING@@A.Length, xmm1; _UNICODE_STRING KerbGlobalMachineName ...
0x1800785c3  movdqu  [rbp+var_10], xmm0
0x1800785c8  movups  xmm0, xmmword ptr [rbp+var_30.Length]
0x1800785cc  movdqu  cs:?KerbGlobalKerbMachineName@@3U_STRING@@A, xmm0; _STRING KerbGlobalKerbMachineName
0x1800785d4  test    rax, rax
0x1800785d7  jz      short loc_180078610
0x1800785d9  xor     r8d, r8d; CaseInsensitive
0x1800785dc  lea     rdx, [rbp+String2]; String2
0x1800785e0  lea     rcx, [rbp+String1]; String1
0x1800785e4  call    cs:__imp_RtlEqualUnicodeString
0x1800785ea  test    al, al
0x1800785ec  jnz     short loc_180078610
0x1800785ee  lea     r9, aNetbiosCompute; "Netbios computer name change detected."...
0x1800785f5  mov     r8d, 0CEEh
0x1800785fb  lea     rdx, aKerbsetcompute_0; "KerbSetComputerName"
0x180078602  mov     ecx, edi
0x180078604  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180078609  mov     cs:?KerbGlobalMachineNameChanged@@3EA, 1; uchar KerbGlobalMachineNameChanged
0x180078610  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x180078617  call    cs:__imp_RtlReleaseResource
0x18007861d  lea     rcx, [rbp+String1]
0x180078621  mov     [rbp+String2.Buffer], rbx
0x180078625  mov     [rbp+var_30.Buffer], rbx
0x180078629  call    KerbFreeString
0x18007862e  lea     rcx, [rbp+var_10]
0x180078632  call    KerbFreeString
0x180078637  lea     rcx, [rbp+String2]
0x18007863b  call    KerbFreeString
0x180078640  lea     rcx, [rbp+var_30]
0x180078644  call    KerbFreeString
0x180078649  lea     r11, [rsp+70h+var_s0]
0x18007864e  mov     eax, ebx
0x180078650  mov     rbx, [r11+18h]
0x180078654  mov     rdi, [r11+20h]
0x180078658  mov     rsp, r11
0x18007865b  pop     rbp
0x18007865c  retn
```
