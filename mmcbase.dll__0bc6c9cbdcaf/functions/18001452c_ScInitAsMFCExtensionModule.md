# ScInitAsMFCExtensionModule

- ea: `0x18001452c`
- end: `0x1800145f5`
- name: `ScInitAsMFCExtensionModule`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007ca8`

## callees

- `0x180003c40`
- `0x1800041f0`
- `0x18001452c`

## import_xrefs

- `MFC42u!__imp_??0CDynLinkLibrary@@QEAA@AEAUAFX_EXTENSION_MODULE@@H@Z` at `0x1800145b3`
- `MFC42u!__imp_??0CDynLinkLibrary@@QEAA@AEAUAFX_EXTENSION_MODULE@@H@Z` at `0x1800145b3`
- `MFC42u!__imp_?AfxInitExtensionModule@@YAHAEAUAFX_EXTENSION_MODULE@@PEAUHINSTANCE__@@@Z` at `0x18001456e`
- `MFC42u!__imp_?AfxInitExtensionModule@@YAHAEAUAFX_EXTENSION_MODULE@@PEAUHINSTANCE__@@@Z` at `0x18001456e`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x180014596`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x180014596`

## string_xrefs

- `0x180014554`: `ScInitAsMFCExtensionModule`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ScInitAsMFCExtensionModule(__int64 a1, HINSTANCE a2)
{
  int v4; // eax
  CDynLinkLibrary *v5; // rax
  unsigned __int64 v7; // [rsp+28h] [rbp-20h] BYREF
  __int128 v8; // [rsp+30h] [rbp-18h]

  v8 = 0;
  ++mmcerror::SC::s_CallDepth;
  v7 = 3;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)&v7, L"ScInitAsMFCExtensionModule");
  if ( AfxInitExtensionModule((struct AFX_EXTENSION_MODULE *)qword_18002C348, a2) )
  {
    v5 = (CDynLinkLibrary *)operator new(0x80u);
    if ( v5 )
      CDynLinkLibrary::CDynLinkLibrary(v5, (struct AFX_EXTENSION_MODULE *)qword_18002C348, 0);
    *(_DWORD *)a1 = v7;
    v4 = HIDWORD(v7);
  }
  else
  {
    v7 = 0x8000400500000003uLL;
    v4 = -2147467259;
    *(_DWORD *)a1 = 3;
  }
  *(_DWORD *)(a1 + 4) = v4;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  --mmcerror::SC::s_CallDepth;
  mmcerror::SC::Trace_((mmcerror::SC *)&v7);
  return a1;
}

```

## disassembly

```asm
0x18001452c  mov     rax, rsp
0x18001452f  mov     [rax+8], rbx
0x180014533  push    rdi
0x180014534  sub     rsp, 40h
0x180014538  mov     rbx, rdx
0x18001453b  mov     rdi, rcx
0x18001453e  xorps   xmm0, xmm0
0x180014541  movdqu  xmmword ptr [rax-18h], xmm0
0x180014546  inc     cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x18001454c  mov     qword ptr [rax-20h], 3
0x180014554  lea     rdx, aScinitasmfcext; "ScInitAsMFCExtensionModule"
0x18001455b  lea     rcx, [rax-20h]; this
0x18001455f  call    ?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x180014564  mov     rdx, rbx
0x180014567  lea     rcx, qword_18002C348
0x18001456e  call    cs:__imp_?AfxInitExtensionModule@@YAHAEAUAFX_EXTENSION_MODULE@@PEAUHINSTANCE__@@@Z; AfxInitExtensionModule(AFX_EXTENSION_MODULE &,HINSTANCE__ *)
0x180014574  test    eax, eax
0x180014576  jnz     short loc_180014591
0x180014578  mov     [rsp+48h+var_20], 3
0x180014580  mov     eax, 80004005h
0x180014585  mov     [rsp+48h+var_1C], eax
0x180014589  mov     dword ptr [rdi], 3
0x18001458f  jmp     short loc_1800145C4
0x180014591  mov     ecx, 80h
0x180014596  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001459c  mov     [rsp+48h+arg_10], rax
0x1800145a1  test    rax, rax
0x1800145a4  jz      short loc_1800145BA
0x1800145a6  xor     r8d, r8d
0x1800145a9  lea     rdx, qword_18002C348
0x1800145b0  mov     rcx, rax
0x1800145b3  call    cs:__imp_??0CDynLinkLibrary@@QEAA@AEAUAFX_EXTENSION_MODULE@@H@Z; CDynLinkLibrary::CDynLinkLibrary(AFX_EXTENSION_MODULE &,int)
0x1800145b9  nop
0x1800145ba  mov     eax, [rsp+48h+var_20]
0x1800145be  mov     [rdi], eax
0x1800145c0  mov     eax, [rsp+48h+var_1C]
0x1800145c4  mov     [rdi+4], eax
0x1800145c7  mov     qword ptr [rdi+10h], 0
0x1800145cf  mov     qword ptr [rdi+8], 0
0x1800145d7  dec     cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x1800145dd  lea     rcx, [rsp+48h+var_20]; this
0x1800145e2  call    ?Trace_@SC@mmcerror@@QEBAXXZ; mmcerror::SC::Trace_(void)
0x1800145e7  mov     rax, rdi
0x1800145ea  mov     rbx, [rsp+48h+arg_0]
0x1800145ef  add     rsp, 40h
0x1800145f3  pop     rdi
0x1800145f4  retn
```
