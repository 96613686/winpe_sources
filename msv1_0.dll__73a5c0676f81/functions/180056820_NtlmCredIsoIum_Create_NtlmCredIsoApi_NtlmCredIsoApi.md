# NtlmCredIsoIum::Create(NtlmCredIsoApi *,NtlmCredIsoApi * *)

- ea: `0x180056820`
- end: `0x180056aa6`
- name: `?Create@NtlmCredIsoIum@@SAJPEAVNtlmCredIsoApi@@PEAPEAV2@@Z`
- size: `646`
- prototype: `__int64 __fastcall(struct NtlmCredIsoApi *, struct NtlmCredIsoApi **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004a1c0`

## callees

- `0x180001ed0`
- `0x18000dea0`
- `0x1800200e8`
- `0x180020574`
- `0x180055504`
- `0x180056248`
- `0x180056820`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056a83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056a83`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005685f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005685f`
- `RPCRT4!NdrClientCall3` at `0x1800569af`
- `RPCRT4!NdrClientCall3` at `0x1800569af`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18005693c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18005693c`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800568ac`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800568ac`
- `RPCRT4!RpcStringFreeW` at `0x18005694c`
- `RPCRT4!RpcStringFreeW` at `0x18005694c`
- `RPCRT4!I_RpcMapWin32Status` at `0x180056922`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800569ca`
- `RPCRT4!I_RpcMapWin32Status` at `0x180056922`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800569ca`

## string_xrefs

- `0x180056877`: `NtlmCredIsoIum::Create`
- `0x1800568f7`: `NtlmCredIsoIum::Create`
- `0x180056919`: `NtlmCredIsoIum::Create`
- `0x180056978`: `NtlmCredIsoIum::Create`
- `0x1800569f3`: `NtlmCredIsoIum::Create`
- `0x180056a2f`: `NtlmCredIsoIum::Create`

## pseudocode

```c
__int64 __fastcall NtlmCredIsoIum::Create(struct NtlmCredIsoApi *a1, struct NtlmCredIsoApi **a2)
{
  HLOCAL v3; // r14
  CLIENT_CALL_RETURN v4; // rbx
  RPC_STATUS v5; // ebx
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  __int16 *v9; // rdx
  struct NtlmCredIsoApi *v10; // rdx
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-50h] BYREF
  void *v13[9]; // [rsp+50h] [rbp-48h] BYREF
  struct NtlmCredIsoApi *Simple; // [rsp+A0h] [rbp+8h] BYREF
  struct NtlmCredIsoApi **v15; // [rsp+A8h] [rbp+10h] BYREF
  const char *v16; // [rsp+B0h] [rbp+18h] BYREF
  RPC_WSTR String; // [rsp+B8h] [rbp+20h] BYREF

  v15 = a2;
  Simple = a1;
  Binding = 0;
  String = 0;
  v13[0] = 0;
  *a2 = 0;
  v3 = LocalAlloc(0x40u, 0x20u);
  v13[2] = v3;
  if ( !v3 )
  {
    LODWORD(v4.Pointer) = -1073741801;
    goto LABEL_14;
  }
  v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, Endpoint, 0, &String);
  if ( v5 )
  {
    v8 = dword_1800861D8;
    if ( (unsigned int)dword_1800861D8 <= 2 )
    {
LABEL_7:
      LODWORD(v4.Pointer) = I_RpcMapWin32Status(v5);
      goto LABEL_14;
    }
    LODWORD(Simple) = 103;
    v9 = &word_18007ACB6;
LABEL_6:
    v16 = "NtlmCredIsoIum::Create";
    LODWORD(v15) = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v8,
      (_DWORD)v9,
      v6,
      v7,
      (__int64)&v16,
      (__int64)&Simple,
      (__int64)&v15);
    goto LABEL_7;
  }
  v5 = RpcBindingFromStringBindingW(String, &Binding);
  RpcStringFreeW(&String);
  if ( v5 )
  {
    v8 = dword_1800861D8;
    if ( (unsigned int)dword_1800861D8 <= 2 )
      goto LABEL_7;
    LODWORD(Simple) = 112;
    v9 = (__int16 *)&dword_18007AB04;
    goto LABEL_6;
  }
  TraceRpcStart("NtlmCredIsoIum::Create");
  Simple = 0;
  v4.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, Binding, v13).Pointer;
  Simple = (struct NtlmCredIsoApi *)v4.Simple;
  TraceRpcEnd("NtlmCredIsoIum::Create");
  if ( SLODWORD(v4.Simple) < 0 )
    NtlmTraceErrorViaWpp("NtlmCredIsoIum::Create", 0x7Cu, "RegisterClientFailed");
  *a2 = NtlmCredIsoIum::NtlmCredIsoIum((NtlmCredIsoIum *)v3, v10, v13[0], Binding);
  v3 = 0;
