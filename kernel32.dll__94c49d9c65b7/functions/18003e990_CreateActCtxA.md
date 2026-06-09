# CreateActCtxA

- ea: `0x18003e990`
- end: `0x18003eca3`
- name: `CreateActCtxA`
- size: `787`
- prototype: `HANDLE __stdcall(PCACTCTXA pActCtx)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000e270`
- `0x18000f920`
- `0x18003e990`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18003ebca`
- `ntdll!DbgPrintEx` at `0x18003ec23`
- `ntdll!DbgPrintEx` at `0x18003ebca`
- `ntdll!DbgPrintEx` at `0x18003ec23`
- `ntdll!RtlFreeUnicodeString` at `0x18003ec3b`
- `ntdll!RtlFreeUnicodeString` at `0x18003ec59`
- `ntdll!RtlFreeUnicodeString` at `0x18003ec3b`
- `ntdll!RtlFreeUnicodeString` at `0x18003ec59`
- `ntdll!RtlInitAnsiString` at `0x18003eab6`
- `ntdll!RtlInitAnsiString` at `0x18003eb45`
- `ntdll!RtlInitAnsiString` at `0x18003eab6`
- `ntdll!RtlInitAnsiString` at `0x18003eb45`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x18003eabc`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x18003eb5e`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x18003eabc`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x18003eb5e`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18003ec62`
- `KERNELBASE!BaseDllFreeResourceId` at `0x18003ec62`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18003ebe2`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18003ebe2`

## string_xrefs

- `0x18003ebc0`: `SXS: %s() BaseDllMapResourceIdA failed\n`
- `0x18003ebb7`: `CreateActCtxA`
- `0x18003ec19`: `CreateActCtxA`

## pseudocode

