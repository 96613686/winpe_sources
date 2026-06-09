# UnloadUserClasses(ushort const *,void * *)

- ea: `0x180008ccc`
- end: `0x180008eeb`
- name: `?UnloadUserClasses@@YAJPEBGPEAPEAX@Z`
- size: `543`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009320`
- `0x18002ed00`
- `0x1800393e4`
- `0x18003f540`

## callees

- `0x1800053a0`
- `0x180008ccc`
- `0x180008ef4`
- `0x18000cb80`
- `0x180010f30`
- `0x1800111a0`
- `0x18002d2d8`
- `0x18002e648`
- `0x18003f42c`
- `0x180041e18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008d3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008d3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008d69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008eb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008d69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008eb0`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180008d4e`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180008d4e`
- `OLEAUT32!__imp_VariantClear` at `0x180008dcb`
- `OLEAUT32!__imp_VariantClear` at `0x180008e30`
- `OLEAUT32!__imp_VariantClear` at `0x180008dcb`
- `OLEAUT32!__imp_VariantClear` at `0x180008e30`

## string_xrefs

- `0x180008e41`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180008e6b`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180008e94`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180008ebb`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180008ed4`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnloadUserClasses(const unsigned __int16 *a1, void **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPCWSTR v5; // rbx
  unsigned int v6; // eax
  unsigned int v7; // eax
  int UserStateSetting; // edi
  BOOL v9; // esi
  wil::details::in1diag3 *v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  int phkResult; // [rsp+20h] [rbp-58h]
  unsigned int phkResulta; // [rsp+20h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-38h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  HKEY hKey; // [rsp+C0h] [rbp+48h] BYREF

  memset(lpSubKey, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s_Classes",
         a1);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)v3,
      phkResult);
LABEL_20:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
    return v4;
  }
  hKey = 0;
  v5 = lpSubKey[0];
  v6 = RegOpenKeyExW(HKEY_USERS, lpSubKey[0], 0, 0x20019u, &hKey);
  if ( v6 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x21D,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
           (const char *)v6,
           phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_20;
  }
  v7 = RegFlushKey(hKey);
  if ( v7 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x21F,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)v7,
      phkResulta);
  if ( hKey )
    RegCloseKey(hKey);
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0;
  UserStateSetting = GetUserStateSetting(2, qword_18007CB80, 34, 8);
  if ( UserStateSetting >= 0 )
  {
    v9 = pvarg.iVal == 0xFFFF;
    VariantClear(&pvarg);
    UserStateSetting = 0;
  }
  else
  {
    VariantClear(&pvarg);
    v9 = 0;
  }
  v10 = retaddr;
  if ( UserStateSetting < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x224,
      (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)UserStateSetting);
  v11 = UnmountRegHive(v10, v5, v9, a2);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)v11,
      (int)&pvarg);
    if ( v5 )
      Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v5);
    return v12;
  }
  else
  {
    if ( v5 )
      Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v5);
    return 0;
  }
}

```

## disassembly

