# W3_RESPONSE::GetHeader(char const *,ushort *)

- ea: `0x180026af0`
- end: `0x180026ce6`
- name: `?GetHeader@W3_RESPONSE@@QEBAPEBDPEBDPEAG@Z`
- size: `502`
- prototype: `const char *__fastcall(W3_RESPONSE *__hidden this, const char *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800221d0`

## callees

- `0x180010e1c`
- `0x18001a520`
- `0x180026af0`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180026b81`
- `msvcrt!_stricmp` at `0x180026b81`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180026b38`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180026b38`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180026c89`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180026cb0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180026c89`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180026cb0`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180026bbe`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180026bbe`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180026c31`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180026c31`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180026be6`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180026c0d`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180026be6`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180026c0d`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x180026c69`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x180026c69`

## pseudocode

```c
const char *__fastcall W3_RESPONSE::GetHeader(W3_RESPONSE *this, const char *a2, unsigned __int16 *a3)
{
  enum _HTTP_HEADER_ID Index; // eax
  const char *Header; // rbx
  int v8; // r15d
  __int64 i; // rsi
  __int64 v10; // rax
  unsigned int CCH; // eax
  __int64 v12; // rcx
  char *v13; // rax
  unsigned int v15; // [rsp+20h] [rbp-69h] BYREF
  _BYTE v16[56]; // [rsp+28h] [rbp-61h] BYREF
  char v17[64]; // [rsp+60h] [rbp-29h] BYREF

  v15 = 0;
  STRA::STRA((STRA *)v16, v17, 0x40u);
  if ( a2 )
  {
    Index = RESPONSE_HEADER_HASH::GetIndex(a2);
    if ( Index != -1 )
    {
      Header = W3_RESPONSE::QueryHeader(this, Index, a3);
LABEL_18:
      STRA::~STRA((STRA *)v16);
      return Header;
    }
    Header = 0;
    v8 = 0;
    for ( i = 0; (unsigned int)i < *((unsigned __int16 *)this + 40); i = (unsigned int)(i + 1) )
    {
      if ( !_stricmp(a2, *(const char **)(*((_QWORD *)this + 11) + 24 * i + 8)) )
      {
        if ( Header )
        {
          if ( !v8 && (int)STRA::Copy((STRA *)v16, Header, v15) < 0 )
            goto LABEL_20;
          v8 = 1;
          if ( (int)STRA::Append((STRA *)v16, ",", 1u) < 0
            || (int)STRA::Append(
                      (STRA *)v16,
                      *(const char **)(*((_QWORD *)this + 11) + 24 * i + 16),
                      *(unsigned __int16 *)(*((_QWORD *)this + 11) + 24 * i + 2)) < 0 )
          {
            goto LABEL_20;
          }
        }
        else
        {
          v10 = *((_QWORD *)this + 11);
          Header = *(const char **)(v10 + 24 * i + 16);
          v15 = *(unsigned __int16 *)(v10 + 24 * i + 2);
        }
      }
    }
    if ( !v8 )
    {
LABEL_16:
      if ( a3 )
        *a3 = v15;
      goto LABEL_18;
    }
    CCH = STRA::QueryCCH((STRA *)v16);
    v12 = *((_QWORD *)this + 6);
    v15 = CCH + 1;
    v13 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 144LL))(v12);
    Header = v13;
    if ( v13 )
    {
      STRA::CopyToBuffer((STRA *)v16, v13, &v15);
      --v15;
      goto LABEL_16;
    }
  }
LABEL_20:
  STRA::~STRA((STRA *)v16);
  return 0;
}

```

## disassembly

