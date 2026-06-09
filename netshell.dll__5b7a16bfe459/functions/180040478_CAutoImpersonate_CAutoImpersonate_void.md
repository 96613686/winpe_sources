# CAutoImpersonate::~CAutoImpersonate(void)

- ea: `0x180040478`
- end: `0x1800404c2`
- name: `??1CAutoImpersonate@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(CAutoImpersonate *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18006198c`
- `0x180064437`

## callees

- `0x180040478`
- `0x1800405b8`

## import_xrefs

- `ole32!CoRevertToSelf` at `0x180040492`
- `ole32!CoRevertToSelf` at `0x180040492`
- `ole32!CoImpersonateClient` at `0x1800404b5`
- `ole32!CoImpersonateClient` at `0x1800404b5`

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
0x180040478  push    rbx
0x18004047a  sub     rsp, 20h
0x18004047e  mov     rbx, rcx
0x180040481  cmp     dword ptr [rcx+0Ch], 0
0x180040485  jz      short loc_18004049A
0x180040487  cmp     dword ptr [rcx+8], 0
0x18004048b  jnz     short loc_18004049A
0x18004048d  cmp     dword ptr [rcx], 0
0x180040490  jz      short loc_18004049A
0x180040492  call    cs:__imp_CoRevertToSelf
0x180040498  jmp     short loc_1800404BC
0x18004049a  call    ?ShouldRecoverLostImpersonation@CAutoImpersonate@@AEAAHXZ; CAutoImpersonate::ShouldRecoverLostImpersonation(void)
0x18004049f  test    eax, eax
0x1800404a1  jz      short loc_1800404BC
0x1800404a3  cmp     dword ptr [rbx+0Ch], 0
0x1800404a7  jz      short loc_1800404BC
0x1800404a9  mov     rcx, rbx; this
0x1800404ac  call    ?ShouldRecoverLostImpersonation@CAutoImpersonate@@AEAAHXZ; CAutoImpersonate::ShouldRecoverLostImpersonation(void)
0x1800404b1  test    eax, eax
0x1800404b3  jz      short loc_1800404BC
0x1800404b5  call    cs:__imp_CoImpersonateClient
0x1800404bb  nop
0x1800404bc  add     rsp, 20h
0x1800404c0  pop     rbx
0x1800404c1  retn
```
