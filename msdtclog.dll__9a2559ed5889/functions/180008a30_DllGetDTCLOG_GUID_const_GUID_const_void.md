# DllGetDTCLOG(_GUID const &,_GUID const &,void * *)

- ea: `0x180008a30`
- end: `0x180008a97`
- name: `?DllGetDTCLOG@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `103`
- prototype: `HRESULT __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008a20`

## callees

- `0x180008a30`
- `0x180008aa0`
- `0x180015010`

## pseudocode

```c
HRESULT __fastcall DllGetDTCLOG(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  HRESULT result; // eax
  int v6; // ebx
  LPVOID ppv; // [rsp+58h] [rbp+20h] BYREF

  ppv = 0;
  result = DllGetClassObject(a1, &IID_IClassFactory, &ppv);
  if ( result >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const struct _GUID *, void **))(*(_QWORD *)ppv + 24LL))(
           ppv,
           0,
           a2,
           a3);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180008a30  mov     [rsp+arg_0], rbx
0x180008a35  push    rdi
0x180008a36  sub     rsp, 30h
0x180008a3a  mov     rbx, r8
0x180008a3d  mov     [rsp+38h+ppv], 0
0x180008a46  mov     rdi, rdx
0x180008a49  lea     r8, [rsp+38h+ppv]; ppv
0x180008a4e  lea     rdx, IID_IClassFactory; riid
0x180008a55  call    DllGetClassObject
0x180008a5a  test    eax, eax
0x180008a5c  js      short loc_180008A8C
0x180008a5e  mov     rcx, [rsp+38h+ppv]
0x180008a63  mov     r9, rbx
0x180008a66  mov     r8, rdi
0x180008a69  xor     edx, edx
0x180008a6b  mov     rax, [rcx]
0x180008a6e  mov     rax, [rax+18h]
0x180008a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a77  mov     rcx, [rsp+38h+ppv]
0x180008a7c  mov     ebx, eax
0x180008a7e  mov     rdx, [rcx]
0x180008a81  mov     rax, [rdx+10h]
0x180008a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a8a  mov     eax, ebx
0x180008a8c  mov     rbx, [rsp+38h+arg_0]
0x180008a91  add     rsp, 30h
0x180008a95  pop     rdi
0x180008a96  retn
```
