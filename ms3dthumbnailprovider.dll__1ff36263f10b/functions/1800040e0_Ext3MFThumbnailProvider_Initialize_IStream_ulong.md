# Ext3MFThumbnailProvider::Initialize(IStream *,ulong)

- ea: `0x1800040e0`
- end: `0x18000413d`
- name: `?Initialize@Ext3MFThumbnailProvider@@UEAAJPEAUIStream@@K@Z`
- size: `93`
- prototype: `__int64 __fastcall(Ext3MFThumbnailProvider *this, struct IStream *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800040e0`
- `0x18000b010`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x180004114`
- `ATL!__imp_AtlComPtrAssign` at `0x180004114`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Ext3MFThumbnailProvider::Initialize(Ext3MFThumbnailProvider *this, struct IStream *a2)
{
  __int64 result; // rax
  _QWORD *v4; // rbx
  __int64 v5; // rcx

  result = 0;
  if ( a2 )
  {
    v4 = (_QWORD *)((char *)this + 56);
    v5 = *((_QWORD *)this + 7);
    if ( v5 )
    {
      *v4 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      AtlComPtrAssign(v4, 0);
    }
    return ((__int64 (__fastcall *)(struct IStream *, GUID *, _QWORD *))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_0000000c_0000_0000_c000_000000000046,
             v4);
  }
  return result;
}

```

## disassembly

```asm
0x1800040e0  mov     [rsp+arg_0], rbx
0x1800040e5  push    rdi
0x1800040e6  sub     rsp, 20h
0x1800040ea  xor     eax, eax
0x1800040ec  mov     rdi, rdx
0x1800040ef  test    rdx, rdx
0x1800040f2  jz      short loc_180004132
0x1800040f4  lea     rbx, [rcx+38h]
0x1800040f8  mov     rcx, [rbx]
0x1800040fb  test    rcx, rcx
0x1800040fe  jz      short loc_18000411A
0x180004100  mov     [rbx], rax
0x180004103  mov     rax, [rcx]
0x180004106  mov     rax, [rax+10h]
0x18000410a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000410f  xor     edx, edx
0x180004111  mov     rcx, rbx
0x180004114  call    cs:__imp_AtlComPtrAssign
0x18000411a  mov     rax, [rdi]
0x18000411d  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180004124  mov     r8, rbx
0x180004127  mov     rcx, rdi
0x18000412a  mov     rax, [rax]
0x18000412d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004132  mov     rbx, [rsp+28h+arg_0]
0x180004137  add     rsp, 20h
0x18000413b  pop     rdi
0x18000413c  retn
```
