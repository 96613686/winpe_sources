# W3_CONTEXT::ExecuteRequest(int,IHttpContext *,ulong,IHttpUser *,int *)

- ea: `0x180021af0`
- end: `0x180021ec1`
- name: `?ExecuteRequest@W3_CONTEXT@@UEAAJHPEAVIHttpContext@@KPEAVIHttpUser@@PEAH@Z`
- size: `977`
- prototype: `signed int __fastcall(W3_CONTEXT *this, int, struct IHttpContext *, int, struct IHttpUser *, int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800020d0`
- `0x180004f3c`
- `0x180009030`
- `0x180009c40`
- `0x180015d80`
- `0x18001ab30`
- `0x180021af0`
- `0x1800231f4`
- `0x180025c78`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_ultoa_s` at `0x180021c91`
- `msvcrt!_ultoa_s` at `0x180021c91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021beb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021beb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180021e74`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180021e74`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021c07`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021c07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021e85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c2a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180021c4b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180021c4b`

## pseudocode

```c
signed int __fastcall W3_CONTEXT::ExecuteRequest(
        W3_CONTEXT *this,
        int a2,
        struct IHttpContext *a3,
        int a4,
        struct IHttpUser *a5,
        int *a6)
{
  struct IHttpUser *v7; // rdx
  signed int result; // eax
  __int64 v12; // rax
  void (__fastcall *v13)(char *, __int64); // rbx
  __int64 v14; // rdx
  HANDLE CurrentThread; // rax
  __int64 v16; // rax
  unsigned int v17; // eax
  int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // r9
  __int64 v21; // rax
  const char *HttpMethod; // rax
  __int64 v23; // r9
  const struct _GUID *v24; // rdx
  unsigned int v25; // r8d
  NOTIFICATION_CONTEXT *v26; // rax
  NOTIFICATION_CONTEXT *v27; // rbx
  void *TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  char Buffer[16]; // [rsp+38h] [rbp-40h] BYREF

  v7 = a5;
  if ( !a3 )
    return -2147024809;
  TokenHandle = 0;
  if ( a5 )
  {
    (*(void (__fastcall **)(char *, struct IHttpUser *))(*((_QWORD *)a3 + 4) + 8LL))((char *)a3 + 32, a5);
LABEL_7:
    *((_BYTE *)a3 + 368) = 1;
    goto LABEL_8;
  }
  if ( *((_BYTE *)this + 368) )
  {
    v12 = (*(__int64 (__fastcall **)(W3_CONTEXT *, _QWORD))(*(_QWORD *)this + 48LL))(this, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 48LL))(v12);
    v13 = *(void (__fastcall **)(char *, __int64))(*((_QWORD *)a3 + 4) + 8LL);
    v14 = (*(__int64 (__fastcall **)(W3_CONTEXT *))(*(_QWORD *)this + 48LL))(this);
    v13((char *)a3 + 32, v14);
    goto LABEL_7;
  }
LABEL_8:
  if ( !a2
    || (W3_CONTEXT *)(*(__int64 (__fastcall **)(struct IHttpContext *, struct IHttpUser *))(*(_QWORD *)a3 + 232LL))(
                       a3,
                       v7) != this )
  {
    return -2147024846;
  }
  if ( *((_DWORD *)this + 2020) >= 0xAu )
    return -2147023895;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    RevertToSelf();
  }
  else if ( GetLastError() != 1008 )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 24LL))(a3);
  v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 144LL))(v16);
  if ( v17 != -1 )
  {
    if ( _ultoa_s(v17, Buffer, 0x10u, 10) )
    {
      v18 = -2147418113;
      goto LABEL_40;
    }
    v19 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 24LL))(a3);
    v20 = -1;
    do
      ++v20;
    while ( Buffer[v20] );
    v18 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v19 + 32LL))(v19, 11, Buffer);
    if ( v18 < 0 )
      goto LABEL_40;
  }
  if ( (a4 & 0x40) == 0 )
    (*(void (__fastcall **)(W3_CONTEXT *, __int64))(*(_QWORD *)this + 376LL))(this, 8);
  *((_DWORD *)a3 + 2021) = a4 | (*(__int64 (__fastcall **)(W3_CONTEXT *))(*(_QWORD *)this + 112LL))(this) & 0x29;
  if ( ((*(__int64 (__fastcall **)(W3_CONTEXT *))(*(_QWORD *)this + 112LL))(this) & 1) == 0 && (a4 & 0x21) == 0 )
    *((_DWORD *)this + 2021) = (*(__int64 (__fastcall **)(W3_CONTEXT *))(*(_QWORD *)this + 112LL))(this) | 1;
  if ( *(_BYTE *)(*((_QWORD *)this + 8) + 1260LL) )
  {
    v21 = *((_QWORD *)a3 + 8);
    *(_BYTE *)(v21 + 1260) = 1;
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v21 + 48) + 392LL) + 9347LL) = 1;
  }
  if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(
                       ((unsigned __int64)this + 8) & -(__int64)(this != 0),
                       0,
                       0) )
  {
    *((_BYTE *)this + 9098) = 1;
    HttpMethod = W3_REQUEST::GetHttpMethod(*((W3_REQUEST **)a3 + 6));
    IISGeneralEvents::GENERAL_CHILD_REQUEST_START::RaiseEvent(
      (struct IHttpTraceContext *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
      v24,
      v25,
      *(const unsigned __int16 **)(v23 + 72),
      HttpMethod,
      *((_DWORD *)a3 + 2020));
  }
  v26 = (NOTIFICATION_CONTEXT *)operator new(0x90u);
  v27 = v26;
  if ( !v26 )
  {
    v18 = -2147024888;
    goto LABEL_40;
  }
  NOTIFICATION_CONTEXT::NOTIFICATION_CONTEXT(v26, a3);
  *((_QWORD *)v27 + 17) = a3;
  *(_QWORD *)v27 = &NOTIFICATION_MAIN::`vftable';
  *((_QWORD *)a3 + 250) = v27;
  if ( (unsigned int)W3_CONTEXT_BASE::StartNotificationLoop(a3, v27, 0) )
  {
    if ( a6 )
      *a6 = 1;
  }
  else
  {
    W3_CONTEXT_BASE::FinishNotificationLoop(v27);
    if ( !a6 )
    {
      v18 = W3_CONTEXT_BASE::PostCompletion(this, 0, 0);
      goto LABEL_40;
    }
    *a6 = 0;
  }
  v18 = 0;
