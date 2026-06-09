# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x18000fae0`
- end: `0x18000fcdc`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ec10`

## callees

- `0x18000173c`
- `0x180002238`
- `0x18000272c`
- `0x18000fae0`
- `0x180029010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000fc57`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fc94`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fc57`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fc94`
- `OLEAUT32!__imp_SysStringLen` at `0x18000fc2c`
- `OLEAUT32!__imp_SysStringLen` at `0x18000fc2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  int v4; // r15d
  unsigned int v5; // eax
  ATL::CComTypeInfoHolder::stringdispid *v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  unsigned __int64 v9; // kr00_8
  bool v10; // cf
  size_t v11; // rax
  OLECHAR *v12; // rax
  unsigned int i; // r12d
  unsigned int v15; // edx
  unsigned int v16; // edx
  OLECHAR *v17; // rcx
  BSTR pbstr; // [rsp+88h] [rbp+48h] BYREF
  _DWORD *v19; // [rsp+90h] [rbp+50h] BYREF
  __int64 v20; // [rsp+98h] [rbp+58h] BYREF

  v20 = 0;
  v4 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v20);
  if ( v4 >= 0 )
  {
    v5 = *(unsigned __int16 *)(v20 + 48);
    *((_DWORD *)this + 12) = v5;
    v6 = 0;
    if ( v5 )
    {
      v7 = v5;
      v9 = v5;
      v8 = 16LL * v5;
      if ( !is_mul_ok(v9, 0x10u) )
        v8 = -1;
      v10 = __CFADD__(v8, 8);
      v11 = v8 + 8;
      if ( v10 )
        v11 = -1;
      v12 = (OLECHAR *)operator new(v11);
      pbstr = v12;
      if ( v12 )
      {
        *(_QWORD *)v12 = v7;
        v6 = (ATL::CComTypeInfoHolder::stringdispid *)(v12 + 4);
        `eh vector constructor iterator'(
          v12 + 4,
          0x10u,
          (unsigned int)v7,
          (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
          (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::~stringdispid);
      }
      else
      {
        v6 = 0;
      }
    }
    if ( *((_DWORD *)this + 12) && !v6 )
    {
      *((_DWORD *)this + 12) = 0;
      return 2147942414LL;
    }
    for ( i = 0; (signed int)i < *((_DWORD *)this + 12); ++i )
    {
      v19 = 0;
      v4 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, _DWORD **))a2->lpVtbl->GetFuncDesc)(a2, i, &v19);
      if ( v4 < 0 )
      {
        if ( v6 )
          ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(v6, v15);
        v6 = 0;
        *((_DWORD *)this + 12) = 0;
        break;
      }
      pbstr = 0;
      v4 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->GetDocumentation)(
             a2,
             (unsigned int)*v19,
             &pbstr,
             0,
             0,
             0);
      if ( v4 < 0 )
      {
        if ( v6 )
          ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(v6, v16);
        v6 = 0;
        *((_DWORD *)this + 12) = 0;
        ((void (__fastcall *)(struct ITypeInfo *, _DWORD *))a2->lpVtbl->ReleaseFuncDesc)(a2, v19);
        SysFreeString(pbstr);
        break;
      }
      v17 = pbstr;
      pbstr = 0;
      *((_QWORD *)v6 + 2 * (int)i) = v17;
      *((_DWORD *)v6 + 4 * (int)i + 2) = SysStringLen(v17);
      *((_DWORD *)v6 + 4 * (int)i + 3) = *v19;
      ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseFuncDesc)(a2);
      SysFreeString(pbstr);
    }
    *((_QWORD *)this + 5) = v6;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v20);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000fae0  push    rbp
