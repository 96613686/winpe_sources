# CHostObj::get_StdOut(ITextStream * *)

- ea: `0x140007f50`
- end: `0x140008047`
- name: `?get_StdOut@CHostObj@@UEAAJPEAPEAUITextStream@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(CHostObj *__hidden this, struct ITextStream **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140007f50`
- `0x14000a0f0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetStdHandle` at `0x140007fd1`
- `KERNEL32!GetStdHandle` at `0x140007fd1`
- `ole32!CoCreateInstance` at `0x140007faa`
- `ole32!CoCreateInstance` at `0x140007faa`

## pseudocode

```c
__int64 __fastcall CHostObj::get_StdOut(CHostObj *this, struct ITextStream **a2)
{
  _QWORD *v5; // rbx
  HRESULT v6; // edi
  HANDLE StdHandle; // rax
  _BOOL8 v8; // r8
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = (_QWORD *)((char *)this + 112);
  *a2 = 0;
  if ( !*((_QWORD *)this + 14) )
  {
    ppv = 0;
    v6 = CoCreateInstance(&CLSID_FileSystemObject, 0, 1u, &IID_IFileSystem3, &ppv);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v8 = 0;
    if ( Global::g_fWindowsNT )
    {
      if ( *(_BYTE *)(*((_QWORD *)this + 16) + 73LL) || (StdHandle = GetStdHandle(0xFFFFFFF5), IsConsole(StdHandle)) )
        v8 = 1;
    }
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, _BOOL8, _QWORD *))(*(_QWORD *)ppv + 256LL))(ppv, 1, v8, v5);
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
0x140007f50  push    rbx
0x140007f52  push    rbp
0x140007f53  push    rsi
0x140007f54  push    rdi
0x140007f55  sub     rsp, 38h
0x140007f59  mov     rsi, rdx
0x140007f5c  mov     rbp, rcx
0x140007f5f  test    rdx, rdx
0x140007f62  jnz     short loc_140007F6E
0x140007f64  mov     eax, 80004003h
0x140007f69  jmp     loc_14000803E
0x140007f6e  lea     rbx, [rcx+70h]
0x140007f72  mov     qword ptr [rdx], 0
0x140007f79  cmp     qword ptr [rbx], 0
0x140007f7d  jnz     loc_140008027
0x140007f83  xor     edx, edx; pUnkOuter
0x140007f85  mov     [rsp+58h+arg_8], 0
0x140007f8e  lea     rax, [rsp+58h+arg_8]
0x140007f93  lea     r9, IID_IFileSystem3; riid
0x140007f9a  mov     [rsp+58h+ppv], rax; ppv
0x140007f9f  lea     rcx, CLSID_FileSystemObject; rclsid
0x140007fa6  lea     r8d, [rdx+1]; dwClsContext
0x140007faa  call    cs:__imp_CoCreateInstance
0x140007fb0  mov     edi, eax
0x140007fb2  test    eax, eax
0x140007fb4  js      short loc_140008023
0x140007fb6  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140007fbd  jz      short loc_140007FEE
0x140007fbf  mov     rax, [rbp+80h]
0x140007fc6  cmp     byte ptr [rax+49h], 0
0x140007fca  jnz     short loc_140007FE3
0x140007fcc  mov     ecx, 0FFFFFFF5h; nStdHandle
0x140007fd1  call    cs:__imp_GetStdHandle
0x140007fd7  mov     rcx, rax; void *
0x140007fda  call    ?IsConsole@@YA_NPEAX@Z; IsConsole(void *)
0x140007fdf  test    al, al
0x140007fe1  jz      short loc_140007FEE
0x140007fe3  mov     r8d, 1
0x140007fe9  mov     edx, r8d
0x140007fec  jmp     short loc_140007FF5
0x140007fee  xor     r8d, r8d
0x140007ff1  lea     edx, [r8+1]
0x140007ff5  mov     rcx, [rsp+58h+arg_8]
0x140007ffa  mov     r9, rbx
0x140007ffd  mov     rax, [rcx]
0x140008000  mov     rax, [rax+100h]
0x140008007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000800c  mov     rcx, [rsp+58h+arg_8]
0x140008011  mov     edi, eax
0x140008013  mov     rax, [rcx]
0x140008016  mov     rax, [rax+10h]
0x14000801a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000801f  test    edi, edi
0x140008021  jns     short loc_140008027
0x140008023  mov     eax, edi
0x140008025  jmp     short loc_14000803E
0x140008027  mov     rax, [rbx]
0x14000802a  mov     [rsi], rax
0x14000802d  mov     rcx, [rbx]
0x140008030  mov     rax, [rcx]
0x140008033  mov     rax, [rax+8]
0x140008037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000803c  xor     eax, eax
0x14000803e  add     rsp, 38h
0x140008042  pop     rdi
0x140008043  pop     rsi
0x140008044  pop     rbp
0x140008045  pop     rbx
0x140008046  retn
```
