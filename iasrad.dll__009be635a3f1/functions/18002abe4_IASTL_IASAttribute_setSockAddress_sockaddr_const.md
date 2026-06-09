# IASTL::IASAttribute::setSockAddress(sockaddr * const)

- ea: `0x18002abe4`
- end: `0x18002ac71`
- name: `?setSockAddress@IASAttribute@IASTL@@QEAAXQEAUsockaddr@@@Z`
- size: `141`
- prototype: `void __fastcall(IASTL::IASAttribute *__hidden this, struct sockaddr *const)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800130a4`
- `0x1800138c8`
- `0x18001d4d0`

## callees

- `0x180009390`
- `0x18002a6bc`
- `0x18002abe4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002abfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002abfa`

## pseudocode

```c
void __fastcall IASTL::IASAttribute::setSockAddress(IASTL::IASAttribute *this, struct sockaddr *const a2)
{
  int v4; // edx
  struct sockaddr *v5; // rbx
  ADDRESS_FAMILY sa_family; // bp
  SCOPE_ID v7; // r9d
  int v8; // edi
  __int64 v9; // r8

  v5 = (struct sockaddr *)CoTaskMemAlloc(0x80u);
  if ( !v5 )
    IASTL::issue_error((IASTL *)0x8007000ELL, v4);
  sa_family = a2->sa_family;
  if ( a2->sa_family == 23 )
    v7.0 = *(struct $::$38AB66A4EA7C49F20D686D738A108FEA::$013671E5920392F7B68C675C97F9F7D8 *)&a2[1].sa_data[6];
  else
    v7.0 = 0;
  v8 = 4;
  v9 = 8;
  if ( sa_family != 23 )
    v9 = 4;
  INETADDR_SETSOCKADDR(sa_family, v5, (char *)a2 + v9, v7, *(_WORD *)a2->sa_data);
  *(_QWORD *)(*(_QWORD *)this + 24LL) = v5;
  if ( sa_family != 2 )
    v8 = 10;
  *(_DWORD *)(*(_QWORD *)this + 16LL) = v8;
}

```

## disassembly

```asm
0x18002abe4  push    rbx
0x18002abe6  push    rbp
0x18002abe7  push    rsi
0x18002abe8  push    rdi
0x18002abe9  push    r14
0x18002abeb  sub     rsp, 30h
0x18002abef  mov     r14, rcx
0x18002abf2  mov     rsi, rdx
0x18002abf5  mov     ecx, 80h; cb
0x18002abfa  call    cs:__imp_CoTaskMemAlloc
0x18002ac00  mov     rbx, rax
0x18002ac03  test    rax, rax
0x18002ac06  jnz     short loc_18002AC13
0x18002ac08  mov     ecx, 8007000Eh; this
0x18002ac0d  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18002ac13  movzx   ebp, word ptr [rsi]
0x18002ac16  movzx   eax, word ptr [rsi+2]
0x18002ac1a  cmp     bp, 17h
0x18002ac1e  jnz     short loc_18002AC26
0x18002ac20  mov     r9d, [rsi+18h]
0x18002ac24  jmp     short loc_18002AC29
0x18002ac26  xor     r9d, r9d; scope
0x18002ac29  mov     edi, 4
0x18002ac2e  mov     [rsp+58h+port], ax; port
0x18002ac33  cmp     bp, 17h
0x18002ac37  mov     rdx, rbx; a
0x18002ac3a  movzx   ecx, bp; af
0x18002ac3d  lea     r8d, [rdi+4]
0x18002ac41  cmovnz  r8d, edi
0x18002ac45  add     r8, rsi; addr
0x18002ac48  call    INETADDR_SETSOCKADDR
0x18002ac4d  mov     rax, [r14]
0x18002ac50  lea     ecx, [rdi-2]
0x18002ac53  cmp     cx, bp
0x18002ac56  mov     [rax+18h], rbx
0x18002ac5a  lea     eax, [rdi+6]
0x18002ac5d  cmovnz  edi, eax
0x18002ac60  mov     rax, [r14]
0x18002ac63  mov     [rax+10h], edi
0x18002ac66  add     rsp, 30h
0x18002ac6a  pop     r14
0x18002ac6c  pop     rdi
0x18002ac6d  pop     rsi
0x18002ac6e  pop     rbp
0x18002ac6f  pop     rbx
0x18002ac70  retn
```
