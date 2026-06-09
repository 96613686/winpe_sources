# ExpandGroup(CRsopToken *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,CSid *)

- ea: `0x180071690`
- end: `0x180071887`
- name: `?ExpandGroup@@YAJPEAUCRsopToken@@PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@PEAVCSid@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(struct CRsopToken *this, struct AUTHZ_RESOURCE_MANAGER_HANDLE__ *, struct CSid *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180072aa8`

## callees

- `0x18000a504`
- `0x180071690`
- `0x180072a08`
- `0x180072fec`
- `0x18007d72c`
- `0x1800a8418`
- `0x1800a8688`
- `0x1800a8964`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800716f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007178b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800717b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007183a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800716f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007178b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800717b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007183a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071779`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071779`
- `AUTHZ!AuthzGetInformationFromContext` at `0x18007174b`
- `AUTHZ!AuthzGetInformationFromContext` at `0x1800717ad`
- `AUTHZ!AuthzGetInformationFromContext` at `0x18007174b`
- `AUTHZ!AuthzGetInformationFromContext` at `0x1800717ad`
- `AUTHZ!AuthziInitializeContextFromSid` at `0x1800716e8`
- `AUTHZ!AuthziInitializeContextFromSid` at `0x1800716e8`
- `AUTHZ!AuthzFreeContext` at `0x180071857`
- `AUTHZ!AuthzFreeContext` at `0x180071857`

## string_xrefs

- `0x1800717bd`: `RsopCreateToken - AuthzGetInformationFromContext(2) failed. Error - %d`
- `0x1800716f8`: `ExpandGroup - AuthziInitializeContextFromSid failed. Error - %d`
- `0x180071791`: `ExpandGroup - Couldn't allocate memory for the token grps. Error - %d`
- `0x180071840`: `RsopCreateToken - couldn't allocate memory(2). Error - %d`
- `0x180071823`: `RsopCreateToken - AddSid failed. Error - 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ExpandGroup(struct CRsopToken *this, struct AUTHZ_RESOURCE_MANAGER_HANDLE__ *a2, struct CSid *a3)
{
  DWORD LastError; // eax
  const unsigned __int16 *v5; // r8
  signed int v6; // eax
  unsigned int v7; // edx
  unsigned int v8; // ebx
  unsigned int *Buffer; // rax
  unsigned int *v10; // rsi
  unsigned int i; // r14d
  const unsigned __int16 *v12; // r8
  CSid *v13; // rax
  int v14; // eax
  struct CSid *v16; // [rsp+40h] [rbp-20h] BYREF
  unsigned int *v17; // [rsp+48h] [rbp-18h] BYREF
  CSid *v18; // [rsp+50h] [rbp-10h]
  DWORD pSizeRequired; // [rsp+A0h] [rbp+40h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+A8h] [rbp+48h] BYREF

  hAuthzClientContext = 0;
  pSizeRequired = 0;
  v17 = 0;
  v16 = 0;
  if ( !(unsigned int)AuthziInitializeContextFromSid(0, *((_QWORD *)a3 + 1), a2, 0, 0, 0, &hAuthzClientContext) )
  {
    LastError = GetLastError();
    v5 = L"ExpandGroup - AuthziInitializeContextFromSid failed. Error - %d";
    goto LABEL_3;
  }
  if ( !AuthzGetInformationFromContext(hAuthzClientContext, AuthzContextInfoGroupsSids, 0, &pSizeRequired, 0)
    && GetLastError() != 122 )
  {
    LastError = GetLastError();
    v5 = L"ExpandGroup - AuthzGetInformationFromContext failed. Error - %d";
    goto LABEL_3;
  }
  Buffer = (unsigned int *)LocalAlloc(0x40u, pSizeRequired);
  v10 = Buffer;
  v17 = Buffer;
  if ( !Buffer )
  {
    LastError = GetLastError();
    v5 = L"ExpandGroup - Couldn't allocate memory for the token grps. Error - %d";
    goto LABEL_3;
  }
  if ( !AuthzGetInformationFromContext(
          hAuthzClientContext,
          AuthzContextInfoGroupsSids,
          pSizeRequired,
          &pSizeRequired,
          Buffer) )
  {
    LastError = GetLastError();
    v5 = L"RsopCreateToken - AuthzGetInformationFromContext(2) failed. Error - %d";
LABEL_3:
    CDebugWrapper::Msg((CDebugWrapper *)dbgAccessCheck, 2u, v5, LastError);
    v6 = GetLastError();
    v8 = v6;
    if ( v6 > 0 )
      v8 = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_20;
  }
  for ( i = 0; i < *v10; ++i )
  {
    v18 = (CSid *)operator new(0x58u);
    v13 = CSid::CSid(v18, *(PSID *)&v10[4 * i + 2], v12);
    XPtrST<CSid>::operator=(&v16, v13);
    if ( !v16 )
    {
      LastError = GetLastError();
      v5 = L"RsopCreateToken - couldn't allocate memory(2). Error - %d";
      goto LABEL_3;
    }
    v14 = CRsopToken::AddSid(this, (PSID *)v16);
    v8 = v14;
    if ( v14 < 0 )
    {
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgAccessCheck,
        2u,
        L"RsopCreateToken - AddSid failed. Error - 0x%x",
        (unsigned int)v14);
      goto LABEL_20;
    }
    v16 = 0;
  }
  v8 = 0;
LABEL_20:
  if ( hAuthzClientContext )
    AuthzFreeContext(hAuthzClientContext);
  XPtrST<CSid>::~XPtrST<CSid>(&v16, v7);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v17);
  return v8;
}

```

