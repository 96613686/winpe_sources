# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x140006a60`
- end: `0x140006c2c`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400058e4`

## callees

- `0x140001c48`
- `0x140003700`
- `0x140006a60`
- `0x140010010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140006ba9`
- `OLEAUT32!__imp_SysFreeString` at `0x140006bee`
- `OLEAUT32!__imp_SysFreeString` at `0x140006ba9`
- `OLEAUT32!__imp_SysFreeString` at `0x140006bee`
- `OLEAUT32!__imp_SysStringLen` at `0x140006bbc`
- `OLEAUT32!__imp_SysStringLen` at `0x140006bbc`

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
  ATL::CComTypeInfoHolder::stringdispid *v12; // r15
  unsigned int i; // r14d
  struct ITypeInfoVtbl *v15; // rax
  OLECHAR *v16; // r12
  UINT v17; // eax
  _DWORD *v18; // rdx
  __int64 v19; // rdx
  unsigned int *v20; // [rsp+88h] [rbp+48h] BYREF
  BSTR pbstr; // [rsp+90h] [rbp+50h] BYREF
  __int64 v22; // [rsp+98h] [rbp+58h] BYREF

  lpVtbl = a2->lpVtbl;
  v22 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))lpVtbl->GetTypeAttr)(a2, &v22) >= 0 )
  {
    v5 = 0;
    v6 = *(unsigned __int16 *)(v22 + 48);
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
      if ( !v11 )
        goto LABEL_11;
      v5 = v11 + 1;
      *v11 = v7;
      v12 = (ATL::CComTypeInfoHolder::stringdispid *)(v11 + 1);
      do
      {
        ATL::CComTypeInfoHolder::stringdispid::stringdispid(v12);
        v12 = (ATL::CComTypeInfoHolder::stringdispid *)((char *)v12 + 16);
        --v7;
      }
      while ( v7 );
      if ( !v5 )
      {
LABEL_11:
        ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v22);
        return 2147942414LL;
      }
    }
    for ( i = 0; (signed int)i < *((_DWORD *)this + 12); ++i )
    {
      v20 = 0;
      v5[2 * (int)i + 1] = 0;
      if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, unsigned int **))a2->lpVtbl->GetFuncDesc)(a2, i, &v20) >= 0 )
      {
        v15 = a2->lpVtbl;
        pbstr = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v15->GetDocumentation)(
               a2,
               *v20,
               &pbstr,
               0,
               0,
               0) < 0 )
        {
          v18 = v20;
        }
        else
        {
          v16 = pbstr;
          pbstr = 0;
          if ( (OLECHAR *)v5[2 * (int)i] == v16 )
          {
            v16 = (OLECHAR *)v5[2 * (int)i];
          }
          else
          {
            SysFreeString((BSTR)v5[2 * (int)i]);
            v5[2 * (int)i] = v16;
          }
          v17 = SysStringLen(v16);
          v18 = v20;
          LODWORD(v5[2 * (int)i + 1]) = v17;
          HIDWORD(v5[2 * (int)i + 1]) = *v18;
        }
        ((void (__fastcall *)(struct ITypeInfo *, _DWORD *))a2->lpVtbl->ReleaseFuncDesc)(a2, v18);
        SysFreeString(pbstr);
      }
    }
    v19 = v22;
    *((_QWORD *)this + 5) = v5;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v19);
  }
  return 0;
}

```

## disassembly

