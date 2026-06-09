# W3_REQUEST::GetHeader(char const *,ushort *)

- ea: `0x180010f80`
- end: `0x180011198`
- name: `?GetHeader@W3_REQUEST@@QEBAPEBDPEBDPEAG@Z`
- size: `536`
- prototype: `const char *__fastcall(W3_REQUEST *__hidden this, const char *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180010f70`
- `0x180019aa0`
- `0x180022490`

## callees

- `0x180010f80`
- `0x1800111a0`
- `0x180016b40`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180011076`
- `msvcrt!_stricmp` at `0x180011076`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180010fd0`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180010fd0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180011018`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180011053`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180011018`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180011053`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800110b6`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800110b6`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180011123`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180011123`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x1800110da`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180011104`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x1800110da`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180011104`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x180011163`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x180011163`

## pseudocode

```c
const char *__fastcall W3_REQUEST::GetHeader(W3_REQUEST *this, const char *a2, unsigned __int16 *a3)
{
  __int64 v3; // r15
  enum _HTTP_HEADER_ID Index; // eax
  const char *Header; // rbx
  int v9; // r14d
  __int64 i; // rdi
  __int64 v12; // rax
  unsigned int CCH; // eax
  __int64 v14; // rcx
  char *v15; // rax
  unsigned int v16; // [rsp+20h] [rbp-79h] BYREF
  W3_REQUEST *v17; // [rsp+28h] [rbp-71h]
  _BYTE v18[64]; // [rsp+30h] [rbp-69h] BYREF
  char v19[64]; // [rsp+70h] [rbp-29h] BYREF

  v3 = *((_QWORD *)this + 5);
  v17 = this;
  v16 = 0;
  STRA::STRA((STRA *)v18, v19, 0x40u);
  if ( a2 )
  {
    Index = REQUEST_HEADER_HASH::GetIndex(a2);
    if ( Index != -1 )
    {
      Header = W3_REQUEST::QueryHeader(this, Index, a3);
LABEL_8:
      STRA::~STRA((STRA *)v18);
      return Header;
    }
    Header = 0;
    v9 = 0;
    for ( i = 0; (unsigned int)i < *(unsigned __int16 *)(v3 + 120); i = (unsigned int)(i + 1) )
    {
      if ( !_stricmp(a2, *(const char **)(*(_QWORD *)(v3 + 128) + 24 * i + 8)) )
      {
        if ( Header )
        {
          if ( !v9 && (int)STRA::Copy((STRA *)v18, Header, v16) < 0 )
            goto LABEL_9;
          v9 = 1;
          if ( (int)STRA::Append((STRA *)v18, ",", 1u) < 0
            || (int)STRA::Append(
                      (STRA *)v18,
                      *(const char **)(*(_QWORD *)(v3 + 128) + 24 * i + 16),
                      *(unsigned __int16 *)(*(_QWORD *)(v3 + 128) + 24 * i + 2)) < 0 )
          {
            goto LABEL_9;
          }
        }
        else
        {
          v12 = *(_QWORD *)(v3 + 128);
          Header = *(const char **)(v12 + 24 * i + 16);
          v16 = *(unsigned __int16 *)(v12 + 24 * i + 2);
        }
      }
    }
    if ( !v9 )
    {
LABEL_6:
      if ( a3 )
        *a3 = v16;
      goto LABEL_8;
    }
    CCH = STRA::QueryCCH((STRA *)v18);
    v14 = *((_QWORD *)v17 + 14);
    v16 = CCH + 1;
    v15 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 144LL))(v14);
    Header = v15;
    if ( v15 )
    {
      STRA::CopyToBuffer((STRA *)v18, v15, &v16);
      --v16;
      goto LABEL_6;
    }
  }
LABEL_9:
  STRA::~STRA((STRA *)v18);
  return 0;
}

```

## disassembly

