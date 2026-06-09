# ATL::AtlThrowImpl(long)

- ea: `0x1800039a4`
- end: `0x1800039c6`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000252c`
- `0x1800028fc`
- `0x180002ed8`
- `0x180002f0c`
- `0x180003150`
- `0x1800032f8`
- `0x1800037c0`
- `0x18000466c`
- `0x180004d18`
- `0x180004efc`

## callees

- `0x1800020a5`
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
0x1800039a4  sub     rsp, 28h
0x1800039a8  mov     edx, ecx; int
0x1800039aa  lea     rcx, [rsp+28h+pExceptionObject]; this
0x1800039af  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x1800039b4  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x1800039bb  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800039c0  call    _CxxThrowException_0
```
