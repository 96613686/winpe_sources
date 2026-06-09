# nfsoncrpc_rpc_create_client_ex

- ea: `0x14000d5f8`
- end: `0x14000d709`
- name: `nfsoncrpc_rpc_create_client_ex`
- size: `273`
- prototype: `char *__fastcall(__int64, int, int, unsigned int, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d4f0`
- `0x14000f4d0`
- `0x14000f66c`

## callees

- `0x14000cb74`
- `0x14000d5f8`
- `0x14000dcf0`
- `0x14000e9e4`
- `0x140019010`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x14000d67f`
- `WS2_32!__imp_closesocket` at `0x14000d67f`

## pseudocode

```c
char *__fastcall nfsoncrpc_rpc_create_client_ex(
        __int64 a1,
        int a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  char *v10; // rax
  char *v11; // rsi
  SOCKET v12; // rcx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax

  if ( !(unsigned int)nfsoncrpc_connect() )
    goto LABEL_9;
  if ( *(_DWORD *)(a1 + 24) == 6 )
  {
    v10 = nfsoncrpc_clnttcp_create(a1, a2, a3, a4, a5);
  }
  else
  {
    if ( *(_DWORD *)(a1 + 24) != 17 )
      goto LABEL_7;
    v10 = nfsoncrpc_clntudp_create(a1, a2, a3, a6, a4, a5);
  }
  v11 = v10;
  if ( !v10 )
  {
LABEL_7:
    v12 = *(_QWORD *)(a1 + 184);
    if ( v12 != -1 )
    {
      closesocket(v12);
      *(_QWORD *)(a1 + 184) = -1;
    }
    goto LABEL_9;
  }
  v14 = (**((__int64 (__fastcall ***)(char *, _QWORD, __int64 (__fastcall *)(), _QWORD, __int64 (__fastcall *)(), _QWORD, __int64))v10
          + 1))(
          v10,
          0,
          xdr_void,
          0,
          xdr_void,
          0,
          a6);
  if ( v14 )
  {
    v15 = v14 - 6;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        v17 = v16 - 2;
        if ( v17 )
        {
          if ( (unsigned int)(v17 - 1) >= 2 )
          {
            (*(void (__fastcall **)(char *))(*((_QWORD *)v11 + 1) + 32LL))(v11);
LABEL_9:
            *(_DWORD *)(a1 + 176) = 3;
            return 0;
          }
        }
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x14000d5f8  push    rbx
0x14000d5fa  push    rbp
0x14000d5fb  push    rsi
0x14000d5fc  push    rdi
0x14000d5fd  push    r14
0x14000d5ff  sub     rsp, 40h
0x14000d603  mov     esi, r9d
0x14000d606  mov     ebp, r8d
0x14000d609  mov     r14d, edx
0x14000d60c  mov     rdi, rcx
0x14000d60f  call    nfsoncrpc_connect
0x14000d614  test    eax, eax
0x14000d616  jz      short loc_14000D690
0x14000d618  cmp     dword ptr [rdi+18h], 6
0x14000d61c  mov     rbx, [rsp+68h+arg_28]
0x14000d624  jz      short loc_14000D64E
0x14000d626  cmp     dword ptr [rdi+18h], 11h
0x14000d62a  jnz     short loc_14000D672
0x14000d62c  mov     eax, [rsp+68h+arg_20]
0x14000d633  mov     r9, rbx
0x14000d636  mov     dword ptr [rsp+68h+var_40], eax
0x14000d63a  mov     r8d, ebp
0x14000d63d  mov     edx, r14d
0x14000d640  mov     dword ptr [rsp+68h+var_48], esi
0x14000d644  mov     rcx, rdi
0x14000d647  call    nfsoncrpc_clntudp_create
0x14000d64c  jmp     short loc_14000D66A
0x14000d64e  mov     eax, [rsp+68h+arg_20]
0x14000d655  mov     r9d, esi
0x14000d658  mov     r8d, ebp
0x14000d65b  mov     dword ptr [rsp+68h+var_48], eax
0x14000d65f  mov     edx, r14d
0x14000d662  mov     rcx, rdi
0x14000d665  call    nfsoncrpc_clnttcp_create
0x14000d66a  mov     rsi, rax
0x14000d66d  test    rax, rax
0x14000d670  jnz     short loc_14000D6A7
0x14000d672  mov     rcx, [rdi+0B8h]; s
0x14000d679  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000d67d  jz      short loc_14000D690
0x14000d67f  call    cs:__imp_closesocket
0x14000d685  mov     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFFFh
0x14000d690  mov     dword ptr [rdi+0B0h], 3
0x14000d69a  xor     eax, eax
0x14000d69c  add     rsp, 40h
0x14000d6a0  pop     r14
0x14000d6a2  pop     rdi
0x14000d6a3  pop     rsi
0x14000d6a4  pop     rbp
0x14000d6a5  pop     rbx
0x14000d6a6  retn
0x14000d6a7  mov     rax, [rsi+8]
0x14000d6ab  lea     r8, xdr_void
0x14000d6b2  mov     [rsp+68h+var_38], rbx
0x14000d6b7  xor     r9d, r9d
0x14000d6ba  mov     [rsp+68h+var_40], 0
0x14000d6c3  xor     edx, edx
0x14000d6c5  mov     rcx, rsi
0x14000d6c8  mov     [rsp+68h+var_48], r8
0x14000d6cd  mov     rax, [rax]
0x14000d6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d6d5  test    eax, eax
0x14000d6d7  jz      short loc_14000D704
0x14000d6d9  sub     eax, 6
0x14000d6dc  jz      short loc_14000D704
0x14000d6de  sub     eax, 1
0x14000d6e1  jz      short loc_14000D704
0x14000d6e3  sub     eax, 2
0x14000d6e6  jz      short loc_14000D704
0x14000d6e8  sub     eax, 1
0x14000d6eb  jz      short loc_14000D704
0x14000d6ed  cmp     eax, 1
0x14000d6f0  jz      short loc_14000D704
0x14000d6f2  mov     rax, [rsi+8]
0x14000d6f6  mov     rcx, rsi
0x14000d6f9  mov     rax, [rax+20h]
0x14000d6fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d702  jmp     short loc_14000D690
0x14000d704  mov     rax, rsi
0x14000d707  jmp     short loc_14000D69C
```
