# InitRpcGlobals(void)

- ea: `0x180015e08`
- end: `0x180015f20`
- name: `?InitRpcGlobals@@YAXXZ`
- size: `280`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013e88`

## callees

- `0x180006fdc`
- `0x180015e08`
- `0x1800160e4`
- `0x180023c5a`
- `0x180023ca0`

## import_xrefs

- `mqsec!ComposeRPCEndPointName` at `0x180015e66`
- `mqsec!ComposeRPCEndPointName` at `0x180015f01`
- `mqsec!ComposeRPCEndPointName` at `0x180015e66`
- `mqsec!ComposeRPCEndPointName` at `0x180015f01`
- `mqsec!GetFalconKeyValue` at `0x180015ed6`
- `mqsec!GetFalconKeyValue` at `0x180015ed6`

## pseudocode

```c
void InitRpcGlobals(void)
{
  unsigned int v0; // [rsp+30h] [rbp-238h] BYREF
  unsigned int v1[3]; // [rsp+34h] [rbp-234h] BYREF
  wchar_t v2[6]; // [rsp+40h] [rbp-228h] BYREF
  _BYTE v3[516]; // [rsp+4Ch] [rbp-21Ch] BYREF

  if ( g_hBindIndex == -1 )
    g_hBindIndex = RtpTlsAlloc();
  if ( g_hThreadIndex == -1 )
    g_hThreadIndex = RtpTlsAlloc();
  if ( !g_pwzQmmgmtEndpoint )
    ComposeRPCEndPointName(L"QMMgmtFacility", 0, &g_pwzQmmgmtEndpoint);
  if ( !g_pwzQmsvcEndpoint )
  {
    wcscpy(v2, L"QMsvc");
    memset_0(v3, 0, 0x1FCu);
    v0 = 520;
    v1[0] = 1;
    if ( GetFalconKeyValue(L"RpcLocalEp", v1, v2, &v0, L"QMsvc") == 234 )
      StringCchCopyW(v2, 0x104u, L"QMsvc");
    ComposeRPCEndPointName(v2, 0, &g_pwzQmsvcEndpoint);
  }
}

```

## disassembly

```asm
0x180015e08  push    rbx
0x180015e0a  sub     rsp, 260h
0x180015e11  mov     rax, cs:__security_cookie
0x180015e18  xor     rax, rsp
0x180015e1b  mov     [rsp+268h+var_18], rax
0x180015e23  or      ebx, 0FFFFFFFFh
0x180015e26  cmp     cs:?g_hBindIndex@@3KA, ebx; ulong g_hBindIndex
0x180015e2c  jnz     short loc_180015E39
0x180015e2e  call    ?RtpTlsAlloc@@YAKXZ; RtpTlsAlloc(void)
0x180015e33  mov     cs:?g_hBindIndex@@3KA, eax; ulong g_hBindIndex
0x180015e39  cmp     cs:?g_hThreadIndex@@3KA, ebx; ulong g_hThreadIndex
0x180015e3f  jnz     short loc_180015E4C
0x180015e41  call    ?RtpTlsAlloc@@YAKXZ; RtpTlsAlloc(void)
0x180015e46  mov     cs:?g_hThreadIndex@@3KA, eax; ulong g_hThreadIndex
0x180015e4c  cmp     cs:?g_pwzQmmgmtEndpoint@@3V?$AP@_W@@A, 0; AP<wchar_t> g_pwzQmmgmtEndpoint
0x180015e54  jnz     short loc_180015E6C
0x180015e56  lea     r8, ?g_pwzQmmgmtEndpoint@@3V?$AP@_W@@A; AP<wchar_t> g_pwzQmmgmtEndpoint
0x180015e5d  xor     edx, edx
0x180015e5f  lea     rcx, aQmmgmtfacility; "QMMgmtFacility"
0x180015e66  call    cs:__imp_?ComposeRPCEndPointName@@YAXPEB_W0PEAPEA_W@Z; ComposeRPCEndPointName(wchar_t const *,wchar_t const *,wchar_t * *)
0x180015e6c  cmp     cs:?g_pwzQmsvcEndpoint@@3V?$AP@_W@@A, 0; AP<wchar_t> g_pwzQmsvcEndpoint
0x180015e74  jnz     loc_180015F07
0x180015e7a  movsd   xmm0, qword ptr cs:aQmsvc; "QMsvc"
0x180015e82  lea     rcx, [rsp+268h+var_21C]; void *
0x180015e87  mov     eax, dword ptr cs:aQmsvc+8; "c"
0x180015e8d  xor     edx, edx; Val
0x180015e8f  mov     r8d, 1FCh; Size
0x180015e95  movsd   qword ptr [rsp+268h+var_228], xmm0
0x180015e9b  mov     [rsp+268h+var_220], eax
0x180015e9f  call    memset_0
0x180015ea4  lea     rbx, aQmsvc; "QMsvc"
0x180015eab  mov     [rsp+268h+var_238], 208h
0x180015eb3  lea     r9, [rsp+268h+var_238]
0x180015eb8  mov     [rsp+268h+var_248], rbx
0x180015ebd  lea     r8, [rsp+268h+var_228]
0x180015ec2  mov     [rsp+268h+var_234], 1
0x180015eca  lea     rdx, [rsp+268h+var_234]
0x180015ecf  lea     rcx, aRpclocalep; "RpcLocalEp"
0x180015ed6  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180015edc  cmp     eax, 0EAh
0x180015ee1  jnz     short loc_180015EF3
0x180015ee3  mov     r8, rbx; wchar_t *
0x180015ee6  lea     edx, [rax+1Ah]; unsigned __int64
0x180015ee9  lea     rcx, [rsp+268h+var_228]; wchar_t *
0x180015eee  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180015ef3  lea     r8, ?g_pwzQmsvcEndpoint@@3V?$AP@_W@@A; AP<wchar_t> g_pwzQmsvcEndpoint
0x180015efa  xor     edx, edx
0x180015efc  lea     rcx, [rsp+268h+var_228]
0x180015f01  call    cs:__imp_?ComposeRPCEndPointName@@YAXPEB_W0PEAPEA_W@Z; ComposeRPCEndPointName(wchar_t const *,wchar_t const *,wchar_t * *)
0x180015f07  mov     rcx, [rsp+268h+var_18]
0x180015f0f  xor     rcx, rsp; StackCookie
0x180015f12  call    __security_check_cookie
0x180015f17  add     rsp, 260h
0x180015f1e  pop     rbx
0x180015f1f  retn
```
