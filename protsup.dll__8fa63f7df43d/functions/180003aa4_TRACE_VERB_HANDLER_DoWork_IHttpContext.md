# TRACE_VERB_HANDLER::DoWork(IHttpContext *)

- ea: `0x180003aa4`
- end: `0x180003e6b`
- name: `?DoWork@TRACE_VERB_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180001290`

## callees

- `0x180002760`
- `0x180003a5c`
- `0x180003aa4`
- `0x180003e74`
- `0x180005010`

## import_xrefs

- `msvcrt!_itoa_s` at `0x180003bd2`
- `msvcrt!_itoa_s` at `0x180003bed`
- `msvcrt!_itoa_s` at `0x180003bd2`
- `msvcrt!_itoa_s` at `0x180003bed`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003d71`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003d71`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003c0d`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003c0d`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003d7f`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003d7f`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003c27`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003c5d`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003c75`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003c8f`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003ca7`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003cc1`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003d2b`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003c27`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003c5d`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003c75`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003c8f`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003ca7`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003cc1`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003d2b`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180003c43`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180003d11`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180003c43`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180003d11`

## pseudocode

```c
__int64 __fastcall TRACE_VERB_HANDLER::DoWork(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // r15
  int v6; // ebx
  __int64 v7; // rax
  struct IHttpTraceContext *v8; // rax
  const struct _GUID *v9; // rdx
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // rbp
  STRA *v13; // rdi
  const char *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int v18; // [rsp+40h] [rbp-78h] BYREF
  const char *v19; // [rsp+48h] [rbp-70h] BYREF
  __int128 v20; // [rsp+50h] [rbp-68h] BYREF
  __int128 v21; // [rsp+60h] [rbp-58h]
  char Buffer[8]; // [rsp+70h] [rbp-48h] BYREF
  char v23[8]; // [rsp+78h] [rbp-40h] BYREF

  v4 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 32))(a2);
  v5 = v4;
  if ( TRACE_VERB_HANDLER::s_fTraceEnabled )
  {
    v6 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 272))(a2);
    if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v7) )
    {
      v8 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64 *))(*a2 + 272))(a2);
      v6 = IISGeneralEvents::GENERAL_TRACE_HANDLER::RaiseEvent(v8, v9);
    }
    v10 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 24))(a2);
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    v12 = v11;
    if ( *(_WORD *)(v11 + 816) || (*(_BYTE *)v11 & 1) != 0 )
    {
      *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5) + 536) = 0;
      (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v5 + 24LL))(
        v5,
        400,
        "Bad Request",
        0,
        0,
        0,
        0);
    }
    else
    {
      _itoa_s(*(unsigned __int16 *)(v11 + 32), Buffer, 6u, 10);
      _itoa_s(*(unsigned __int16 *)(v12 + 34), v23, 6u, 10);
      v13 = (STRA *)(a1 + 8);
      v14 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 64LL))(v10);
      v6 = STRA::Copy(v13, v14);
      if ( v6 < 0 )
        goto LABEL_21;
      v6 = STRA::Append(v13, " ");
      if ( v6 < 0 )
        goto LABEL_21;
      v6 = STRA::Append(v13, *(const char **)(v12 + 56), *(unsigned __int16 *)(v12 + 42));
      if ( v6 < 0 )
        goto LABEL_21;
      v6 = STRA::Append(v13, " HTTP/");
      if ( v6 < 0 )
        goto LABEL_21;
      v6 = STRA::Append(v13, Buffer);
      if ( v6 < 0 )
        goto LABEL_21;
      v6 = STRA::Append(v13, ".");
      if ( v6 < 0 )
        goto LABEL_21;
      v6 = STRA::Append(v13, v23);
      if ( v6 < 0 )
        goto LABEL_21;
      v6 = STRA::Append(v13, "\r\n");
      if ( v6 < 0 )
        goto LABEL_21;
      v15 = *a2;
      v19 = 0;
      v18 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64 *, const char *, const char **, unsigned int *))(v15 + 120))(
             a2,
             "ALL_RAW",
             &v19,
             &v18);
      if ( v6 < 0 )
        goto LABEL_21;
      v6 = STRA::Append(v13, v19, v18);
      if ( v6 < 0 )
        goto LABEL_21;
      v6 = STRA::Append(v13, "\r\n");
      if ( v6 < 0 )
        goto LABEL_21;
      v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
      *(_QWORD *)(v16 + 256) = "message/http";
      *(_WORD *)(v16 + 248) = 12;
      v20 = 0;
      v21 = 0;
      *((_QWORD *)&v20 + 1) = STRA::QueryStr(v13);
      LODWORD(v21) = STRA::QueryCCH(v13);
      v6 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v5 + 160LL))(v5, &v20, 0xFFFFFFFFLL);
    }
    if ( v6 >= 0 )
      return 2;
LABEL_21:
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5) + 536) = 0;
    (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v5 + 24LL))(
      v5,
      500,
      "Internal Server Error",
      0,
      v6,
      0,
      0);
    return 2;
  }
  *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4) + 536) = 0;
  (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v5 + 24LL))(
    v5,
    501,
    "Not Implemented",
    0,
    0,
    0,
    0);
  return 2;
}

```

