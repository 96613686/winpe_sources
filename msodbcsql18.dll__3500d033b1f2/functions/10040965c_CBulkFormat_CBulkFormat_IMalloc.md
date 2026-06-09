# CBulkFormat::CBulkFormat(IMalloc *)

- ea: `0x10040965c`
- end: `0x1004097cb`
- name: `??0CBulkFormat@@QEAA@PEAUIMalloc@@@Z`
- size: `367`
- prototype: `CBulkFormat *__fastcall(CBulkFormat *__hidden this, struct IMalloc *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1004085bc`
- `0x100409338`

## callees

- `0x10040965c`
- `0x100409898`
- `0x10040e480`
- `0x10054811c`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1004096f8`
- `KERNEL32!LoadLibraryW` at `0x1004096f8`
- `KERNEL32!GetProcAddress` at `0x100409711`
- `KERNEL32!GetProcAddress` at `0x100409711`

## string_xrefs

- `0x1004096f1`: `xmllite.dll`
- `0x10040970a`: `CreateXmlReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
CBulkFormat *__fastcall CBulkFormat::CBulkFormat(CBulkFormat *this, struct IMalloc *a2)
{
  _QWORD *v3; // rsi
  _QWORD *v4; // rdi
  char *v5; // r14
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  char pExceptionObject; // [rsp+58h] [rbp+10h] BYREF

  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *(_QWORD *)this = &CBulkRecord::`vftable';
  *((_QWORD *)this + 8) = 0;
  v3 = (_QWORD *)((char *)this + 72);
  *((_QWORD *)this + 10) = (char *)this + 72;
  *((_QWORD *)this + 9) = (char *)this + 72;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  v4 = (_QWORD *)((char *)this + 104);
  *((_QWORD *)this + 14) = (char *)this + 104;
  *((_QWORD *)this + 13) = (char *)this + 104;
  *((_QWORD *)this + 15) = 0;
  v5 = (char *)this + 128;
  *((_QWORD *)this + 16) = 0;
  *((_BYTE *)this + 136) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 38) = 0;
  *((_QWORD *)this + 20) = a2;
  LibraryW = LoadLibraryW(L"xmllite.dll");
  *((_QWORD *)this + 15) = LibraryW;
  if ( !LibraryW )
  {
    CXMLRWLoadException::CXMLRWLoadException(&pExceptionObject, 1);
    throw (CXMLRWLoadException *)&pExceptionObject;
  }
  ProcAddress = GetProcAddress(LibraryW, "CreateXmlReader");
  if ( !ProcAddress )
  {
    CXMLRWLoadException::CXMLRWLoadException(&pExceptionObject, 2);
    throw (CXMLRWLoadException *)&pExceptionObject;
  }
  if ( ((unsigned int (__fastcall *)(__int64 *, char *, _QWORD))ProcAddress)(
         qword_1005586F0,
         v5,
         *((_QWORD *)this + 20)) )
  {
    CXMLRWLoadException::CXMLRWLoadException(&pExceptionObject, 3);
    throw (CXMLRWLoadException *)&pExceptionObject;
  }
  v4[1] = v4;
  *v4 = v4;
  v3[1] = v3;
  *v3 = v3;
  CBulkFormat::Init(this);
  return this;
}

```

## disassembly

```asm
0x10040965c  mov     rax, rsp
0x10040965f  mov     [rax+8], rcx
0x100409663  push    rsi
0x100409664  push    rdi
0x100409665  push    r14
0x100409667  sub     rsp, 30h
0x10040966b  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x100409673  mov     [rax+18h], rbx
0x100409677  mov     [rax+20h], rbp
0x10040967b  mov     rbx, rcx
0x10040967e  xor     ebp, ebp
0x100409680  mov     [rcx+8], rbp
0x100409684  mov     [rcx+10h], rbp
0x100409688  mov     [rcx+18h], rbp
0x10040968c  mov     [rcx+20h], rbp
0x100409690  mov     [rcx+28h], rbp
0x100409694  mov     [rcx+30h], rbp
0x100409698  mov     [rcx+38h], rbp
0x10040969c  lea     rax, ??_7CBulkRecord@@6B@; const CBulkRecord::`vftable'
0x1004096a3  mov     [rcx], rax
0x1004096a6  mov     [rcx+40h], rbp
0x1004096aa  lea     rsi, [rcx+48h]
0x1004096ae  mov     [rsi+8], rsi
0x1004096b2  mov     [rsi], rsi
0x1004096b5  mov     [rcx+58h], rbp
0x1004096b9  mov     [rcx+60h], rbp
0x1004096bd  lea     rdi, [rcx+68h]
0x1004096c1  mov     [rdi+8], rdi
0x1004096c5  mov     [rdi], rdi
0x1004096c8  mov     [rcx+78h], rbp
0x1004096cc  lea     r14, [rcx+80h]
0x1004096d3  mov     [r14], rbp
0x1004096d6  mov     [rcx+88h], bpl
0x1004096dd  mov     [rcx+90h], rbp
0x1004096e4  mov     [rcx+98h], ebp
0x1004096ea  mov     [rcx+0A0h], rdx
0x1004096f1  lea     rcx, LibFileName; "xmllite.dll"
0x1004096f8  call    cs:__imp_LoadLibraryW
0x1004096fe  mov     [rbx+78h], rax
0x100409702  mov     rcx, rax; hModule
0x100409705  test    rax, rax
0x100409708  jz      short loc_100409789
0x10040970a  lea     rdx, ProcName; "CreateXmlReader"
0x100409711  call    cs:__imp_GetProcAddress
0x100409717  test    rax, rax
0x10040971a  jz      loc_1004097AA
0x100409720  mov     r8, [rbx+0A0h]
0x100409727  mov     rdx, r14
0x10040972a  lea     rcx, qword_1005586F0
0x100409731  call    cs:__guard_dispatch_icall_fptr
0x100409737  test    eax, eax
0x100409739  jnz     short loc_100409768
0x10040973b  mov     [rdi+8], rdi
0x10040973f  mov     [rdi], rdi
0x100409742  mov     [rsi+8], rsi
0x100409746  mov     [rsi], rsi
0x100409749  mov     rcx, rbx; this
0x10040974c  call    ?Init@CBulkFormat@@AEAAXXZ; CBulkFormat::Init(void)
0x100409751  nop
0x100409752  mov     rax, rbx
0x100409755  mov     rbx, [rsp+48h+arg_10]
0x10040975a  mov     rbp, [rsp+48h+arg_18]
0x10040975f  add     rsp, 30h
0x100409763  pop     r14
0x100409765  pop     rdi
0x100409766  pop     rsi
0x100409767  retn
0x100409768  mov     edx, 3
0x10040976d  lea     rcx, [rsp+48h+pExceptionObject]
0x100409772  call    ??0CXMLRWLoadException@@QEAA@W4EX_CODE@0@@Z; CXMLRWLoadException::CXMLRWLoadException(CXMLRWLoadException::EX_CODE)
0x100409777  lea     rdx, _TI1?AVCXMLRWLoadException@@; pThrowInfo
0x10040977e  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x100409783  call    _CxxThrowException_0
0x100409789  mov     edx, 1
0x10040978e  lea     rcx, [rsp+48h+pExceptionObject]
0x100409793  call    ??0CXMLRWLoadException@@QEAA@W4EX_CODE@0@@Z; CXMLRWLoadException::CXMLRWLoadException(CXMLRWLoadException::EX_CODE)
0x100409798  lea     rdx, _TI1?AVCXMLRWLoadException@@; pThrowInfo
0x10040979f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1004097a4  call    _CxxThrowException_0
0x1004097aa  mov     edx, 2
0x1004097af  lea     rcx, [rsp+48h+pExceptionObject]
0x1004097b4  call    ??0CXMLRWLoadException@@QEAA@W4EX_CODE@0@@Z; CXMLRWLoadException::CXMLRWLoadException(CXMLRWLoadException::EX_CODE)
0x1004097b9  lea     rdx, _TI1?AVCXMLRWLoadException@@; pThrowInfo
0x1004097c0  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1004097c5  call    _CxxThrowException_0
```
