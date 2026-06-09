# ATL::AtlThrowImpl(long)

- ea: `0x140006940`
- end: `0x140006962`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140005e4c`
- `0x1400061bc`
- `0x1400067c8`
- `0x140006800`
- `0x140007110`
- `0x140007880`
- `0x140007a88`

## callees

- `0x140002168`
- `0x140005a78`

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
0x140006940  sub     rsp, 28h
0x140006944  mov     edx, ecx; int
0x140006946  lea     rcx, [rsp+28h+pExceptionObject]; this
0x14000694b  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x140006950  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x140006957  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14000695c  call    _CxxThrowException_0
```
