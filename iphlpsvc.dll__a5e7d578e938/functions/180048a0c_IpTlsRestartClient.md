# IpTlsRestartClient

- ea: `0x180048a0c`
- end: `0x180049015`
- name: `IpTlsRestartClient`
- size: `1545`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180045014`
- `0x180061f70`
- `0x180062040`
- `0x18006305c`

## callees

- `0x18000d7c0`
- `0x180047cfc`
- `0x180048a0c`
- `0x18004901c`
- `0x1800492cc`
- `0x18005ff80`
- `0x1800620a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048a51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048dd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048a51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048dd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048a69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048a9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048e55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048f1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048f6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048a69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048a9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048e55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048f1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048f6b`
- `SspiCli!SspiFreeAuthIdentity` at `0x180048d50`
- `SspiCli!SspiFreeAuthIdentity` at `0x180048d50`
- `webio!__imp_WebCloseHttpRequest` at `0x180048b0a`
- `webio!__imp_WebCloseHttpRequest` at `0x180048b0a`
- `webio!__imp_WebCloseSession` at `0x180048af1`
- `webio!__imp_WebCloseSession` at `0x180048af1`
- `webio!__imp_WebCreateHttpRequest` at `0x180048c0e`
- `webio!__imp_WebCreateHttpRequest` at `0x180048c0e`
- `webio!__imp_WebCreateSession` at `0x180048b32`
- `webio!__imp_WebCreateSession` at `0x180048b32`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048cee`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048d96`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048e24`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048e9b`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048f08`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048cee`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048d96`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048e24`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048e9b`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048f08`
- `webio!__imp_WebSetSessionOption` at `0x180048ba2`
- `webio!__imp_WebSetSessionOption` at `0x180048ba2`

## string_xrefs

- `0x180048b4b`: `%s:WebCreateSession failed: %d`
- `0x180048c32`: `%s:WebCreateHttpRequest failed: %d`
- `0x180048fda`: `%s:WebCreateHttpRequest failed: %d`
- `0x180048df3`: `%s:WebSetHttpRequestOption: WebHttpRequestOptionSslCipherConfig setting null cipher`
- `0x180048de6`: `%s:WebSetHttpRequestOption: WebHttpRequestOptionSslCipherConfig setting default cipher`
- `0x180048e3d`: `%s:WebSetHttpRequestOption: WebHttpRequestOptionSslCipherConfig failed: %d`
- `0x180048eba`: `%s:WebSetHttpRequestOption: WebHttpRequestOptionProxyConfig failed: %d`
- `0x180048ec7`: `%s:WebSetHttpRequestOption: WebProxyConfigTypeSpecificProxy setting proxy = %s`

## pseudocode

```c
__int64 __fastcall IpTlsRestartClient(_QWORD *a1, char a2)
{
  __int64 v4; // r8
  __int64 *v5; // r14
  __int64 v6; // rcx
  unsigned int Session; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r14
  unsigned int v15; // eax
  __int64 v16; // r8
  void *v17; // rcx
  __int64 v18; // rcx
  unsigned int v19; // eax
  char v20; // bl
  const wchar_t *v21; // rdx
  __int64 v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned int v26; // eax
  __int64 v27; // r8
  int v28; // eax
  __int64 v29; // rcx
  __int64 result; // rax
  __int64 v31; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v32[3]; // [rsp+28h] [rbp-58h] BYREF
  _DWORD v33[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v34; // [rsp+48h] [rbp-38h]
  __int64 v35; // [rsp+50h] [rbp-30h]
  __int128 v36; // [rsp+58h] [rbp-28h] BYREF
  __int128 v37; // [rsp+68h] [rbp-18h]
  __int64 v38; // [rsp+78h] [rbp-8h]
  BOOL v39; // [rsp+D0h] [rbp+50h] BYREF
  int v40; // [rsp+D8h] [rbp+58h] BYREF

  v38 = 0;
  v31 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  EnterCriticalSection(&stru_1800CC350);
  if ( byte_1800CC378 )
  {
    LeaveCriticalSection(&stru_1800CC350);
    EventWrite0(0x10000000, L"%s:IpTlsRestartClient. Aborted due to shutdown", a1[16] + 56LL);
LABEL_52:
    IpTlsStoreInterfacePersistentValues((const BYTE *)a1[16], *(_DWORD *)(a1[16] + 1024LL), 12);
    if ( *((_DWORD *)a1 + 37) == 1 )
      *((_DWORD *)a1 + 37) = 2;
    v8 = IpTlsClientScheduleReconnect(a1);
    goto LABEL_55;
  }
  LeaveCriticalSection(&stru_1800CC350);
  v4 = a1[16] + 56LL;
  if ( *((_DWORD *)a1 + 30) != 1 )
  {
    EventWrite0(0x10000000, L"%s:IpTlsRestartClient: Invalid client state: %d", v4);
    goto LABEL_52;
  }
  EventWrite0(0x10000000, L"%s:Restarting Client", v4);
  v5 = a1 + 1;
  v6 = a1[1];
  if ( v6 )
  {
    WebCloseSession(v6, 0);
    *v5 = 0;
  }
  if ( *a1 )
  {
    WebCloseHttpRequest(*a1, 0);
    *a1 = 0;
  }
  IpTlsCleanupReceiveBlock(a1 + 11);
  a1[11] = 0;
  Session = WebCreateSession(qword_1800CC328, 0, a1 + 1);
  v8 = Session;
  if ( Session )
  {
    EventWrite0(0x10000000, L"%s:WebCreateSession failed: %d", a1[16] + 56LL, Session, v31);
    *(_DWORD *)(a1[16] + 1192LL) = 8;
LABEL_11:
    *(_DWORD *)(a1[16] + 1196LL) = v8;
    goto LABEL_51;
  }
  v9 = *v5;
  v31 = 1;
  v8 = WebSetSessionOption(v9, 1, &v31, 8);
  if ( v8 )
  {
    EventWrite0(0x10000000, L"%s:WebSetSessionOption for basic auth scheme failed:%d", a1[16] + 56LL, v8);
LABEL_14:
    *(_DWORD *)(a1[16] + 1192LL) = 8;
    goto LABEL_11;
  }
  v10 = *v5;
  *((_QWORD *)&v36 + 1) = a1[2];
  *((_QWORD *)&v37 + 1) = 0;
  *(_QWORD *)&v36 = "POST";
  LODWORD(v38) = 0;
  LODWORD(v37) = 65537;
  v11 = WebCreateHttpRequest(v10, 0, &v36, a1);
  v8 = v11;
  if ( v11 == 6 || v11 == 87 )
  {
    EventWrite0(0x10000000, L"%s:WebCreateHttpRequest failed: %d", a1[16] + 56LL, v11);
    ShutdownClientInternal(a1);
    return v8;
  }
  if ( v11 )
  {
    EventWrite0(0x10000000, L"%s:WebCreateHttpRequest failed: %d", a1[16] + 56LL, v11);
    goto LABEL_14;
  }
  if ( a2 )
    *(_QWORD *)(a1[16] + 1136LL) = a1[16] + 1120LL;
  v12 = a1[16];
  if ( *(_QWORD *)(v12 + 1120) != v12 + 1120 )
  {
    if ( a2 || *(_DWORD *)(v12 + 1196) != -2145844841 )
      *(_QWORD *)(v12 + 1136) = **(_QWORD **)(v12 + 1136);
    else
      EventWrite0(0x10000000, L"%s:Re-using the certificate: %d", v12 + 56);
    v13 = a1[16];
    v14 = *(_QWORD *)(v13 + 1136);
    if ( v14 == v13 + 1120 )
    {
      *(_DWORD *)(v13 + 1192) = 7;
      *(_DWORD *)(a1[16] + 1196LL) = 259;
      goto LABEL_52;
    }
    v15 = WebSetHttpRequestOption(*a1, 2, v14 + 16, 8);
    v16 = a1[16] + 56LL;
    v8 = v15;
    if ( v15 )
    {
      EventWrite0(0x10000000, L"%s:WebSetHttpRequestOption failed: %d", v16, v15);
      *(_DWORD *)(a1[16] + 1192LL) = 7;
      goto LABEL_11;
    }
    EventWrite0(0x10000000, L"%s:WebSetHttpRequestOption:Certificate CN: %s", v16, v14 + 28);
  }
  if ( a2 )
  {
    v17 = (void *)a1[9];
    if ( v17 )
    {
      SspiFreeAuthIdentity(v17);
      a1[9] = 0;
    }
    *((_DWORD *)a1 + 16) = 0;
    *((_DWORD *)a1 + 20) = 32;
  }
  if ( *(_BYTE *)(a1[16] + 1020LL) )
  {
    v18 = *a1;
    v40 = 128;
    v19 = WebSetHttpRequestOption(v18, 5, &v40, 4);
    v8 = v19;
    if ( v19 )
    {
      EventWrite0(
        0x10000000,
        L"%s:WebSetHttpRequestOption: WebHttpRequestOptionIgnoredServerCertErrors failed: %d",
        a1[16] + 56LL,
        v19);
      goto LABEL_51;
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 22));
  v20 = *((_BYTE *)a1 + 224);
  v21 = L"%s:WebSetHttpRequestOption: WebHttpRequestOptionSslCipherConfig setting null cipher";
  if ( !v20 )
    v21 = L"%s:WebSetHttpRequestOption: WebHttpRequestOptionSslCipherConfig setting default cipher";
  EventWrite0(0x10000000, v21, a1[16] + 56LL);
  v22 = *a1;
  v39 = v20 != 0;
  v23 = WebSetHttpRequestOption(v22, 37, &v39, 4);
  v8 = v23;
  if ( v23 )
  {
    EventWrite0(
      0x10000000,
      L"%s:WebSetHttpRequestOption: WebHttpRequestOptionSslCipherConfig failed: %d",
      a1[16] + 56LL,
      v23);
LABEL_42:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 22));
    goto LABEL_51;
  }
  if ( !a1[5] )
    goto LABEL_50;
  v24 = *a1;
  v32[1] = a1[5];
  v25 = a1[6];
  v32[0] = 1;
  v32[2] = v25;
  v26 = WebSetHttpRequestOption(v24, 10, v32, 24);
  v27 = a1[16] + 56LL;
  v8 = v26;
  if ( v26 )
  {
    EventWrite0(0x10000000, L"%s:WebSetHttpRequestOption: WebHttpRequestOptionProxyConfig failed: %d", v27, v26);
    goto LABEL_42;
  }
  EventWrite0(0x10000000, L"%s:WebSetHttpRequestOption: WebProxyConfigTypeSpecificProxy setting proxy = %s", v27, a1[5]);
  if ( !a1[9] )
  {
LABEL_50:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 22));
    v8 = IpTlsConnect(a1);
    if ( !v8 )
      goto LABEL_55;
    goto LABEL_51;
  }
  v28 = *((_DWORD *)a1 + 20);
  v34 = a1[9];
  v29 = *a1;
  v35 = 0;
  v33[0] = 1;
  v33[1] = v28;
  v8 = WebSetHttpRequestOption(v29, 12, v33, 24);
  if ( !v8 )
  {
    EventWrite0(
      0x10000000,
      L"%s:WebSetHttpRequestOption: WebHttpRequestOptionProxyCreds set proxy creds succeeded",
      a1[16] + 56LL);
    goto LABEL_50;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 22));
  EventWrite0(
    0x10000000,
    L"%s:WebSetHttpRequestOption: WebHttpRequestOptionProxyCreds setting proxy creds failed 0x%x",
    a1[16] + 56LL,
    v8);
