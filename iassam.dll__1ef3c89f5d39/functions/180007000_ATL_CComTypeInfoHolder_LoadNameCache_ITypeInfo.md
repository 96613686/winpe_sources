# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x180007000`
- end: `0x180007265`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000680c`

## callees

- `0x180001e70`
- `0x1800033bc`
- `0x180007000`
- `0x18002e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800071c7`
- `OLEAUT32!__imp_SysFreeString` at `0x180007219`
- `OLEAUT32!__imp_SysFreeString` at `0x1800071c7`
- `OLEAUT32!__imp_SysFreeString` at `0x180007219`
- `OLEAUT32!__imp_SysStringLen` at `0x1800071da`
- `OLEAUT32!__imp_SysStringLen` at `0x1800071da`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rsi
  OLECHAR *v4; // rdi
  unsigned __int64 v5; // rcx
  _DWORD *v6; // r14
  __int64 v7; // r15
  __int64 v8; // rax
  bool v9; // cf
  size_t v10; // rax
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
        v11 = operator new(v10);
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
0x180007000  mov     r11, rsp
0x180007003  mov     [r11+8], rsi
0x180007007  mov     [r11+10h], rdx
0x18000700b  push    rdi
0x18000700c  push    r12
0x18000700e  push    r13
0x180007010  push    r14
0x180007012  push    r15
0x180007014  sub     rsp, 60h
0x180007018  mov     rsi, rdx
0x18000701b  mov     r15, rcx
0x18000701e  mov     qword ptr [r11+20h], 0
0x180007026  mov     rax, [rdx]
0x180007029  lea     rdx, [r11+20h]
0x18000702d  mov     rcx, rsi
0x180007030  mov     rax, [rax+18h]
0x180007034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007039  test    eax, eax
0x18000703b  js      loc_18000724D
0x180007041  xor     edi, edi
0x180007043  mov     [rsp+88h+pbstr], rdi
0x18000704b  mov     rax, [rsp+88h+arg_18]
0x180007053  movzx   ecx, word ptr [rax+30h]
0x180007057  lea     r14, [r15+30h]
0x18000705b  mov     [rsp+88h+var_48], r14
0x180007060  mov     [r14], ecx
0x180007063  lea     rax, [r15+28h]
0x180007067  mov     [rsp+88h+var_40], rax
0x18000706c  mov     [rax], rdi
0x18000706f  test    ecx, ecx
0x180007071  jz      loc_18000711A
0x180007077  mov     r15d, ecx
0x18000707a  lea     r12d, [rdi+10h]
0x18000707e  mov     eax, r12d
0x180007081  mul     rcx
0x180007084  lea     rcx, [rdi-1]
0x180007088  cmovb   rax, rcx
0x18000708c  add     rax, 8
0x180007090  cmovb   rax, rcx
0x180007094  mov     rcx, rax; Size
0x180007097  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000709c  mov     [rsp+88h+var_38], rax
0x1800070a1  test    rax, rax
0x1800070a4  jz      short loc_1800070D0
0x1800070a6  mov     [rax], r15
0x1800070a9  lea     rdi, [rax+8]
0x1800070ad  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x1800070b4  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x1800070b9  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x1800070c0  mov     r8d, r15d; unsigned __int64
0x1800070c3  mov     edx, r12d; unsigned __int64
0x1800070c6  mov     rcx, rdi; void *
0x1800070c9  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800070ce  jmp     short loc_1800070D2
0x1800070d0  xor     edi, edi
0x1800070d2  mov     [rsp+88h+pbstr], rdi
0x1800070da  jmp     short loc_1800070F1
0x1800070dc  mov     rsi, [rsp+88h+arg_8]
0x1800070e4  mov     rdi, [rsp+88h+pbstr]
0x1800070ec  mov     r14, [rsp+88h+var_48]
0x1800070f1  test    rdi, rdi
0x1800070f4  jnz     short loc_18000711A
0x1800070f6  mov     rax, [rsi]
0x1800070f9  mov     rdx, [rsp+88h+arg_18]
0x180007101  mov     rcx, rsi
0x180007104  mov     rax, [rax+98h]
0x18000710b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007110  mov     eax, 8007000Eh
0x180007115  jmp     loc_18000724F
0x18000711a  xor     r15d, r15d
0x18000711d  cmp     [r14], r15d
0x180007120  jle     loc_18000722B
0x180007126  mov     [rsp+88h+arg_8], 0
0x180007132  movsxd  r12, r15d
0x180007135  add     r12, r12
0x180007138  mov     qword ptr [rdi+r12*8+8], 0
0x180007141  mov     rax, [rsi]
0x180007144  lea     r8, [rsp+88h+arg_8]
0x18000714c  mov     edx, r15d
0x18000714f  mov     rcx, rsi
0x180007152  mov     rax, [rax+28h]
0x180007156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000715b  test    eax, eax
0x18000715d  js      loc_18000721F
0x180007163  mov     [rsp+88h+pbstr], 0
0x18000716f  mov     rax, [rsi]
0x180007172  mov     [rsp+88h+var_60], 0
0x18000717b  mov     [rsp+88h+var_68], 0
0x180007184  xor     r9d, r9d
0x180007187  lea     r8, [rsp+88h+pbstr]
0x18000718f  mov     rdx, [rsp+88h+arg_8]
0x180007197  mov     edx, [rdx]
0x180007199  mov     rcx, rsi
0x18000719c  mov     rax, [rax+60h]
0x1800071a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a5  test    eax, eax
0x1800071a7  js      short loc_1800071F6
0x1800071a9  mov     r13, [rsp+88h+pbstr]
0x1800071b1  mov     [rsp+88h+pbstr], 0
0x1800071bd  cmp     [rdi+r12*8], r13
0x1800071c1  jz      short loc_1800071D3
0x1800071c3  mov     rcx, [rdi+r12*8]; bstrString
0x1800071c7  call    cs:__imp_SysFreeString
0x1800071cd  mov     [rdi+r12*8], r13
0x1800071d1  jmp     short loc_1800071D7
0x1800071d3  mov     r13, [rdi+r12*8]
0x1800071d7  mov     rcx, r13; pbstr
0x1800071da  call    cs:__imp_SysStringLen
0x1800071e0  mov     [rdi+r12*8+8], eax
0x1800071e5  mov     rdx, [rsp+88h+arg_8]
0x1800071ed  mov     eax, [rdx]
0x1800071ef  mov     [rdi+r12*8+0Ch], eax
0x1800071f4  jmp     short loc_1800071FE
0x1800071f6  mov     rdx, [rsp+88h+arg_8]
0x1800071fe  mov     rax, [rsi]
0x180007201  mov     rcx, rsi
0x180007204  mov     rax, [rax+0A0h]
0x18000720b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007210  nop
0x180007211  mov     rcx, [rsp+88h+pbstr]; bstrString
0x180007219  call    cs:__imp_SysFreeString
0x18000721f  inc     r15d
0x180007222  cmp     r15d, [r14]
0x180007225  jl      loc_180007126
0x18000722b  mov     rax, [rsp+88h+var_40]
0x180007230  mov     [rax], rdi
0x180007233  mov     rax, [rsi]
0x180007236  mov     rdx, [rsp+88h+arg_18]
0x18000723e  mov     rcx, rsi
0x180007241  mov     rax, [rax+98h]
0x180007248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000724d  xor     eax, eax
0x18000724f  mov     rsi, [rsp+88h+arg_0]
0x180007257  add     rsp, 60h
0x18000725b  pop     r15
0x18000725d  pop     r14
0x18000725f  pop     r13
0x180007261  pop     r12
0x180007263  pop     rdi
0x180007264  retn
```
