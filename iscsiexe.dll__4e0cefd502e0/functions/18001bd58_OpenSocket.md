# OpenSocket

- ea: `0x18001bd58`
- end: `0x18001be8d`
- name: `OpenSocket`
- size: `309`
- prototype: `int __fastcall(unsigned __int16 *, __int64, SOCKET *, _WORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c474`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x18001bd58`

## import_xrefs

- `WS2_32!__imp_bind` at `0x18001be15`
- `WS2_32!__imp_bind` at `0x18001be15`
- `WS2_32!__imp_closesocket` at `0x18001be2b`
- `WS2_32!__imp_closesocket` at `0x18001be2b`
- `WS2_32!__imp_getsockname` at `0x18001be52`
- `WS2_32!__imp_getsockname` at `0x18001be52`
- `WS2_32!__imp_socket` at `0x18001bdac`
- `WS2_32!__imp_socket` at `0x18001bdac`
- `WS2_32!__imp_WSAGetLastError` at `0x18001bdbb`
- `WS2_32!__imp_WSAGetLastError` at `0x18001be20`
- `WS2_32!__imp_WSAGetLastError` at `0x18001bdbb`
- `WS2_32!__imp_WSAGetLastError` at `0x18001be20`

## pseudocode

```c
int __fastcall OpenSocket(unsigned __int16 *a1, __int64 a2, SOCKET *a3, _WORD *a4)
{
  SOCKET v7; // rdi
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  int Error; // ebx
  __int16 v17; // ax
  int namelen[4]; // [rsp+20h] [rbp-69h] BYREF
  struct sockaddr name; // [rsp+30h] [rbp-59h] BYREF
  __int128 v20; // [rsp+40h] [rbp-49h]
  __int128 v21; // [rsp+50h] [rbp-39h]
  __int128 v22; // [rsp+60h] [rbp-29h]
  __int128 v23; // [rsp+70h] [rbp-19h]
  __int128 v24; // [rsp+80h] [rbp-9h]
  __int128 v25; // [rsp+90h] [rbp+7h]
  __int128 v26; // [rsp+A0h] [rbp+17h]

  namelen[0] = 0;
  memset_0(&name, 0, 0x80u);
  v7 = socket(*a1, 1, 0);
  if ( v7 == -1 )
    return WSAGetLastError();
  v9 = *((_OWORD *)a1 + 1);
  name = *(struct sockaddr *)a1;
  v10 = *((_OWORD *)a1 + 2);
  v20 = v9;
  v11 = *((_OWORD *)a1 + 3);
  v21 = v10;
  v12 = *((_OWORD *)a1 + 4);
  v22 = v11;
  v13 = *((_OWORD *)a1 + 5);
  v23 = v12;
  v14 = *((_OWORD *)a1 + 6);
  v24 = v13;
  v15 = *((_OWORD *)a1 + 7);
  v25 = v14;
  v26 = v15;
  *(_WORD *)name.sa_data = 0;
  if ( bind(v7, &name, 128) == -1
    || (memset_0(&name, 0, 0x80u), namelen[0] = 128, getsockname(v7, &name, namelen) == -1) )
  {
    Error = WSAGetLastError();
    closesocket(v7);
    return Error;
  }
  else
  {
    v17 = *(_WORD *)name.sa_data;
    *a3 = v7;
    *a4 = v17;
    return 0;
  }
}

