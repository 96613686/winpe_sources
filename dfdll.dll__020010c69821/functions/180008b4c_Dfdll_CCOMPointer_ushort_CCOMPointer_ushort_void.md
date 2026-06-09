# Dfdll::CCOMPointer<ushort>::~CCOMPointer<ushort>(void)

- ea: `0x180008b4c`
- end: `0x180008b8b`
- name: `??1?$CCOMPointer@G@Dfdll@@UEAA@XZ`
- size: `63`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000dadc`
- `0x18001f25a`
- `0x18001f27e`
- `0x18001f302`
- `0x18001f30e`
- `0x18001f326`
- `0x18001f39e`
- `0x18001f3c2`
- `0x18001f3fe`

## callees

- `0x180008b4c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180008b68`
- `ole32!CoTaskMemFree` at `0x180008b68`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall Dfdll::CCOMPointer<unsigned short>::~CCOMPointer<unsigned short>(__int64 a1)
{
  void *v2; // rcx
  void **result; // rax

  *(_QWORD *)a1 = &Dfdll::CCOMPointerBase::`vftable';
  v2 = *(void **)(a1 + 8);
  if ( v2 )
    CoTaskMemFree(v2);
  *(_QWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 20) = 0;
  *(_DWORD *)(a1 + 16) = 0;
  result = &Dfdll::CObject::`vftable';
  *(_QWORD *)a1 = &Dfdll::CObject::`vftable';
  return result;
}

```

## disassembly

```asm
0x180008b4c  push    rbx
0x180008b4e  sub     rsp, 20h
0x180008b52  mov     rbx, rcx
0x180008b55  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x180008b5c  mov     [rcx], rax
0x180008b5f  mov     rcx, [rcx+8]; pv
0x180008b63  test    rcx, rcx
0x180008b66  jz      short loc_180008B6E
0x180008b68  call    cs:__imp_CoTaskMemFree
0x180008b6e  and     qword ptr [rbx+8], 0
0x180008b73  mov     byte ptr [rbx+14h], 0
0x180008b77  and     dword ptr [rbx+10h], 0
0x180008b7b  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180008b82  mov     [rbx], rax
0x180008b85  add     rsp, 20h
0x180008b89  pop     rbx
0x180008b8a  retn
```
