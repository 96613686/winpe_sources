# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x18000ce8c`
- end: `0x18000d0f1`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b1d4`

## callees

- `0x180001cf8`
- `0x18000ce8c`
- `0x18000e470`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000d053`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d0a5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d053`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d0a5`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d066`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d066`

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
0x18000ce8c  mov     r11, rsp
0x18000ce8f  mov     [r11+8], rsi
0x18000ce93  mov     [r11+10h], rdx
0x18000ce97  push    rdi
0x18000ce98  push    r12
0x18000ce9a  push    r13
0x18000ce9c  push    r14
0x18000ce9e  push    r15
0x18000cea0  sub     rsp, 60h
0x18000cea4  mov     rsi, rdx
0x18000cea7  mov     r15, rcx
0x18000ceaa  mov     qword ptr [r11+20h], 0
0x18000ceb2  mov     rax, [rdx]
0x18000ceb5  lea     rdx, [r11+20h]
0x18000ceb9  mov     rcx, rsi
0x18000cebc  mov     rax, [rax+18h]
0x18000cec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cec5  test    eax, eax
0x18000cec7  js      loc_18000D0D9
0x18000cecd  xor     edi, edi
0x18000cecf  mov     [rsp+88h+pbstr], rdi
0x18000ced7  mov     rax, [rsp+88h+arg_18]
0x18000cedf  movzx   ecx, word ptr [rax+30h]
0x18000cee3  lea     r14, [r15+30h]
0x18000cee7  mov     [rsp+88h+var_48], r14
0x18000ceec  mov     [r14], ecx
0x18000ceef  lea     rax, [r15+28h]
0x18000cef3  mov     [rsp+88h+var_40], rax
0x18000cef8  mov     [rax], rdi
0x18000cefb  test    ecx, ecx
0x18000cefd  jz      loc_18000CFA6
0x18000cf03  mov     r15d, ecx
0x18000cf06  lea     r12d, [rdi+10h]
0x18000cf0a  mov     eax, r12d
0x18000cf0d  mul     rcx
0x18000cf10  lea     rcx, [rdi-1]
0x18000cf14  cmovb   rax, rcx
0x18000cf18  add     rax, 8
0x18000cf1c  cmovb   rax, rcx
0x18000cf20  mov     rcx, rax; Size
0x18000cf23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cf28  mov     [rsp+88h+var_38], rax
0x18000cf2d  test    rax, rax
0x18000cf30  jz      short loc_18000CF5C
0x18000cf32  mov     [rax], r15
0x18000cf35  lea     rdi, [rax+8]
0x18000cf39  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18000cf40  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x18000cf45  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x18000cf4c  mov     r8d, r15d; unsigned __int64
0x18000cf4f  mov     edx, r12d; unsigned __int64
0x18000cf52  mov     rcx, rdi; void *
0x18000cf55  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000cf5a  jmp     short loc_18000CF5E
0x18000cf5c  xor     edi, edi
0x18000cf5e  mov     [rsp+88h+pbstr], rdi
0x18000cf66  jmp     short loc_18000CF7D
0x18000cf68  mov     rsi, [rsp+88h+arg_8]
0x18000cf70  mov     rdi, [rsp+88h+pbstr]
0x18000cf78  mov     r14, [rsp+88h+var_48]
0x18000cf7d  test    rdi, rdi
0x18000cf80  jnz     short loc_18000CFA6
0x18000cf82  mov     rax, [rsi]
0x18000cf85  mov     rdx, [rsp+88h+arg_18]
0x18000cf8d  mov     rcx, rsi
0x18000cf90  mov     rax, [rax+98h]
0x18000cf97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf9c  mov     eax, 8007000Eh
0x18000cfa1  jmp     loc_18000D0DB
0x18000cfa6  xor     r15d, r15d
0x18000cfa9  cmp     [r14], r15d
0x18000cfac  jle     loc_18000D0B7
0x18000cfb2  mov     [rsp+88h+arg_8], 0
0x18000cfbe  movsxd  r12, r15d
0x18000cfc1  add     r12, r12
0x18000cfc4  mov     qword ptr [rdi+r12*8+8], 0
0x18000cfcd  mov     rax, [rsi]
0x18000cfd0  lea     r8, [rsp+88h+arg_8]
0x18000cfd8  mov     edx, r15d
0x18000cfdb  mov     rcx, rsi
0x18000cfde  mov     rax, [rax+28h]
0x18000cfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfe7  test    eax, eax
0x18000cfe9  js      loc_18000D0AB
0x18000cfef  mov     [rsp+88h+pbstr], 0
0x18000cffb  mov     rax, [rsi]
0x18000cffe  mov     [rsp+88h+var_60], 0
0x18000d007  mov     [rsp+88h+var_68], 0
0x18000d010  xor     r9d, r9d
0x18000d013  lea     r8, [rsp+88h+pbstr]
0x18000d01b  mov     rdx, [rsp+88h+arg_8]
0x18000d023  mov     edx, [rdx]
0x18000d025  mov     rcx, rsi
0x18000d028  mov     rax, [rax+60h]
0x18000d02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d031  test    eax, eax
0x18000d033  js      short loc_18000D082
0x18000d035  mov     r13, [rsp+88h+pbstr]
0x18000d03d  mov     [rsp+88h+pbstr], 0
0x18000d049  cmp     [rdi+r12*8], r13
0x18000d04d  jz      short loc_18000D05F
0x18000d04f  mov     rcx, [rdi+r12*8]; bstrString
0x18000d053  call    cs:__imp_SysFreeString
0x18000d059  mov     [rdi+r12*8], r13
0x18000d05d  jmp     short loc_18000D063
0x18000d05f  mov     r13, [rdi+r12*8]
0x18000d063  mov     rcx, r13; pbstr
0x18000d066  call    cs:__imp_SysStringLen
0x18000d06c  mov     [rdi+r12*8+8], eax
0x18000d071  mov     rdx, [rsp+88h+arg_8]
0x18000d079  mov     eax, [rdx]
0x18000d07b  mov     [rdi+r12*8+0Ch], eax
0x18000d080  jmp     short loc_18000D08A
0x18000d082  mov     rdx, [rsp+88h+arg_8]
0x18000d08a  mov     rax, [rsi]
0x18000d08d  mov     rcx, rsi
0x18000d090  mov     rax, [rax+0A0h]
0x18000d097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d09c  nop
0x18000d09d  mov     rcx, [rsp+88h+pbstr]; bstrString
0x18000d0a5  call    cs:__imp_SysFreeString
0x18000d0ab  inc     r15d
0x18000d0ae  cmp     r15d, [r14]
0x18000d0b1  jl      loc_18000CFB2
0x18000d0b7  mov     rax, [rsp+88h+var_40]
0x18000d0bc  mov     [rax], rdi
0x18000d0bf  mov     rax, [rsi]
0x18000d0c2  mov     rdx, [rsp+88h+arg_18]
0x18000d0ca  mov     rcx, rsi
0x18000d0cd  mov     rax, [rax+98h]
0x18000d0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0d9  xor     eax, eax
0x18000d0db  mov     rsi, [rsp+88h+arg_0]
0x18000d0e3  add     rsp, 60h
0x18000d0e7  pop     r15
0x18000d0e9  pop     r14
0x18000d0eb  pop     r13
0x18000d0ed  pop     r12
0x18000d0ef  pop     rdi
0x18000d0f0  retn
```
