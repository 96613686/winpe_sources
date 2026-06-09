# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x18000f06c`
- end: `0x18000f268`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ea78`

## callees

- `0x1800019c8`
- `0x180002d84`
- `0x18000f06c`
- `0x180014ae8`
- `0x180022010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000f1e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f220`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f1e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f220`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f1b8`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f1b8`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  int v4; // r15d
  unsigned int v5; // eax
  ATL::CComTypeInfoHolder::stringdispid *v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  unsigned __int64 v9; // kr00_8
  bool v10; // cf
  unsigned __int64 v11; // rax
  OLECHAR *v12; // rax
  unsigned int i; // r12d
  OLECHAR *v15; // rcx
  BSTR pbstr; // [rsp+88h] [rbp+48h] BYREF
  _DWORD *v17; // [rsp+90h] [rbp+50h] BYREF
  __int64 v18; // [rsp+98h] [rbp+58h] BYREF

  v18 = 0;
  v4 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v18);
  if ( v4 >= 0 )
  {
    v5 = *(unsigned __int16 *)(v18 + 48);
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
      v12 = (OLECHAR *)MmAllocate(v11);
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
      v17 = 0;
      v4 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, _DWORD **))a2->lpVtbl->GetFuncDesc)(a2, i, &v17);
      if ( v4 < 0 )
      {
        if ( v6 )
          ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(v6);
        v6 = 0;
        *((_DWORD *)this + 12) = 0;
        break;
      }
      pbstr = 0;
      v4 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->GetDocumentation)(
             a2,
             (unsigned int)*v17,
             &pbstr,
             0,
             0,
             0);
      if ( v4 < 0 )
      {
        if ( v6 )
          ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(v6);
        v6 = 0;
        *((_DWORD *)this + 12) = 0;
        ((void (__fastcall *)(struct ITypeInfo *, _DWORD *))a2->lpVtbl->ReleaseFuncDesc)(a2, v17);
        SysFreeString(pbstr);
        break;
      }
      v15 = pbstr;
      pbstr = 0;
      *((_QWORD *)v6 + 2 * (int)i) = v15;
      *((_DWORD *)v6 + 4 * (int)i + 2) = SysStringLen(v15);
      *((_DWORD *)v6 + 4 * (int)i + 3) = *v17;
      ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseFuncDesc)(a2);
      SysFreeString(pbstr);
    }
    *((_QWORD *)this + 5) = v6;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v18);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f06c  push    rbp
