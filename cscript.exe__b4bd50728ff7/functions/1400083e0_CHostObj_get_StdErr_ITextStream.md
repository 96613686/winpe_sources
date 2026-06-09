# CHostObj::get_StdErr(ITextStream * *)

- ea: `0x1400083e0`
- end: `0x1400084d5`
- name: `?get_StdErr@CHostObj@@UEAAJPEAPEAUITextStream@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(CHostObj *__hidden this, struct ITextStream **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400083e0`
- `0x14000a0f0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetStdHandle` at `0x140008461`
- `KERNEL32!GetStdHandle` at `0x140008461`
- `ole32!CoCreateInstance` at `0x14000843a`
- `ole32!CoCreateInstance` at `0x14000843a`

## pseudocode

```c
__int64 __fastcall CHostObj::get_StdErr(CHostObj *this, struct ITextStream **a2)
{
  _QWORD *v5; // rbx
  HRESULT v6; // edi
  HANDLE StdHandle; // rax
  _BOOL8 v8; // r8
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = (_QWORD *)((char *)this + 120);
  *a2 = 0;
  if ( !*((_QWORD *)this + 15) )
  {
    ppv = 0;
    v6 = CoCreateInstance(&CLSID_FileSystemObject, 0, 1u, &IID_IFileSystem3, &ppv);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v8 = 0;
    if ( Global::g_fWindowsNT )
    {
      if ( *(_BYTE *)(*((_QWORD *)this + 16) + 73LL) || (StdHandle = GetStdHandle(0xFFFFFFF4), IsConsole(StdHandle)) )
        v8 = 1;
    }
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, _BOOL8, _QWORD *))(*(_QWORD *)ppv + 256LL))(ppv, 2, v8, v5);
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
0x1400083e0  push    rbx
0x1400083e2  push    rbp
0x1400083e3  push    rsi
0x1400083e4  push    rdi
0x1400083e5  sub     rsp, 38h
0x1400083e9  mov     rsi, rdx
0x1400083ec  mov     rbp, rcx
0x1400083ef  test    rdx, rdx
0x1400083f2  jnz     short loc_1400083FE
0x1400083f4  mov     eax, 80004003h
0x1400083f9  jmp     loc_1400084CC
0x1400083fe  lea     rbx, [rcx+78h]
0x140008402  mov     qword ptr [rdx], 0
0x140008409  cmp     qword ptr [rbx], 0
0x14000840d  jnz     loc_1400084B5
0x140008413  xor     edx, edx; pUnkOuter
0x140008415  mov     [rsp+58h+arg_8], 0
0x14000841e  lea     rax, [rsp+58h+arg_8]
0x140008423  lea     r9, IID_IFileSystem3; riid
0x14000842a  mov     [rsp+58h+ppv], rax; ppv
0x14000842f  lea     rcx, CLSID_FileSystemObject; rclsid
0x140008436  lea     r8d, [rdx+1]; dwClsContext
0x14000843a  call    cs:__imp_CoCreateInstance
0x140008440  mov     edi, eax
0x140008442  test    eax, eax
0x140008444  js      short loc_1400084B1
0x140008446  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x14000844d  jz      short loc_14000847B
0x14000844f  mov     rax, [rbp+80h]
0x140008456  cmp     byte ptr [rax+49h], 0
0x14000845a  jnz     short loc_140008473
0x14000845c  mov     ecx, 0FFFFFFF4h; nStdHandle
0x140008461  call    cs:__imp_GetStdHandle
0x140008467  mov     rcx, rax; void *
0x14000846a  call    ?IsConsole@@YA_NPEAX@Z; IsConsole(void *)
0x14000846f  test    al, al
0x140008471  jz      short loc_14000847B
0x140008473  mov     r8d, 1
0x140008479  jmp     short loc_14000847E
0x14000847b  xor     r8d, r8d
0x14000847e  mov     rcx, [rsp+58h+arg_8]
0x140008483  mov     r9, rbx
0x140008486  mov     edx, 2
0x14000848b  mov     rax, [rcx]
0x14000848e  mov     rax, [rax+100h]
0x140008495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000849a  mov     rcx, [rsp+58h+arg_8]
0x14000849f  mov     edi, eax
0x1400084a1  mov     rax, [rcx]
0x1400084a4  mov     rax, [rax+10h]
0x1400084a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084ad  test    edi, edi
0x1400084af  jns     short loc_1400084B5
0x1400084b1  mov     eax, edi
0x1400084b3  jmp     short loc_1400084CC
0x1400084b5  mov     rax, [rbx]
0x1400084b8  mov     [rsi], rax
0x1400084bb  mov     rcx, [rbx]
0x1400084be  mov     rax, [rcx]
0x1400084c1  mov     rax, [rax+8]
0x1400084c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084ca  xor     eax, eax
0x1400084cc  add     rsp, 38h
0x1400084d0  pop     rdi
0x1400084d1  pop     rsi
0x1400084d2  pop     rbp
0x1400084d3  pop     rbx
0x1400084d4  retn
```
