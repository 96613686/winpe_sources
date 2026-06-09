# CArguments::CreateRuntimeUnnamedNode(ushort *,ushort *,int,ulong)

- ea: `0x140013e64`
- end: `0x140013f31`
- name: `?CreateRuntimeUnnamedNode@CArguments@@AEAAPEAURuntimeNode@@PEAG0HK@Z`
- size: `205`
- prototype: `struct RuntimeNode *(CArguments *__hidden this, unsigned __int16 *, unsigned __int16 *, int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012ec0`

## callees

- `0x140009dab`
- `0x140009dc3`
- `0x140013e64`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140013eb7`
- `OLEAUT32!__imp_SysAllocString` at `0x140013edc`
- `OLEAUT32!__imp_SysAllocString` at `0x140013eb7`
- `OLEAUT32!__imp_SysAllocString` at `0x140013edc`
- `OLEAUT32!__imp_SysFreeString` at `0x140013ef7`
- `OLEAUT32!__imp_SysFreeString` at `0x140013f05`
- `OLEAUT32!__imp_SysFreeString` at `0x140013ef7`
- `OLEAUT32!__imp_SysFreeString` at `0x140013f05`
- `OLEAUT32!__imp_SysStringLen` at `0x140013eaa`
- `OLEAUT32!__imp_SysStringLen` at `0x140013ecf`
- `OLEAUT32!__imp_SysStringLen` at `0x140013eaa`
- `OLEAUT32!__imp_SysStringLen` at `0x140013ecf`

## pseudocode

```c
struct RuntimeNode *__fastcall CArguments::CreateRuntimeUnnamedNode(
        CArguments *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned int a5)
{
  void *v8; // rbx
  struct RuntimeNode *result; // rax
  BSTR v10; // rax
  OLECHAR *v11; // rdi
  BSTR v12; // rax
  OLECHAR *v13; // rcx

  v8 = malloc_0(0x28u);
  if ( !v8 )
    return 0;
  *(_OWORD *)v8 = 0;
  *((_OWORD *)v8 + 1) = 0;
  *((_QWORD *)v8 + 4) = 0;
  *(_DWORD *)v8 = 1;
  if ( SysStringLen(a2) )
  {
    v10 = SysAllocString(a2);
    *((_QWORD *)v8 + 2) = v10;
    if ( !v10 )
    {
      v11 = (OLECHAR *)*((_QWORD *)v8 + 3);
LABEL_8:
      v13 = (OLECHAR *)*((_QWORD *)v8 + 2);
      if ( v13 )
        SysFreeString(v13);
      if ( v11 )
        SysFreeString(v11);
      free_0(v8);
      return 0;
    }
  }
  if ( SysStringLen(a3) )
  {
    v12 = SysAllocString(a3);
    *((_QWORD *)v8 + 3) = v12;
    v11 = v12;
    if ( !v12 )
      goto LABEL_8;
  }
  *((_DWORD *)v8 + 8) = a5;
  result = (struct RuntimeNode *)v8;
  *((_DWORD *)v8 + 9) = a4;
  return result;
}

```

## disassembly

```asm
0x140013e64  push    rbx
0x140013e66  push    rbp
0x140013e67  push    rsi
0x140013e68  push    rdi
0x140013e69  push    r14
0x140013e6b  sub     rsp, 20h
0x140013e6f  mov     ecx, 28h ; '('; Size
0x140013e74  mov     r14d, r9d
0x140013e77  mov     rdi, r8
0x140013e7a  mov     rbp, rdx
0x140013e7d  call    malloc_0
0x140013e82  mov     rbx, rax
0x140013e85  test    rax, rax
0x140013e88  jnz     short loc_140013E91
0x140013e8a  xor     eax, eax
0x140013e8c  jmp     loc_140013F26
0x140013e91  xorps   xmm0, xmm0
0x140013e94  xor     eax, eax
0x140013e96  movups  xmmword ptr [rbx], xmm0
0x140013e99  mov     rcx, rbp; pbstr
0x140013e9c  movups  xmmword ptr [rbx+10h], xmm0
0x140013ea0  mov     [rbx+20h], rax
0x140013ea4  mov     dword ptr [rbx], 1
0x140013eaa  call    cs:__imp_SysStringLen
0x140013eb0  test    eax, eax
0x140013eb2  jz      short loc_140013ECC
0x140013eb4  mov     rcx, rbp; psz
0x140013eb7  call    cs:__imp_SysAllocString
0x140013ebd  mov     [rbx+10h], rax
0x140013ec1  test    rax, rax
0x140013ec4  jnz     short loc_140013ECC
0x140013ec6  mov     rdi, [rbx+18h]
0x140013eca  jmp     short loc_140013EEE
0x140013ecc  mov     rcx, rdi; pbstr
0x140013ecf  call    cs:__imp_SysStringLen
0x140013ed5  test    eax, eax
0x140013ed7  jz      short loc_140013F18
0x140013ed9  mov     rcx, rdi; psz
0x140013edc  call    cs:__imp_SysAllocString
0x140013ee2  mov     [rbx+18h], rax
0x140013ee6  mov     rdi, rax
0x140013ee9  test    rax, rax
0x140013eec  jnz     short loc_140013F18
0x140013eee  mov     rcx, [rbx+10h]; bstrString
0x140013ef2  test    rcx, rcx
0x140013ef5  jz      short loc_140013EFD
0x140013ef7  call    cs:__imp_SysFreeString
0x140013efd  test    rdi, rdi
0x140013f00  jz      short loc_140013F0B
0x140013f02  mov     rcx, rdi; bstrString
0x140013f05  call    cs:__imp_SysFreeString
0x140013f0b  mov     rcx, rbx; Block
0x140013f0e  call    free_0
0x140013f13  jmp     loc_140013E8A
0x140013f18  mov     eax, [rsp+48h+arg_20]
0x140013f1c  mov     [rbx+20h], eax
0x140013f1f  mov     rax, rbx
0x140013f22  mov     [rbx+24h], r14d
0x140013f26  add     rsp, 20h
0x140013f2a  pop     r14
0x140013f2c  pop     rdi
0x140013f2d  pop     rsi
0x140013f2e  pop     rbp
0x140013f2f  pop     rbx
0x140013f30  retn
```
