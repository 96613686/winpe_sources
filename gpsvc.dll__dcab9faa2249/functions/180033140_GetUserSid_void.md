# GetUserSid(void *)

- ea: `0x180033140`
- end: `0x180033421`
- name: `?GetUserSid@@YAPEAXPEAX@Z`
- size: `737`
- prototype: `void *__fastcall(HANDLE TokenHandle)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800246a8`
- `0x1800310b0`
- `0x1800336a0`
- `0x18006ea44`
- `0x180071890`
- `0x1800b2d88`
- `0x1800b3bd0`

## callees

- `0x180033140`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003315c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800331ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003315c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800331ae`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800332d7`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800332d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800331d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003321d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033414`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800331d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003321d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033414`
- `ntdll!NtQueryInformationToken` at `0x180033188`
- `ntdll!NtQueryInformationToken` at `0x18003336a`
- `ntdll!NtQueryInformationToken` at `0x180033188`
- `ntdll!NtQueryInformationToken` at `0x18003336a`
- `ntdll!RtlCopySid` at `0x1800331cb`
- `ntdll!RtlCopySid` at `0x1800331cb`
- `ntdll!RtlLengthSid` at `0x1800331a0`
- `ntdll!RtlLengthSid` at `0x1800331a0`

## string_xrefs

- `0x180033260`: `GetUserSid: Failed to allocate %d bytes`
- `0x18003327d`: `GetUserSid: Failed to allocate %d bytes`
- `0x1800332b4`: `GetUserSid: Failed to allocate %d bytes`
- `0x18003331e`: `GetUserSid: Failed to allocate %d bytes`
- `0x180033337`: `GetUserSid: Failed to query user info from user token, status = 0x%x`
- `0x180033384`: `GetUserSid: Failed to query user info from user token, status = 0x%x`
- `0x1800333d6`: `GetUserSid: RtlCopySid Failed. status = %d`
- `0x180033400`: `GetUserSid: RtlCopySid Failed. status = %d`

## pseudocode

