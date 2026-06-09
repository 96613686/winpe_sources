# ATL::CComBSTR::Append(ushort const *,int)

- ea: `0x180014f8c`
- end: `0x180015036`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBGH@Z`
- size: `170`
- prototype: `int(ATL::CComBSTR *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014f64`

## callees

- `0x180014f8c`
- `0x18002e0b2`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180014fd1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180014fd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180015017`
- `OLEAUT32!__imp_SysFreeString` at `0x180015017`
- `OLEAUT32!__imp_SysStringLen` at `0x180014fbe`
- `OLEAUT32!__imp_SysStringLen` at `0x180014fbe`

## pseudocode

```c
__int64 __fastcall ATL::CComBSTR::Append(const void **this, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  OLECHAR *v7; // rcx
  signed int v8; // ebx
  signed int v9; // ebp
  BSTR v10; // rax
  BSTR v11; // r14

  v3 = a3;
  if ( !a2 )
    return a3 != 0 ? 0x80070057 : 0;
  v7 = (OLECHAR *)*this;
  if ( v7 )
    v8 = SysStringLen(v7);
  else
    v8 = 0;
  v9 = v8 + v3;
  if ( v8 + (int)v3 < v8 )
    return 2147942414LL;
  v10 = SysAllocStringLen(0, v9);
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  if ( *this )
    memcpy_0(v10, *this, 2LL * v8);
  memcpy_0(&v11[v8], a2, 2 * v3);
  v11[v9] = 0;
  SysFreeString((BSTR)*this);
  result = 0;
  *this = v11;
  return result;
}

```

## disassembly

```asm
0x180014f8c  push    rbx
0x180014f8e  push    rbp
0x180014f8f  push    rsi
0x180014f90  push    rdi
0x180014f91  push    r14
0x180014f93  push    r15
0x180014f95  sub     rsp, 28h
0x180014f99  movsxd  rdi, r8d
0x180014f9c  mov     r15, rdx
0x180014f9f  mov     rsi, rcx
0x180014fa2  test    rdx, rdx
0x180014fa5  jnz     short loc_180014FB2
0x180014fa7  neg     edi
0x180014fa9  sbb     eax, eax
0x180014fab  and     eax, 80070057h
0x180014fb0  jmp     short loc_180015029
0x180014fb2  mov     rcx, [rcx]; pbstr
0x180014fb5  test    rcx, rcx
0x180014fb8  jnz     short loc_180014FBE
0x180014fba  xor     ebx, ebx
0x180014fbc  jmp     short loc_180014FC6
0x180014fbe  call    cs:__imp_SysStringLen
0x180014fc4  mov     ebx, eax
0x180014fc6  lea     ebp, [rbx+rdi]
0x180014fc9  cmp     ebp, ebx
0x180014fcb  jl      short loc_180015024
0x180014fcd  mov     edx, ebp; ui
0x180014fcf  xor     ecx, ecx; strIn
0x180014fd1  call    cs:__imp_SysAllocStringLen
0x180014fd7  mov     r14, rax
0x180014fda  test    rax, rax
0x180014fdd  jz      short loc_180015024
0x180014fdf  mov     rdx, [rsi]; Src
0x180014fe2  test    rdx, rdx
0x180014fe5  jz      short loc_180014FF5
0x180014fe7  movsxd  r8, ebx
0x180014fea  mov     rcx, rax; void *
0x180014fed  add     r8, r8; Size
0x180014ff0  call    memcpy_0
0x180014ff5  movsxd  rax, ebx
0x180014ff8  mov     r8, rdi
0x180014ffb  add     r8, r8; Size
0x180014ffe  mov     rdx, r15; Src
0x180015001  lea     rcx, [r14+rax*2]; void *
0x180015005  call    memcpy_0
0x18001500a  movsxd  rcx, ebp
0x18001500d  xor     eax, eax
0x18001500f  mov     [r14+rcx*2], ax
0x180015014  mov     rcx, [rsi]; bstrString
0x180015017  call    cs:__imp_SysFreeString
0x18001501d  xor     eax, eax
0x18001501f  mov     [rsi], r14
0x180015022  jmp     short loc_180015029
0x180015024  mov     eax, 8007000Eh
0x180015029  add     rsp, 28h
0x18001502d  pop     r15
0x18001502f  pop     r14
0x180015031  pop     rdi
0x180015032  pop     rsi
0x180015033  pop     rbp
0x180015034  pop     rbx
0x180015035  retn
```
