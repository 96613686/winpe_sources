# OpenEventInWebDriverNamespace

- ea: `0x180008450`
- end: `0x18000861e`
- name: `OpenEventInWebDriverNamespace`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180020c34`

## callees

- `0x1800073a0`
- `0x180008450`
- `0x180018b30`
- `0x18002b530`
- `0x18002ba84`
- `0x1800679d4`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentApplicationUserModelId` at `0x1800084ff`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentApplicationUserModelId` at `0x1800084ff`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800085b7`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800085b7`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180008543`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180008543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000854d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000854d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085d0`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x180008486`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x180008486`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x1800084af`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x1800084af`

## pseudocode

```c
HANDLE OpenEventInWebDriverNamespace()
{
  HANDLE BoundaryDescriptorW; // rax
  HANDLE v1; // rbx
  LPWSTR v2; // rax
  signed int LastError; // eax
  bool v4; // sf
  const char *v5; // r9
  UINT32 applicationUserModelIdLength[4]; // [rsp+50h] [rbp-2C8h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+60h] [rbp-2B8h] BYREF
  WCHAR Name[200]; // [rsp+170h] [rbp-1A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  BoundaryDescriptorW = BoundaryDescriptor;
  v1 = 0;
  if ( BoundaryDescriptor
    || (BoundaryDescriptorW = CreateBoundaryDescriptorW(L"MicrosoftWebDriverBoundary", 0),
        (BoundaryDescriptor = BoundaryDescriptorW) != 0) )
  {
    if ( Handle || (Handle = OpenPrivateNamespaceW(BoundaryDescriptorW, L"MicrosoftWebDriverBoundary")) != 0 )
    {
      v2 = Block;
      if ( !Block )
      {
        Block = (LPWSTR)operator new[](0x104u);
        applicationUserModelIdLength[0] = 130;
        if ( GetCurrentApplicationUserModelId(applicationUserModelIdLength, applicationUserModelId) < 0 )
          goto LABEL_17;
        if ( !LCMapStringEx(&LocaleName, 0x100u, applicationUserModelId, -1, Block, 130, 0, 0, 0) )
        {
          LastError = GetLastError();
          v4 = LastError < 0;
          if ( LastError > 0 )
            v4 = 1;
          if ( v4 )
            goto LABEL_17;
        }
        v2 = Block;
      }
      if ( (int)StringCchPrintfW(
                  Name,
                  0xC4u,
                  L"%s\\%s%s%s",
                  L"MicrosoftWebDriverBoundary",
                  L"WebDriverStartEvent_",
                  v2,
                  &LocaleName) < 0 )
      {
LABEL_17:
        CleanupWebDriverStatics();
        return v1;
      }
      v1 = OpenEventW(0x100002u, 0, Name);
      if ( !v1 )
      {
        if ( GetLastError() != 2 && GetLastError() != 3 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x85,
            (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webdriver\\webdriverdispatcher.cxx",
            v5);
        goto LABEL_17;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180008450  mov     [rsp+arg_0], rbx
0x180008455  push    rdi
0x180008456  sub     rsp, 310h
0x18000845d  mov     rax, cs:__security_cookie
0x180008464  xor     rax, rsp
0x180008467  mov     [rsp+318h+var_18], rax
0x18000846f  mov     rax, cs:BoundaryDescriptor
0x180008476  xor     ebx, ebx
0x180008478  test    rax, rax
0x18000847b  jnz     short loc_18000849C
0x18000847d  xor     edx, edx; Flags
0x18000847f  lea     rcx, AliasPrefix; "MicrosoftWebDriverBoundary"
0x180008486  call    cs:__imp_CreateBoundaryDescriptorW
0x18000848c  mov     cs:BoundaryDescriptor, rax
0x180008493  test    rax, rax
0x180008496  jz      loc_1800085FA
0x18000849c  cmp     cs:Handle, rbx
0x1800084a3  jnz     short loc_1800084C5
0x1800084a5  lea     rdx, AliasPrefix; "MicrosoftWebDriverBoundary"
0x1800084ac  mov     rcx, rax; lpBoundaryDescriptor
0x1800084af  call    cs:__imp_OpenPrivateNamespaceW
0x1800084b5  mov     cs:Handle, rax
0x1800084bc  test    rax, rax
0x1800084bf  jz      loc_1800085FA
0x1800084c5  mov     rax, cs:Block
0x1800084cc  lea     rdi, LocaleName
0x1800084d3  test    rax, rax
0x1800084d6  jnz     loc_18000856E
0x1800084dc  mov     ecx, 104h; unsigned __int64
0x1800084e1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800084e6  lea     rdx, [rsp+318h+applicationUserModelId]; applicationUserModelId
0x1800084eb  mov     cs:Block, rax
0x1800084f2  lea     rcx, [rsp+318h+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800084f7  mov     [rsp+318h+applicationUserModelIdLength], 82h
0x1800084ff  call    cs:__imp_GetCurrentApplicationUserModelId
0x180008505  test    eax, eax
0x180008507  js      loc_1800085F5
0x18000850d  mov     rax, cs:Block
0x180008514  lea     r8, [rsp+318h+applicationUserModelId]; lpSrcStr
0x180008519  mov     [rsp+318h+sortHandle], rbx; sortHandle
0x18000851e  mov     r9d, 0FFFFFFFFh; cchSrc
0x180008524  mov     [rsp+318h+lpReserved], rbx; lpReserved
0x180008529  mov     edx, 100h; dwMapFlags
0x18000852e  mov     [rsp+318h+lpVersionInformation], rbx; lpVersionInformation
0x180008533  mov     rcx, rdi; lpLocaleName
0x180008536  mov     [rsp+318h+cchDest], 82h; cchDest
0x18000853e  mov     [rsp+318h+lpDestStr], rax; lpDestStr
0x180008543  call    cs:__imp_LCMapStringEx
0x180008549  test    eax, eax
0x18000854b  jnz     short loc_180008567
0x18000854d  call    cs:__imp_GetLastError
0x180008553  test    eax, eax
0x180008555  jle     short loc_180008561
0x180008557  movzx   eax, ax
0x18000855a  or      eax, 80070000h
0x18000855f  test    eax, eax
0x180008561  js      loc_1800085F5
0x180008567  mov     rax, cs:Block
0x18000856e  mov     [rsp+318h+lpVersionInformation], rdi
0x180008573  lea     r9, AliasPrefix; "MicrosoftWebDriverBoundary"
0x18000857a  mov     qword ptr [rsp+318h+cchDest], rax
0x18000857f  lea     r8, aSSSS; "%s\\%s%s%s"
0x180008586  lea     rax, aWebdriverstart; "WebDriverStartEvent_"
0x18000858d  mov     edx, 0C4h; unsigned __int64
0x180008592  lea     rcx, [rsp+318h+Name]; unsigned __int16 *
0x18000859a  mov     [rsp+318h+lpDestStr], rax
0x18000859f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800085a4  test    eax, eax
0x1800085a6  js      short loc_1800085F5
0x1800085a8  lea     r8, [rsp+318h+Name]; lpName
0x1800085b0  xor     edx, edx; bInheritHandle
0x1800085b2  mov     ecx, 100002h; dwDesiredAccess
0x1800085b7  call    cs:__imp_OpenEventW
0x1800085bd  mov     rbx, rax
0x1800085c0  test    rax, rax
0x1800085c3  jnz     short loc_1800085FA
0x1800085c5  call    cs:__imp_GetLastError
0x1800085cb  cmp     eax, 2
0x1800085ce  jz      short loc_1800085F5
0x1800085d0  call    cs:__imp_GetLastError
0x1800085d6  cmp     eax, 3
0x1800085d9  jz      short loc_1800085F5
0x1800085db  mov     rcx, [rsp+318h]; this
0x1800085e3  lea     r8, aOnecoreuapInet_25; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800085ea  mov     edx, 85h; void *
0x1800085ef  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800085f5  call    CleanupWebDriverStatics
0x1800085fa  mov     rax, rbx
0x1800085fd  mov     rcx, [rsp+318h+var_18]
0x180008605  xor     rcx, rsp; StackCookie
0x180008608  call    __security_check_cookie
0x18000860d  mov     rbx, [rsp+318h+arg_0]
0x180008615  add     rsp, 310h
0x18000861c  pop     rdi
0x18000861d  retn
```
