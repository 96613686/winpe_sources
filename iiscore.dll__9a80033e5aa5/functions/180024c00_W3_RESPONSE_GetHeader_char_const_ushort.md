# W3_RESPONSE::GetHeader(char const *,ushort *)

- ea: `0x180024c00`
- end: `0x180024db7`
- name: `?GetHeader@W3_RESPONSE@@QEBAPEBDPEBDPEAG@Z`
- size: `439`
- prototype: `const char *__fastcall(W3_RESPONSE *__hidden this, const char *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800205a0`

## callees

- `0x1800100f4`
- `0x180018fc8`
- `0x180024c00`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180024c8b`
- `msvcrt!_stricmp` at `0x180024c8b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024c48`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024c48`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024d67`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024d88`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024d67`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024d88`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180024cbe`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180024cbe`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180024d1b`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180024d1b`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180024ce0`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180024d01`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180024ce0`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180024d01`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x180024d4d`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x180024d4d`

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
0x180024c00  mov     [rsp-8+arg_18], rbx
0x180024c05  push    rbp
0x180024c06  push    rsi
0x180024c07  push    rdi
0x180024c08  push    r12
0x180024c0a  push    r13
0x180024c0c  push    r14
0x180024c0e  push    r15
0x180024c10  lea     rbp, [rsp-27h]
0x180024c15  sub     rsp, 0B0h
0x180024c1c  mov     rax, cs:__security_cookie
0x180024c23  xor     rax, rsp
0x180024c26  mov     [rbp+57h+var_40], rax
0x180024c2a  mov     r14, r8
0x180024c2d  mov     [rbp+57h+var_C0], 0
0x180024c34  mov     r13, rdx
0x180024c37  mov     rdi, rcx
0x180024c3a  mov     r8d, 40h ; '@'
0x180024c40  lea     rdx, [rbp+57h+var_80]
0x180024c44  lea     rcx, [rbp+57h+var_B8]
0x180024c48  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180024c4e  test    r13, r13
0x180024c51  jz      loc_180024D84
0x180024c57  mov     rcx, r13; char *
0x180024c5a  call    ?GetIndex@RESPONSE_HEADER_HASH@@SAKPEBD@Z; RESPONSE_HEADER_HASH::GetIndex(char const *)
0x180024c5f  cmp     eax, 0FFFFFFFFh
0x180024c62  jnz     loc_180024D72
0x180024c68  xor     ebx, ebx
0x180024c6a  xor     r15d, r15d
0x180024c6d  xor     esi, esi
0x180024c6f  movzx   eax, word ptr [rdi+50h]
0x180024c73  cmp     esi, eax
0x180024c75  jnb     loc_180024D12
0x180024c7b  mov     rdx, [rdi+58h]
0x180024c7f  lea     r12, [rsi+rsi*2]
0x180024c83  mov     rcx, r13; String1
0x180024c86  mov     rdx, [rdx+r12*8+8]; String2
0x180024c8b  call    cs:__imp__stricmp
0x180024c91  test    eax, eax
0x180024c93  jnz     short loc_180024D0B
0x180024c95  test    rbx, rbx
0x180024c98  jnz     short loc_180024CAE
0x180024c9a  mov     rax, [rdi+58h]
0x180024c9e  mov     rbx, [rax+r12*8+10h]
0x180024ca3  movzx   eax, word ptr [rax+r12*8+2]
0x180024ca9  mov     [rbp+57h+var_C0], eax
0x180024cac  jmp     short loc_180024D0B
0x180024cae  test    r15d, r15d
0x180024cb1  jnz     short loc_180024CCC
0x180024cb3  mov     r8d, [rbp+57h+var_C0]
0x180024cb7  lea     rcx, [rbp+57h+var_B8]
0x180024cbb  mov     rdx, rbx
0x180024cbe  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180024cc4  test    eax, eax
0x180024cc6  js      loc_180024D84
0x180024ccc  mov     r15d, 1
0x180024cd2  lea     rdx, asc_180039188; ","
0x180024cd9  mov     r8d, r15d
0x180024cdc  lea     rcx, [rbp+57h+var_B8]
0x180024ce0  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180024ce6  test    eax, eax
0x180024ce8  js      loc_180024D84
0x180024cee  mov     rdx, [rdi+58h]
0x180024cf2  lea     rcx, [rbp+57h+var_B8]
0x180024cf6  movzx   r8d, word ptr [rdx+r12*8+2]
0x180024cfc  mov     rdx, [rdx+r12*8+10h]
0x180024d01  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180024d07  test    eax, eax
0x180024d09  js      short loc_180024D84
0x180024d0b  inc     esi
0x180024d0d  jmp     loc_180024C6F
0x180024d12  test    r15d, r15d
0x180024d15  jz      short loc_180024D56
0x180024d17  lea     rcx, [rbp+57h+var_B8]
0x180024d1b  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180024d21  mov     rcx, [rdi+30h]
0x180024d25  lea     edx, [rax+1]
0x180024d28  mov     [rbp+57h+var_C0], edx
0x180024d2b  mov     rax, [rcx]
0x180024d2e  mov     rax, [rax+90h]
0x180024d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d3a  mov     rbx, rax
0x180024d3d  test    rax, rax
0x180024d40  jz      short loc_180024D84
0x180024d42  lea     r8, [rbp+57h+var_C0]
0x180024d46  mov     rdx, rax
0x180024d49  lea     rcx, [rbp+57h+var_B8]
0x180024d4d  call    cs:__imp_?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z; STRA::CopyToBuffer(char *,ulong *)
0x180024d53  dec     [rbp+57h+var_C0]
0x180024d56  test    r14, r14
0x180024d59  jz      short loc_180024D63
0x180024d5b  movzx   ecx, word ptr [rbp+57h+var_C0]
0x180024d5f  mov     [r14], cx
0x180024d63  lea     rcx, [rbp+57h+var_B8]
0x180024d67  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180024d6d  mov     rax, rbx
0x180024d70  jmp     short loc_180024D90
0x180024d72  mov     r8, r14; unsigned __int16 *
0x180024d75  mov     edx, eax; enum _HTTP_HEADER_ID
0x180024d77  mov     rcx, rdi; this
0x180024d7a  call    ?QueryHeader@W3_RESPONSE@@QEBAPEBDW4_HTTP_HEADER_ID@@PEAG@Z; W3_RESPONSE::QueryHeader(_HTTP_HEADER_ID,ushort *)
0x180024d7f  mov     rbx, rax
0x180024d82  jmp     short loc_180024D63
0x180024d84  lea     rcx, [rbp+57h+var_B8]
0x180024d88  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180024d8e  xor     eax, eax
0x180024d90  mov     rcx, [rbp+57h+var_40]
0x180024d94  xor     rcx, rsp; StackCookie
0x180024d97  call    __security_check_cookie
0x180024d9c  mov     rbx, [rsp+0E0h+arg_18]
0x180024da4  add     rsp, 0B0h
0x180024dab  pop     r15
0x180024dad  pop     r14
0x180024daf  pop     r13
0x180024db1  pop     r12
0x180024db3  pop     rdi
0x180024db4  pop     rsi
0x180024db5  pop     rbp
0x180024db6  retn
```
