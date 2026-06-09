# CScriptFile::Create(ushort const *,IDebugApplication64 *,CScriptFile * *)

- ea: `0x140009514`
- end: `0x14000964e`
- name: `?Create@CScriptFile@@SAJPEBGPEAUIDebugApplication64@@PEAPEAV1@@Z`
- size: `314`
- prototype: `__int64 __fastcall(OLECHAR *psz, struct IDebugApplication64 *, struct CScriptFile **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140001090`

## callees

- `0x140009514`
- `0x140009c70`
- `0x14000e648`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140009575`
- `OLEAUT32!__imp_SysAllocString` at `0x140009575`

## pseudocode

```c
__int64 __fastcall CScriptFile::Create(OLECHAR *psz, struct IDebugApplication64 *a2, struct CScriptFile **a3)
{
  CScriptFile *v6; // rax
  struct IUnknown *v7; // rdx
  CScriptFile *v8; // rbx
  BSTR v9; // rax
  int v10; // edi
  _QWORD *v11; // r15
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF

  if ( psz && a3 )
  {
    v13 = 0;
    v6 = (CScriptFile *)operator new(0x88u);
    if ( !v6 || (v8 = CScriptFile::CScriptFile(v6, v7)) == 0 )
      return (unsigned int)-2147024882;
    v9 = SysAllocString(psz);
    *((_QWORD *)v8 + 12) = v9;
    if ( v9 )
    {
      if ( !a2
        || (v11 = (_QWORD *)((char *)v8 + 120),
            v10 = ((__int64 (__fastcall *)(struct IDebugApplication64 *, char *))a2->lpVtbl->CreateApplicationNode)(
                    a2,
                    (char *)v8 + 120),
            v10 >= 0)
        && (v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v11 + 64LL))(*v11, (__int64)v8 + 8), v10 >= 0)
        && (v10 = ((__int64 (__fastcall *)(struct IDebugApplication64 *, __int64 *))a2->lpVtbl->GetRootNode)(a2, &v13),
            v10 >= 0)
        && (v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v11 + 80LL))(*v11, v13),
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13),
            v10 >= 0) )
      {
        *a3 = v8;
        return 0;
      }
    }
    else
    {
      v10 = -2147024882;
    }
    (*(void (__fastcall **)(CScriptFile *))(*(_QWORD *)v8 + 16LL))(v8);
    return (unsigned int)v10;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x140009514  mov     [rsp+arg_8], rbx
0x140009519  mov     [rsp+arg_10], rsi
0x14000951e  push    rdi
0x14000951f  push    r14
0x140009521  push    r15
0x140009523  sub     rsp, 20h
0x140009527  mov     r14, r8
0x14000952a  mov     rsi, rdx
0x14000952d  mov     rdi, rcx
0x140009530  test    rcx, rcx
0x140009533  jz      loc_140009635
0x140009539  test    r8, r8
0x14000953c  jz      loc_140009635
0x140009542  mov     ecx, 88h; Size
0x140009547  mov     [rsp+38h+arg_0], 0
0x140009550  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009555  test    rax, rax
0x140009558  jz      loc_14000962C
0x14000955e  mov     rcx, rax; this
0x140009561  call    ??0CScriptFile@@AEAA@PEAUIUnknown@@@Z; CScriptFile::CScriptFile(IUnknown *)
0x140009566  mov     rbx, rax
0x140009569  test    rax, rax
0x14000956c  jz      loc_14000962C
0x140009572  mov     rcx, rdi; psz
0x140009575  call    cs:__imp_SysAllocString
0x14000957b  mov     [rbx+60h], rax
0x14000957f  test    rax, rax
0x140009582  jnz     short loc_14000958E
0x140009584  mov     edi, 8007000Eh
0x140009589  jmp     loc_140009614
0x14000958e  test    rsi, rsi
0x140009591  jz      loc_140009625
0x140009597  mov     rax, [rsi]
0x14000959a  lea     r15, [rbx+78h]
0x14000959e  mov     rdx, r15
0x1400095a1  mov     rcx, rsi
0x1400095a4  mov     rax, [rax+0D8h]
0x1400095ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095b0  mov     edi, eax
0x1400095b2  test    eax, eax
0x1400095b4  js      short loc_140009614
0x1400095b6  mov     rcx, [r15]
0x1400095b9  lea     rdx, [rbx+8]
0x1400095bd  mov     rax, [rcx]
0x1400095c0  mov     rax, [rax+40h]
0x1400095c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095c9  mov     edi, eax
0x1400095cb  test    eax, eax
0x1400095cd  js      short loc_140009614
0x1400095cf  mov     rax, [rsi]
0x1400095d2  lea     rdx, [rsp+38h+arg_0]
0x1400095d7  mov     rcx, rsi
0x1400095da  mov     rax, [rax+60h]
0x1400095de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095e3  mov     edi, eax
0x1400095e5  test    eax, eax
0x1400095e7  js      short loc_140009614
0x1400095e9  mov     rcx, [r15]
0x1400095ec  mov     rdx, [rsp+38h+arg_0]
0x1400095f1  mov     rax, [rcx]
0x1400095f4  mov     rax, [rax+50h]
0x1400095f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095fd  mov     rcx, [rsp+38h+arg_0]
0x140009602  mov     edi, eax
0x140009604  mov     rax, [rcx]
0x140009607  mov     rax, [rax+10h]
0x14000960b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009610  test    edi, edi
0x140009612  jns     short loc_140009625
0x140009614  mov     rax, [rbx]
0x140009617  mov     rcx, rbx
0x14000961a  mov     rax, [rax+10h]
0x14000961e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009623  jmp     short loc_140009631
0x140009625  mov     [r14], rbx
0x140009628  xor     edi, edi
0x14000962a  jmp     short loc_140009631
0x14000962c  mov     edi, 8007000Eh
0x140009631  mov     eax, edi
0x140009633  jmp     short loc_14000963A
0x140009635  mov     eax, 80004003h
0x14000963a  mov     rbx, [rsp+38h+arg_8]
0x14000963f  mov     rsi, [rsp+38h+arg_10]
0x140009644  add     rsp, 20h
0x140009648  pop     r15
0x14000964a  pop     r14
0x14000964c  pop     rdi
0x14000964d  retn
```
