# CAutoImpersonate::~CAutoImpersonate(void)

- ea: `0x180030a00`
- end: `0x180030a4a`
- name: `??1CAutoImpersonate@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(CAutoImpersonate *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b8c0`
- `0x18001bb00`
- `0x180021990`
- `0x18002b060`
- `0x18002b1b0`
- `0x18002b2d0`
- `0x18002d0c0`
- `0x18002d69c`
- `0x18002dcb4`
- `0x180031674`
- `0x1800316e8`
- `0x1800317f4`
- `0x1800328a0`
- `0x18003543c`
- `0x18003565e`

## callees

- `0x180030a00`
- `0x180030b40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180030a1a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180030a1a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180030a3d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180030a3d`

## pseudocode

```c
void __fastcall CAutoImpersonate::~CAutoImpersonate(CAutoImpersonate *this)
{
  if ( *((_DWORD *)this + 3) && !*((_DWORD *)this + 2) && *(_DWORD *)this )
  {
    CoRevertToSelf();
  }
  else if ( (unsigned int)CAutoImpersonate::ShouldRecoverLostImpersonation(this) && *((_DWORD *)this + 3) )
  {
    if ( (unsigned int)CAutoImpersonate::ShouldRecoverLostImpersonation(this) )
      CoImpersonateClient();
  }
}

```

## disassembly

```asm
0x180030a00  push    rbx
0x180030a02  sub     rsp, 20h
0x180030a06  mov     rbx, rcx
0x180030a09  cmp     dword ptr [rcx+0Ch], 0
0x180030a0d  jz      short loc_180030A22
0x180030a0f  cmp     dword ptr [rcx+8], 0
0x180030a13  jnz     short loc_180030A22
0x180030a15  cmp     dword ptr [rcx], 0
0x180030a18  jz      short loc_180030A22
0x180030a1a  call    cs:__imp_CoRevertToSelf
0x180030a20  jmp     short loc_180030A44
0x180030a22  call    ?ShouldRecoverLostImpersonation@CAutoImpersonate@@AEAAHXZ; CAutoImpersonate::ShouldRecoverLostImpersonation(void)
0x180030a27  test    eax, eax
0x180030a29  jz      short loc_180030A44
0x180030a2b  cmp     dword ptr [rbx+0Ch], 0
0x180030a2f  jz      short loc_180030A44
0x180030a31  mov     rcx, rbx; this
0x180030a34  call    ?ShouldRecoverLostImpersonation@CAutoImpersonate@@AEAAHXZ; CAutoImpersonate::ShouldRecoverLostImpersonation(void)
0x180030a39  test    eax, eax
0x180030a3b  jz      short loc_180030A44
0x180030a3d  call    cs:__imp_CoImpersonateClient
0x180030a43  nop
0x180030a44  add     rsp, 20h
0x180030a48  pop     rbx
0x180030a49  retn
```
