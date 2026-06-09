# DllIsMultiStream(ILockBytes *)

- ea: `0x180060ef0`
- end: `0x180060f93`
- name: `?DllIsMultiStream@@YAJPEAUILockBytes@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(struct ILockBytes *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000745c`

## callees

- `0x18000cdd8`
- `0x180034570`
- `0x180060ef0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060f82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060f82`

## pseudocode

```c
__int64 __fastcall DllIsMultiStream(struct ILockBytes *a1)
{
  int Buffer; // ebx
  unsigned int v3; // esi
  HRESULT (__stdcall *ReadAt)(ILockBytes *, ULARGE_INTEGER, void *, ULONG, ULONG *); // rax
  unsigned int v6; // [rsp+68h] [rbp+10h] BYREF
  int v7; // [rsp+70h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  pv = 0;
  v6 = 516;
  Buffer = GetBuffer(0x204u, 0x204u, (unsigned __int8 **)&pv, &v6);
  if ( Buffer >= 0 )
  {
    v3 = v6;
    ReadAt = a1->lpVtbl->ReadAt;
    v7 = 0;
    Buffer = ((__int64 (__fastcall *)(struct ILockBytes *, _QWORD, LPVOID, _QWORD, int *))ReadAt)(a1, 0, pv, v6, &v7);
    if ( Buffer >= 0 )
    {
      if ( v7 == v3 )
        Buffer = CMSFHeader::Validate((CMSFHeader *)pv);
      else
        Buffer = -2147286787;
    }
  }
  CoTaskMemFree(pv);
  return (unsigned int)Buffer;
}

```

## disassembly

```asm
0x180060ef0  mov     rax, rsp
0x180060ef3  push    rbx
0x180060ef4  push    rsi
0x180060ef5  push    r14
0x180060ef7  sub     rsp, 40h
0x180060efb  mov     r14, rcx
0x180060efe  mov     qword ptr [rax+20h], 0
0x180060f06  mov     ecx, 204h; unsigned int
0x180060f0b  lea     r9, [rax+10h]; unsigned int *
0x180060f0f  mov     edx, ecx; unsigned int
0x180060f11  mov     [rax+10h], ecx
0x180060f14  lea     r8, [rax+20h]; unsigned __int8 **
0x180060f18  call    ?GetBuffer@@YAJKKPEAPEAEPEAK@Z; GetBuffer(ulong,ulong,uchar * *,ulong *)
0x180060f1d  mov     ebx, eax
0x180060f1f  test    eax, eax
0x180060f21  js      short loc_180060F7D
0x180060f23  mov     rax, [r14]
0x180060f26  lea     rcx, [rsp+58h+arg_10]
0x180060f2b  mov     esi, [rsp+58h+arg_8]
0x180060f2f  mov     r9d, esi
0x180060f32  mov     r8, [rsp+58h+pv]
0x180060f37  mov     [rsp+58h+var_38], rcx
0x180060f3c  mov     rcx, r14
0x180060f3f  mov     rax, [rax+18h]
0x180060f43  mov     [rsp+58h+var_28], 0
0x180060f4c  mov     rdx, [rsp+58h+var_28]
0x180060f51  mov     [rsp+58h+arg_10], 0
0x180060f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f5e  mov     ebx, eax
0x180060f60  test    eax, eax
0x180060f62  js      short loc_180060F7D
0x180060f64  cmp     [rsp+58h+arg_10], esi
0x180060f68  jz      short loc_180060F71
0x180060f6a  mov     ebx, 800300FDh
0x180060f6f  jmp     short loc_180060F7D
0x180060f71  mov     rcx, [rsp+58h+pv]; this
0x180060f76  call    ?Validate@CMSFHeader@@QEBAJXZ; CMSFHeader::Validate(void)
0x180060f7b  mov     ebx, eax
0x180060f7d  mov     rcx, [rsp+58h+pv]; pv
0x180060f82  call    cs:__imp_CoTaskMemFree
0x180060f88  mov     eax, ebx
0x180060f8a  add     rsp, 40h
0x180060f8e  pop     r14
0x180060f90  pop     rsi
0x180060f91  pop     rbx
0x180060f92  retn
```
