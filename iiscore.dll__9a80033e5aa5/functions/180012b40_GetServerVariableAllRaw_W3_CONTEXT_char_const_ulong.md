# GetServerVariableAllRaw(W3_CONTEXT *,char const * *,ulong *)

- ea: `0x180012b40`
- end: `0x180012dd7`
- name: `?GetServerVariableAllRaw@@YAJPEAVW3_CONTEXT@@PEAPEBDPEAK@Z`
- size: `663`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const char **, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180012b40`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180012b7b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180012b7b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180012c62`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180012d88`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180012dbe`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180012c62`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180012d88`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180012dbe`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180012d5c`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180012daf`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180012d5c`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180012daf`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012bf5`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012c13`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012c2f`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012c4d`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012cdc`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012cfe`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012d1e`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012d40`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012bf5`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012c13`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012c2f`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012c4d`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012cdc`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012cfe`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012d1e`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180012d40`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x180012da0`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x180012da0`

## pseudocode

```c
__int64 __fastcall GetServerVariableAllRaw(struct W3_CONTEXT *a1, const char **a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rbp
  unsigned int v8; // edi
  __int64 v9; // rcx
  const char *v10; // rdx
  const char *v11; // r14
  int v12; // esi
  __int64 i; // rbx
  __int64 v15; // rax
  unsigned int v16; // r14d
  const char *v17; // rdi
  unsigned int v18; // edx
  __int64 v19; // rax
  char *v20; // rax
  const char *v21; // rbx
  unsigned int v22; // [rsp+20h] [rbp-288h] BYREF
  _BYTE v23[56]; // [rsp+28h] [rbp-280h] BYREF
  char v24[512]; // [rsp+60h] [rbp-248h] BYREF

  STRA::STRA((STRA *)v23, v24, 0x200u);
  v6 = 0;
  v7 = *(_QWORD *)(*((_QWORD *)a1 + 6) + 40LL);
  while ( v6 < 0x29 )
  {
    v8 = *(unsigned __int16 *)(v7 + 16LL * v6 + 152);
    if ( (_WORD)v8 )
    {
      v9 = 32LL * v6;
      v10 = *(const char **)((char *)&REQUEST_HEADER_HASH::sm_rgHeaders + v9);
      if ( !v10 )
      {
        v12 = -2147024883;
LABEL_11:
        STRA::~STRA((STRA *)v23);
        return (unsigned int)v12;
      }
      v11 = *(const char **)(v7 + 16LL * v6 + 160);
      v12 = STRA::Append((STRA *)v23, v10, *(unsigned __int16 *)((char *)&REQUEST_HEADER_HASH::sm_rgHeaders + v9 + 16));
      if ( v12 < 0 )
        goto LABEL_11;
      v12 = STRA::Append((STRA *)v23, ": ", 2u);
      if ( v12 < 0 )
        goto LABEL_11;
      if ( v11 )
      {
        v12 = STRA::Append((STRA *)v23, v11, v8);
        if ( v12 < 0 )
          goto LABEL_11;
      }
      v12 = STRA::Append((STRA *)v23, "\r\n", 2u);
      if ( v12 < 0 )
        goto LABEL_11;
    }
    ++v6;
  }
  for ( i = 0; (unsigned int)i < *(unsigned __int16 *)(v7 + 120); i = (unsigned int)(i + 1) )
  {
    v15 = *(_QWORD *)(v7 + 128);
    v16 = *(unsigned __int16 *)(v15 + 24 * i + 2);
    v17 = *(const char **)(v15 + 24 * i + 16);
    v12 = STRA::Append((STRA *)v23, *(const char **)(v15 + 24 * i + 8), *(unsigned __int16 *)(v15 + 24 * i));
    if ( v12 < 0 )
      goto LABEL_11;
    v12 = STRA::Append((STRA *)v23, ": ", 2u);
    if ( v12 < 0 )
      goto LABEL_11;
    if ( v17 )
    {
      v12 = STRA::Append((STRA *)v23, v17, v16);
      if ( v12 < 0 )
        goto LABEL_11;
    }
    v12 = STRA::Append((STRA *)v23, "\r\n", 2u);
    if ( v12 < 0 )
      goto LABEL_11;
  }
  v18 = STRA::QueryCCH((STRA *)v23) + 1;
  v19 = *(_QWORD *)a1;
  v22 = v18;
  v20 = (char *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *))(v19 + 144))(a1);
  v21 = v20;
  if ( v20 )
  {
    STRA::CopyToBuffer((STRA *)v23, v20, &v22);
    *a2 = v21;
    *a3 = STRA::QueryCCH((STRA *)v23);
    STRA::~STRA((STRA *)v23);
    return 0;
  }
  else
  {
    STRA::~STRA((STRA *)v23);
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x180012b40  push    rbx
0x180012b42  push    rbp
0x180012b43  push    r12
0x180012b45  push    r13
0x180012b47  push    r15
0x180012b49  sub     rsp, 280h
0x180012b50  mov     rax, cs:__security_cookie
0x180012b57  xor     rax, rsp
0x180012b5a  mov     [rsp+2A8h+var_48], rax
0x180012b62  mov     r13, r8
0x180012b65  mov     r12, rdx
0x180012b68  mov     r15, rcx
0x180012b6b  lea     rdx, [rsp+2A8h+var_248]
0x180012b70  mov     r8d, 200h
0x180012b76  lea     rcx, [rsp+2A8h+var_280]
0x180012b7b  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180012b81  mov     rax, [r15+30h]
0x180012b85  lea     r8, ?sm_rgHeaders@REQUEST_HEADER_HASH@@0PAUHEADER_RECORD@@A; HEADER_RECORD near * REQUEST_HEADER_HASH::sm_rgHeaders
0x180012b8c  mov     [rsp+2A8h+arg_18], rsi
0x180012b94  xor     ebx, ebx
0x180012b96  mov     [rsp+2A8h+var_30], rdi
0x180012b9e  mov     [rsp+2A8h+var_38], r14
0x180012ba6  mov     rbp, [rax+28h]
0x180012baa  nop     word ptr [rax+rax+00h]
0x180012bb0  cmp     ebx, 29h ; ')'
0x180012bb3  jnb     loc_180012CA9
0x180012bb9  mov     eax, ebx
0x180012bbb  add     rax, rax
0x180012bbe  mov     ecx, ebx
0x180012bc0  movzx   edi, word ptr [rbp+rax*8+98h]
0x180012bc8  test    di, di
0x180012bcb  jnz     short loc_180012BD1
0x180012bcd  inc     ebx
0x180012bcf  jmp     short loc_180012BB0
0x180012bd1  shl     rcx, 5
0x180012bd5  mov     rdx, [rcx+r8]
0x180012bd9  test    rdx, rdx
0x180012bdc  jz      loc_180012CA2
0x180012be2  movzx   r8d, word ptr [rcx+r8+10h]
0x180012be8  lea     rcx, [rsp+2A8h+var_280]
0x180012bed  mov     r14, [rbp+rax*8+0A0h]
0x180012bf5  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180012bfb  mov     esi, eax
0x180012bfd  test    eax, eax
0x180012bff  js      short loc_180012C5D
0x180012c01  mov     r8d, 2
0x180012c07  lea     rdx, asc_1800395A8; ": "
0x180012c0e  lea     rcx, [rsp+2A8h+var_280]
0x180012c13  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180012c19  mov     esi, eax
0x180012c1b  test    eax, eax
0x180012c1d  js      short loc_180012C5D
0x180012c1f  test    r14, r14
0x180012c22  jz      short loc_180012C3B
0x180012c24  mov     r8d, edi
0x180012c27  lea     rcx, [rsp+2A8h+var_280]
0x180012c2c  mov     rdx, r14
0x180012c2f  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180012c35  mov     esi, eax
0x180012c37  test    eax, eax
0x180012c39  js      short loc_180012C5D
0x180012c3b  mov     r8d, 2
0x180012c41  lea     rdx, Control; "\r\n"
0x180012c48  lea     rcx, [rsp+2A8h+var_280]
0x180012c4d  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180012c53  mov     esi, eax
0x180012c55  test    eax, eax
0x180012c57  jns     loc_180012DCB
0x180012c5d  lea     rcx, [rsp+2A8h+var_280]
0x180012c62  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180012c68  mov     eax, esi
0x180012c6a  mov     r14, [rsp+2A8h+var_38]
0x180012c72  mov     rdi, [rsp+2A8h+var_30]
0x180012c7a  mov     rsi, [rsp+2A8h+arg_18]
0x180012c82  mov     rcx, [rsp+2A8h+var_48]
0x180012c8a  xor     rcx, rsp; StackCookie
0x180012c8d  call    __security_check_cookie
0x180012c92  add     rsp, 280h
0x180012c99  pop     r15
0x180012c9b  pop     r13
0x180012c9d  pop     r12
0x180012c9f  pop     rbp
0x180012ca0  pop     rbx
0x180012ca1  retn
0x180012ca2  mov     esi, 8007000Dh
0x180012ca7  jmp     short loc_180012C5D
0x180012ca9  xor     ebx, ebx
0x180012cab  movzx   eax, word ptr [rbp+78h]
0x180012caf  cmp     ebx, eax
0x180012cb1  jnb     loc_180012D57
0x180012cb7  mov     rax, [rbp+80h]
0x180012cbe  lea     rcx, [rbx+rbx*2]
0x180012cc2  movzx   r14d, word ptr [rax+rcx*8+2]
0x180012cc8  mov     rdi, [rax+rcx*8+10h]
0x180012ccd  movzx   r8d, word ptr [rax+rcx*8]
0x180012cd2  mov     rdx, [rax+rcx*8+8]
0x180012cd7  lea     rcx, [rsp+2A8h+var_280]
0x180012cdc  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180012ce2  mov     esi, eax
0x180012ce4  test    eax, eax
0x180012ce6  js      loc_180012C5D
0x180012cec  mov     r8d, 2
0x180012cf2  lea     rdx, asc_1800395A8; ": "
0x180012cf9  lea     rcx, [rsp+2A8h+var_280]
0x180012cfe  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180012d04  mov     esi, eax
0x180012d06  test    eax, eax
0x180012d08  js      loc_180012C5D
0x180012d0e  test    rdi, rdi
0x180012d11  jz      short loc_180012D2E
0x180012d13  mov     r8d, r14d
0x180012d16  lea     rcx, [rsp+2A8h+var_280]
0x180012d1b  mov     rdx, rdi
0x180012d1e  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180012d24  mov     esi, eax
0x180012d26  test    eax, eax
0x180012d28  js      loc_180012C5D
0x180012d2e  mov     r8d, 2
0x180012d34  lea     rdx, Control; "\r\n"
0x180012d3b  lea     rcx, [rsp+2A8h+var_280]
0x180012d40  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180012d46  mov     esi, eax
0x180012d48  test    eax, eax
0x180012d4a  js      loc_180012C5D
0x180012d50  inc     ebx
0x180012d52  jmp     loc_180012CAB
0x180012d57  lea     rcx, [rsp+2A8h+var_280]
0x180012d5c  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180012d62  mov     rcx, r15
0x180012d65  lea     edx, [rax+1]
0x180012d68  mov     rax, [r15]
0x180012d6b  mov     [rsp+2A8h+var_288], edx
0x180012d6f  mov     rax, [rax+90h]
0x180012d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d7b  lea     rcx, [rsp+2A8h+var_280]
0x180012d80  mov     rbx, rax
0x180012d83  test    rax, rax
0x180012d86  jnz     short loc_180012D98
0x180012d88  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180012d8e  mov     eax, 80070008h
0x180012d93  jmp     loc_180012C6A
0x180012d98  lea     r8, [rsp+2A8h+var_288]
0x180012d9d  mov     rdx, rbx
0x180012da0  call    cs:__imp_?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z; STRA::CopyToBuffer(char *,ulong *)
0x180012da6  lea     rcx, [rsp+2A8h+var_280]
0x180012dab  mov     [r12], rbx
0x180012daf  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180012db5  lea     rcx, [rsp+2A8h+var_280]
0x180012dba  mov     [r13+0], eax
0x180012dbe  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180012dc4  xor     eax, eax
0x180012dc6  jmp     loc_180012C6A
0x180012dcb  lea     r8, ?sm_rgHeaders@REQUEST_HEADER_HASH@@0PAUHEADER_RECORD@@A; HEADER_RECORD near * REQUEST_HEADER_HASH::sm_rgHeaders
0x180012dd2  jmp     loc_180012BCD
```
