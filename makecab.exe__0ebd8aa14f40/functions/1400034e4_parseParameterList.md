# parseParameterList

- ea: `0x1400034e4`
- end: `0x140003741`
- name: `parseParameterList`
- size: `605`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140003310`
- `0x140003748`

## callees

- `0x14000313c`
- `0x1400034e4`
- `0x140008620`
- `0x14000a29c`
- `0x14000a4f8`
- `0x14000e406`
- `0x14000e41e`
- `0x14000e450`

## import_xrefs

- `msvcrt!strspn` at `0x1400035f9`
- `msvcrt!strspn` at `0x140003637`
- `msvcrt!strspn` at `0x1400035f9`
- `msvcrt!strspn` at `0x140003637`
- `msvcrt!strpbrk` at `0x14000355e`
- `msvcrt!strpbrk` at `0x14000355e`
- `msvcrt!malloc` at `0x140003686`
- `msvcrt!malloc` at `0x140003686`
- `msvcrt!free` at `0x1400036e1`
- `msvcrt!free` at `0x140003718`
- `msvcrt!free` at `0x1400036e1`
- `msvcrt!free` at `0x140003718`
- `msvcrt!_strdup` at `0x1400036b7`
- `msvcrt!_strdup` at `0x1400036b7`

## pseudocode

```c
const char *__fastcall parseParameterList(char **a1, __int64 a2, const char *a3, _DWORD *a4)
{
  char *v8; // rax
  const char *v9; // rbx
  char *v11; // rax
  const char *v12; // rbp
  __int64 v13; // rax
  signed __int64 v14; // rsi
  size_t v15; // rax
  const char *v16; // rbx
  const char *QuotedString; // rsi
  void **v18; // rbx
  char *v19; // rax
  char v20[32]; // [rsp+30h] [rbp-458h] BYREF
  char Source[1024]; // [rsp+50h] [rbp-438h] BYREF

  if ( !*a1 )
  {
    v8 = (char *)GLCreateList(0, (__int64)DestroyFileParm, "file parameter", (__int64)a3);
    *a1 = v8;
    if ( !v8 )
      return 0;
  }
  v9 = (const char *)(a2 + 1);
  if ( !*v9 )
  {
    ErrSet((__int64)a3, (int)"Missing parameter name", a3);
    return 0;
  }
  v11 = strpbrk(v9, "= \t");
  v12 = v11;
  if ( !v11 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v9[v13] );
    if ( v13 == 3 && !strncmp_0(v9, "RUN", 3u) )
    {
      *a4 = 1;
      return v9 + 3;
    }
LABEL_15:
    ErrSet((__int64)a3, (int)"%1 assignment operator missing", "%c", 61);
    return 0;
  }
  v14 = v11 - v9;
  if ( (unsigned __int64)(v11 - v9) >= 0x20 )
  {
    ErrSet((__int64)a3, (int)"Parameter name exceeds maximum length(%1): %2", "%d%s", 31, v9);
    return 0;
  }
  memcpy_0(v20, v9, v11 - v9);
  v20[v14] = 0;
  v15 = strspn(v12, " \t");
  if ( v12[v15] != 61 )
    goto LABEL_15;
  v16 = &v12[v15 + 1];
  QuotedString = &v16[strspn(v16, " \t")];
  if ( *QuotedString == 47 && QuotedString > v16 )
  {
    Source[0] = 0;
  }
  else
  {
    QuotedString = (const char *)getQuotedString(Source, (__int64)"parameter value", (__int64)a3);
    if ( !QuotedString )
      return 0;
  }
  v18 = (void **)malloc(8u);
  if ( !v18 )
  {
    ErrSet((__int64)a3, (int)"Out of memory saving %1", "%s", "parameter value");
    return 0;
  }
  v19 = _strdup(Source);
  *v18 = v19;
  if ( !v19 )
  {
    ErrSet((__int64)a3, (int)"Out of memory saving %1", "%s", "parameter value");
LABEL_24:
    free(v18);
    return 0;
  }
  if ( !GLAdd(*a1, v20, (char *)v18, "file parameter", 1, (__int64)a3) )
  {
    free(*v18);
    goto LABEL_24;
  }
  return QuotedString;
}

