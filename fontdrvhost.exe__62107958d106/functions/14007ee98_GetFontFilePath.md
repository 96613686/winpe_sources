# GetFontFilePath

- ea: `0x14007ee98`
- end: `0x14007ef57`
- name: `GetFontFilePath`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14008066c`
- `0x140081220`

## callees

- `0x140052a14`
- `0x140075de0`
- `0x14007e914`
- `0x14007ee98`
- `0x140092a58`

## pseudocode

```c
_BOOL8 __fastcall GetFontFilePath(void *a1, __int64 a2)
{
  BOOL v3; // ebx
  WCHAR pDest[261]; // [rsp+30h] [rbp-238h] BYREF

  v3 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      pDest[0] = 0;
      if ( EngGetFilePath(a1, (WCHAR (*)[261])pDest) )
      {
        if ( pDest[0] )
          v3 = SplitPath(pDest) == 1;
      }
    }
  }
  if ( v3 )
    WStrCpyExt(a2, pDest, 522);
  return v3;
}

```

## disassembly

```asm
0x14007ee98  mov     [rsp+arg_10], rbx
0x14007ee9d  push    rsi
0x14007ee9e  push    rdi
0x14007ee9f  push    r14
0x14007eea1  sub     rsp, 250h
0x14007eea8  mov     rax, cs:__security_cookie
0x14007eeaf  xor     rax, rsp
0x14007eeb2  mov     [rsp+268h+var_28], rax
0x14007eeba  mov     rsi, rdx
0x14007eebd  mov     [rsp+268h+var_240], rdx
0x14007eec2  xor     r14d, r14d
0x14007eec5  mov     ebx, r14d
0x14007eec8  mov     [rsp+268h+var_244], ebx
0x14007eecc  mov     [rsp+268h+var_248], r14b
0x14007eed1  test    rcx, rcx
0x14007eed4  jz      short loc_14007EF15
0x14007eed6  test    rdx, rdx
0x14007eed9  jz      short loc_14007EF15
0x14007eedb  mov     [rsp+268h+pDest], r14w
0x14007eee1  lea     rdx, [rsp+268h+pDest]; pDest
0x14007eee6  call    EngGetFilePath
0x14007eeeb  lea     edi, [r14+1]
0x14007eeef  cmp     eax, edi
0x14007eef1  jnz     short loc_14007EF1A
0x14007eef3  cmp     [rsp+268h+pDest], r14w
0x14007eef9  jz      short loc_14007EF1A
0x14007eefb  lea     rdx, [rsp+268h+var_248]
0x14007ef00  lea     rcx, [rsp+268h+pDest]; String1
0x14007ef05  call    SplitPath
0x14007ef0a  cmp     eax, edi
0x14007ef0c  cmovz   ebx, edi
0x14007ef0f  mov     [rsp+268h+var_244], ebx
0x14007ef13  jmp     short loc_14007EF1A
0x14007ef15  mov     edi, 1
0x14007ef1a  cmp     ebx, edi
0x14007ef1c  jnz     short loc_14007EF31
0x14007ef1e  mov     r8d, 20Ah
0x14007ef24  lea     rdx, [rsp+268h+pDest]
0x14007ef29  mov     rcx, rsi
0x14007ef2c  call    WStrCpyExt
0x14007ef31  mov     eax, ebx
0x14007ef33  mov     rcx, [rsp+268h+var_28]
0x14007ef3b  xor     rcx, rsp; StackCookie
0x14007ef3e  call    __security_check_cookie
0x14007ef43  mov     rbx, [rsp+268h+arg_10]
0x14007ef4b  add     rsp, 250h
0x14007ef52  pop     r14
0x14007ef54  pop     rdi
0x14007ef55  pop     rsi
0x14007ef56  retn
0x1400978d3  push    rbp
0x1400978d5  sub     rsp, 20h
0x1400978d9  mov     rbp, rdx
0x1400978dc  cmp     dword ptr [rbp+24h], 1
0x1400978e0  jnz     short loc_1400978F6
0x1400978e2  mov     r8d, 20Ah
0x1400978e8  lea     rdx, [rbp+30h]
0x1400978ec  mov     rcx, [rbp+28h]
0x1400978f0  call    WStrCpyExt
0x1400978f5  nop
0x1400978f6  add     rsp, 20h
0x1400978fa  pop     rbp
0x1400978fb  retn
```