```c
void *__fastcall GetUserSid(HANDLE TokenHandle)
{
  PSID *v2; // rbx
  NTSTATUS v3; // eax
  HLOCAL v4; // rax
  void *v5; // rdi
  NTSTATUS v6; // esi
  void (*v8)(unsigned int, const unsigned __int16 *, ...); // rax
  PSID *v9; // rax
  ULONG TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = 200;
  v2 = (PSID *)LocalAlloc(0, 0xC8u);
  if ( v2 )
  {
    v3 = NtQueryInformationToken(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength);
    if ( v3 == -1073741789 )
    {
      v9 = (PSID *)LocalReAlloc(v2, TokenInformationLength, 2u);
      if ( !v9 )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_10;
        v8 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( !g_lpDebugMsgContextInstance || (char *)g_lpDebugMsgContext == (char *)g_lpDebugMsg )
            goto LABEL_10;
LABEL_15:
          RedirectDebugMsg(2u, L"GetUserSid: Failed to allocate %d bytes", TokenInformationLength);
          goto LABEL_10;
        }
LABEL_27:
        v8(2u, L"GetUserSid: Failed to allocate %d bytes", TokenInformationLength);
        goto LABEL_10;
      }
      v2 = v9;
      v3 = NtQueryInformationToken(TokenHandle, TokenUser, v9, TokenInformationLength, &TokenInformationLength);
    }
    if ( v3 < 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"GetUserSid: Failed to query user info from user token, status = 0x%x", (unsigned int)v3);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            2u,
            L"GetUserSid: Failed to query user info from user token, status = 0x%x",
            (unsigned int)v3);
        }
      }
      goto LABEL_10;
    }
    TokenInformationLength = RtlLengthSid(*v2);
    v4 = LocalAlloc(0, TokenInformationLength);
    v5 = v4;
    if ( v4 )
    {
      v6 = RtlCopySid(TokenInformationLength, v4, *v2);
      LocalFree(v2);
      if ( v6 < 0 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"GetUserSid: RtlCopySid Failed. status = %d", (unsigned int)v6);
          }
          else if ( g_lpDebugMsgContextInstance )
          {
            if ( g_lpDebugMsgContext )
              RedirectDebugMsg(2u, L"GetUserSid: RtlCopySid Failed. status = %d", (unsigned int)v6);
          }
        }
        LocalFree(v5);
        return 0;
      }
      return v5;
    }
    if ( !*(_DWORD *)&g_dwDebugLevel )
    {
LABEL_10:
      LocalFree(v2);
      return 0;
    }
    v8 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( !g_lpDebugMsgContextInstance || (char *)g_lpDebugMsgContext == (char *)g_lpDebugMsg )
        goto LABEL_10;
      goto LABEL_15;
    }
    goto LABEL_27;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"GetUserSid: Failed to allocate %d bytes", TokenInformationLength);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"GetUserSid: Failed to allocate %d bytes", TokenInformationLength);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180033140  mov     [rsp+arg_10], rbx
0x180033145  push    rdi
0x180033146  sub     rsp, 30h
0x18003314a  mov     rdi, rcx
0x18003314d  mov     [rsp+38h+TokenInformationLength], 0C8h
0x180033155  xor     ecx, ecx; uFlags
0x180033157  mov     edx, 0C8h; uBytes
0x18003315c  call    cs:__imp_LocalAlloc
0x180033162  mov     rbx, rax
0x180033165  test    rax, rax
0x180033168  jz      loc_1800331F7
0x18003316e  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180033173  lea     rax, [rsp+38h+TokenInformationLength]
0x180033178  mov     r8, rbx; TokenInformation
0x18003317b  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180033180  mov     edx, 1; TokenInformationClass
0x180033185  mov     rcx, rdi; TokenHandle
0x180033188  call    cs:__imp_NtQueryInformationToken
0x18003318e  cmp     eax, 0C0000023h
0x180033193  jz      loc_1800332CA
0x180033199  test    eax, eax
0x18003319b  js      short loc_18003320D
0x18003319d  mov     rcx, [rbx]; Sid
0x1800331a0  call    cs:__imp_RtlLengthSid
0x1800331a6  mov     edx, eax; uBytes
0x1800331a8  xor     ecx, ecx; uFlags
0x1800331aa  mov     [rsp+38h+TokenInformationLength], edx
0x1800331ae  call    cs:__imp_LocalAlloc
0x1800331b4  mov     rdi, rax
0x1800331b7  test    rax, rax
0x1800331ba  jz      short loc_180033230
0x1800331bc  mov     r8, [rbx]; SourceSid
0x1800331bf  mov     rdx, rax; DestinationSid
0x1800331c2  mov     ecx, [rsp+38h+TokenInformationLength]; DestinationSidLength
0x1800331c6  mov     [rsp+38h+arg_0], rsi
0x1800331cb  call    cs:__imp_RtlCopySid
0x1800331d1  mov     rcx, rbx; hMem
0x1800331d4  mov     esi, eax
0x1800331d6  call    cs:__imp_LocalFree
0x1800331dc  test    esi, esi
0x1800331de  js      loc_1800333BE
0x1800331e4  mov     rsi, [rsp+38h+arg_0]
0x1800331e9  mov     rax, rdi
0x1800331ec  mov     rbx, [rsp+38h+arg_10]
0x1800331f1  add     rsp, 30h
0x1800331f5  pop     rdi
0x1800331f6  retn
0x1800331f7  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800331fe  jnz     short loc_18003326C
0x180033200  xor     eax, eax
0x180033202  mov     rbx, [rsp+38h+arg_10]
0x180033207  add     rsp, 30h
0x18003320b  pop     rdi
0x18003320c  retn
0x18003320d  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180033214  jnz     loc_180033375
0x18003321a  mov     rcx, rbx; hMem
0x18003321d  call    cs:__imp_LocalFree
0x180033223  mov     rbx, [rsp+38h+arg_10]
0x180033228  xor     eax, eax
0x18003322a  add     rsp, 30h
0x18003322e  pop     rdi
0x18003322f  retn
0x180033230  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180033237  jz      short loc_18003321A
0x180033239  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180033240  test    rax, rax
0x180033243  jnz     loc_180033319
0x180033249  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rax; void * g_lpDebugMsgContextInstance
0x180033250  jz      short loc_18003321A
0x180033252  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rax; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180033259  jz      short loc_18003321A
0x18003325b  mov     r8d, [rsp+38h+TokenInformationLength]
0x180033260  lea     rdx, aGetusersidFail; "GetUserSid: Failed to allocate %d bytes"
0x180033267  jmp     loc_18003333E
0x18003326c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180033273  test    rax, rax
0x180033276  jz      short loc_180033293
0x180033278  mov     r8d, [rsp+38h+TokenInformationLength]
0x18003327d  lea     rdx, aGetusersidFail; "GetUserSid: Failed to allocate %d bytes"
0x180033284  mov     ecx, 2
0x180033289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003328e  jmp     loc_180033200
0x180033293  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18003329b  jz      loc_180033200
0x1800332a1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800332a9  jz      loc_180033200
0x1800332af  mov     r8d, [rsp+38h+TokenInformationLength]
0x1800332b4  lea     rdx, aGetusersidFail; "GetUserSid: Failed to allocate %d bytes"
0x1800332bb  mov     ecx, 2; unsigned int
0x1800332c0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800332c5  jmp     loc_180033200
0x1800332ca  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x1800332ce  mov     r8d, 2; uFlags
0x1800332d4  mov     rcx, rbx; hMem
0x1800332d7  call    cs:__imp_LocalReAlloc
0x1800332dd  test    rax, rax
0x1800332e0  jnz     short loc_18003334D
0x1800332e2  cmp     cs:?g_dwDebugLevel@@3KA, eax; ulong g_dwDebugLevel
0x1800332e8  jz      loc_18003321A
0x1800332ee  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800332f5  test    rax, rax
0x1800332f8  jnz     short loc_180033319
0x1800332fa  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rax; void * g_lpDebugMsgContextInstance
0x180033301  jz      loc_18003321A
0x180033307  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rax; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003330e  jz      loc_18003321A
0x180033314  jmp     loc_18003325B
0x180033319  mov     r8d, [rsp+38h+TokenInformationLength]
0x18003331e  lea     rdx, aGetusersidFail; "GetUserSid: Failed to allocate %d bytes"
0x180033325  mov     ecx, 2
0x18003332a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003332f  jmp     loc_18003321A
0x180033334  mov     r8d, eax
0x180033337  lea     rdx, aGetusersidFail_0; "GetUserSid: Failed to query user info f"...
0x18003333e  mov     ecx, 2; unsigned int
0x180033343  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180033348  jmp     loc_18003321A
0x18003334d  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180033352  lea     rcx, [rsp+38h+TokenInformationLength]
0x180033357  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x18003335c  mov     r8, rax; TokenInformation
0x18003335f  mov     rcx, rdi; TokenHandle
0x180033362  mov     edx, 1; TokenInformationClass
0x180033367  mov     rbx, rax
0x18003336a  call    cs:__imp_NtQueryInformationToken
0x180033370  jmp     loc_180033199
0x180033375  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003337c  test    r9, r9
0x18003337f  jz      short loc_18003339D
0x180033381  mov     r8d, eax
0x180033384  lea     rdx, aGetusersidFail_0; "GetUserSid: Failed to query user info f"...
0x18003338b  mov     rax, r9
0x18003338e  mov     ecx, 2
0x180033393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033398  jmp     loc_18003321A
0x18003339d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800333a5  jz      loc_18003321A
0x1800333ab  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800333b3  jz      loc_18003321A
0x1800333b9  jmp     loc_180033334
0x1800333be  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800333c5  jz      short loc_180033411
0x1800333c7  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800333ce  test    rax, rax
0x1800333d1  jz      short loc_1800333E9
0x1800333d3  mov     r8d, esi
0x1800333d6  lea     rdx, aGetusersidRtlc; "GetUserSid: RtlCopySid Failed. status ="...
0x1800333dd  mov     ecx, 2
0x1800333e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333e7  jmp     short loc_180033411
0x1800333e9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800333f1  jz      short loc_180033411
0x1800333f3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800333fb  jz      short loc_180033411
0x1800333fd  mov     r8d, esi
0x180033400  lea     rdx, aGetusersidRtlc; "GetUserSid: RtlCopySid Failed. status ="...
0x180033407  mov     ecx, 2; unsigned int
0x18003340c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180033411  mov     rcx, rdi; hMem
0x180033414  call    cs:__imp_LocalFree
0x18003341a  xor     edi, edi
0x18003341c  jmp     loc_1800331E4
```
