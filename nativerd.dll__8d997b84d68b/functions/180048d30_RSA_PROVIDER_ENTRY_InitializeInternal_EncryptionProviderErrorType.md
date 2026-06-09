# RSA_PROVIDER_ENTRY::InitializeInternal(EncryptionProviderErrorType *)

- ea: `0x180048d30`
- end: `0x180048f26`
- name: `?InitializeInternal@RSA_PROVIDER_ENTRY@@UEAAJPEAW4EncryptionProviderErrorType@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(RSA_PROVIDER_ENTRY *__hidden this, enum EncryptionProviderErrorType *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x18000c3f0`
- `0x180048d30`
- `0x180059bea`
- `0x180059bf6`
- `0x180059c30`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180048eef`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180048efa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180048eef`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180048efa`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180048e32`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180048e55`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180048ea7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180048ec9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180048e32`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180048e55`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180048ea7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180048ec9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180048d80`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180048da0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180048d80`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180048da0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180048dda`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180048dda`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180048e0a`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180048e0a`

## string_xrefs

- `0x180048dcf`: `NetFrameworkConfigurationKey`

## pseudocode

```c
__int64 __fastcall RSA_PROVIDER_ENTRY::InitializeInternal(
        RSA_PROVIDER_ENTRY *this,
        enum EncryptionProviderErrorType *a2)
{
  CONFIG_ELEMENT **v4; // rsi
  int v5; // ebx
  const wchar_t *Str; // rax
  int v7; // eax
  int v8; // ebx
  const wchar_t *v9; // rax
  const wchar_t *v10; // rax
  const wchar_t *v11; // rax
  struct ATTRIBUTE_ENTRY *v13; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v14[56]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v15[64]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v16[32]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v17[32]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(v16, 0, sizeof(v16));
  STRU::STRU((STRU *)v15, v16, 0x20u);
  memset_0(v17, 0, sizeof(v17));
  STRU::STRU((STRU *)v14, v17, 0x20u);
  v4 = (CONFIG_ELEMENT **)((char *)this + 32);
  v13 = 0;
  if ( CONFIG_ELEMENT::GetAttributeEntry(
         *((CONFIG_ELEMENT **)this + 4),
         L"keyContainerName",
         &v13,
         (RSA_PROVIDER_ENTRY *)((char *)this + 40)) >= 0
    || (v5 = STRU::Copy((RSA_PROVIDER_ENTRY *)((char *)this + 40), L"NetFrameworkConfigurationKey"), v5 >= 0) )
  {
    if ( CONFIG_ELEMENT::GetAttributeEntry(*v4, L"cspProviderName", &v13, (RSA_PROVIDER_ENTRY *)((char *)this + 96)) < 0 )
      STRU::Reset((RSA_PROVIDER_ENTRY *)((char *)this + 96));
    if ( CONFIG_ELEMENT::GetAttributeEntry(*v4, L"useMachineContainer", &v13, (struct STRU *)v15) < 0 )
    {
      v8 = 1;
    }
    else
    {
      Str = STRU::QueryStr((STRU *)v15);
      v7 = wcscmp_0(Str, L"false");
      v8 = 1;
      if ( !v7 )
        goto LABEL_11;
      v9 = STRU::QueryStr((STRU *)v15);
      if ( wcscmp_0(v9, L"true") )
      {
LABEL_8:
        *(_DWORD *)a2 = 1;
        v5 = -2147024883;
        goto LABEL_16;
      }
    }
    v7 = 1;
LABEL_11:
    *((_DWORD *)this + 38) = v7;
    if ( CONFIG_ELEMENT::GetAttributeEntry(*v4, L"useOAEP", &v13, (struct STRU *)v14) >= 0 )
    {
      v10 = STRU::QueryStr((STRU *)v14);
      if ( !wcscmp_0(v10, L"false") )
      {
        v8 = 0;
      }
      else
      {
        v11 = STRU::QueryStr((STRU *)v14);
        if ( wcscmp_0(v11, L"true") )
          goto LABEL_8;
      }
    }
    *((_DWORD *)this + 39) = v8;
    v5 = 0;
  }
LABEL_16:
  STRU::~STRU((STRU *)v14);
  STRU::~STRU((STRU *)v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180048d30  mov     [rsp-8+arg_10], rbx
0x180048d35  mov     [rsp-8+arg_18], rsi
0x180048d3a  push    rbp
0x180048d3b  push    rdi
0x180048d3c  push    r14
0x180048d3e  lea     rbp, [rsp-30h]
0x180048d43  sub     rsp, 130h
0x180048d4a  mov     rax, cs:__security_cookie
0x180048d51  xor     rax, rsp
0x180048d54  mov     [rbp+40h+var_20], rax
0x180048d58  mov     r14, rdx
0x180048d5b  mov     rdi, rcx
0x180048d5e  mov     esi, 40h ; '@'
0x180048d63  lea     rcx, [rbp+40h+var_A0]; void *
0x180048d67  mov     r8d, esi; Size
0x180048d6a  xor     edx, edx; Val
0x180048d6c  call    memset_0
0x180048d71  lea     ebx, [rsi-20h]
0x180048d74  mov     r8d, ebx
0x180048d77  lea     rdx, [rbp+40h+var_A0]
0x180048d7b  lea     rcx, [rsp+140h+var_E0]
0x180048d80  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180048d86  mov     r8d, esi; Size
0x180048d89  lea     rcx, [rbp+40h+var_60]; void *
0x180048d8d  xor     edx, edx; Val
0x180048d8f  call    memset_0
0x180048d94  mov     r8d, ebx
0x180048d97  lea     rdx, [rbp+40h+var_60]
0x180048d9b  lea     rcx, [rsp+140h+var_118]
0x180048da0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180048da6  lea     rsi, [rdi+20h]
0x180048daa  mov     [rsp+140h+var_120], 0
0x180048db3  mov     rcx, [rsi]; this
0x180048db6  lea     r9, [rdi+28h]; struct STRU *
0x180048dba  lea     r8, [rsp+140h+var_120]; struct ATTRIBUTE_ENTRY **
0x180048dbf  lea     rdx, aKeycontainerna; "keyContainerName"
0x180048dc6  call    ?GetAttributeEntry@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAUATTRIBUTE_ENTRY@@PEAVSTRU@@@Z; CONFIG_ELEMENT::GetAttributeEntry(ushort const *,ATTRIBUTE_ENTRY * *,STRU *)
0x180048dcb  test    eax, eax
0x180048dcd  jns     short loc_180048DEA
0x180048dcf  lea     rdx, aNetframeworkco; "NetFrameworkConfigurationKey"
0x180048dd6  lea     rcx, [rdi+28h]
0x180048dda  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180048de0  mov     ebx, eax
0x180048de2  test    eax, eax
0x180048de4  js      loc_180048EEA
0x180048dea  mov     rcx, [rsi]; this
0x180048ded  lea     r9, [rdi+60h]; struct STRU *
0x180048df1  lea     r8, [rsp+140h+var_120]; struct ATTRIBUTE_ENTRY **
0x180048df6  lea     rdx, aCspprovidernam; "cspProviderName"
0x180048dfd  call    ?GetAttributeEntry@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAUATTRIBUTE_ENTRY@@PEAVSTRU@@@Z; CONFIG_ELEMENT::GetAttributeEntry(ushort const *,ATTRIBUTE_ENTRY * *,STRU *)
0x180048e02  test    eax, eax
0x180048e04  jns     short loc_180048E10
0x180048e06  lea     rcx, [rdi+60h]
0x180048e0a  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180048e10  mov     rcx, [rsi]; this
0x180048e13  lea     r9, [rsp+140h+var_E0]; struct STRU *
0x180048e18  lea     r8, [rsp+140h+var_120]; struct ATTRIBUTE_ENTRY **
0x180048e1d  lea     rdx, aUsemachinecont; "useMachineContainer"
0x180048e24  call    ?GetAttributeEntry@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAUATTRIBUTE_ENTRY@@PEAVSTRU@@@Z; CONFIG_ELEMENT::GetAttributeEntry(ushort const *,ATTRIBUTE_ENTRY * *,STRU *)
0x180048e29  test    eax, eax
0x180048e2b  js      short loc_180048E78
0x180048e2d  lea     rcx, [rsp+140h+var_E0]
0x180048e32  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180048e38  mov     rcx, rax; String1
0x180048e3b  lea     rdx, aFalse; "false"
0x180048e42  call    wcscmp_0
0x180048e47  mov     ebx, 1
0x180048e4c  test    eax, eax
0x180048e4e  jz      short loc_180048E7F
0x180048e50  lea     rcx, [rsp+140h+var_E0]
0x180048e55  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180048e5b  mov     rcx, rax; String1
0x180048e5e  lea     rdx, aTrue; "true"
0x180048e65  call    wcscmp_0
0x180048e6a  test    eax, eax
0x180048e6c  jz      short loc_180048E7D
0x180048e6e  mov     [r14], ebx
0x180048e71  mov     ebx, 8007000Dh
0x180048e76  jmp     short loc_180048EEA
0x180048e78  mov     ebx, 1
0x180048e7d  mov     eax, ebx
0x180048e7f  mov     [rdi+98h], eax
0x180048e85  lea     r9, [rsp+140h+var_118]; struct STRU *
0x180048e8a  mov     rcx, [rsi]; this
0x180048e8d  lea     r8, [rsp+140h+var_120]; struct ATTRIBUTE_ENTRY **
0x180048e92  lea     rdx, aUseoaep; "useOAEP"
0x180048e99  call    ?GetAttributeEntry@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAUATTRIBUTE_ENTRY@@PEAVSTRU@@@Z; CONFIG_ELEMENT::GetAttributeEntry(ushort const *,ATTRIBUTE_ENTRY * *,STRU *)
0x180048e9e  test    eax, eax
0x180048ea0  js      short loc_180048EE2
0x180048ea2  lea     rcx, [rsp+140h+var_118]
0x180048ea7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180048ead  mov     rcx, rax; String1
0x180048eb0  lea     rdx, aFalse; "false"
0x180048eb7  call    wcscmp_0
0x180048ebc  test    eax, eax
0x180048ebe  jnz     short loc_180048EC4
0x180048ec0  xor     ebx, ebx
0x180048ec2  jmp     short loc_180048EE2
0x180048ec4  lea     rcx, [rsp+140h+var_118]
0x180048ec9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180048ecf  mov     rcx, rax; String1
0x180048ed2  lea     rdx, aTrue; "true"
0x180048ed9  call    wcscmp_0
0x180048ede  test    eax, eax
0x180048ee0  jnz     short loc_180048E6E
0x180048ee2  mov     [rdi+9Ch], ebx
0x180048ee8  xor     ebx, ebx
0x180048eea  lea     rcx, [rsp+140h+var_118]
0x180048eef  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180048ef5  lea     rcx, [rsp+140h+var_E0]
0x180048efa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180048f00  mov     eax, ebx
0x180048f02  mov     rcx, [rbp+40h+var_20]
0x180048f06  xor     rcx, rsp; StackCookie
0x180048f09  call    __security_check_cookie
0x180048f0e  lea     r11, [rsp+140h+var_10]
0x180048f16  mov     rbx, [r11+30h]
0x180048f1a  mov     rsi, [r11+38h]
0x180048f1e  mov     rsp, r11
0x180048f21  pop     r14
0x180048f23  pop     rdi
0x180048f24  pop     rbp
0x180048f25  retn
```
