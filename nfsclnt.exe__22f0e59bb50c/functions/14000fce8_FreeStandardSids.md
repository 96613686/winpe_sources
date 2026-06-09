# FreeStandardSids

- ea: `0x14000fce8`
- end: `0x14000fd48`
- name: `FreeStandardSids`
- size: `96`
- prototype: `PVOID()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000facc`
- `0x14000fd50`

## callees

- `0x14000fce8`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x14000fcf8`
- `ADVAPI32!FreeSid` at `0x14000fd15`
- `ADVAPI32!FreeSid` at `0x14000fd32`
- `ADVAPI32!FreeSid` at `0x14000fcf8`
- `ADVAPI32!FreeSid` at `0x14000fd15`
- `ADVAPI32!FreeSid` at `0x14000fd32`

## pseudocode

```c
PVOID FreeStandardSids()
{
  PVOID result; // rax

  if ( qword_140021BA8 )
  {
    result = FreeSid(qword_140021BA8);
    qword_140021BA8 = 0;
  }
  if ( pSid )
  {
    result = FreeSid(pSid);
    pSid = 0;
  }
  if ( qword_140021BB0 )
  {
    result = FreeSid(qword_140021BB0);
    qword_140021BB0 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000fce8  sub     rsp, 28h
0x14000fcec  mov     rcx, cs:qword_140021BA8; pSid
0x14000fcf3  test    rcx, rcx
0x14000fcf6  jz      short loc_14000FD09
0x14000fcf8  call    cs:__imp_FreeSid
0x14000fcfe  mov     cs:qword_140021BA8, 0
0x14000fd09  mov     rcx, cs:pSid; pSid
0x14000fd10  test    rcx, rcx
0x14000fd13  jz      short loc_14000FD26
0x14000fd15  call    cs:__imp_FreeSid
0x14000fd1b  mov     cs:pSid, 0
0x14000fd26  mov     rcx, cs:qword_140021BB0; pSid
0x14000fd2d  test    rcx, rcx
0x14000fd30  jz      short loc_14000FD43
0x14000fd32  call    cs:__imp_FreeSid
0x14000fd38  mov     cs:qword_140021BB0, 0
0x14000fd43  add     rsp, 28h
0x14000fd47  retn
```
