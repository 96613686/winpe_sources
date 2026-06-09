# W3_FILTER_CONTEXT::ServerSupportFunction(_HTTP_FILTER_CONTEXT *,SF_REQ_TYPE,void *,unsigned __int64,unsigned __int64)

- ea: `0x180007d40`
- end: `0x180008233`
- name: `?ServerSupportFunction@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@W4SF_REQ_TYPE@@PEAX_K3@Z`
- size: `1267`
- prototype: `__int64 __fastcall(struct _HTTP_FILTER_CONTEXT *, int, void *, char *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x1800057a0`
- `0x180005b20`
- `0x180007490`
- `0x180007d40`
- `0x180008240`
- `0x18000aa50`
- `0x18000abdc`
- `0x18000af48`
- `0x18000c970`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008200`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000821c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008200`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000821c`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180007e74`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180007f66`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180007f7f`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180008039`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180008052`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180007e74`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180007f66`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180007f7f`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180008039`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180008052`
- `iisutil!NormalizeUrl` at `0x18000819b`
- `iisutil!NormalizeUrl` at `0x18000819b`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180007f97`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000806a`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180007f97`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000806a`
- `iisutil!?QuerySizeCCH@STRA@@QEBAKXZ` at `0x180008099`
- `iisutil!?QuerySizeCCH@STRA@@QEBAKXZ` at `0x180008099`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007ff5`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000807c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007ff5`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000807c`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180008004`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000808b`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180008004`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000808b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007e25`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000820a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008226`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007e25`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000820a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008226`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180007d83`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180007d83`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180007f51`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180008024`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180007f51`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180008024`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::ServerSupportFunction(
        struct _HTTP_FILTER_CONTEXT *a1,
        int a2,
        void *a3,
        char *a4)
{
  char *ServerContext; // rdi
  struct IHttpContext *v9; // rsi
  int v10; // ebx
  __int64 v11; // rax
  int v12; // eax
  int CertificateInfo; // eax
  char *v15; // r12
  __int64 v16; // rbx
  struct IHttpResponse *v17; // rax
  __int64 v18; // rax
  DWORD cbInData; // eax
  DWORD SizeCCH; // eax
  int v21; // ebx
  __int64 v22; // rax
  PVOID pvInData; // rax
  __int64 v24; // rax
  DWORD v25; // eax
  unsigned int v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v29; // [rsp+58h] [rbp-A8h]
  _HTTP_FILTER_RAW_DATA v30; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v31[64]; // [rsp+80h] [rbp-80h] BYREF
  char v32[256]; // [rsp+C0h] [rbp-40h] BYREF

  STRA::STRA((STRA *)v31, v32, 0x100u);
  v27 = 0;
  v28 = 0;
  v29 = 0;
  if ( !a1 || (ServerContext = (char *)a1->ServerContext) == 0 )
  {
    SetLastError(0x57u);
    STRA::~STRA((STRA *)v31);
    return 0;
  }
  v9 = (struct IHttpContext *)*((_QWORD *)ServerContext + 3);
  if ( a2 > 7 )
  {
    if ( a2 == 8 )
    {
      CertificateInfo = W3_FILTER_CONTEXT::DisableNotification((W3_FILTER_CONTEXT *)ServerContext, (unsigned int)a4);
    }
    else
    {
      if ( a2 != 1015 || !v9 )
        goto LABEL_15;
      CertificateInfo = GetCertificateInfoEx(
                          v9,
                          *((_DWORD *)a3 + 10),
                          (unsigned int *)a3,
                          *((unsigned __int8 **)a3 + 1),
                          (unsigned int *)a3 + 4,
                          (unsigned int *)a3 + 11);
    }
LABEL_61:
    if ( CertificateInfo < 0 )
      goto LABEL_62;
    goto LABEL_13;
  }
  if ( a2 == 7 )
  {
    if ( !a3 )
    {
      CertificateInfo = -2147024809;
      goto LABEL_62;
    }
    CertificateInfo = NormalizeUrl((char *)a3);
    goto LABEL_61;
  }
  if ( a2 )
  {
    v10 = a2 - 1;
    if ( v10 )
    {
      if ( v10 == 5 && a4 == (char *)1 )
      {
        if ( v9 )
        {
          v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v9 + 24LL))(v9);
          v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 176LL))(v11);
        }
        else
        {
          v12 = 0;
        }
        *(_DWORD *)a3 = v12;
        goto LABEL_13;
      }
      goto LABEL_15;
    }
    CertificateInfo = STRA::Append((STRA *)(ServerContext + 288), (const char *)a3);
    goto LABEL_61;
  }
  if ( !v9 )
  {
LABEL_15:
    CertificateInfo = -2147024846;
LABEL_62:
    v25 = WIN32_FROM_HRESULT(CertificateInfo);
    SetLastError(v25);
    STRA::~STRA((STRA *)v31);
    return 0;
  }
  v15 = "200 OK";
  if ( a3 )
    v15 = (char *)a3;
  if ( a4 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a4[v16] );
  }
  else
  {
    a4 = "\r\n";
    LODWORD(v16) = 2;
  }
  if ( *((_DWORD *)ServerContext + 35)
    || *((_DWORD *)ServerContext + 36)
    && (unsigned int)W3_FILTER_CONTEXT::IsNotificationNeeded((W3_FILTER_CONTEXT *)ServerContext, 0x400u) )
  {
    *(_QWORD *)&v30.dwReserved = 0;
    v26 = 0;
    CertificateInfo = STRA::Copy((STRA *)v31, "HTTP/1.1 ");
    if ( CertificateInfo < 0 )
      goto LABEL_62;
    CertificateInfo = STRA::Append((STRA *)v31, v15);
    if ( CertificateInfo < 0 )
      goto LABEL_62;
    CertificateInfo = STRA::Append((STRA *)v31, "\r\n");
    if ( CertificateInfo < 0 )
      goto LABEL_62;
    CertificateInfo = STRA::Append((STRA *)v31, a4, v16);
    if ( CertificateInfo < 0 )
      goto LABEL_62;
    v30.pvInData = STRA::QueryStr((STRA *)v31);
    v30.cbInData = STRA::QueryCCH((STRA *)v31);
    SizeCCH = STRA::QuerySizeCCH((STRA *)v31);
    v21 = *((_DWORD *)ServerContext + 35);
    v30.cbInBuffer = SizeCCH;
    *((_DWORD *)ServerContext + 35) = 1;
    CertificateInfo = W3_FILTER_CONTEXT::NotifySendRawFilters((W3_FILTER_CONTEXT *)ServerContext, &v30, (int *)&v26);
    *((_DWORD *)ServerContext + 35) = v21;
    if ( CertificateInfo < 0 )
      goto LABEL_62;
    if ( v26 )
      goto LABEL_13;
    if ( !(*(unsigned int (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v9 + 40LL))(v9)
      && !*((_DWORD *)ServerContext + 100) )
    {
      v22 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v9 + 32LL))(v9);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 128LL))(v22);
    }
    pvInData = v30.pvInData;
    *((_DWORD *)ServerContext + 100) = 1;
    *((_QWORD *)&v28 + 1) = pvInData;
    cbInData = v30.cbInData;
    LODWORD(v28) = 0;
    goto LABEL_51;
  }
  if ( (*(unsigned int (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v9 + 40LL))(v9)
    || *((_DWORD *)ServerContext + 100)
    || !(unsigned int)CheckForEndofHeaders(a4, v16, &v26) )
  {
    CertificateInfo = STRA::Copy((STRA *)v31, "HTTP/1.1 ");
    if ( CertificateInfo < 0 )
      goto LABEL_62;
    CertificateInfo = STRA::Append((STRA *)v31, v15);
    if ( CertificateInfo < 0 )
      goto LABEL_62;
    CertificateInfo = STRA::Append((STRA *)v31, "\r\n");
    if ( CertificateInfo < 0 )
      goto LABEL_62;
    CertificateInfo = STRA::Append((STRA *)v31, a4, v16);
    if ( CertificateInfo < 0 )
      goto LABEL_62;
    if ( !(*(unsigned int (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v9 + 40LL))(v9)
      && !*((_DWORD *)ServerContext + 100) )
    {
      v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v9 + 32LL))(v9);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 128LL))(v18);
    }
    *((_DWORD *)ServerContext + 100) = 1;
    LODWORD(v28) = 0;
    *((_QWORD *)&v28 + 1) = STRA::QueryStr((STRA *)v31);
    cbInData = STRA::QueryCCH((STRA *)v31);
LABEL_51:
    LODWORD(v29) = cbInData;
    v24 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v9 + 32LL))(v9);
    CertificateInfo = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, int, int *, _QWORD))(*(_QWORD *)v24 + 168LL))(
                        v24,
                        &v28,
                        1,
                        0,
                        1,
                        &v27,
                        0);
    if ( CertificateInfo < 0 )
      goto LABEL_62;
    goto LABEL_13;
  }
  *((_DWORD *)ServerContext + 100) = 1;
  v17 = (struct IHttpResponse *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v9 + 32LL))(v9);
  CertificateInfo = SetStatusAndHeaders(v17, v15, a4, v16);
  if ( CertificateInfo < 0 )
    goto LABEL_62;
LABEL_13:
  STRA::~STRA((STRA *)v31);
  return 1;
}

```

