# ATL::CSid::IsValid(void)

- ea: `0x18000d60c`
- end: `0x18000d62e`
- name: `?IsValid@CSid@ATL@@QEBA_NXZ`
- size: `34`
- prototype: `bool __fastcall(ATL::CSid *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180008888`
- `0x1800095a4`

## callees

- `0x18000d60c`

## import_xrefs

- `ADVAPI32!IsValidSid` at `0x18000d61e`
- `ADVAPI32!IsValidSid` at `0x18000d61e`

## pseudocode

```c
bool __fastcall ATL::CSid::IsValid(ATL::CSid *this)
{
  return *((_BYTE *)this + 76) && IsValidSid((char *)this + 8);
}

```

## disassembly

```asm
0x18000d60c  sub     rsp, 28h
0x18000d610  cmp     byte ptr [rcx+4Ch], 0
0x18000d614  jnz     short loc_18000D61A
0x18000d616  xor     al, al
0x18000d618  jmp     short loc_18000D629
0x18000d61a  add     rcx, 8; pSid
0x18000d61e  call    cs:__imp_IsValidSid
0x18000d624  test    eax, eax
0x18000d626  setnz   al
0x18000d629  add     rsp, 28h
0x18000d62d  retn
```
