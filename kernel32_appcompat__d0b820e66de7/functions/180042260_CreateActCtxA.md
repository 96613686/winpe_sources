# CreateActCtxA

- ea: `0x180042260`
- end: `0x1800425b0`
- name: `CreateActCtxA`
- size: `848`
- prototype: `HANDLE __stdcall(PCACTCTXA pActCtx)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000b474`
- `0x18000ccf0`
- `0x180042260`
- `0x1800827c0`
- `0x180084010`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x1800424b2`
- `ntdll!DbgPrintEx` at `0x180042517`
- `ntdll!DbgPrintEx` at `0x1800424b2`
- `ntdll!DbgPrintEx` at `0x180042517`
- `ntdll!RtlFreeUnicodeString` at `0x180042535`
- `ntdll!RtlFreeUnicodeString` at `0x180042559`
- `ntdll!RtlFreeUnicodeString` at `0x180042535`
- `ntdll!RtlFreeUnicodeString` at `0x180042559`
- `ntdll!RtlInitAnsiString` at `0x180042386`
- `ntdll!RtlInitAnsiString` at `0x180042421`
- `ntdll!RtlInitAnsiString` at `0x180042386`
- `ntdll!RtlInitAnsiString` at `0x180042421`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x180042392`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x180042440`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x180042392`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x180042440`
- `KERNELBASE!BaseDllFreeResourceId` at `0x180042568`
- `KERNELBASE!BaseDllFreeResourceId` at `0x180042568`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800424d0`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800424d0`

## string_xrefs

- `0x1800424a8`: `SXS: %s() BaseDllMapResourceIdA failed\n`
- `0x18004249f`: `CreateActCtxA`
- `0x18004250d`: `CreateActCtxA`

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
0x180042260  mov     [rsp-8+arg_8], rbx
0x180042265  mov     [rsp-8+arg_10], rsi
0x18004226a  push    rbp
0x18004226b  push    rdi
0x18004226c  push    r13
0x18004226e  push    r14
0x180042270  push    r15
0x180042272  lea     rbp, [rsp-1C0h]
0x18004227a  sub     rsp, 2C0h
0x180042281  mov     rax, cs:__security_cookie
0x180042288  xor     rax, rsp
0x18004228b  mov     [rbp+1E0h+var_30], rax
0x180042292  xorps   xmm0, xmm0
0x180042295  mov     [rsp+2E0h+pActCtx.cbSize], 38h ; '8'
0x18004229d  xor     eax, eax
0x18004229f  xorps   xmm1, xmm1
0x1800422a2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800422a6  mov     dword ptr [rbp+1E0h+pActCtx.hModule+4], eax
0x1800422a9  xor     r14d, r14d
0x1800422ac  mov     rdi, rcx
0x1800422af  movups  xmmword ptr [rsp+2E0h+pActCtx.dwFlags], xmm0
0x1800422b4  movups  xmmword ptr [rsp+2E0h+pActCtx+14h], xmm0
0x1800422b9  movups  xmmword ptr [rbp+1E0h+pActCtx.lpResourceName+4], xmm0
0x1800422bd  movups  xmmword ptr [rsp+2E0h+UnicodeString.Length], xmm0
0x1800422c2  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm1
0x1800422c7  movups  xmmword ptr [rsp+2E0h+var_2B0.Length], xmm0
0x1800422cc  mov     r13, gs:30h
0x1800422d5  test    rcx, rcx
0x1800422d8  jz      loc_1800424F9
0x1800422de  mov     r9d, [rcx]
0x1800422e1  lea     r15, [rcx+10h]
0x1800422e5  lea     rdx, [r9+rcx]
0x1800422e9  cmp     r15, rdx
0x1800422ec  ja      loc_1800424F9
0x1800422f2  mov     ecx, [rcx+4]
0x1800422f5  mov     [rsp+2E0h+pActCtx.dwFlags], ecx
0x1800422f9  test    ecx, 0FFFFFF00h
0x1800422ff  jnz     loc_1800424E7
0x180042305  test    cl, 1
0x180042308  jz      short loc_180042317
0x18004230a  lea     rax, [rdi+12h]
0x18004230e  cmp     rax, rdx
0x180042311  ja      loc_1800424E7
0x180042317  test    cl, 2
0x18004231a  jz      short loc_180042329
0x18004231c  lea     rax, [rdi+14h]
0x180042320  cmp     rax, rdx
0x180042323  ja      loc_1800424E7
0x180042329  test    cl, 4
0x18004232c  jz      short loc_18004233B
0x18004232e  lea     rax, [rdi+20h]
0x180042332  cmp     rax, rdx
0x180042335  ja      loc_1800424E7
0x18004233b  test    cl, 8
0x18004233e  jz      short loc_18004234D
0x180042340  lea     rax, [rdi+28h]
0x180042344  cmp     rax, rdx
0x180042347  ja      loc_1800424E7
0x18004234d  test    cl, 20h
0x180042350  jz      short loc_18004235F
0x180042352  lea     rax, [rdi+30h]
0x180042356  cmp     rax, rdx
0x180042359  ja      loc_1800424E7
0x18004235f  mov     r8d, ecx
0x180042362  and     r8d, 80h
0x180042369  jz      short loc_180042378
0x18004236b  lea     rax, [rdi+38h]
0x18004236f  cmp     rax, rdx
0x180042372  ja      loc_1800424E7
0x180042378  mov     rdx, [rdi+8]; SourceString
0x18004237c  test    rdx, rdx
0x18004237f  jz      short loc_1800423DB
0x180042381  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x180042386  call    cs:__imp_RtlInitAnsiString
0x18004238d  nop     dword ptr [rax+rax+00h]
0x180042392  call    cs:__imp_GetEightBitStringToUnicodeStringRoutine
0x180042399  nop     dword ptr [rax+rax+00h]
0x18004239e  mov     r8b, 1
0x1800423a1  lea     rdx, [rsp+2E0h+DestinationString]
0x1800423a6  lea     rcx, [rsp+2E0h+UnicodeString]
0x1800423ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423b0  mov     ebx, eax
0x1800423b2  test    eax, eax
0x1800423b4  jns     short loc_1800423CB
0x1800423b6  cmp     eax, 80000005h
0x1800423bb  jnz     loc_180042528
0x1800423c1  mov     ebx, 0C0000106h
0x1800423c6  jmp     loc_180042528
0x1800423cb  mov     rax, [rsp+2E0h+UnicodeString.Buffer]
0x1800423d0  mov     ecx, [rsp+2E0h+pActCtx.dwFlags]
0x1800423d4  mov     [rsp+2E0h+pActCtx.lpSource], rax
0x1800423d9  jmp     short loc_1800423EB
0x1800423db  test    r8d, r8d
0x1800423de  jz      loc_180042523
0x1800423e4  xor     ebx, ebx
0x1800423e6  mov     [rsp+2E0h+pActCtx.lpSource], rbx
0x1800423eb  test    cl, 1
0x1800423ee  jz      short loc_1800423F9
0x1800423f0  movzx   eax, word ptr [r15]
0x1800423f4  mov     [rsp+2E0h+pActCtx.wProcessorArchitecture], ax
0x1800423f9  test    cl, 2
0x1800423fc  jz      short loc_180042407
0x1800423fe  movzx   eax, word ptr [rdi+12h]
0x180042402  mov     [rsp+2E0h+pActCtx.wLangId], ax
0x180042407  test    cl, cl
0x180042409  jns     short loc_180042413
0x18004240b  mov     rax, [rdi+30h]
0x18004240f  mov     [rbp+1E0h+pActCtx.hModule], rax
0x180042413  test    cl, 4
0x180042416  jz      short loc_180042488
0x180042418  mov     rdx, [rdi+18h]; SourceString
0x18004241c  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x180042421  call    cs:__imp_RtlInitAnsiString
0x180042428  nop     dword ptr [rax+rax+00h]
0x18004242d  mov     eax, 20Ah
0x180042432  mov     [rsp+2E0h+var_2B0.MaximumLength], ax
0x180042437  lea     rax, [rbp+1E0h+var_240]
0x18004243b  mov     [rsp+2E0h+var_2B0.Buffer], rax
0x180042440  call    cs:__imp_GetEightBitStringToUnicodeStringRoutine
0x180042447  nop     dword ptr [rax+rax+00h]
0x18004244c  xor     r8d, r8d
0x18004244f  lea     rdx, [rsp+2E0h+DestinationString]
0x180042454  lea     rcx, [rsp+2E0h+var_2B0]
0x180042459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004245e  mov     ebx, eax
0x180042460  cmp     eax, 80000005h
0x180042465  jz      loc_1800423C1
0x18004246b  mov     ecx, 0C0000000h
0x180042470  and     eax, ecx
0x180042472  cmp     eax, ecx
0x180042474  jz      loc_180042528
0x18004247a  mov     rax, [rsp+2E0h+var_2B0.Buffer]
0x18004247f  mov     ecx, [rsp+2E0h+pActCtx.dwFlags]
0x180042483  mov     [rsp+2E0h+pActCtx.lpAssemblyDirectory], rax
0x180042488  test    cl, 8
0x18004248b  jz      short loc_1800424CB
0x18004248d  mov     rcx, [rdi+20h]; SourceString
0x180042491  call    BaseDllMapResourceIdA
0x180042496  mov     r14, rax
0x180042499  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004249d  jnz     short loc_1800424C7
0x18004249f  lea     r9, aCreateactctxa_0; "CreateActCtxA"
0x1800424a6  xor     edx, edx; Level
0x1800424a8  lea     r8, aSxsSBasedllmap_0; "SXS: %s() BaseDllMapResourceIdA failed"...
0x1800424af  lea     ecx, [rax+34h]; ComponentId
0x1800424b2  call    cs:__imp_DbgPrintEx
0x1800424b9  nop     dword ptr [rax+rax+00h]
0x1800424be  mov     ebx, [r13+1250h]
0x1800424c5  jmp     short loc_180042528
0x1800424c7  mov     [rbp+1E0h+pActCtx.lpResourceName], rax
0x1800424cb  lea     rcx, [rsp+2E0h+pActCtx]; pActCtx
0x1800424d0  call    cs:__imp_CreateActCtxW
0x1800424d7  nop     dword ptr [rax+rax+00h]
0x1800424dc  mov     rsi, rax
0x1800424df  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800424e3  jnz     short loc_180042528
0x1800424e5  jmp     short loc_1800424BE
0x1800424e7  mov     [rsp+2E0h+var_2B8], r9d
0x1800424ec  lea     r8, aSxsSBadFlagsSi; "SXS: %s() Bad flags/size 0x%lx/0x%lx\n"
0x1800424f3  mov     dword ptr [rsp+2E0h+var_2C0], ecx
0x1800424f7  jmp     short loc_18004250B
0x1800424f9  mov     eax, [rcx]
0x1800424fb  lea     r8, aSxsSNullPOrSiz; "SXS: %s() Null %p or size 0x%lx too sma"...
0x180042502  mov     [rsp+2E0h+var_2B8], eax
0x180042506  mov     [rsp+2E0h+var_2C0], rdi
0x18004250b  xor     edx, edx; Level
0x18004250d  lea     r9, aCreateactctxa_0; "CreateActCtxA"
0x180042514  lea     ecx, [rdx+33h]; ComponentId
0x180042517  call    cs:__imp_DbgPrintEx
0x18004251e  nop     dword ptr [rax+rax+00h]
0x180042523  mov     ebx, 0C000000Dh
0x180042528  cmp     [rsp+2E0h+UnicodeString.Buffer], 0
0x18004252e  jz      short loc_180042541
0x180042530  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x180042535  call    cs:__imp_RtlFreeUnicodeString
0x18004253c  nop     dword ptr [rax+rax+00h]
0x180042541  mov     rax, [rsp+2E0h+var_2B0.Buffer]
0x180042546  test    rax, rax
0x180042549  jz      short loc_180042565
0x18004254b  lea     rcx, [rbp+1E0h+var_240]
0x18004254f  cmp     rax, rcx
0x180042552  jz      short loc_180042565
0x180042554  lea     rcx, [rsp+2E0h+var_2B0]; UnicodeString
0x180042559  call    cs:__imp_RtlFreeUnicodeString
0x180042560  nop     dword ptr [rax+rax+00h]
0x180042565  mov     rcx, r14
0x180042568  call    cs:__imp_BaseDllFreeResourceId
0x18004256f  nop     dword ptr [rax+rax+00h]
0x180042574  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180042578  jnz     short loc_180042581
0x18004257a  mov     ecx, ebx
0x18004257c  call    BaseSetLastNTError
0x180042581  mov     rax, rsi
0x180042584  mov     rcx, [rbp+1E0h+var_30]
0x18004258b  xor     rcx, rsp; StackCookie
0x18004258e  call    __security_check_cookie
0x180042593  lea     r11, [rsp+2E0h+var_20]
0x18004259b  mov     rbx, [r11+38h]
0x18004259f  mov     rsi, [r11+40h]
0x1800425a3  mov     rsp, r11
0x1800425a6  pop     r15
0x1800425a8  pop     r14
0x1800425aa  pop     r13
0x1800425ac  pop     rdi
0x1800425ad  pop     rbp
0x1800425ae  retn
```
