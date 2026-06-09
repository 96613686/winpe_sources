# NtlmCredIsoIum::CompareEncryptedNtowfAndDecryptSecrets(_UNICODE_STRING *,_MSV1_0_SECRETS_WRAPPER *)

- ea: `0x180056640`
- end: `0x180056817`
- name: `?CompareEncryptedNtowfAndDecryptSecrets@NtlmCredIsoIum@@UEAAJPEAU_UNICODE_STRING@@PEAU_MSV1_0_SECRETS_WRAPPER@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(NtlmCredIsoIum *__hidden this, struct _UNICODE_STRING *, struct _MSV1_0_SECRETS_WRAPPER *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001ed0`
- `0x18000dea0`
- `0x1800200e8`
- `0x180020574`
- `0x18002fb50`
- `0x180030844`
- `0x180056640`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800566c1`
- `RPCRT4!NdrClientCall3` at `0x1800566c1`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800566d9`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800566d9`

## string_xrefs

- `0x180056685`: `NtlmCredIsoIum::CompareEncryptedNtowfAndDecryptSecrets`
- `0x1800566fc`: `NtlmCredIsoIum::CompareEncryptedNtowfAndDecryptSecrets`
- `0x18005673a`: `NtlmCredIsoIum::CompareEncryptedNtowfAndDecryptSecrets`
- `0x18005674e`: `NtlmCredIsoIum::CompareEncryptedNtowfAndDecryptSecrets`

## pseudocode

```c
__int64 __fastcall NtlmCredIsoIum::CompareEncryptedNtowfAndDecryptSecrets(
        NtlmCredIsoIum *this,
        struct _UNICODE_STRING *a2,
        struct _MSV1_0_SECRETS_WRAPPER *a3)
{
  struct _MSV1_0_SECRETS_WRAPPER *v6; // rdi
  int Pointer; // ebx
  _OWORD *v8; // rax
  __int64 v9; // rcx
  _BYTE v11[352]; // [rsp+70h] [rbp-188h] BYREF

