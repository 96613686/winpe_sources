# SelectGroupLGPOToApply(void *,ushort * *)

- ea: `0x18004f57c`
- end: `0x18004f7fc`
- name: `?SelectGroupLGPOToApply@@YAHPEAXPEAPEAG@Z`
- size: `640`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800147b0`

## callees

- `0x18000a504`
- `0x18004f57c`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f5e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f61a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f6c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f71d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f73e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f77c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f7ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f5e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f61a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f6c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f71d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f73e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f77c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f7ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f5bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f5bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f7cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f7d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f7cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f7d9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18004f66b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18004f66b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004f687`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004f687`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004f6a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004f6a1`

## string_xrefs

- `0x18004f788`: `SelectGroupLGPOToApply:  CreateWellKnownSid for well-known type=%d failed with err=0x%x`
- `0x18004f7b9`: `SelectGroupLGPOToApply:  CreateWellKnownSid for well-known type=%d failed with err=0x%x`
- `0x18004f723`: `SelectGroupLGPOToApply:  CheckTokenMembership for well-known SID type=%d failed with err=0x%x`
- `0x18004f744`: `SelectGroupLGPOToApply:  CheckTokenMembership for well-known SID type=%d failed with err=0x%x`
- `0x18004f6ce`: `SelectGroupLGPOToApply:  ConvertSidToStringSid for well-known SID type=%d failed with err=0x%x`
- `0x18004f6ff`: `SelectGroupLGPOToApply:  ConvertSidToStringSid for well-known SID type=%d failed with err=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SelectGroupLGPOToApply(HANDLE TokenHandle, LPWSTR *StringSid)
{
  HLOCAL v4; // rdi
  void (*v5)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v6; // eax
  DWORD v7; // eax
  unsigned int i; // esi
  WELL_KNOWN_SID_TYPE v10; // r14d
  void (*v11)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v12; // eax
  const wchar_t *v13; // rdx
  DWORD v14; // eax
  DWORD v15; // eax
  void (*v16)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD LastError; // eax
  DWORD v18; // eax
  void *v19; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbSid; // [rsp+88h] [rbp+48h] BYREF
  WINBOOL IsMember; // [rsp+90h] [rbp+50h] BYREF
  WELL_KNOWN_SID_TYPE WellKnownSidType; // [rsp+98h] [rbp+58h]
  int v23; // [rsp+9Ch] [rbp+5Ch]

  cbSid = 68;
  IsMember = 0;
  WellKnownSidType = WinBuiltinAdministratorsSid;
  v23 = 27;
  *StringSid = 0;
  v4 = LocalAlloc(0x40u, 0x44u);
  v19 = v4;
  if ( v4 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 2 )
        goto LABEL_37;
      cbSid = 68;
      v10 = *((_DWORD *)&WellKnownSidType + (int)i);
      if ( !CreateWellKnownSid(v10, 0, v4, &cbSid) )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v16 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            LastError = GetLastError();
            v16(
              2u,
              L"SelectGroupLGPOToApply:  CreateWellKnownSid for well-known type=%d failed with err=0x%x",
              (unsigned int)v10,
              LastError);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v18 = GetLastError();
            RedirectDebugMsg(
              2u,
              L"SelectGroupLGPOToApply:  CreateWellKnownSid for well-known type=%d failed with err=0x%x",
              (unsigned int)v10,
              v18);
          }
        }
        LocalFree(v4);
        return 0;
      }
      IsMember = 0;
      if ( !CheckTokenMembership(TokenHandle, v4, &IsMember) )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v11 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v12 = GetLastError();
            v13 = L"SelectGroupLGPOToApply:  CheckTokenMembership for well-known SID type=%d failed with err=0x%x";
LABEL_19:
            v11(2u, v13, (unsigned int)v10, v12);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v15 = GetLastError();
            RedirectDebugMsg(
              2u,
              L"SelectGroupLGPOToApply:  CheckTokenMembership for well-known SID type=%d failed with err=0x%x",
              (unsigned int)v10,
              v15);
          }
        }
LABEL_29:
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v19);
        return 0;
      }
      if ( IsMember )
        break;
    }
    if ( !ConvertSidToStringSidW(v4, StringSid) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v11 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v12 = GetLastError();
          v13 = L"SelectGroupLGPOToApply:  ConvertSidToStringSid for well-known SID type=%d failed with err=0x%x";
          goto LABEL_19;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v14 = GetLastError();
          RedirectDebugMsg(
            2u,
            L"SelectGroupLGPOToApply:  ConvertSidToStringSid for well-known SID type=%d failed with err=0x%x",
            (unsigned int)v10,
            v14);
        }
      }
      goto LABEL_29;
    }
LABEL_37:
    LocalFree(v4);
    return 1;
  }
  else
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v5 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v6 = GetLastError();
        v5(2u, L"SelectGroupLGPOToApply:  Failed to allocate memory (size=%d), err=0x%x", cbSid, v6);
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
        {
          v7 = GetLastError();
          RedirectDebugMsg(2u, L"SelectGroupLGPOToApply:  Failed to allocate memory (size=%d), err=0x%x", cbSid, v7);
        }
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18004f57c  mov     [rsp-38h+arg_0], rbx
0x18004f581  push    rbp
0x18004f582  push    rsi
0x18004f583  push    rdi
0x18004f584  push    r12
0x18004f586  push    r13
0x18004f588  push    r14
0x18004f58a  push    r15
0x18004f58c  mov     rbp, rsp
0x18004f58f  sub     rsp, 40h
0x18004f593  mov     r15, rdx
0x18004f596  mov     r12, rcx
0x18004f599  mov     [rbp+cbSid], 44h ; 'D'
0x18004f5a0  xor     r13d, r13d
0x18004f5a3  mov     [rbp+IsMember], r13d
0x18004f5a7  mov     [rbp+WellKnownSidType], 1Ah
0x18004f5ae  mov     [rbp+arg_1C], 1Bh
0x18004f5b5  mov     [rdx], r13
0x18004f5b8  lea     edx, [r13+44h]; uBytes
0x18004f5bc  lea     ecx, [rdx-4]; uFlags
0x18004f5bf  call    cs:__imp_LocalAlloc
0x18004f5c5  mov     rdi, rax
0x18004f5c8  mov     [rbp+var_10], rax
0x18004f5cc  test    rax, rax
0x18004f5cf  jnz     short loc_18004F640
0x18004f5d1  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004f5d8  jz      short loc_18004F639
0x18004f5da  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004f5e1  test    rdi, rdi
0x18004f5e4  jz      short loc_18004F608
0x18004f5e6  call    cs:__imp_GetLastError
0x18004f5ec  mov     r9d, eax
0x18004f5ef  mov     r8d, [rbp+cbSid]
0x18004f5f3  lea     rdx, aSelectgrouplgp_1; "SelectGroupLGPOToApply:  Failed to allo"...
0x18004f5fa  lea     ecx, [r13+2]
0x18004f5fe  mov     rax, rdi
0x18004f601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f606  jmp     short loc_18004F639
0x18004f608  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004f60f  jz      short loc_18004F639
0x18004f611  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004f618  jz      short loc_18004F639
0x18004f61a  call    cs:__imp_GetLastError
0x18004f620  mov     r9d, eax
0x18004f623  mov     r8d, [rbp+cbSid]
0x18004f627  lea     rdx, aSelectgrouplgp_1; "SelectGroupLGPOToApply:  Failed to allo"...
0x18004f62e  mov     ecx, 2; unsigned int
0x18004f633  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004f638  nop
0x18004f639  xor     eax, eax
0x18004f63b  jmp     loc_18004F7E4
0x18004f640  mov     esi, r13d
0x18004f643  mov     ebx, 2
0x18004f648  cmp     esi, ebx
0x18004f64a  jnb     loc_18004F7D6
0x18004f650  mov     [rbp+cbSid], 44h ; 'D'
0x18004f657  movsxd  rax, esi
0x18004f65a  mov     r14d, [rbp+rax*4+WellKnownSidType]
0x18004f65f  lea     r9, [rbp+cbSid]; cbSid
0x18004f663  mov     r8, rdi; pSid
0x18004f666  xor     edx, edx; DomainSid
0x18004f668  mov     ecx, r14d; WellKnownSidType
0x18004f66b  call    cs:__imp_CreateWellKnownSid
0x18004f671  test    eax, eax
0x18004f673  jz      loc_18004F767
0x18004f679  mov     [rbp+IsMember], r13d
0x18004f67d  lea     r8, [rbp+IsMember]; IsMember
0x18004f681  mov     rdx, rdi; SidToCheck
0x18004f684  mov     rcx, r12; TokenHandle
0x18004f687  call    cs:__imp_CheckTokenMembership
0x18004f68d  test    eax, eax
0x18004f68f  jz      short loc_18004F708
0x18004f691  cmp     [rbp+IsMember], r13d
0x18004f695  jnz     short loc_18004F69B
0x18004f697  inc     esi
0x18004f699  jmp     short loc_18004F648
0x18004f69b  mov     rdx, r15; StringSid
0x18004f69e  mov     rcx, rdi; Sid
0x18004f6a1  call    cs:__imp_ConvertSidToStringSidW
0x18004f6a7  test    eax, eax
0x18004f6a9  jnz     loc_18004F7D6
0x18004f6af  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004f6b6  jz      loc_18004F759
0x18004f6bc  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004f6c3  test    rdi, rdi
0x18004f6c6  jz      short loc_18004F6E7
0x18004f6c8  call    cs:__imp_GetLastError
0x18004f6ce  lea     rdx, aSelectgrouplgp_2; "SelectGroupLGPOToApply:  ConvertSidToSt"...
0x18004f6d5  mov     r8d, r14d
0x18004f6d8  mov     r9d, eax
0x18004f6db  mov     ecx, ebx
0x18004f6dd  mov     rax, rdi
0x18004f6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6e5  jmp     short loc_18004F759
0x18004f6e7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004f6ee  jz      short loc_18004F759
0x18004f6f0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004f6f7  jz      short loc_18004F759
0x18004f6f9  call    cs:__imp_GetLastError
0x18004f6ff  lea     rdx, aSelectgrouplgp_2; "SelectGroupLGPOToApply:  ConvertSidToSt"...
0x18004f706  jmp     short loc_18004F74B
0x18004f708  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004f70f  jz      short loc_18004F759
0x18004f711  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004f718  test    rdi, rdi
0x18004f71b  jz      short loc_18004F72C
0x18004f71d  call    cs:__imp_GetLastError
0x18004f723  lea     rdx, aSelectgrouplgp_0; "SelectGroupLGPOToApply:  CheckTokenMemb"...
0x18004f72a  jmp     short loc_18004F6D5
0x18004f72c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004f733  jz      short loc_18004F759
0x18004f735  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004f73c  jz      short loc_18004F759
0x18004f73e  call    cs:__imp_GetLastError
0x18004f744  lea     rdx, aSelectgrouplgp_0; "SelectGroupLGPOToApply:  CheckTokenMemb"...
0x18004f74b  mov     r9d, eax
0x18004f74e  mov     r8d, r14d
0x18004f751  mov     ecx, ebx; unsigned int
0x18004f753  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004f758  nop
0x18004f759  lea     rcx, [rbp+var_10]
0x18004f75d  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18004f762  jmp     loc_18004F639
0x18004f767  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004f76e  jz      short loc_18004F7C8
0x18004f770  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004f777  test    rsi, rsi
0x18004f77a  jz      short loc_18004F79B
0x18004f77c  call    cs:__imp_GetLastError
0x18004f782  mov     r9d, eax
0x18004f785  mov     r8d, r14d
0x18004f788  lea     rdx, aSelectgrouplgp; "SelectGroupLGPOToApply:  CreateWellKnow"...
0x18004f78f  mov     ecx, ebx
0x18004f791  mov     rax, rsi
0x18004f794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f799  jmp     short loc_18004F7C8
0x18004f79b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004f7a2  jz      short loc_18004F7C8
0x18004f7a4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004f7ab  jz      short loc_18004F7C8
0x18004f7ad  call    cs:__imp_GetLastError
0x18004f7b3  mov     r9d, eax
0x18004f7b6  mov     r8d, r14d
0x18004f7b9  lea     rdx, aSelectgrouplgp; "SelectGroupLGPOToApply:  CreateWellKnow"...
0x18004f7c0  mov     ecx, ebx; unsigned int
0x18004f7c2  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004f7c7  nop
0x18004f7c8  mov     rcx, rdi; hMem
0x18004f7cb  call    cs:__imp_LocalFree
0x18004f7d1  jmp     loc_18004F639
0x18004f7d6  mov     rcx, rdi; hMem
0x18004f7d9  call    cs:__imp_LocalFree
0x18004f7df  mov     eax, 1
0x18004f7e4  mov     rbx, [rsp+40h+arg_0]
0x18004f7ec  add     rsp, 40h
0x18004f7f0  pop     r15
0x18004f7f2  pop     r14
0x18004f7f4  pop     r13
0x18004f7f6  pop     r12
0x18004f7f8  pop     rdi
0x18004f7f9  pop     rsi
0x18004f7fa  pop     rbp
0x18004f7fb  retn
```
