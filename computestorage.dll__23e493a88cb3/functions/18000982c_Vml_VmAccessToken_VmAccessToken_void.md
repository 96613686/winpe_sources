# Vml::VmAccessToken::~VmAccessToken(void)

- ea: `0x18000982c`
- end: `0x180009865`
- name: `??1VmAccessToken@Vml@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800434ba`

## callees

- `0x18000982c`
- `0x18000ad80`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009838`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009838`

## string_xrefs

- `0x180009853`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmAccessToken::~VmAccessToken(void **this)
{
  void *v1; // rcx
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *this;
  if ( v1 )
  {
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1004,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v2);
  }
}

```

## disassembly

```asm
0x18000982c  sub     rsp, 28h
0x180009830  mov     rcx, [rcx]; hObject
0x180009833  test    rcx, rcx
0x180009836  jz      short loc_180009848
0x180009838  call    cs:__imp_CloseHandle
0x18000983f  nop     dword ptr [rax+rax+00h]
0x180009844  test    eax, eax
0x180009846  jz      short loc_18000984E
0x180009848  add     rsp, 28h
0x18000984c  retn
0x18000984e  mov     rcx, [rsp+28h]; this
0x180009853  lea     r8, aOnecoreVmCommo_7; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18000985a  mov     edx, 1004h; void *
0x18000985f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
