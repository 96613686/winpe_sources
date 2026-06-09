# CSecurityLogHelper::CleanUp(void)

- ea: `0x18001528c`
- end: `0x1800152fc`
- name: `?CleanUp@CSecurityLogHelper@@AEAAXXZ`
- size: `112`
- prototype: `void __fastcall(CSecurityLogHelper *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d6a0`
- `0x180015250`

## callees

- `0x18001528c`

## import_xrefs

- `AUTHZ!AuthziFreeAuditEventType` at `0x1800152b2`
- `AUTHZ!AuthziFreeAuditEventType` at `0x1800152b2`
- `AUTHZ!AuthzFreeResourceManager` at `0x1800152de`
- `AUTHZ!AuthzFreeResourceManager` at `0x1800152de`

## pseudocode

```c
void __fastcall CSecurityLogHelper::CleanUp(CSecurityLogHelper *this)
{
  unsigned int i; // esi
  __int64 v3; // rbx
  AUTHZ_RESOURCE_MANAGER_HANDLE v4; // rcx

  for ( i = 0; i < *((_DWORD *)this + 140); *((_QWORD *)this + v3 + 7) = 0 )
  {
    v3 = 2LL * i;
    AuthziFreeAuditEventType(*((_QWORD *)this + 2 * i++ + 7));
  }
  v4 = (AUTHZ_RESOURCE_MANAGER_HANDLE)*((_QWORD *)this + 5);
  *((_DWORD *)this + 140) = 0;
  if ( v4 )
  {
    AuthzFreeResourceManager(v4);
    *((_QWORD *)this + 5) = 0;
  }
}

```

## disassembly

```asm
0x18001528c  mov     [rsp+arg_0], rbx
0x180015291  mov     [rsp+arg_8], rsi
0x180015296  push    rdi
0x180015297  sub     rsp, 20h
0x18001529b  xor     esi, esi
0x18001529d  mov     rdi, rcx
0x1800152a0  cmp     [rcx+230h], esi
0x1800152a6  jbe     short loc_1800152CB
0x1800152a8  mov     ebx, esi
0x1800152aa  add     rbx, rbx
0x1800152ad  mov     rcx, [rdi+rbx*8+38h]
0x1800152b2  call    cs:__imp_AuthziFreeAuditEventType
0x1800152b8  inc     esi
0x1800152ba  mov     qword ptr [rdi+rbx*8+38h], 0
0x1800152c3  cmp     esi, [rdi+230h]
0x1800152c9  jb      short loc_1800152A8
0x1800152cb  mov     rcx, [rdi+28h]; hAuthzResourceManager
0x1800152cf  mov     dword ptr [rdi+230h], 0
0x1800152d9  test    rcx, rcx
0x1800152dc  jz      short loc_1800152EC
0x1800152de  call    cs:__imp_AuthzFreeResourceManager
0x1800152e4  mov     qword ptr [rdi+28h], 0
0x1800152ec  mov     rbx, [rsp+28h+arg_0]
0x1800152f1  mov     rsi, [rsp+28h+arg_8]
0x1800152f6  add     rsp, 20h
0x1800152fa  pop     rdi
0x1800152fb  retn
```
