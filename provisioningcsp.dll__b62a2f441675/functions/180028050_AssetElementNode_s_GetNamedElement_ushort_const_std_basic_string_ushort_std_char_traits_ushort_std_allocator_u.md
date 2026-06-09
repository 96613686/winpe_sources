# AssetElementNode::s_GetNamedElement(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>> *)

- ea: `0x180028050`
- end: `0x1800282c7`
- name: `?s_GetNamedElement@AssetElementNode@@CA?AV?$unique_ptr@UIElement@@U?$ProvReleaser@UIElement@@@@@std@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAV?$unique_ptr@UIProvisioningPackage@@U?$ProvReleaser@UIProvisioningPackage@@@@@3@@Z`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180026dbc`

## callees

- `0x1800090e0`
- `0x180026b6c`
- `0x180028050`
- `0x18003586a`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180028173`
- `msvcrt!_wcsicmp` at `0x180028173`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x1800280a9`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x1800280a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall AssetElementNode::s_GetNamedElement(_QWORD *a1, const wchar_t *a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *v7; // rdi
  int v8; // eax
  _QWORD *v9; // rcx
  _QWORD *v10; // rsi
  int v11; // eax
  __int64 v12; // rbx
  __int64 *NextElement; // rax
  __int64 v14; // r12
  _QWORD *v15; // r12
  _QWORD *v16; // rcx
  int v18; // [rsp+20h] [rbp-E0h]
  _QWORD *v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v21; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v22; // [rsp+48h] [rbp-B8h]
  wchar_t String2[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v22 = a1;
  v7 = 0;
  v21 = 0;
  v19 = 0;
  if ( a3[3] >= 8u )
    a3 = (_QWORD *)*a3;
  v8 = OpenProvisioningPackageForRead(a3, &v19);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)(unsigned int)v8,
      v18);
  v9 = 0;
  if ( v19 )
  {
    v7 = v19;
    v21 = v19;
    v9 = v19;
  }
  v10 = 0;
  v22 = 0;
  v19 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD **))(*v9 + 112LL))(v9, &v19);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)(unsigned int)v11,
      v18);
  if ( v19 )
    v10 = v19;
  v22 = v10;
  GetNextElement(&v20, v10);
  v12 = v20;
  while ( 1 )
  {
    if ( !v12 )
    {
      *a1 = 0;
      if ( v10 )
        (*(void (__fastcall **)(_QWORD *))(*v10 + 8LL))(v10);
      if ( v7 )
        goto LABEL_32;
      return a1;
    }
    memset_0(String2, 0, 0x208u);
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, wchar_t *, __int64))(*(_QWORD *)v12 + 24LL))(
           v12,
           L"Name",
           String2,
           260) >= 0
      && !_wcsicmp(a2, String2) )
    {
      break;
    }
    NextElement = (__int64 *)GetNextElement(&v19, v10);
    if ( &v20 != NextElement )
    {
      v14 = *NextElement;
      *NextElement = 0;
      if ( v14 != v12 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 80LL))(v12);
        v12 = v14;
        v20 = v14;
      }
    }
    if ( v19 )
      (*(void (__fastcall **)(_QWORD *))(*v19 + 80LL))(v19);
  }
  if ( a4 )
  {
    if ( a4 != &v21 )
    {
      v15 = v7;
      v7 = 0;
      v21 = 0;
      v16 = (_QWORD *)*a4;
      if ( v15 != (_QWORD *)*a4 )
      {
        if ( v16 )
          (*(void (__fastcall **)(_QWORD *))(*v16 + 128LL))(v16);
        *a4 = v15;
      }
    }
  }
  *a1 = v12;
  if ( v10 )
    (*(void (__fastcall **)(_QWORD *))(*v10 + 8LL))(v10);
  if ( v7 )
LABEL_32:
    (*(void (__fastcall **)(_QWORD *))(*v7 + 128LL))(v7);
  return a1;
}

```

