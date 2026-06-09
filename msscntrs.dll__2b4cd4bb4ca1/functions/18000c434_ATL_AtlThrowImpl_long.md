# ATL::AtlThrowImpl(long)

- ea: `0x18000c434`
- end: `0x18000c456`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bd2c`
- `0x18000c308`
- `0x18000e624`
- `0x18000edc8`
- `0x18000efac`
- `0x180010cbc`

## callees

- `0x18000332c`
- `0x18000b380`

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
0x18000c434  sub     rsp, 28h
0x18000c438  mov     edx, ecx; int
0x18000c43a  lea     rcx, [rsp+28h+pExceptionObject]; this
0x18000c43f  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000c444  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000c44b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c450  call    _CxxThrowException_0
```
