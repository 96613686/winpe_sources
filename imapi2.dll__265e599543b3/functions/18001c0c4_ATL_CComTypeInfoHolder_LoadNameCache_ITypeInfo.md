# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x18001c0c4`
- end: `0x18001c294`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b910`

## callees

- `0x18000fdc8`
- `0x180010e70`
- `0x18001c0c4`
- `0x18004a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001c211`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c256`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c211`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c256`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c224`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c224`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfoVtbl *lpVtbl; // rax
  _QWORD *v5; // rdi
  unsigned __int64 v6; // rcx
  __int64 v7; // r14
  __int64 v8; // rax
  bool v9; // cf
  unsigned __int64 v10; // rax
  _QWORD *v11; // rax
  unsigned int i; // r14d
  struct ITypeInfoVtbl *v14; // rax
  OLECHAR *v15; // r12
  UINT v16; // eax
  _DWORD *v17; // rdx
  __int64 v18; // rdx
  unsigned int *v19; // [rsp+88h] [rbp+48h] BYREF
  BSTR pbstr; // [rsp+90h] [rbp+50h] BYREF
  __int64 v21; // [rsp+98h] [rbp+58h] BYREF

  lpVtbl = a2->lpVtbl;
  v21 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))lpVtbl->GetTypeAttr)(a2, &v21) >= 0 )
  {
    v5 = 0;
    v6 = *(unsigned __int16 *)(v21 + 48);
    *((_DWORD *)this + 12) = v6;
    *((_QWORD *)this + 5) = 0;
    if ( (_DWORD)v6 )
    {
      v7 = (unsigned int)v6;
      v8 = 16 * v6;
      if ( !is_mul_ok(v6, 0x10u) )
        v8 = -1;
      v9 = __CFADD__(v8, 8);
      v10 = v8 + 8;
      if ( v9 )
        v10 = -1;
      v11 = operator new[](v10);
      if ( !v11
        || (v5 = v11 + 1,
            *v11 = v7,
            `vector constructor iterator'(
              v11 + 1,
              0x10u,
              (unsigned int)v7,
              (void *(*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid),
            !v5) )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v21);
        return 2147942414LL;
      }
    }
    for ( i = 0; (signed int)i < *((_DWORD *)this + 12); ++i )
    {
      v19 = 0;
      v5[2 * (int)i + 1] = 0;
      if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, unsigned int **))a2->lpVtbl->GetFuncDesc)(a2, i, &v19) >= 0 )
      {
        v14 = a2->lpVtbl;
        pbstr = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v14->GetDocumentation)(
               a2,
               *v19,
               &pbstr,
               0,
               0,
               0) < 0 )
        {
          v17 = v19;
        }
        else
        {
          v15 = pbstr;
          pbstr = 0;
          if ( (OLECHAR *)v5[2 * (int)i] == v15 )
          {
            v15 = (OLECHAR *)v5[2 * (int)i];
          }
          else
          {
            SysFreeString((BSTR)v5[2 * (int)i]);
            v5[2 * (int)i] = v15;
          }
          v16 = SysStringLen(v15);
          v17 = v19;
          LODWORD(v5[2 * (int)i + 1]) = v16;
          HIDWORD(v5[2 * (int)i + 1]) = *v17;
        }
        ((void (__fastcall *)(struct ITypeInfo *, _DWORD *))a2->lpVtbl->ReleaseFuncDesc)(a2, v17);
        SysFreeString(pbstr);
      }
    }
    v18 = v21;
    *((_QWORD *)this + 5) = v5;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18001c0c4  push    rbp
0x18001c0c6  push    rbx
0x18001c0c7  push    rsi
0x18001c0c8  push    rdi
0x18001c0c9  push    r12
0x18001c0cb  push    r14
0x18001c0cd  push    r15
0x18001c0cf  mov     rbp, rsp
0x18001c0d2  sub     rsp, 40h
0x18001c0d6  mov     rax, [rdx]
0x18001c0d9  mov     rbx, rdx
0x18001c0dc  mov     rsi, rcx
0x18001c0df  mov     [rbp+arg_18], 0
0x18001c0e7  lea     rdx, [rbp+arg_18]
0x18001c0eb  mov     rcx, rbx
0x18001c0ee  mov     rax, [rax+18h]
0x18001c0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0f7  test    eax, eax
0x18001c0f9  js      loc_18001C283
0x18001c0ff  mov     rax, [rbp+arg_18]
0x18001c103  xor     edi, edi
0x18001c105  movzx   ecx, word ptr [rax+30h]
0x18001c109  mov     [rsi+30h], ecx
0x18001c10c  mov     [rsi+28h], rdi
0x18001c110  test    ecx, ecx
0x18001c112  jz      short loc_18001C17F
0x18001c114  mov     r14d, ecx
0x18001c117  lea     r15d, [rdi+10h]
0x18001c11b  mov     eax, r15d
0x18001c11e  mul     rcx
0x18001c121  lea     rcx, [rdi-1]
0x18001c125  cmovb   rax, rcx
0x18001c129  add     rax, 8
0x18001c12d  cmovb   rax, rcx
0x18001c131  mov     rcx, rax; unsigned __int64
0x18001c134  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c139  test    rax, rax
0x18001c13c  jz      short loc_18001C15F
0x18001c13e  lea     rdi, [rax+8]
0x18001c142  mov     [rax], r14
0x18001c145  mov     rcx, rdi; void *
0x18001c148  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void *(*)(void *)
0x18001c14f  mov     r8d, r14d; unsigned __int64
0x18001c152  mov     edx, r15d; unsigned __int64
0x18001c155  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18001c15a  test    rdi, rdi
0x18001c15d  jnz     short loc_18001C17F
0x18001c15f  mov     rax, [rbx]
0x18001c162  mov     rcx, rbx
0x18001c165  mov     rdx, [rbp+arg_18]
0x18001c169  mov     rax, [rax+98h]
0x18001c170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c175  mov     eax, 8007000Eh
0x18001c17a  jmp     loc_18001C285
0x18001c17f  xor     r14d, r14d
0x18001c182  cmp     [rsi+30h], r14d
0x18001c186  jle     loc_18001C269
0x18001c18c  movsxd  r15, r14d
0x18001c18f  lea     r8, [rbp+arg_8]
0x18001c193  add     r15, r15
0x18001c196  mov     [rbp+arg_8], 0
0x18001c19e  mov     edx, r14d
0x18001c1a1  mov     rcx, rbx
0x18001c1a4  mov     qword ptr [rdi+r15*8+8], 0
0x18001c1ad  mov     rax, [rbx]
0x18001c1b0  mov     rax, [rax+28h]
0x18001c1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1b9  test    eax, eax
0x18001c1bb  js      loc_18001C25C
0x18001c1c1  mov     rax, [rbx]
0x18001c1c4  lea     r8, [rbp+pbstr]
0x18001c1c8  mov     rdx, [rbp+arg_8]
0x18001c1cc  xor     r9d, r9d
0x18001c1cf  mov     [rbp+pbstr], 0
0x18001c1d7  mov     rcx, rbx
0x18001c1da  mov     [rsp+40h+var_18], 0
0x18001c1e3  mov     rax, [rax+60h]
0x18001c1e7  mov     edx, [rdx]
0x18001c1e9  mov     [rsp+40h+var_20], 0
0x18001c1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1f7  test    eax, eax
0x18001c1f9  js      short loc_18001C23C
0x18001c1fb  mov     r12, [rbp+pbstr]
0x18001c1ff  mov     [rbp+pbstr], 0
0x18001c207  cmp     [rdi+r15*8], r12
0x18001c20b  jz      short loc_18001C21D
0x18001c20d  mov     rcx, [rdi+r15*8]; bstrString
0x18001c211  call    cs:__imp_SysFreeString
0x18001c217  mov     [rdi+r15*8], r12
0x18001c21b  jmp     short loc_18001C221
0x18001c21d  mov     r12, [rdi+r15*8]
0x18001c221  mov     rcx, r12; pbstr
0x18001c224  call    cs:__imp_SysStringLen
0x18001c22a  mov     rdx, [rbp+arg_8]
0x18001c22e  mov     [rdi+r15*8+8], eax
0x18001c233  mov     eax, [rdx]
0x18001c235  mov     [rdi+r15*8+0Ch], eax
0x18001c23a  jmp     short loc_18001C240
0x18001c23c  mov     rdx, [rbp+arg_8]
0x18001c240  mov     rax, [rbx]
0x18001c243  mov     rcx, rbx
0x18001c246  mov     rax, [rax+0A0h]
0x18001c24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c252  mov     rcx, [rbp+pbstr]; bstrString
0x18001c256  call    cs:__imp_SysFreeString
0x18001c25c  inc     r14d
0x18001c25f  cmp     r14d, [rsi+30h]
0x18001c263  jl      loc_18001C18C
0x18001c269  mov     rdx, [rbp+arg_18]
0x18001c26d  mov     rcx, rbx
0x18001c270  mov     [rsi+28h], rdi
0x18001c274  mov     rax, [rbx]
0x18001c277  mov     rax, [rax+98h]
0x18001c27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c283  xor     eax, eax
0x18001c285  add     rsp, 40h
0x18001c289  pop     r15
0x18001c28b  pop     r14
0x18001c28d  pop     r12
0x18001c28f  pop     rdi
0x18001c290  pop     rsi
0x18001c291  pop     rbx
0x18001c292  pop     rbp
0x18001c293  retn
```