```asm
0x140006a60  push    rbp
0x140006a62  push    rbx
0x140006a63  push    rsi
0x140006a64  push    rdi
0x140006a65  push    r12
0x140006a67  push    r14
0x140006a69  push    r15
0x140006a6b  mov     rbp, rsp
0x140006a6e  sub     rsp, 40h
0x140006a72  mov     rax, [rdx]
0x140006a75  mov     rbx, rdx
0x140006a78  mov     rsi, rcx
0x140006a7b  mov     [rbp+arg_18], 0
0x140006a83  lea     rdx, [rbp+arg_18]
0x140006a87  mov     rcx, rbx
0x140006a8a  mov     rax, [rax+18h]
0x140006a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a93  test    eax, eax
0x140006a95  js      loc_140006C1B
0x140006a9b  mov     rax, [rbp+arg_18]
0x140006a9f  xor     edi, edi
0x140006aa1  movzx   ecx, word ptr [rax+30h]
0x140006aa5  mov     [rsi+30h], ecx
0x140006aa8  mov     [rsi+28h], rdi
0x140006aac  test    ecx, ecx
0x140006aae  jz      short loc_140006B17
0x140006ab0  mov     r14d, ecx
0x140006ab3  lea     eax, [rdi+10h]
0x140006ab6  mul     rcx
0x140006ab9  lea     rcx, [rdi-1]
0x140006abd  cmovb   rax, rcx
0x140006ac1  add     rax, 8
0x140006ac5  cmovb   rax, rcx
0x140006ac9  mov     rcx, rax; unsigned __int64
0x140006acc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140006ad1  test    rax, rax
0x140006ad4  jz      short loc_140006AF7
0x140006ad6  lea     rdi, [rax+8]
0x140006ada  mov     [rax], r14
0x140006add  mov     r15, rdi
0x140006ae0  mov     rcx, r15; this
0x140006ae3  call    ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::stringdispid(void)
0x140006ae8  add     r15, 10h
0x140006aec  sub     r14, 1
0x140006af0  jnz     short loc_140006AE0
0x140006af2  test    rdi, rdi
0x140006af5  jnz     short loc_140006B17
0x140006af7  mov     rax, [rbx]
0x140006afa  mov     rcx, rbx
0x140006afd  mov     rdx, [rbp+arg_18]
0x140006b01  mov     rax, [rax+98h]
0x140006b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b0d  mov     eax, 8007000Eh
0x140006b12  jmp     loc_140006C1D
0x140006b17  xor     r14d, r14d
0x140006b1a  cmp     [rsi+30h], r14d
0x140006b1e  jle     loc_140006C01
0x140006b24  movsxd  r15, r14d
0x140006b27  lea     r8, [rbp+arg_8]
0x140006b2b  add     r15, r15
0x140006b2e  mov     [rbp+arg_8], 0
0x140006b36  mov     edx, r14d
0x140006b39  mov     rcx, rbx
0x140006b3c  mov     qword ptr [rdi+r15*8+8], 0
0x140006b45  mov     rax, [rbx]
0x140006b48  mov     rax, [rax+28h]
0x140006b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b51  test    eax, eax
0x140006b53  js      loc_140006BF4
0x140006b59  mov     rax, [rbx]
0x140006b5c  lea     r8, [rbp+pbstr]
0x140006b60  mov     rdx, [rbp+arg_8]
0x140006b64  xor     r9d, r9d
0x140006b67  mov     [rbp+pbstr], 0
0x140006b6f  mov     rcx, rbx
0x140006b72  mov     [rsp+40h+var_18], 0
0x140006b7b  mov     rax, [rax+60h]
0x140006b7f  mov     edx, [rdx]
0x140006b81  mov     [rsp+40h+var_20], 0
0x140006b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b8f  test    eax, eax
0x140006b91  js      short loc_140006BD4
0x140006b93  mov     r12, [rbp+pbstr]
0x140006b97  mov     [rbp+pbstr], 0
0x140006b9f  cmp     [rdi+r15*8], r12
0x140006ba3  jz      short loc_140006BB5
0x140006ba5  mov     rcx, [rdi+r15*8]; bstrString
0x140006ba9  call    cs:__imp_SysFreeString
0x140006baf  mov     [rdi+r15*8], r12
0x140006bb3  jmp     short loc_140006BB9
0x140006bb5  mov     r12, [rdi+r15*8]
0x140006bb9  mov     rcx, r12; pbstr
0x140006bbc  call    cs:__imp_SysStringLen
0x140006bc2  mov     rdx, [rbp+arg_8]
0x140006bc6  mov     [rdi+r15*8+8], eax
0x140006bcb  mov     eax, [rdx]
0x140006bcd  mov     [rdi+r15*8+0Ch], eax
0x140006bd2  jmp     short loc_140006BD8
0x140006bd4  mov     rdx, [rbp+arg_8]
0x140006bd8  mov     rax, [rbx]
0x140006bdb  mov     rcx, rbx
0x140006bde  mov     rax, [rax+0A0h]
0x140006be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bea  mov     rcx, [rbp+pbstr]; bstrString
0x140006bee  call    cs:__imp_SysFreeString
0x140006bf4  inc     r14d
0x140006bf7  cmp     r14d, [rsi+30h]
0x140006bfb  jl      loc_140006B24
0x140006c01  mov     rdx, [rbp+arg_18]
0x140006c05  mov     rcx, rbx
0x140006c08  mov     [rsi+28h], rdi
0x140006c0c  mov     rax, [rbx]
0x140006c0f  mov     rax, [rax+98h]
0x140006c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c1b  xor     eax, eax
0x140006c1d  add     rsp, 40h
0x140006c21  pop     r15
0x140006c23  pop     r14
0x140006c25  pop     r12
0x140006c27  pop     rdi
0x140006c28  pop     rsi
0x140006c29  pop     rbx
0x140006c2a  pop     rbp
0x140006c2b  retn
```
