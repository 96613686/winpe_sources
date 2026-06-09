# getTokenFromUrlList(_PROCESS_ENTRY *,_MODULE_ENTRY *,ushort const *,ushort const *,ushort const *,void * *,ulong *)

- ea: `0x180195a68`
- end: `0x180195d70`
- name: `?getTokenFromUrlList@@YAHPEAU_PROCESS_ENTRY@@PEAU_MODULE_ENTRY@@PEBG22PEAPEAXPEAK@Z`
- size: `776`
- prototype: `__int64 __fastcall(struct _PROCESS_ENTRY *, struct _MODULE_ENTRY *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18019ef84`

## callees

- `0x1800084a0`
- `0x180022bb0`
- `0x18018b498`
- `0x18018b9e4`
- `0x180195a68`
- `0x1801abf80`
- `0x1801abfbc`
- `0x1801d6350`
- `0x180205010`

## string_xrefs

- `0x180195b07`: `DebugInfoD - getTokenFromUrlList for module %ls file %s`
- `0x180195b89`: `DebugInfoD getTokenFromUrlList ...`
- `0x180195bb0`: `DebugInfoD - getTokenFromUrlList exit as module %ls is a known source provider`
- `0x180195c20`: `DebugInfoD getTokenFromUrlList exit as module is a known source provider.`
- `0x180195c91`: `DebugInfoD getTokenFromUrlList exit as fnSymGetSourceFileUrlListCallback is nullptr.`
- `0x180195cd4`: `DebugInfoD getTokenFromUrlList the call to GetSourceFileUrlList failed.`
- `0x180195d08`: `DebugInfoD getTokenFromUrlList succeeded getting token from web url list.`
- `0x180195d30`: `DebugInfoD getTokenFromUrlList failed getting token from web url list.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall getTokenFromUrlList(
        struct _PROCESS_ENTRY *a1,
        struct _MODULE_ENTRY *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        void **a6,
        unsigned int *a7)
{
  struct _MODULE_ENTRY *v7; // rsi
  char *v8; // r14
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rdx
  __int64 v12; // rcx
  char *v14; // [rsp+90h] [rbp-78h]
  unsigned __int16 *v15[3]; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 v16; // [rsp+B8h] [rbp-50h]

  v7 = a2;
  v8 = (char *)a2 + 46;
  v14 = (char *)a2 + 46;
  if ( a2 == (struct _MODULE_ENTRY *)-46LL )
  {
    LogXmlInfo(L"SourceStream", L"DebugInfoD getTokenFromUrlList ...");
  }
  else
  {
    try
    {
      FormatStdWString(v15, L"DebugInfoD - getTokenFromUrlList for module %ls file %s", (char *)a2 + 46, a3);
      v9 = (const unsigned __int16 *)v15;
      if ( v16 > 7 )
        v9 = v15[0];
      LogXmlInfo(L"SourceStream", v9);
      std::wstring::_Tidy_deallocate(v15);
    }
    catch ( ... )
    {
      LogXmlInfo(L"SourceStream", L"DebugInfoD getTokenFromUrlList ...");
      v7 = a2;
      v8 = v14;
    }
  }
  if ( *((int *)v7 + 4956) <= 0 )
  {
    v12 = *((_QWORD *)v7 + 3028);
    if ( v12 )
    {
      if ( qword_1802AF968 )
        qword_1802AF968(v12, *((unsigned int *)v7 + 6058));
      *((_QWORD *)v7 + 3028) = 0;
      *((_DWORD *)v7 + 6058) = 0;
    }
    LoadDynamicCalls(&g_OleAut32CallsDesc);
  }
  else if ( v8 )
  {
    try
    {
      FormatStdWString(v15, L"DebugInfoD - getTokenFromUrlList exit as module %ls is a known source provider", v8);
      v10 = (const unsigned __int16 *)v15;
      if ( v16 > 7 )
        v10 = v15[0];
      LogXmlInfo(L"SourceStream", v10);
      std::wstring::_Tidy_deallocate(v15);
    }
    catch ( ... )
    {
      LogXmlInfo(L"SourceStream", L"DebugInfoD getTokenFromUrlList exit as module is a known source provider.");
    }
  }
  else
  {
    LogXmlInfo(L"SourceStream", L"DebugInfoD getTokenFromUrlList exit as module is a known source provider.");
  }
  return 0;
}

```

## disassembly

