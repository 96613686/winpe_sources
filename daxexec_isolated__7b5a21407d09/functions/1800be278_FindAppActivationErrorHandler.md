# FindAppActivationErrorHandler

- ea: `0x1800be278`
- end: `0x1800be527`
- name: `FindAppActivationErrorHandler`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bde50`

## callees

- `0x180004f70`
- `0x18001079c`
- `0x1800125f4`
- `0x1800be278`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800be30e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800be30e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be3a0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be3f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be3a0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be3f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be33e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be427`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be48c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be33e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be427`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be48c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800be461`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800be461`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
GUID *__fastcall FindAppActivationErrorHandler(GUID *a1, unsigned int a2)
{
  int v4; // eax
  int v5; // eax
  int ValueW; // eax
  HRESULT v7; // eax
  GUID v8; // xmm6
  int phkResult; // [rsp+20h] [rbp-D8h]
  int phkResulta; // [rsp+20h] [rbp-D8h]
  int phkResultb; // [rsp+20h] [rbp-D8h]
  DWORD pcbData; // [rsp+40h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B0h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-A8h] BYREF
  WCHAR Value[16]; // [rsp+60h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( a2 == -2147023673 )
  {
    *a1 = GUID_00000000_0000_0000_0000_000000000000;
    return a1;
  }
  else
  {
    v4 = StringCchPrintfW(Value, 9u, L"%08x", a2);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\AppActivationErrorHelper.h",
        (const char *)(unsigned int)v4,
        phkResult);
    hKey = 0;
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\AppActivationErrorHandlers",
           0,
           0x20119u,
           &hKey);
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    if ( v5 == -2147024894 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      *a1 = GUID_00000000_0000_0000_0000_000000000000;
      return a1;
    }
    else
    {
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x16,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\AppActivationErrorHelper.h",
          (const char *)(unsigned int)v5,
          phkResulta);
      pcbData = 78;
      ValueW = RegGetValueW(hKey, 0, Value, 2u, 0, sz, &pcbData);
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      if ( ValueW != -2147024894 )
        goto LABEL_20;
      pcbData = 78;
      ValueW = RegGetValueW(hKey, 0, 0, 2u, 0, sz, &pcbData);
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      if ( ValueW == -2147024894 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        *a1 = GUID_00000000_0000_0000_0000_000000000000;
        return a1;
      }
      else
      {
LABEL_20:
        if ( ValueW < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x28,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\AppActivationErrorHelper.h",
            (const char *)(unsigned int)ValueW,
            phkResultb);
        pclsid = 0;
        v7 = CLSIDFromString(sz, &pclsid);
        if ( v7 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2C,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\AppActivationErrorHelper.h",
            (const char *)(unsigned int)v7,
            phkResultb);
        v8 = pclsid;
        if ( hKey )
          RegCloseKey(hKey);
        *a1 = v8;
        return a1;
      }
    }
  }
}

```

## disassembly

