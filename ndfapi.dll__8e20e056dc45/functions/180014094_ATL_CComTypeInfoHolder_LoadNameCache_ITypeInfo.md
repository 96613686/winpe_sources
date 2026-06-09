# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x180014094`
- end: `0x1800142f9`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800131d8`

## callees

- `0x1800018b4`
- `0x1800025cc`
- `0x180014094`
- `0x180021010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001425b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800142ad`
- `OLEAUT32!__imp_SysFreeString` at `0x18001425b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800142ad`
- `OLEAUT32!__imp_SysStringLen` at `0x18001426e`
- `OLEAUT32!__imp_SysStringLen` at `0x18001426e`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rsi
  OLECHAR *v4; // rdi
  unsigned __int64 v5; // rcx
  _DWORD *v6; // r14
  __int64 v7; // r15
  __int64 v8; // rax
  bool v9; // cf
  unsigned __int64 v10; // rax
  _QWORD *v11; // rax
  unsigned int i; // r15d
  OLECHAR *v14; // r13
  char *v15; // [rsp+40h] [rbp-48h]
  OLECHAR **v16; // [rsp+48h] [rbp-40h]
  struct ITypeInfo *v17; // [rsp+98h] [rbp+10h] BYREF
  BSTR pbstr; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+20h] BYREF

  v17 = a2;
  v2 = a2;
  v19 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v19) >= 0 )
  {
    v4 = 0;
    pbstr = 0;
    v5 = *(unsigned __int16 *)(v19 + 48);
    v6 = (_DWORD *)((char *)this + 48);
    v15 = (char *)this + 48;
    *((_DWORD *)this + 12) = v5;
    v16 = (OLECHAR **)((char *)this + 40);
    *((_QWORD *)this + 5) = 0;
    if ( (_DWORD)v5 )
    {
      v7 = (unsigned int)v5;
      v8 = 16 * v5;
      if ( !is_mul_ok(v5, 0x10u) )
        v8 = -1;
      v9 = __CFADD__(v8, 8);
      v10 = v8 + 8;
      if ( v9 )
        v10 = -1;
      try
      {
        v11 = operator new[](v10);
        if ( v11 )
        {
          *v11 = v7;
          v4 = (OLECHAR *)(v11 + 1);
          `eh vector constructor iterator'(
            v11 + 1,
            0x10u,
            (unsigned int)v7,
            (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
            (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        }
        else
        {
          v4 = 0;
        }
        pbstr = v4;
      }
      catch ( ... )
      {
        v2 = v17;
        v4 = pbstr;
        v6 = v15;
      }
      if ( !v4 )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v19);
        return 2147942414LL;
      }
    }
    for ( i = 0; (signed int)i < *v6; ++i )
    {
      v17 = 0;
      *(_QWORD *)&v4[8 * i + 4] = 0;
      if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v2->lpVtbl->GetFuncDesc)(v2, i, &v17) >= 0 )
      {
        pbstr = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v2->lpVtbl->GetDocumentation)(
               v2,
               LODWORD(v17->lpVtbl),
               &pbstr,
               0,
               0,
               0) >= 0 )
        {
          v14 = pbstr;
          pbstr = 0;
          if ( *(OLECHAR **)&v4[8 * i] == v14 )
          {
            v14 = *(OLECHAR **)&v4[8 * i];
          }
          else
          {
            SysFreeString(*(BSTR *)&v4[8 * i]);
            *(_QWORD *)&v4[8 * i] = v14;
          }
          *(_DWORD *)&v4[8 * i + 4] = SysStringLen(v14);
          *(_DWORD *)&v4[8 * i + 6] = v17->lpVtbl;
        }
        ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
        SysFreeString(pbstr);
      }
    }
    *v16 = v4;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v19);
  }
  return 0;
}

