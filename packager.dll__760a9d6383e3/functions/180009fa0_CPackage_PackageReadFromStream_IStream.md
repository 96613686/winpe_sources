# CPackage::PackageReadFromStream(IStream *)

- ea: `0x180009fa0`
- end: `0x18000a06d`
- name: `?PackageReadFromStream@CPackage@@IEAAJPEAUIStream@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006900`

## callees

- `0x1800074e0`
- `0x180007cf8`
- `0x180008c8c`
- `0x180009fa0`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CPackage::PackageReadFromStream(CPackage *this, struct IStream *a2)
{
  int v4; // ecx
  int v5; // ecx
  unsigned __int16 v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  v8 = 0;
  if ( ((int (__fastcall *)(struct IStream *, int *, __int64))a2->lpVtbl->Read)(a2, &v8, 4) >= 0 )
  {
    ((void (__fastcall *)(struct IStream *, unsigned __int16 *, __int64))a2->lpVtbl->Read)(a2, &v7, 2);
    if ( v7 != 2 || (int)CPackage::IconReadFromStream(this, a2) >= 0 )
    {
      ((void (__fastcall *)(struct IStream *, unsigned __int16 *, __int64, _QWORD))a2->lpVtbl->Read)(a2, &v7, 2, 0);
      v4 = v7;
      *((_DWORD *)this + 26) = v7;
      v5 = v4 - 1;
      if ( !v5 )
        return CPackage::CmlReadFromStream((void **)this, a2);
      if ( v5 == 2 )
        return CPackage::EmbedReadFromStream(this, a2);
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180009fa0  mov     [rsp+arg_0], rbx
0x180009fa5  mov     [rsp+arg_18], rsi
0x180009faa  push    rdi
0x180009fab  sub     rsp, 30h
0x180009faf  xor     eax, eax
0x180009fb1  mov     rbx, rdx
0x180009fb4  mov     [rsp+38h+arg_8], ax
0x180009fb9  xor     r9d, r9d
0x180009fbc  mov     [rsp+38h+arg_10], eax
0x180009fc0  mov     rdi, rcx
0x180009fc3  mov     rax, [rdx]
0x180009fc6  mov     rcx, rbx
0x180009fc9  lea     rdx, [rsp+38h+arg_10]
0x180009fce  lea     r8d, [r9+4]
0x180009fd2  mov     rax, [rax+18h]
0x180009fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fdb  test    eax, eax
0x180009fdd  js      short loc_18000A058
0x180009fdf  mov     rax, [rbx]
0x180009fe2  lea     rdx, [rsp+38h+arg_8]
0x180009fe7  xor     r9d, r9d
0x180009fea  mov     rcx, rbx
0x180009fed  mov     rax, [rax+18h]
0x180009ff1  lea     esi, [r9+2]
0x180009ff5  mov     r8d, esi
0x180009ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ffd  cmp     [rsp+38h+arg_8], si
0x18000a002  jnz     short loc_18000A013
0x18000a004  mov     rdx, rbx; struct IStream *
0x18000a007  mov     rcx, rdi; this
0x18000a00a  call    ?IconReadFromStream@CPackage@@IEAAJPEAUIStream@@@Z; CPackage::IconReadFromStream(IStream *)
0x18000a00f  test    eax, eax
0x18000a011  js      short loc_18000A058
0x18000a013  mov     rax, [rbx]
0x18000a016  lea     rdx, [rsp+38h+arg_8]
0x18000a01b  xor     r9d, r9d
0x18000a01e  mov     r8d, esi
0x18000a021  mov     rcx, rbx
0x18000a024  mov     rax, [rax+18h]
0x18000a028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a02d  movzx   ecx, [rsp+38h+arg_8]
0x18000a032  mov     [rdi+68h], ecx
0x18000a035  sub     ecx, 1
0x18000a038  jz      short loc_18000A04B
0x18000a03a  cmp     ecx, esi
0x18000a03c  jnz     short loc_18000A058
0x18000a03e  mov     rdx, rbx; struct IStream *
0x18000a041  mov     rcx, rdi; this
0x18000a044  call    ?EmbedReadFromStream@CPackage@@IEAAJPEAUIStream@@@Z; CPackage::EmbedReadFromStream(IStream *)
0x18000a049  jmp     short loc_18000A05D
0x18000a04b  mov     rdx, rbx; struct IStream *
0x18000a04e  mov     rcx, rdi; this
0x18000a051  call    ?CmlReadFromStream@CPackage@@IEAAJPEAUIStream@@@Z; CPackage::CmlReadFromStream(IStream *)
0x18000a056  jmp     short loc_18000A05D
0x18000a058  mov     eax, 80004005h
0x18000a05d  mov     rbx, [rsp+38h+arg_0]
0x18000a062  mov     rsi, [rsp+38h+arg_18]
0x18000a067  add     rsp, 30h
0x18000a06b  pop     rdi
0x18000a06c  retn
```