```asm
0x180026af0  mov     [rsp-8+arg_18], rbx
0x180026af5  push    rbp
0x180026af6  push    rsi
0x180026af7  push    rdi
0x180026af8  push    r12
0x180026afa  push    r13
0x180026afc  push    r14
0x180026afe  push    r15
0x180026b00  lea     rbp, [rsp-27h]
0x180026b05  sub     rsp, 0B0h
0x180026b0c  mov     rax, cs:__security_cookie
0x180026b13  xor     rax, rsp
0x180026b16  mov     [rbp+57h+var_40], rax
0x180026b1a  mov     r14, r8
0x180026b1d  mov     [rbp+57h+var_C0], 0
0x180026b24  mov     r13, rdx
0x180026b27  mov     rdi, rcx
0x180026b2a  mov     r8d, 40h ; '@'
0x180026b30  lea     rdx, [rbp+57h+var_80]
0x180026b34  lea     rcx, [rbp+57h+var_B8]
0x180026b38  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180026b3f  nop     dword ptr [rax+rax+00h]
0x180026b44  test    r13, r13
0x180026b47  jz      loc_180026CAC
0x180026b4d  mov     rcx, r13; char *
0x180026b50  call    ?GetIndex@RESPONSE_HEADER_HASH@@SAKPEBD@Z; RESPONSE_HEADER_HASH::GetIndex(char const *)
0x180026b55  cmp     eax, 0FFFFFFFFh
0x180026b58  jnz     loc_180026C9A
0x180026b5e  xor     ebx, ebx
0x180026b60  xor     r15d, r15d
0x180026b63  xor     esi, esi
0x180026b65  movzx   eax, word ptr [rdi+50h]
0x180026b69  cmp     esi, eax
0x180026b6b  jnb     loc_180026C28
0x180026b71  mov     rdx, [rdi+58h]
0x180026b75  lea     r12, [rsi+rsi*2]
0x180026b79  mov     rcx, r13; String1
0x180026b7c  mov     rdx, [rdx+r12*8+8]; String2
0x180026b81  call    cs:__imp__stricmp
0x180026b88  nop     dword ptr [rax+rax+00h]
0x180026b8d  test    eax, eax
0x180026b8f  jnz     loc_180026C21
0x180026b95  test    rbx, rbx
0x180026b98  jnz     short loc_180026BAE
0x180026b9a  mov     rax, [rdi+58h]
0x180026b9e  mov     rbx, [rax+r12*8+10h]
0x180026ba3  movzx   eax, word ptr [rax+r12*8+2]
0x180026ba9  mov     [rbp+57h+var_C0], eax
0x180026bac  jmp     short loc_180026C21
0x180026bae  test    r15d, r15d
0x180026bb1  jnz     short loc_180026BD2
0x180026bb3  mov     r8d, [rbp+57h+var_C0]
0x180026bb7  lea     rcx, [rbp+57h+var_B8]
0x180026bbb  mov     rdx, rbx
0x180026bbe  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180026bc5  nop     dword ptr [rax+rax+00h]
0x180026bca  test    eax, eax
0x180026bcc  js      loc_180026CAC
0x180026bd2  mov     r15d, 1
0x180026bd8  lea     rdx, asc_18003C188; ","
0x180026bdf  mov     r8d, r15d
0x180026be2  lea     rcx, [rbp+57h+var_B8]
0x180026be6  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180026bed  nop     dword ptr [rax+rax+00h]
0x180026bf2  test    eax, eax
0x180026bf4  js      loc_180026CAC
0x180026bfa  mov     rdx, [rdi+58h]
0x180026bfe  lea     rcx, [rbp+57h+var_B8]
0x180026c02  movzx   r8d, word ptr [rdx+r12*8+2]
0x180026c08  mov     rdx, [rdx+r12*8+10h]
0x180026c0d  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180026c14  nop     dword ptr [rax+rax+00h]
0x180026c19  test    eax, eax
0x180026c1b  js      loc_180026CAC
0x180026c21  inc     esi
0x180026c23  jmp     loc_180026B65
0x180026c28  test    r15d, r15d
0x180026c2b  jz      short loc_180026C78
0x180026c2d  lea     rcx, [rbp+57h+var_B8]
0x180026c31  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180026c38  nop     dword ptr [rax+rax+00h]
0x180026c3d  mov     rcx, [rdi+30h]
0x180026c41  lea     edx, [rax+1]
0x180026c44  mov     [rbp+57h+var_C0], edx
0x180026c47  mov     rax, [rcx]
0x180026c4a  mov     rax, [rax+90h]
0x180026c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c56  mov     rbx, rax
0x180026c59  test    rax, rax
0x180026c5c  jz      short loc_180026CAC
0x180026c5e  lea     r8, [rbp+57h+var_C0]
0x180026c62  mov     rdx, rax
0x180026c65  lea     rcx, [rbp+57h+var_B8]
0x180026c69  call    cs:__imp_?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z; STRA::CopyToBuffer(char *,ulong *)
0x180026c70  nop     dword ptr [rax+rax+00h]
0x180026c75  dec     [rbp+57h+var_C0]
0x180026c78  test    r14, r14
0x180026c7b  jz      short loc_180026C85
0x180026c7d  movzx   ecx, word ptr [rbp+57h+var_C0]
0x180026c81  mov     [r14], cx
0x180026c85  lea     rcx, [rbp+57h+var_B8]
0x180026c89  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180026c90  nop     dword ptr [rax+rax+00h]
0x180026c95  mov     rax, rbx
0x180026c98  jmp     short loc_180026CBE
0x180026c9a  mov     r8, r14; unsigned __int16 *
0x180026c9d  mov     edx, eax; enum _HTTP_HEADER_ID
0x180026c9f  mov     rcx, rdi; this
0x180026ca2  call    ?QueryHeader@W3_RESPONSE@@QEBAPEBDW4_HTTP_HEADER_ID@@PEAG@Z; W3_RESPONSE::QueryHeader(_HTTP_HEADER_ID,ushort *)
0x180026ca7  mov     rbx, rax
0x180026caa  jmp     short loc_180026C85
0x180026cac  lea     rcx, [rbp+57h+var_B8]
0x180026cb0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180026cb7  nop     dword ptr [rax+rax+00h]
0x180026cbc  xor     eax, eax
0x180026cbe  mov     rcx, [rbp+57h+var_40]
0x180026cc2  xor     rcx, rsp; StackCookie
0x180026cc5  call    __security_check_cookie
0x180026cca  mov     rbx, [rsp+0E0h+arg_18]
0x180026cd2  add     rsp, 0B0h
0x180026cd9  pop     r15
0x180026cdb  pop     r14
0x180026cdd  pop     r13
0x180026cdf  pop     r12
0x180026ce1  pop     rdi
0x180026ce2  pop     rsi
0x180026ce3  pop     rbp
0x180026ce4  retn
```