```

## disassembly

```asm
0x180014094  mov     r11, rsp
0x180014097  mov     [r11+8], rsi
0x18001409b  mov     [r11+10h], rdx
0x18001409f  push    rdi
0x1800140a0  push    r12
0x1800140a2  push    r13
0x1800140a4  push    r14
0x1800140a6  push    r15
0x1800140a8  sub     rsp, 60h
0x1800140ac  mov     rsi, rdx
0x1800140af  mov     r15, rcx
0x1800140b2  mov     qword ptr [r11+20h], 0
0x1800140ba  mov     rax, [rdx]
0x1800140bd  lea     rdx, [r11+20h]
0x1800140c1  mov     rcx, rsi
0x1800140c4  mov     rax, [rax+18h]
0x1800140c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140cd  test    eax, eax
0x1800140cf  js      loc_1800142E1
0x1800140d5  xor     edi, edi
0x1800140d7  mov     [rsp+88h+pbstr], rdi
0x1800140df  mov     rax, [rsp+88h+arg_18]
0x1800140e7  movzx   ecx, word ptr [rax+30h]
0x1800140eb  lea     r14, [r15+30h]
0x1800140ef  mov     [rsp+88h+var_48], r14
0x1800140f4  mov     [r14], ecx
0x1800140f7  lea     rax, [r15+28h]
0x1800140fb  mov     [rsp+88h+var_40], rax
0x180014100  mov     [rax], rdi
0x180014103  test    ecx, ecx
0x180014105  jz      loc_1800141AE
0x18001410b  mov     r15d, ecx
0x18001410e  lea     r12d, [rdi+10h]
0x180014112  mov     eax, r12d
0x180014115  mul     rcx
0x180014118  lea     rcx, [rdi-1]
0x18001411c  cmovb   rax, rcx
0x180014120  add     rax, 8
0x180014124  cmovb   rax, rcx
0x180014128  mov     rcx, rax; unsigned __int64
0x18001412b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014130  mov     [rsp+88h+var_38], rax
0x180014135  test    rax, rax
0x180014138  jz      short loc_180014164
0x18001413a  mov     [rax], r15
0x18001413d  lea     rdi, [rax+8]
0x180014141  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180014148  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x18001414d  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x180014154  mov     r8d, r15d; unsigned __int64
0x180014157  mov     edx, r12d; unsigned __int64
0x18001415a  mov     rcx, rdi; void *
0x18001415d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180014162  jmp     short loc_180014166
0x180014164  xor     edi, edi
0x180014166  mov     [rsp+88h+pbstr], rdi
0x18001416e  jmp     short loc_180014185
0x180014170  mov     rsi, [rsp+88h+arg_8]
0x180014178  mov     rdi, [rsp+88h+pbstr]
0x180014180  mov     r14, [rsp+88h+var_48]
0x180014185  test    rdi, rdi
0x180014188  jnz     short loc_1800141AE
0x18001418a  mov     rax, [rsi]
0x18001418d  mov     rdx, [rsp+88h+arg_18]
0x180014195  mov     rcx, rsi
0x180014198  mov     rax, [rax+98h]
0x18001419f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141a4  mov     eax, 8007000Eh
0x1800141a9  jmp     loc_1800142E3
0x1800141ae  xor     r15d, r15d
0x1800141b1  cmp     [r14], r15d
0x1800141b4  jle     loc_1800142BF
0x1800141ba  mov     [rsp+88h+arg_8], 0
0x1800141c6  movsxd  r12, r15d
0x1800141c9  add     r12, r12
0x1800141cc  mov     qword ptr [rdi+r12*8+8], 0
0x1800141d5  mov     rax, [rsi]
0x1800141d8  lea     r8, [rsp+88h+arg_8]
0x1800141e0  mov     edx, r15d
0x1800141e3  mov     rcx, rsi
0x1800141e6  mov     rax, [rax+28h]
0x1800141ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141ef  test    eax, eax
0x1800141f1  js      loc_1800142B3
0x1800141f7  mov     [rsp+88h+pbstr], 0
0x180014203  mov     rax, [rsi]
0x180014206  mov     [rsp+88h+var_60], 0
0x18001420f  mov     [rsp+88h+var_68], 0
0x180014218  xor     r9d, r9d
0x18001421b  lea     r8, [rsp+88h+pbstr]
0x180014223  mov     rdx, [rsp+88h+arg_8]
0x18001422b  mov     edx, [rdx]
0x18001422d  mov     rcx, rsi
0x180014230  mov     rax, [rax+60h]
0x180014234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014239  test    eax, eax
0x18001423b  js      short loc_18001428A
0x18001423d  mov     r13, [rsp+88h+pbstr]
0x180014245  mov     [rsp+88h+pbstr], 0
0x180014251  cmp     [rdi+r12*8], r13
0x180014255  jz      short loc_180014267
0x180014257  mov     rcx, [rdi+r12*8]; bstrString
0x18001425b  call    cs:__imp_SysFreeString
0x180014261  mov     [rdi+r12*8], r13
0x180014265  jmp     short loc_18001426B
0x180014267  mov     r13, [rdi+r12*8]
0x18001426b  mov     rcx, r13; pbstr
0x18001426e  call    cs:__imp_SysStringLen
0x180014274  mov     [rdi+r12*8+8], eax
0x180014279  mov     rdx, [rsp+88h+arg_8]
0x180014281  mov     eax, [rdx]
0x180014283  mov     [rdi+r12*8+0Ch], eax
0x180014288  jmp     short loc_180014292
0x18001428a  mov     rdx, [rsp+88h+arg_8]
0x180014292  mov     rax, [rsi]
0x180014295  mov     rcx, rsi
0x180014298  mov     rax, [rax+0A0h]
0x18001429f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142a4  nop
0x1800142a5  mov     rcx, [rsp+88h+pbstr]; bstrString
0x1800142ad  call    cs:__imp_SysFreeString
0x1800142b3  inc     r15d
0x1800142b6  cmp     r15d, [r14]
0x1800142b9  jl      loc_1800141BA
0x1800142bf  mov     rax, [rsp+88h+var_40]
0x1800142c4  mov     [rax], rdi
0x1800142c7  mov     rax, [rsi]
0x1800142ca  mov     rdx, [rsp+88h+arg_18]
0x1800142d2  mov     rcx, rsi
0x1800142d5  mov     rax, [rax+98h]
0x1800142dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142e1  xor     eax, eax
0x1800142e3  mov     rsi, [rsp+88h+arg_0]
0x1800142eb  add     rsp, 60h
0x1800142ef  pop     r15
0x1800142f1  pop     r14
0x1800142f3  pop     r13
0x1800142f5  pop     r12
0x1800142f7  pop     rdi
0x1800142f8  retn
```
