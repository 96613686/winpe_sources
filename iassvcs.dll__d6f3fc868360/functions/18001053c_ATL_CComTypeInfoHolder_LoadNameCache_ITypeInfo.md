# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x18001053c`
- end: `0x18001077f`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(OLECHAR *this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010020`

## callees

- `0x180001d84`
- `0x18000d98c`
- `0x18001053c`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800106e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180010738`
- `OLEAUT32!__imp_SysFreeString` at `0x1800106e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180010738`
- `OLEAUT32!__imp_SysStringLen` at `0x1800106f9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800106f9`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(OLECHAR *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rsi
  OLECHAR *v3; // rdi
  unsigned __int64 v4; // rcx
  __int64 v5; // r14
  __int64 v6; // rax
  bool v7; // cf
  size_t v8; // rax
  _QWORD *v9; // rax
  int v11; // r14d
  OLECHAR *v12; // r12
  BSTR pbstr; // [rsp+80h] [rbp+8h] BYREF
  struct ITypeInfo *v14; // [rsp+88h] [rbp+10h] BYREF
  __int64 v15; // [rsp+90h] [rbp+18h] BYREF
  _QWORD *v16; // [rsp+98h] [rbp+20h]

  v14 = a2;
  pbstr = this;
  v2 = a2;
  v15 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v15) >= 0 )
  {
    v3 = 0;
    pbstr = 0;
    v4 = *(unsigned __int16 *)(v15 + 48);
    dword_1800242D0 = v4;
    qword_1800242C8 = 0;
    if ( (_WORD)v4 )
    {
      v5 = (unsigned int)v4;
      v6 = 16 * v4;
      if ( !is_mul_ok(v4, 0x10u) )
        v6 = -1;
      v7 = __CFADD__(v6, 8);
      v8 = v6 + 8;
      if ( v7 )
        v8 = -1;
      try
      {
        v9 = operator new(v8);
        v16 = v9;
        if ( v9 )
        {
          *v9 = v5;
          v3 = (OLECHAR *)(v9 + 1);
          `eh vector constructor iterator'(
            v9 + 1,
            0x10u,
            (unsigned int)v5,
            (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
            (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        }
        else
        {
          v3 = 0;
        }
        pbstr = v3;
      }
      catch ( ... )
      {
        v2 = v14;
        v3 = pbstr;
      }
      if ( !v3 )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v15);
        return 2147942414LL;
      }
      LODWORD(v4) = dword_1800242D0;
    }
    v11 = 0;
    if ( (int)v4 > 0 )
    {
      do
      {
        v14 = 0;
        *(_QWORD *)&v3[8 * v11 + 4] = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v2->lpVtbl->GetFuncDesc)(
               v2,
               (unsigned int)v11,
               &v14) >= 0 )
        {
          pbstr = 0;
          if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v2->lpVtbl->GetDocumentation)(
                 v2,
                 LODWORD(v14->lpVtbl),
                 &pbstr,
                 0,
                 0,
                 0) >= 0 )
          {
            v12 = pbstr;
            pbstr = 0;
            if ( *(OLECHAR **)&v3[8 * v11] == v12 )
            {
              v12 = *(OLECHAR **)&v3[8 * v11];
            }
            else
            {
              SysFreeString(*(BSTR *)&v3[8 * v11]);
              *(_QWORD *)&v3[8 * v11] = v12;
            }
            *(_DWORD *)&v3[8 * v11 + 4] = SysStringLen(v12);
            *(_DWORD *)&v3[8 * v11 + 6] = v14->lpVtbl;
          }
          ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
          SysFreeString(pbstr);
        }
        ++v11;
      }
      while ( v11 < dword_1800242D0 );
    }
    qword_1800242C8 = (__int64)v3;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v15);
  }
  return 0;
}

```

## disassembly

```asm
0x18001053c  mov     r11, rsp
0x18001053f  mov     [r11+10h], rdx
0x180010543  mov     [r11+8], rcx
0x180010547  push    rbx
0x180010548  push    rsi
0x180010549  push    rdi
0x18001054a  push    r12
0x18001054c  push    r14
0x18001054e  push    r15
0x180010550  sub     rsp, 48h
0x180010554  mov     rsi, rdx
0x180010557  xor     ebx, ebx
0x180010559  mov     [r11+18h], rbx
0x18001055d  mov     rax, [rdx]
0x180010560  lea     rdx, [r11+18h]
0x180010564  mov     rcx, rsi
0x180010567  mov     rax, [rax+18h]
0x18001056b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010570  test    eax, eax
0x180010572  js      loc_18001076F
0x180010578  mov     edi, ebx
0x18001057a  mov     [rsp+78h+pbstr], rbx
0x180010582  mov     rax, [rsp+78h+arg_10]
0x18001058a  movzx   ecx, word ptr [rax+30h]
0x18001058e  mov     cs:dword_1800242D0, ecx
0x180010594  mov     cs:qword_1800242C8, rbx
0x18001059b  test    cx, cx
0x18001059e  jz      loc_18001064E
0x1800105a4  mov     r14d, ecx
0x1800105a7  lea     r15d, [rbx+10h]
0x1800105ab  mov     eax, r15d
0x1800105ae  mul     rcx
0x1800105b1  lea     rcx, [rbx-1]
0x1800105b5  cmovb   rax, rcx
0x1800105b9  add     rax, 8
0x1800105bd  cmovb   rax, rcx
0x1800105c1  mov     rcx, rax; Size
0x1800105c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800105c9  mov     [rsp+78h+arg_18], rax
0x1800105d1  test    rax, rax
0x1800105d4  jz      short loc_180010600
0x1800105d6  mov     [rax], r14
0x1800105d9  lea     rdi, [rax+8]
0x1800105dd  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x1800105e4  mov     [rsp+78h+var_58], rax; void (*)(void *)
0x1800105e9  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x1800105f0  mov     r8d, r14d; unsigned __int64
0x1800105f3  mov     edx, r15d; unsigned __int64
0x1800105f6  mov     rcx, rdi; void *
0x1800105f9  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800105fe  jmp     short loc_180010603
0x180010600  mov     rdi, rbx
0x180010603  mov     [rsp+78h+pbstr], rdi
0x18001060b  jmp     short loc_18001061F
0x18001060d  xor     ebx, ebx
0x18001060f  mov     rsi, [rsp+78h+arg_8]
0x180010617  mov     rdi, [rsp+78h+pbstr]
0x18001061f  test    rdi, rdi
0x180010622  jnz     short loc_180010648
0x180010624  mov     rax, [rsi]
0x180010627  mov     rdx, [rsp+78h+arg_10]
0x18001062f  mov     rcx, rsi
0x180010632  mov     rax, [rax+98h]
0x180010639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001063e  mov     eax, 8007000Eh
0x180010643  jmp     loc_180010771
0x180010648  mov     ecx, cs:dword_1800242D0
0x18001064e  mov     r14d, ebx
0x180010651  test    ecx, ecx
0x180010653  jle     loc_18001074E
0x180010659  mov     [rsp+78h+arg_8], rbx
0x180010661  movsxd  r15, r14d
0x180010664  add     r15, r15
0x180010667  mov     qword ptr [rdi+r15*8+8], 0
0x180010670  mov     rax, [rsi]
0x180010673  lea     r8, [rsp+78h+arg_8]
0x18001067b  mov     edx, r14d
0x18001067e  mov     rcx, rsi
0x180010681  mov     rax, [rax+28h]
0x180010685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001068a  test    eax, eax
0x18001068c  js      loc_18001073E
0x180010692  mov     [rsp+78h+pbstr], rbx
0x18001069a  mov     rax, [rsi]
0x18001069d  mov     [rsp+78h+var_50], rbx
0x1800106a2  mov     [rsp+78h+var_58], rbx
0x1800106a7  xor     r9d, r9d
0x1800106aa  lea     r8, [rsp+78h+pbstr]
0x1800106b2  mov     rdx, [rsp+78h+arg_8]
0x1800106ba  mov     edx, [rdx]
0x1800106bc  mov     rcx, rsi
0x1800106bf  mov     rax, [rax+60h]
0x1800106c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106c8  test    eax, eax
0x1800106ca  js      short loc_180010715
0x1800106cc  mov     r12, [rsp+78h+pbstr]
0x1800106d4  mov     [rsp+78h+pbstr], rbx
0x1800106dc  cmp     [rdi+r15*8], r12
0x1800106e0  jz      short loc_1800106F2
0x1800106e2  mov     rcx, [rdi+r15*8]; bstrString
0x1800106e6  call    cs:__imp_SysFreeString
0x1800106ec  mov     [rdi+r15*8], r12
0x1800106f0  jmp     short loc_1800106F6
0x1800106f2  mov     r12, [rdi+r15*8]
0x1800106f6  mov     rcx, r12; pbstr
0x1800106f9  call    cs:__imp_SysStringLen
0x1800106ff  mov     [rdi+r15*8+8], eax
0x180010704  mov     rdx, [rsp+78h+arg_8]
0x18001070c  mov     eax, [rdx]
0x18001070e  mov     [rdi+r15*8+0Ch], eax
0x180010713  jmp     short loc_18001071D
0x180010715  mov     rdx, [rsp+78h+arg_8]
0x18001071d  mov     rax, [rsi]
0x180010720  mov     rcx, rsi
0x180010723  mov     rax, [rax+0A0h]
0x18001072a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001072f  nop
0x180010730  mov     rcx, [rsp+78h+pbstr]; bstrString
0x180010738  call    cs:__imp_SysFreeString
0x18001073e  inc     r14d
0x180010741  cmp     r14d, cs:dword_1800242D0
0x180010748  jl      loc_180010659
0x18001074e  mov     cs:qword_1800242C8, rdi
0x180010755  mov     rax, [rsi]
0x180010758  mov     rdx, [rsp+78h+arg_10]
0x180010760  mov     rcx, rsi
0x180010763  mov     rax, [rax+98h]
0x18001076a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001076f  xor     eax, eax
0x180010771  add     rsp, 48h
0x180010775  pop     r15
0x180010777  pop     r14
0x180010779  pop     r12
0x18001077b  pop     rdi
0x18001077c  pop     rsi
0x18001077d  pop     rbx
0x18001077e  retn
```
