# CHostObj::get_StdIn(ITextStream * *)

- ea: `0x140012a70`
- end: `0x140012b4b`
- name: `?get_StdIn@CHostObj@@UEAAJPEAPEAUITextStream@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(CHostObj *__hidden this, struct ITextStream **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140012a70`
- `0x140017010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140012aca`
- `ole32!CoCreateInstance` at `0x140012aca`

## pseudocode

```c
__int64 __fastcall CHostObj::get_StdIn(CHostObj *this, struct ITextStream **a2)
{
  _QWORD *v5; // rbx
  HRESULT v6; // edi
  _BOOL8 v7; // r8
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = (_QWORD *)((char *)this + 104);
  *a2 = 0;
  if ( !*((_QWORD *)this + 13) )
  {
    ppv = 0;
    v6 = CoCreateInstance(&CLSID_FileSystemObject, 0, 1u, &IID_IFileSystem3, &ppv);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v7 = Global::g_fWindowsNT && *(_BYTE *)(*((_QWORD *)this + 16) + 73LL);
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _BOOL8, _QWORD *))(*(_QWORD *)ppv + 256LL))(ppv, 0, v7, v5);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v6 < 0 )
      return (unsigned int)v6;
  }
  *a2 = (struct ITextStream *)*v5;
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  return 0;
}

```

## disassembly

```asm
0x140012a70  push    rbx
0x140012a72  push    rbp
0x140012a73  push    rsi
0x140012a74  push    rdi
0x140012a75  sub     rsp, 38h
0x140012a79  mov     rsi, rdx
0x140012a7c  mov     rbp, rcx
0x140012a7f  test    rdx, rdx
0x140012a82  jnz     short loc_140012A8E
0x140012a84  mov     eax, 80004003h
0x140012a89  jmp     loc_140012B42
0x140012a8e  lea     rbx, [rcx+68h]
0x140012a92  mov     qword ptr [rdx], 0
0x140012a99  cmp     qword ptr [rbx], 0
0x140012a9d  jnz     loc_140012B2B
0x140012aa3  xor     edx, edx; pUnkOuter
0x140012aa5  mov     [rsp+58h+arg_8], 0
0x140012aae  lea     rax, [rsp+58h+arg_8]
0x140012ab3  lea     r9, IID_IFileSystem3; riid
0x140012aba  mov     [rsp+58h+ppv], rax; ppv
0x140012abf  lea     rcx, CLSID_FileSystemObject; rclsid
0x140012ac6  lea     r8d, [rdx+1]; dwClsContext
0x140012aca  call    cs:__imp_CoCreateInstance
0x140012ad0  mov     edi, eax
0x140012ad2  test    eax, eax
0x140012ad4  js      short loc_140012B27
0x140012ad6  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140012add  jz      short loc_140012AF4
0x140012adf  mov     rax, [rbp+80h]
0x140012ae6  cmp     byte ptr [rax+49h], 0
0x140012aea  jz      short loc_140012AF4
0x140012aec  mov     r8d, 1
0x140012af2  jmp     short loc_140012AF7
0x140012af4  xor     r8d, r8d
0x140012af7  mov     rcx, [rsp+58h+arg_8]
0x140012afc  mov     r9, rbx
0x140012aff  xor     edx, edx
0x140012b01  mov     rax, [rcx]
0x140012b04  mov     rax, [rax+100h]
0x140012b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b10  mov     rcx, [rsp+58h+arg_8]
0x140012b15  mov     edi, eax
0x140012b17  mov     rax, [rcx]
0x140012b1a  mov     rax, [rax+10h]
0x140012b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b23  test    edi, edi
0x140012b25  jns     short loc_140012B2B
0x140012b27  mov     eax, edi
0x140012b29  jmp     short loc_140012B42
0x140012b2b  mov     rax, [rbx]
0x140012b2e  mov     [rsi], rax
0x140012b31  mov     rcx, [rbx]
0x140012b34  mov     rax, [rcx]
0x140012b37  mov     rax, [rax+8]
0x140012b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b40  xor     eax, eax
0x140012b42  add     rsp, 38h
0x140012b46  pop     rdi
0x140012b47  pop     rsi
0x140012b48  pop     rbp
0x140012b49  pop     rbx
0x140012b4a  retn
```
