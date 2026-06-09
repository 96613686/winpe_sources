# InitializeDomainAdminSid

- ea: `0x180120148`
- end: `0x180120328`
- name: `InitializeDomainAdminSid`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800a504c`

## callees

- `0x180120148`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801201e0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180120206`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012022c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180120254`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180120280`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801202ac`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801202d8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180120304`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801201e0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180120206`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012022c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180120254`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180120280`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801202ac`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801202d8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180120304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012025e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012028a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801202b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801202e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012030e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012025e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012028a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801202b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801202e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012030e`

## pseudocode

```c
__int64 InitializeDomainAdminSid()
{
  DWORD LastError; // ebx
  DWORD cbSid; // [rsp+30h] [rbp+10h] BYREF

  gpEnterpriseAdminSid = EnterpriseAdminSid;
  gpDomainAdminSid = DomainAdminSid;
  gpSchemaAdminSid = SchemaAdminSid;
  gpBuiltinAdminSid = BuiltinAdminSid;
  gpAuthUserSid = AuthUsersSid;
  gpEveryoneSid = EveryoneSid;
  gpEnterpriseUsersSid = EnterpriseUsersSid;
  cbSid = 28;
  gpLocalSystemSid = LocalSystemSid;
  if ( !CreateWellKnownSid(WinAccountDomainAdminsSid, gpDomainSid, DomainAdminSid, &cbSid) )
    return GetLastError();
  cbSid = 28;
  if ( !CreateWellKnownSid(WinAccountEnterpriseAdminsSid, gpRootDomainSid, gpEnterpriseAdminSid, &cbSid) )
    return GetLastError();
  cbSid = 28;
  if ( !CreateWellKnownSid(WinAccountSchemaAdminsSid, gpRootDomainSid, gpSchemaAdminSid, &cbSid) )
    return GetLastError();
  LastError = 0;
  cbSid = 28;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, gpDomainSid, gpBuiltinAdminSid, &cbSid) )
    LastError = GetLastError();
  cbSid = 28;
  if ( !CreateWellKnownSid(WinAuthenticatedUserSid, gpDomainSid, gpAuthUserSid, &cbSid) )
    LastError = GetLastError();
  cbSid = 28;
  if ( !CreateWellKnownSid(WinAccountDomainUsersSid, gpRootDomainSid, gpEnterpriseUsersSid, &cbSid) )
    LastError = GetLastError();
  cbSid = 28;
  if ( !CreateWellKnownSid(WinWorldSid, gpDomainSid, gpEveryoneSid, &cbSid) )
    LastError = GetLastError();
  cbSid = 28;
  if ( !CreateWellKnownSid(WinLocalSystemSid, gpDomainSid, gpLocalSystemSid, &cbSid) )
    return GetLastError();
  return LastError;
}

