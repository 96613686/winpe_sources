# DecryptPartialBlock

- ea: `0x180002b3c`
- end: `0x180002bd4`
- name: `DecryptPartialBlock`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001820`

## callees

- `0x180001a50`
- `0x180002aa8`
- `0x180002b3c`
- `0x180003b50`

## pseudocode

```c
__int64 __fastcall DecryptPartialBlock(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 result; // rax
  char *v9; // r8
  _QWORD *i; // rdx
  char v11; // al
  unsigned int v12; // r10d
  __int64 v13; // [rsp+20h] [rbp-28h] BYREF

  v13 = 0;
  result = SystemFunction002(*(_QWORD *)(a1 + 16), *(_BYTE **)(a2 + 16), (__int64)&v13);
  if ( (int)result >= 0 )
  {
    v9 = (char *)&v13;
    for ( i = (_QWORD *)(a3 + 16); a4; --a4 )
    {
      v11 = *v9++;
      *(_BYTE *)(*i)++ = v11;
    }
    *i += 8LL;
    *(_QWORD *)(a1 + 16) += 8LL;
    AdvanceDataKey((unsigned int *)a2);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180002b3c  mov     [rsp+arg_18], rbx
0x180002b41  push    rbp
0x180002b42  push    rsi
0x180002b43  push    rdi
0x180002b44  sub     rsp, 30h
0x180002b48  mov     rax, cs:__security_cookie
0x180002b4f  xor     rax, rsp
0x180002b52  mov     [rsp+48h+var_20], rax
0x180002b57  mov     rsi, r8
0x180002b5a  mov     [rsp+48h+var_28], 0
0x180002b63  mov     rbp, rdx
0x180002b66  lea     r8, [rsp+48h+var_28]
0x180002b6b  mov     rdx, [rdx+10h]
0x180002b6f  mov     rbx, rcx
0x180002b72  mov     rcx, [rcx+10h]
0x180002b76  mov     edi, r9d
0x180002b79  call    SystemFunction002
0x180002b7e  mov     r10d, eax
0x180002b81  test    eax, eax
0x180002b83  js      short loc_180002BB9
0x180002b85  lea     r8, [rsp+48h+var_28]
0x180002b8a  lea     rdx, [rsi+10h]
0x180002b8e  test    edi, edi
0x180002b90  jz      short loc_180002BA5
0x180002b92  mov     rcx, [rdx]
0x180002b95  mov     al, [r8]
0x180002b98  inc     r8
0x180002b9b  mov     [rcx], al
0x180002b9d  inc     qword ptr [rdx]
0x180002ba0  add     edi, 0FFFFFFFFh
0x180002ba3  jnz     short loc_180002B92
0x180002ba5  add     qword ptr [rdx], 8
0x180002ba9  mov     rcx, rbp
0x180002bac  add     qword ptr [rbx+10h], 8
0x180002bb1  call    AdvanceDataKey
0x180002bb6  mov     eax, r10d
0x180002bb9  mov     rcx, [rsp+48h+var_20]
0x180002bbe  xor     rcx, rsp; StackCookie
0x180002bc1  call    __security_check_cookie
0x180002bc6  mov     rbx, [rsp+48h+arg_18]
0x180002bcb  add     rsp, 30h
0x180002bcf  pop     rdi
0x180002bd0  pop     rsi
0x180002bd1  pop     rbp
0x180002bd2  retn
```
