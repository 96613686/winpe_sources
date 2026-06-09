# CCabFolder::OnCopy(IUnknown *,IShellItemArray *,IBindCtx *)

- ea: `0x18000ee90`
- end: `0x18000ef13`
- name: `?OnCopy@CCabFolder@@SAJPEAUIUnknown@@PEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `131`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002620`
- `0x18000ee90`
- `0x180013010`

## import_xrefs

- `ole32!OleSetClipboard` at `0x18000eee5`
- `ole32!OleSetClipboard` at `0x18000eee5`

## pseudocode

```c
__int64 __fastcall CCabFolder::OnCopy(struct IUnknown *a1, struct IShellItemArray *a2, struct IBindCtx *a3)
{
  struct IShellItemArrayVtbl *lpVtbl; // rax
  HRESULT v4; // ebx
  LPDATAOBJECT pDataObj; // [rsp+30h] [rbp-18h] BYREF

  lpVtbl = a2->lpVtbl;
  pDataObj = 0;
  v4 = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, const GUID *, GUID *, LPDATAOBJECT *))lpVtbl->BindToHandler)(
         a2,
         0,
         &BHID_DataObject,
         &GUID_0000010e_0000_0000_c000_000000000046,
         &pDataObj);
  if ( v4 >= 0 )
  {
    v4 = OleSetClipboard(pDataObj);
    ((void (__fastcall *)(LPDATAOBJECT))pDataObj->lpVtbl->Release)(pDataObj);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ee90  push    rbx
0x18000ee92  sub     rsp, 40h
0x18000ee96  mov     rax, cs:__security_cookie
0x18000ee9d  xor     rax, rsp
0x18000eea0  mov     [rsp+48h+var_10], rax
0x18000eea5  mov     rax, [rdx]
0x18000eea8  lea     rcx, [rsp+48h+pDataObj]
0x18000eead  mov     r10, rdx
0x18000eeb0  mov     [rsp+48h+var_28], rcx
0x18000eeb5  lea     r9, _GUID_0000010e_0000_0000_c000_000000000046
0x18000eebc  mov     [rsp+48h+pDataObj], 0
0x18000eec5  lea     r8, BHID_DataObject
0x18000eecc  xor     edx, edx
0x18000eece  mov     rax, [rax+18h]
0x18000eed2  mov     rcx, r10
0x18000eed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeda  mov     ebx, eax
0x18000eedc  test    eax, eax
0x18000eede  js      short loc_18000EEFE
0x18000eee0  mov     rcx, [rsp+48h+pDataObj]; pDataObj
0x18000eee5  call    cs:__imp_OleSetClipboard
0x18000eeeb  mov     rcx, [rsp+48h+pDataObj]
0x18000eef0  mov     ebx, eax
0x18000eef2  mov     rax, [rcx]
0x18000eef5  mov     rax, [rax+10h]
0x18000eef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eefe  mov     eax, ebx
0x18000ef00  mov     rcx, [rsp+48h+var_10]
0x18000ef05  xor     rcx, rsp; StackCookie
0x18000ef08  call    __security_check_cookie
0x18000ef0d  add     rsp, 40h
0x18000ef11  pop     rbx
0x18000ef12  retn
```
