# Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)

- ea: `0x140012a00`
- end: `0x140012a23`
- name: `?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ`
- size: `35`
- prototype: `void __fastcall(Windows::Detail **, HINSTANCE)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x140013288`
- `0x1400158f0`
- `0x140024604`
- `0x140024980`
- `0x1400249e0`
- `0x140024bd8`
- `0x140024c30`
- `0x140025660`
- `0x140025964`
- `0x140025fb0`
- `0x140027b78`
- `0x140029ee0`

## callees

- `0x140012a00`
- `0x140012ae0`

## pseudocode

```c
void __fastcall Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(
        Windows::Detail **a1,
        HINSTANCE a2)
{
  Windows::Detail *v3; // rcx

  v3 = *a1;
  if ( v3 )
  {
    Windows::Detail::CloseWithFreeLibrary(v3, a2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x140012a00  push    rbx
0x140012a02  sub     rsp, 20h
0x140012a06  mov     rbx, rcx
0x140012a09  mov     rcx, [rcx]; this
0x140012a0c  test    rcx, rcx
0x140012a0f  jz      short loc_140012A1D
0x140012a11  call    ?CloseWithFreeLibrary@Detail@Windows@@YAXPEAUHINSTANCE__@@@Z; Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)
0x140012a16  mov     qword ptr [rbx], 0
0x140012a1d  add     rsp, 20h
0x140012a21  pop     rbx
0x140012a22  retn
```
