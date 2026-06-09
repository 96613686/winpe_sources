# ODBC_PARAMETER::CopyValue(char const *)

- ea: `0x180001d40`
- end: `0x180001d92`
- name: `?CopyValue@ODBC_PARAMETER@@QEAAHPEBD@Z`
- size: `82`
- prototype: `_BOOL8 __fastcall(void **this, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001d40`
- `0x18000ec56`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180001d78`
- `KERNEL32!SetLastError` at `0x180001d78`

## pseudocode

```c
_BOOL8 __fastcall ODBC_PARAMETER::CopyValue(void **this, const char *a2)
{
  __int64 v3; // rax
  int v4; // eax
  __int64 v5; // rbx

  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  v4 = v3 + 1;
  v5 = v4;
  if ( v4 > (__int64)this[3] )
    SetLastError(0x7Au);
  else
    memcpy_0(this[2], a2, v4);
  return v5 <= (__int64)this[3];
}

```

## disassembly

```asm
0x180001d40  mov     [rsp+arg_0], rbx
0x180001d45  push    rdi
0x180001d46  sub     rsp, 20h
0x180001d4a  mov     rdi, rcx
0x180001d4d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001d51  inc     rax
0x180001d54  cmp     byte ptr [rdx+rax], 0
0x180001d58  jnz     short loc_180001D51
0x180001d5a  inc     eax
0x180001d5c  movsxd  rbx, eax
0x180001d5f  cmp     rbx, [rcx+18h]
0x180001d63  jg      short loc_180001D73
0x180001d65  mov     rcx, [rcx+10h]; void *
0x180001d69  mov     r8, rbx; Size
0x180001d6c  call    memcpy_0
0x180001d71  jmp     short loc_180001D7E
0x180001d73  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180001d78  call    cs:__imp_SetLastError
0x180001d7e  xor     eax, eax
0x180001d80  cmp     rbx, [rdi+18h]
0x180001d84  mov     rbx, [rsp+28h+arg_0]
0x180001d89  setle   al
0x180001d8c  add     rsp, 20h
0x180001d90  pop     rdi
0x180001d91  retn
```
