# setVarValue

- ea: `0x14000e1f4`
- end: `0x14000e368`
- name: `setVarValue`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000dcf8`
- `0x14000e028`

## callees

- `0x140008620`
- `0x14000ce88`
- `0x14000e1f4`
- `0x14000e412`
- `0x14000e450`
- `0x14000f010`

## import_xrefs

- `msvcrt!free` at `0x14000e342`
- `msvcrt!free` at `0x14000e342`
- `msvcrt!_strdup` at `0x14000e2dc`
- `msvcrt!_strdup` at `0x14000e2dc`

## string_xrefs

- `0x14000e2f5`: `attempting to set variable: %1`

## pseudocode

```c
__int64 __fastcall setVarValue(const char **a1, char *a2, __int64 a3)
{
  unsigned __int64 v6; // rax
  __int64 v7; // rdx
  const char *v9; // rax
  __int64 v10; // rax
  char *p_Source; // rcx
  char *v12; // rax
  char *v13; // rdi
  char *v14; // rax
  const char *v15; // [rsp+20h] [rbp-348h]
  char Source; // [rsp+40h] [rbp-328h] BYREF
  char v17[255]; // [rsp+41h] [rbp-327h] BYREF
  char v18[512]; // [rsp+140h] [rbp-228h] BYREF

  Source = 0;
  memset_0(v17, 0, sizeof(v17));
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 256;
  if ( v6 >= 0x100 )
  {
    ErrSet(a3, "Variable value is longer than maximum (%1 chars): %2", "%d%s", 256, *a1);
    return 0;
  }
  v9 = a1[3];
  if ( v9 )
  {
    if ( !((unsigned int (__fastcall *)(const char *, const char *, char *, char *, int, __int64))v9)(
            a1[6],
            *a1,
            a2,
            &Source,
            256,
            a3) )
      return 0;
  }
  else
  {
    v10 = 2147483646;
    p_Source = &Source;
    do
    {
      if ( !v10 )
        break;
      if ( !*a2 )
        break;
      *p_Source++ = *a2++;
      --v10;
      --v7;
    }
    while ( v7 );
    v12 = p_Source - 1;
    if ( v7 )
      v12 = p_Source;
    *v12 = 0;
  }
  v13 = (char *)a1[1];
  v14 = _strdup(&Source);
  a1[1] = v14;
  if ( !v14 )
  {
    v15 = *a1;
    a1[1] = v13;
    MsgSet(v18, 512, "attempting to set variable: %1", "%s", v15);
    ErrSet(a3, "Out of memory: %1", "%s", v18);
    return 0;
  }
  if ( v13 )
    free(v13);
  return 1;
}

```

## disassembly

```asm
0x14000e1f4  push    rbx
0x14000e1f6  push    rsi
0x14000e1f7  push    rdi
0x14000e1f8  sub     rsp, 350h
0x14000e1ff  mov     rax, cs:__security_cookie
0x14000e206  xor     rax, rsp
0x14000e209  mov     [rsp+368h+var_28], rax
0x14000e211  mov     rsi, r8
0x14000e214  mov     [rsp+368h+Source], 0
0x14000e219  mov     rdi, rdx
0x14000e21c  mov     rbx, rcx
0x14000e21f  xor     edx, edx; Val
0x14000e221  lea     rcx, [rsp+368h+var_327]; void *
0x14000e226  mov     r8d, 0FFh; Size
0x14000e22c  call    memset_0
0x14000e231  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e235  inc     rax
0x14000e238  cmp     byte ptr [rdi+rax], 0
0x14000e23c  jnz     short loc_14000E235
0x14000e23e  mov     edx, 100h
0x14000e243  cmp     rax, rdx
0x14000e246  jb      short loc_14000E270
0x14000e248  mov     rax, [rbx]
0x14000e24b  lea     r8, aDS; "%d%s"
0x14000e252  mov     r9d, edx
0x14000e255  mov     [rsp+368h+var_348], rax
0x14000e25a  lea     rdx, aVariableValueI; "Variable value is longer than maximum ("...
0x14000e261  mov     rcx, rsi
0x14000e264  call    ErrSet
0x14000e269  xor     eax, eax
0x14000e26b  jmp     loc_14000E34D
0x14000e270  mov     rax, [rbx+18h]
0x14000e274  test    rax, rax
0x14000e277  jnz     short loc_14000E2B2
0x14000e279  mov     eax, 7FFFFFFEh
0x14000e27e  lea     rcx, [rsp+368h+Source]
0x14000e283  test    rax, rax
0x14000e286  jz      short loc_14000E2A2
0x14000e288  mov     r8b, [rdi]
0x14000e28b  test    r8b, r8b
0x14000e28e  jz      short loc_14000E2A2
0x14000e290  mov     [rcx], r8b
0x14000e293  inc     rdi
0x14000e296  inc     rcx
0x14000e299  dec     rax
0x14000e29c  sub     rdx, 1
0x14000e2a0  jnz     short loc_14000E283
0x14000e2a2  test    rdx, rdx
0x14000e2a5  lea     rax, [rcx-1]
0x14000e2a9  cmovnz  rax, rcx
0x14000e2ad  mov     byte ptr [rax], 0
0x14000e2b0  jmp     short loc_14000E2D3
0x14000e2b2  mov     rcx, [rbx+30h]
0x14000e2b6  lea     r9, [rsp+368h+Source]
0x14000e2bb  mov     [rsp+368h+var_340], rsi
0x14000e2c0  mov     r8, rdi
0x14000e2c3  mov     dword ptr [rsp+368h+var_348], edx
0x14000e2c7  mov     rdx, [rbx]
0x14000e2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e2cf  test    eax, eax
0x14000e2d1  jz      short loc_14000E269
0x14000e2d3  mov     rdi, [rbx+8]
0x14000e2d7  lea     rcx, [rsp+368h+Source]; Source
0x14000e2dc  call    cs:__imp__strdup
0x14000e2e2  mov     [rbx+8], rax
0x14000e2e6  test    rax, rax
0x14000e2e9  jnz     short loc_14000E33A
0x14000e2eb  mov     rax, [rbx]
0x14000e2ee  lea     r9, aS_4; "%s"
0x14000e2f5  lea     r8, aAttemptingToSe; "attempting to set variable: %1"
0x14000e2fc  mov     [rsp+368h+var_348], rax
0x14000e301  mov     edx, 200h
0x14000e306  mov     [rbx+8], rdi
0x14000e30a  lea     rcx, [rsp+368h+var_228]
0x14000e312  call    MsgSet
0x14000e317  lea     r9, [rsp+368h+var_228]
0x14000e31f  mov     rcx, rsi
0x14000e322  lea     r8, aS_4; "%s"
0x14000e329  lea     rdx, aOutOfMemory1_0; "Out of memory: %1"
0x14000e330  call    ErrSet
0x14000e335  jmp     loc_14000E269
0x14000e33a  test    rdi, rdi
0x14000e33d  jz      short loc_14000E348
0x14000e33f  mov     rcx, rdi; Block
0x14000e342  call    cs:__imp_free
0x14000e348  mov     eax, 1
0x14000e34d  mov     rcx, [rsp+368h+var_28]
0x14000e355  xor     rcx, rsp; StackCookie
0x14000e358  call    __security_check_cookie
0x14000e35d  add     rsp, 350h
0x14000e364  pop     rdi
0x14000e365  pop     rsi
0x14000e366  pop     rbx
0x14000e367  retn
```
