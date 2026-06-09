# IsVpnClientAccessCheck

- ea: `0x180025af0`
- end: `0x180025bfd`
- name: `IsVpnClientAccessCheck`
- size: `269`
- prototype: `__int64 __fastcall(HANDLE ClientToken)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000dea0`

## callees

- `0x180019d18`
- `0x18001d8e0`
- `0x180025af0`
- `0x18002d28c`
- `0x18002d3fc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180025bb8`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180025bb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025bcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025bcd`

## pseudocode

```c
bool __fastcall IsVpnClientAccessCheck(HANDLE ClientToken)
{
  bool v2; // si
  void *v3; // rbx
  int SecurityDescriptor; // edi
  WINBOOL AccessStatus; // [rsp+40h] [rbp-C0h] BYREF
  DWORD PrivilegeSetLength[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD GrantedAccess; // [rsp+50h] [rbp-B0h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp-A8h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp-90h] BYREF

  *(_QWORD *)PrivilegeSetLength = 0;
  v2 = 0;
  AccessStatus = 0;
  v3 = 0;
  SecurityDescriptor = VpnAllowedPluginDeclarationInitialize();
  if ( !SecurityDescriptor )
  {
    SecurityDescriptor = VpnAllowedPluginDeclarationGetSecurityDescriptor(
                           (PSECURITY_DESCRIPTOR *)PrivilegeSetLength,
                           (ULONG *)&AccessStatus);
    if ( !SecurityDescriptor )
      v3 = *(void **)PrivilegeSetLength;
  }
  VpnAllowedPluginDeclarationShutdown();
  if ( !SecurityDescriptor )
  {
    PrivilegeSetLength[0] = 500;
    GrantedAccess = 0;
    AccessStatus = 0;
    GenericMapping = (_GENERIC_MAPPING)_mm_load_si128((const __m128i *)&_xmm);
    if ( AccessCheck(
           v3,
           ClientToken,
           1u,
           &GenericMapping,
           &PrivilegeSet,
           PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      v2 = AccessStatus != 0;
    }
    LocalFree(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x180025af0  mov     [rsp-8+arg_8], rbx
0x180025af5  mov     [rsp-8+arg_10], rsi
0x180025afa  push    rbp
0x180025afb  push    rdi
0x180025afc  push    r14
0x180025afe  lea     rbp, [rsp-180h]
0x180025b06  sub     rsp, 280h
0x180025b0d  mov     rax, cs:__security_cookie
0x180025b14  xor     rax, rsp
0x180025b17  mov     [rbp+190h+var_20], rax
0x180025b1e  mov     r14, rcx
0x180025b21  mov     qword ptr [rsp+290h+var_248], 0
0x180025b2a  xor     sil, sil
0x180025b2d  mov     [rsp+290h+var_250], 0
0x180025b35  xor     ebx, ebx
0x180025b37  call    VpnAllowedPluginDeclarationInitialize
0x180025b3c  mov     edi, eax
0x180025b3e  test    eax, eax
0x180025b40  jnz     short loc_180025B5B
0x180025b42  lea     rdx, [rsp+290h+var_250]
0x180025b47  lea     rcx, [rsp+290h+var_248]
0x180025b4c  call    VpnAllowedPluginDeclarationGetSecurityDescriptor
0x180025b51  test    eax, eax
0x180025b53  mov     edi, eax
0x180025b55  cmovz   rbx, qword ptr [rsp+290h+var_248]
0x180025b5b  call    VpnAllowedPluginDeclarationShutdown
0x180025b60  test    edi, edi
0x180025b62  jnz     short loc_180025BD3
0x180025b64  movdqa  xmm0, cs:__xmm@00000001000000010000000100000001
0x180025b6c  lea     rax, [rsp+290h+var_250]
0x180025b71  mov     [rsp+290h+AccessStatus], rax; AccessStatus
0x180025b76  lea     r9, [rsp+290h+GenericMapping]; GenericMapping
0x180025b7b  lea     rax, [rsp+290h+var_240]
0x180025b80  mov     [rsp+290h+var_248], 1F4h
0x180025b88  mov     [rsp+290h+GrantedAccess], rax; GrantedAccess
0x180025b8d  lea     r8d, [rdi+1]; DesiredAccess
0x180025b91  lea     rax, [rsp+290h+var_248]
0x180025b96  mov     [rsp+290h+var_240], edi
0x180025b9a  mov     [rsp+290h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180025b9f  mov     rdx, r14; ClientToken
0x180025ba2  lea     rax, [rsp+290h+var_220]
0x180025ba7  mov     [rsp+290h+var_250], edi
0x180025bab  mov     rcx, rbx; pSecurityDescriptor
0x180025bae  mov     [rsp+290h+PrivilegeSet], rax; PrivilegeSet
0x180025bb3  movups  xmmword ptr [rsp+290h+GenericMapping.GenericRead], xmm0
0x180025bb8  call    cs:__imp_AccessCheck
0x180025bbe  test    eax, eax
0x180025bc0  jz      short loc_180025BCA
0x180025bc2  cmp     [rsp+290h+var_250], edi
0x180025bc6  setnz   sil
0x180025bca  mov     rcx, rbx; hMem
0x180025bcd  call    cs:__imp_LocalFree
0x180025bd3  mov     al, sil
0x180025bd6  mov     rcx, [rbp+190h+var_20]
0x180025bdd  xor     rcx, rsp; StackCookie
0x180025be0  call    __security_check_cookie
0x180025be5  lea     r11, [rsp+290h+var_10]
0x180025bed  mov     rbx, [r11+28h]
0x180025bf1  mov     rsi, [r11+30h]
0x180025bf5  mov     rsp, r11
0x180025bf8  pop     r14
0x180025bfa  pop     rdi
0x180025bfb  pop     rbp
0x180025bfc  retn
```
