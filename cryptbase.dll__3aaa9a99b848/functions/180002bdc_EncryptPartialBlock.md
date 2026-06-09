# EncryptPartialBlock

- ea: `0x180002bdc`
- end: `0x180002c89`
- name: `EncryptPartialBlock`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002c90`

## callees

- `0x180002350`
- `0x180002aa8`
- `0x180002bdc`
- `0x180003b11`
- `0x180003b50`

## pseudocode

```c
__int64 __fastcall EncryptPartialBlock(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 *v5; // rcx
  _BYTE *v8; // rdx
  char *v9; // r8
  unsigned int v10; // r10d
  __int64 v12; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v13[32]; // [rsp+28h] [rbp-20h] BYREF

  v12 = 0;
  v5 = &v12;
  if ( a4 )
  {
    v8 = *(_BYTE **)(a1 + 16);
    do
    {
      *(_BYTE *)v5 = *v8;
      v5 = (__int64 *)((char *)v5 + 1);
      *(_QWORD *)(a1 + 16) = ++v8;
      --a4;
    }
    while ( a4 );
  }
  v9 = (char *)(v13 - (_BYTE *)v5);
  if ( v5 > (__int64 *)v13 )
    v9 = 0;
  if ( v9 )
    memset_0(v5, 0, (size_t)v9);
  SystemFunction001((__int64)&v12, *(_BYTE **)(a2 + 16), *(_QWORD *)(a3 + 16));
  *(_QWORD *)(a1 + 16) += 8LL;
  *(_QWORD *)(a3 + 16) += 8LL;
  AdvanceDataKey(a2);
  return v10;
}

```

## disassembly

```asm
0x180002bdc  push    rbx
0x180002bde  push    rsi
0x180002bdf  push    rdi
0x180002be0  sub     rsp, 30h
0x180002be4  mov     rax, cs:__security_cookie
0x180002beb  xor     rax, rsp
0x180002bee  mov     qword ptr [rsp+48h+var_20], rax
0x180002bf3  mov     [rsp+48h+var_28], 0
0x180002bfc  mov     rbx, rcx
0x180002bff  lea     rcx, [rsp+48h+var_28]
0x180002c04  mov     rdi, r8
0x180002c07  mov     rsi, rdx
0x180002c0a  test    r9d, r9d
0x180002c0d  jz      short loc_180002C27
0x180002c0f  mov     rdx, [rbx+10h]
0x180002c13  mov     al, [rdx]
0x180002c15  mov     [rcx], al
0x180002c17  inc     rcx; void *
0x180002c1a  inc     rdx
0x180002c1d  mov     [rbx+10h], rdx
0x180002c21  add     r9d, 0FFFFFFFFh
0x180002c25  jnz     short loc_180002C13
0x180002c27  xor     eax, eax
0x180002c29  lea     r8, [rsp+48h+var_20]
0x180002c2e  sub     r8, rcx
0x180002c31  lea     rdx, [rsp+48h+var_20]
0x180002c36  cmp     rcx, rdx
0x180002c39  cmova   r8, rax; Size
0x180002c3d  test    r8, r8
0x180002c40  jz      short loc_180002C49
0x180002c42  xor     edx, edx; Val
0x180002c44  call    memset_0
0x180002c49  mov     r8, [rdi+10h]
0x180002c4d  lea     rcx, [rsp+48h+var_28]
0x180002c52  mov     rdx, [rsi+10h]
0x180002c56  call    SystemFunction001
0x180002c5b  add     qword ptr [rbx+10h], 8
0x180002c60  mov     rcx, rsi
0x180002c63  add     qword ptr [rdi+10h], 8
0x180002c68  mov     r10d, eax
0x180002c6b  call    AdvanceDataKey
0x180002c70  mov     eax, r10d
0x180002c73  mov     rcx, qword ptr [rsp+48h+var_20]
0x180002c78  xor     rcx, rsp; StackCookie
0x180002c7b  call    __security_check_cookie
0x180002c80  add     rsp, 30h
0x180002c84  pop     rdi
0x180002c85  pop     rsi
0x180002c86  pop     rbx
0x180002c87  retn
```