```asm
0x180008ccc  push    rbp
0x180008cce  push    rbx
0x180008ccf  push    rsi
0x180008cd0  push    rdi
0x180008cd1  push    r12
0x180008cd3  push    r14
0x180008cd5  mov     rbp, rsp
0x180008cd8  sub     rsp, 78h
0x180008cdc  mov     r14, rdx
0x180008cdf  mov     [rbp+lpSubKey], 0
0x180008ce7  mov     [rbp+var_18], 0
0x180008cef  mov     [rbp+var_10], 0
0x180008cf7  mov     r8, rcx
0x180008cfa  lea     rdx, aSClasses; "%s_Classes"
0x180008d01  lea     rcx, [rbp+lpSubKey]
0x180008d05  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180008d0a  mov     ebx, eax
0x180008d0c  test    eax, eax
0x180008d0e  js      loc_180008E64
0x180008d14  mov     [rbp+hKey], 0
0x180008d1c  lea     rax, [rbp+hKey]
0x180008d20  mov     qword ptr [rsp+78h+phkResult], rax; unsigned int
0x180008d25  mov     r9d, 20019h; samDesired
0x180008d2b  xor     r8d, r8d; ulOptions
0x180008d2e  mov     rbx, [rbp+lpSubKey]
0x180008d32  mov     rdx, rbx; lpSubKey
0x180008d35  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180008d3c  call    cs:__imp_RegOpenKeyExW
0x180008d42  test    eax, eax
0x180008d44  jnz     loc_180008E8D
0x180008d4a  mov     rcx, [rbp+hKey]; hKey
0x180008d4e  call    cs:__imp_RegFlushKey
0x180008d54  mov     rcx, [rbp+30h]; this
0x180008d58  test    eax, eax
0x180008d5a  jnz     loc_180008EB8
0x180008d60  mov     rcx, [rbp+hKey]; hKey
0x180008d64  test    rcx, rcx
0x180008d67  jz      short loc_180008D6F
0x180008d69  call    cs:__imp_RegCloseKey
0x180008d6f  xorps   xmm0, xmm0
0x180008d72  xor     eax, eax
0x180008d74  movups  xmmword ptr [rbp+pvarg], xmm0
0x180008d78  mov     qword ptr [rbp+pvarg+10h], rax
0x180008d7c  mov     word ptr [rbp+pvarg], ax
0x180008d80  mov     [rsp+78h+var_40], rax
0x180008d85  mov     [rsp+78h+var_48], eax
0x180008d89  lea     rax, [rbp+pvarg]
0x180008d8d  mov     qword ptr [rsp+78h+phkResult], rax; int
0x180008d92  mov     r12d, 8
0x180008d98  mov     r9d, r12d
0x180008d9b  lea     r8d, [r12+1Ah]
0x180008da0  lea     rdx, qword_18007CB80
0x180008da7  lea     ecx, [r12-6]
0x180008dac  call    ?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@QEBUUSERSTATE_SETTING_DESCRIPTOR@@IIAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const * const,uint,uint,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x180008db1  mov     edi, eax
0x180008db3  test    eax, eax
0x180008db5  jns     short loc_180008E0F
0x180008db7  mov     eax, 0FFFh
0x180008dbc  cmp     word ptr [rbp+pvarg], ax
0x180008dc0  jnz     short loc_180008DC7
0x180008dc2  mov     word ptr [rbp+pvarg], r12w
0x180008dc7  lea     rcx, [rbp+pvarg]; pvarg
0x180008dcb  call    cs:__imp_VariantClear
0x180008dd1  xor     esi, esi
0x180008dd3  mov     rcx, [rbp+30h]; this
0x180008dd7  test    edi, edi
0x180008dd9  js      loc_180008ED1
0x180008ddf  mov     r9, r14
0x180008de2  mov     r8d, esi
0x180008de5  mov     rdx, rbx
0x180008de8  call    ?UnmountRegHive@@YAJPEAUHKEY__@@PEBGW4UnloadFlags@@PEAPEAX@Z; UnmountRegHive(HKEY__ *,ushort const *,UnloadFlags,void * *)
0x180008ded  mov     edi, eax
0x180008def  test    eax, eax
0x180008df1  js      short loc_180008E3A
0x180008df3  test    rbx, rbx
0x180008df6  jz      short loc_180008E00
0x180008df8  mov     rcx, rbx
0x180008dfb  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180008e00  xor     eax, eax
0x180008e02  add     rsp, 78h
0x180008e06  pop     r14
0x180008e08  pop     r12
0x180008e0a  pop     rdi
0x180008e0b  pop     rsi
0x180008e0c  pop     rbx
0x180008e0d  pop     rbp
0x180008e0e  retn
0x180008e0f  xor     esi, esi
0x180008e11  or      eax, 0FFFFFFFFh
0x180008e14  cmp     ax, word ptr [rbp+pvarg+8]
0x180008e18  setz    sil
0x180008e1c  mov     eax, 0FFFh
0x180008e21  cmp     word ptr [rbp+pvarg], ax
0x180008e25  jnz     short loc_180008E2C
0x180008e27  mov     word ptr [rbp+pvarg], r12w
0x180008e2c  lea     rcx, [rbp+pvarg]; pvarg
0x180008e30  call    cs:__imp_VariantClear
0x180008e36  xor     edi, edi
0x180008e38  jmp     short loc_180008DD3
0x180008e3a  mov     rcx, [rbp+30h]; this
0x180008e3e  mov     r9d, edi; char *
0x180008e41  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008e48  mov     edx, 22Ch; void *
0x180008e4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e52  nop
0x180008e53  test    rbx, rbx
0x180008e56  jz      short loc_180008E60
0x180008e58  mov     rcx, rbx
0x180008e5b  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180008e60  mov     eax, edi
0x180008e62  jmp     short loc_180008E02
0x180008e64  mov     rcx, [rbp+30h]; this
0x180008e68  mov     r9d, eax; char *
0x180008e6b  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008e72  mov     edx, 217h; void *
0x180008e77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e7c  nop
0x180008e7d  lea     rcx, [rbp+lpSubKey]
0x180008e81  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180008e86  mov     eax, ebx
0x180008e88  jmp     loc_180008E02
0x180008e8d  mov     rcx, [rbp+30h]; this
0x180008e91  mov     r9d, eax; char *
0x180008e94  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008e9b  mov     edx, 21Dh; void *
0x180008ea0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180008ea5  mov     ebx, eax
0x180008ea7  mov     rcx, [rbp+hKey]; hKey
0x180008eab  test    rcx, rcx
0x180008eae  jz      short loc_180008E7D
0x180008eb0  call    cs:__imp_RegCloseKey
0x180008eb6  jmp     short loc_180008E7D
0x180008eb8  mov     r9d, eax; char *
0x180008ebb  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008ec2  mov     edx, 21Fh; void *
0x180008ec7  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180008ecc  jmp     loc_180008D60
0x180008ed1  mov     r9d, edi; char *
0x180008ed4  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008edb  mov     edx, 224h; void *
0x180008ee0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008ee5  jmp     loc_180008DDF
```
