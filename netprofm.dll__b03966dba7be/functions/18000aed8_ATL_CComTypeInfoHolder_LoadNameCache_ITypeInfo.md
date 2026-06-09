# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x18000aed8`
- end: `0x18000b12a`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001941c`

## callees

- `0x18000aed8`
- `0x1800120d0`
- `0x180012870`
- `0x1800128ac`
- `0x180043010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000b088`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b0d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b088`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b0d1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b09b`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b09b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rsi
  BSTR v4; // rdi
  unsigned __int64 v5; // rcx
  _DWORD *v6; // r14
  __int64 v7; // r15
  __int64 v8; // rax
  bool v9; // cf
  unsigned __int64 v10; // rax
  unsigned int i; // r15d
  OLECHAR *v13; // r13
  char *v14; // [rsp+40h] [rbp-68h]
  BSTR *v15; // [rsp+48h] [rbp-60h]
  _QWORD *v16; // [rsp+58h] [rbp-50h]
  struct ITypeInfo *v17; // [rsp+60h] [rbp-48h] BYREF
  __int64 v18; // [rsp+68h] [rbp-40h] BYREF
  BSTR pbstr; // [rsp+70h] [rbp-38h] BYREF

  v2 = a2;
  v17 = a2;
  v18 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v18) >= 0 )
  {
    v4 = 0;
    pbstr = 0;
    v5 = *(unsigned __int16 *)(v18 + 48);
    v6 = (_DWORD *)((char *)this + 48);
    v14 = (char *)this + 48;
    *((_DWORD *)this + 12) = v5;
    v15 = (BSTR *)((char *)this + 40);
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
        v16 = operator new[](v10);
        *v16 = v7;
        v4 = (BSTR)(v16 + 1);
        `eh vector constructor iterator'(
          v16 + 1,
          0x10u,
          (unsigned int)v7,
          (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
          (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        pbstr = (BSTR)(v16 + 1);
      }
      catch ( ... )
      {
        v4 = pbstr;
        v2 = v17;
        v6 = v14;
      }
      if ( !v4 )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v18);
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
          v13 = pbstr;
          pbstr = 0;
          if ( *(OLECHAR **)&v4[8 * i] == v13 )
          {
            v13 = *(OLECHAR **)&v4[8 * i];
          }
          else
          {
            SysFreeString(*(BSTR *)&v4[8 * i]);
            *(_QWORD *)&v4[8 * i] = v13;
          }
          *(_DWORD *)&v4[8 * i + 4] = SysStringLen(v13);
          *(_DWORD *)&v4[8 * i + 6] = v17->lpVtbl;
        }
        ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
        SysFreeString(pbstr);
      }
    }
    *v15 = v4;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18000aed8  mov     [rsp+arg_10], rsi
