# Js::EngineInterfaceObject::EntryIntl_CompareString(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x1801ab0d0`
- end: `0x1801ab383`
- name: `?EntryIntl_CompareString@EngineInterfaceObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `691`
- prototype: `__int64 __fastcall(__int64, int, __int64, _DWORD *, _DWORD *, unsigned __int64, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1802c0290`

## callees

- `0x180036e50`
- `0x180053c00`
- `0x18007434c`
- `0x1801ab0d0`
- `0x1801ab38c`
- `0x1803149f0`
- `0x1803481f0`
- `0x180364010`

## import_xrefs

- `KERNEL32!CompareStringEx` at `0x1801ab311`
- `KERNEL32!CompareStringEx` at `0x1801ab311`
- `KERNEL32!GetUserDefaultLocaleName` at `0x1801ab276`
- `KERNEL32!GetUserDefaultLocaleName` at `0x1801ab276`
- `KERNEL32!GetLastError` at `0x1801ab286`
- `KERNEL32!GetLastError` at `0x1801ab333`
- `KERNEL32!GetLastError` at `0x1801ab286`
- `KERNEL32!GetLastError` at `0x1801ab333`

## pseudocode

```c
__int64 __fastcall Js::EngineInterfaceObject::EntryIntl_CompareString(
        __int64 a1,
        int a2,
        __int64 a3,
        _DWORD *a4,
        _DWORD *a5,
        unsigned __int64 a6,
        unsigned __int64 a7,
        unsigned __int64 a8,
        unsigned __int64 a9)
{
  ThreadContext **v10; // r8
  struct Js::ScriptContext *v11; // r14
  __int64 v12; // r15
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v16; // rdx
  const wchar_t *v17; // rax
  const unsigned __int16 *v18; // rdx
  DWORD FlagsForSensitivity; // ebp
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r8
  signed int LastError; // eax
  int cchCount2; // esi
  const WCHAR *lpString2; // rbx
  int v26; // edi
  const WCHAR *v27; // rax
  WCHAR *v28; // rcx
  int v29; // eax
  signed int v30; // eax
  WCHAR LocaleName[88]; // [rsp+60h] [rbp-F8h] BYREF

  v10 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1072LL);
  ThreadContext::ProbeStack(v10[148], 0x450u, (struct Js::ScriptContext *)v10, 0);
  v11 = *(struct Js::ScriptContext **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1072LL);
  if ( (a2 & 0xFFFFFFu) < 7
    || !Js::JavascriptString::Is((unsigned __int64)a4)
    || !Js::JavascriptString::Is((unsigned __int64)a5) )
  {
    return *(_QWORD *)(*(_QWORD *)v11 + 1056LL);
  }
  v12 = 0;
  LocaleName[0] = 0;
  if ( a6 != *(_QWORD *)(*(_QWORD *)v11 + 1056LL) )
  {
    if ( !Js::JavascriptString::Is(a6) )
      return v14;
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 704LL))(v13);
  }
  if ( a7 == *(_QWORD *)(*(_QWORD *)v11 + 1056LL) )
  {
    FlagsForSensitivity = 0x8000000;
  }
  else
  {
    if ( !Js::JavascriptString::Is(a7) )
      return v14;
    v17 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 704LL))(v16);
    FlagsForSensitivity = Js::getFlagsForSensitivity(v17, v18);
  }
  v20 = *(_QWORD *)(*(_QWORD *)v11 + 1056LL);
  if ( a8 != v20 )
  {
    if ( (unsigned int)Js::JavascriptOperators::GetTypeId(a8) != 2 )
      return v20;
    if ( *(_BYTE *)(v21 + 16) )
      FlagsForSensitivity |= 4u;
  }
  if ( a9 != v20 )
  {
    if ( (unsigned int)Js::JavascriptOperators::GetTypeId(a9) != 2 )
      return v20;
    if ( *(_BYTE *)(v22 + 16) )
      FlagsForSensitivity |= 8u;
  }
  if ( !v12 && !GetUserDefaultLocaleName(LocaleName, 85) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Js::JavascriptError::MapAndThrowError(v11, LastError);
  }
  cchCount2 = a5[4];
  lpString2 = (const WCHAR *)(*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a5 + 704LL))(a5);
  v26 = a4[4];
  v27 = (const WCHAR *)(*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a4 + 704LL))(a4);
  v28 = LocaleName;
  if ( v12 )
    v28 = (WCHAR *)v12;
  v29 = CompareStringEx(v28, FlagsForSensitivity, v27, v26, lpString2, cchCount2, 0, 0, 0);
  if ( !v29 )
  {
    v30 = GetLastError();
    if ( v30 > 0 )
      v30 = (unsigned __int16)v30 | 0x80070000;
    Js::JavascriptError::MapAndThrowError(v11, v30);
  }
  return (unsigned int)(v29 - 2) | 0x1000000000000LL;
}

