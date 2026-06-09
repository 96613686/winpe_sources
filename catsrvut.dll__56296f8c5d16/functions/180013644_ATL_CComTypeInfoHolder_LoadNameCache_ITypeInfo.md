# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x180013644`
- end: `0x18001384a`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012f8c`

## callees

- `0x18000f8d4`
- `0x180010a9c`
- `0x180013644`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800136b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800136b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800137b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800137fb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800137b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800137fb`
- `OLEAUT32!__imp_SysStringLen` at `0x180013789`
- `OLEAUT32!__imp_SysStringLen` at `0x180013789`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(OLECHAR *this, struct ITypeInfo *a2)
{
  int v3; // r14d
  unsigned __int64 v4; // rdx
  ATL::CComTypeInfoHolder::stringdispid *v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  bool v8; // cf
  SIZE_T v9; // rax
  OLECHAR *v10; // rax
  int i; // r15d
  OLECHAR *v13; // rcx
  BSTR pbstr; // [rsp+80h] [rbp+40h] BYREF
  _DWORD *v15; // [rsp+88h] [rbp+48h] BYREF
  __int64 v16; // [rsp+90h] [rbp+50h] BYREF

  pbstr = this;
  v16 = 0;
  v3 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v16);
  if ( v3 >= 0 )
  {
    v4 = *(unsigned __int16 *)(v16 + 48);
    dword_1800701E0 = v4;
    v5 = 0;
    if ( (_WORD)v4 )
    {
      v6 = (unsigned int)v4;
      v7 = 16 * v4;
      if ( !is_mul_ok(v4, 0x10u) )
        v7 = -1;
      v8 = __CFADD__(v7, 8);
      v9 = v7 + 8;
      if ( v8 )
        v9 = -1;
      v10 = (OLECHAR *)CoTaskMemAlloc(v9);
      pbstr = v10;
      if ( v10 )
      {
        *(_QWORD *)v10 = v6;
        v5 = (ATL::CComTypeInfoHolder::stringdispid *)(v10 + 4);
        `eh vector constructor iterator'(
          v10 + 4,
          0x10u,
          (unsigned int)v6,
          (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
          (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::~stringdispid);
      }
      else
      {
        v5 = 0;
      }
      LODWORD(v4) = dword_1800701E0;
    }
    if ( (_DWORD)v4 && !v5 )
    {
      dword_1800701E0 = 0;
      return 2147942414LL;
    }
    for ( i = 0; i < (int)v4; ++i )
    {
      v15 = 0;
      v3 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, _DWORD **))a2->lpVtbl->GetFuncDesc)(
             a2,
             (unsigned int)i,
             &v15);
      if ( v3 < 0 )
      {
        if ( v5 )
          ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(v5);
        v5 = 0;
        dword_1800701E0 = 0;
        break;
      }
      pbstr = 0;
      v3 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->GetDocumentation)(
             a2,
             (unsigned int)*v15,
             &pbstr,
             0,
             0,
             0);
      if ( v3 < 0 )
      {
        if ( v5 )
          ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(v5);
        v5 = 0;
        dword_1800701E0 = 0;
        ((void (__fastcall *)(struct ITypeInfo *, _DWORD *))a2->lpVtbl->ReleaseFuncDesc)(a2, v15);
        SysFreeString(pbstr);
        break;
      }
      v13 = pbstr;
      pbstr = 0;
      *((_QWORD *)v5 + 2 * i) = v13;
      *((_DWORD *)v5 + 4 * i + 2) = SysStringLen(v13);
      *((_DWORD *)v5 + 4 * i + 3) = *v15;
      ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseFuncDesc)(a2);
      SysFreeString(pbstr);
      LODWORD(v4) = dword_1800701E0;
    }
    qword_1800701D8 = (__int64)v5;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v16);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013644  mov     [rsp-38h+pbstr], rcx
0x180013649  push    rbp
0x18001364a  push    rbx
0x18001364b  push    rsi
0x18001364c  push    rdi
0x18001364d  push    r12
0x18001364f  push    r14
0x180013651  push    r15
0x180013653  mov     rbp, rsp
0x180013656  sub     rsp, 40h
0x18001365a  mov     rsi, rdx
0x18001365d  xor     r12d, r12d
0x180013660  mov     [rbp+arg_10], r12
0x180013664  mov     rax, [rdx]
0x180013667  lea     rdx, [rbp+arg_10]
0x18001366b  mov     rcx, rsi
0x18001366e  mov     rax, [rax+18h]
0x180013672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013677  mov     r14d, eax
0x18001367a  test    eax, eax
0x18001367c  js      loc_180013838
0x180013682  mov     rcx, [rbp+arg_10]
0x180013686  movzx   edx, word ptr [rcx+30h]
0x18001368a  mov     cs:dword_1800701E0, edx
0x180013690  mov     edi, r12d
0x180013693  test    dx, dx
0x180013696  jz      short loc_1800136FB
0x180013698  mov     ebx, edx
0x18001369a  lea     r15d, [r12+10h]
0x18001369f  mov     eax, r15d
0x1800136a2  mul     rdx
0x1800136a5  lea     rcx, [r12-1]
0x1800136aa  cmovb   rax, rcx
0x1800136ae  add     rax, 8
0x1800136b2  cmovb   rax, rcx
0x1800136b6  mov     rcx, rax; cb
0x1800136b9  call    cs:__imp_CoTaskMemAlloc
0x1800136bf  mov     [rbp+pbstr], rax
0x1800136c3  test    rax, rax
0x1800136c6  jz      short loc_1800136F2
0x1800136c8  mov     [rax], rbx
0x1800136cb  lea     rdi, [rax+8]
0x1800136cf  lea     rax, ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x1800136d6  mov     [rsp+40h+var_20], rax; void (*)(void *)
0x1800136db  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x1800136e2  mov     r8d, ebx; unsigned __int64
0x1800136e5  mov     edx, r15d; unsigned __int64
0x1800136e8  mov     rcx, rdi; void *
0x1800136eb  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800136f0  jmp     short loc_1800136F5
0x1800136f2  mov     rdi, r12
0x1800136f5  mov     edx, cs:dword_1800701E0
0x1800136fb  test    edx, edx
0x1800136fd  jz      short loc_180013715
0x1800136ff  test    rdi, rdi
0x180013702  jnz     short loc_180013715
0x180013704  mov     cs:dword_1800701E0, r12d
0x18001370b  mov     eax, 8007000Eh
0x180013710  jmp     loc_18001383B
0x180013715  mov     r15d, r12d
0x180013718  cmp     r15d, edx
0x18001371b  jge     loc_18001381B
0x180013721  mov     [rbp+arg_8], r12
0x180013725  mov     rax, [rsi]
0x180013728  lea     r8, [rbp+arg_8]
0x18001372c  mov     edx, r15d
0x18001372f  mov     rcx, rsi
0x180013732  mov     rax, [rax+28h]
0x180013736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001373b  mov     r14d, eax
0x18001373e  test    eax, eax
0x180013740  js      loc_180013804
0x180013746  mov     [rbp+pbstr], r12
0x18001374a  mov     rax, [rsi]
0x18001374d  mov     [rsp+40h+var_18], r12
0x180013752  mov     [rsp+40h+var_20], r12
0x180013757  xor     r9d, r9d
0x18001375a  lea     r8, [rbp+pbstr]
0x18001375e  mov     rdx, [rbp+arg_8]
0x180013762  mov     edx, [rdx]
0x180013764  mov     rcx, rsi
0x180013767  mov     rax, [rax+60h]
0x18001376b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013770  mov     r14d, eax
0x180013773  test    eax, eax
0x180013775  js      short loc_1800137C9
0x180013777  mov     rcx, [rbp+pbstr]; pbstr
0x18001377b  mov     [rbp+pbstr], r12
0x18001377f  movsxd  rbx, r15d
0x180013782  add     rbx, rbx
0x180013785  mov     [rdi+rbx*8], rcx
0x180013789  call    cs:__imp_SysStringLen
0x18001378f  mov     [rdi+rbx*8+8], eax
0x180013793  mov     rdx, [rbp+arg_8]
0x180013797  mov     eax, [rdx]
0x180013799  mov     [rdi+rbx*8+0Ch], eax
0x18001379d  mov     rax, [rsi]
0x1800137a0  mov     rcx, rsi
0x1800137a3  mov     rax, [rax+0A0h]
0x1800137aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137af  nop
0x1800137b0  mov     rcx, [rbp+pbstr]; bstrString
0x1800137b4  call    cs:__imp_SysFreeString
0x1800137ba  nop
0x1800137bb  inc     r15d
0x1800137be  mov     edx, cs:dword_1800701E0
0x1800137c4  jmp     loc_180013718
0x1800137c9  test    rdi, rdi
0x1800137cc  jz      short loc_1800137D6
0x1800137ce  mov     rcx, rdi; this
0x1800137d1  call    ??_Estringdispid@CComTypeInfoHolder@ATL@@QEAAPEAXI@Z; ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(uint)
0x1800137d6  mov     rdi, r12
0x1800137d9  mov     cs:dword_1800701E0, r12d
0x1800137e0  mov     rax, [rsi]
0x1800137e3  mov     rdx, [rbp+arg_8]
0x1800137e7  mov     rcx, rsi
0x1800137ea  mov     rax, [rax+0A0h]
0x1800137f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137f6  nop
0x1800137f7  mov     rcx, [rbp+pbstr]; bstrString
0x1800137fb  call    cs:__imp_SysFreeString
0x180013801  nop
0x180013802  jmp     short loc_18001381B
0x180013804  test    rdi, rdi
0x180013807  jz      short loc_180013811
0x180013809  mov     rcx, rdi; this
0x18001380c  call    ??_Estringdispid@CComTypeInfoHolder@ATL@@QEAAPEAXI@Z; ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(uint)
0x180013811  mov     rdi, r12
0x180013814  mov     cs:dword_1800701E0, r12d
0x18001381b  mov     cs:qword_1800701D8, rdi
0x180013822  mov     rax, [rsi]
0x180013825  mov     rdx, [rbp+arg_10]
0x180013829  mov     rcx, rsi
0x18001382c  mov     rax, [rax+98h]
0x180013833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013838  mov     eax, r14d
0x18001383b  add     rsp, 40h
0x18001383f  pop     r15
0x180013841  pop     r14
0x180013843  pop     r12
0x180013845  pop     rdi
0x180013846  pop     rsi
0x180013847  pop     rbx
0x180013848  pop     rbp
0x180013849  retn
```
