# ATL::AtlThrowImpl(long)

- ea: `0x18000418c`
- end: `0x1800041ae`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d90`
- `0x1800030ec`
- `0x1800036f8`
- `0x180003730`
- `0x18000387c`
- `0x180003a50`
- `0x180003f80`
- `0x180004694`
- `0x180004cf0`
- `0x180004ef8`

## callees

- `0x18000265c`
- `0x180002a68`

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
0x18000418c  sub     rsp, 28h
0x180004190  mov     edx, ecx; int
0x180004192  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180004197  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000419c  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x1800041a3  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800041a8  call    _CxxThrowException_0
```
