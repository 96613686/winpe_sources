# RegistryConfig::ParseCommand(HKEY__ *,ushort const *)

- ea: `0x18000b3f0`
- end: `0x18000b658`
- name: `?ParseCommand@RegistryConfig@@AEAA?AUCommand@@PEAUHKEY__@@PEBG@Z`
- size: `616`
- prototype: `_WORD *__fastcall(__int64, _WORD *, HKEY, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000a0dc`

## callees

- `0x18000112c`
- `0x180007c18`
- `0x18000a588`
- `0x18000b06c`
- `0x18000b0bc`
- `0x18000b3f0`
- `0x18000c600`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b474`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b4a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b60e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b631`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b474`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b4a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b60e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b631`

## string_xrefs

- `0x18000b44d`: `CommandLine`
- `0x18000b56a`: `ContinueInstall`
- `0x18000b47a`: `WorkingDirectory`

## pseudocode

```c
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
0x18000b3f0  push    rbp
0x18000b3f2  push    rbx
0x18000b3f3  push    rsi
0x18000b3f4  push    rdi
0x18000b3f5  push    r13
0x18000b3f7  push    r14
0x18000b3f9  push    r15
0x18000b3fb  lea     rbp, [rsp-27h]
0x18000b400  sub     rsp, 0E0h
0x18000b407  mov     rax, cs:__security_cookie
0x18000b40e  xor     rax, rsp
0x18000b411  mov     [rbp+57h+var_40], rax
0x18000b415  mov     r15, r9
0x18000b418  mov     r14, r8
0x18000b41b  mov     rsi, rdx
0x18000b41e  mov     [rbp+57h+var_C0], rdx
0x18000b422  mov     r13d, 7
0x18000b428  mov     [rbp+57h+var_68], r13
0x18000b42c  mov     [rbp+57h+var_70], 0
0x18000b434  xor     eax, eax
0x18000b436  mov     word ptr [rbp+57h+Src], ax
0x18000b43a  mov     [rbp+57h+var_88], r13
0x18000b43e  mov     [rbp+57h+var_90], rax
0x18000b442  mov     word ptr [rbp+57h+var_A0], ax
0x18000b446  mov     [rbp+57h+var_C8], rax
0x18000b44a  mov     [rbp+57h+var_D0], eax
0x18000b44d  lea     r9, aCommandline; "CommandLine"
0x18000b454  lea     rdx, [rbp+57h+var_60]
0x18000b458  call    ?GetStringValue@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG@Z; RegistryConfig::GetStringValue(HKEY__ *,ushort const *)
0x18000b45d  mov     rdx, rax; Src
0x18000b460  lea     rcx, [rbp+57h+Src]; void *
0x18000b464  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000b469  cmp     [rbp+57h+var_48], 8
0x18000b46e  jb      short loc_18000B47A
0x18000b470  mov     rcx, [rbp+57h+var_60]
0x18000b474  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b47a  lea     r9, aWorkingdirecto; "WorkingDirectory"
0x18000b481  mov     r8, r14
0x18000b484  lea     rdx, [rbp+57h+var_60]
0x18000b488  call    ?GetStringValue@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG@Z; RegistryConfig::GetStringValue(HKEY__ *,ushort const *)
0x18000b48d  mov     rdx, rax; Src
0x18000b490  lea     rcx, [rbp+57h+var_A0]; void *
0x18000b494  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000b499  cmp     [rbp+57h+var_48], 8
0x18000b49e  jb      short loc_18000B4AA
0x18000b4a0  mov     rcx, [rbp+57h+var_60]
0x18000b4a4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b4aa  lea     rdi, [rbp+57h+var_A0]
0x18000b4ae  cmp     [rbp+57h+var_88], 8
0x18000b4b3  cmovnb  rdi, [rbp+57h+var_A0]
0x18000b4b8  lea     rbx, [rbp+57h+Src]
0x18000b4bc  cmp     [rbp+57h+var_68], 8
0x18000b4c1  cmovnb  rbx, [rbp+57h+Src]
0x18000b4c6  mov     [rsi+18h], r13
0x18000b4ca  mov     qword ptr [rsi+10h], 0
0x18000b4d2  xor     eax, eax
0x18000b4d4  mov     [rsi], ax
0x18000b4d7  mov     rdx, r15; Src
0x18000b4da  mov     rcx, rsi; void *
0x18000b4dd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000b4e2  nop
0x18000b4e3  lea     rcx, [rsi+20h]; void *
0x18000b4e7  mov     [rcx+18h], r13
0x18000b4eb  mov     qword ptr [rcx+10h], 0
0x18000b4f3  xor     eax, eax
0x18000b4f5  mov     [rcx], ax
0x18000b4f8  mov     rdx, rbx; Src
0x18000b4fb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000b500  nop
0x18000b501  lea     rcx, [rsi+40h]; void *
0x18000b505  mov     [rcx+18h], r13
0x18000b509  mov     qword ptr [rcx+10h], 0
0x18000b511  xor     eax, eax
0x18000b513  mov     [rcx], ax
0x18000b516  mov     rdx, rdi; Src
0x18000b519  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000b51e  mov     dword ptr [rsi+60h], 0
0x18000b525  mov     dword ptr [rsi+64h], 1
0x18000b52c  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x18000b530  lea     r8, aReturncodesucc; "ReturnCodeSuccess"
0x18000b537  mov     rdx, r14; HKEY
0x18000b53a  call    ?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)
0x18000b53f  test    eax, eax
0x18000b541  jnz     short loc_18000B549
0x18000b543  mov     eax, [rbp+57h+var_D0]
0x18000b546  mov     [rsi+68h], eax
0x18000b549  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x18000b54d  lea     r8, aReturncoderest; "ReturnCodeRestart"
0x18000b554  mov     rdx, r14; HKEY
0x18000b557  call    ?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)
0x18000b55c  test    eax, eax
0x18000b55e  jnz     short loc_18000B566
0x18000b560  mov     eax, [rbp+57h+var_D0]
0x18000b563  mov     [rsi+6Ch], eax
0x18000b566  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x18000b56a  lea     r8, aContinueinstal; "ContinueInstall"
0x18000b571  mov     rdx, r14; HKEY
0x18000b574  call    ?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)
0x18000b579  test    eax, eax
0x18000b57b  jnz     short loc_18000B587
0x18000b57d  cmp     [rbp+57h+var_D0], 1
0x18000b581  setz    al
0x18000b584  mov     [rsi+64h], eax
0x18000b587  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x18000b58b  lea     r8, aRestartrequire; "RestartRequired"
0x18000b592  mov     rdx, r14; HKEY
0x18000b595  call    ?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)
0x18000b59a  test    eax, eax
0x18000b59c  jnz     short loc_18000B5A8
0x18000b59e  cmp     [rbp+57h+var_D0], 1
0x18000b5a2  setz    al
0x18000b5a5  mov     [rsi+60h], eax
0x18000b5a8  mov     eax, cs:dword_180014230
0x18000b5ae  cmp     eax, 4
0x18000b5b1  jbe     short loc_18000B603
0x18000b5b3  lea     rax, [rbp+57h+var_A0]
0x18000b5b7  cmp     [rbp+57h+var_88], 8
0x18000b5bc  cmovnb  rax, [rbp+57h+var_A0]
0x18000b5c1  mov     [rbp+57h+var_A8], rax
0x18000b5c5  lea     rax, [rbp+57h+Src]
0x18000b5c9  cmp     [rbp+57h+var_68], 8
0x18000b5ce  cmovnb  rax, [rbp+57h+Src]
0x18000b5d3  mov     [rbp+57h+var_C8], rax
0x18000b5d7  mov     [rbp+57h+var_C0], r15
0x18000b5db  lea     rax, [rbp+57h+var_A8]
0x18000b5df  mov     [rsp+110h+var_E0], rax
0x18000b5e4  lea     rax, [rbp+57h+var_C8]
0x18000b5e8  mov     [rsp+110h+var_E8], rax
0x18000b5ed  lea     rax, [rbp+57h+var_C0]
0x18000b5f1  mov     [rsp+110h+var_F0], rax
0x18000b5f6  lea     rdx, byte_180010C03
0x18000b5fd  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000b602  nop
0x18000b603  cmp     [rbp+57h+var_88], 8
0x18000b608  jb      short loc_18000B614
0x18000b60a  mov     rcx, [rbp+57h+var_A0]
0x18000b60e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b614  mov     [rbp+57h+var_88], r13
0x18000b618  mov     [rbp+57h+var_90], 0
0x18000b620  xor     ecx, ecx
0x18000b622  mov     word ptr [rbp+57h+var_A0], cx
0x18000b626  cmp     [rbp+57h+var_68], 8
0x18000b62b  jb      short loc_18000B637
0x18000b62d  mov     rcx, [rbp+57h+Src]
0x18000b631  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b637  mov     rax, rsi
0x18000b63a  mov     rcx, [rbp+57h+var_40]
0x18000b63e  xor     rcx, rsp; StackCookie
0x18000b641  call    __security_check_cookie
0x18000b646  add     rsp, 0E0h
0x18000b64d  pop     r15
0x18000b64f  pop     r14
0x18000b651  pop     r13
0x18000b653  pop     rdi
0x18000b654  pop     rsi
0x18000b655  pop     rbx
0x18000b656  pop     rbp
0x18000b657  retn
```
