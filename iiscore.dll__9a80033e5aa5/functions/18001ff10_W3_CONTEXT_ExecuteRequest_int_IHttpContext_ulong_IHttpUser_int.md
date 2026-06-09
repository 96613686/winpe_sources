# W3_CONTEXT::ExecuteRequest(int,IHttpContext *,ulong,IHttpUser *,int *)

- ea: `0x18001ff10`
- end: `0x1800202b0`
- name: `?ExecuteRequest@W3_CONTEXT@@UEAAJHPEAVIHttpContext@@KPEAVIHttpUser@@PEAH@Z`
- size: `928`
- prototype: `__int64 __usercall@<rax>(W3_CONTEXT *__hidden this@<rcx>, int@<edx>, struct IHttpContext *@<r8>, unsigned int@<r9d>, struct IHttpUser *, int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002040`
- `0x180004b2c`
- `0x180008930`
- `0x1800093d0`
- `0x180014c00`
- `0x180019558`
- `0x18001ff10`
- `0x180021578`
- `0x180023df4`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_ultoa_s` at `0x180020093`
- `msvcrt!_ultoa_s` at `0x180020093`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002000b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002000b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180020270`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180020270`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020021`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020021`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002027b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002027b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002002b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002002b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020038`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180020053`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180020053`

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
0x18001ff10  mov     [rsp+arg_8], rbx
0x18001ff15  mov     [rsp+arg_18], rbp
0x18001ff1a  push    rsi
0x18001ff1b  push    rdi
0x18001ff1c  push    r12
0x18001ff1e  push    r14
0x18001ff20  push    r15
0x18001ff22  sub     rsp, 50h
0x18001ff26  mov     rax, cs:__security_cookie
0x18001ff2d  xor     rax, rsp
0x18001ff30  mov     [rsp+78h+var_30], rax
0x18001ff35  mov     r15, [rsp+78h+arg_28]
0x18001ff3d  mov     r12d, edx
0x18001ff40  mov     rdx, [rsp+78h+arg_20]
0x18001ff48  mov     ebp, r9d
0x18001ff4b  mov     r14, r8
0x18001ff4e  mov     rsi, rcx
0x18001ff51  test    r8, r8
0x18001ff54  jnz     short loc_18001FF60
0x18001ff56  mov     eax, 80070057h
0x18001ff5b  jmp     loc_18002028A
0x18001ff60  mov     [rsp+78h+TokenHandle], 0
0x18001ff69  mov     edi, 1
0x18001ff6e  test    rdx, rdx
0x18001ff71  jz      short loc_18001FF80
0x18001ff73  lea     rcx, [r8+20h]
0x18001ff77  mov     rax, [rcx]
0x18001ff7a  mov     rax, [rax+8]
0x18001ff7e  jmp     short loc_18001FFC8
0x18001ff80  cmp     byte ptr [rcx+170h], 0
0x18001ff87  jz      short loc_18001FFD4
0x18001ff89  mov     rax, [rcx]
0x18001ff8c  mov     rax, [rax+30h]
0x18001ff90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff95  mov     rdx, rax
0x18001ff98  mov     rcx, [rax]
0x18001ff9b  mov     rax, [rcx+30h]
0x18001ff9f  mov     rcx, rdx
0x18001ffa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffa7  mov     rax, [r14+20h]
0x18001ffab  mov     rcx, [rsi]
0x18001ffae  mov     rbx, [rax+8]
0x18001ffb2  mov     rax, [rcx+30h]
0x18001ffb6  mov     rcx, rsi
0x18001ffb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffbe  mov     rdx, rax
0x18001ffc1  lea     rcx, [r14+20h]
0x18001ffc5  mov     rax, rbx
0x18001ffc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffcd  mov     [r14+170h], dil
0x18001ffd4  test    r12d, r12d
0x18001ffd7  jz      loc_180020285
0x18001ffdd  mov     rax, [r14]
0x18001ffe0  mov     rcx, r14
0x18001ffe3  mov     rax, [rax+0E8h]
0x18001ffea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffef  cmp     rax, rsi
0x18001fff2  jnz     loc_180020285
0x18001fff8  cmp     dword ptr [rsi+1F90h], 0Ah
0x18001ffff  jb      short loc_18002000B
0x180020001  mov     eax, 800703E9h
0x180020006  jmp     loc_18002028A
0x18002000b  call    cs:__imp_GetCurrentThread
0x180020011  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x180020016  mov     r8d, edi; OpenAsSelf
0x180020019  mov     rcx, rax; ThreadHandle
0x18002001c  mov     edx, 4; DesiredAccess
0x180020021  call    cs:__imp_OpenThreadToken
0x180020027  test    eax, eax
0x180020029  jnz     short loc_180020053
0x18002002b  call    cs:__imp_GetLastError
0x180020031  cmp     eax, 3F0h
0x180020036  jz      short loc_180020059
0x180020038  call    cs:__imp_GetLastError
0x18002003e  test    eax, eax
0x180020040  jle     loc_18002028A
0x180020046  movzx   eax, ax
0x180020049  or      eax, 80070000h
0x18002004e  jmp     loc_18002028A
0x180020053  call    cs:__imp_RevertToSelf
0x180020059  mov     rax, [r14]
0x18002005c  mov     rcx, r14
0x18002005f  mov     rax, [rax+18h]
0x180020063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020068  mov     rdx, rax
0x18002006b  mov     rcx, [rax]
0x18002006e  mov     rax, [rcx+90h]
0x180020075  mov     rcx, rdx
0x180020078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002007d  cmp     eax, 0FFFFFFFFh
0x180020080  jnb     short loc_1800200F3
0x180020082  mov     r9d, 0Ah; Radix
0x180020088  lea     rdx, [rsp+78h+Buffer]; Buffer
0x18002008d  mov     ecx, eax; Value
0x18002008f  lea     r8d, [r9+6]; BufferCount
0x180020093  call    cs:__imp__ultoa_s
0x180020099  test    eax, eax
0x18002009b  jz      short loc_1800200A7
0x18002009d  mov     ebx, 8000FFFFh
0x1800200a2  jmp     loc_180020264
0x1800200a7  mov     rax, [r14]
0x1800200aa  mov     rcx, r14
0x1800200ad  mov     rax, [rax+18h]
0x1800200b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200b6  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800200ba  mov     rcx, [rax]
0x1800200bd  mov     r10, [rcx+20h]
0x1800200c1  lea     rcx, [rsp+78h+Buffer]
0x1800200c6  inc     r9
0x1800200c9  cmp     byte ptr [rcx+r9], 0
0x1800200ce  jnz     short loc_1800200C6
0x1800200d0  mov     rcx, rax
0x1800200d3  mov     dword ptr [rsp+78h+var_58], edi
0x1800200d7  mov     rax, r10
0x1800200da  lea     r8, [rsp+78h+Buffer]
0x1800200df  mov     edx, 0Bh
0x1800200e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200e9  mov     ebx, eax
0x1800200eb  test    eax, eax
0x1800200ed  js      loc_180020264
0x1800200f3  test    bpl, 40h
0x1800200f7  jnz     short loc_180020110
0x1800200f9  mov     rax, [rsi]
0x1800200fc  mov     edx, 8
0x180020101  mov     rcx, rsi
0x180020104  mov     rax, [rax+178h]
0x18002010b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020110  mov     rax, [rsi]
0x180020113  mov     rcx, rsi
0x180020116  mov     rax, [rax+70h]
0x18002011a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002011f  and     eax, 29h
0x180020122  mov     rcx, rsi
0x180020125  or      eax, ebp
0x180020127  mov     [r14+1F94h], eax
0x18002012e  mov     rax, [rsi]
0x180020131  mov     rax, [rax+70h]
0x180020135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002013a  test    dil, al
0x18002013d  setz    cl
0x180020140  test    bpl, 21h
0x180020144  setz    al
0x180020147  test    al, cl
0x180020149  jz      short loc_180020162
0x18002014b  mov     rax, [rsi]
0x18002014e  mov     rcx, rsi
0x180020151  mov     rax, [rax+70h]
0x180020155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002015a  or      eax, edi
0x18002015c  mov     [rsi+1F94h], eax
0x180020162  mov     rax, [rsi+40h]
0x180020166  cmp     byte ptr [rax+4ECh], 0
0x18002016d  jz      short loc_18002018C
0x18002016f  mov     rax, [r14+40h]
0x180020173  mov     [rax+4ECh], dil
0x18002017a  mov     rax, [rax+30h]
0x18002017e  mov     rcx, [rax+188h]
0x180020185  mov     [rcx+2483h], dil
0x18002018c  lea     rcx, [rsi+8]
0x180020190  mov     rax, rsi
0x180020193  neg     rax
0x180020196  sbb     rbx, rbx
0x180020199  xor     r8d, r8d
0x18002019c  and     rbx, rcx
0x18002019f  xor     edx, edx
0x1800201a1  mov     rcx, rbx
0x1800201a4  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800201a9  test    eax, eax
0x1800201ab  jz      short loc_1800201E5
0x1800201ad  mov     [rsi+238Ah], dil
0x1800201b4  mov     rcx, [r14+30h]; this
0x1800201b8  mov     r9, [rcx+28h]
0x1800201bc  mov     r8, [r9+18h]
0x1800201c0  shr     r8, 20h
0x1800201c4  call    ?GetHttpMethod@W3_REQUEST@@QEBAPEBDXZ; W3_REQUEST::GetHttpMethod(void)
0x1800201c9  mov     ecx, [r14+1F90h]
0x1800201d0  mov     r9, [r9+48h]; unsigned __int16 *
0x1800201d4  mov     dword ptr [rsp+78h+var_50], ecx; char
0x1800201d8  mov     rcx, rbx; struct IHttpTraceContext *
0x1800201db  mov     [rsp+78h+var_58], rax; char *
0x1800201e0  call    ?RaiseEvent@GENERAL_CHILD_REQUEST_START@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KPEBGPEBDK@Z; IISGeneralEvents::GENERAL_CHILD_REQUEST_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ushort const *,char const *,ulong)
0x1800201e5  mov     ecx, 90h; Size
0x1800201ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800201ef  mov     rbx, rax
0x1800201f2  test    rax, rax
0x1800201f5  jz      short loc_18002025F
0x1800201f7  mov     rdx, r14; struct W3_CONTEXT_BASE *
0x1800201fa  mov     rcx, rax; this
0x1800201fd  call    ??0NOTIFICATION_CONTEXT@@QEAA@PEAVW3_CONTEXT_BASE@@@Z; NOTIFICATION_CONTEXT::NOTIFICATION_CONTEXT(W3_CONTEXT_BASE *)
0x180020202  lea     rax, ??_7NOTIFICATION_MAIN@@6B@; const NOTIFICATION_MAIN::`vftable'
0x180020209  mov     [rbx+88h], r14
0x180020210  mov     [rbx], rax
0x180020213  xor     r8d, r8d
0x180020216  mov     rdx, rbx
0x180020219  mov     [r14+7D0h], rbx
0x180020220  mov     rcx, r14
0x180020223  call    ?StartNotificationLoop@W3_CONTEXT_BASE@@QEAA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@H@Z; W3_CONTEXT_BASE::StartNotificationLoop(NOTIFICATION_CONTEXT *,int)
0x180020228  test    eax, eax
0x18002022a  jnz     short loc_180020255
0x18002022c  mov     rcx, rbx
0x18002022f  call    ?FinishNotificationLoop@W3_CONTEXT_BASE@@SA?AW4ASYNC_STATUS@@PEAVNOTIFICATION_CONTEXT@@@Z; W3_CONTEXT_BASE::FinishNotificationLoop(NOTIFICATION_CONTEXT *)
0x180020234  test    r15, r15
0x180020237  jz      short loc_180020244
0x180020239  mov     dword ptr [r15], 0
0x180020240  xor     ebx, ebx
0x180020242  jmp     short loc_180020264
0x180020244  xor     r8d, r8d; unsigned int
0x180020247  xor     edx, edx; unsigned int
0x180020249  mov     rcx, rsi; this
0x18002024c  call    ?PostCompletion@W3_CONTEXT_BASE@@QEAAJKK@Z; W3_CONTEXT_BASE::PostCompletion(ulong,ulong)
0x180020251  mov     ebx, eax
0x180020253  jmp     short loc_180020264
0x180020255  test    r15, r15
0x180020258  jz      short loc_180020240
0x18002025a  mov     [r15], edi
0x18002025d  jmp     short loc_180020240
0x18002025f  mov     ebx, 80070008h
0x180020264  mov     rdx, [rsp+78h+TokenHandle]; Token
0x180020269  test    rdx, rdx
0x18002026c  jz      short loc_180020281
0x18002026e  xor     ecx, ecx; Thread
0x180020270  call    cs:__imp_SetThreadToken
0x180020276  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x18002027b  call    cs:__imp_CloseHandle
0x180020281  mov     eax, ebx
0x180020283  jmp     short loc_18002028A
0x180020285  mov     eax, 80070032h
0x18002028a  mov     rcx, [rsp+78h+var_30]
0x18002028f  xor     rcx, rsp; StackCookie
0x180020292  call    __security_check_cookie
0x180020297  lea     r11, [rsp+78h+var_28]
0x18002029c  mov     rbx, [r11+38h]
0x1800202a0  mov     rbp, [r11+48h]
0x1800202a4  mov     rsp, r11
0x1800202a7  pop     r15
0x1800202a9  pop     r14
0x1800202ab  pop     r12
0x1800202ad  pop     rdi
0x1800202ae  pop     rsi
0x1800202af  retn
```
