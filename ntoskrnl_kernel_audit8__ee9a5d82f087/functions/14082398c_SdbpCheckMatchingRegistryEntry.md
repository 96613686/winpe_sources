# SdbpCheckMatchingRegistryEntry

- ea: `0x14082398c`
- end: `0x140823b62`
- name: `SdbpCheckMatchingRegistryEntry`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140823860`

## callees

- `0x140403380`
- `0x140481fa0`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406ddaa0`
- `0x14082398c`
- `0x140823b68`
- `0x1408c2f88`

## string_xrefs

- `0x1408239f0`: `\REGISTRY\MACHINE\%s`
- `0x140823a2b`: `SdbpCheckMatchingRegistryEntry`
- `0x140823ab4`: `SdbpCheckMatchingRegistryEntry`
- `0x140823a1e`: `Failed to construct full key path`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingRegistryEntry(
        __int64 a1,
        void *a2,
        unsigned int a3,
        void *a4,
        int a5,
        __int64 a6,
        void *a7,
        size_t a8,
        _DWORD *a9)
{
  unsigned int v12; // edi
  __int64 v14; // [rsp+20h] [rbp-E0h]
  HANDLE KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int64 v18; // [rsp+98h] [rbp-68h] BYREF
  int v19; // [rsp+A0h] [rbp-60h]
  wchar_t pszDest[264]; // [rsp+B0h] [rbp-50h] BYREF

  pszDest[0] = 0;
  v18 = 0;
  *a9 = 0;
  v19 = 0;
  KeyHandle = 0;
  v12 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( RtlStringCchPrintfW(pszDest, 0x104u, L"\\REGISTRY\\MACHINE\\%s", a1) < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpCheckMatchingRegistryEntry",
      1538,
      (unsigned int)"Failed to construct full key path");
    goto LABEL_10;
  }
  RtlInitUnicodeString(&DestinationString, pszDest);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
    goto LABEL_9;
  if ( (int)ZwQuerySystemInformation(1, &v18, 12) < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpCheckMatchingRegistryEntry",
      1573,
      (unsigned int)"Failed to get processor architecture [%x]");
    goto LABEL_10;
  }
  if ( (_WORD)v18 == 9 && ZwOpenKey(&KeyHandle, 0x20219u, &ObjectAttributes) >= 0 )
  {
LABEL_9:
    LODWORD(v14) = a5;
    v12 = SdbpCheckMatchingRegistryValue((__int64)KeyHandle, a2, a3, a4, v14, a6, a7, a8, a9);
  }
  else
  {
    v12 = 1;
  }
LABEL_10:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v12;
}

