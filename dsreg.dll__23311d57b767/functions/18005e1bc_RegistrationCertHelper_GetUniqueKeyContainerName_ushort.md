# RegistrationCertHelper::GetUniqueKeyContainerName(ushort * *)

- ea: `0x18005e1bc`
- end: `0x18005e2e1`
- name: `?GetUniqueKeyContainerName@RegistrationCertHelper@@AEAAJPEAPEAG@Z`
- size: `293`
- prototype: `__int64 __fastcall(RegistrationCertHelper *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18005d774`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x18000ddf0`
- `0x180043ef8`
- `0x180044300`
- `0x18005e1bc`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18005e1fe`
- `RPCRT4!UuidCreate` at `0x18005e1fe`
- `RPCRT4!RpcStringFreeW` at `0x18005e295`
- `RPCRT4!RpcStringFreeW` at `0x18005e295`
- `RPCRT4!UuidToStringW` at `0x18005e22d`
- `RPCRT4!UuidToStringW` at `0x18005e22d`

## string_xrefs

- `0x18005e264`: `CopyStringW`
- `0x18005e208`: `%s: UuidCreate failed with error code (RPC_STATUS): 0x%08x`

## pseudocode

```c
__int64 __fastcall RegistrationCertHelper::GetUniqueKeyContainerName(
        RegistrationCertHelper *this,
        unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rdi
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int16 *v11; // [rsp+28h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-20h] BYREF

  StringUuid = 0;
  Uuid = 0;
  v2 = 0;
  v11 = 0;
  *a2 = 0;
  v4 = UuidCreate(&Uuid);
  if ( v4 )
  {
    Logger::TraceError(
      L"%s: UuidCreate failed with error code (RPC_STATUS): 0x%08x",
      L"RegistrationCertHelper::GetUniqueKeyContainerName",
      v4);
LABEL_3:
    v5 = -2147467259;
    goto LABEL_11;
  }
  v6 = UuidToStringW(&Uuid, &StringUuid);
  if ( v6 )
  {
    Logger::TraceError(
      L"%s: UuidToStringW failed with error code (RPC_STATUS): 0x%08x",
      L"RegistrationCertHelper::GetUniqueKeyContainerName",
      v6);
    goto LABEL_3;
  }
  v7 = -1;
  do
    ++v7;
  while ( StringUuid[v7] );
  v8 = CopyStringW(StringUuid, v7, &v11);
  v5 = v8;
  if ( v8 >= 0 )
  {
    *a2 = v11;
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationCertHelper::GetUniqueKeyContainerName",
      L"CopyStringW",
      (unsigned int)v8);
    v2 = v11;
  }
LABEL_11:
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  if ( v2 )
    operator delete(v2);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertHelper::GetUniqueKeyContainerName", v5);
  return v5;
}

```

## disassembly

```asm
0x18005e1bc  mov     [rsp-18h+arg_0], rbx
0x18005e1c1  mov     [rsp-18h+arg_10], rsi
0x18005e1c6  push    rbp
0x18005e1c7  push    rdi
0x18005e1c8  push    r14
0x18005e1ca  mov     rbp, rsp
0x18005e1cd  sub     rsp, 50h
0x18005e1d1  mov     rax, cs:__security_cookie
0x18005e1d8  xor     rax, rsp
0x18005e1db  mov     [rbp+var_10], rax
0x18005e1df  xor     r14d, r14d
0x18005e1e2  lea     rcx, [rbp+Uuid]; Uuid
0x18005e1e6  xorps   xmm0, xmm0
0x18005e1e9  mov     [rbp+StringUuid], r14
0x18005e1ed  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18005e1f1  mov     edi, r14d
0x18005e1f4  mov     [rbp+var_28], r14
0x18005e1f8  mov     [rdx], r14
0x18005e1fb  mov     rsi, rdx
0x18005e1fe  call    cs:__imp_UuidCreate
0x18005e204  test    eax, eax
0x18005e206  jz      short loc_18005E225
0x18005e208  lea     rcx, aSUuidcreateFai; "%s: UuidCreate failed with error code ("...
0x18005e20f  lea     rdx, aRegistrationce_9; "RegistrationCertHelper::GetUniqueKeyCon"...
0x18005e216  mov     r8d, eax
0x18005e219  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005e21e  mov     ebx, 80004005h
0x18005e223  jmp     short loc_18005E28B
0x18005e225  lea     rdx, [rbp+StringUuid]; StringUuid
0x18005e229  lea     rcx, [rbp+Uuid]; Uuid
0x18005e22d  call    cs:__imp_UuidToStringW
0x18005e233  test    eax, eax
0x18005e235  jz      short loc_18005E240
0x18005e237  lea     rcx, aSUuidtostringw_0; "%s: UuidToStringW failed with error cod"...
0x18005e23e  jmp     short loc_18005E20F
0x18005e240  mov     rcx, [rbp+StringUuid]; Source
0x18005e244  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005e248  inc     rdx; unsigned __int64
0x18005e24b  cmp     [rcx+rdx*2], r14w
0x18005e250  jnz     short loc_18005E248
0x18005e252  lea     r8, [rbp+var_28]; unsigned __int16 **
0x18005e256  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x18005e25b  mov     ebx, eax
0x18005e25d  test    eax, eax
0x18005e25f  jns     short loc_18005E284
0x18005e261  mov     r9d, eax
0x18005e264  lea     r8, aCopystringw; "CopyStringW"
0x18005e26b  lea     rdx, aRegistrationce_9; "RegistrationCertHelper::GetUniqueKeyCon"...
0x18005e272  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005e279  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005e27e  mov     rdi, [rbp+var_28]
0x18005e282  jmp     short loc_18005E28B
0x18005e284  mov     rax, [rbp+var_28]
0x18005e288  mov     [rsi], rax
0x18005e28b  cmp     [rbp+StringUuid], r14
0x18005e28f  jz      short loc_18005E29B
0x18005e291  lea     rcx, [rbp+StringUuid]; String
0x18005e295  call    cs:__imp_RpcStringFreeW
0x18005e29b  test    rdi, rdi
0x18005e29e  jz      short loc_18005E2A8
0x18005e2a0  mov     rcx, rdi; Block
0x18005e2a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005e2a8  mov     r8d, ebx
0x18005e2ab  lea     rdx, aRegistrationce_9; "RegistrationCertHelper::GetUniqueKeyCon"...
0x18005e2b2  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18005e2b9  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005e2be  mov     eax, ebx
0x18005e2c0  mov     rcx, [rbp+var_10]
0x18005e2c4  xor     rcx, rsp; StackCookie
0x18005e2c7  call    __security_check_cookie
0x18005e2cc  lea     r11, [rsp+50h+var_s0]
0x18005e2d1  mov     rbx, [r11+20h]
0x18005e2d5  mov     rsi, [r11+30h]
0x18005e2d9  mov     rsp, r11
0x18005e2dc  pop     r14
0x18005e2de  pop     rdi
0x18005e2df  pop     rbp
0x18005e2e0  retn
```
