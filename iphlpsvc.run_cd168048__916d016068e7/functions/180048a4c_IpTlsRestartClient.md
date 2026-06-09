# IpTlsRestartClient

- ea: `0x180048a4c`
- end: `0x180049055`
- name: `IpTlsRestartClient`
- size: `1545`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180045054`
- `0x180061f50`
- `0x180062020`
- `0x18006303c`

## callees

- `0x18000d7b0`
- `0x180047d3c`
- `0x180048a4c`
- `0x18004905c`
- `0x18004930c`
- `0x18005ff60`
- `0x180062084`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048a91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048e13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048a91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048e13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048aa9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048adc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048e95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048f5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048fab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048aa9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048adc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048e95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048f5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048fab`
- `SspiCli!SspiFreeAuthIdentity` at `0x180048d90`
- `SspiCli!SspiFreeAuthIdentity` at `0x180048d90`
- `webio!__imp_WebCloseHttpRequest` at `0x180048b4a`
- `webio!__imp_WebCloseHttpRequest` at `0x180048b4a`
- `webio!__imp_WebCloseSession` at `0x180048b31`
- `webio!__imp_WebCloseSession` at `0x180048b31`
- `webio!__imp_WebCreateHttpRequest` at `0x180048c4e`
- `webio!__imp_WebCreateHttpRequest` at `0x180048c4e`
- `webio!__imp_WebCreateSession` at `0x180048b72`
- `webio!__imp_WebCreateSession` at `0x180048b72`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048d2e`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048dd6`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048e64`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048edb`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048f48`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048d2e`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048dd6`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048e64`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048edb`
- `webio!__imp_WebSetHttpRequestOption` at `0x180048f48`
- `webio!__imp_WebSetSessionOption` at `0x180048be2`
- `webio!__imp_WebSetSessionOption` at `0x180048be2`

## string_xrefs

- `0x180048b8b`: `%s:WebCreateSession failed: %d`
- `0x180048c72`: `%s:WebCreateHttpRequest failed: %d`
- `0x18004901a`: `%s:WebCreateHttpRequest failed: %d`
- `0x180048e33`: `%s:WebSetHttpRequestOption: WebHttpRequestOptionSslCipherConfig setting null cipher`
- `0x180048e26`: `%s:WebSetHttpRequestOption: WebHttpRequestOptionSslCipherConfig setting default cipher`
- `0x180048e7d`: `%s:WebSetHttpRequestOption: WebHttpRequestOptionSslCipherConfig failed: %d`
- `0x180048efa`: `%s:WebSetHttpRequestOption: WebHttpRequestOptionProxyConfig failed: %d`
- `0x180048f07`: `%s:WebSetHttpRequestOption: WebProxyConfigTypeSpecificProxy setting proxy = %s`

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
0x180048a4c  mov     [rsp-38h+arg_0], rbx
0x180048a51  push    rbp
0x180048a52  push    rsi
0x180048a53  push    rdi
0x180048a54  push    r12
0x180048a56  push    r13
0x180048a58  push    r14
0x180048a5a  push    r15
0x180048a5c  mov     rbp, rsp
0x180048a5f  sub     rsp, 80h
0x180048a66  xor     eax, eax
0x180048a68  lea     rbx, stru_1800CC350
0x180048a6f  xorps   xmm0, xmm0
0x180048a72  mov     [rbp+var_8], rax
0x180048a76  mov     rdi, rcx
0x180048a79  mov     [rbp+var_60], rax
0x180048a7d  mov     rcx, rbx; lpCriticalSection
0x180048a80  mov     [rbp+arg_10], eax
0x180048a83  mov     r12b, dl
0x180048a86  xor     r13d, r13d
0x180048a89  movups  [rbp+var_28], xmm0
0x180048a8d  movups  [rbp+var_18], xmm0
0x180048a91  call    cs:__imp_EnterCriticalSection
0x180048a98  nop     dword ptr [rax+rax+00h]
0x180048a9d  cmp     cs:byte_1800CC378, r13b
0x180048aa4  mov     rcx, rbx; lpCriticalSection
0x180048aa7  jz      short loc_180048ADC
0x180048aa9  call    cs:__imp_LeaveCriticalSection
0x180048ab0  nop     dword ptr [rax+rax+00h]
0x180048ab5  mov     r8, [rdi+80h]
0x180048abc  lea     rdx, aSIptlsrestartc; "%s:IpTlsRestartClient. Aborted due to s"...
0x180048ac3  add     r8, 38h ; '8'
0x180048ac7  mov     ecx, 10000000h
0x180048acc  call    EventWrite0
0x180048ad1  mov     r15d, 0Ch
0x180048ad7  jmp     loc_180048FCD
0x180048adc  call    cs:__imp_LeaveCriticalSection
0x180048ae3  nop     dword ptr [rax+rax+00h]
0x180048ae8  mov     r8, [rdi+80h]
0x180048aef  mov     r9d, [rdi+78h]
0x180048af3  add     r8, 38h ; '8'
0x180048af7  cmp     r9d, 1
0x180048afb  jz      short loc_180048B10
0x180048afd  lea     rdx, aSIptlsrestartc_0; "%s:IpTlsRestartClient: Invalid client s"...
0x180048b04  mov     ecx, 10000000h
0x180048b09  call    EventWrite0
0x180048b0e  jmp     short loc_180048AD1
0x180048b10  mov     esi, 10000000h
0x180048b15  lea     rdx, aSRestartingCli; "%s:Restarting Client"
0x180048b1c  mov     ecx, esi
0x180048b1e  call    EventWrite0
0x180048b23  lea     r14, [rdi+8]
0x180048b27  mov     rcx, [r14]
0x180048b2a  test    rcx, rcx
0x180048b2d  jz      short loc_180048B40
0x180048b2f  xor     edx, edx
0x180048b31  call    cs:__imp_WebCloseSession
0x180048b38  nop     dword ptr [rax+rax+00h]
0x180048b3d  mov     [r14], r13
0x180048b40  mov     rcx, [rdi]
0x180048b43  test    rcx, rcx
0x180048b46  jz      short loc_180048B59
0x180048b48  xor     edx, edx
0x180048b4a  call    cs:__imp_WebCloseHttpRequest
0x180048b51  nop     dword ptr [rax+rax+00h]
0x180048b56  mov     [rdi], r13
0x180048b59  lea     rcx, [rdi+58h]
0x180048b5d  call    IpTlsCleanupReceiveBlock
0x180048b62  mov     [rdi+58h], r13
0x180048b66  mov     r8, r14
0x180048b69  mov     rcx, cs:qword_1800CC328
0x180048b70  xor     edx, edx
0x180048b72  call    cs:__imp_WebCreateSession
0x180048b79  nop     dword ptr [rax+rax+00h]
0x180048b7e  mov     ebx, eax
0x180048b80  test    eax, eax
0x180048b82  jz      short loc_180048BC9
0x180048b84  mov     r8, [rdi+80h]
0x180048b8b  lea     rdx, aSWebcreatesess; "%s:WebCreateSession failed: %d"
0x180048b92  add     r8, 38h ; '8'
0x180048b96  mov     r9d, eax
0x180048b99  mov     ecx, esi
0x180048b9b  call    EventWrite0
0x180048ba0  mov     rcx, [rdi+80h]
0x180048ba7  mov     dword ptr [rcx+4A8h], 8
0x180048bb1  mov     rax, [rdi+80h]
0x180048bb8  mov     [rax+4ACh], ebx
0x180048bbe  mov     r15d, 0Ch
0x180048bc4  jmp     loc_180048FC5
0x180048bc9  mov     rcx, [r14]
0x180048bcc  lea     r8, [rbp+var_60]
0x180048bd0  mov     eax, 1
0x180048bd5  mov     edx, eax
0x180048bd7  mov     [rbp+var_60], rax
0x180048bdb  lea     r15d, [rax+7]
0x180048bdf  mov     r9d, r15d
0x180048be2  call    cs:__imp_WebSetSessionOption
0x180048be9  nop     dword ptr [rax+rax+00h]
0x180048bee  mov     ebx, eax
0x180048bf0  test    eax, eax
0x180048bf2  jz      short loc_180048C20
0x180048bf4  lea     rdx, aSWebsetsession; "%s:WebSetSessionOption for basic auth s"...
0x180048bfb  mov     r8, [rdi+80h]
0x180048c02  mov     r9d, ebx
0x180048c05  add     r8, 38h ; '8'
0x180048c09  mov     ecx, esi
0x180048c0b  call    EventWrite0
0x180048c10  mov     rax, [rdi+80h]
0x180048c17  mov     [rax+4A8h], r15d
0x180048c1e  jmp     short loc_180048BB1
0x180048c20  mov     rax, [rdi+10h]
0x180048c24  lea     r8, [rbp+var_28]
0x180048c28  mov     rcx, [r14]
0x180048c2b  mov     r9, rdi
0x180048c2e  mov     qword ptr [rbp+var_28+8], rax
0x180048c32  xor     edx, edx
0x180048c34  lea     rax, aPost; "POST"
0x180048c3b  mov     qword ptr [rbp+var_18+8], r13
0x180048c3f  mov     qword ptr [rbp+var_28], rax
0x180048c43  mov     dword ptr [rbp+var_8], r13d
0x180048c47  mov     dword ptr [rbp+var_18], 10001h
0x180048c4e  call    cs:__imp_WebCreateHttpRequest
0x180048c55  nop     dword ptr [rax+rax+00h]
0x180048c5a  mov     ebx, eax
0x180048c5c  cmp     eax, 6
0x180048c5f  jz      loc_180049013
0x180048c65  cmp     eax, 57h ; 'W'
0x180048c68  jz      loc_180049013
0x180048c6e  test    eax, eax
0x180048c70  jz      short loc_180048C7B
0x180048c72  lea     rdx, aSWebcreatehttp; "%s:WebCreateHttpRequest failed: %d"
0x180048c79  jmp     short loc_180048BFB
0x180048c7b  test    r12b, r12b
0x180048c7e  jz      short loc_180048C95
0x180048c80  mov     rcx, [rdi+80h]
0x180048c87  lea     rax, [rcx+460h]
0x180048c8e  mov     [rcx+470h], rax
0x180048c95  mov     rdx, [rdi+80h]
0x180048c9c  lea     rax, [rdx+460h]
0x180048ca3  cmp     [rax], rax
0x180048ca6  jz      loc_180048D82
0x180048cac  test    r12b, r12b
0x180048caf  jnz     short loc_180048CD4
0x180048cb1  mov     r9d, 80190197h
0x180048cb7  cmp     [rdx+4ACh], r9d
0x180048cbe  jnz     short loc_180048CD4
0x180048cc0  lea     r8, [rdx+38h]
0x180048cc4  mov     ecx, esi
0x180048cc6  lea     rdx, aSReUsingTheCer; "%s:Re-using the certificate: %d"
0x180048ccd  call    EventWrite0
0x180048cd2  jmp     short loc_180048CE5
0x180048cd4  mov     rax, [rdx+470h]
0x180048cdb  mov     rcx, [rax]
0x180048cde  mov     [rdx+470h], rcx
0x180048ce5  mov     rcx, [rdi+80h]
0x180048cec  mov     r14, [rcx+470h]
0x180048cf3  lea     rax, [rcx+460h]
0x180048cfa  cmp     r14, rax
0x180048cfd  jnz     short loc_180048D1F
0x180048cff  mov     dword ptr [rcx+4A8h], 7
0x180048d09  mov     rax, [rdi+80h]
0x180048d10  mov     dword ptr [rax+4ACh], 103h
0x180048d1a  jmp     loc_180048AD1
0x180048d1f  mov     rcx, [rdi]
0x180048d22  lea     r8, [r14+10h]
0x180048d26  mov     r9, r15
0x180048d29  mov     edx, 2
0x180048d2e  call    cs:__imp_WebSetHttpRequestOption
0x180048d35  nop     dword ptr [rax+rax+00h]
0x180048d3a  mov     r8, [rdi+80h]
0x180048d41  mov     ecx, esi
0x180048d43  add     r8, 38h ; '8'
0x180048d47  mov     ebx, eax
0x180048d49  test    eax, eax
0x180048d4b  jz      short loc_180048D72
0x180048d4d  mov     r9d, eax
0x180048d50  lea     rdx, aSWebsethttpreq_8; "%s:WebSetHttpRequestOption failed: %d"
0x180048d57  call    EventWrite0
0x180048d5c  mov     rax, [rdi+80h]
0x180048d63  mov     dword ptr [rax+4A8h], 7
0x180048d6d  jmp     loc_180048BB1
0x180048d72  lea     r9, [r14+1Ch]
0x180048d76  lea     rdx, aSWebsethttpreq_4; "%s:WebSetHttpRequestOption:Certificate "...
0x180048d7d  call    EventWrite0
0x180048d82  test    r12b, r12b
0x180048d85  jz      short loc_180048DAB
0x180048d87  mov     rcx, [rdi+48h]; AuthData
0x180048d8b  test    rcx, rcx
0x180048d8e  jz      short loc_180048DA0
0x180048d90  call    cs:__imp_SspiFreeAuthIdentity
0x180048d97  nop     dword ptr [rax+rax+00h]
0x180048d9c  mov     [rdi+48h], r13
0x180048da0  mov     [rdi+40h], r13d
0x180048da4  mov     dword ptr [rdi+50h], 20h ; ' '
0x180048dab  mov     rax, [rdi+80h]
0x180048db2  mov     r15d, 4
0x180048db8  cmp     [rax+3FCh], r13b
0x180048dbf  jz      short loc_180048E09
0x180048dc1  mov     rcx, [rdi]
0x180048dc4  lea     r8, [rbp+arg_18]
0x180048dc8  mov     r9d, r15d
0x180048dcb  mov     [rbp+arg_18], 80h
0x180048dd2  lea     edx, [r15+1]
0x180048dd6  call    cs:__imp_WebSetHttpRequestOption
0x180048ddd  nop     dword ptr [rax+rax+00h]
0x180048de2  mov     ebx, eax
0x180048de4  test    eax, eax
0x180048de6  jz      short loc_180048E09
0x180048de8  mov     r8, [rdi+80h]
0x180048def  lea     rdx, aSWebsethttpreq; "%s:WebSetHttpRequestOption: WebHttpRequ"...
0x180048df6  add     r8, 38h ; '8'
0x180048dfa  mov     r9d, eax
0x180048dfd  mov     ecx, esi
0x180048dff  call    EventWrite0
0x180048e04  jmp     loc_180048BBE
0x180048e09  lea     r14, [rdi+0B0h]
0x180048e10  mov     rcx, r14; lpCriticalSection
0x180048e13  call    cs:__imp_EnterCriticalSection
0x180048e1a  nop     dword ptr [rax+rax+00h]
0x180048e1f  mov     r8, [rdi+80h]
0x180048e26  lea     rax, aSWebsethttpreq_1; "%s:WebSetHttpRequestOption: WebHttpRequ"...
0x180048e2d  mov     bl, [rdi+0E0h]
0x180048e33  lea     rdx, aSWebsethttpreq_3; "%s:WebSetHttpRequestOption: WebHttpRequ"...
0x180048e3a  add     r8, 38h ; '8'
0x180048e3e  mov     ecx, esi
0x180048e40  test    bl, bl
0x180048e42  cmovz   rdx, rax
0x180048e46  call    EventWrite0
0x180048e4b  mov     rcx, [rdi]
0x180048e4e  lea     r8, [rbp+arg_10]
0x180048e52  xor     eax, eax
0x180048e54  mov     r9, r15
0x180048e57  test    bl, bl
0x180048e59  mov     edx, 25h ; '%'
0x180048e5e  setnz   al
0x180048e61  mov     [rbp+arg_10], eax
0x180048e64  call    cs:__imp_WebSetHttpRequestOption
0x180048e6b  nop     dword ptr [rax+rax+00h]
0x180048e70  mov     ebx, eax
0x180048e72  test    eax, eax
0x180048e74  jz      short loc_180048EA6
0x180048e76  mov     r8, [rdi+80h]
0x180048e7d  lea     rdx, aSWebsethttpreq_6; "%s:WebSetHttpRequestOption: WebHttpRequ"...
0x180048e84  add     r8, 38h ; '8'
0x180048e88  mov     ecx, esi
0x180048e8a  mov     r9d, eax
0x180048e8d  call    EventWrite0
0x180048e92  mov     rcx, r14; lpCriticalSection
0x180048e95  call    cs:__imp_LeaveCriticalSection
0x180048e9c  nop     dword ptr [rax+rax+00h]
0x180048ea1  jmp     loc_180048BBE
0x180048ea6  mov     rax, [rdi+28h]
0x180048eaa  test    rax, rax
0x180048ead  jz      loc_180048FA2
0x180048eb3  mov     rcx, [rdi]
0x180048eb6  lea     r8, [rbp+var_58]
0x180048eba  mov     r15d, 18h
0x180048ec0  mov     [rbp+var_50], rax
0x180048ec4  mov     rax, [rdi+30h]
0x180048ec8  mov     r9d, r15d
0x180048ecb  mov     [rbp+var_58], 1
0x180048ed3  mov     [rbp+var_48], rax
0x180048ed7  lea     edx, [r15-0Eh]
0x180048edb  call    cs:__imp_WebSetHttpRequestOption
0x180048ee2  nop     dword ptr [rax+rax+00h]
0x180048ee7  mov     r8, [rdi+80h]
0x180048eee  mov     ecx, esi
0x180048ef0  add     r8, 38h ; '8'
0x180048ef4  mov     ebx, eax
0x180048ef6  test    eax, eax
0x180048ef8  jz      short loc_180048F03
0x180048efa  lea     rdx, aSWebsethttpreq_7; "%s:WebSetHttpRequestOption: WebHttpRequ"...
0x180048f01  jmp     short loc_180048E8A
0x180048f03  mov     r9, [rdi+28h]
0x180048f07  lea     rdx, aSWebsethttpreq_2; "%s:WebSetHttpRequestOption: WebProxyCon"...
0x180048f0e  call    EventWrite0
0x180048f13  mov     rcx, [rdi+48h]
0x180048f17  test    rcx, rcx
0x180048f1a  jz      loc_180048FA2
0x180048f20  mov     eax, [rdi+50h]
0x180048f23  lea     r8, [rbp+var_40]
0x180048f27  mov     r9, r15
0x180048f2a  mov     [rbp+var_38], rcx
0x180048f2e  mov     rcx, [rdi]
0x180048f31  mov     r15d, 0Ch
0x180048f37  mov     edx, r15d
0x180048f3a  mov     [rbp+var_30], r13
0x180048f3e  mov     [rbp+var_40], 1
0x180048f45  mov     [rbp+var_3C], eax
0x180048f48  call    cs:__imp_WebSetHttpRequestOption
0x180048f4f  nop     dword ptr [rax+rax+00h]
0x180048f54  mov     ebx, eax
0x180048f56  test    eax, eax
0x180048f58  jz      short loc_180048F87
0x180048f5a  mov     rcx, r14; lpCriticalSection
0x180048f5d  call    cs:__imp_LeaveCriticalSection
0x180048f64  nop     dword ptr [rax+rax+00h]
0x180048f69  mov     r8, [rdi+80h]
0x180048f70  lea     rdx, aSWebsethttpreq_0; "%s:WebSetHttpRequestOption: WebHttpRequ"...
0x180048f77  add     r8, 38h ; '8'
  ... truncated ...
```
