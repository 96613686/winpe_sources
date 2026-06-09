# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x180013844`
- end: `0x180013a87`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(OLECHAR *this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001317c`

## callees

- `0x180001618`
- `0x1800020cc`
- `0x180013844`
- `0x18001c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800139ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a40`
- `OLEAUT32!__imp_SysFreeString` at `0x1800139ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a40`
- `OLEAUT32!__imp_SysStringLen` at `0x180013a01`
- `OLEAUT32!__imp_SysStringLen` at `0x180013a01`

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
  unsigned __int64 v8; // rax
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
    dword_180027110 = v4;
    qword_180027108 = 0;
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
        v9 = operator new[](v8);
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
      LODWORD(v4) = dword_180027110;
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
      while ( v11 < dword_180027110 );
    }
    qword_180027108 = (__int64)v3;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180013844  mov     r11, rsp
0x180013847  mov     [r11+10h], rdx
0x18001384b  mov     [r11+8], rcx
0x18001384f  push    rbx
0x180013850  push    rsi
0x180013851  push    rdi
0x180013852  push    r12
0x180013854  push    r14
0x180013856  push    r15
0x180013858  sub     rsp, 48h
0x18001385c  mov     rsi, rdx
0x18001385f  xor     ebx, ebx
0x180013861  mov     [r11+18h], rbx
0x180013865  mov     rax, [rdx]
0x180013868  lea     rdx, [r11+18h]
0x18001386c  mov     rcx, rsi
0x18001386f  mov     rax, [rax+18h]
0x180013873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013878  test    eax, eax
0x18001387a  js      loc_180013A77
0x180013880  mov     edi, ebx
0x180013882  mov     [rsp+78h+pbstr], rbx
0x18001388a  mov     rax, [rsp+78h+arg_10]
0x180013892  movzx   ecx, word ptr [rax+30h]
0x180013896  mov     cs:dword_180027110, ecx
0x18001389c  mov     cs:qword_180027108, rbx
0x1800138a3  test    cx, cx
0x1800138a6  jz      loc_180013956
0x1800138ac  mov     r14d, ecx
0x1800138af  lea     r15d, [rbx+10h]
0x1800138b3  mov     eax, r15d
0x1800138b6  mul     rcx
0x1800138b9  lea     rcx, [rbx-1]
0x1800138bd  cmovb   rax, rcx
0x1800138c1  add     rax, 8
0x1800138c5  cmovb   rax, rcx
0x1800138c9  mov     rcx, rax; unsigned __int64
0x1800138cc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800138d1  mov     [rsp+78h+arg_18], rax
0x1800138d9  test    rax, rax
0x1800138dc  jz      short loc_180013908
0x1800138de  mov     [rax], r14
0x1800138e1  lea     rdi, [rax+8]
0x1800138e5  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x1800138ec  mov     [rsp+78h+var_58], rax; void (*)(void *)
0x1800138f1  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x1800138f8  mov     r8d, r14d; unsigned __int64
0x1800138fb  mov     edx, r15d; unsigned __int64
0x1800138fe  mov     rcx, rdi; void *
0x180013901  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180013906  jmp     short loc_18001390B
0x180013908  mov     rdi, rbx
0x18001390b  mov     [rsp+78h+pbstr], rdi
0x180013913  jmp     short loc_180013927
0x180013915  xor     ebx, ebx
0x180013917  mov     rsi, [rsp+78h+arg_8]
0x18001391f  mov     rdi, [rsp+78h+pbstr]
0x180013927  test    rdi, rdi
0x18001392a  jnz     short loc_180013950
0x18001392c  mov     rax, [rsi]
0x18001392f  mov     rdx, [rsp+78h+arg_10]
0x180013937  mov     rcx, rsi
0x18001393a  mov     rax, [rax+98h]
0x180013941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013946  mov     eax, 8007000Eh
0x18001394b  jmp     loc_180013A79
0x180013950  mov     ecx, cs:dword_180027110
0x180013956  mov     r14d, ebx
0x180013959  test    ecx, ecx
0x18001395b  jle     loc_180013A56
0x180013961  mov     [rsp+78h+arg_8], rbx
0x180013969  movsxd  r15, r14d
0x18001396c  add     r15, r15
0x18001396f  mov     qword ptr [rdi+r15*8+8], 0
0x180013978  mov     rax, [rsi]
0x18001397b  lea     r8, [rsp+78h+arg_8]
0x180013983  mov     edx, r14d
0x180013986  mov     rcx, rsi
0x180013989  mov     rax, [rax+28h]
0x18001398d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013992  test    eax, eax
0x180013994  js      loc_180013A46
0x18001399a  mov     [rsp+78h+pbstr], rbx
0x1800139a2  mov     rax, [rsi]
0x1800139a5  mov     [rsp+78h+var_50], rbx
0x1800139aa  mov     [rsp+78h+var_58], rbx
0x1800139af  xor     r9d, r9d
0x1800139b2  lea     r8, [rsp+78h+pbstr]
0x1800139ba  mov     rdx, [rsp+78h+arg_8]
0x1800139c2  mov     edx, [rdx]
0x1800139c4  mov     rcx, rsi
0x1800139c7  mov     rax, [rax+60h]
0x1800139cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139d0  test    eax, eax
0x1800139d2  js      short loc_180013A1D
0x1800139d4  mov     r12, [rsp+78h+pbstr]
0x1800139dc  mov     [rsp+78h+pbstr], rbx
0x1800139e4  cmp     [rdi+r15*8], r12
0x1800139e8  jz      short loc_1800139FA
0x1800139ea  mov     rcx, [rdi+r15*8]; bstrString
0x1800139ee  call    cs:__imp_SysFreeString
0x1800139f4  mov     [rdi+r15*8], r12
0x1800139f8  jmp     short loc_1800139FE
0x1800139fa  mov     r12, [rdi+r15*8]
0x1800139fe  mov     rcx, r12; pbstr
0x180013a01  call    cs:__imp_SysStringLen
0x180013a07  mov     [rdi+r15*8+8], eax
0x180013a0c  mov     rdx, [rsp+78h+arg_8]
0x180013a14  mov     eax, [rdx]
0x180013a16  mov     [rdi+r15*8+0Ch], eax
0x180013a1b  jmp     short loc_180013A25
0x180013a1d  mov     rdx, [rsp+78h+arg_8]
0x180013a25  mov     rax, [rsi]
0x180013a28  mov     rcx, rsi
0x180013a2b  mov     rax, [rax+0A0h]
0x180013a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a37  nop
0x180013a38  mov     rcx, [rsp+78h+pbstr]; bstrString
0x180013a40  call    cs:__imp_SysFreeString
0x180013a46  inc     r14d
0x180013a49  cmp     r14d, cs:dword_180027110
0x180013a50  jl      loc_180013961
0x180013a56  mov     cs:qword_180027108, rdi
0x180013a5d  mov     rax, [rsi]
0x180013a60  mov     rdx, [rsp+78h+arg_10]
0x180013a68  mov     rcx, rsi
0x180013a6b  mov     rax, [rax+98h]
0x180013a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a77  xor     eax, eax
0x180013a79  add     rsp, 48h
0x180013a7d  pop     r15
0x180013a7f  pop     r14
0x180013a81  pop     r12
0x180013a83  pop     rdi
0x180013a84  pop     rsi
0x180013a85  pop     rbx
0x180013a86  retn
```
