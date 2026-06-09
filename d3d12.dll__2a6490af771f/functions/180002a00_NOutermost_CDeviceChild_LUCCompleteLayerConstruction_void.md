# NOutermost::CDeviceChild::LUCCompleteLayerConstruction(void)

- ea: `0x180002a00`
- end: `0x180002a4f`
- name: `?LUCCompleteLayerConstruction@CDeviceChild@NOutermost@@UEAAJXZ`
- size: `79`
- prototype: `__int64 __fastcall(NOutermost::CDeviceChild *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800029f0`

## callees

- `0x180002a00`
- `0x18000be84`
- `0x180015010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NOutermost::CDeviceChild::LUCCompleteLayerConstruction(NOutermost::CDeviceChild *this)
{
  __int64 v1; // rcx
  int v2; // eax
  __int64 result; // rax
  _com_error *v4; // [rsp+20h] [rbp-38h] BYREF
  void **pExceptionObject; // [rsp+28h] [rbp-30h] BYREF
  int v6; // [rsp+30h] [rbp-28h]
  __int128 v7; // [rsp+38h] [rbp-20h]

  v1 = *((_QWORD *)this + 3);
  try
  {
    v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 64LL))(v1);
    if ( v2 < 0 )
    {
      pExceptionObject = &_com_error::`vftable';
      v6 = v2;
      v7 = 0;
      throw (_com_error *)&pExceptionObject;
    }
    result = 0;
  }
  catch ( _com_error *v4 )
  {
    return *((unsigned int *)v4 + 2);
  }
  return result;
}

```

## disassembly

```asm
0x180002a00  sub     rsp, 58h
0x180002a04  mov     rcx, [rcx+18h]
0x180002a08  mov     rax, [rcx]
0x180002a0b  mov     rax, [rax+40h]
0x180002a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a14  test    eax, eax
0x180002a16  jns     short loc_180002A42
0x180002a18  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180002a1f  mov     [rsp+58h+pExceptionObject], rcx
0x180002a24  mov     [rsp+58h+var_28], eax
0x180002a28  xorps   xmm0, xmm0
0x180002a2b  movdqu  [rsp+58h+var_20], xmm0
0x180002a31  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180002a38  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180002a3d  call    _CxxThrowException_0
0x180002a42  xor     eax, eax
0x180002a44  add     rsp, 58h
0x180002a48  retn
0x180002a49  mov     eax, [rsp+58h+arg_8]
0x180002a4d  jmp     short loc_180002A44
```