```c
HANDLE __stdcall CreateActCtxA(PCACTCTXA pActCtx)
{
  __int64 v1; // rsi
  const WCHAR *v2; // r14
  struct _TEB *v4; // r13
  __int64 cbSize; // r9
  USHORT *p_wProcessorArchitecture; // r15
  const ACTCTXA *v7; // rdx
  DWORD dwFlags; // ecx
  const char *lpSource; // rdx
  __int64 (__fastcall *EightBitStringToUnicodeStringRoutine)(struct _UNICODE_STRING *, struct _STRING *, __int64); // rax
  __int64 v11; // r8
  int v12; // eax
  unsigned int LastStatusValue; // ebx
  __int64 (__fastcall *v14)(struct _UNICODE_STRING *, struct _STRING *, _QWORD); // rax
  unsigned int v15; // eax
  const WCHAR *v16; // rax
  struct _UNICODE_STRING v18; // [rsp+30h] [rbp-D0h] BYREF
  struct _STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-B0h] BYREF
  ACTCTXW pActCtxa; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[528]; // [rsp+A0h] [rbp-60h] BYREF

  pActCtxa.cbSize = 56;
  v1 = -1;
  v2 = 0;
  memset(&pActCtxa.dwFlags, 0, 52);
  UnicodeString = 0;
  DestinationString = 0;
  v18 = 0;
  v4 = NtCurrentTeb();
  if ( !pActCtx
    || (cbSize = pActCtx->cbSize,
        p_wProcessorArchitecture = &pActCtx->wProcessorArchitecture,
        v7 = (PCACTCTXA)((char *)pActCtx + cbSize),
        &pActCtx->wProcessorArchitecture > (USHORT *)((char *)pActCtx + cbSize)) )
  {
    DbgPrintEx(0x33u, 0, "SXS: %s() Null %p or size 0x%lx too small\n", "CreateActCtxA", pActCtx, pActCtx->cbSize);
    goto LABEL_42;
  }
  dwFlags = pActCtx->dwFlags;
  pActCtxa.dwFlags = dwFlags;
  if ( (dwFlags & 0xFFFFFF00) != 0
    || (dwFlags & 1) != 0 && &pActCtx->wLangId > (LANGID *)v7
    || (dwFlags & 2) != 0 && &pActCtx->wLangId + 1 > (LANGID *)v7
    || (dwFlags & 4) != 0 && &pActCtx->lpResourceName > (LPCSTR *)v7
    || (dwFlags & 8) != 0 && &pActCtx->lpApplicationName > (LPCSTR *)v7
    || (dwFlags & 0x20) != 0 && &pActCtx->hModule > (HMODULE *)v7
    || (dwFlags & 0x80) != 0 && &pActCtx[1] > v7 )
  {
    DbgPrintEx(0x33u, 0, "SXS: %s() Bad flags/size 0x%lx/0x%lx\n", "CreateActCtxA", dwFlags, cbSize);
    goto LABEL_42;
  }
  lpSource = pActCtx->lpSource;
  if ( !lpSource )
  {
    if ( (dwFlags & 0x80) != 0 )
    {
      LastStatusValue = 0;
      pActCtxa.lpSource = 0;
      goto LABEL_23;
    }
LABEL_42:
    LastStatusValue = -1073741811;
    goto LABEL_43;
  }
  RtlInitAnsiString(&DestinationString, lpSource);
  EightBitStringToUnicodeStringRoutine = (__int64 (__fastcall *)(struct _UNICODE_STRING *, struct _STRING *, __int64))GetEightBitStringToUnicodeStringRoutine();
  LOBYTE(v11) = 1;
  v12 = EightBitStringToUnicodeStringRoutine(&UnicodeString, &DestinationString, v11);
  LastStatusValue = v12;
  if ( v12 < 0 )
  {
    if ( v12 != -2147483643 )
      goto LABEL_43;
    goto LABEL_19;
  }
  LOBYTE(dwFlags) = pActCtxa.dwFlags;
  pActCtxa.lpSource = UnicodeString.Buffer;
LABEL_23:
  if ( (dwFlags & 1) != 0 )
    pActCtxa.wProcessorArchitecture = *p_wProcessorArchitecture;
  if ( (dwFlags & 2) != 0 )
    pActCtxa.wLangId = pActCtx->wLangId;
  if ( (dwFlags & 0x80u) != 0 )
    pActCtxa.hModule = pActCtx->hModule;
  if ( (dwFlags & 4) != 0 )
  {
    RtlInitAnsiString(&DestinationString, pActCtx->lpAssemblyDirectory);
    v18.MaximumLength = 522;
    v18.Buffer = (PWSTR)v22;
    v14 = (__int64 (__fastcall *)(struct _UNICODE_STRING *, struct _STRING *, _QWORD))GetEightBitStringToUnicodeStringRoutine();
    v15 = v14(&v18, &DestinationString, 0);
    LastStatusValue = v15;
    if ( v15 == -2147483643 )
    {
LABEL_19:
      LastStatusValue = -1073741562;
      goto LABEL_43;
    }
    if ( (v15 & 0xC0000000) == 0xC0000000 )
      goto LABEL_43;
    LOBYTE(dwFlags) = pActCtxa.dwFlags;
    pActCtxa.lpAssemblyDirectory = v18.Buffer;
  }
  if ( (dwFlags & 8) != 0 )
  {
    v16 = (const WCHAR *)BaseDllMapResourceIdA(pActCtx->lpResourceName);
    v2 = v16;
    if ( v16 == (const WCHAR *)-1LL )
    {
      DbgPrintEx(0x33u, 0, "SXS: %s() BaseDllMapResourceIdA failed\n", "CreateActCtxA");
LABEL_36:
      LastStatusValue = v4->LastStatusValue;
      goto LABEL_43;
    }
    pActCtxa.lpResourceName = v16;
  }
  v1 = (__int64)CreateActCtxW(&pActCtxa);
  if ( v1 == -1 )
    goto LABEL_36;
LABEL_43:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v18.Buffer && (_BYTE *)v18.Buffer != v22 )
    RtlFreeUnicodeString(&v18);
  BaseDllFreeResourceId(v2);
  if ( v1 == -1 )
    BaseSetLastNTError(LastStatusValue);
  return (HANDLE)v1;
}

```

