# SHGetDefaultConnectedIdentityProvider(_GUID *)

- ea: `0x1800748b4`
- end: `0x1800749a2`
- name: `?SHGetDefaultConnectedIdentityProvider@@YAJPEAU_GUID@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006f048`

## callees

- `0x1800254e0`
- `0x1800748b4`
- `0x1800749a8`
- `0x1800749f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007495c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007495c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180074922`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180074922`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x180074913`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x180074940`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x180074913`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x180074940`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x1800748f9`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x1800748f9`

## pseudocode

```c
__int64 __fastcall SHGetDefaultConnectedIdentityProvider(struct _GUID *a1)
{
  int IdentityProviderInfoByGUID; // ebx
  _BYTE *v3; // rax
  _BYTE *v4; // rdi
  char v5; // si
  SIZE_T cb; // [rsp+20h] [rbp-48h] BYREF
  struct _GUID v8; // [rsp+28h] [rbp-40h] BYREF

  LOWORD(IdentityProviderInfoByGUID) = 1168;
  *a1 = GUID_NULL;
  if ( (unsigned __int8)ConnectedIdentityDisabledByRegistry() )
    return (unsigned __int16)IdentityProviderInfoByGUID | 0x80070000;
  v8 = 0;
  if ( (unsigned int)GetDefaultIdentityProvider(&v8) )
    goto LABEL_10;
  LODWORD(cb) = 0;
  if ( (unsigned int)GetIdentityProviderInfoByGUID(&v8, 0, &cb) != 122 )
    goto LABEL_10;
  v3 = CoTaskMemAlloc((unsigned int)cb);
  v4 = v3;
  if ( !v3 )
    goto LABEL_10;
  v5 = 0;
  IdentityProviderInfoByGUID = GetIdentityProviderInfoByGUID(&v8, v3, &cb);
  if ( !IdentityProviderInfoByGUID )
  {
    v5 = 0;
    if ( (v4[32] & 1) != 0 )
      v5 = IdentityProviderInfoByGUID + 1;
  }
  CoTaskMemFree(v4);
  if ( v5 )
    *a1 = v8;
  else
LABEL_10:
    IdentityProviderInfoByGUID = GetFirstConnectedIdentityProvider(a1);
  if ( IdentityProviderInfoByGUID > 0 )
    return (unsigned __int16)IdentityProviderInfoByGUID | 0x80070000;
  return (unsigned int)IdentityProviderInfoByGUID;
}

```

## disassembly

```asm
0x1800748b4  push    rbx
0x1800748b6  push    rbp
0x1800748b7  push    rsi
0x1800748b8  push    rdi
0x1800748b9  sub     rsp, 48h
0x1800748bd  mov     rax, cs:__security_cookie
0x1800748c4  xor     rax, rsp
0x1800748c7  mov     [rsp+68h+var_30], rax
0x1800748cc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800748d3  mov     rbp, rcx
0x1800748d6  mov     ebx, 490h
0x1800748db  movdqu  xmmword ptr [rcx], xmm0
0x1800748df  call    _ConnectedIdentityDisabledByRegistry
0x1800748e4  test    al, al
0x1800748e6  jnz     loc_180074981
0x1800748ec  xorps   xmm0, xmm0
0x1800748ef  lea     rcx, [rsp+68h+var_40]
0x1800748f4  movups  [rsp+68h+var_40], xmm0
0x1800748f9  call    cs:__imp_GetDefaultIdentityProvider
0x1800748ff  test    eax, eax
0x180074901  jnz     short loc_180074973
0x180074903  lea     r8, [rsp+68h+cb]
0x180074908  mov     dword ptr [rsp+68h+cb], eax
0x18007490c  xor     edx, edx
0x18007490e  lea     rcx, [rsp+68h+var_40]
0x180074913  call    cs:__imp_GetIdentityProviderInfoByGUID
0x180074919  cmp     eax, 7Ah ; 'z'
0x18007491c  jnz     short loc_180074973
0x18007491e  mov     ecx, dword ptr [rsp+68h+cb]; cb
0x180074922  call    cs:__imp_CoTaskMemAlloc
0x180074928  mov     rdi, rax
0x18007492b  test    rax, rax
0x18007492e  jz      short loc_180074973
0x180074930  lea     r8, [rsp+68h+cb]
0x180074935  mov     rdx, rax
0x180074938  lea     rcx, [rsp+68h+var_40]
0x18007493d  xor     sil, sil
0x180074940  call    cs:__imp_GetIdentityProviderInfoByGUID
0x180074946  mov     ebx, eax
0x180074948  test    eax, eax
0x18007494a  jnz     short loc_180074959
0x18007494c  lea     eax, [rbx+1]
0x18007494f  movzx   esi, sil
0x180074953  test    [rdi+20h], al
0x180074956  cmovnz  esi, eax
0x180074959  mov     rcx, rdi; pv
0x18007495c  call    cs:__imp_CoTaskMemFree
0x180074962  test    sil, sil
0x180074965  jz      short loc_180074973
0x180074967  movups  xmm0, [rsp+68h+var_40]
0x18007496c  movdqu  xmmword ptr [rbp+0], xmm0
0x180074971  jmp     short loc_18007497D
0x180074973  mov     rcx, rbp
0x180074976  call    _GetFirstConnectedIdentityProvider
0x18007497b  mov     ebx, eax
0x18007497d  test    ebx, ebx
0x18007497f  jle     short loc_18007498A
0x180074981  movzx   ebx, bx
0x180074984  or      ebx, 80070000h
0x18007498a  mov     eax, ebx
0x18007498c  mov     rcx, [rsp+68h+var_30]
0x180074991  xor     rcx, rsp; StackCookie
0x180074994  call    __security_check_cookie
0x180074999  add     rsp, 48h
0x18007499d  pop     rdi
0x18007499e  pop     rsi
0x18007499f  pop     rbp
0x1800749a0  pop     rbx
0x1800749a1  retn
```
