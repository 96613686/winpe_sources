# CWriter::FreeSecurityRelatedMembers(void)

- ea: `0x18002a664`
- end: `0x18002a6e7`
- name: `?FreeSecurityRelatedMembers@CWriter@@AEAAXXZ`
- size: `131`
- prototype: `void __fastcall(CWriter *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a2fc`
- `0x18002aad0`

## callees

- `0x18002a664`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18002a679`
- `KERNEL32!LocalFree` at `0x18002a6d0`
- `KERNEL32!LocalFree` at `0x18002a679`
- `KERNEL32!LocalFree` at `0x18002a6d0`
- `ADVAPI32!FreeSid` at `0x18002a696`
- `ADVAPI32!FreeSid` at `0x18002a6b3`
- `ADVAPI32!FreeSid` at `0x18002a696`
- `ADVAPI32!FreeSid` at `0x18002a6b3`

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
0x18002a664  push    rbx
0x18002a666  sub     rsp, 20h
0x18002a66a  mov     rbx, rcx
0x18002a66d  mov     rcx, [rcx+10028h]; hMem
0x18002a674  test    rcx, rcx
0x18002a677  jz      short loc_18002A68A
0x18002a679  call    cs:__imp_LocalFree
0x18002a67f  mov     qword ptr [rbx+10028h], 0
0x18002a68a  mov     rcx, [rbx+10020h]; pSid
0x18002a691  test    rcx, rcx
0x18002a694  jz      short loc_18002A6A7
0x18002a696  call    cs:__imp_FreeSid
0x18002a69c  mov     qword ptr [rbx+10020h], 0
0x18002a6a7  mov     rcx, [rbx+10018h]; pSid
0x18002a6ae  test    rcx, rcx
0x18002a6b1  jz      short loc_18002A6C4
0x18002a6b3  call    cs:__imp_FreeSid
0x18002a6b9  mov     qword ptr [rbx+10018h], 0
0x18002a6c4  mov     rcx, [rbx+10030h]; hMem
0x18002a6cb  test    rcx, rcx
0x18002a6ce  jz      short loc_18002A6E1
0x18002a6d0  call    cs:__imp_LocalFree
0x18002a6d6  mov     qword ptr [rbx+10030h], 0
0x18002a6e1  add     rsp, 20h
0x18002a6e5  pop     rbx
0x18002a6e6  retn
```