LABEL_51:
  if ( v8 != 997 )
    goto LABEL_52;
LABEL_55:
  result = 0;
  if ( v8 != 997 )
    return v8;
  return result;
}

```

## disassembly

```asm
0x180048a0c  mov     [rsp-38h+arg_0], rbx
0x180048a11  push    rbp
0x180048a12  push    rsi
0x180048a13  push    rdi
0x180048a14  push    r12
0x180048a16  push    r13
0x180048a18  push    r14
0x180048a1a  push    r15
0x180048a1c  mov     rbp, rsp
0x180048a1f  sub     rsp, 80h
0x180048a26  xor     eax, eax
0x180048a28  lea     rbx, stru_1800CC350
0x180048a2f  xorps   xmm0, xmm0
0x180048a32  mov     [rbp+var_8], rax
0x180048a36  mov     rdi, rcx
0x180048a39  mov     [rbp+var_60], rax
0x180048a3d  mov     rcx, rbx; lpCriticalSection
0x180048a40  mov     [rbp+arg_10], eax
0x180048a43  mov     r12b, dl
0x180048a46  xor     r13d, r13d
0x180048a49  movups  [rbp+var_28], xmm0
0x180048a4d  movups  [rbp+var_18], xmm0
0x180048a51  call    cs:__imp_EnterCriticalSection
0x180048a58  nop     dword ptr [rax+rax+00h]
0x180048a5d  cmp     cs:byte_1800CC378, r13b
0x180048a64  mov     rcx, rbx; lpCriticalSection
0x180048a67  jz      short loc_180048A9C
0x180048a69  call    cs:__imp_LeaveCriticalSection
0x180048a70  nop     dword ptr [rax+rax+00h]
0x180048a75  mov     r8, [rdi+80h]
0x180048a7c  lea     rdx, aSIptlsrestartc; "%s:IpTlsRestartClient. Aborted due to s"...
0x180048a83  add     r8, 38h ; '8'
0x180048a87  mov     ecx, 10000000h
0x180048a8c  call    EventWrite0
0x180048a91  mov     r15d, 0Ch
0x180048a97  jmp     loc_180048F8D
0x180048a9c  call    cs:__imp_LeaveCriticalSection
0x180048aa3  nop     dword ptr [rax+rax+00h]
0x180048aa8  mov     r8, [rdi+80h]
0x180048aaf  mov     r9d, [rdi+78h]
0x180048ab3  add     r8, 38h ; '8'
0x180048ab7  cmp     r9d, 1
0x180048abb  jz      short loc_180048AD0
0x180048abd  lea     rdx, aSIptlsrestartc_0; "%s:IpTlsRestartClient: Invalid client s"...
0x180048ac4  mov     ecx, 10000000h
0x180048ac9  call    EventWrite0
0x180048ace  jmp     short loc_180048A91
0x180048ad0  mov     esi, 10000000h
0x180048ad5  lea     rdx, aSRestartingCli; "%s:Restarting Client"
0x180048adc  mov     ecx, esi
0x180048ade  call    EventWrite0
0x180048ae3  lea     r14, [rdi+8]
0x180048ae7  mov     rcx, [r14]
0x180048aea  test    rcx, rcx
0x180048aed  jz      short loc_180048B00
0x180048aef  xor     edx, edx
0x180048af1  call    cs:__imp_WebCloseSession
0x180048af8  nop     dword ptr [rax+rax+00h]
0x180048afd  mov     [r14], r13
0x180048b00  mov     rcx, [rdi]
0x180048b03  test    rcx, rcx
0x180048b06  jz      short loc_180048B19
0x180048b08  xor     edx, edx
0x180048b0a  call    cs:__imp_WebCloseHttpRequest
0x180048b11  nop     dword ptr [rax+rax+00h]
0x180048b16  mov     [rdi], r13
0x180048b19  lea     rcx, [rdi+58h]
0x180048b1d  call    IpTlsCleanupReceiveBlock
0x180048b22  mov     [rdi+58h], r13
0x180048b26  mov     r8, r14
0x180048b29  mov     rcx, cs:qword_1800CC328
0x180048b30  xor     edx, edx
0x180048b32  call    cs:__imp_WebCreateSession
0x180048b39  nop     dword ptr [rax+rax+00h]
0x180048b3e  mov     ebx, eax
0x180048b40  test    eax, eax
0x180048b42  jz      short loc_180048B89
0x180048b44  mov     r8, [rdi+80h]
0x180048b4b  lea     rdx, aSWebcreatesess; "%s:WebCreateSession failed: %d"
0x180048b52  add     r8, 38h ; '8'
0x180048b56  mov     r9d, eax
0x180048b59  mov     ecx, esi
0x180048b5b  call    EventWrite0
0x180048b60  mov     rcx, [rdi+80h]
0x180048b67  mov     dword ptr [rcx+4A8h], 8
0x180048b71  mov     rax, [rdi+80h]
0x180048b78  mov     [rax+4ACh], ebx
0x180048b7e  mov     r15d, 0Ch
0x180048b84  jmp     loc_180048F85
0x180048b89  mov     rcx, [r14]
0x180048b8c  lea     r8, [rbp+var_60]
0x180048b90  mov     eax, 1
0x180048b95  mov     edx, eax
0x180048b97  mov     [rbp+var_60], rax
0x180048b9b  lea     r15d, [rax+7]
0x180048b9f  mov     r9d, r15d
0x180048ba2  call    cs:__imp_WebSetSessionOption
0x180048ba9  nop     dword ptr [rax+rax+00h]
0x180048bae  mov     ebx, eax
0x180048bb0  test    eax, eax
0x180048bb2  jz      short loc_180048BE0
0x180048bb4  lea     rdx, aSWebsetsession; "%s:WebSetSessionOption for basic auth s"...
0x180048bbb  mov     r8, [rdi+80h]
0x180048bc2  mov     r9d, ebx
0x180048bc5  add     r8, 38h ; '8'
0x180048bc9  mov     ecx, esi
0x180048bcb  call    EventWrite0
0x180048bd0  mov     rax, [rdi+80h]
0x180048bd7  mov     [rax+4A8h], r15d
0x180048bde  jmp     short loc_180048B71
0x180048be0  mov     rax, [rdi+10h]
0x180048be4  lea     r8, [rbp+var_28]
0x180048be8  mov     rcx, [r14]
0x180048beb  mov     r9, rdi
0x180048bee  mov     qword ptr [rbp+var_28+8], rax
0x180048bf2  xor     edx, edx
0x180048bf4  lea     rax, aPost; "POST"
0x180048bfb  mov     qword ptr [rbp+var_18+8], r13
0x180048bff  mov     qword ptr [rbp+var_28], rax
0x180048c03  mov     dword ptr [rbp+var_8], r13d
0x180048c07  mov     dword ptr [rbp+var_18], 10001h
0x180048c0e  call    cs:__imp_WebCreateHttpRequest
0x180048c15  nop     dword ptr [rax+rax+00h]
0x180048c1a  mov     ebx, eax
0x180048c1c  cmp     eax, 6
0x180048c1f  jz      loc_180048FD3
0x180048c25  cmp     eax, 57h ; 'W'
0x180048c28  jz      loc_180048FD3
0x180048c2e  test    eax, eax
0x180048c30  jz      short loc_180048C3B
0x180048c32  lea     rdx, aSWebcreatehttp; "%s:WebCreateHttpRequest failed: %d"
0x180048c39  jmp     short loc_180048BBB
0x180048c3b  test    r12b, r12b
0x180048c3e  jz      short loc_180048C55
0x180048c40  mov     rcx, [rdi+80h]
0x180048c47  lea     rax, [rcx+460h]
0x180048c4e  mov     [rcx+470h], rax
0x180048c55  mov     rdx, [rdi+80h]
0x180048c5c  lea     rax, [rdx+460h]
0x180048c63  cmp     [rax], rax
0x180048c66  jz      loc_180048D42
0x180048c6c  test    r12b, r12b
0x180048c6f  jnz     short loc_180048C94
0x180048c71  mov     r9d, 80190197h
0x180048c77  cmp     [rdx+4ACh], r9d
0x180048c7e  jnz     short loc_180048C94
0x180048c80  lea     r8, [rdx+38h]
0x180048c84  mov     ecx, esi
0x180048c86  lea     rdx, aSReUsingTheCer; "%s:Re-using the certificate: %d"
0x180048c8d  call    EventWrite0
0x180048c92  jmp     short loc_180048CA5
0x180048c94  mov     rax, [rdx+470h]
0x180048c9b  mov     rcx, [rax]
0x180048c9e  mov     [rdx+470h], rcx
0x180048ca5  mov     rcx, [rdi+80h]
0x180048cac  mov     r14, [rcx+470h]
0x180048cb3  lea     rax, [rcx+460h]
0x180048cba  cmp     r14, rax
0x180048cbd  jnz     short loc_180048CDF
0x180048cbf  mov     dword ptr [rcx+4A8h], 7
0x180048cc9  mov     rax, [rdi+80h]
0x180048cd0  mov     dword ptr [rax+4ACh], 103h
0x180048cda  jmp     loc_180048A91
0x180048cdf  mov     rcx, [rdi]
0x180048ce2  lea     r8, [r14+10h]
0x180048ce6  mov     r9, r15
0x180048ce9  mov     edx, 2
0x180048cee  call    cs:__imp_WebSetHttpRequestOption
0x180048cf5  nop     dword ptr [rax+rax+00h]
0x180048cfa  mov     r8, [rdi+80h]
0x180048d01  mov     ecx, esi
0x180048d03  add     r8, 38h ; '8'
0x180048d07  mov     ebx, eax
0x180048d09  test    eax, eax
0x180048d0b  jz      short loc_180048D32
0x180048d0d  mov     r9d, eax
0x180048d10  lea     rdx, aSWebsethttpreq_8; "%s:WebSetHttpRequestOption failed: %d"
0x180048d17  call    EventWrite0
0x180048d1c  mov     rax, [rdi+80h]
0x180048d23  mov     dword ptr [rax+4A8h], 7
0x180048d2d  jmp     loc_180048B71
0x180048d32  lea     r9, [r14+1Ch]
0x180048d36  lea     rdx, aSWebsethttpreq_4; "%s:WebSetHttpRequestOption:Certificate "...
0x180048d3d  call    EventWrite0
0x180048d42  test    r12b, r12b
0x180048d45  jz      short loc_180048D6B
0x180048d47  mov     rcx, [rdi+48h]; AuthData
0x180048d4b  test    rcx, rcx
0x180048d4e  jz      short loc_180048D60
0x180048d50  call    cs:__imp_SspiFreeAuthIdentity
0x180048d57  nop     dword ptr [rax+rax+00h]
0x180048d5c  mov     [rdi+48h], r13
0x180048d60  mov     [rdi+40h], r13d
0x180048d64  mov     dword ptr [rdi+50h], 20h ; ' '
0x180048d6b  mov     rax, [rdi+80h]
0x180048d72  mov     r15d, 4
0x180048d78  cmp     [rax+3FCh], r13b
0x180048d7f  jz      short loc_180048DC9
0x180048d81  mov     rcx, [rdi]
0x180048d84  lea     r8, [rbp+arg_18]
0x180048d88  mov     r9d, r15d
0x180048d8b  mov     [rbp+arg_18], 80h
0x180048d92  lea     edx, [r15+1]
0x180048d96  call    cs:__imp_WebSetHttpRequestOption
0x180048d9d  nop     dword ptr [rax+rax+00h]
0x180048da2  mov     ebx, eax
0x180048da4  test    eax, eax
0x180048da6  jz      short loc_180048DC9
0x180048da8  mov     r8, [rdi+80h]
0x180048daf  lea     rdx, aSWebsethttpreq; "%s:WebSetHttpRequestOption: WebHttpRequ"...
0x180048db6  add     r8, 38h ; '8'
0x180048dba  mov     r9d, eax
0x180048dbd  mov     ecx, esi
0x180048dbf  call    EventWrite0
0x180048dc4  jmp     loc_180048B7E
0x180048dc9  lea     r14, [rdi+0B0h]
0x180048dd0  mov     rcx, r14; lpCriticalSection
0x180048dd3  call    cs:__imp_EnterCriticalSection
0x180048dda  nop     dword ptr [rax+rax+00h]
0x180048ddf  mov     r8, [rdi+80h]
0x180048de6  lea     rax, aSWebsethttpreq_1; "%s:WebSetHttpRequestOption: WebHttpRequ"...
0x180048ded  mov     bl, [rdi+0E0h]
0x180048df3  lea     rdx, aSWebsethttpreq_3; "%s:WebSetHttpRequestOption: WebHttpRequ"...
0x180048dfa  add     r8, 38h ; '8'
0x180048dfe  mov     ecx, esi
0x180048e00  test    bl, bl
0x180048e02  cmovz   rdx, rax
0x180048e06  call    EventWrite0
0x180048e0b  mov     rcx, [rdi]
0x180048e0e  lea     r8, [rbp+arg_10]
0x180048e12  xor     eax, eax
0x180048e14  mov     r9, r15
0x180048e17  test    bl, bl
0x180048e19  mov     edx, 25h ; '%'
0x180048e1e  setnz   al
0x180048e21  mov     [rbp+arg_10], eax
0x180048e24  call    cs:__imp_WebSetHttpRequestOption
0x180048e2b  nop     dword ptr [rax+rax+00h]
0x180048e30  mov     ebx, eax
0x180048e32  test    eax, eax
0x180048e34  jz      short loc_180048E66
0x180048e36  mov     r8, [rdi+80h]
0x180048e3d  lea     rdx, aSWebsethttpreq_6; "%s:WebSetHttpRequestOption: WebHttpRequ"...
0x180048e44  add     r8, 38h ; '8'
0x180048e48  mov     ecx, esi
0x180048e4a  mov     r9d, eax
0x180048e4d  call    EventWrite0
0x180048e52  mov     rcx, r14; lpCriticalSection
0x180048e55  call    cs:__imp_LeaveCriticalSection
0x180048e5c  nop     dword ptr [rax+rax+00h]
0x180048e61  jmp     loc_180048B7E
0x180048e66  mov     rax, [rdi+28h]
0x180048e6a  test    rax, rax
0x180048e6d  jz      loc_180048F62
0x180048e73  mov     rcx, [rdi]
0x180048e76  lea     r8, [rbp+var_58]
0x180048e7a  mov     r15d, 18h
0x180048e80  mov     [rbp+var_50], rax
0x180048e84  mov     rax, [rdi+30h]
0x180048e88  mov     r9d, r15d
0x180048e8b  mov     [rbp+var_58], 1
0x180048e93  mov     [rbp+var_48], rax
0x180048e97  lea     edx, [r15-0Eh]
0x180048e9b  call    cs:__imp_WebSetHttpRequestOption
0x180048ea2  nop     dword ptr [rax+rax+00h]
0x180048ea7  mov     r8, [rdi+80h]
0x180048eae  mov     ecx, esi
0x180048eb0  add     r8, 38h ; '8'
0x180048eb4  mov     ebx, eax
0x180048eb6  test    eax, eax
0x180048eb8  jz      short loc_180048EC3
0x180048eba  lea     rdx, aSWebsethttpreq_7; "%s:WebSetHttpRequestOption: WebHttpRequ"...
0x180048ec1  jmp     short loc_180048E4A
0x180048ec3  mov     r9, [rdi+28h]
0x180048ec7  lea     rdx, aSWebsethttpreq_2; "%s:WebSetHttpRequestOption: WebProxyCon"...
0x180048ece  call    EventWrite0
0x180048ed3  mov     rcx, [rdi+48h]
0x180048ed7  test    rcx, rcx
0x180048eda  jz      loc_180048F62
0x180048ee0  mov     eax, [rdi+50h]
0x180048ee3  lea     r8, [rbp+var_40]
0x180048ee7  mov     r9, r15
0x180048eea  mov     [rbp+var_38], rcx
0x180048eee  mov     rcx, [rdi]
0x180048ef1  mov     r15d, 0Ch
0x180048ef7  mov     edx, r15d
0x180048efa  mov     [rbp+var_30], r13
0x180048efe  mov     [rbp+var_40], 1
0x180048f05  mov     [rbp+var_3C], eax
0x180048f08  call    cs:__imp_WebSetHttpRequestOption
0x180048f0f  nop     dword ptr [rax+rax+00h]
0x180048f14  mov     ebx, eax
0x180048f16  test    eax, eax
0x180048f18  jz      short loc_180048F47
0x180048f1a  mov     rcx, r14; lpCriticalSection
0x180048f1d  call    cs:__imp_LeaveCriticalSection
0x180048f24  nop     dword ptr [rax+rax+00h]
0x180048f29  mov     r8, [rdi+80h]
0x180048f30  lea     rdx, aSWebsethttpreq_0; "%s:WebSetHttpRequestOption: WebHttpRequ"...
0x180048f37  add     r8, 38h ; '8'
  ... truncated ...
```
