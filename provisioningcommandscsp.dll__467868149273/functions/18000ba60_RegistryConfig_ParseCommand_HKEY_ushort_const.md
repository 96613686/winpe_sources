# RegistryConfig::ParseCommand(HKEY__ *,ushort const *)

- ea: `0x18000ba60`
- end: `0x18000bce1`
- name: `?ParseCommand@RegistryConfig@@AEAA?AUCommand@@PEAUHKEY__@@PEBG@Z`
- size: `641`
- prototype: `struct Command __high(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000a5f4`

## callees

- `0x180001134`
- `0x180007fac`
- `0x18000aaf0`
- `0x18000b6a4`
- `0x18000b6f8`
- `0x18000ba60`
- `0x18000ccc0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000bae4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bb1a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bc8a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bcb3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bae4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bb1a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bc8a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bcb3`

## string_xrefs

- `0x18000babd`: `CommandLine`
- `0x18000bbe6`: `ContinueInstall`
- `0x18000baf0`: `WorkingDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_WORD *__fastcall RegistryConfig::ParseCommand(__int64 a1, _WORD *a2, HKEY a3, void *a4)
{
  void *StringValue; // rax
  __int64 v8; // rcx
  void *v9; // rax
  void **v10; // rdi
  void **v11; // rbx
  RegistryConfig *v12; // rcx
  RegistryConfig *v13; // rcx
  RegistryConfig *v14; // rcx
  RegistryConfig *v15; // rcx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  void **v19; // rax
  void **v20; // rax
  unsigned int v22; // [rsp+40h] [rbp-79h] BYREF
  void **v23; // [rsp+48h] [rbp-71h] BYREF
  void *v24; // [rsp+50h] [rbp-69h] BYREF
  void **v25; // [rsp+68h] [rbp-51h] BYREF
  void *v26[2]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v27; // [rsp+80h] [rbp-39h]
  unsigned __int64 v28; // [rsp+88h] [rbp-31h]
  void *Src[3]; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int64 v30; // [rsp+A8h] [rbp-11h]
  void *v31[3]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int64 v32; // [rsp+C8h] [rbp+Fh]

  v24 = a2;
  v30 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  v28 = 7;
  v27 = 0;
  LOWORD(v26[0]) = 0;
  v23 = 0;
  v22 = 0;
  StringValue = (void *)RegistryConfig::GetStringValue(a1, v31, a3, L"CommandLine");
  std::wstring::operator=(Src, StringValue);
  if ( v32 >= 8 )
    operator delete(v31[0]);
  v9 = (void *)RegistryConfig::GetStringValue(v8, v31, a3, L"WorkingDirectory");
  std::wstring::operator=(v26, v9);
  if ( v32 >= 8 )
    operator delete(v31[0]);
  v10 = v26;
  if ( v28 >= 8 )
    v10 = (void **)v26[0];
  v11 = Src;
  if ( v30 >= 8 )
    v11 = (void **)Src[0];
  *((_QWORD *)a2 + 3) = 7;
  *((_QWORD *)a2 + 2) = 0;
  *a2 = 0;
  std::wstring::assign(a2, a4);
  *((_QWORD *)a2 + 7) = 7;
  *((_QWORD *)a2 + 6) = 0;
  a2[16] = 0;
  std::wstring::assign(a2 + 16, v11);
  *((_QWORD *)a2 + 11) = 7;
  *((_QWORD *)a2 + 10) = 0;
  a2[32] = 0;
  std::wstring::assign(a2 + 32, v10);
  *((_DWORD *)a2 + 24) = 0;
  *((_DWORD *)a2 + 25) = 1;
  if ( !RegistryConfig::GetNumericalValue(v12, a3, L"ReturnCodeSuccess", &v22) )
    *((_DWORD *)a2 + 26) = v22;
  if ( !RegistryConfig::GetNumericalValue(v13, a3, L"ReturnCodeRestart", &v22) )
    *((_DWORD *)a2 + 27) = v22;
  if ( !RegistryConfig::GetNumericalValue(v14, a3, L"ContinueInstall", &v22) )
    *((_DWORD *)a2 + 25) = v22 == 1;
  if ( !RegistryConfig::GetNumericalValue(v15, a3, L"RestartRequired", &v22) )
    *((_DWORD *)a2 + 24) = v22 == 1;
  if ( (unsigned int)dword_180014230 > 4 )
  {
    v19 = v26;
    if ( v28 >= 8 )
      v19 = (void **)v26[0];
    v25 = v19;
    v20 = Src;
    if ( v30 >= 8 )
      v20 = (void **)Src[0];
    v23 = v20;
    v24 = a4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v16,
      (unsigned int)byte_180010C03,
      v17,
      v18,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v25);
  }
  if ( v28 >= 8 )
    operator delete(v26[0]);
  v28 = 7;
  v27 = 0;
  LOWORD(v26[0]) = 0;
  if ( v30 >= 8 )
    operator delete(Src[0]);
  return a2;
}

```