## disassembly

```asm
0x180003aa4  push    rsi
0x180003aa6  push    rdi
0x180003aa7  push    r14
0x180003aa9  push    r15
0x180003aab  sub     rsp, 98h
0x180003ab2  mov     rax, cs:__security_cookie
0x180003ab9  xor     rax, rsp
0x180003abc  mov     [rsp+0B8h+var_38], rax
0x180003ac4  mov     rax, [rdx]
0x180003ac7  mov     rdi, rcx
0x180003aca  mov     rcx, rdx
0x180003acd  mov     r14, rdx
0x180003ad0  mov     rax, [rax+20h]
0x180003ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ad9  cmp     cs:?s_fTraceEnabled@TRACE_VERB_HANDLER@@0HA, 0; int TRACE_VERB_HANDLER::s_fTraceEnabled
0x180003ae0  mov     r15, rax
0x180003ae3  jnz     short loc_180003B2D
0x180003ae5  mov     rcx, [rax]
0x180003ae8  mov     rax, [rcx+8]
0x180003aec  mov     rcx, r15
0x180003aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003af4  xor     esi, esi
0x180003af6  lea     r8, aNotImplemented; "Not Implemented"
0x180003afd  mov     [rsp+0B8h+var_88], esi
0x180003b01  xor     r9d, r9d
0x180003b04  mov     edx, 1F5h
0x180003b09  mov     [rsp+0B8h+var_90], rsi
0x180003b0e  mov     [rax+218h], si
0x180003b15  mov     rcx, [r15]
0x180003b18  mov     [rsp+0B8h+var_98], esi
0x180003b1c  mov     rax, [rcx+18h]
0x180003b20  mov     rcx, r15
0x180003b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b28  jmp     loc_180003E48
0x180003b2d  mov     rax, [r14]
0x180003b30  xor     esi, esi
0x180003b32  mov     [rsp+0B8h+arg_10], rbx
0x180003b3a  mov     rcx, r14
0x180003b3d  mov     [rsp+0B8h+arg_18], rbp
0x180003b45  mov     ebx, esi
0x180003b47  mov     [rsp+0B8h+var_28], r12
0x180003b4f  mov     rax, [rax+110h]
0x180003b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b5b  mov     rcx, rax
0x180003b5e  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180003b63  test    eax, eax
0x180003b65  jz      short loc_180003B83
0x180003b67  mov     rax, [r14]
0x180003b6a  mov     rcx, r14
0x180003b6d  mov     rax, [rax+110h]
0x180003b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b79  mov     rcx, rax; struct IHttpTraceContext *
0x180003b7c  call    ?RaiseEvent@GENERAL_TRACE_HANDLER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISGeneralEvents::GENERAL_TRACE_HANDLER::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x180003b81  mov     ebx, eax
0x180003b83  mov     rcx, [r14]
0x180003b86  mov     rax, [rcx+18h]
0x180003b8a  mov     rcx, r14
0x180003b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b92  mov     r12, rax
0x180003b95  mov     rcx, [rax]
0x180003b98  mov     rax, [rcx+8]
0x180003b9c  mov     rcx, r12
0x180003b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ba4  mov     rbp, rax
0x180003ba7  cmp     [rax+330h], si
0x180003bae  jnz     loc_180003DAA
0x180003bb4  test    byte ptr [rax], 1
0x180003bb7  jnz     loc_180003DAA
0x180003bbd  movzx   ecx, word ptr [rax+20h]; Value
0x180003bc1  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x180003bc6  mov     r9d, 0Ah; Radix
0x180003bcc  mov     r8d, 6; BufferCount
0x180003bd2  call    cs:__imp__itoa_s
0x180003bd8  movzx   ecx, word ptr [rbp+22h]; Value
0x180003bdc  lea     rdx, [rsp+0B8h+var_40]; Buffer
0x180003be1  mov     r9d, 0Ah; Radix
0x180003be7  mov     r8d, 6; BufferCount
0x180003bed  call    cs:__imp__itoa_s
0x180003bf3  mov     rax, [r12]
0x180003bf7  mov     rcx, r12
0x180003bfa  add     rdi, 8
0x180003bfe  mov     rax, [rax+40h]
0x180003c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c07  mov     rdx, rax
0x180003c0a  mov     rcx, rdi
0x180003c0d  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180003c13  mov     ebx, eax
0x180003c15  test    eax, eax
0x180003c17  js      loc_180003DEF
0x180003c1d  lea     rdx, asc_18000703C; " "
0x180003c24  mov     rcx, rdi
0x180003c27  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180003c2d  mov     ebx, eax
0x180003c2f  test    eax, eax
0x180003c31  js      loc_180003DEF
0x180003c37  movzx   r8d, word ptr [rbp+2Ah]
0x180003c3c  mov     rcx, rdi
0x180003c3f  mov     rdx, [rbp+38h]
0x180003c43  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180003c49  mov     ebx, eax
0x180003c4b  test    eax, eax
0x180003c4d  js      loc_180003DEF
0x180003c53  lea     rdx, aHttp_0; " HTTP/"
0x180003c5a  mov     rcx, rdi
0x180003c5d  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180003c63  mov     ebx, eax
0x180003c65  test    eax, eax
0x180003c67  js      loc_180003DEF
0x180003c6d  lea     rdx, [rsp+0B8h+Buffer]
0x180003c72  mov     rcx, rdi
0x180003c75  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180003c7b  mov     ebx, eax
0x180003c7d  test    eax, eax
0x180003c7f  js      loc_180003DEF
0x180003c85  lea     rdx, asc_180007048; "."
0x180003c8c  mov     rcx, rdi
0x180003c8f  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180003c95  mov     ebx, eax
0x180003c97  test    eax, eax
0x180003c99  js      loc_180003DEF
0x180003c9f  lea     rdx, [rsp+0B8h+var_40]
0x180003ca4  mov     rcx, rdi
0x180003ca7  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180003cad  mov     ebx, eax
0x180003caf  test    eax, eax
0x180003cb1  js      loc_180003DEF
0x180003cb7  lea     rdx, asc_18000704C; "\r\n"
0x180003cbe  mov     rcx, rdi
0x180003cc1  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180003cc7  mov     ebx, eax
0x180003cc9  test    eax, eax
0x180003ccb  js      loc_180003DEF
0x180003cd1  mov     rax, [r14]
0x180003cd4  lea     r9, [rsp+0B8h+var_78]
0x180003cd9  lea     r8, [rsp+0B8h+var_70]
0x180003cde  mov     [rsp+0B8h+var_70], rsi
0x180003ce3  lea     rdx, aAllRaw; "ALL_RAW"
0x180003cea  mov     [rsp+0B8h+var_78], esi
0x180003cee  mov     rcx, r14
0x180003cf1  mov     rax, [rax+78h]
0x180003cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cfa  mov     ebx, eax
0x180003cfc  test    eax, eax
0x180003cfe  js      loc_180003DEF
0x180003d04  mov     r8d, [rsp+0B8h+var_78]
0x180003d09  mov     rcx, rdi
0x180003d0c  mov     rdx, [rsp+0B8h+var_70]
0x180003d11  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180003d17  mov     ebx, eax
0x180003d19  test    eax, eax
0x180003d1b  js      loc_180003DEF
0x180003d21  lea     rdx, asc_18000704C; "\r\n"
0x180003d28  mov     rcx, rdi
0x180003d2b  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180003d31  mov     ebx, eax
0x180003d33  test    eax, eax
0x180003d35  js      loc_180003DEF
0x180003d3b  mov     rax, [r15]
0x180003d3e  mov     rcx, r15
0x180003d41  mov     rax, [rax+8]
0x180003d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4a  xorps   xmm0, xmm0
0x180003d4d  lea     rcx, aMessageHttp; "message/http"
0x180003d54  mov     [rax+100h], rcx
0x180003d5b  mov     rcx, rdi
0x180003d5e  mov     word ptr [rax+0F8h], 0Ch
0x180003d67  movups  [rsp+0B8h+var_68], xmm0
0x180003d6c  movups  [rsp+0B8h+var_58], xmm0
0x180003d71  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003d77  mov     rcx, rdi
0x180003d7a  mov     qword ptr [rsp+0B8h+var_68+8], rax
0x180003d7f  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180003d85  mov     dword ptr [rsp+0B8h+var_58], eax
0x180003d89  mov     r8d, 0FFFFFFFFh
0x180003d8f  mov     rax, [r15]
0x180003d92  lea     rdx, [rsp+0B8h+var_68]
0x180003d97  mov     rcx, r15
0x180003d9a  mov     rax, [rax+0A0h]
0x180003da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da6  mov     ebx, eax
0x180003da8  jmp     short loc_180003DEB
0x180003daa  mov     rax, [r15]
0x180003dad  mov     rcx, r15
0x180003db0  mov     rax, [rax+8]
0x180003db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003db9  mov     [rsp+0B8h+var_88], esi
0x180003dbd  lea     r8, aBadRequest; "Bad Request"
0x180003dc4  xor     r9d, r9d
0x180003dc7  mov     [rsp+0B8h+var_90], rsi
0x180003dcc  mov     edx, 190h
0x180003dd1  mov     [rsp+0B8h+var_98], esi
0x180003dd5  mov     [rax+218h], si
0x180003ddc  mov     rcx, r15
0x180003ddf  mov     rax, [r15]
0x180003de2  mov     rax, [rax+18h]
0x180003de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003deb  test    ebx, ebx
0x180003ded  jns     short loc_180003E30
0x180003def  mov     rax, [r15]
0x180003df2  mov     rcx, r15
0x180003df5  mov     rax, [rax+8]
0x180003df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dfe  mov     [rsp+0B8h+var_88], esi
0x180003e02  lea     r8, aInternalServer; "Internal Server Error"
0x180003e09  xor     r9d, r9d
0x180003e0c  mov     [rsp+0B8h+var_90], rsi
0x180003e11  mov     edx, 1F4h
0x180003e16  mov     [rsp+0B8h+var_98], ebx
0x180003e1a  mov     [rax+218h], si
0x180003e21  mov     rcx, r15
0x180003e24  mov     rax, [r15]
0x180003e27  mov     rax, [rax+18h]
0x180003e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e30  mov     rbp, [rsp+0B8h+arg_18]
0x180003e38  mov     rbx, [rsp+0B8h+arg_10]
0x180003e40  mov     r12, [rsp+0B8h+var_28]
0x180003e48  mov     eax, 2
0x180003e4d  mov     rcx, [rsp+0B8h+var_38]
0x180003e55  xor     rcx, rsp; StackCookie
0x180003e58  call    __security_check_cookie
0x180003e5d  add     rsp, 98h
0x180003e64  pop     r15
0x180003e66  pop     r14
0x180003e68  pop     rdi
0x180003e69  pop     rsi
0x180003e6a  retn
```