```asm
0x180010f80  mov     [rsp-8+arg_18], rbx
0x180010f85  push    rbp
0x180010f86  push    rsi
0x180010f87  push    rdi
0x180010f88  push    r12
0x180010f8a  push    r13
0x180010f8c  push    r14
0x180010f8e  push    r15
0x180010f90  lea     rbp, [rsp-27h]
0x180010f95  sub     rsp, 0C0h
0x180010f9c  mov     rax, cs:__security_cookie
0x180010fa3  xor     rax, rsp
0x180010fa6  mov     [rbp+57h+var_40], rax
0x180010faa  mov     r15, [rcx+28h]
0x180010fae  mov     rsi, r8
0x180010fb1  mov     r13, rdx
0x180010fb4  mov     [rbp+57h+var_C8], rcx
0x180010fb8  mov     r12, rcx
0x180010fbb  mov     [rbp+57h+var_D0], 0
0x180010fc2  mov     r8d, 40h ; '@'
0x180010fc8  lea     rdx, [rbp+57h+var_80]
0x180010fcc  lea     rcx, [rbp+57h+var_C0]
0x180010fd0  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180010fd7  nop     dword ptr [rax+rax+00h]
0x180010fdc  test    r13, r13
0x180010fdf  jz      short loc_18001104F
0x180010fe1  mov     rcx, r13; char *
0x180010fe4  call    ?GetIndex@REQUEST_HEADER_HASH@@SAKPEBD@Z; REQUEST_HEADER_HASH::GetIndex(char const *)
0x180010fe9  cmp     eax, 0FFFFFFFFh
0x180010fec  jnz     loc_180011183
0x180010ff2  xor     ebx, ebx
0x180010ff4  xor     r14d, r14d
0x180010ff7  xor     edi, edi
0x180010ff9  movzx   eax, word ptr [r15+78h]
0x180010ffe  cmp     edi, eax
0x180011000  jb      short loc_180011063
0x180011002  test    r14d, r14d
0x180011005  jnz     loc_18001111F
0x18001100b  test    rsi, rsi
0x18001100e  jnz     loc_180011177
0x180011014  lea     rcx, [rbp+57h+var_C0]
0x180011018  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001101f  nop     dword ptr [rax+rax+00h]
0x180011024  mov     rax, rbx
0x180011027  mov     rcx, [rbp+57h+var_40]
0x18001102b  xor     rcx, rsp; StackCookie
0x18001102e  call    __security_check_cookie
0x180011033  mov     rbx, [rsp+0F0h+arg_18]
0x18001103b  add     rsp, 0C0h
0x180011042  pop     r15
0x180011044  pop     r14
0x180011046  pop     r13
0x180011048  pop     r12
0x18001104a  pop     rdi
0x18001104b  pop     rsi
0x18001104c  pop     rbp
0x18001104d  retn
0x18001104f  lea     rcx, [rbp+57h+var_C0]
0x180011053  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001105a  nop     dword ptr [rax+rax+00h]
0x18001105f  xor     eax, eax
0x180011061  jmp     short loc_180011027
0x180011063  mov     rdx, [r15+80h]
0x18001106a  lea     r12, [rdi+rdi*2]
0x18001106e  mov     rcx, r13; String1
0x180011071  mov     rdx, [rdx+r12*8+8]; String2
0x180011076  call    cs:__imp__stricmp
0x18001107d  nop     dword ptr [rax+rax+00h]
0x180011082  test    eax, eax
0x180011084  jnz     loc_180011118
0x18001108a  test    rbx, rbx
0x18001108d  jnz     short loc_1800110A6
0x18001108f  mov     rax, [r15+80h]
0x180011096  mov     rbx, [rax+r12*8+10h]
0x18001109b  movzx   eax, word ptr [rax+r12*8+2]
0x1800110a1  mov     [rbp+57h+var_D0], eax
0x1800110a4  jmp     short loc_180011118
0x1800110a6  test    r14d, r14d
0x1800110a9  jnz     short loc_1800110C6
0x1800110ab  mov     r8d, [rbp+57h+var_D0]
0x1800110af  lea     rcx, [rbp+57h+var_C0]
0x1800110b3  mov     rdx, rbx
0x1800110b6  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x1800110bd  nop     dword ptr [rax+rax+00h]
0x1800110c2  test    eax, eax
0x1800110c4  js      short loc_18001104F
0x1800110c6  mov     r14d, 1
0x1800110cc  lea     rdx, asc_18003C188; ","
0x1800110d3  mov     r8d, r14d
0x1800110d6  lea     rcx, [rbp+57h+var_C0]
0x1800110da  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x1800110e1  nop     dword ptr [rax+rax+00h]
0x1800110e6  test    eax, eax
0x1800110e8  js      loc_18001104F
0x1800110ee  mov     rdx, [r15+80h]
0x1800110f5  lea     rcx, [rbp+57h+var_C0]
0x1800110f9  movzx   r8d, word ptr [rdx+r12*8+2]
0x1800110ff  mov     rdx, [rdx+r12*8+10h]
0x180011104  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18001110b  nop     dword ptr [rax+rax+00h]
0x180011110  test    eax, eax
0x180011112  js      loc_18001104F
0x180011118  inc     edi
0x18001111a  jmp     loc_180010FF9
0x18001111f  lea     rcx, [rbp+57h+var_C0]
0x180011123  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18001112a  nop     dword ptr [rax+rax+00h]
0x18001112f  mov     rcx, [rbp+57h+var_C8]
0x180011133  lea     edx, [rax+1]
0x180011136  mov     rcx, [rcx+70h]
0x18001113a  mov     [rbp+57h+var_D0], edx
0x18001113d  mov     rax, [rcx]
0x180011140  mov     rax, [rax+90h]
0x180011147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001114c  mov     rbx, rax
0x18001114f  test    rax, rax
0x180011152  jz      loc_18001104F
0x180011158  lea     r8, [rbp+57h+var_D0]
0x18001115c  mov     rdx, rax
0x18001115f  lea     rcx, [rbp+57h+var_C0]
0x180011163  call    cs:__imp_?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z; STRA::CopyToBuffer(char *,ulong *)
0x18001116a  nop     dword ptr [rax+rax+00h]
0x18001116f  dec     [rbp+57h+var_D0]
0x180011172  jmp     loc_18001100B
0x180011177  movzx   ecx, word ptr [rbp+57h+var_D0]
0x18001117b  mov     [rsi], cx
0x18001117e  jmp     loc_180011014
0x180011183  mov     r8, rsi; unsigned __int16 *
0x180011186  mov     edx, eax; enum _HTTP_HEADER_ID
0x180011188  mov     rcx, r12; this
0x18001118b  call    ?QueryHeader@W3_REQUEST@@QEBAPEBDW4_HTTP_HEADER_ID@@PEAG@Z; W3_REQUEST::QueryHeader(_HTTP_HEADER_ID,ushort *)
0x180011190  mov     rbx, rax
0x180011193  jmp     loc_180011014
```
