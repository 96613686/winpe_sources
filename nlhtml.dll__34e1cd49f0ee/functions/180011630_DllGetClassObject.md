# DllGetClassObject

- ea: `0x180011630`
- end: `0x18001172b`
- name: `DllGetClassObject`
- size: `251`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180011630`
- `0x180011734`
- `0x180014700`
- `0x180025010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v3; // rax
  CHtmlIFilterCF *v4; // rax
  __int64 (***v5)(void); // rax
  __int64 (***v6)(void); // rdi
  __int64 (*v7)(void); // rax
  __int64 v9; // rax
  HRESULT v10; // ebx
  void *retaddr; // [rsp+28h] [rbp+0h]
  __int64 (***v12)(void); // [rsp+48h] [rbp+20h]

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  v3 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_HtmlIFilter.Data1;
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_HtmlIFilter.Data1 )
    v3 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_HtmlIFilter.Data4;
  if ( !v3 )
    goto LABEL_5;
  v9 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_HtmlClass.Data1;
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_HtmlClass.Data1 )
    v9 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_HtmlClass.Data4;
  if ( v9 )
    return -2147467262;
LABEL_5:
  v4 = (CHtmlIFilterCF *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
    return -2147024882;
  v5 = (__int64 (***)(void))CHtmlIFilterCF::CHtmlIFilterCF(v4);
  v6 = v5;
  v12 = v5;
  if ( !v5 )
    return -2147024882;
  v7 = **v5;
  try
  {
    v10 = v7();
    ((void (__fastcall *)(__int64 (***)(void)))(*v6)[2])(v6);
  }
  catch ( ... )
  {
    if ( v12 )
      ((void (__fastcall *)(__int64 (***)(void)))(*v12)[2])(v12);
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      422,
      "onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\htmliflt.cxx");
  }
  return v10;
}

```

## disassembly

```asm
0x180011630  mov     [rsp+arg_0], rbx
0x180011635  mov     [rsp+arg_8], rsi
0x18001163a  mov     [rsp+arg_10], r8
0x18001163f  push    rdi
0x180011640  sub     rsp, 20h
0x180011644  mov     rbx, r8
0x180011647  mov     rsi, rdx
0x18001164a  test    r8, r8
0x18001164d  jz      loc_18001171E
0x180011653  mov     [rsp+28h+arg_18], 0
0x18001165c  mov     qword ptr [r8], 0
0x180011663  mov     rax, [rcx]
0x180011666  sub     rax, qword ptr cs:CLSID_HtmlIFilter.Data1
0x18001166d  jnz     short loc_18001167A
0x18001166f  mov     rax, [rcx+8]
0x180011673  sub     rax, qword ptr cs:CLSID_HtmlIFilter.Data4
0x18001167a  test    rax, rax
0x18001167d  jnz     short loc_1800116E7
0x18001167f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011686  mov     ecx, 10h; unsigned __int64
0x18001168b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011690  mov     [rsp+28h+arg_18], rax
0x180011695  test    rax, rax
0x180011698  jz      short loc_18001170E
0x18001169a  mov     rcx, rax; this
0x18001169d  call    ??0CHtmlIFilterCF@@QEAA@XZ; CHtmlIFilterCF::CHtmlIFilterCF(void)
0x1800116a2  mov     rdi, rax
0x1800116a5  mov     [rsp+28h+arg_18], rax
0x1800116aa  test    rax, rax
0x1800116ad  jz      short loc_180011717
0x1800116af  mov     rax, [rax]
0x1800116b2  mov     r8, rbx
0x1800116b5  mov     rdx, rsi
0x1800116b8  mov     rcx, rdi
0x1800116bb  mov     rax, [rax]
0x1800116be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116c3  mov     ebx, eax
0x1800116c5  mov     rax, [rdi]
0x1800116c8  mov     rcx, rdi
0x1800116cb  mov     rax, [rax+10h]
0x1800116cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116d4  nop
0x1800116d5  mov     eax, ebx
0x1800116d7  mov     rbx, [rsp+28h+arg_0]
0x1800116dc  mov     rsi, [rsp+28h+arg_8]
0x1800116e1  add     rsp, 20h
0x1800116e5  pop     rdi
0x1800116e6  retn
0x1800116e7  mov     rax, [rcx]
0x1800116ea  sub     rax, qword ptr cs:CLSID_HtmlClass.Data1
0x1800116f1  jnz     short loc_1800116FE
0x1800116f3  mov     rax, [rcx+8]
0x1800116f7  sub     rax, qword ptr cs:CLSID_HtmlClass.Data4
0x1800116fe  test    rax, rax
0x180011701  jz      loc_18001167F
0x180011707  mov     ebx, 80004002h
0x18001170c  jmp     short loc_1800116D5
0x18001170e  mov     [rsp+28h+arg_18], 0
0x180011717  mov     ebx, 8007000Eh
0x18001171c  jmp     short loc_1800116D5
0x18001171e  mov     eax, 80070057h
0x180011723  jmp     short loc_1800116D7
0x180011725  mov     ebx, dword ptr [rsp+28h+arg_10]
0x180011729  jmp     short loc_1800116D5
```
