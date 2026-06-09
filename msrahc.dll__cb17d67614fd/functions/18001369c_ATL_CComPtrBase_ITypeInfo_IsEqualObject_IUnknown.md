# ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)

- ea: `0x18001369c`
- end: `0x18001372a`
- name: `?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z`
- size: `142`
- prototype: `bool __fastcall(void (__fastcall ****)(_QWORD, GUID *, __int64 *), void (__fastcall ***)(_QWORD, GUID *, __int64 *))`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001317c`

## callees

- `0x180008924`
- `0x18001369c`
- `0x18001c010`

## pseudocode

```c
bool __fastcall ATL::CComPtrBase<ITypeInfo>::IsEqualObject(
        void (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        void (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  void (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rcx
  bool v5; // bl
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v3 = *a1;
  if ( !v3 )
    return a2 == 0;
  if ( !a2 )
    return 0;
  v7 = 0;
  v6 = 0;
  (**v3)(v3, &GUID_00000000_0000_0000_c000_000000000046, &v7);
  (**a2)(a2, &GUID_00000000_0000_0000_c000_000000000046, &v6);
  v5 = v7 == v6;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  return v5;
}

```

## disassembly

```asm
0x18001369c  push    rbx
0x18001369e  sub     rsp, 20h
0x1800136a2  mov     rbx, rdx
0x1800136a5  mov     rcx, [rcx]
0x1800136a8  test    rcx, rcx
0x1800136ab  jnz     short loc_1800136B5
0x1800136ad  test    rdx, rdx
0x1800136b0  setz    al
0x1800136b3  jmp     short loc_180013724
0x1800136b5  test    rbx, rbx
0x1800136b8  jz      short loc_180013722
0x1800136ba  mov     [rsp+28h+arg_10], 0
0x1800136c3  mov     [rsp+28h+arg_0], 0
0x1800136cc  mov     rax, [rcx]
0x1800136cf  lea     r8, [rsp+28h+arg_10]
0x1800136d4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800136db  mov     rax, [rax]
0x1800136de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136e3  mov     rax, [rbx]
0x1800136e6  lea     r8, [rsp+28h+arg_0]
0x1800136eb  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800136f2  mov     rcx, rbx
0x1800136f5  mov     rax, [rax]
0x1800136f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136fd  mov     rax, [rsp+28h+arg_0]
0x180013702  cmp     [rsp+28h+arg_10], rax
0x180013707  setz    bl
0x18001370a  lea     rcx, [rsp+28h+arg_0]
0x18001370f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013714  lea     rcx, [rsp+28h+arg_10]
0x180013719  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001371e  mov     al, bl
0x180013720  jmp     short loc_180013724
0x180013722  xor     al, al
0x180013724  add     rsp, 20h
0x180013728  pop     rbx
0x180013729  retn
```