```

## disassembly

```asm
0x1801ab0d0  mov     r11, rsp
0x1801ab0d3  mov     [r11+10h], rdx
0x1801ab0d7  mov     [r11+8], rcx
0x1801ab0db  mov     [r11+18h], r8
0x1801ab0df  mov     [r11+20h], r9
0x1801ab0e3  push    rbx
0x1801ab0e4  push    rbp
0x1801ab0e5  push    rsi
0x1801ab0e6  push    rdi
0x1801ab0e7  push    r12
0x1801ab0e9  push    r14
0x1801ab0eb  push    r15
0x1801ab0ed  sub     rsp, 120h
0x1801ab0f4  mov     rax, cs:__security_cookie
0x1801ab0fb  xor     rax, rsp
0x1801ab0fe  mov     [rsp+158h+var_48], rax
0x1801ab106  mov     rbx, [r11+8]
0x1801ab10a  xor     r9d, r9d; void *
0x1801ab10d  mov     edx, 450h; unsigned __int64
0x1801ab112  mov     rax, [rbx+8]
0x1801ab116  mov     rcx, [rax+8]
0x1801ab11a  mov     rcx, [rcx+430h]
0x1801ab121  mov     r8, rcx; struct Js::ScriptContext *
0x1801ab124  mov     rcx, [rcx+4A0h]; this
0x1801ab12b  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x1801ab130  mov     rax, [rbx+8]
0x1801ab134  lea     rdi, [rsp+158h+arg_10]
0x1801ab13c  mov     edx, [rsp+158h+arg_8]
0x1801ab143  and     edx, 0FFFFFFh
0x1801ab149  mov     [rsp+158h+var_108], 0
0x1801ab152  mov     rcx, [rax+8]
0x1801ab156  mov     r14, [rcx+430h]
0x1801ab15d  cmp     edx, 7
0x1801ab160  jb      loc_1801AB356
0x1801ab166  mov     r12, [rdi+8]
0x1801ab16a  mov     rcx, r12; void *
0x1801ab16d  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801ab172  test    al, al
0x1801ab174  jz      loc_1801AB356
0x1801ab17a  mov     rbx, [rdi+10h]
0x1801ab17e  mov     rcx, rbx; void *
0x1801ab181  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801ab186  test    al, al
0x1801ab188  jz      loc_1801AB356
0x1801ab18e  xor     eax, eax
0x1801ab190  xor     r15d, r15d
0x1801ab193  mov     [rsp+158h+LocaleName], ax
0x1801ab198  mov     rax, [r14]
0x1801ab19b  mov     rdx, [rdi+18h]
0x1801ab19f  mov     r8, [rax+420h]
0x1801ab1a6  cmp     rdx, r8
0x1801ab1a9  jz      short loc_1801AB1D4
0x1801ab1ab  mov     rcx, rdx; void *
0x1801ab1ae  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801ab1b3  test    al, al
0x1801ab1b5  jnz     short loc_1801AB1BF
0x1801ab1b7  mov     rax, r8
0x1801ab1ba  jmp     loc_1801AB360
0x1801ab1bf  mov     rax, [rdx]
0x1801ab1c2  mov     rcx, rdx
0x1801ab1c5  mov     rax, [rax+2C0h]
0x1801ab1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab1d1  mov     r15, rax
0x1801ab1d4  mov     rcx, [r14]
0x1801ab1d7  mov     rdx, [rdi+20h]
0x1801ab1db  mov     r8, [rcx+420h]
0x1801ab1e2  cmp     rdx, r8
0x1801ab1e5  jz      short loc_1801AB211
0x1801ab1e7  mov     rcx, rdx; void *
0x1801ab1ea  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801ab1ef  test    al, al
0x1801ab1f1  jz      short loc_1801AB1B7
0x1801ab1f3  mov     rax, [rdx]
0x1801ab1f6  mov     rcx, rdx
0x1801ab1f9  mov     rax, [rax+2C0h]
0x1801ab200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab205  mov     rcx, rax; this
0x1801ab208  call    ?getFlagsForSensitivity@Js@@YAKPEBG@Z; Js::getFlagsForSensitivity(ushort const *)
0x1801ab20d  mov     ebp, eax
0x1801ab20f  jmp     short loc_1801AB216
0x1801ab211  mov     ebp, 8000000h
0x1801ab216  mov     rax, [r14]
0x1801ab219  mov     r8, [rdi+28h]
0x1801ab21d  mov     rdx, [rax+420h]
0x1801ab224  cmp     r8, rdx
0x1801ab227  jz      short loc_1801AB240
0x1801ab229  mov     rcx, r8
0x1801ab22c  call    ?GetTypeId@JavascriptOperators@Js@@SA?AW4TypeId@2@PEAX@Z; Js::JavascriptOperators::GetTypeId(void *)
0x1801ab231  cmp     eax, 2
0x1801ab234  jnz     short loc_1801AB256
0x1801ab236  cmp     byte ptr [r8+10h], 0
0x1801ab23b  jz      short loc_1801AB240
0x1801ab23d  or      ebp, 4
0x1801ab240  mov     r8, [rdi+30h]
0x1801ab244  cmp     r8, rdx
0x1801ab247  jz      short loc_1801AB268
0x1801ab249  mov     rcx, r8
0x1801ab24c  call    ?GetTypeId@JavascriptOperators@Js@@SA?AW4TypeId@2@PEAX@Z; Js::JavascriptOperators::GetTypeId(void *)
0x1801ab251  cmp     eax, 2
0x1801ab254  jz      short loc_1801AB25E
0x1801ab256  mov     rax, rdx
0x1801ab259  jmp     loc_1801AB360
0x1801ab25e  cmp     byte ptr [r8+10h], 0
0x1801ab263  jz      short loc_1801AB268
0x1801ab265  or      ebp, 8
0x1801ab268  test    r15, r15
0x1801ab26b  jnz     short loc_1801AB2A9
0x1801ab26d  lea     edx, [r15+55h]; cchLocaleName
0x1801ab271  lea     rcx, [rsp+158h+LocaleName]; lpLocaleName
0x1801ab276  call    cs:__imp_GetUserDefaultLocaleName
0x1801ab27d  nop     dword ptr [rax+rax+00h]
0x1801ab282  test    eax, eax
0x1801ab284  jnz     short loc_1801AB2A9
0x1801ab286  call    cs:__imp_GetLastError
0x1801ab28d  nop     dword ptr [rax+rax+00h]
0x1801ab292  test    eax, eax
0x1801ab294  jle     short loc_1801AB29E
0x1801ab296  movzx   eax, ax
0x1801ab299  or      eax, 80070000h
0x1801ab29e  mov     edx, eax; int
0x1801ab2a0  mov     rcx, r14; struct Js::ScriptContext *
0x1801ab2a3  call    ?MapAndThrowError@JavascriptError@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptError::MapAndThrowError(Js::ScriptContext *,long)
0x1801ab2a9  mov     rax, [rbx]
0x1801ab2ac  mov     rcx, rbx
0x1801ab2af  mov     esi, [rbx+10h]
0x1801ab2b2  mov     rax, [rax+2C0h]
0x1801ab2b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab2be  mov     rdx, [r12]
0x1801ab2c2  mov     rbx, rax
0x1801ab2c5  mov     edi, [r12+10h]
0x1801ab2ca  mov     rcx, r12
0x1801ab2cd  mov     rax, [rdx+2C0h]
0x1801ab2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab2d9  mov     [rsp+158h+lParam], 0; lParam
0x1801ab2e2  lea     rcx, [rsp+158h+LocaleName]
0x1801ab2e7  mov     [rsp+158h+lpReserved], 0; lpReserved
0x1801ab2f0  test    r15, r15
0x1801ab2f3  mov     [rsp+158h+lpVersionInformation], 0; lpVersionInformation
0x1801ab2fc  mov     r9d, edi; cchCount1
0x1801ab2ff  cmovnz  rcx, r15; lpLocaleName
0x1801ab303  mov     [rsp+158h+cchCount2], esi; cchCount2
0x1801ab307  mov     r8, rax; lpString1
0x1801ab30a  mov     [rsp+158h+lpString2], rbx; lpString2
0x1801ab30f  mov     edx, ebp; dwCmpFlags
0x1801ab311  call    cs:__imp_CompareStringEx
0x1801ab318  nop     dword ptr [rax+rax+00h]
0x1801ab31d  test    eax, eax
0x1801ab31f  jz      short loc_1801AB333
0x1801ab321  add     eax, 0FFFFFFFEh
0x1801ab324  mov     rcx, 1000000000000h
0x1801ab32e  or      rax, rcx
0x1801ab331  jmp     short loc_1801AB360
0x1801ab333  call    cs:__imp_GetLastError
0x1801ab33a  nop     dword ptr [rax+rax+00h]
0x1801ab33f  test    eax, eax
0x1801ab341  jle     short loc_1801AB34B
0x1801ab343  movzx   eax, ax
0x1801ab346  or      eax, 80070000h
0x1801ab34b  mov     edx, eax; int
0x1801ab34d  mov     rcx, r14; struct Js::ScriptContext *
0x1801ab350  call    ?MapAndThrowError@JavascriptError@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptError::MapAndThrowError(Js::ScriptContext *,long)
0x1801ab356  mov     rax, [r14]
0x1801ab359  mov     rax, [rax+420h]
0x1801ab360  mov     rcx, [rsp+158h+var_48]
0x1801ab368  xor     rcx, rsp; StackCookie
0x1801ab36b  call    __security_check_cookie
0x1801ab370  add     rsp, 120h
0x1801ab377  pop     r15
0x1801ab379  pop     r14
0x1801ab37b  pop     r12
0x1801ab37d  pop     rdi
0x1801ab37e  pop     rsi
0x1801ab37f  pop     rbp
0x1801ab380  pop     rbx
0x1801ab381  retn
```
