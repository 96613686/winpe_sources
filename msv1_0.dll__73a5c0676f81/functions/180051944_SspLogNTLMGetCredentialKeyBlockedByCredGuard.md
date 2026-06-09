# SspLogNTLMGetCredentialKeyBlockedByCredGuard

- ea: `0x180051944`
- end: `0x180051a91`
- name: `SspLogNTLMGetCredentialKeyBlockedByCredGuard`
- size: `333`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800462b0`

## callees

- `0x180012fd0`
- `0x18001eaec`
- `0x18001f878`
- `0x18002fb50`
- `0x180051944`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180051978`
- `ntdll!EtwEventEnabled` at `0x180051978`
- `ntdll!EtwEventWrite` at `0x180051a55`
- `ntdll!EtwEventWrite` at `0x180051a55`

## pseudocode

```c
__int64 SspLogNTLMGetCredentialKeyBlockedByCredGuard()
{
  __int64 result; // rax
  const wchar_t *v1; // r8
  __int64 v2; // rcx
  __int64 v3; // rax
  bool v4; // zf
  const wchar_t *v5; // rdx
  __int64 v6; // rax
  _QWORD v7[2]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v8[32]; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v9[788]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v10[8]; // [rsp+678h] [rbp+578h] BYREF
  __int128 v11; // [rsp+680h] [rbp+580h]
  __int128 v12; // [rsp+690h] [rbp+590h]

  result = EtwEventEnabled(MsvEtwLogHandle, NTLMGetCredentialKeyBlockedByCredGuard);
  if ( (_BYTE)result )
  {
    v11 = 0;
    v12 = 0;
    SspTelemetry::ClientImageInfo::ClientImageInfo((SspTelemetry::ClientImageInfo *)v8, LsaFunctions);
    SspTelemetry::ClientImageInfo::GetSvchostServiceTag(v8, v7);
    v1 = L"-";
    if ( v7[0] )
      v1 = (const wchar_t *)v7[0];
    v2 = -1;
    v3 = -1;
    do
      ++v3;
    while ( v9[v3] );
    v4 = v3 == 0;
    v5 = v9;
    v6 = -1;
    if ( v4 )
      v5 = L"-";
    *(_QWORD *)&v11 = v5;
    do
      ++v6;
    while ( v5[v6] );
    *((_QWORD *)&v11 + 1) = (unsigned int)(2 * v6 + 2);
    do
      ++v2;
    while ( v1[v2] );
    *(_QWORD *)&v12 = v1;
    *((_QWORD *)&v12 + 1) = (unsigned int)(2 * v2 + 2);
    EtwEventWrite(MsvEtwLogHandle, NTLMGetCredentialKeyBlockedByCredGuard, 2);
    wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(v7);
    return wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(v10);
  }
  return result;
}

```

## disassembly

```asm
0x180051944  mov     [rsp-8+arg_0], rbx
0x180051949  push    rbp
0x18005194a  lea     rbp, [rsp-5B0h]
0x180051952  sub     rsp, 6B0h
0x180051959  mov     rax, cs:__security_cookie
0x180051960  xor     rax, rsp
0x180051963  mov     [rbp+5B0h+var_10], rax
0x18005196a  mov     rcx, cs:MsvEtwLogHandle
0x180051971  lea     rdx, NTLMGetCredentialKeyBlockedByCredGuard
0x180051978  call    cs:__imp_EtwEventEnabled
0x18005197e  xor     ebx, ebx
0x180051980  test    al, al
0x180051982  jz      loc_180051A71
0x180051988  mov     rdx, cs:LsaFunctions; struct _LSA_SECPKG_FUNCTION_TABLE *
0x18005198f  lea     rcx, [rsp+6B0h+var_680]; this
0x180051994  xorps   xmm0, xmm0
0x180051997  movups  [rbp+5B0h+var_30], xmm0
0x18005199e  movups  [rbp+5B0h+var_20], xmm0
0x1800519a5  call    ??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z; SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)
0x1800519aa  lea     rdx, [rsp+6B0h+var_690]
0x1800519af  lea     rcx, [rsp+6B0h+var_680]
0x1800519b4  call    ?GetSvchostServiceTag@ClientImageInfo@SspTelemetry@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SspTelemetry::ClientImageInfo::GetSvchostServiceTag(void)
0x1800519b9  mov     rax, [rsp+6B0h+var_690]
0x1800519be  lea     r9, asc_1800745A0; "-"
0x1800519c5  test    rax, rax
0x1800519c8  lea     rdx, [rsp+6B0h+var_660]
0x1800519cd  mov     r8, r9
0x1800519d0  cmovnz  r8, rax
0x1800519d4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800519d8  mov     rax, rcx
0x1800519db  inc     rax
0x1800519de  cmp     [rdx+rax*2], bx
0x1800519e2  jnz     short loc_1800519DB
0x1800519e4  test    rax, rax
0x1800519e7  lea     rdx, [rsp+6B0h+var_660]
0x1800519ec  mov     rax, rcx
0x1800519ef  cmovz   rdx, r9
0x1800519f3  mov     qword ptr [rbp+5B0h+var_30], rdx
0x1800519fa  inc     rax
0x1800519fd  cmp     [rdx+rax*2], bx
0x180051a01  jnz     short loc_1800519FA
0x180051a03  lea     eax, ds:2[rax*2]
0x180051a0a  mov     dword ptr [rbp+5B0h+var_30+0Ch], ebx
0x180051a10  mov     dword ptr [rbp+5B0h+var_30+8], eax
0x180051a16  inc     rcx
0x180051a19  cmp     [r8+rcx*2], bx
0x180051a1e  jnz     short loc_180051A16
0x180051a20  lea     eax, ds:2[rcx*2]
0x180051a27  mov     qword ptr [rbp+5B0h+var_20], r8
0x180051a2e  mov     rcx, cs:MsvEtwLogHandle
0x180051a35  lea     r9, [rbp+5B0h+var_30]
0x180051a3c  mov     r8d, 2
0x180051a42  mov     dword ptr [rbp+5B0h+var_20+8], eax
0x180051a48  lea     rdx, NTLMGetCredentialKeyBlockedByCredGuard
0x180051a4f  mov     dword ptr [rbp+5B0h+var_20+0Ch], ebx
0x180051a55  call    cs:__imp_EtwEventWrite
0x180051a5b  lea     rcx, [rsp+6B0h+var_690]
0x180051a60  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180051a65  lea     rcx, [rbp+5B0h+var_38]
0x180051a6c  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x180051a71  mov     rcx, [rbp+5B0h+var_10]
0x180051a78  xor     rcx, rsp; StackCookie
0x180051a7b  call    __security_check_cookie
0x180051a80  mov     rbx, [rsp+6B0h+arg_0]
0x180051a88  add     rsp, 6B0h
0x180051a8f  pop     rbp
0x180051a90  retn
```
