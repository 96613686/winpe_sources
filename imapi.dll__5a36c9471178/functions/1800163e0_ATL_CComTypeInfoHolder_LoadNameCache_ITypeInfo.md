# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x1800163e0`
- end: `0x1800165ac`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015bd8`

## callees

- `0x18000119c`
- `0x1800150d8`
- `0x1800163e0`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016529`
- `OLEAUT32!__imp_SysFreeString` at `0x18001656e`
- `OLEAUT32!__imp_SysFreeString` at `0x180016529`
- `OLEAUT32!__imp_SysFreeString` at `0x18001656e`
- `OLEAUT32!__imp_SysStringLen` at `0x18001653c`
- `OLEAUT32!__imp_SysStringLen` at `0x18001653c`

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
0x1800163e0  push    rbp
0x1800163e2  push    rbx
0x1800163e3  push    rsi
0x1800163e4  push    rdi
0x1800163e5  push    r12
0x1800163e7  push    r14
0x1800163e9  push    r15
0x1800163eb  mov     rbp, rsp
0x1800163ee  sub     rsp, 40h
0x1800163f2  mov     rax, [rdx]
0x1800163f5  mov     rbx, rdx
0x1800163f8  mov     rsi, rcx
0x1800163fb  mov     [rbp+arg_18], 0
0x180016403  lea     rdx, [rbp+arg_18]
0x180016407  mov     rcx, rbx
0x18001640a  mov     rax, [rax+18h]
0x18001640e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016413  test    eax, eax
0x180016415  js      loc_18001659B
0x18001641b  mov     rax, [rbp+arg_18]
0x18001641f  xor     edi, edi
0x180016421  movzx   ecx, word ptr [rax+30h]
0x180016425  mov     [rsi+30h], ecx
0x180016428  mov     [rsi+28h], rdi
0x18001642c  test    ecx, ecx
0x18001642e  jz      short loc_180016497
0x180016430  mov     r14d, ecx
0x180016433  lea     eax, [rdi+10h]
0x180016436  mul     rcx
0x180016439  lea     rcx, [rdi-1]
0x18001643d  cmovb   rax, rcx
0x180016441  add     rax, 8
0x180016445  cmovb   rax, rcx
0x180016449  mov     rcx, rax; unsigned __int64
0x18001644c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180016451  test    rax, rax
0x180016454  jz      short loc_180016477
0x180016456  lea     rdi, [rax+8]
0x18001645a  mov     [rax], r14
0x18001645d  mov     r15, rdi
0x180016460  mov     rcx, r15; this
0x180016463  call    ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::stringdispid(void)
0x180016468  add     r15, 10h
0x18001646c  sub     r14, 1
0x180016470  jnz     short loc_180016460
0x180016472  test    rdi, rdi
0x180016475  jnz     short loc_180016497
0x180016477  mov     rax, [rbx]
0x18001647a  mov     rcx, rbx
0x18001647d  mov     rdx, [rbp+arg_18]
0x180016481  mov     rax, [rax+98h]
0x180016488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001648d  mov     eax, 8007000Eh
0x180016492  jmp     loc_18001659D
0x180016497  xor     r14d, r14d
0x18001649a  cmp     [rsi+30h], r14d
0x18001649e  jle     loc_180016581
0x1800164a4  movsxd  r15, r14d
0x1800164a7  lea     r8, [rbp+arg_8]
0x1800164ab  add     r15, r15
0x1800164ae  mov     [rbp+arg_8], 0
0x1800164b6  mov     edx, r14d
0x1800164b9  mov     rcx, rbx
0x1800164bc  mov     qword ptr [rdi+r15*8+8], 0
0x1800164c5  mov     rax, [rbx]
0x1800164c8  mov     rax, [rax+28h]
0x1800164cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164d1  test    eax, eax
0x1800164d3  js      loc_180016574
0x1800164d9  mov     rax, [rbx]
0x1800164dc  lea     r8, [rbp+pbstr]
0x1800164e0  mov     rdx, [rbp+arg_8]
0x1800164e4  xor     r9d, r9d
0x1800164e7  mov     [rbp+pbstr], 0
0x1800164ef  mov     rcx, rbx
0x1800164f2  mov     [rsp+40h+var_18], 0
0x1800164fb  mov     rax, [rax+60h]
0x1800164ff  mov     edx, [rdx]
0x180016501  mov     [rsp+40h+var_20], 0
0x18001650a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001650f  test    eax, eax
0x180016511  js      short loc_180016554
0x180016513  mov     r12, [rbp+pbstr]
0x180016517  mov     [rbp+pbstr], 0
0x18001651f  cmp     [rdi+r15*8], r12
0x180016523  jz      short loc_180016535
0x180016525  mov     rcx, [rdi+r15*8]; bstrString
0x180016529  call    cs:__imp_SysFreeString
0x18001652f  mov     [rdi+r15*8], r12
0x180016533  jmp     short loc_180016539
0x180016535  mov     r12, [rdi+r15*8]
0x180016539  mov     rcx, r12; pbstr
0x18001653c  call    cs:__imp_SysStringLen
0x180016542  mov     rdx, [rbp+arg_8]
0x180016546  mov     [rdi+r15*8+8], eax
0x18001654b  mov     eax, [rdx]
0x18001654d  mov     [rdi+r15*8+0Ch], eax
0x180016552  jmp     short loc_180016558
0x180016554  mov     rdx, [rbp+arg_8]
0x180016558  mov     rax, [rbx]
0x18001655b  mov     rcx, rbx
0x18001655e  mov     rax, [rax+0A0h]
0x180016565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001656a  mov     rcx, [rbp+pbstr]; bstrString
0x18001656e  call    cs:__imp_SysFreeString
0x180016574  inc     r14d
0x180016577  cmp     r14d, [rsi+30h]
0x18001657b  jl      loc_1800164A4
0x180016581  mov     rdx, [rbp+arg_18]
0x180016585  mov     rcx, rbx
0x180016588  mov     [rsi+28h], rdi
0x18001658c  mov     rax, [rbx]
0x18001658f  mov     rax, [rax+98h]
0x180016596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001659b  xor     eax, eax
0x18001659d  add     rsp, 40h
0x1800165a1  pop     r15
0x1800165a3  pop     r14
0x1800165a5  pop     r12
0x1800165a7  pop     rdi
0x1800165a8  pop     rsi
0x1800165a9  pop     rbx
0x1800165aa  pop     rbp
0x1800165ab  retn
```
