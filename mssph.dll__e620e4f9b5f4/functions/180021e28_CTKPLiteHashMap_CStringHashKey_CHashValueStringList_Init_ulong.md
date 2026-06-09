# CTKPLiteHashMap<CStringHashKey,CHashValueStringList>::Init(ulong)

- ea: `0x180021e28`
- end: `0x180021f0b`
- name: `?Init@?$CTKPLiteHashMap@VCStringHashKey@@VCHashValueStringList@@@@QEAAXK@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180020b7c`

## callees

- `0x18000e7fc`
- `0x180010250`
- `0x180011028`
- `0x180021e28`

## string_xrefs

- `0x180021ee2`: `onecoreuap\base\appmodel\Search\common\include\tplite_common.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTKPLiteHashMap<CStringHashKey,CHashValueStringList>::Init(__int64 a1)
{
  __int64 i; // rdx
  unsigned int v3; // ecx
  __int64 v4; // rsi
  __int64 v5; // rax
  bool v6; // cf
  unsigned __int64 v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !*(_QWORD *)(a1 + 8) )
  {
    for ( i = 0; (unsigned int)i < 0x1A; i = (unsigned int)(i + 1) )
    {
      v3 = *(_DWORD *)&asc_18002CAA0[2 * i];
      if ( !v3 )
        break;
      if ( v3 >= 0x11 )
        goto LABEL_8;
    }
    v3 = 17;
LABEL_8:
    *(_DWORD *)a1 = v3;
    v4 = v3;
    v5 = 8LL * v3;
    if ( !is_mul_ok(v3, 8u) )
      v5 = -1;
    v6 = __CFADD__(v5, 8);
    v7 = v5 + 8;
    if ( v6 )
      v7 = -1;
    v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
    {
      *v8 = v4;
      v9 = v8 + 1;
      `eh vector constructor iterator'(
        v8 + 1,
        8u,
        (unsigned int)v4,
        CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>::CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>,
        CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>::~CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>);
    }
    else
    {
      v9 = 0;
    }
    *(_QWORD *)(a1 + 8) = v9;
    if ( !v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x510,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\tplite_common.hxx",
        (const char *)0x8007000ELL,
        v10);
    *(_DWORD *)(a1 + 16) = 1;
  }
}

```

## disassembly

```asm
0x180021e28  mov     [rsp+arg_8], rbx
0x180021e2d  mov     [rsp+arg_10], rsi
0x180021e32  push    rdi
0x180021e33  sub     rsp, 30h
0x180021e37  mov     rdi, rcx
0x180021e3a  cmp     qword ptr [rcx+8], 0
0x180021e3f  jnz     loc_180021EFB
0x180021e45  xor     edx, edx
0x180021e47  cmp     edx, 1Ah
0x180021e4a  jnb     short loc_180021E63
0x180021e4c  lea     rcx, asc_18002CAA0; "\v"
0x180021e53  mov     ecx, [rcx+rdx*4]
0x180021e56  test    ecx, ecx
0x180021e58  jz      short loc_180021E63
0x180021e5a  cmp     ecx, 11h
0x180021e5d  jnb     short loc_180021E68
0x180021e5f  inc     edx
0x180021e61  jmp     short loc_180021E47
0x180021e63  mov     ecx, 11h
0x180021e68  mov     [rdi], ecx
0x180021e6a  mov     esi, ecx
0x180021e6c  mov     eax, 8
0x180021e71  mul     rsi
0x180021e74  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180021e7b  cmovb   rax, rcx
0x180021e7f  add     rax, 8
0x180021e83  cmovb   rax, rcx
0x180021e87  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021e8e  mov     rcx, rax; unsigned __int64
0x180021e91  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180021e96  mov     [rsp+38h+arg_0], rax
0x180021e9b  test    rax, rax
0x180021e9e  jz      short loc_180021ECC
0x180021ea0  mov     [rax], rsi
0x180021ea3  lea     rbx, [rax+8]
0x180021ea7  lea     rax, ??1?$CTPKeyedLiteSList@VCStringHashKey@@VCHashValueStringList@@@@QEAA@XZ; CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>::~CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>(void)
0x180021eae  mov     qword ptr [rsp+38h+var_18], rax; void (*)(void *)
0x180021eb3  lea     r9, ??0?$CTPKeyedLiteSList@VCStringHashKey@@VCHashValueStringList@@@@QEAA@XZ; void (*)(void *)
0x180021eba  mov     r8d, esi; unsigned __int64
0x180021ebd  mov     edx, 8; unsigned __int64
0x180021ec2  mov     rcx, rbx; void *
0x180021ec5  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180021eca  jmp     short loc_180021ECE
0x180021ecc  xor     ebx, ebx
0x180021ece  mov     [rdi+8], rbx
0x180021ed2  test    rbx, rbx
0x180021ed5  jnz     short loc_180021EF4
0x180021ed7  mov     rcx, [rsp+38h]; this
0x180021edc  mov     r9d, 8007000Eh; char *
0x180021ee2  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180021ee9  mov     edx, 510h; void *
0x180021eee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021ef4  mov     dword ptr [rdi+10h], 1
0x180021efb  mov     rbx, [rsp+38h+arg_8]
0x180021f00  mov     rsi, [rsp+38h+arg_10]
0x180021f05  add     rsp, 30h
0x180021f09  pop     rdi
0x180021f0a  retn
```
