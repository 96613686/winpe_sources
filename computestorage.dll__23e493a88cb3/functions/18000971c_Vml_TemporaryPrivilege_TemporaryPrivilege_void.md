# Vml::TemporaryPrivilege::~TemporaryPrivilege(void)

- ea: `0x18000971c`
- end: `0x180009789`
- name: `??1TemporaryPrivilege@Vml@@QEAA@XZ`
- size: `109`
- prototype: `void __fastcall(const struct _LUID *this, __int64, __int64, const char *)`
- caller_count: `24`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009ad8`
- `0x1800146e0`
- `0x180014a00`
- `0x180015050`
- `0x18001a5f4`
- `0x18001c5d4`
- `0x18001db70`
- `0x18001ea88`
- `0x180027e8c`
- `0x180028640`
- `0x18004350b`
- `0x18004351d`
- `0x180043af2`
- `0x180043b04`
- `0x180043b16`
- `0x180043c99`
- `0x180043cab`
- `0x180043f82`
- `0x180043f94`
- `0x1800440c4`
- `0x18004418f`
- `0x1800442e0`
- `0x1800442f2`
- `0x180044c39`

## callees

- `0x18000971c`
- `0x18000ab54`
- `0x18000ad80`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009745`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009745`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000975b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000975b`

## string_xrefs

- `0x180009777`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::TemporaryPrivilege::~TemporaryPrivilege(
        const struct _LUID *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  void *v5; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    if ( !this[2].LowPart )
      Vml::VmAccessToken::EnablePrivilege((Vml::VmAccessToken *)&this[1], this, 0);
    if ( LOBYTE(this[2].HighPart) )
      RevertToSelf();
    v5 = (void *)this[1];
    if ( v5 && !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1004,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        a4);
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1E04,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      a4);
  }
}

```

## disassembly

```asm
0x18000971c  mov     [rsp+arg_0], rcx
0x180009721  push    rbx
0x180009722  sub     rsp, 20h
0x180009726  mov     rbx, rcx
0x180009729  cmp     dword ptr [rcx+10h], 0
0x18000972d  jnz     short loc_18000973F
0x18000972f  add     rcx, 8; this
0x180009733  xor     r8d, r8d; int
0x180009736  mov     rdx, rbx; struct _LUID *
0x180009739  call    ?EnablePrivilege@VmAccessToken@Vml@@QEAAHAEBU_LUID@@H@Z; Vml::VmAccessToken::EnablePrivilege(_LUID const &,int)
0x18000973e  nop
0x18000973f  cmp     byte ptr [rbx+14h], 0
0x180009743  jz      short loc_180009752
0x180009745  call    cs:__imp_RevertToSelf
0x18000974c  nop     dword ptr [rax+rax+00h]
0x180009751  nop
0x180009752  mov     rcx, [rbx+8]; hObject
0x180009756  test    rcx, rcx
0x180009759  jz      short loc_18000976B
0x18000975b  call    cs:__imp_CloseHandle
0x180009762  nop     dword ptr [rax+rax+00h]
0x180009767  test    eax, eax
0x180009769  jz      short loc_180009772
0x18000976b  add     rsp, 20h
0x18000976f  pop     rbx
0x180009770  retn
0x180009772  mov     rcx, [rsp+28h]; this
0x180009777  lea     r8, aOnecoreVmCommo_7; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18000977e  mov     edx, 1004h; void *
0x180009783  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
