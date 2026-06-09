# __ExceptionPtrCopy(void *,void const *)

- ea: `0x180017530`
- end: `0x18001755e`
- name: `?__ExceptionPtrCopy@@YAXPEAXPEBX@Z`
- size: `46`
- prototype: `void __fastcall(void *, const void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800175d0`

## callees

- `0x1800184f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __ExceptionPtrCopy(_QWORD *a1, _QWORD *a2)
{
  *a1 = 0;
  a1[1] = 0;
  std::_Ptr_base<__ExceptionPtr>::_Reset(a1, *a2, a2[1]);
}

```

## disassembly

```asm
0x180017530  sub     rsp, 38h
0x180017534  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001753d  mov     qword ptr [rcx], 0
0x180017544  mov     qword ptr [rcx+8], 0
0x18001754c  mov     r8, [rdx+8]
0x180017550  mov     rdx, [rdx]
0x180017553  call    ?_Reset@?$_Ptr_base@V__ExceptionPtr@@@std@@QEAAXPEAV__ExceptionPtr@@PEAV_Ref_count_base@2@@Z; std::_Ptr_base<__ExceptionPtr>::_Reset(__ExceptionPtr *,std::_Ref_count_base *)
0x180017558  nop
0x180017559  add     rsp, 38h
0x18001755d  retn
```
