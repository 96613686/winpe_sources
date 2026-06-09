# W3_REQUEST::GetChannelBindingToken(uchar * *,ulong *)

- ea: `0x18001895c`
- end: `0x180018ac8`
- name: `?GetChannelBindingToken@W3_REQUEST@@QEAAJPEAPEAEPEAK@Z`
- size: `364`
- prototype: `__int64 __fastcall(W3_REQUEST *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022060`

## callees

- `0x18001895c`
- `0x180038010`

## import_xrefs

- `w3dt!UlAtqReceiveChannelBindingToken` at `0x1800189fe`
- `w3dt!UlAtqReceiveChannelBindingToken` at `0x180018aa9`
- `w3dt!UlAtqReceiveChannelBindingToken` at `0x1800189fe`
- `w3dt!UlAtqReceiveChannelBindingToken` at `0x180018aa9`

## pseudocode

```c
__int64 __fastcall W3_REQUEST::GetChannelBindingToken(W3_REQUEST *this, unsigned __int8 **a2, unsigned int *a3)
{
  __int64 v5; // rcx
  unsigned int i; // r9d
  _QWORD *v8; // rcx
  void *v9; // rsi
  struct _HTTP_REQUEST_CHANNEL_BIND_STATUS *v10; // rax
  struct _HTTP_REQUEST_CHANNEL_BIND_STATUS *v11; // rbx
  int v12; // ecx
  struct _HTTP_REQUEST_CHANNEL_BIND_STATUS *v13; // rax
  __int64 v15; // rdx
  unsigned int v16; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  *a3 = 0;
  v5 = *((_QWORD *)this + 5);
  v16 = 0;
  if ( !*(_QWORD *)(v5 + 840) )
    return 0;
  for ( i = 0; i < *(unsigned __int16 *)(v5 + 848); ++i )
  {
    if ( *(_DWORD *)(*(_QWORD *)(v5 + 856) + 16LL * i) == 1 )
    {
      _mm_lfence();
      v15 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 856LL) + 16LL * i + 8);
      *a2 = *(unsigned __int8 **)(v15 + 8);
      *a3 = *(_DWORD *)(v15 + 16);
      return 0;
    }
  }
  v8 = (_QWORD *)*((_QWORD *)this + 14);
  v9 = *(void **)(v8[49] + 9440LL);
  if ( !v9 )
    return 0;
  v10 = (struct _HTTP_REQUEST_CHANNEL_BIND_STATUS *)(*(__int64 (__fastcall **)(_QWORD *, __int64))(*v8 + 144LL))(
                                                      v8,
                                                      224);
  v11 = v10;
  if ( !v10 )
    return 2147942408LL;
  v16 = 224;
  v12 = UlAtqReceiveChannelBindingToken(v9, v10, &v16);
  if ( v12 == -2147024662 )
  {
    v13 = (struct _HTTP_REQUEST_CHANNEL_BIND_STATUS *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 14)
                                                                                                + 144LL))(
                                                        *((_QWORD *)this + 14),
                                                        v16);
    v11 = v13;
    if ( !v13 )
      return 2147942408LL;
    v12 = UlAtqReceiveChannelBindingToken(v9, v13, &v16);
  }
  if ( v12 >= 0 )
  {
    *a2 = v11->ChannelToken;
    *a3 = v11->ChannelTokenSize;
  }
  else if ( v12 == -2147023728 )
  {
    return 0;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001895c  mov     [rsp+arg_8], rbx
0x180018961  mov     [rsp+arg_10], rsi
0x180018966  push    rdi
0x180018967  push    r14
0x180018969  push    r15
0x18001896b  sub     rsp, 20h
0x18001896f  mov     qword ptr [rdx], 0
0x180018976  mov     rdi, rcx
0x180018979  mov     dword ptr [r8], 0
0x180018980  mov     r14, r8
0x180018983  mov     rcx, [rcx+28h]
0x180018987  mov     r15, rdx
0x18001898a  mov     [rsp+38h+arg_0], 0
0x180018992  cmp     qword ptr [rcx+348h], 0
0x18001899a  jz      loc_180018A9A
0x1800189a0  movzx   r8d, word ptr [rcx+350h]
0x1800189a8  xor     r9d, r9d
0x1800189ab  cmp     r9d, r8d
0x1800189ae  jb      loc_180018A5F
0x1800189b4  mov     rcx, [rdi+70h]
0x1800189b8  mov     rax, [rcx+188h]
0x1800189bf  mov     rsi, [rax+24E0h]
0x1800189c6  test    rsi, rsi
0x1800189c9  jz      loc_180018A9A
0x1800189cf  mov     rax, [rcx]
0x1800189d2  mov     edx, 0E0h
0x1800189d7  mov     rax, [rax+90h]
0x1800189de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189e3  mov     rbx, rax
0x1800189e6  test    rax, rax
0x1800189e9  jz      short loc_180018A32
0x1800189eb  lea     r8, [rsp+38h+arg_0]
0x1800189f0  mov     [rsp+38h+arg_0], 0E0h
0x1800189f8  mov     rdx, rax
0x1800189fb  mov     rcx, rsi
0x1800189fe  call    cs:__imp_?UlAtqReceiveChannelBindingToken@@YAJPEAXPEAU_HTTP_REQUEST_CHANNEL_BIND_STATUS@@PEAK@Z; UlAtqReceiveChannelBindingToken(void *,_HTTP_REQUEST_CHANNEL_BIND_STATUS *,ulong *)
0x180018a05  nop     dword ptr [rax+rax+00h]
0x180018a0a  mov     ecx, eax
0x180018a0c  cmp     eax, 800700EAh
0x180018a11  jnz     short loc_180018A4C
0x180018a13  mov     rcx, [rdi+70h]
0x180018a17  mov     edx, [rsp+38h+arg_0]
0x180018a1b  mov     rax, [rcx]
0x180018a1e  mov     rax, [rax+90h]
0x180018a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a2a  mov     rbx, rax
0x180018a2d  test    rax, rax
0x180018a30  jnz     short loc_180018A9E
0x180018a32  mov     eax, 80070008h
0x180018a37  mov     rbx, [rsp+38h+arg_8]
0x180018a3c  mov     rsi, [rsp+38h+arg_10]
0x180018a41  add     rsp, 20h
0x180018a45  pop     r15
0x180018a47  pop     r14
0x180018a49  pop     rdi
0x180018a4a  retn
0x180018a4c  test    ecx, ecx
0x180018a4e  jns     short loc_180018AB9
0x180018a50  xor     eax, eax
0x180018a52  cmp     ecx, 80070490h
0x180018a58  cmovz   ecx, eax
0x180018a5b  mov     eax, ecx
0x180018a5d  jmp     short loc_180018A37
0x180018a5f  mov     rax, [rcx+358h]
0x180018a66  mov     edx, r9d
0x180018a69  add     rdx, rdx
0x180018a6c  cmp     dword ptr [rax+rdx*8], 1
0x180018a70  jz      short loc_180018A7A
0x180018a72  inc     r9d
0x180018a75  jmp     loc_1800189AB
0x180018a7a  lfence
0x180018a7d  mov     rax, [rdi+28h]
0x180018a81  mov     rcx, [rax+358h]
0x180018a88  mov     rdx, [rcx+rdx*8+8]
0x180018a8d  mov     rax, [rdx+8]
0x180018a91  mov     [r15], rax
0x180018a94  mov     eax, [rdx+10h]
0x180018a97  mov     [r14], eax
0x180018a9a  xor     eax, eax
0x180018a9c  jmp     short loc_180018A37
0x180018a9e  lea     r8, [rsp+38h+arg_0]
0x180018aa3  mov     rdx, rax
0x180018aa6  mov     rcx, rsi
0x180018aa9  call    cs:__imp_?UlAtqReceiveChannelBindingToken@@YAJPEAXPEAU_HTTP_REQUEST_CHANNEL_BIND_STATUS@@PEAK@Z; UlAtqReceiveChannelBindingToken(void *,_HTTP_REQUEST_CHANNEL_BIND_STATUS *,ulong *)
0x180018ab0  nop     dword ptr [rax+rax+00h]
0x180018ab5  mov     ecx, eax
0x180018ab7  jmp     short loc_180018A4C
0x180018ab9  mov     rax, [rbx+8]
0x180018abd  mov     [r15], rax
0x180018ac0  mov     eax, [rbx+10h]
0x180018ac3  mov     [r14], eax
0x180018ac6  jmp     short loc_180018A5B
```