```

## disassembly

```asm
0x180120148  mov     [rsp-8+arg_8], rbx
0x18012014d  mov     [rsp-8+arg_10], rdi
0x180120152  push    rbp
0x180120153  mov     rbp, rsp
0x180120156  sub     rsp, 20h
0x18012015a  mov     rdx, cs:gpDomainSid; DomainSid
0x180120161  lea     rax, EnterpriseAdminSid
0x180120168  mov     cs:gpEnterpriseAdminSid, rax
0x18012016f  lea     r8, DomainAdminSid; pSid
0x180120176  lea     rax, SchemaAdminSid
0x18012017d  mov     cs:gpDomainAdminSid, r8
0x180120184  mov     cs:gpSchemaAdminSid, rax
0x18012018b  lea     r9, [rbp+cbSid]; cbSid
0x18012018f  lea     rax, BuiltinAdminSid
0x180120196  mov     edi, 1Ch
0x18012019b  mov     cs:gpBuiltinAdminSid, rax
0x1801201a2  lea     rax, AuthUsersSid
0x1801201a9  mov     cs:gpAuthUserSid, rax
0x1801201b0  lea     rax, EveryoneSid
0x1801201b7  mov     cs:gpEveryoneSid, rax
0x1801201be  lea     rax, EnterpriseUsersSid
0x1801201c5  mov     cs:gpEnterpriseUsersSid, rax
0x1801201cc  lea     ecx, [rdi+0Dh]; WellKnownSidType
0x1801201cf  lea     rax, LocalSystemSid
0x1801201d6  mov     [rbp+cbSid], edi
0x1801201d9  mov     cs:gpLocalSystemSid, rax
0x1801201e0  call    cs:__imp_CreateWellKnownSid
0x1801201e6  test    eax, eax
0x1801201e8  jz      loc_18012030E
0x1801201ee  mov     r8, cs:gpEnterpriseAdminSid; pSid
0x1801201f5  lea     r9, [rbp+cbSid]; cbSid
0x1801201f9  mov     rdx, cs:gpRootDomainSid; DomainSid
0x180120200  lea     ecx, [rdi+14h]; WellKnownSidType
0x180120203  mov     [rbp+cbSid], edi
0x180120206  call    cs:__imp_CreateWellKnownSid
0x18012020c  test    eax, eax
0x18012020e  jz      loc_18012030E
0x180120214  mov     r8, cs:gpSchemaAdminSid; pSid
0x18012021b  lea     r9, [rbp+cbSid]; cbSid
0x18012021f  mov     rdx, cs:gpRootDomainSid; DomainSid
0x180120226  lea     ecx, [rdi+13h]; WellKnownSidType
0x180120229  mov     [rbp+cbSid], edi
0x18012022c  call    cs:__imp_CreateWellKnownSid
0x180120232  test    eax, eax
0x180120234  jz      loc_18012030E
0x18012023a  mov     r8, cs:gpBuiltinAdminSid; pSid
0x180120241  lea     r9, [rbp+cbSid]; cbSid
0x180120245  mov     rdx, cs:gpDomainSid; DomainSid
0x18012024c  lea     ecx, [rdi-2]; WellKnownSidType
0x18012024f  xor     ebx, ebx
0x180120251  mov     [rbp+cbSid], edi
0x180120254  call    cs:__imp_CreateWellKnownSid
0x18012025a  test    eax, eax
0x18012025c  jnz     short loc_180120266
0x18012025e  call    cs:__imp_GetLastError
0x180120264  mov     ebx, eax
0x180120266  mov     r8, cs:gpAuthUserSid; pSid
0x18012026d  lea     r9, [rbp+cbSid]; cbSid
0x180120271  mov     rdx, cs:gpDomainSid; DomainSid
0x180120278  mov     ecx, 11h; WellKnownSidType
0x18012027d  mov     [rbp+cbSid], edi
0x180120280  call    cs:__imp_CreateWellKnownSid
0x180120286  test    eax, eax
0x180120288  jnz     short loc_180120292
0x18012028a  call    cs:__imp_GetLastError
0x180120290  mov     ebx, eax
0x180120292  mov     r8, cs:gpEnterpriseUsersSid; pSid
0x180120299  lea     r9, [rbp+cbSid]; cbSid
0x18012029d  mov     rdx, cs:gpRootDomainSid; DomainSid
0x1801202a4  mov     ecx, 2Ah ; '*'; WellKnownSidType
0x1801202a9  mov     [rbp+cbSid], edi
0x1801202ac  call    cs:__imp_CreateWellKnownSid
0x1801202b2  test    eax, eax
0x1801202b4  jnz     short loc_1801202BE
0x1801202b6  call    cs:__imp_GetLastError
0x1801202bc  mov     ebx, eax
0x1801202be  mov     r8, cs:gpEveryoneSid; pSid
0x1801202c5  lea     r9, [rbp+cbSid]; cbSid
0x1801202c9  mov     rdx, cs:gpDomainSid; DomainSid
0x1801202d0  mov     ecx, 1; WellKnownSidType
0x1801202d5  mov     [rbp+cbSid], edi
0x1801202d8  call    cs:__imp_CreateWellKnownSid
0x1801202de  test    eax, eax
0x1801202e0  jnz     short loc_1801202EA
0x1801202e2  call    cs:__imp_GetLastError
0x1801202e8  mov     ebx, eax
0x1801202ea  mov     r8, cs:gpLocalSystemSid; pSid
0x1801202f1  lea     r9, [rbp+cbSid]; cbSid
0x1801202f5  mov     rdx, cs:gpDomainSid; DomainSid
0x1801202fc  mov     ecx, 16h; WellKnownSidType
0x180120301  mov     [rbp+cbSid], edi
0x180120304  call    cs:__imp_CreateWellKnownSid
0x18012030a  test    eax, eax
0x18012030c  jnz     short loc_180120316
0x18012030e  call    cs:__imp_GetLastError
0x180120314  mov     ebx, eax
0x180120316  mov     rdi, [rsp+20h+arg_10]
0x18012031b  mov     eax, ebx
0x18012031d  mov     rbx, [rsp+20h+arg_8]
0x180120322  add     rsp, 20h
0x180120326  pop     rbp
0x180120327  retn
```
