# MakePathUNC(ushort const *,ushort const *)

- ea: `0x1800887c0`
- end: `0x180088b5a`
- name: `?MakePathUNC@@YAPEAGPEBG0@Z`
- size: `922`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18009f4d4`

## callees

- `0x18002c690`
- `0x18003d8d0`
- `0x180049c90`
- `0x1800746c8`
- `0x180075ec0`
- `0x18007d320`
- `0x1800887c0`
- `0x180088b60`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008892f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008892f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088960`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800889d6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800889d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800888ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800888ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008897d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008897d`

## string_xrefs

- `0x18008881e`: `MakePathUNC: Entering with <%s>`
- `0x180088852`: `MakePathUNC: Entering with <%s>`
- `0x180088af6`: `MakePathUNC: lpFile is NULL, setting lpResult to a null string`
- `0x180088b19`: `MakePathUNC: lpFile is NULL, setting lpResult to a null string`
- `0x180088935`: `MakePathUNC: ExpandEnvironmentString failed with error %d, setting szSysRoot to %%systemroot%% `
- `0x180088966`: `MakePathUNC: ExpandEnvironmentString failed with error %d, setting szSysRoot to %%systemroot%% `
- `0x180088a1d`: `MakePathUNC: Input path %s is not an absolute path`
- `0x180088a45`: `MakePathUNC: Input path %s is not an absolute path`
- `0x180088aaa`: `MakePathUNC: Returning a UNCPath of %s`
- `0x180088ad0`: `MakePathUNC: Returning a UNCPath of %s`

## pseudocode

```c
unsigned __int16 *__fastcall MakePathUNC(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  const WCHAR *v4; // r8
  const WCHAR *v5; // r8
  __int64 v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r15
  unsigned __int64 v10; // r14
  unsigned __int16 *v11; // rbx
  const unsigned __int16 *v13; // rcx
  unsigned int v14; // r8d
  void (*v15)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD LastError; // eax
  DWORD v17; // eax
  __int64 cchCount2; // rbp
  unsigned __int16 *v19; // r15
  const unsigned __int16 *v20; // r8
  unsigned int v21[4]; // [rsp+30h] [rbp-268h] BYREF
  WCHAR String1[264]; // [rsp+40h] [rbp-258h] BYREF

  v21[0] = 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      v4 = a1;
      if ( !a1 )
        v4 = L"NULL";
      g_lpDebugMsg(4u, L"MakePathUNC: Entering with <%s>", v4);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v5 = a1;
      if ( !a1 )
        v5 = L"NULL";
      RedirectDebugMsg(4u, L"MakePathUNC: Entering with <%s>", v5);
    }
  }
  v6 = -1;
  if ( a1 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a1[v7] );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  v9 = (unsigned int)(v7 + v8 + 10);
  v10 = (unsigned int)v9;
  v11 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v9);
  if ( !v11 )
    return 0;
  if ( !a1 || !*a1 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"MakePathUNC: lpFile is NULL, setting lpResult to a null string");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"MakePathUNC: lpFile is NULL, setting lpResult to a null string");
      }
    }
    *v11 = 0;
    return v11;
  }
  if ( !(unsigned int)IsUNCPath(a1) )
  {
    StringCchCopyW(v11, (unsigned int)v9, L"\\\\");
    StringCchCatW(v11, (unsigned int)v9, a2);
    if ( (int)SafeExpandEnvironmentStrings(v13, String1, v14) < 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v15 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          LastError = GetLastError();
          v15(
            2u,
            L"MakePathUNC: ExpandEnvironmentString failed with error %d, setting szSysRoot to %%systemroot%% ",
            LastError);
        }
        else if ( g_lpDebugMsgContextInstance )
        {
          if ( g_lpDebugMsgContext )
          {
            v17 = GetLastError();
            RedirectDebugMsg(
              2u,
              L"MakePathUNC: ExpandEnvironmentString failed with error %d, setting szSysRoot to %%systemroot%% ",
              v17);
          }
        }
      }
      LocalFree(v11);
      return 0;
    }
    cchCount2 = -1;
    do
      ++cchCount2;
    while ( String1[cchCount2] );
    v19 = CheckSlashEx(v11, v9, v21);
    do
      ++v6;
    while ( a1[v6] );
    if ( (unsigned int)v6 > (unsigned int)cchCount2
      && CompareStringW(0x400u, 1u, String1, cchCount2, a1, cchCount2) == 2 )
    {
      StringCchCatW(v11, v10, L"admin$");
      v20 = &a1[(unsigned int)cchCount2];
    }
    else
    {
      if ( a1[1] != 58 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"MakePathUNC: Input path %s is not an absolute path", a1);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"MakePathUNC: Input path %s is not an absolute path", a1);
          }
        }
        StringCchCatW(v11, v10, a1);
        return v11;
      }
      if ( v21[0] <= 2 )
        goto LABEL_51;
      v20 = a1 + 2;
      *v19 = *a1;
      *(_DWORD *)(v19 + 1) = 36;
    }
    StringCchCatW(v11, v10, v20);
