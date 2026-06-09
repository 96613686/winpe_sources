# CSecurityAttributesForSharedObjects::~CSecurityAttributesForSharedObjects(void)

- ea: `0x180025e58`
- end: `0x180025ea1`
- name: `??1CSecurityAttributesForSharedObjects@@QEAA@XZ`
- size: `73`
- prototype: `void __fastcall(CSecurityAttributesForSharedObjects *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020fa0`
- `0x180024594`
- `0x1800a73bc`

## callees

- `0x180025e58`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e6f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180025e83`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180025e83`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180025e92`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180025e99`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180025e99`

## pseudocode

```c
void __fastcall CSecurityAttributesForSharedObjects::~CSecurityAttributesForSharedObjects(HLOCAL *this)
{
  LocalFree(this[3]);
  LocalFree(this[2]);
  if ( this[9] )
    DestroyPrivateObjectSecurity(this + 9);
  FreeSid(this[7]);
  FreeSid(this[8]);
}

```

## disassembly

```asm
0x180025e58  push    rbx
0x180025e5a  sub     rsp, 20h
0x180025e5e  mov     rbx, rcx
0x180025e61  mov     rcx, [rcx+18h]; hMem
0x180025e65  call    cs:__imp_LocalFree
0x180025e6b  mov     rcx, [rbx+10h]; hMem
0x180025e6f  call    cs:__imp_LocalFree
0x180025e75  lea     rcx, [rbx+48h]; ObjectDescriptor
0x180025e79  cmp     qword ptr [rcx], 0
0x180025e7d  jnz     short loc_180025E99
0x180025e7f  mov     rcx, [rbx+38h]; pSid
0x180025e83  call    cs:__imp_FreeSid
0x180025e89  mov     rcx, [rbx+40h]
0x180025e8d  add     rsp, 20h
0x180025e91  pop     rbx
0x180025e92  jmp     cs:__imp_FreeSid
0x180025e99  call    cs:__imp_DestroyPrivateObjectSecurity
0x180025e9f  jmp     short loc_180025E7F
```
