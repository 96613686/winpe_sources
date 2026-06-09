# ATL::AtlThrowImpl(long)

- ea: `0x18000278c`
- end: `0x1800027ae`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x1800022c4`
- `0x180003414`
- `0x1800037ac`
- `0x180003d88`
- `0x180003dbc`
- `0x180004d4c`
- `0x180005488`
- `0x18000566c`
- `0x180007a1c`
- `0x180007dac`
- `0x1800091fc`
- `0x1800094a8`
- `0x1800099e4`
- `0x18000a4bc`

## callees

- `0x180001d04`
- `0x1800020d8`

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
0x18000278c  sub     rsp, 28h
0x180002790  mov     edx, ecx; int
0x180002792  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180002797  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000279c  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x1800027a3  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800027a8  call    _CxxThrowException_0
```
