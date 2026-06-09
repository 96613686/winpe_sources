# CDirectMusicSynthSinkFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000e7c0`
- end: `0x18000e888`
- name: `?CreateInstance@CDirectMusicSynthSinkFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `200`
- prototype: `int(CDirectMusicSynthSinkFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000e4d0`
- `0x18000e7c0`
- `0x18000eea0`
- `0x18000ffe0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000e815`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000e815`

## pseudocode

```c
__int64 __fastcall CDirectMusicSynthSinkFactory::CreateInstance(
        CDirectMusicSynthSinkFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  CDSLink *v7; // rax
  CDSLink *v8; // rbx
  int Interface; // edi

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  try
  {
    v7 = (CDSLink *)malloc(0xE8u);
    if ( v7 )
      v8 = CDSLink::CDSLink(v7);
    else
      v8 = 0;
  }
  catch ( ... )
  {
    return 2147942414LL;
  }
  if ( !v8 )
    return 2147942414LL;
  *((_QWORD *)v8 + 3) = 0;
  *((_QWORD *)v8 + 6) = v8;
  Interface = CDSLink::QueryInterface(v8, a3, a4);
  if ( Interface < 0 )
    CDSLink::`scalar deleting destructor'(v8);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18000e7c0  mov     [rsp+arg_0], rbx
0x18000e7c5  mov     [rsp+arg_8], rsi
0x18000e7ca  push    rdi
0x18000e7cb  sub     rsp, 30h
0x18000e7cf  mov     rdi, r9
0x18000e7d2  mov     rsi, r8
0x18000e7d5  test    r9, r9
0x18000e7d8  jnz     short loc_18000E7EF
0x18000e7da  mov     eax, 80004003h
0x18000e7df  mov     rbx, [rsp+38h+arg_0]
0x18000e7e4  mov     rsi, [rsp+38h+arg_8]
0x18000e7e9  add     rsp, 30h
0x18000e7ed  pop     rdi
0x18000e7ee  retn
0x18000e7ef  mov     qword ptr [r9], 0
0x18000e7f6  test    rdx, rdx
0x18000e7f9  jz      short loc_18000E810
0x18000e7fb  mov     eax, 80040110h
0x18000e800  mov     rbx, [rsp+38h+arg_0]
0x18000e805  mov     rsi, [rsp+38h+arg_8]
0x18000e80a  add     rsp, 30h
0x18000e80e  pop     rdi
0x18000e80f  retn
0x18000e810  mov     ecx, 0E8h; Size
0x18000e815  call    cs:__imp_malloc
0x18000e81b  test    rax, rax
0x18000e81e  jz      short loc_18000E82D
0x18000e820  mov     rcx, rax; this
0x18000e823  call    ??0CDSLink@@QEAA@XZ; CDSLink::CDSLink(void)
0x18000e828  mov     rbx, rax
0x18000e82b  jmp     short loc_18000E82F
0x18000e82d  xor     ebx, ebx
0x18000e82f  mov     [rsp+38h+var_18], rbx
0x18000e834  test    rbx, rbx
0x18000e837  jz      short loc_18000E873
0x18000e839  mov     qword ptr [rbx+18h], 0
0x18000e841  mov     [rbx+30h], rbx
0x18000e845  mov     r8, rdi; void **
0x18000e848  mov     rdx, rsi; struct _GUID *
0x18000e84b  mov     rcx, rbx; this
0x18000e84e  call    ?QueryInterface@CDSLink@@UEAAJAEBU_GUID@@PEAPEAX@Z; CDSLink::QueryInterface(_GUID const &,void * *)
0x18000e853  mov     edi, eax
0x18000e855  test    eax, eax
0x18000e857  jns     short loc_18000E861
0x18000e859  mov     rcx, rbx; this
0x18000e85c  call    ??_GCDSLink@@QEAAPEAXI@Z; CDSLink::`scalar deleting destructor'(uint)
0x18000e861  mov     eax, edi
0x18000e863  mov     rbx, [rsp+38h+arg_0]
0x18000e868  mov     rsi, [rsp+38h+arg_8]
0x18000e86d  add     rsp, 30h
0x18000e871  pop     rdi
0x18000e872  retn
0x18000e873  mov     eax, 8007000Eh
0x18000e878  mov     rbx, [rsp+38h+arg_0]
0x18000e87d  mov     rsi, [rsp+38h+arg_8]
0x18000e882  add     rsp, 30h
0x18000e886  pop     rdi
0x18000e887  retn
```
