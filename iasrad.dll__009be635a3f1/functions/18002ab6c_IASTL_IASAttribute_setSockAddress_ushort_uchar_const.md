# IASTL::IASAttribute::setSockAddress(ushort,uchar * const)

- ea: `0x18002ab6c`
- end: `0x18002abdb`
- name: `?setSockAddress@IASAttribute@IASTL@@QEAAXGQEAE@Z`
- size: `111`
- prototype: `void(IASTL::IASAttribute *__hidden this, unsigned __int16, unsigned __int8 *const)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800131b8`
- `0x18001b118`
- `0x180024e00`

## callees

- `0x180009390`
- `0x18002a6bc`
- `0x18002ab6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ab83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ab83`

## pseudocode

```c
void __fastcall IASTL::IASAttribute::setSockAddress(
        IASTL::IASAttribute *this,
        ADDRESS_FAMILY a2,
        unsigned __int8 *const a3)
{
  int v6; // edx
  struct sockaddr *v7; // rbx
  int v8; // ecx

  v7 = (struct sockaddr *)CoTaskMemAlloc(0x80u);
  if ( !v7 )
    IASTL::issue_error((IASTL *)0x8007000ELL, v6);
  INETADDR_SETSOCKADDR(a2, v7, a3, 0, 0);
  *(_QWORD *)(*(_QWORD *)this + 24LL) = v7;
  v8 = 4;
  if ( a2 != 2 )
    v8 = 10;
  *(_DWORD *)(*(_QWORD *)this + 16LL) = v8;
}

```

## disassembly

```asm
0x18002ab6c  push    rbx
0x18002ab6e  push    rbp
0x18002ab6f  push    rsi
0x18002ab70  push    rdi
0x18002ab71  sub     rsp, 38h
0x18002ab75  mov     rsi, rcx
0x18002ab78  mov     rbp, r8
0x18002ab7b  mov     ecx, 80h; cb
0x18002ab80  movzx   edi, dx
0x18002ab83  call    cs:__imp_CoTaskMemAlloc
0x18002ab89  mov     rbx, rax
0x18002ab8c  test    rax, rax
0x18002ab8f  jnz     short loc_18002AB9C
0x18002ab91  mov     ecx, 8007000Eh; this
0x18002ab96  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18002ab9c  xor     eax, eax
0x18002ab9e  xor     r9d, r9d; scope
0x18002aba1  mov     r8, rbp; addr
0x18002aba4  mov     [rsp+58h+port], ax; port
0x18002aba9  mov     rdx, rbx; a
0x18002abac  movzx   ecx, di; af
0x18002abaf  call    INETADDR_SETSOCKADDR
0x18002abb4  mov     rax, [rsi]
0x18002abb7  mov     edx, 2
0x18002abbc  cmp     dx, di
0x18002abbf  mov     [rax+18h], rbx
0x18002abc3  lea     ecx, [rdx+2]
0x18002abc6  lea     eax, [rdx+8]
0x18002abc9  cmovnz  ecx, eax
0x18002abcc  mov     rax, [rsi]
0x18002abcf  mov     [rax+10h], ecx
0x18002abd2  add     rsp, 38h
0x18002abd6  pop     rdi
0x18002abd7  pop     rsi
0x18002abd8  pop     rbp
0x18002abd9  pop     rbx
0x18002abda  retn
```
