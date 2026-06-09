# CDomNode::RemoveChildNode(IDomNode *)

- ea: `0x180024fd0`
- end: `0x180025088`
- name: `?RemoveChildNode@CDomNode@@UEAAJPEAUIDomNode@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(CDomNode *__hidden this, struct IDomNode *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800110bc`
- `0x180024308`
- `0x180024fd0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CDomNode::RemoveChildNode(CDomNode *this, struct IUnknown *a2)
{
  int v3; // edi
  struct IUnknown **i; // rbx
  struct IUnknown **v5; // r15
  struct IUnknown **j; // r14

  if ( a2 )
  {
    for ( i = (struct IUnknown **)*((_QWORD *)this + 1); ; ++i )
    {
      if ( i == *((struct IUnknown ***)this + 2) )
        return (unsigned int)-2147023728;
      if ( *i == a2 )
        break;
    }
    try
    {
      v3 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))a2->lpVtbl[6].AddRef)(a2, 0);
      if ( v3 >= 0 )
      {
        v5 = (struct IUnknown **)*((_QWORD *)this + 2);
        for ( j = i + 1; j != v5; ++j )
        {
          if ( *i != *j )
            ATL::AtlComPtrAssign(i, *j);
          ++i;
        }
        wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)(*((_QWORD *)this + 2) - 8LL));
        *((_QWORD *)this + 2) -= 8LL;
      }
    }
    catch ( std::bad_alloc )
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180024fd0  mov     [rsp+arg_0], rbx
0x180024fd5  mov     [rsp+arg_10], rsi
0x180024fda  push    rdi
0x180024fdb  push    r14
0x180024fdd  push    r15
0x180024fdf  sub     rsp, 20h
0x180024fe3  mov     r8, rdx
0x180024fe6  mov     rsi, rcx
0x180024fe9  test    rdx, rdx
0x180024fec  jnz     short loc_180024FF5
0x180024fee  mov     edi, 80070057h
0x180024ff3  jmp     short loc_180025066
0x180024ff5  mov     rbx, [rcx+8]
0x180024ff9  cmp     rbx, [rcx+10h]
0x180024ffd  jnz     short loc_180025006
0x180024fff  mov     edi, 80070490h
0x180025004  jmp     short loc_180025066
0x180025006  cmp     [rbx], r8
0x180025009  jnz     short loc_18002507D
0x18002500b  mov     rax, [rdx]
0x18002500e  xor     edx, edx
0x180025010  mov     rcx, r8
0x180025013  mov     rax, [rax+98h]
0x18002501a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002501f  mov     edi, eax
0x180025021  test    eax, eax
0x180025023  jns     short loc_180025027
0x180025025  jmp     short loc_180025066
0x180025027  mov     r15, [rsi+10h]
0x18002502b  lea     r14, [rbx+8]
0x18002502f  jmp     short loc_180025049
0x180025031  mov     rdx, [r14]; struct IUnknown *
0x180025034  cmp     [rbx], rdx
0x180025037  jz      short loc_180025041
0x180025039  mov     rcx, rbx; struct IUnknown **
0x18002503c  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180025041  add     rbx, 8
0x180025045  add     r14, 8
0x180025049  cmp     r14, r15
0x18002504c  jnz     short loc_180025031
0x18002504e  mov     rcx, [rsi+10h]
0x180025052  sub     rcx, 8
0x180025056  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002505b  add     qword ptr [rsi+10h], 0FFFFFFFFFFFFFFF8h
0x180025060  jmp     short loc_180025066
0x180025062  mov     edi, [rsp+38h+arg_8]
0x180025066  mov     eax, edi
0x180025068  mov     rbx, [rsp+38h+arg_0]
0x18002506d  mov     rsi, [rsp+38h+arg_10]
0x180025072  add     rsp, 20h
0x180025076  pop     r15
0x180025078  pop     r14
0x18002507a  pop     rdi
0x18002507b  retn
0x18002507d  add     rbx, 8
0x180025081  jmp     loc_180024FF9
```
