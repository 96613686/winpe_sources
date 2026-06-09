# ATL::CComBSTR::Append(ushort const *,int)

- ea: `0x180015d44`
- end: `0x180015e0f`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBGH@Z`
- size: `203`
- prototype: `__int64 __fastcall(const void **this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015d1c`

## callees

- `0x1800096a8`
- `0x180015d44`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180015db9`
- `msvcrt!memcpy_s` at `0x180015dd6`
- `msvcrt!memcpy_s` at `0x180015db9`
- `msvcrt!memcpy_s` at `0x180015dd6`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180015d8c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180015d8c`
- `OLEAUT32!__imp_SysFreeString` at `0x180015df0`
- `OLEAUT32!__imp_SysFreeString` at `0x180015df0`
- `OLEAUT32!__imp_SysStringLen` at `0x180015d74`
- `OLEAUT32!__imp_SysStringLen` at `0x180015d9d`
- `OLEAUT32!__imp_SysStringLen` at `0x180015d74`
- `OLEAUT32!__imp_SysStringLen` at `0x180015d9d`

## pseudocode

```c
__int64 __fastcall ATL::CComBSTR::Append(const void **this, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rbp
  OLECHAR *v6; // rcx
  signed int v7; // eax
  __int64 v8; // rsi
  signed int v9; // edi
  BSTR v10; // r14
  errno_t v11; // eax
  errno_t v12; // eax

  v3 = a3;
  if ( !a2 )
    return 0;
  v6 = (OLECHAR *)*this;
  if ( v6 )
  {
    if ( !a3 )
      return 0;
  }
  v7 = SysStringLen(v6);
  v8 = v7;
  v9 = v7 + v3;
  if ( v7 + (int)v3 >= v7 )
  {
    v10 = SysAllocStringLen(0, v9);
    if ( v10 )
    {
      if ( SysStringLen((BSTR)*this) )
      {
        v11 = memcpy_s(v10, 2LL * v9, *this, 2 * v8);
        ATL::AtlCrtErrorCheck(v11);
      }
      v12 = memcpy_s(&v10[v8], 2 * v3, a2, 2 * v3);
      ATL::AtlCrtErrorCheck(v12);
      v10[v9] = 0;
      SysFreeString((BSTR)*this);
      *this = v10;
      return 0;
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180015d44  push    rbx
0x180015d46  push    rbp
0x180015d47  push    rsi
0x180015d48  push    rdi
0x180015d49  push    r14
0x180015d4b  push    r15
0x180015d4d  sub     rsp, 28h
0x180015d51  movsxd  rbp, r8d
0x180015d54  mov     r15, rdx
0x180015d57  mov     rbx, rcx
0x180015d5a  test    rdx, rdx
0x180015d5d  jz      loc_180015DF9
0x180015d63  mov     rcx, [rcx]; pbstr
0x180015d66  test    rcx, rcx
0x180015d69  jz      short loc_180015D74
0x180015d6b  test    r8d, r8d
0x180015d6e  jz      loc_180015DF9
0x180015d74  call    cs:__imp_SysStringLen
0x180015d7a  movsxd  rsi, eax
0x180015d7d  lea     edi, [rsi+rbp]
0x180015d80  cmp     edi, esi
0x180015d82  jl      loc_180015E08
0x180015d88  mov     edx, edi; ui
0x180015d8a  xor     ecx, ecx; strIn
0x180015d8c  call    cs:__imp_SysAllocStringLen
0x180015d92  mov     r14, rax
0x180015d95  test    rax, rax
0x180015d98  jz      short loc_180015E08
0x180015d9a  mov     rcx, [rbx]; pbstr
0x180015d9d  call    cs:__imp_SysStringLen
0x180015da3  test    eax, eax
0x180015da5  jz      short loc_180015DC6
0x180015da7  mov     r9, rsi
0x180015daa  add     r9, r9; SourceSize
0x180015dad  movsxd  rdx, edi
0x180015db0  add     rdx, rdx; DestinationSize
0x180015db3  mov     r8, [rbx]; Source
0x180015db6  mov     rcx, r14; Destination
0x180015db9  call    cs:__imp_memcpy_s
0x180015dbf  mov     ecx, eax; int
0x180015dc1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180015dc6  mov     rdx, rbp
0x180015dc9  add     rdx, rdx; DestinationSize
0x180015dcc  lea     rcx, [r14+rsi*2]; Destination
0x180015dd0  mov     r9, rdx; SourceSize
0x180015dd3  mov     r8, r15; Source
0x180015dd6  call    cs:__imp_memcpy_s
0x180015ddc  mov     ecx, eax; int
0x180015dde  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180015de3  movsxd  rcx, edi
0x180015de6  xor     eax, eax
0x180015de8  mov     [r14+rcx*2], ax
0x180015ded  mov     rcx, [rbx]; bstrString
0x180015df0  call    cs:__imp_SysFreeString
0x180015df6  mov     [rbx], r14
0x180015df9  xor     eax, eax
0x180015dfb  add     rsp, 28h
0x180015dff  pop     r15
0x180015e01  pop     r14
0x180015e03  pop     rdi
0x180015e04  pop     rsi
0x180015e05  pop     rbp
0x180015e06  pop     rbx
0x180015e07  retn
0x180015e08  mov     eax, 8007000Eh
0x180015e0d  jmp     short loc_180015DFB
```