```asm
0x1800be278  mov     rax, rsp
0x1800be27b  mov     [rax+8], rcx
0x1800be27f  push    rbx
0x1800be280  sub     rsp, 0F0h
0x1800be287  movaps  xmmword ptr [rax-18h], xmm6
0x1800be28b  mov     rax, cs:__security_cookie
0x1800be292  xor     rax, rsp
0x1800be295  mov     [rsp+0F8h+var_28], rax
0x1800be29d  mov     rbx, rcx
0x1800be2a0  cmp     edx, 800704C7h
0x1800be2a6  jnz     short loc_1800BE2BB
0x1800be2a8  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800be2af  movdqu  xmmword ptr [rcx], xmm0
0x1800be2b3  mov     rax, rcx
0x1800be2b6  jmp     loc_1800BE4B2
0x1800be2bb  mov     r9d, edx
0x1800be2be  lea     r8, a08x; "%08x"
0x1800be2c5  mov     edx, 9; unsigned __int64
0x1800be2ca  lea     rcx, [rsp+0F8h+Value]; unsigned __int16 *
0x1800be2cf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800be2d4  mov     rcx, [rsp+0F8h]; this
0x1800be2dc  test    eax, eax
0x1800be2de  js      loc_1800BE4D4
0x1800be2e4  mov     [rsp+0F8h+hKey], 0
0x1800be2ed  lea     rax, [rsp+0F8h+hKey]
0x1800be2f2  mov     [rsp+0F8h+phkResult], rax; int
0x1800be2f7  mov     r9d, 20119h; samDesired
0x1800be2fd  xor     r8d, r8d; ulOptions
0x1800be300  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800be307  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800be30e  call    cs:__imp_RegOpenKeyExW
0x1800be315  nop     dword ptr [rax+rax+00h]
0x1800be31a  test    eax, eax
0x1800be31c  jle     short loc_1800BE326
0x1800be31e  movzx   eax, ax
0x1800be321  or      eax, 80070000h
0x1800be326  cmp     eax, 80070002h
0x1800be32b  jnz     short loc_1800BE356
0x1800be32d  movups  xmm6, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800be334  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1800be339  test    rcx, rcx
0x1800be33c  jz      short loc_1800BE34A
0x1800be33e  call    cs:__imp_RegCloseKey
0x1800be345  nop     dword ptr [rax+rax+00h]
0x1800be34a  movdqu  xmmword ptr [rbx], xmm6
0x1800be34e  mov     rax, rbx
0x1800be351  jmp     loc_1800BE4B2
0x1800be356  mov     rcx, [rsp+0F8h]; this
0x1800be35e  test    eax, eax
0x1800be360  js      loc_1800BE4E9
0x1800be366  mov     [rsp+0F8h+var_B8], 4Eh ; 'N'
0x1800be36e  lea     rax, [rsp+0F8h+var_B8]
0x1800be373  mov     [rsp+0F8h+pcbData], rax; pcbData
0x1800be378  lea     rax, [rsp+0F8h+sz]
0x1800be380  mov     [rsp+0F8h+pvData], rax; pvData
0x1800be385  mov     [rsp+0F8h+phkResult], 0; int
0x1800be38e  mov     r9d, 2; dwFlags
0x1800be394  lea     r8, [rsp+0F8h+Value]; lpValue
0x1800be399  xor     edx, edx; lpSubKey
0x1800be39b  mov     rcx, [rsp+0F8h+hKey]; hkey
0x1800be3a0  call    cs:__imp_RegGetValueW
0x1800be3a7  nop     dword ptr [rax+rax+00h]
0x1800be3ac  test    eax, eax
0x1800be3ae  jle     short loc_1800BE3B8
0x1800be3b0  movzx   eax, ax
0x1800be3b3  or      eax, 80070000h
0x1800be3b8  cmp     eax, 80070002h
0x1800be3bd  jnz     short loc_1800BE43C
0x1800be3bf  mov     [rsp+0F8h+var_B8], 4Eh ; 'N'
0x1800be3c7  lea     rax, [rsp+0F8h+var_B8]
0x1800be3cc  mov     [rsp+0F8h+pcbData], rax; pcbData
0x1800be3d1  lea     rax, [rsp+0F8h+sz]
0x1800be3d9  mov     [rsp+0F8h+pvData], rax; pvData
0x1800be3de  mov     [rsp+0F8h+phkResult], 0; pdwType
0x1800be3e7  mov     r9d, 2; dwFlags
0x1800be3ed  xor     r8d, r8d; lpValue
0x1800be3f0  xor     edx, edx; lpSubKey
0x1800be3f2  mov     rcx, [rsp+0F8h+hKey]; hkey
0x1800be3f7  call    cs:__imp_RegGetValueW
0x1800be3fe  nop     dword ptr [rax+rax+00h]
0x1800be403  test    eax, eax
0x1800be405  jle     short loc_1800BE40F
0x1800be407  movzx   eax, ax
0x1800be40a  or      eax, 80070000h
0x1800be40f  cmp     eax, 80070002h
0x1800be414  jnz     short loc_1800BE43C
0x1800be416  movups  xmm6, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800be41d  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1800be422  test    rcx, rcx
0x1800be425  jz      short loc_1800BE433
0x1800be427  call    cs:__imp_RegCloseKey
0x1800be42e  nop     dword ptr [rax+rax+00h]
0x1800be433  movdqu  xmmword ptr [rbx], xmm6
0x1800be437  mov     rax, rbx
0x1800be43a  jmp     short loc_1800BE4B2
0x1800be43c  mov     rcx, [rsp+0F8h]; this
0x1800be444  test    eax, eax
0x1800be446  js      loc_1800BE4FD
0x1800be44c  xorps   xmm0, xmm0
0x1800be44f  movups  xmmword ptr [rsp+0F8h+pclsid.Data1], xmm0
0x1800be454  lea     rdx, [rsp+0F8h+pclsid]; pclsid
0x1800be459  lea     rcx, [rsp+0F8h+sz]; lpsz
0x1800be461  call    cs:__imp_CLSIDFromString
0x1800be468  nop     dword ptr [rax+rax+00h]
0x1800be46d  mov     rcx, [rsp+0F8h]; this
0x1800be475  test    eax, eax
0x1800be477  js      loc_1800BE511
0x1800be47d  movaps  xmm6, xmmword ptr [rsp+0F8h+pclsid.Data1]
0x1800be482  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1800be487  test    rcx, rcx
0x1800be48a  jz      short loc_1800BE498
0x1800be48c  call    cs:__imp_RegCloseKey
0x1800be493  nop     dword ptr [rax+rax+00h]
0x1800be498  movdqu  xmmword ptr [rbx], xmm6
0x1800be49c  mov     rax, rbx
0x1800be49f  jmp     short loc_1800BE4B2
0x1800be4a1  movups  xmm0, xmmword ptr [rsp+0F8h+pclsid.Data1]
0x1800be4a6  mov     rax, [rsp+0F8h+arg_0]
0x1800be4ae  movdqu  xmmword ptr [rax], xmm0
0x1800be4b2  mov     rcx, [rsp+0F8h+var_28]
0x1800be4ba  xor     rcx, rsp; StackCookie
0x1800be4bd  call    __security_check_cookie
0x1800be4c2  movaps  xmm6, [rsp+0F8h+var_18]
0x1800be4ca  add     rsp, 0F0h
0x1800be4d1  pop     rbx
0x1800be4d2  retn
0x1800be4d4  mov     r9d, eax; char *
0x1800be4d7  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800be4de  mov     edx, 0Bh; void *
0x1800be4e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800be4e9  mov     r9d, eax; char *
0x1800be4ec  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800be4f3  mov     edx, 16h; void *
0x1800be4f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800be4fd  mov     r9d, eax; char *
0x1800be500  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800be507  mov     edx, 28h ; '('; void *
0x1800be50c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800be511  mov     r9d, eax; char *
0x1800be514  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800be51b  mov     edx, 2Ch ; ','; void *
0x1800be520  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
