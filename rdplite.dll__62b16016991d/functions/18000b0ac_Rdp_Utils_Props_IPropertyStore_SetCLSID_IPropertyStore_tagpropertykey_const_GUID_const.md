# Rdp::Utils::Props::IPropertyStore_SetCLSID(IPropertyStore *,_tagpropertykey const &,_GUID const &)

- ea: `0x18000b0ac`
- end: `0x18000b128`
- name: `?IPropertyStore_SetCLSID@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_GUID@@@Z`
- size: `124`
- prototype: `int(Rdp::Utils::Props *__hidden this, struct IPropertyStore *, const struct _tagpropertykey *, const struct _GUID *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c410`
- `0x180017d90`
- `0x180017f38`
- `0x18001e824`

## callees

- `0x180006a74`
- `0x18000b0ac`
- `0x18002a010`

## import_xrefs

- `PROPSYS!InitPropVariantFromCLSID` at `0x18000b0d7`
- `PROPSYS!InitPropVariantFromCLSID` at `0x18000b0d7`

## string_xrefs

- `0x18000b0eb`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_SetCLSID(
        Rdp::Utils::Props *this,
        struct IPropertyStore *a2,
        const struct _tagpropertykey *a3,
        const struct _GUID *a4)
{
  HRESULT inited; // eax
  unsigned int v7; // ebx
  int v9[4]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_OWORD *)v9 = 0;
  v10 = 0;
  inited = InitPropVariantFromCLSID(&a3->fmtid, (PROPVARIANT *)v9);
  v7 = inited;
  if ( inited >= 0 )
    return (*(__int64 (__fastcall **)(Rdp::Utils::Props *, struct IPropertyStore *, int *))(*(_QWORD *)this + 48LL))(
             this,
             a2,
             v9);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x189,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PropsHelpers.h",
    (const char *)(unsigned int)inited,
    v9[0]);
  return v7;
}

```

## disassembly

```asm
0x18000b0ac  mov     r11, rsp
0x18000b0af  mov     [r11+8], rbx
0x18000b0b3  mov     [r11+10h], rsi
0x18000b0b7  push    rdi
0x18000b0b8  sub     rsp, 40h
0x18000b0bc  mov     rsi, rdx
0x18000b0bf  mov     rdi, rcx
0x18000b0c2  xorps   xmm0, xmm0
0x18000b0c5  xor     eax, eax
0x18000b0c7  movups  xmmword ptr [rsp+48h+var_28], xmm0; int
0x18000b0cc  mov     [r11-18h], rax
0x18000b0d0  lea     rdx, [r11-28h]; ppropvar
0x18000b0d4  mov     rcx, r8; clsid
0x18000b0d7  call    cs:__imp_InitPropVariantFromCLSID
0x18000b0dd  mov     ebx, eax
0x18000b0df  test    eax, eax
0x18000b0e1  jns     short loc_18000B100
0x18000b0e3  mov     rcx, [rsp+48h]; this
0x18000b0e8  mov     r9d, eax; char *
0x18000b0eb  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000b0f2  mov     edx, 189h; void *
0x18000b0f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b0fc  mov     eax, ebx
0x18000b0fe  jmp     short loc_18000B118
0x18000b100  mov     rax, [rdi]
0x18000b103  lea     r8, [rsp+48h+var_28]
0x18000b108  mov     rdx, rsi
0x18000b10b  mov     rcx, rdi
0x18000b10e  mov     rax, [rax+30h]
0x18000b112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b117  nop
0x18000b118  mov     rbx, [rsp+48h+arg_0]
0x18000b11d  mov     rsi, [rsp+48h+arg_8]
0x18000b122  add     rsp, 40h
0x18000b126  pop     rdi
0x18000b127  retn
```
