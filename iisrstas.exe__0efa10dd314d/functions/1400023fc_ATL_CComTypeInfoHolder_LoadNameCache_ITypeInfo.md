# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x1400023fc`
- end: `0x140002644`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400020ec`

## callees

- `0x140001008`
- `0x140001060`
- `0x140001868`
- `0x140001888`
- `0x1400023fc`
- `0x140006010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140002555`
- `OLEAUT32!__imp_SysFreeString` at `0x1400025c7`
- `OLEAUT32!__imp_SysFreeString` at `0x140002555`
- `OLEAUT32!__imp_SysFreeString` at `0x1400025c7`
- `OLEAUT32!__imp_SysStringLen` at `0x14000252b`
- `OLEAUT32!__imp_SysStringLen` at `0x14000252b`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(OLECHAR *this, struct ITypeInfo *a2)
{
  struct ITypeInfoVtbl *lpVtbl; // rax
  int v4; // r15d
  __int64 v5; // rdi
  unsigned __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rax
  bool v9; // cf
  unsigned __int64 v10; // rax
  _QWORD *v11; // rax
  ATL::CComTypeInfoHolder::stringdispid *v12; // r14
  unsigned int v14; // r14d
  struct ITypeInfoVtbl *v15; // rax
  struct ITypeInfoVtbl *v16; // rax
  OLECHAR *v17; // rcx
  UINT v18; // eax
  unsigned int *v19; // rdx
  __int64 v20; // r14
  ATL::CComTypeInfoHolder::stringdispid *i; // rbx
  __int64 v22; // r14
  ATL::CComTypeInfoHolder::stringdispid *j; // rbx
  BSTR pbstr; // [rsp+80h] [rbp+40h] BYREF
  unsigned int *v25; // [rsp+88h] [rbp+48h] BYREF
  __int64 v26; // [rsp+90h] [rbp+50h] BYREF

  pbstr = this;
  lpVtbl = a2->lpVtbl;
  v26 = 0;
  v4 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *))lpVtbl->GetTypeAttr)(a2, &v26);
  if ( v4 >= 0 )
  {
    v5 = 0;
    v6 = *(unsigned __int16 *)(v26 + 48);
    dword_14000A0C0 = v6;
    if ( (_WORD)v6 )
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
      if ( v11 )
      {
        v5 = (__int64)(v11 + 1);
        *v11 = v7;
        v12 = (ATL::CComTypeInfoHolder::stringdispid *)(v11 + 1);
        do
        {
          ATL::CComTypeInfoHolder::stringdispid::stringdispid(v12);
          v12 = (ATL::CComTypeInfoHolder::stringdispid *)((char *)v12 + 16);
          --v7;
        }
        while ( v7 );
      }
      LODWORD(v6) = dword_14000A0C0;
    }
    if ( (_DWORD)v6 && !v5 )
    {
      dword_14000A0C0 = 0;
      return 2147942414LL;
    }
    v14 = 0;
    if ( (int)v6 > 0 )
    {
      while ( 1 )
      {
        v15 = a2->lpVtbl;
        v25 = 0;
        v4 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, unsigned int **))v15->GetFuncDesc)(a2, v14, &v25);
        if ( v4 < 0 )
          break;
        v16 = a2->lpVtbl;
        pbstr = 0;
        v4 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v16->GetDocumentation)(
               a2,
               *v25,
               &pbstr,
               0,
               0,
               0);
        if ( v4 < 0 )
        {
          if ( v5 )
          {
            v20 = *(_QWORD *)(v5 - 8);
            for ( i = (ATL::CComTypeInfoHolder::stringdispid *)(v5 + 16 * v20); v20; --v20 )
            {
              i = (ATL::CComTypeInfoHolder::stringdispid *)((char *)i - 16);
              ATL::CComTypeInfoHolder::stringdispid::~stringdispid(i);
            }
            operator delete[]((void *)(v5 - 8));
          }
          dword_14000A0C0 = 0;
          v5 = 0;
          ((void (__fastcall *)(struct ITypeInfo *, unsigned int *))a2->lpVtbl->ReleaseFuncDesc)(a2, v25);
          SysFreeString(pbstr);
          goto LABEL_29;
        }
        v17 = pbstr;
        pbstr = 0;
        *(_QWORD *)(v5 + 16LL * (int)v14) = v17;
        v18 = SysStringLen(v17);
        v19 = v25;
        *(_DWORD *)(v5 + 16LL * (int)v14 + 8) = v18;
        *(_DWORD *)(v5 + 16LL * (int)v14 + 12) = *v19;
        ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseFuncDesc)(a2);
        SysFreeString(pbstr);
        if ( (int)++v14 >= dword_14000A0C0 )
          goto LABEL_29;
      }
      if ( v5 )
      {
        v22 = *(_QWORD *)(v5 - 8);
        for ( j = (ATL::CComTypeInfoHolder::stringdispid *)(v5 + 16 * v22); v22; --v22 )
        {
          j = (ATL::CComTypeInfoHolder::stringdispid *)((char *)j - 16);
          ATL::CComTypeInfoHolder::stringdispid::~stringdispid(j);
        }
        operator delete[]((void *)(v5 - 8));
      }
      v5 = 0;
      dword_14000A0C0 = 0;
    }
LABEL_29:
    qword_14000A0B8 = v5;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v26);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400023fc  mov     [rsp-38h+arg_18], rbx
0x140002401  mov     [rsp-38h+pbstr], rcx
0x140002406  push    rbp
0x140002407  push    rsi
0x140002408  push    rdi
0x140002409  push    r12
0x14000240b  push    r13
0x14000240d  push    r14
0x14000240f  push    r15
0x140002411  mov     rbp, rsp
0x140002414  sub     rsp, 40h
0x140002418  mov     rax, [rdx]
0x14000241b  mov     rsi, rdx
0x14000241e  xor     r13d, r13d
0x140002421  lea     rdx, [rbp+arg_10]
0x140002425  mov     rcx, rsi
0x140002428  mov     [rbp+arg_10], r13
0x14000242c  mov     rax, [rax+18h]
0x140002430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002435  mov     r15d, eax
0x140002438  test    eax, eax
0x14000243a  js      loc_140002629
0x140002440  mov     rcx, [rbp+arg_10]
0x140002444  mov     edi, r13d
0x140002447  movzx   edx, word ptr [rcx+30h]
0x14000244b  mov     cs:dword_14000A0C0, edx
0x140002451  test    dx, dx
0x140002454  jz      short loc_14000249E
0x140002456  lea     rcx, [r13-1]
0x14000245a  mov     ebx, edx
0x14000245c  lea     eax, [r13+10h]
0x140002460  mul     rdx
0x140002463  cmovb   rax, rcx
0x140002467  add     rax, 8
0x14000246b  cmovb   rax, rcx
0x14000246f  mov     rcx, rax; unsigned __int64
0x140002472  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140002477  test    rax, rax
0x14000247a  jz      short loc_140002498
0x14000247c  lea     rdi, [rax+8]
0x140002480  mov     [rax], rbx
0x140002483  mov     r14, rdi
0x140002486  mov     rcx, r14; this
0x140002489  call    ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::stringdispid(void)
0x14000248e  add     r14, 10h
0x140002492  sub     rbx, 1
0x140002496  jnz     short loc_140002486
0x140002498  mov     edx, cs:dword_14000A0C0
0x14000249e  test    edx, edx
0x1400024a0  jz      short loc_1400024B8
0x1400024a2  test    rdi, rdi
0x1400024a5  jnz     short loc_1400024B8
0x1400024a7  mov     cs:dword_14000A0C0, r13d
0x1400024ae  mov     eax, 8007000Eh
0x1400024b3  jmp     loc_14000262C
0x1400024b8  mov     r14d, r13d
0x1400024bb  test    edx, edx
0x1400024bd  jle     loc_14000260C
0x1400024c3  mov     rax, [rsi]
0x1400024c6  lea     r8, [rbp+arg_8]
0x1400024ca  mov     edx, r14d
0x1400024cd  mov     [rbp+arg_8], r13
0x1400024d1  mov     rcx, rsi
0x1400024d4  mov     rax, [rax+28h]
0x1400024d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024dd  mov     r15d, eax
0x1400024e0  test    eax, eax
0x1400024e2  js      loc_1400025CF
0x1400024e8  mov     rax, [rsi]
0x1400024eb  lea     r8, [rbp+pbstr]
0x1400024ef  mov     rdx, [rbp+arg_8]
0x1400024f3  xor     r9d, r9d
0x1400024f6  mov     [rbp+pbstr], r13
0x1400024fa  mov     rcx, rsi
0x1400024fd  mov     [rsp+40h+var_18], r13
0x140002502  mov     rax, [rax+60h]
0x140002506  mov     edx, [rdx]
0x140002508  mov     [rsp+40h+var_20], r13
0x14000250d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002512  mov     r15d, eax
0x140002515  test    eax, eax
0x140002517  js      short loc_140002570
0x140002519  mov     rcx, [rbp+pbstr]; pbstr
0x14000251d  movsxd  rbx, r14d
0x140002520  add     rbx, rbx
0x140002523  mov     [rbp+pbstr], r13
0x140002527  mov     [rdi+rbx*8], rcx
0x14000252b  call    cs:__imp_SysStringLen
0x140002531  mov     rdx, [rbp+arg_8]
0x140002535  mov     rcx, rsi
0x140002538  mov     [rdi+rbx*8+8], eax
0x14000253c  mov     eax, [rdx]
0x14000253e  mov     [rdi+rbx*8+0Ch], eax
0x140002542  mov     rax, [rsi]
0x140002545  mov     rax, [rax+0A0h]
0x14000254c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002551  mov     rcx, [rbp+pbstr]; bstrString
0x140002555  call    cs:__imp_SysFreeString
0x14000255b  inc     r14d
0x14000255e  cmp     r14d, cs:dword_14000A0C0
0x140002565  jl      loc_1400024C3
0x14000256b  jmp     loc_14000260C
0x140002570  test    rdi, rdi
0x140002573  jz      short loc_1400025A3
0x140002575  mov     r14, [rdi-8]
0x140002579  mov     rbx, r14
0x14000257c  shl     rbx, 4
0x140002580  add     rbx, rdi
0x140002583  test    r14, r14
0x140002586  jz      short loc_14000259A
0x140002588  sub     rbx, 10h
0x14000258c  mov     rcx, rbx; this
0x14000258f  call    ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x140002594  sub     r14, 1
0x140002598  jnz     short loc_140002588
0x14000259a  lea     rcx, [rdi-8]; void *
0x14000259e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1400025a3  mov     rdx, [rbp+arg_8]
0x1400025a7  mov     rcx, rsi
0x1400025aa  mov     cs:dword_14000A0C0, r13d
0x1400025b1  mov     rdi, r13
0x1400025b4  mov     rax, [rsi]
0x1400025b7  mov     rax, [rax+0A0h]
0x1400025be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025c3  mov     rcx, [rbp+pbstr]; bstrString
0x1400025c7  call    cs:__imp_SysFreeString
0x1400025cd  jmp     short loc_14000260C
0x1400025cf  test    rdi, rdi
0x1400025d2  jz      short loc_140002602
0x1400025d4  mov     r14, [rdi-8]
0x1400025d8  mov     rbx, r14
0x1400025db  shl     rbx, 4
0x1400025df  add     rbx, rdi
0x1400025e2  test    r14, r14
0x1400025e5  jz      short loc_1400025F9
0x1400025e7  sub     rbx, 10h
0x1400025eb  mov     rcx, rbx; this
0x1400025ee  call    ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x1400025f3  sub     r14, 1
0x1400025f7  jnz     short loc_1400025E7
0x1400025f9  lea     rcx, [rdi-8]; void *
0x1400025fd  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140002602  mov     rdi, r13
0x140002605  mov     cs:dword_14000A0C0, r13d
0x14000260c  mov     rdx, [rbp+arg_10]
0x140002610  mov     rcx, rsi
0x140002613  mov     cs:qword_14000A0B8, rdi
0x14000261a  mov     rax, [rsi]
0x14000261d  mov     rax, [rax+98h]
0x140002624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002629  mov     eax, r15d
0x14000262c  mov     rbx, [rsp+40h+arg_18]
0x140002634  add     rsp, 40h
0x140002638  pop     r15
0x14000263a  pop     r14
0x14000263c  pop     r13
0x14000263e  pop     r12
0x140002640  pop     rdi
0x140002641  pop     rsi
0x140002642  pop     rbp
0x140002643  retn
```
