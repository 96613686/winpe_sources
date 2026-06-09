# CHandlerBase::Initialize(IMVEngine *,int *)

- ea: `0x18000ee90`
- end: `0x18000ef14`
- name: `?Initialize@CHandlerBase@@UEAAJPEAUIMVEngine@@PEAH@Z`
- size: `132`
- prototype: `__int64 __fastcall(CHandlerBase *this, struct IMVEngine *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014550`
- `0x180030720`

## callees

- `0x1800076a4`
- `0x18000ee90`
- `0x18003f010`

## string_xrefs

- `0x18000eead`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHandlerBase::Initialize(CHandlerBase *this, struct IMVEngine *a2, int *a3)
{
  __int64 v5; // rdx
  __int64 v7; // rcx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 )
  {
    v5 = 27;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
      (const char *)0x80004003LL,
      v8);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v5 = 28;
    goto LABEL_3;
  }
  *a3 = 0;
  if ( *((struct IMVEngine **)this + 2) != a2 )
  {
    (*(void (__fastcall **)(struct IMVEngine *))(*(_QWORD *)a2 + 8LL))(a2);
    v7 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = a2;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ee90  mov     [rsp+arg_0], rbx
0x18000ee95  push    rdi; int
0x18000ee96  sub     rsp, 20h
0x18000ee9a  mov     rbx, rdx
0x18000ee9d  mov     rdi, rcx
0x18000eea0  test    rdx, rdx
0x18000eea3  jnz     short loc_18000EEC5
0x18000eea5  lea     edx, [rbx+1Bh]; void *
0x18000eea8  mov     ebx, 80004003h
0x18000eead  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000eeb4  mov     r9d, ebx; char *
0x18000eeb7  mov     rcx, [rsp+28h]; this
0x18000eebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eec1  mov     eax, ebx
0x18000eec3  jmp     short loc_18000EF09
0x18000eec5  test    r8, r8
0x18000eec8  jnz     short loc_18000EED0
0x18000eeca  lea     edx, [r8+1Ch]
0x18000eece  jmp     short loc_18000EEA8
0x18000eed0  mov     dword ptr [r8], 0
0x18000eed7  cmp     [rcx+10h], rbx
0x18000eedb  jz      short loc_18000EF07
0x18000eedd  mov     rax, [rdx]
0x18000eee0  mov     rcx, rbx
0x18000eee3  mov     rax, [rax+8]
0x18000eee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeec  nop
0x18000eeed  mov     rcx, [rdi+10h]
0x18000eef1  mov     [rdi+10h], rbx
0x18000eef5  test    rcx, rcx
0x18000eef8  jz      short loc_18000EF07
0x18000eefa  mov     rax, [rcx]
0x18000eefd  mov     rax, [rax+10h]
0x18000ef01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef06  nop
0x18000ef07  xor     eax, eax
0x18000ef09  mov     rbx, [rsp+28h+arg_0]
0x18000ef0e  add     rsp, 20h
0x18000ef12  pop     rdi
0x18000ef13  retn
```
