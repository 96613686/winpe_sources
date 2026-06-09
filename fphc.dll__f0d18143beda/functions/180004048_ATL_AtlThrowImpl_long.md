# ATL::AtlThrowImpl(long)

- ea: `0x180004048`
- end: `0x18000406a`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d88`
- `0x1800030ac`
- `0x180003688`
- `0x1800036bc`
- `0x1800037f4`
- `0x18000399c`
- `0x180003e64`
- `0x1800044a4`
- `0x180004a88`
- `0x180004c68`
- `0x18000d52c`
- `0x18000d5d4`
- `0x18000db3c`
- `0x18000dd44`
- `0x18000e470`
- `0x18000e5fc`
- `0x18000e7fc`
- `0x18000eb7c`

## callees

- `0x1800026cc`
- `0x180002ab8`

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
0x180004048  sub     rsp, 28h
0x18000404c  mov     edx, ecx; int
0x18000404e  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180004053  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180004058  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000405f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180004064  call    _CxxThrowException_0
```
