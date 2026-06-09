# ThrowExceptionIfFailed(long,ushort const *,ushort const *,uint,uint)

- ea: `0x180024a00`
- end: `0x180024a40`
- name: `?ThrowExceptionIfFailed@@YAXJPEBG0II@Z`
- size: `64`
- prototype: `void __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180023e00`

## callees

- `0x180024a00`
- `0x18002df9b`

## string_xrefs

- `0x180024a0f`: `inetsrv\iis\mb\config\src\core\schemagen\tmbschemageneration.cpp`

## pseudocode

```c
void __fastcall ThrowExceptionIfFailed(int a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  int v4; // [rsp+20h] [rbp-28h] BYREF
  const unsigned __int16 *v5; // [rsp+28h] [rbp-20h]
  const unsigned __int16 *v6; // [rsp+30h] [rbp-18h]
  int v7; // [rsp+38h] [rbp-10h]
  int v8; // [rsp+3Ch] [rbp-Ch]

  if ( a1 < 0 )
  {
    v4 = a1;
    v5 = L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmbschemageneration.cpp";
    v6 = a3;
    v7 = a4;
    v8 = 0;
    throw (TException *)&v4;
  }
}

```

## disassembly

```asm
0x180024a00  mov     r11, rsp
0x180024a03  sub     rsp, 48h
0x180024a07  test    ecx, ecx
0x180024a09  jns     short loc_180024A3B
0x180024a0b  mov     [rsp+48h+var_28], ecx
0x180024a0f  lea     rax, aInetsrvIisMbCo_5; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180024a16  mov     [r11-20h], rax
0x180024a1a  lea     rdx, _TI1?AUTException@@; pThrowInfo
0x180024a21  mov     [r11-18h], r8
0x180024a25  lea     rcx, [r11-28h]; pExceptionObject
0x180024a29  mov     [r11-10h], r9d
0x180024a2d  mov     [rsp+48h+var_C], 0
0x180024a35  call    _CxxThrowException_0
0x180024a3b  add     rsp, 48h
0x180024a3f  retn
```