```

## disassembly

```asm
0x1400034e4  push    rbx
0x1400034e6  push    rbp
0x1400034e7  push    rsi
0x1400034e8  push    rdi
0x1400034e9  push    r14
0x1400034eb  sub     rsp, 460h
0x1400034f2  mov     rax, cs:__security_cookie
0x1400034f9  xor     rax, rsp
0x1400034fc  mov     [rsp+488h+var_38], rax
0x140003504  cmp     qword ptr [rcx], 0
0x140003508  mov     rsi, r9
0x14000350b  mov     rdi, r8
0x14000350e  mov     rbx, rdx
0x140003511  mov     r14, rcx
0x140003514  jnz     short loc_140003536
0x140003516  mov     r9, r8
0x140003519  lea     rdx, DestroyFileParm
0x140003520  lea     r8, aFileParameter; "file parameter"
0x140003527  xor     ecx, ecx
0x140003529  call    GLCreateList
0x14000352e  mov     [r14], rax
0x140003531  test    rax, rax
0x140003534  jz      short loc_14000354D
0x140003536  inc     rbx
0x140003539  cmp     byte ptr [rbx], 0
0x14000353c  jnz     short loc_140003554
0x14000353e  lea     rdx, aMissingParamet; "Missing parameter name"
0x140003545  mov     rcx, rdi
0x140003548  call    ErrSet
0x14000354d  xor     eax, eax
0x14000354f  jmp     loc_140003723
0x140003554  lea     rdx, asc_140011C88; "= \t"
0x14000355b  mov     rcx, rbx; Str
0x14000355e  call    cs:__imp_strpbrk
0x140003564  mov     rbp, rax
0x140003567  test    rax, rax
0x14000356a  jnz     short loc_1400035A8
0x14000356c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003570  inc     rax
0x140003573  cmp     byte ptr [rbx+rax], 0
0x140003577  jnz     short loc_140003570
0x140003579  cmp     rax, 3
0x14000357d  jnz     loc_140003605
0x140003583  mov     r8d, eax; MaxCount
0x140003586  lea     rdx, Str2; "RUN"
0x14000358d  mov     rcx, rbx; Str1
0x140003590  call    strncmp_0
0x140003595  test    eax, eax
0x140003597  jnz     short loc_140003605
0x140003599  mov     dword ptr [rsi], 1
0x14000359f  lea     rax, [rbx+3]
0x1400035a3  jmp     loc_140003723
0x1400035a8  mov     rsi, rbp
0x1400035ab  sub     rsi, rbx
0x1400035ae  cmp     rsi, 20h ; ' '
0x1400035b2  jb      short loc_1400035DA
0x1400035b4  mov     r9d, 1Fh
0x1400035ba  mov     [rsp+488h+var_468], rbx
0x1400035bf  lea     r8, aDS; "%d%s"
0x1400035c6  mov     rcx, rdi
0x1400035c9  lea     rdx, aParameterNameE; "Parameter name exceeds maximum length(%"...
0x1400035d0  call    ErrSet
0x1400035d5  jmp     loc_14000354D
0x1400035da  mov     r8, rsi; Size
0x1400035dd  lea     rcx, [rsp+488h+var_458]; void *
0x1400035e2  mov     rdx, rbx; Src
0x1400035e5  call    memcpy_0
0x1400035ea  lea     rdx, Control; " \t"
0x1400035f1  mov     [rsp+rsi+488h+var_458], 0
0x1400035f6  mov     rcx, rbp; Str
0x1400035f9  call    cs:__imp_strspn
0x1400035ff  cmp     byte ptr [rax+rbp], 3Dh ; '='
0x140003603  jz      short loc_140003626
0x140003605  mov     r9d, 3Dh ; '='
0x14000360b  lea     r8, aC; "%c"
0x140003612  lea     rdx, a1AssignmentOpe; "%1 assignment operator missing"
0x140003619  mov     rcx, rdi
0x14000361c  call    ErrSet
0x140003621  jmp     loc_14000354D
0x140003626  lea     rbx, [rbp+1]
0x14000362a  add     rbx, rax
0x14000362d  lea     rdx, Control; " \t"
0x140003634  mov     rcx, rbx; Str
0x140003637  call    cs:__imp_strspn
0x14000363d  lea     rbp, aParameterValue; "parameter value"
0x140003644  lea     rsi, [rax+rbx]
0x140003648  cmp     byte ptr [rsi], 2Fh ; '/'
0x14000364b  jnz     short loc_140003659
0x14000364d  cmp     rsi, rbx
0x140003650  jbe     short loc_140003659
0x140003652  mov     [rsp+488h+Source], 0
0x140003657  jmp     short loc_140003681
0x140003659  mov     [rsp+488h+var_460], rdi; __int64
0x14000365e  lea     rcx, [rsp+488h+Source]; void *
0x140003663  mov     r8, rsi
0x140003666  mov     [rsp+488h+var_468], rbp; __int64
0x14000366b  mov     edx, 400h
0x140003670  call    getQuotedString
0x140003675  mov     rsi, rax
0x140003678  test    rax, rax
0x14000367b  jz      loc_14000354D
0x140003681  mov     ecx, 8; Size
0x140003686  call    cs:__imp_malloc
0x14000368c  mov     rbx, rax
0x14000368f  test    rax, rax
0x140003692  jnz     short loc_1400036B2
0x140003694  mov     r9, rbp
0x140003697  lea     r8, aS_4; "%s"
0x14000369e  lea     rdx, aOutOfMemorySav; "Out of memory saving %1"
0x1400036a5  mov     rcx, rdi
0x1400036a8  call    ErrSet
0x1400036ad  jmp     loc_14000354D
0x1400036b2  lea     rcx, [rsp+488h+Source]; Source
0x1400036b7  call    cs:__imp__strdup
0x1400036bd  mov     [rbx], rax
0x1400036c0  test    rax, rax
0x1400036c3  jnz     short loc_1400036EC
0x1400036c5  mov     r9, rbp
0x1400036c8  lea     r8, aS_4; "%s"
0x1400036cf  lea     rdx, aOutOfMemorySav; "Out of memory saving %1"
0x1400036d6  mov     rcx, rdi
0x1400036d9  call    ErrSet
0x1400036de  mov     rcx, rbx; Block
0x1400036e1  call    cs:__imp_free
0x1400036e7  jmp     loc_14000354D
0x1400036ec  mov     rcx, [r14]
0x1400036ef  lea     r9, aFileParameter; "file parameter"
0x1400036f6  mov     [rsp+488h+var_460], rdi
0x1400036fb  lea     rdx, [rsp+488h+var_458]
0x140003700  mov     r8, rbx
0x140003703  mov     dword ptr [rsp+488h+var_468], 1
0x14000370b  call    GLAdd
0x140003710  test    rax, rax
0x140003713  jnz     short loc_140003720
0x140003715  mov     rcx, [rbx]; Block
0x140003718  call    cs:__imp_free
0x14000371e  jmp     short loc_1400036DE
0x140003720  mov     rax, rsi
0x140003723  mov     rcx, [rsp+488h+var_38]
0x14000372b  xor     rcx, rsp; StackCookie
0x14000372e  call    __security_check_cookie
0x140003733  add     rsp, 460h
0x14000373a  pop     r14
0x14000373c  pop     rdi
0x14000373d  pop     rsi
0x14000373e  pop     rbp
0x14000373f  pop     rbx
0x140003740  retn
```
