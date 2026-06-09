# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x14000370c`
- end: `0x1400038d6`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400031f4`

## callees

- `0x1400011f8`
- `0x140002154`
- `0x14000370c`
- `0x140007010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140003832`
- `OLEAUT32!__imp_SysFreeString` at `0x140003894`
- `OLEAUT32!__imp_SysFreeString` at `0x140003832`
- `OLEAUT32!__imp_SysFreeString` at `0x140003894`
- `OLEAUT32!__imp_SysStringLen` at `0x140003862`
- `OLEAUT32!__imp_SysStringLen` at `0x140003862`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfoVtbl *lpVtbl; // rax
  __int64 v4; // rdi
  unsigned __int64 v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // rax
  bool v8; // cf
  unsigned __int64 v9; // rax
  _QWORD *v10; // rax
  ATL::CComTypeInfoHolder::stringdispid *v11; // r14
  int v12; // esi
  struct ITypeInfoVtbl *v13; // rax
  OLECHAR *v14; // r15
  UINT v16; // eax
  ATL::CComTypeInfoHolder *v17; // rdx
  ATL::CComTypeInfoHolder *v18; // [rsp+80h] [rbp+40h] BYREF
  BSTR pbstr; // [rsp+88h] [rbp+48h] BYREF
  __int64 v20; // [rsp+90h] [rbp+50h] BYREF

  v18 = this;
  lpVtbl = a2->lpVtbl;
  v20 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))lpVtbl->GetTypeAttr)(a2, &v20) >= 0 )
  {
    v4 = 0;
    v5 = *(unsigned __int16 *)(v20 + 48);
    dword_14000B080 = v5;
    qword_14000B078 = 0;
    if ( (_WORD)v5 )
    {
      v6 = (unsigned int)v5;
      v7 = 16 * v5;
      if ( !is_mul_ok(v5, 0x10u) )
        v7 = -1;
      v8 = __CFADD__(v7, 8);
      v9 = v7 + 8;
      if ( v8 )
        v9 = -1;
      v10 = operator new[](v9);
      if ( !v10 )
        goto LABEL_17;
      v4 = (__int64)(v10 + 1);
      *v10 = v6;
      v11 = (ATL::CComTypeInfoHolder::stringdispid *)(v10 + 1);
      do
      {
        ATL::CComTypeInfoHolder::stringdispid::stringdispid(v11);
        v11 = (ATL::CComTypeInfoHolder::stringdispid *)((char *)v11 + 16);
        --v6;
      }
      while ( v6 );
      if ( !v4 )
      {
LABEL_17:
        ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v20);
        return 2147942414LL;
      }
      LODWORD(v5) = dword_14000B080;
    }
    v12 = 0;
    if ( (int)v5 > 0 )
    {
      do
      {
        v18 = 0;
        *(_QWORD *)(v4 + 16LL * v12 + 8) = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, ATL::CComTypeInfoHolder **))a2->lpVtbl->GetFuncDesc)(
               a2,
               (unsigned int)v12,
               &v18) >= 0 )
        {
          v13 = a2->lpVtbl;
          pbstr = 0;
          if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v13->GetDocumentation)(
                 a2,
                 *(unsigned int *)v18,
                 &pbstr,
                 0,
                 0,
                 0) < 0 )
          {
            v17 = v18;
          }
          else
          {
            v14 = pbstr;
            pbstr = 0;
            if ( *(OLECHAR **)(v4 + 16LL * v12) == v14 )
            {
              v14 = *(OLECHAR **)(v4 + 16LL * v12);
            }
            else
            {
              SysFreeString(*(BSTR *)(v4 + 16LL * v12));
              *(_QWORD *)(v4 + 16LL * v12) = v14;
            }
            v16 = SysStringLen(v14);
            v17 = v18;
            *(_DWORD *)(v4 + 16LL * v12 + 8) = v16;
            *(_DWORD *)(v4 + 16LL * v12 + 12) = *(_DWORD *)v17;
          }
          ((void (__fastcall *)(struct ITypeInfo *, ATL::CComTypeInfoHolder *))a2->lpVtbl->ReleaseFuncDesc)(a2, v17);
          SysFreeString(pbstr);
        }
        ++v12;
      }
      while ( v12 < dword_14000B080 );
    }
    qword_14000B078 = v4;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v20);
  }
  return 0;
}

```

## disassembly

