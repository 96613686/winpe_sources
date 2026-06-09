# ATL::AtlThrowImpl(long)

- ea: `0x1800030b4`
- end: `0x1800030d6`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1800025d8`
- `0x18000296c`
- `0x180002f48`
- `0x180002f7c`
- `0x180003cec`
- `0x180004428`
- `0x18000460c`
- `0x1800054a0`
- `0x180006e5c`

## callees

- `0x180001d18`
- `0x1800020e8`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  char pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, a1);
  throw (ATL::CAtlException *)&pExceptionObject;
}

```

## disassembly

```asm
0x1800030b4  sub     rsp, 28h
0x1800030b8  mov     edx, ecx; int
0x1800030ba  lea     rcx, [rsp+28h+pExceptionObject]; this
0x1800030bf  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x1800030c4  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x1800030cb  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800030d0  call    _CxxThrowException_0
```
