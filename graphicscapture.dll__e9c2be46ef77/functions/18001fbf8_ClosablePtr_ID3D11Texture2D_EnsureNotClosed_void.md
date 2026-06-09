# ClosablePtr<ID3D11Texture2D>::EnsureNotClosed(void)

- ea: `0x18001fbf8`
- end: `0x18001fc44`
- name: `?EnsureNotClosed@?$ClosablePtr@UID3D11Texture2D@@@@QEBAAEBU?$com_ptr@UID3D11Texture2D@@@winrt@@XZ`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180020060`
- `0x180021cb0`

## callees

- `0x1800022f2`
- `0x180003330`
- `0x1800033c0`
- `0x1800058c4`
- `0x18001fbf8`

## pseudocode

```c
_QWORD *__fastcall ClosablePtr<ID3D11Texture2D>::EnsureNotClosed(_QWORD *a1)
{
  unsigned int *v2; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v4[32]; // [rsp+38h] [rbp-20h] BYREF
  char v5; // [rsp+60h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    winrt::impl::slim_source_location::current(v4);
    v2 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v5, -2147483629);
    winrt::hresult_error::hresult_error(pExceptionObject, *v2);
    throw (winrt::hresult_error *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x18001fbf8  sub     rsp, 58h
0x18001fbfc  cmp     qword ptr [rcx], 0
0x18001fc00  jz      short loc_18001FC0A
0x18001fc02  mov     rax, rcx
0x18001fc05  add     rsp, 58h
0x18001fc09  retn
0x18001fc0a  lea     rcx, [rsp+58h+var_20]
0x18001fc0f  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001fc14  mov     edx, 80000013h; int
0x18001fc19  lea     rcx, [rsp+58h+arg_0]; this
0x18001fc1e  mov     r8, rax
0x18001fc21  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18001fc26  lea     rcx, [rsp+58h+pExceptionObject]
0x18001fc2b  mov     edx, [rax]
0x18001fc2d  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001fc32  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18001fc39  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001fc3e  call    _CxxThrowException_0
```