```asm
0x14000370c  mov     [rsp-38h+arg_0], rcx
0x140003711  push    rbp
0x140003712  push    rbx
0x140003713  push    rsi
0x140003714  push    rdi
0x140003715  push    r12
0x140003717  push    r14
0x140003719  push    r15
0x14000371b  mov     rbp, rsp
0x14000371e  sub     rsp, 40h
0x140003722  mov     rax, [rdx]
0x140003725  mov     rbx, rdx
0x140003728  xor     r12d, r12d
0x14000372b  lea     rdx, [rbp+arg_10]
0x14000372f  mov     rcx, rbx
0x140003732  mov     [rbp+arg_10], r12
0x140003736  mov     rax, [rax+18h]
0x14000373a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000373f  test    eax, eax
0x140003741  js      loc_1400038C5
0x140003747  mov     rax, [rbp+arg_10]
0x14000374b  mov     edi, r12d
0x14000374e  movzx   ecx, word ptr [rax+30h]
0x140003752  mov     cs:dword_14000B080, ecx
0x140003758  mov     cs:qword_14000B078, r12
0x14000375f  test    cx, cx
0x140003762  jz      short loc_1400037BB
0x140003764  mov     esi, ecx
0x140003766  lea     eax, [r12+10h]
0x14000376b  mul     rcx
0x14000376e  lea     rcx, [r12-1]
0x140003773  cmovb   rax, rcx
0x140003777  add     rax, 8
0x14000377b  cmovb   rax, rcx
0x14000377f  mov     rcx, rax; unsigned __int64
0x140003782  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140003787  test    rax, rax
0x14000378a  jz      loc_14000383E
0x140003790  lea     rdi, [rax+8]
0x140003794  mov     [rax], rsi
0x140003797  mov     r14, rdi
0x14000379a  mov     rcx, r14; this
0x14000379d  call    ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::stringdispid(void)
0x1400037a2  add     r14, 10h
0x1400037a6  sub     rsi, 1
0x1400037aa  jnz     short loc_14000379A
0x1400037ac  test    rdi, rdi
0x1400037af  jz      loc_14000383E
0x1400037b5  mov     ecx, cs:dword_14000B080
0x1400037bb  mov     esi, r12d
0x1400037be  test    ecx, ecx
0x1400037c0  jle     loc_1400038A8
0x1400037c6  movsxd  r14, esi
0x1400037c9  lea     r8, [rbp+arg_0]
0x1400037cd  add     r14, r14
0x1400037d0  mov     [rbp+arg_0], r12
0x1400037d4  mov     edx, esi
0x1400037d6  mov     rcx, rbx
0x1400037d9  mov     [rdi+r14*8+8], r12
0x1400037de  mov     rax, [rbx]
0x1400037e1  mov     rax, [rax+28h]
0x1400037e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037ea  test    eax, eax
0x1400037ec  js      loc_14000389A
0x1400037f2  mov     rax, [rbx]
0x1400037f5  lea     r8, [rbp+pbstr]
0x1400037f9  mov     rdx, [rbp+arg_0]
0x1400037fd  xor     r9d, r9d
0x140003800  mov     [rbp+pbstr], r12
0x140003804  mov     rcx, rbx
0x140003807  mov     [rsp+40h+var_18], r12
0x14000380c  mov     rax, [rax+60h]
0x140003810  mov     edx, [rdx]
0x140003812  mov     [rsp+40h+var_20], r12
0x140003817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000381c  test    eax, eax
0x14000381e  js      short loc_14000387A
0x140003820  mov     r15, [rbp+pbstr]
0x140003824  mov     [rbp+pbstr], r12
0x140003828  cmp     [rdi+r14*8], r15
0x14000382c  jz      short loc_14000385B
0x14000382e  mov     rcx, [rdi+r14*8]; bstrString
0x140003832  call    cs:__imp_SysFreeString
0x140003838  mov     [rdi+r14*8], r15
0x14000383c  jmp     short loc_14000385F
0x14000383e  mov     rax, [rbx]
0x140003841  mov     rcx, rbx
0x140003844  mov     rdx, [rbp+arg_10]
0x140003848  mov     rax, [rax+98h]
0x14000384f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003854  mov     eax, 8007000Eh
0x140003859  jmp     short loc_1400038C7
0x14000385b  mov     r15, [rdi+r14*8]
0x14000385f  mov     rcx, r15; pbstr
0x140003862  call    cs:__imp_SysStringLen
0x140003868  mov     rdx, [rbp+arg_0]
0x14000386c  mov     [rdi+r14*8+8], eax
0x140003871  mov     eax, [rdx]
0x140003873  mov     [rdi+r14*8+0Ch], eax
0x140003878  jmp     short loc_14000387E
0x14000387a  mov     rdx, [rbp+arg_0]
0x14000387e  mov     rax, [rbx]
0x140003881  mov     rcx, rbx
0x140003884  mov     rax, [rax+0A0h]
0x14000388b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003890  mov     rcx, [rbp+pbstr]; bstrString
0x140003894  call    cs:__imp_SysFreeString
0x14000389a  inc     esi
0x14000389c  cmp     esi, cs:dword_14000B080
0x1400038a2  jl      loc_1400037C6
0x1400038a8  mov     rdx, [rbp+arg_10]
0x1400038ac  mov     rcx, rbx
0x1400038af  mov     cs:qword_14000B078, rdi
0x1400038b6  mov     rax, [rbx]
0x1400038b9  mov     rax, [rax+98h]
0x1400038c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038c5  xor     eax, eax
0x1400038c7  add     rsp, 40h
0x1400038cb  pop     r15
0x1400038cd  pop     r14
0x1400038cf  pop     r12
0x1400038d1  pop     rdi
0x1400038d2  pop     rsi
0x1400038d3  pop     rbx
0x1400038d4  pop     rbp
0x1400038d5  retn
```
