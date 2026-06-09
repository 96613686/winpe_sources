# nfsoncrpc_open_socket_and_apply_options

- ea: `0x14000d264`
- end: `0x14000d33b`
- name: `nfsoncrpc_open_socket_and_apply_options`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000cdd0`

## callees

- `0x14000d264`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x14000d2d0`
- `WS2_32!__imp_closesocket` at `0x14000d319`
- `WS2_32!__imp_closesocket` at `0x14000d2d0`
- `WS2_32!__imp_closesocket` at `0x14000d319`
- `WS2_32!__imp_setsockopt` at `0x14000d2c2`
- `WS2_32!__imp_setsockopt` at `0x14000d30b`
- `WS2_32!__imp_setsockopt` at `0x14000d2c2`
- `WS2_32!__imp_setsockopt` at `0x14000d30b`
- `WS2_32!__imp_socket` at `0x14000d27b`
- `WS2_32!__imp_socket` at `0x14000d27b`

## pseudocode

```c
__int64 __fastcall nfsoncrpc_open_socket_and_apply_options(int *a1)
{
  SOCKET v2; // rax
  SOCKET v3; // rdi
  int optval; // [rsp+40h] [rbp+8h] BYREF

  v2 = socket(a1[4], a1[5], a1[6]);
  v3 = v2;
  if ( v2 == -1 )
  {
    a1[44] = 17;
    return v3;
  }
  if ( a1[7] )
  {
    optval = 1;
    if ( setsockopt(v2, 0xFFFF, -5, (const char *)&optval, 4) == -1 )
    {
      closesocket(v3);
      a1[44] = 12;
      return -1;
    }
  }
  if ( a1[9] )
  {
    optval = 1;
    if ( setsockopt(v3, 0xFFFF, 32, (const char *)&optval, 4) == -1 )
    {
      closesocket(v3);
      a1[44] = 3;
      return -1;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14000d264  mov     [rsp+arg_8], rbx
0x14000d269  push    rdi
0x14000d26a  sub     rsp, 30h
0x14000d26e  mov     r8d, [rcx+18h]; protocol
0x14000d272  mov     rbx, rcx
0x14000d275  mov     edx, [rcx+14h]; type
0x14000d278  mov     ecx, [rcx+10h]; af
0x14000d27b  call    cs:__imp_socket
0x14000d281  mov     rdi, rax
0x14000d284  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000d288  jnz     short loc_14000D299
0x14000d28a  mov     dword ptr [rbx+0B0h], 11h
0x14000d294  jmp     loc_14000D32D
0x14000d299  cmp     dword ptr [rbx+1Ch], 0
0x14000d29d  jz      short loc_14000D2E2
0x14000d29f  lea     r9, [rsp+38h+optval]; optval
0x14000d2a4  mov     [rsp+38h+optval], 1
0x14000d2ac  mov     edx, 0FFFFh; level
0x14000d2b1  mov     [rsp+38h+optlen], 4; optlen
0x14000d2b9  mov     r8d, 0FFFFFFFBh; optname
0x14000d2bf  mov     rcx, rdi; s
0x14000d2c2  call    cs:__imp_setsockopt
0x14000d2c8  cmp     eax, 0FFFFFFFFh
0x14000d2cb  jnz     short loc_14000D2E2
0x14000d2cd  mov     rcx, rdi; s
0x14000d2d0  call    cs:__imp_closesocket
0x14000d2d6  mov     dword ptr [rbx+0B0h], 0Ch
0x14000d2e0  jmp     short loc_14000D329
0x14000d2e2  cmp     dword ptr [rbx+24h], 0
0x14000d2e6  jz      short loc_14000D32D
0x14000d2e8  lea     r9, [rsp+38h+optval]; optval
0x14000d2ed  mov     [rsp+38h+optval], 1
0x14000d2f5  mov     edx, 0FFFFh; level
0x14000d2fa  mov     [rsp+38h+optlen], 4; optlen
0x14000d302  mov     r8d, 20h ; ' '; optname
0x14000d308  mov     rcx, rdi; s
0x14000d30b  call    cs:__imp_setsockopt
0x14000d311  cmp     eax, 0FFFFFFFFh
0x14000d314  jnz     short loc_14000D32D
0x14000d316  mov     rcx, rdi; s
0x14000d319  call    cs:__imp_closesocket
0x14000d31f  mov     dword ptr [rbx+0B0h], 3
0x14000d329  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000d32d  mov     rbx, [rsp+38h+arg_8]
0x14000d332  mov     rax, rdi
0x14000d335  add     rsp, 30h
0x14000d339  pop     rdi
0x14000d33a  retn
```
