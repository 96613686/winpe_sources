# BinaryLogWriter_shared

- ea: `0x180028b00`
- end: `0x180028ea1`
- name: `BinaryLogWriter_shared`
- size: `929`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x1800286d0`
- `0x180028720`
- `0x180028eb0`
- `0x180028f80`

## callees

- `0x180006e64`
- `0x180006ef8`
- `0x180007c80`
- `0x18000ab88`
- `0x18000abb8`
- `0x180028b00`
- `0x180044842`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x180028cb4`
- `msvcrt!malloc` at `0x180028cb4`
- `msvcrt!_wcsdup` at `0x180028cf9`
- `msvcrt!_wcsdup` at `0x180028d69`
- `msvcrt!_wcsdup` at `0x180028cf9`
- `msvcrt!_wcsdup` at `0x180028d69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028b7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028bcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028c2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028dfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028b7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028bcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028c2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180028dfa`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180028cdb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180028cdb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180028c9f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180028ccd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180028c9f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180028ccd`

## string_xrefs

- `0x180028b70`: `mpunits.dll`
- `0x180028bc0`: `mpunits.dll`
- `0x180028c20`: `mpunits.dll`
- `0x180028dec`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall BinaryLogWriter_shared(
        void (__fastcall ***a1)(_QWORD, LPCWSTR *),
        const WCHAR *a2,
        const wchar_t *a3,
        wchar_t *a4,
        __int64 a5,
        int a6,
        void (__fastcall ***a7)(_QWORD, LPCWSTR *),
        int a8,
        __int64 a9)
{
  void (__fastcall ***v9)(_QWORD, LPCWSTR *); // rdi
  HMODULE ModuleHandleA; // rax
  __int64 String_LoadString; // rax
  int v15; // ecx
  HMODULE v16; // rax
  HMODULE v17; // rax
  unsigned int v18; // ebx
  __int64 v19; // rbx
  DWORD v20; // eax
  DWORD v21; // esi
  WCHAR *v22; // rax
  DWORD FileAttributesW; // eax
  void (__fastcall **v24)(_QWORD, LPCWSTR *); // rax
  void (__fastcall **v25)(_QWORD, LPCWSTR *); // rax
  wchar_t *v26; // rax
  _QWORD *v27; // rcx
  ULONGLONG v29; // rdx
  __int64 v30; // rbx
  HMODULE v31; // rax
  LPCWSTR lpSrc; // [rsp+30h] [rbp-48h] BYREF
  __int64 v33; // [rsp+38h] [rbp-40h] BYREF
  wchar_t *String; // [rsp+40h] [rbp-38h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-28h] BYREF

  v9 = a7;
  String = a4;
  lpSrc = a2;
  *(_QWORD *)&EventDescriptor.Id = a9;
  v33 = 0;
  if ( !a1 )
  {
    EventDescriptor.Keyword = 1;
    *(_DWORD *)&EventDescriptor.Id = 101;
    *(_DWORD *)&EventDescriptor.Level = 4;
    Etw_Trace0(&EventDescriptor);
    EventDescriptor = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    String_LoadString = Intlstr_GetString_LoadString(ModuleHandleA, 2005);
    v15 = 1;
    LOBYTE(EventDescriptor.Keyword) = 0;
LABEL_29:
    *(_QWORD *)&EventDescriptor.Id = String_LoadString;
    MI_ReportErrorDetails_ForCustomError(v15, (int)L"BinaryLogger", 0, 0);
    goto LABEL_30;
  }
  if ( !*a3 )
  {
    EventDescriptor.Keyword = 1;
    *(_DWORD *)&EventDescriptor.Id = 103;
    *(_DWORD *)&EventDescriptor.Level = 4;
    Etw_Trace0(&EventDescriptor);
    EventDescriptor = 0;
    v16 = GetModuleHandleA("mpunits.dll");
    String_LoadString = Intlstr_GetString_LoadString(v16, 2004);
    LOBYTE(EventDescriptor.Keyword) = 0;
    v15 = 3;
    goto LABEL_29;
  }
  if ( !a5 && !a6 )
  {
    EventDescriptor.Keyword = 1;
    *(_DWORD *)&EventDescriptor.Id = 104;
    *(_DWORD *)&EventDescriptor.Level = 4;
    Etw_Trace0(&EventDescriptor);
    EventDescriptor = 0;
    v17 = GetModuleHandleA("mpunits.dll");
    String_LoadString = Intlstr_GetString_LoadString(v17, 2006);
    LOBYTE(EventDescriptor.Keyword) = 0;
    v15 = 4;
    goto LABEL_29;
  }
  if ( !((unsigned int (__fastcall *)(__int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 *, __int64))s_observableFT[0])(
          BinaryLogWriter_OnSubscribe,
          BinaryLogWriter_OnDestroy,
          &v33,
          64) )
  {
    v19 = v33;
    memset_0((void *)(v33 + 40), 0, 0x40u);
    v20 = ExpandEnvironmentStringsW(a2, 0, 0);
    v21 = v20;
    if ( !v20 )
    {
LABEL_30:
      v18 = 4;
      goto LABEL_31;
    }
    v22 = (WCHAR *)malloc(2LL * v20);
    *(_QWORD *)(v19 + 48) = v22;
    if ( v22 )
    {
      if ( ExpandEnvironmentStringsW(lpSrc, v22, v21) == v21 )
      {
        FileAttributesW = GetFileAttributesW(*(LPCWSTR *)(v19 + 48));
        if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
        {
          v29 = *(_QWORD *)(v19 + 48);
          *(_DWORD *)&EventDescriptor.Id = 102;
          *(_DWORD *)&EventDescriptor.Level = 4;
          EventDescriptor.Keyword = 1;
          Etw_Trace1_LPCWSTR(&EventDescriptor, v29);
          v30 = *(_QWORD *)(v19 + 48);
          EventDescriptor = 0;
          v31 = GetModuleHandleA("mpunits.dll");
          String_LoadString = Intlstr_FormatString_FormatMessage(v31, 2003, v30);
          v15 = 2;
          LOBYTE(EventDescriptor.Keyword) = 1;
          goto LABEL_29;
        }
        *(_QWORD *)(v19 + 40) = a1;
        *(_QWORD *)(v19 + 56) = _wcsdup(a3);
        if ( a7 )
        {
          v24 = *a7;
          lpSrc = 0;
          if ( v24 )
            (*v24)(a7, &lpSrc);
        }
        else
        {
          v9 = 0;
        }
        *(_QWORD *)(v19 + 96) = v9;
        v25 = *a1;
        lpSrc = 0;
        if ( v25 )
          (*v25)(a1, &lpSrc);
        if ( *(_QWORD *)(v19 + 48) && *(_QWORD *)(v19 + 56) )
        {
          if ( String )
          {
            v26 = _wcsdup(String);
            *(_QWORD *)(v19 + 64) = v26;
            if ( !v26 )
              goto LABEL_9;
          }
          else
          {
            *(_QWORD *)(v19 + 64) = 0;
          }
          v27 = *(_QWORD **)&EventDescriptor.Id;
          *(_QWORD *)(v19 + 72) = a5;
          *(_DWORD *)(v19 + 80) = a6;
          *(_DWORD *)(v19 + 84) = a8;
          *v27 = v33;
          *(_DWORD *)&EventDescriptor.Id = 106;
          *(_DWORD *)&EventDescriptor.Level = 4;
          EventDescriptor.Keyword = 1;
          Etw_Trace0(&EventDescriptor);
          return 0;
        }
      }
    }
  }
LABEL_9:
  v18 = 27;
LABEL_31:
  *(_DWORD *)&EventDescriptor.Id = 105;
  *(_DWORD *)&EventDescriptor.Level = 4;
  EventDescriptor.Keyword = 1;
  Etw_Trace0(&EventDescriptor);
  if ( v33 )
  {
    if ( *(_QWORD *)v33 )
      (*(void (**)(void))(*(_QWORD *)v33 + 16LL))();
  }
  return v18;
}

```

