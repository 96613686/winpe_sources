# ATL::CDacl::CAccessAce::GetLength(void)

- ea: `0x18000c170`
- end: `0x18000c186`
- name: `?GetLength@CAccessAce@CDacl@ATL@@UEBAIXZ`
- size: `22`
- prototype: `__int64 __fastcall(ATL::CDacl::CAccessAce *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x18000c178`
- `ADVAPI32!GetLengthSid` at `0x18000c178`

## pseudocode

```c
__int64 __fastcall ATL::CDacl::CAccessAce::GetLength(ATL::CDacl::CAccessAce *this)
{
  return GetLengthSid((char *)this + 16) + 8;
}

```

## disassembly

```asm
0x18000c170  sub     rsp, 28h
0x18000c174  add     rcx, 10h; pSid
0x18000c178  call    cs:__imp_GetLengthSid
0x18000c17e  add     eax, 8
0x18000c181  add     rsp, 28h
0x18000c185  retn
```