```

## disassembly

```asm
0x18001bd58  mov     [rsp-8+arg_8], rbx
0x18001bd5d  push    rbp
0x18001bd5e  push    rsi
0x18001bd5f  push    rdi
0x18001bd60  push    r14
0x18001bd62  push    r15
0x18001bd64  lea     rbp, [rsp-37h]
0x18001bd69  sub     rsp, 0C0h
0x18001bd70  mov     rax, cs:__security_cookie
0x18001bd77  xor     rax, rsp
0x18001bd7a  mov     [rbp+57h+var_30], rax
0x18001bd7e  mov     rsi, r8
0x18001bd81  mov     [rbp+57h+namelen], 0
0x18001bd88  mov     rbx, rcx
0x18001bd8b  mov     r15d, 80h
0x18001bd91  mov     r8d, r15d; Size
0x18001bd94  lea     rcx, [rbp+57h+name]; void *
0x18001bd98  xor     edx, edx; Val
0x18001bd9a  mov     r14, r9
0x18001bd9d  call    memset_0
0x18001bda2  movzx   ecx, word ptr [rbx]; af
0x18001bda5  lea     edx, [r15-7Fh]; type
0x18001bda9  xor     r8d, r8d; protocol
0x18001bdac  call    cs:__imp_socket
0x18001bdb2  mov     rdi, rax
0x18001bdb5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bdb9  jnz     short loc_18001BDC6
0x18001bdbb  call    cs:__imp_WSAGetLastError
0x18001bdc1  jmp     loc_18001BE6A
0x18001bdc6  movaps  xmm0, xmmword ptr [rbx]
0x18001bdc9  lea     rdx, [rbp+57h+name]; name
0x18001bdcd  movaps  xmm1, xmmword ptr [rbx+10h]
0x18001bdd1  xor     eax, eax
0x18001bdd3  movaps  xmmword ptr [rbp+57h+name.sa_family], xmm0
0x18001bdd7  mov     r8d, r15d; namelen
0x18001bdda  movaps  xmm0, xmmword ptr [rbx+20h]
0x18001bdde  mov     rcx, rdi; s
0x18001bde1  movaps  [rbp+57h+var_A0], xmm1
0x18001bde5  movaps  xmm1, xmmword ptr [rbx+30h]
0x18001bde9  movaps  [rbp+57h+var_90], xmm0
0x18001bded  movaps  xmm0, xmmword ptr [rbx+40h]
0x18001bdf1  movaps  [rbp+57h+var_80], xmm1
0x18001bdf5  movaps  xmm1, xmmword ptr [rbx+50h]
0x18001bdf9  movaps  [rbp+57h+var_70], xmm0
0x18001bdfd  movaps  xmm0, xmmword ptr [rbx+60h]
0x18001be01  movaps  [rbp+57h+var_60], xmm1
0x18001be05  movaps  xmm1, xmmword ptr [rbx+70h]
0x18001be09  movaps  [rbp+57h+var_50], xmm0
0x18001be0d  movaps  [rbp+57h+var_40], xmm1
0x18001be11  mov     word ptr [rbp+57h+name.sa_data], ax
0x18001be15  call    cs:__imp_bind
0x18001be1b  cmp     eax, 0FFFFFFFFh
0x18001be1e  jnz     short loc_18001BE35
0x18001be20  call    cs:__imp_WSAGetLastError
0x18001be26  mov     rcx, rdi; s
0x18001be29  mov     ebx, eax
0x18001be2b  call    cs:__imp_closesocket
0x18001be31  mov     eax, ebx
0x18001be33  jmp     short loc_18001BE6A
0x18001be35  mov     r8, r15; Size
0x18001be38  lea     rcx, [rbp+57h+name]; void *
0x18001be3c  xor     edx, edx; Val
0x18001be3e  call    memset_0
0x18001be43  lea     r8, [rbp+57h+namelen]; namelen
0x18001be47  mov     [rbp+57h+namelen], r15d
0x18001be4b  lea     rdx, [rbp+57h+name]; name
0x18001be4f  mov     rcx, rdi; s
0x18001be52  call    cs:__imp_getsockname
0x18001be58  cmp     eax, 0FFFFFFFFh
0x18001be5b  jz      short loc_18001BE20
0x18001be5d  movzx   eax, word ptr [rbp+57h+name.sa_data]
0x18001be61  mov     [rsi], rdi
0x18001be64  mov     [r14], ax
0x18001be68  xor     eax, eax
0x18001be6a  mov     rcx, [rbp+57h+var_30]
0x18001be6e  xor     rcx, rsp; StackCookie
0x18001be71  call    __security_check_cookie
0x18001be76  mov     rbx, [rsp+0E0h+arg_8]
0x18001be7e  add     rsp, 0C0h
0x18001be85  pop     r15
0x18001be87  pop     r14
0x18001be89  pop     rdi
0x18001be8a  pop     rsi
0x18001be8b  pop     rbp
0x18001be8c  retn
```