  v6 = a3;
  memset_0(v11, 0, sizeof(v11));
  TraceRpcStart("NtlmCredIsoIum::CompareEncryptedNtowfAndDecryptSecrets");
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x12u,
                            0,
                            *((_QWORD *)this + 2),
                            a2,
                            v6,
                            v11).Pointer;
  TraceRpcEnd("NtlmCredIsoIum::CompareEncryptedNtowfAndDecryptSecrets");
  NtlmTraceStatusViaWpp("NtlmCredIsoIum::CompareEncryptedNtowfAndDecryptSecrets", 564, (unsigned int)Pointer);
  if ( Pointer >= 0 )
  {
    v8 = v11;
    v9 = 2;
    do
    {
      *(_OWORD *)v6 = *v8;
      *((_OWORD *)v6 + 1) = v8[1];
      *((_OWORD *)v6 + 2) = v8[2];
      *((_OWORD *)v6 + 3) = v8[3];
      *((_OWORD *)v6 + 4) = v8[4];
      *((_OWORD *)v6 + 5) = v8[5];
      *((_OWORD *)v6 + 6) = v8[6];
      *((_OWORD *)v6 + 7) = v8[7];
      v6 = (struct _MSV1_0_SECRETS_WRAPPER *)((char *)v6 + 128);
      v8 += 8;
      --v9;
    }
    while ( v9 );
    *(_OWORD *)v6 = *v8;
    *((_OWORD *)v6 + 1) = v8[1];
    *((_OWORD *)v6 + 2) = v8[2];
    *((_OWORD *)v6 + 3) = v8[3];
    *((_OWORD *)v6 + 4) = v8[4];
    *((_OWORD *)v6 + 5) = v8[5];
    *(_QWORD *)a3 = LocalhostNtLmCredIsoObj::IsoObj;
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180056640  mov     [rsp+arg_18], rbx
0x180056645  push    rsi
0x180056646  push    rdi
0x180056647  push    r14
0x180056649  sub     rsp, 1E0h
0x180056650  mov     rax, cs:__security_cookie
0x180056657  xor     rax, rsp
0x18005665a  mov     [rsp+1F8h+var_28], rax
0x180056662  mov     rsi, r8
0x180056665  mov     r14, rdx
0x180056668  mov     rbx, rcx
0x18005666b  mov     [rsp+1F8h+var_1A0], r8
0x180056670  mov     rdi, r8
0x180056673  xor     edx, edx; Val
0x180056675  mov     r8d, 160h; Size
0x18005667b  lea     rcx, [rsp+1F8h+var_188]; void *
0x180056680  call    memset_0
0x180056685  lea     rcx, aNtlmcredisoium_18; "NtlmCredIsoIum::CompareEncryptedNtowfAn"...
0x18005668c  call    TraceRpcStart
0x180056691  nop
0x180056692  mov     [rsp+1F8h+var_1B0], 0
0x18005669b  lea     rax, [rsp+1F8h+var_188]
0x1800566a0  mov     [rsp+1F8h+var_1C8], rax
0x1800566a5  mov     [rsp+1F8h+var_1D0], rdi
0x1800566aa  mov     [rsp+1F8h+var_1D8], r14
0x1800566af  mov     r9, [rbx+10h]
0x1800566b3  xor     r8d, r8d; pReturnValue
0x1800566b6  lea     edx, [r8+12h]; nProcNum
0x1800566ba  lea     rcx, pProxyInfo; pProxyInfo
0x1800566c1  call    cs:__imp_NdrClientCall3
0x1800566c7  mov     rbx, rax
0x1800566ca  mov     [rsp+1F8h+var_1B0], rax
0x1800566cf  mov     [rsp+1F8h+var_1B8], eax
0x1800566d3  jmp     short loc_18005673A
0x1800566d5  mov     edi, eax
0x1800566d7  mov     ecx, eax; Status
0x1800566d9  call    cs:__imp_I_RpcMapWin32Status
0x1800566df  mov     ebx, eax
0x1800566e1  mov     [rsp+1F8h+var_1B8], eax
0x1800566e5  mov     ecx, cs:dword_1800861D8
0x1800566eb  cmp     ecx, 2
0x1800566ee  jbe     short loc_180056732
0x1800566f0  mov     [rsp+1F8h+var_1B4], edi
0x1800566f4  mov     dword ptr [rsp+1F8h+var_1B0], 232h
0x1800566fc  lea     rax, aNtlmcredisoium_18; "NtlmCredIsoIum::CompareEncryptedNtowfAn"...
0x180056703  mov     [rsp+1F8h+var_1A8], rax
0x180056708  lea     rax, [rsp+1F8h+var_1B4]
0x18005670d  mov     [rsp+1F8h+var_1C8], rax
0x180056712  lea     rax, [rsp+1F8h+var_1B0]
0x180056717  mov     [rsp+1F8h+var_1D0], rax
0x18005671c  lea     rax, [rsp+1F8h+var_1A8]
0x180056721  mov     [rsp+1F8h+var_1D8], rax
0x180056726  lea     rdx, dword_18007ABFC
0x18005672d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180056732  mov     rsi, [rsp+1F8h+var_1A0]
0x180056737  mov     rdi, rsi
0x18005673a  lea     rcx, aNtlmcredisoium_18; "NtlmCredIsoIum::CompareEncryptedNtowfAn"...
0x180056741  call    TraceRpcEnd
0x180056746  mov     r8d, ebx
0x180056749  mov     edx, 234h
0x18005674e  lea     rcx, aNtlmcredisoium_18; "NtlmCredIsoIum::CompareEncryptedNtowfAn"...
0x180056755  call    NtlmTraceStatusViaWpp
0x18005675a  test    ebx, ebx
0x18005675c  js      loc_1800567F1
0x180056762  lea     rax, [rsp+1F8h+var_188]
0x180056767  mov     ecx, 2
0x18005676c  lea     edx, [rcx+7Eh]
0x18005676f  movups  xmm0, xmmword ptr [rax]
0x180056772  movups  xmmword ptr [rdi], xmm0
0x180056775  movups  xmm1, xmmword ptr [rax+10h]
0x180056779  movups  xmmword ptr [rdi+10h], xmm1
0x18005677d  movups  xmm0, xmmword ptr [rax+20h]
0x180056781  movups  xmmword ptr [rdi+20h], xmm0
0x180056785  movups  xmm1, xmmword ptr [rax+30h]
0x180056789  movups  xmmword ptr [rdi+30h], xmm1
0x18005678d  movups  xmm0, xmmword ptr [rax+40h]
0x180056791  movups  xmmword ptr [rdi+40h], xmm0
0x180056795  movups  xmm1, xmmword ptr [rax+50h]
0x180056799  movups  xmmword ptr [rdi+50h], xmm1
0x18005679d  movups  xmm0, xmmword ptr [rax+60h]
0x1800567a1  movups  xmmword ptr [rdi+60h], xmm0
0x1800567a5  movups  xmm1, xmmword ptr [rax+70h]
0x1800567a9  movups  xmmword ptr [rdi+70h], xmm1
0x1800567ad  add     rdi, rdx
0x1800567b0  add     rax, rdx
0x1800567b3  sub     rcx, 1
0x1800567b7  jnz     short loc_18005676F
0x1800567b9  movups  xmm0, xmmword ptr [rax]
0x1800567bc  movups  xmmword ptr [rdi], xmm0
0x1800567bf  movups  xmm1, xmmword ptr [rax+10h]
0x1800567c3  movups  xmmword ptr [rdi+10h], xmm1
0x1800567c7  movups  xmm0, xmmword ptr [rax+20h]
0x1800567cb  movups  xmmword ptr [rdi+20h], xmm0
0x1800567cf  movups  xmm1, xmmword ptr [rax+30h]
0x1800567d3  movups  xmmword ptr [rdi+30h], xmm1
0x1800567d7  movups  xmm0, xmmword ptr [rax+40h]
0x1800567db  movups  xmmword ptr [rdi+40h], xmm0
0x1800567df  movups  xmm1, xmmword ptr [rax+50h]
0x1800567e3  movups  xmmword ptr [rdi+50h], xmm1
0x1800567e7  mov     rax, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x1800567ee  mov     [rsi], rax
0x1800567f1  mov     eax, ebx
0x1800567f3  mov     rcx, [rsp+1F8h+var_28]
0x1800567fb  xor     rcx, rsp; StackCookie
0x1800567fe  call    __security_check_cookie
0x180056803  mov     rbx, [rsp+1F8h+arg_18]
0x18005680b  add     rsp, 1E0h
0x180056812  pop     r14
0x180056814  pop     rdi
0x180056815  pop     rsi
0x180056816  retn
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