## disassembly

```asm
0x18000ba60  push    rbp
0x18000ba62  push    rbx
0x18000ba63  push    rsi
0x18000ba64  push    rdi
0x18000ba65  push    r13
0x18000ba67  push    r14
0x18000ba69  push    r15
0x18000ba6b  lea     rbp, [rsp-27h]
0x18000ba70  sub     rsp, 0E0h
0x18000ba77  mov     rax, cs:__security_cookie
0x18000ba7e  xor     rax, rsp
0x18000ba81  mov     [rbp+57h+var_40], rax
0x18000ba85  mov     r15, r9
0x18000ba88  mov     r14, r8
0x18000ba8b  mov     rsi, rdx
0x18000ba8e  mov     [rbp+57h+var_C0], rdx
0x18000ba92  mov     r13d, 7
0x18000ba98  mov     [rbp+57h+var_68], r13
0x18000ba9c  mov     [rbp+57h+var_70], 0
0x18000baa4  xor     eax, eax
0x18000baa6  mov     word ptr [rbp+57h+Src], ax
0x18000baaa  mov     [rbp+57h+var_88], r13
0x18000baae  mov     [rbp+57h+var_90], rax
0x18000bab2  mov     word ptr [rbp+57h+var_A0], ax
0x18000bab6  mov     [rbp+57h+var_C8], rax
0x18000baba  mov     [rbp+57h+var_D0], eax
0x18000babd  lea     r9, aCommandline; "CommandLine"
0x18000bac4  lea     rdx, [rbp+57h+var_60]
0x18000bac8  call    ?GetStringValue@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG@Z; RegistryConfig::GetStringValue(HKEY__ *,ushort const *)
0x18000bacd  mov     rdx, rax; Src
0x18000bad0  lea     rcx, [rbp+57h+Src]; void *
0x18000bad4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000bad9  cmp     [rbp+57h+var_48], 8
0x18000bade  jb      short loc_18000BAF0
0x18000bae0  mov     rcx, [rbp+57h+var_60]
0x18000bae4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000baeb  nop     dword ptr [rax+rax+00h]
0x18000baf0  lea     r9, aWorkingdirecto; "WorkingDirectory"
0x18000baf7  mov     r8, r14
0x18000bafa  lea     rdx, [rbp+57h+var_60]
0x18000bafe  call    ?GetStringValue@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG@Z; RegistryConfig::GetStringValue(HKEY__ *,ushort const *)
0x18000bb03  mov     rdx, rax; Src
0x18000bb06  lea     rcx, [rbp+57h+var_A0]; void *
0x18000bb0a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000bb0f  cmp     [rbp+57h+var_48], 8
0x18000bb14  jb      short loc_18000BB26
0x18000bb16  mov     rcx, [rbp+57h+var_60]
0x18000bb1a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bb21  nop     dword ptr [rax+rax+00h]
0x18000bb26  lea     rdi, [rbp+57h+var_A0]
0x18000bb2a  cmp     [rbp+57h+var_88], 8
0x18000bb2f  cmovnb  rdi, [rbp+57h+var_A0]
0x18000bb34  lea     rbx, [rbp+57h+Src]
0x18000bb38  cmp     [rbp+57h+var_68], 8
0x18000bb3d  cmovnb  rbx, [rbp+57h+Src]
0x18000bb42  mov     [rsi+18h], r13
0x18000bb46  mov     qword ptr [rsi+10h], 0
0x18000bb4e  xor     eax, eax
0x18000bb50  mov     [rsi], ax
0x18000bb53  mov     rdx, r15; Src
0x18000bb56  mov     rcx, rsi; void *
0x18000bb59  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000bb5e  nop
0x18000bb5f  lea     rcx, [rsi+20h]; void *
0x18000bb63  mov     [rcx+18h], r13
0x18000bb67  mov     qword ptr [rcx+10h], 0
0x18000bb6f  xor     eax, eax
0x18000bb71  mov     [rcx], ax
0x18000bb74  mov     rdx, rbx; Src
0x18000bb77  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000bb7c  nop
0x18000bb7d  lea     rcx, [rsi+40h]; void *
0x18000bb81  mov     [rcx+18h], r13
0x18000bb85  mov     qword ptr [rcx+10h], 0
0x18000bb8d  xor     eax, eax
0x18000bb8f  mov     [rcx], ax
0x18000bb92  mov     rdx, rdi; Src
0x18000bb95  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000bb9a  mov     dword ptr [rsi+60h], 0
0x18000bba1  mov     dword ptr [rsi+64h], 1
0x18000bba8  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x18000bbac  lea     r8, aReturncodesucc; "ReturnCodeSuccess"
0x18000bbb3  mov     rdx, r14; HKEY
0x18000bbb6  call    ?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)
0x18000bbbb  test    eax, eax
0x18000bbbd  jnz     short loc_18000BBC5
0x18000bbbf  mov     eax, [rbp+57h+var_D0]
0x18000bbc2  mov     [rsi+68h], eax
0x18000bbc5  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x18000bbc9  lea     r8, aReturncoderest; "ReturnCodeRestart"
0x18000bbd0  mov     rdx, r14; HKEY
0x18000bbd3  call    ?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)
0x18000bbd8  test    eax, eax
0x18000bbda  jnz     short loc_18000BBE2
0x18000bbdc  mov     eax, [rbp+57h+var_D0]
0x18000bbdf  mov     [rsi+6Ch], eax
0x18000bbe2  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x18000bbe6  lea     r8, aContinueinstal; "ContinueInstall"
0x18000bbed  mov     rdx, r14; HKEY
0x18000bbf0  call    ?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)
0x18000bbf5  test    eax, eax
0x18000bbf7  jnz     short loc_18000BC03
0x18000bbf9  cmp     [rbp+57h+var_D0], 1
0x18000bbfd  setz    al
0x18000bc00  mov     [rsi+64h], eax
0x18000bc03  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x18000bc07  lea     r8, aRestartrequire; "RestartRequired"
0x18000bc0e  mov     rdx, r14; HKEY
0x18000bc11  call    ?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)
0x18000bc16  test    eax, eax
0x18000bc18  jnz     short loc_18000BC24
0x18000bc1a  cmp     [rbp+57h+var_D0], 1
0x18000bc1e  setz    al
0x18000bc21  mov     [rsi+60h], eax
0x18000bc24  mov     eax, cs:dword_180014230
0x18000bc2a  cmp     eax, 4
0x18000bc2d  jbe     short loc_18000BC7F
0x18000bc2f  lea     rax, [rbp+57h+var_A0]
0x18000bc33  cmp     [rbp+57h+var_88], 8
0x18000bc38  cmovnb  rax, [rbp+57h+var_A0]
0x18000bc3d  mov     [rbp+57h+var_A8], rax
0x18000bc41  lea     rax, [rbp+57h+Src]
0x18000bc45  cmp     [rbp+57h+var_68], 8
0x18000bc4a  cmovnb  rax, [rbp+57h+Src]
0x18000bc4f  mov     [rbp+57h+var_C8], rax
0x18000bc53  mov     [rbp+57h+var_C0], r15
0x18000bc57  lea     rax, [rbp+57h+var_A8]
0x18000bc5b  mov     [rsp+110h+var_E0], rax
0x18000bc60  lea     rax, [rbp+57h+var_C8]
0x18000bc64  mov     [rsp+110h+var_E8], rax
0x18000bc69  lea     rax, [rbp+57h+var_C0]
0x18000bc6d  mov     [rsp+110h+var_F0], rax
0x18000bc72  lea     rdx, byte_180010C03
0x18000bc79  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000bc7e  nop
0x18000bc7f  cmp     [rbp+57h+var_88], 8
0x18000bc84  jb      short loc_18000BC96
0x18000bc86  mov     rcx, [rbp+57h+var_A0]
0x18000bc8a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bc91  nop     dword ptr [rax+rax+00h]
0x18000bc96  mov     [rbp+57h+var_88], r13
0x18000bc9a  mov     [rbp+57h+var_90], 0
0x18000bca2  xor     ecx, ecx
0x18000bca4  mov     word ptr [rbp+57h+var_A0], cx
0x18000bca8  cmp     [rbp+57h+var_68], 8
0x18000bcad  jb      short loc_18000BCBF
0x18000bcaf  mov     rcx, [rbp+57h+Src]
0x18000bcb3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bcba  nop     dword ptr [rax+rax+00h]
0x18000bcbf  mov     rax, rsi
0x18000bcc2  mov     rcx, [rbp+57h+var_40]
0x18000bcc6  xor     rcx, rsp; StackCookie
0x18000bcc9  call    __security_check_cookie
0x18000bcce  add     rsp, 0E0h
0x18000bcd5  pop     r15
0x18000bcd7  pop     r14
0x18000bcd9  pop     r13
0x18000bcdb  pop     rdi
0x18000bcdc  pop     rsi
0x18000bcdd  pop     rbx
0x18000bcde  pop     rbp
0x18000bcdf  retn
```
