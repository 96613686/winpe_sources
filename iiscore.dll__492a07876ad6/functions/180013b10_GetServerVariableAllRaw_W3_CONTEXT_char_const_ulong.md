# GetServerVariableAllRaw(W3_CONTEXT *,char const * *,ulong *)

- ea: `0x180013b10`
- end: `0x180013dfc`
- name: `?GetServerVariableAllRaw@@YAJPEAVW3_CONTEXT@@PEAPEBDPEAK@Z`
- size: `748`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const char **, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180013b10`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180013b4b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180013b4b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180013c4a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180013d95`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180013ddd`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180013c4a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180013d95`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180013ddd`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180013d63`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180013dc8`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180013d63`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180013dc8`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013bc5`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013be9`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013c0b`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013c2f`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013ccb`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013cf3`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013d19`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013d41`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013bc5`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013be9`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013c0b`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013c2f`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013ccb`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013cf3`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013d19`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180013d41`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x180013db3`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x180013db3`

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
0x180013b10  push    rbx
0x180013b12  push    rbp
0x180013b13  push    r12
0x180013b15  push    r13
0x180013b17  push    r15
0x180013b19  sub     rsp, 280h
0x180013b20  mov     rax, cs:__security_cookie
0x180013b27  xor     rax, rsp
0x180013b2a  mov     [rsp+2A8h+var_48], rax
0x180013b32  mov     r13, r8
0x180013b35  mov     r12, rdx
0x180013b38  mov     r15, rcx
0x180013b3b  lea     rdx, [rsp+2A8h+var_248]
0x180013b40  mov     r8d, 200h
0x180013b46  lea     rcx, [rsp+2A8h+var_280]
0x180013b4b  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180013b52  nop     dword ptr [rax+rax+00h]
0x180013b57  mov     rax, [r15+30h]
0x180013b5b  lea     r8, ?sm_rgHeaders@REQUEST_HEADER_HASH@@0PAUHEADER_RECORD@@A; HEADER_RECORD near * REQUEST_HEADER_HASH::sm_rgHeaders
0x180013b62  mov     [rsp+2A8h+arg_18], rsi
0x180013b6a  xor     ebx, ebx
0x180013b6c  mov     [rsp+2A8h+var_30], rdi
0x180013b74  mov     [rsp+2A8h+var_38], r14
0x180013b7c  mov     rbp, [rax+28h]
0x180013b80  cmp     ebx, 29h ; ')'
0x180013b83  jnb     loc_180013C98
0x180013b89  mov     eax, ebx
0x180013b8b  add     rax, rax
0x180013b8e  mov     ecx, ebx
0x180013b90  movzx   edi, word ptr [rbp+rax*8+98h]
0x180013b98  test    di, di
0x180013b9b  jnz     short loc_180013BA1
0x180013b9d  inc     ebx
0x180013b9f  jmp     short loc_180013B80
0x180013ba1  shl     rcx, 5
0x180013ba5  mov     rdx, [rcx+r8]
0x180013ba9  test    rdx, rdx
0x180013bac  jz      loc_180013C91
0x180013bb2  movzx   r8d, word ptr [rcx+r8+10h]
0x180013bb8  lea     rcx, [rsp+2A8h+var_280]
0x180013bbd  mov     r14, [rbp+rax*8+0A0h]
0x180013bc5  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180013bcc  nop     dword ptr [rax+rax+00h]
0x180013bd1  mov     esi, eax
0x180013bd3  test    eax, eax
0x180013bd5  js      short loc_180013C45
0x180013bd7  mov     r8d, 2
0x180013bdd  lea     rdx, asc_18003C5A8; ": "
0x180013be4  lea     rcx, [rsp+2A8h+var_280]
0x180013be9  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180013bf0  nop     dword ptr [rax+rax+00h]
0x180013bf5  mov     esi, eax
0x180013bf7  test    eax, eax
0x180013bf9  js      short loc_180013C45
0x180013bfb  test    r14, r14
0x180013bfe  jz      short loc_180013C1D
0x180013c00  mov     r8d, edi
0x180013c03  lea     rcx, [rsp+2A8h+var_280]
0x180013c08  mov     rdx, r14
0x180013c0b  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180013c12  nop     dword ptr [rax+rax+00h]
0x180013c17  mov     esi, eax
0x180013c19  test    eax, eax
0x180013c1b  js      short loc_180013C45
0x180013c1d  mov     r8d, 2
0x180013c23  lea     rdx, Control; "\r\n"
0x180013c2a  lea     rcx, [rsp+2A8h+var_280]
0x180013c2f  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180013c36  nop     dword ptr [rax+rax+00h]
0x180013c3b  mov     esi, eax
0x180013c3d  test    eax, eax
0x180013c3f  jns     loc_180013DF0
0x180013c45  lea     rcx, [rsp+2A8h+var_280]
0x180013c4a  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180013c51  nop     dword ptr [rax+rax+00h]
0x180013c56  mov     eax, esi
0x180013c58  mov     r14, [rsp+2A8h+var_38]
0x180013c60  mov     rdi, [rsp+2A8h+var_30]
0x180013c68  mov     rsi, [rsp+2A8h+arg_18]
0x180013c70  mov     rcx, [rsp+2A8h+var_48]
0x180013c78  xor     rcx, rsp; StackCookie
0x180013c7b  call    __security_check_cookie
0x180013c80  add     rsp, 280h
0x180013c87  pop     r15
0x180013c89  pop     r13
0x180013c8b  pop     r12
0x180013c8d  pop     rbp
0x180013c8e  pop     rbx
0x180013c8f  retn
0x180013c91  mov     esi, 8007000Dh
0x180013c96  jmp     short loc_180013C45
0x180013c98  xor     ebx, ebx
0x180013c9a  movzx   eax, word ptr [rbp+78h]
0x180013c9e  cmp     ebx, eax
0x180013ca0  jnb     loc_180013D5E
0x180013ca6  mov     rax, [rbp+80h]
0x180013cad  lea     rcx, [rbx+rbx*2]
0x180013cb1  movzx   r14d, word ptr [rax+rcx*8+2]
0x180013cb7  mov     rdi, [rax+rcx*8+10h]
0x180013cbc  movzx   r8d, word ptr [rax+rcx*8]
0x180013cc1  mov     rdx, [rax+rcx*8+8]
0x180013cc6  lea     rcx, [rsp+2A8h+var_280]
0x180013ccb  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180013cd2  nop     dword ptr [rax+rax+00h]
0x180013cd7  mov     esi, eax
0x180013cd9  test    eax, eax
0x180013cdb  js      loc_180013C45
0x180013ce1  mov     r8d, 2
0x180013ce7  lea     rdx, asc_18003C5A8; ": "
0x180013cee  lea     rcx, [rsp+2A8h+var_280]
0x180013cf3  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180013cfa  nop     dword ptr [rax+rax+00h]
0x180013cff  mov     esi, eax
0x180013d01  test    eax, eax
0x180013d03  js      loc_180013C45
0x180013d09  test    rdi, rdi
0x180013d0c  jz      short loc_180013D2F
0x180013d0e  mov     r8d, r14d
0x180013d11  lea     rcx, [rsp+2A8h+var_280]
0x180013d16  mov     rdx, rdi
0x180013d19  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180013d20  nop     dword ptr [rax+rax+00h]
0x180013d25  mov     esi, eax
0x180013d27  test    eax, eax
0x180013d29  js      loc_180013C45
0x180013d2f  mov     r8d, 2
0x180013d35  lea     rdx, Control; "\r\n"
0x180013d3c  lea     rcx, [rsp+2A8h+var_280]
0x180013d41  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180013d48  nop     dword ptr [rax+rax+00h]
0x180013d4d  mov     esi, eax
0x180013d4f  test    eax, eax
0x180013d51  js      loc_180013C45
0x180013d57  inc     ebx
0x180013d59  jmp     loc_180013C9A
0x180013d5e  lea     rcx, [rsp+2A8h+var_280]
0x180013d63  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180013d6a  nop     dword ptr [rax+rax+00h]
0x180013d6f  mov     rcx, r15
0x180013d72  lea     edx, [rax+1]
0x180013d75  mov     rax, [r15]
0x180013d78  mov     [rsp+2A8h+var_288], edx
0x180013d7c  mov     rax, [rax+90h]
0x180013d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d88  lea     rcx, [rsp+2A8h+var_280]
0x180013d8d  mov     rbx, rax
0x180013d90  test    rax, rax
0x180013d93  jnz     short loc_180013DAB
0x180013d95  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180013d9c  nop     dword ptr [rax+rax+00h]
0x180013da1  mov     eax, 80070008h
0x180013da6  jmp     loc_180013C58
0x180013dab  lea     r8, [rsp+2A8h+var_288]
0x180013db0  mov     rdx, rbx
0x180013db3  call    cs:__imp_?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z; STRA::CopyToBuffer(char *,ulong *)
0x180013dba  nop     dword ptr [rax+rax+00h]
0x180013dbf  lea     rcx, [rsp+2A8h+var_280]
0x180013dc4  mov     [r12], rbx
0x180013dc8  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180013dcf  nop     dword ptr [rax+rax+00h]
0x180013dd4  lea     rcx, [rsp+2A8h+var_280]
0x180013dd9  mov     [r13+0], eax
0x180013ddd  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180013de4  nop     dword ptr [rax+rax+00h]
0x180013de9  xor     eax, eax
0x180013deb  jmp     loc_180013C58
0x180013df0  lea     r8, ?sm_rgHeaders@REQUEST_HEADER_HASH@@0PAUHEADER_RECORD@@A; HEADER_RECORD near * REQUEST_HEADER_HASH::sm_rgHeaders
0x180013df7  jmp     loc_180013B9D
```
