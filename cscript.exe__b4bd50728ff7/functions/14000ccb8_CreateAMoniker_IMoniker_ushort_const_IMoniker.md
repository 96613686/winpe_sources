# CreateAMoniker(IMoniker *,ushort const *,IMoniker * *)

- ea: `0x14000ccb8`
- end: `0x14000ccf1`
- name: `?CreateAMoniker@@YAJPEAUIMoniker@@PEBGPEAPEAU1@@Z`
- size: `57`
- prototype: `int(struct IMoniker *, const unsigned __int16 *, struct IMoniker **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400014b0`
- `0x140012360`

## callees

- `0x14000ccb8`
- `0x14000ccf8`

## import_xrefs

- `ole32!CreateFileMoniker` at `0x14000cce0`
- `ole32!CreateFileMoniker` at `0x14000cce0`

## pseudocode

```c
int __fastcall CreateAMoniker(struct IMoniker *a1, const unsigned __int16 *a2, struct IMoniker **a3)
{
  int result; // eax

  if ( byte_14001E9D0 )
    return CreateFileMoniker(a2, a3);
  result = DynCreateURLMoniker(a1, a2, a3);
  if ( result < 0 )
    return CreateFileMoniker(a2, a3);
  return result;
}

```

## disassembly

```asm
0x14000ccb8  mov     [rsp+arg_0], rbx
0x14000ccbd  push    rdi
0x14000ccbe  sub     rsp, 20h
0x14000ccc2  cmp     cs:byte_14001E9D0, 0
0x14000ccc9  mov     rbx, r8
0x14000cccc  mov     rdi, rdx
0x14000cccf  jnz     short loc_14000CCDA
0x14000ccd1  call    ?DynCreateURLMoniker@@YAJPEAUIMoniker@@PEBGPEAPEAU1@@Z; DynCreateURLMoniker(IMoniker *,ushort const *,IMoniker * *)
0x14000ccd6  test    eax, eax
0x14000ccd8  jns     short loc_14000CCE6
0x14000ccda  mov     rdx, rbx; ppmk
0x14000ccdd  mov     rcx, rdi; lpszPathName
0x14000cce0  call    cs:__imp_CreateFileMoniker
0x14000cce6  mov     rbx, [rsp+28h+arg_0]
0x14000cceb  add     rsp, 20h
0x14000ccef  pop     rdi
0x14000ccf0  retn
```
