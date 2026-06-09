# CWriter::FreeSecurityRelatedMembers(void)

- ea: `0x18002d9cc`
- end: `0x18002da4f`
- name: `?FreeSecurityRelatedMembers@CWriter@@AEAAXXZ`
- size: `131`
- prototype: `void __fastcall(CWriter *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d45c`
- `0x18002df14`

## callees

- `0x18002d9cc`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x18002d9fe`
- `ADVAPI32!FreeSid` at `0x18002da1b`
- `ADVAPI32!FreeSid` at `0x18002d9fe`
- `ADVAPI32!FreeSid` at `0x18002da1b`
- `KERNEL32!LocalFree` at `0x18002d9e1`
- `KERNEL32!LocalFree` at `0x18002da38`
- `KERNEL32!LocalFree` at `0x18002d9e1`
- `KERNEL32!LocalFree` at `0x18002da38`

## pseudocode

```c
void __fastcall CWriter::FreeSecurityRelatedMembers(CWriter *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v2 = (void *)*((_QWORD *)this + 8197);
  if ( v2 )
  {
    LocalFree(v2);
    *((_QWORD *)this + 8197) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 8196);
  if ( v3 )
  {
    FreeSid(v3);
    *((_QWORD *)this + 8196) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 8195);
  if ( v4 )
  {
    FreeSid(v4);
    *((_QWORD *)this + 8195) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 8198);
  if ( v5 )
  {
    LocalFree(v5);
    *((_QWORD *)this + 8198) = 0;
  }
}

```

## disassembly

```asm
0x18002d9cc  push    rbx
0x18002d9ce  sub     rsp, 20h
0x18002d9d2  mov     rbx, rcx
0x18002d9d5  mov     rcx, [rcx+10028h]; hMem
0x18002d9dc  test    rcx, rcx
0x18002d9df  jz      short loc_18002D9F2
0x18002d9e1  call    cs:__imp_LocalFree
0x18002d9e7  mov     qword ptr [rbx+10028h], 0
0x18002d9f2  mov     rcx, [rbx+10020h]; pSid
0x18002d9f9  test    rcx, rcx
0x18002d9fc  jz      short loc_18002DA0F
0x18002d9fe  call    cs:__imp_FreeSid
0x18002da04  mov     qword ptr [rbx+10020h], 0
0x18002da0f  mov     rcx, [rbx+10018h]; pSid
0x18002da16  test    rcx, rcx
0x18002da19  jz      short loc_18002DA2C
0x18002da1b  call    cs:__imp_FreeSid
0x18002da21  mov     qword ptr [rbx+10018h], 0
0x18002da2c  mov     rcx, [rbx+10030h]; hMem
0x18002da33  test    rcx, rcx
0x18002da36  jz      short loc_18002DA49
0x18002da38  call    cs:__imp_LocalFree
0x18002da3e  mov     qword ptr [rbx+10030h], 0
0x18002da49  add     rsp, 20h
0x18002da4d  pop     rbx
0x18002da4e  retn
```
