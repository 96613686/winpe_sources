# CNDFHelperClass::InitializeMatchAttributes(void)

- ea: `0x18000f970`
- end: `0x18000fd0f`
- name: `?InitializeMatchAttributes@CNDFHelperClass@@AEAAJXZ`
- size: `927`
- prototype: `__int64 __fastcall(CNDFHelperClass *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dc10`
- `0x18000fff8`

## callees

- `0x180003414`
- `0x18000a528`
- `0x18000cb04`
- `0x18000ce00`
- `0x18000f970`
- `0x1800112a0`
- `0x18001150c`
- `0x180011920`
- `0x180013686`
- `0x1800136b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000fa4d`
- `ADVAPI32!RegCloseKey` at `0x18000fcd5`
- `ADVAPI32!RegCloseKey` at `0x18000fa4d`
- `ADVAPI32!RegCloseKey` at `0x18000fcd5`
- `ADVAPI32!RegEnumValueW` at `0x18000fb32`
- `ADVAPI32!RegEnumValueW` at `0x18000fb32`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fa1a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fa1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNDFHelperClass::InitializeMatchAttributes(CNDFHelperClass *this)
{
  HKEY v2; // rsi
  signed int v3; // ebx
  LSTATUS v4; // eax
  int v5; // ecx
  LSTATUS v6; // edi
  __int64 v8; // r8
  DWORD v9; // r12d
  unsigned __int64 i; // r15
  __int64 *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A0h]
  HKEY v20; // [rsp+68h] [rbp-98h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h]
  _WORD v23[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h]
  __int64 v25; // [rsp+98h] [rbp-68h]
  int v26; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v28; // [rsp+B0h] [rbp-50h]
  _WORD v29[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v30; // [rsp+D0h] [rbp-30h]
  __int64 v31; // [rsp+D8h] [rbp-28h]
  int v32; // [rsp+E0h] [rbp-20h]
  BYTE Data[272]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR SubKey[264]; // [rsp+200h] [rbp+100h] BYREF
  WCHAR ValueName[264]; // [rsp+410h] [rbp+310h] BYREF

  v2 = 0;
  v21 = 0;
  v22 = 0;
  memset_0(SubKey, 0, 0x208u);
  v3 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", *((_QWORD *)this + 3), L"MatchAttributes");
  if ( v3 >= 0 )
  {
    hKey = 0;
    v4 = RegOpenKeyExW(*((HKEY *)this + 4), SubKey, 0, 0x20019u, &hKey);
    v6 = v4;
    if ( !v4 )
      v2 = hKey;
    v20 = v2;
    if ( v4 == 2 )
    {
      *((_DWORD *)this + 72) = 1;
      if ( v2 )
        RegCloseKey(v2);
      return 0;
    }
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    else
      v3 = v4;
    if ( v3 < 0 )
    {
      if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
        McTemplateU0qqzz_EventWriteTransfer(
          v5,
          (unsigned int)RegistryError,
          v3,
          601,
          *((_QWORD *)this + 1),
          (__int64)L"MatchAttributes");
      goto LABEL_40;
    }
    v18 = 0;
    v8 = 0;
    v19 = 0;
    v9 = 0;
    if ( v4 )
    {
LABEL_29:
      if ( v6 == 259 )
      {
        v11 = (__int64 *)((char *)this + 296);
        if ( (__int128 *)((char *)this + 296) != &v18 )
        {
          v12 = *v11;
          *v11 = v18;
          *(_QWORD *)&v18 = v12;
          v13 = *((_QWORD *)this + 38);
          *((_QWORD *)this + 38) = *((_QWORD *)&v18 + 1);
          *((_QWORD *)&v18 + 1) = v13;
          v14 = *((_QWORD *)this + 39);
          *((_QWORD *)this + 39) = v8;
          v19 = v14;
        }
        *((_DWORD *)this + 72) = 1;
      }
      else
      {
        if ( v6 <= 0 )
LABEL_35:
          v3 = v6;
        else
          v3 = (unsigned __int16)v6 | 0x80070000;
        if ( v3 < 0 && (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
          McTemplateU0qqzz_EventWriteTransfer(
            v5,
            (unsigned int)RegistryError,
            v3,
            659,
            *((_QWORD *)this + 1),
            (__int64)L"MatchAttributes");
      }
      std::vector<StoredMatchValue>::~vector<StoredMatchValue>(&v18);
      goto LABEL_40;
    }
    while ( 1 )
    {
      if ( v3 < 0 )
        goto LABEL_35;
      memset_0(ValueName, 0, 0x208u);
      LODWORD(hKey) = 260;
      Type = 0;
      cbData = 261;
      v6 = RegEnumValueW(v2, v9, ValueName, (LPDWORD)&hKey, 0, &Type, Data, &cbData);
      v25 = 7;
      v24 = 0;
      v23[0] = 0;
      v27 = 0;
      v28 = 0;
      v31 = 7;
      v30 = 0;
      v29[0] = 0;
      std::wstring::assign(v23, ValueName);
      if ( !v6 )
      {
        switch ( Type )
        {
          case 1u:
            std::wstring::assign(v29, Data);
            v26 = 10;
            goto LABEL_26;
          case 3u:
            for ( i = 0; i < cbData; ++i )
              std::vector<unsigned char>::push_back(&v27, &Data[i]);
            v26 = 14;
            goto LABEL_26;
          case 4u:
            v32 = *(_DWORD *)Data;
            v26 = 7;
LABEL_26:
            std::vector<StoredMatchValue>::push_back(&v18, v23);
            goto LABEL_27;
        }
        v3 = -2147467263;
      }
LABEL_27:
      StoredMatchValue::~StoredMatchValue((StoredMatchValue *)v23);
      ++v9;
      if ( v6 )
      {
        v8 = v19;
        goto LABEL_29;
      }
    }
  }
LABEL_40:
  if ( v2 )
    RegCloseKey(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000f970  mov     [rsp-8+arg_8], rbx
0x18000f975  mov     [rsp-8+arg_10], rsi
0x18000f97a  push    rbp
0x18000f97b  push    rdi
0x18000f97c  push    r12
0x18000f97e  push    r14
0x18000f980  push    r15
0x18000f982  lea     rbp, [rsp-530h]
0x18000f98a  sub     rsp, 630h
0x18000f991  mov     rax, cs:__security_cookie
0x18000f998  xor     rax, rsp
0x18000f99b  mov     [rbp+550h+var_30], rax
0x18000f9a2  mov     r14, rcx
0x18000f9a5  xor     esi, esi
0x18000f9a7  mov     [rsp+650h+var_5E0], rsi
0x18000f9ac  mov     [rsp+650h+var_5D8], rsi
0x18000f9b1  xor     edx, edx; Val
0x18000f9b3  mov     r8d, 208h; Size
0x18000f9b9  lea     rcx, [rbp+550h+SubKey]; void *
0x18000f9c0  call    memset_0
0x18000f9c5  lea     r15, aMatchattribute; "MatchAttributes"
0x18000f9cc  mov     [rsp+650h+phkResult], r15
0x18000f9d1  mov     r9, [r14+18h]
0x18000f9d5  lea     r8, aSS; "%s\\%s"
0x18000f9dc  mov     edx, 104h; unsigned __int64
0x18000f9e1  lea     rcx, [rbp+550h+SubKey]; unsigned __int16 *
0x18000f9e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f9ed  mov     ebx, eax
0x18000f9ef  test    eax, eax
0x18000f9f1  js      loc_18000FCCD
0x18000f9f7  mov     [rsp+650h+hKey], rsi
0x18000f9fc  lea     rax, [rsp+650h+hKey]
0x18000fa01  mov     [rsp+650h+phkResult], rax; phkResult
0x18000fa06  mov     r9d, 20019h; samDesired
0x18000fa0c  xor     r8d, r8d; ulOptions
0x18000fa0f  lea     rdx, [rbp+550h+SubKey]; lpSubKey
0x18000fa16  mov     rcx, [r14+20h]; hKey
0x18000fa1a  call    cs:__imp_RegOpenKeyExW
0x18000fa21  nop     dword ptr [rax+rax+00h]
0x18000fa26  mov     edi, eax
0x18000fa28  test    eax, eax
0x18000fa2a  cmovz   rsi, [rsp+650h+hKey]
0x18000fa30  mov     [rsp+650h+var_5E8], rsi
0x18000fa35  cmp     eax, 2
0x18000fa38  jnz     short loc_18000FA60
0x18000fa3a  mov     dword ptr [r14+120h], 1
0x18000fa45  test    rsi, rsi
0x18000fa48  jz      short loc_18000FA59
0x18000fa4a  mov     rcx, rsi; hKey
0x18000fa4d  call    cs:__imp_RegCloseKey
0x18000fa54  nop     dword ptr [rax+rax+00h]
0x18000fa59  xor     eax, eax
0x18000fa5b  jmp     loc_18000FCE3
0x18000fa60  test    eax, eax
0x18000fa62  jg      short loc_18000FA68
0x18000fa64  mov     ebx, eax
0x18000fa66  jmp     short loc_18000FA71
0x18000fa68  movzx   ebx, ax
0x18000fa6b  or      ebx, 80070000h
0x18000fa71  test    ebx, ebx
0x18000fa73  jns     short loc_18000FAAA
0x18000fa75  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000fa7c  jz      loc_18000FCCD
0x18000fa82  mov     [rsp+650h+lpType], r15
0x18000fa87  mov     rax, [r14+8]
0x18000fa8b  mov     [rsp+650h+phkResult], rax
0x18000fa90  mov     r9d, 259h
0x18000fa96  mov     r8d, ebx
0x18000fa99  lea     rdx, RegistryError
0x18000faa0  call    McTemplateU0qqzz_EventWriteTransfer
0x18000faa5  jmp     loc_18000FCCD
0x18000faaa  xorps   xmm0, xmm0
0x18000faad  movdqu  [rsp+650h+var_600], xmm0
0x18000fab3  xor     r8d, r8d
0x18000fab6  mov     [rsp+650h+var_5F0], r8
0x18000fabb  xor     r12d, r12d
0x18000fabe  test    eax, eax
0x18000fac0  jnz     loc_18000FC21
0x18000fac6  test    ebx, ebx
0x18000fac8  js      loc_18000FC6C
0x18000face  xor     edx, edx; Val
0x18000fad0  mov     r8d, 208h; Size
0x18000fad6  lea     rcx, [rbp+550h+ValueName]; void *
0x18000fadd  call    memset_0
0x18000fae2  mov     dword ptr [rsp+650h+hKey], 104h
0x18000faea  mov     [rsp+650h+Type], 0
0x18000faf2  mov     [rsp+650h+cbData], 105h
0x18000fafa  lea     rax, [rsp+650h+cbData]
0x18000faff  mov     [rsp+650h+lpcbData], rax; lpcbData
0x18000fb04  lea     rax, [rbp+550h+Data]
0x18000fb08  mov     [rsp+650h+lpData], rax; lpData
0x18000fb0d  lea     rax, [rsp+650h+Type]
0x18000fb12  mov     [rsp+650h+lpType], rax; lpType
0x18000fb17  mov     [rsp+650h+phkResult], 0; lpReserved
0x18000fb20  lea     r9, [rsp+650h+hKey]; lpcchValueName
0x18000fb25  lea     r8, [rbp+550h+ValueName]; lpValueName
0x18000fb2c  mov     edx, r12d; dwIndex
0x18000fb2f  mov     rcx, rsi; hKey
0x18000fb32  call    cs:__imp_RegEnumValueW
0x18000fb39  nop     dword ptr [rax+rax+00h]
0x18000fb3e  mov     edi, eax
0x18000fb40  mov     [rbp+550h+var_5B8], 7
0x18000fb48  mov     [rbp+550h+var_5C0], 0
0x18000fb50  xor     ecx, ecx
0x18000fb52  mov     [rbp+550h+var_5D0], cx
0x18000fb56  mov     [rbp+550h+var_5A8], rcx
0x18000fb5a  xorps   xmm0, xmm0
0x18000fb5d  movdqa  [rbp+550h+var_5A0], xmm0
0x18000fb62  mov     [rbp+550h+var_578], 7
0x18000fb6a  mov     [rbp+550h+var_580], rcx
0x18000fb6e  mov     [rbp+550h+var_590], cx
0x18000fb72  lea     rdx, [rbp+550h+ValueName]; Src
0x18000fb79  lea     rcx, [rbp+550h+var_5D0]; void *
0x18000fb7d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000fb82  test    edi, edi
0x18000fb84  jnz     short loc_18000FC01
0x18000fb86  mov     eax, [rsp+650h+Type]
0x18000fb8a  sub     eax, 1
0x18000fb8d  jz      short loc_18000FBDE
0x18000fb8f  sub     eax, 2
0x18000fb92  jz      short loc_18000FBAF
0x18000fb94  cmp     eax, 1
0x18000fb97  jz      short loc_18000FBA0
0x18000fb99  mov     ebx, 80004001h
0x18000fb9e  jmp     short loc_18000FC01
0x18000fba0  mov     eax, dword ptr [rbp+550h+Data]
0x18000fba3  mov     [rbp+550h+var_570], eax
0x18000fba6  mov     [rbp+550h+var_5B0], 7
0x18000fbad  jmp     short loc_18000FBF2
0x18000fbaf  xor     r15d, r15d
0x18000fbb2  cmp     [rsp+650h+cbData], r15d
0x18000fbb7  jbe     short loc_18000FBD5
0x18000fbb9  lea     rdx, [rbp+550h+Data]
0x18000fbbd  add     rdx, r15
0x18000fbc0  lea     rcx, [rbp+550h+var_5A8]
0x18000fbc4  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAXAEBE@Z; std::vector<uchar>::push_back(uchar const &)
0x18000fbc9  inc     r15
0x18000fbcc  mov     eax, [rsp+650h+cbData]
0x18000fbd0  cmp     r15, rax
0x18000fbd3  jb      short loc_18000FBB9
0x18000fbd5  mov     [rbp+550h+var_5B0], 0Eh
0x18000fbdc  jmp     short loc_18000FBF2
0x18000fbde  lea     rdx, [rbp+550h+Data]; Src
0x18000fbe2  lea     rcx, [rbp+550h+var_590]; void *
0x18000fbe6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000fbeb  mov     [rbp+550h+var_5B0], 0Ah
0x18000fbf2  lea     rdx, [rbp+550h+var_5D0]
0x18000fbf6  lea     rcx, [rsp+650h+var_600]
0x18000fbfb  call    ?push_back@?$vector@UStoredMatchValue@@V?$allocator@UStoredMatchValue@@@std@@@std@@QEAAXAEBUStoredMatchValue@@@Z; std::vector<StoredMatchValue>::push_back(StoredMatchValue const &)
0x18000fc00  nop
0x18000fc01  lea     rcx, [rbp+550h+var_5D0]; this
0x18000fc05  call    ??1StoredMatchValue@@QEAA@XZ; StoredMatchValue::~StoredMatchValue(void)
0x18000fc0a  inc     r12d
0x18000fc0d  test    edi, edi
0x18000fc0f  jz      loc_18000FAC6
0x18000fc15  mov     r8, [rsp+650h+var_5F0]
0x18000fc1a  lea     r15, aMatchattribute; "MatchAttributes"
0x18000fc21  cmp     edi, 103h
0x18000fc27  jz      short loc_18000FC77
0x18000fc29  test    edi, edi
0x18000fc2b  jle     short loc_18000FC73
0x18000fc2d  movzx   ebx, di
0x18000fc30  or      ebx, 80070000h
0x18000fc36  test    ebx, ebx
0x18000fc38  jns     loc_18000FCC2
0x18000fc3e  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000fc45  jz      short loc_18000FCC2
0x18000fc47  mov     [rsp+650h+lpType], r15
0x18000fc4c  mov     rax, [r14+8]
0x18000fc50  mov     [rsp+650h+phkResult], rax
0x18000fc55  mov     r9d, 293h
0x18000fc5b  mov     r8d, ebx
0x18000fc5e  lea     rdx, RegistryError
0x18000fc65  call    McTemplateU0qqzz_EventWriteTransfer
0x18000fc6a  jmp     short loc_18000FCC2
0x18000fc6c  lea     r15, aMatchattribute; "MatchAttributes"
0x18000fc73  mov     ebx, edi
0x18000fc75  jmp     short loc_18000FC36
0x18000fc77  lea     rdx, [r14+128h]
0x18000fc7e  lea     rax, [rsp+650h+var_600]
0x18000fc83  cmp     rdx, rax
0x18000fc86  jz      short loc_18000FCB7
0x18000fc88  mov     rcx, [rdx]
0x18000fc8b  mov     rax, qword ptr [rsp+650h+var_600]
0x18000fc90  mov     [rdx], rax
0x18000fc93  mov     qword ptr [rsp+650h+var_600], rcx
0x18000fc98  mov     rcx, [rdx+8]
0x18000fc9c  mov     rax, qword ptr [rsp+650h+var_600+8]
0x18000fca1  mov     [rdx+8], rax
0x18000fca5  mov     qword ptr [rsp+650h+var_600+8], rcx
0x18000fcaa  mov     rax, [rdx+10h]
0x18000fcae  mov     [rdx+10h], r8
0x18000fcb2  mov     [rsp+650h+var_5F0], rax
0x18000fcb7  mov     dword ptr [r14+120h], 1
0x18000fcc2  lea     rcx, [rsp+650h+var_600]
0x18000fcc7  call    ??1?$vector@UStoredMatchValue@@V?$allocator@UStoredMatchValue@@@std@@@std@@QEAA@XZ; std::vector<StoredMatchValue>::~vector<StoredMatchValue>(void)
0x18000fccc  nop
0x18000fccd  test    rsi, rsi
0x18000fcd0  jz      short loc_18000FCE1
0x18000fcd2  mov     rcx, rsi; hKey
0x18000fcd5  call    cs:__imp_RegCloseKey
0x18000fcdc  nop     dword ptr [rax+rax+00h]
0x18000fce1  mov     eax, ebx
0x18000fce3  mov     rcx, [rbp+550h+var_30]
0x18000fcea  xor     rcx, rsp; StackCookie
0x18000fced  call    __security_check_cookie
0x18000fcf2  lea     r11, [rsp+650h+var_20]
0x18000fcfa  mov     rbx, [r11+38h]
0x18000fcfe  mov     rsi, [r11+40h]
0x18000fd02  mov     rsp, r11
0x18000fd05  pop     r15
0x18000fd07  pop     r14
0x18000fd09  pop     r12
0x18000fd0b  pop     rdi
0x18000fd0c  pop     rbp
0x18000fd0d  retn
```
