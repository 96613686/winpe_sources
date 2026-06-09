# ATL::CComBSTR::Append(ushort const *,int)

- ea: `0x140005a30`
- end: `0x140005afb`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBGH@Z`
- size: `203`
- prototype: `int(ATL::CComBSTR *__hidden this, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005a08`
- `0x1400118d0`
- `0x140011d2c`

## callees

- `0x140005a30`
- `0x140005b04`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140005aa5`
- `msvcrt!memcpy_s` at `0x140005ac2`
- `msvcrt!memcpy_s` at `0x140005aa5`
- `msvcrt!memcpy_s` at `0x140005ac2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140005a78`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140005a78`
- `OLEAUT32!__imp_SysFreeString` at `0x140005adc`
- `OLEAUT32!__imp_SysFreeString` at `0x140005adc`
- `OLEAUT32!__imp_SysStringLen` at `0x140005a60`
- `OLEAUT32!__imp_SysStringLen` at `0x140005a89`
- `OLEAUT32!__imp_SysStringLen` at `0x140005a60`
- `OLEAUT32!__imp_SysStringLen` at `0x140005a89`

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
0x140005a30  push    rbx
0x140005a32  push    rbp
0x140005a33  push    rsi
0x140005a34  push    rdi
0x140005a35  push    r14
0x140005a37  push    r15
0x140005a39  sub     rsp, 28h
0x140005a3d  movsxd  rbp, r8d
0x140005a40  mov     r15, rdx
0x140005a43  mov     rbx, rcx
0x140005a46  test    rdx, rdx
0x140005a49  jz      loc_140005AE5
0x140005a4f  mov     rcx, [rcx]; pbstr
0x140005a52  test    rcx, rcx
0x140005a55  jz      short loc_140005A60
0x140005a57  test    r8d, r8d
0x140005a5a  jz      loc_140005AE5
0x140005a60  call    cs:__imp_SysStringLen
0x140005a66  movsxd  rsi, eax
0x140005a69  lea     edi, [rsi+rbp]
0x140005a6c  cmp     edi, esi
0x140005a6e  jl      loc_140005AF4
0x140005a74  mov     edx, edi; ui
0x140005a76  xor     ecx, ecx; strIn
0x140005a78  call    cs:__imp_SysAllocStringLen
0x140005a7e  mov     r14, rax
0x140005a81  test    rax, rax
0x140005a84  jz      short loc_140005AF4
0x140005a86  mov     rcx, [rbx]; pbstr
0x140005a89  call    cs:__imp_SysStringLen
0x140005a8f  test    eax, eax
0x140005a91  jz      short loc_140005AB2
0x140005a93  mov     r9, rsi
0x140005a96  add     r9, r9; SourceSize
0x140005a99  movsxd  rdx, edi
0x140005a9c  add     rdx, rdx; DestinationSize
0x140005a9f  mov     r8, [rbx]; Source
0x140005aa2  mov     rcx, r14; Destination
0x140005aa5  call    cs:__imp_memcpy_s
0x140005aab  mov     ecx, eax; int
0x140005aad  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140005ab2  mov     rdx, rbp
0x140005ab5  add     rdx, rdx; DestinationSize
0x140005ab8  lea     rcx, [r14+rsi*2]; Destination
0x140005abc  mov     r9, rdx; SourceSize
0x140005abf  mov     r8, r15; Source
0x140005ac2  call    cs:__imp_memcpy_s
0x140005ac8  mov     ecx, eax; int
0x140005aca  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140005acf  movsxd  rcx, edi
0x140005ad2  xor     eax, eax
0x140005ad4  mov     [r14+rcx*2], ax
0x140005ad9  mov     rcx, [rbx]; bstrString
0x140005adc  call    cs:__imp_SysFreeString
0x140005ae2  mov     [rbx], r14
0x140005ae5  xor     eax, eax
0x140005ae7  add     rsp, 28h
0x140005aeb  pop     r15
0x140005aed  pop     r14
0x140005aef  pop     rdi
0x140005af0  pop     rsi
0x140005af1  pop     rbp
0x140005af2  pop     rbx
0x140005af3  retn
0x140005af4  mov     eax, 8007000Eh
0x140005af9  jmp     short loc_140005AE7
```
