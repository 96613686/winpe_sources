# ATL::CComBSTR::Append(ushort const *)

- ea: `0x180018da4`
- end: `0x180018ecd`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBG@Z`
- size: `297`
- prototype: `__int64 __fastcall(const void **this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a104`

## callees

- `0x180005688`
- `0x180018da4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180018e3a`
- `msvcrt!memcpy_s` at `0x180018e68`
- `msvcrt!memcpy_s` at `0x180018e3a`
- `msvcrt!memcpy_s` at `0x180018e68`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180018e0d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180018e0d`
- `OLEAUT32!__imp_SysFreeString` at `0x180018e91`
- `OLEAUT32!__imp_SysFreeString` at `0x180018e91`
- `OLEAUT32!__imp_SysStringLen` at `0x180018ded`
- `OLEAUT32!__imp_SysStringLen` at `0x180018e1e`
- `OLEAUT32!__imp_SysStringLen` at `0x180018ded`
- `OLEAUT32!__imp_SysStringLen` at `0x180018e1e`

## pseudocode

```c
__int64 __fastcall ATL::CComBSTR::Append(const void **this, const unsigned __int16 *a2)
{
  __int64 v4; // rbx
  OLECHAR *v5; // rcx
  signed int v6; // eax
  __int64 v7; // r15
  signed int v8; // ebp
  BSTR v10; // r14
  errno_t v11; // eax
  errno_t v12; // eax

  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
  }
  else
  {
    LODWORD(v4) = 0;
  }
  if ( !a2 )
    return 0;
  v5 = (OLECHAR *)*this;
  if ( v5 )
  {
    if ( !(_DWORD)v4 )
      return 0;
  }
  v6 = SysStringLen(v5);
  v7 = v6;
  v8 = v6 + v4;
  if ( v6 + (int)v4 < v6 )
    return 2147942414LL;
  v10 = SysAllocStringLen(0, v8);
  if ( !v10 )
    return 2147942414LL;
  if ( SysStringLen((BSTR)*this) )
  {
    v11 = memcpy_s(v10, 2LL * v8, *this, 2 * v7);
    if ( v11 )
    {
      if ( v11 == 12 )
        goto LABEL_24;
      if ( v11 == 22 || v11 == 34 )
        goto LABEL_26;
      if ( v11 != 80 )
        goto LABEL_25;
    }
  }
  v12 = memcpy_s(&v10[v7], 2LL * (int)v4, a2, 2LL * (int)v4);
  if ( v12 )
  {
    if ( v12 != 12 )
    {
      if ( v12 != 22 && v12 != 34 )
      {
        if ( v12 == 80 )
          goto LABEL_22;
LABEL_25:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_26:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_24:
    ATL::AtlThrowImpl(-2147024882);
  }
LABEL_22:
  v10[v8] = 0;
  SysFreeString((BSTR)*this);
  *this = v10;
  return 0;
}

```

## disassembly

```asm
0x180018da4  push    rbx
0x180018da6  push    rbp
0x180018da7  push    rsi
0x180018da8  push    rdi
0x180018da9  push    r12
0x180018dab  push    r14
0x180018dad  push    r15
0x180018daf  sub     rsp, 20h
0x180018db3  mov     rsi, rdx
0x180018db6  mov     rdi, rcx
0x180018db9  xor     r12d, r12d
0x180018dbc  test    rdx, rdx
0x180018dbf  jnz     short loc_180018DC6
0x180018dc1  mov     ebx, r12d
0x180018dc4  jmp     short loc_180018DD4
0x180018dc6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018dca  inc     rbx
0x180018dcd  cmp     [rdx+rbx*2], r12w
0x180018dd2  jnz     short loc_180018DCA
0x180018dd4  test    rsi, rsi
0x180018dd7  jz      loc_180018E9A
0x180018ddd  mov     rcx, [rcx]; pbstr
0x180018de0  test    rcx, rcx
0x180018de3  jz      short loc_180018DED
0x180018de5  test    ebx, ebx
0x180018de7  jz      loc_180018E9A
0x180018ded  call    cs:__imp_SysStringLen
0x180018df3  movsxd  r15, eax
0x180018df6  lea     ebp, [r15+rbx]
0x180018dfa  cmp     ebp, r15d
0x180018dfd  jge     short loc_180018E09
0x180018dff  mov     eax, 8007000Eh
0x180018e04  jmp     loc_180018E9D
0x180018e09  mov     edx, ebp; ui
0x180018e0b  xor     ecx, ecx; strIn
0x180018e0d  call    cs:__imp_SysAllocStringLen
0x180018e13  mov     r14, rax
0x180018e16  test    rax, rax
0x180018e19  jz      short loc_180018DFF
0x180018e1b  mov     rcx, [rdi]; pbstr
0x180018e1e  call    cs:__imp_SysStringLen
0x180018e24  test    eax, eax
0x180018e26  jz      short loc_180018E58
0x180018e28  mov     r9, r15
0x180018e2b  add     r9, r9; SourceSize
0x180018e2e  movsxd  rdx, ebp
0x180018e31  add     rdx, rdx; DestinationSize
0x180018e34  mov     r8, [rdi]; Source
0x180018e37  mov     rcx, r14; Destination
0x180018e3a  call    cs:__imp_memcpy_s
0x180018e40  test    eax, eax
0x180018e42  jz      short loc_180018E58
0x180018e44  cmp     eax, 0Ch
0x180018e47  jz      short loc_180018EAC
0x180018e49  cmp     eax, 16h
0x180018e4c  jz      short loc_180018EC2
0x180018e4e  cmp     eax, 22h ; '"'
0x180018e51  jz      short loc_180018EC2
0x180018e53  cmp     eax, 50h ; 'P'
0x180018e56  jnz     short loc_180018EB7
0x180018e58  movsxd  rdx, ebx
0x180018e5b  add     rdx, rdx; DestinationSize
0x180018e5e  lea     rcx, [r14+r15*2]; Destination
0x180018e62  mov     r9, rdx; SourceSize
0x180018e65  mov     r8, rsi; Source
0x180018e68  call    cs:__imp_memcpy_s
0x180018e6e  test    eax, eax
0x180018e70  jz      short loc_180018E86
0x180018e72  cmp     eax, 0Ch
0x180018e75  jz      short loc_180018EAC
0x180018e77  cmp     eax, 16h
0x180018e7a  jz      short loc_180018EC2
0x180018e7c  cmp     eax, 22h ; '"'
0x180018e7f  jz      short loc_180018EC2
0x180018e81  cmp     eax, 50h ; 'P'
0x180018e84  jnz     short loc_180018EB7
0x180018e86  movsxd  rcx, ebp
0x180018e89  mov     [r14+rcx*2], r12w
0x180018e8e  mov     rcx, [rdi]; bstrString
0x180018e91  call    cs:__imp_SysFreeString
0x180018e97  mov     [rdi], r14
0x180018e9a  mov     eax, r12d
0x180018e9d  add     rsp, 20h
0x180018ea1  pop     r15
0x180018ea3  pop     r14
0x180018ea5  pop     r12
0x180018ea7  pop     rdi
0x180018ea8  pop     rsi
0x180018ea9  pop     rbp
0x180018eaa  pop     rbx
0x180018eab  retn
0x180018eac  mov     ecx, 8007000Eh; int
0x180018eb1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180018eb7  mov     ecx, 80004005h; int
0x180018ebc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180018ec2  mov     ecx, 80070057h; int
0x180018ec7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
