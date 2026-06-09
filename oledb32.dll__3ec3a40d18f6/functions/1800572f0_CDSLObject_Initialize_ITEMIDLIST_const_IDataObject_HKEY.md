# CDSLObject::Initialize(_ITEMIDLIST const *,IDataObject *,HKEY__ *)

- ea: `0x1800572f0`
- end: `0x180057399`
- name: `?Initialize@CDSLObject@@UEAAJPEFBU_ITEMIDLIST@@PEAUIDataObject@@PEAUHKEY__@@@Z`
- size: `169`
- prototype: `int(CDSLObject *__hidden this, const struct _ITEMIDLIST *, struct IDataObject *, HKEY)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800572f0`
- `0x180087010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18005735c`
- `KERNEL32!CloseHandle` at `0x18005735c`
- `ADVAPI32!RegOpenKeyExW` at `0x180057381`
- `ADVAPI32!RegOpenKeyExW` at `0x180057381`

## pseudocode

```c
__int64 __fastcall CDSLObject::Initialize(
        CDSLObject *this,
        const struct _ITEMIDLIST *a2,
        struct IDataObject *a3,
        HKEY a4)
{
  __int64 v5; // rcx
  HANDLE *phkResult; // rbx

  *((_QWORD *)this + 125) = a2;
  v5 = *((_QWORD *)this + 126);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 126) = 0;
  }
  if ( a3 )
  {
    *((_QWORD *)this + 126) = a3;
    ((void (__fastcall *)(struct IDataObject *))a3->lpVtbl->AddRef)(a3);
  }
  phkResult = (HANDLE *)((char *)this + 1016);
  if ( *phkResult )
  {
    CloseHandle(*phkResult);
    *phkResult = 0;
  }
  if ( a4 )
    RegOpenKeyExW(a4, 0, 0, 0x2000000u, (PHKEY)phkResult);
  return 0;
}

```

## disassembly

```asm
0x1800572f0  mov     [rsp+arg_0], rbx
0x1800572f5  mov     [rsp+arg_8], rsi
0x1800572fa  push    rdi
0x1800572fb  sub     rsp, 30h
0x1800572ff  mov     rbx, rcx
0x180057302  mov     [rcx+3E8h], rdx
0x180057309  mov     rcx, [rcx+3F0h]
0x180057310  mov     rsi, r9
0x180057313  mov     rdi, r8
0x180057316  test    rcx, rcx
0x180057319  jz      short loc_180057332
0x18005731b  mov     rax, [rcx]
0x18005731e  mov     rax, [rax+10h]
0x180057322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057327  mov     qword ptr [rbx+3F0h], 0
0x180057332  test    rdi, rdi
0x180057335  jz      short loc_18005734D
0x180057337  mov     [rbx+3F0h], rdi
0x18005733e  mov     rcx, rdi
0x180057341  mov     rax, [rdi]
0x180057344  mov     rax, [rax+8]
0x180057348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005734d  add     rbx, 3F8h
0x180057354  mov     rcx, [rbx]; hObject
0x180057357  test    rcx, rcx
0x18005735a  jz      short loc_180057369
0x18005735c  call    cs:__imp_CloseHandle
0x180057362  mov     qword ptr [rbx], 0
0x180057369  test    rsi, rsi
0x18005736c  jz      short loc_180057387
0x18005736e  mov     r9d, 2000000h; samDesired
0x180057374  mov     [rsp+38h+phkResult], rbx; phkResult
0x180057379  xor     r8d, r8d; ulOptions
0x18005737c  xor     edx, edx; lpSubKey
0x18005737e  mov     rcx, rsi; hKey
0x180057381  call    cs:__imp_RegOpenKeyExW
0x180057387  mov     rbx, [rsp+38h+arg_0]
0x18005738c  xor     eax, eax
0x18005738e  mov     rsi, [rsp+38h+arg_8]
0x180057393  add     rsp, 30h
0x180057397  pop     rdi
0x180057398  retn
```
