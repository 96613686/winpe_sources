# ReadFromSocket

- ea: `0x18001be94`
- end: `0x18001bf33`
- name: `ReadFromSocket`
- size: `159`
- prototype: `__int64 __fastcall(SOCKET s, char *buf, int len, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c138`

## callees

- `0x180001410`
- `0x18001be94`

## import_xrefs

- `WS2_32!__imp_recv` at `0x18001bf04`
- `WS2_32!__imp_recv` at `0x18001bf04`
- `WS2_32!__imp_select` at `0x18001beeb`
- `WS2_32!__imp_select` at `0x18001beeb`

## pseudocode

```c
__int64 __fastcall ReadFromSocket(SOCKET s, char *buf, int len, int *a4)
{
  int v8; // eax
  struct timeval v10; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v11[2]; // [rsp+38h] [rbp-40h] BYREF

  v11[1] = s;
  *a4 = 0;
  v10.tv_usec = 0;
  v11[0] = 1;
  v10.tv_sec = 15;
  if ( (unsigned int)(select(0, (fd_set *)v11, 0, 0, &v10) + 1) <= 1 )
    return 1;
  v8 = recv(s, buf, len, 0);
  if ( (unsigned int)(v8 + 1) <= 1 )
    return 1;
  *a4 = v8;
  return 0;
}

```

## disassembly

```asm
0x18001be94  mov     r11, rsp
0x18001be97  push    rbx
0x18001be98  push    rbp
0x18001be99  push    rsi
0x18001be9a  push    rdi
0x18001be9b  sub     rsp, 58h
0x18001be9f  mov     rax, cs:__security_cookie
0x18001bea6  xor     rax, rsp
0x18001bea9  mov     [rsp+78h+var_30], rax
0x18001beae  xor     eax, eax
0x18001beb0  mov     [r11-38h], rcx
0x18001beb4  mov     [r9], eax
0x18001beb7  mov     rbx, r9
0x18001beba  mov     [r11-48h], rax
0x18001bebe  mov     ebp, r8d
0x18001bec1  lea     rax, [r11-48h]
0x18001bec5  mov     qword ptr [r11-40h], 1
0x18001becd  mov     rsi, rdx
0x18001bed0  mov     [r11-58h], rax
0x18001bed4  mov     rdi, rcx
0x18001bed7  mov     dword ptr [rsp+78h+var_48], 0Fh
0x18001bedf  xor     r9d, r9d; exceptfds
0x18001bee2  lea     rdx, [r11-40h]; readfds
0x18001bee6  xor     r8d, r8d; writefds
0x18001bee9  xor     ecx, ecx; nfds
0x18001beeb  call    cs:__imp_select
0x18001bef1  inc     eax
0x18001bef3  cmp     eax, 1
0x18001bef6  jbe     short loc_18001BF18
0x18001bef8  xor     r9d, r9d; flags
0x18001befb  mov     r8d, ebp; len
0x18001befe  mov     rdx, rsi; buf
0x18001bf01  mov     rcx, rdi; s
0x18001bf04  call    cs:__imp_recv
0x18001bf0a  lea     ecx, [rax+1]
0x18001bf0d  cmp     ecx, 1
0x18001bf10  jbe     short loc_18001BF18
0x18001bf12  mov     [rbx], eax
0x18001bf14  xor     eax, eax
0x18001bf16  jmp     short loc_18001BF1D
0x18001bf18  mov     eax, 1
0x18001bf1d  mov     rcx, [rsp+78h+var_30]
0x18001bf22  xor     rcx, rsp; StackCookie
0x18001bf25  call    __security_check_cookie
0x18001bf2a  add     rsp, 58h
0x18001bf2e  pop     rdi
0x18001bf2f  pop     rsi
0x18001bf30  pop     rbp
0x18001bf31  pop     rbx
0x18001bf32  retn
```
