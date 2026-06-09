# tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>(void)

- ea: `0x1800123d8`
- end: `0x1800123ef`
- name: `??1?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ`
- size: `23`
- prototype: `PVOID __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012b00`

## callees

- `0x1800123d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800123e4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800123e4`

## pseudocode

```c
PVOID __fastcall tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>(
        void **a1)
{
  void *v1; // rcx
  PVOID result; // rax

  v1 = *a1;
  if ( v1 )
    return FreeSid(v1);
  return result;
}

```

## disassembly

```asm
0x1800123d8  sub     rsp, 28h
0x1800123dc  mov     rcx, [rcx]; pSid
0x1800123df  test    rcx, rcx
0x1800123e2  jz      short loc_1800123EA
0x1800123e4  call    cs:__imp_FreeSid
0x1800123ea  add     rsp, 28h
0x1800123ee  retn
```