LABEL_14:
  if ( v3 )
    LocalFree(v3);
  NtlmTraceStatusViaWpp("NtlmCredIsoIum::Create", 137, LODWORD(v4.Pointer));
  return LODWORD(v4.Pointer);
}

```

## disassembly

```asm
0x180056820  mov     rax, rsp
0x180056823  mov     [rax+10h], rdx
0x180056827  mov     [rax+8], rcx
0x18005682b  push    rbx
0x18005682c  push    rdi
0x18005682d  push    r14
0x18005682f  push    r15
0x180056831  sub     rsp, 78h
0x180056835  mov     r15, rdx
0x180056838  mov     qword ptr [rax-50h], 0
0x180056840  mov     qword ptr [rax+20h], 0
0x180056848  mov     qword ptr [rax-48h], 0
0x180056850  mov     qword ptr [rdx], 0
0x180056857  mov     edx, 20h ; ' '; uBytes
0x18005685c  lea     ecx, [rdx+20h]; uFlags
0x18005685f  call    cs:__imp_LocalAlloc
0x180056865  mov     r14, rax
0x180056868  mov     [rsp+98h+var_38], rax
0x18005686d  test    rax, rax
0x180056870  jnz     short loc_180056883
0x180056872  mov     ebx, 0C0000017h
0x180056877  lea     rdi, aNtlmcredisoium_1; "NtlmCredIsoIum::Create"
0x18005687e  jmp     loc_180056A7B
0x180056883  lea     rax, [rsp+98h+String]
0x18005688b  mov     [rsp+98h+StringBinding], rax; StringBinding
0x180056890  mov     [rsp+98h+Options], 0; Options
0x180056899  lea     r9, Endpoint; "LSA_ISO_RPC_SERVER"
0x1800568a0  xor     r8d, r8d; NetworkAddr
0x1800568a3  lea     rdx, ProtSeq; "ncalrpc"
0x1800568aa  xor     ecx, ecx; ObjUuid
0x1800568ac  call    cs:__imp_RpcStringBindingComposeW
0x1800568b2  mov     ebx, eax
0x1800568b4  test    eax, eax
0x1800568b6  jz      short loc_18005692F
0x1800568b8  mov     ecx, cs:dword_1800861D8
0x1800568be  cmp     ecx, 2
0x1800568c1  jbe     short loc_180056919
0x1800568c3  mov     dword ptr [rsp+98h+arg_0], 67h ; 'g'
0x1800568ce  lea     rdx, word_18007ACB6
0x1800568d5  lea     rax, [rsp+98h+arg_8]
0x1800568dd  mov     [rsp+98h+var_68], rax
0x1800568e2  lea     rax, [rsp+98h+arg_0]
0x1800568ea  mov     [rsp+98h+StringBinding], rax
0x1800568ef  lea     rax, [rsp+98h+arg_10]
0x1800568f7  lea     rdi, aNtlmcredisoium_1; "NtlmCredIsoIum::Create"
0x1800568fe  mov     [rsp+98h+Options], rax
0x180056903  mov     [rsp+98h+arg_10], rdi
0x18005690b  mov     dword ptr [rsp+98h+arg_8], ebx
0x180056912  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180056917  jmp     short loc_180056920
0x180056919  lea     rdi, aNtlmcredisoium_1; "NtlmCredIsoIum::Create"
0x180056920  mov     ecx, ebx; Status
0x180056922  call    cs:__imp_I_RpcMapWin32Status
0x180056928  mov     ebx, eax
0x18005692a  jmp     loc_180056A7B
0x18005692f  lea     rdx, [rsp+98h+Binding]; Binding
0x180056934  mov     rcx, [rsp+98h+String]; StringBinding
0x18005693c  call    cs:__imp_RpcBindingFromStringBindingW
0x180056942  mov     ebx, eax
0x180056944  lea     rcx, [rsp+98h+String]; String
0x18005694c  call    cs:__imp_RpcStringFreeW
0x180056952  test    ebx, ebx
0x180056954  jz      short loc_180056978
0x180056956  mov     ecx, cs:dword_1800861D8
0x18005695c  cmp     ecx, 2
0x18005695f  jbe     short loc_180056919
0x180056961  mov     dword ptr [rsp+98h+arg_0], 70h ; 'p'
0x18005696c  lea     rdx, dword_18007AB04
0x180056973  jmp     loc_1800568D5
0x180056978  lea     rdi, aNtlmcredisoium_1; "NtlmCredIsoIum::Create"
0x18005697f  mov     rcx, rdi
0x180056982  call    TraceRpcStart
0x180056987  nop
0x180056988  mov     [rsp+98h+arg_0], 0
0x180056994  lea     rax, [rsp+98h+var_48]
0x180056999  mov     [rsp+98h+Options], rax
0x18005699e  mov     r9, [rsp+98h+Binding]
0x1800569a3  xor     r8d, r8d; pReturnValue
0x1800569a6  xor     edx, edx; nProcNum
0x1800569a8  lea     rcx, pProxyInfo; pProxyInfo
0x1800569af  call    cs:__imp_NdrClientCall3
0x1800569b5  mov     rbx, rax
0x1800569b8  mov     [rsp+98h+arg_0], rax
0x1800569c0  mov     [rsp+98h+var_58], eax
0x1800569c4  jmp     short loc_180056A43
0x1800569c6  mov     edi, eax
0x1800569c8  mov     ecx, eax; Status
0x1800569ca  call    cs:__imp_I_RpcMapWin32Status
0x1800569d0  mov     ebx, eax
0x1800569d2  mov     [rsp+98h+var_58], eax
0x1800569d6  mov     ecx, cs:dword_1800861D8
0x1800569dc  cmp     ecx, 2
0x1800569df  jbe     short loc_180056A2F
0x1800569e1  mov     dword ptr [rsp+98h+arg_0], edi
0x1800569e8  mov     dword ptr [rsp+98h+arg_10], 79h ; 'y'
0x1800569f3  lea     rax, aNtlmcredisoium_1; "NtlmCredIsoIum::Create"
0x1800569fa  mov     [rsp+98h+var_40], rax
0x1800569ff  lea     rax, [rsp+98h+arg_0]
0x180056a07  mov     [rsp+98h+var_68], rax
0x180056a0c  lea     rax, [rsp+98h+arg_10]
0x180056a14  mov     [rsp+98h+StringBinding], rax
0x180056a19  lea     rax, [rsp+98h+var_40]
0x180056a1e  mov     [rsp+98h+Options], rax
0x180056a23  lea     rdx, word_18007AF9E
0x180056a2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180056a2f  lea     rdi, aNtlmcredisoium_1; "NtlmCredIsoIum::Create"
0x180056a36  mov     r15, [rsp+98h+arg_8]
0x180056a3e  mov     r14, [rsp+98h+var_38]
0x180056a43  mov     rcx, rdi
0x180056a46  call    TraceRpcEnd
0x180056a4b  test    ebx, ebx
0x180056a4d  jns     short loc_180056A63
0x180056a4f  lea     r8, aRegisterclient; "RegisterClientFailed"
0x180056a56  mov     edx, 7Ch ; '|'; unsigned int
0x180056a5b  mov     rcx, rdi; char *
0x180056a5e  call    ?NtlmTraceErrorViaWpp@@YAXPEBDK0@Z; NtlmTraceErrorViaWpp(char const *,ulong,char const *)
0x180056a63  mov     r9, [rsp+98h+Binding]; void *
0x180056a68  mov     r8, [rsp+98h+var_48]; void *
0x180056a6d  mov     rcx, r14; this
0x180056a70  call    ??0NtlmCredIsoIum@@AEAA@PEAVNtlmCredIsoApi@@PEAX1@Z; NtlmCredIsoIum::NtlmCredIsoIum(NtlmCredIsoApi *,void *,void *)
0x180056a75  mov     [r15], rax
0x180056a78  xor     r14d, r14d
0x180056a7b  test    r14, r14
0x180056a7e  jz      short loc_180056A89
0x180056a80  mov     rcx, r14; hMem
0x180056a83  call    cs:__imp_LocalFree
0x180056a89  mov     r8d, ebx
0x180056a8c  mov     edx, 89h
0x180056a91  mov     rcx, rdi
0x180056a94  call    NtlmTraceStatusViaWpp
0x180056a99  mov     eax, ebx
0x180056a9b  add     rsp, 78h
0x180056a9f  pop     r15
0x180056aa1  pop     r14
0x180056aa3  pop     rdi
0x180056aa4  pop     rbx
0x180056aa5  retn
0x18006c210  push    rbp
0x18006c212  sub     rsp, 40h
0x18006c216  mov     rbp, rdx
0x18006c219  mov     rcx, [rcx]
0x18006c21c  mov     ecx, [rcx]; ExceptionCode
0x18006c21e  call    cs:__imp_RpcExceptionFilter
0x18006c224  nop
0x18006c225  add     rsp, 40h
0x18006c229  pop     rbp
0x18006c22a  retn
```