## disassembly

```asm
0x180071690  mov     r11, rsp
0x180071693  mov     [r11+8], rbx
0x180071697  push    rbp
0x180071698  push    rsi
0x180071699  push    rdi
0x18007169a  push    r14
0x18007169c  push    r15
0x18007169e  mov     rbp, rsp
0x1800716a1  sub     rsp, 60h
0x1800716a5  mov     r10, r8
0x1800716a8  mov     r15, rcx
0x1800716ab  mov     [rbp+hAuthzClientContext], 0
0x1800716b3  mov     [rbp+pSizeRequired], 0
0x1800716ba  mov     [rbp+var_18], 0
0x1800716c2  mov     [rbp+var_20], 0
0x1800716ca  xor     eax, eax
0x1800716cc  lea     rcx, [rbp+hAuthzClientContext]
0x1800716d0  mov     [r11-58h], rcx
0x1800716d4  mov     [r11-60h], rax
0x1800716d8  mov     [r11-68h], rax
0x1800716dc  xor     r9d, r9d
0x1800716df  mov     r8, rdx
0x1800716e2  mov     rdx, [r10+8]
0x1800716e6  xor     ecx, ecx
0x1800716e8  call    cs:__imp_AuthziInitializeContextFromSid
0x1800716ee  test    eax, eax
0x1800716f0  jnz     short loc_180071731
0x1800716f2  call    cs:__imp_GetLastError
0x1800716f8  lea     r8, aExpandgroupAut; "ExpandGroup - AuthziInitializeContextFr"...
0x1800716ff  mov     edx, 2; unsigned int
0x180071704  mov     r9d, eax
0x180071707  lea     rcx, ?dbgAccessCheck@@3VCDebugWrapper@@A; this
0x18007170e  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180071713  call    cs:__imp_GetLastError
0x180071719  mov     ebx, eax
0x18007171b  test    eax, eax
0x18007171d  jle     loc_18007184E
0x180071723  movzx   ebx, ax
0x180071726  or      ebx, 80070000h
0x18007172c  jmp     loc_18007184E
0x180071731  mov     [rsp+60h+Buffer], 0; Buffer
0x18007173a  lea     r9, [rbp+pSizeRequired]; pSizeRequired
0x18007173e  xor     r8d, r8d; BufferSize
0x180071741  lea     edi, [r8+2]
0x180071745  mov     edx, edi; InfoClass
0x180071747  mov     rcx, [rbp+hAuthzClientContext]; hAuthzClientContext
0x18007174b  call    cs:__imp_AuthzGetInformationFromContext
0x180071751  test    eax, eax
0x180071753  jnz     short loc_180071771
0x180071755  call    cs:__imp_GetLastError
0x18007175b  cmp     eax, 7Ah ; 'z'
0x18007175e  jz      short loc_180071771
0x180071760  call    cs:__imp_GetLastError
0x180071766  lea     r8, aExpandgroupAut_0; "ExpandGroup - AuthzGetInformationFromCo"...
0x18007176d  mov     edx, edi
0x18007176f  jmp     short loc_180071704
0x180071771  mov     edx, [rbp+pSizeRequired]; uBytes
0x180071774  mov     ecx, 40h ; '@'; uFlags
0x180071779  call    cs:__imp_LocalAlloc
0x18007177f  mov     rsi, rax
0x180071782  mov     [rbp+var_18], rax
0x180071786  test    rax, rax
0x180071789  jnz     short loc_18007179A
0x18007178b  call    cs:__imp_GetLastError
0x180071791  lea     r8, aExpandgroupCou; "ExpandGroup - Couldn't allocate memory "...
0x180071798  jmp     short loc_18007176D
0x18007179a  mov     [rsp+60h+Buffer], rsi; Buffer
0x18007179f  lea     r9, [rbp+pSizeRequired]; pSizeRequired
0x1800717a3  mov     r8d, [rbp+pSizeRequired]; BufferSize
0x1800717a7  mov     edx, edi; InfoClass
0x1800717a9  mov     rcx, [rbp+hAuthzClientContext]; hAuthzClientContext
0x1800717ad  call    cs:__imp_AuthzGetInformationFromContext
0x1800717b3  test    eax, eax
0x1800717b5  jnz     short loc_1800717C6
0x1800717b7  call    cs:__imp_GetLastError
0x1800717bd  lea     r8, aRsopcreatetoke_0; "RsopCreateToken - AuthzGetInformationFr"...
0x1800717c4  jmp     short loc_18007176D
0x1800717c6  xor     r14d, r14d
0x1800717c9  cmp     r14d, [rsi]
0x1800717cc  jnb     short loc_18007184C
0x1800717ce  mov     ecx, 58h ; 'X'; Size
0x1800717d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800717d8  mov     [rbp+var_10], rax
0x1800717dc  mov     edx, r14d
0x1800717df  add     rdx, rdx
0x1800717e2  mov     rdx, [rsi+rdx*8+8]; pSourceSid
0x1800717e7  mov     rcx, rax; this
0x1800717ea  call    ??0CSid@@QEAA@QEAXPEBG@Z; CSid::CSid(void * const,ushort const *)
0x1800717ef  nop
0x1800717f0  mov     rdx, rax
0x1800717f3  lea     rcx, [rbp+var_20]
0x1800717f7  call    ??4?$XPtrST@VCSid@@@@QEAAPEAVCSid@@PEAV1@@Z; XPtrST<CSid>::operator=(CSid *)
0x1800717fc  mov     rdx, [rbp+var_20]; struct CSid *
0x180071800  test    rdx, rdx
0x180071803  jz      short loc_18007183A
0x180071805  mov     rcx, r15; this
0x180071808  call    ?AddSid@CRsopToken@@QEAAJPEAVCSid@@@Z; CRsopToken::AddSid(CSid *)
0x18007180d  mov     ebx, eax
0x18007180f  test    eax, eax
0x180071811  js      short loc_180071820
0x180071813  mov     [rbp+var_20], 0
0x18007181b  inc     r14d
0x18007181e  jmp     short loc_1800717C9
0x180071820  mov     r9d, eax
0x180071823  lea     r8, aRsopcreatetoke_4; "RsopCreateToken - AddSid failed. Error "...
0x18007182a  mov     edx, edi; unsigned int
0x18007182c  lea     rcx, ?dbgAccessCheck@@3VCDebugWrapper@@A; this
0x180071833  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180071838  jmp     short loc_18007184E
0x18007183a  call    cs:__imp_GetLastError
0x180071840  lea     r8, aRsopcreatetoke_3; "RsopCreateToken - couldn't allocate mem"...
0x180071847  jmp     loc_18007176D
0x18007184c  xor     ebx, ebx
0x18007184e  mov     rcx, [rbp+hAuthzClientContext]; hAuthzClientContext
0x180071852  test    rcx, rcx
0x180071855  jz      short loc_18007185E
0x180071857  call    cs:__imp_AuthzFreeContext
0x18007185d  nop
0x18007185e  lea     rcx, [rbp+var_20]
0x180071862  call    ??1?$XPtrST@VCSid@@@@QEAA@XZ; XPtrST<CSid>::~XPtrST<CSid>(void)
0x180071867  nop
0x180071868  lea     rcx, [rbp+var_18]
0x18007186c  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180071871  mov     eax, ebx
0x180071873  mov     rbx, [rsp+60h+arg_0]
0x18007187b  add     rsp, 60h
0x18007187f  pop     r15
0x180071881  pop     r14
0x180071883  pop     rdi
0x180071884  pop     rsi
0x180071885  pop     rbp
0x180071886  retn
```
