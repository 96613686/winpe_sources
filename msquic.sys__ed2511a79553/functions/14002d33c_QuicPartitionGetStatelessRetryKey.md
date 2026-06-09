# QuicPartitionGetStatelessRetryKey

- ea: `0x14002d33c`
- end: `0x14002d461`
- name: `QuicPartitionGetStatelessRetryKey`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002d290`
- `0x14002d468`

## callees

- `0x14002d33c`
- `0x140034b30`
- `0x140034c90`
- `0x140034d20`
- `0x14003c8e0`
- `0x14003e928`

## string_xrefs

- `0x14002d3dd`: `Create stateless retry key`

## pseudocode

```c
__int64 __fastcall QuicPartitionGetStatelessRetryKey(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // [rsp+20h] [rbp-60h]
  __int64 v10; // [rsp+48h] [rbp-38h] BYREF
  __int64 v11[4]; // [rsp+50h] [rbp-30h] BYREF

  if ( *(_QWORD *)(a1 + 16 * (a2 & 1) + 72) == a2 )
    return *(_QWORD *)(a1 + 16 * ((a2 & 1) + 4));
  v4 = 0;
  if ( (int)CxPlatKbKdfDerive(&pbSecret, cbSecret, v8, cbSecret, (__int64)v11) < 0 )
    return 0;
  v10 = 0;
  v5 = CxPlatKeyCreate((unsigned int)dword_14005C5F0, v11, &v10);
  if ( v5 >= 0 )
  {
    CxPlatKeyFree(*(_QWORD *)(a1 + 16 * ((a2 & 1) + 4)));
    *(_QWORD *)(a1 + 16 * ((a2 & 1) + 4)) = v10;
    *(_QWORD *)(a1 + 16 * (a2 & 1) + 72) = a2;
    v4 = v10;
  }
  else if ( (Microsoft_QuicEnableBits & 4) != 0 )
  {
    McTemplateU0qs_EtwWriteTransfer(v7, v6, (unsigned int)v5, "Create stateless retry key");
  }
  memset(v11, 0, sizeof(v11));
  return v4;
}

```

## disassembly

```asm
0x14002d33c  mov     [rsp-8+arg_10], rbx
0x14002d341  mov     [rsp-8+arg_18], rdi
0x14002d346  push    rbp
0x14002d347  mov     rbp, rsp
0x14002d34a  sub     rsp, 80h
0x14002d351  mov     rax, cs:__security_cookie
0x14002d358  xor     rax, rsp
0x14002d35b  mov     [rbp+var_10], rax
0x14002d35f  mov     rdi, rcx
0x14002d362  mov     [rbp+var_40], rdx
0x14002d366  mov     rcx, rdx
0x14002d369  and     ecx, 1
0x14002d36c  add     rcx, rcx
0x14002d36f  cmp     [rdi+rcx*8+48h], rdx
0x14002d374  jnz     short loc_14002D389
0x14002d376  and     edx, 1
0x14002d379  add     rdx, 4
0x14002d37d  add     rdx, rdx
0x14002d380  mov     rax, [rdi+rdx*8]
0x14002d384  jmp     loc_14002D43F
0x14002d389  mov     edx, cs:cbSecret; cbSecret
0x14002d38f  lea     rax, [rbp+var_30]
0x14002d393  mov     [rsp+80h+var_50], rax; __int64
0x14002d398  lea     r9, [rbp+var_40]
0x14002d39c  lea     rcx, pbSecret; pbSecret
0x14002d3a3  mov     [rsp+80h+var_58], edx; int
0x14002d3a7  call    CxPlatKbKdfDerive
0x14002d3ac  xor     ebx, ebx
0x14002d3ae  test    eax, eax
0x14002d3b0  jns     short loc_14002D3B9
0x14002d3b2  xor     eax, eax
0x14002d3b4  jmp     loc_14002D43F
0x14002d3b9  mov     ecx, cs:dword_14005C5F0
0x14002d3bf  lea     r8, [rbp+var_38]
0x14002d3c3  lea     rdx, [rbp+var_30]
0x14002d3c7  mov     [rbp+var_38], rbx
0x14002d3cb  call    CxPlatKeyCreate
0x14002d3d0  test    eax, eax
0x14002d3d2  jns     short loc_14002D3EE
0x14002d3d4  test    cs:Microsoft_QuicEnableBits, 4
0x14002d3db  jz      short loc_14002D431
0x14002d3dd  lea     r9, aCreateStateles; "Create stateless retry key"
0x14002d3e4  mov     r8d, eax
0x14002d3e7  call    McTemplateU0qs_EtwWriteTransfer
0x14002d3ec  jmp     short loc_14002D431
0x14002d3ee  mov     rcx, [rbp+var_40]
0x14002d3f2  and     ecx, 1
0x14002d3f5  add     rcx, 4
0x14002d3f9  add     rcx, rcx
0x14002d3fc  mov     rcx, [rdi+rcx*8]
0x14002d400  call    CxPlatKeyFree
0x14002d405  mov     rcx, [rbp+var_40]
0x14002d409  mov     rax, [rbp+var_38]
0x14002d40d  and     ecx, 1
0x14002d410  add     rcx, 4
0x14002d414  add     rcx, rcx
0x14002d417  mov     [rdi+rcx*8], rax
0x14002d41b  mov     rcx, [rbp+var_40]
0x14002d41f  mov     rax, rcx
0x14002d422  and     eax, 1
0x14002d425  add     rax, rax
0x14002d428  mov     [rdi+rax*8+48h], rcx
0x14002d42d  mov     rbx, [rbp+var_38]
0x14002d431  xor     eax, eax
0x14002d433  lea     rdi, [rbp+var_30]
0x14002d437  lea     ecx, [rax+20h]
0x14002d43a  rep stosb
0x14002d43c  mov     rax, rbx
0x14002d43f  mov     rcx, [rbp+var_10]
0x14002d443  xor     rcx, rsp; StackCookie
0x14002d446  call    __security_check_cookie
0x14002d44b  lea     r11, [rsp+80h+var_s0]
0x14002d453  mov     rbx, [r11+20h]
0x14002d457  mov     rdi, [r11+28h]
0x14002d45b  mov     rsp, r11
0x14002d45e  pop     rbp
0x14002d45f  retn
```
