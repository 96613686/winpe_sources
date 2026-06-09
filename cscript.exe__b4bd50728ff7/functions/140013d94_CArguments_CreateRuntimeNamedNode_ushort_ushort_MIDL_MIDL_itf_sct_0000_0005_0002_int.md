# CArguments::CreateRuntimeNamedNode(ushort *,ushort *,__MIDL___MIDL_itf_sct_0000_0005_0002,int)

- ea: `0x140013d94`
- end: `0x140013e5b`
- name: `?CreateRuntimeNamedNode@CArguments@@AEAAPEAURuntimeNode@@PEAG0W4__MIDL___MIDL_itf_sct_0000_0005_0002@@H@Z`
- size: `199`
- prototype: `struct RuntimeNode *__high(unsigned __int16 *, unsigned __int16 *, enum __MIDL___MIDL_itf_sct_0000_0005_0002, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012e60`

## callees

- `0x140009dab`
- `0x140009dc3`
- `0x140013d94`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140013de1`
- `OLEAUT32!__imp_SysAllocString` at `0x140013e06`
- `OLEAUT32!__imp_SysAllocString` at `0x140013de1`
- `OLEAUT32!__imp_SysAllocString` at `0x140013e06`
- `OLEAUT32!__imp_SysFreeString` at `0x140013e21`
- `OLEAUT32!__imp_SysFreeString` at `0x140013e2f`
- `OLEAUT32!__imp_SysFreeString` at `0x140013e21`
- `OLEAUT32!__imp_SysFreeString` at `0x140013e2f`
- `OLEAUT32!__imp_SysStringLen` at `0x140013dd4`
- `OLEAUT32!__imp_SysStringLen` at `0x140013df9`
- `OLEAUT32!__imp_SysStringLen` at `0x140013dd4`
- `OLEAUT32!__imp_SysStringLen` at `0x140013df9`

## pseudocode

```c
void *__fastcall CArguments::CreateRuntimeNamedNode(__int64 a1, OLECHAR *a2, OLECHAR *a3, int a4, int a5)
{
  void *v8; // rbx
  void *result; // rax
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
  result = v8;
  *((_DWORD *)v8 + 9) = a4;
  return result;
}

```

## disassembly

```asm
0x140013d94  push    rbx
0x140013d96  push    rbp
0x140013d97  push    rsi
0x140013d98  push    rdi
0x140013d99  push    r14
0x140013d9b  sub     rsp, 20h
0x140013d9f  mov     ecx, 28h ; '('; Size
0x140013da4  mov     r14d, r9d
0x140013da7  mov     rdi, r8
0x140013daa  mov     rbp, rdx
0x140013dad  call    malloc_0
0x140013db2  mov     rbx, rax
0x140013db5  test    rax, rax
0x140013db8  jnz     short loc_140013DC1
0x140013dba  xor     eax, eax
0x140013dbc  jmp     loc_140013E50
0x140013dc1  xorps   xmm0, xmm0
0x140013dc4  xor     eax, eax
0x140013dc6  movups  xmmword ptr [rbx], xmm0
0x140013dc9  mov     rcx, rbp; pbstr
0x140013dcc  movups  xmmword ptr [rbx+10h], xmm0
0x140013dd0  mov     [rbx+20h], rax
0x140013dd4  call    cs:__imp_SysStringLen
0x140013dda  test    eax, eax
0x140013ddc  jz      short loc_140013DF6
0x140013dde  mov     rcx, rbp; psz
0x140013de1  call    cs:__imp_SysAllocString
0x140013de7  mov     [rbx+10h], rax
0x140013deb  test    rax, rax
0x140013dee  jnz     short loc_140013DF6
0x140013df0  mov     rdi, [rbx+18h]
0x140013df4  jmp     short loc_140013E18
0x140013df6  mov     rcx, rdi; pbstr
0x140013df9  call    cs:__imp_SysStringLen
0x140013dff  test    eax, eax
0x140013e01  jz      short loc_140013E42
0x140013e03  mov     rcx, rdi; psz
0x140013e06  call    cs:__imp_SysAllocString
0x140013e0c  mov     [rbx+18h], rax
0x140013e10  mov     rdi, rax
0x140013e13  test    rax, rax
0x140013e16  jnz     short loc_140013E42
0x140013e18  mov     rcx, [rbx+10h]; bstrString
0x140013e1c  test    rcx, rcx
0x140013e1f  jz      short loc_140013E27
0x140013e21  call    cs:__imp_SysFreeString
0x140013e27  test    rdi, rdi
0x140013e2a  jz      short loc_140013E35
0x140013e2c  mov     rcx, rdi; bstrString
0x140013e2f  call    cs:__imp_SysFreeString
0x140013e35  mov     rcx, rbx; Block
0x140013e38  call    free_0
0x140013e3d  jmp     loc_140013DBA
0x140013e42  mov     eax, [rsp+48h+arg_20]
0x140013e46  mov     [rbx+20h], eax
0x140013e49  mov     rax, rbx
0x140013e4c  mov     [rbx+24h], r14d
0x140013e50  add     rsp, 20h
0x140013e54  pop     r14
0x140013e56  pop     rdi
0x140013e57  pop     rsi
0x140013e58  pop     rbp
0x140013e59  pop     rbx
0x140013e5a  retn
```