0x18000fae2  push    rbx
0x18000fae3  push    rsi
0x18000fae4  push    rdi
0x18000fae5  push    r12
0x18000fae7  push    r14
0x18000fae9  push    r15
0x18000faeb  mov     rbp, rsp
0x18000faee  sub     rsp, 40h
0x18000faf2  mov     rsi, rdx
0x18000faf5  mov     r14, rcx
0x18000faf8  mov     [rbp+arg_18], 0
0x18000fb00  mov     rax, [rdx]
0x18000fb03  lea     rdx, [rbp+arg_18]
0x18000fb07  mov     rcx, rsi
0x18000fb0a  mov     rax, [rax+18h]
0x18000fb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb13  mov     r15d, eax
0x18000fb16  test    eax, eax
0x18000fb18  js      loc_18000FCCA
0x18000fb1e  mov     rcx, [rbp+arg_18]
0x18000fb22  movzx   eax, word ptr [rcx+30h]
0x18000fb26  mov     [r14+30h], eax
0x18000fb2a  xor     edi, edi
0x18000fb2c  test    eax, eax
0x18000fb2e  jz      short loc_18000FB89
0x18000fb30  mov     ebx, eax
0x18000fb32  lea     r12d, [rdi+10h]
0x18000fb36  mov     eax, r12d
0x18000fb39  mul     rbx
0x18000fb3c  lea     rcx, [rdi-1]
0x18000fb40  cmovb   rax, rcx
0x18000fb44  add     rax, 8
0x18000fb48  cmovb   rax, rcx
0x18000fb4c  mov     rcx, rax; Size
0x18000fb4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fb54  mov     [rbp+pbstr], rax
0x18000fb58  test    rax, rax
0x18000fb5b  jz      short loc_18000FB87
0x18000fb5d  mov     [rax], rbx
0x18000fb60  lea     rdi, [rax+8]
0x18000fb64  lea     rax, ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x18000fb6b  mov     [rsp+40h+var_20], rax; void (*)(void *)
0x18000fb70  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x18000fb77  mov     r8d, ebx; unsigned __int64
0x18000fb7a  mov     edx, r12d; unsigned __int64
0x18000fb7d  mov     rcx, rdi; void *
0x18000fb80  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000fb85  jmp     short loc_18000FB89
0x18000fb87  xor     edi, edi
0x18000fb89  cmp     dword ptr [r14+30h], 0
0x18000fb8e  jz      short loc_18000FBA3
0x18000fb90  test    rdi, rdi
0x18000fb93  jnz     short loc_18000FBA3
0x18000fb95  mov     [r14+30h], edi
0x18000fb99  mov     eax, 8007000Eh
0x18000fb9e  jmp     loc_18000FCCD
0x18000fba3  xor     r12d, r12d
0x18000fba6  cmp     r12d, [r14+30h]
0x18000fbaa  jge     loc_18000FCB0
0x18000fbb0  mov     [rbp+arg_10], 0
0x18000fbb8  mov     rax, [rsi]
0x18000fbbb  lea     r8, [rbp+arg_10]
0x18000fbbf  mov     edx, r12d
0x18000fbc2  mov     rcx, rsi
0x18000fbc5  mov     rax, [rax+28h]
0x18000fbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbce  mov     r15d, eax
0x18000fbd1  test    eax, eax
0x18000fbd3  js      loc_18000FC9D
0x18000fbd9  mov     [rbp+pbstr], 0
0x18000fbe1  mov     rax, [rsi]
0x18000fbe4  mov     [rsp+40h+var_18], 0
0x18000fbed  mov     [rsp+40h+var_20], 0
0x18000fbf6  xor     r9d, r9d
0x18000fbf9  lea     r8, [rbp+pbstr]
0x18000fbfd  mov     rdx, [rbp+arg_10]
0x18000fc01  mov     edx, [rdx]
0x18000fc03  mov     rcx, rsi
0x18000fc06  mov     rax, [rax+60h]
0x18000fc0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc0f  mov     r15d, eax
0x18000fc12  test    eax, eax
0x18000fc14  js      short loc_18000FC66
0x18000fc16  mov     rcx, [rbp+pbstr]; pbstr
0x18000fc1a  mov     [rbp+pbstr], 0
0x18000fc22  movsxd  rbx, r12d
0x18000fc25  add     rbx, rbx
0x18000fc28  mov     [rdi+rbx*8], rcx
0x18000fc2c  call    cs:__imp_SysStringLen
0x18000fc32  mov     [rdi+rbx*8+8], eax
0x18000fc36  mov     rdx, [rbp+arg_10]
0x18000fc3a  mov     eax, [rdx]
0x18000fc3c  mov     [rdi+rbx*8+0Ch], eax
0x18000fc40  mov     rax, [rsi]
0x18000fc43  mov     rcx, rsi
0x18000fc46  mov     rax, [rax+0A0h]
0x18000fc4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc52  nop
0x18000fc53  mov     rcx, [rbp+pbstr]; bstrString
0x18000fc57  call    cs:__imp_SysFreeString
0x18000fc5d  nop
0x18000fc5e  inc     r12d
0x18000fc61  jmp     loc_18000FBA6
0x18000fc66  test    rdi, rdi
0x18000fc69  jz      short loc_18000FC73
0x18000fc6b  mov     rcx, rdi; this
0x18000fc6e  call    ??_Estringdispid@CComTypeInfoHolder@ATL@@QEAAPEAXI@Z; ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(uint)
0x18000fc73  xor     edi, edi
0x18000fc75  mov     [r14+30h], edi
0x18000fc79  mov     rax, [rsi]
0x18000fc7c  mov     rdx, [rbp+arg_10]
0x18000fc80  mov     rcx, rsi
0x18000fc83  mov     rax, [rax+0A0h]
0x18000fc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc8f  nop
0x18000fc90  mov     rcx, [rbp+pbstr]; bstrString
0x18000fc94  call    cs:__imp_SysFreeString
0x18000fc9a  nop
0x18000fc9b  jmp     short loc_18000FCB0
0x18000fc9d  test    rdi, rdi
0x18000fca0  jz      short loc_18000FCAA
0x18000fca2  mov     rcx, rdi; this
0x18000fca5  call    ??_Estringdispid@CComTypeInfoHolder@ATL@@QEAAPEAXI@Z; ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(uint)
0x18000fcaa  xor     edi, edi
0x18000fcac  mov     [r14+30h], edi
0x18000fcb0  mov     [r14+28h], rdi
0x18000fcb4  mov     rax, [rsi]
0x18000fcb7  mov     rdx, [rbp+arg_18]
0x18000fcbb  mov     rcx, rsi
0x18000fcbe  mov     rax, [rax+98h]
0x18000fcc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcca  mov     eax, r15d
0x18000fccd  add     rsp, 40h
0x18000fcd1  pop     r15
0x18000fcd3  pop     r14
0x18000fcd5  pop     r12
0x18000fcd7  pop     rdi
0x18000fcd8  pop     rsi
0x18000fcd9  pop     rbx
0x18000fcda  pop     rbp
0x18000fcdb  retn
```
