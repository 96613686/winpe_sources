# CHandlerBase::PostProcess(long,_MVProvisionData *,long)

- ea: `0x18000ef20`
- end: `0x18000ef58`
- name: `?PostProcess@CHandlerBase@@UEAAJJPEAU_MVProvisionData@@J@Z`
- size: `56`
- prototype: `__int64 __fastcall(CHandlerBase *this, __int64, struct _MVProvisionData *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076a4`
- `0x18000ef20`

## string_xrefs

- `0x18000ef33`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHandlerBase::PostProcess(CHandlerBase *this, __int64 a2, struct _MVProvisionData *a3, int a4)
{
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a4 || a3 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4B,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
    (const char *)0x80004003LL,
    v5);
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000ef20  sub     rsp, 28h
0x18000ef24  test    r9d, r9d
0x18000ef27  jz      short loc_18000EF51
0x18000ef29  test    r8, r8
0x18000ef2c  jnz     short loc_18000EF51
0x18000ef2e  mov     rcx, [rsp+28h]; this
0x18000ef33  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000ef3a  mov     r9d, 80004003h; char *
0x18000ef40  mov     edx, 4Bh ; 'K'; void *
0x18000ef45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef4a  mov     eax, 80004003h
0x18000ef4f  jmp     short loc_18000EF53
0x18000ef51  xor     eax, eax
0x18000ef53  add     rsp, 28h
0x18000ef57  retn
```
