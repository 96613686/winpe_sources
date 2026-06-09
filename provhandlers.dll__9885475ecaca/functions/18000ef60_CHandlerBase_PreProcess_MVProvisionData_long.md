# CHandlerBase::PreProcess(_MVProvisionData *,long)

- ea: `0x18000ef60`
- end: `0x18000ef98`
- name: `?PreProcess@CHandlerBase@@UEAAJPEAU_MVProvisionData@@J@Z`
- size: `56`
- prototype: `__int64 __fastcall(CHandlerBase *__hidden this, struct _MVProvisionData *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076a4`
- `0x18000ef60`

## string_xrefs

- `0x18000ef73`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHandlerBase::PreProcess(CHandlerBase *this, struct _MVProvisionData *a2, int a3)
{
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a3 || a2 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x43,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
    (const char *)0x80004003LL,
    v4);
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000ef60  sub     rsp, 28h
0x18000ef64  test    r8d, r8d
0x18000ef67  jz      short loc_18000EF91
0x18000ef69  test    rdx, rdx
0x18000ef6c  jnz     short loc_18000EF91
0x18000ef6e  mov     rcx, [rsp+28h]; this
0x18000ef73  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000ef7a  mov     r9d, 80004003h; char *
0x18000ef80  mov     edx, 43h ; 'C'; void *
0x18000ef85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef8a  mov     eax, 80004003h
0x18000ef8f  jmp     short loc_18000EF93
0x18000ef91  xor     eax, eax
0x18000ef93  add     rsp, 28h
0x18000ef97  retn
```
