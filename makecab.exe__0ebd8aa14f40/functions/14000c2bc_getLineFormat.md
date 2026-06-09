# getLineFormat

- ea: `0x14000c2bc`
- end: `0x14000c39f`
- name: `getLineFormat`
- size: `227`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c3a8`
- `0x14000c488`
- `0x14000c560`

## callees

- `0x14000c2bc`
- `0x14000d70c`
- `0x14000dfd8`
- `0x14000e412`
- `0x14000e450`

## pseudocode

```c
const char *__fastcall getLineFormat(__int64 a1, __int64 a2, char *a3, unsigned int a4)
{
  const char *v8; // rbp
  __int64 v9; // rax
  __int64 v10; // rcx
  _BYTE v12[512]; // [rsp+30h] [rbp-288h] BYREF
  int v13; // [rsp+230h] [rbp-88h]
  int v14; // [rsp+250h] [rbp-68h]
  __int64 v15; // [rsp+258h] [rbp-60h]
  char pszDest[32]; // [rsp+260h] [rbp-58h] BYREF

  memset_0(v12, 0, 0x230u);
  v8 = DirectoryName;
  if ( (unsigned int)nameFromTemplate(pszDest, 32, a3, a4, DirectoryName, (__int64)v12) )
  {
    v9 = VarFind(*(_QWORD *)(a1 + 16), (__int64)pszDest, (__int64)v12);
    if ( v9 )
      return *(const char **)(v9 + 8);
  }
  v10 = *(_QWORD *)(a1 + 16);
  v13 = 0;
  v12[0] = 0;
  v14 = 0;
  v15 = 0;
  v9 = VarFind(v10, a2, (__int64)v12);
  if ( v9 )
    return *(const char **)(v9 + 8);
  return v8;
}

```

## disassembly

```asm
0x14000c2bc  push    rbx
0x14000c2be  push    rbp
0x14000c2bf  push    rsi
0x14000c2c0  push    rdi
0x14000c2c1  push    r14
0x14000c2c3  sub     rsp, 290h
0x14000c2ca  mov     rax, cs:__security_cookie
0x14000c2d1  xor     rax, rsp
0x14000c2d4  mov     [rsp+2B8h+var_38], rax
0x14000c2dc  mov     rdi, r8
0x14000c2df  mov     r14, rdx
0x14000c2e2  mov     rbx, rcx
0x14000c2e5  xor     edx, edx; Val
0x14000c2e7  mov     r8d, 230h; Size
0x14000c2ed  lea     rcx, [rsp+2B8h+var_288]; void *
0x14000c2f2  mov     esi, r9d
0x14000c2f5  call    memset_0
0x14000c2fa  lea     rax, [rsp+2B8h+var_288]
0x14000c2ff  mov     r9d, esi
0x14000c302  mov     [rsp+2B8h+var_290], rax; __int64
0x14000c307  lea     rbp, DirectoryName
0x14000c30e  mov     r8, rdi
0x14000c311  mov     [rsp+2B8h+var_298], rbp; __int64
0x14000c316  mov     edx, 20h ; ' '
0x14000c31b  lea     rcx, [rsp+2B8h+pszDest]; pszDest
0x14000c323  call    nameFromTemplate
0x14000c328  xor     edi, edi
0x14000c32a  test    eax, eax
0x14000c32c  jz      short loc_14000C349
0x14000c32e  mov     rcx, [rbx+10h]
0x14000c332  lea     r8, [rsp+2B8h+var_288]
0x14000c337  lea     rdx, [rsp+2B8h+pszDest]
0x14000c33f  call    VarFind
0x14000c344  test    rax, rax
0x14000c347  jnz     short loc_14000C37A
0x14000c349  mov     rcx, [rbx+10h]
0x14000c34d  lea     r8, [rsp+2B8h+var_288]
0x14000c352  mov     rdx, r14
0x14000c355  mov     [rsp+2B8h+var_88], edi
0x14000c35c  mov     [rsp+2B8h+var_288], dil
0x14000c361  mov     [rsp+2B8h+var_68], edi
0x14000c368  mov     [rsp+2B8h+var_60], rdi
0x14000c370  call    VarFind
0x14000c375  test    rax, rax
0x14000c378  jz      short loc_14000C37E
0x14000c37a  mov     rbp, [rax+8]
0x14000c37e  mov     rax, rbp
0x14000c381  mov     rcx, [rsp+2B8h+var_38]
0x14000c389  xor     rcx, rsp; StackCookie
0x14000c38c  call    __security_check_cookie
0x14000c391  add     rsp, 290h
0x14000c398  pop     r14
0x14000c39a  pop     rdi
0x14000c39b  pop     rsi
0x14000c39c  pop     rbp
0x14000c39d  pop     rbx
0x14000c39e  retn
```