LABEL_40:
  if ( TokenHandle )
  {
    SetThreadToken(0, TokenHandle);
    CloseHandle(TokenHandle);
  }
  return v18;
}

```

## disassembly

```asm
0x180021af0  mov     [rsp+arg_8], rbx
0x180021af5  mov     [rsp+arg_18], rbp
0x180021afa  push    rsi
0x180021afb  push    rdi
0x180021afc  push    r12
0x180021afe  push    r14
0x180021b00  push    r15
0x180021b02  sub     rsp, 50h
0x180021b06  mov     rax, cs:__security_cookie
0x180021b0d  xor     rax, rsp
0x180021b10  mov     [rsp+78h+var_30], rax
0x180021b15  mov     r15, [rsp+78h+arg_28]
0x180021b1d  mov     r12d, edx
0x180021b20  mov     rdx, [rsp+78h+arg_20]
0x180021b28  mov     ebp, r9d
0x180021b2b  mov     r14, r8
0x180021b2e  mov     rsi, rcx
0x180021b31  test    r8, r8
0x180021b34  jnz     short loc_180021B40
0x180021b36  mov     eax, 80070057h
0x180021b3b  jmp     loc_180021E9A
0x180021b40  mov     [rsp+78h+TokenHandle], 0
0x180021b49  mov     edi, 1
0x180021b4e  test    rdx, rdx
0x180021b51  jz      short loc_180021B60
0x180021b53  lea     rcx, [r8+20h]
0x180021b57  mov     rax, [rcx]
0x180021b5a  mov     rax, [rax+8]
0x180021b5e  jmp     short loc_180021BA8
0x180021b60  cmp     byte ptr [rcx+170h], 0
0x180021b67  jz      short loc_180021BB4
0x180021b69  mov     rax, [rcx]
0x180021b6c  mov     rax, [rax+30h]
0x180021b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b75  mov     rdx, rax
0x180021b78  mov     rcx, [rax]
0x180021b7b  mov     rax, [rcx+30h]
0x180021b7f  mov     rcx, rdx
0x180021b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b87  mov     rax, [r14+20h]
0x180021b8b  mov     rcx, [rsi]
0x180021b8e  mov     rbx, [rax+8]
0x180021b92  mov     rax, [rcx+30h]
0x180021b96  mov     rcx, rsi
0x180021b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b9e  mov     rdx, rax
0x180021ba1  lea     rcx, [r14+20h]
0x180021ba5  mov     rax, rbx
0x180021ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bad  mov     [r14+170h], dil
0x180021bb4  test    r12d, r12d
0x180021bb7  jz      loc_180021E95
0x180021bbd  mov     rax, [r14]
0x180021bc0  mov     rcx, r14
0x180021bc3  mov     rax, [rax+0E8h]
0x180021bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bcf  cmp     rax, rsi
0x180021bd2  jnz     loc_180021E95
0x180021bd8  cmp     dword ptr [rsi+1F90h], 0Ah
0x180021bdf  jb      short loc_180021BEB
0x180021be1  mov     eax, 800703E9h
0x180021be6  jmp     loc_180021E9A
0x180021beb  call    cs:__imp_GetCurrentThread
0x180021bf2  nop     dword ptr [rax+rax+00h]
0x180021bf7  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x180021bfc  mov     r8d, edi; OpenAsSelf
0x180021bff  mov     rcx, rax; ThreadHandle
0x180021c02  mov     edx, 4; DesiredAccess
0x180021c07  call    cs:__imp_OpenThreadToken
0x180021c0e  nop     dword ptr [rax+rax+00h]
0x180021c13  test    eax, eax
0x180021c15  jnz     short loc_180021C4B
0x180021c17  call    cs:__imp_GetLastError
0x180021c1e  nop     dword ptr [rax+rax+00h]
0x180021c23  cmp     eax, 3F0h
0x180021c28  jz      short loc_180021C57
0x180021c2a  call    cs:__imp_GetLastError
0x180021c31  nop     dword ptr [rax+rax+00h]
0x180021c36  test    eax, eax
0x180021c38  jle     loc_180021E9A
0x180021c3e  movzx   eax, ax
0x180021c41  or      eax, 80070000h
0x180021c46  jmp     loc_180021E9A
0x180021c4b  call    cs:__imp_RevertToSelf
0x180021c52  nop     dword ptr [rax+rax+00h]
0x180021c57  mov     rax, [r14]
0x180021c5a  mov     rcx, r14
0x180021c5d  mov     rax, [rax+18h]
0x180021c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c66  mov     rdx, rax
0x180021c69  mov     rcx, [rax]
0x180021c6c  mov     rax, [rcx+90h]
0x180021c73  mov     rcx, rdx
0x180021c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c7b  cmp     eax, 0FFFFFFFFh
0x180021c7e  jnb     short loc_180021CF7
0x180021c80  mov     r9d, 0Ah; Radix
0x180021c86  lea     rdx, [rsp+78h+Buffer]; Buffer
0x180021c8b  mov     ecx, eax; Value
0x180021c8d  lea     r8d, [r9+6]; BufferCount
0x180021c91  call    cs:__imp__ultoa_s
0x180021c98  nop     dword ptr [rax+rax+00h]
0x180021c9d  test    eax, eax
0x180021c9f  jz      short loc_180021CAB
0x180021ca1  mov     ebx, 8000FFFFh
0x180021ca6  jmp     loc_180021E68
0x180021cab  mov     rax, [r14]
0x180021cae  mov     rcx, r14
0x180021cb1  mov     rax, [rax+18h]
0x180021cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cba  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021cbe  mov     rcx, [rax]
0x180021cc1  mov     r10, [rcx+20h]
0x180021cc5  lea     rcx, [rsp+78h+Buffer]
0x180021cca  inc     r9
0x180021ccd  cmp     byte ptr [rcx+r9], 0
0x180021cd2  jnz     short loc_180021CCA
0x180021cd4  mov     rcx, rax
0x180021cd7  mov     dword ptr [rsp+78h+var_58], edi
0x180021cdb  mov     rax, r10
0x180021cde  lea     r8, [rsp+78h+Buffer]
0x180021ce3  mov     edx, 0Bh
0x180021ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ced  mov     ebx, eax
0x180021cef  test    eax, eax
0x180021cf1  js      loc_180021E68
0x180021cf7  test    bpl, 40h
0x180021cfb  jnz     short loc_180021D14
0x180021cfd  mov     rax, [rsi]
0x180021d00  mov     edx, 8
0x180021d05  mov     rcx, rsi
0x180021d08  mov     rax, [rax+178h]
0x180021d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d14  mov     rax, [rsi]
0x180021d17  mov     rcx, rsi
0x180021d1a  mov     rax, [rax+70h]
0x180021d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d23  and     eax, 29h
0x180021d26  mov     rcx, rsi
0x180021d29  or      eax, ebp
0x180021d2b  mov     [r14+1F94h], eax
0x180021d32  mov     rax, [rsi]
0x180021d35  mov     rax, [rax+70h]
0x180021d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d3e  test    dil, al
0x180021d41  setz    cl
0x180021d44  test    bpl, 21h
0x180021d48  setz    al
0x180021d4b  test    al, cl
0x180021d4d  jz      short loc_180021D66
0x180021d4f  mov     rax, [rsi]
0x180021d52  mov     rcx, rsi
0x180021d55  mov     rax, [rax+70h]
0x180021d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d5e  or      eax, edi
0x180021d60  mov     [rsi+1F94h], eax
0x180021d66  mov     rax, [rsi+40h]
0x180021d6a  cmp     byte ptr [rax+4ECh], 0
0x180021d71  jz      short loc_180021D90
0x180021d73  mov     rax, [r14+40h]
0x180021d77  mov     [rax+4ECh], dil
0x180021d7e  mov     rax, [rax+30h]
0x180021d82  mov     rcx, [rax+188h]
0x180021d89  mov     [rcx+2483h], dil
0x180021d90  lea     rcx, [rsi+8]
0x180021d94  mov     rax, rsi
0x180021d97  neg     rax
0x180021d9a  sbb     rbx, rbx
0x180021d9d  xor     r8d, r8d
0x180021da0  and     rbx, rcx
0x180021da3  xor     edx, edx
0x180021da5  mov     rcx, rbx
0x180021da8  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180021dad  test    eax, eax
0x180021daf  jz      short loc_180021DE9
0x180021db1  mov     [rsi+238Ah], dil
0x180021db8  mov     rcx, [r14+30h]; this
0x180021dbc  mov     r9, [rcx+28h]
0x180021dc0  mov     r8, [r9+18h]
0x180021dc4  shr     r8, 20h
0x180021dc8  call    ?GetHttpMethod@W3_REQUEST@@QEBAPEBDXZ; W3_REQUEST::GetHttpMethod(void)
0x180021dcd  mov     ecx, [r14+1F90h]
0x180021dd4  mov     r9, [r9+48h]; unsigned __int16 *
0x180021dd8  mov     dword ptr [rsp+78h+var_50], ecx; char
0x180021ddc  mov     rcx, rbx; struct IHttpTraceContext *
0x180021ddf  mov     [rsp+78h+var_58], rax; char *
0x180021de4  call    ?RaiseEvent@GENERAL_CHILD_REQUEST_START@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KPEBGPEBDK@Z; IISGeneralEvents::GENERAL_CHILD_REQUEST_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ushort const *,char const *,ulong)
0x180021de9  mov     ecx, 90h; Size
0x180021dee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021df3  mov     rbx, rax
0x180021df6  test    rax, rax
0x180021df9  jz      short loc_180021E63
0x180021dfb  mov     rdx, r14; struct W3_CONTEXT_BASE *
0x180021dfe  mov     rcx, rax; this
0x180021e01  call    ??0NOTIFICATION_CONTEXT@@QEAA@PEAVW3_CONTEXT_BASE@@@Z; NOTIFICATION_CONTEXT::NOTIFICATION_CONTEXT(W3_CONTEXT_BASE *)
0x180021e06  lea     rax, ??_7NOTIFICATION_MAIN@@6B@; const NOTIFICATION_MAIN::`vftable'
0x180021e0d  mov     [rbx+88h], r14
0x180021e14  mov     [rbx], rax
0x180021e17  xor     r8d, r8d
0x180021e1a  mov     rdx, rbx
0x180021e1d  mov     [r14+7D0h], rbx
0x180021e24  mov     rcx, r14
0x180021e27  call    ?StartNotificationLoop@W3_CONTEXT_BASE@@QEAA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@H@Z; W3_CONTEXT_BASE::StartNotificationLoop(NOTIFICATION_CONTEXT *,int)
0x180021e2c  test    eax, eax
0x180021e2e  jnz     short loc_180021E59
0x180021e30  mov     rcx, rbx
0x180021e33  call    ?FinishNotificationLoop@W3_CONTEXT_BASE@@SA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@@Z; W3_CONTEXT_BASE::FinishNotificationLoop(NOTIFICATION_CONTEXT *)
0x180021e38  test    r15, r15
0x180021e3b  jz      short loc_180021E48
0x180021e3d  mov     dword ptr [r15], 0
0x180021e44  xor     ebx, ebx
0x180021e46  jmp     short loc_180021E68
0x180021e48  xor     r8d, r8d; unsigned int
0x180021e4b  xor     edx, edx; unsigned int
0x180021e4d  mov     rcx, rsi; this
0x180021e50  call    ?PostCompletion@W3_CONTEXT_BASE@@QEAAJKK@Z; W3_CONTEXT_BASE::PostCompletion(ulong,ulong)
0x180021e55  mov     ebx, eax
0x180021e57  jmp     short loc_180021E68
0x180021e59  test    r15, r15
0x180021e5c  jz      short loc_180021E44
0x180021e5e  mov     [r15], edi
0x180021e61  jmp     short loc_180021E44
0x180021e63  mov     ebx, 80070008h
0x180021e68  mov     rdx, [rsp+78h+TokenHandle]; Token
0x180021e6d  test    rdx, rdx
0x180021e70  jz      short loc_180021E91
0x180021e72  xor     ecx, ecx; Thread
0x180021e74  call    cs:__imp_SetThreadToken
0x180021e7b  nop     dword ptr [rax+rax+00h]
0x180021e80  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x180021e85  call    cs:__imp_CloseHandle
0x180021e8c  nop     dword ptr [rax+rax+00h]
0x180021e91  mov     eax, ebx
0x180021e93  jmp     short loc_180021E9A
0x180021e95  mov     eax, 80070032h
0x180021e9a  mov     rcx, [rsp+78h+var_30]
0x180021e9f  xor     rcx, rsp; StackCookie
0x180021ea2  call    __security_check_cookie
0x180021ea7  lea     r11, [rsp+78h+var_28]
0x180021eac  mov     rbx, [r11+38h]
0x180021eb0  mov     rbp, [r11+48h]
0x180021eb4  mov     rsp, r11
0x180021eb7  pop     r15
0x180021eb9  pop     r14
0x180021ebb  pop     r12
0x180021ebd  pop     rdi
0x180021ebe  pop     rsi
0x180021ebf  retn
```