## disassembly

```asm
0x180007d40  push    rbp
0x180007d42  push    rbx
0x180007d43  push    rdi
0x180007d44  push    r13
0x180007d46  push    r14
0x180007d48  push    r15
0x180007d4a  lea     rbp, [rsp-0D8h]
0x180007d52  sub     rsp, 1D8h
0x180007d59  mov     rax, cs:__security_cookie
0x180007d60  xor     rax, rsp
0x180007d63  mov     [rbp+100h+var_40], rax
0x180007d6a  mov     r15, r8
0x180007d6d  mov     ebx, edx
0x180007d6f  mov     rdi, rcx
0x180007d72  lea     rdx, [rbp+100h+var_140]
0x180007d76  mov     r8d, 100h
0x180007d7c  lea     rcx, [rbp+100h+var_180]
0x180007d80  mov     r14, r9
0x180007d83  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180007d89  xor     r13d, r13d
0x180007d8c  xorps   xmm0, xmm0
0x180007d8f  mov     [rsp+200h+var_1BC], r13d
0x180007d94  movups  [rsp+200h+var_1B8], xmm0
0x180007d99  movups  [rsp+200h+var_1A8], xmm0
0x180007d9e  test    rdi, rdi
0x180007da1  jz      loc_180008217
0x180007da7  mov     rdi, [rdi+8]
0x180007dab  test    rdi, rdi
0x180007dae  jz      loc_180008217
0x180007db4  mov     [rsp+200h+arg_8], rsi
0x180007dbc  mov     rsi, [rdi+18h]
0x180007dc0  mov     [rsp+200h+var_30], r12
0x180007dc8  cmp     ebx, 7
0x180007dcb  jg      loc_1800081A3
0x180007dd1  jz      loc_18000818C
0x180007dd7  test    ebx, ebx
0x180007dd9  jz      loc_180007E7F
0x180007ddf  sub     ebx, 1
0x180007de2  jz      loc_180007E6A
0x180007de8  cmp     ebx, 5
0x180007deb  jnz     short loc_180007E60
0x180007ded  cmp     r14, 1
0x180007df1  jnz     short loc_180007E60
0x180007df3  test    rsi, rsi
0x180007df6  jz      short loc_180007E1B
0x180007df8  mov     rax, [rsi]
0x180007dfb  mov     rcx, rsi
0x180007dfe  mov     rax, [rax+18h]
0x180007e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e07  mov     rcx, rax
0x180007e0a  mov     rax, [rax]
0x180007e0d  mov     rax, [rax+0B0h]
0x180007e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e19  jmp     short loc_180007E1E
0x180007e1b  mov     eax, r13d
0x180007e1e  mov     [r15], eax
0x180007e21  lea     rcx, [rbp+100h+var_180]
0x180007e25  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007e2b  mov     eax, 1
0x180007e30  mov     r12, [rsp+200h+var_30]
0x180007e38  mov     rsi, [rsp+200h+arg_8]
0x180007e40  mov     rcx, [rbp+100h+var_40]
0x180007e47  xor     rcx, rsp; StackCookie
0x180007e4a  call    __security_check_cookie
0x180007e4f  add     rsp, 1D8h
0x180007e56  pop     r15
0x180007e58  pop     r14
0x180007e5a  pop     r13
0x180007e5c  pop     rdi
0x180007e5d  pop     rbx
0x180007e5e  pop     rbp
0x180007e5f  retn
0x180007e60  mov     eax, 80070032h
0x180007e65  jmp     loc_1800081F7
0x180007e6a  lea     rcx, [rdi+120h]
0x180007e71  mov     rdx, r15
0x180007e74  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180007e7a  jmp     loc_1800081EF
0x180007e7f  test    rsi, rsi
0x180007e82  jz      short loc_180007E60
0x180007e84  test    r15, r15
0x180007e87  lea     r12, a200Ok; "200 OK"
0x180007e8e  cmovnz  r12, r15
0x180007e92  test    r14, r14
0x180007e95  jz      short loc_180007EA9
0x180007e97  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180007e9e  inc     rbx
0x180007ea1  cmp     [r14+rbx], r13b
0x180007ea5  jnz     short loc_180007E9E
0x180007ea7  jmp     short loc_180007EB5
0x180007ea9  lea     r14, SubStr; "\r\n"
0x180007eb0  mov     ebx, 2
0x180007eb5  cmp     [rdi+8Ch], r13d
0x180007ebc  jnz     loc_18000800F
0x180007ec2  cmp     [rdi+90h], r13d
0x180007ec9  jz      short loc_180007EE0
0x180007ecb  mov     edx, 400h; unsigned int
0x180007ed0  mov     rcx, rdi; this
0x180007ed3  call    ?IsNotificationNeeded@W3_FILTER_CONTEXT@@QEAAHK@Z; W3_FILTER_CONTEXT::IsNotificationNeeded(ulong)
0x180007ed8  test    eax, eax
0x180007eda  jnz     loc_18000800F
0x180007ee0  mov     rax, [rsi]
0x180007ee3  mov     rcx, rsi
0x180007ee6  mov     rax, [rax+28h]
0x180007eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eef  test    eax, eax
0x180007ef1  jnz     short loc_180007F46
0x180007ef3  cmp     [rdi+190h], r13d
0x180007efa  jnz     short loc_180007F46
0x180007efc  lea     r8, [rsp+200h+var_1C0]; unsigned int *
0x180007f01  mov     edx, ebx; unsigned int
0x180007f03  mov     rcx, r14; char *
0x180007f06  call    ?CheckForEndofHeaders@@YAHPEADKPEAK@Z; CheckForEndofHeaders(char *,ulong,ulong *)
0x180007f0b  test    eax, eax
0x180007f0d  jz      short loc_180007F46
0x180007f0f  mov     dword ptr [rdi+190h], 1
0x180007f19  mov     rcx, rsi
0x180007f1c  mov     rax, [rsi]
0x180007f1f  mov     rax, [rax+20h]
0x180007f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f28  mov     rcx, rax; struct IHttpResponse *
0x180007f2b  mov     r9d, ebx; unsigned int
0x180007f2e  mov     r8, r14; char *
0x180007f31  mov     rdx, r12; String
0x180007f34  call    ?SetStatusAndHeaders@@YAJPEAVIHttpResponse@@PEAD1K@Z; SetStatusAndHeaders(IHttpResponse *,char *,char *,ulong)
0x180007f39  test    eax, eax
0x180007f3b  js      loc_1800081F7
0x180007f41  jmp     loc_180007E21
0x180007f46  lea     rdx, Str2; "HTTP/1.1 "
0x180007f4d  lea     rcx, [rbp+100h+var_180]
0x180007f51  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180007f57  test    eax, eax
0x180007f59  js      loc_1800081F7
0x180007f5f  mov     rdx, r12
0x180007f62  lea     rcx, [rbp+100h+var_180]
0x180007f66  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180007f6c  test    eax, eax
0x180007f6e  js      loc_1800081F7
0x180007f74  lea     rdx, SubStr; "\r\n"
0x180007f7b  lea     rcx, [rbp+100h+var_180]
0x180007f7f  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180007f85  test    eax, eax
0x180007f87  js      loc_1800081F7
0x180007f8d  mov     r8d, ebx
0x180007f90  lea     rcx, [rbp+100h+var_180]
0x180007f94  mov     rdx, r14
0x180007f97  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180007f9d  test    eax, eax
0x180007f9f  js      loc_1800081F7
0x180007fa5  mov     rax, [rsi]
0x180007fa8  mov     rcx, rsi
0x180007fab  mov     rax, [rax+28h]
0x180007faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fb4  test    eax, eax
0x180007fb6  jnz     short loc_180007FE2
0x180007fb8  cmp     [rdi+190h], r13d
0x180007fbf  jnz     short loc_180007FE2
0x180007fc1  mov     rax, [rsi]
0x180007fc4  mov     rcx, rsi
0x180007fc7  mov     rax, [rax+20h]
0x180007fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fd0  mov     rcx, rax
0x180007fd3  mov     rax, [rax]
0x180007fd6  mov     rax, [rax+80h]
0x180007fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fe2  mov     dword ptr [rdi+190h], 1
0x180007fec  lea     rcx, [rbp+100h+var_180]
0x180007ff0  mov     dword ptr [rsp+200h+var_1B8], r13d
0x180007ff5  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180007ffb  lea     rcx, [rbp+100h+var_180]
0x180007fff  mov     qword ptr [rsp+200h+var_1B8+8], rax
0x180008004  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18000800a  jmp     loc_180008138
0x18000800f  lea     rdx, Str2; "HTTP/1.1 "
0x180008016  mov     qword ptr [rsp+200h+var_198.dwReserved], r13
0x18000801b  lea     rcx, [rbp+100h+var_180]
0x18000801f  mov     [rsp+200h+var_1C0], r13d
0x180008024  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000802a  test    eax, eax
0x18000802c  js      loc_1800081F7
0x180008032  mov     rdx, r12
0x180008035  lea     rcx, [rbp+100h+var_180]
0x180008039  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000803f  test    eax, eax
0x180008041  js      loc_1800081F7
0x180008047  lea     rdx, SubStr; "\r\n"
0x18000804e  lea     rcx, [rbp+100h+var_180]
0x180008052  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180008058  test    eax, eax
0x18000805a  js      loc_1800081F7
0x180008060  mov     r8d, ebx
0x180008063  lea     rcx, [rbp+100h+var_180]
0x180008067  mov     rdx, r14
0x18000806a  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180008070  test    eax, eax
0x180008072  js      loc_1800081F7
0x180008078  lea     rcx, [rbp+100h+var_180]
0x18000807c  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180008082  lea     rcx, [rbp+100h+var_180]
0x180008086  mov     [rsp+200h+var_198.pvInData], rax
0x18000808b  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180008091  lea     rcx, [rbp+100h+var_180]
0x180008095  mov     [rsp+200h+var_198.cbInData], eax
0x180008099  call    cs:__imp_?QuerySizeCCH@STRA@@QEBAKXZ; STRA::QuerySizeCCH(void)
0x18000809f  mov     ebx, [rdi+8Ch]
0x1800080a5  lea     r8, [rsp+200h+var_1C0]; int *
0x1800080aa  lea     rdx, [rsp+200h+var_198]; struct _HTTP_FILTER_RAW_DATA *
0x1800080af  mov     [rsp+200h+var_198.cbInBuffer], eax
0x1800080b3  mov     rcx, rdi; this
0x1800080b6  mov     dword ptr [rdi+8Ch], 1
0x1800080c0  call    ?NotifySendRawFilters@W3_FILTER_CONTEXT@@QEAAJPEAU_HTTP_FILTER_RAW_DATA@@PEAH@Z; W3_FILTER_CONTEXT::NotifySendRawFilters(_HTTP_FILTER_RAW_DATA *,int *)
0x1800080c5  mov     [rdi+8Ch], ebx
0x1800080cb  test    eax, eax
0x1800080cd  js      loc_1800081F7
0x1800080d3  cmp     [rsp+200h+var_1C0], r13d
0x1800080d8  jnz     loc_180007E21
0x1800080de  mov     rax, [rsi]
0x1800080e1  mov     rcx, rsi
0x1800080e4  mov     rax, [rax+28h]
0x1800080e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080ed  test    eax, eax
0x1800080ef  jnz     short loc_18000811B
0x1800080f1  cmp     [rdi+190h], r13d
0x1800080f8  jnz     short loc_18000811B
0x1800080fa  mov     rax, [rsi]
0x1800080fd  mov     rcx, rsi
0x180008100  mov     rax, [rax+20h]
0x180008104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008109  mov     rcx, rax
0x18000810c  mov     rax, [rax]
0x18000810f  mov     rax, [rax+80h]
0x180008116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000811b  mov     rax, [rsp+200h+var_198.pvInData]
0x180008120  mov     dword ptr [rdi+190h], 1
0x18000812a  mov     qword ptr [rsp+200h+var_1B8+8], rax
0x18000812f  mov     eax, [rsp+200h+var_198.cbInData]
0x180008133  mov     dword ptr [rsp+200h+var_1B8], r13d
0x180008138  mov     dword ptr [rsp+200h+var_1A8], eax
0x18000813c  mov     rcx, rsi
0x18000813f  mov     rax, [rsi]
0x180008142  mov     rax, [rax+20h]
0x180008146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000814b  mov     rcx, rax
0x18000814e  mov     [rsp+200h+var_1D0], r13
0x180008153  lea     rdx, [rsp+200h+var_1BC]
0x180008158  xor     r9d, r9d
0x18000815b  mov     [rsp+200h+var_1D8], rdx
0x180008160  mov     r8d, 1
0x180008166  mov     rax, [rax]
0x180008169  lea     rdx, [rsp+200h+var_1B8]
0x18000816e  mov     dword ptr [rsp+200h+var_1E0], 1
0x180008176  mov     rax, [rax+0A8h]
0x18000817d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008182  test    eax, eax
0x180008184  jns     loc_180007E21
0x18000818a  jmp     short loc_1800081F7
0x18000818c  test    r15, r15
0x18000818f  jnz     short loc_180008198
0x180008191  mov     eax, 80070057h
0x180008196  jmp     short loc_1800081F7
0x180008198  mov     rcx, r15
0x18000819b  call    cs:__imp_?NormalizeUrl@@YAJPEAD@Z; NormalizeUrl(char *)
0x1800081a1  jmp     short loc_1800081EF
0x1800081a3  cmp     ebx, 8
0x1800081a6  jz      short loc_1800081E4
0x1800081a8  cmp     ebx, 3F7h
0x1800081ae  jnz     loc_180007E60
0x1800081b4  test    rsi, rsi
0x1800081b7  jz      loc_180007E60
0x1800081bd  mov     r9, [r15+8]; unsigned __int8 *
0x1800081c1  lea     rax, [r15+2Ch]
0x1800081c5  mov     edx, [r15+28h]; unsigned int
0x1800081c9  lea     rcx, [r15+10h]
0x1800081cd  mov     [rsp+200h+var_1D8], rax; unsigned int *
0x1800081d2  mov     r8, r15; unsigned int *
0x1800081d5  mov     [rsp+200h+var_1E0], rcx; unsigned int *
0x1800081da  mov     rcx, rsi; struct IHttpContext *
0x1800081dd  call    ?GetCertificateInfoEx@@YAJPEAVIHttpContext@@KPEAKPEAE11@Z; GetCertificateInfoEx(IHttpContext *,ulong,ulong *,uchar *,ulong *,ulong *)
0x1800081e2  jmp     short loc_1800081EF
0x1800081e4  mov     edx, r14d; unsigned int
0x1800081e7  mov     rcx, rdi; this
0x1800081ea  call    ?DisableNotification@W3_FILTER_CONTEXT@@QEAAJK@Z; W3_FILTER_CONTEXT::DisableNotification(ulong)
0x1800081ef  test    eax, eax
0x1800081f1  jns     loc_180007E21
0x1800081f7  mov     ecx, eax; int
0x1800081f9  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800081fe  mov     ecx, eax; dwErrCode
0x180008200  call    cs:__imp_SetLastError
0x180008206  lea     rcx, [rbp+100h+var_180]
0x18000820a  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008210  xor     eax, eax
0x180008212  jmp     loc_180007E30
0x180008217  mov     ecx, 57h ; 'W'; dwErrCode
0x18000821c  call    cs:__imp_SetLastError
0x180008222  lea     rcx, [rbp+100h+var_180]
0x180008226  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000822c  xor     eax, eax
0x18000822e  jmp     loc_180007E40
```
