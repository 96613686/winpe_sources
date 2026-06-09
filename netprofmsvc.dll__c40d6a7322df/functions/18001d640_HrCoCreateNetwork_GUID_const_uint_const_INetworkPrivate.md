# HrCoCreateNetwork(_GUID const *,uint const *,INetworkPrivate * *)

- ea: `0x18001d640`
- end: `0x18001d7cc`
- name: `?HrCoCreateNetwork@@YAJPEBU_GUID@@PEBIPEAPEAUINetworkPrivate@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(const struct _GUID *, const unsigned int *, struct INetworkPrivate **)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d430`
- `0x18001d504`
- `0x180083f40`
- `0x180084ca0`
- `0x18009dc10`

## callees

- `0x18001d640`
- `0x18001d840`
- `0x1800360b0`
- `0x180083ff4`
- `0x1800841c4`
- `0x1800a88a0`
- `0x1800a88c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d777`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001d762`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001d762`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001d66d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001d66d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001d70d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001d70d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001d74a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001d74a`
- `IPHLPAPI!GetSessionCompartmentId` at `0x18001d758`
- `IPHLPAPI!GetSessionCompartmentId` at `0x18001d758`

## pseudocode

```c
__int64 __fastcall HrCoCreateNetwork(const struct _GUID *a1, NET_IF_COMPARTMENT_ID *a2, struct INetworkPrivate **a3)
{
  NET_IF_COMPARTMENT_ID SessionCompartmentId; // edi
  Network *v6; // rax
  Network *v7; // rbx
  unsigned int v8; // edi
  HRESULT v10; // eax
  unsigned int v11; // ebx
  signed int LastError; // eax
  ULONG TokenInformation; // [rsp+30h] [rbp-88h] BYREF
  DWORD ReturnLength[3]; // [rsp+34h] [rbp-84h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-78h] BYREF

  if ( StringFromGUID2(a1, sz, 39) != 39 )
    return 2147500037LL;
  if ( a2 )
  {
    SessionCompartmentId = *a2;
  }
  else
  {
    SessionCompartmentId = 0;
    v10 = CoImpersonateClient();
    v11 = 0;
    if ( v10 != -2147417833 )
      v11 = v10;
    if ( v11 )
      return v11;
    ReturnLength[0] = 0;
    TokenInformation = 0;
    if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenSessionId, &TokenInformation, 4u, ReturnLength) )
    {
      SessionCompartmentId = GetSessionCompartmentId(TokenInformation);
      v11 = 0;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    CoRevertToSelf();
    if ( v11 )
      return v11;
  }
  *a3 = 0;
  v6 = (Network *)operator new(0x298u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v6 )
    return (unsigned int)-2147024882;
  v7 = Network::Network(v6);
  v8 = Network::RuntimeClassInitialize(v7, SessionCompartmentId, sz);
  if ( (v8 & 0x80000000) == 0 )
  {
    v8 = Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INetworkPrivate,INetworkPrivate2,IPropertyBag>>(
           v7,
           &GUID_8a40a45d_055c_4b62_abd7_6d613e2ceaec,
           a3);
    if ( !v7 )
      return v8;
LABEL_20:
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INetworkPrivate,INetworkPrivate2,IPropertyBag>::Release(v7);
    return v8;
  }
  if ( v7 )
    goto LABEL_20;
  return v8;
}

