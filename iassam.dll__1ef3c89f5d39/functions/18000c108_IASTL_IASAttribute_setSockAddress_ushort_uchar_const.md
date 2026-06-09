# IASTL::IASAttribute::setSockAddress(ushort,uchar * const)

- ea: `0x18000c108`
- end: `0x18000c170`
- name: `?setSockAddress@IASAttribute@IASTL@@QEAAXGQEAE@Z`
- size: `104`
- prototype: `void(IASTL::IASAttribute *__hidden this, unsigned __int16, unsigned __int8 *const)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014d20`
- `0x18001c160`
- `0x18002752c`
- `0x1800276b0`

## callees

- `0x18000b81c`
- `0x18000c108`
- `0x18000c360`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c11f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c11f`

## pseudocode

```c
void __fastcall IASTL::IASAttribute::setSockAddress(
        IASTL::IASAttribute *this,
        ADDRESS_FAMILY a2,
        unsigned __int8 *const a3)
{
  struct sockaddr *v6; // rax
  int v7; // edx
  struct sockaddr *v8; // rbx
  int v9; // ecx
  USHORT v10; // [rsp+20h] [rbp-38h]

  v6 = (struct sockaddr *)CoTaskMemAlloc(0x80u);
  v8 = v6;
  if ( !v6 )
    IASTL::issue_error((IASTL *)0x8007000ELL, v7);
  INETADDR_SETSOCKADDR(a2, v6, a3, 0, v10);
  *(_QWORD *)(*(_QWORD *)this + 24LL) = v8;
  v9 = 4;
  if ( a2 != 2 )
    v9 = 10;
  *(_DWORD *)(*(_QWORD *)this + 16LL) = v9;
}

```

## disassembly

```asm
0x18000c108  push    rbx
0x18000c10a  push    rbp
0x18000c10b  push    rsi
0x18000c10c  push    rdi
0x18000c10d  sub     rsp, 38h
0x18000c111  mov     rsi, rcx
0x18000c114  mov     rbp, r8
0x18000c117  mov     ecx, 80h; cb
0x18000c11c  movzx   edi, dx
0x18000c11f  call    cs:__imp_CoTaskMemAlloc
0x18000c125  mov     rbx, rax
0x18000c128  test    rax, rax
0x18000c12b  jnz     short loc_18000C138
0x18000c12d  mov     ecx, 8007000Eh; this
0x18000c132  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18000c138  xor     r9d, r9d; scope
0x18000c13b  mov     r8, rbp; addr
0x18000c13e  mov     rdx, rbx; a
0x18000c141  movzx   ecx, di; af
0x18000c144  call    INETADDR_SETSOCKADDR
0x18000c149  mov     rax, [rsi]
0x18000c14c  mov     edx, 2
0x18000c151  cmp     dx, di
0x18000c154  mov     [rax+18h], rbx
0x18000c158  lea     ecx, [rdx+2]
0x18000c15b  lea     eax, [rdx+8]
0x18000c15e  cmovnz  ecx, eax
0x18000c161  mov     rax, [rsi]
0x18000c164  mov     [rax+10h], ecx
0x18000c167  add     rsp, 38h
0x18000c16b  pop     rdi
0x18000c16c  pop     rsi
0x18000c16d  pop     rbp
0x18000c16e  pop     rbx
0x18000c16f  retn
```
