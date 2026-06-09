# DhcpFreeCachedParamsData

- ea: `0x180001b50`
- end: `0x180001bc3`
- name: `DhcpFreeCachedParamsData`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001b50`
- `0x180002160`

## pseudocode

```c
__int64 __fastcall DhcpFreeCachedParamsData(int *a1)
{
  __int64 v1; // rbx
  unsigned int v2; // ebp
  unsigned int v3; // esi
  __int64 v4; // rdi
  __int64 result; // rax

  v1 = *((_QWORD *)a1 + 1);
  if ( v1 )
  {
    v2 = *a1;
    if ( *a1 )
    {
      v3 = 0;
      do
      {
        v4 = 32LL * v3;
        result = DhcpFree(v4 + v1 + 16);
        ++v3;
        *(_DWORD *)(v4 + v1 + 24) = 0;
      }
      while ( v3 < v2 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001b50  push    rbx
0x180001b52  sub     rsp, 20h
0x180001b56  mov     rbx, [rcx+8]
0x180001b5a  test    rbx, rbx
0x180001b5d  jnz     short loc_180001B65
0x180001b5f  add     rsp, 20h
0x180001b63  pop     rbx
0x180001b64  retn
0x180001b65  mov     [rsp+28h+arg_0], rbp
0x180001b6a  mov     ebp, [rcx]
0x180001b6c  test    ebp, ebp
0x180001b6e  jz      short loc_180001BBC
0x180001b70  mov     [rsp+28h+arg_8], rsi
0x180001b75  mov     [rsp+28h+arg_10], rdi
0x180001b7a  mov     [rsp+28h+arg_18], r14
0x180001b7f  xor     r14d, r14d
0x180001b82  mov     esi, r14d
0x180001b85  nop     word ptr [rax+rax+00000000h]
0x180001b90  mov     edi, esi
0x180001b92  lea     rcx, [rbx+10h]
0x180001b96  shl     rdi, 5
0x180001b9a  add     rcx, rdi
0x180001b9d  call    DhcpFree
0x180001ba2  inc     esi
0x180001ba4  mov     [rdi+rbx+18h], r14d
0x180001ba9  cmp     esi, ebp
0x180001bab  jb      short loc_180001B90
0x180001bad  mov     r14, [rsp+28h+arg_18]
0x180001bb2  mov     rdi, [rsp+28h+arg_10]
0x180001bb7  mov     rsi, [rsp+28h+arg_8]
0x180001bbc  mov     rbp, [rsp+28h+arg_0]
0x180001bc1  jmp     short loc_180001B5F
```