```

## disassembly

```asm
0x18001d640  push    rbx
0x18001d642  push    rsi
0x18001d643  sub     rsp, 0A8h
0x18001d64a  mov     rax, cs:__security_cookie
0x18001d651  xor     rax, rsp
0x18001d654  mov     [rsp+0B8h+var_28], rax
0x18001d65c  mov     rsi, r8
0x18001d65f  mov     rbx, rdx
0x18001d662  mov     r8d, 27h ; '''; cchMax
0x18001d668  lea     rdx, [rsp+0B8h+sz]; lpsz
0x18001d66d  call    cs:__imp_StringFromGUID2
0x18001d673  cmp     eax, 27h ; '''
0x18001d676  jnz     loc_18001D78E
0x18001d67c  mov     [rsp+0B8h+arg_8], rbp
0x18001d684  xor     ebp, ebp
0x18001d686  mov     [rsp+0B8h+var_18], rdi
0x18001d68e  test    rbx, rbx
0x18001d691  jz      short loc_18001D70B
0x18001d693  mov     edi, [rbx]
0x18001d695  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d69c  mov     [rsi], rbp
0x18001d69f  mov     ecx, 298h; unsigned __int64
0x18001d6a4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d6a9  test    rax, rax
0x18001d6ac  jz      loc_18001D7C2
0x18001d6b2  mov     rcx, rax; this
0x18001d6b5  call    ??0Network@@QEAA@XZ; Network::Network(void)
0x18001d6ba  lea     r8, [rsp+0B8h+sz]; wchar_t *
0x18001d6bf  mov     edx, edi; unsigned int
0x18001d6c1  mov     rcx, rax; this
0x18001d6c4  mov     rbx, rax
0x18001d6c7  call    ?RuntimeClassInitialize@Network@@QEAAJIPEB_W@Z; Network::RuntimeClassInitialize(uint,wchar_t const *)
0x18001d6cc  mov     edi, eax
0x18001d6ce  test    eax, eax
0x18001d6d0  jns     loc_18001D798
0x18001d6d6  test    rbx, rbx
0x18001d6d9  jnz     loc_18001D7B5
0x18001d6df  mov     eax, edi
0x18001d6e1  mov     rbp, [rsp+0B8h+arg_8]
0x18001d6e9  mov     rdi, [rsp+0B8h+var_18]
0x18001d6f1  mov     rcx, [rsp+0B8h+var_28]
0x18001d6f9  xor     rcx, rsp; StackCookie
0x18001d6fc  call    __security_check_cookie
0x18001d701  add     rsp, 0A8h
0x18001d708  pop     rsi
0x18001d709  pop     rbx
0x18001d70a  retn
0x18001d70b  mov     edi, ebp
0x18001d70d  call    cs:__imp_CoImpersonateClient
0x18001d713  cmp     eax, 80010117h
0x18001d718  mov     ebx, ebp
0x18001d71a  cmovnz  ebx, eax
0x18001d71d  test    ebx, ebx
0x18001d71f  jnz     short loc_18001D770
0x18001d721  lea     rax, [rsp+0B8h+var_84]
0x18001d726  mov     [rsp+0B8h+var_84], ebp
0x18001d72a  mov     r9d, 4; TokenInformationLength
0x18001d730  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18001d735  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18001d73a  mov     [rsp+0B8h+TokenInformation], ebp
0x18001d73e  mov     edx, 0Ch; TokenInformationClass
0x18001d743  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18001d74a  call    cs:__imp_GetTokenInformation
0x18001d750  test    eax, eax
0x18001d752  jz      short loc_18001D777
0x18001d754  mov     ecx, [rsp+0B8h+TokenInformation]; SessionId
0x18001d758  call    cs:__imp_GetSessionCompartmentId
0x18001d75e  mov     edi, eax
0x18001d760  mov     ebx, ebp
0x18001d762  call    cs:__imp_CoRevertToSelf
0x18001d768  test    ebx, ebx
0x18001d76a  jz      loc_18001D695
0x18001d770  mov     eax, ebx
0x18001d772  jmp     loc_18001D6E1
0x18001d777  call    cs:__imp_GetLastError
0x18001d77d  mov     ebx, eax
0x18001d77f  test    eax, eax
0x18001d781  jle     short loc_18001D762
0x18001d783  movzx   ebx, ax
0x18001d786  or      ebx, 80070000h
0x18001d78c  jmp     short loc_18001D762
0x18001d78e  mov     eax, 80004005h
0x18001d793  jmp     loc_18001D6F1
0x18001d798  mov     r8, rsi
0x18001d79b  lea     rdx, _GUID_8a40a45d_055c_4b62_abd7_6d613e2ceaec
0x18001d7a2  mov     rcx, rbx
0x18001d7a5  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UINetworkPrivate@@UINetworkPrivate2@@UIPropertyBag@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UINetworkPrivate@@UINetworkPrivate2@@UIPropertyBag@@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INetworkPrivate,INetworkPrivate2,IPropertyBag>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INetworkPrivate,INetworkPrivate2,IPropertyBag> *,_GUID const &,void * *)
0x18001d7aa  mov     edi, eax
0x18001d7ac  test    rbx, rbx
0x18001d7af  jz      loc_18001D6DF
0x18001d7b5  mov     rcx, rbx
0x18001d7b8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UINetworkPrivate@@UINetworkPrivate2@@UIPropertyBag@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,INetworkPrivate,INetworkPrivate2,IPropertyBag>::Release(void)
0x18001d7bd  jmp     loc_18001D6DF
0x18001d7c2  mov     edi, 8007000Eh
0x18001d7c7  jmp     loc_18001D6DF
```
