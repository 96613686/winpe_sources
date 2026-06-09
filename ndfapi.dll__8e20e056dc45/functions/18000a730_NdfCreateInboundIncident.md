# NdfCreateInboundIncident

- ea: `0x18000a730`
- end: `0x18000a9da`
- name: `NdfCreateInboundIncident`
- size: `682`
- prototype: `HRESULT __stdcall(LPCWSTR applicationID, LPCWSTR serviceID, SID *userID, const SOCKADDR_STORAGE *localTarget, IPPROTO protocol, DWORD dwFlags, NDFHANDLE *handle)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000721c`
- `0x180008f1c`
- `0x1800098b0`
- `0x18000a730`
- `0x18000a9e0`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000a9b1`
- `ole32!CoTaskMemFree` at `0x18000a9b1`
- `wdi!WdiCancel` at `0x18000a7a8`
- `wdi!WdiCancel` at `0x18000a7a8`

## string_xrefs

- `0x18000a952`: `protocol`
- `0x18000a788`: `NdfCreateInboundIncident`
- `0x18000a833`: `serviceid`

## pseudocode

```c
HRESULT __stdcall NdfCreateInboundIncident(
        LPCWSTR applicationID,
        LPCWSTR serviceID,
        SID *userID,
        const SOCKADDR_STORAGE *localTarget,
        IPPROTO protocol,
        DWORD dwFlags,
        NDFHANDLE *handle)
{
  DWORD v12; // edx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int16 v22; // si
  unsigned __int64 v23; // rbx
  HRESULT Incident; // edi
  unsigned __int16 v25; // si
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rcx
  LPVOID pv[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v29; // [rsp+30h] [rbp-D0h]
  __int64 v30; // [rsp+38h] [rbp-C8h]
  HELPER_ATTRIBUTE attributes[6]; // [rsp+40h] [rbp-C0h] BYREF

  v30 = 15;
  v29 = 0;
  LOBYTE(pv[0]) = 0;
  std::string::assign((size_t *)pv, "NdfCreateInboundIncident", 0x18u);
  TelemeterAPICall(pv);
  if ( (unsigned int)WdiCancel(0) == -2147023611 )
    return -2147467260;
  if ( !applicationID && !serviceID || dwFlags > 3 )
    return -2147024809;
  attributes[0].pwszName = 0;
  memset_0(&attributes[0].type, 0, 0x358u);
  v12 = 0;
  if ( applicationID )
  {
    attributes[0].type = AT_STRING;
    attributes[0].pwszName = L"appid";
    v12 = 1;
    attributes[0].Int64 = (LONGLONG)applicationID;
  }
  if ( serviceID )
  {
    v13 = (unsigned __int16)v12;
    LOWORD(v12) = v12 + 1;
    attributes[v13].pwszName = L"serviceid";
    attributes[v13].type = AT_STRING;
    *((_QWORD *)&attributes[0].Boolean + v13 * 18) = serviceID;
  }
  v14 = (unsigned __int16)v12;
  attributes[v14].pwszName = L"localaddr";
  attributes[v14].type = AT_SOCKADDR;
  if ( localTarget )
  {
    v15 = *(_OWORD *)localTarget->__ss_pad2;
    *((_OWORD *)&attributes[0].Boolean + 9 * (unsigned __int16)v12) = *(_OWORD *)&localTarget->ss_family;
    v16 = *(_OWORD *)&localTarget->__ss_pad2[16];
    *((_OWORD *)&attributes[0].OctetString + 9 * (unsigned __int16)v12 + 1) = v15;
    v17 = *(_OWORD *)&localTarget->__ss_pad2[32];
    *((_OWORD *)&attributes[0].OctetString + 9 * (unsigned __int16)v12 + 2) = v16;
    v18 = *(_OWORD *)&localTarget->__ss_pad2[48];
    *((_OWORD *)&attributes[0].OctetString + 9 * (unsigned __int16)v12 + 3) = v17;
    v19 = *(_OWORD *)&localTarget->__ss_pad2[64];
    *((_OWORD *)&attributes[0].OctetString + 9 * (unsigned __int16)v12 + 4) = v18;
    v20 = *(_OWORD *)&localTarget->__ss_pad2[80];
    *((_OWORD *)&attributes[0].OctetString + 9 * (unsigned __int16)v12 + 5) = v19;
    v21 = *(_OWORD *)&localTarget->__ss_pad2[96];
    *((_OWORD *)&attributes[0].OctetString + 9 * (unsigned __int16)v12 + 6) = v20;
    *((_OWORD *)&attributes[0].OctetString + 9 * (unsigned __int16)v12 + 7) = v21;
  }
  LOWORD(v12) = v12 + 1;
  v22 = v12;
  *(_OWORD *)pv = 0;
  v23 = 18LL * (unsigned __int16)v12;
  attributes[v23 / 0x12].pwszName = L"userid";
  attributes[v23 / 0x12].type = AT_OCTET_STRING;
  *(&attributes[0].Boolean + 2 * v23) = 12;
  if ( userID )
  {
    *(&attributes[0].Int64 + 18 * (unsigned __int16)v12 + 1) = (LONGLONG)userID;
LABEL_17:
    v25 = v22 + 1;
    v26 = 18LL * v25;
    attributes[v26 / 0x12].pwszName = L"inboundflags";
    attributes[v26 / 0x12].type = AT_UINT32;
    *(&attributes[0].Boolean + 2 * v26) = dwFlags;
    v27 = 18LL * (unsigned __int16)(v25 + 1);
    attributes[v27 / 0x12].pwszName = L"protocol";
    attributes[v27 / 0x12].type = AT_UINT32;
    *(&attributes[0].Boolean + 2 * v27) = protocol;
    Incident = NdfCreateIncident(L"Winsock", (unsigned __int16)(v25 + 2), attributes, handle);
    if ( Incident >= 0 && *handle )
      *((_DWORD *)*handle + 4) = 8;
    goto LABEL_20;
  }
  Incident = GetSID((struct tagOCTET_STRING *)pv, v12);
  if ( Incident >= 0 )
  {
    *(&attributes[0].Boolean + 2 * v23) = (BOOL)pv[0];
    *((LPVOID *)&attributes[0].Int64 + v23 + 1) = pv[1];
    goto LABEL_17;
  }
LABEL_20:
  if ( LODWORD(pv[0]) )
    CoTaskMemFree(pv[1]);
  return Incident;
}

```

## disassembly

```asm
0x18000a730  push    rbp
0x18000a732  push    rbx
0x18000a733  push    rsi
0x18000a734  push    rdi
0x18000a735  push    r12
0x18000a737  push    r14
0x18000a739  push    r15
0x18000a73b  lea     rbp, [rsp-2B0h]
0x18000a743  sub     rsp, 3B0h
0x18000a74a  mov     rax, cs:__security_cookie
0x18000a751  xor     rax, rsp
0x18000a754  mov     [rbp+2E0h+var_40], rax
0x18000a75b  mov     r12, [rbp+2E0h+handle]
0x18000a762  mov     r14, r8
0x18000a765  mov     rdi, rdx
0x18000a768  mov     [rsp+3E0h+var_3A8], 0Fh
0x18000a771  mov     rsi, rcx
0x18000a774  mov     [rsp+3E0h+var_3B0], 0
0x18000a77d  mov     r8d, 18h; Size
0x18000a783  mov     byte ptr [rsp+3E0h+pv], 0
0x18000a788  lea     rdx, aNdfcreateinbou_0; "NdfCreateInboundIncident"
0x18000a78f  mov     rbx, r9
0x18000a792  lea     rcx, [rsp+3E0h+pv]; void *
0x18000a797  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000a79c  lea     rcx, [rsp+3E0h+pv]
0x18000a7a1  call    ?TelemeterAPICall@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; TelemeterAPICall(std::string)
0x18000a7a6  xor     ecx, ecx
0x18000a7a8  call    cs:__imp_WdiCancel
0x18000a7ae  cmp     eax, 80070505h
0x18000a7b3  jnz     short loc_18000A7BF
0x18000a7b5  mov     eax, 80004004h
0x18000a7ba  jmp     loc_18000A9B9
0x18000a7bf  test    rsi, rsi
0x18000a7c2  jnz     short loc_18000A7C9
0x18000a7c4  test    rdi, rdi
0x18000a7c7  jz      short loc_18000A7D6
0x18000a7c9  mov     r15d, [rbp+2E0h+dwFlags]
0x18000a7d0  cmp     r15d, 3
0x18000a7d4  jbe     short loc_18000A7E0
0x18000a7d6  mov     eax, 80070057h
0x18000a7db  jmp     loc_18000A9B9
0x18000a7e0  xor     edx, edx; Val
0x18000a7e2  mov     [rsp+3E0h+attributes.pwszName], 0
0x18000a7eb  mov     r8d, 358h; Size
0x18000a7f1  lea     rcx, [rsp+3E0h+attributes.type]; void *
0x18000a7f6  call    memset_0
0x18000a7fb  xor     edx, edx
0x18000a7fd  lea     r8d, [rdx+0Ah]
0x18000a801  lea     r9d, [rdx+1]
0x18000a805  test    rsi, rsi
0x18000a808  jz      short loc_18000A824
0x18000a80a  lea     rax, aAppid; "appid"
0x18000a811  mov     [rsp+3E0h+attributes.type], r8d
0x18000a816  mov     [rsp+3E0h+attributes.pwszName], rax
0x18000a81b  movzx   edx, r9w
0x18000a81f  mov     qword ptr [rsp+3E0h+attributes.10h], rsi
0x18000a824  test    rdi, rdi
0x18000a827  jz      short loc_18000A84D
0x18000a829  movzx   eax, dx
0x18000a82c  lea     rcx, [rax+rax*8]
0x18000a830  add     rcx, rcx
0x18000a833  lea     rax, aServiceid; "serviceid"
0x18000a83a  add     dx, r9w
0x18000a83e  mov     [rsp+rcx*8+3E0h+attributes.pwszName], rax
0x18000a843  mov     [rsp+rcx*8+3E0h+attributes.type], r8d
0x18000a848  mov     qword ptr [rsp+rcx*8+3E0h+attributes.10h], rdi
0x18000a84d  movzx   eax, dx
0x18000a850  lea     rcx, [rax+rax*8]
0x18000a854  add     rcx, rcx
0x18000a857  lea     rax, aLocaladdr; "localaddr"
0x18000a85e  mov     [rsp+rcx*8+3E0h+attributes.pwszName], rax
0x18000a863  mov     [rsp+rcx*8+3E0h+attributes.type], 0Dh
0x18000a86b  test    rbx, rbx
0x18000a86e  jz      short loc_18000A8B7
0x18000a870  movups  xmm0, xmmword ptr [rbx]
0x18000a873  movups  xmm1, xmmword ptr [rbx+10h]
0x18000a877  movups  xmmword ptr [rsp+rcx*8+3E0h+attributes.10h], xmm0
0x18000a87c  movups  xmm0, xmmword ptr [rbx+20h]
0x18000a880  movups  xmmword ptr [rsp+rcx*8+3E0h+attributes.10h+10h], xmm1
0x18000a885  movups  xmm1, xmmword ptr [rbx+30h]
0x18000a889  movups  xmmword ptr [rsp+rcx*8+3E0h+attributes.10h+20h], xmm0
0x18000a88e  movups  xmm0, xmmword ptr [rbx+40h]
0x18000a892  movups  xmmword ptr [rbp+rcx*8+2E0h+attributes.10h+30h], xmm1
0x18000a897  movups  xmm1, xmmword ptr [rbx+50h]
0x18000a89b  movups  xmmword ptr [rbp+rcx*8+2E0h+attributes.10h+40h], xmm0
0x18000a8a0  movups  xmm0, xmmword ptr [rbx+60h]
0x18000a8a4  movups  xmmword ptr [rbp+rcx*8+2E0h+attributes.10h+50h], xmm1
0x18000a8a9  movups  xmm1, xmmword ptr [rbx+70h]
0x18000a8ad  movups  xmmword ptr [rbp+rcx*8+2E0h+attributes.10h+60h], xmm0
0x18000a8b2  movups  xmmword ptr [rbp+rcx*8+2E0h+attributes.10h+70h], xmm1
0x18000a8b7  add     dx, r9w; int
0x18000a8bb  lea     rax, aUserid; "userid"
0x18000a8c2  movzx   esi, dx
0x18000a8c5  xorps   xmm0, xmm0
0x18000a8c8  movups  xmmword ptr [rsp+3E0h+pv], xmm0
0x18000a8cd  lea     rbx, [rsi+rsi*8]
0x18000a8d1  add     rbx, rbx
0x18000a8d4  mov     [rsp+rbx*8+3E0h+attributes.pwszName], rax
0x18000a8d9  mov     [rsp+rbx*8+3E0h+attributes.type], 0Eh
0x18000a8e1  mov     dword ptr [rsp+rbx*8+3E0h+attributes.10h], 0Ch
0x18000a8e9  test    r14, r14
0x18000a8ec  jz      short loc_18000A8F5
0x18000a8ee  mov     qword ptr [rsp+rbx*8+3E0h+attributes.10h+8], r14
0x18000a8f3  jmp     short loc_18000A921
0x18000a8f5  lea     rcx, [rsp+3E0h+pv]; struct tagOCTET_STRING *
0x18000a8fa  call    ?GetSID@@YAJPEAUtagOCTET_STRING@@H@Z; GetSID(tagOCTET_STRING *,int)
0x18000a8ff  mov     edi, eax
0x18000a901  test    eax, eax
0x18000a903  js      loc_18000A9A5
0x18000a909  mov     eax, dword ptr [rsp+3E0h+pv]
0x18000a90d  mov     r9d, 1
0x18000a913  mov     dword ptr [rsp+rbx*8+3E0h+attributes.10h], eax
0x18000a917  mov     rax, [rsp+3E0h+pv+8]
0x18000a91c  mov     qword ptr [rsp+rbx*8+3E0h+attributes.10h+8], rax
0x18000a921  add     si, r9w
0x18000a925  lea     rdx, aInboundflags; "inboundflags"
0x18000a92c  movzx   ecx, si
0x18000a92f  mov     r8d, 7
0x18000a935  lea     rax, [rcx+rcx*8]
0x18000a939  add     cx, r9w
0x18000a93d  add     rax, rax
0x18000a940  mov     [rsp+rax*8+3E0h+attributes.pwszName], rdx
0x18000a945  mov     [rsp+rax*8+3E0h+attributes.type], r8d
0x18000a94a  movzx   edx, cx
0x18000a94d  mov     dword ptr [rsp+rax*8+3E0h+attributes.10h], r15d
0x18000a952  lea     rax, aProtocol; "protocol"
0x18000a959  lea     rcx, [rdx+rdx*8]
0x18000a95d  add     dx, r9w
0x18000a961  add     rcx, rcx
0x18000a964  movzx   edx, dx; celt
0x18000a967  mov     r9, r12; handle
0x18000a96a  mov     [rsp+rcx*8+3E0h+attributes.pwszName], rax
0x18000a96f  mov     eax, [rbp+2E0h+protocol]
0x18000a975  mov     [rsp+rcx*8+3E0h+attributes.type], r8d
0x18000a97a  lea     r8, [rsp+3E0h+attributes]; attributes
0x18000a97f  mov     dword ptr [rsp+rcx*8+3E0h+attributes.10h], eax
0x18000a983  lea     rcx, aWinsock; "Winsock"
0x18000a98a  call    NdfCreateIncident
0x18000a98f  mov     edi, eax
0x18000a991  test    eax, eax
0x18000a993  js      short loc_18000A9A5
0x18000a995  mov     rax, [r12]
0x18000a999  test    rax, rax
0x18000a99c  jz      short loc_18000A9A5
0x18000a99e  mov     dword ptr [rax+10h], 8
0x18000a9a5  cmp     dword ptr [rsp+3E0h+pv], 0
0x18000a9aa  jz      short loc_18000A9B7
0x18000a9ac  mov     rcx, [rsp+3E0h+pv+8]; pv
0x18000a9b1  call    cs:__imp_CoTaskMemFree
0x18000a9b7  mov     eax, edi
0x18000a9b9  mov     rcx, [rbp+2E0h+var_40]
0x18000a9c0  xor     rcx, rsp; StackCookie
0x18000a9c3  call    __security_check_cookie
0x18000a9c8  add     rsp, 3B0h
0x18000a9cf  pop     r15
0x18000a9d1  pop     r14
0x18000a9d3  pop     r12
0x18000a9d5  pop     rdi
0x18000a9d6  pop     rsi
0x18000a9d7  pop     rbx
0x18000a9d8  pop     rbp
0x18000a9d9  retn
```
