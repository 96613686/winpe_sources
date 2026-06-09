# readtcp

- ea: `0x14000df10`
- end: `0x14000e098`
- name: `readtcp`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000df10`
- `0x14001830e`
- `0x140018350`

## import_xrefs

- `WS2_32!__imp_recv` at `0x14000e02e`
- `WS2_32!__imp_recv` at `0x14000e02e`
- `WS2_32!__imp_select` at `0x14000dff2`
- `WS2_32!__imp_select` at `0x14000dff2`
- `WS2_32!__imp_WSAGetLastError` at `0x14000dffd`
- `WS2_32!__imp_WSAGetLastError` at `0x14000e04e`
- `WS2_32!__imp_WSAGetLastError` at `0x14000dffd`
- `WS2_32!__imp_WSAGetLastError` at `0x14000e04e`

## pseudocode

```c
__int64 __fastcall readtcp(__int64 a1, char *a2, int a3)
{
  fd_set *p_readfds; // rcx
  __int64 v8; // rdx
  __int128 *v9; // rax
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  int v18; // eax
  int Error; // eax
  int v20; // eax
  unsigned int v21; // edi
  _DWORD v22[2]; // [rsp+30h] [rbp-448h] BYREF
  SOCKET v23; // [rsp+38h] [rbp-440h]
  fd_set readfds; // [rsp+240h] [rbp-238h] BYREF

  v22[1] = 0;
  memset_0(v22, 0, 0x204u);
  if ( !a3 )
    return 0;
  v23 = *(_QWORD *)a1;
  v22[0] = 1;
  while ( 1 )
  {
    p_readfds = &readfds;
    v8 = 4;
    v9 = (__int128 *)v22;
    do
    {
      v10 = *v9;
      v11 = v9[1];
      v9 += 8;
      *(_OWORD *)&p_readfds->fd_count = v10;
      v12 = *(v9 - 6);
      *(_OWORD *)&p_readfds->fd_array[1] = v11;
      v13 = *(v9 - 5);
      *(_OWORD *)&p_readfds->fd_array[3] = v12;
      v14 = *(v9 - 4);
      *(_OWORD *)&p_readfds->fd_array[5] = v13;
      v15 = *(v9 - 3);
      *(_OWORD *)&p_readfds->fd_array[7] = v14;
      v16 = *(v9 - 2);
      *(_OWORD *)&p_readfds->fd_array[9] = v15;
      v17 = *(v9 - 1);
      *(_OWORD *)&p_readfds->fd_array[11] = v16;
      *(_OWORD *)&p_readfds->fd_array[13] = v17;
      p_readfds = (fd_set *)((char *)p_readfds + 128);
      --v8;
    }
    while ( v8 );
    *(_QWORD *)&p_readfds->fd_count = *(_QWORD *)v9;
    v18 = select(64, &readfds, 0, 0, (const struct timeval *)(a1 + 8));
    if ( v18 != -1 )
      break;
    Error = WSAGetLastError();
    if ( Error != 4 )
    {
      *(_DWORD *)(a1 + 160) = 4;
      *(_DWORD *)(a1 + 164) = Error;
      return 0xFFFFFFFFLL;
    }
  }
  if ( v18 )
  {
    v20 = recv(*(_QWORD *)a1, a2, a3, 0);
    v21 = v20;
    if ( v20 == -1 )
    {
      *(_DWORD *)(a1 + 164) = WSAGetLastError();
    }
    else
    {
      if ( v20 )
        return v21;
      *(_DWORD *)(a1 + 164) = -1;
      v21 = -1;
    }
    *(_DWORD *)(a1 + 160) = 4;
    return v21;
  }
  *(_DWORD *)(a1 + 160) = 5;
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x14000df10  mov     [rsp+arg_18], rbx
0x14000df15  push    rbp
0x14000df16  push    rsi
0x14000df17  push    rdi
0x14000df18  sub     rsp, 460h
0x14000df1f  mov     rax, cs:__security_cookie
0x14000df26  xor     rax, rsp
0x14000df29  mov     [rsp+478h+var_28], rax
0x14000df31  mov     edi, r8d
0x14000df34  mov     rbp, rdx
0x14000df37  mov     rbx, rcx
0x14000df3a  xor     eax, eax
0x14000df3c  xor     edx, edx; Val
0x14000df3e  mov     [rsp+478h+var_444], eax
0x14000df42  mov     r8d, 204h; Size
0x14000df48  lea     rcx, [rsp+478h+var_448]; void *
0x14000df4d  call    memset_0
0x14000df52  test    edi, edi
0x14000df54  jnz     short loc_14000DF5D
0x14000df56  xor     eax, eax
0x14000df58  jmp     loc_14000E075
0x14000df5d  mov     rax, [rbx]
0x14000df60  lea     rsi, [rbx+8]
0x14000df64  mov     [rsp+478h+var_440], rax
0x14000df69  mov     [rsp+478h+var_448], 1
0x14000df71  lea     rcx, [rsp+478h+readfds]
0x14000df79  mov     edx, 4
0x14000df7e  lea     rax, [rsp+478h+var_448]
0x14000df83  movups  xmm0, xmmword ptr [rax]
0x14000df86  movups  xmm1, xmmword ptr [rax+10h]
0x14000df8a  lea     rax, [rax+80h]
0x14000df91  movups  xmmword ptr [rcx], xmm0
0x14000df94  movups  xmm0, xmmword ptr [rax-60h]
0x14000df98  movups  xmmword ptr [rcx+10h], xmm1
0x14000df9c  movups  xmm1, xmmword ptr [rax-50h]
0x14000dfa0  movups  xmmword ptr [rcx+20h], xmm0
0x14000dfa4  movups  xmm0, xmmword ptr [rax-40h]
0x14000dfa8  movups  xmmword ptr [rcx+30h], xmm1
0x14000dfac  movups  xmm1, xmmword ptr [rax-30h]
0x14000dfb0  movups  xmmword ptr [rcx+40h], xmm0
0x14000dfb4  movups  xmm0, xmmword ptr [rax-20h]
0x14000dfb8  movups  xmmword ptr [rcx+50h], xmm1
0x14000dfbc  movups  xmm1, xmmword ptr [rax-10h]
0x14000dfc0  movups  xmmword ptr [rcx+60h], xmm0
0x14000dfc4  movups  xmmword ptr [rcx+70h], xmm1
0x14000dfc8  lea     rcx, [rcx+80h]
0x14000dfcf  sub     rdx, 1
0x14000dfd3  jnz     short loc_14000DF83
0x14000dfd5  mov     rax, [rax]
0x14000dfd8  lea     rdx, [rsp+478h+readfds]; readfds
0x14000dfe0  xor     r9d, r9d; exceptfds
0x14000dfe3  mov     [rcx], rax
0x14000dfe6  xor     r8d, r8d; writefds
0x14000dfe9  mov     [rsp+478h+timeout], rsi; timeout
0x14000dfee  lea     ecx, [r9+40h]; nfds
0x14000dff2  call    cs:__imp_select
0x14000dff8  cmp     eax, 0FFFFFFFFh
0x14000dffb  jnz     short loc_14000E01E
0x14000dffd  call    cs:__imp_WSAGetLastError
0x14000e003  cmp     eax, 4
0x14000e006  jz      loc_14000DF71
0x14000e00c  mov     dword ptr [rbx+0A0h], 4
0x14000e016  mov     [rbx+0A4h], eax
0x14000e01c  jmp     short loc_14000E072
0x14000e01e  test    eax, eax
0x14000e020  jz      short loc_14000E068
0x14000e022  mov     rcx, [rbx]; s
0x14000e025  xor     r9d, r9d; flags
0x14000e028  mov     r8d, edi; len
0x14000e02b  mov     rdx, rbp; buf
0x14000e02e  call    cs:__imp_recv
0x14000e034  mov     edi, eax
0x14000e036  cmp     eax, 0FFFFFFFFh
0x14000e039  jz      short loc_14000E04E
0x14000e03b  test    eax, eax
0x14000e03d  jnz     short loc_14000E064
0x14000e03f  mov     dword ptr [rbx+0A4h], 0FFFFFFFFh
0x14000e049  or      edi, 0FFFFFFFFh
0x14000e04c  jmp     short loc_14000E05A
0x14000e04e  call    cs:__imp_WSAGetLastError
0x14000e054  mov     [rbx+0A4h], eax
0x14000e05a  mov     dword ptr [rbx+0A0h], 4
0x14000e064  mov     eax, edi
0x14000e066  jmp     short loc_14000E075
0x14000e068  mov     dword ptr [rbx+0A0h], 5
0x14000e072  or      eax, 0FFFFFFFFh
0x14000e075  mov     rcx, [rsp+478h+var_28]
0x14000e07d  xor     rcx, rsp; StackCookie
0x14000e080  call    __security_check_cookie
0x14000e085  mov     rbx, [rsp+478h+arg_18]
0x14000e08d  add     rsp, 460h
0x14000e094  pop     rdi
0x14000e095  pop     rsi
0x14000e096  pop     rbp
0x14000e097  retn
```
