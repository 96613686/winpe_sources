# ProvXmlEnumerator::CreateInstance(IProvisioningPackage *)

- ea: `0x180033724`
- end: `0x180033871`
- name: `?CreateInstance@ProvXmlEnumerator@@SA?AV?$unique_ptr@VProvXmlEnumerator@@U?$default_delete@VProvXmlEnumerator@@@std@@@std@@PEAUIProvisioningPackage@@@Z`
- size: `333`
- prototype: `__int64 *__fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002e740`

## callees

- `0x180002f44`
- `0x18001b388`
- `0x180033724`
- `0x180037010`

## string_xrefs

- `0x18003385f`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`

## pseudocode

```c
__int64 *__fastcall ProvXmlEnumerator::CreateInstance(__int64 *a1, __int64 a2)
{
  _QWORD *v4; // rax
  int v5; // eax
  _QWORD *v6; // rdi
  int (__fastcall ***v7)(_QWORD, _QWORD *); // rsi
  int (__fastcall ***v8)(_QWORD, __int64 *); // rcx
  __int64 v9; // rdi
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // rsi
  __int64 v14; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  int (__fastcall ***v17)(_QWORD, __int64 *); // [rsp+68h] [rbp+30h] BYREF
  __int64 v18; // [rsp+70h] [rbp+38h] BYREF
  __int64 v19; // [rsp+78h] [rbp+40h] BYREF

  v4 = operator new(0x20u);
  if ( v4 )
  {
    *v4 = 0;
    v4[1] = 0;
    v4[2] = 0;
    v4[3] = 0;
  }
  *a1 = (__int64)v4;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a2 + 112LL))(a2, &v17);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      (const char *)(unsigned int)v5,
      1);
  if ( (**v17)(v17, &v18) >= 0 )
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 64LL))(v18, &v19);
  *(_QWORD *)*a1 = a2;
  v6 = (_QWORD *)*a1;
  v7 = v17;
  v8 = *(int (__fastcall ****)(_QWORD, __int64 *))(*a1 + 8);
  if ( v17 != v8 )
  {
    if ( v8 )
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, __int64 *)))(*v8)[1])(v8);
    v6[1] = v7;
  }
  v9 = *a1;
  v10 = v18;
  v11 = *(_QWORD *)(*a1 + 16);
  if ( v18 != v11 )
  {
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 80LL))(v11);
    *(_QWORD *)(v9 + 16) = v10;
  }
  v12 = *a1;
  v13 = v19;
  v14 = *(_QWORD *)(*a1 + 24);
  if ( v19 != v14 )
  {
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *(_QWORD *)(v12 + 24) = v13;
  }
  return a1;
}

```

## disassembly

```asm
0x180033724  mov     [rsp-20h+arg_0], rcx
0x180033729  push    rbp
0x18003372a  push    rbx
0x18003372b  push    rsi
0x18003372c  push    rdi
0x18003372d  mov     rbp, rsp
0x180033730  sub     rsp, 38h
0x180033734  mov     rdi, rdx
0x180033737  mov     rbx, rcx
0x18003373a  mov     [rbp+var_18], 0
0x180033741  mov     ecx, 20h ; ' '; Size
0x180033746  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003374b  test    rax, rax
0x18003374e  jz      short loc_18003376F
0x180033750  mov     qword ptr [rax], 0
0x180033757  mov     qword ptr [rax+8], 0
0x18003375f  mov     qword ptr [rax+10h], 0
0x180033767  mov     qword ptr [rax+18h], 0
0x18003376f  mov     [rbx], rax
0x180033772  mov     [rbp+var_18], 1
0x180033779  mov     [rbp+arg_8], 0
0x180033781  mov     [rbp+arg_10], 0
0x180033789  mov     [rbp+arg_18], 0
0x180033791  mov     rax, [rdi]
0x180033794  lea     rdx, [rbp+arg_8]
0x180033798  mov     rcx, rdi
0x18003379b  mov     rax, [rax+70h]
0x18003379f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337a4  mov     rcx, [rbp+20h]; this
0x1800337a8  test    eax, eax
0x1800337aa  js      loc_18003385C
0x1800337b0  mov     rcx, [rbp+arg_8]
0x1800337b4  mov     rax, [rcx]
0x1800337b7  lea     rdx, [rbp+arg_10]
0x1800337bb  mov     rax, [rax]
0x1800337be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337c3  test    eax, eax
0x1800337c5  js      short loc_1800337DB
0x1800337c7  mov     rcx, [rbp+arg_10]
0x1800337cb  mov     rax, [rcx]
0x1800337ce  lea     rdx, [rbp+arg_18]
0x1800337d2  mov     rax, [rax+40h]
0x1800337d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337db  mov     rax, [rbx]
0x1800337de  mov     [rax], rdi
0x1800337e1  mov     rdi, [rbx]
0x1800337e4  mov     rsi, [rbp+arg_8]
0x1800337e8  mov     rcx, [rdi+8]
0x1800337ec  cmp     rsi, rcx
0x1800337ef  jz      short loc_180033806
0x1800337f1  test    rcx, rcx
0x1800337f4  jz      short loc_180033802
0x1800337f6  mov     rax, [rcx]
0x1800337f9  mov     rax, [rax+8]
0x1800337fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033802  mov     [rdi+8], rsi
0x180033806  mov     rdi, [rbx]
0x180033809  mov     rsi, [rbp+arg_10]
0x18003380d  mov     rcx, [rdi+10h]
0x180033811  cmp     rsi, rcx
0x180033814  jz      short loc_18003382B
0x180033816  test    rcx, rcx
0x180033819  jz      short loc_180033827
0x18003381b  mov     rax, [rcx]
0x18003381e  mov     rax, [rax+50h]
0x180033822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033827  mov     [rdi+10h], rsi
0x18003382b  mov     rdi, [rbx]
0x18003382e  mov     rsi, [rbp+arg_18]
0x180033832  mov     rcx, [rdi+18h]
0x180033836  cmp     rsi, rcx
0x180033839  jz      short loc_180033850
0x18003383b  test    rcx, rcx
0x18003383e  jz      short loc_18003384C
0x180033840  mov     rax, [rcx]
0x180033843  mov     rax, [rax+10h]
0x180033847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003384c  mov     [rdi+18h], rsi
0x180033850  mov     rax, rbx
0x180033853  add     rsp, 38h
0x180033857  pop     rdi
0x180033858  pop     rsi
0x180033859  pop     rbx
0x18003385a  pop     rbp
0x18003385b  retn
0x18003385c  mov     r9d, eax; char *
0x18003385f  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x180033866  mov     edx, 0Bh; void *
0x18003386b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