```

## disassembly

```asm
0x14082398c  push    rbp
0x14082398e  push    rsi
0x14082398f  push    rdi
0x140823990  push    r12
0x140823992  push    r13
0x140823994  push    r14
0x140823996  push    r15
0x140823998  lea     rbp, [rsp-1D0h]
0x1408239a0  sub     rsp, 2D0h
0x1408239a7  mov     rax, cs:__security_cookie
0x1408239ae  xor     rax, rsp
0x1408239b1  mov     [rbp+200h+var_40], rax
0x1408239b8  mov     rsi, [rbp+200h+arg_40]
0x1408239bf  xor     eax, eax
0x1408239c1  mov     r13, [rbp+200h+arg_30]
0x1408239c8  xorps   xmm1, xmm1
0x1408239cb  mov     r12, r9
0x1408239ce  mov     [rbp+200h+pszDest], ax
0x1408239d2  mov     r14d, r8d
0x1408239d5  mov     [rbp+200h+var_268], rax
0x1408239d9  mov     r15, rdx
0x1408239dc  mov     dword ptr [rsi], 0
0x1408239e2  xorps   xmm0, xmm0
0x1408239e5  mov     [rbp+200h+var_260], eax
0x1408239e8  mov     r9, rcx
0x1408239eb  mov     [rsp+300h+KeyHandle], rax
0x1408239f0  lea     r8, aRegistryMachin_103; "\\REGISTRY\\MACHINE\\%s"
0x1408239f7  mov     edx, 104h; cchDest
0x1408239fc  lea     rcx, [rbp+200h+pszDest]; pszDest
0x140823a00  xor     edi, edi
0x140823a02  movups  xmmword ptr [rbp+200h+DestinationString.Length], xmm0
0x140823a06  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm1
0x140823a0b  movups  xmmword ptr [rsp+300h+ObjectAttributes.ObjectName], xmm1
0x140823a10  movups  xmmword ptr [rsp+300h+ObjectAttributes.SecurityDescriptor], xmm1
0x140823a15  call    RtlStringCchPrintfW
0x140823a1a  test    eax, eax
0x140823a1c  jns     short loc_140823A3F
0x140823a1e  lea     r9, aFailedToConstr; "Failed to construct full key path"
0x140823a25  mov     r8d, 602h
0x140823a2b  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x140823a32  lea     ecx, [rdi+1]
0x140823a35  call    AslLogCallPrintf
0x140823a3a  jmp     loc_140823B2E
0x140823a3f  lea     rdx, [rbp+200h+pszDest]; SourceString
0x140823a43  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x140823a47  call    RtlInitUnicodeString
0x140823a4c  lea     rax, [rbp+200h+DestinationString]
0x140823a50  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x140823a58  xorps   xmm0, xmm0
0x140823a5b  mov     [rsp+300h+ObjectAttributes.ObjectName], rax
0x140823a60  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x140823a65  mov     [rsp+300h+ObjectAttributes.RootDirectory], rdi
0x140823a6a  mov     edx, 20019h; DesiredAccess
0x140823a6f  mov     [rsp+300h+ObjectAttributes.Attributes], 240h
0x140823a77  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x140823a7c  movdqu  xmmword ptr [rsp+300h+ObjectAttributes.SecurityDescriptor], xmm0
0x140823a82  call    ZwOpenKey
0x140823a87  test    eax, eax
0x140823a89  jns     short loc_140823AED
0x140823a8b  xor     r9d, r9d
0x140823a8e  lea     rdx, [rbp+200h+var_268]
0x140823a92  lea     r8d, [r9+0Ch]
0x140823a96  lea     ecx, [r9+1]
0x140823a9a  call    ZwQuerySystemInformation
0x140823a9f  test    eax, eax
0x140823aa1  jns     short loc_140823AC7
0x140823aa3  lea     r9, aFailedToGetPro; "Failed to get processor architecture [%"...
0x140823aaa  mov     dword ptr [rsp+300h+var_2E0], eax
0x140823aae  mov     r8d, 625h
0x140823ab4  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x140823abb  mov     ecx, 1
0x140823ac0  call    AslLogCallPrintf
0x140823ac5  jmp     short loc_140823B2E
0x140823ac7  cmp     word ptr [rbp+200h+var_268], 9
0x140823acc  jz      short loc_140823AD5
0x140823ace  mov     edi, 1
0x140823ad3  jmp     short loc_140823B2E
0x140823ad5  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x140823ada  mov     edx, 20219h; DesiredAccess
0x140823adf  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x140823ae4  call    ZwOpenKey
0x140823ae9  test    eax, eax
0x140823aeb  js      short loc_140823ACE
0x140823aed  mov     rax, [rbp+200h+arg_38]
0x140823af4  mov     r9, r12
0x140823af7  mov     rcx, [rsp+300h+KeyHandle]
0x140823afc  mov     r8d, r14d
0x140823aff  mov     [rsp+300h+var_2C0], rsi
0x140823b04  mov     rdx, r15
0x140823b07  mov     [rsp+300h+var_2C8], rax
0x140823b0c  mov     rax, [rbp+200h+arg_28]
0x140823b13  mov     [rsp+300h+var_2D0], r13
0x140823b18  mov     [rsp+300h+var_2D8], rax
0x140823b1d  mov     eax, [rbp+200h+arg_20]
0x140823b23  mov     dword ptr [rsp+300h+var_2E0], eax
0x140823b27  call    SdbpCheckMatchingRegistryValue
0x140823b2c  mov     edi, eax
0x140823b2e  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x140823b33  test    rcx, rcx
0x140823b36  jz      short loc_140823B3D
0x140823b38  call    ZwClose
0x140823b3d  mov     eax, edi
0x140823b3f  mov     rcx, [rbp+200h+var_40]
0x140823b46  xor     rcx, rsp; StackCookie
0x140823b49  call    __security_check_cookie
0x140823b4e  add     rsp, 2D0h
0x140823b55  pop     r15
0x140823b57  pop     r14
0x140823b59  pop     r13
0x140823b5b  pop     r12
0x140823b5d  pop     rdi
0x140823b5e  pop     rsi
0x140823b5f  pop     rbp
0x140823b60  retn
```
