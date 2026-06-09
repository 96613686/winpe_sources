# marshal_new_auth

- ea: `0x14000b394`
- end: `0x14000b456`
- name: `marshal_new_auth`
- size: `194`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14000add4`
- `0x14000b170`
- `0x14000b2a0`

## callees

- `0x14000b394`
- `0x14000c5f4`
- `0x14001830e`
- `0x140019010`

## import_xrefs

- `msvcrt!perror` at `0x14000b423`
- `msvcrt!perror` at `0x14000b423`

## pseudocode

```c
__int64 __fastcall marshal_new_auth(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // r8
  int v4; // r9d
  __int64 v5; // r8
  int v6; // r9d
  __int64 (__fastcall *v7)(); // rax
  _BYTE v9[4]; // [rsp+20h] [rbp-60h] BYREF
  int v10; // [rsp+24h] [rbp-5Ch]
  __int64 (__fastcall **v11)(); // [rsp+28h] [rbp-58h]
  __int64 v12; // [rsp+38h] [rbp-48h]
  __int64 v13; // [rsp+40h] [rbp-40h]
  int v14; // [rsp+48h] [rbp-38h]

  v10 = 0;
  memset_0(v9, 0, 0x54u);
  v2 = *(_QWORD *)(a1 + 64);
  v11 = off_140020030;
  v14 = 400;
  v13 = v2 + 52;
  v12 = v2 + 52;
  if ( (unsigned int)xdr_opaque_auth((__int64)v9, a1, v3, v4)
    && (unsigned int)xdr_opaque_auth((__int64)v9, a1 + 24, v5, v6) )
  {
    *(_DWORD *)(v2 + 452) = ((__int64 (__fastcall *)(_BYTE *))v11[4])(v9);
  }
  else
  {
    perror("auth_none.c - Fatal marshalling problem");
  }
  v7 = v11[7];
  if ( v7 )
    ((void (__fastcall *)(_BYTE *))v7)(v9);
  return 0;
}

```

## disassembly

```asm
0x14000b394  mov     [rsp-8+arg_0], rbx
0x14000b399  mov     [rsp-8+arg_8], rdi
0x14000b39e  push    rbp
0x14000b39f  mov     rbp, rsp
0x14000b3a2  sub     rsp, 80h
0x14000b3a9  xor     eax, eax
0x14000b3ab  mov     rbx, rcx
0x14000b3ae  xor     edx, edx; Val
0x14000b3b0  mov     [rbp+var_5C], eax
0x14000b3b3  lea     rcx, [rbp+var_60]; void *
0x14000b3b7  lea     r8d, [rax+54h]; Size
0x14000b3bb  call    memset_0
0x14000b3c0  mov     rdi, [rbx+40h]
0x14000b3c4  lea     rcx, off_140020030
0x14000b3cb  mov     [rbp+var_58], rcx
0x14000b3cf  mov     rdx, rbx
0x14000b3d2  lea     rcx, [rbp+var_60]
0x14000b3d6  mov     [rbp+var_38], 190h
0x14000b3dd  lea     rax, [rdi+34h]
0x14000b3e1  mov     [rbp+var_40], rax
0x14000b3e5  mov     [rbp+var_48], rax
0x14000b3e9  call    xdr_opaque_auth
0x14000b3ee  test    eax, eax
0x14000b3f0  jz      short loc_14000B41C
0x14000b3f2  lea     rdx, [rbx+18h]
0x14000b3f6  lea     rcx, [rbp+var_60]
0x14000b3fa  call    xdr_opaque_auth
0x14000b3ff  test    eax, eax
0x14000b401  jz      short loc_14000B41C
0x14000b403  mov     rax, [rbp+var_58]
0x14000b407  lea     rcx, [rbp+var_60]
0x14000b40b  mov     rax, [rax+20h]
0x14000b40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b414  mov     [rdi+1C4h], eax
0x14000b41a  jmp     short loc_14000B429
0x14000b41c  lea     rcx, ErrMsg; "auth_none.c - Fatal marshalling problem"
0x14000b423  call    cs:__imp_perror
0x14000b429  mov     rax, [rbp+var_58]
0x14000b42d  mov     rax, [rax+38h]
0x14000b431  test    rax, rax
0x14000b434  jz      short loc_14000B43F
0x14000b436  lea     rcx, [rbp+var_60]
0x14000b43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b43f  lea     r11, [rsp+80h+var_s0]
0x14000b447  xor     eax, eax
0x14000b449  mov     rbx, [r11+10h]
0x14000b44d  mov     rdi, [r11+18h]
0x14000b451  mov     rsp, r11
0x14000b454  pop     rbp
0x14000b455  retn
```