0x18000f06e  push    rbx
0x18000f06f  push    rsi
0x18000f070  push    rdi
0x18000f071  push    r12
0x18000f073  push    r14
0x18000f075  push    r15
0x18000f077  mov     rbp, rsp
0x18000f07a  sub     rsp, 40h
0x18000f07e  mov     rsi, rdx
0x18000f081  mov     r14, rcx
0x18000f084  mov     [rbp+arg_18], 0
0x18000f08c  mov     rax, [rdx]
0x18000f08f  lea     rdx, [rbp+arg_18]
0x18000f093  mov     rcx, rsi
0x18000f096  mov     rax, [rax+18h]
0x18000f09a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f09f  mov     r15d, eax
0x18000f0a2  test    eax, eax
0x18000f0a4  js      loc_18000F256
0x18000f0aa  mov     rcx, [rbp+arg_18]
0x18000f0ae  movzx   eax, word ptr [rcx+30h]
0x18000f0b2  mov     [r14+30h], eax
0x18000f0b6  xor     edi, edi
0x18000f0b8  test    eax, eax
0x18000f0ba  jz      short loc_18000F115
0x18000f0bc  mov     ebx, eax
0x18000f0be  lea     r12d, [rdi+10h]
0x18000f0c2  mov     eax, r12d
0x18000f0c5  mul     rbx
0x18000f0c8  lea     rcx, [rdi-1]
0x18000f0cc  cmovb   rax, rcx
0x18000f0d0  add     rax, 8
0x18000f0d4  cmovb   rax, rcx
0x18000f0d8  mov     rcx, rax; unsigned __int64
0x18000f0db  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000f0e0  mov     [rbp+pbstr], rax
0x18000f0e4  test    rax, rax
0x18000f0e7  jz      short loc_18000F113
0x18000f0e9  mov     [rax], rbx
0x18000f0ec  lea     rdi, [rax+8]
0x18000f0f0  lea     rax, ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x18000f0f7  mov     [rsp+40h+var_20], rax; void (*)(void *)
0x18000f0fc  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x18000f103  mov     r8d, ebx; unsigned __int64
0x18000f106  mov     edx, r12d; unsigned __int64
0x18000f109  mov     rcx, rdi; void *
0x18000f10c  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000f111  jmp     short loc_18000F115
0x18000f113  xor     edi, edi
0x18000f115  cmp     dword ptr [r14+30h], 0
0x18000f11a  jz      short loc_18000F12F
0x18000f11c  test    rdi, rdi
0x18000f11f  jnz     short loc_18000F12F
0x18000f121  mov     [r14+30h], edi
0x18000f125  mov     eax, 8007000Eh
0x18000f12a  jmp     loc_18000F259
0x18000f12f  xor     r12d, r12d
0x18000f132  cmp     r12d, [r14+30h]
0x18000f136  jge     loc_18000F23C
0x18000f13c  mov     [rbp+arg_10], 0
0x18000f144  mov     rax, [rsi]
0x18000f147  lea     r8, [rbp+arg_10]
0x18000f14b  mov     edx, r12d
0x18000f14e  mov     rcx, rsi
0x18000f151  mov     rax, [rax+28h]
0x18000f155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f15a  mov     r15d, eax
0x18000f15d  test    eax, eax
0x18000f15f  js      loc_18000F229
0x18000f165  mov     [rbp+pbstr], 0
0x18000f16d  mov     rax, [rsi]
0x18000f170  mov     [rsp+40h+var_18], 0
0x18000f179  mov     [rsp+40h+var_20], 0
0x18000f182  xor     r9d, r9d
0x18000f185  lea     r8, [rbp+pbstr]
0x18000f189  mov     rdx, [rbp+arg_10]
0x18000f18d  mov     edx, [rdx]
0x18000f18f  mov     rcx, rsi
0x18000f192  mov     rax, [rax+60h]
0x18000f196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f19b  mov     r15d, eax
0x18000f19e  test    eax, eax
0x18000f1a0  js      short loc_18000F1F2
0x18000f1a2  mov     rcx, [rbp+pbstr]; pbstr
0x18000f1a6  mov     [rbp+pbstr], 0
0x18000f1ae  movsxd  rbx, r12d
0x18000f1b1  add     rbx, rbx
0x18000f1b4  mov     [rdi+rbx*8], rcx
0x18000f1b8  call    cs:__imp_SysStringLen
0x18000f1be  mov     [rdi+rbx*8+8], eax
0x18000f1c2  mov     rdx, [rbp+arg_10]
0x18000f1c6  mov     eax, [rdx]
0x18000f1c8  mov     [rdi+rbx*8+0Ch], eax
0x18000f1cc  mov     rax, [rsi]
0x18000f1cf  mov     rcx, rsi
0x18000f1d2  mov     rax, [rax+0A0h]
0x18000f1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1de  nop
0x18000f1df  mov     rcx, [rbp+pbstr]; bstrString
0x18000f1e3  call    cs:__imp_SysFreeString
0x18000f1e9  nop
0x18000f1ea  inc     r12d
0x18000f1ed  jmp     loc_18000F132
0x18000f1f2  test    rdi, rdi
0x18000f1f5  jz      short loc_18000F1FF
0x18000f1f7  mov     rcx, rdi; this
0x18000f1fa  call    ??_Estringdispid@CComTypeInfoHolder@ATL@@QEAAPEAXI@Z; ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(uint)
0x18000f1ff  xor     edi, edi
0x18000f201  mov     [r14+30h], edi
0x18000f205  mov     rax, [rsi]
0x18000f208  mov     rdx, [rbp+arg_10]
0x18000f20c  mov     rcx, rsi
0x18000f20f  mov     rax, [rax+0A0h]
0x18000f216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f21b  nop
0x18000f21c  mov     rcx, [rbp+pbstr]; bstrString
0x18000f220  call    cs:__imp_SysFreeString
0x18000f226  nop
0x18000f227  jmp     short loc_18000F23C
0x18000f229  test    rdi, rdi
0x18000f22c  jz      short loc_18000F236
0x18000f22e  mov     rcx, rdi; this
0x18000f231  call    ??_Estringdispid@CComTypeInfoHolder@ATL@@QEAAPEAXI@Z; ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(uint)
0x18000f236  xor     edi, edi
0x18000f238  mov     [r14+30h], edi
0x18000f23c  mov     [r14+28h], rdi
0x18000f240  mov     rax, [rsi]
0x18000f243  mov     rdx, [rbp+arg_18]
0x18000f247  mov     rcx, rsi
0x18000f24a  mov     rax, [rax+98h]
0x18000f251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f256  mov     eax, r15d
0x18000f259  add     rsp, 40h
0x18000f25d  pop     r15
0x18000f25f  pop     r14
0x18000f261  pop     r12
0x18000f263  pop     rdi
0x18000f264  pop     rsi
0x18000f265  pop     rbx
0x18000f266  pop     rbp
0x18000f267  retn
```
