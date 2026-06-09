# Dfdll::CVariantArray::Add(ushort const *)

- ea: `0x180001e84`
- end: `0x180001f36`
- name: `?Add@CVariantArray@Dfdll@@QEAAJPEBG@Z`
- size: `178`
- prototype: `__int64 __fastcall(Dfdll::CVariantArray *__hidden this, OLECHAR *psz)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002720`
- `0x180005010`
- `0x180005130`
- `0x180005400`
- `0x180007640`

## callees

- `0x180001e84`
- `0x180001f38`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180001ebb`
- `OLEAUT32!__imp_SysAllocString` at `0x180001ebb`
- `OLEAUT32!__imp_SysFreeString` at `0x180001eac`
- `OLEAUT32!__imp_SysFreeString` at `0x180001eda`
- `OLEAUT32!__imp_SysFreeString` at `0x180001eff`
- `OLEAUT32!__imp_SysFreeString` at `0x180001f1d`
- `OLEAUT32!__imp_SysFreeString` at `0x180001eac`
- `OLEAUT32!__imp_SysFreeString` at `0x180001eda`
- `OLEAUT32!__imp_SysFreeString` at `0x180001eff`
- `OLEAUT32!__imp_SysFreeString` at `0x180001f1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CVariantArray::Add(Dfdll::CVariantArray *this, OLECHAR *psz)
{
  BSTR v4; // rax
  OLECHAR *v5; // rdi
  int v6; // ebx
  struct tagVARIANT *v7; // rax
  struct tagVARIANT *v9; // [rsp+48h] [rbp+10h] BYREF

  SysFreeString(0);
  v4 = SysAllocString(psz);
  v5 = v4;
  if ( !psz || v4 )
  {
    v9 = 0;
    v6 = Dfdll::CVariantArray::AddNewItem(this, &v9);
    if ( v6 >= 0 )
    {
      v7 = v9;
      v9->vt = 8;
      v7->llVal = (LONGLONG)v5;
      v6 = 0;
      SysFreeString(0);
    }
    else
    {
      SysFreeString(v5);
    }
  }
  else
  {
    v6 = -2147024882;
    SysFreeString(0);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180001e84  mov     r11, rsp
0x180001e87  mov     [r11+8], rbx
0x180001e8b  mov     [r11+18h], rsi
0x180001e8f  push    rdi
0x180001e90  sub     rsp, 30h
0x180001e94  mov     rbx, rdx
0x180001e97  mov     rsi, rcx
0x180001e9a  lea     rax, ??_7CBSTR@Dfdll@@6B@; const Dfdll::CBSTR::`vftable'
0x180001ea1  mov     [r11-18h], rax
0x180001ea5  and     qword ptr [r11-10h], 0
0x180001eaa  xor     ecx, ecx; bstrString
0x180001eac  call    cs:__imp_SysFreeString
0x180001eb2  and     [rsp+38h+var_10], 0
0x180001eb8  mov     rcx, rbx; psz
0x180001ebb  call    cs:__imp_SysAllocString
0x180001ec1  mov     rdi, rax
0x180001ec4  mov     [rsp+38h+var_10], rax
0x180001ec9  test    rbx, rbx
0x180001ecc  jz      short loc_180001EE3
0x180001ece  test    rax, rax
0x180001ed1  jnz     short loc_180001EE3
0x180001ed3  mov     ebx, 8007000Eh
0x180001ed8  xor     ecx, ecx; bstrString
0x180001eda  call    cs:__imp_SysFreeString
0x180001ee0  nop
0x180001ee1  jmp     short loc_180001F24
0x180001ee3  and     [rsp+38h+arg_8], 0
0x180001ee9  lea     rdx, [rsp+38h+arg_8]; struct tagVARIANT **
0x180001eee  mov     rcx, rsi; this
0x180001ef1  call    ?AddNewItem@CVariantArray@Dfdll@@IEAAJAEAPEAUtagVARIANT@@@Z; Dfdll::CVariantArray::AddNewItem(tagVARIANT * &)
0x180001ef6  mov     ebx, eax
0x180001ef8  test    eax, eax
0x180001efa  jns     short loc_180001F08
0x180001efc  mov     rcx, rdi; bstrString
0x180001eff  call    cs:__imp_SysFreeString
0x180001f05  nop
0x180001f06  jmp     short loc_180001F24
0x180001f08  mov     ecx, 8
0x180001f0d  mov     rax, [rsp+38h+arg_8]
0x180001f12  mov     [rax], cx
0x180001f15  mov     [rax+8], rdi
0x180001f19  xor     ebx, ebx
0x180001f1b  xor     ecx, ecx; bstrString
0x180001f1d  call    cs:__imp_SysFreeString
0x180001f23  nop
0x180001f24  mov     eax, ebx
0x180001f26  mov     rbx, [rsp+38h+arg_0]
0x180001f2b  mov     rsi, [rsp+38h+arg_10]
0x180001f30  add     rsp, 30h
0x180001f34  pop     rdi
0x180001f35  retn
```