LABEL_51:
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"MakePathUNC: Returning a UNCPath of %s", v11);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"MakePathUNC: Returning a UNCPath of %s", v11);
      }
    }
    return v11;
  }
  StringCchCopyW(v11, (unsigned int)v9, a1);
  return v11;
}

```

## disassembly

```asm
0x1800887c0  mov     [rsp+arg_10], rbx
0x1800887c5  push    rbp
0x1800887c6  push    rsi
0x1800887c7  push    rdi
0x1800887c8  push    r12
0x1800887ca  push    r13
0x1800887cc  push    r14
0x1800887ce  push    r15
0x1800887d0  sub     rsp, 260h
0x1800887d7  mov     rax, cs:__security_cookie
0x1800887de  xor     rax, rsp
0x1800887e1  mov     [rsp+298h+var_48], rax
0x1800887e9  xor     r12d, r12d
0x1800887ec  mov     rbp, rdx
0x1800887ef  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800887f6  mov     rdi, rcx
0x1800887f9  mov     [rsp+298h+var_268], r12d
0x1800887fe  lea     r13d, [r12+4]
0x180088803  jz      short loc_180088865
0x180088805  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008880c  test    rax, rax
0x18008880f  jz      short loc_180088833
0x180088811  lea     rcx, aNull_1; "NULL"
0x180088818  test    rdi, rdi
0x18008881b  mov     r8, rdi
0x18008881e  lea     rdx, aMakepathuncEnt; "MakePathUNC: Entering with <%s>"
0x180088825  cmovz   r8, rcx
0x180088829  mov     ecx, r13d
0x18008882c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088831  jmp     short loc_180088865
0x180088833  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18008883a  jz      short loc_180088865
0x18008883c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180088843  jz      short loc_180088865
0x180088845  lea     rcx, aNull_1; "NULL"
0x18008884c  test    rdi, rdi
0x18008884f  mov     r8, rdi
0x180088852  lea     rdx, aMakepathuncEnt; "MakePathUNC: Entering with <%s>"
0x180088859  cmovz   r8, rcx
0x18008885d  mov     ecx, r13d; unsigned int
0x180088860  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180088865  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180088869  test    rdi, rdi
0x18008886c  jnz     short loc_180088873
0x18008886e  mov     rcx, r12
0x180088871  jmp     short loc_180088880
0x180088873  mov     rcx, rsi
0x180088876  inc     rcx
0x180088879  cmp     [rdi+rcx*2], r12w
0x18008887e  jnz     short loc_180088876
0x180088880  test    rbp, rbp
0x180088883  jnz     short loc_18008888A
0x180088885  mov     rax, r12
0x180088888  jmp     short loc_180088898
0x18008888a  mov     rax, rsi
0x18008888d  inc     rax
0x180088890  cmp     [rbp+rax*2+0], r12w
0x180088896  jnz     short loc_18008888D
0x180088898  lea     r15d, [rax+0Ah]
0x18008889c  add     r15d, ecx
0x18008889f  mov     ecx, 40h ; '@'; uFlags
0x1800888a4  mov     r14d, r15d
0x1800888a7  lea     rdx, [r15+r15]; uBytes
0x1800888ab  call    cs:__imp_LocalAlloc
0x1800888b1  mov     rbx, rax
0x1800888b4  test    rax, rax
0x1800888b7  jnz     short loc_1800888C0
0x1800888b9  xor     eax, eax
0x1800888bb  jmp     loc_180088B2F
0x1800888c0  test    rdi, rdi
0x1800888c3  jz      loc_180088AE1
0x1800888c9  cmp     [rdi], r12w
0x1800888cd  jz      loc_180088AE1
0x1800888d3  mov     rcx, rdi; unsigned __int16 *
0x1800888d6  call    ?IsUNCPath@@YAHPEBG@Z; IsUNCPath(ushort const *)
0x1800888db  mov     rdx, r14; unsigned __int64
0x1800888de  mov     rcx, rbx; unsigned __int16 *
0x1800888e1  test    eax, eax
0x1800888e3  jz      short loc_1800888F2
0x1800888e5  mov     r8, rdi; unsigned __int16 *
0x1800888e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800888ed  jmp     loc_180088B2C
0x1800888f2  lea     r8, asc_1800CF110; "\\\\"
0x1800888f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800888fe  mov     r8, rbp; unsigned __int16 *
0x180088901  mov     rdx, r14; unsigned __int64
0x180088904  mov     rcx, rbx; unsigned __int16 *
0x180088907  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008890c  lea     rdx, [rsp+298h+String1]; unsigned __int16 *
0x180088911  call    ?SafeExpandEnvironmentStrings@@YAJPEBGPEAGK@Z; SafeExpandEnvironmentStrings(ushort const *,ushort *,ulong)
0x180088916  test    eax, eax
0x180088918  jns     short loc_180088988
0x18008891a  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180088921  jz      short loc_18008897A
0x180088923  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008892a  test    rdi, rdi
0x18008892d  jz      short loc_18008894E
0x18008892f  call    cs:__imp_GetLastError
0x180088935  lea     rdx, aMakepathuncExp; "MakePathUNC: ExpandEnvironmentString fa"...
0x18008893c  mov     ecx, 2
0x180088941  mov     r8d, eax
0x180088944  mov     rax, rdi
0x180088947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008894c  jmp     short loc_18008897A
0x18008894e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180088955  jz      short loc_18008897A
0x180088957  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008895e  jz      short loc_18008897A
0x180088960  call    cs:__imp_GetLastError
0x180088966  lea     rdx, aMakepathuncExp; "MakePathUNC: ExpandEnvironmentString fa"...
0x18008896d  mov     ecx, 2; unsigned int
0x180088972  mov     r8d, eax
0x180088975  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008897a  mov     rcx, rbx; hMem
0x18008897d  call    cs:__imp_LocalFree
0x180088983  jmp     loc_1800888B9
0x180088988  lea     rax, [rsp+298h+String1]
0x18008898d  mov     rbp, rsi
0x180088990  inc     rbp
0x180088993  cmp     [rax+rbp*2], r12w
0x180088998  jnz     short loc_180088990
0x18008899a  lea     r8, [rsp+298h+var_268]; unsigned int *
0x18008899f  mov     edx, r15d; unsigned int
0x1800889a2  mov     rcx, rbx; unsigned __int16 *
0x1800889a5  call    ?CheckSlashEx@@YAPEAGPEAGIPEAI@Z; CheckSlashEx(ushort *,uint,uint *)
0x1800889aa  mov     r15, rax
0x1800889ad  inc     rsi
0x1800889b0  cmp     [rdi+rsi*2], r12w
0x1800889b5  jnz     short loc_1800889AD
0x1800889b7  cmp     esi, ebp
0x1800889b9  jbe     short loc_1800889FE
0x1800889bb  mov     [rsp+298h+cchCount2], ebp; cchCount2
0x1800889bf  lea     r8, [rsp+298h+String1]; lpString1
0x1800889c4  mov     r9d, ebp; cchCount1
0x1800889c7  mov     [rsp+298h+lpString2], rdi; lpString2
0x1800889cc  mov     edx, 1; dwCmpFlags
0x1800889d1  mov     ecx, 400h; Locale
0x1800889d6  call    cs:__imp_CompareStringW
0x1800889dc  cmp     eax, 2
0x1800889df  jnz     short loc_1800889FE
0x1800889e1  lea     r8, aAdmin; "admin$"
0x1800889e8  mov     rdx, r14; unsigned __int64
0x1800889eb  mov     rcx, rbx; unsigned __int16 *
0x1800889ee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800889f3  mov     eax, ebp
0x1800889f5  lea     r8, [rdi+rax*2]
0x1800889f9  jmp     loc_180088A83
0x1800889fe  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180088a03  jz      short loc_180088A69
0x180088a05  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180088a0c  jz      short loc_180088A56
0x180088a0e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180088a15  test    rax, rax
0x180088a18  jz      short loc_180088A30
0x180088a1a  mov     r8, rdi
0x180088a1d  lea     rdx, aMakepathuncInp; "MakePathUNC: Input path %s is not an ab"...
0x180088a24  mov     ecx, 2
0x180088a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088a2e  jmp     short loc_180088A56
0x180088a30  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180088a37  jz      short loc_180088A56
0x180088a39  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180088a40  jz      short loc_180088A56
0x180088a42  mov     r8, rdi
0x180088a45  lea     rdx, aMakepathuncInp; "MakePathUNC: Input path %s is not an ab"...
0x180088a4c  mov     ecx, 2; unsigned int
0x180088a51  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180088a56  mov     r8, rdi; unsigned __int16 *
0x180088a59  mov     rdx, r14; unsigned __int64
0x180088a5c  mov     rcx, rbx; unsigned __int16 *
0x180088a5f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180088a64  jmp     loc_180088B2C
0x180088a69  cmp     [rsp+298h+var_268], 2
0x180088a6e  jbe     short loc_180088A8E
0x180088a70  movzx   eax, word ptr [rdi]
0x180088a73  lea     r8, [rdi+4]; unsigned __int16 *
0x180088a77  mov     [r15], ax
0x180088a7b  mov     dword ptr [r15+2], 24h ; '$'
0x180088a83  mov     rdx, r14; unsigned __int64
0x180088a86  mov     rcx, rbx; unsigned __int16 *
0x180088a89  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180088a8e  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180088a95  jz      loc_180088B2C
0x180088a9b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180088aa2  test    rax, rax
0x180088aa5  jz      short loc_180088ABB
0x180088aa7  mov     r8, rbx
0x180088aaa  lea     rdx, aMakepathuncRet; "MakePathUNC: Returning a UNCPath of %s"
0x180088ab1  mov     ecx, r13d
0x180088ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ab9  jmp     short loc_180088B2C
0x180088abb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180088ac2  jz      short loc_180088B2C
0x180088ac4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180088acb  jz      short loc_180088B2C
0x180088acd  mov     r8, rbx
0x180088ad0  lea     rdx, aMakepathuncRet; "MakePathUNC: Returning a UNCPath of %s"
0x180088ad7  mov     ecx, r13d; unsigned int
0x180088ada  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180088adf  jmp     short loc_180088B2C
0x180088ae1  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180088ae8  jz      short loc_180088B28
0x180088aea  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180088af1  test    rax, rax
0x180088af4  jz      short loc_180088B07
0x180088af6  lea     rdx, aMakepathuncLpf; "MakePathUNC: lpFile is NULL, setting lp"...
0x180088afd  mov     ecx, r13d
0x180088b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088b05  jmp     short loc_180088B28
0x180088b07  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180088b0e  jz      short loc_180088B28
0x180088b10  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180088b17  jz      short loc_180088B28
0x180088b19  lea     rdx, aMakepathuncLpf; "MakePathUNC: lpFile is NULL, setting lp"...
0x180088b20  mov     ecx, r13d; unsigned int
0x180088b23  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180088b28  mov     [rbx], r12w
0x180088b2c  mov     rax, rbx
0x180088b2f  mov     rcx, [rsp+298h+var_48]
0x180088b37  xor     rcx, rsp; StackCookie
0x180088b3a  call    __security_check_cookie
0x180088b3f  mov     rbx, [rsp+298h+arg_10]
0x180088b47  add     rsp, 260h
0x180088b4e  pop     r15
0x180088b50  pop     r14
0x180088b52  pop     r13
0x180088b54  pop     r12
0x180088b56  pop     rdi
0x180088b57  pop     rsi
0x180088b58  pop     rbp
0x180088b59  retn
```
