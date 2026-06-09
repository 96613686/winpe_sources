# CDSLink::GetLatencyClock(IReferenceClock * *)

- ea: `0x18000f9e0`
- end: `0x18000fa77`
- name: `?GetLatencyClock@CDSLink@@UEAAJPEAPEAUIReferenceClock@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(CDSLink *__hidden this, struct IReferenceClock **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f9e0`
- `0x1800148c5`

## pseudocode

```c
__int64 __fastcall CDSLink::GetLatencyClock(CDSLink *this, struct IReferenceClock **a2)
{
  __int64 v5; // rax

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  if ( memcmp_0(&IID_IReferenceClock, &IID_IReferenceClock, 0x10u)
    && memcmp_0(&IID_IReferenceClock, &IID_IUnknown, 0x10u) )
  {
    return 2147500034LL;
  }
  v5 = *((_QWORD *)this + 6);
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 80));
  *a2 = (struct IReferenceClock *)((char *)this + 32);
  return 0;
}

```

## disassembly

```asm
0x18000f9e0  mov     [rsp+arg_0], rbx
0x18000f9e5  push    rdi
0x18000f9e6  sub     rsp, 20h
0x18000f9ea  mov     rbx, rdx
0x18000f9ed  mov     rdi, rcx
0x18000f9f0  test    rdx, rdx
0x18000f9f3  jnz     short loc_18000FA05
0x18000f9f5  mov     eax, 80004003h
0x18000f9fa  mov     rbx, [rsp+28h+arg_0]
0x18000f9ff  add     rsp, 20h
0x18000fa03  pop     rdi
0x18000fa04  retn
0x18000fa05  mov     qword ptr [rdx], 0
0x18000fa0c  lea     rcx, IID_IReferenceClock; Buf1
0x18000fa13  lea     rdx, IID_IReferenceClock; Buf2
0x18000fa1a  mov     r8d, 10h; Size
0x18000fa20  call    memcmp_0
0x18000fa25  test    eax, eax
0x18000fa27  jz      short loc_18000FA56
0x18000fa29  mov     r8d, 10h; Size
0x18000fa2f  lea     rdx, IID_IUnknown; Buf2
0x18000fa36  lea     rcx, IID_IReferenceClock; Buf1
0x18000fa3d  call    memcmp_0
0x18000fa42  test    eax, eax
0x18000fa44  jz      short loc_18000FA56
0x18000fa46  mov     eax, 80004002h
0x18000fa4b  mov     rbx, [rsp+28h+arg_0]
0x18000fa50  add     rsp, 20h
0x18000fa54  pop     rdi
0x18000fa55  retn
0x18000fa56  mov     rax, [rdi+30h]
0x18000fa5a  lea     rcx, [rdi+20h]
0x18000fa5e  test    rax, rax
0x18000fa61  jz      short loc_18000FA67
0x18000fa63  lock inc dword ptr [rax+50h]
0x18000fa67  mov     [rbx], rcx
0x18000fa6a  xor     eax, eax
0x18000fa6c  mov     rbx, [rsp+28h+arg_0]
0x18000fa71  add     rsp, 20h
0x18000fa75  pop     rdi
0x18000fa76  retn
```
