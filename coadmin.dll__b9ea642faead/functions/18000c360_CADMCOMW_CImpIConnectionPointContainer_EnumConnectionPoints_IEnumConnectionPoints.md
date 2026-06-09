# CADMCOMW::CImpIConnectionPointContainer::EnumConnectionPoints(IEnumConnectionPoints * *)

- ea: `0x18000c360`
- end: `0x18000c431`
- name: `?EnumConnectionPoints@CImpIConnectionPointContainer@CADMCOMW@@UEAAJPEAPEAUIEnumConnectionPoints@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(CADMCOMW::CImpIConnectionPointContainer *__hidden this, struct IEnumConnectionPoints **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001064`
- `0x18000c360`
- `0x18000cd48`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CImpIConnectionPointContainer::EnumConnectionPoints(
        CADMCOMW::CImpIConnectionPointContainer *this,
        struct IEnumConnectionPoints **a2)
{
  int v4; // edi
  _QWORD *v5; // rbx
  struct IConnectionPoint *v7; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    v7 = (struct IConnectionPoint *)(*((_QWORD *)this + 1) + 840LL);
    v5 = operator new(0x28u);
    if ( v5 )
    {
      v5[2] = this;
      *v5 = &COEnumConnectionPoints::`vftable';
      *((_DWORD *)v5 + 2) = 1;
      v5[3] = 0;
      v5[4] = 0;
      v4 = COEnumConnectionPoints::Init((COEnumConnectionPoints *)v5, 1u, &v7, 0);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IEnumConnectionPoints **))*v5)(
               v5,
               &IID_IEnumConnectionPoints,
               a2);
        if ( v4 >= 0 )
          v4 = 0;
      }
      (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c360  mov     [rsp+arg_0], rbx
0x18000c365  mov     [rsp+arg_10], rsi
0x18000c36a  push    rdi
0x18000c36b  sub     rsp, 20h
0x18000c36f  mov     rsi, rdx
0x18000c372  mov     rdi, rcx
0x18000c375  test    rdx, rdx
0x18000c378  jnz     short loc_18000C384
0x18000c37a  mov     edi, 80070057h
0x18000c37f  jmp     loc_18000C41F
0x18000c384  mov     qword ptr [rdx], 0
0x18000c38b  mov     rax, [rcx+8]
0x18000c38f  mov     ecx, 28h ; '('; Size
0x18000c394  add     rax, 348h
0x18000c39a  mov     [rsp+28h+arg_8], rax
0x18000c39f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c3a4  mov     rbx, rax
0x18000c3a7  test    rax, rax
0x18000c3aa  jz      short loc_18000C41A
0x18000c3ac  lea     rax, ??_7COEnumConnectionPoints@@6B@; const COEnumConnectionPoints::`vftable'
0x18000c3b3  mov     [rbx+10h], rdi
0x18000c3b7  mov     edx, 1; unsigned int
0x18000c3bc  mov     [rbx], rax
0x18000c3bf  xor     r9d, r9d; unsigned int
0x18000c3c2  mov     [rbx+8], edx
0x18000c3c5  lea     r8, [rsp+28h+arg_8]; struct IConnectionPoint **
0x18000c3ca  mov     qword ptr [rbx+18h], 0
0x18000c3d2  mov     rcx, rbx; this
0x18000c3d5  mov     qword ptr [rbx+20h], 0
0x18000c3dd  call    ?Init@COEnumConnectionPoints@@QEAAJKPEAPEAUIConnectionPoint@@K@Z; COEnumConnectionPoints::Init(ulong,IConnectionPoint * *,ulong)
0x18000c3e2  mov     edi, eax
0x18000c3e4  test    eax, eax
0x18000c3e6  js      short loc_18000C409
0x18000c3e8  mov     rax, [rbx]
0x18000c3eb  lea     rdx, IID_IEnumConnectionPoints
0x18000c3f2  mov     r8, rsi
0x18000c3f5  mov     rcx, rbx
0x18000c3f8  mov     rax, [rax]
0x18000c3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c400  mov     edi, eax
0x18000c402  xor     eax, eax
0x18000c404  test    edi, edi
0x18000c406  cmovns  edi, eax
0x18000c409  mov     rax, [rbx]
0x18000c40c  mov     rcx, rbx
0x18000c40f  mov     rax, [rax+10h]
0x18000c413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c418  jmp     short loc_18000C41F
0x18000c41a  mov     edi, 8007000Eh
0x18000c41f  mov     rbx, [rsp+28h+arg_0]
0x18000c424  mov     eax, edi
0x18000c426  mov     rsi, [rsp+28h+arg_10]
0x18000c42b  add     rsp, 20h
0x18000c42f  pop     rdi
0x18000c430  retn
```
