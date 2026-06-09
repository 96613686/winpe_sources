# FindAppActivationErrorHandler

- ea: `0x1800bc3d8`
- end: `0x1800bc680`
- name: `FindAppActivationErrorHandler`
- size: `680`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bbfc0`

## callees

- `0x1800053a0`
- `0x18000ec7c`
- `0x180010a84`
- `0x1800bc3d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc49b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc57e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc5e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc49b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc57e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc5e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bc46b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bc46b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bc4fa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bc54e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bc4fa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bc54e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800bc5b8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800bc5b8`

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
0x1800bc3d8  mov     rax, rsp
0x1800bc3db  mov     [rax+8], rcx
0x1800bc3df  push    rbx
0x1800bc3e0  sub     rsp, 0F0h
0x1800bc3e7  movaps  xmmword ptr [rax-18h], xmm6
0x1800bc3eb  mov     rax, cs:__security_cookie
0x1800bc3f2  xor     rax, rsp
0x1800bc3f5  mov     [rsp+0F8h+var_28], rax
0x1800bc3fd  mov     rbx, rcx
0x1800bc400  cmp     edx, 800704C7h
0x1800bc406  jnz     short loc_1800BC41B
0x1800bc408  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800bc40f  movdqu  xmmword ptr [rcx], xmm0
0x1800bc413  mov     rax, rcx
0x1800bc416  jmp     loc_1800BC60B
0x1800bc41b  mov     r9d, edx
0x1800bc41e  lea     r8, a08x; "%08x"
0x1800bc425  mov     edx, 9; unsigned __int64
0x1800bc42a  lea     rcx, [rsp+0F8h+Value]; unsigned __int16 *
0x1800bc42f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bc434  mov     rcx, [rsp+0F8h]; this
0x1800bc43c  test    eax, eax
0x1800bc43e  js      loc_1800BC62D
0x1800bc444  and     [rsp+0F8h+hKey], 0
0x1800bc44a  lea     rax, [rsp+0F8h+hKey]
0x1800bc44f  mov     [rsp+0F8h+phkResult], rax; int
0x1800bc454  mov     r9d, 20119h; samDesired
0x1800bc45a  xor     r8d, r8d; ulOptions
0x1800bc45d  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800bc464  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bc46b  call    cs:__imp_RegOpenKeyExW
0x1800bc472  nop     dword ptr [rax+rax+00h]
0x1800bc477  test    eax, eax
0x1800bc479  jle     short loc_1800BC483
0x1800bc47b  movzx   eax, ax
0x1800bc47e  or      eax, 80070000h
0x1800bc483  cmp     eax, 80070002h
0x1800bc488  jnz     short loc_1800BC4B3
0x1800bc48a  movups  xmm6, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800bc491  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1800bc496  test    rcx, rcx
0x1800bc499  jz      short loc_1800BC4A7
0x1800bc49b  call    cs:__imp_RegCloseKey
0x1800bc4a2  nop     dword ptr [rax+rax+00h]
0x1800bc4a7  movdqu  xmmword ptr [rbx], xmm6
0x1800bc4ab  mov     rax, rbx
0x1800bc4ae  jmp     loc_1800BC60B
0x1800bc4b3  mov     rcx, [rsp+0F8h]; this
0x1800bc4bb  test    eax, eax
0x1800bc4bd  js      loc_1800BC642
0x1800bc4c3  mov     [rsp+0F8h+var_B8], 4Eh ; 'N'
0x1800bc4cb  lea     rax, [rsp+0F8h+var_B8]
0x1800bc4d0  mov     [rsp+0F8h+pcbData], rax; pcbData
0x1800bc4d5  lea     rax, [rsp+0F8h+sz]
0x1800bc4dd  mov     [rsp+0F8h+pvData], rax; pvData
0x1800bc4e2  and     [rsp+0F8h+phkResult], 0
0x1800bc4e8  mov     r9d, 2; dwFlags
0x1800bc4ee  lea     r8, [rsp+0F8h+Value]; lpValue
0x1800bc4f3  xor     edx, edx; lpSubKey
0x1800bc4f5  mov     rcx, [rsp+0F8h+hKey]; hkey
0x1800bc4fa  call    cs:__imp_RegGetValueW
0x1800bc501  nop     dword ptr [rax+rax+00h]
0x1800bc506  test    eax, eax
0x1800bc508  jle     short loc_1800BC512
0x1800bc50a  movzx   eax, ax
0x1800bc50d  or      eax, 80070000h
0x1800bc512  cmp     eax, 80070002h
0x1800bc517  jnz     short loc_1800BC593
0x1800bc519  mov     [rsp+0F8h+var_B8], 4Eh ; 'N'
0x1800bc521  lea     rax, [rsp+0F8h+var_B8]
0x1800bc526  mov     [rsp+0F8h+pcbData], rax; pcbData
0x1800bc52b  lea     rax, [rsp+0F8h+sz]
0x1800bc533  mov     [rsp+0F8h+pvData], rax; pvData
0x1800bc538  and     [rsp+0F8h+phkResult], 0
0x1800bc53e  mov     r9d, 2; dwFlags
0x1800bc544  xor     r8d, r8d; lpValue
0x1800bc547  xor     edx, edx; lpSubKey
0x1800bc549  mov     rcx, [rsp+0F8h+hKey]; hkey
0x1800bc54e  call    cs:__imp_RegGetValueW
0x1800bc555  nop     dword ptr [rax+rax+00h]
0x1800bc55a  test    eax, eax
0x1800bc55c  jle     short loc_1800BC566
0x1800bc55e  movzx   eax, ax
0x1800bc561  or      eax, 80070000h
0x1800bc566  cmp     eax, 80070002h
0x1800bc56b  jnz     short loc_1800BC593
0x1800bc56d  movups  xmm6, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800bc574  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1800bc579  test    rcx, rcx
0x1800bc57c  jz      short loc_1800BC58A
0x1800bc57e  call    cs:__imp_RegCloseKey
0x1800bc585  nop     dword ptr [rax+rax+00h]
0x1800bc58a  movdqu  xmmword ptr [rbx], xmm6
0x1800bc58e  mov     rax, rbx
0x1800bc591  jmp     short loc_1800BC60B
0x1800bc593  mov     rcx, [rsp+0F8h]; this
0x1800bc59b  test    eax, eax
0x1800bc59d  js      loc_1800BC656
0x1800bc5a3  xorps   xmm0, xmm0
0x1800bc5a6  movups  xmmword ptr [rsp+0F8h+pclsid.Data1], xmm0
0x1800bc5ab  lea     rdx, [rsp+0F8h+pclsid]; pclsid
0x1800bc5b0  lea     rcx, [rsp+0F8h+sz]; lpsz
0x1800bc5b8  call    cs:__imp_CLSIDFromString
0x1800bc5bf  nop     dword ptr [rax+rax+00h]
0x1800bc5c4  mov     rcx, [rsp+0F8h]; this
0x1800bc5cc  test    eax, eax
0x1800bc5ce  js      loc_1800BC66A
0x1800bc5d4  movaps  xmm6, xmmword ptr [rsp+0F8h+pclsid.Data1]
0x1800bc5d9  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1800bc5de  test    rcx, rcx
0x1800bc5e1  jz      short loc_1800BC5EF
0x1800bc5e3  call    cs:__imp_RegCloseKey
0x1800bc5ea  nop     dword ptr [rax+rax+00h]
0x1800bc5ef  movdqu  xmmword ptr [rbx], xmm6
0x1800bc5f3  mov     rax, rbx
0x1800bc5f6  jmp     short loc_1800BC60B
0x1800bc5f8  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800bc5ff  mov     rax, [rsp+0F8h+arg_0]
0x1800bc607  movdqu  xmmword ptr [rax], xmm0
0x1800bc60b  mov     rcx, [rsp+0F8h+var_28]
0x1800bc613  xor     rcx, rsp; StackCookie
0x1800bc616  call    __security_check_cookie
0x1800bc61b  movaps  xmm6, [rsp+0F8h+var_18]
0x1800bc623  add     rsp, 0F0h
0x1800bc62a  pop     rbx
0x1800bc62b  retn
0x1800bc62d  mov     r9d, eax; char *
0x1800bc630  lea     r8, aOnecoreBaseApp_31; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bc637  mov     edx, 0Bh; void *
0x1800bc63c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bc642  mov     r9d, eax; char *
0x1800bc645  lea     r8, aOnecoreBaseApp_31; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bc64c  mov     edx, 16h; void *
0x1800bc651  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bc656  mov     r9d, eax; char *
0x1800bc659  lea     r8, aOnecoreBaseApp_31; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bc660  mov     edx, 28h ; '('; void *
0x1800bc665  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bc66a  mov     r9d, eax; char *
0x1800bc66d  lea     r8, aOnecoreBaseApp_31; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bc674  mov     edx, 2Ch ; ','; void *
0x1800bc679  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
