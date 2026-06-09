# ATL::CComTypeInfoHolder::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18001bc44`
- end: `0x18001bcae`
- name: `?GetTypeInfo@CComTypeInfoHolder@ATL@@QEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, unsigned int, unsigned int, struct ITypeInfo **)`
- caller_count: `23`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a190`
- `0x18001bbb0`
- `0x18001bbd0`
- `0x18001bbf0`
- `0x18001bc10`
- `0x18001bc30`
- `0x180026ca0`
- `0x180026e10`
- `0x180028760`
- `0x180028800`
- `0x18002abc0`
- `0x18002e4f0`
- `0x18002e5d0`
- `0x18002e5f0`
- `0x1800337b0`
- `0x180033870`
- `0x180033890`
- `0x180037ed0`
- `0x1800380c0`
- `0x1800380e0`
- `0x18003da50`
- `0x18003da70`
- `0x180044b00`

## callees

- `0x18001b910`
- `0x18001bc44`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTypeInfo(
        ATL::CComTypeInfoHolder *this,
        int a2,
        LCID a3,
        struct ITypeInfo **a4)
{
  unsigned int TI; // ecx
  __int64 v8; // rdx

  if ( a2 )
    return 2147614731LL;
  if ( a4 )
  {
    TI = 0;
    if ( !*((_QWORD *)this + 3) )
      TI = ATL::CComTypeInfoHolder::GetTI(this, a3);
    *a4 = (struct ITypeInfo *)*((_QWORD *)this + 3);
    v8 = *((_QWORD *)this + 3);
    if ( v8 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(*((_QWORD *)this + 3));
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return TI;
}

```

## disassembly

```asm
0x18001bc44  mov     [rsp+arg_0], rbx
0x18001bc49  push    rdi
0x18001bc4a  sub     rsp, 20h
0x18001bc4e  mov     rdi, r9
0x18001bc51  mov     rbx, rcx
0x18001bc54  test    edx, edx
0x18001bc56  jz      short loc_18001BC5F
0x18001bc58  mov     eax, 8002000Bh
0x18001bc5d  jmp     short loc_18001BCA3
0x18001bc5f  test    rdi, rdi
0x18001bc62  jnz     short loc_18001BC6B
0x18001bc64  mov     ecx, 80004003h
0x18001bc69  jmp     short loc_18001BCA1
0x18001bc6b  xor     ecx, ecx
0x18001bc6d  cmp     [rbx+18h], rcx
0x18001bc71  jnz     short loc_18001BC80
0x18001bc73  mov     edx, r8d; lcid
0x18001bc76  mov     rcx, rbx; this
0x18001bc79  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18001bc7e  mov     ecx, eax
0x18001bc80  mov     rax, [rbx+18h]
0x18001bc84  mov     [rdi], rax
0x18001bc87  mov     rdx, [rbx+18h]
0x18001bc8b  test    rdx, rdx
0x18001bc8e  jz      short loc_18001BCA1
0x18001bc90  mov     rax, [rdx]
0x18001bc93  mov     rcx, rdx
0x18001bc96  mov     rax, [rax+8]
0x18001bc9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc9f  xor     ecx, ecx
0x18001bca1  mov     eax, ecx
0x18001bca3  mov     rbx, [rsp+28h+arg_0]
0x18001bca8  add     rsp, 20h
0x18001bcac  pop     rdi
0x18001bcad  retn
```