```asm
0x180195a68  mov     r11, rsp
0x180195a6b  push    rbx
0x180195a6c  push    rsi
0x180195a6d  push    r12
0x180195a6f  push    r13
0x180195a71  push    r14
0x180195a73  push    r15
0x180195a75  sub     rsp, 0D8h
0x180195a7c  mov     qword ptr [r11-70h], 0FFFFFFFFFFFFFFFEh
0x180195a84  mov     rax, cs:__security_cookie
0x180195a8b  xor     rax, rsp
0x180195a8e  mov     [rsp+108h+var_48], rax
0x180195a96  mov     rax, r9
0x180195a99  mov     [rsp+108h+var_B8], rax
0x180195a9e  mov     r15, r8
0x180195aa1  mov     rsi, rdx
0x180195aa4  mov     [rsp+108h+var_B0], rcx
0x180195aa9  mov     [rsp+108h+var_A8], rcx
0x180195aae  mov     [rsp+108h+var_A0], rdx
0x180195ab3  mov     [rsp+108h+var_98], r8
0x180195ab8  mov     [rsp+108h+var_90], rax
0x180195abd  mov     rax, [rsp+108h+arg_20]
0x180195ac5  mov     [rsp+108h+var_C0], rax
0x180195aca  mov     r12, [rsp+108h+arg_28]
0x180195ad2  mov     [rsp+108h+var_88], r12
0x180195ada  mov     r13, [rsp+108h+arg_30]
0x180195ae2  mov     [rsp+108h+var_80], r13
0x180195aea  lea     r14, [rdx+2Eh]
0x180195aee  mov     [rsp+108h+var_78], r14
0x180195af6  xor     ebx, ebx
0x180195af8  test    r14, r14
0x180195afb  jz      loc_180195B89
0x180195b01  mov     r9, r8
0x180195b04  mov     r8, r14
0x180195b07  lea     rdx, aDebuginfodGett_1; "DebugInfoD - getTokenFromUrlList for mo"...
0x180195b0e  lea     rcx, [r11-68h]
0x180195b12  call    ?FormatStdWString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBGZZ; FormatStdWString(ushort const * const,...)
0x180195b17  nop
0x180195b18  lea     rdx, [rsp+108h+var_68]
0x180195b20  cmp     [rsp+108h+var_50], 7
0x180195b29  cmova   rdx, [rsp+108h+var_68]; unsigned __int16 *
0x180195b32  lea     rcx, aSourcestream; "SourceStream"
0x180195b39  call    ?LogXmlInfo@@YAXPEBG0ZZ; LogXmlInfo(ushort const *,ushort const *,...)
0x180195b3e  nop
0x180195b3f  lea     rcx, [rsp+108h+var_68]
0x180195b47  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180195b4c  nop
0x180195b4d  jmp     short loc_180195B9C
0x180195b4f  xor     ebx, ebx
0x180195b51  mov     rax, [rsp+108h+var_A8]
0x180195b56  mov     [rsp+108h+var_B0], rax
0x180195b5b  mov     rsi, [rsp+108h+var_A0]
0x180195b60  mov     r15, [rsp+108h+var_98]
0x180195b65  mov     rax, [rsp+108h+var_90]
0x180195b6a  mov     [rsp+108h+var_B8], rax
0x180195b6f  mov     r12, [rsp+108h+var_88]
0x180195b77  mov     r13, [rsp+108h+var_80]
0x180195b7f  mov     r14, [rsp+108h+var_78]
0x180195b87  jmp     short loc_180195B9C
0x180195b89  lea     rdx, aDebuginfodGett_3; "DebugInfoD getTokenFromUrlList ..."
0x180195b90  lea     rcx, aSourcestream; "SourceStream"
0x180195b97  call    ?LogXmlInfo@@YAXPEBG0ZZ; LogXmlInfo(ushort const *,ushort const *,...)
0x180195b9c  cmp     [rsi+4D70h], ebx
0x180195ba2  jle     loc_180195C35
0x180195ba8  test    r14, r14
0x180195bab  jz      short loc_180195C20
0x180195bad  mov     r8, r14
0x180195bb0  lea     rdx, aDebuginfodGett_0; "DebugInfoD - getTokenFromUrlList exit a"...
0x180195bb7  lea     rcx, [rsp+108h+var_68]
0x180195bbf  call    ?FormatStdWString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBGZZ; FormatStdWString(ushort const * const,...)
0x180195bc4  nop
0x180195bc5  lea     rdx, [rsp+108h+var_68]
0x180195bcd  cmp     [rsp+108h+var_50], 7
0x180195bd6  cmova   rdx, [rsp+108h+var_68]; unsigned __int16 *
0x180195bdf  lea     rcx, aSourcestream; "SourceStream"
0x180195be6  call    ?LogXmlInfo@@YAXPEBG0ZZ; LogXmlInfo(ushort const *,ushort const *,...)
0x180195beb  nop
0x180195bec  lea     rcx, [rsp+108h+var_68]
0x180195bf4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180195bf9  nop
0x180195bfa  xor     eax, eax
0x180195bfc  mov     rcx, [rsp+108h+var_48]
0x180195c04  xor     rcx, rsp; StackCookie
0x180195c07  call    __security_check_cookie
0x180195c0c  add     rsp, 0D8h
0x180195c13  pop     r15
0x180195c15  pop     r14
0x180195c17  pop     r13
0x180195c19  pop     r12
0x180195c1b  pop     rsi
0x180195c1c  pop     rbx
0x180195c1d  retn
0x180195c1e  jmp     short loc_180195BFA
0x180195c20  lea     rdx, aDebuginfodGett_2; "DebugInfoD getTokenFromUrlList exit as "...
0x180195c27  lea     rcx, aSourcestream; "SourceStream"
0x180195c2e  call    ?LogXmlInfo@@YAXPEBG0ZZ; LogXmlInfo(ushort const *,ushort const *,...)
0x180195c33  jmp     short loc_180195BFA
0x180195c35  mov     rcx, [rsi+5EA0h]
0x180195c3c  test    rcx, rcx
0x180195c3f  jz      short loc_180195C65
0x180195c41  mov     rax, cs:qword_1802AF968
0x180195c48  test    rax, rax
0x180195c4b  jz      short loc_180195C58
0x180195c4d  mov     edx, [rsi+5EA8h]
0x180195c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195c58  mov     [rsi+5EA0h], rbx
0x180195c5f  mov     [rsi+5EA8h], ebx
0x180195c65  lea     rcx, ?g_OleAut32CallsDesc@@3U_DYNAMIC_CALLS_DESC@@C; _DYNAMIC_CALLS_DESC volatile g_OleAut32CallsDesc
0x180195c6c  call    LoadDynamicCalls
0x180195c71  test    eax, eax
0x180195c73  jnz     short loc_180195BFA
0x180195c75  mov     rax, cs:qword_1802ECD70
0x180195c7c  test    rax, rax
0x180195c7f  jz      loc_180195BFA
0x180195c85  mov     rax, cs:qword_1802B1C58
0x180195c8c  test    rax, rax
0x180195c8f  jnz     short loc_180195C9A
0x180195c91  lea     rdx, aDebuginfodGett_4; "DebugInfoD getTokenFromUrlList exit as "...
0x180195c98  jmp     short loc_180195C27
0x180195c9a  mov     [rsp+108h+var_C8], rbx
0x180195c9f  lea     rcx, [rsp+108h+var_C8]
0x180195ca4  mov     [rsp+108h+var_E0], rcx
0x180195ca9  mov     rcx, [rsp+108h+var_C0]
0x180195cae  mov     [rsp+108h+var_E8], rcx
0x180195cb3  mov     r14, [rsp+108h+var_B8]
0x180195cb8  mov     r9, r14
0x180195cbb  mov     r8, r15
0x180195cbe  mov     rdx, [rsi+18h]
0x180195cc2  mov     rcx, [rsp+108h+var_B0]
0x180195cc7  mov     rcx, [rcx+30h]
0x180195ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195cd0  test    eax, eax
0x180195cd2  jns     short loc_180195CE0
0x180195cd4  lea     rdx, aDebuginfodGett_6; "DebugInfoD getTokenFromUrlList the call"...
0x180195cdb  jmp     loc_180195C27
0x180195ce0  mov     rax, cs:qword_1802AF960
0x180195ce7  test    rax, rax
0x180195cea  jz      short loc_180195D30
0x180195cec  mov     r9, r13
0x180195cef  mov     r8, r12
0x180195cf2  mov     rdx, [rsp+108h+var_C8]
0x180195cf7  mov     rcx, r14
0x180195cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195cff  test    eax, eax
0x180195d01  jz      short loc_180195D30
0x180195d03  mov     ebx, 1
0x180195d08  lea     rdx, aDebuginfodGett_5; "DebugInfoD getTokenFromUrlList succeede"...
0x180195d0f  lea     rcx, aSourcestream; "SourceStream"
0x180195d16  call    ?LogXmlInfo@@YAXPEBG0ZZ; LogXmlInfo(ushort const *,ushort const *,...)
0x180195d1b  mov     rdx, [rsi+130h]; unsigned __int16 *
0x180195d22  lea     rcx, aSourcestreamDe; "SourceStream_DebugInfoD"
0x180195d29  call    ?FeatureUsed@@YAXPEBG0@Z; FeatureUsed(ushort const *,ushort const *)
0x180195d2e  jmp     short loc_180195D43
0x180195d30  lea     rdx, aDebuginfodGett; "DebugInfoD getTokenFromUrlList failed g"...
0x180195d37  lea     rcx, aSourcestream; "SourceStream"
0x180195d3e  call    ?LogXmlError@@YAXPEBG0ZZ; LogXmlError(ushort const *,ushort const *,...)
0x180195d43  mov     rax, cs:qword_1802ECD70
0x180195d4a  mov     rcx, [rsp+108h+var_C8]
0x180195d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195d54  mov     rcx, [r12]
0x180195d58  mov     [rsi+5EA0h], rcx
0x180195d5f  mov     ecx, [r13+0]
0x180195d63  mov     [rsi+5EA8h], ecx
0x180195d69  mov     eax, ebx
0x180195d6b  jmp     loc_180195BFC
```
