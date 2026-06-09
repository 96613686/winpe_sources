# ATL::AtlThrowImpl(long)

- ea: `0x180003eb0`
- end: `0x180003ed2`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000366c`
- `0x180003c48`
- `0x18000498c`
- `0x180005038`
- `0x18000521c`
- `0x1800063d4`

## callees

- `0x180003030`
- `0x1800123a4`

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
0x180003eb0  sub     rsp, 28h
0x180003eb4  mov     edx, ecx; int
0x180003eb6  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180003ebb  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180003ec0  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180003ec7  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180003ecc  call    _CxxThrowException_0
```
