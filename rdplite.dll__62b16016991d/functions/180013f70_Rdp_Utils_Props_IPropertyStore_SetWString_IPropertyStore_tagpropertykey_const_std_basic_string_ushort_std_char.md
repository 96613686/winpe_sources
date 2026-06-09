# Rdp::Utils::Props::IPropertyStore_SetWString(IPropertyStore *,_tagpropertykey const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180013f70`
- end: `0x18001404d`
- name: `?IPropertyStore_SetWString@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800140a8`

## callees

- `0x180006a74`
- `0x180013f70`
- `0x180028340`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013fbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013fbe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001403c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001403c`

## string_xrefs

- `0x180013fea`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_SetWString(__int64 a1, __int64 a2, _WORD **a3)
{
  _WORD *v3; // rbx
  unsigned int v5; // ebx
  __int64 v6; // rax
  SIZE_T v7; // rdi
  void *v8; // rax
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = a3;
  *(_OWORD *)pvar = 0;
  v11 = 0;
  if ( (unsigned __int64)a3[3] > 7 )
    v3 = *a3;
  if ( !v3 )
  {
    v5 = -2147024809;
LABEL_9:
    *(_OWORD *)pvar = 0;
    v11 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PropsHelpers.h",
      (const char *)v5,
      0);
    goto LABEL_13;
  }
  v6 = -1;
  do
    ++v6;
  while ( v3[v6] );
  v7 = 2 * v6 + 2;
  v8 = CoTaskMemAlloc(v7);
  pvar[1] = v8;
  if ( !v8 )
  {
    v5 = -2147024882;
    goto LABEL_9;
  }
  if ( v7 )
    memcpy_0(v8, v3, v7);
  LOWORD(pvar[0]) = 31;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)a1 + 48LL))(
         a1,
         PKEY_EncodingDllName,
         pvar);
LABEL_13:
  PropVariantClear(pvar);
  return v5;
}

```

## disassembly

```asm
0x180013f70  push    rbx
0x180013f72  push    rbp
0x180013f73  push    rsi
0x180013f74  push    rdi
0x180013f75  sub     rsp, 48h
0x180013f79  mov     rbx, r8
0x180013f7c  mov     rsi, rcx
0x180013f7f  xorps   xmm0, xmm0
0x180013f82  xor     eax, eax
0x180013f84  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x180013f89  mov     [rsp+68h+var_38], rax
0x180013f8e  cmp     qword ptr [r8+18h], 7
0x180013f93  jbe     short loc_180013F98
0x180013f95  mov     rbx, [r8]
0x180013f98  xor     ebp, ebp
0x180013f9a  test    rbx, rbx
0x180013f9d  jnz     short loc_180013FA6
0x180013f9f  mov     ebx, 80070057h
0x180013fa4  jmp     short loc_180013FD3
0x180013fa6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013faa  inc     rax
0x180013fad  cmp     [rbx+rax*2], bp
0x180013fb1  jnz     short loc_180013FAA
0x180013fb3  lea     rdi, ds:2[rax*2]
0x180013fbb  mov     rcx, rdi; cb
0x180013fbe  call    cs:__imp_CoTaskMemAlloc
0x180013fc4  mov     [rsp+68h+pvar+8], rax
0x180013fc9  test    rax, rax
0x180013fcc  jnz     short loc_180013FFD
0x180013fce  mov     ebx, 8007000Eh
0x180013fd3  xorps   xmm0, xmm0
0x180013fd6  xor     eax, eax
0x180013fd8  movups  xmmword ptr [rsp+68h+pvar], xmm0; int
0x180013fdd  mov     [rsp+68h+var_38], rax
0x180013fe2  mov     rcx, [rsp+68h]; this
0x180013fe7  mov     r9d, ebx; char *
0x180013fea  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180013ff1  mov     edx, 1B6h; void *
0x180013ff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ffb  jmp     short loc_180014037
0x180013ffd  test    rdi, rdi
0x180014000  jz      short loc_180014010
0x180014002  mov     r8, rdi; Size
0x180014005  mov     rdx, rbx; Src
0x180014008  mov     rcx, rax; void *
0x18001400b  call    memcpy_0
0x180014010  mov     eax, 1Fh
0x180014015  mov     word ptr [rsp+68h+pvar], ax
0x18001401a  mov     rax, [rsi]
0x18001401d  lea     r8, [rsp+68h+pvar]
0x180014022  lea     rdx, PKEY_EncodingDllName
0x180014029  mov     rcx, rsi
0x18001402c  mov     rax, [rax+30h]
0x180014030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014035  mov     ebx, eax
0x180014037  lea     rcx, [rsp+68h+pvar]; pvar
0x18001403c  call    cs:__imp_PropVariantClear
0x180014042  mov     eax, ebx
0x180014044  add     rsp, 48h
0x180014048  pop     rdi
0x180014049  pop     rsi
0x18001404a  pop     rbp
0x18001404b  pop     rbx
0x18001404c  retn
```