## disassembly

```asm
0x180028050  push    rbp
0x180028052  push    rbx
0x180028053  push    rsi
0x180028054  push    rdi
0x180028055  push    r12
0x180028057  push    r13
0x180028059  push    r14
0x18002805b  push    r15
0x18002805d  lea     rbp, [rsp-188h]
0x180028065  sub     rsp, 288h
0x18002806c  mov     rax, cs:__security_cookie
0x180028073  xor     rax, rsp
0x180028076  mov     [rbp+1C0h+var_50], rax
0x18002807d  mov     r15, r9
0x180028080  mov     r13, rdx
0x180028083  mov     r14, rcx
0x180028086  mov     [rsp+2C0h+var_278], rcx
0x18002808b  xor     edi, edi
0x18002808d  mov     [rsp+2C0h+var_280], rdi
0x180028092  mov     [rsp+2C0h+var_290], rdi
0x180028097  cmp     qword ptr [r8+18h], 8
0x18002809c  jb      short loc_1800280A1
0x18002809e  mov     r8, [r8]
0x1800280a1  lea     rdx, [rsp+2C0h+var_290]
0x1800280a6  mov     rcx, r8
0x1800280a9  call    cs:__imp_OpenProvisioningPackageForRead
0x1800280b0  nop     dword ptr [rax+rax+00h]
0x1800280b5  mov     rcx, [rbp+1C8h]; this
0x1800280bc  test    eax, eax
0x1800280be  js      loc_1800282B2
0x1800280c4  mov     rax, [rsp+2C0h+var_290]
0x1800280c9  xor     ecx, ecx
0x1800280cb  test    rax, rax
0x1800280ce  jz      short loc_1800280DB
0x1800280d0  mov     rdi, rax
0x1800280d3  mov     [rsp+2C0h+var_280], rax
0x1800280d8  mov     rcx, rax
0x1800280db  xor     esi, esi
0x1800280dd  mov     [rsp+2C0h+var_278], rsi
0x1800280e2  mov     [rsp+2C0h+var_290], rsi
0x1800280e7  mov     rax, [rcx]
0x1800280ea  lea     rdx, [rsp+2C0h+var_290]
0x1800280ef  mov     rax, [rax+70h]
0x1800280f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280f8  mov     rcx, [rbp+1C8h]; this
0x1800280ff  test    eax, eax
0x180028101  js      loc_18002829D
0x180028107  mov     rax, [rsp+2C0h+var_290]
0x18002810c  test    rax, rax
0x18002810f  cmovnz  rsi, rax
0x180028113  mov     [rsp+2C0h+var_278], rsi
0x180028118  mov     rdx, rsi
0x18002811b  lea     rcx, [rsp+2C0h+var_288]
0x180028120  call    GetNextElement
0x180028125  nop
0x180028126  mov     rbx, [rsp+2C0h+var_288]
0x18002812b  test    rbx, rbx
0x18002812e  jz      loc_180028242
0x180028134  xor     edx, edx; Val
0x180028136  mov     r8d, 208h; Size
0x18002813c  lea     rcx, [rsp+2C0h+String2]; void *
0x180028141  call    memset_0
0x180028146  mov     rax, [rbx]
0x180028149  mov     r9d, 104h
0x18002814f  lea     r8, [rsp+2C0h+String2]
0x180028154  lea     rdx, aName; "Name"
0x18002815b  mov     rcx, rbx
0x18002815e  mov     rax, [rax+18h]
0x180028162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028167  test    eax, eax
0x180028169  js      short loc_180028183
0x18002816b  lea     rdx, [rsp+2C0h+String2]; String2
0x180028170  mov     rcx, r13; String1
0x180028173  call    cs:__imp__wcsicmp
0x18002817a  nop     dword ptr [rax+rax+00h]
0x18002817f  test    eax, eax
0x180028181  jz      short loc_1800281E1
0x180028183  mov     rdx, rsi
0x180028186  lea     rcx, [rsp+2C0h+var_290]
0x18002818b  call    GetNextElement
0x180028190  lea     rcx, [rsp+2C0h+var_288]
0x180028195  cmp     rcx, rax
0x180028198  jz      short loc_1800281C5
0x18002819a  mov     r12, [rax]
0x18002819d  mov     qword ptr [rax], 0
0x1800281a4  cmp     r12, rbx
0x1800281a7  jz      short loc_1800281C5
0x1800281a9  test    rbx, rbx
0x1800281ac  jz      short loc_1800281BD
0x1800281ae  mov     rax, [rbx]
0x1800281b1  mov     rcx, rbx
0x1800281b4  mov     rax, [rax+50h]
0x1800281b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281bd  mov     rbx, r12
0x1800281c0  mov     [rsp+2C0h+var_288], rbx
0x1800281c5  mov     rcx, [rsp+2C0h+var_290]
0x1800281ca  test    rcx, rcx
0x1800281cd  jz      short loc_1800281DC
0x1800281cf  mov     rax, [rcx]
0x1800281d2  mov     rax, [rax+50h]
0x1800281d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281db  nop
0x1800281dc  jmp     loc_18002812B
0x1800281e1  test    r15, r15
0x1800281e4  jz      short loc_180028219
0x1800281e6  lea     rax, [rsp+2C0h+var_280]
0x1800281eb  cmp     r15, rax
0x1800281ee  jz      short loc_180028219
0x1800281f0  mov     r12, rdi
0x1800281f3  xor     edi, edi
0x1800281f5  mov     [rsp+2C0h+var_280], rdi
0x1800281fa  mov     rcx, [r15]
0x1800281fd  cmp     r12, rcx
0x180028200  jz      short loc_180028219
0x180028202  test    rcx, rcx
0x180028205  jz      short loc_180028216
0x180028207  mov     rax, [rcx]
0x18002820a  mov     rax, [rax+80h]
0x180028211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028216  mov     [r15], r12
0x180028219  mov     [r14], rbx
0x18002821c  test    rsi, rsi
0x18002821f  jz      short loc_180028231
0x180028221  mov     rax, [rsi]
0x180028224  mov     rcx, rsi
0x180028227  mov     rax, [rax+8]
0x18002822b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028230  nop
0x180028231  test    rdi, rdi
0x180028234  jz      short loc_180028276
0x180028236  mov     rax, [rdi]
0x180028239  mov     rax, [rax+80h]
0x180028240  jmp     short loc_18002826D
0x180028242  mov     qword ptr [r14], 0
0x180028249  test    rsi, rsi
0x18002824c  jz      short loc_18002825E
0x18002824e  mov     rax, [rsi]
0x180028251  mov     rcx, rsi
0x180028254  mov     rax, [rax+8]
0x180028258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002825d  nop
0x18002825e  test    rdi, rdi
0x180028261  jz      short loc_180028276
0x180028263  mov     rdx, [rdi]
0x180028266  mov     rax, [rdx+80h]
0x18002826d  mov     rcx, rdi
0x180028270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028275  nop
0x180028276  mov     rax, r14
0x180028279  mov     rcx, [rbp+1C0h+var_50]
0x180028280  xor     rcx, rsp; StackCookie
0x180028283  call    __security_check_cookie
0x180028288  add     rsp, 288h
0x18002828f  pop     r15
0x180028291  pop     r14
0x180028293  pop     r13
0x180028295  pop     r12
0x180028297  pop     rdi
0x180028298  pop     rsi
0x180028299  pop     rbx
0x18002829a  pop     rbp
0x18002829b  retn
0x18002829d  mov     r9d, eax; char *
0x1800282a0  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x1800282a7  mov     edx, 70h ; 'p'; void *
0x1800282ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800282b2  mov     r9d, eax; char *
0x1800282b5  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x1800282bc  mov     edx, 69h ; 'i'; void *
0x1800282c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