## disassembly

```asm
0x18003e990  mov     [rsp-8+arg_8], rbx
0x18003e995  mov     [rsp-8+arg_10], rsi
0x18003e99a  push    rbp
0x18003e99b  push    rdi
0x18003e99c  push    r13
0x18003e99e  push    r14
0x18003e9a0  push    r15
0x18003e9a2  lea     rbp, [rsp-1C0h]
0x18003e9aa  sub     rsp, 2C0h
0x18003e9b1  mov     rax, cs:__security_cookie
0x18003e9b8  xor     rax, rsp
0x18003e9bb  mov     [rbp+1E0h+var_30], rax
0x18003e9c2  xorps   xmm0, xmm0
0x18003e9c5  mov     [rsp+2E0h+pActCtx.cbSize], 38h ; '8'
0x18003e9cd  xor     eax, eax
0x18003e9cf  xorps   xmm1, xmm1
0x18003e9d2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003e9d6  mov     dword ptr [rbp+1E0h+pActCtx.hModule+4], eax
0x18003e9d9  xor     r14d, r14d
0x18003e9dc  mov     rdi, rcx
0x18003e9df  movups  xmmword ptr [rsp+2E0h+pActCtx.dwFlags], xmm0
0x18003e9e4  movups  xmmword ptr [rsp+2E0h+pActCtx+14h], xmm0
0x18003e9e9  movups  xmmword ptr [rbp+1E0h+pActCtx.lpResourceName+4], xmm0
0x18003e9ed  movups  xmmword ptr [rsp+2E0h+UnicodeString.Length], xmm0
0x18003e9f2  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm1
0x18003e9f7  movups  xmmword ptr [rsp+2E0h+var_2B0.Length], xmm0
0x18003e9fc  mov     r13, gs:30h
0x18003ea05  test    rcx, rcx
0x18003ea08  jz      loc_18003EC05
0x18003ea0e  mov     r9d, [rcx]
0x18003ea11  lea     r15, [rcx+10h]
0x18003ea15  lea     rdx, [r9+rcx]
0x18003ea19  cmp     r15, rdx
0x18003ea1c  ja      loc_18003EC05
0x18003ea22  mov     ecx, [rcx+4]
0x18003ea25  mov     [rsp+2E0h+pActCtx.dwFlags], ecx
0x18003ea29  test    ecx, 0FFFFFF00h
0x18003ea2f  jnz     loc_18003EBF3
0x18003ea35  test    cl, 1
0x18003ea38  jz      short loc_18003EA47
0x18003ea3a  lea     rax, [rdi+12h]
0x18003ea3e  cmp     rax, rdx
0x18003ea41  ja      loc_18003EBF3
0x18003ea47  test    cl, 2
0x18003ea4a  jz      short loc_18003EA59
0x18003ea4c  lea     rax, [rdi+14h]
0x18003ea50  cmp     rax, rdx
0x18003ea53  ja      loc_18003EBF3
0x18003ea59  test    cl, 4
0x18003ea5c  jz      short loc_18003EA6B
0x18003ea5e  lea     rax, [rdi+20h]
0x18003ea62  cmp     rax, rdx
0x18003ea65  ja      loc_18003EBF3
0x18003ea6b  test    cl, 8
0x18003ea6e  jz      short loc_18003EA7D
0x18003ea70  lea     rax, [rdi+28h]
0x18003ea74  cmp     rax, rdx
0x18003ea77  ja      loc_18003EBF3
0x18003ea7d  test    cl, 20h
0x18003ea80  jz      short loc_18003EA8F
0x18003ea82  lea     rax, [rdi+30h]
0x18003ea86  cmp     rax, rdx
0x18003ea89  ja      loc_18003EBF3
0x18003ea8f  mov     r8d, ecx
0x18003ea92  and     r8d, 80h
0x18003ea99  jz      short loc_18003EAA8
0x18003ea9b  lea     rax, [rdi+38h]
0x18003ea9f  cmp     rax, rdx
0x18003eaa2  ja      loc_18003EBF3
0x18003eaa8  mov     rdx, [rdi+8]; SourceString
0x18003eaac  test    rdx, rdx
0x18003eaaf  jz      short loc_18003EAFF
0x18003eab1  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x18003eab6  call    cs:__imp_RtlInitAnsiString
0x18003eabc  call    cs:__imp_GetEightBitStringToUnicodeStringRoutine
0x18003eac2  mov     r8b, 1
0x18003eac5  lea     rdx, [rsp+2E0h+DestinationString]
0x18003eaca  lea     rcx, [rsp+2E0h+UnicodeString]
0x18003eacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ead4  mov     ebx, eax
0x18003ead6  test    eax, eax
0x18003ead8  jns     short loc_18003EAEF
0x18003eada  cmp     eax, 80000005h
0x18003eadf  jnz     loc_18003EC2E
0x18003eae5  mov     ebx, 0C0000106h
0x18003eaea  jmp     loc_18003EC2E
0x18003eaef  mov     rax, [rsp+2E0h+UnicodeString.Buffer]
0x18003eaf4  mov     ecx, [rsp+2E0h+pActCtx.dwFlags]
0x18003eaf8  mov     [rsp+2E0h+pActCtx.lpSource], rax
0x18003eafd  jmp     short loc_18003EB0F
0x18003eaff  test    r8d, r8d
0x18003eb02  jz      loc_18003EC29
0x18003eb08  xor     ebx, ebx
0x18003eb0a  mov     [rsp+2E0h+pActCtx.lpSource], rbx
0x18003eb0f  test    cl, 1
0x18003eb12  jz      short loc_18003EB1D
0x18003eb14  movzx   eax, word ptr [r15]
0x18003eb18  mov     [rsp+2E0h+pActCtx.wProcessorArchitecture], ax
0x18003eb1d  test    cl, 2
0x18003eb20  jz      short loc_18003EB2B
0x18003eb22  movzx   eax, word ptr [rdi+12h]
0x18003eb26  mov     [rsp+2E0h+pActCtx.wLangId], ax
0x18003eb2b  test    cl, cl
0x18003eb2d  jns     short loc_18003EB37
0x18003eb2f  mov     rax, [rdi+30h]
0x18003eb33  mov     [rbp+1E0h+pActCtx.hModule], rax
0x18003eb37  test    cl, 4
0x18003eb3a  jz      short loc_18003EBA0
0x18003eb3c  mov     rdx, [rdi+18h]; SourceString
0x18003eb40  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x18003eb45  call    cs:__imp_RtlInitAnsiString
0x18003eb4b  mov     eax, 20Ah
0x18003eb50  mov     [rsp+2E0h+var_2B0.MaximumLength], ax
0x18003eb55  lea     rax, [rbp+1E0h+var_240]
0x18003eb59  mov     [rsp+2E0h+var_2B0.Buffer], rax
0x18003eb5e  call    cs:__imp_GetEightBitStringToUnicodeStringRoutine
0x18003eb64  xor     r8d, r8d
0x18003eb67  lea     rdx, [rsp+2E0h+DestinationString]
0x18003eb6c  lea     rcx, [rsp+2E0h+var_2B0]
0x18003eb71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb76  mov     ebx, eax
0x18003eb78  cmp     eax, 80000005h
0x18003eb7d  jz      loc_18003EAE5
0x18003eb83  mov     ecx, 0C0000000h
0x18003eb88  and     eax, ecx
0x18003eb8a  cmp     eax, ecx
0x18003eb8c  jz      loc_18003EC2E
0x18003eb92  mov     rax, [rsp+2E0h+var_2B0.Buffer]
0x18003eb97  mov     ecx, [rsp+2E0h+pActCtx.dwFlags]
0x18003eb9b  mov     [rsp+2E0h+pActCtx.lpAssemblyDirectory], rax
0x18003eba0  test    cl, 8
0x18003eba3  jz      short loc_18003EBDD
0x18003eba5  mov     rcx, [rdi+20h]; SourceString
0x18003eba9  call    BaseDllMapResourceIdA
0x18003ebae  mov     r14, rax
0x18003ebb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003ebb5  jnz     short loc_18003EBD9
0x18003ebb7  lea     r9, aCreateactctxa_0; "CreateActCtxA"
0x18003ebbe  xor     edx, edx; Level
0x18003ebc0  lea     r8, aSxsSBasedllmap_0; "SXS: %s() BaseDllMapResourceIdA failed"...
0x18003ebc7  lea     ecx, [rax+34h]; ComponentId
0x18003ebca  call    cs:__imp_DbgPrintEx
0x18003ebd0  mov     ebx, [r13+1250h]
0x18003ebd7  jmp     short loc_18003EC2E
0x18003ebd9  mov     [rbp+1E0h+pActCtx.lpResourceName], rax
0x18003ebdd  lea     rcx, [rsp+2E0h+pActCtx]; pActCtx
0x18003ebe2  call    cs:__imp_CreateActCtxW
0x18003ebe8  mov     rsi, rax
0x18003ebeb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003ebef  jnz     short loc_18003EC2E
0x18003ebf1  jmp     short loc_18003EBD0
0x18003ebf3  mov     [rsp+2E0h+var_2B8], r9d
0x18003ebf8  lea     r8, aSxsSBadFlagsSi; "SXS: %s() Bad flags/size 0x%lx/0x%lx\n"
0x18003ebff  mov     dword ptr [rsp+2E0h+var_2C0], ecx
0x18003ec03  jmp     short loc_18003EC17
0x18003ec05  mov     eax, [rcx]
0x18003ec07  lea     r8, aSxsSNullPOrSiz; "SXS: %s() Null %p or size 0x%lx too sma"...
0x18003ec0e  mov     [rsp+2E0h+var_2B8], eax
0x18003ec12  mov     [rsp+2E0h+var_2C0], rdi
0x18003ec17  xor     edx, edx; Level
0x18003ec19  lea     r9, aCreateactctxa_0; "CreateActCtxA"
0x18003ec20  lea     ecx, [rdx+33h]; ComponentId
0x18003ec23  call    cs:__imp_DbgPrintEx
0x18003ec29  mov     ebx, 0C000000Dh
0x18003ec2e  cmp     [rsp+2E0h+UnicodeString.Buffer], 0
0x18003ec34  jz      short loc_18003EC41
0x18003ec36  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x18003ec3b  call    cs:__imp_RtlFreeUnicodeString
0x18003ec41  mov     rax, [rsp+2E0h+var_2B0.Buffer]
0x18003ec46  test    rax, rax
0x18003ec49  jz      short loc_18003EC5F
0x18003ec4b  lea     rcx, [rbp+1E0h+var_240]
0x18003ec4f  cmp     rax, rcx
0x18003ec52  jz      short loc_18003EC5F
0x18003ec54  lea     rcx, [rsp+2E0h+var_2B0]; UnicodeString
0x18003ec59  call    cs:__imp_RtlFreeUnicodeString
0x18003ec5f  mov     rcx, r14
0x18003ec62  call    cs:__imp_BaseDllFreeResourceId
0x18003ec68  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18003ec6c  jnz     short loc_18003EC75
0x18003ec6e  mov     ecx, ebx
0x18003ec70  call    BaseSetLastNTError
0x18003ec75  mov     rax, rsi
0x18003ec78  mov     rcx, [rbp+1E0h+var_30]
0x18003ec7f  xor     rcx, rsp; StackCookie
0x18003ec82  call    __security_check_cookie
0x18003ec87  lea     r11, [rsp+2E0h+var_20]
0x18003ec8f  mov     rbx, [r11+38h]
0x18003ec93  mov     rsi, [r11+40h]
0x18003ec97  mov     rsp, r11
0x18003ec9a  pop     r15
0x18003ec9c  pop     r14
0x18003ec9e  pop     r13
0x18003eca0  pop     rdi
0x18003eca1  pop     rbp
0x18003eca2  retn
```
