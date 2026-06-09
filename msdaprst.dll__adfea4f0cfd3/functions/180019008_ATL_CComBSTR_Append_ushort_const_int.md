# ATL::CComBSTR::Append(ushort const *,int)

- ea: `0x180019008`
- end: `0x1800190b5`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBGH@Z`
- size: `173`
- prototype: `int(ATL::CComBSTR *__hidden this, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024200`
- `0x180026dc0`
- `0x180027d24`
- `0x180028a9c`

## callees

- `0x180019008`
- `0x18002f092`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001904b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001904b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001908f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001908f`
- `OLEAUT32!__imp_SysStringLen` at `0x180019031`
- `OLEAUT32!__imp_SysStringLen` at `0x180019031`

## pseudocode

```c
__int64 __fastcall ATL::CComBSTR::Append(BSTR *this, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  signed int v7; // eax
  size_t v8; // rbx
  signed int v9; // esi
  BSTR v10; // rax
  OLECHAR *v11; // r14
  size_t v12; // rbx

  v3 = a3;
  if ( !a2 )
    return a3 != 0 ? 0x80070057 : 0;
  v7 = SysStringLen(*this);
  v8 = v7;
  v9 = v7 + v3;
  if ( v7 + (int)v3 < v7 )
    return 2147942414LL;
  v10 = SysAllocStringLen(0, v9);
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  v12 = v8;
  memcpy_0(v10, *this, v12 * 2);
  memcpy_0(&v11[v12], a2, 2 * v3);
  v11[v9] = 0;
  SysFreeString(*this);
  result = 0;
  *this = v11;
  return result;
}

```

## disassembly

```asm
0x180019008  push    rbx
0x18001900a  push    rbp
0x18001900b  push    rsi
0x18001900c  push    rdi
0x18001900d  push    r14
0x18001900f  push    r15
0x180019011  sub     rsp, 28h
0x180019015  movsxd  rdi, r8d
0x180019018  mov     rbp, rdx
0x18001901b  mov     r15, rcx
0x18001901e  test    rdx, rdx
0x180019021  jnz     short loc_18001902E
0x180019023  neg     edi
0x180019025  sbb     eax, eax
0x180019027  and     eax, 80070057h
0x18001902c  jmp     short loc_1800190A7
0x18001902e  mov     rcx, [rcx]; pbstr
0x180019031  call    cs:__imp_SysStringLen
0x180019038  nop     dword ptr [rax+rax+00h]
0x18001903d  movsxd  rbx, eax
0x180019040  lea     esi, [rbx+rdi]
0x180019043  cmp     esi, ebx
0x180019045  jl      short loc_1800190A2
0x180019047  mov     edx, esi; ui
0x180019049  xor     ecx, ecx; strIn
0x18001904b  call    cs:__imp_SysAllocStringLen
0x180019052  nop     dword ptr [rax+rax+00h]
0x180019057  mov     r14, rax
0x18001905a  test    rax, rax
0x18001905d  jz      short loc_1800190A2
0x18001905f  mov     rdx, [r15]; Src
0x180019062  add     rbx, rbx
0x180019065  mov     r8, rbx; Size
0x180019068  mov     rcx, rax; void *
0x18001906b  call    memcpy_0
0x180019070  mov     r8, rdi
0x180019073  lea     rcx, [rbx+r14]; void *
0x180019077  add     r8, r8; Size
0x18001907a  mov     rdx, rbp; Src
0x18001907d  call    memcpy_0
0x180019082  movsxd  rcx, esi
0x180019085  xor     eax, eax
0x180019087  mov     [r14+rcx*2], ax
0x18001908c  mov     rcx, [r15]; bstrString
0x18001908f  call    cs:__imp_SysFreeString
0x180019096  nop     dword ptr [rax+rax+00h]
0x18001909b  xor     eax, eax
0x18001909d  mov     [r15], r14
0x1800190a0  jmp     short loc_1800190A7
0x1800190a2  mov     eax, 8007000Eh
0x1800190a7  add     rsp, 28h
0x1800190ab  pop     r15
0x1800190ad  pop     r14
0x1800190af  pop     rdi
0x1800190b0  pop     rsi
0x1800190b1  pop     rbp
0x1800190b2  pop     rbx
0x1800190b3  retn
```