0x18000aedd  push    rdi
0x18000aede  push    r12
0x18000aee0  push    r13
0x18000aee2  push    r14
0x18000aee4  push    r15
0x18000aee6  sub     rsp, 80h
0x18000aeed  mov     rax, cs:__security_cookie
0x18000aef4  xor     rax, rsp
0x18000aef7  mov     [rsp+0A8h+var_30], rax
0x18000aefc  mov     rsi, rdx
0x18000aeff  mov     r15, rcx
0x18000af02  mov     [rsp+0A8h+var_48], rdx
0x18000af07  mov     [rsp+0A8h+var_40], 0
0x18000af10  mov     rax, [rdx]
0x18000af13  lea     rdx, [rsp+0A8h+var_40]
0x18000af18  mov     rcx, rsi
0x18000af1b  mov     rax, [rax+18h]
0x18000af1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af24  test    eax, eax
0x18000af26  js      loc_18000B102
0x18000af2c  xor     edi, edi
0x18000af2e  mov     [rsp+0A8h+pbstr], rdi
0x18000af33  mov     rax, [rsp+0A8h+var_40]
0x18000af38  movzx   ecx, word ptr [rax+30h]
0x18000af3c  lea     r14, [r15+30h]
0x18000af40  mov     [rsp+0A8h+var_68], r14
0x18000af45  mov     [r14], ecx
0x18000af48  lea     rax, [r15+28h]
0x18000af4c  mov     [rsp+0A8h+var_60], rax
0x18000af51  mov     [rax], rdi
0x18000af54  test    ecx, ecx
0x18000af56  jz      loc_18000AFF0
0x18000af5c  mov     r15d, ecx
0x18000af5f  mov     [rsp+0A8h+var_58], rcx
0x18000af64  lea     r12d, [rdi+10h]
0x18000af68  mov     eax, r12d
0x18000af6b  mul     rcx
0x18000af6e  lea     rcx, [rdi-1]
0x18000af72  cmovb   rax, rcx
0x18000af76  add     rax, 8
0x18000af7a  cmovb   rax, rcx
0x18000af7e  mov     rcx, rax; unsigned __int64
0x18000af81  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000af86  mov     [rsp+0A8h+var_50], rax
0x18000af8b  mov     [rax], r15
0x18000af8e  lea     rdi, [rax+8]
0x18000af92  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18000af99  mov     [rsp+0A8h+var_88], rax; void (*)(void *)
0x18000af9e  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x18000afa5  mov     r8d, r15d; unsigned __int64
0x18000afa8  mov     edx, r12d; unsigned __int64
0x18000afab  mov     rcx, rdi; void *
0x18000afae  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000afb3  nop
0x18000afb4  mov     [rsp+0A8h+pbstr], rdi
0x18000afb9  jmp     short loc_18000AFCA
0x18000afbb  mov     rdi, [rsp+0A8h+pbstr]
0x18000afc0  mov     rsi, [rsp+0A8h+var_48]
0x18000afc5  mov     r14, [rsp+0A8h+var_68]
0x18000afca  test    rdi, rdi
0x18000afcd  jnz     short loc_18000AFF0
0x18000afcf  mov     rax, [rsi]
0x18000afd2  mov     rdx, [rsp+0A8h+var_40]
0x18000afd7  mov     rcx, rsi
0x18000afda  mov     rax, [rax+98h]
0x18000afe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afe6  mov     eax, 8007000Eh
0x18000afeb  jmp     loc_18000B104
0x18000aff0  xor     r15d, r15d
0x18000aff3  cmp     [r14], r15d
0x18000aff6  jle     loc_18000B0E3
0x18000affc  mov     [rsp+0A8h+var_48], 0
0x18000b005  movsxd  r12, r15d
0x18000b008  add     r12, r12
0x18000b00b  mov     qword ptr [rdi+r12*8+8], 0
0x18000b014  mov     rax, [rsi]
0x18000b017  lea     r8, [rsp+0A8h+var_48]
0x18000b01c  mov     edx, r15d
0x18000b01f  mov     rcx, rsi
0x18000b022  mov     rax, [rax+28h]
0x18000b026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b02b  test    eax, eax
0x18000b02d  js      loc_18000B0D7
0x18000b033  mov     [rsp+0A8h+pbstr], 0
0x18000b03c  mov     rax, [rsi]
0x18000b03f  mov     [rsp+0A8h+var_80], 0
0x18000b048  mov     [rsp+0A8h+var_88], 0
0x18000b051  xor     r9d, r9d
0x18000b054  lea     r8, [rsp+0A8h+pbstr]
0x18000b059  mov     rdx, [rsp+0A8h+var_48]
0x18000b05e  mov     edx, [rdx]
0x18000b060  mov     rcx, rsi
0x18000b063  mov     rax, [rax+60h]
0x18000b067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b06c  test    eax, eax
0x18000b06e  js      short loc_18000B0B4
0x18000b070  mov     r13, [rsp+0A8h+pbstr]
0x18000b075  mov     [rsp+0A8h+pbstr], 0
0x18000b07e  cmp     [rdi+r12*8], r13
0x18000b082  jz      short loc_18000B094
0x18000b084  mov     rcx, [rdi+r12*8]; bstrString
0x18000b088  call    cs:__imp_SysFreeString
0x18000b08e  mov     [rdi+r12*8], r13
0x18000b092  jmp     short loc_18000B098
0x18000b094  mov     r13, [rdi+r12*8]
0x18000b098  mov     rcx, r13; pbstr
0x18000b09b  call    cs:__imp_SysStringLen
0x18000b0a1  mov     [rdi+r12*8+8], eax
0x18000b0a6  mov     rdx, [rsp+0A8h+var_48]
0x18000b0ab  mov     eax, [rdx]
0x18000b0ad  mov     [rdi+r12*8+0Ch], eax
0x18000b0b2  jmp     short loc_18000B0B9
0x18000b0b4  mov     rdx, [rsp+0A8h+var_48]
0x18000b0b9  mov     rax, [rsi]
0x18000b0bc  mov     rcx, rsi
0x18000b0bf  mov     rax, [rax+0A0h]
0x18000b0c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0cb  nop
0x18000b0cc  mov     rcx, [rsp+0A8h+pbstr]; bstrString
0x18000b0d1  call    cs:__imp_SysFreeString
0x18000b0d7  inc     r15d
0x18000b0da  cmp     r15d, [r14]
0x18000b0dd  jl      loc_18000AFFC
0x18000b0e3  mov     rax, [rsp+0A8h+var_60]
0x18000b0e8  mov     [rax], rdi
0x18000b0eb  mov     rax, [rsi]
0x18000b0ee  mov     rdx, [rsp+0A8h+var_40]
0x18000b0f3  mov     rcx, rsi
0x18000b0f6  mov     rax, [rax+98h]
0x18000b0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b102  xor     eax, eax
0x18000b104  mov     rcx, [rsp+0A8h+var_30]
0x18000b109  xor     rcx, rsp; StackCookie
0x18000b10c  call    __security_check_cookie
0x18000b111  mov     rsi, [rsp+0A8h+arg_10]
0x18000b119  add     rsp, 80h
0x18000b120  pop     r15
0x18000b122  pop     r14
0x18000b124  pop     r13
0x18000b126  pop     r12
0x18000b128  pop     rdi
0x18000b129  retn
```
