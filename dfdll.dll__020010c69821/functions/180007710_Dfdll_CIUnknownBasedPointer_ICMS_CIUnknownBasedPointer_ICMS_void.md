# Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(void)

- ea: `0x180007710`
- end: `0x18000774e`
- name: `??1?$CIUnknownBasedPointer@UICMS@@@Dfdll@@UEAA@XZ`
- size: `62`
- prototype: ``
- caller_count: `27`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000dadc`
- `0x18001f1ee`
- `0x18001f21e`
- `0x18001f266`
- `0x18001f272`
- `0x18001f28a`
- `0x18001f296`
- `0x18001f2a2`
- `0x18001f2ae`
- `0x18001f2ba`
- `0x18001f2c6`
- `0x18001f2d2`
- `0x18001f2de`
- `0x18001f2ea`
- `0x18001f2f6`
- `0x18001f332`
- `0x18001f34a`
- `0x18001f356`
- `0x18001f362`
- `0x18001f36e`
- `0x18001f37a`
- `0x18001f386`
- `0x18001f392`
- `0x18001f3b6`
- `0x18001f3da`
- `0x18001f3e6`
- `0x18001f3f2`

## callees

- `0x180007710`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall Dfdll::CIUnknownBasedPointer<ICMS>::~CIUnknownBasedPointer<ICMS>(_QWORD *a1)
{
  __int64 v2; // rcx
  void **result; // rax

  *a1 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  v2 = a1[1];
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  a1[1] = 0;
  result = &Dfdll::CObject::`vftable';
  *a1 = &Dfdll::CObject::`vftable';
  return result;
}

```

## disassembly

```asm
0x180007710  push    rbx
0x180007712  sub     rsp, 20h
0x180007716  mov     rbx, rcx
0x180007719  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180007720  mov     [rcx], rax
0x180007723  mov     rcx, [rcx+8]
0x180007727  test    rcx, rcx
0x18000772a  jz      short loc_180007739
0x18000772c  mov     rax, [rcx]
0x18000772f  mov     rax, [rax+10h]
0x180007733  call    cs:__guard_dispatch_icall_fptr
0x180007739  and     qword ptr [rbx+8], 0
0x18000773e  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180007745  mov     [rbx], rax
0x180007748  add     rsp, 20h
0x18000774c  pop     rbx
0x18000774d  retn
```
