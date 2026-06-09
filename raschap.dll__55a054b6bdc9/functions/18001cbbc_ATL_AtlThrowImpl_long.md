# ATL::AtlThrowImpl(long)

- ea: `0x18001cbbc`
- end: `0x18001cbde`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005df0`
- `0x180006600`
- `0x18000b070`
- `0x18001227c`
- `0x18001256c`

## callees

- `0x180014bbe`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl()
{
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  pExceptionObject = -2147024882;
  throw (ATL::CAtlException *)&pExceptionObject;
}

```

## disassembly

```asm
0x18001cbbc  mov     [rsp+pExceptionObject], ecx
0x18001cbc0  sub     rsp, 28h
0x18001cbc4  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18001cbcb  mov     [rsp+28h+pExceptionObject], 8007000Eh
0x18001cbd3  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18001cbd8  call    _CxxThrowException_0
```
