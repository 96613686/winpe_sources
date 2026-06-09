# ATL::AtlThrowImpl(long)

- ea: `0x1800068ec`
- end: `0x18000690e`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180005da0`
- `0x18000615c`
- `0x180006768`
- `0x1800067a0`
- `0x1800086fc`
- `0x180008f00`
- `0x180009108`
- `0x18000ce9c`
- `0x18000d2f0`
- `0x18001032c`
- `0x180010644`
- `0x180011e48`
- `0x180012144`
- `0x180012560`

## callees

- `0x180001f9c`
- `0x1800054e8`

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
0x1800068ec  sub     rsp, 28h
0x1800068f0  mov     edx, ecx; int
0x1800068f2  lea     rcx, [rsp+28h+pExceptionObject]; this
0x1800068f7  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x1800068fc  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180006903  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180006908  call    _CxxThrowException_0
```