## disassembly

```asm
0x180028b00  push    rbp
0x180028b02  push    rbx
0x180028b03  push    rsi
0x180028b04  push    rdi
0x180028b05  push    r12
0x180028b07  push    r13
0x180028b09  push    r14
0x180028b0b  push    r15
0x180028b0d  mov     rbp, rsp
0x180028b10  sub     rsp, 78h
0x180028b14  mov     rax, cs:__security_cookie
0x180028b1b  xor     rax, rsp
0x180028b1e  mov     [rbp+var_18], rax
0x180028b22  mov     rax, [rbp+arg_40]
0x180028b29  xor     ebx, ebx
0x180028b2b  mov     rdi, [rbp+arg_30]
0x180028b2f  mov     r14, rcx
0x180028b32  mov     [rbp+String], r9
0x180028b36  mov     r15, r8
0x180028b39  mov     [rbp+lpSrc], rdx
0x180028b3d  mov     rsi, rdx
0x180028b40  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x180028b44  lea     ecx, [rbx+1]
0x180028b47  mov     [rbp+var_40], rbx
0x180028b4b  test    r14, r14
0x180028b4e  jnz     short loc_180028B9A
0x180028b50  mov     [rbp+EventDescriptor.Keyword], rcx
0x180028b54  xor     esi, esi
0x180028b56  lea     rcx, [rbp+EventDescriptor]
0x180028b5a  mov     dword ptr [rbp+EventDescriptor.Id], 65h ; 'e'
0x180028b61  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x180028b68  call    Etw_Trace0
0x180028b6d  xorps   xmm0, xmm0
0x180028b70  lea     rcx, ModuleName; "mpunits.dll"
0x180028b77  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x180028b7b  call    cs:__imp_GetModuleHandleA
0x180028b81  mov     rcx, rax
0x180028b84  mov     edx, 7D5h
0x180028b89  call    _Intlstr_GetString_LoadString
0x180028b8e  lea     ecx, [rbx+1]
0x180028b91  mov     byte ptr [rbp+EventDescriptor.Keyword], sil
0x180028b95  jmp     loc_180028E17
0x180028b9a  cmp     [r8], bx
0x180028b9e  jnz     short loc_180028BEE
0x180028ba0  mov     [rbp+EventDescriptor.Keyword], rcx
0x180028ba4  xor     esi, esi
0x180028ba6  lea     rcx, [rbp+EventDescriptor]
0x180028baa  mov     dword ptr [rbp+EventDescriptor.Id], 67h ; 'g'
0x180028bb1  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x180028bb8  call    Etw_Trace0
0x180028bbd  xorps   xmm0, xmm0
0x180028bc0  lea     rcx, ModuleName; "mpunits.dll"
0x180028bc7  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x180028bcb  call    cs:__imp_GetModuleHandleA
0x180028bd1  mov     rcx, rax
0x180028bd4  mov     edx, 7D4h
0x180028bd9  call    _Intlstr_GetString_LoadString
0x180028bde  lea     r8d, [rsi+5]
0x180028be2  mov     byte ptr [rbp+EventDescriptor.Keyword], sil
0x180028be6  lea     ecx, [rsi+3]
0x180028be9  jmp     loc_180028E1D
0x180028bee  mov     r13, [rbp+arg_20]
0x180028bf2  mov     r12d, [rbp+arg_28]
0x180028bf6  test    r13, r13
0x180028bf9  jnz     short loc_180028C4F
0x180028bfb  test    r12d, r12d
0x180028bfe  jnz     short loc_180028C4F
0x180028c00  mov     [rbp+EventDescriptor.Keyword], rcx
0x180028c04  xor     esi, esi
0x180028c06  lea     rcx, [rbp+EventDescriptor]
0x180028c0a  mov     dword ptr [rbp+EventDescriptor.Id], 68h ; 'h'
0x180028c11  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x180028c18  call    Etw_Trace0
0x180028c1d  xorps   xmm0, xmm0
0x180028c20  lea     rcx, ModuleName; "mpunits.dll"
0x180028c27  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x180028c2b  call    cs:__imp_GetModuleHandleA
0x180028c31  mov     rcx, rax
0x180028c34  mov     edx, 7D6h
0x180028c39  call    _Intlstr_GetString_LoadString
0x180028c3e  lea     r8d, [r12+5]
0x180028c43  mov     byte ptr [rbp+EventDescriptor.Keyword], sil
0x180028c47  lea     ecx, [rsi+4]
0x180028c4a  jmp     loc_180028E1D
0x180028c4f  mov     rax, cs:off_180047B90
0x180028c56  lea     r8, [rbp+var_40]
0x180028c5a  mov     r9d, 40h ; '@'
0x180028c60  lea     rdx, BinaryLogWriter_OnDestroy
0x180028c67  lea     rcx, BinaryLogWriter_OnSubscribe
0x180028c6e  mov     rax, [rax]
0x180028c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c76  test    eax, eax
0x180028c78  jz      short loc_180028C84
0x180028c7a  mov     ebx, 1Bh
0x180028c7f  jmp     loc_180028E49
0x180028c84  mov     rbx, [rbp+var_40]
0x180028c88  xor     edx, edx; Val
0x180028c8a  lea     r8d, [rdx+40h]; Size
0x180028c8e  lea     rcx, [rbx+28h]; void *
0x180028c92  call    memset_0
0x180028c97  xor     r8d, r8d; nSize
0x180028c9a  xor     edx, edx; lpDst
0x180028c9c  mov     rcx, rsi; lpSrc
0x180028c9f  call    cs:__imp_ExpandEnvironmentStringsW
0x180028ca5  mov     esi, eax
0x180028ca7  test    eax, eax
0x180028ca9  jz      loc_180028E44
0x180028caf  mov     ecx, esi
0x180028cb1  add     rcx, rcx; Size
0x180028cb4  call    cs:__imp_malloc
0x180028cba  mov     [rbx+30h], rax
0x180028cbe  test    rax, rax
0x180028cc1  jz      short loc_180028C7A
0x180028cc3  mov     rcx, [rbp+lpSrc]; lpSrc
0x180028cc7  mov     r8d, esi; nSize
0x180028cca  mov     rdx, rax; lpDst
0x180028ccd  call    cs:__imp_ExpandEnvironmentStringsW
0x180028cd3  cmp     eax, esi
0x180028cd5  jnz     short loc_180028C7A
0x180028cd7  mov     rcx, [rbx+30h]; lpFileName
0x180028cdb  call    cs:__imp_GetFileAttributesW
0x180028ce1  cmp     eax, 0FFFFFFFFh
0x180028ce4  jz      loc_180028DC3
0x180028cea  test    al, 10h
0x180028cec  jz      loc_180028DC3
0x180028cf2  mov     rcx, r15; String
0x180028cf5  mov     [rbx+28h], r14
0x180028cf9  call    cs:__imp__wcsdup
0x180028cff  xor     esi, esi
0x180028d01  mov     [rbx+38h], rax
0x180028d05  test    rdi, rdi
0x180028d08  jz      short loc_180028D27
0x180028d0a  mov     rax, [rdi]
0x180028d0d  mov     [rbp+lpSrc], rsi
0x180028d11  test    rax, rax
0x180028d14  jz      short loc_180028D2A
0x180028d16  mov     rax, [rax]
0x180028d19  lea     rdx, [rbp+lpSrc]
0x180028d1d  mov     rcx, rdi
0x180028d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d25  jmp     short loc_180028D2A
0x180028d27  mov     rdi, rsi
0x180028d2a  mov     [rbx+60h], rdi
0x180028d2e  mov     rax, [r14]
0x180028d31  mov     [rbp+lpSrc], rsi
0x180028d35  test    rax, rax
0x180028d38  jz      short loc_180028D49
0x180028d3a  mov     rax, [rax]
0x180028d3d  lea     rdx, [rbp+lpSrc]
0x180028d41  mov     rcx, r14
0x180028d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d49  cmp     [rbx+30h], rsi
0x180028d4d  jz      loc_180028C7A
0x180028d53  cmp     [rbx+38h], rsi
0x180028d57  jz      loc_180028C7A
0x180028d5d  mov     rax, [rbp+String]
0x180028d61  test    rax, rax
0x180028d64  jz      short loc_180028D7D
0x180028d66  mov     rcx, rax; String
0x180028d69  call    cs:__imp__wcsdup
0x180028d6f  mov     [rbx+40h], rax
0x180028d73  test    rax, rax
0x180028d76  jnz     short loc_180028D81
0x180028d78  jmp     loc_180028C7A
0x180028d7d  mov     [rbx+40h], rsi
0x180028d81  mov     rcx, qword ptr [rbp+EventDescriptor.Id]
0x180028d85  mov     eax, [rbp+arg_38]
0x180028d8b  mov     [rbx+48h], r13
0x180028d8f  mov     [rbx+50h], r12d
0x180028d93  mov     [rbx+54h], eax
0x180028d96  mov     rax, [rbp+var_40]
0x180028d9a  mov     [rcx], rax
0x180028d9d  lea     rcx, [rbp+EventDescriptor]
0x180028da1  mov     dword ptr [rbp+EventDescriptor.Id], 6Ah ; 'j'
0x180028da8  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x180028daf  mov     [rbp+EventDescriptor.Keyword], 1
0x180028db7  call    Etw_Trace0
0x180028dbc  xor     eax, eax
0x180028dbe  jmp     loc_180028E84
0x180028dc3  mov     rdx, [rbx+30h]
0x180028dc7  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x180028dcb  mov     dword ptr [rbp+EventDescriptor.Id], 66h ; 'f'
0x180028dd2  xor     esi, esi
0x180028dd4  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x180028ddb  mov     [rbp+EventDescriptor.Keyword], 1
0x180028de3  call    Etw_Trace1_LPCWSTR
0x180028de8  mov     rbx, [rbx+30h]
0x180028dec  lea     rcx, ModuleName; "mpunits.dll"
0x180028df3  xorps   xmm0, xmm0
0x180028df6  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x180028dfa  call    cs:__imp_GetModuleHandleA
0x180028e00  mov     r8, rbx
0x180028e03  mov     edx, 7D3h
0x180028e08  mov     rcx, rax
0x180028e0b  call    _Intlstr_FormatString_FormatMessage
0x180028e10  lea     ecx, [rsi+2]; int
0x180028e13  mov     byte ptr [rbp+EventDescriptor.Keyword], 1
0x180028e17  mov     r8d, 15h
0x180028e1d  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x180028e21  lea     r9, [rbp+EventDescriptor]
0x180028e25  movaps  xmm0, xmmword ptr [rbp+EventDescriptor.Id]
0x180028e29  lea     rdx, aBinarylogger; "BinaryLogger"
0x180028e30  mov     [rsp+78h+var_50], rsi; __int64
0x180028e35  movdqa  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x180028e3a  mov     [rsp+78h+var_58], rsi; __int64
0x180028e3f  call    MI_ReportErrorDetails_ForCustomError
0x180028e44  mov     ebx, 4
0x180028e49  lea     rcx, [rbp+EventDescriptor]
0x180028e4d  mov     dword ptr [rbp+EventDescriptor.Id], 69h ; 'i'
0x180028e54  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x180028e5b  mov     [rbp+EventDescriptor.Keyword], 1
0x180028e63  call    Etw_Trace0
0x180028e68  mov     rcx, [rbp+var_40]
0x180028e6c  test    rcx, rcx
0x180028e6f  jz      short loc_180028E82
0x180028e71  mov     rax, [rcx]
0x180028e74  test    rax, rax
0x180028e77  jz      short loc_180028E82
0x180028e79  mov     rax, [rax+10h]
0x180028e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e82  mov     eax, ebx
0x180028e84  mov     rcx, [rbp+var_18]
0x180028e88  xor     rcx, rsp; StackCookie
0x180028e8b  call    __security_check_cookie
0x180028e90  add     rsp, 78h
0x180028e94  pop     r15
0x180028e96  pop     r14
0x180028e98  pop     r13
0x180028e9a  pop     r12
0x180028e9c  pop     rdi
0x180028e9d  pop     rsi
0x180028e9e  pop     rbx
0x180028e9f  pop     rbp
0x180028ea0  retn
```
