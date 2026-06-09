# writetcp

- ea: `0x14000e0a0`
- end: `0x14000e119`
- name: `writetcp`
- size: `121`
- prototype: `__int64 __fastcall(__int64, const char *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000e0a0`

## import_xrefs

- `WS2_32!__imp_sendto` at `0x14000e0db`
- `WS2_32!__imp_sendto` at `0x14000e0db`
- `WS2_32!__imp_WSAGetLastError` at `0x14000e0fe`
- `WS2_32!__imp_WSAGetLastError` at `0x14000e0fe`

## pseudocode

```c
__int64 __fastcall writetcp(__int64 a1, const char *a2, int a3)
{
  int v6; // esi
  const struct sockaddr *to; // r14
  int v8; // eax
  __int64 result; // rax

  v6 = a3;
  if ( a3 <= 0 )
    return (unsigned int)a3;
  to = (const struct sockaddr *)(a1 + 24);
  while ( 1 )
  {
    v8 = sendto(*(_QWORD *)a1, a2, v6, 0, to, *(_DWORD *)(a1 + 152));
    if ( v8 == -1 )
      break;
    v6 -= v8;
    a2 += v8;
    if ( v6 <= 0 )
      return (unsigned int)a3;
  }
  *(_DWORD *)(a1 + 164) = WSAGetLastError();
  result = 0xFFFFFFFFLL;
  *(_DWORD *)(a1 + 160) = 3;
  return result;
}

```

## disassembly

```asm
0x14000e0a0  push    rbx
0x14000e0a2  push    rbp
0x14000e0a3  push    rsi
0x14000e0a4  push    rdi
0x14000e0a5  push    r14
0x14000e0a7  sub     rsp, 30h
0x14000e0ab  mov     edi, r8d
0x14000e0ae  mov     rbp, rdx
0x14000e0b1  mov     rbx, rcx
0x14000e0b4  mov     esi, r8d
0x14000e0b7  test    r8d, r8d
0x14000e0ba  jle     short loc_14000E0F1
0x14000e0bc  lea     r14, [rcx+18h]
0x14000e0c0  mov     eax, [rbx+98h]
0x14000e0c6  xor     r9d, r9d; flags
0x14000e0c9  mov     rcx, [rbx]; s
0x14000e0cc  mov     r8d, esi; len
0x14000e0cf  mov     [rsp+58h+tolen], eax; tolen
0x14000e0d3  mov     rdx, rbp; buf
0x14000e0d6  mov     [rsp+58h+to], r14; to
0x14000e0db  call    cs:__imp_sendto
0x14000e0e1  cmp     eax, 0FFFFFFFFh
0x14000e0e4  jz      short loc_14000E0FE
0x14000e0e6  sub     esi, eax
0x14000e0e8  cdqe
0x14000e0ea  add     rbp, rax
0x14000e0ed  test    esi, esi
0x14000e0ef  jg      short loc_14000E0C0
0x14000e0f1  mov     eax, edi
0x14000e0f3  add     rsp, 30h
0x14000e0f7  pop     r14
0x14000e0f9  pop     rdi
0x14000e0fa  pop     rsi
0x14000e0fb  pop     rbp
0x14000e0fc  pop     rbx
0x14000e0fd  retn
0x14000e0fe  call    cs:__imp_WSAGetLastError
0x14000e104  mov     [rbx+0A4h], eax
0x14000e10a  or      eax, 0FFFFFFFFh
0x14000e10d  mov     dword ptr [rbx+0A0h], 3
0x14000e117  jmp     short loc_14000E0F3
```
